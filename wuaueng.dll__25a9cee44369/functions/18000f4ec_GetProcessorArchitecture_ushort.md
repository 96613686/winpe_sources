# GetProcessorArchitecture(ushort *)

- ea: `0x18000f4ec`
- end: `0x18000f56a`
- name: `?GetProcessorArchitecture@@YAJPEAG@Z`
- size: `126`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e23c`

## callees

- `0x180003760`
- `0x18000f4ec`
- `0x18000fc90`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18000f547`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18000f547`

## string_xrefs

- `0x18000f510`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

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
0x18000f4ec  push    rbx
0x18000f4ee  sub     rsp, 60h
0x18000f4f2  mov     rax, cs:__security_cookie
0x18000f4f9  xor     rax, rsp
0x18000f4fc  mov     [rsp+68h+var_18], rax
0x18000f501  xor     eax, eax
0x18000f503  mov     rbx, rcx
0x18000f506  test    rcx, rcx
0x18000f509  jnz     short loc_18000F52D
0x18000f50b  mov     rcx, [rsp+68h]; this
0x18000f510  lea     r8, aCW1SSrcClientL_1; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f517  mov     ebx, 80070057h
0x18000f51c  mov     edx, 10Ah; void *
0x18000f521  mov     r9d, ebx; char *
0x18000f524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f529  mov     eax, ebx
0x18000f52b  jmp     short loc_18000F557
0x18000f52d  xorps   xmm0, xmm0
0x18000f530  mov     [rcx], ax
0x18000f533  lea     rcx, [rsp+68h+SystemInfo]; lpSystemInfo
0x18000f538  movups  xmmword ptr [rsp+68h+SystemInfo], xmm0
0x18000f53d  movups  xmmword ptr [rsp+68h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000f542  movups  xmmword ptr [rsp+68h+SystemInfo.dwNumberOfProcessors], xmm0
0x18000f547  call    cs:__imp_GetNativeSystemInfo
0x18000f54d  movzx   eax, word ptr [rsp+68h+SystemInfo]
0x18000f552  mov     [rbx], ax
0x18000f555  xor     eax, eax
0x18000f557  mov     rcx, [rsp+68h+var_18]
0x18000f55c  xor     rcx, rsp; StackCookie
0x18000f55f  call    __security_check_cookie
0x18000f564  add     rsp, 60h
0x18000f568  pop     rbx
0x18000f569  retn
```
