---
title: How to Upload Large Files to Google Colab without Directly Uploading to Google Services
date: 2023-03-11 21:00:00 +0800
categories: [Technical, Deep Learning]
tags: [colab]     # TAG names should always be lowercase
---

Google is completely blocked in China and Google Drive and Colab are only accessible if you use a proxy server, often making your connection unstable and slow. Today I found a way to indirectly upload large files to Google Colab.

First, you need to upload your files to another cloud service that is easily accessible (in my case, it's Feishu Docs). Next, download the file, at the same time keeping an eye on the ‘Network’ tab of the developer tools, where you can find the request to download it. Now copy that request as `cURL`, then in a Colab notebook, you can use this command, complete with the necessary cookies to get your file into the VM super fast (so long as your cloud service uses CDN, of course).

I must add that this technique may also be employed to upload files to Google Drive with equal efficacy.