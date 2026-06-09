# SHQualifyUsernameAsLocal

- ea: `0x180016aa8`
- end: `0x180016bc8`
- name: `SHQualifyUsernameAsLocal`
- size: `288`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800164c8`

## callees

- `0x18000b598`
- `0x18000b828`
- `0x18000bcc0`
- `0x18000c240`
- `0x180016aa8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180016ae5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180016b1d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180016ae5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180016b1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180016b09`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180016b09`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016b85`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180016b85`

## pseudocode

```c
__int64 __fastcall SHQualifyUsernameAsLocal(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  wchar_t *v5; // r9
  __int64 cchCount2; // r9
  __int64 v8; // rcx
  DWORD nSize; // [rsp+30h] [rbp-48h] BYREF
  WCHAR Buffer[16]; // [rsp+38h] [rbp-40h] BYREF

  v4 = -2147024809;
  if ( a1 && a2 && !wcschr(a1, 0x40u) )
  {
    nSize = 16;
    if ( !GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &nSize) )
      return (unsigned int)ResultFromKnownLastError();
    v5 = wcschr(a1, 0x5Cu);
    if ( !v5 )
      return (unsigned int)StringCchPrintfW(a2, 0x111u, L"%s\\%s", Buffer, a1);
    cchCount2 = v5 - a1;
    v8 = -1;
    do
      ++v8;
    while ( Buffer[v8] );
    if ( v8 == (unsigned int)cchCount2 && CompareStringW(0x7Fu, 1u, a1, cchCount2, Buffer, cchCount2) == 2 )
      return (unsigned int)StringCchCopyW(a2, 0x111u, a1);
  }
  return v4;
}

```

## disassembly

```asm
0x180016aa8  mov     [rsp+arg_10], rbx
0x180016aad  push    rbp
0x180016aae  push    rsi
0x180016aaf  push    rdi
0x180016ab0  sub     rsp, 60h
0x180016ab4  mov     rax, cs:__security_cookie
0x180016abb  xor     rax, rsp
0x180016abe  mov     [rsp+78h+var_20], rax
0x180016ac3  xor     ebp, ebp
0x180016ac5  mov     rsi, rdx
0x180016ac8  mov     rdi, rcx
0x180016acb  mov     ebx, 80070057h
0x180016ad0  test    rcx, rcx
0x180016ad3  jz      loc_180016BA9
0x180016ad9  test    rdx, rdx
0x180016adc  jz      loc_180016BA9
0x180016ae2  lea     edx, [rbp+40h]; Ch
0x180016ae5  call    cs:__imp_wcschr
0x180016aeb  test    rax, rax
0x180016aee  jnz     loc_180016BA9
0x180016af4  lea     r8, [rsp+78h+nSize]; nSize
0x180016af9  mov     [rsp+78h+nSize], 10h
0x180016b01  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x180016b06  lea     ecx, [rbp+4]; NameType
0x180016b09  call    cs:__imp_GetComputerNameExW
0x180016b0f  test    eax, eax
0x180016b11  jz      loc_180016BA2
0x180016b17  lea     edx, [rbp+5Ch]; Ch
0x180016b1a  mov     rcx, rdi; Str
0x180016b1d  call    cs:__imp_wcschr
0x180016b23  mov     r9, rax
0x180016b26  test    rax, rax
0x180016b29  jnz     short loc_180016B4B
0x180016b2b  lea     r9, [rsp+78h+Buffer]
0x180016b30  mov     [rsp+78h+lpString2], rdi
0x180016b35  lea     r8, aSS; "%s\\%s"
0x180016b3c  mov     edx, 111h; unsigned __int64
0x180016b41  mov     rcx, rsi; unsigned __int16 *
0x180016b44  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016b49  jmp     short loc_180016BA7
0x180016b4b  sub     r9, rdi
0x180016b4e  lea     rax, [rsp+78h+Buffer]
0x180016b53  sar     r9, 1; cchCount1
0x180016b56  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180016b5a  inc     rcx
0x180016b5d  cmp     [rax+rcx*2], bp
0x180016b61  jnz     short loc_180016B5A
0x180016b63  mov     eax, r9d
0x180016b66  cmp     rcx, rax
0x180016b69  jnz     short loc_180016BA9
0x180016b6b  mov     edx, 1; dwCmpFlags
0x180016b70  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x180016b75  lea     rax, [rsp+78h+Buffer]
0x180016b7a  mov     r8, rdi; lpString1
0x180016b7d  mov     [rsp+78h+lpString2], rax; lpString2
0x180016b82  lea     ecx, [rdx+7Eh]; Locale
0x180016b85  call    cs:__imp_CompareStringW
0x180016b8b  cmp     eax, 2
0x180016b8e  jnz     short loc_180016BA9
0x180016b90  mov     r8, rdi; unsigned __int16 *
0x180016b93  mov     edx, 111h; unsigned __int64
0x180016b98  mov     rcx, rsi; unsigned __int16 *
0x180016b9b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016ba0  jmp     short loc_180016BA7
0x180016ba2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180016ba7  mov     ebx, eax
0x180016ba9  mov     eax, ebx
0x180016bab  mov     rcx, [rsp+78h+var_20]
0x180016bb0  xor     rcx, rsp; StackCookie
0x180016bb3  call    __security_check_cookie
0x180016bb8  mov     rbx, [rsp+78h+arg_10]
0x180016bc0  add     rsp, 60h
0x180016bc4  pop     rdi
0x180016bc5  pop     rsi
0x180016bc6  pop     rbp
0x180016bc7  retn
```
