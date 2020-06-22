# Introduction

This project is "Goorder coupon and loyalty card mobile version prototype"

![優惠券&集點卡](https://northbei.github.io/GoorderCoupon/screenshot/demo.png)

Here is [demo](https://northbei.github.io/GoorderCoupon/)

> Notice: This project is only a prototype, just use for demo, it's deprecated from 2019/12/15

## Dev Environment

- Node version：v8.9.4
- NPM version：v6.13.4

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

after your run `npm install`
the console will show messenge below, notice that your dependency packages have some vulnerabilities
```bash
found 7 vulnerabilities (4 low, 1 moderate, 2 high)
  run `npm audit fix` to fix them, or `npm audit` for details
```
if you run `npm audit fix` finished, console will show messenge like below
```bash
fixed 0 of 7 vulnerabilities in 947 scanned packages
  4 package updates for 7 vulnerabilities involved breaking changes
  (use `npm audit fix --force` to install breaking changes; or refer to `npm audit` for steps to fix these manually)
```
and you can't run `npm audit fix --force` in this project,
because it will force update packages to lastest,
and new version of packages will not compatible with this project.

if you run `npm audit fix --force` finished,
when you execute `npm run dev`, you will get much errors you can't handle.

## Reference
- Image download from [here](https://brandpacks.com/templates/pizza-restaurant-loyalty-card-template/)
- For detailed explanation on how things work, consult the [docs for vue-loader](http://vuejs.github.io/vue-loader).
