- #ElizaOS
- ## pnpm intro
	- Yes, I can explain how pnpm scripts work. pnpm is a package manager for Node.js that uses a similar script system to npm.
	  
	  Scripts in pnpm are defined in the `package.json` file under the "scripts" section. Here's a basic example:
	  
	  ```json
	  {
	    "scripts": {
	      "start": "node index.js",
	      "dev": "nodemon index.js",
	      "test": "jest",
	      "build": "tsc"
	    }
	  }
	  ```
	  
	  To run these scripts, you use:
	- `pnpm run <script-name>` or the shorter version `pnpm <script-name>`
	- For common scripts like "start", "test", you can omit "run": `pnpm start`
	  
	  Some key features of pnpm scripts:
	  1. You can run multiple scripts sequentially using `&&`: 
	   ```json
	   "build": "tsc && node dist/index.js"
	   ```
	  
	  2. Or run them in parallel using `&`:
	   ```json
	   "dev": "tsc --watch & nodemon dist/index.js"
	   ```
	  
	  3. pnpm also supports pre/post hooks like npm:
	   ```json
	   {
	     "scripts": {
	       "prebuild": "rimraf dist",
	       "build": "tsc",
	       "postbuild": "cp package.json dist/"
	     }
	   }
	   ```
	  
	  Would you like me to explain any specific aspect of pnpm scripts in more detail?
- ## pnpm run dev
	- in package.json --> "dev": "bash ./scripts/dev.sh"
	- https://github.com/elizaOS/eliza/blob/develop/scripts/dev.sh
	- Script runtime:
		- Let me explain how this script executes at runtime:
		- 0. once execute``pnpm dev``
		- 1. Initial Execution Flow:
		  ```bash
		  # First checks and setup
		  echo "Passing arguments: $*"
		  # Shows help message
		  # Checks if packages directory exists
		  
		  # Builds the commands array
		  COMMANDS=()
		  ```
		- 2. Command Collection Phase:
		  ```bash
		  # 1. Adds core package command
		  COMMANDS+=("pnpm --dir $CORE_PACKAGE dev -- $*")
		  
		  # 2. Adds working folders commands
		  for FOLDER in "${WORKING_FOLDERS[@]}"; do
		      COMMANDS+=("pnpm --dir $PACKAGE dev -- $*")
		  done
		  
		  # 3. Adds client command if directory exists
		  COMMANDS+=("pnpm --dir client dev -- $*")
		  
		  # 4. Adds agent command with nodemon watching
		  COMMANDS+=("nodemon ${WATCH_PATHS[@]} ... dev -- $*")
		  ```
		- 3. Execution Phase:
		  ```bash
		  # First runs build
		  pnpm build
		  
		  # Then runs all commands concurrently
		  npx concurrently --raw "${COMMANDS[@]}"
		  ```
		  
		  In practice, it runs like this:
		  1. You execute `./dev.sh`
		  2. It builds all packages first with `pnpm build`
		  3. Then starts multiple development servers concurrently:
		     ```
		     Core package dev server
		     │
		     Client-direct dev server
		     │
		     Client dev server
		     │
		     Agent (watching for changes in other packages)
		     ```
		  
		  For example, if a file changes:
		  1. In core package → Its dev server recompiles
		  2. When core's dist folder changes → Agent sees this and restarts
		  3. All servers continue running independently
		- Would you like to see a specific example of what happens when you make a code change in one of the packages?
-