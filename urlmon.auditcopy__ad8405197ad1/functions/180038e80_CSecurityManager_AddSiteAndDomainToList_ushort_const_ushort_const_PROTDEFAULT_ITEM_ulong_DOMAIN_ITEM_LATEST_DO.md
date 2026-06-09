# CSecurityManager::AddSiteAndDomainToList(ushort const *,ushort const *,PROTDEFAULT_ITEM *,ulong,DOMAIN_ITEM_LATEST * *,DOMAIN_ITEM_LATEST * *,DOMAIN_ITEM_LATEST * *)

- ea: `0x180038e80`
- end: `0x180039875`
- name: `?AddSiteAndDomainToList@CSecurityManager@@IEAAJPEBG0PEAUPROTDEFAULT_ITEM@@KPEAPEAUDOMAIN_ITEM_LATEST@@22@Z`
- size: `2549`
- prototype: `__int64 __fastcall(CSecurityManager *this, unsigned __int16 *, const unsigned __int16 *, struct PROTDEFAULT_ITEM *, unsigned int, struct DOMAIN_ITEM_LATEST **, struct DOMAIN_ITEM_LATEST **, struct DOMAIN_ITEM_LATEST **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038a4c`
- `0x180038c68`

## callees

- `0x180038e80`
- `0x1801285fe`
- `0x180128660`

## import_xrefs

- `iertutil!IUriBuilderInternalCreateDomain` at `0x1800392e9`
- `iertutil!IUriBuilderInternalCreateDomain` at `0x1800392e9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800390f2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180039165`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800391c4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180039228`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800395d0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800390f2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180039165`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800391c4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180039228`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800395d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003924f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003932e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003949d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003924f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003932e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003949d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800393a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800393bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800393a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800393bd`

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
    v68 = (const WCHAR *)*(&off_18012D430 + i);
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
0x180038e80  mov     r11, rsp
0x180038e83  push    rbp
0x180038e84  push    r13
0x180038e86  lea     rbp, [r11-1D8h]
0x180038e8d  sub     rsp, 2C8h
0x180038e94  mov     rax, cs:__security_cookie
0x180038e9b  xor     rax, rsp
0x180038e9e  mov     [rbp+1D0h+var_40], rax
0x180038ea5  mov     rax, [rbp+1D0h+arg_28]
0x180038eac  xor     r13d, r13d
0x180038eaf  mov     r10, [rbp+1D0h+arg_30]
0x180038eb6  mov     [r11-18h], rsi
0x180038eba  mov     rsi, rdx
0x180038ebd  mov     [r11-38h], r15
0x180038ec1  mov     r15, r8
0x180038ec4  mov     [rsp+2D0h+var_268], rax
0x180038ec9  mov     r11, 0FFFFFFFFFFFFFFFFh
0x180038ed0  mov     rax, [rbp+1D0h+arg_38]
0x180038ed7  mov     rdx, r11
0x180038eda  mov     [rsp+2D0h+var_258], rax
0x180038edf  mov     [rsp+2D0h+var_260], r9
0x180038ee4  mov     [rsp+2D0h+var_270], r10
0x180038ee9  mov     [rsp+2D0h+var_290], r13
0x180038eee  mov     dword ptr [rsp+2D0h+var_288], r13d
0x180038ef3  inc     rdx
0x180038ef6  cmp     [rsi+rdx*2], r13w
0x180038efb  jnz     short loc_180038EF3
0x180038efd  mov     [rsp+2D0h+arg_0], rbx
0x180038f05  mov     [rsp+2D0h+var_18], rdi
0x180038f0d  mov     [rsp+2D0h+var_20], r12
0x180038f15  mov     [rsp+2D0h+var_28], r14
0x180038f1d  mov     [rsp+2D0h+var_278], rdx
0x180038f22  test    r15, r15
0x180038f25  jz      loc_180039568
0x180038f2b  mov     r12, r11
0x180038f2e  xchg    ax, ax
0x180038f30  inc     r12
0x180038f33  cmp     [r8+r12*2], r13w
0x180038f38  jnz     short loc_180038F30
0x180038f3a  lea     r8, [rbp+1D0h+var_250]
0x180038f3e  mov     edi, 104h
0x180038f43  mov     ebx, edi
0x180038f45  mov     r14d, r13d
0x180038f48  test    r15, r15
0x180038f4b  jnz     loc_1800393EF
0x180038f51  test    rsi, rsi
0x180038f54  jz      loc_18003906F
0x180038f5a  test    edx, edx
0x180038f5c  jz      loc_18003906F
0x180038f62  test    r12d, r12d
0x180038f65  jz      short loc_180038FE4
0x180038f67  test    rbx, rbx
0x180038f6a  jz      loc_18003981A
0x180038f70  cmp     rbx, 7FFFFFFFh
0x180038f77  ja      loc_180039812
0x180038f7d  mov     ecx, 1
0x180038f82  lea     rdx, asc_18013A8F8; "."
0x180038f89  mov     r9, rbx
0x180038f8c  mov     r10, r8
0x180038f8f  mov     r11, r13
0x180038f92  test    rcx, rcx
0x180038f95  jz      short loc_180038FB7
0x180038f97  movzx   eax, word ptr [rdx]
0x180038f9a  test    ax, ax
0x180038f9d  jz      short loc_180038FB7
0x180038f9f  mov     [r10], ax
0x180038fa3  add     rdx, 2
0x180038fa7  add     r10, 2
0x180038fab  dec     rcx
0x180038fae  inc     r11
0x180038fb1  sub     r9, 1
0x180038fb5  jnz     short loc_180038F92
0x180038fb7  test    r9, r9
0x180038fba  lea     rdx, [r11-1]
0x180038fbe  lea     rcx, [r10-2]
0x180038fc2  mov     r14d, 8007007Ah
0x180038fc8  cmovnz  rdx, r11
0x180038fcc  cmovnz  rcx, r10
0x180038fd0  cmovnz  r14d, r13d
0x180038fd4  sub     rbx, rdx
0x180038fd7  lea     r8, [r8+rdx*2]
0x180038fdb  mov     [rcx], r13w
0x180038fdf  mov     rdx, [rsp+2D0h+var_278]
0x180038fe4  test    r14d, r14d
0x180038fe7  js      loc_18003906F
0x180038fed  test    rbx, rbx
0x180038ff0  jz      loc_18003983D
0x180038ff6  cmp     rbx, 7FFFFFFFh
0x180038ffd  ja      loc_180039832
0x180039003  mov     eax, edx
0x180039005  cmp     rax, 7FFFFFFFh
0x18003900b  jnb     loc_180039683
0x180039011  mov     rdx, rbx
0x180039014  mov     r9, r13
0x180039017  test    rax, rax
0x18003901a  jz      short loc_18003903C
0x18003901c  movzx   ecx, word ptr [rsi]
0x18003901f  test    cx, cx
0x180039022  jz      short loc_18003903C
0x180039024  mov     [r8], cx
0x180039028  add     rsi, 2
0x18003902c  add     r8, 2
0x180039030  dec     rax
0x180039033  inc     r9
0x180039036  sub     rdx, 1
0x18003903a  jnz     short loc_180039017
0x18003903c  test    rdx, rdx
0x18003903f  lea     rcx, [r8-2]
0x180039043  lea     rax, [r9-1]
0x180039047  mov     r14d, 8007007Ah
0x18003904d  cmovnz  rcx, r8
0x180039051  cmovnz  rax, r9
0x180039055  cmovnz  r14d, r13d
0x180039059  mov     [rcx], r13w
0x18003905d  mov     rcx, rbx
0x180039060  sub     rcx, rax
0x180039063  test    r14d, r14d
0x180039066  js      loc_1800397BE
0x18003906c  mov     rbx, rcx
0x18003906f  sub     edi, ebx
0x180039071  mov     [rsp+2D0h+var_290], r13
0x180039076  mov     eax, r13d
0x180039079  mov     dword ptr [rsp+2D0h+var_288], eax
0x18003907d  test    r14d, r14d
0x180039080  jns     loc_1800392C2
0x180039086  sub     edi, eax
0x180039088  mov     [rsp+2D0h+var_280], rdi
0x18003908d  jnz     loc_180039476
0x180039093  test    r14d, r14d
0x180039096  js      loc_180039377
0x18003909c  mov     r11, 0FFFFFFFFFFFFFFFFh
0x1800390a3  mov     rdx, [rsp+2D0h+var_268]
0x1800390a8  xor     esi, esi
0x1800390aa  xor     r12d, r12d
0x1800390ad  xor     r15d, r15d
0x1800390b0  mov     rbx, [rdx]
0x1800390b3  test    rbx, rbx
0x1800390b6  jz      loc_18003924A
0x1800390bc  mov     r10, [rsp+2D0h+var_270]
0x1800390c1  mov     rcx, [rsp+2D0h+var_290]
0x1800390c6  mov     rax, [r10]
0x1800390c9  mov     r8, [rax+18h]; lpString1
0x1800390cd  test    r8, r8
0x1800390d0  jz      loc_180039656
0x1800390d6  test    rcx, rcx
0x1800390d9  jz      short loc_180039119
0x1800390db  mov     [rsp+2D0h+cchCount2], r11d; cchCount2
0x1800390e0  mov     r9d, r11d; cchCount1
0x1800390e3  mov     [rsp+2D0h+lpString2], rcx; lpString2
0x1800390e8  mov     edx, 1001h; dwCmpFlags
0x1800390ed  mov     ecx, 7Fh; Locale
0x1800390f2  call    cs:__imp_CompareStringW
0x1800390f9  nop     dword ptr [rax+rax+00h]
0x1800390fe  mov     rdx, [rsp+2D0h+var_268]
0x180039103  mov     r10, [rsp+2D0h+var_270]
0x180039108  add     eax, 0FFFFFFFEh
0x18003910b  jz      loc_180039600
0x180039111  test    eax, eax
0x180039113  js      loc_180039633
0x180039119  cmp     [rsp+2D0h+var_290], rsi
0x18003911e  jz      loc_180039301
0x180039124  mov     rdx, [rsp+2D0h+var_258]
0x180039129  xor     edi, edi
0x18003912b  mov     rax, [rdx]
0x18003912e  test    rax, rax
0x180039131  jz      short loc_180039190
0x180039133  mov     r8, [rax+18h]; lpString1
0x180039137  mov     rcx, [rsp+2D0h+var_290]
0x18003913c  test    r8, r8
0x18003913f  jz      loc_180039665
0x180039145  test    rcx, rcx
0x180039148  jz      short loc_180039190
0x18003914a  mov     r9, 0FFFFFFFFFFFFFFFFh; cchCount1
0x180039151  mov     edx, 1001h; dwCmpFlags
0x180039156  mov     [rsp+2D0h+cchCount2], r9d; cchCount2
0x18003915b  mov     [rsp+2D0h+lpString2], rcx; lpString2
0x180039160  mov     ecx, 7Fh; Locale
0x180039165  call    cs:__imp_CompareStringW
0x18003916c  nop     dword ptr [rax+rax+00h]
0x180039171  mov     rdx, [rsp+2D0h+var_258]
0x180039176  add     eax, 0FFFFFFFEh
0x180039179  test    eax, eax
0x18003917b  jg      short loc_180039190
0x18003917d  mov     rbx, [rdx]
0x180039180  test    rbx, rbx
0x180039183  jz      short loc_1800391E5
0x180039185  nop     word ptr [rax+rax+00000000h]
0x180039190  mov     r8, [rbx+18h]; lpString1
0x180039194  mov     rax, [rsp+2D0h+var_290]
0x180039199  test    r8, r8
0x18003919c  jz      loc_180039608
0x1800391a2  test    rax, rax
0x1800391a5  jz      short loc_1800391ED
0x1800391a7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800391ae  mov     edx, 1001h; dwCmpFlags
0x1800391b3  mov     [rsp+2D0h+cchCount2], ecx; cchCount2
0x1800391b7  mov     r9d, ecx; cchCount1
0x1800391ba  mov     ecx, 7Fh; Locale
0x1800391bf  mov     [rsp+2D0h+lpString2], rax; lpString2
0x1800391c4  call    cs:__imp_CompareStringW
0x1800391cb  nop     dword ptr [rax+rax+00h]
0x1800391d0  mov     ecx, eax
0x1800391d2  lea     eax, [rcx-2]
0x1800391d5  test    eax, eax
0x1800391d7  jg      short loc_1800391ED
0x1800391d9  mov     rdi, rbx
0x1800391dc  mov     rbx, [rbx+20h]
0x1800391e0  test    rbx, rbx
0x1800391e3  jnz     short loc_180039190
0x1800391e5  mov     r12d, 1
0x1800391eb  jmp     short loc_18003924A
0x1800391ed  test    rdi, rdi
0x1800391f0  jz      loc_1800395F6
0x1800391f6  mov     r8, [rdi+18h]; lpString1
0x1800391fa  mov     rax, [rsp+2D0h+var_290]
0x1800391ff  test    r8, r8
0x180039202  jz      loc_180039674
0x180039208  test    rax, rax
0x18003920b  jz      short loc_180039241
0x18003920d  mov     r9, 0FFFFFFFFFFFFFFFFh; cchCount1
0x180039214  mov     edx, 1001h; dwCmpFlags
0x180039219  mov     [rsp+2D0h+cchCount2], r9d; cchCount2
0x18003921e  mov     ecx, 7Fh; Locale
0x180039223  mov     [rsp+2D0h+lpString2], rax; lpString2
0x180039228  call    cs:__imp_CompareStringW
0x18003922f  nop     dword ptr [rax+rax+00h]
0x180039234  mov     ecx, eax
0x180039236  lea     eax, [rcx-2]
0x180039239  test    eax, eax
0x18003923b  jz      loc_18003955B
0x180039241  mov     r15d, 1
0x180039247  mov     rbx, rdi
0x18003924a  mov     ecx, 28h ; '('; cb
0x18003924f  call    cs:__imp_CoTaskMemAlloc
0x180039256  nop     dword ptr [rax+rax+00h]
0x18003925b  mov     rdx, rax
0x18003925e  test    rax, rax
0x180039261  jz      loc_1800396CA
0x180039267  xor     eax, eax
0x180039269  xorps   xmm0, xmm0
0x18003926c  movups  xmmword ptr [rdx], xmm0
0x18003926f  movups  xmmword ptr [rdx+10h], xmm0
0x180039273  mov     [rdx+20h], rax
0x180039277  mov     rcx, [rsp+2D0h+var_290]
0x18003927c  mov     [rdx+18h], rcx
0x180039280  mov     rcx, [rsp+2D0h+var_268]
0x180039285  mov     [rsp+2D0h+var_290], rax
0x18003928a  mov     rax, [rcx]
0x18003928d  test    rax, rax
0x180039290  jz      loc_18003963E
0x180039296  test    r12d, r12d
0x180039299  jnz     loc_180039617
0x18003929f  test    esi, esi
0x1800392a1  jnz     loc_180039692
0x1800392a7  test    r15d, r15d
0x1800392aa  jz      short loc_1800392B8
0x1800392ac  mov     rax, [rbx+20h]
0x1800392b0  mov     [rdx+20h], rax
0x1800392b4  mov     [rbx+20h], rdx
0x1800392b8  mov     rdi, [rsp+2D0h+var_280]
0x1800392bd  mov     rbx, rdx
0x1800392c0  jmp     short loc_18003931E
0x1800392c2  lea     rax, [rsp+2D0h+var_288]
0x1800392c7  mov     r9d, edi
0x1800392ca  mov     [rsp+30h], rax
0x1800392cf  lea     r8, [rbp+1D0h+var_250]
0x1800392d3  lea     rax, [rsp+2D0h+var_290]
0x1800392d8  mov     edx, 1
0x1800392dd  mov     qword ptr [rsp+2D0h+cchCount2], rax
0x1800392e2  xor     ecx, ecx
0x1800392e4  mov     dword ptr [rsp+2D0h+lpString2], r13d
0x1800392e9  call    cs:__imp_?IUriBuilderInternalCreateDomain@@YAJKW4__MIDL_IUri_0002@@PEBGKKPEAPEAGPEAK@Z; IUriBuilderInternalCreateDomain(ulong,__MIDL_IUri_0002,ushort const *,ulong,ulong,ushort * *,ulong *)
0x1800392f0  nop     dword ptr [rax+rax+00h]
0x1800392f5  mov     r14d, eax
0x1800392f8  mov     eax, dword ptr [rsp+2D0h+var_288]
0x1800392fc  jmp     loc_180039086
0x180039301  mov     rax, [rdx]
0x180039304  mov     rcx, [rax+18h]
0x180039308  test    rcx, rcx
0x18003930b  cmovz   rbx, rax
0x18003930f  setnz   sil
0x180039313  jnz     loc_18003924A
0x180039319  test    rbx, rbx
0x18003931c  jz      short loc_180039377
0x18003931e  test    edi, edi
0x180039320  jz      loc_180039544
0x180039326  inc     dword ptr [rbx+10h]
0x180039329  mov     ecx, 20h ; ' '; cb
0x18003932e  call    cs:__imp_CoTaskMemAlloc
0x180039335  nop     dword ptr [rax+rax+00h]
0x18003933a  test    rax, rax
0x18003933d  jz      loc_1800396D5
0x180039343  xorps   xmm0, xmm0
0x180039346  movups  xmmword ptr [rax], xmm0
0x180039349  movups  xmmword ptr [rax+10h], xmm0
0x18003934d  mov     rcx, [rbx]
0x180039350  mov     [rax+18h], rcx
0x180039354  mov     rcx, [rsp+2D0h+var_260]
0x180039359  mov     [rax], rcx
0x18003935c  mov     ecx, [rbp+1D0h+arg_20]
  ... truncated ...
```
