# Transformation
## Approach
**' '.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])**

this is the prompt used to encode the flag so to reverse engineer this i got to know what the command did
It takes an empty string and iterates over the flag by skipping over every alternate 8 bit character and adds a 16 bit
character to the empty string by shifting the first 8 bit character by 8 bits and adding the second 8 bit character making it 16 bit 

to get the flag now we have to do the exact opposite on the enc.txt
that is iterating over each 16bit character in the code and shifting the first part to the right by 8 bits and adding 
the second 8 bit seperately

## Solution

## Takeaway
Look at how the flag is being encoded first
