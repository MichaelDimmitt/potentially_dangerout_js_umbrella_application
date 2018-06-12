## potentially dangerous 😉, Javascript Umbrella Application:
top level package.json 

will interact with package.json of child projects using bash.

![umbrella](https://raw.githubusercontent.com/MichaelDimmitt/potentially_dangerout_js_umbrella_application/master/assets/new_umbrella.png)

## Not currently working, but how it should work:
### Warning, many of these commands are dangerous<br>Make sure you know what you are doing.

In each directory, Run npm install as a background process
```bash
for d in ./*/; do (cd $d && npm install &>/dev/null &); done;,
```
In each directory, Run npm start as a background process
```bash
for d in ./*/; do (cd $d && npm start &>/dev/null &); done;,
```
In each directory, Tell the jobs what jobs are running.
```bash
for d in ./*/; do (cd $d && jobs); done;
```
In each directory, stop all jobs that have been created.
```bash
for d in ./*/; do (cd $d && kill $(jobs -p)| xargs kill);
```

### The above bash scripts have been added in as script commands in the package.json.

## To Do, what needs to be solved to get the program working:
The current obstacle in the project is related to the bash behavior.
<br/>The state management that is occouring in the `for d in ./*/` is not allowing the jobs command to give a report of current jobs.
<br/>Because of low confidence in the result of the jobs command. 
<br/>Currently have low confidence in the npm start command.

Status: The project is close to completion but not yet stable and has a current low confidence rating for effectiveness.

## Installation:
```
git clone https://github.com/MichaelDimmitt/potentially_dangerout_js_umbrella_application.git;
npm install;
npm start;
```

After installation, you can verify that the program is working two ways: 
## Using bash:
```bash
jobs;
```

## Using the browser
```html
http://localhost:8010/v1/request0
http://localhost:8011/v1/request1
http://localhost:8012/v1/request2
```

## useful links: 

