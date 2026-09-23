# EVEN RSA CAN BE BROKEN
## Approach
After downloading the encryption code and looking at the hint about observing N closely
it was clear that from the code N is supposed to be a product of 2 prime numbers but N was even
in every netcat request. So it means that one of the prime factor of N is 2 so the other one is
N/2. This makes cracking the RSA encryption easy as the numbers are small 
## Solution
I Directly searched for online RSA decryption programs as the Public Key (N) is very vulnerable

## Takeaway
Sometimes Public key is not so vulnerable so i have to manually decrypt based on the encryption file
