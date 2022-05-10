---
title: "Site Uplift"
date: 2022-05-10T13:45:11+08:00
cover: 
    image: img/amplify.png
    alt: 'amplify'
    caption: 'amplify'
---

So there's a few changes that's taking place right now. My site has been down for quite awhile now. Mainly due to issues with having to use azure's contianer (for the CI/CD with hugo) and integration with my github repo for the hugo directory and public static generate pages. 

There's a few things I have done now. As I've also been experimenting with my own personal cloud using AWS EC2 with S3 (I am using Next as my personal cloud app of choice), I decided that its also timely that I'd switch from Azure and Github spaces to AWS. So for my new setup, I am changing my hugo theme (had issues with ghostwriter) and am using AWS Amplify with AWS for my deployment and CI/CD process. I will be using Route53 to connect my site domain to the internally generated URL.