# InitClrHost(IProcessHost * *,long (*)(ushort const *,ushort const *,ulong,void * *))

- ea: `0x18005b928`
- end: `0x18005bbb2`
- name: `?InitClrHost@@YAJPEAPEAUIProcessHost@@P6AJPEBG1KPEAPEAX@Z@Z`
- size: `650`
- prototype: `__int64 __fastcall(struct IProcessHost **, __int64 (__fastcall *)(LPWSTR, const wchar_t *, __int64, struct IProcessHost **))`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180059ea8`
- `0x18005b754`

## callees

- `0x18004d030`
- `0x180054690`
- `0x180054760`
- `0x18005b928`
- `0x18006585c`
- `0x180065b60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005b9c4`
- `KERNEL32!GetLastError` at `0x18005b9c4`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18005b992`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18005ba4a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18005b992`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18005ba4a`

## string_xrefs

- `0x18005b988`: `%windir%\system32\inetsrv\wbhst_pm.dll`
- `0x18005b9ff`: `Failed to expand protocol manager path %S. hr = 0x%x\n`
- `0x18005ba79`: `Failed to expand protocol manager path %S. hr = 0x%x\n`
- `0x18005bad4`: `GetProtocolManager`
- `0x18005bb01`: `GetProtocolManager`

## pseudocode

```c

```
