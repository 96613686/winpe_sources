# CreateCookie

- ea: `0x18001c728`
- end: `0x18001c78d`
- name: `CreateCookie`
- size: `101`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b514`
- `0x180017870`
- `0x180017f40`
- `0x180018a40`
- `0x180018d98`
- `0x180019084`

## callees

- `0x18001d038`
- `0x180029280`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001c74d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001c74d`

## pseudocode

```c
__int64 __fastcall CreateCookie(_OWORD *a1)
{
  __int64 result; // rax
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+20h] [rbp-28h] BYREF

  *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
  GetSystemTimeAsFileTime(SystemTimeAsFileTime);
  SystemTimeAsFileTime[1].dwLowDateTime = dword_180034858++;
  result = Random(0xFFFFFFFFLL);
  SystemTimeAsFileTime[1].dwHighDateTime = result;
  *a1 = *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime;
  return result;
}

```

## disassembly

```asm
0x18001c728  push    rbx
0x18001c72a  sub     rsp, 40h
0x18001c72e  mov     rax, cs:__security_cookie
0x18001c735  xor     rax, rsp
0x18001c738  mov     [rsp+48h+var_18], rax
0x18001c73d  mov     rbx, rcx
0x18001c740  xorps   xmm0, xmm0
0x18001c743  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001c748  movups  xmmword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x18001c74d  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c753  mov     eax, cs:dword_180034858
0x18001c759  or      ecx, 0FFFFFFFFh
0x18001c75c  mov     [rsp+48h+SystemTimeAsFileTime.dwLowDateTime+8], eax
0x18001c760  inc     eax
0x18001c762  mov     cs:dword_180034858, eax
0x18001c768  call    Random
0x18001c76d  mov     [rsp+48h+SystemTimeAsFileTime.dwHighDateTime+8], eax
0x18001c771  movups  xmm0, xmmword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x18001c776  movdqu  xmmword ptr [rbx], xmm0
0x18001c77a  mov     rcx, [rsp+48h+var_18]
0x18001c77f  xor     rcx, rsp; StackCookie
0x18001c782  call    __security_check_cookie
0x18001c787  add     rsp, 40h
0x18001c78b  pop     rbx
0x18001c78c  retn
```
