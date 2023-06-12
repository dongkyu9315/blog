---
title: "Basics of SSH"
layout: post
description: "Basic description of ssh (secure shell)"
categories: [Tech, Protocol]
tags: [ssh]
comments: true
---

> "Secure Shell (SSH) is a cryptographic network protocol for operating network services securely over an unsecured network"
> <p style="text-align: right;">- wikipedia</p>

#### An SSH client can connect to an SSH server using a secure channel, provided by SSH, over an unsecured network.

<br />

#### Usage

+ Common usage of SSH is the access to shell accounts on Unix-like operating systems, but it sees some limited use on Windows as well. SSH is typically used to log in to a remote machine and execute commands, but it also supports tunneling, forwarding TCP ports and X11 connections; it can transfer files using the associated SSH file transfer (SFTP) or secure copy (SCP) protocols.

+ SSH uses the client-server model.

+ The encryption used by SSH is intended to provide confidentiality and integrity of data over an unsecured network.

+ SSH uses public-key cryptography to authenticate the remote computer and allow it to authenticate the user. There are several version of SSH, but in all versions, it is important to verify unknown public keys, before accepting them as valid.

+ SSH is important in cloud computing to solve connectivity problems, avoiding the security issues of exposing a cloud-based virtual machine directly on the Internet. An SSH tunnel can provide a secure path over the Internet, through a firewall to a virtual machine.

<br />

#### File transfer protocols

+ Secure copy (SCP), which evolved from RCP protocol over SSH

+ rsync, intended to be more efficient than SCP

+ SSH File Transfer Protocol (SFTP), a secure alternative to FTP

+ Files transferred over shell protocol, which evolved from Unix shell commands over SSH

<br />

#### Architecture

##### The SSH-2 protocol has an internal structure with well-specified layers

+ The Transport Layer
    - handles initial key exchange as well as server authentication, and sets up encryption, compression and integrity verification
    - arranges for key re-exchange, usually after 1 GB of data has been transferred or after 1 hour has passed, whichever occurs first

+ The User Authentication Layer
    - handles client authentication and provides a number of authentication methods
    - Authentication is client-driven: the server merely responds to the client's authentication requests
    - Widely used user-authentication methods include the following:
        + password: a method for straightforward password authentication
        + publickey: a method for public key-based authentication, usually supporting at least DSA or RSA keypairs
        + keyboard-interactive: a versatile method where the server sends one or more prompts to enter information and the client displays them and sends back responses keyed-in by the user
        + GSSAPI authentication: methods which provide an extensible scheme to perform SSH authentication using external mechanisms such as Kerberos 5 or NTLM, providing single sign-on capability to SSH sessions

+ The Connection Layer
    - defines the concept of channels, channel requests and global requests using which SSH services are provided
    - A single SSH connection can host multiple channels simultaneously, each transferring data in both directions
    - Channel requests are used to relay out-of-band channel-specific data, such as the changed size of a terminal window or the exit code of a server-side process
    - The SSH client requests a server-side port to be forwarded using a global request
    - Standard channel types include:
        + shell for terminal shells, SFTP and exec requests (including SCP transfers)
        + direct-tcpip for client-to-server forwarded connections
        + forwarded-tcpip for server-to-client forwarded connections

+ The SSHFP DNS Record
    - provides the public host key fingerprints in order to aid in verifying the authenticity of the host

<br />

***

#### Reference  
- [Wikipedia page on SSH](https://en.wikipedia.org/wiki/Secure_Shell "Wikipedia page on SSH")

***
