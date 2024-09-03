1. Not able to do git push:
    Problem:
        git push
        Enumerating objects: 13, done.
        Counting objects: 100% (13/13), done.
        Delta compression using up to 10 threads
        Compressing objects: 100% (10/10), done.
        error: RPC failed; HTTP 400 curl 22 The requested URL returned error: 400
        send-pack: unexpected disconnect while reading sideband packet
        Writing objects: 100% (10/10), 1.46 MiB | 2.37 MiB/s, done.
        Total 10 (delta 2), reused 0 (delta 0), pack-reused 0
        fatal: the remote end hung up unexpectedly
        Everything up-to-date
    Solution: Reduce the Buffer Size: Sometimes, this issue occurs due to large files or repositories. You can try reducing the HTTP post buffer:
        git config --global http.postBuffer 524288000
    This command increases the buffer size to 500MB, which might help if the problem is due to large files.
2. Git pushes where not showing in github contribution graph
    Problem was: Both remote and local had different emailIds.
    Solution: Let your global email config as it is, for local add you emailId same as on github using this command: git config --local user.email id@gmail.com
