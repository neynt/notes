# g3tt1ng r00t

## Tools

Knowing the fundamentals is great, but if you want to get stuff done fast,
cybersecurity in 2020 is first and foremost being familiar with many many tools.
It's impossible to code everything yourself from first principles. Here are some
tools!

### Essential tools

- Port scanners: nmap, masscan
- Login brute forcer: hydra
- Directory brute forcer: gobuster, dirbuster
- SQLi finder: sqlmap
- Password crackers: hashcat, john
- Remote exploit framework: msfconsole

### Situational tools

- LDAP stuff: smbclient, rpcclient, ldapsearch
- Windows local exploitation: mimikatz, mimikittenz
- Windows local privesc: juicy potato
- Linux process snooping: pspy
- Web exploit framework: burpsuite

### rpcclient

You can pass an empty string username to bind to an anonymous session. This
sometimes lets you run commands even if you don't have a user/pass pair.

```
rpcclient -I $ip -U '' -N $domain
```

After you have a command prompt, get stuff:

- enumdomusers: List users in domain
- enumdomgroups: List groups in domain
- enumalsgroups [builtin|domain]: List alias groups
- queryaaliasmem: Query alias membership

## Reversing

Sometimes you gotta use gdb or radare2 or ghidra or IDA or cutter or binja or
something

### Gdb commands

- start: run your program
- frame: show current call frame
- bt: show call stack
- layout asm (C-X C-A): show a tui frame for surrounding instructions
- disass: disassemble
- b *0xffff: set breakpoint at location 0xffff
- c: continue
- step (s): step one line
- stepi (si): step one instruction
- n: step over function call
- ni: step over asm function call
- set: modify register, variable, or memory
- x 0xffff: print memory location 0xffff as hex
- finish: continue until return from current frame
