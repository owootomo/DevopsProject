### Steps to host a static website with a custom domain

1. Create a custom domain name using Amazon Route 53
2. Use an Amazon S3 bucket to host a sample website.
3. Enable status website hosting and direct the domain to the S3 bucket.

I'm excited to share my journey of setting up my static website on Amazon S3 using my chosen bucket name abiproject.click. Let's walk through the steps together:

* Registering My Domain
   
![image](https://github.com/owootomo/Devops-Project/assets/144632027/dd6d858f-be11-4b29-a4c2-a43a783b079e)
I headed to my domain registrar's website and eagerly searched for my desired domain name, abiproject.click. I added it to my cart and proceeded to checkout. Carefully filling in my contact information and payment details, I completed the registration and confirmed my purchase, anticipation building with each step.
![image](https://github.com/owootomo/Devops-Project/assets/144632027/94fe5918-c506-4ceb-b7de-594dd9bab36f)
![image](https://github.com/owootomo/Devops-Project/assets/144632027/4ecd07ef-9660-4202-ac57-73263b1b1926)
![image](https://github.com/owootomo/Devops-Project/assets/144632027/41806abf-9e58-44f7-a879-ceb9ac6f7d04)
![image](https://github.com/owootomo/Devops-Project/assets/144632027/b5e5dd62-43de-447f-86b1-24eb23624f75)
* Creating My S3 Bucket:

Opening the Amazon S3 console, I felt a sense of anticipation as I clicked on "Create Bucket." I entered the unique name I had chosen, abiproject.click, and meticulously selected the desired region. Unchecking the "Block all public access" option, I ensured that the world would have access to my creation. After acknowledging the warning message and clicking "Create bucket," I watched with satisfaction as my bucket materialized.
![image](https://github.com/owootomo/Devops-Project/assets/144632027/afe9cdec-0b10-4958-8cae-c4309e44a92d)
![image](https://github.com/owootomo/Devops-Project/assets/144632027/aea38b31-691a-49f9-95d8-a6e03bd7561c)
![image](https://github.com/owootomo/Devops-Project/assets/144632027/b5eb6be4-8e42-4079-bd16-47265cf18131)

* Uploading My Website Files:
   
Clicking on the newly created bucket, abiproject.click, I eagerly clicked the "Upload" button. With a careful hand, I selected the website files I had prepared, including the all-important index.html, along with the css files and images that would bring my vision to life. With a final click of "Upload," I entrusted my files to the vast digital storage of Amazon S3.
![image](https://github.com/owootomo/Devops-Project/assets/144632027/a6dbb6ca-fe08-40e1-923b-4215ea8e16f8)
![image](https://github.com/owootomo/Devops-Project/assets/144632027/d7a67728-6868-4ce4-b0b4-a44e643cf10f)

* Enabling Static Website Hosting:
   
Navigating to the "Properties" tab for my bucket, I found the "Static website hosting" section. With a feeling of accomplishment, I enabled the option "Use this bucket to host a website." Carefully setting the "Index document" to "index.html" and the "Error document" to "error.html," I ensured a seamless experience for my visitors. Clicking "Save changes," I felt a surge of satisfaction knowing my website was ready to be unveiled.
![image](https://github.com/owootomo/Devops-Project/assets/144632027/21dff92d-3942-42b2-b929-6513a615c2a3)

* Updating the Bucket Policy:
   
On the "Permissions" tab, I clicked "Edit bucket policy" and replaced the existing policy with the code provided, granting public access to my website files. Saving the changes, I knew my creation was ready to be shared with the world.
![image](https://github.com/owootomo/Devops-Project/assets/144632027/80fa3385-ac38-4440-8ac9-e0e8df3eb483)

* Verifying Website Access:
   
Heart pounding with anticipation, I clicked on the "Website endpoint" URL. With a wave of relief and excitement, my browser displayed the content of my uploaded "index.html" file. My website was live!
![image](https://github.com/owootomo/Devops-Project/assets/144632027/5a3dd0d7-685f-46ac-b5ed-5bdf23102f94)
![image](https://github.com/owootomo/Devops-Project/assets/144632027/5a3f1675-e46a-471e-a250-6a01e96e7b12)

 * Connecting My Domain:
    
Opening the Amazon Route 53 console, I navigated to the hosted zone associated with my domain name, abiproject.click. Clicking on "Create Record," I carefully chose the "Simple routing policy" and selected "A - Alias to S3 bucket endpoint" for the record type. Setting the alias name to "www" and choosing the desired region, I finally selected my bucket, abiproject.click, and clicked "Create record."
![image](https://github.com/owootomo/Devops-Project/assets/144632027/52d978d3-756e-4ca5-8624-f685a0bfa582)
![image](https://github.com/owootomo/Devops-Project/assets/144632027/467982cc-22f8-4896-87d7-0f460b4b6093)
![image](https://github.com/owootomo/Devops-Project/assets/144632027/e797e793-944e-42e2-8444-9d98b061e4ab)

* Witnessing the Magic:
After patiently waiting for the DNS propagation to complete, I held my breath and typed abiproject.click into my browser. A smile crept across my face as I saw my website content displayed in all its glory, served directly from my Amazon S3 bucket.

![image](https://github.com/owootomo/Devops-Project/assets/144632027/d0b47c94-5a01-440d-9246-a4d734c88426)










