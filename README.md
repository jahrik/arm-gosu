# docker gosu

```
root@casey:~# docker run -it -e GOSU_USER=nobody jahrik/arm-gosu:aarch64 bash
nobody@e979edc48939:/$ ps waux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
nobody       1  1.4  0.0   3776  2880 pts/0    Ss   00:31   0:00 bash
nobody      14  0.0  0.0   5288  2408 pts/0    R+   00:31   0:00 ps waux
```
