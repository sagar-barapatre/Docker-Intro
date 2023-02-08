1. `docker login`
2. `docker build -t <your_docker_username>/<project_name_of_your_choice>:0.0.1.RELEASE .`
3. `docker conatiner ls`
// Above command will show you an empty table
4. `docker container run -d -p 4000:4000 diethrone/docker-intro-project:0.0.1.RELEASE`
// first 4000 is your local port which is written on app.js file and second 4000 is for the docker-port(that should be empty to run the container)
//After running above command, it should console some big long string. Something similar to this - 53cef41a67e02f0c37cbd3e3f219240855c9555a1bc037a4e88dc3a460757298
5. `docker ps`
//Running this command should show a table with one entry(if you haven't run any conatiner) containing CONTAINER ID and various fields.


// Now the docker is up and running, visit the browser and hit https://localhost:4000 (your port which is written first), you should be able to see the page created by you as you were able to see when running `node app.js`. If it's running up and fine, congrats your conatiner with image is all set.

//To stop the server hit onto the terminal
`docker stop 53ce`
//53ce is the first four letters of the container ID which is to be stopped.



Everything we are doing, is all local so in case we need to push to public repo, we just need to hit
`docker push diethrone/docker-intro-project:0.0.1.RELEASE`

//this will push the container to a different repo on docker. We should see a new repo on https://hub.docker.com/repositories/<your_username>

If it's showing, your conatiner is now public, people can now pull anytime using the command
`docker pull <your_username>/<your_repo_name>`
