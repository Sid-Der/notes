# Linux and Shell

Everyday Linux commands and shell tips.

---

## Navigation

```bash
pwd                  # print working directory
ls -lah              # list with details, hidden files, human sizes
cd -                 # go to previous directory
tree -L 2            # show directory tree (2 levels)
```

---

## File Operations

```bash
cp -r src/ dst/      # copy directory recursively
mv file.txt dir/     # move or rename
rm -rf dir/          # remove recursively (careful!)
ln -s target link    # create symlink
chmod +x script.sh   # make executable
chown user:group file
```

---

## grep and find

```bash
# find files
find . -name "*.py"           # by name
find . -type f -mtime -7      # modified in last 7 days
find . -size +10M             # larger than 10MB

# grep
grep -r "pattern" .           # recursive search
grep -rn "pattern" .          # with line numbers
grep -rl "pattern" .          # just filenames
grep -v "pattern" file        # invert match
grep -E "foo|bar" file        # extended regex
```

---

## Processes

```bash
ps aux               # list all processes
top                  # live process viewer (htop is nicer)
kill -9 PID          # force kill
pkill firefox        # kill by name
lsof -i :8080        # what is using port 8080?
```

---

## Disk and System

```bash
df -h                # disk usage (human readable)
du -sh dir/          # directory size
free -h              # memory usage
uname -a             # kernel info
uptime               # system uptime and load
```

---

## Network

```bash
curl -I https://example.com    # headers only
wget -q URL -O file            # download quietly
ss -tlnp                       # open TCP ports
ping -c 4 8.8.8.8              # ping 4 times
```

---

## See Also

- [grep-find.md](grep-find.md) - extended grep and find reference
