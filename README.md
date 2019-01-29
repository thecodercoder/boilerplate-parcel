# boilerplate-parcel

![Bundle your files more quickly with Parcel JS](https://imgur.com/D7ggQBB)

Parcel.js is billed as a "zero configuration" bundler. It can transform and compile your HTML, SCSS, JS and many other file types, with a minimum of time spent setting up a config file.

If you're just working on a simple front-end web app and don't require a lot of control over your build, you can swap in Parcel for WebPack or Gulp.

## How to install Parcel

You can install Parcel either using npm or yarn. You'll also need to create a package.json file. 

*Note: if you don't have [Node.js](https://nodejs.org/en/) installed, you will need to do that before following these steps!*

**npm:**
```
npm install -g parcel-bundler
npm init -y
```

**yarn:**
```
yarn global add parcel-bundler
yarn init -y
```

## Set up your files

We'll create a very simple website with just these files:

* index.html
* script.js
* style.scss

The script.js file will be where you include your Sass file:

```
import '/style.scss';
```

## Run Parcel!

To run Parcel, on your command line, use this command:

```
parcel index.html
```

This will build your project, and start a local dev server at http://localhost:1234/. The cool part about this is that anytime you make changes to your files, Parcel will automatically rebuild and update the local site for you.

## Add autoprefixer

I wanted to add autoprefixer to add vendor prefixes to CSS properties that need it. Unfortunately Parcel doesn't do that by default, but it was fairly simple to add autoprefixer to my project.

First I installed PostCSS, which runs autoprefixer:

```
yarn add postcss-modules autoprefixer
```

Then I created a config file in my project root with the following code:

```
{  
  "plugins": {
    "autoprefixer": true
  }
}
```

Note: this code is different from what Parcel has in their PostCSS setup instructions. 

However, when using their code snippet, when I built the project, the CSS class name that was using prefixed properties got renamed. This made all the CSS styles for that class name not work. So if you're using autoprefixer I'd recommend using the code snippet I have above here.

## More resources

I created this GitHub project to accompany a tutorial on getting up and running with Parcel.

Check it out here: 