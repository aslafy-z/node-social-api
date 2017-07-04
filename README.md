# @aestetype/node-social-api

[![npm version](https://badge.fury.io/js/%40aestetype%2Fnode-social-api.svg)](https://badge.fury.io/js/%40aestetype%2Fnode-social-api)
[![CircleCI](https://circleci.com/gh/aestetype/node-social-api.svg?style=svg)](https://circleci.com/gh/aestetype/node-social-api)
[![codecov](https://codecov.io/gh/aestetype/node-social-api/branch/master/graph/badge.svg)](https://codecov.io/gh/aestetype/node-social-api)
[![Dependency Status](https://david-dm.org/aestetype/node-social-api.svg)](https://david-dm.org/aestetype/node-social-api)
[![devDependency Status](https://david-dm.org/aestetype/node-social-api/dev-status.svg)](https://david-dm.org/aestetype/node-social-api#info=devDependencies)

Social api client for node with typescript definitions that support promises.
Include:
* Twitter
* Instagram
* Facebook
* Tumblr
* Github

## Install

`yarn add @aestetype/node-social-api`

## Usage

```javascript
import { Instagram, Twitter, Facebook, Tumblr, Github } from '@aestetype/node-social-api';

// Instagram
const instagram = new Instagram({
  clientId: 'your-client-id',
  accessToken: 'user-access-token',
});

// Some get query with promise
instagram.get('users/self').then((data) => {
  console.log(data);
});

// Twitter
const twitter = new Twitter({
  consumerKey: 'your-consumer-key',
  consumerSecret: 'your-consumer-secret',
  accessToken: 'your-access-token',
  accessTokenSecret: 'your-access-token-secret',
});

// Some get query
twitter.get('media/recent').then((data) => {
  console.log(data);
});

// Facebook
const facebook = new Facebook({
  appId: 'your-app-id',
  appSecret: 'your-app-secret',
});
// Or with a valid accessToken
const facebook = new Facebook({
  accessToken: 'your-access-token',
});

// Some get query
facebook.get(':some-id').then((data) => {
  console.log(data);
});

// Tumblr
const tumblr = new Tumblr({
  consumerKey: 'your-consumer-key',
});

// Some get query
tumblr.get('blog/scipsy.tumblr.com/info').then((data) => {
  console.log(data);
});

// Github
const github = new Github({
  accessToken: 'your-access-token',
});
// Or if you want to use the public api
const github = new Github({
  public: true,
});

// Some get query
github.get(':some-github-route').then((data) => {
  console.log(data);
});
```
