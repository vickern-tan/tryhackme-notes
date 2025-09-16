> Although there are many different content discovery tools available, all with their features and flaws, we're going to cover three which are preinstalled on our attack box, ffuf, dirb and gobuster.

## **ffuf**
> ffuf is a fast web fuzzer written in Go that allows typical directory discovery, virtual host discovery (without DNS records) and GET and POST parameter fuzzing.

#### **What is a fast web fuzzer?**
> A _web fuzzer_ tries lots of inputs (words, filenames, parameter values, headers, etc.) against a web server to discover hidden resources, endpoints, files, parameters, virtual hosts, and sometimes weird behavior.  
> A **fast** web fuzzer (like **ffuf**) is optimized for high concurrency and low overhead so it can try thousands of requests per second while giving you filtering and matching controls (status codes, body size, regex matches, etc.). ffuf is written in Go, is easy to script, and is popular for quick directory/parameter discovery.

*Use Case 1:*
```
user@machine$ ffuf -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt -u http://10.201.16.48/FUZZ
```

- `FUZZ` is a placeholder token — a marker that ffuf will replace, one word at a time, with entries from the supplied wordlist.
- `-w /.../common.txt` → use that wordlist (each line is a candidate),
- `-u http://10.201.16.48/FUZZ` → for each word in the wordlist, request `http://10.201.16.48/<word>` (replacing `FUZZ`).

*Use Case 2:*
```
ffuf -w common.txt -u http://10.201.16.48/FUZZ -t 40 -mc 200,301,302 -o ffuf.json -of json
```

- `-t 40 → threads/concurrency (speed)
- `-mc 200,301,302` → show only these status codes (match codes)
- `-fs SIZE` → filter responses by exact size (useful to remove noise)
- `-mr 'regex'` → match response bodies with regex
- `-o results.json -of json` → save output