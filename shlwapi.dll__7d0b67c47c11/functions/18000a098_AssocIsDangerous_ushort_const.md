# _AssocIsDangerous(ushort const *)

- ea: `0x18000a098`
- end: `0x18000a207`
- name: `?_AssocIsDangerous@@YAHPEBG@Z`
- size: `367`
- prototype: `__int64 __fastcall(LPCWSTR szFullPathname)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000dfc0`

## callees

- `0x18000a098`
- `0x18000a210`
- `0x180012550`
- `0x180014004`
- `0x1800369c5`
- `0x180037010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x18000a151`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18000a151`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferiIsExecutableFileType` at `0x18000a1e8`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferiIsExecutableFileType` at `0x18000a1e8`

## pseudocode

```c
__int64 __fastcall _AssocIsDangerous(LPCWSTR szFullPathname)
{
  unsigned int v2; // ebx
  GUID Buf1; // [rsp+40h] [rbp-38h] BYREF
  void *ppv; // [rsp+50h] [rbp-28h] BYREF
  int v6; // [rsp+58h] [rbp-20h]
  int v7; // [rsp+5Ch] [rbp-1Ch]

  if ( !szFullPathname || *szFullPathname && (*szFullPathname != 46 || szFullPathname[1]) )
  {
    v2 = IsTypeInList(szFullPathname);
    if ( !v2 && szFullPathname )
    {
      ppv = 0;
      Buf1 = CLSID_QueryAssociations;
      if ( memcmp_0(&Buf1, &CLSID_QueryAssociations, 0x10u) )
      {
        if ( memcmp_0(&Buf1, &IID_IQueryAssociations, v2 + 16) )
          goto LABEL_21;
      }
      if ( SHCoCreateInstance(0, &CLSID_QueryAssociations, 0, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, &ppv) < 0 )
        goto LABEL_21;
      if ( (*(int (__fastcall **)(void *, _QWORD, LPCWSTR, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
             ppv,
             0,
             szFullPathname,
             0,
             0) >= 0 )
      {
        v6 = 0;
        v7 = 4;
        if ( (*(int (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)ppv + 48LL))(ppv, 0, 5) >= 0 )
          v2 = v6 & 0x20000;
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( !v2 )
      {
LABEL_21:
        if ( *szFullPathname && (unsigned __int8)IsSaferiIsExecutableFileTypePresent() )
          return SaferiIsExecutableFileType(szFullPathname, 1u);
      }
    }
  }
  else
  {
    return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x18000a098  push    rbp
0x18000a09a  push    rbx
0x18000a09b  push    rsi
0x18000a09c  push    rdi
0x18000a09d  mov     rbp, rsp
0x18000a0a0  sub     rsp, 78h
0x18000a0a4  mov     rax, cs:__security_cookie
0x18000a0ab  xor     rax, rsp
0x18000a0ae  mov     [rbp+var_18], rax
0x18000a0b2  xor     esi, esi
0x18000a0b4  mov     rdi, rcx
0x18000a0b7  test    rcx, rcx
0x18000a0ba  jz      short loc_18000A0D9
0x18000a0bc  cmp     si, [rcx]
0x18000a0bf  jz      short loc_18000A0CF
0x18000a0c1  lea     eax, [rsi+2Eh]
0x18000a0c4  cmp     ax, [rcx]
0x18000a0c7  jnz     short loc_18000A0D9
0x18000a0c9  cmp     si, [rcx+2]
0x18000a0cd  jnz     short loc_18000A0D9
0x18000a0cf  mov     ebx, 1
0x18000a0d4  jmp     loc_18000A1F0
0x18000a0d9  call    IsTypeInList
0x18000a0de  mov     ebx, eax
0x18000a0e0  test    eax, eax
0x18000a0e2  jnz     loc_18000A1F0
0x18000a0e8  test    rdi, rdi
0x18000a0eb  jz      loc_18000A1F0
0x18000a0f1  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x18000a0f8  lea     r8d, [rax+10h]; Size
0x18000a0fc  mov     [rbp+var_28], rsi
0x18000a100  lea     rdx, CLSID_QueryAssociations; Buf2
0x18000a107  lea     rcx, [rbp+Buf1]; Buf1
0x18000a10b  movdqu  [rbp+Buf1], xmm0
0x18000a110  call    memcmp_0
0x18000a115  test    eax, eax
0x18000a117  jz      short loc_18000A135
0x18000a119  lea     r8d, [rbx+10h]; Size
0x18000a11d  lea     rdx, IID_IQueryAssociations; Buf2
0x18000a124  lea     rcx, [rbp+Buf1]; Buf1
0x18000a128  call    memcmp_0
0x18000a12d  test    eax, eax
0x18000a12f  jnz     loc_18000A1D2
0x18000a135  lea     rax, [rbp+var_28]
0x18000a139  xor     r8d, r8d; pUnkOuter
0x18000a13c  lea     r9, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x18000a143  mov     [rsp+78h+ppv], rax; ppv
0x18000a148  lea     rdx, CLSID_QueryAssociations; pclsid
0x18000a14f  xor     ecx, ecx; pszCLSID
0x18000a151  call    cs:__imp_SHCoCreateInstance
0x18000a157  test    eax, eax
0x18000a159  js      short loc_18000A1D2
0x18000a15b  mov     rcx, [rbp+var_28]
0x18000a15f  xor     r9d, r9d
0x18000a162  mov     r8, rdi
0x18000a165  mov     [rsp+78h+ppv], rsi
0x18000a16a  xor     edx, edx
0x18000a16c  mov     rax, [rcx]
0x18000a16f  mov     rax, [rax+18h]
0x18000a173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a178  test    eax, eax
0x18000a17a  js      short loc_18000A1BE
0x18000a17c  mov     rcx, [rbp+var_28]
0x18000a180  lea     rdx, [rbp+var_1C]
0x18000a184  mov     [rsp+78h+var_50], rdx
0x18000a189  xor     r9d, r9d
0x18000a18c  lea     rdx, [rbp+var_20]
0x18000a190  mov     [rbp+var_20], esi
0x18000a193  mov     [rbp+var_1C], 4
0x18000a19a  mov     rax, [rcx]
0x18000a19d  mov     [rsp+78h+ppv], rdx
0x18000a1a2  lea     r8d, [r9+5]
0x18000a1a6  xor     edx, edx
0x18000a1a8  mov     rax, [rax+30h]
0x18000a1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1b1  test    eax, eax
0x18000a1b3  js      short loc_18000A1BE
0x18000a1b5  mov     ebx, [rbp+var_20]
0x18000a1b8  and     ebx, 20000h
0x18000a1be  mov     rcx, [rbp+var_28]
0x18000a1c2  mov     rax, [rcx]
0x18000a1c5  mov     rax, [rax+10h]
0x18000a1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1ce  test    ebx, ebx
0x18000a1d0  jnz     short loc_18000A1F0
0x18000a1d2  cmp     [rdi], si
0x18000a1d5  jz      short loc_18000A1F0
0x18000a1d7  call    IsSaferiIsExecutableFileTypePresent
0x18000a1dc  test    al, al
0x18000a1de  jz      short loc_18000A1F0
0x18000a1e0  mov     edx, 1; bFromShellExecute
0x18000a1e5  mov     rcx, rdi; szFullPathname
0x18000a1e8  call    cs:__imp_SaferiIsExecutableFileType
0x18000a1ee  mov     ebx, eax
0x18000a1f0  mov     eax, ebx
0x18000a1f2  mov     rcx, [rbp+var_18]
0x18000a1f6  xor     rcx, rsp; StackCookie
0x18000a1f9  call    __security_check_cookie
0x18000a1fe  add     rsp, 78h
0x18000a202  pop     rdi
0x18000a203  pop     rsi
0x18000a204  pop     rbx
0x18000a205  pop     rbp
0x18000a206  retn
```
