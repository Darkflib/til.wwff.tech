+++
date = '2024-12-01T21:09:19Z'
draft = false
title = 'Model Context Protocol'
+++

## MCP (Model Context Protocol)

Spec at [modelcontextprotocol.io](https://modelcontextprotocol.io/)

While right now only Claude desktop and a couple of other apps support it, it's an elegant way to extend the capabilities of a LLM. 

You can think of it like a plugin system, but it solves a lot of the problems that come with plugins such as security, performance, and compatibility.

Security in this case comes by having a small 'server' that is separate from the main app, and that can be run in a sandbox (if needed). This server can be written in any language, and can even be run on a different machine than the main app (although right now, it isn't really supported.)

By having it as a separate process, it can be run in a different security context and you don't need to expose the main app to the internet directly or expose API keys, as the server can be the only thing that talks to the internet.

In addition, since the main app and the server talk a standardised protocol based around JSON-RPC, it's easy to write a server in any language, and it's easy to write a client in any language.
