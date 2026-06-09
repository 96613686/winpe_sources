# __crtCompareStringA

- ea: `0x18007eb78`
- end: `0x18007ef05`
- name: `__crtCompareStringA`
- size: `909`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180081580`

## callees

- `0x18007eb78`
- `0x18008fab3`
- `0x18008fb5b`
- `0x18008fe00`
- `0x180096100`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18007ec30`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18007ec30`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18007eea5`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18007eea5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007eccc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007ed72`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007eda2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007ee4d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007eccc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007ed72`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007eda2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007ee4d`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x18007ebbf`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x18007ebe4`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x18007ebbf`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x18007ebe4`

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
  BYTE *LeadByte; // rax
  BYTE *v12; // rax
  int v13; // eax
  int cchWideChar; // r13d
  size_t v15; // rcx
  __int64 v16; // rax
  void *v17; // rsp
  WCHAR *lpWideCharStr; // rbx
  WCHAR *v19; // rax
  int v20; // eax
  int v21; // r15d
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  __int64 v24; // rax
  void *v25; // rsp
  WCHAR *p_lpMultiByteStr; // rdi
  WCHAR *v27; // rax
  WCHAR *v28; // r14
  WCHAR *v29; // rcx
  bool v30; // zf
  unsigned int v31; // edi
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
  if ( !v7 || !v9 )
  {
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
        LeadByte = CPInfo.LeadByte;
        if ( CPInfo.LeadByte[0] )
        {
          while ( LeadByte[1] )
          {
            if ( (unsigned int)*a3 >= *LeadByte && (unsigned int)*a3 <= LeadByte[1] )
              return 2;
            LeadByte += 2;
            if ( !*LeadByte )
              return 3;
          }
        }
      }
      return 3;
    }
    if ( v9 > 0 )
    {
      if ( CPInfo.MaxCharSize >= 2 )
      {
        v12 = CPInfo.LeadByte;
        if ( CPInfo.LeadByte[0] )
        {
          while ( v12[1] )
          {
            if ( (unsigned __int8)*String >= *v12 && (unsigned __int8)*String <= v12[1] )
              return 2;
            v12 += 2;
            if ( !*v12 )
              return 1;
          }
        }
      }
      return 1;
    }
  }
  v13 = MultiByteToWideChar(CodePage, 9u, a3, v7, 0, 0);
  cchWideChar = v13;
  if ( !v13 )
    return 0;
  v15 = (2LL * v13 + 16) & -(__int64)(2LL * v13 < (unsigned __int64)(2LL * v13 + 16));
  if ( !v15 )
    return 0;
  if ( v15 > 0x400 )
  {
    v19 = (WCHAR *)malloc_base(v15);
    lpWideCharStr = v19;
    if ( !v19 )
      goto LABEL_39;
    *(_DWORD *)v19 = 56797;
  }
  else
  {
    v16 = v15 + 15;
    if ( v15 + 15 < v15 )
      v16 = 0xFFFFFFFFFFFFFF0LL;
    v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
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
  v20 = MultiByteToWideChar(CodePage, 9u, String, v9, 0, 0);
  v21 = v20;
  if ( !v20 )
    goto LABEL_61;
  v22 = 2LL * v20 + 16;
  v23 = v22 & -(__int64)(2LL * v20 < v22);
  if ( !v23 )
    goto LABEL_61;
  if ( v23 > 0x400 )
  {
    v27 = (WCHAR *)malloc_base(v22 & -(__int64)(2LL * v20 < v22));
    p_lpMultiByteStr = v27;
    if ( !v27 )
      goto LABEL_51;
    *(_DWORD *)v27 = 56797;
  }
  else
  {
    v24 = v23 + 15;
    if ( v23 + 15 < v23 )
      v24 = 0xFFFFFFFFFFFFFF0LL;
    v25 = alloca(v24 & 0xFFFFFFFFFFFFFFF0uLL);
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
    v29 = lpWideCharStr - 8;
    v30 = *((_DWORD *)lpWideCharStr - 4) == 56797;
LABEL_62:
    if ( v30 )
      free_base(v29);
    return 0;
  }
  v28 = p_lpMultiByteStr - 8;
  if ( !MultiByteToWideChar(CodePage, 1u, lpMultiByteStr, v9, p_lpMultiByteStr, v21) )
  {
    if ( *(_DWORD *)v28 == 56797 )
      free_base(v28);
    v29 = lpWideCharStr - 8;
    v30 = *((_DWORD *)lpWideCharStr - 4) == 56797;
    goto LABEL_62;
  }
  v31 = CompareStringEx(lpLocaleName, 0x1000u, lpWideCharStr, cchWideChar, p_lpMultiByteStr, v21, 0, 0, 0);
  if ( *(_DWORD *)v28 == 56797 )
    free_base(v28);
  if ( *((_DWORD *)lpWideCharStr - 4) == 56797 )
    free_base(lpWideCharStr - 8);
  return v31;
}

```

## disassembly

```asm
0x18007eb78  push    rbp
0x18007eb7a  push    rbx
0x18007eb7b  push    rsi
0x18007eb7c  push    rdi
0x18007eb7d  push    r13
0x18007eb7f  push    r14
0x18007eb81  push    r15
0x18007eb83  sub     rsp, 80h
0x18007eb8a  lea     rbp, [rsp+50h]
0x18007eb8f  mov     rax, cs:__security_cookie
0x18007eb96  xor     rax, rbp
0x18007eb99  mov     [rbp+60h+var_38], rax
0x18007eb9d  mov     r15, [rbp+60h+String]
0x18007eba4  xor     ebx, ebx
0x18007eba6  movsxd  rdi, r9d
0x18007eba9  mov     r14, r8
0x18007ebac  mov     [rbp+60h+lpLocaleName], rcx
0x18007ebb0  mov     [rbp+60h+lpMultiByteStr], r15
0x18007ebb4  test    r9d, r9d
0x18007ebb7  jle     short loc_18007EBCA
0x18007ebb9  mov     rdx, rdi; Count
0x18007ebbc  mov     rcx, r8; String
0x18007ebbf  call    cs:__imp___strncnt
0x18007ebc5  mov     rdi, rax
0x18007ebc8  jmp     short loc_18007EBD3
0x18007ebca  cmp     edi, 0FFFFFFFFh
0x18007ebcd  jl      loc_18007EEE1
0x18007ebd3  movsxd  rsi, [rbp+60h+arg_28]
0x18007ebda  test    esi, esi
0x18007ebdc  jle     short loc_18007EBEF
0x18007ebde  mov     rdx, rsi; Count
0x18007ebe1  mov     rcx, r15; String
0x18007ebe4  call    cs:__imp___strncnt
0x18007ebea  mov     rsi, rax
0x18007ebed  jmp     short loc_18007EBF8
0x18007ebef  cmp     esi, 0FFFFFFFFh
0x18007ebf2  jl      loc_18007EEE1
0x18007ebf8  test    edi, edi
0x18007ebfa  jz      short loc_18007EC04
0x18007ebfc  test    esi, esi
0x18007ebfe  jnz     loc_18007ECB2
0x18007ec04  cmp     edi, esi
0x18007ec06  jz      loc_18007EEFE
0x18007ec0c  cmp     esi, 1
0x18007ec0f  jg      loc_18007ECA8
0x18007ec15  cmp     edi, 1
0x18007ec18  jg      short loc_18007EC6E
0x18007ec1a  mov     ecx, [rbp+60h+CodePage]; CodePage
0x18007ec20  lea     rdx, [rbp+60h+CPInfo]; lpCPInfo
0x18007ec24  xorps   xmm0, xmm0
0x18007ec27  xor     eax, eax
0x18007ec29  movups  xmmword ptr [rbp+60h+CPInfo.MaxCharSize], xmm0
0x18007ec2d  mov     dword ptr [rbp+60h+CPInfo.LeadByte+0Ah], eax
0x18007ec30  call    cs:__imp_GetCPInfo
0x18007ec36  test    eax, eax
0x18007ec38  jz      loc_18007EEE1
0x18007ec3e  test    edi, edi
0x18007ec40  jle     short loc_18007EC78
0x18007ec42  cmp     [rbp+60h+CPInfo.MaxCharSize], 2
0x18007ec46  jb      short loc_18007EC6E
0x18007ec48  lea     rax, [rbp+60h+CPInfo.LeadByte]
0x18007ec4c  cmp     [rbp+60h+CPInfo.LeadByte], bl
0x18007ec4f  jz      short loc_18007EC6E
0x18007ec51  cmp     [rax+1], bl
0x18007ec54  jz      short loc_18007EC6E
0x18007ec56  mov     cl, [r14]
0x18007ec59  cmp     cl, [rax]
0x18007ec5b  jb      short loc_18007EC66
0x18007ec5d  cmp     cl, [rax+1]
0x18007ec60  jbe     loc_18007EEFE
0x18007ec66  add     rax, 2
0x18007ec6a  cmp     [rax], bl
0x18007ec6c  jnz     short loc_18007EC51
0x18007ec6e  mov     eax, 3
0x18007ec73  jmp     loc_18007EEE3
0x18007ec78  test    esi, esi
0x18007ec7a  jle     short loc_18007ECB2
0x18007ec7c  cmp     [rbp+60h+CPInfo.MaxCharSize], 2
0x18007ec80  jb      short loc_18007ECA8
0x18007ec82  lea     rax, [rbp+60h+CPInfo.LeadByte]
0x18007ec86  cmp     [rbp+60h+CPInfo.LeadByte], bl
0x18007ec89  jz      short loc_18007ECA8
0x18007ec8b  cmp     [rax+1], bl
0x18007ec8e  jz      short loc_18007ECA8
0x18007ec90  mov     cl, [r15]
0x18007ec93  cmp     cl, [rax]
0x18007ec95  jb      short loc_18007ECA0
0x18007ec97  cmp     cl, [rax+1]
0x18007ec9a  jbe     loc_18007EEFE
0x18007eca0  add     rax, 2
0x18007eca4  cmp     [rax], bl
0x18007eca6  jnz     short loc_18007EC8B
0x18007eca8  mov     eax, 1
0x18007ecad  jmp     loc_18007EEE3
0x18007ecb2  mov     ecx, [rbp+60h+CodePage]; CodePage
0x18007ecb8  mov     r9d, edi; cbMultiByte
0x18007ecbb  mov     [rsp+0B0h+cchWideChar], ebx; cchWideChar
0x18007ecbf  mov     r8, r14; lpMultiByteStr
0x18007ecc2  mov     edx, 9; dwFlags
0x18007ecc7  mov     [rsp+0B0h+lpWideCharStr], rbx; lpWideCharStr
0x18007eccc  call    cs:__imp_MultiByteToWideChar
0x18007ecd2  movsxd  r13, eax
0x18007ecd5  test    eax, eax
0x18007ecd7  jz      loc_18007EEE1
0x18007ecdd  mov     rcx, r13
0x18007ece0  add     rcx, rcx
0x18007ece3  lea     rdx, [rcx+10h]
0x18007ece7  cmp     rcx, rdx
0x18007ecea  sbb     rcx, rcx
0x18007eced  and     rcx, rdx; Size
0x18007ecf0  jz      loc_18007EEE1
0x18007ecf6  mov     rdx, 0FFFFFFFFFFFFFF0h
0x18007ed00  cmp     rcx, 400h
0x18007ed07  ja      short loc_18007ED37
0x18007ed09  lea     rax, [rcx+0Fh]
0x18007ed0d  cmp     rax, rcx
0x18007ed10  ja      short loc_18007ED15
0x18007ed12  mov     rax, rdx
0x18007ed15  and     rax, 0FFFFFFFFFFFFFFF0h
0x18007ed19  call    _alloca_probe
0x18007ed1e  sub     rsp, rax
0x18007ed21  lea     rbx, [rsp+0B0h+lpMultiByteStr]
0x18007ed26  test    rbx, rbx
0x18007ed29  jz      loc_18007EEE1
0x18007ed2f  mov     dword ptr [rbx], 0CCCCh
0x18007ed35  jmp     short loc_18007ED4A
0x18007ed37  call    _malloc_base
0x18007ed3c  mov     rbx, rax
0x18007ed3f  test    rax, rax
0x18007ed42  jz      short loc_18007ED4E
0x18007ed44  mov     dword ptr [rax], 0DDDDh
0x18007ed4a  add     rbx, 10h
0x18007ed4e  test    rbx, rbx
0x18007ed51  jz      loc_18007EEE1
0x18007ed57  mov     ecx, [rbp+60h+CodePage]; CodePage
0x18007ed5d  mov     r9d, edi; cbMultiByte
0x18007ed60  mov     [rsp+0B0h+cchWideChar], r13d; cchWideChar
0x18007ed65  mov     r8, r14; lpMultiByteStr
0x18007ed68  mov     edx, 1; dwFlags
0x18007ed6d  mov     [rsp+0B0h+lpWideCharStr], rbx; lpWideCharStr
0x18007ed72  call    cs:__imp_MultiByteToWideChar
0x18007ed78  test    eax, eax
0x18007ed7a  jz      loc_18007EED0
0x18007ed80  mov     ecx, [rbp+60h+CodePage]; CodePage
0x18007ed86  mov     r9d, esi; cbMultiByte
0x18007ed89  mov     [rsp+0B0h+cchWideChar], 0; cchWideChar
0x18007ed91  mov     r8, r15; lpMultiByteStr
0x18007ed94  mov     edx, 9; dwFlags
0x18007ed99  mov     [rsp+0B0h+lpWideCharStr], 0; lpWideCharStr
0x18007eda2  call    cs:__imp_MultiByteToWideChar
0x18007eda8  movsxd  r15, eax
0x18007edab  test    eax, eax
0x18007edad  jz      loc_18007EED0
0x18007edb3  mov     rax, r15
0x18007edb6  add     rax, rax
0x18007edb9  lea     rcx, [rax+10h]
0x18007edbd  cmp     rax, rcx
0x18007edc0  sbb     rdx, rdx
0x18007edc3  and     rdx, rcx
0x18007edc6  jz      loc_18007EED0
0x18007edcc  cmp     rdx, 400h
0x18007edd3  ja      short loc_18007EE0A
0x18007edd5  lea     rax, [rdx+0Fh]
0x18007edd9  cmp     rax, rdx
0x18007eddc  ja      short loc_18007EDE8
0x18007edde  mov     rax, 0FFFFFFFFFFFFFF0h
0x18007ede8  and     rax, 0FFFFFFFFFFFFFFF0h
0x18007edec  call    _alloca_probe
0x18007edf1  sub     rsp, rax
0x18007edf4  lea     rdi, [rsp+0B0h+lpMultiByteStr]
0x18007edf9  test    rdi, rdi
0x18007edfc  jz      loc_18007EED0
0x18007ee02  mov     dword ptr [rdi], 0CCCCh
0x18007ee08  jmp     short loc_18007EE20
0x18007ee0a  mov     rcx, rdx; Size
0x18007ee0d  call    _malloc_base
0x18007ee12  mov     rdi, rax
0x18007ee15  test    rax, rax
0x18007ee18  jz      short loc_18007EE24
0x18007ee1a  mov     dword ptr [rax], 0DDDDh
0x18007ee20  add     rdi, 10h
0x18007ee24  test    rdi, rdi
0x18007ee27  jz      loc_18007EED0
0x18007ee2d  mov     r8, [rbp+60h+lpMultiByteStr]; lpMultiByteStr
0x18007ee31  lea     r14, [rdi-10h]
0x18007ee35  mov     ecx, [rbp+60h+CodePage]; CodePage
0x18007ee3b  mov     r9d, esi; cbMultiByte
0x18007ee3e  mov     [rsp+0B0h+cchWideChar], r15d; cchWideChar
0x18007ee43  mov     edx, 1; dwFlags
0x18007ee48  mov     [rsp+0B0h+lpWideCharStr], rdi; lpWideCharStr
0x18007ee4d  call    cs:__imp_MultiByteToWideChar
0x18007ee53  test    eax, eax
0x18007ee55  jnz     short loc_18007EE71
0x18007ee57  mov     edi, 0DDDDh
0x18007ee5c  cmp     [r14], edi
0x18007ee5f  jnz     short loc_18007EE69
0x18007ee61  mov     rcx, r14; Block
0x18007ee64  call    _free_base
0x18007ee69  lea     rcx, [rbx-10h]
0x18007ee6d  cmp     [rcx], edi
0x18007ee6f  jmp     short loc_18007EEDA
0x18007ee71  mov     rcx, [rbp+60h+lpLocaleName]; lpLocaleName
0x18007ee75  mov     r9d, r13d; cchCount1
0x18007ee78  mov     [rsp+0B0h+lParam], 0; lParam
0x18007ee81  mov     r8, rbx; lpString1
0x18007ee84  mov     [rsp+0B0h+lpReserved], 0; lpReserved
0x18007ee8d  mov     edx, 1000h; dwCmpFlags
0x18007ee92  mov     [rsp+0B0h+lpVersionInformation], 0; lpVersionInformation
0x18007ee9b  mov     [rsp+0B0h+cchWideChar], r15d; cchCount2
0x18007eea0  mov     [rsp+0B0h+lpWideCharStr], rdi; lpString2
0x18007eea5  call    cs:__imp_CompareStringEx
0x18007eeab  mov     esi, 0DDDDh
0x18007eeb0  mov     edi, eax
0x18007eeb2  cmp     [r14], esi
0x18007eeb5  jnz     short loc_18007EEBF
0x18007eeb7  mov     rcx, r14; Block
0x18007eeba  call    _free_base
0x18007eebf  lea     rcx, [rbx-10h]; Block
0x18007eec3  cmp     [rcx], esi
0x18007eec5  jnz     short loc_18007EECC
0x18007eec7  call    _free_base
0x18007eecc  mov     eax, edi
0x18007eece  jmp     short loc_18007EEE3
0x18007eed0  lea     rcx, [rbx-10h]; Block
0x18007eed4  cmp     dword ptr [rcx], 0DDDDh
0x18007eeda  jnz     short loc_18007EEE1
0x18007eedc  call    _free_base
0x18007eee1  xor     eax, eax
0x18007eee3  mov     rcx, [rbp+60h+var_38]
0x18007eee7  xor     rcx, rbp; StackCookie
0x18007eeea  call    __security_check_cookie
0x18007eeef  lea     rsp, [rbp+30h]
0x18007eef3  pop     r15
0x18007eef5  pop     r14
0x18007eef7  pop     r13
0x18007eef9  pop     rdi
0x18007eefa  pop     rsi
0x18007eefb  pop     rbx
0x18007eefc  pop     rbp
0x18007eefd  retn
0x18007eefe  mov     eax, 2
0x18007ef03  jmp     short loc_18007EEE3
```
