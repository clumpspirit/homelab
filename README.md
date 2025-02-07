# 🏠 Homelab

This repo contains all of the configuration and documentation of my homelab.

The purpose of my homelab is to learn and to have fun. I'm transitioning my career to where my true passion is, DevOps. Given this, I try to work with Kubernetes every day, and my homelab is the place where I can try out and learn new things. By self-hosting some applications, i'm responsible for the entire process of deploying and maintaining an application from A to Z. It forces me to think about backup strategies, security, scalability and the ease of deployment and maintenance.

## Principles

So far, I have a few principles that guide my choices for my homelab.

* I aim to adopt best practices in deployment and security, applying the [twelve-factor](https://12factor.net/) to the best of my ability
* Everything is deployed through GitOps
* Only expose applications to the internet via tunnel or proxy
* I try to leverage AWS solutions when possible to use in a cluster that's running on local hardware
* When selecting self hosted options, I always opt for the ones that allow me to run a separate Postgres database that I can manage independently

## Distribution

I use [K3s](https://k3s.io/) as my Kubernetes distribution. I chose K3s because although it's lightweight, it comes shipped with support for tools such as Helm. It's also a huge plus that it integrates particularly well with Rancher.

## Databases

I've since recently discovered a newfound hobby in maintaining and [playing with databases](https://clumpspirit.com/posts/cloudnativepg/). Currently, I have the [CloudNativePG](https://cloudnative-pg.io/) operator and a few databases clusters deployed & backed up to the cloud.

I'm working towards an ideal setup where I have custom metrics visualized in Grafana for a few of my applications, as well as all of my homelab data backed up to my S3 bucket in the cloud.

## Hardware

Currently, I have a single node built from scratch with [these parts](https://pcpartpicker.com/user/edin1/saved/XnqzZL). The goal was to have something practically powerful, but nonchalant and as quiet as a whisper. It sits in my living room and you wouldn't even notice it's there. I love it.

## Secrets

### 🛠️ Undergoing overhaul

Looking into integrating the [External Secrets Operator](https://external-secrets.io/latest/) so that I can store my secrets in the AWS Secrets Manager, aligning with my goal of implementing cloud solutions when I can.

Since my entire setup is open-source, I keep a [SOPS age](https://github.com/getsops/sops?tab=readme-ov-file#encrypting-using-age) private key in a Secret locally on my cluster. This key is used to decrypt secrets while allowing me to share my configuration on GitHub.

## Repo Structure

Decided to fully commit to Flux CD and their best practices. Once I get more hardware, I'll be able to scale at a moment's notice thanks to this structure.

Set up the repo according to [this guide](https://fluxcd.io/flux/guides/repository-structure/).

And following [this example](https://github.com/fluxcd/flux2-kustomize-helm-example).
