# My Guild to Set Up Node.js for Linux Ubuntu 16.04

## Install Node.js

```
sudo apt-get update
sudo apt-get install nodejs
sudo apt-get install npm
```

## Install yarn

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update && sudo apt-get install yarn
```

## Install Ruby and SASS (Recommended)

```
sudo apt-get update
sudo apt-get install ruby-full rubygems
sudo gem install sass
```

## Install Global Modules (Recommended)

**JSHint**
```
yarn global add jshint
```

**JavaScript Task Runner**
```
yarn global add grunt-cli
```

**For Angular Developer**
```
yarn global add @angular/cli
```

**For React Developer**
```
yarn global add create-react-app
```

**Monitor for any changes in your source and automatically restart your server**
```
yarn global add nodemon
```