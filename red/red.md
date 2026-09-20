# Red
## Approach
I started by downloading the image file and ran some basic commands like **file** and **strings** on the image
**file** gave only the basic information about the image but **strings** gave a hidden poem type text when i ran it. After some time looking at the output from **strings** the only pattern i could find is the first letters of each line of the poem made up to **CHECKLSB**
I then watched some videos about **LSB** and **Stegenography** and found an online **LSB** extractor [aperisolve](https://www.aperisolve.com/) and uploaded my image in that and found something which looked like **BASE64** encoded
Then i decoded that in a[decoder](https://www.base64decode.org/) to get the flag
## Solution
basic information
![basic information](https://github.com/srvkaush1k/bitskriegp1/blob/main/red/s1.png?raw=true)
extracting LSB
![lsb](https://github.com/srvkaush1k/bitskriegp1/blob/main/red/s3.png?raw=true)
decoding from base 64
![base64](https://github.com/srvkaush1k/bitskriegp1/blob/main/red/s2.png?raw=true)
from this i got the flag as **picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}**
## Takeaway
directly use zsteg tool or directly use aperisolve for all information on an image
