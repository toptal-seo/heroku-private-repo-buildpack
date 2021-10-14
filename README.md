This supports loading a build pack from a private git repository.

It hooks in only to the release and compile api.

To use:-

1. Add this to heroku as a buildpack

    heroku buildpacks:set heroku/ruby
    
2. Add a file in the project root   .heroku-private-build.yml with the following shape:-

   heroku config:set BUILDPACK_REPO=git@github.com:user/private-repor

3. Add the base64 encoded deploy key to the BUILDPACK_SSH_KEY env variable
    
   heroku config:set BUILDPACK_SSH_KEY=$(cat path/to/your/keys/id_rsa | base64)
    
    
Then push to heroku.
   
# heroku-private-buildpack
