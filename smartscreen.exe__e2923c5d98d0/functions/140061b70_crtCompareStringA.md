# __crtCompareStringA

- ea: `0x140061b70`
- end: `0x140061f13`
- name: `__crtCompareStringA`
- size: `931`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140051e0c`

## callees

- `0x140025aa0`
- `0x140061b70`
- `0x1400624e0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x140061bb7`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x140061bdc`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x140061bb7`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x140061bdc`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x140061c2c`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x140061c2c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140061cc6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140061d6d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140061d9d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140061e49`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140061cc6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140061d6d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140061d9d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140061e49`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x140061ea2`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x140061ea2`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140061e60`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140061eb7`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140061ec5`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140061edb`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140061e60`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140061eb7`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140061ec5`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140061edb`
- `api-ms-win-crt-heap-l1-1-0!_malloc_base` at `0x140061d31`
- `api-ms-win-crt-heap-l1-1-0!_malloc_base` at `0x140061e08`
- `api-ms-win-crt-heap-l1-1-0!_malloc_base` at `0x140061d31`
- `api-ms-win-crt-heap-l1-1-0!_malloc_base` at `0x140061e08`

## pseudocode

```c
__int64 __fastcall _crtCompareStringA(
        const WCHAR *a1,
        __int64 a2,
        const char *a3,
        int a4,
        char *String,
        int a6,
        UINT CodePage)
{
  int v7; // edi
  int v9; // esi
  BYTE *i; // rax
  BYTE *j; // rax
  int v12; // eax
  int cchWideChar; // r13d
  size_t v14; // rcx
  __int64 v15; // rax
  void *v16; // rsp
  WCHAR *lpWideCharStr; // rbx
  WCHAR *v18; // rax
  int v19; // eax
  int v20; // r15d
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  __int64 v23; // rax
  void *v24; // rsp
  WCHAR *p_lpMultiByteStr; // rdi
  WCHAR *v26; // rax
  WCHAR *v27; // r14
  WCHAR *v28; // rcx
  bool v29; // zf
  unsigned int v30; // edi
  _BYTE v32[32]; // [rsp+0h] [rbp-50h] BYREF
  LPCCH lpMultiByteStr; // [rsp+50h] [rbp+0h] BYREF
  LPCWSTR lpLocaleName; // [rsp+58h] [rbp+8h]
  _cpinfo CPInfo; // [rsp+60h] [rbp+10h] BYREF

  v7 = a4;
  lpLocaleName = a1;
  lpMultiByteStr = String;
  if ( a4 <= 0 )
  {
    if ( a4 < -1 )
      return 0;
  }
  else
  {
    v7 = __strncnt(a3, a4);
  }
  v9 = a6;
  if ( a6 <= 0 )
  {
    if ( a6 < -1 )
      return 0;
  }
  else
  {
    v9 = __strncnt(String, a6);
  }
  if ( v7 && v9 )
    goto LABEL_29;
  if ( v7 == v9 )
    return 2;
  if ( v9 > 1 )
    return 1;
  if ( v7 > 1 )
    return 3;
  memset(&CPInfo, 0, sizeof(CPInfo));
  if ( !GetCPInfo(CodePage, &CPInfo) )
    return 0;
  if ( v7 > 0 )
  {
    if ( CPInfo.MaxCharSize >= 2 )
    {
      for ( i = CPInfo.LeadByte; *i && i[1]; i += 2 )
      {
        if ( (unsigned int)*a3 >= *i && (unsigned int)*a3 <= i[1] )
          return 2;
      }
    }
    return 3;
  }
  if ( v9 > 0 )
  {
    if ( CPInfo.MaxCharSize >= 2 )
    {
      for ( j = CPInfo.LeadByte; *j && j[1]; j += 2 )
      {
        if ( (unsigned __int8)*String >= *j && (unsigned __int8)*String <= j[1] )
          return 2;
      }
    }
    return 1;
  }
LABEL_29:
  v12 = MultiByteToWideChar(CodePage, 9u, a3, v7, 0, 0);
  cchWideChar = v12;
  if ( !v12 )
    return 0;
  v14 = (2LL * v12 + 16) & -(__int64)(2LL * v12 < (unsigned __int64)(2LL * v12 + 16));
  if ( !v14 )
    return 0;
  if ( v14 > 0x400 )
  {
    v18 = (WCHAR *)_malloc_base(v14);
    lpWideCharStr = v18;
    if ( !v18 )
      goto LABEL_39;
    *(_DWORD *)v18 = 56797;
  }
  else
  {
    v15 = v14 + 15;
    if ( v14 + 15 < v14 )
      v15 = 0xFFFFFFFFFFFFFF0LL;
    v16 = alloca(v15 & 0xFFFFFFFFFFFFFFF0uLL);
    lpWideCharStr = (WCHAR *)&lpMultiByteStr;
    if ( v32 == (_BYTE *)-80LL )
      return 0;
    LODWORD(lpMultiByteStr) = 52428;
  }
  lpWideCharStr += 8;
LABEL_39:
  if ( !lpWideCharStr )
    return 0;
  if ( !MultiByteToWideChar(CodePage, 1u, a3, v7, lpWideCharStr, cchWideChar) )
    goto LABEL_61;
  v19 = MultiByteToWideChar(CodePage, 9u, String, v9, 0, 0);
  v20 = v19;
  if ( !v19 )
    goto LABEL_61;
  v21 = 2LL * v19 + 16;
  v22 = v21 & -(__int64)(2LL * v19 < v21);
  if ( !v22 )
    goto LABEL_61;
  if ( v22 > 0x400 )
  {
    v26 = (WCHAR *)_malloc_base(v21 & -(__int64)(2LL * v19 < v21));
    p_lpMultiByteStr = v26;
    if ( !v26 )
      goto LABEL_51;
    *(_DWORD *)v26 = 56797;
  }
  else
  {
    v23 = v22 + 15;
    if ( v22 + 15 < v22 )
      v23 = 0xFFFFFFFFFFFFFF0LL;
    v24 = alloca(v23 & 0xFFFFFFFFFFFFFFF0uLL);
    p_lpMultiByteStr = (WCHAR *)&lpMultiByteStr;
    if ( v32 == (_BYTE *)-80LL )
      goto LABEL_61;
    LODWORD(lpMultiByteStr) = 52428;
  }
  p_lpMultiByteStr += 8;
LABEL_51:
  if ( !p_lpMultiByteStr )
  {
LABEL_61:
    v28 = lpWideCharStr - 8;
    v29 = *((_DWORD *)lpWideCharStr - 4) == 56797;
LABEL_62:
    if ( v29 )
      _free_base(v28);
    return 0;
  }
  v27 = p_lpMultiByteStr - 8;
  if ( !MultiByteToWideChar(CodePage, 1u, lpMultiByteStr, v9, p_lpMultiByteStr, v20) )
  {
    if ( *(_DWORD *)v27 == 56797 )
      _free_base(v27);
    v28 = lpWideCharStr - 8;
    v29 = *((_DWORD *)lpWideCharStr - 4) == 56797;
    goto LABEL_62;
  }
  v30 = CompareStringEx(lpLocaleName, 0x1000u, lpWideCharStr, cchWideChar, p_lpMultiByteStr, v20, 0, 0, 0);
  if ( *(_DWORD *)v27 == 56797 )
    _free_base(v27);
  if ( *((_DWORD *)lpWideCharStr - 4) == 56797 )
    _free_base(lpWideCharStr - 8);
  return v30;
}

```

## disassembly

```asm
0x140061b70  push    rbp
0x140061b72  push    rbx
0x140061b73  push    rsi
0x140061b74  push    rdi
0x140061b75  push    r13
0x140061b77  push    r14
0x140061b79  push    r15
0x140061b7b  sub     rsp, 80h
0x140061b82  lea     rbp, [rsp+50h]
0x140061b87  mov     rax, cs:__security_cookie
0x140061b8e  xor     rax, rbp
0x140061b91  mov     [rbp+60h+var_38], rax
0x140061b95  mov     r15, [rbp+60h+String]
0x140061b9c  xor     ebx, ebx
0x140061b9e  movsxd  rdi, r9d
0x140061ba1  mov     r14, r8
0x140061ba4  mov     [rbp+60h+lpLocaleName], rcx
0x140061ba8  mov     [rbp+60h+lpMultiByteStr], r15
0x140061bac  test    r9d, r9d
0x140061baf  jle     short loc_140061BC2
0x140061bb1  mov     rdx, rdi; Count
0x140061bb4  mov     rcx, r8; String
0x140061bb7  call    cs:__imp___strncnt
0x140061bbd  mov     rdi, rax
0x140061bc0  jmp     short loc_140061BCB
0x140061bc2  cmp     edi, 0FFFFFFFFh
0x140061bc5  jl      loc_140061EE1
0x140061bcb  movsxd  rsi, [rbp+60h+arg_28]
0x140061bd2  test    esi, esi
0x140061bd4  jle     short loc_140061BE7
0x140061bd6  mov     rdx, rsi; Count
0x140061bd9  mov     rcx, r15; String
0x140061bdc  call    cs:__imp___strncnt
0x140061be2  mov     rsi, rax
0x140061be5  jmp     short loc_140061BF0
0x140061be7  cmp     esi, 0FFFFFFFFh
0x140061bea  jl      loc_140061EE1
0x140061bf0  test    edi, edi
0x140061bf2  jz      short loc_140061BFC
0x140061bf4  test    esi, esi
0x140061bf6  jnz     loc_140061CAC
0x140061bfc  cmp     edi, esi
0x140061bfe  jz      loc_140061F0C
0x140061c04  cmp     esi, 1
0x140061c07  jg      loc_140061F05
0x140061c0d  cmp     edi, 1
0x140061c10  jg      loc_140061EFE
0x140061c16  mov     ecx, [rbp+60h+CodePage]; CodePage
0x140061c1c  lea     rdx, [rbp+60h+CPInfo]; lpCPInfo
0x140061c20  xorps   xmm0, xmm0
0x140061c23  xor     eax, eax
0x140061c25  movups  xmmword ptr [rbp+60h+CPInfo.MaxCharSize], xmm0
0x140061c29  mov     dword ptr [rbp+60h+CPInfo.LeadByte+0Ah], eax
0x140061c2c  call    cs:__imp_GetCPInfo
0x140061c32  test    eax, eax
0x140061c34  jz      loc_140061EE1
0x140061c3a  test    edi, edi
0x140061c3c  jle     short loc_140061C73
0x140061c3e  cmp     [rbp+60h+CPInfo.MaxCharSize], 2
0x140061c42  jb      loc_140061EFE
0x140061c48  lea     rax, [rbp+60h+CPInfo.LeadByte]
0x140061c4c  cmp     [rax], bl
0x140061c4e  jz      loc_140061EFE
0x140061c54  cmp     [rax+1], bl
0x140061c57  jz      loc_140061EFE
0x140061c5d  mov     cl, [r14]
0x140061c60  cmp     cl, [rax]
0x140061c62  jb      short loc_140061C6D
0x140061c64  cmp     cl, [rax+1]
0x140061c67  jbe     loc_140061F0C
0x140061c6d  add     rax, 2
0x140061c71  jmp     short loc_140061C4C
0x140061c73  test    esi, esi
0x140061c75  jle     short loc_140061CAC
0x140061c77  cmp     [rbp+60h+CPInfo.MaxCharSize], 2
0x140061c7b  jb      loc_140061F05
0x140061c81  lea     rax, [rbp+60h+CPInfo.LeadByte]
0x140061c85  cmp     [rax], bl
0x140061c87  jz      loc_140061F05
0x140061c8d  cmp     [rax+1], bl
0x140061c90  jz      loc_140061F05
0x140061c96  mov     cl, [r15]
0x140061c99  cmp     cl, [rax]
0x140061c9b  jb      short loc_140061CA6
0x140061c9d  cmp     cl, [rax+1]
0x140061ca0  jbe     loc_140061F0C
0x140061ca6  add     rax, 2
0x140061caa  jmp     short loc_140061C85
0x140061cac  mov     ecx, [rbp+60h+CodePage]; CodePage
0x140061cb2  mov     r9d, edi; cbMultiByte
0x140061cb5  mov     [rsp+0B0h+cchWideChar], ebx; cchWideChar
0x140061cb9  mov     r8, r14; lpMultiByteStr
0x140061cbc  mov     edx, 9; dwFlags
0x140061cc1  mov     [rsp+0B0h+lpWideCharStr], rbx; lpWideCharStr
0x140061cc6  call    cs:__imp_MultiByteToWideChar
0x140061ccc  movsxd  r13, eax
0x140061ccf  test    eax, eax
0x140061cd1  jz      loc_140061EE1
0x140061cd7  mov     rcx, r13
0x140061cda  add     rcx, rcx
0x140061cdd  lea     rdx, [rcx+10h]
0x140061ce1  cmp     rcx, rdx
0x140061ce4  sbb     rcx, rcx
0x140061ce7  and     rcx, rdx; Size
0x140061cea  jz      loc_140061EE1
0x140061cf0  mov     rdx, 0FFFFFFFFFFFFFF0h
0x140061cfa  cmp     rcx, 400h
0x140061d01  ja      short loc_140061D31
0x140061d03  lea     rax, [rcx+0Fh]
0x140061d07  cmp     rax, rcx
0x140061d0a  ja      short loc_140061D0F
0x140061d0c  mov     rax, rdx
0x140061d0f  and     rax, 0FFFFFFFFFFFFFFF0h
0x140061d13  call    _alloca_probe
0x140061d18  sub     rsp, rax
0x140061d1b  lea     rbx, [rsp+0B0h+lpMultiByteStr]
0x140061d20  test    rbx, rbx
0x140061d23  jz      loc_140061EE1
0x140061d29  mov     dword ptr [rbx], 0CCCCh
0x140061d2f  jmp     short loc_140061D45
0x140061d31  call    cs:__imp__malloc_base
0x140061d37  mov     rbx, rax
0x140061d3a  test    rax, rax
0x140061d3d  jz      short loc_140061D49
0x140061d3f  mov     dword ptr [rax], 0DDDDh
0x140061d45  add     rbx, 10h
0x140061d49  test    rbx, rbx
0x140061d4c  jz      loc_140061EE1
0x140061d52  mov     ecx, [rbp+60h+CodePage]; CodePage
0x140061d58  mov     r9d, edi; cbMultiByte
0x140061d5b  mov     [rsp+0B0h+cchWideChar], r13d; cchWideChar
0x140061d60  mov     r8, r14; lpMultiByteStr
0x140061d63  mov     edx, 1; dwFlags
0x140061d68  mov     [rsp+0B0h+lpWideCharStr], rbx; lpWideCharStr
0x140061d6d  call    cs:__imp_MultiByteToWideChar
0x140061d73  test    eax, eax
0x140061d75  jz      loc_140061ECF
0x140061d7b  mov     ecx, [rbp+60h+CodePage]; CodePage
0x140061d81  mov     r9d, esi; cbMultiByte
0x140061d84  mov     [rsp+0B0h+cchWideChar], 0; cchWideChar
0x140061d8c  mov     r8, r15; lpMultiByteStr
0x140061d8f  mov     edx, 9; dwFlags
0x140061d94  mov     [rsp+0B0h+lpWideCharStr], 0; lpWideCharStr
0x140061d9d  call    cs:__imp_MultiByteToWideChar
0x140061da3  movsxd  r15, eax
0x140061da6  test    eax, eax
0x140061da8  jz      loc_140061ECF
0x140061dae  mov     rax, r15
0x140061db1  add     rax, rax
0x140061db4  lea     rcx, [rax+10h]
0x140061db8  cmp     rax, rcx
0x140061dbb  sbb     rdx, rdx
0x140061dbe  and     rdx, rcx
0x140061dc1  jz      loc_140061ECF
0x140061dc7  cmp     rdx, 400h
0x140061dce  ja      short loc_140061E05
0x140061dd0  lea     rax, [rdx+0Fh]
0x140061dd4  cmp     rax, rdx
0x140061dd7  ja      short loc_140061DE3
0x140061dd9  mov     rax, 0FFFFFFFFFFFFFF0h
0x140061de3  and     rax, 0FFFFFFFFFFFFFFF0h
0x140061de7  call    _alloca_probe
0x140061dec  sub     rsp, rax
0x140061def  lea     rdi, [rsp+0B0h+lpMultiByteStr]
0x140061df4  test    rdi, rdi
0x140061df7  jz      loc_140061ECF
0x140061dfd  mov     dword ptr [rdi], 0CCCCh
0x140061e03  jmp     short loc_140061E1C
0x140061e05  mov     rcx, rdx; Size
0x140061e08  call    cs:__imp__malloc_base
0x140061e0e  mov     rdi, rax
0x140061e11  test    rax, rax
0x140061e14  jz      short loc_140061E20
0x140061e16  mov     dword ptr [rax], 0DDDDh
0x140061e1c  add     rdi, 10h
0x140061e20  test    rdi, rdi
0x140061e23  jz      loc_140061ECF
0x140061e29  mov     r8, [rbp+60h+lpMultiByteStr]; lpMultiByteStr
0x140061e2d  lea     r14, [rdi-10h]
0x140061e31  mov     ecx, [rbp+60h+CodePage]; CodePage
0x140061e37  mov     r9d, esi; cbMultiByte
0x140061e3a  mov     [rsp+0B0h+cchWideChar], r15d; cchWideChar
0x140061e3f  mov     edx, 1; dwFlags
0x140061e44  mov     [rsp+0B0h+lpWideCharStr], rdi; lpWideCharStr
0x140061e49  call    cs:__imp_MultiByteToWideChar
0x140061e4f  test    eax, eax
0x140061e51  jnz     short loc_140061E6E
0x140061e53  mov     edi, 0DDDDh
0x140061e58  cmp     [r14], edi
0x140061e5b  jnz     short loc_140061E66
0x140061e5d  mov     rcx, r14; Block
0x140061e60  call    cs:__imp__free_base
0x140061e66  lea     rcx, [rbx-10h]
0x140061e6a  cmp     [rcx], edi
0x140061e6c  jmp     short loc_140061ED9
0x140061e6e  mov     rcx, [rbp+60h+lpLocaleName]; lpLocaleName
0x140061e72  mov     r9d, r13d; cchCount1
0x140061e75  mov     [rsp+0B0h+lParam], 0; lParam
0x140061e7e  mov     r8, rbx; lpString1
0x140061e81  mov     [rsp+0B0h+lpReserved], 0; lpReserved
0x140061e8a  mov     edx, 1000h; dwCmpFlags
0x140061e8f  mov     [rsp+0B0h+lpVersionInformation], 0; lpVersionInformation
0x140061e98  mov     [rsp+0B0h+cchWideChar], r15d; cchCount2
0x140061e9d  mov     [rsp+0B0h+lpWideCharStr], rdi; lpString2
0x140061ea2  call    cs:__imp_CompareStringEx
0x140061ea8  mov     esi, 0DDDDh
0x140061ead  mov     edi, eax
0x140061eaf  cmp     [r14], esi
0x140061eb2  jnz     short loc_140061EBD
0x140061eb4  mov     rcx, r14; Block
0x140061eb7  call    cs:__imp__free_base
0x140061ebd  lea     rcx, [rbx-10h]; Block
0x140061ec1  cmp     [rcx], esi
0x140061ec3  jnz     short loc_140061ECB
0x140061ec5  call    cs:__imp__free_base
0x140061ecb  mov     eax, edi
0x140061ecd  jmp     short loc_140061EE3
0x140061ecf  lea     rcx, [rbx-10h]; Block
0x140061ed3  cmp     dword ptr [rcx], 0DDDDh
0x140061ed9  jnz     short loc_140061EE1
0x140061edb  call    cs:__imp__free_base
0x140061ee1  xor     eax, eax
0x140061ee3  mov     rcx, [rbp+60h+var_38]
0x140061ee7  xor     rcx, rbp; StackCookie
0x140061eea  call    __security_check_cookie
0x140061eef  lea     rsp, [rbp+30h]
0x140061ef3  pop     r15
0x140061ef5  pop     r14
0x140061ef7  pop     r13
0x140061ef9  pop     rdi
0x140061efa  pop     rsi
0x140061efb  pop     rbx
0x140061efc  pop     rbp
0x140061efd  retn
0x140061efe  mov     eax, 3
0x140061f03  jmp     short loc_140061EE3
0x140061f05  mov     eax, 1
0x140061f0a  jmp     short loc_140061EE3
0x140061f0c  mov     eax, 2
0x140061f11  jmp     short loc_140061EE3
```
