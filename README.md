# Yii 2 Starter Kit

<!-- BADGES/ -->

[![Packagist](https://img.shields.io/packagist/v/yii2-starter-kit/yii2-starter-kit.svg)](https://packagist.org/packages/yii2-starter-kit/yii2-starter-kit)
[![Packagist](https://img.shields.io/packagist/dt/yii2-starter-kit/yii2-starter-kit.svg)](https://packagist.org/packages/yii2-starter-kit/yii2-starter-kit)
[![Build Status](https://travis-ci.org/yii2-starter-kit/yii2-starter-kit.svg?branch=master)](https://travis-ci.org/yii2-starter-kit/yii2-starter-kit)

<!-- /BADGES -->

This is Yii2 start application template.

It was created and developing as a fast start for building an advanced sites based on Yii2.

It covers typical use cases for a new project and will help you not to waste your time doing the same work in every project

This fork is a version of the Yii2 starter kit with a few smaller updates and a bit of tailoring towards using it with Vagrant exclusively.

It's for personal use first and foremost but maybe this is useful to someone else, too. :)

## Before you start
Please, consider helping project via [contributions](https://github.com/yii2-starter-kit/yii2-starter-kit/issues) or [donations](#donations).

## TABLE OF CONTENTS
- [Demo](#demo)
- [Features](#features)
- [Installation](docs/installation.md)
    - [Manual installation](docs/installation.md#manual-installation)
    - [Vagrant installation](docs/installation.md#vagrant-installation)
- [Components documentation](docs/components.md)
- [Console commands](docs/console.md)
- [Testing](docs/testing.md)
- [FAQ](docs/faq.md)
- [How to contribute?](#how-to-contribute)
- [Have any questions?](#have-any-questions)
- [Why did you remove Docker support?](#why-did-you-remove-docker-support)

## Quickstart
1. Install [Vagrant](https://www.vagrantup.com/)
2. Copy `./vagrant/vagrant.yml.dist` to `./vagrant/vagrant.yml`
3. Copy `./.env.dist` to `./.env`
3. Create GitHub [personal API token](https://github.com/blog/1509-personal-api-tokens)
4. Edit values as desired including adding the GitHub personal API token to `./vagrant/vagrant.yml`
5. Edit domains as desired in `./.env`
   
   If you edit domains in `./.env`, you need to make appropriate changes to `./vagrant/vhost.conf` and `./Vagrantfile`
6. Run:
```
vagrant plugin install vagrant-hostmanager
vagrant up
```
That`s all. After provision application will be accessible on http://yii2-starter-kit.localhost

## FEATURES
### Admin backend
- Beautiful and open source dashboard theme for backend [AdminLTE 2](http://almsaeedstudio.com/AdminLTE)
- Content management components: articles, categories, static pages, editable menu, editable carousels, text blocks
- Settings editor. Application settings form (based on KeyStorage component)
- [File manager](https://github.com/MihailDev/yii2-elfinder)
- Users, RBAC management
- Events timeline
- Logs viewer
- System monitoring

### I18N
- Built-in translations:
    - English
    - Spanish
    - Russian
    - Ukrainian
    - Chinese
    - Vietnamese
    - Polish
    - Portuguese (Brazil)
- Language switcher, built-in behavior to choose locale based on browser preferred language
- Backend translations manager

### Users
- Sign in
- Sign up
- Profile editing(avatar, locale, personal data)
- Optional activation by email
- OAuth authorization
- RBAC with predefined `guest`, `user`, `manager` and `administrator` roles
- RBAC migrations support

### Development
- Ready-to-use Vagrant-based stack (php, nginx, mysql, mailcatcher)
- .env support
- [Webpack](https://webpack.js.org/) build configuration
- Key-value storage service
- Ready to use REST API module
- [File storage component + file upload widget](https://github.com/trntv/yii2-file-kit)
- On-demand thumbnail creation [trntv/yii2-glide](https://github.com/trntv/yii2-glide)
- Built-in queue component [yiisoft/yii2-queue](https://github.com/yiisoft/yii2-queue)
- Command Bus with queued and async tasks support [trntv/yii2-command-bus](https://github.com/trntv/yii2-command-bus)
- `ExtendedMessageController` with ability to replace source code language and migrate messages between message sources
- [Some useful shortcuts](https://github.com/yii2-starter-kit/yii2-starter-kit/blob/master/common/helpers.php)

### Other
- Useful behaviors (GlobalAccessBehavior, CacheInvalidateBehavior)
- Maintenance mode support ([more](#maintenance-mode))
- [Aceeditor widget](https://github.com/trntv/yii2-aceeditor)
- [Datetimepicker widget](https://github.com/trntv/yii2-bootstrap-datetimepicker),
- [Imperavi Reactor Widget](https://github.com/asofter/yii2-imperavi-redactor),
- [Xhprof Debug panel](https://github.com/trntv/yii2-debug-xhprof)
- Sitemap generator
- Extended IDE autocompletion
- Test-ready
- Vagrant support
- Built-in [mailcatcher](http://mailcatcher.me/)
- [Swagger](https://swagger.io/) for API docs.

## DEMO
Demo is hosted by awesome [Digital Ocean](https://m.do.co/c/d7f000191ea8)
- Frontend: [http://yii2-starter-kit.terentev.net](http://yii2-starter-kit.terentev.net)
- Backend: [http://backend.yii2-starter-kit.terentev.net](http://backend.yii2-starter-kit.terentev.net)

`administrator` role account
```
Login: webmaster
Password: webmaster
```

`manager` role account
```
Login: manager
Password: manager
```

`user` role account
```
Login: user
Password: user
```

## How to contribute?
You can contribute in any way you want. Any help appreciated, but most of all i need help with docs (^_^)

## Have any questions?
Mail to [eugene@terentev.net](mailto:eugene@terentev.net)

## Why did you remove Docker support?
More of a personal choice. I pretty much exclusively use Windows and frankly, Docker is an absolute nightmare on Windows. Neither the kind-of deprecated Docker Toolbox nor the "new and improved" Docker for Windows work properly when volumes come into play. In comparison, Vagrant has been very easy to use. Sure, some small changes (like I made in this fork) were necessary. But this is a far cry from what is usually necessary to get a docker-compose system set up on a Windows host.

## READ MORE
- [Yii2](https://github.com/yiisoft/yii2/tree/master/docs)


### NOTE
This template was created mostly for developers NOT for end users.
This is a point where you can start your application, rather than creating it from scratch.
Good luck!

