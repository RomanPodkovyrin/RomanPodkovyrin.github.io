---
layout: post
title: Modern Age Data Deluge
date: 2023-07-31 19:50 +0100
categories: [Photography, Data]
tags: [storage, home, future, nas]     ## TAG names should always be lowercase
# img_path: /assets/postsImgs/test
## published: false
---

## Introduction

In today's world of pocket cameras known as smartphones, we have all become amateur photographers and videographers thanks to their ubiquity. It gifted us with high-definition capabilities, allowing us to capture life's fleeting moments.

The coincidence of having these powerful devices in our pockets leads to an avalanche of photos and videos, creating a staggering volume of data that we must deal with daily.

However, with limited device storage, we are compelled to seek alternative solutions, often turning to cloud storage. This article delves into the intricacies of managing our data and exploring possible solutions.

### The infinite data glitch

The rise of pocket cameras has revolutionized the way we capture and immortalize our memories. The ease of access and the ability to instantly record events have made pocket cameras an integral part of modern life. As our smartphones evolved into pocket cameras, the sheer convenience and ever-improving camera quality have triggered an explosion of data we create daily.

### The Data Deluge: Capturing Moments in Pixels

The allure of high-definition photos and videos prompts us to click away tirelessly, amassing an astonishing volume of media content. Each trip, party, or mundane moment turns into a potential photo or video opportunity. We find ourselves grappling with how to store, organize, and manage the ever-growing collection of digital souvenirs. Let's try to calculate how much data we generate. Taking my phone as an example (Samsung S21) one photo takes up about **3 MB** and a 1-minute video is about **500 MB**. Looking through my gallery I take about 100 pictures and 5 mins of videos weekly. You might be different, so please use a handy calculator below to find for yourself.

<html>
<head>
  
  <h4>Number of pictures you take weekly</h4>
  <p><input type="number" id="pictures" oninput="this.value = this.value.replace(/[^0-9.]/g, '').replace(/(\..*)\./g, '$1');" pattern="[0-9]+" value="100" size=7/> pictures, <input type="number" id="picturesSize" oninput="this.value = this.value.replace(/[^0-9.]/g, '').replace(/(\..*)\./g, '$1');" pattern="[0-9]+" value="3" size=7/> mb per picture</p>
  <h4>How many minutes of videos you take weekly</h4>
  <p><input type="number" id="videos" oninput="this.value = this.value.replace(/[^0-9.]/g, '').replace(/(\..*)\./g, '$1');" pattern="[0-9]+" value="5" size=7/> min of video, <input type="number" id="videosSize" oninput="this.value = this.value.replace(/[^0-9.]/g, '').replace(/(\..*)\./g, '$1');" pattern="[0-9]+" value="500" size=7/> mb per 1 min</p>
  <br>
  <button onclick="calculateSize()">Calculate</button>
  <p>Yearly data size: <span id="dataSize">0</span></p>
  <p>Data size in 10 years: <span id="tenYearsdataSize">0</span></p>
  <p>Data over a lifespan of 70 years: <span id="lifespanSize">0</span></p>
  <br>
  <br>
  <br>
  <br>

  <script>
    document.getElementById("pictures").addEventListener("change", calculateSize);
    document.getElementById("videos").addEventListener("change", calculateSize);
    document.getElementById("videosSize").addEventListener("change", calculateSize);
    document.getElementById("picturesSize").addEventListener("change", calculateSize);
    let oneMbInBytes = 1048576;
    function formatBytes(bytes, decimals = 2) {
      if (!+bytes) return '0 Bytes';

      const k = 1024;
      const dm = decimals < 0 ? 0 : decimals;
      const sizes = ['Bytes', 'KiB', 'MiB', 'GiB', 'TiB', 'PiB', 'EiB', 'ZiB', 'YiB'];

      const i = Math.floor(Math.log(bytes) / Math.log(k));

      return `${parseFloat((bytes / Math.pow(k, i)).toFixed(dm))} ${sizes[i]}`;
    }

    function calculateSize() {
      const pictureinputBox = document.getElementById('pictures');
      const videosinputBox = document.getElementById('videos');
      const dataSizeSpan = document.getElementById('dataSize');
      const lifespanSizeSpan = document.getElementById('lifespanSize');
      const tenYearsdataSizeSpan = document.getElementById('tenYearsdataSize');
      const videosSize = document.getElementById('videosSize');
      const picturesSize = document.getElementById('picturesSize');
      const pictureNum = pictureinputBox.value;
      const videoNum = videosinputBox.value;
      const picturesSizeNum = picturesSize.value;
      const videosSizeNum = videosSize.value;
      const bytes = ((picturesSizeNum *oneMbInBytes* pictureNum) + (videosSizeNum *oneMbInBytes* videoNum))*52;
      dataSizeSpan.textContent = formatBytes(bytes);
      tenYearsdataSizeSpan.textContent = formatBytes(bytes*10);
      lifespanSizeSpan.textContent = formatBytes(bytes*70);
    }
  </script>

</head>
<body onload="calculateSize()">
</body>
</html>

Now with only 100 pictures and about 5 mins of video a week, I generate nearly **150 GB** a year😲! It might seem small, but have to take into consideration any of the images that you also download and save on your phone. Additionally, as technology is going to be improving, the file sizes of those will most definitely increase. Which will further increase the data you accumulate in a year. Additionally, if you are part of a family and share your data backups, this number can double, triple, quadruple and so on.

## Pandora's box of storage solutions

### Portable HHD or SSD

The first obvious way you will think about storing data will be by just buying a basic hard drive from Amazon and storing it all there. That's an obvious solution, there are no monthly fees, no setup, you just plug and play. But using those technologies came with a big caveat that people don't tend to considerer

Cons:

1. Hard drives are a lot more likely to fail after 3 years
   - Then the scariest part you might not even notice that the drive started to fail until it's too late
2. Easy to break
3. If it gets lost, that's all your data gone

Pros:

1. Cheap
2. Easy to use
3. Portable

As highlighted above, it might seem like an easy and cheap storage solution, but you are at great risk of losing all your data with this method, especially if not handled with care or knowledge. And the SSDs are still too expensive when looking at larger sizes to even consider them for data backup and storage.

### Cloud

#### Seeking Solace in the Cloud

Cloud is the new-age solution to storing large amounts of data, but again although it improves on the Hard drive storing option, it creates new issues. Using services like Google Photos, Apple's iCloud, and Dropbox comes with the following

Cons:

- Privacy is under question with a lot of those services
- Despite better security, those guys are a large target in the eyes of hackers, which can endanger your data being erased or leaked online.
- Monthly subscription costs for higher storage options
- Data Exit strategies are blurry and not guaranteed to be always available

Pros:

- Increased security
- Better redundancy
- Scalability
- Availability

#### Data Exit Strategies

As the saying goes, "Once it's on the internet, it's there forever." The same applies to cloud-stored data, making the process of leaving one cloud provider for another a daunting task. This "cloud lock-in" can be frustrating, limiting our ability to exercise full control over our data.

There might be many reasons that you decide to change your cloud provider: An increase in monthly fees, security and privacy concerns, the cloud storage provider going out of business, etc. If you use it over several years you can accumulate an insane amount of data. Let's say will have 1tb of data saved (Which according to my calculation is just the amount of data I generated in a year), it will take you ages to download it. Let's see how long it's going to take you to download it depending on your internet speed.

<html>
<head>
  
  <h4>Your internet speed</h4>
  <p> Download speed = <input type="number" id="download" oninput="this.value = this.value.replace(/[^0-9.]/g, '').replace(/(\..*)\./g, '$1');" pattern="[0-9]+" value="100" size=7/> Mbps,  Upload speed = <input type="number" id="upload" oninput="this.value = this.value.replace(/[^0-9.]/g, '').replace(/(\..*)\./g, '$1');" pattern="[0-9]+" value="25" size=7/> Mbps</p>
  <h4>Size of your data</h4>
  <p><input type="number" id="totalDataSize" oninput="this.value = this.value.replace(/[^0-9.]/g, '').replace(/(\..*)\./g, '$1');" pattern="[0-9]+" value="1000" size=7/> GB</p>
  <br>
  <button onclick="calculateSpeed()">Calculate</button>
  <p>Time to download: <span id="downloadTime">0</span></p>
  <p>Time to upload: <span id="uploadTime">0</span></p>

  <br>
  <br>
  <br>
  <script>
    document.getElementById("download").addEventListener("change", calculateSpeed);
    document.getElementById("upload").addEventListener("change", calculateSpeed);
    document.getElementById("totalDataSize").addEventListener("change", calculateSpeed);
    function formatBytes(bytes, decimals = 2) {
      if (!+bytes) return '0 Bytes';

      const k = 1024;
      const dm = decimals < 0 ? 0 : decimals;
      const sizes = ['Bytes', 'KiB', 'MiB', 'GiB', 'TiB', 'PiB', 'EiB', 'ZiB', 'YiB'];

      const i = Math.floor(Math.log(bytes) / Math.log(k));

      return `${parseFloat((bytes / Math.pow(k, i)).toFixed(dm))} ${sizes[i]}`;
    }

    function toHoursAndMinutes(totalSeconds) {
      const totalMinutes = Math.floor(totalSeconds / 60);
      const TotalHours = Math.floor(totalMinutes / 60);

      const seconds = Math.floor(totalSeconds % 60);
      const hours = Math.floor((totalMinutes / 60) % 24);
      const minutes = totalMinutes % 60;
      const days =  Math.floor(TotalHours / 24);

      return `${days}:days, ${hours}:h, ${minutes}:m, ${seconds}:s`;
    }

    function calculateSpeed() {
      const downloadSpeed = document.getElementById('download').value;
      const uploadSpeed = document.getElementById('upload').value;
      const dataSize = document.getElementById('totalDataSize').value;

      downloadTime.textContent = toHoursAndMinutes((dataSize*1024*1024*1024*8 ) / (downloadSpeed*1000000));
      uploadTime.textContent = toHoursAndMinutes((dataSize*1024*1024*1024*8 ) / (uploadSpeed*1000000));
    }
  </script>

</head>
  <body onload="calculateSpeed()">
    <!-- Your page content here -->
  </body>
</html>

It will take around 5 days to download and upload your data to a different service. This is also considering that you have a stable internet connection or that you can leave your computer open and connected for multiple days. And even if you can do this, you would need to have actual storage large enough to temporarily store it.

Even if the services are offering some ways of automatically moving between different cloud storage service providers, there is no guarantee that they won't remove it in the future or that it there will be some limitations or charges you are going to be uncomfortable paying.

## NAS: An Alternative Solution to Cloud Storage

In the quest for a more personalized and controllable approach to managing your data, Network Attached Storage (NAS) emerges as a compelling alternative to traditional cloud storage solutions. NAS devices are essentially specialized servers that connect to a home or office network, providing shared storage accessible to all devices connected to that network. This local storage option offers several advantages that may appeal to users seeking more autonomy over their data.

## 1. Complete Ownership and Privacy

One of the primary appeals of NAS is the sense of complete ownership and control it provides. Unlike third-party cloud providers, NAS is hosted on-premises, meaning users retain full ownership of their data. There's no need to entrust sensitive media content to external entities, addressing privacy concerns associated with cloud storage. Users have the peace of mind of knowing that their data remains within their physical control.

## 2. Cost-Effectiveness

While some cloud storage services offer free tiers, the amount of storage is often limited. To access more significant storage capacities, users are usually required to pay monthly subscription fees. Over time, these costs can add up, especially for users with substantial media collections. On the other hand, investing in a NAS device provides a one-time cost, and users can expand storage capacity by adding additional hard drives as needed.

> NAS hard drives need to be updated every once in a while to prevent losing your data if the disk fails. RAID is also highly recommended.
{: .prompt-tip }

## 3. No Data Transfer Limits

With NAS, data transfer is limited only by the local network's capabilities, providing users with the freedom to transfer and access their media files without such restrictions. As with NAS you also have a direct connection to the storage you can transfer large data over high speed and reliable connection.

## 4. Seamless Integration and Accessibility

NAS devices integrate seamlessly into home or office networks, making media content accessible from all connected devices. Whether it's a desktop computer, smartphone, tablet, or smart TV, users can access their media files effortlessly, just like they would with cloud storage services.

## NAS cons

- Requires some technical knowledge
- All the Security and Backups are up to you
- You become your own admin

## Conclusion

While cloud storage solutions offer undeniable convenience and accessibility, they might not be the best fit for users seeking greater control over their data and privacy. Network Attached Storage (NAS) presents an attractive alternative, providing complete ownership, data security, and the ability to access media files locally without data transfer limits. By adopting a NAS solution, users can strike a balance between the convenience of cloud storage and the autonomy of on-premises data management, ensuring that their cherished memories remain safe, private, and easily accessible within the confines of their network.
Don't get me wrong, I fully understand how it sounds if you are not as technically savvy when you are listening to my rumbling about doing something so technical and becoming your own IT admin. It's a big ask, but rather than making this article to make you set up your NAS, I am doing it to raise awareness on the amounts of data that is being generated, and that we all need to put a bit more thought into how we are going to be storing it. As highlighted, due to the sheer amount of data generated on yearly bases, it can get very difficult or expensive to store it for the years to come if we don't start thinking about it now
