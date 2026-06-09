# GetProcessorArchitecture(ushort *)

- ea: `0x18000f53c`
- end: `0x18000f5ba`
- name: `?GetProcessorArchitecture@@YAJPEAG@Z`
- size: `126`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e1c8`

## callees

- `0x180003760`
- `0x18000f53c`
- `0x18000fce0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18000f597`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18000f597`

## string_xrefs

- `0x18000f560`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

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
0x18000f53c  push    rbx
0x18000f53e  sub     rsp, 60h
0x18000f542  mov     rax, cs:__security_cookie
0x18000f549  xor     rax, rsp
0x18000f54c  mov     [rsp+68h+var_18], rax
0x18000f551  xor     eax, eax
0x18000f553  mov     rbx, rcx
0x18000f556  test    rcx, rcx
0x18000f559  jnz     short loc_18000F57D
0x18000f55b  mov     rcx, [rsp+68h]; this
0x18000f560  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f567  mov     ebx, 80070057h
0x18000f56c  mov     edx, 10Ah; void *
0x18000f571  mov     r9d, ebx; char *
0x18000f574  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f579  mov     eax, ebx
0x18000f57b  jmp     short loc_18000F5A7
0x18000f57d  xorps   xmm0, xmm0
0x18000f580  mov     [rcx], ax
0x18000f583  lea     rcx, [rsp+68h+SystemInfo]; lpSystemInfo
0x18000f588  movups  xmmword ptr [rsp+68h+SystemInfo], xmm0
0x18000f58d  movups  xmmword ptr [rsp+68h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000f592  movups  xmmword ptr [rsp+68h+SystemInfo.dwNumberOfProcessors], xmm0
0x18000f597  call    cs:__imp_GetNativeSystemInfo
0x18000f59d  movzx   eax, word ptr [rsp+68h+SystemInfo]
0x18000f5a2  mov     [rbx], ax
0x18000f5a5  xor     eax, eax
0x18000f5a7  mov     rcx, [rsp+68h+var_18]
0x18000f5ac  xor     rcx, rsp; StackCookie
0x18000f5af  call    __security_check_cookie
0x18000f5b4  add     rsp, 60h
0x18000f5b8  pop     rbx
0x18000f5b9  retn
```
