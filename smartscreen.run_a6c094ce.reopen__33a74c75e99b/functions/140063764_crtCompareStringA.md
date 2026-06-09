# __crtCompareStringA

- ea: `0x140063764`
- end: `0x140063b5c`
- name: `__crtCompareStringA`
- size: `1016`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400537ec`

## callees

- `0x140026c20`
- `0x140063764`
- `0x1400641a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x1400637ab`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x1400637d6`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x1400637ab`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x1400637d6`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x14006382c`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x14006382c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400638cc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14006397f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400639b5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140063a6d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400638cc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14006397f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400639b5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140063a6d`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x140063ad2`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x140063ad2`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140063a8a`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140063aed`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140063b01`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140063b1d`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140063a8a`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140063aed`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140063b01`
- `api-ms-win-crt-heap-l1-1-0!_free_base` at `0x140063b1d`
- `api-ms-win-crt-heap-l1-1-0!_malloc_base` at `0x14006393d`
- `api-ms-win-crt-heap-l1-1-0!_malloc_base` at `0x140063a26`
- `api-ms-win-crt-heap-l1-1-0!_malloc_base` at `0x14006393d`
- `api-ms-win-crt-heap-l1-1-0!_malloc_base` at `0x140063a26`

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
0x140063764  push    rbp
0x140063766  push    rbx
0x140063767  push    rsi
0x140063768  push    rdi
0x140063769  push    r13
0x14006376b  push    r14
0x14006376d  push    r15
0x14006376f  sub     rsp, 80h
0x140063776  lea     rbp, [rsp+50h]
0x14006377b  mov     rax, cs:__security_cookie
0x140063782  xor     rax, rbp
0x140063785  mov     [rbp+60h+var_38], rax
0x140063789  mov     r15, [rbp+60h+String]
0x140063790  xor     ebx, ebx
0x140063792  movsxd  rdi, r9d
0x140063795  mov     r14, r8
0x140063798  mov     [rbp+60h+lpLocaleName], rcx
0x14006379c  mov     [rbp+60h+lpMultiByteStr], r15
0x1400637a0  test    r9d, r9d
0x1400637a3  jle     short loc_1400637BC
0x1400637a5  mov     rdx, rdi; Count
0x1400637a8  mov     rcx, r8; String
0x1400637ab  call    cs:__imp___strncnt
0x1400637b2  nop     dword ptr [rax+rax+00h]
0x1400637b7  mov     rdi, rax
0x1400637ba  jmp     short loc_1400637C5
0x1400637bc  cmp     edi, 0FFFFFFFFh
0x1400637bf  jl      loc_140063B29
0x1400637c5  movsxd  rsi, [rbp+60h+arg_28]
0x1400637cc  test    esi, esi
0x1400637ce  jle     short loc_1400637E7
0x1400637d0  mov     rdx, rsi; Count
0x1400637d3  mov     rcx, r15; String
0x1400637d6  call    cs:__imp___strncnt
0x1400637dd  nop     dword ptr [rax+rax+00h]
0x1400637e2  mov     rsi, rax
0x1400637e5  jmp     short loc_1400637F0
0x1400637e7  cmp     esi, 0FFFFFFFFh
0x1400637ea  jl      loc_140063B29
0x1400637f0  test    edi, edi
0x1400637f2  jz      short loc_1400637FC
0x1400637f4  test    esi, esi
0x1400637f6  jnz     loc_1400638B2
0x1400637fc  cmp     edi, esi
0x1400637fe  jz      loc_140063B55
0x140063804  cmp     esi, 1
0x140063807  jg      loc_140063B4E
0x14006380d  cmp     edi, 1
0x140063810  jg      loc_140063B47
0x140063816  mov     ecx, [rbp+60h+CodePage]; CodePage
0x14006381c  lea     rdx, [rbp+60h+CPInfo]; lpCPInfo
0x140063820  xorps   xmm0, xmm0
0x140063823  xor     eax, eax
0x140063825  movups  xmmword ptr [rbp+60h+CPInfo.MaxCharSize], xmm0
0x140063829  mov     dword ptr [rbp+60h+CPInfo.LeadByte+0Ah], eax
0x14006382c  call    cs:__imp_GetCPInfo
0x140063833  nop     dword ptr [rax+rax+00h]
0x140063838  test    eax, eax
0x14006383a  jz      loc_140063B29
0x140063840  test    edi, edi
0x140063842  jle     short loc_140063879
0x140063844  cmp     [rbp+60h+CPInfo.MaxCharSize], 2
0x140063848  jb      loc_140063B47
0x14006384e  lea     rax, [rbp+60h+CPInfo.LeadByte]
0x140063852  cmp     [rax], bl
0x140063854  jz      loc_140063B47
0x14006385a  cmp     [rax+1], bl
0x14006385d  jz      loc_140063B47
0x140063863  mov     cl, [r14]
0x140063866  cmp     cl, [rax]
0x140063868  jb      short loc_140063873
0x14006386a  cmp     cl, [rax+1]
0x14006386d  jbe     loc_140063B55
0x140063873  add     rax, 2
0x140063877  jmp     short loc_140063852
0x140063879  test    esi, esi
0x14006387b  jle     short loc_1400638B2
0x14006387d  cmp     [rbp+60h+CPInfo.MaxCharSize], 2
0x140063881  jb      loc_140063B4E
0x140063887  lea     rax, [rbp+60h+CPInfo.LeadByte]
0x14006388b  cmp     [rax], bl
0x14006388d  jz      loc_140063B4E
0x140063893  cmp     [rax+1], bl
0x140063896  jz      loc_140063B4E
0x14006389c  mov     cl, [r15]
0x14006389f  cmp     cl, [rax]
0x1400638a1  jb      short loc_1400638AC
0x1400638a3  cmp     cl, [rax+1]
0x1400638a6  jbe     loc_140063B55
0x1400638ac  add     rax, 2
0x1400638b0  jmp     short loc_14006388B
0x1400638b2  mov     ecx, [rbp+60h+CodePage]; CodePage
0x1400638b8  mov     r9d, edi; cbMultiByte
0x1400638bb  mov     [rsp+0B0h+cchWideChar], ebx; cchWideChar
0x1400638bf  mov     r8, r14; lpMultiByteStr
0x1400638c2  mov     edx, 9; dwFlags
0x1400638c7  mov     [rsp+0B0h+lpWideCharStr], rbx; lpWideCharStr
0x1400638cc  call    cs:__imp_MultiByteToWideChar
0x1400638d3  nop     dword ptr [rax+rax+00h]
0x1400638d8  movsxd  r13, eax
0x1400638db  test    eax, eax
0x1400638dd  jz      loc_140063B29
0x1400638e3  mov     rcx, r13
0x1400638e6  add     rcx, rcx
0x1400638e9  lea     rdx, [rcx+10h]
0x1400638ed  cmp     rcx, rdx
0x1400638f0  sbb     rcx, rcx
0x1400638f3  and     rcx, rdx; Size
0x1400638f6  jz      loc_140063B29
0x1400638fc  mov     rdx, 0FFFFFFFFFFFFFF0h
0x140063906  cmp     rcx, 400h
0x14006390d  ja      short loc_14006393D
0x14006390f  lea     rax, [rcx+0Fh]
0x140063913  cmp     rax, rcx
0x140063916  ja      short loc_14006391B
0x140063918  mov     rax, rdx
0x14006391b  and     rax, 0FFFFFFFFFFFFFFF0h
0x14006391f  call    _alloca_probe
0x140063924  sub     rsp, rax
0x140063927  lea     rbx, [rsp+0B0h+lpMultiByteStr]
0x14006392c  test    rbx, rbx
0x14006392f  jz      loc_140063B29
0x140063935  mov     dword ptr [rbx], 0CCCCh
0x14006393b  jmp     short loc_140063957
0x14006393d  call    cs:__imp__malloc_base
0x140063944  nop     dword ptr [rax+rax+00h]
0x140063949  mov     rbx, rax
0x14006394c  test    rax, rax
0x14006394f  jz      short loc_14006395B
0x140063951  mov     dword ptr [rax], 0DDDDh
0x140063957  add     rbx, 10h
0x14006395b  test    rbx, rbx
0x14006395e  jz      loc_140063B29
0x140063964  mov     ecx, [rbp+60h+CodePage]; CodePage
0x14006396a  mov     r9d, edi; cbMultiByte
0x14006396d  mov     [rsp+0B0h+cchWideChar], r13d; cchWideChar
0x140063972  mov     r8, r14; lpMultiByteStr
0x140063975  mov     edx, 1; dwFlags
0x14006397a  mov     [rsp+0B0h+lpWideCharStr], rbx; lpWideCharStr
0x14006397f  call    cs:__imp_MultiByteToWideChar
0x140063986  nop     dword ptr [rax+rax+00h]
0x14006398b  test    eax, eax
0x14006398d  jz      loc_140063B11
0x140063993  mov     ecx, [rbp+60h+CodePage]; CodePage
0x140063999  mov     r9d, esi; cbMultiByte
0x14006399c  mov     [rsp+0B0h+cchWideChar], 0; cchWideChar
0x1400639a4  mov     r8, r15; lpMultiByteStr
0x1400639a7  mov     edx, 9; dwFlags
0x1400639ac  mov     [rsp+0B0h+lpWideCharStr], 0; lpWideCharStr
0x1400639b5  call    cs:__imp_MultiByteToWideChar
0x1400639bc  nop     dword ptr [rax+rax+00h]
0x1400639c1  movsxd  r15, eax
0x1400639c4  test    eax, eax
0x1400639c6  jz      loc_140063B11
0x1400639cc  mov     rax, r15
0x1400639cf  add     rax, rax
0x1400639d2  lea     rcx, [rax+10h]
0x1400639d6  cmp     rax, rcx
0x1400639d9  sbb     rdx, rdx
0x1400639dc  and     rdx, rcx
0x1400639df  jz      loc_140063B11
0x1400639e5  cmp     rdx, 400h
0x1400639ec  ja      short loc_140063A23
0x1400639ee  lea     rax, [rdx+0Fh]
0x1400639f2  cmp     rax, rdx
0x1400639f5  ja      short loc_140063A01
0x1400639f7  mov     rax, 0FFFFFFFFFFFFFF0h
0x140063a01  and     rax, 0FFFFFFFFFFFFFFF0h
0x140063a05  call    _alloca_probe
0x140063a0a  sub     rsp, rax
0x140063a0d  lea     rdi, [rsp+0B0h+lpMultiByteStr]
0x140063a12  test    rdi, rdi
0x140063a15  jz      loc_140063B11
0x140063a1b  mov     dword ptr [rdi], 0CCCCh
0x140063a21  jmp     short loc_140063A40
0x140063a23  mov     rcx, rdx; Size
0x140063a26  call    cs:__imp__malloc_base
0x140063a2d  nop     dword ptr [rax+rax+00h]
0x140063a32  mov     rdi, rax
0x140063a35  test    rax, rax
0x140063a38  jz      short loc_140063A44
0x140063a3a  mov     dword ptr [rax], 0DDDDh
0x140063a40  add     rdi, 10h
0x140063a44  test    rdi, rdi
0x140063a47  jz      loc_140063B11
0x140063a4d  mov     r8, [rbp+60h+lpMultiByteStr]; lpMultiByteStr
0x140063a51  lea     r14, [rdi-10h]
0x140063a55  mov     ecx, [rbp+60h+CodePage]; CodePage
0x140063a5b  mov     r9d, esi; cbMultiByte
0x140063a5e  mov     [rsp+0B0h+cchWideChar], r15d; cchWideChar
0x140063a63  mov     edx, 1; dwFlags
0x140063a68  mov     [rsp+0B0h+lpWideCharStr], rdi; lpWideCharStr
0x140063a6d  call    cs:__imp_MultiByteToWideChar
0x140063a74  nop     dword ptr [rax+rax+00h]
0x140063a79  test    eax, eax
0x140063a7b  jnz     short loc_140063A9E
0x140063a7d  mov     edi, 0DDDDh
0x140063a82  cmp     [r14], edi
0x140063a85  jnz     short loc_140063A96
0x140063a87  mov     rcx, r14; Block
0x140063a8a  call    cs:__imp__free_base
0x140063a91  nop     dword ptr [rax+rax+00h]
0x140063a96  lea     rcx, [rbx-10h]
0x140063a9a  cmp     [rcx], edi
0x140063a9c  jmp     short loc_140063B1B
0x140063a9e  mov     rcx, [rbp+60h+lpLocaleName]; lpLocaleName
0x140063aa2  mov     r9d, r13d; cchCount1
0x140063aa5  mov     [rsp+0B0h+lParam], 0; lParam
0x140063aae  mov     r8, rbx; lpString1
0x140063ab1  mov     [rsp+0B0h+lpReserved], 0; lpReserved
0x140063aba  mov     edx, 1000h; dwCmpFlags
0x140063abf  mov     [rsp+0B0h+lpVersionInformation], 0; lpVersionInformation
0x140063ac8  mov     [rsp+0B0h+cchWideChar], r15d; cchCount2
0x140063acd  mov     [rsp+0B0h+lpWideCharStr], rdi; lpString2
0x140063ad2  call    cs:__imp_CompareStringEx
0x140063ad9  nop     dword ptr [rax+rax+00h]
0x140063ade  mov     esi, 0DDDDh
0x140063ae3  mov     edi, eax
0x140063ae5  cmp     [r14], esi
0x140063ae8  jnz     short loc_140063AF9
0x140063aea  mov     rcx, r14; Block
0x140063aed  call    cs:__imp__free_base
0x140063af4  nop     dword ptr [rax+rax+00h]
0x140063af9  lea     rcx, [rbx-10h]; Block
0x140063afd  cmp     [rcx], esi
0x140063aff  jnz     short loc_140063B0D
0x140063b01  call    cs:__imp__free_base
0x140063b08  nop     dword ptr [rax+rax+00h]
0x140063b0d  mov     eax, edi
0x140063b0f  jmp     short loc_140063B2B
0x140063b11  lea     rcx, [rbx-10h]; Block
0x140063b15  cmp     dword ptr [rcx], 0DDDDh
0x140063b1b  jnz     short loc_140063B29
0x140063b1d  call    cs:__imp__free_base
0x140063b24  nop     dword ptr [rax+rax+00h]
0x140063b29  xor     eax, eax
0x140063b2b  mov     rcx, [rbp+60h+var_38]
0x140063b2f  xor     rcx, rbp; StackCookie
0x140063b32  call    __security_check_cookie
0x140063b37  lea     rsp, [rbp+30h]
0x140063b3b  pop     r15
0x140063b3d  pop     r14
0x140063b3f  pop     r13
0x140063b41  pop     rdi
0x140063b42  pop     rsi
0x140063b43  pop     rbx
0x140063b44  pop     rbp
0x140063b45  retn
0x140063b47  mov     eax, 3
0x140063b4c  jmp     short loc_140063B2B
0x140063b4e  mov     eax, 1
0x140063b53  jmp     short loc_140063B2B
0x140063b55  mov     eax, 2
0x140063b5a  jmp     short loc_140063B2B
```
