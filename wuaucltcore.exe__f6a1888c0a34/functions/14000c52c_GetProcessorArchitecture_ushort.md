# GetProcessorArchitecture(ushort *)

- ea: `0x14000c52c`
- end: `0x14000c5aa`
- name: `?GetProcessorArchitecture@@YAJPEAG@Z`
- size: `126`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400105d8`

## callees

- `0x140002ac0`
- `0x14000c52c`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x14000c587`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x14000c587`

## string_xrefs

- `0x14000c550`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

## pseudocode

```c
__int64 __fastcall GetProcessorArchitecture(unsigned __int16 *a1)
{
  _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( a1 )
  {
    *a1 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    *a1 = SystemInfo.wProcessorArchitecture;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
      (const char *)0x80070057LL,
      SystemInfo.dwOemId);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14000c52c  push    rbx
0x14000c52e  sub     rsp, 60h
0x14000c532  mov     rax, cs:__security_cookie
0x14000c539  xor     rax, rsp
0x14000c53c  mov     [rsp+68h+var_18], rax
0x14000c541  xor     eax, eax
0x14000c543  mov     rbx, rcx
0x14000c546  test    rcx, rcx
0x14000c549  jnz     short loc_14000C56D
0x14000c54b  mov     rcx, [rsp+68h]; this
0x14000c550  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c557  mov     ebx, 80070057h
0x14000c55c  mov     edx, 10Ah; void *
0x14000c561  mov     r9d, ebx; char *
0x14000c564  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c569  mov     eax, ebx
0x14000c56b  jmp     short loc_14000C597
0x14000c56d  xorps   xmm0, xmm0
0x14000c570  mov     [rcx], ax
0x14000c573  lea     rcx, [rsp+68h+SystemInfo]; lpSystemInfo
0x14000c578  movups  xmmword ptr [rsp+68h+SystemInfo], xmm0
0x14000c57d  movups  xmmword ptr [rsp+68h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x14000c582  movups  xmmword ptr [rsp+68h+SystemInfo.dwNumberOfProcessors], xmm0
0x14000c587  call    cs:__imp_GetNativeSystemInfo
0x14000c58d  movzx   eax, word ptr [rsp+68h+SystemInfo]
0x14000c592  mov     [rbx], ax
0x14000c595  xor     eax, eax
0x14000c597  mov     rcx, [rsp+68h+var_18]
0x14000c59c  xor     rcx, rsp; StackCookie
0x14000c59f  call    __security_check_cookie
0x14000c5a4  add     rsp, 60h
0x14000c5a8  pop     rbx
0x14000c5a9  retn
```
