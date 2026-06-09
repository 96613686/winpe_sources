# WTSTerminateProcess

- ea: `0x180009520`
- end: `0x180009532`
- name: `WTSTerminateProcess`
- size: `18`
- prototype: `BOOL __stdcall(HANDLE hServer, DWORD ProcessId, DWORD ExitCode)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `WINSTA!WinStationTerminateProcess` at `0x180009524`
- `WINSTA!WinStationTerminateProcess` at `0x180009524`

## pseudocode

```c
BOOL __stdcall WTSTerminateProcess(HANDLE hServer, DWORD ProcessId, DWORD ExitCode)
{
  return (unsigned __int8)WinStationTerminateProcess(hServer, ProcessId, ExitCode);
}

```

## disassembly

```asm
0x180009520  sub     rsp, 28h
0x180009524  call    cs:__imp_WinStationTerminateProcess
0x18000952a  movzx   eax, al
0x18000952d  add     rsp, 28h
0x180009531  retn
```
