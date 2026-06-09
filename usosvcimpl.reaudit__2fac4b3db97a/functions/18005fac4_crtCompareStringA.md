# __crtCompareStringA

- ea: `0x18005fac4`
- end: `0x18005fe51`
- name: `__crtCompareStringA`
- size: `909`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004bcb0`

## callees

- `0x18005fac4`
- `0x1800dd5a6`
- `0x1800dd666`
- `0x1800dd930`
- `0x1800e45c0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18005fb7c`
- `api-ms-win-core-localization-l1-2-0!GetCPInfo` at `0x18005fb7c`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18005fdf1`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18005fdf1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005fc18`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005fcbe`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005fcee`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005fd99`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005fc18`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005fcbe`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005fcee`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005fd99`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x18005fb0b`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x18005fb30`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x18005fb0b`
- `api-ms-win-crt-string-l1-1-0!__strncnt` at `0x18005fb30`

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
0x18005fac4  push    rbp
0x18005fac6  push    rbx
0x18005fac7  push    rsi
0x18005fac8  push    rdi
0x18005fac9  push    r13
0x18005facb  push    r14
0x18005facd  push    r15
0x18005facf  sub     rsp, 80h
0x18005fad6  lea     rbp, [rsp+50h]
0x18005fadb  mov     rax, cs:__security_cookie
0x18005fae2  xor     rax, rbp
0x18005fae5  mov     [rbp+60h+var_38], rax
0x18005fae9  mov     r15, [rbp+60h+String]
0x18005faf0  xor     ebx, ebx
0x18005faf2  movsxd  rdi, r9d
0x18005faf5  mov     r14, r8
0x18005faf8  mov     [rbp+60h+lpLocaleName], rcx
0x18005fafc  mov     [rbp+60h+lpMultiByteStr], r15
0x18005fb00  test    r9d, r9d
0x18005fb03  jle     short loc_18005FB16
0x18005fb05  mov     rdx, rdi; Count
0x18005fb08  mov     rcx, r8; String
0x18005fb0b  call    cs:__imp___strncnt
0x18005fb11  mov     rdi, rax
0x18005fb14  jmp     short loc_18005FB1F
0x18005fb16  cmp     edi, 0FFFFFFFFh
0x18005fb19  jl      loc_18005FE2D
0x18005fb1f  movsxd  rsi, [rbp+60h+arg_28]
0x18005fb26  test    esi, esi
0x18005fb28  jle     short loc_18005FB3B
0x18005fb2a  mov     rdx, rsi; Count
0x18005fb2d  mov     rcx, r15; String
0x18005fb30  call    cs:__imp___strncnt
0x18005fb36  mov     rsi, rax
0x18005fb39  jmp     short loc_18005FB44
0x18005fb3b  cmp     esi, 0FFFFFFFFh
0x18005fb3e  jl      loc_18005FE2D
0x18005fb44  test    edi, edi
0x18005fb46  jz      short loc_18005FB50
0x18005fb48  test    esi, esi
0x18005fb4a  jnz     loc_18005FBFE
0x18005fb50  cmp     edi, esi
0x18005fb52  jz      loc_18005FE4A
0x18005fb58  cmp     esi, 1
0x18005fb5b  jg      loc_18005FBF4
0x18005fb61  cmp     edi, 1
0x18005fb64  jg      short loc_18005FBBA
0x18005fb66  mov     ecx, [rbp+60h+CodePage]; CodePage
0x18005fb6c  lea     rdx, [rbp+60h+CPInfo]; lpCPInfo
0x18005fb70  xorps   xmm0, xmm0
0x18005fb73  xor     eax, eax
0x18005fb75  movups  xmmword ptr [rbp+60h+CPInfo.MaxCharSize], xmm0
0x18005fb79  mov     dword ptr [rbp+60h+CPInfo.LeadByte+0Ah], eax
0x18005fb7c  call    cs:__imp_GetCPInfo
0x18005fb82  test    eax, eax
0x18005fb84  jz      loc_18005FE2D
0x18005fb8a  test    edi, edi
0x18005fb8c  jle     short loc_18005FBC4
0x18005fb8e  cmp     [rbp+60h+CPInfo.MaxCharSize], 2
0x18005fb92  jb      short loc_18005FBBA
0x18005fb94  lea     rax, [rbp+60h+CPInfo.LeadByte]
0x18005fb98  cmp     [rbp+60h+CPInfo.LeadByte], bl
0x18005fb9b  jz      short loc_18005FBBA
0x18005fb9d  cmp     [rax+1], bl
0x18005fba0  jz      short loc_18005FBBA
0x18005fba2  mov     cl, [r14]
0x18005fba5  cmp     cl, [rax]
0x18005fba7  jb      short loc_18005FBB2
0x18005fba9  cmp     cl, [rax+1]
0x18005fbac  jbe     loc_18005FE4A
0x18005fbb2  add     rax, 2
0x18005fbb6  cmp     [rax], bl
0x18005fbb8  jnz     short loc_18005FB9D
0x18005fbba  mov     eax, 3
0x18005fbbf  jmp     loc_18005FE2F
0x18005fbc4  test    esi, esi
0x18005fbc6  jle     short loc_18005FBFE
0x18005fbc8  cmp     [rbp+60h+CPInfo.MaxCharSize], 2
0x18005fbcc  jb      short loc_18005FBF4
0x18005fbce  lea     rax, [rbp+60h+CPInfo.LeadByte]
0x18005fbd2  cmp     [rbp+60h+CPInfo.LeadByte], bl
0x18005fbd5  jz      short loc_18005FBF4
0x18005fbd7  cmp     [rax+1], bl
0x18005fbda  jz      short loc_18005FBF4
0x18005fbdc  mov     cl, [r15]
0x18005fbdf  cmp     cl, [rax]
0x18005fbe1  jb      short loc_18005FBEC
0x18005fbe3  cmp     cl, [rax+1]
0x18005fbe6  jbe     loc_18005FE4A
0x18005fbec  add     rax, 2
0x18005fbf0  cmp     [rax], bl
0x18005fbf2  jnz     short loc_18005FBD7
0x18005fbf4  mov     eax, 1
0x18005fbf9  jmp     loc_18005FE2F
0x18005fbfe  mov     ecx, [rbp+60h+CodePage]; CodePage
0x18005fc04  mov     r9d, edi; cbMultiByte
0x18005fc07  mov     [rsp+0B0h+cchWideChar], ebx; cchWideChar
0x18005fc0b  mov     r8, r14; lpMultiByteStr
0x18005fc0e  mov     edx, 9; dwFlags
0x18005fc13  mov     [rsp+0B0h+lpWideCharStr], rbx; lpWideCharStr
0x18005fc18  call    cs:__imp_MultiByteToWideChar
0x18005fc1e  movsxd  r13, eax
0x18005fc21  test    eax, eax
0x18005fc23  jz      loc_18005FE2D
0x18005fc29  mov     rcx, r13
0x18005fc2c  add     rcx, rcx
0x18005fc2f  lea     rdx, [rcx+10h]
0x18005fc33  cmp     rcx, rdx
0x18005fc36  sbb     rcx, rcx
0x18005fc39  and     rcx, rdx; Size
0x18005fc3c  jz      loc_18005FE2D
0x18005fc42  mov     rdx, 0FFFFFFFFFFFFFF0h
0x18005fc4c  cmp     rcx, 400h
0x18005fc53  ja      short loc_18005FC83
0x18005fc55  lea     rax, [rcx+0Fh]
0x18005fc59  cmp     rax, rcx
0x18005fc5c  ja      short loc_18005FC61
0x18005fc5e  mov     rax, rdx
0x18005fc61  and     rax, 0FFFFFFFFFFFFFFF0h
0x18005fc65  call    _alloca_probe
0x18005fc6a  sub     rsp, rax
0x18005fc6d  lea     rbx, [rsp+0B0h+lpMultiByteStr]
0x18005fc72  test    rbx, rbx
0x18005fc75  jz      loc_18005FE2D
0x18005fc7b  mov     dword ptr [rbx], 0CCCCh
0x18005fc81  jmp     short loc_18005FC96
0x18005fc83  call    _malloc_base
0x18005fc88  mov     rbx, rax
0x18005fc8b  test    rax, rax
0x18005fc8e  jz      short loc_18005FC9A
0x18005fc90  mov     dword ptr [rax], 0DDDDh
0x18005fc96  add     rbx, 10h
0x18005fc9a  test    rbx, rbx
0x18005fc9d  jz      loc_18005FE2D
0x18005fca3  mov     ecx, [rbp+60h+CodePage]; CodePage
0x18005fca9  mov     r9d, edi; cbMultiByte
0x18005fcac  mov     [rsp+0B0h+cchWideChar], r13d; cchWideChar
0x18005fcb1  mov     r8, r14; lpMultiByteStr
0x18005fcb4  mov     edx, 1; dwFlags
0x18005fcb9  mov     [rsp+0B0h+lpWideCharStr], rbx; lpWideCharStr
0x18005fcbe  call    cs:__imp_MultiByteToWideChar
0x18005fcc4  test    eax, eax
0x18005fcc6  jz      loc_18005FE1C
0x18005fccc  mov     ecx, [rbp+60h+CodePage]; CodePage
0x18005fcd2  mov     r9d, esi; cbMultiByte
0x18005fcd5  mov     [rsp+0B0h+cchWideChar], 0; cchWideChar
0x18005fcdd  mov     r8, r15; lpMultiByteStr
0x18005fce0  mov     edx, 9; dwFlags
0x18005fce5  mov     [rsp+0B0h+lpWideCharStr], 0; lpWideCharStr
0x18005fcee  call    cs:__imp_MultiByteToWideChar
0x18005fcf4  movsxd  r15, eax
0x18005fcf7  test    eax, eax
0x18005fcf9  jz      loc_18005FE1C
0x18005fcff  mov     rax, r15
0x18005fd02  add     rax, rax
0x18005fd05  lea     rcx, [rax+10h]
0x18005fd09  cmp     rax, rcx
0x18005fd0c  sbb     rdx, rdx
0x18005fd0f  and     rdx, rcx
0x18005fd12  jz      loc_18005FE1C
0x18005fd18  cmp     rdx, 400h
0x18005fd1f  ja      short loc_18005FD56
0x18005fd21  lea     rax, [rdx+0Fh]
0x18005fd25  cmp     rax, rdx
0x18005fd28  ja      short loc_18005FD34
0x18005fd2a  mov     rax, 0FFFFFFFFFFFFFF0h
0x18005fd34  and     rax, 0FFFFFFFFFFFFFFF0h
0x18005fd38  call    _alloca_probe
0x18005fd3d  sub     rsp, rax
0x18005fd40  lea     rdi, [rsp+0B0h+lpMultiByteStr]
0x18005fd45  test    rdi, rdi
0x18005fd48  jz      loc_18005FE1C
0x18005fd4e  mov     dword ptr [rdi], 0CCCCh
0x18005fd54  jmp     short loc_18005FD6C
0x18005fd56  mov     rcx, rdx; Size
0x18005fd59  call    _malloc_base
0x18005fd5e  mov     rdi, rax
0x18005fd61  test    rax, rax
0x18005fd64  jz      short loc_18005FD70
0x18005fd66  mov     dword ptr [rax], 0DDDDh
0x18005fd6c  add     rdi, 10h
0x18005fd70  test    rdi, rdi
0x18005fd73  jz      loc_18005FE1C
0x18005fd79  mov     r8, [rbp+60h+lpMultiByteStr]; lpMultiByteStr
0x18005fd7d  lea     r14, [rdi-10h]
0x18005fd81  mov     ecx, [rbp+60h+CodePage]; CodePage
0x18005fd87  mov     r9d, esi; cbMultiByte
0x18005fd8a  mov     [rsp+0B0h+cchWideChar], r15d; cchWideChar
0x18005fd8f  mov     edx, 1; dwFlags
0x18005fd94  mov     [rsp+0B0h+lpWideCharStr], rdi; lpWideCharStr
0x18005fd99  call    cs:__imp_MultiByteToWideChar
0x18005fd9f  test    eax, eax
0x18005fda1  jnz     short loc_18005FDBD
0x18005fda3  mov     edi, 0DDDDh
0x18005fda8  cmp     [r14], edi
0x18005fdab  jnz     short loc_18005FDB5
0x18005fdad  mov     rcx, r14; Block
0x18005fdb0  call    _free_base
0x18005fdb5  lea     rcx, [rbx-10h]
0x18005fdb9  cmp     [rcx], edi
0x18005fdbb  jmp     short loc_18005FE26
0x18005fdbd  mov     rcx, [rbp+60h+lpLocaleName]; lpLocaleName
0x18005fdc1  mov     r9d, r13d; cchCount1
0x18005fdc4  mov     [rsp+0B0h+lParam], 0; lParam
0x18005fdcd  mov     r8, rbx; lpString1
0x18005fdd0  mov     [rsp+0B0h+lpReserved], 0; lpReserved
0x18005fdd9  mov     edx, 1000h; dwCmpFlags
0x18005fdde  mov     [rsp+0B0h+lpVersionInformation], 0; lpVersionInformation
0x18005fde7  mov     [rsp+0B0h+cchWideChar], r15d; cchCount2
0x18005fdec  mov     [rsp+0B0h+lpWideCharStr], rdi; lpString2
0x18005fdf1  call    cs:__imp_CompareStringEx
0x18005fdf7  mov     esi, 0DDDDh
0x18005fdfc  mov     edi, eax
0x18005fdfe  cmp     [r14], esi
0x18005fe01  jnz     short loc_18005FE0B
0x18005fe03  mov     rcx, r14; Block
0x18005fe06  call    _free_base
0x18005fe0b  lea     rcx, [rbx-10h]; Block
0x18005fe0f  cmp     [rcx], esi
0x18005fe11  jnz     short loc_18005FE18
0x18005fe13  call    _free_base
0x18005fe18  mov     eax, edi
0x18005fe1a  jmp     short loc_18005FE2F
0x18005fe1c  lea     rcx, [rbx-10h]; Block
0x18005fe20  cmp     dword ptr [rcx], 0DDDDh
0x18005fe26  jnz     short loc_18005FE2D
0x18005fe28  call    _free_base
0x18005fe2d  xor     eax, eax
0x18005fe2f  mov     rcx, [rbp+60h+var_38]
0x18005fe33  xor     rcx, rbp; StackCookie
0x18005fe36  call    __security_check_cookie
0x18005fe3b  lea     rsp, [rbp+30h]
0x18005fe3f  pop     r15
0x18005fe41  pop     r14
0x18005fe43  pop     r13
0x18005fe45  pop     rdi
0x18005fe46  pop     rsi
0x18005fe47  pop     rbx
0x18005fe48  pop     rbp
0x18005fe49  retn
0x18005fe4a  mov     eax, 2
0x18005fe4f  jmp     short loc_18005FE2F
```
