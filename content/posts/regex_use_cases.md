---
title: "Regex Use Cases"
date: 2019-01-06T21:41:19-05:00
draft: true
author: Linux Bytes
tags:
    - regex
    - emails

---

Regex's some hate some love, but in the end, we all need something productive in our life. Some people hate because the mini-language can be arcane. Others love it because it adds superpowers for text processing. Learning the arcane secrets of regex can be a rough experience, but it doesn't have to.  

so let excerices a regex enscription for everyday needs 
 
### Finding Mailing data

extract email adresses from some file


```
'([[:alnum:]_.-]+@[[:alnum:]_.-]+?\.[[:alpha:].]{2,6})'
```

### Check for IP address

Look for IPv4 address in files


```
'([0-9]{1,3}\.){3}[0-9]{1,3}'
```


- [By: rubenmoran](https://www.commandlinefu.com/commands/view/5668/extract-ipv4-addressess-from-file)
- [By: wires](https://www.commandlinefu.com/commands/view/2431/extract-email-adresses-from-some-file-or-any-other-pattern)
