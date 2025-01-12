# 🏠 Homelab

This repo contains all of the configuration and documentation of my homelab.

The purpose of my homelab is to learn and to have fun. I'm transitioning my career to where my true passion is, DevOps. Given this, I try to work with Kubernetes every day, and my homelab is the place where I can try out and learn new things. By self-hosting some applications, i'm responsible for the entire process of deploying and maintaining an application from A to Z. It forces me to think about backup strategies, security, scalability and the ease of deployment and maintenance.

## Principles

So far, I have a few principles that guide my choices for my homelab.

* I aim to adopt best practices in deployment and security, applying the [twelve-factor](https://12factor.net/) to the best of my ability
* Everything is deployed through GitOps
* Only expose applications to the internet via tunnel or proxy

## Distribution

I use [K3s](https://k3s.io/) as my Kubernetes distribution. I chose K3s because although it's lightweight, it comes shipped with support for tools such as Helm. It's also a huge plus that it integrates particularly well with Rancher.

## Hardware

Currently, I have a single node built from scratch with [these parts](https://pcpartpicker.com/user/edin1/saved/XnqzZL). The goal was to have something practically powerful, but nonchalant and as quiet as a whisper. It sits in my living room and you wouldn't even notice it's there. I love it.

## Secrets

Since my entire setup is open-source, I keep a [SOPS age](https://github.com/getsops/sops?tab=readme-ov-file#encrypting-using-age) private key in a Secret locally on my cluster. This key is used to decrypt secrets while allowing me to share my configuration on GitHub.

## Repo Structure

Decided to fully commit to Flux CD and their best practices. Once I get more hardware, I'll be able to scale at a moment's notice thanks to this structure.

Set up the repo according to [this guide](https://fluxcd.io/flux/guides/repository-structure/).

And following [this example](https://github.com/fluxcd/flux2-kustomize-helm-example).
