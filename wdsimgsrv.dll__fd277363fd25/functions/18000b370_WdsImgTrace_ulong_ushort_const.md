# WdsImgTrace(ulong,ushort const *,...)

- ea: `0x18000b370`
- end: `0x18000b3a5`
- name: `?WdsImgTrace@@YAKKPEBGZZ`
- size: `53`
- prototype: `unsigned int(unsigned int, const unsigned __int16 *, ...)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a0c`
- `0x180002e64`
- `0x1800036b0`
- `0x180003838`
- `0x180003af4`
- `0x180003dc4`
- `0x180006548`
- `0x180006b10`
- `0x180006e50`
- `0x180007120`
- `0x180007700`
- `0x180007c28`
- `0x18000b668`
- `0x18000c0ec`
- `0x18000c69c`

## import_xrefs

- `WDSSRV!WdsTraceV` at `0x18000b393`
- `WDSSRV!WdsTraceV` at `0x18000b393`

## pseudocode

```c
__int64 WdsImgTrace(unsigned int a1, const unsigned __int16 *a2, ...)
{
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  return WdsTraceV(g_hProvider, a1, a2, (__int64 *)va);
}

```

## disassembly

```asm
0x18000b370  mov     rax, rsp
0x18000b373  mov     [rax+10h], rdx
0x18000b377  mov     [rax+18h], r8
0x18000b37b  mov     [rax+20h], r9
0x18000b37f  sub     rsp, 38h
0x18000b383  mov     r8, rdx
0x18000b386  lea     r9, [rax+18h]
0x18000b38a  mov     edx, ecx
0x18000b38c  mov     rcx, cs:?g_hProvider@@3PEAXEA; void * g_hProvider
0x18000b393  call    cs:__imp_WdsTraceV
0x18000b39a  nop     dword ptr [rax+rax+00h]
0x18000b39f  add     rsp, 38h
0x18000b3a3  retn
```
