# CSecurityManager::ReadMappings(int,ulong *,ulong *,uchar * *)

- ea: `0x180031e30`
- end: `0x180032c5b`
- name: `?ReadMappings@CSecurityManager@@IEAAHHPEAK0PEAPEAE@Z`
- size: `3627`
- prototype: `int(CSecurityManager *__hidden this, int, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180031048`
- `0x18003125c`

## callees

- `0x1800150e0`
- `0x180031e30`
- `0x1800342d0`
- `0x18006fc88`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSValueW` at `0x1800324a1`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSValueW` at `0x18003264c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSValueW` at `0x180032a91`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSValueW` at `0x180032ad4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSValueW` at `0x1800324a1`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSValueW` at `0x18003264c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSValueW` at `0x180032a91`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSValueW` at `0x180032ad4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryInfoUSKeyW` at `0x180031ffa`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryInfoUSKeyW` at `0x1800321ba`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryInfoUSKeyW` at `0x1800323ac`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryInfoUSKeyW` at `0x180032b2f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryInfoUSKeyW` at `0x180032b80`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryInfoUSKeyW` at `0x180032bc4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryInfoUSKeyW` at `0x180031ffa`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryInfoUSKeyW` at `0x1800321ba`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryInfoUSKeyW` at `0x1800323ac`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryInfoUSKeyW` at `0x180032b2f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryInfoUSKeyW` at `0x180032b80`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryInfoUSKeyW` at `0x180032bc4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x180032282`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x18003293a`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x1800329d7`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x180032a0e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x180032282`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x18003293a`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x1800329d7`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegEnumUSKeyW` at `0x180032a0e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180031f9e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180032136`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180032343`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180032770`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800327af`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180032831`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180031f9e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180032136`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180032343`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180032770`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800327af`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180032831`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x1800320ab`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x1800320cf`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180032553`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x1800320ab`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x1800320cf`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180032553`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800321f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800323e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032586`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800321f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800323e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032586`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032c20`

## pseudocode

```c
_BOOL8 __fastcall CSecurityManager::ReadMappings(
        CSecurityManager *this,
        BOOL a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int8 **a5)
{
  CSecurityManager *v5; // r10
  __int64 v7; // rcx
  unsigned int *v8; // r13
  BOOL v9; // r12d
  BOOL v10; // r15d
  const unsigned __int16 *v11; // r8
  __int64 v12; // rdx
  WCHAR *v13; // rax
  WCHAR *v14; // rcx
  bool v15; // zf
  LSTATUS v16; // ebx
  void *v17; // rbx
  BOOL fIgnoreHKCU; // eax
  LSTATUS v19; // eax
  SHREGENUM_FLAGS enumRegFlags; // eax
  DWORD v21; // ecx
  _WORD *v22; // rcx
  DWORD v23; // edx
  BOOL v24; // ebx
  HUSKEY v26; // rbx
  BOOL v27; // eax
  LSTATUS v28; // eax
  DWORD *v29; // r13
  int *v30; // r12
  SHREGENUM_FLAGS v31; // eax
  int v32; // edx
  DWORD v33; // ecx
  unsigned int v34; // ecx
  SIZE_T v35; // rbx
  char *v36; // rax
  char *v37; // r15
  int v38; // eax
  unsigned int v39; // edx
  SHREGENUM_FLAGS v40; // eax
  unsigned __int64 v41; // r8
  __int64 v42; // rcx
  WCHAR *v43; // rdx
  _WORD *v44; // r9
  _WORD *v45; // rcx
  HUSKEY v46; // rbx
  BOOL v47; // eax
  LSTATUS v48; // eax
  DWORD *v49; // rsi
  SHREGENUM_FLAGS v50; // eax
  DWORD *v51; // rdi
  SIZE_T v52; // rbx
  _DWORD *v53; // rax
  _DWORD *v54; // rdi
  DWORD v55; // ebx
  DWORD v56; // r14d
  SHREGENUM_FLAGS v57; // eax
  WCHAR *v58; // r8
  __int64 v59; // rdx
  __int64 v60; // r10
  _WORD *v61; // r9
  _WORD *v62; // rcx
  unsigned __int8 *v63; // r14
  DWORD v64; // edx
  SIZE_T v65; // rbx
  _DWORD *v66; // rax
  _DWORD *v67; // rsi
  LPVOID *v68; // r15
  DWORD v69; // r14d
  DWORD v70; // ebx
  SHREGENUM_FLAGS v71; // eax
  WCHAR *v72; // r8
  __int64 v73; // rdx
  __int64 v74; // r10
  _WORD *v75; // r9
  _WORD *v76; // rcx
  const wchar_t *v77; // rdx
  __int64 v78; // r8
  WCHAR *v79; // r9
  __int64 v80; // rax
  unsigned __int64 v81; // rcx
  unsigned __int8 *v82; // rax
  DWORD v83; // eax
  SHREGENUM_FLAGS v84; // eax
  unsigned __int64 v85; // r8
  __int64 v86; // rcx
  WCHAR *v87; // rdx
  _WORD *v88; // r9
  DWORD pcchValueName; // [rsp+48h] [rbp-C0h] BYREF
  DWORD pdwType; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD pvData; // [rsp+50h] [rbp-B8h] BYREF
  DWORD v92; // [rsp+54h] [rbp-B4h] BYREF
  DWORD pcchMaxSubKeyLen[2]; // [rsp+58h] [rbp-B0h] BYREF
  const unsigned int *v94; // [rsp+60h] [rbp-A8h] BYREF
  HUSKEY hRelativeUSKey; // [rsp+68h] [rbp-A0h]
  BOOL v96; // [rsp+70h] [rbp-98h]
  int v97; // [rsp+74h] [rbp-94h]
  BOOL v98; // [rsp+78h] [rbp-90h]
  DWORD v99; // [rsp+80h] [rbp-88h] BYREF
  DWORD pcchName; // [rsp+84h] [rbp-84h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp-80h] BYREF
  BOOL v102; // [rsp+8Ch] [rbp-7Ch]
  DWORD v103; // [rsp+90h] [rbp-78h]
  HUSKEY v104; // [rsp+98h] [rbp-70h] BYREF
  const unsigned int *v105; // [rsp+A0h] [rbp-68h] BYREF
  HUSKEY hUSkey; // [rsp+A8h] [rbp-60h]
  BOOL v107; // [rsp+B0h] [rbp-58h]
  int v108; // [rsp+B4h] [rbp-54h]
  BOOL v109; // [rsp+B8h] [rbp-50h]
  const unsigned int *v110; // [rsp+C0h] [rbp-48h] BYREF
  HUSKEY hUSKey; // [rsp+C8h] [rbp-40h]
  BOOL v112; // [rsp+D0h] [rbp-38h]
  int v113; // [rsp+D4h] [rbp-34h]
  BOOL v114; // [rsp+D8h] [rbp-30h]
  DWORD pcValues; // [rsp+E0h] [rbp-28h] BYREF
  DWORD v116; // [rsp+E4h] [rbp-24h] BYREF
  HUSKEY v117; // [rsp+E8h] [rbp-20h] BYREF
  HUSKEY phNewUSKey; // [rsp+F0h] [rbp-18h] BYREF
  BOOL v119; // [rsp+F8h] [rbp-10h]
  unsigned int *v120; // [rsp+100h] [rbp-8h]
  unsigned __int8 *v121; // [rsp+108h] [rbp+0h]
  unsigned int *v122; // [rsp+110h] [rbp+8h]
  WCHAR pszValueName[32]; // [rsp+118h] [rbp+10h] BYREF
  WCHAR pwzPath[264]; // [rsp+158h] [rbp+50h] BYREF
  WCHAR v125[264]; // [rsp+368h] [rbp+260h] BYREF
  WCHAR pwzName[264]; // [rsp+578h] [rbp+470h] BYREF

  v5 = this;
  v7 = 2147483646;
  v8 = a4;
  v120 = a4;
  v9 = !a2;
  v122 = a3;
  v10 = a2;
  v102 = v9;
  v114 = v9;
  v98 = v9;
  v119 = a2;
  v110 = &CRegKey::`vftable';
  hUSKey = 0;
  v112 = a2;
  v113 = 0;
  v94 = &CRegKey::`vftable';
  hRelativeUSKey = 0;
  v96 = a2;
  v97 = 0;
  if ( CSecurityManager::s_fESCEnabled )
  {
    v77 = L"EscDomains\\";
    v78 = 260;
    v79 = pwzPath;
    do
    {
      if ( !v7 )
        break;
      if ( !*v77 )
        break;
      *v79++ = *v77++;
      --v7;
      --v78;
    }
    while ( v78 );
    v14 = v79 - 1;
    if ( v78 )
      v14 = v79;
    v15 = v78 == 0;
  }
  else
  {
    v11 = L"Domains\\";
    v12 = 260;
    v13 = pwzPath;
    do
    {
      if ( !v7 )
        break;
      if ( !*v11 )
        break;
      *v13++ = *v11++;
      --v7;
      --v12;
    }
    while ( v12 );
    v14 = v13 - 1;
    if ( v12 )
      v14 = v13;
    v15 = v12 == 0;
  }
  v16 = -2147024774;
  *v14 = 0;
  if ( !v15 )
    v16 = 0;
  if ( v16 < 0 )
    goto LABEL_32;
  if ( !*((_QWORD *)v5 + 22)
    && !(unsigned int)CRegKeyZoneMap::OpenKey(
                        (CSecurityManager *)((char *)v5 + 168),
                        CSecurityManager::s_fUsePoliciesZoneMap) )
  {
    v16 = -2147467259;
    goto LABEL_32;
  }
  v17 = (void *)*((_QWORD *)v5 + 22);
  pcchMaxSubKeyLen[0] = 0;
  pcValues = 0;
  phNewUSKey = 0;
  CRegKey::Close((CRegKey *)&v110);
  if ( !v113 )
  {
LABEL_14:
    fIgnoreHKCU = v112;
    goto LABEL_15;
  }
  fIgnoreHKCU = v112;
  if ( !v112 )
  {
    if ( !SHRegOpenUSKeyW(pwzPath, 0x20019u, v17, &phNewUSKey, 1) )
      goto LABEL_16;
    goto LABEL_14;
  }
LABEL_15:
  v19 = SHRegOpenUSKeyW(pwzPath, 0x20019u, v17, &phNewUSKey, fIgnoreHKCU);
  v16 = v19;
  if ( !v19 )
  {
LABEL_16:
    hUSKey = phNewUSKey;
    goto LABEL_17;
  }
  if ( v19 < 0 )
    goto LABEL_32;
LABEL_17:
  if ( !hUSKey )
  {
    v16 = 1010;
    goto LABEL_22;
  }
  if ( v113 )
  {
    if ( v112 )
      goto LABEL_145;
    v16 = SHRegQueryInfoUSKeyW(hUSKey, a3, pcchMaxSubKeyLen, &pcValues, 0, SHREGENUM_HKLM);
    if ( !v16 )
      goto LABEL_22;
  }
  if ( v112 )
  {
LABEL_145:
    enumRegFlags = SHREGENUM_HKLM;
    goto LABEL_21;
  }
  enumRegFlags = v114;
LABEL_21:
  v16 = SHRegQueryInfoUSKeyW(hUSKey, a3, pcchMaxSubKeyLen, &pcValues, 0, enumRegFlags);
LABEL_22:
  if ( v16 >= 0 && *a3 )
  {
    v21 = 2 * pcchMaxSubKeyLen[0] + 41;
    if ( v21 < 2 * pcchMaxSubKeyLen[0] + 34 )
    {
      *v8 = -1;
LABEL_26:
      v16 = -2147024362;
      goto LABEL_32;
    }
    v80 = v21 & 0xFFFFFFF8;
    *v8 = v80;
    v81 = v80 * *a3;
    if ( v81 > 0xFFFFFFFF )
      goto LABEL_26;
    v82 = (unsigned __int8 *)operator new((unsigned int)v81);
    v121 = v82;
    v63 = v82;
    *a5 = v82;
    if ( v82 )
    {
      v83 = *a3;
      v16 = 0;
      *a3 = 0;
      LODWORD(phNewUSKey) = v83;
      v23 = 0;
      v103 = 0;
      if ( !v83 )
        goto LABEL_32;
      while ( 1 )
      {
        v99 = 260;
        if ( !hUSKey )
          goto LABEL_166;
        if ( v113 && !v112 )
        {
          v16 = SHRegEnumUSKeyW(hUSKey, v23, v125, &v99, SHREGENUM_HKLM);
          if ( !v16 )
            goto LABEL_165;
          v23 = v103;
        }
        v99 = 260;
        if ( v112 )
          v84 = SHREGENUM_HKLM;
        else
          v84 = v114;
        v16 = SHRegEnumUSKeyW(hUSKey, v23, v125, &v99, v84);
LABEL_165:
        if ( v16 < 0 )
          goto LABEL_32;
LABEL_166:
        v85 = pcchMaxSubKeyLen[0] + 1;
        if ( pcchMaxSubKeyLen[0] == -1 )
        {
          v16 = -2147024809;
LABEL_30:
          if ( v16 < 0 )
            goto LABEL_32;
          goto LABEL_31;
        }
        if ( v85 > 0x7FFFFFFF )
        {
          v16 = -2147024809;
          *((_WORD *)v63 + 14) = 0;
          goto LABEL_30;
        }
        v86 = 2147483646;
        v87 = v125;
        v88 = v63 + 28;
        do
        {
          if ( !v86 )
            break;
          if ( !*v87 )
            break;
          *v88++ = *v87++;
          --v86;
          --v85;
        }
        while ( v85 );
        v22 = v88 - 1;
        v16 = -2147024774;
        if ( v85 )
        {
          v22 = v88;
          v16 = 0;
        }
        *v22 = 0;
        if ( !v85 )
          goto LABEL_30;
        v26 = hUSKey;
        v117 = 0;
        (*((void (__fastcall **)(const unsigned int **))v94 + 2))(&v94);
        if ( !v26 && v63 == (unsigned __int8 *)-28LL )
          goto LABEL_42;
        if ( v97 )
        {
          v27 = v96;
          if ( v96 )
            goto LABEL_40;
          if ( !SHRegOpenUSKeyW((LPCWSTR)v63 + 14, 0x20019u, v26, &v117, 1) )
          {
LABEL_41:
            hRelativeUSKey = v117;
            goto LABEL_42;
          }
        }
        v27 = v96;
LABEL_40:
        v28 = SHRegOpenUSKeyW((LPCWSTR)v63 + 14, 0x20019u, v26, &v117, v27);
        v16 = v28;
        if ( !v28 )
          goto LABEL_41;
        if ( v28 < 0 )
          goto LABEL_32;
LABEL_42:
        v105 = &CRegKey::`vftable';
        v29 = (DWORD *)(v63 + 24);
        hUSkey = 0;
        v107 = v10;
        v108 = 0;
        v109 = v9;
        pcchMaxSubKeyLen[1] = 0;
        if ( !hRelativeUSKey )
          goto LABEL_127;
        v30 = (int *)(v63 + 16);
        if ( v97 )
        {
          if ( v96 )
            goto LABEL_128;
          if ( !SHRegQueryInfoUSKeyW(
                  hRelativeUSKey,
                  (LPDWORD)v63 + 4,
                  &pcchMaxSubKeyLen[1],
                  (LPDWORD)v63 + 6,
                  0,
                  SHREGENUM_HKLM) )
            goto LABEL_47;
        }
        if ( !v96 )
        {
          v31 = v98;
          goto LABEL_46;
        }
LABEL_128:
        v31 = SHREGENUM_HKLM;
LABEL_46:
        if ( SHRegQueryInfoUSKeyW(hRelativeUSKey, (LPDWORD)v63 + 4, &pcchMaxSubKeyLen[1], (LPDWORD)v63 + 6, 0, v31) )
        {
LABEL_127:
          v16 = -2147467259;
          goto LABEL_125;
        }
LABEL_47:
        v32 = *v30;
        if ( !*v30 )
          goto LABEL_126;
        v33 = 2 * pcchMaxSubKeyLen[1] + 25;
        if ( v33 < 2 * pcchMaxSubKeyLen[1] + 18 )
        {
          *((_DWORD *)v63 + 5) = -1;
          v16 = -2147024362;
LABEL_125:
          v51 = v29;
          goto LABEL_97;
        }
        v34 = v33 & 0xFFFFFFF8;
        *((_DWORD *)v63 + 5) = v34;
        v35 = v34 * v32;
        v36 = (char *)CoTaskMemAlloc(v35);
        v37 = v36;
        if ( v36 )
        {
          memset_0(v36, 0, (unsigned int)v35);
          v38 = *v30;
          v39 = 0;
          v92 = 0;
          *(_QWORD *)v63 = v37;
          LODWORD(v117) = v38;
          *v30 = 0;
          if ( !v38 )
          {
LABEL_126:
            v16 = 0;
            v51 = (DWORD *)(v63 + 24);
            goto LABEL_97;
          }
          while ( 2 )
          {
            pcchName = 260;
            if ( hRelativeUSKey )
            {
              if ( !v97 || v96 )
                goto LABEL_53;
              v16 = SHRegEnumUSKeyW(hRelativeUSKey, v39, pwzName, &pcchName, SHREGENUM_HKLM);
              if ( v16 )
              {
                v39 = v92;
LABEL_53:
                pcchName = 260;
                if ( v96 )
                  v40 = SHREGENUM_HKLM;
                else
                  v40 = v98;
                v16 = SHRegEnumUSKeyW(hRelativeUSKey, v39, pwzName, &pcchName, v40);
              }
              if ( v16 < 0 )
                goto LABEL_125;
            }
            v41 = pcchMaxSubKeyLen[1] + 1;
            if ( pcchMaxSubKeyLen[1] == -1 )
            {
              v16 = -2147024809;
            }
            else if ( v41 > 0x7FFFFFFF )
            {
              v16 = -2147024809;
              *((_WORD *)v37 + 6) = 0;
            }
            else
            {
              v42 = 2147483646;
              v43 = pwzName;
              v44 = v37 + 12;
              do
              {
                if ( !v42 )
                  break;
                if ( !*v43 )
                  break;
                *v44++ = *v43++;
                --v42;
                --v41;
              }
              while ( v41 );
              v45 = v44 - 1;
              v16 = -2147024774;
              if ( v41 )
              {
                v45 = v44;
                v16 = 0;
              }
              *v45 = 0;
              if ( v41 )
              {
                v46 = hRelativeUSKey;
                v104 = 0;
                (*((void (__fastcall **)(const unsigned int **, WCHAR *))v105 + 2))(&v105, v43);
                if ( !v46 && v37 == (char *)-12LL )
                  goto LABEL_72;
                if ( !v108 )
                {
LABEL_68:
                  v47 = v107;
                  goto LABEL_69;
                }
                v47 = v107;
                if ( !v107 )
                {
                  if ( SHRegOpenUSKeyW((LPCWSTR)v37 + 6, 0x20019u, v46, &v104, 1) )
                    goto LABEL_68;
LABEL_70:
                  hUSkey = v104;
                  goto LABEL_72;
                }
LABEL_69:
                v48 = SHRegOpenUSKeyW((LPCWSTR)v37 + 6, 0x20019u, v46, &v104, v47);
                v16 = v48;
                if ( !v48 )
                  goto LABEL_70;
                if ( v48 < 0 )
                  goto LABEL_125;
LABEL_72:
                LODWORD(v104) = 0;
                v116 = 0;
                v49 = (DWORD *)(v37 + 8);
                if ( hUSkey )
                {
                  if ( !v108 )
                    goto LABEL_74;
                  if ( v107 )
                    goto LABEL_129;
                  v16 = SHRegQueryInfoUSKeyW(hUSkey, (LPDWORD)&v104, &v116, (LPDWORD)v37 + 2, 0, SHREGENUM_HKLM);
                  if ( v16 )
                  {
LABEL_74:
                    if ( !v107 )
                    {
                      v50 = v109;
                      goto LABEL_76;
                    }
LABEL_129:
                    v50 = SHREGENUM_HKLM;
LABEL_76:
                    v16 = SHRegQueryInfoUSKeyW(hUSkey, (LPDWORD)&v104, &v116, (LPDWORD)v37 + 2, 0, v50);
                  }
                  v51 = v29;
                  if ( v16 < 0 )
                    goto LABEL_97;
                }
                else
                {
                  v16 = 1010;
                }
                if ( *v49 )
                {
                  v52 = saturated_mul(*v49, 0x44u);
                  v53 = CoTaskMemAlloc(v52);
                  v54 = v53;
                  if ( !v53 )
                  {
                    *(_QWORD *)v37 = 0;
                    v16 = -2147024882;
                    v51 = v29;
                    goto LABEL_97;
                  }
                  memset_0(v53, 0, v52);
                  *(_QWORD *)v37 = v54;
                  v55 = 0;
                  v56 = *v49;
                  pdwType = 0;
                  pvData = 0;
                  *v49 = 0;
                  if ( v56 )
                  {
                    do
                    {
                      pcchValueName = 32;
                      pcbData = 4;
                      if ( hUSkey )
                      {
                        if ( v108
                          && !v107
                          && !SHRegEnumUSValueW(
                                hUSkey,
                                v55,
                                pszValueName,
                                &pcchValueName,
                                &pdwType,
                                &pvData,
                                &pcbData,
                                SHREGENUM_HKLM)
                          || ((pcbData = 4, pcchValueName = 32, v107) ? (v57 = SHREGENUM_HKLM) : (v57 = v109),
                              !SHRegEnumUSValueW(
                                 hUSkey,
                                 v55,
                                 pszValueName,
                                 &pcchValueName,
                                 &pdwType,
                                 &pvData,
                                 &pcbData,
                                 v57)) )
                        {
                          if ( pdwType == 4 )
                          {
                            v58 = pszValueName;
                            v59 = 2147483646;
                            v60 = 32;
                            v61 = &v54[17 * *v49 + 1];
                            do
                            {
                              if ( !v59 )
                                break;
                              if ( !*v58 )
                                break;
                              *v61++ = *v58++;
                              --v59;
                              --v60;
                            }
                            while ( v60 );
                            v62 = v61 - 1;
                            if ( v60 )
                              v62 = v61;
                            *v62 = 0;
                            v54[17 * (*v49)++] = pvData;
                          }
                        }
                      }
                      ++v55;
                    }
                    while ( v55 < v56 );
                  }
                  v63 = v121;
                  v16 = 0;
                  goto LABEL_96;
                }
              }
            }
            v51 = v29;
            if ( v16 < 0 )
              goto LABEL_97;
LABEL_96:
            v64 = v92;
            v51 = v29;
            ++*v30;
            v39 = v64 + 1;
            v92 = v39;
            if ( v39 >= (unsigned int)v117 )
              goto LABEL_97;
            v37 += *((unsigned int *)v63 + 5);
            continue;
          }
        }
        *(_QWORD *)v63 = 0;
        v16 = -2147024882;
        v51 = (DWORD *)(v63 + 24);
LABEL_97:
        v105 = &CRegKey::`vftable';
        if ( hUSkey )
          SHRegCloseUSKey(hUSkey);
        if ( v16 < 0 )
          goto LABEL_32;
        if ( *v51 )
        {
          v65 = saturated_mul(*v51, 0x44u);
          v66 = CoTaskMemAlloc(v65);
          v67 = v66;
          if ( !v66 )
          {
            *((_QWORD *)v63 + 1) = 0;
            v16 = -2147024882;
            goto LABEL_32;
          }
          memset_0(v66, 0, v65);
          *((_QWORD *)v63 + 1) = v67;
          v68 = (LPVOID *)(v63 + 8);
          pdwType = 0;
          v69 = *v51;
          v70 = 0;
          pcchValueName = 0;
          for ( *v51 = 0; v70 < v69; ++v70 )
          {
            pvData = 32;
            v92 = 4;
            if ( hRelativeUSKey )
            {
              if ( v97
                && !v96
                && !SHRegEnumUSValueW(
                      hRelativeUSKey,
                      v70,
                      pszValueName,
                      &pvData,
                      &pdwType,
                      &pcchValueName,
                      &v92,
                      SHREGENUM_HKLM)
                || ((v92 = 4, pvData = 32, v96) ? (v71 = SHREGENUM_HKLM) : (v71 = v98),
                    !SHRegEnumUSValueW(hRelativeUSKey, v70, pszValueName, &pvData, &pdwType, &pcchValueName, &v92, v71)) )
              {
                if ( pdwType == 4 )
                {
                  v72 = pszValueName;
                  v73 = 2147483646;
                  v74 = 32;
                  v75 = &v67[17 * *v51 + 1];
                  do
                  {
                    if ( !v73 )
                      break;
                    if ( !*v72 )
                      break;
                    *v75++ = *v72++;
                    --v73;
                    --v74;
                  }
                  while ( v74 );
                  v76 = v75 - 1;
                  if ( v74 )
                    v76 = v75;
                  *v76 = 0;
                  v67[17 * (*v51)++] = pcchValueName;
                }
              }
            }
          }
          v16 = 0;
          if ( !*v51 && *v68 )
          {
            CoTaskMemFree(*v68);
            *v68 = 0;
          }
          v9 = v102;
          v8 = v120;
        }
        else
        {
          v9 = v102;
          v8 = v120;
        }
LABEL_31:
        v23 = ++v103;
        ++*v122;
        if ( v23 >= (unsigned int)phNewUSKey )
          goto LABEL_32;
        v10 = v119;
        v63 = &v121[*v8];
        v121 = v63;
      }
    }
    v16 = -2147024882;
  }
LABEL_32:
  v24 = v16 >= 0;
  v94 = &CRegKey::`vftable';
  if ( hRelativeUSKey )
  {
    SHRegCloseUSKey(hRelativeUSKey);
    hRelativeUSKey = 0;
  }
  v110 = &CRegKey::`vftable';
  if ( hUSKey )
    SHRegCloseUSKey(hUSKey);
  return v24;
}

```

## disassembly

```asm
0x180031e30  mov     r11, rsp
0x180031e33  push    rbp
0x180031e34  push    rbx
0x180031e35  lea     rbp, [r11-6C8h]
0x180031e3c  sub     rsp, 7B8h
0x180031e43  mov     rax, cs:__security_cookie
0x180031e4a  xor     rax, rsp
0x180031e4d  mov     [rbp+6C0h+var_40], rax
0x180031e54  mov     [r11+10h], rsi
0x180031e58  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180031e5f  mov     [r11-18h], rdi
0x180031e63  mov     r10, rcx
0x180031e66  mov     rdi, [rbp+6C0h+arg_20]
0x180031e6d  mov     rsi, r8
0x180031e70  mov     [r11-20h], r12
0x180031e74  mov     ecx, 7FFFFFFEh
0x180031e79  xor     r12d, r12d
0x180031e7c  mov     [r11-28h], r13
0x180031e80  test    edx, edx
0x180031e82  mov     [r11-38h], r15
0x180031e86  mov     r13, r9
0x180031e89  mov     [rbp+6C0h+var_6C8], r9
0x180031e8d  setz    r12b
0x180031e91  mov     [rbp+6C0h+var_6B8], r8
0x180031e95  cmp     cs:?s_fESCEnabled@CSecurityManager@@0HA, 0; int CSecurityManager::s_fESCEnabled
0x180031e9c  mov     r15d, edx
0x180031e9f  mov     [rbp+6C0h+var_73C], r12d
0x180031ea3  mov     [rbp+6C0h+var_6F0], r12d
0x180031ea7  mov     [rsp+7C0h+var_750], r12d
0x180031eac  mov     [rbp+6C0h+var_6D0], edx
0x180031eaf  mov     [rbp+6C0h+var_708], rax
0x180031eb3  mov     [rbp+6C0h+hUSKey], 0
0x180031ebb  mov     [rbp+6C0h+var_6F8], edx
0x180031ebe  mov     [rbp+6C0h+var_6F4], 0
0x180031ec5  mov     [rsp+7C0h+var_768], rax
0x180031eca  mov     [rsp+7C0h+hRelativeUSKey], 0
0x180031ed3  mov     [rsp+7C0h+var_758], edx
0x180031ed7  mov     [rsp+7C0h+var_754], 0
0x180031edf  jnz     loc_180032844
0x180031ee5  lea     r8, aDomains; "Domains\\"
0x180031eec  mov     edx, 104h
0x180031ef1  lea     rax, [rbp+6C0h+pwzPath]
0x180031ef5  test    rcx, rcx
0x180031ef8  jz      short loc_180031F19
0x180031efa  movzx   r9d, word ptr [r8]
0x180031efe  test    r9w, r9w
0x180031f02  jz      short loc_180031F19
0x180031f04  mov     [rax], r9w
0x180031f08  add     r8, 2
0x180031f0c  add     rax, 2
0x180031f10  dec     rcx
0x180031f13  sub     rdx, 1
0x180031f17  jnz     short loc_180031EF5
0x180031f19  test    rdx, rdx
0x180031f1c  lea     rcx, [rax-2]
0x180031f20  cmovnz  rcx, rax
0x180031f24  xor     eax, eax
0x180031f26  test    rdx, rdx
0x180031f29  mov     ebx, 8007007Ah
0x180031f2e  mov     [rcx], ax
0x180031f31  cmovnz  ebx, eax
0x180031f34  mov     [rsp+7C0h+var_28], r14
0x180031f3c  test    ebx, ebx
0x180031f3e  js      loc_180032068
0x180031f44  lea     rcx, [r10+0A8h]; this
0x180031f4b  cmp     qword ptr [rcx+8], 0
0x180031f50  jz      loc_180032AE7
0x180031f56  mov     rbx, [r10+0B0h]
0x180031f5d  lea     rcx, [rbp+6C0h+var_708]; this
0x180031f61  mov     [rsp+7C0h+pcchMaxSubKeyLen], 0
0x180031f69  mov     [rbp+6C0h+pcValues], 0
0x180031f70  mov     [rbp+6C0h+phNewUSKey], 0
0x180031f78  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x180031f7d  cmp     [rbp+6C0h+var_6F4], 0
0x180031f81  jnz     loc_18003280E
0x180031f87  mov     eax, [rbp+6C0h+var_6F8]
0x180031f8a  lea     r9, [rbp+6C0h+phNewUSKey]; phNewUSKey
0x180031f8e  mov     [rsp+7C0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180031f92  mov     r8, rbx; hRelativeUSKey
0x180031f95  lea     rcx, [rbp+6C0h+pwzPath]; pwzPath
0x180031f99  mov     edx, 20019h; samDesired
0x180031f9e  call    cs:__imp_SHRegOpenUSKeyW
0x180031fa4  mov     ebx, eax
0x180031fa6  test    eax, eax
0x180031fa8  jnz     loc_180032A27
0x180031fae  mov     rax, [rbp+6C0h+phNewUSKey]
0x180031fb2  mov     [rbp+6C0h+hUSKey], rax
0x180031fb6  cmp     [rbp+6C0h+hUSKey], 0
0x180031fbb  jz      loc_18003288C
0x180031fc1  cmp     [rbp+6C0h+var_6F4], 0
0x180031fc5  jnz     loc_180032B04
0x180031fcb  cmp     [rbp+6C0h+var_6F8], 0
0x180031fcf  jnz     loc_180032804
0x180031fd5  xor     eax, eax
0x180031fd7  cmp     [rbp+6C0h+var_6F0], eax
0x180031fda  setnz   al
0x180031fdd  mov     rcx, [rbp+6C0h+hUSKey]; hUSKey
0x180031fe1  lea     r9, [rbp+6C0h+pcValues]; pcValues
0x180031fe5  mov     [rsp+7C0h+enumRegFlags], eax; enumRegFlags
0x180031fe9  lea     r8, [rsp+7C0h+pcchMaxSubKeyLen]; pcchMaxSubKeyLen
0x180031fee  mov     rdx, rsi; pcSubKeys
0x180031ff1  mov     qword ptr [rsp+7C0h+fIgnoreHKCU], 0; pcchMaxValueNameLen
0x180031ffa  call    cs:__imp_SHRegQueryInfoUSKeyW
0x180032000  mov     ebx, eax
0x180032002  test    ebx, ebx
0x180032004  js      short loc_180032068
0x180032006  cmp     dword ptr [rsi], 0
0x180032009  jbe     short loc_180032068
0x18003200b  mov     eax, [rsp+7C0h+pcchMaxSubKeyLen]
0x18003200f  lea     eax, ds:22h[rax*2]
0x180032016  lea     ecx, [rax+7]
0x180032019  cmp     ecx, eax
0x18003201b  jnb     loc_180032896
0x180032021  mov     dword ptr [r13+0], 0FFFFFFFFh
0x180032029  mov     ebx, 80070216h
0x18003202e  jmp     short loc_180032068
0x180032030  test    r8, r8
0x180032033  lea     rcx, [r9-2]
0x180032037  mov     ebx, 8007007Ah
0x18003203c  cmovnz  rcx, r9
0x180032040  cmovnz  ebx, esi
0x180032043  mov     [rcx], si
0x180032046  jnz     loc_1800320F0
0x18003204c  test    ebx, ebx
0x18003204e  js      short loc_180032068
0x180032050  mov     edx, [rbp+6C0h+var_738]
0x180032053  mov     r8, [rbp+6C0h+var_6B8]
0x180032057  inc     edx
0x180032059  mov     [rbp+6C0h+var_738], edx
0x18003205c  inc     dword ptr [r8]
0x18003205f  cmp     edx, dword ptr [rbp+6C0h+phNewUSKey]
0x180032062  jb      loc_180032C43
0x180032068  mov     rcx, [rsp+7C0h+hRelativeUSKey]; hUSKey
0x18003206d  lea     rdi, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180032074  mov     r15, [rsp+7C0h+var_30]
0x18003207c  not     ebx
0x18003207e  mov     r14, [rsp+7C0h+var_28]
0x180032086  mov     r13, [rsp+7C0h+var_20]
0x18003208e  mov     r12, [rsp+7C0h+var_18]
0x180032096  mov     rsi, [rsp+7C0h+arg_8]
0x18003209e  shr     ebx, 1Fh
0x1800320a1  mov     [rsp+7C0h+var_768], rdi
0x1800320a6  test    rcx, rcx
0x1800320a9  jz      short loc_1800320BA
0x1800320ab  call    cs:__imp_SHRegCloseUSKey
0x1800320b1  mov     [rsp+7C0h+hRelativeUSKey], 0
0x1800320ba  mov     rcx, [rbp+6C0h+hUSKey]; hUSKey
0x1800320be  mov     [rbp+6C0h+var_708], rdi
0x1800320c2  mov     rdi, [rsp+7B0h]
0x1800320ca  test    rcx, rcx
0x1800320cd  jz      short loc_1800320D5
0x1800320cf  call    cs:__imp_SHRegCloseUSKey
0x1800320d5  mov     eax, ebx
0x1800320d7  mov     rcx, [rbp+6C0h+var_40]
0x1800320de  xor     rcx, rsp; StackCookie
0x1800320e1  call    __security_check_cookie
0x1800320e6  add     rsp, 7B8h
0x1800320ed  pop     rbx
0x1800320ee  pop     rbp
0x1800320ef  retn
0x1800320f0  mov     rax, [rsp+7C0h+var_768]
0x1800320f5  lea     rcx, [rsp+7C0h+var_768]
0x1800320fa  mov     rbx, [rbp+6C0h+hUSKey]
0x1800320fe  mov     [rbp+6C0h+var_6E0], rsi
0x180032102  mov     rax, [rax+10h]
0x180032106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003210b  test    rbx, rbx
0x18003210e  jz      loc_1800327CE
0x180032114  cmp     [rsp+7C0h+var_754], 0
0x180032119  jnz     loc_18003274D
0x18003211f  mov     eax, [rsp+7C0h+var_758]
0x180032123  lea     r9, [rbp+6C0h+var_6E0]; phNewUSKey
0x180032127  mov     [rsp+7C0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x18003212b  mov     r8, rbx; hRelativeUSKey
0x18003212e  mov     edx, 20019h; samDesired
0x180032133  mov     rcx, rdi; pwzPath
0x180032136  call    cs:__imp_SHRegOpenUSKeyW
0x18003213c  mov     ebx, eax
0x18003213e  test    eax, eax
0x180032140  jnz     loc_1800327DC
0x180032146  mov     rax, [rbp+6C0h+var_6E0]
0x18003214a  mov     [rsp+7C0h+hRelativeUSKey], rax
0x18003214f  cmp     [rsp+7C0h+hRelativeUSKey], 0
0x180032155  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x18003215c  mov     [rbp+6C0h+var_728], rax
0x180032160  lea     r13, [r14+18h]
0x180032164  mov     [rbp+6C0h+hUSkey], rsi
0x180032168  mov     [rbp+6C0h+var_718], r15d
0x18003216c  mov     [rbp+6C0h+var_714], esi
0x18003216f  mov     [rbp+6C0h+var_710], r12d
0x180032173  mov     [rsp+7C0h+pcchMaxSubKeyLen+4], esi
0x180032177  jz      loc_180032732
0x18003217d  cmp     [rsp+7C0h+var_754], 0
0x180032182  lea     r12, [r14+10h]
0x180032186  jnz     loc_180032B58
0x18003218c  cmp     [rsp+7C0h+var_758], 0
0x180032191  jnz     loc_180032739
0x180032197  cmp     [rsp+7C0h+var_750], 0
0x18003219c  mov     eax, esi
0x18003219e  setnz   al
0x1800321a1  mov     rcx, [rsp+7C0h+hRelativeUSKey]; hUSKey
0x1800321a6  lea     r8, [rsp+7C0h+pcchMaxSubKeyLen+4]; pcchMaxSubKeyLen
0x1800321ab  mov     [rsp+7C0h+enumRegFlags], eax; enumRegFlags
0x1800321af  mov     r9, r13; pcValues
0x1800321b2  mov     rdx, r12; pcSubKeys
0x1800321b5  mov     qword ptr [rsp+7C0h+fIgnoreHKCU], rsi; pcchMaxValueNameLen
0x1800321ba  call    cs:__imp_SHRegQueryInfoUSKeyW
0x1800321c0  test    eax, eax
0x1800321c2  jnz     loc_180032732
0x1800321c8  mov     edx, [r12]
0x1800321cc  test    edx, edx
0x1800321ce  jz      loc_180032728
0x1800321d4  mov     eax, [rsp+7C0h+pcchMaxSubKeyLen+4]
0x1800321d8  lea     eax, ds:12h[rax*2]
0x1800321df  lea     ecx, [rax+7]
0x1800321e2  cmp     ecx, eax
0x1800321e4  jb      loc_180032713
0x1800321ea  and     ecx, 0FFFFFFF8h
0x1800321ed  imul    edx, ecx
0x1800321f0  mov     [r14+14h], ecx
0x1800321f4  mov     ecx, edx; cb
0x1800321f6  mov     ebx, edx
0x1800321f8  call    cs:__imp_CoTaskMemAlloc
0x1800321fe  mov     r15, rax
0x180032201  test    rax, rax
0x180032204  jz      loc_180032A50
0x18003220a  mov     r8d, ebx; Size
0x18003220d  xor     edx, edx; Val
0x18003220f  mov     rcx, rax; void *
0x180032212  call    memset_0
0x180032217  mov     eax, [r12]
0x18003221b  mov     edx, esi; dwIndex
0x18003221d  mov     [rsp+7C0h+var_774], edx
0x180032221  mov     [r14], r15
0x180032224  mov     dword ptr [rbp+6C0h+var_6E0], eax
0x180032227  mov     [r12], esi
0x18003222b  test    eax, eax
0x18003222d  jz      loc_180032728
0x180032233  mov     rcx, [rsp+7C0h+hRelativeUSKey]; hUSKey
0x180032238  mov     [rsp+7C0h+pcchName], 104h
0x180032240  test    rcx, rcx
0x180032243  jz      short loc_180032292
0x180032245  cmp     [rsp+7C0h+var_754], 0
0x18003224a  jnz     loc_1800329EF
0x180032250  cmp     [rsp+7C0h+var_758], 0
0x180032255  mov     [rsp+7C0h+pcchName], 104h
0x18003225d  jnz     loc_180032709
0x180032263  cmp     [rsp+7C0h+var_750], 0
0x180032268  mov     eax, esi
0x18003226a  setnz   al
0x18003226d  mov     rcx, [rsp+7C0h+hRelativeUSKey]; hUSKey
0x180032272  lea     r9, [rsp+7C0h+pcchName]; pcchName
0x180032277  lea     r8, [rbp+6C0h+pwzName]; pwzName
0x18003227e  mov     [rsp+7C0h+fIgnoreHKCU], eax; enumRegFlags
0x180032282  call    cs:__imp_SHRegEnumUSKeyW
0x180032288  mov     ebx, eax
0x18003228a  test    ebx, ebx
0x18003228c  js      loc_180032720
0x180032292  mov     eax, [rsp+7C0h+pcchMaxSubKeyLen+4]
0x180032296  lea     rdi, [r15+0Ch]
0x18003229a  add     eax, 1
0x18003229d  mov     r8d, eax
0x1800322a0  jz      loc_180032BEF
0x1800322a6  cmp     r8, 7FFFFFFFh
0x1800322ad  ja      loc_180032B93
0x1800322b3  mov     ecx, 7FFFFFFEh
0x1800322b8  lea     rdx, [rbp+6C0h+pwzName]
0x1800322bf  mov     r9, rdi
0x1800322c2  test    rcx, rcx
0x1800322c5  jz      short loc_1800322E4
0x1800322c7  movzx   eax, word ptr [rdx]
0x1800322ca  test    ax, ax
0x1800322cd  jz      short loc_1800322E4
0x1800322cf  mov     [r9], ax
0x1800322d3  add     rdx, 2
0x1800322d7  add     r9, 2
0x1800322db  dec     rcx
0x1800322de  sub     r8, 1
0x1800322e2  jnz     short loc_1800322C2
0x1800322e4  test    r8, r8
0x1800322e7  lea     rcx, [r9-2]
0x1800322eb  mov     ebx, 8007007Ah
0x1800322f0  cmovnz  rcx, r9
0x1800322f4  cmovnz  ebx, esi
0x1800322f7  mov     [rcx], si
0x1800322fa  jz      loc_1800326F9
0x180032300  mov     rax, [rbp+6C0h+var_728]
0x180032304  lea     rcx, [rbp+6C0h+var_728]
0x180032308  mov     rbx, [rsp+7C0h+hRelativeUSKey]
0x18003230d  mov     [rbp+6C0h+var_730], rsi
0x180032311  mov     rax, [rax+10h]
0x180032315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003231a  test    rbx, rbx
0x18003231d  jz      loc_1800327E7
0x180032323  cmp     [rbp+6C0h+var_714], 0
0x180032327  jnz     loc_18003278D
0x18003232d  mov     eax, [rbp+6C0h+var_718]
0x180032330  lea     r9, [rbp+6C0h+var_730]; phNewUSKey
0x180032334  mov     [rsp+7C0h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180032338  mov     r8, rbx; hRelativeUSKey
  ... truncated ...
```
