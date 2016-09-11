# grapes [![Go Report Card](https://goreportcard.com/badge/github.com/yaronsumel/grapes)](https://goreportcard.com/report/github.com/yaronsumel/grapes) [![Build Status](https://travis-ci.org/yaronsumel/grapes.svg?branch=master)](https://travis-ci.org/yaronsumel/grapes) [![Build status](https://ci.appveyor.com/api/projects/status/fnepp81rdi8prawn/branch/master?svg=true)](https://ci.appveyor.com/project/yaronsumel/grapes/branch/master) [![GoDoc](https://godoc.org/github.com/yaronsumel/grapes?status.svg)](https://godoc.org/github.com/yaronsumel/grapes)

grapes is lightweight tool designed to distribute commands over ssh with ease.

### Installation ###

  Run (golang required):

    $ go get -u github.com/yaronsumel/grapes

  ... or Grab Portable Binary - v.0.2.2 (md5sum):
* [linux](https://github.com/yaronsumel/grapes/releases/download/v0.2.2/grapes.7z) (d71a04fc489b5696a06c045ed892d103)
* [windows](https://github.com/yaronsumel/grapes/releases/download/v0.2.2/win.zip) (f9f7b8de79df69a13c2a6e7a0d06ab6c)
* [darwin](https://github.com/yaronsumel/grapes/releases/download/v0.2.2/darwin.zip) (b98791fdb97e04332960ca10e92c8766)

### Usage ###

 Example:

    $ grapes -c config.yml -i ~/.ssh/id_rsa -s prod -cmd whats_up --async

* use the --help flag for full usage output.

### Config ###

config structure (YAML):

 ```
version: 1
servers:
  prod :
      - name : "prod server #1"
        host : "prod.example.com:22"
        user : "ubuntu"
  staging :
      - name : "staging server #1"
        host : "staging.example.com:22"
        user : "ubuntu"
      - name : "staging server #2"
        host : "staging.example.com:23"
        user : "ubuntu"
commands:
  whats_up :
      - "ls -al /tmp"
      - "date"
  date :
      - "date"
 ```
 
> ##### Written and Maintained by [@YaronSumel](https://twitter.com/yaronsumel) #####
