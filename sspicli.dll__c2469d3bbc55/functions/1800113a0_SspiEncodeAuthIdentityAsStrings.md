# SspiEncodeAuthIdentityAsStrings

- ea: `0x1800113a0`
- end: `0x180011fcc`
- name: `SspiEncodeAuthIdentityAsStrings`
- size: `3116`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE pAuthIdentity, PCWSTR *ppszUserName, PCWSTR *ppszDomainName, PCWSTR *ppszPackedCredentialsString)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000fae0`
- `0x1800110f0`
- `0x180017410`

## callees

- `0x180005cc0`
- `0x1800113a0`
- `0x180015068`
- `0x18001592c`
- `0x180018600`
- `0x18001fe8c`
- `0x18001fed4`
- `0x1800201e4`
- `0x180022047`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180011ef2`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180011ef2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011484`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800114fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011561`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800115bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800116b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011707`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011744`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800118c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001190d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001194e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011990`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011a46`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011ae9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011b50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011ba9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011c27`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011d2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011f3c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011f97`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011484`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800114fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011561`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800115bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800116b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011707`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011744`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800118c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001190d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001194e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011990`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011a46`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011ae9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011b50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011ba9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011c27`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011d2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011f3c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011f97`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiEncodeAuthIdentityAsStrings(
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE pAuthIdentity,
        PCWSTR *ppszUserName,
        PCWSTR *ppszDomainName,
        PCWSTR *ppszPackedCredentialsString)
{
  int v4; // esi
  PVOID *v5; // r12
  PVOID *v6; // r15
  PVOID *v7; // rbx
  char *v9; // r13
  _WORD *v11; // r14
  int v12; // ecx
  unsigned int v13; // eax
  int v14; // ebx
  char *v15; // rax
  char *v16; // rcx
  __int64 v17; // rax
  char *v18; // rcx
  __int64 v19; // rsi
  WCHAR *v20; // rax
  unsigned int v21; // eax
  __int64 v22; // rbx
  WCHAR *v23; // rax
  __int64 v24; // rax
  _WORD *v25; // rax
  int v26; // eax
  char *v27; // rcx
  unsigned int v28; // eax
  unsigned int v29; // esi
  WCHAR *v30; // rax
  WCHAR *v31; // rax
  HLOCAL v32; // rax
  char *v33; // r14
  unsigned __int8 *v34; // rcx
  unsigned __int8 *v35; // rcx
  const void **v36; // rdi
  HLOCAL v37; // rax
  HLOCAL v38; // rax
  HLOCAL v39; // rax
  HLOCAL v40; // rax
  __int64 v41; // rsi
  __int64 v42; // r15
  __int64 v43; // rdi
  __int64 v44; // rdx
  HLOCAL v45; // rax
  char *v46; // rcx
  size_t v47; // rbx
  char *v48; // rcx
  WCHAR *v49; // rax
  unsigned int v50; // eax
  __int64 v51; // rbx
  WCHAR *v52; // rax
  PVOID v53; // rdi
  __int16 v54; // r15
  __int64 v55; // rdx
  _WORD *v56; // rax
  _WORD *v57; // rdx
  __int64 v58; // rax
  unsigned int v59; // edx
  unsigned int v60; // r15d
  _WORD *v61; // rax
  _WORD *v62; // rcx
  int v63; // eax
  bool v64; // zf
  PVOID v65; // rdx
  char *v66; // rdi
  enum _CRED_MARSHAL_TYPE v67; // ecx
  PVOID v68; // rdx
  unsigned int v69; // eax
  __int64 v70; // rdx
  _BYTE *v71; // rax
  PVOID v72; // rcx
  __int64 v73; // rdx
  _BYTE *v74; // rax
  PVOID v75; // rcx
  _BYTE *v76; // rdx
  __int64 i; // rax
  const unsigned __int16 *v78; // rcx
  wchar_t *v79; // rax
  __int64 v80; // rsi
  __int64 v81; // rdi
  _WORD *v82; // r14
  HLOCAL v83; // rax
  WCHAR *v84; // rax
  PVOID v85; // [rsp+28h] [rbp-59h] BYREF
  _QWORD v86[2]; // [rsp+30h] [rbp-51h] BYREF
  void *Src; // [rsp+40h] [rbp-41h] BYREF
  enum _CRED_MARSHAL_TYPE v88[2]; // [rsp+48h] [rbp-39h] BYREF
  PVOID v89; // [rsp+50h] [rbp-31h]
  PVOID v90; // [rsp+58h] [rbp-29h]
  unsigned __int16 *v91; // [rsp+60h] [rbp-21h] BYREF
  __int64 v92; // [rsp+68h] [rbp-19h]
  PVOID v93; // [rsp+70h] [rbp-11h]
  __int64 v94; // [rsp+78h] [rbp-9h]
  PVOID DataBuffer; // [rsp+80h] [rbp-1h]
  _DWORD v96[2]; // [rsp+88h] [rbp+7h] BYREF
  _WORD *v97; // [rsp+90h] [rbp+Fh]
  unsigned int Size; // [rsp+E8h] [rbp+67h]

  v4 = 0;
  v5 = (PVOID *)ppszPackedCredentialsString;
  Src = 0;
  v89 = 0;
  v6 = (PVOID *)ppszDomainName;
  *(_QWORD *)v88 = 0;
  v7 = (PVOID *)ppszUserName;
  v93 = 0;
  v91 = 0;
  v9 = 0;
  v85 = 0;
  if ( !pAuthIdentity )
    return -1073741811;
  *ppszUserName = 0;
  v11 = 0;
  *ppszDomainName = 0;
  v86[0] = 0;
  DataBuffer = 0;
  LODWORD(v92) = 24;
  Size = 0;
  v90 = 0;
  LODWORD(v94) = 0;
  if ( ppszPackedCredentialsString )
    *ppszPackedCredentialsString = 0;
  if ( *(_DWORD *)pAuthIdentity == 513 )
  {
    v12 = *((unsigned __int16 *)pAuthIdentity + 8);
    v13 = v12 + *((unsigned __int16 *)pAuthIdentity + 12);
    HIDWORD(v86[0]) = 0;
    if ( v13 >= 0x7FFD || (*((_BYTE *)pAuthIdentity + 36) & 0x10) != 0 )
    {
      v14 = -1073741811;
LABEL_69:
      v36 = (const void **)v85;
LABEL_70:
      if ( *ppszUserName )
      {
        SspiLocalFree((PVOID)*ppszUserName);
        *ppszUserName = 0;
      }
      if ( *v6 )
      {
        SspiLocalFree(*v6);
        *v6 = 0;
      }
      if ( v5 && *v5 )
      {
        SspiLocalFree(*v5);
        *v5 = 0;
      }
      goto LABEL_160;
    }
    if ( !ppszPackedCredentialsString || !*((_DWORD *)pAuthIdentity + 7) && !*((_WORD *)pAuthIdentity + 22) )
    {
      if ( *((_DWORD *)pAuthIdentity + 3) )
      {
        v31 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)(v12 + 2) + 2LL);
        *ppszUserName = v31;
        if ( !v31 )
          goto LABEL_13;
        memcpy_0(
          v31,
          (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 3),
          *((unsigned __int16 *)pAuthIdentity + 8));
      }
      if ( *((_DWORD *)pAuthIdentity + 5) )
      {
        v32 = LocalAlloc(0x40u, *((unsigned __int16 *)pAuthIdentity + 12) + 4LL);
        *v6 = v32;
        if ( !v32 )
          goto LABEL_13;
        memcpy_0(
          v32,
          (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 5),
          *((unsigned __int16 *)pAuthIdentity + 12));
      }
      goto LABEL_158;
    }
    v15 = (char *)LocalAlloc(0x40u, v13 + 4 + 2LL);
    v90 = v15;
    if ( !v15 )
    {
LABEL_13:
      v14 = -1073741801;
LABEL_68:
      v5 = (PVOID *)ppszPackedCredentialsString;
      goto LABEL_69;
    }
    v16 = v15;
    if ( *((_WORD *)pAuthIdentity + 12) )
    {
      memcpy_0(
        v15,
        (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 5),
        *((unsigned __int16 *)pAuthIdentity + 12));
      v17 = *((unsigned __int16 *)pAuthIdentity + 12);
      v18 = (char *)v90;
      *(_WORD *)((char *)v90 + v17) = 92;
      v16 = &v18[v17 + 2];
    }
    memcpy_0(
      v16,
      (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 3),
      *((unsigned __int16 *)pAuthIdentity + 8));
    v19 = -1;
    v91 = (unsigned __int16 *)v90;
    if ( *((_WORD *)pAuthIdentity + 8) || *((_WORD *)pAuthIdentity + 12) )
    {
      v21 = LocalCredMarshalCredentialW(UsernameForPackedCredentials, &v91, (unsigned __int16 **)&Src);
      v9 = (char *)Src;
      if ( v21 )
        goto LABEL_21;
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)Src + v22) );
      v23 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)(2 * v22 + 2) + 2LL);
      *ppszUserName = v23;
      if ( !v23 )
        goto LABEL_13;
      memcpy_0(v23, v9, 2LL * (unsigned int)v22);
    }
    else
    {
      v20 = (WCHAR *)LocalAlloc(0x40u, 0xCu);
      *ppszUserName = v20;
      if ( !v20 )
        goto LABEL_13;
      *(_QWORD *)v20 = 0x40004000400040LL;
    }
    v24 = *((unsigned __int16 *)pAuthIdentity + 22) + (unsigned int)*((unsigned __int16 *)pAuthIdentity + 16) + 24;
    v92 = v24;
    if ( (unsigned int)v24 >= 0xFFFF )
    {
      v14 = -1073741811;
      goto LABEL_68;
    }
    v92 = ((_DWORD)v24 + 1) & 0xFFFFFFFE;
    v25 = LocalAlloc(0x40u, (unsigned int)v92 + 2LL);
    v11 = v25;
    if ( !v25 )
      goto LABEL_13;
    *v25 = 24;
    v26 = *((_DWORD *)pAuthIdentity + 9);
    *((_DWORD *)v11 + 1) = v26;
    if ( !*((_DWORD *)pAuthIdentity + 5) )
    {
      v26 |= 0x40000u;
      *((_DWORD *)v11 + 1) = v26;
    }
    if ( !*((_DWORD *)pAuthIdentity + 3) )
      *((_DWORD *)v11 + 1) = v26 | 0x20000;
    *((_DWORD *)v11 + 2) = 24;
    v11[6] = *((_WORD *)pAuthIdentity + 16);
    memcpy_0(
      v11 + 12,
      (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 7),
      *((unsigned __int16 *)pAuthIdentity + 16));
    v27 = (char *)v11 + *((unsigned __int16 *)pAuthIdentity + 16) + 24;
    *((_DWORD *)v11 + 4) = *((unsigned __int16 *)pAuthIdentity + 16) + 24;
    v11[10] = *((_WORD *)pAuthIdentity + 22) >> 1;
    memcpy_0(
      v27,
      (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 10),
      *((unsigned __int16 *)pAuthIdentity + 22));
    LODWORD(v86[0]) = v92;
    v86[1] = v11;
    if ( v9 )
    {
      SspiLocalFree(v9);
      Src = 0;
    }
    v28 = LocalCredMarshalCredentialW(BinaryBlobCredential, v86, (unsigned __int16 **)&Src);
    v9 = (char *)Src;
    if ( !v28 )
    {
      do
        ++v19;
      while ( *((_WORD *)Src + v19) );
      if ( (unsigned int)v19 <= 8 )
      {
        v14 = -1073741637;
        goto LABEL_68;
      }
      v29 = v19 - 8;
      v30 = (WCHAR *)LocalAlloc(0x40u, 2 * v29 + 2 + 2LL);
      v5 = (PVOID *)ppszPackedCredentialsString;
      *ppszPackedCredentialsString = v30;
      if ( !v30 )
      {
        v14 = -1073741801;
        goto LABEL_69;
      }
      goto LABEL_40;
    }
LABEL_21:
    v14 = -1073741670;
    goto LABEL_68;
  }
  if ( *(_DWORD *)pAuthIdentity == 512 )
  {
    v33 = (char *)pAuthIdentity + 8;
    if ( ppszPackedCredentialsString && *((_DWORD *)pAuthIdentity + 16) )
      v4 = 1;
  }
  else
  {
    v33 = (char *)pAuthIdentity;
  }
  if ( (v33[44] & 0x10) != 0 )
  {
    v11 = (_WORD *)v86[0];
    v14 = -1073741811;
    goto LABEL_69;
  }
  if ( (v33[44] & 1) != 0 )
  {
    if ( *(_QWORD *)v33 )
    {
      v14 = SspiHelperConvertAnsiStringToUnicodeString(*(unsigned __int8 **)v33, *((_DWORD *)v33 + 2), ppszUserName);
      if ( v14 < 0 )
        goto LABEL_67;
    }
    v34 = (unsigned __int8 *)*((_QWORD *)v33 + 2);
    if ( v34 )
    {
      v14 = SspiHelperConvertAnsiStringToUnicodeString(v34, *((_DWORD *)v33 + 6), (const unsigned __int16 **)v6);
      if ( v14 < 0 )
        goto LABEL_67;
    }
    if ( ppszPackedCredentialsString )
    {
      v35 = (unsigned __int8 *)*((_QWORD *)v33 + 4);
      if ( v35 )
      {
        v14 = SspiHelperConvertAnsiStringToUnicodeString(v35, *((_DWORD *)v33 + 10), (const unsigned __int16 **)v88);
        v89 = *(PVOID *)v88;
        if ( v14 < 0 )
          goto LABEL_67;
      }
    }
    if ( v4 )
    {
      v14 = SspiHelperConvertAnsiStringToUnicodeString(
              *((unsigned __int8 **)pAuthIdentity + 7),
              *((_DWORD *)pAuthIdentity + 16),
              (const unsigned __int16 **)&v91);
      if ( v14 >= 0 )
      {
        v88[0] = *((enum _CRED_MARSHAL_TYPE *)pAuthIdentity + 16);
        v93 = v91;
        goto LABEL_91;
      }
      v93 = v91;
LABEL_67:
      v11 = (_WORD *)v86[0];
      goto LABEL_68;
    }
    v7 = (PVOID *)ppszUserName;
    goto LABEL_155;
  }
  if ( *(_QWORD *)v33 )
  {
    v37 = LocalAlloc(0x40u, (unsigned int)(2 * *((_DWORD *)v33 + 2) + 2) + 2LL);
    *v7 = v37;
    if ( !v37 )
      goto LABEL_79;
    memcpy_0(v37, *(const void **)v33, 2LL * *((unsigned int *)v33 + 2));
  }
  if ( *((_QWORD *)v33 + 2) )
  {
    v38 = LocalAlloc(0x40u, (unsigned int)(2 * *((_DWORD *)v33 + 6) + 2) + 2LL);
    *v6 = v38;
    if ( !v38 )
      goto LABEL_79;
    memcpy_0(v38, *((const void **)v33 + 2), 2LL * *((unsigned int *)v33 + 6));
  }
  if ( ppszPackedCredentialsString && *((_QWORD *)v33 + 4) )
  {
    v39 = LocalAlloc(0x40u, (unsigned int)(2 * *((_DWORD *)v33 + 10) + 2) + 2LL);
    v89 = v39;
    if ( !v39 )
      goto LABEL_79;
    memcpy_0(v39, *((const void **)v33 + 4), 2LL * *((unsigned int *)v33 + 10));
  }
  if ( !v4 )
  {
LABEL_155:
    if ( ppszPackedCredentialsString )
    {
      *ppszPackedCredentialsString = (PCWSTR)v89;
      v89 = 0;
      goto LABEL_157;
    }
    if ( *v6 && *(_WORD *)*v6 )
      goto LABEL_157;
    v78 = (const unsigned __int16 *)*v7;
    v88[0] = 0;
    if ( (unsigned int)SspiHelperIsEncodedNullUserName(v78) )
    {
      if ( *v7 )
      {
        SspiLocalFree(*v7);
        *v7 = 0;
      }
      if ( *v6 )
      {
        SspiLocalFree(*v6);
        *v6 = 0;
      }
      goto LABEL_157;
    }
    if ( !(unsigned int)LocalCredIsMarshaledCredentialW((const unsigned __int16 *)*v7) )
      goto LABEL_157;
    if ( LocalCredUnmarshalCredentialW((const unsigned __int16 *)*v7, v88, &v85) )
    {
      v14 = -1073741670;
      goto LABEL_67;
    }
    if ( v88[0] != UsernameForPackedCredentials )
    {
LABEL_157:
      v11 = (_WORD *)v86[0];
      goto LABEL_158;
    }
    if ( *v7 )
    {
      SspiLocalFree(*v7);
      *v7 = 0;
    }
    if ( *v6 )
    {
      SspiLocalFree(*v6);
      *v6 = 0;
    }
    v36 = (const void **)v85;
    v79 = wcschr(*(const wchar_t **)v85, 0x5Cu);
    v80 = -1;
    if ( !v79 )
    {
      do
LABEL_203:
        ++v80;
      while ( *((_WORD *)*v36 + v80) );
      if ( (unsigned int)v80 <= 0x7FFD )
      {
        v84 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)(2 * v80 + 2) + 2LL);
        *ppszUserName = v84;
        if ( v84 )
        {
          memcpy_0(v84, *v36, 2LL * (unsigned int)v80);
          v11 = (_WORD *)v86[0];
          goto LABEL_159;
        }
        v14 = -1073741801;
      }
      else
      {
        v14 = -1073741811;
      }
      v11 = (_WORD *)v86[0];
      v5 = 0;
      goto LABEL_70;
    }
    *v79 = 0;
    v81 = -1;
    v82 = v79 + 1;
    do
      ++v81;
    while ( v82[v81] );
    if ( (unsigned int)v81 > 0x7FFD )
    {
      v14 = -1073741811;
      goto LABEL_67;
    }
    v83 = LocalAlloc(0x40u, (unsigned int)(2 * v81 + 2) + 2LL);
    *v6 = v83;
    if ( v83 )
    {
      memcpy_0(v83, v82, 2LL * (unsigned int)v81);
      v36 = (const void **)v85;
      goto LABEL_203;
    }
LABEL_79:
    v14 = -1073741801;
    goto LABEL_67;
  }
  v88[0] = *((enum _CRED_MARSHAL_TYPE *)pAuthIdentity + 16);
  v40 = LocalAlloc(0x40u, (unsigned int)(2 * v88[0] + 2) + 2LL);
  v93 = v40;
  if ( !v40 )
    goto LABEL_79;
  memcpy_0(v40, *((const void **)pAuthIdentity + 7), 2LL * *((unsigned int *)pAuthIdentity + 16));
LABEL_91:
  v41 = -1;
  v96[1] = 0;
  if ( *ppszUserName )
  {
    v42 = -1;
    do
      ++v42;
    while ( (*ppszUserName)[v42] );
  }
  else
  {
    LODWORD(v42) = 0;
  }
  if ( *ppszDomainName )
  {
    v43 = -1;
    do
      ++v43;
    while ( (*ppszDomainName)[v43] );
  }
  else
  {
    LODWORD(v43) = 0;
  }
  if ( v89 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_WORD *)v89 + v44) );
  }
  else
  {
    v44 = 0;
  }
  v94 = v44;
  if ( (unsigned int)v42 > 0x7FFD || (unsigned int)v43 > 0x7FFD || (unsigned int)v44 > 0x7FFD )
    goto LABEL_130;
  v45 = LocalAlloc(0x40u, (unsigned int)(2 * (v43 + v42) + 4) + 2LL);
  v90 = v45;
  if ( !v45 )
    goto LABEL_110;
  v46 = (char *)v45;
  if ( (_DWORD)v43 )
  {
    v47 = 2LL * (unsigned int)v43;
    memcpy_0(v45, *ppszDomainName, v47);
    v48 = (char *)v90 + 2;
    *(_WORD *)((char *)v90 + v47) = 92;
    v46 = &v48[v47];
  }
  memcpy_0(v46, *ppszUserName, 2LL * (unsigned int)v42);
  v91 = (unsigned __int16 *)v90;
  if ( *ppszDomainName )
  {
    SspiLocalFree((PVOID)*ppszDomainName);
    *ppszDomainName = 0;
  }
  if ( *ppszUserName )
  {
    SspiLocalFree((PVOID)*ppszUserName);
    *ppszUserName = 0;
  }
  if ( (_DWORD)v42 || (_DWORD)v43 )
  {
    v50 = LocalCredMarshalCredentialW(UsernameForPackedCredentials, &v91, (unsigned __int16 **)&Src);
    v9 = (char *)Src;
    if ( v50 )
    {
      v14 = -1073741670;
      goto LABEL_111;
    }
    v51 = -1;
    do
      ++v51;
    while ( *((_WORD *)Src + v51) );
    v52 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)(2 * v51 + 2) + 2LL);
    *ppszUserName = v52;
    if ( !v52 )
    {
LABEL_110:
      v14 = -1073741801;
LABEL_111:
      v6 = (PVOID *)ppszDomainName;
      goto LABEL_67;
    }
    memcpy_0(v52, v9, 2LL * (unsigned int)v51);
  }
  else
  {
    v49 = (WCHAR *)LocalAlloc(0x40u, 0xCu);
    *ppszUserName = v49;
    if ( !v49 )
      goto LABEL_110;
    *(_QWORD *)v49 = 0x40004000400040LL;
  }
  v53 = v89;
  if ( v89 )
  {
    v54 = v94;
    v55 = (unsigned int)(2 * v94 + 32);
    Size = v55;
    if ( (unsigned int)v55 >= 0xFFFF )
    {
LABEL_130:
      v14 = -1073741811;
      goto LABEL_111;
    }
    v56 = LocalAlloc(0x40u, v55 + 2);
    DataBuffer = v56;
    v57 = v56;
    if ( !v56 )
      goto LABEL_110;
    *v56 = 28;
    v56[1] = Size;
    *((_DWORD *)v56 + 5) = 28;
    v58 = (unsigned __int16)(2 * v54);
    v57[12] = v58;
    *(_OWORD *)(v57 + 2) = SEC_WINNT_AUTH_DATA_TYPE_PASSWORD;
    memcpy_0(v57 + 14, v53, (unsigned __int16)v58);
    v59 = Size;
  }
  else
  {
    v59 = 0;
    Size = 0;
  }
  v60 = v59 + 2 * (v88[0] + 12);
  LODWORD(v92) = v60;
  if ( v60 >= 0xFFFF )
    goto LABEL_130;
  v61 = LocalAlloc(0x40u, v60 + 2LL);
  v86[0] = v61;
  v62 = v61;
  if ( !v61 )
    goto LABEL_110;
  *v61 = 24;
  v63 = *((_DWORD *)v33 + 11);
  *((_DWORD *)v62 + 1) = v63;
  if ( !*((_QWORD *)v33 + 2) )
  {
    v63 |= 0x40000u;
    *((_DWORD *)v62 + 1) = v63;
  }
  v64 = *(_QWORD *)v33 == 0;
  v11 = (_WORD *)v86[0];
  if ( v64 )
    *(_DWORD *)(v86[0] + 4LL) = v63 | 0x20000;
  v65 = DataBuffer;
  v66 = (char *)(v11 + 12);
  if ( DataBuffer )
  {
    *((_DWORD *)v11 + 2) = 24;
    v11[6] = Size;
    memcpy_0(v11 + 12, v65, Size);
    v66 += Size;
  }
  v67 = v88[0];
  if ( v88[0] )
  {
    v68 = v93;
    v11[10] = v88[0];
    *((_DWORD *)v11 + 4) = (_DWORD)v66 - (_DWORD)v11;
    memcpy_0(v66, v68, 2LL * (unsigned int)v67);
  }
  v96[0] = v60;
  v97 = v11;
  if ( v9 )
  {
    SspiLocalFree(v9);
    Src = 0;
  }
  v69 = LocalCredMarshalCredentialW(BinaryBlobCredential, v96, (unsigned __int16 **)&Src);
  v9 = (char *)Src;
  if ( v69 )
  {
    v14 = -1073741670;
LABEL_148:
    v6 = (PVOID *)ppszDomainName;
    goto LABEL_68;
  }
  do
    ++v41;
  while ( *((_WORD *)Src + v41) );
  if ( (unsigned int)v41 <= 8 )
  {
    v14 = -1073741637;
    goto LABEL_148;
  }
  v29 = v41 - 8;
  v30 = (WCHAR *)LocalAlloc(0x40u, 2 * v29 + 2 + 2LL);
  v5 = (PVOID *)ppszPackedCredentialsString;
  *ppszPackedCredentialsString = v30;
  if ( !v30 )
  {
    v6 = (PVOID *)ppszDomainName;
    v14 = -1073741801;
    goto LABEL_69;
  }
LABEL_40:
  memcpy_0(v30, v9 + 16, 2LL * v29);
LABEL_158:
  v36 = (const void **)v85;
LABEL_159:
  v14 = 0;
LABEL_160:
  if ( v9 )
    SspiLocalFree(v9);
  if ( v11 )
  {
    v70 = (unsigned int)v92;
    v71 = v11;
    if ( (_DWORD)v92 )
    {
      do
      {
        *v71++ = 0;
        --v70;
      }
      while ( v70 );
    }
    SspiLocalFree(v11);
  }
  v72 = DataBuffer;
  if ( DataBuffer )
  {
    v73 = Size;
    v74 = DataBuffer;
    if ( Size )
    {
      do
      {
        *v74++ = 0;
        --v73;
      }
      while ( v73 );
    }
    SspiLocalFree(v72);
  }
  if ( v93 )
    SspiLocalFree(v93);
  v75 = v89;
  if ( v89 )
  {
    v76 = v89;
    for ( i = 2LL * (unsigned int)v94; i; --i )
      *v76++ = 0;
    SspiLocalFree(v75);
  }
  if ( v90 )
    SspiLocalFree(v90);
  if ( v36 )
    SspiLocalFree(v36);
  return SspNtStatusToSecStatus((unsigned int)v14);
}

```

## disassembly

```asm
0x1800113a0  mov     rax, rsp
0x1800113a3  mov     [rax+20h], r9
0x1800113a7  mov     [rax+18h], r8
0x1800113ab  mov     [rax+10h], rdx
0x1800113af  push    rbp
0x1800113b0  push    rbx
0x1800113b1  push    rsi
0x1800113b2  push    rdi
0x1800113b3  push    r12
0x1800113b5  push    r13
0x1800113b7  push    r14
0x1800113b9  push    r15
0x1800113bb  lea     rbp, [rax-5Fh]
0x1800113bf  sub     rsp, 98h
0x1800113c6  xor     esi, esi
0x1800113c8  mov     r12, r9
0x1800113cb  mov     [rbp+57h+Src], rsi
0x1800113cf  mov     eax, esi
0x1800113d1  mov     [rbp+57h+var_88], rax
0x1800113d5  mov     r15, r8
0x1800113d8  mov     qword ptr [rbp+57h+var_90], rax
0x1800113dc  mov     rbx, rdx
0x1800113df  mov     [rbp+57h+var_68], rsi
0x1800113e3  mov     rdi, rcx
0x1800113e6  mov     [rbp+57h+var_78], rsi
0x1800113ea  mov     r13d, esi
0x1800113ed  mov     [rbp+57h+var_B0], rsi
0x1800113f1  test    rcx, rcx
0x1800113f4  jnz     short loc_180011400
0x1800113f6  mov     eax, 0C000000Dh
0x1800113fb  jmp     loc_180011E31
0x180011400  mov     [rdx], rsi
0x180011403  mov     r14, rsi
0x180011406  mov     [r8], rsi
0x180011409  mov     [rbp+57h+var_A8], rsi
0x18001140d  mov     [rbp+57h+DataBuffer], rsi
0x180011411  mov     dword ptr [rbp+57h+var_70], 18h
0x180011418  mov     dword ptr [rbp+57h+Size], esi
0x18001141b  mov     [rbp+57h+var_80], rsi
0x18001141f  mov     dword ptr [rbp+57h+var_60], esi
0x180011422  test    r9, r9
0x180011425  jz      short loc_18001142A
0x180011427  mov     [r9], rsi
0x18001142a  cmp     dword ptr [rcx], 201h
0x180011430  jnz     loc_18001176E
0x180011436  movzx   ecx, word ptr [rcx+10h]
0x18001143a  mov     ebx, 7FFDh
0x18001143f  movzx   eax, word ptr [rdi+18h]
0x180011443  add     eax, ecx
0x180011445  mov     dword ptr [rbp+57h+var_A8+4], esi
0x180011448  cmp     eax, ebx
0x18001144a  jb      short loc_180011456
0x18001144c  mov     ebx, 0C000000Dh
0x180011451  jmp     loc_180011860
0x180011456  test    byte ptr [rdi+24h], 10h
0x18001145a  jnz     short loc_18001144C
0x18001145c  test    r9, r9
0x18001145f  jz      loc_1800116F2
0x180011465  cmp     [rdi+1Ch], esi
0x180011468  jnz     short loc_180011474
0x18001146a  cmp     [rdi+2Ch], si
0x18001146e  jz      loc_1800116F2
0x180011474  lea     edx, [rax+4]
0x180011477  mov     r12d, 40h ; '@'
0x18001147d  add     rdx, 2; uBytes
0x180011481  mov     ecx, r12d; uFlags
0x180011484  call    cs:__imp_LocalAlloc
0x18001148a  mov     [rbp+57h+var_80], rax
0x18001148e  test    rax, rax
0x180011491  jnz     short loc_18001149D
0x180011493  mov     ebx, 0C0000017h
0x180011498  jmp     loc_18001185C
0x18001149d  mov     rcx, rax; void *
0x1800114a0  cmp     [rdi+18h], si
0x1800114a4  jz      short loc_1800114CB
0x1800114a6  mov     edx, [rdi+14h]
0x1800114a9  movzx   r8d, word ptr [rdi+18h]; Size
0x1800114ae  add     rdx, rdi; Src
0x1800114b1  call    memcpy_0
0x1800114b6  movzx   eax, word ptr [rdi+18h]
0x1800114ba  mov     rcx, [rbp+57h+var_80]
0x1800114be  mov     word ptr [rax+rcx], 5Ch ; '\'
0x1800114c4  add     rcx, 2
0x1800114c8  add     rcx, rax; void *
0x1800114cb  mov     edx, [rdi+0Ch]
0x1800114ce  movzx   r8d, word ptr [rdi+10h]; Size
0x1800114d3  add     rdx, rdi; Src
0x1800114d6  call    memcpy_0
0x1800114db  mov     rax, [rbp+57h+var_80]
0x1800114df  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800114e3  xor     ebx, ebx
0x1800114e5  mov     [rbp+57h+var_78], rax
0x1800114e9  cmp     [rdi+10h], bx
0x1800114ed  jnz     short loc_18001151F
0x1800114ef  cmp     [rdi+18h], bx
0x1800114f3  jnz     short loc_18001151F
0x1800114f5  lea     edx, [rsi+0Dh]; uBytes
0x1800114f8  mov     ecx, r12d; uFlags
0x1800114fb  call    cs:__imp_LocalAlloc
0x180011501  mov     rdx, [rbp+57h+arg_8]
0x180011505  mov     rcx, rax
0x180011508  mov     [rdx], rax
0x18001150b  test    rax, rax
0x18001150e  jz      short loc_180011493
0x180011510  mov     rax, 40004000400040h
0x18001151a  mov     [rcx], rax
0x18001151d  jmp     short loc_180011588
0x18001151f  lea     r8, [rbp+57h+Src]; unsigned __int16 **
0x180011523  mov     ecx, 4; enum _CRED_MARSHAL_TYPE
0x180011528  lea     rdx, [rbp+57h+var_78]; void *
0x18001152c  call    ?LocalCredMarshalCredentialW@@YAKW4_CRED_MARSHAL_TYPE@@PEAXPEAPEAG@Z; LocalCredMarshalCredentialW(_CRED_MARSHAL_TYPE,void *,ushort * *)
0x180011531  mov     r13, [rbp+57h+Src]
0x180011535  test    eax, eax
0x180011537  jz      short loc_180011543
0x180011539  mov     ebx, 0C000009Ah
0x18001153e  jmp     loc_18001185C
0x180011543  mov     rbx, rsi
0x180011546  xor     eax, eax
0x180011548  inc     rbx
0x18001154b  cmp     [r13+rbx*2+0], ax
0x180011551  jnz     short loc_180011548
0x180011553  lea     edx, ds:2[rbx*2]
0x18001155a  mov     ecx, r12d; uFlags
0x18001155d  add     rdx, 2; uBytes
0x180011561  call    cs:__imp_LocalAlloc
0x180011567  mov     rdx, [rbp+57h+arg_8]
0x18001156b  mov     [rdx], rax
0x18001156e  test    rax, rax
0x180011571  jz      loc_180011493
0x180011577  mov     r8d, ebx
0x18001157a  mov     rdx, r13; Src
0x18001157d  add     r8, r8; Size
0x180011580  mov     rcx, rax; void *
0x180011583  call    memcpy_0
0x180011588  movzx   eax, word ptr [rdi+20h]
0x18001158c  mov     ebx, 0FFFFh
0x180011591  movzx   ecx, word ptr [rdi+2Ch]
0x180011595  add     eax, 18h
0x180011598  add     eax, ecx
0x18001159a  mov     [rbp+57h+var_70], rax
0x18001159e  cmp     eax, ebx
0x1800115a0  jb      short loc_1800115AC
0x1800115a2  mov     ebx, 0C000000Dh
0x1800115a7  jmp     loc_18001185C
0x1800115ac  inc     eax
0x1800115ae  mov     ecx, r12d; uFlags
0x1800115b1  and     eax, 0FFFFFFFEh
0x1800115b4  mov     [rbp+57h+var_70], rax
0x1800115b8  lea     rdx, [rax+2]; uBytes
0x1800115bc  call    cs:__imp_LocalAlloc
0x1800115c2  xor     ecx, ecx
0x1800115c4  mov     r14, rax
0x1800115c7  test    rax, rax
0x1800115ca  jz      loc_180011493
0x1800115d0  mov     word ptr [rax], 18h
0x1800115d5  mov     eax, [rdi+24h]
0x1800115d8  mov     [r14+4], eax
0x1800115dc  cmp     [rdi+14h], ecx
0x1800115df  jnz     short loc_1800115E9
0x1800115e1  bts     eax, 12h
0x1800115e5  mov     [r14+4], eax
0x1800115e9  cmp     [rdi+0Ch], ecx
0x1800115ec  jnz     short loc_1800115F6
0x1800115ee  bts     eax, 11h
0x1800115f2  mov     [r14+4], eax
0x1800115f6  lea     rbx, [r14+18h]
0x1800115fa  mov     eax, ebx
0x1800115fc  mov     rcx, rbx; void *
0x1800115ff  sub     eax, r14d
0x180011602  mov     [r14+8], eax
0x180011606  movzx   eax, word ptr [rdi+20h]
0x18001160a  mov     [r14+0Ch], ax
0x18001160f  mov     edx, [rdi+1Ch]
0x180011612  movzx   r8d, word ptr [rdi+20h]; Size
0x180011617  add     rdx, rdi; Src
0x18001161a  call    memcpy_0
0x18001161f  movzx   ecx, word ptr [rdi+20h]
0x180011623  add     rcx, rbx; void *
0x180011626  mov     eax, ecx
0x180011628  sub     eax, r14d
0x18001162b  mov     [r14+10h], eax
0x18001162f  movzx   eax, word ptr [rdi+2Ch]
0x180011633  shr     ax, 1
0x180011636  mov     [r14+14h], ax
0x18001163b  mov     edx, [rdi+28h]
0x18001163e  movzx   r8d, word ptr [rdi+2Ch]; Size
0x180011643  add     rdx, rdi; Src
0x180011646  call    memcpy_0
0x18001164b  mov     rax, [rbp+57h+var_70]
0x18001164f  xor     ebx, ebx
0x180011651  mov     dword ptr [rbp+57h+var_A8], eax
0x180011654  mov     rax, r14
0x180011657  sar     rax, 20h
0x18001165b  mov     [rbp+57h+var_A0], r14d
0x18001165f  mov     [rbp+57h+var_9C], eax
0x180011662  test    r13, r13
0x180011665  jz      short loc_180011673
0x180011667  mov     rcx, r13; DataBuffer
0x18001166a  call    SspiLocalFree
0x18001166f  mov     [rbp+57h+Src], rbx
0x180011673  lea     r8, [rbp+57h+Src]; unsigned __int16 **
0x180011677  mov     ecx, 3; enum _CRED_MARSHAL_TYPE
0x18001167c  lea     rdx, [rbp+57h+var_A8]; void *
0x180011680  call    ?LocalCredMarshalCredentialW@@YAKW4_CRED_MARSHAL_TYPE@@PEAXPEAPEAG@Z; LocalCredMarshalCredentialW(_CRED_MARSHAL_TYPE,void *,ushort * *)
0x180011685  mov     r13, [rbp+57h+Src]
0x180011689  test    eax, eax
0x18001168b  jnz     loc_180011539
0x180011691  inc     rsi
0x180011694  cmp     [r13+rsi*2+0], bx
0x18001169a  jnz     short loc_180011691
0x18001169c  cmp     esi, 8
0x18001169f  jbe     short loc_1800116E8
0x1800116a1  add     esi, 0FFFFFFF8h
0x1800116a4  mov     ecx, r12d; uFlags
0x1800116a7  lea     edx, ds:2[rsi*2]
0x1800116ae  add     rdx, 2; uBytes
0x1800116b2  call    cs:__imp_LocalAlloc
0x1800116b8  mov     r12, [rbp+57h+arg_18]
0x1800116bc  mov     [r12], rax
0x1800116c0  test    rax, rax
0x1800116c3  jnz     short loc_1800116CF
0x1800116c5  mov     ebx, 0C0000017h
0x1800116ca  jmp     loc_180011860
0x1800116cf  mov     r8d, esi
0x1800116d2  lea     rdx, [r13+10h]; Src
0x1800116d6  add     r8, r8; Size
0x1800116d9  mov     rcx, rax; void *
0x1800116dc  call    memcpy_0
0x1800116e1  xor     esi, esi
0x1800116e3  jmp     loc_180011D7A
0x1800116e8  mov     ebx, 0C00000BBh
0x1800116ed  jmp     loc_18001185C
0x1800116f2  mov     r12d, 40h ; '@'
0x1800116f8  cmp     [rdi+0Ch], esi
0x1800116fb  jz      short loc_180011730
0x1800116fd  lea     edx, [rcx+2]
0x180011700  mov     ecx, r12d; uFlags
0x180011703  add     rdx, 2; uBytes
0x180011707  call    cs:__imp_LocalAlloc
0x18001170d  mov     rdx, [rbp+57h+arg_8]
0x180011711  mov     [rdx], rax
0x180011714  test    rax, rax
0x180011717  jz      loc_180011493
0x18001171d  mov     edx, [rdi+0Ch]
0x180011720  mov     rcx, rax; void *
0x180011723  movzx   r8d, word ptr [rdi+10h]; Size
0x180011728  add     rdx, rdi; Src
0x18001172b  call    memcpy_0
0x180011730  cmp     [rdi+14h], esi
0x180011733  jz      loc_180011D7A
0x180011739  movzx   edx, word ptr [rdi+18h]
0x18001173d  mov     ecx, r12d; uFlags
0x180011740  add     rdx, 4; uBytes
0x180011744  call    cs:__imp_LocalAlloc
0x18001174a  mov     [r15], rax
0x18001174d  test    rax, rax
0x180011750  jz      loc_180011493
0x180011756  mov     edx, [rdi+14h]
0x180011759  mov     rcx, rax; void *
0x18001175c  movzx   r8d, word ptr [rdi+18h]; Size
0x180011761  add     rdx, rdi; Src
0x180011764  call    memcpy_0
0x180011769  jmp     loc_180011D7A
0x18001176e  cmp     dword ptr [rcx], 200h
0x180011774  jnz     short loc_18001178B
0x180011776  lea     r14, [rcx+8]
0x18001177a  xor     ecx, ecx
0x18001177c  test    r9, r9
0x18001177f  jz      short loc_180011790
0x180011781  cmp     [rdi+40h], ecx
0x180011784  jz      short loc_180011790
0x180011786  lea     esi, [rcx+1]
0x180011789  jmp     short loc_180011790
0x18001178b  mov     r14, rdi
0x18001178e  xor     ecx, ecx
0x180011790  test    byte ptr [r14+2Ch], 10h
0x180011795  jz      short loc_1800117A5
0x180011797  mov     r14, [rbp+57h+var_A8]
0x18001179b  mov     ebx, 0C000000Dh
0x1800117a0  jmp     loc_180011860
0x1800117a5  test    byte ptr [r14+2Ch], 1
0x1800117aa  mov     r12d, 40h ; '@'
0x1800117b0  jz      loc_1800118B2
0x1800117b6  cmp     [r14], rcx
0x1800117b9  jz      short loc_1800117D4
0x1800117bb  mov     edx, [r14+8]; unsigned int
0x1800117bf  mov     r8, rbx; unsigned __int16 **
0x1800117c2  mov     rcx, [r14]; unsigned __int8 *
0x1800117c5  call    ?SspiHelperConvertAnsiStringToUnicodeString@@YAJPEAEKPEAPEBG@Z; SspiHelperConvertAnsiStringToUnicodeString(uchar *,ulong,ushort const * *)
0x1800117ca  mov     ebx, eax
0x1800117cc  test    eax, eax
0x1800117ce  js      loc_180011858
0x1800117d4  mov     rcx, [r14+10h]; unsigned __int8 *
0x1800117d8  xor     ebx, ebx
0x1800117da  test    rcx, rcx
0x1800117dd  jz      short loc_1800117F3
0x1800117df  mov     edx, [r14+18h]; unsigned int
0x1800117e3  mov     r8, r15; unsigned __int16 **
0x1800117e6  call    ?SspiHelperConvertAnsiStringToUnicodeString@@YAJPEAEKPEAPEBG@Z; SspiHelperConvertAnsiStringToUnicodeString(uchar *,ulong,ushort const * *)
0x1800117eb  mov     ebx, eax
  ... truncated ...
```
