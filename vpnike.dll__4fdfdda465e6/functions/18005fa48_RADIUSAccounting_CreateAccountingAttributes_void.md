# RADIUSAccounting::CreateAccountingAttributes(void)

- ea: `0x18005fa48`
- end: `0x18006056c`
- name: `?CreateAccountingAttributes@RADIUSAccounting@@IEAAKXZ`
- size: `2852`
- prototype: `__int64 __fastcall(RADIUSAccounting *this)`
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x180060880`

## callees

- `0x180007794`
- `0x1800077bc`
- `0x18000a0d0`
- `0x180014b90`
- `0x180020b78`
- `0x180020bdc`
- `0x18004b20c`
- `0x18004fca8`
- `0x18005fa48`
- `0x180064d14`
- `0x180065b18`
- `0x180065b9c`
- `0x1800662a8`
- `0x1800662cc`
- `0x1800662f8`
- `0x180066384`
- `0x1800665ec`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `msvcrt!_itoa_s` at `0x18005fec1`
- `msvcrt!_itoa_s` at `0x18006016f`
- `msvcrt!_itoa_s` at `0x18005fec1`
- `msvcrt!_itoa_s` at `0x18006016f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800604af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800604af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800604a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800604a1`
- `WS2_32!__imp_ntohl` at `0x18005ffd7`
- `WS2_32!__imp_ntohl` at `0x18005ffd7`
- `DSROLE!DsRoleFreeMemory` at `0x180060252`
- `DSROLE!DsRoleFreeMemory` at `0x180060252`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180060233`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180060233`

## string_xrefs

- `0x1800603e2`: `StringCopyWtoAAlloc failed: %d`
- `0x18005fbf5`: `RasAuthAttributeCreate failed with ERROR_NOT_ENOUGH_MEMORY`
- `0x180060526`: `CreateAccountingAttributes failed`

## pseudocode

```c
__int64 __fastcall RADIUSAccounting::CreateAccountingAttributes(RADIUSAccounting *this)
{
  __int64 v1; // rbx
  __int64 v3; // rdi
  __int64 v4; // rax
  int v5; // r12d
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 result; // rax
  int v9; // ebx
  __int64 i; // rax
  __int64 VendorSpecific; // r14
  int v12; // edx
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 v15; // rax
  _DWORD *v16; // rax
  __int64 j; // rax
  __int64 v18; // rcx
  _DWORD *v19; // rsi
  DWORD v20; // r15d
  PVOID *v21; // rcx
  unsigned int v22; // ebx
  DWORD inserted; // eax
  __int16 v24; // r11
  unsigned int v25; // ebx
  __int64 k; // rax
  __int64 v27; // rsi
  const WCHAR *v28; // rcx
  unsigned int v29; // r10d
  __int64 v30; // rax
  __int64 m; // rax
  DWORD v32; // eax
  int v33; // ecx
  __int64 v34; // rax
  unsigned int v35; // ebx
  __int64 v36; // r8
  __int64 v37; // rax
  int v38; // r9d
  const WCHAR *v39; // rcx
  IPv4Helper *v40; // rcx
  int v41; // r14d
  signed int v42; // eax
  IPv6Helper *v43; // rcx
  __int64 v44; // rax
  unsigned int v45; // ecx
  __int64 v46; // rax
  unsigned int v47; // ecx
  __int64 v48; // rax
  unsigned int v49; // ecx
  __int64 v50; // rcx
  unsigned int SecondsSince1970; // eax
  unsigned int v52; // r12d
  const WCHAR *v53; // rbx
  __int64 v54; // r9
  unsigned int v55; // eax
  unsigned int v56; // edi
  char *v57; // rbx
  __int64 v58; // rcx
  HANDLE ProcessHeap; // rax
  __int64 v60; // rcx
  size_t Size; // [rsp+20h] [rbp-E0h]
  size_t Sizea; // [rsp+20h] [rbp-E0h]
  size_t Sizeb; // [rsp+20h] [rbp-E0h]
  size_t Sizec; // [rsp+20h] [rbp-E0h]
  size_t Sized; // [rsp+20h] [rbp-E0h]
  size_t Sizee; // [rsp+20h] [rbp-E0h]
  size_t Sizef; // [rsp+20h] [rbp-E0h]
  LPCWCH lpWideCharStr; // [rsp+28h] [rbp-D8h]
  int v69; // [rsp+70h] [rbp-90h]
  PBYTE v70; // [rsp+78h] [rbp-88h] BYREF
  STRSAFE_PCNZCH pszSrc; // [rsp+80h] [rbp-80h]
  char Buffer[16]; // [rsp+88h] [rbp-78h] BYREF
  int v73; // [rsp+98h] [rbp-68h]
  WCHAR WideCharStr[8]; // [rsp+A0h] [rbp-60h] BYREF
  int v75; // [rsp+B0h] [rbp-50h]
  WCHAR v76[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v77; // [rsp+BCh] [rbp-44h]
  char v78[50]; // [rsp+BEh] [rbp-42h] BYREF
  wchar_t v79[40]; // [rsp+F0h] [rbp-10h] BYREF
  char pszDest[288]; // [rsp+140h] [rbp+40h] BYREF
  int v81; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v82[2044]; // [rsp+264h] [rbp+164h] BYREF

  v1 = *((_QWORD *)this + 1);
  v70 = 0;
  v3 = 0;
  v4 = *(_QWORD *)(v1 + 112);
  v5 = *(_DWORD *)(v4 + 1472);
  v69 = *(_DWORD *)(v4 + 40);
  v81 = 0;
  memset_0(v82, 0, sizeof(v82));
  v6 = *(_QWORD *)(v1 + 120);
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v3 = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
      }
      if ( (_QWORD)xmmword_1800AABC0 )
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gBaseTemplateFunc)(
          gBaseEtwContext,
          xmmword_1800AABC0,
          L"Failed to get authenticator attributes, cannot proceed accounting");
      return 13;
    }
    v9 = 0;
    for ( i = RasAuthAttributeGetFirst(25, v7); i; i = (__int64)RasAuthAttributeGetNext((_DWORD **)&v70, 25) )
      ++v9;
    for ( j = RasAuthAttributeGetFirst(22, v3); j; j = (__int64)RasAuthAttributeGetNext((_DWORD **)&v70, 22) )
      ++v9;
    VendorSpecific = RasAuthAttributeGetVendorSpecific(v18, 10, v3);
    if ( VendorSpecific )
      ++v9;
  }
  else
  {
    v9 = 0;
    VendorSpecific = 0;
  }
  v12 = v9 + 1;
  v13 = *(_QWORD *)(*((_QWORD *)this + 1) + 112LL);
  if ( !*(_WORD *)(v13 + 2172) )
    v12 = v9;
  v14 = (_QWORD *)(v13 + 2120);
  if ( v14 )
  {
    v15 = *v14 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *v14 == *(_QWORD *)&GUID_NULL.Data1 )
      v15 = v14[1] - *(_QWORD *)GUID_NULL.Data4;
    if ( v15 )
      ++v12;
  }
  v16 = RasAuthAttributeCreate(v12 + 44);
  *((_QWORD *)this + 5) = v16;
  if ( !v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
    }
    if ( (_QWORD)xmmword_1800AABC0 )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gBaseTemplateFunc)(
        gBaseEtwContext,
        xmmword_1800AABC0,
        L"RasAuthAttributeCreate failed with ERROR_NOT_ENOUGH_MEMORY");
    return 8;
  }
  v19 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 48LL))(*((_QWORD *)this + 1));
  if ( v19 )
  {
    v22 = 0;
    if ( *v19 )
    {
      do
      {
        LODWORD(Size) = v19[4 * v22 + 1];
        v20 = RasAuthAttributeInsert(v22, *((_QWORD *)this + 5), v19[4 * v22], 0, Size, *(LPCWCH *)&v19[4 * v22 + 2]);
        if ( v20 )
          goto LABEL_122;
      }
      while ( v19[4 * ++v22] );
    }
    inserted = RasAuthAttributeInsertNAS(v22, *((_QWORD *)this + 5));
    v24 = 0;
    v20 = inserted;
    if ( inserted )
      goto LABEL_122;
    v25 = v22 + 1;
    if ( v3 )
    {
      for ( k = RasAuthAttributeGetFirst(25, v3); k; k = (__int64)RasAuthAttributeGetNext((_DWORD **)&v70, 25) )
      {
        LODWORD(Size) = *(_DWORD *)(k + 4);
        v20 = RasAuthAttributeInsert(v25, *((_QWORD *)this + 5), *(_DWORD *)k, 0, Size, *(LPCWCH *)(k + 8));
        if ( v20 )
          goto LABEL_122;
        ++v25;
      }
    }
    v27 = -1;
    v28 = (const WCHAR *)(*(_QWORD *)(*((_QWORD *)this + 1) + 112LL) + 2172LL);
    if ( v24 != *v28 )
    {
      v29 = v25;
      v30 = -1;
      ++v25;
      do
        ++v30;
      while ( v28[v30] != v24 );
      LODWORD(Size) = v30;
      v20 = RasAuthAttributeInsert(v29, *((_QWORD *)this + 5), 25, 1, Size, v28);
      if ( v20 )
        goto LABEL_122;
    }
    if ( v3 )
    {
      for ( m = RasAuthAttributeGetFirst(22, v3); m; m = (__int64)RasAuthAttributeGetNext((_DWORD **)&v70, 22) )
      {
        LODWORD(Size) = *(_DWORD *)(m + 4);
        v20 = RasAuthAttributeInsert(v25, *((_QWORD *)this + 5), *(_DWORD *)m, 0, Size, *(LPCWCH *)(m + 8));
        if ( v20 )
          goto LABEL_122;
        ++v25;
      }
    }
    if ( VendorSpecific )
    {
      LODWORD(Size) = *(_DWORD *)(VendorSpecific + 4);
      v32 = RasAuthAttributeInsert(
              v25,
              *((_QWORD *)this + 5),
              *(_DWORD *)VendorSpecific,
              0,
              Size,
              *(LPCWCH *)(VendorSpecific + 8));
      VendorSpecific = 0;
      v20 = v32;
      if ( v32 )
        goto LABEL_123;
      ++v25;
    }
    v33 = *((_DWORD *)this + 14);
    *(_OWORD *)Buffer = 0;
    v73 = 0;
    _itoa_s(v33, Buffer, 0x14u, 10);
    v34 = -1;
    do
      ++v34;
    while ( Buffer[v34] != (_BYTE)VendorSpecific );
    LODWORD(Size) = v34;
    v20 = RasAuthAttributeInsert(v25, *((_QWORD *)this + 5), 44, 0, Size, (LPCWCH)Buffer);
    if ( v20 )
      goto LABEL_123;
    v35 = v25 + 1;
    memset_0(pszDest, 0, 0x111u);
    v36 = *(_QWORD *)(*((_QWORD *)this + 1) + 120LL);
    if ( !v36 || (StringCchCopyA(pszDest, 0x111u, (STRSAFE_LPCSTR)(v36 + 8)), pszDest[0] == (_BYTE)VendorSpecific) )
    {
      v39 = (const WCHAR *)(*(_QWORD *)(*((_QWORD *)this + 1) + 112LL) + 2686LL);
      if ( (_WORD)VendorSpecific == *v39 )
      {
LABEL_76:
        v40 = *(IPv4Helper **)(*((_QWORD *)this + 1) + 32LL);
        if ( !v40 )
        {
          v41 = v69;
          goto LABEL_83;
        }
        v41 = v69;
        if ( !IPv4Helper::DoNegotiate(v40) || v5 == 2 && v69 != 2 )
        {
LABEL_83:
          v43 = *(IPv6Helper **)(*((_QWORD *)this + 1) + 40LL);
          if ( v43 && IPv6Helper::DoNegotiate(v43) && (v5 != 2 || v41 == 2) )
          {
            LODWORD(Sizea) = 8;
            VendorSpecific = 0;
            v20 = RasAuthAttributeInsert(
                    v35,
                    *((_QWORD *)this + 5),
                    96,
                    0,
                    Sizea,
                    (LPCWCH)(*(_QWORD *)(*((_QWORD *)this + 1) + 40LL) + 60LL));
            if ( v20 )
              goto LABEL_123;
            LODWORD(Sizeb) = 8;
            v20 = RasAuthAttributeInsert(
                    v35 + 1,
                    *((_QWORD *)this + 5),
                    97,
                    0,
                    Sizeb,
                    (LPCWCH)(*(_QWORD *)(*((_QWORD *)this + 1) + 40LL) + 52LL));
            if ( v20 )
              goto LABEL_123;
            v35 += 2;
          }
          else
          {
            VendorSpecific = 0;
          }
          v44 = *((_QWORD *)this + 1);
          if ( *(_DWORD *)(v44 + 100) )
          {
            v45 = v35;
            LODWORD(Sizea) = 4;
            ++v35;
            v20 = RasAuthAttributeInsert(v45, *((_QWORD *)this + 5), 27, 0, Sizea, (LPCWCH)*(unsigned int *)(v44 + 100));
            if ( v20 )
              goto LABEL_123;
          }
          v46 = *((_QWORD *)this + 1);
          if ( *(_DWORD *)(v46 + 96) )
          {
            v47 = v35++;
            LODWORD(Sizea) = 4;
            v20 = RasAuthAttributeInsert(v47, *((_QWORD *)this + 5), 28, 0, Sizea, (LPCWCH)*(unsigned int *)(v46 + 96));
            if ( v20 )
              goto LABEL_123;
          }
          v48 = *((_QWORD *)this + 1);
          if ( *(_DWORD *)(v48 + 136) != -1 )
          {
            v49 = v35++;
            LODWORD(Sizea) = 4;
            v20 = RasAuthAttributeInsert(v49, *((_QWORD *)this + 5), 62, 0, Sizea, (LPCWCH)*(unsigned int *)(v48 + 136));
            if ( v20 )
              goto LABEL_123;
          }
          v50 = *((_QWORD *)this + 1);
          *(_OWORD *)WideCharStr = 0;
          v75 = 0;
          _itoa_s(*(_DWORD *)(v50 + 140), (char *)WideCharStr, 0x14u, 10);
          do
            ++v27;
          while ( *((_BYTE *)WideCharStr + v27) );
          LODWORD(Sizea) = v27;
          v20 = RasAuthAttributeInsert(v35, *((_QWORD *)this + 5), 50, 0, Sizea, WideCharStr);
          if ( v20 )
            goto LABEL_123;
          LODWORD(Sizec) = 4;
          v20 = RasAuthAttributeInsert(
                  v35 + 1,
                  *((_QWORD *)this + 5),
                  51,
                  0,
                  Sizec,
                  (LPCWCH)*(unsigned int *)(*((_QWORD *)this + 1) + 144LL));
          if ( v20 )
            goto LABEL_123;
          SecondsSince1970 = GetSecondsSince1970();
          LODWORD(Sized) = 4;
          v20 = RasAuthAttributeInsert(v35 + 2, *((_QWORD *)this + 5), 55, 0, Sized, (LPCWCH)SecondsSince1970);
          if ( v20 )
            goto LABEL_123;
          v52 = v35 + 3;
          if ( *(_BYTE *)(*((_QWORD *)this + 2) + 84LL) )
          {
            v53 = (const WCHAR *)(v20 + 1);
          }
          else
          {
            v70 = 0;
            if ( DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &v70) )
              goto LABEL_108;
            v53 = (const WCHAR *)(3LL - (((*(_DWORD *)v70 - 1) & 0xFFFFFFFD) != 0));
            DsRoleFreeMemory(v70);
          }
          LODWORD(Sizee) = 4;
          v20 = RasAuthAttributeInsert(v52, *((_QWORD *)this + 5), 45, 0, Sizee, v53);
          if ( v20 )
            goto LABEL_123;
          ++v52;
LABEL_108:
          wcscpy(v79, L"{00000000-0000-0000-0000-00000000000}");
          v79[39] = 0;
          v54 = *(_QWORD *)(*((_QWORD *)this + 1) + 112LL);
          LODWORD(lpWideCharStr) = *(unsigned __int16 *)(v54 + 2126);
          LODWORD(Sizee) = *(unsigned __int16 *)(v54 + 2124);
          StringCchPrintfW(
            v79,
            0x28u,
            L"{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
            *(unsigned int *)(v54 + 2120),
            Sizee,
            lpWideCharStr,
            *(unsigned __int8 *)(v54 + 2128),
            *(unsigned __int8 *)(v54 + 2129),
            *(unsigned __int8 *)(v54 + 2130),
            *(unsigned __int8 *)(v54 + 2131),
            *(unsigned __int8 *)(v54 + 2132),
            *(unsigned __int8 *)(v54 + 2133),
            *(unsigned __int8 *)(v54 + 2134),
            *(unsigned __int8 *)(v54 + 2135));
          VendorSpecific = 0;
          pszSrc = 0;
          v55 = StringCopyWtoAAlloc(v79);
          v56 = v55;
          if ( v55 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids, v55);
            }
            if ( (_QWORD)xmmword_1800AABC0 )
            {
              LOWORD(v81) = 0;
              FormatRRASErrorString(&v81, L"StringCopyWtoAAlloc failed: %d", v56);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
                gBaseEtwContext,
                xmmword_1800AABC0,
                &v81);
            }
          }
          else
          {
            *(_DWORD *)v76 = 922812416;
            v57 = (char *)pszSrc;
            v77 = 10560;
            StringCbCopyNA(v78, 0x2Cu, pszSrc, 0x28u);
            v58 = -1;
            *(_DWORD *)(*((_QWORD *)this + 5) + 16LL * v52) = -1;
            do
              ++v58;
            while ( v78[v58] );
            LODWORD(Sizef) = v58 + 7;
            v20 = RasAuthAttributeInsert(v52, *((_QWORD *)this + 5), 26, 0, Sizef, v76);
            if ( v20 )
              goto LABEL_123;
            ++v52;
            if ( v57 )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v57);
            }
          }
          v60 = 2LL * v52;
          *(_DWORD *)(*((_QWORD *)this + 5) + 8 * v60) = 0;
          *(_DWORD *)(*((_QWORD *)this + 5) + 8 * v60 + 4) = 0;
          *(_QWORD *)(*((_QWORD *)this + 5) + 8 * v60 + 8) = 0;
          return 0;
        }
        v42 = ntohl(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 32LL) + 20LL));
        LODWORD(Sizea) = 4;
        v20 = RasAuthAttributeInsert(v35, *((_QWORD *)this + 5), 8, 0, Sizea, (LPCWCH)v42);
        if ( !v20 )
        {
          ++v35;
          goto LABEL_83;
        }
LABEL_122:
        VendorSpecific = 0;
        goto LABEL_123;
      }
      v37 = -1;
      do
        ++v37;
      while ( v39[v37] != (_WORD)VendorSpecific );
      v38 = 1;
    }
    else
    {
      v37 = -1;
      do
        ++v37;
      while ( pszDest[v37] != (_BYTE)VendorSpecific );
      v38 = 0;
      v39 = (const WCHAR *)pszDest;
    }
    LODWORD(Sizea) = v37;
    v20 = RasAuthAttributeInsert(v35, *((_QWORD *)this + 5), 1, v38, Sizea, v39);
    if ( v20 )
      goto LABEL_123;
    ++v35;
    goto LABEL_76;
  }
  v20 = 13;
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  VendorSpecific = 0;
  if ( !(_QWORD)xmmword_1800AABC0 )
    goto LABEL_124;
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gBaseTemplateFunc)(
    gBaseEtwContext,
    xmmword_1800AABC0,
    L"Failed to get User attributes, cannot proceed accounting");
LABEL_123:
  v21 = (PVOID *)WPP_GLOBAL_Control;
LABEL_124:
  if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 7) & 0x20000000) != 0 && *((_BYTE *)v21 + 25) )
    WPP_SF_(v21[2], 39, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
  if ( (_QWORD)xmmword_1800AABC0 )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gBaseTemplateFunc)(
      gBaseEtwContext,
      xmmword_1800AABC0,
      L"CreateAccountingAttributes failed");
  RasAuthAttributeDestroy(*((_DWORD **)this + 5));
  result = v20;
  *((_QWORD *)this + 5) = VendorSpecific;
  return result;
}

```

## disassembly

```asm
0x18005fa48  push    rbp
0x18005fa4a  push    rbx
0x18005fa4b  push    rsi
0x18005fa4c  push    rdi
0x18005fa4d  push    r12
0x18005fa4f  push    r13
0x18005fa51  push    r14
0x18005fa53  push    r15
0x18005fa55  lea     rbp, [rsp-978h]
0x18005fa5d  sub     rsp, 0A78h
0x18005fa64  mov     rax, cs:__security_cookie
0x18005fa6b  xor     rax, rsp
0x18005fa6e  mov     [rbp+9B0h+var_50], rax
0x18005fa75  mov     rbx, [rcx+8]
0x18005fa79  mov     r13, rcx
0x18005fa7c  xor     r15d, r15d
0x18005fa7f  xor     edx, edx; Val
0x18005fa81  mov     r8d, 7FCh; Size
0x18005fa87  mov     [rsp+0AB0h+var_A38], r15
0x18005fa8c  mov     edi, r15d
0x18005fa8f  mov     rax, [rbx+70h]
0x18005fa93  mov     ecx, [rax+28h]
0x18005fa96  mov     r12d, [rax+5C0h]
0x18005fa9d  mov     [rsp+0AB0h+var_A40], ecx
0x18005faa1  lea     rcx, [rbp+9B0h+var_84C]; void *
0x18005faa8  mov     [rbp+9B0h+var_850], r15d
0x18005faaf  call    memset_0
0x18005fab4  mov     rcx, [rbx+78h]
0x18005fab8  lea     esi, [r15+19h]
0x18005fabc  test    rcx, rcx
0x18005fabf  jz      loc_18005FB55
0x18005fac5  mov     rax, [rcx]
0x18005fac8  mov     rax, [rax+10h]
0x18005facc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fad1  mov     rdi, rax
0x18005fad4  test    rax, rax
0x18005fad7  jnz     short loc_18005FB3E
0x18005fad9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fae0  lea     rbx, WPP_GLOBAL_Control
0x18005fae7  cmp     rcx, rbx
0x18005faea  jz      short loc_18005FB0E
0x18005faec  test    dword ptr [rcx+1Ch], 20000000h
0x18005faf3  jz      short loc_18005FB0E
0x18005faf5  cmp     byte ptr [rcx+19h], 1
0x18005faf9  jb      short loc_18005FB0E
0x18005fafb  mov     rcx, [rcx+10h]
0x18005faff  lea     edx, [rsi+0Ah]
0x18005fb02  lea     r8, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids
0x18005fb09  call    WPP_SF_
0x18005fb0e  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005fb15  test    rdx, rdx
0x18005fb18  jz      short loc_18005FB34
0x18005fb1a  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005fb21  lea     r8, aFailedToGetAut; "Failed to get authenticator attributes,"...
0x18005fb28  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005fb2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb34  mov     eax, 0Dh
0x18005fb39  jmp     loc_180060549
0x18005fb3e  lea     r8, [rsp+0AB0h+var_A38]
0x18005fb43  mov     rdx, rdi
0x18005fb46  mov     ecx, esi
0x18005fb48  mov     ebx, r15d
0x18005fb4b  call    RasAuthAttributeGetFirst
0x18005fb50  jmp     loc_18005FC20
0x18005fb55  mov     ebx, r15d
0x18005fb58  mov     r14, r15
0x18005fb5b  mov     rax, [r13+8]
0x18005fb5f  lea     edx, [rbx+1]
0x18005fb62  mov     rcx, [rax+70h]
0x18005fb66  cmp     r15w, [rcx+87Ch]
0x18005fb6e  cmovz   edx, ebx
0x18005fb71  add     rcx, 848h
0x18005fb78  jz      short loc_18005FB98
0x18005fb7a  mov     rax, [rcx]
0x18005fb7d  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18005fb84  jnz     short loc_18005FB91
0x18005fb86  mov     rax, [rcx+8]
0x18005fb8a  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18005fb91  test    rax, rax
0x18005fb94  jz      short loc_18005FB98
0x18005fb96  inc     edx
0x18005fb98  lea     ecx, [rdx+2Ch]
0x18005fb9b  call    RasAuthAttributeCreate
0x18005fba0  mov     [r13+28h], rax
0x18005fba4  test    rax, rax
0x18005fba7  jnz     loc_18005FC6B
0x18005fbad  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fbb4  lea     rbx, WPP_GLOBAL_Control
0x18005fbbb  cmp     rcx, rbx
0x18005fbbe  jz      short loc_18005FBE2
0x18005fbc0  test    dword ptr [rcx+1Ch], 20000000h
0x18005fbc7  jz      short loc_18005FBE2
0x18005fbc9  cmp     byte ptr [rcx+19h], 1
0x18005fbcd  jb      short loc_18005FBE2
0x18005fbcf  mov     rcx, [rcx+10h]
0x18005fbd3  lea     edx, [rax+24h]
0x18005fbd6  lea     r8, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids
0x18005fbdd  call    WPP_SF_
0x18005fbe2  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005fbe9  test    rdx, rdx
0x18005fbec  jz      short loc_18005FC08
0x18005fbee  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005fbf5  lea     r8, aRasauthattribu_1; "RasAuthAttributeCreate failed with ERRO"...
0x18005fbfc  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005fc03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc08  mov     eax, 8
0x18005fc0d  jmp     loc_180060549
0x18005fc12  inc     ebx
0x18005fc14  lea     rcx, [rsp+0AB0h+var_A38]
0x18005fc19  mov     edx, esi
0x18005fc1b  call    RasAuthAttributeGetNext
0x18005fc20  test    rax, rax
0x18005fc23  jnz     short loc_18005FC12
0x18005fc25  lea     r8, [rsp+0AB0h+var_A38]
0x18005fc2a  mov     rdx, rdi
0x18005fc2d  lea     ecx, [rax+16h]
0x18005fc30  call    RasAuthAttributeGetFirst
0x18005fc35  jmp     short loc_18005FC48
0x18005fc37  inc     ebx
0x18005fc39  lea     rcx, [rsp+0AB0h+var_A38]
0x18005fc3e  mov     edx, 16h
0x18005fc43  call    RasAuthAttributeGetNext
0x18005fc48  test    rax, rax
0x18005fc4b  jnz     short loc_18005FC37
0x18005fc4d  mov     r8, rdi
0x18005fc50  lea     edx, [rax+0Ah]
0x18005fc53  call    RasAuthAttributeGetVendorSpecific
0x18005fc58  mov     r14, rax
0x18005fc5b  test    rax, rax
0x18005fc5e  jz      loc_18005FB5B
0x18005fc64  inc     ebx
0x18005fc66  jmp     loc_18005FB5B
0x18005fc6b  mov     rcx, [r13+8]
0x18005fc6f  mov     rax, [rcx]
0x18005fc72  mov     rax, [rax+30h]
0x18005fc76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc7b  mov     rsi, rax
0x18005fc7e  lea     rax, WPP_GLOBAL_Control
0x18005fc85  test    rsi, rsi
0x18005fc88  jnz     short loc_18005FCF5
0x18005fc8a  lea     r15d, [rsi+0Dh]
0x18005fc8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fc95  cmp     rcx, rax
0x18005fc98  jz      short loc_18005FCC3
0x18005fc9a  test    dword ptr [rcx+1Ch], 20000000h
0x18005fca1  jz      short loc_18005FCC3
0x18005fca3  cmp     byte ptr [rcx+19h], 1
0x18005fca7  jb      short loc_18005FCC3
0x18005fca9  mov     rcx, [rcx+10h]
0x18005fcad  lea     edx, [rsi+25h]
0x18005fcb0  lea     r8, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids
0x18005fcb7  call    WPP_SF_
0x18005fcbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fcc3  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18005fcca  xor     r14d, r14d
0x18005fccd  test    rdx, rdx
0x18005fcd0  jz      loc_1800604E3
0x18005fcd6  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18005fcdd  lea     r8, aFailedToGetUse; "Failed to get User attributes, cannot p"...
0x18005fce4  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005fceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcf0  jmp     loc_1800604DC
0x18005fcf5  mov     ebx, r15d
0x18005fcf8  cmp     [rsi], r15d
0x18005fcfb  jz      short loc_18005FD41
0x18005fcfd  mov     rdx, [r13+28h]; int
0x18005fd01  xor     r9d, r9d; int
0x18005fd04  mov     r8d, ebx
0x18005fd07  mov     ecx, ebx; int
0x18005fd09  add     r8, r8
0x18005fd0c  mov     rax, [rsi+r8*8+8]
0x18005fd11  mov     [rsp+0AB0h+lpWideCharStr], rax; lpWideCharStr
0x18005fd16  mov     eax, [rsi+r8*8+4]
0x18005fd1b  mov     r8d, [rsi+r8*8]; int
0x18005fd1f  mov     dword ptr [rsp+0AB0h+Size], eax; Size
0x18005fd23  call    RasAuthAttributeInsert
0x18005fd28  xor     ecx, ecx
0x18005fd2a  mov     r15d, eax
0x18005fd2d  test    eax, eax
0x18005fd2f  jnz     loc_1800604D9
0x18005fd35  inc     ebx
0x18005fd37  mov     eax, ebx
0x18005fd39  add     rax, rax
0x18005fd3c  cmp     [rsi+rax*8], ecx
0x18005fd3f  jnz     short loc_18005FCFD
0x18005fd41  mov     rdx, [r13+28h]
0x18005fd45  mov     ecx, ebx
0x18005fd47  call    RasAuthAttributeInsertNAS
0x18005fd4c  xor     r11d, r11d
0x18005fd4f  mov     r15d, eax
0x18005fd52  test    eax, eax
0x18005fd54  jnz     loc_1800604D9
0x18005fd5a  inc     ebx
0x18005fd5c  test    rdi, rdi
0x18005fd5f  jz      short loc_18005FDB6
0x18005fd61  lea     r8, [rsp+0AB0h+var_A38]
0x18005fd66  mov     rdx, rdi
0x18005fd69  lea     ecx, [rax+19h]
0x18005fd6c  call    RasAuthAttributeGetFirst
0x18005fd71  jmp     short loc_18005FDB1
0x18005fd73  mov     rcx, [rax+8]
0x18005fd77  xor     r9d, r9d; int
0x18005fd7a  mov     r8d, [rax]; int
0x18005fd7d  mov     rdx, [r13+28h]; int
0x18005fd81  mov     [rsp+0AB0h+lpWideCharStr], rcx; lpWideCharStr
0x18005fd86  mov     ecx, [rax+4]
0x18005fd89  mov     dword ptr [rsp+0AB0h+Size], ecx; Size
0x18005fd8d  mov     ecx, ebx; int
0x18005fd8f  call    RasAuthAttributeInsert
0x18005fd94  xor     r11d, r11d
0x18005fd97  mov     r15d, eax
0x18005fd9a  test    eax, eax
0x18005fd9c  jnz     loc_1800604D9
0x18005fda2  inc     ebx
0x18005fda4  lea     edx, [rax+19h]
0x18005fda7  lea     rcx, [rsp+0AB0h+var_A38]
0x18005fdac  call    RasAuthAttributeGetNext
0x18005fdb1  test    rax, rax
0x18005fdb4  jnz     short loc_18005FD73
0x18005fdb6  mov     rax, [r13+8]
0x18005fdba  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005fdbe  mov     rcx, [rax+70h]
0x18005fdc2  add     rcx, 87Ch
0x18005fdc9  cmp     r11w, [rcx]
0x18005fdcd  jz      short loc_18005FE0B
0x18005fdcf  mov     r10d, ebx
0x18005fdd2  mov     rax, rsi
0x18005fdd5  inc     ebx
0x18005fdd7  inc     rax
0x18005fdda  cmp     [rcx+rax*2], r11w
0x18005fddf  jnz     short loc_18005FDD7
0x18005fde1  mov     rdx, [r13+28h]; int
0x18005fde5  mov     r9d, 1; int
0x18005fdeb  mov     [rsp+0AB0h+lpWideCharStr], rcx; lpWideCharStr
0x18005fdf0  mov     ecx, r10d; int
0x18005fdf3  mov     dword ptr [rsp+0AB0h+Size], eax; Size
0x18005fdf7  lea     r8d, [r9+18h]; int
0x18005fdfb  call    RasAuthAttributeInsert
0x18005fe00  mov     r15d, eax
0x18005fe03  test    eax, eax
0x18005fe05  jnz     loc_1800604D9
0x18005fe0b  test    rdi, rdi
0x18005fe0e  jz      short loc_18005FE6E
0x18005fe10  mov     rdx, rdi
0x18005fe13  lea     r8, [rsp+0AB0h+var_A38]
0x18005fe18  mov     edi, 16h
0x18005fe1d  mov     ecx, edi
0x18005fe1f  call    RasAuthAttributeGetFirst
0x18005fe24  jmp     short loc_18005FE60
0x18005fe26  mov     rcx, [rax+8]
0x18005fe2a  xor     r9d, r9d; int
0x18005fe2d  mov     r8d, [rax]; int
0x18005fe30  mov     rdx, [r13+28h]; int
0x18005fe34  mov     [rsp+0AB0h+lpWideCharStr], rcx; lpWideCharStr
0x18005fe39  mov     ecx, [rax+4]
0x18005fe3c  mov     dword ptr [rsp+0AB0h+Size], ecx; Size
0x18005fe40  mov     ecx, ebx; int
0x18005fe42  call    RasAuthAttributeInsert
0x18005fe47  mov     r15d, eax
0x18005fe4a  test    eax, eax
0x18005fe4c  jnz     loc_1800604D9
0x18005fe52  inc     ebx
0x18005fe54  lea     rcx, [rsp+0AB0h+var_A38]
0x18005fe59  mov     edx, edi
0x18005fe5b  call    RasAuthAttributeGetNext
0x18005fe60  test    rax, rax
0x18005fe63  jnz     short loc_18005FE26
0x18005fe65  test    r15d, r15d
0x18005fe68  jnz     loc_1800604D9
0x18005fe6e  test    r14, r14
0x18005fe71  jz      short loc_18005FEA5
0x18005fe73  mov     rax, [r14+8]
0x18005fe77  xor     r9d, r9d; int
0x18005fe7a  mov     r8d, [r14]; int
0x18005fe7d  mov     ecx, ebx; int
0x18005fe7f  mov     rdx, [r13+28h]; int
0x18005fe83  mov     [rsp+0AB0h+lpWideCharStr], rax; lpWideCharStr
0x18005fe88  mov     eax, [r14+4]
0x18005fe8c  mov     dword ptr [rsp+0AB0h+Size], eax; Size
0x18005fe90  call    RasAuthAttributeInsert
0x18005fe95  xor     r14d, r14d
0x18005fe98  mov     r15d, eax
0x18005fe9b  test    eax, eax
0x18005fe9d  jnz     loc_1800604DC
0x18005fea3  inc     ebx
0x18005fea5  mov     ecx, [r13+38h]; Value
0x18005fea9  lea     rdx, [rbp+9B0h+Buffer]; Buffer
0x18005fead  xor     eax, eax
0x18005feaf  xorps   xmm0, xmm0
0x18005feb2  movups  xmmword ptr [rbp+9B0h+Buffer], xmm0
0x18005feb6  mov     [rbp+9B0h+var_A18], eax
0x18005feb9  lea     r9d, [rax+0Ah]; Radix
0x18005febd  lea     r8d, [rax+14h]; BufferCount
0x18005fec1  call    cs:__imp__itoa_s
0x18005fec7  lea     rcx, [rbp+9B0h+Buffer]
0x18005fecb  mov     rax, rsi
0x18005fece  inc     rax
0x18005fed1  cmp     [rcx+rax], r14b
0x18005fed5  jnz     short loc_18005FECE
0x18005fed7  mov     rdx, [r13+28h]; int
  ... truncated ...
```
