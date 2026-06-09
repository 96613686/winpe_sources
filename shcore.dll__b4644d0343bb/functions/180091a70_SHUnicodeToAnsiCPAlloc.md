# SHUnicodeToAnsiCPAlloc

- ea: `0x180091a70`
- end: `0x180091b4e`
- name: `SHUnicodeToAnsiCPAlloc`
- size: `222`
- prototype: `__int64 __fastcall(UINT CodePage, LPCWCH lpWideCharStr)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001abfc`
- `0x18001c82c`
- `0x180091a70`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180091abb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180091b12`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180091abb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180091b12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091b35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091b35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180091ade`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180091ade`

## pseudocode

```c
__int64 __fastcall SHUnicodeToAnsiCPAlloc(UINT CodePage, LPCWCH lpWideCharStr, CHAR **a3)
{
  __int64 v3; // rax
  int v7; // r12d
  int v8; // eax
  SIZE_T cbMultiByte; // r14
  int Error; // eax
  int v11; // ebx
  CHAR *lpMultiByteStr; // rax
  CHAR *v13; // rdi

  v3 = -1;
  do
    ++v3;
  while ( lpWideCharStr[v3] );
  v7 = v3 + 1;
  v8 = WideCharToMultiByte(CodePage, 0, lpWideCharStr, v3 + 1, 0, 0, 0, 0);
  cbMultiByte = v8;
  if ( v8 )
  {
    *a3 = 0;
    goto LABEL_6;
  }
  Error = ResultFromLastError();
  *a3 = 0;
  v11 = Error;
  if ( Error >= 0 )
  {
LABEL_6:
    lpMultiByteStr = (CHAR *)CoTaskMemAlloc(cbMultiByte);
    v13 = lpMultiByteStr;
    if ( !lpMultiByteStr )
      return (unsigned int)-2147024882;
    if ( WideCharToMultiByte(CodePage, 0, lpWideCharStr, v7, lpMultiByteStr, cbMultiByte, 0, 0) )
    {
      v11 = 0;
    }
    else
    {
      v11 = ResultFromKnownLastError();
      if ( v11 < 0 )
      {
LABEL_12:
        CoTaskMemFree(v13);
        return (unsigned int)v11;
      }
    }
    *a3 = v13;
    v13 = 0;
    goto LABEL_12;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180091a70  push    rbx
0x180091a72  push    rbp
0x180091a73  push    rsi
0x180091a74  push    rdi
0x180091a75  push    r12
0x180091a77  push    r13
0x180091a79  push    r14
0x180091a7b  push    r15
0x180091a7d  sub     rsp, 48h
0x180091a81  or      rax, 0FFFFFFFFFFFFFFFFh
0x180091a85  mov     rsi, r8
0x180091a88  xor     r13d, r13d
0x180091a8b  mov     rbp, rdx
0x180091a8e  mov     r15d, ecx
0x180091a91  inc     rax
0x180091a94  cmp     [rdx+rax*2], r13w
0x180091a99  jnz     short loc_180091A91
0x180091a9b  mov     [rsp+88h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180091aa0  lea     r12d, [rax+1]
0x180091aa4  mov     [rsp+88h+lpDefaultChar], r13; lpDefaultChar
0x180091aa9  mov     r9d, r12d; cchWideChar
0x180091aac  mov     [rsp+88h+cbMultiByte], r13d; cbMultiByte
0x180091ab1  mov     r8, rbp; lpWideCharStr
0x180091ab4  xor     edx, edx; dwFlags
0x180091ab6  mov     [rsp+88h+lpMultiByteStr], r13; lpMultiByteStr
0x180091abb  call    cs:__imp_WideCharToMultiByte
0x180091ac1  movsxd  r14, eax
0x180091ac4  test    eax, eax
0x180091ac6  jz      short loc_180091ACD
0x180091ac8  mov     [rsi], r13
0x180091acb  jmp     short loc_180091ADB
0x180091acd  call    ResultFromLastError
0x180091ad2  mov     [rsi], r13
0x180091ad5  mov     ebx, eax
0x180091ad7  test    eax, eax
0x180091ad9  js      short loc_180091B3B
0x180091adb  mov     rcx, r14; cb
0x180091ade  call    cs:__imp_CoTaskMemAlloc
0x180091ae4  mov     rdi, rax
0x180091ae7  test    rax, rax
0x180091aea  jnz     short loc_180091AF3
0x180091aec  mov     ebx, 8007000Eh
0x180091af1  jmp     short loc_180091B3B
0x180091af3  mov     [rsp+88h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180091af8  mov     r9d, r12d; cchWideChar
0x180091afb  mov     [rsp+88h+lpDefaultChar], r13; lpDefaultChar
0x180091b00  mov     r8, rbp; lpWideCharStr
0x180091b03  mov     [rsp+88h+cbMultiByte], r14d; cbMultiByte
0x180091b08  xor     edx, edx; dwFlags
0x180091b0a  mov     ecx, r15d; CodePage
0x180091b0d  mov     [rsp+88h+lpMultiByteStr], rdi; lpMultiByteStr
0x180091b12  call    cs:__imp_WideCharToMultiByte
0x180091b18  test    eax, eax
0x180091b1a  jz      short loc_180091B21
0x180091b1c  mov     ebx, r13d
0x180091b1f  jmp     short loc_180091B2C
0x180091b21  call    ResultFromKnownLastError
0x180091b26  mov     ebx, eax
0x180091b28  test    eax, eax
0x180091b2a  js      short loc_180091B32
0x180091b2c  mov     [rsi], rdi
0x180091b2f  mov     rdi, r13
0x180091b32  mov     rcx, rdi; pv
0x180091b35  call    cs:__imp_CoTaskMemFree
0x180091b3b  mov     eax, ebx
0x180091b3d  add     rsp, 48h
0x180091b41  pop     r15
0x180091b43  pop     r14
0x180091b45  pop     r13
0x180091b47  pop     r12
0x180091b49  pop     rdi
0x180091b4a  pop     rsi
0x180091b4b  pop     rbp
0x180091b4c  pop     rbx
0x180091b4d  retn
```
