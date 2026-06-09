# CanFileBeCommitted(ushort const *,ushort const *)

- ea: `0x180011e40`
- end: `0x180011f0e`
- name: `?CanFileBeCommitted@@YA_NPEBG0@Z`
- size: `206`
- prototype: `char __fastcall(wchar_t *String1, wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012b00`
- `0x180014d80`

## callees

- `0x180011e40`
- `0x18001b020`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180011e8d`
- `msvcrt!_wcsicmp` at `0x180011ea3`
- `msvcrt!_wcsicmp` at `0x180011eb7`
- `msvcrt!_wcsicmp` at `0x180011ecb`
- `msvcrt!_wcsicmp` at `0x180011edf`
- `msvcrt!_wcsicmp` at `0x180011e8d`
- `msvcrt!_wcsicmp` at `0x180011ea3`
- `msvcrt!_wcsicmp` at `0x180011eb7`
- `msvcrt!_wcsicmp` at `0x180011ecb`
- `msvcrt!_wcsicmp` at `0x180011edf`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180011e76`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180011e76`

## pseudocode

```c
char __fastcall CanFileBeCommitted(wchar_t *String1, wchar_t *a2)
{
  char v4; // bl
  WCHAR Dst[4]; // [rsp+20h] [rbp-18h] BYREF

  ExpandEnvironmentStringsW(L"%SystemDrive%", Dst, 3u);
  Dst[2] = 0;
  if ( !_wcsicmp(a2, L"\\pagefile.sys") || !_wcsicmp(String1, Dst) && !_wcsicmp(a2, L"\\hiberfil.sys") )
    return 0;
  v4 = 1;
  if ( !_wcsicmp(String1, Dst) )
    return _wcsicmp(a2, L"\\UWFSWAP.SYS") != 0;
  return v4;
}

```

## disassembly

```asm
0x180011e40  mov     [rsp+arg_10], rbx
0x180011e45  mov     [rsp+arg_18], rsi
0x180011e4a  push    rdi
0x180011e4b  sub     rsp, 30h
0x180011e4f  mov     rax, cs:__security_cookie
0x180011e56  xor     rax, rsp
0x180011e59  mov     [rsp+38h+var_10], rax
0x180011e5e  mov     rdi, rdx
0x180011e61  mov     rsi, rcx
0x180011e64  lea     rdx, [rsp+38h+Dst]; lpDst
0x180011e69  mov     r8d, 3; nSize
0x180011e6f  lea     rcx, Src; "%SystemDrive%"
0x180011e76  call    cs:__imp_ExpandEnvironmentStringsW
0x180011e7c  xor     eax, eax
0x180011e7e  lea     rdx, aPagefileSys; "\\pagefile.sys"
0x180011e85  mov     rcx, rdi; String1
0x180011e88  mov     [rsp+38h+var_14], ax
0x180011e8d  call    cs:__imp__wcsicmp
0x180011e93  test    eax, eax
0x180011e95  jnz     short loc_180011E9B
0x180011e97  xor     bl, bl
0x180011e99  jmp     short loc_180011EEF
0x180011e9b  lea     rdx, [rsp+38h+Dst]; String2
0x180011ea0  mov     rcx, rsi; String1
0x180011ea3  call    cs:__imp__wcsicmp
0x180011ea9  test    eax, eax
0x180011eab  jnz     short loc_180011EC1
0x180011ead  lea     rdx, aHiberfilSys; "\\hiberfil.sys"
0x180011eb4  mov     rcx, rdi; String1
0x180011eb7  call    cs:__imp__wcsicmp
0x180011ebd  test    eax, eax
0x180011ebf  jz      short loc_180011E97
0x180011ec1  lea     rdx, [rsp+38h+Dst]; String2
0x180011ec6  mov     rcx, rsi; String1
0x180011ec9  mov     bl, 1
0x180011ecb  call    cs:__imp__wcsicmp
0x180011ed1  test    eax, eax
0x180011ed3  jnz     short loc_180011EEF
0x180011ed5  lea     rdx, aUwfswapSys_1; "\\UWFSWAP.SYS"
0x180011edc  mov     rcx, rdi; String1
0x180011edf  call    cs:__imp__wcsicmp
0x180011ee5  xor     ecx, ecx
0x180011ee7  movzx   ebx, bl
0x180011eea  test    eax, eax
0x180011eec  cmovz   ebx, ecx
0x180011eef  mov     al, bl
0x180011ef1  mov     rcx, [rsp+38h+var_10]
0x180011ef6  xor     rcx, rsp; StackCookie
0x180011ef9  call    __security_check_cookie
0x180011efe  mov     rbx, [rsp+38h+arg_10]
0x180011f03  mov     rsi, [rsp+38h+arg_18]
0x180011f08  add     rsp, 30h
0x180011f0c  pop     rdi
0x180011f0d  retn
```
