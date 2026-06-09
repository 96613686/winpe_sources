# TrkReportEvent(ulong,ushort,...)

- ea: `0x18000cef8`
- end: `0x18000cf2c`
- name: `?TrkReportEvent@@YAJKGZZ`
- size: `52`
- prototype: `__int64(DWORD, unsigned __int16, ...)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e28`
- `0x180002488`
- `0x180002b50`
- `0x180003798`
- `0x180006a80`
- `0x18000c158`
- `0x18000c430`
- `0x18000cd40`
- `0x18000f22c`

## callees

- `0x18000ffc0`

## pseudocode

```c
__int64 TrkReportEvent(DWORD a1, unsigned __int16 a2, ...)
{
  va_list va; // [rsp+60h] [rbp+18h] BYREF

  va_start(va, a2);
  return TrkReportRawEvent(a1, a2, 0, 0, va);
}

```

## disassembly

```asm
0x18000cef8  mov     rax, rsp
0x18000cefb  mov     [rax+10h], dx
0x18000ceff  mov     [rax+18h], r8
0x18000cf03  mov     [rax+20h], r9
0x18000cf07  sub     rsp, 48h
0x18000cf0b  mov     qword ptr [rax-18h], 0
0x18000cf13  lea     rax, [rax+18h]
0x18000cf17  xor     r9d, r9d; void *
0x18000cf1a  mov     [rsp+48h+var_28], rax; char *
0x18000cf1f  xor     r8d, r8d; unsigned int
0x18000cf22  call    ?TrkReportRawEvent@@YAJKGKPEBXPEAD@Z; TrkReportRawEvent(ulong,ushort,ulong,void const *,char *)
0x18000cf27  add     rsp, 48h
0x18000cf2b  retn
```
