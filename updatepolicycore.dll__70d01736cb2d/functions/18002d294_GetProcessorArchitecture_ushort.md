# GetProcessorArchitecture(ushort *)

- ea: `0x18002d294`
- end: `0x18002d312`
- name: `?GetProcessorArchitecture@@YAJPEAG@Z`
- size: `126`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002bee8`

## callees

- `0x18000aac0`
- `0x18002d294`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002d2ef`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002d2ef`

## string_xrefs

- `0x18002d2b8`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x18002d294  push    rbx
0x18002d296  sub     rsp, 60h
0x18002d29a  mov     rax, cs:__security_cookie
0x18002d2a1  xor     rax, rsp
0x18002d2a4  mov     [rsp+68h+var_18], rax
0x18002d2a9  xor     eax, eax
0x18002d2ab  mov     rbx, rcx
0x18002d2ae  test    rcx, rcx
0x18002d2b1  jnz     short loc_18002D2D5
0x18002d2b3  mov     rcx, [rsp+68h]; this
0x18002d2b8  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18002d2bf  mov     ebx, 80070057h
0x18002d2c4  mov     edx, 10Ah; void *
0x18002d2c9  mov     r9d, ebx; char *
0x18002d2cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d2d1  mov     eax, ebx
0x18002d2d3  jmp     short loc_18002D2FF
0x18002d2d5  xorps   xmm0, xmm0
0x18002d2d8  mov     [rcx], ax
0x18002d2db  lea     rcx, [rsp+68h+SystemInfo]; lpSystemInfo
0x18002d2e0  movups  xmmword ptr [rsp+68h+SystemInfo], xmm0
0x18002d2e5  movups  xmmword ptr [rsp+68h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18002d2ea  movups  xmmword ptr [rsp+68h+SystemInfo.dwNumberOfProcessors], xmm0
0x18002d2ef  call    cs:__imp_GetNativeSystemInfo
0x18002d2f5  movzx   eax, word ptr [rsp+68h+SystemInfo]
0x18002d2fa  mov     [rbx], ax
0x18002d2fd  xor     eax, eax
0x18002d2ff  mov     rcx, [rsp+68h+var_18]
0x18002d304  xor     rcx, rsp; StackCookie
0x18002d307  call    __security_check_cookie
0x18002d30c  add     rsp, 60h
0x18002d310  pop     rbx
0x18002d311  retn
```
