This Heroku buildpack was inspired by another [buildpack](https://github.com/SectorLabs/heroku-buildpack-git-submodule.git)
This build pack supports the use of GitHub's OAuth tokens instead of SSH.

## Usage

1. Add the buildpack to your Heroku app:

        heroku buildpacks:add https://github.com/tudortibu/heroku-git-submodules.git
        
    Keep in mind that the buildpack order is important. If you'll specify this buildpack after your default one (e.g. `heroku/nodejs`) it'll not work. See [https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app](https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app) for details.

2. Set the `GIT_REPO_URL` to the HTTPS URL of your Git repo:

        heroku config:set GIT_REPO_URL=https://github.com/{username}/{repo}.git

3. Set `GIT_USERNAME` to your github.com username:
       
       heroku config:set GIT_USERNAME={username}
        
4. Set `GIT_OAUTH` to your github.com OAuth token for you:  
        
        heroku config:set GIT_SSH_KEY={OAuth_token}

