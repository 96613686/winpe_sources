# Trace(ulong,ushort const *,...)

- ea: `0x180002a30`
- end: `0x180002a65`
- name: `?Trace@@YAXKPEBGZZ`
- size: `53`
- prototype: `void(unsigned int, const unsigned __int16 *, ...)`
- caller_count: `22`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a70`
- `0x180003050`
- `0x180003924`
- `0x180004030`
- `0x1800041c4`
- `0x180004660`
- `0x180004848`
- `0x180004c58`
- `0x180005aa4`
- `0x180006770`
- `0x1800069c4`
- `0x18000abe4`
- `0x18000adf8`
- `0x18000b7c4`
- `0x18000bdc0`
- `0x18000c63c`
- `0x18000d13c`
- `0x18000e08c`
- `0x18000e314`
- `0x18000ea3c`
- `0x18000eda0`
- `0x18000f8b8`

## import_xrefs

- `WDSSRV!WdsTraceV` at `0x180002a53`
- `WDSSRV!WdsTraceV` at `0x180002a53`

## pseudocode

```c
void Trace(unsigned int a1, const unsigned __int16 *a2, ...)
{
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  WdsTraceV(g_hPxeProvider, a1, a2, (__int64 *)va);
}

```

## disassembly

```asm
0x180002a30  mov     rax, rsp
0x180002a33  mov     [rax+10h], rdx
0x180002a37  mov     [rax+18h], r8
0x180002a3b  mov     [rax+20h], r9
0x180002a3f  sub     rsp, 38h
0x180002a43  mov     r8, rdx
0x180002a46  lea     r9, [rax+18h]
0x180002a4a  mov     edx, ecx
0x180002a4c  mov     rcx, cs:?g_hPxeProvider@@3PEAXEA; void * g_hPxeProvider
0x180002a53  call    cs:__imp_WdsTraceV
0x180002a5a  nop     dword ptr [rax+rax+00h]
0x180002a5f  add     rsp, 38h
0x180002a63  retn
```
