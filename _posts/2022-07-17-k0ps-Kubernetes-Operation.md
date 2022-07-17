---
layout: post
title: kOps Kubernetes Operation
date: 2022-07-17 09:55:00 +0700
categories: kubernetes, kOps, technical
---
# kOps sang Kubernetes Operator
> kubernetes cluster adalah management orchestration yang sering digunakan untuk menjalankan dan menjaga lifecycle aplikasi, membuat kubernetes cluster merupakan
> suatu tantangan bagi perusahaan maupun individual engineer, berbagai macam cara tersedia untuk membuat cluster ini, mulai dari yang ***hard way***,
> ribet way, simple ribet way, lumayan enak way, sangat enak way. \n
> kOps alat pembangun kubernetes cluster yang lumayan enak way

## Apa itu kOps?
Automation, satu kata yang dapat mendeskripsikan kOps, dengan fokus pembuatan cluster dan instalasi beberapa addon yang di perlukan, kOps adalah tool yang dapat
digunakan untuk membuat cluster kubernetes di atas *Cloud*. AWS, GCP, Azure, Openstack, dapat dan disupport oleh komunitas kOps. kOps adalah kepanjangan dari
Kubernetes Operation, dengan kata lain alat untuk pengoprasian Kubernetes.

Pengoprasian Kubernetes meliputi beberapa hal. membangun cluster, merawat cluster, management cluster, update cluster, instalasi addon cluster dan sebagainya.
kOps adalah sebuah command automation.

## Bagaimana ini bekerja?
Dekade ini infrastructure berkembang sangat pesat, salah satunya Cloud Computing, Cloud Computing dapat memungkinkan kita membuat sumber daya dengan menggunakan code.
beberapa orang menyebutnya Infrastructure as code (IaC). dengan kemampuan cloud computing yang sekarang beberapa kegiatan pembuatan infrastructure lebih termudahkan, 
termasuk membangun cluster kubernetes, kOps merupakan tool automation yang dapat mengautomasi Cloud sehingga dapat membuat cluster dengan menggunakan resource
atau infrastructur yang ada di cloud. ***provision*** merupakan kata yang tepat untuk proses awal pembuatan cluster kubernetes menggunakan kOps, dengan membuat 
beberapa VM atau instance diatas cloud tersebut.

Kita tarik waktu kebelakang, salah satu yang jadi concern dan merupakan hal yang paling penting dalam pembuatan cluster dan patut dipertanyakan "*bagaimana kOps dapat
berkomunikasi dengan cloud?*", \n
*let me tell you a story*, cloud computing memiliki kemampuan mendengarkan beberapa request user dari beberapa jenis dan alat komunikasi. dashboard, command line, programatic acces,
dan lain sebagainya, Cloud mampu menerjemahkan beberapa request dari berbagai sumber tersebut ke bahasa yang *dia* mengerti. dengan melewati API (Application Programming
Interface).

kOps merupakan tool yang dapat mengobrol dan membuat request ke cloud computing, dan setiap merk cloud computing memiliki cara masing masing. kOps akan berkomunikasi dengan
cloud melalui API dari cloud tersebut, dan seperti biasa API memiliki beberapa security mechanism yang berbeda beda, kOps dan Cloud adalah hal yang sama, kOps perlu
ditambahkan beberapa parameter supaya diizinkan untuk menggunakan API dari cloud tersebut.

Authentication and Authorization, baca sendiri di [sini](https://www.geeksforgeeks.org/difference-between-authentication-and-authorization/)

Security Mechanism passed, baru kOps akan membuat resource resource yang dibutuhkan di Cloud Computing. resource yang dimaksud antara lain VM, Network, Subnet, dan
lain sebagainya. kemudian kOps akan menginstall aplikasi/dependecies yang dibutuhkan untuk membuat cluster di atas resource yang dibikin sebelumnya.

## Individual perspective
membangun cluster ada beberapa cara, menggunakan EKS, atau pakai kOps atau mungkin yang lain. \n
kOps tool yang bagus, gampang dan memiliki komunitas yang aktif, sempat takjub dengan isu yang ku submit sebelumnya, yang di fix lebih cepat dari dugaan.

## Why kOps?
Bekerja di Start Up memiliki tantangan financial tersendiri. bahkan beberapa perusahaan melakukan lay off. untuk mengurangi beberapa pengeluaran. masalah financial 
mungkin kOps bisa membantu kita dalam membuat cluster, beberapa pengalaman kebelakang EKS lebih mahal dibandingkan kOps. alasan yang lebih rinci terkait financial 
yaitu EKS langsung charge sekitar $148 untuk EKS service saja sedangkan kOps dibawah $100 untuk master yang dimana dapat digantikan EKS service di EKS.

Saat ini telah berjalan 10 aplikasi dengan masing masing HPAnya, sejauh ini belum ada penemuan kendala berarti dalam pengoprasian Kubernetes menggunakan 
kOps yang mengharuskan berpindah ke managed Kubernetes seperti EKS. keadaan financial mungkin menjadi pertimbangan utama dalam penggunaan kOps ini.

## Conclusion
ziggy zagga, kOps automation, 
building kubernetes dengan menggunakan raw material dari cloud computing, yang diharapkan lebih hemat.
