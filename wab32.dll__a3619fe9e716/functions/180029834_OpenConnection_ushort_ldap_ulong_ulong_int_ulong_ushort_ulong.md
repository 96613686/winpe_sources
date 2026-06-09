# OpenConnection(ushort *,ldap * *,ulong *,ulong *,int *,ulong,ushort *,ulong)

- ea: `0x180029834`
- end: `0x180029b84`
- name: `?OpenConnection@@YAKPEAGPEAPEAUldap@@PEAK2PEAHK0K@Z`
- size: `848`
- prototype: `unsigned int __usercall@<eax>(unsigned __int16 *@<rcx>, struct ldap **@<rdx>, unsigned int *@<r8>, unsigned int *@<r9>, int *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1800253b8`
- `0x180026090`
- `0x1800266c8`

## callees

- `0x1800045e4`
- `0x1800270d4`
- `0x1800273cc`
- `0x1800277e4`
- `0x180029834`
- `0x180091eaa`
- `0x180093010`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800298b7`
- `KERNEL32!lstrcmpiW` at `0x1800298b7`
- `KERNEL32!LocalAlloc` at `0x180029946`
- `KERNEL32!LocalAlloc` at `0x180029946`
- `KERNEL32!LocalFree` at `0x1800298c5`
- `KERNEL32!LocalFree` at `0x1800298c5`

## pseudocode

```c

```
