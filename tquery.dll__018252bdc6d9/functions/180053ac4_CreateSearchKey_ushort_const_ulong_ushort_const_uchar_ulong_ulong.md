# CreateSearchKey(ushort const *,ulong,ushort const *,uchar *,ulong,ulong *)

- ea: `0x180053ac4`
- end: `0x180054171`
- name: `?CreateSearchKey@@YAJPEBGK0PEAEKPEAK@Z`
- size: `1709`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpLocaleName@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned __int8 *@<r9>, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180052b10`

## callees

- `0x180053ac4`
- `0x180054178`
- `0x180055618`
- `0x18008a284`
- `0x180188d74`
- `0x180188d90`
- `0x180189cce`
- `0x18018a123`
- `0x18018e778`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053fbf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053fbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054022`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053f90`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180053bc5`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180053f82`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18005412c`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180053bc5`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180053f82`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18005412c`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180053b78`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180053b78`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180053ebd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180053ebd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180053b21`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180053b3d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180053b21`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x180053b3d`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x180053ee6`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x180053ee6`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x180053e8a`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x180053e8a`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x180053fff`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x180053fff`

## pseudocode

```c
__int64 __fastcall CreateSearchKey(
        LPCWSTR lpLocaleName,
        int a2,
        unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned int *v6; // rsi
  HRESULT Services; // ebx
  DWORD v11; // r12d
  BOOL valid; // eax
  const WCHAR *v13; // r14
  WCHAR *lpDestStr; // rdx
  int v15; // r15d
  signed int Error; // ebx
  unsigned int v17; // r8d
  LPWSTR v18; // r10
  unsigned int v19; // edi
  unsigned int v20; // r8d
  int v21; // r11d
  char v22; // cl
  int v23; // ecx
  int v24; // eax
  __int64 v25; // r14
  unsigned int i; // ecx
  char v27; // r11
  LPWSTR v28; // r13
  unsigned int v29; // r12d
  unsigned int v30; // r10d
  __int64 v31; // r9
  __int64 v32; // rsi
  char v33; // cl
  char v34; // di
  int v35; // r11d
  unsigned int v36; // r12d
  unsigned __int8 *v37; // rdx
  unsigned __int8 v38; // cl
  void *v39; // rcx
  __int64 v41; // r8
  HRESULT v42; // r14d
  bool v43; // bl
  unsigned int v44; // esi
  unsigned int v45; // eax
  signed int LastError; // eax
  int v47; // r11d
  __int64 v48; // rcx
  unsigned int v49; // edx
  unsigned __int8 *v50; // rsi
  unsigned __int8 v51; // r9
  char v52; // al
  __int64 v53; // rax
  __int64 v54; // rbx
  WCHAR *v55; // rax
  LPWSTR v56; // rdx
  char SearchKeyFlags; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v58; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 *v59; // [rsp+60h] [rbp-A0h]
  unsigned int v60; // [rsp+6Ch] [rbp-94h]
  __int64 v61; // [rsp+70h] [rbp-90h]
  unsigned int *v62; // [rsp+78h] [rbp-88h]
  LPVOID pv; // [rsp+80h] [rbp-80h]
  __int128 v64; // [rsp+90h] [rbp-70h] BYREF
  struct _MAPPING_ENUM_OPTIONS pbag; // [rsp+A0h] [rbp-60h] BYREF
  int cchDest[2]; // [rsp+F0h] [rbp-10h]
  LPWSTR v67; // [rsp+F8h] [rbp-8h]
  _BYTE v68[576]; // [rsp+100h] [rbp+0h] BYREF

  v6 = a6;
  v59 = a4;
  Services = 0;
  v62 = a6;
  pv = 0;
  v58 = 0;
  if ( !StrCmpIW(lpLocaleName, L"ko") || !StrCmpIW(lpLocaleName, L"ko-KR") )
  {
    v64 = xmmword_1802DD280;
    if ( byte_18036932C )
      goto LABEL_63;
    AcquireSRWLockExclusive(&s_srwElsServiceLock);
    if ( !byte_18036932C )
    {
      memset_0(&pbag, 0, sizeof(pbag));
      pbag.Size = 80;
      pbag.pGuid = (GUID *)&v64;
      Services = MappingGetServices(&pbag, &g_scriptAutoDetection, &pdwServicesCount);
      if ( Services >= 0 )
      {
        if ( pdwServicesCount )
          byte_18036932C = 1;
        else
          Services = -2147467259;
      }
    }
    ReleaseSRWLockExclusive(&s_srwElsServiceLock);
    if ( Services >= 0 )
    {
LABEL_63:
      memset_0(&pbag, 0, 0x40u);
      v41 = -1;
      pbag.Size = 64;
      do
        ++v41;
      while ( a3[v41] );
      v42 = MappingRecognizeText(g_scriptAutoDetection, a3, v41, 0, 0, (PMAPPING_PROPERTY_BAG)&pbag);
      if ( v42 >= 0 )
      {
        v43 = 0;
        v44 = 0;
        if ( LODWORD(pbag.pszInputLanguage) )
        {
          while ( !v43 )
          {
            v43 = StrStrIW(L"Hang", *(PCWSTR *)&pbag.pszCategory[36 * v44++ + 12]) != 0;
            if ( v44 >= LODWORD(pbag.pszInputLanguage) )
            {
              if ( v43 )
                break;
              goto LABEL_70;
            }
          }
        }
        else
        {
LABEL_70:
          v42 = 1;
        }
        MappingFreePropertyBag((PMAPPING_PROPERTY_BAG)&pbag);
        v6 = v62;
      }
      if ( !v42 )
      {
        Error = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                  (PMAPPING_SERVICE_INFO *)g_koreanDecomposition,
                  a3,
                  &v58);
        if ( Error < 0 )
        {
          v39 = v58;
          goto LABEL_56;
        }
        pv = v58;
        a3 = v58;
      }
    }
  }
  SearchKeyFlags = GetSearchKeyFlags(lpLocaleName);
  *(_QWORD *)cchDest = 576;
  v67 = 0;
  v11 = a2 | 0x400;
  *v6 = 0;
  valid = IsValidLocaleName(lpLocaleName);
  v13 = &psz;
  lpDestStr = (WCHAR *)v68;
  if ( valid )
    v13 = lpLocaleName;
  v15 = 0;
  if ( v67 )
    lpDestStr = v67;
  if ( LCMapStringEx(v13, v11, a3, -1, lpDestStr, cchDest[0], 0, 0, 0) )
  {
LABEL_8:
    Error = 0;
    v56 = v67;
    v18 = (LPWSTR)v68;
    v19 = cchDest[0];
    v61 = *(_QWORD *)cchDest;
    v20 = 0;
    if ( v67 )
      v18 = v67;
    *(_QWORD *)&v64 = v67;
    v21 = 0;
    while ( v20 < cchDest[0] )
    {
      v22 = *((_BYTE *)v18 + v20);
      if ( v22 == 1 )
      {
        v25 = v20 + 1;
        for ( i = v20 + 1; i < cchDest[0]; ++i )
        {
          if ( *((_BYTE *)v18 + i) == 1 )
          {
            v17 = v21 + 1;
            if ( v21 != -1 && a5 )
            {
              if ( v17 > a5 )
              {
                v17 = 0;
                Error = -2147024774;
              }
              else
              {
                v27 = SearchKeyFlags;
                v28 = (LPWSTR)v68;
                LODWORD(v58) = v25;
                v29 = i - 1;
                v30 = v17;
                if ( v67 )
                  v28 = v67;
                v60 = i - 1;
                v31 = 0;
                v32 = 0;
                while ( (unsigned int)v25 < v19 )
                {
                  if ( (unsigned int)v32 >= v19 )
                    break;
                  v33 = *((_BYTE *)v28 + v32);
                  if ( v33 == 1 )
                    break;
                  if ( (unsigned __int8)(v33 + 87) <= 6u || (v27 & 2) != 0 && (unsigned __int8)(v33 + 64) <= 0x39u )
                  {
                    v34 = 0;
                    v35 = 3;
                  }
                  else
                  {
                    v34 = 1;
                    ++v15;
                    v35 = 2;
                  }
                  if ( (unsigned int)v31 < v30 )
                  {
                    v36 = v61;
                    v37 = v59;
                    do
                    {
                      if ( (unsigned int)v32 >= v36 )
                        break;
                      if ( !v35 )
                        break;
                      --v35;
                      v37[v31] = *((_BYTE *)v28 + v32);
                      v31 = (unsigned int)(v31 + 1);
                      v32 = (unsigned int)(v32 + 1);
                    }
                    while ( (unsigned int)v31 < v30 );
                    v56 = (LPWSTR)v64;
                    v17 = v30;
                    v29 = v60;
                  }
                  v27 = SearchKeyFlags;
                  if ( (SearchKeyFlags & 4) != 0 && v34 )
                  {
                    if ( (unsigned int)v31 >= v30 )
                      goto LABEL_52;
                    if ( (SearchKeyFlags & 1) == 0 )
                    {
                      v38 = *((_BYTE *)v28 + v25);
                      if ( v38 == 1 )
                      {
                        v59[v31] = 2;
                      }
                      else
                      {
                        v25 = (unsigned int)(v25 + 1);
                        v59[v31] = v38;
                      }
                    }
                    v31 = (unsigned int)(v31 + 1);
                  }
                  if ( (unsigned int)v31 >= v30 )
                    break;
                  v19 = v61;
                }
                if ( (v27 & 4) == 0 )
                  goto LABEL_53;
LABEL_52:
                if ( (v27 & 1) != 0 )
                {
                  v47 = v15 - v29 + (_DWORD)v58 - 1;
                  v48 = 0;
                  if ( v30 )
                  {
                    v49 = v61;
                    v50 = v59;
                    do
                    {
                      if ( v29 >= v49 || !v15 )
                        break;
                      v51 = v50[v48];
                      if ( (unsigned __int8)(v51 + 87) <= 6u
                        || (SearchKeyFlags & 2) != 0 && (unsigned __int8)(v51 + 64) <= 0x39u )
                      {
                        v48 = (unsigned int)(v48 + 3);
                      }
                      else
                      {
                        v48 = (unsigned int)(v48 + 2);
                        if ( (unsigned int)v48 < v30 )
                        {
                          if ( v47 )
                          {
                            --v47;
                            v52 = 2;
                          }
                          else
                          {
                            v53 = v29--;
                            v52 = *((_BYTE *)v28 + v53);
                          }
                          v50[v48] = v52;
                          v48 = (unsigned int)(v48 + 1);
                        }
                        --v15;
                      }
                    }
                    while ( (unsigned int)v48 < v30 );
                    v56 = (LPWSTR)v64;
                  }
                }
LABEL_53:
                v59[v30 - 1] = 0;
              }
            }
            goto LABEL_54;
          }
        }
        break;
      }
      if ( (unsigned __int8)(v22 + 87) <= 6u || (SearchKeyFlags & 2) != 0 && (unsigned __int8)(v22 + 64) <= 0x39u )
        v23 = 3;
      else
        v23 = 2;
      v20 += v23;
      if ( v23 + (unsigned int)((SearchKeyFlags & 4) != 0) > 3 )
        v24 = 3;
      else
        v24 = v23 + ((SearchKeyFlags & 4) != 0);
      v21 += v24;
    }
    v17 = 0;
    goto LABEL_54;
  }
  Error = ResultFromKnownLastError();
  if ( Error == -2147024774 )
  {
    v45 = LCMapStringEx(v13, v11, a3, -1, 0, 0, 0, 0, 0);
    if ( !v45 )
    {
      LastError = GetLastError();
      Error = LastError;
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
      if ( Error >= 0 )
        Error = -2147467259;
      goto LABEL_84;
    }
    if ( v45 < 0x240 )
    {
      v56 = v67;
      LODWORD(v54) = cchDest[0];
    }
    else
    {
      v54 = v45;
      v67 = (LPWSTR)operator new[](v45, (const struct std::nothrow_t *)&std::nothrow);
      v56 = v67;
      if ( !v67 )
      {
        Error = -2147024882;
        goto LABEL_55;
      }
      *(_QWORD *)cchDest = v54;
    }
    v55 = (WCHAR *)v68;
    if ( v56 )
      v55 = v56;
    if ( LCMapStringEx(v13, v11, a3, -1, v55, v54, 0, 0, 0) )
      goto LABEL_8;
    Error = ResultFromKnownLastError();
  }
  if ( Error < 0 )
  {
LABEL_84:
    v56 = v67;
    goto LABEL_55;
  }
  v17 = 0;
  v56 = v67;
LABEL_54:
  *v62 = v17;
LABEL_55:
  operator delete(v56);
  v39 = pv;
LABEL_56:
  CoTaskMemFree_0(v39);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180053ac4  push    rbp
0x180053ac6  push    rbx
0x180053ac7  push    rsi
0x180053ac8  push    rdi
0x180053ac9  push    r12
0x180053acb  push    r13
0x180053acd  push    r14
0x180053acf  push    r15
0x180053ad1  lea     rbp, [rsp-258h]
0x180053ad9  sub     rsp, 358h
0x180053ae0  mov     rax, cs:__security_cookie
0x180053ae7  xor     rax, rsp
0x180053aea  mov     [rbp+290h+var_50], rax
0x180053af1  mov     rsi, [rbp+290h+arg_28]
0x180053af8  mov     r12d, edx
0x180053afb  xor     r13d, r13d
0x180053afe  mov     [rsp+390h+var_330], r9
0x180053b03  mov     ebx, r13d
0x180053b06  mov     [rsp+390h+var_318], rsi
0x180053b0b  lea     rdx, psz2; "ko"
0x180053b12  mov     [rbp+290h+pv], rbx
0x180053b16  mov     [rsp+390h+var_338], rbx
0x180053b1b  mov     rdi, r8
0x180053b1e  mov     r15, rcx
0x180053b21  call    cs:__imp_StrCmpIW
0x180053b27  lea     r14d, [r13+40h]
0x180053b2b  test    eax, eax
0x180053b2d  jz      loc_180053E36
0x180053b33  lea     rdx, aKoKr; "ko-KR"
0x180053b3a  mov     rcx, r15; psz1
0x180053b3d  call    cs:__imp_StrCmpIW
0x180053b43  test    eax, eax
0x180053b45  jz      loc_180053E36
0x180053b4b  mov     rcx, r15
0x180053b4e  call    ?GetSearchKeyFlags@@YA?AW4SEARCHKEY_FLAGS@@PEBG@Z; GetSearchKeyFlags(ushort const *)
0x180053b53  mov     rcx, r15; lpLocaleName
0x180053b56  mov     dword ptr [rsp+390h+var_340], eax
0x180053b5a  mov     r13d, eax
0x180053b5d  mov     qword ptr [rbp+290h+var_2A0], 240h
0x180053b65  mov     [rbp+290h+var_298], 0
0x180053b6d  bts     r12d, 0Ah
0x180053b72  mov     dword ptr [rsi], 0
0x180053b78  call    cs:__imp_IsValidLocaleName
0x180053b7e  mov     ecx, [rbp+290h+var_2A0]
0x180053b81  lea     r14, psz
0x180053b88  test    eax, eax
0x180053b8a  lea     rdx, [rbp+290h+var_290]
0x180053b8e  mov     rax, [rbp+290h+var_298]
0x180053b92  mov     r8, rdi; lpSrcStr
0x180053b95  cmovnz  r14, r15
0x180053b99  xor     r15d, r15d
0x180053b9c  mov     [rsp+390h+sortHandle], r15; sortHandle
0x180053ba1  test    rax, rax
0x180053ba4  mov     [rsp+390h+lpReserved], r15; lpReserved
0x180053ba9  cmovnz  rdx, rax
0x180053bad  mov     [rsp+390h+lpVersionInformation], r15; lpVersionInformation
0x180053bb2  mov     [rsp+390h+cchDest], ecx; cchDest
0x180053bb6  or      r9d, 0FFFFFFFFh; cchSrc
0x180053bba  mov     [rsp+390h+lpDestStr], rdx; lpDestStr
0x180053bbf  mov     rcx, r14; lpLocaleName
0x180053bc2  mov     edx, r12d; dwMapFlags
0x180053bc5  call    cs:__imp_LCMapStringEx
0x180053bcb  mov     esi, eax
0x180053bcd  test    eax, eax
0x180053bcf  jz      loc_180053F4A
0x180053bd5  mov     ebx, r15d
0x180053bd8  jmp     short loc_180053BF4
0x180053bda  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180053bdf  mov     ebx, eax
0x180053be1  test    ebx, ebx
0x180053be3  js      loc_180053FAF
0x180053be9  mov     r8d, r15d
0x180053bec  test    esi, esi
0x180053bee  jz      loc_180054168
0x180053bf4  mov     rdx, [rbp+290h+var_298]
0x180053bf8  lea     r10, [rbp+290h+var_290]
0x180053bfc  mov     rdi, qword ptr [rbp+290h+var_2A0]
0x180053c00  test    rdx, rdx
0x180053c03  mov     [rsp+390h+var_320], rdi
0x180053c08  mov     r8d, r15d
0x180053c0b  cmovnz  r10, rdx
0x180053c0f  mov     qword ptr [rbp+290h+var_300], rdx
0x180053c13  mov     r11d, r15d
0x180053c16  mov     esi, 3
0x180053c1b  cmp     r8d, edi
0x180053c1e  jnb     loc_180053F3A
0x180053c24  mov     eax, r8d
0x180053c27  mov     r9d, 1
0x180053c2d  mov     cl, [rax+r10]
0x180053c31  cmp     cl, r9b
0x180053c34  jz      short loc_180053C7A
0x180053c36  lea     eax, [rcx+57h]
0x180053c39  cmp     al, 6
0x180053c3b  jbe     loc_180053E12
0x180053c41  test    r13b, 2
0x180053c45  jnz     loc_180053E06
0x180053c4b  mov     ecx, 2
0x180053c50  add     r8d, ecx
0x180053c53  mov     eax, r15d
0x180053c56  mov     r9d, r13d
0x180053c59  and     r9d, 4
0x180053c5d  setnz   al
0x180053c60  add     eax, ecx
0x180053c62  cmp     eax, esi
0x180053c64  ja      loc_180053DFF
0x180053c6a  test    r9d, r9d
0x180053c6d  mov     eax, r15d
0x180053c70  setnz   al
0x180053c73  add     eax, ecx
0x180053c75  add     r11d, eax
0x180053c78  jmp     short loc_180053C1B
0x180053c7a  lea     r14d, [r8+1]
0x180053c7e  mov     ecx, r14d
0x180053c81  cmp     ecx, edi
0x180053c83  jnb     loc_180053F3A
0x180053c89  mov     eax, ecx
0x180053c8b  cmp     [rax+r10], r9b
0x180053c8f  jnz     loc_180053F42
0x180053c95  lea     r8d, [r11+1]
0x180053c99  test    r8d, r8d
0x180053c9c  jz      loc_180053DC1
0x180053ca2  mov     eax, [rbp+290h+arg_20]
0x180053ca8  test    eax, eax
0x180053caa  jz      loc_180053DC1
0x180053cb0  cmp     r8d, eax
0x180053cb3  ja      loc_18005415B
0x180053cb9  mov     r11d, dword ptr [rsp+390h+var_340]
0x180053cbe  lea     r13, [rbp+290h+var_290]
0x180053cc2  test    rdx, rdx
0x180053cc5  mov     dword ptr [rsp+390h+var_338], r14d
0x180053cca  lea     r12d, [rcx-1]
0x180053cce  mov     r10d, r8d
0x180053cd1  cmovnz  r13, rdx
0x180053cd5  mov     [rsp+390h+var_324], r12d
0x180053cda  xor     r9d, r9d
0x180053cdd  xor     esi, esi
0x180053cdf  mov     eax, 1
0x180053ce4  cmp     r14d, edi
0x180053ce7  jnb     loc_180053DA5
0x180053ced  cmp     esi, edi
0x180053cef  jnb     loc_180053DA5
0x180053cf5  mov     cl, [rsi+r13]
0x180053cf9  cmp     cl, al
0x180053cfb  jz      loc_180053DA5
0x180053d01  lea     eax, [rcx+57h]
0x180053d04  cmp     al, 6
0x180053d06  jbe     loc_180053E25
0x180053d0c  test    r11b, 2
0x180053d10  jnz     loc_180053E19
0x180053d16  mov     eax, 1
0x180053d1b  mov     dil, al
0x180053d1e  add     r15d, eax
0x180053d21  lea     r11d, [rax+1]
0x180053d25  cmp     r9d, r10d
0x180053d28  jnb     short loc_180053D64
0x180053d2a  mov     r12, [rsp+390h+var_320]
0x180053d2f  mov     rdx, [rsp+390h+var_330]
0x180053d34  cmp     esi, r12d
0x180053d37  jnb     short loc_180053D58
0x180053d39  test    r11d, r11d
0x180053d3c  jz      short loc_180053D58
0x180053d3e  mov     al, [rsi+r13]
0x180053d42  dec     r11d
0x180053d45  mov     [r9+rdx], al
0x180053d49  mov     eax, 1
0x180053d4e  add     r9d, eax
0x180053d51  add     esi, eax
0x180053d53  cmp     r9d, r10d
0x180053d56  jb      short loc_180053D34
0x180053d58  mov     rdx, qword ptr [rbp+290h+var_300]
0x180053d5c  mov     r8d, r10d
0x180053d5f  mov     r12d, [rsp+390h+var_324]
0x180053d64  mov     r11d, dword ptr [rsp+390h+var_340]
0x180053d69  test    r11b, 4
0x180053d6d  jz      short loc_180053D9C
0x180053d6f  test    dil, dil
0x180053d72  jz      short loc_180053D9C
0x180053d74  cmp     r9d, r10d
0x180053d77  jnb     short loc_180053DAB
0x180053d79  test    al, r11b
0x180053d7c  jnz     short loc_180053D99
0x180053d7e  mov     cl, [r14+r13]
0x180053d82  mov     eax, 1
0x180053d87  cmp     cl, al
0x180053d89  jnz     loc_180053F29
0x180053d8f  mov     rcx, [rsp+390h+var_330]
0x180053d94  mov     byte ptr [r9+rcx], 2
0x180053d99  add     r9d, eax
0x180053d9c  cmp     r9d, r10d
0x180053d9f  jb      loc_180054151
0x180053da5  test    r11b, 4
0x180053da9  jz      short loc_180053DB4
0x180053dab  test    al, r11b
0x180053dae  jnz     loc_180054046
0x180053db4  mov     rax, [rsp+390h+var_330]
0x180053db9  lea     ecx, [r10-1]
0x180053dbd  mov     byte ptr [rcx+rax], 0
0x180053dc1  mov     rax, [rsp+390h+var_318]
0x180053dc6  mov     [rax], r8d
0x180053dc9  mov     rcx, rdx; Block
0x180053dcc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053dd1  mov     rcx, [rbp+290h+pv]; pv
0x180053dd5  call    CoTaskMemFree_0
0x180053dda  mov     eax, ebx
0x180053ddc  mov     rcx, [rbp+290h+var_50]
0x180053de3  xor     rcx, rsp; StackCookie
0x180053de6  call    __security_check_cookie
0x180053deb  add     rsp, 358h
0x180053df2  pop     r15
0x180053df4  pop     r14
0x180053df6  pop     r13
0x180053df8  pop     r12
0x180053dfa  pop     rdi
0x180053dfb  pop     rsi
0x180053dfc  pop     rbx
0x180053dfd  pop     rbp
0x180053dfe  retn
0x180053dff  mov     eax, esi
0x180053e01  jmp     loc_180053C75
0x180053e06  add     cl, 40h ; '@'
0x180053e09  cmp     cl, 39h ; '9'
0x180053e0c  ja      loc_180053C4B
0x180053e12  mov     ecx, esi
0x180053e14  jmp     loc_180053C50
0x180053e19  add     cl, 40h ; '@'
0x180053e1c  cmp     cl, 39h ; '9'
0x180053e1f  ja      loc_180053D16
0x180053e25  mov     eax, 1
0x180053e2a  xor     dil, dil
0x180053e2d  lea     r11d, [rax+2]
0x180053e31  jmp     loc_180053D25
0x180053e36  cmp     cs:byte_18036932C, r13b
0x180053e3d  movups  xmm0, cs:xmmword_1802DD280
0x180053e44  movdqu  [rbp+290h+var_300], xmm0
0x180053e49  jz      loc_180053FB8
0x180053e4f  mov     r8, r14; Size
0x180053e52  lea     rcx, [rbp+290h+pbag]; void *
0x180053e56  xor     edx, edx; Val
0x180053e58  call    memset_0
0x180053e5d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180053e61  mov     [rbp+290h+pbag.Size], r14
0x180053e65  inc     r8; dwLength
0x180053e68  cmp     [rdi+r8*2], r13w
0x180053e6d  jnz     short loc_180053E65
0x180053e6f  mov     rcx, cs:?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; pServiceInfo
0x180053e76  lea     rax, [rbp+290h+pbag]
0x180053e7a  mov     qword ptr [rsp+390h+cchDest], rax; pbag
0x180053e7f  xor     r9d, r9d; dwIndex
0x180053e82  mov     rdx, rdi; pszText
0x180053e85  mov     [rsp+390h+lpDestStr], r13; pOptions
0x180053e8a  call    cs:__imp_MappingRecognizeText
0x180053e90  mov     r14d, eax
0x180053e93  test    eax, eax
0x180053e95  js      short loc_180053EF1
0x180053e97  mov     bl, r13b
0x180053e9a  mov     esi, r13d
0x180053e9d  cmp     [rbp+290h+pbag.dwRangesCount], r13d
0x180053ea1  jbe     short loc_180053EDC
0x180053ea3  test    bl, bl
0x180053ea5  jnz     short loc_180053EE2
0x180053ea7  mov     rdx, [rbp+290h+pbag.prgResultRanges]
0x180053eab  mov     ecx, esi
0x180053ead  lea     rax, [rcx+rcx*8]
0x180053eb1  mov     rdx, [rdx+rax*8+18h]; pszSrch
0x180053eb6  lea     rcx, pszFirst; "Hang"
0x180053ebd  call    cs:__imp_StrStrIW
0x180053ec3  test    rax, rax
0x180053ec6  movzx   ebx, bl
0x180053ec9  mov     eax, 1
0x180053ece  cmovnz  ebx, eax
0x180053ed1  add     esi, eax
0x180053ed3  cmp     esi, [rbp+290h+pbag.dwRangesCount]
0x180053ed6  jb      short loc_180053EA3
0x180053ed8  test    bl, bl
0x180053eda  jnz     short loc_180053EE2
0x180053edc  mov     r14d, 1
0x180053ee2  lea     rcx, [rbp+290h+pbag]; pBag
0x180053ee6  call    cs:__imp_MappingFreePropertyBag
0x180053eec  mov     rsi, [rsp+390h+var_318]
0x180053ef1  test    r14d, r14d
0x180053ef4  jnz     loc_180053B4B
0x180053efa  lea     r8, [rsp+390h+var_338]; unsigned __int16 **
0x180053eff  mov     rdx, rdi; pszText
0x180053f02  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; prgServices
0x180053f09  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x180053f0e  mov     ebx, eax
0x180053f10  test    eax, eax
0x180053f12  js      loc_18005403C
0x180053f18  mov     rax, [rsp+390h+var_338]
0x180053f1d  mov     [rbp+290h+pv], rax
0x180053f21  mov     rdi, rax
0x180053f24  jmp     loc_180053B4B
0x180053f29  mov     rdi, [rsp+390h+var_330]
0x180053f2e  add     r14d, eax
0x180053f31  mov     [r9+rdi], cl
0x180053f35  jmp     loc_180053D99
0x180053f3a  mov     r8d, r15d
0x180053f3d  jmp     loc_180053DC1
0x180053f42  add     ecx, r9d
0x180053f45  jmp     loc_180053C81
  ... truncated ...
```
