---
title:  "Waslala"
layout: archive
permalink: /Waslala/
author_profile: true
comments: true
---

Introduction

In this guide, we will be setting up a simple WSGI application served by uWSGI. We will use the Nginx web server as a reverse proxy to the application server to provide more robust connection handling. We will be installing and configuring these components on an Ubuntu 14.04 server.
Definitions and Concepts
Clarifying Some Terms

Before we jump in, we should address some confusing terminology associated with the interrelated concepts we will be dealing with. These three separate terms that appear interchangeable, but actually have distinct meanings:

    WSGI: A Python spec that defines a standard interface for communication between an application or framework and an application/web server. This was created in order to simplify and standardize communication between these components for consistency and interchangeability. This basically defines an API interface that can be used over other protocols.
    uWSGI: An application server container that aims to provide a full stack for developing and deploying web applications and services. The main component is an application server that can handle apps of different languages. It communicates with the application using the methods defined by the WSGI spec, and with other web servers over a variety of other protocols. This is the piece that translates requests from a conventional web server into a format that the application can process.
    uwsgi: A fast, binary protocol implemented by the uWSGI server to communicate with a more full-featured web server. This is a wire protocol, not a transport protocol. It is the preferred way to speak to web servers that are proxying requests to uWSGI.
