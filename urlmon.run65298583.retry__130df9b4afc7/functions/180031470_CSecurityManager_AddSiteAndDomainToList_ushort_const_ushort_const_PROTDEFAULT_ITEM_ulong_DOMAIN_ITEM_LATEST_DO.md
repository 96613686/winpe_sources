# CSecurityManager::AddSiteAndDomainToList(ushort const *,ushort const *,PROTDEFAULT_ITEM *,ulong,DOMAIN_ITEM_LATEST * *,DOMAIN_ITEM_LATEST * *,DOMAIN_ITEM_LATEST * *)

- ea: `0x180031470`
- end: `0x180031e20`
- name: `?AddSiteAndDomainToList@CSecurityManager@@IEAAJPEBG0PEAUPROTDEFAULT_ITEM@@KPEAPEAUDOMAIN_ITEM_LATEST@@22@Z`
- size: `2480`
- prototype: `__int64 __fastcall(CSecurityManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct PROTDEFAULT_ITEM *, unsigned int, struct DOMAIN_ITEM_LATEST **, struct DOMAIN_ITEM_LATEST **, struct DOMAIN_ITEM_LATEST **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031048`
- `0x18003125c`

## callees

- `0x180031470`
- `0x18011ba3e`
- `0x18011baa0`

## import_xrefs

- `iertutil!IUriBuilderInternalCreateDomain` at `0x1800318b7`
- `iertutil!IUriBuilderInternalCreateDomain` at `0x1800318b7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800316e2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003174f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800317a4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031802`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031b80`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800316e2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003174f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800317a4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031802`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031b80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031823`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800318f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031a52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031cb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031823`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800318f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031a52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180031cb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003196b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031979`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003196b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031979`

## pseudocode

```c
__int64 __fastcall CSecurityManager::AddSiteAndDomainToList(
        CSecurityManager *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct PROTDEFAULT_ITEM *a4,
        unsigned int a5,
        struct DOMAIN_ITEM_LATEST **a6,
        struct DOMAIN_ITEM_LATEST **a7,
        struct DOMAIN_ITEM_LATEST **a8)
{
  _WORD *v8; // r13
  const unsigned __int16 *v10; // r15
  __int64 v11; // rdx
  __int64 v12; // r12
  unsigned __int16 *v13; // r8
  unsigned __int64 v14; // rbx
  int Domain; // r14d
  __int64 v16; // rcx
  const wchar_t *v17; // rdx
  unsigned __int64 v18; // r9
  unsigned __int16 *v19; // r10
  __int64 v20; // r11
  unsigned __int16 *v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rdx
  int v24; // r9d
  unsigned __int16 *v25; // rcx
  int v26; // eax
  unsigned int v27; // edi
  int v28; // eax
  unsigned int v29; // edi
  struct DOMAIN_ITEM_LATEST **v30; // rdx
  int v31; // esi
  int v32; // r12d
  int v33; // r15d
  struct DOMAIN_ITEM_LATEST *v34; // rbx
  struct DOMAIN_ITEM_LATEST **v35; // r10
  const WCHAR *v36; // r8
  int v37; // eax
  int v38; // eax
  struct DOMAIN_ITEM_LATEST **v39; // rdx
  struct DOMAIN_ITEM_LATEST *v40; // rdi
  const WCHAR *v41; // r8
  int v42; // eax
  const WCHAR *v43; // r8
  int v44; // ecx
  const WCHAR *v45; // r8
  int v46; // ecx
  _OWORD *v47; // rax
  struct DOMAIN_ITEM_LATEST **v48; // rcx
  __int64 v49; // rcx
  _OWORD *v50; // rax
  __int64 v52; // rax
  __int64 v53; // r9
  unsigned __int16 *v54; // r8
  __int64 v55; // r10
  unsigned __int16 *v56; // rcx
  __int64 v57; // rdx
  unsigned __int64 v58; // rbx
  SIZE_T v59; // rdi
  _WORD *v60; // rax
  __int64 v61; // rcx
  unsigned __int16 *v62; // rdx
  _WORD *v63; // r8
  _WORD *v64; // rcx
  unsigned int v65; // r14d
  const WCHAR *v66; // rdi
  int i; // ebx
  const WCHAR *v68; // rcx
  struct DOMAIN_ITEM_LATEST **v69; // r8
  unsigned __int64 v70; // rdi
  SIZE_T v71; // r15
  WCHAR *v72; // rax
  WCHAR *v73; // rbx
  __int64 v74; // rcx
  const WCHAR *v75; // rdx
  bool v76; // zf
  WCHAR *v77; // rcx
  __int64 v78; // rax
  unsigned int v79; // ecx
  PCNZWCH lpString2; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v81; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v82; // [rsp+58h] [rbp-B0h]
  __int64 v83; // [rsp+60h] [rbp-A8h]
  struct DOMAIN_ITEM_LATEST **v84; // [rsp+68h] [rbp-A0h]
  struct DOMAIN_ITEM_LATEST **v85; // [rsp+70h] [rbp-98h]
  struct PROTDEFAULT_ITEM *v86; // [rsp+78h] [rbp-90h]
  struct DOMAIN_ITEM_LATEST **v87; // [rsp+80h] [rbp-88h]
  unsigned __int16 v88[264]; // [rsp+88h] [rbp-80h] BYREF

  v8 = 0;
  v10 = a3;
  v85 = a6;
  v11 = -1;
  v87 = a8;
  v86 = a4;
  v84 = a7;
  lpString2 = 0;
  LODWORD(v81) = 0;
  do
    ++v11;
  while ( a2[v11] );
  v83 = v11;
  if ( a3 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
LABEL_6:
    v13 = v88;
    v14 = 260;
    Domain = 0;
    if ( v10 && (_DWORD)v12 )
    {
      v52 = (unsigned int)v12;
      if ( (unsigned int)v12 >= 0x7FFFFFFFuLL )
      {
        v28 = 0;
        v88[0] = 0;
        LODWORD(v81) = 0;
        Domain = -2147024809;
        lpString2 = 0;
        v27 = 0;
        goto LABEL_32;
      }
      v53 = 260;
      v54 = v88;
      v55 = 0;
      do
      {
        if ( !v52 )
          break;
        if ( !*v10 )
          break;
        *v54++ = *v10++;
        --v52;
        ++v55;
        --v53;
      }
      while ( v53 );
      v56 = v54 - 1;
      v57 = v55 - 1;
      Domain = -2147024774;
      if ( v53 )
      {
        v56 = v54;
        v57 = v55;
        Domain = 0;
      }
      v14 = 260 - v57;
      *v56 = 0;
      v13 = &v88[v57];
      if ( Domain < 0 )
        goto LABEL_30;
      LODWORD(v11) = v83;
    }
    if ( !a2 || !(_DWORD)v11 )
      goto LABEL_30;
    if ( (_DWORD)v12 )
    {
      if ( v14 )
      {
        if ( v14 > 0x7FFFFFFF )
        {
          Domain = -2147024809;
          *v13 = 0;
        }
        else
        {
          v16 = 1;
          v17 = L".";
          v18 = v14;
          v19 = v13;
          v20 = 0;
          do
          {
            if ( !v16 )
              break;
            if ( !*v17 )
              break;
            *v19++ = *v17++;
            --v16;
            ++v20;
            --v18;
          }
          while ( v18 );
          v11 = v20 - 1;
          v21 = v19 - 1;
          Domain = -2147024774;
          if ( v18 )
          {
            v11 = v20;
            v21 = v19;
            Domain = 0;
          }
          v14 -= v11;
          v13 += v11;
          *v21 = 0;
          LODWORD(v11) = v83;
        }
      }
      else
      {
        Domain = -2147024809;
      }
    }
    if ( Domain < 0 )
      goto LABEL_30;
    if ( v14 )
    {
      if ( v14 > 0x7FFFFFFF )
      {
        Domain = -2147024809;
      }
      else
      {
        v22 = (unsigned int)v11;
        if ( (unsigned int)v11 < 0x7FFFFFFFuLL )
        {
          v23 = v14;
          v24 = 0;
          do
          {
            if ( !v22 )
              break;
            if ( !*a2 )
              break;
            *v13++ = *a2++;
            --v22;
            ++v24;
            --v23;
          }
          while ( v23 );
          v25 = v13 - 1;
          v26 = v24 - 1;
          Domain = -2147024774;
          if ( v23 )
          {
            v25 = v13;
            v26 = v24;
            Domain = 0;
          }
          *v25 = 0;
          LODWORD(v14) = v14 - v26;
          goto LABEL_30;
        }
        Domain = -2147024809;
      }
      *v13 = 0;
    }
    else
    {
      Domain = -2147024809;
    }
LABEL_30:
    v27 = 260 - v14;
    lpString2 = 0;
    v28 = 0;
    LODWORD(v81) = 0;
    if ( Domain >= 0 )
    {
      Domain = IUriBuilderInternalCreateDomain(
                 0,
                 Uri_HOST_DNS,
                 v88,
                 v27,
                 0,
                 (unsigned __int16 **)&lpString2,
                 (unsigned int *)&v81);
      v28 = v81;
    }
LABEL_32:
    v29 = v27 - v28;
    v82 = v29;
    if ( !v29 )
      goto LABEL_33;
    if ( v28 )
      v82 = --v29;
    v58 = v29 + 1;
    v59 = saturated_mul(v58, 2u);
    v60 = CoTaskMemAlloc(v59);
    v8 = v60;
    if ( !v60 )
      goto LABEL_126;
    memset_0(v60, 0, v59);
    if ( Domain >= 0 )
    {
      if ( v58 )
      {
        if ( v58 <= 0x7FFFFFFF )
        {
          v29 = v82;
          if ( (unsigned int)v82 > 0x7FFFFFFE )
          {
            Domain = -2147024809;
            *v8 = 0;
          }
          else
          {
            v61 = (unsigned int)v82;
            v62 = v88;
            v63 = v8;
            do
            {
              if ( !v61 )
                break;
              if ( !*v62 )
                break;
              *v63++ = *v62++;
              --v61;
              --v58;
            }
            while ( v58 );
            v64 = v63 - 1;
            Domain = -2147024774;
            if ( v58 )
            {
              v64 = v63;
              Domain = 0;
            }
            *v64 = 0;
          }
LABEL_33:
          if ( Domain < 0 )
            goto LABEL_73;
          goto LABEL_34;
        }
        Domain = -2147024809;
        *v8 = 0;
      }
      else
      {
        Domain = -2147024809;
      }
    }
    v29 = v82;
    goto LABEL_33;
  }
  v65 = 0;
  LODWORD(v12) = 0;
LABEL_105:
  if ( v65 >= a5 )
  {
    LODWORD(v11) = v83;
    v8 = 0;
    goto LABEL_6;
  }
  v66 = (const WCHAR *)((char *)a4 + 68 * v65 + 4);
  for ( i = 0; ; ++i )
  {
    v68 = (const WCHAR *)*(&off_1801202A0 + i);
    if ( !v68 )
      break;
    if ( v66 && CompareStringW(0x7Fu, 0x1001u, v66, -1, v68, -1) == 2 )
    {
      a4 = v86;
      ++v65;
      goto LABEL_105;
    }
  }
  v29 = 0;
  Domain = 0;
  v82 = 0;
  v8 = 0;
  LODWORD(v81) = v83;
  v73 = 0;
  if ( a2 )
  {
    v78 = -1;
    do
      ++v78;
    while ( a2[v78] );
    v79 = v78 + 1;
    if ( (int)v78 + 1 < (unsigned int)v78
      || (v70 = v79, v71 = saturated_mul(v79, 2u), v72 = (WCHAR *)CoTaskMemAlloc(v71), (v73 = v72) == 0) )
    {
      lpString2 = v73;
      goto LABEL_126;
    }
    memset_0(v72, 0, v71);
    if ( v70 )
    {
      if ( v70 > 0x7FFFFFFF )
      {
        v29 = v82;
        *v73 = 0;
        lpString2 = v73;
      }
      else
      {
        v74 = 2147483646;
        v75 = v73;
        do
        {
          if ( !v74 )
            break;
          if ( !*a2 )
            break;
          *v73++ = *a2++;
          --v74;
          --v70;
        }
        while ( v70 );
        v76 = v70 == 0;
        v77 = v73 - 1;
        v29 = v82;
        if ( !v76 )
          v77 = v73;
        *v77 = 0;
        lpString2 = v75;
      }
      goto LABEL_34;
    }
    v29 = v82;
  }
  lpString2 = v73;
  if ( !v73 )
    goto LABEL_126;
LABEL_34:
  v30 = v85;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = *v85;
  if ( !*v85 )
    goto LABEL_58;
  v35 = v84;
  v36 = (const WCHAR *)*((_QWORD *)*v84 + 3);
  if ( v36 )
  {
    if ( !lpString2 )
      goto LABEL_40;
    v37 = CompareStringW(0x7Fu, 0x1001u, v36, -1, lpString2, -1);
    v30 = v85;
    v35 = v84;
  }
  else
  {
    v37 = (lpString2 == 0) + 1;
  }
  v38 = v37 - 2;
  if ( !v38 )
  {
    v34 = *v35;
    goto LABEL_68;
  }
  if ( v38 < 0 )
  {
    v32 = 1;
    goto LABEL_58;
  }
LABEL_40:
  if ( !lpString2 )
  {
    v49 = *((_QWORD *)*v30 + 3);
    if ( !v49 )
      v34 = *v30;
    LOBYTE(v31) = v49 != 0;
    if ( !v49 )
    {
LABEL_68:
      if ( !v34 )
        goto LABEL_73;
      goto LABEL_69;
    }
LABEL_58:
    v47 = CoTaskMemAlloc(0x28u);
    if ( v47 )
    {
      *v47 = 0;
      v47[1] = 0;
      *((_QWORD *)v47 + 4) = 0;
      *((_QWORD *)v47 + 3) = lpString2;
      v48 = v85;
      lpString2 = 0;
      if ( *v85 )
      {
        if ( v32 )
        {
          v69 = v84;
          v34 = (struct DOMAIN_ITEM_LATEST *)v47;
          v29 = v82;
          *((_QWORD *)*v84 + 4) = v47;
          *v69 = (struct DOMAIN_ITEM_LATEST *)v47;
        }
        else if ( v31 )
        {
          v29 = v82;
          v34 = (struct DOMAIN_ITEM_LATEST *)v47;
          *((_QWORD *)v47 + 4) = *v85;
          *v48 = (struct DOMAIN_ITEM_LATEST *)v47;
        }
        else
        {
          if ( v33 )
          {
            *((_QWORD *)v47 + 4) = *((_QWORD *)v34 + 4);
            *((_QWORD *)v34 + 4) = v47;
          }
          v29 = v82;
          v34 = (struct DOMAIN_ITEM_LATEST *)v47;
        }
      }
      else
      {
        v34 = (struct DOMAIN_ITEM_LATEST *)v47;
        v29 = v82;
        *v84 = (struct DOMAIN_ITEM_LATEST *)v47;
        *v48 = (struct DOMAIN_ITEM_LATEST *)v47;
      }
      goto LABEL_69;
    }
LABEL_126:
    Domain = -2147024882;
    goto LABEL_73;
  }
  v39 = v87;
  v40 = 0;
  if ( *v87 )
  {
    v41 = (const WCHAR *)*((_QWORD *)*v87 + 3);
    if ( v41 )
    {
      v42 = CompareStringW(0x7Fu, 0x1001u, v41, -1, lpString2, -1);
      v39 = v87;
    }
    else
    {
      v42 = (lpString2 == 0) + 1;
    }
    if ( v42 - 2 <= 0 )
    {
      v34 = *v39;
      if ( !*v39 )
      {
LABEL_51:
        v32 = 1;
        goto LABEL_58;
      }
    }
  }
  while ( 1 )
  {
    v43 = (const WCHAR *)*((_QWORD *)v34 + 3);
    if ( v43 )
    {
      if ( !lpString2 )
        break;
      v44 = CompareStringW(0x7Fu, 0x1001u, v43, -1, lpString2, -1);
    }
    else
    {
      v44 = (lpString2 == 0) + 1;
    }
    if ( v44 - 2 > 0 )
      break;
    v40 = v34;
    v34 = (struct DOMAIN_ITEM_LATEST *)*((_QWORD *)v34 + 4);
    if ( !v34 )
      goto LABEL_51;
  }
  if ( !v40 )
  {
    v31 = 1;
    goto LABEL_58;
  }
  v45 = (const WCHAR *)*((_QWORD *)v40 + 3);
  if ( v45 )
  {
    if ( !lpString2 )
    {
LABEL_57:
      v33 = 1;
      v34 = v40;
      goto LABEL_58;
    }
    v46 = CompareStringW(0x7Fu, 0x1001u, v45, -1, lpString2, -1);
  }
  else
  {
    v46 = (lpString2 == 0) + 1;
  }
  if ( v46 != 2 )
    goto LABEL_57;
  v34 = v40;
  v29 = v82;
LABEL_69:
  if ( v29 )
  {
    ++*((_DWORD *)v34 + 4);
    v50 = CoTaskMemAlloc(0x20u);
    if ( v50 )
    {
      *v50 = 0;
      v50[1] = 0;
      *((_QWORD *)v50 + 3) = *(_QWORD *)v34;
      *(_QWORD *)v50 = v86;
      *((_QWORD *)v50 + 2) = v8;
      v8 = 0;
      *((_DWORD *)v50 + 2) = a5;
      *(_QWORD *)v34 = v50;
    }
    else
    {
      Domain = -2147024882;
    }
  }
  else
  {
    *((_QWORD *)v34 + 1) = v86;
    *((_DWORD *)v34 + 5) = a5;
  }
  *v87 = v34;
LABEL_73:
  if ( lpString2 )
    CoTaskMemFree((LPVOID)lpString2);
  if ( v8 )
    CoTaskMemFree(v8);
  return (unsigned int)Domain;
}

```

## disassembly

```asm
0x180031470  mov     r11, rsp
0x180031473  push    rbp
0x180031474  push    r13
0x180031476  lea     rbp, [r11-1D8h]
0x18003147d  sub     rsp, 2C8h
0x180031484  mov     rax, cs:__security_cookie
0x18003148b  xor     rax, rsp
0x18003148e  mov     [rbp+1D0h+var_40], rax
0x180031495  mov     rax, [rbp+1D0h+arg_28]
0x18003149c  xor     r13d, r13d
0x18003149f  mov     r10, [rbp+1D0h+arg_30]
0x1800314a6  mov     [r11-18h], rsi
0x1800314aa  mov     rsi, rdx
0x1800314ad  mov     [r11-38h], r15
0x1800314b1  mov     r15, r8
0x1800314b4  mov     [rsp+2D0h+var_268], rax
0x1800314b9  mov     r11, 0FFFFFFFFFFFFFFFFh
0x1800314c0  mov     rax, [rbp+1D0h+arg_38]
0x1800314c7  mov     rdx, r11
0x1800314ca  mov     [rsp+2D0h+var_258], rax
0x1800314cf  mov     [rsp+2D0h+var_260], r9
0x1800314d4  mov     [rsp+2D0h+var_270], r10
0x1800314d9  mov     [rsp+2D0h+var_290], r13
0x1800314de  mov     dword ptr [rsp+2D0h+var_288], r13d
0x1800314e3  inc     rdx
0x1800314e6  cmp     [rsi+rdx*2], r13w
0x1800314eb  jnz     short loc_1800314E3
0x1800314ed  mov     [rsp+2D0h+arg_0], rbx
0x1800314f5  mov     [rsp+2D0h+var_18], rdi
0x1800314fd  mov     [rsp+2D0h+var_20], r12
0x180031505  mov     [rsp+2D0h+var_28], r14
0x18003150d  mov     [rsp+2D0h+var_278], rdx
0x180031512  test    r15, r15
0x180031515  jz      loc_180031B18
0x18003151b  mov     r12, r11
0x18003151e  xchg    ax, ax
0x180031520  inc     r12
0x180031523  cmp     [r8+r12*2], r13w
0x180031528  jnz     short loc_180031520
0x18003152a  lea     r8, [rbp+1D0h+var_250]
0x18003152e  mov     edi, 104h
0x180031533  mov     ebx, edi
0x180031535  mov     r14d, r13d
0x180031538  test    r15, r15
0x18003153b  jnz     loc_1800319A4
0x180031541  test    rsi, rsi
0x180031544  jz      loc_18003165F
0x18003154a  test    edx, edx
0x18003154c  jz      loc_18003165F
0x180031552  test    r12d, r12d
0x180031555  jz      short loc_1800315D4
0x180031557  test    rbx, rbx
0x18003155a  jz      loc_180031DC5
0x180031560  cmp     rbx, 7FFFFFFFh
0x180031567  ja      loc_180031DBD
0x18003156d  mov     ecx, 1
0x180031572  lea     rdx, asc_18012DC5C; "."
0x180031579  mov     r9, rbx
0x18003157c  mov     r10, r8
0x18003157f  mov     r11, r13
0x180031582  test    rcx, rcx
0x180031585  jz      short loc_1800315A7
0x180031587  movzx   eax, word ptr [rdx]
0x18003158a  test    ax, ax
0x18003158d  jz      short loc_1800315A7
0x18003158f  mov     [r10], ax
0x180031593  add     rdx, 2
0x180031597  add     r10, 2
0x18003159b  dec     rcx
0x18003159e  inc     r11
0x1800315a1  sub     r9, 1
0x1800315a5  jnz     short loc_180031582
0x1800315a7  test    r9, r9
0x1800315aa  lea     rdx, [r11-1]
0x1800315ae  lea     rcx, [r10-2]
0x1800315b2  mov     r14d, 8007007Ah
0x1800315b8  cmovnz  rdx, r11
0x1800315bc  cmovnz  rcx, r10
0x1800315c0  cmovnz  r14d, r13d
0x1800315c4  sub     rbx, rdx
0x1800315c7  lea     r8, [r8+rdx*2]
0x1800315cb  mov     [rcx], r13w
0x1800315cf  mov     rdx, [rsp+2D0h+var_278]
0x1800315d4  test    r14d, r14d
0x1800315d7  js      loc_18003165F
0x1800315dd  test    rbx, rbx
0x1800315e0  jz      loc_180031DE8
0x1800315e6  cmp     rbx, 7FFFFFFFh
0x1800315ed  ja      loc_180031DDD
0x1800315f3  mov     eax, edx
0x1800315f5  cmp     rax, 7FFFFFFFh
0x1800315fb  jnb     loc_180031C2D
0x180031601  mov     rdx, rbx
0x180031604  mov     r9, r13
0x180031607  test    rax, rax
0x18003160a  jz      short loc_18003162C
0x18003160c  movzx   ecx, word ptr [rsi]
0x18003160f  test    cx, cx
0x180031612  jz      short loc_18003162C
0x180031614  mov     [r8], cx
0x180031618  add     rsi, 2
0x18003161c  add     r8, 2
0x180031620  dec     rax
0x180031623  inc     r9
0x180031626  sub     rdx, 1
0x18003162a  jnz     short loc_180031607
0x18003162c  test    rdx, rdx
0x18003162f  lea     rcx, [r8-2]
0x180031633  lea     rax, [r9-1]
0x180031637  mov     r14d, 8007007Ah
0x18003163d  cmovnz  rcx, r8
0x180031641  cmovnz  rax, r9
0x180031645  cmovnz  r14d, r13d
0x180031649  mov     [rcx], r13w
0x18003164d  mov     rcx, rbx
0x180031650  sub     rcx, rax
0x180031653  test    r14d, r14d
0x180031656  js      loc_180031D69
0x18003165c  mov     rbx, rcx
0x18003165f  sub     edi, ebx
0x180031661  mov     [rsp+2D0h+var_290], r13
0x180031666  mov     eax, r13d
0x180031669  mov     dword ptr [rsp+2D0h+var_288], eax
0x18003166d  test    r14d, r14d
0x180031670  jns     loc_180031890
0x180031676  sub     edi, eax
0x180031678  mov     [rsp+2D0h+var_280], rdi
0x18003167d  jnz     loc_180031A2B
0x180031683  test    r14d, r14d
0x180031686  js      loc_180031939
0x18003168c  mov     r11, 0FFFFFFFFFFFFFFFFh
0x180031693  mov     rdx, [rsp+2D0h+var_268]
0x180031698  xor     esi, esi
0x18003169a  xor     r12d, r12d
0x18003169d  xor     r15d, r15d
0x1800316a0  mov     rbx, [rdx]
0x1800316a3  test    rbx, rbx
0x1800316a6  jz      loc_18003181E
0x1800316ac  mov     r10, [rsp+2D0h+var_270]
0x1800316b1  mov     rcx, [rsp+2D0h+var_290]
0x1800316b6  mov     rax, [r10]
0x1800316b9  mov     r8, [rax+18h]; lpString1
0x1800316bd  test    r8, r8
0x1800316c0  jz      loc_180031C00
0x1800316c6  test    rcx, rcx
0x1800316c9  jz      short loc_180031703
0x1800316cb  mov     [rsp+2D0h+cchCount2], r11d; cchCount2
0x1800316d0  mov     r9d, r11d; cchCount1
0x1800316d3  mov     [rsp+2D0h+lpString2], rcx; lpString2
0x1800316d8  mov     edx, 1001h; dwCmpFlags
0x1800316dd  mov     ecx, 7Fh; Locale
0x1800316e2  call    cs:__imp_CompareStringW
0x1800316e8  mov     rdx, [rsp+2D0h+var_268]
0x1800316ed  mov     r10, [rsp+2D0h+var_270]
0x1800316f2  add     eax, 0FFFFFFFEh
0x1800316f5  jz      loc_180031BAA
0x1800316fb  test    eax, eax
0x1800316fd  js      loc_180031BDD
0x180031703  cmp     [rsp+2D0h+var_290], rsi
0x180031708  jz      loc_1800318C9
0x18003170e  mov     rdx, [rsp+2D0h+var_258]
0x180031713  xor     edi, edi
0x180031715  mov     rax, [rdx]
0x180031718  test    rax, rax
0x18003171b  jz      short loc_180031770
0x18003171d  mov     r8, [rax+18h]; lpString1
0x180031721  mov     rcx, [rsp+2D0h+var_290]
0x180031726  test    r8, r8
0x180031729  jz      loc_180031C0F
0x18003172f  test    rcx, rcx
0x180031732  jz      short loc_180031770
0x180031734  mov     r9, 0FFFFFFFFFFFFFFFFh; cchCount1
0x18003173b  mov     edx, 1001h; dwCmpFlags
0x180031740  mov     [rsp+2D0h+cchCount2], r9d; cchCount2
0x180031745  mov     [rsp+2D0h+lpString2], rcx; lpString2
0x18003174a  mov     ecx, 7Fh; Locale
0x18003174f  call    cs:__imp_CompareStringW
0x180031755  mov     rdx, [rsp+2D0h+var_258]
0x18003175a  add     eax, 0FFFFFFFEh
0x18003175d  test    eax, eax
0x18003175f  jg      short loc_180031770
0x180031761  mov     rbx, [rdx]
0x180031764  test    rbx, rbx
0x180031767  jz      short loc_1800317BF
0x180031769  nop     dword ptr [rax+00000000h]
0x180031770  mov     r8, [rbx+18h]; lpString1
0x180031774  mov     rax, [rsp+2D0h+var_290]
0x180031779  test    r8, r8
0x18003177c  jz      loc_180031BB2
0x180031782  test    rax, rax
0x180031785  jz      short loc_1800317C7
0x180031787  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003178e  mov     edx, 1001h; dwCmpFlags
0x180031793  mov     [rsp+2D0h+cchCount2], ecx; cchCount2
0x180031797  mov     r9d, ecx; cchCount1
0x18003179a  mov     ecx, 7Fh; Locale
0x18003179f  mov     [rsp+2D0h+lpString2], rax; lpString2
0x1800317a4  call    cs:__imp_CompareStringW
0x1800317aa  mov     ecx, eax
0x1800317ac  lea     eax, [rcx-2]
0x1800317af  test    eax, eax
0x1800317b1  jg      short loc_1800317C7
0x1800317b3  mov     rdi, rbx
0x1800317b6  mov     rbx, [rbx+20h]
0x1800317ba  test    rbx, rbx
0x1800317bd  jnz     short loc_180031770
0x1800317bf  mov     r12d, 1
0x1800317c5  jmp     short loc_18003181E
0x1800317c7  test    rdi, rdi
0x1800317ca  jz      loc_180031BA0
0x1800317d0  mov     r8, [rdi+18h]; lpString1
0x1800317d4  mov     rax, [rsp+2D0h+var_290]
0x1800317d9  test    r8, r8
0x1800317dc  jz      loc_180031C1E
0x1800317e2  test    rax, rax
0x1800317e5  jz      short loc_180031815
0x1800317e7  mov     r9, 0FFFFFFFFFFFFFFFFh; cchCount1
0x1800317ee  mov     edx, 1001h; dwCmpFlags
0x1800317f3  mov     [rsp+2D0h+cchCount2], r9d; cchCount2
0x1800317f8  mov     ecx, 7Fh; Locale
0x1800317fd  mov     [rsp+2D0h+lpString2], rax; lpString2
0x180031802  call    cs:__imp_CompareStringW
0x180031808  mov     ecx, eax
0x18003180a  lea     eax, [rcx-2]
0x18003180d  test    eax, eax
0x18003180f  jz      loc_180031B0B
0x180031815  mov     r15d, 1
0x18003181b  mov     rbx, rdi
0x18003181e  mov     ecx, 28h ; '('; cb
0x180031823  call    cs:__imp_CoTaskMemAlloc
0x180031829  mov     rdx, rax
0x18003182c  test    rax, rax
0x18003182f  jz      loc_180031C74
0x180031835  xor     eax, eax
0x180031837  xorps   xmm0, xmm0
0x18003183a  movups  xmmword ptr [rdx], xmm0
0x18003183d  movups  xmmword ptr [rdx+10h], xmm0
0x180031841  mov     [rdx+20h], rax
0x180031845  mov     rcx, [rsp+2D0h+var_290]
0x18003184a  mov     [rdx+18h], rcx
0x18003184e  mov     rcx, [rsp+2D0h+var_268]
0x180031853  mov     [rsp+2D0h+var_290], rax
0x180031858  mov     rax, [rcx]
0x18003185b  test    rax, rax
0x18003185e  jz      loc_180031BE8
0x180031864  test    r12d, r12d
0x180031867  jnz     loc_180031BC1
0x18003186d  test    esi, esi
0x18003186f  jnz     loc_180031C3C
0x180031875  test    r15d, r15d
0x180031878  jz      short loc_180031886
0x18003187a  mov     rax, [rbx+20h]
0x18003187e  mov     [rdx+20h], rax
0x180031882  mov     [rbx+20h], rdx
0x180031886  mov     rdi, [rsp+2D0h+var_280]
0x18003188b  mov     rbx, rdx
0x18003188e  jmp     short loc_1800318E6
0x180031890  lea     rax, [rsp+2D0h+var_288]
0x180031895  mov     r9d, edi
0x180031898  mov     [rsp+30h], rax
0x18003189d  lea     r8, [rbp+1D0h+var_250]
0x1800318a1  lea     rax, [rsp+2D0h+var_290]
0x1800318a6  mov     edx, 1
0x1800318ab  mov     qword ptr [rsp+2D0h+cchCount2], rax
0x1800318b0  xor     ecx, ecx
0x1800318b2  mov     dword ptr [rsp+2D0h+lpString2], r13d
0x1800318b7  call    cs:__imp_?IUriBuilderInternalCreateDomain@@YAJKW4__MIDL_IUri_0002@@PEBGKKPEAPEAGPEAK@Z; IUriBuilderInternalCreateDomain(ulong,__MIDL_IUri_0002,ushort const *,ulong,ulong,ushort * *,ulong *)
0x1800318bd  mov     r14d, eax
0x1800318c0  mov     eax, dword ptr [rsp+2D0h+var_288]
0x1800318c4  jmp     loc_180031676
0x1800318c9  mov     rax, [rdx]
0x1800318cc  mov     rcx, [rax+18h]
0x1800318d0  test    rcx, rcx
0x1800318d3  cmovz   rbx, rax
0x1800318d7  setnz   sil
0x1800318db  jnz     loc_18003181E
0x1800318e1  test    rbx, rbx
0x1800318e4  jz      short loc_180031939
0x1800318e6  test    edi, edi
0x1800318e8  jz      loc_180031AF4
0x1800318ee  inc     dword ptr [rbx+10h]
0x1800318f1  mov     ecx, 20h ; ' '; cb
0x1800318f6  call    cs:__imp_CoTaskMemAlloc
0x1800318fc  test    rax, rax
0x1800318ff  jz      loc_180031C7F
0x180031905  xorps   xmm0, xmm0
0x180031908  movups  xmmword ptr [rax], xmm0
0x18003190b  movups  xmmword ptr [rax+10h], xmm0
0x18003190f  mov     rcx, [rbx]
0x180031912  mov     [rax+18h], rcx
0x180031916  mov     rcx, [rsp+2D0h+var_260]
0x18003191b  mov     [rax], rcx
0x18003191e  mov     ecx, [rbp+1D0h+arg_20]
0x180031924  mov     [rax+10h], r13
0x180031928  xor     r13d, r13d
0x18003192b  mov     [rax+8], ecx
0x18003192e  mov     [rbx], rax
0x180031931  mov     rax, [rsp+2D0h+var_258]
0x180031936  mov     [rax], rbx
0x180031939  mov     rcx, [rsp+2D0h+var_290]; pv
  ... truncated ...
```
