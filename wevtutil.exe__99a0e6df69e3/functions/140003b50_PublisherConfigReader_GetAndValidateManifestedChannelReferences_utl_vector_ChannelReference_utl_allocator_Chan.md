# PublisherConfigReader::GetAndValidateManifestedChannelReferences(utl::vector<ChannelReference,utl::allocator<ChannelReference>> &)

- ea: `0x140003b50`
- end: `0x140004aa8`
- name: `?GetAndValidateManifestedChannelReferences@PublisherConfigReader@@QEBA_NAEAV?$vector@UChannelReference@@V?$allocator@UChannelReference@@@utl@@@utl@@@Z`
- size: `3928`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x14000adf0`
- `0x140017fbc`
- `0x14001e0c0`

## callees

- `0x140003800`
- `0x140003b50`
- `0x140004ab0`
- `0x140004ae0`
- `0x140004b20`
- `0x140004cb0`
- `0x140005600`
- `0x140006cd0`
- `0x140006db0`
- `0x140007fd0`
- `0x14000cc80`
- `0x14000d6e8`
- `0x14001aa58`
- `0x140021b00`
- `0x140022cec`
- `0x14002c814`
- `0x14002c880`
- `0x14002c97c`
- `0x14002ca10`
- `0x14002f6c8`
- `0x140031810`
- `0x140031828`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x140003fb1`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x140003fb1`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400044d6`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400044d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003be2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004470`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003be2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004470`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003bd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004419`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004462`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003bd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004419`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004462`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140004427`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140004427`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003d1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004314`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003d1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004314`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140004366`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140004366`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003dc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003dd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400046f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004a9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003dc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003dd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400046f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004a9b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003ea7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140004691`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400046d5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003ea7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140004691`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400046d5`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140003d05`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140004303`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140003d05`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140004303`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall PublisherConfigReader::GetAndValidateManifestedChannelReferences(
        __int64 a1,
        const struct std::nothrow_t **a2)
{
  const struct std::nothrow_t **v2; // r12
  __int64 v3; // r14
  const struct std::nothrow_t *v4; // rbx
  const struct std::nothrow_t *v5; // rcx
  __int64 v6; // rdi
  char *v7; // rsi
  HANDLE ProcessHeap; // rax
  __int64 v9; // rax
  _DWORD *v10; // rdi
  unsigned int v11; // ebx
  unsigned int v12; // esi
  const char *v13; // r8
  HKEY v14; // rcx
  void *hTransaction; // rdx
  unsigned int PublishersRegKey; // edi
  HKEY v17; // rbx
  void *v18; // rdi
  HKEY *v19; // rax
  LSTATUS ValueW; // eax
  const char *v22; // r8
  PVOID *v23; // rcx
  __int64 v24; // rcx
  const char *v25; // r8
  __int64 v26; // rsi
  const struct std::nothrow_t *v27; // rdi
  const struct std::nothrow_t *v28; // rdx
  const char *v29; // r8
  unsigned __int64 v30; // rbx
  const struct std::nothrow_t *v31; // rbx
  unsigned __int64 v32; // rdi
  unsigned __int64 v33; // rdi
  unsigned __int64 v34; // rax
  unsigned __int64 v35; // rax
  __int64 v36; // rdi
  char *v37; // rax
  __int64 v38; // rcx
  char *v39; // r14
  char *v40; // r15
  const struct std::nothrow_t *v41; // r12
  unsigned __int64 v42; // rdi
  __int64 i; // r11
  __int64 v44; // r11
  char *v45; // rdi
  const struct std::nothrow_t *v46; // r9
  __int64 j; // r8
  __int64 v48; // rcx
  __int64 v49; // r8
  unsigned __int16 v50; // di
  __int64 v51; // rbx
  void *v52; // rax
  unsigned int v53; // eax
  const char *v54; // r8
  unsigned int v55; // edi
  HKEY v56; // r15
  LSTATUS v57; // eax
  unsigned __int64 v58; // rsi
  char *v59; // rdx
  LPBYTE v60; // rax
  unsigned __int64 v61; // rdi
  _QWORD *v62; // r14
  unsigned __int64 v63; // rcx
  __int64 v64; // rcx
  unsigned __int64 v65; // rax
  unsigned __int64 v66; // rax
  SIZE_T v67; // r12
  HANDLE v68; // rax
  char *v69; // r12
  LPBYTE v70; // rdx
  LPBYTE v71; // r13
  HANDLE v72; // rax
  unsigned __int64 v73; // rcx
  char *v74; // rdi
  _WORD *v75; // rcx
  size_t v76; // r14
  char *v77; // rdi
  LPBYTE v78; // rax
  unsigned __int64 v79; // rsi
  _QWORD *v80; // r15
  unsigned __int64 v81; // rcx
  __int64 v82; // rcx
  unsigned __int64 v83; // rax
  unsigned __int64 v84; // rax
  __int64 v85; // r13
  char *v86; // rax
  char *v87; // r12
  __int64 v88; // rdi
  size_t v89; // rcx
  _WORD *v90; // rcx
  LPBYTE v91; // rax
  __int64 v92; // rcx
  BYTE *v93; // rcx
  unsigned __int64 v94; // rdi
  unsigned __int64 v95; // r8
  LSTATUS v96; // eax
  const char *v97; // r8
  unsigned int v98; // edi
  LSTATUS v99; // eax
  const char *v100; // r8
  unsigned int v101; // edi
  _WORD *v102; // rcx
  __int64 v103; // r14
  const char *v104; // r8
  PVOID *v105; // rcx
  PVOID *v106; // rcx
  const char *v107; // r8
  WCHAR SubKey[2]; // [rsp+40h] [rbp-79h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-75h] BYREF
  unsigned int pvData; // [rsp+48h] [rbp-71h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-6Dh] BYREF
  unsigned __int16 v112; // [rsp+50h] [rbp-69h]
  HKEY hkey; // [rsp+58h] [rbp-61h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-59h] BYREF
  __int64 v115; // [rsp+68h] [rbp-51h]
  const struct std::nothrow_t **v116; // [rsp+70h] [rbp-49h]
  _BYTE v117[40]; // [rsp+78h] [rbp-41h] BYREF
  __int64 v118; // [rsp+A0h] [rbp-19h]
  __int64 v119; // [rsp+A8h] [rbp-11h]
  __m128i pExceptionObject; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v121; // [rsp+C0h] [rbp+7h]
  int v122; // [rsp+C8h] [rbp+Fh]
  __int64 v123; // [rsp+CCh] [rbp+13h]
  char v124; // [rsp+D4h] [rbp+1Bh]

  v2 = a2;
  v116 = a2;
  v3 = a1;
  v115 = a1;
  v4 = *a2;
  v5 = a2[1];
  a2[1] = *a2;
  v6 = (v5 - v4) / 48;
  while ( v6 )
  {
    --v6;
    v7 = (char *)*((_QWORD *)v4 + 6 * v6);
    if ( v7 != (char *)v4 + 48 * v6 + 16 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
    }
  }
  if ( *(_BYTE *)(v3 + 136) )
    return 0;
  v9 = *(_QWORD *)(v3 + 32);
  if ( v9 )
  {
    v10 = *(_DWORD **)(v9 + 184);
    if ( v10 )
    {
      v11 = v10[2];
      utl::vector<ChannelReference,utl::allocator<ChannelReference>>::reserve(v2, v11);
      v12 = 0;
      cbData = 0;
      while ( v12 < v11 )
      {
        if ( !(unsigned __int8)utl::vector<ChannelReference,utl::allocator<ChannelReference>>::emplace_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,unsigned long const &,unsigned long &,unsigned long const &,0>(
                                 (_DWORD)v2,
                                 *v10 + 24 * v12,
                                 *v10 + 24 * v12 + 20,
                                 (unsigned int)&cbData,
                                 *(_QWORD *)v10 + 24LL * v12 + 16) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, 14);
          }
          EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v13, 772);
          throw (EvtException *)&pExceptionObject;
        }
        cbData = ++v12;
      }
      return 1;
    }
  }
  hkey = 0;
  v14 = *(HKEY *)v3;
  hTransaction = *(void **)(v3 + 8);
  if ( *(_QWORD *)v3 )
  {
    hkey = 0;
    if ( hTransaction == (void *)-1LL )
      PublishersRegKey = RegOpenKeyExW(v14, L"ChannelReferences", 0, 0x20019u, &hkey);
    else
      PublishersRegKey = RegOpenKeyTransactedW(v14, L"ChannelReferences", 0, 0x20019u, &hkey, hTransaction, 0);
  }
  else
  {
    hKey = 0;
    PublishersRegKey = GetPublishersRegKey(&hKey, hTransaction);
    v17 = hKey;
    if ( !PublishersRegKey )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              &pExceptionObject,
                              *(_QWORD *)(v3 + 40),
                              (__int64)(*(_QWORD *)(v3 + 48) - *(_QWORD *)(v3 + 40)) >> 1)
        && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                              &pExceptionObject,
                              L"\\ChannelReferences",
                              18) )
      {
        v18 = *(void **)(v3 + 8);
        v19 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
        PublishersRegKey = OpenRegKey(v17, (const wchar_t *)pExceptionObject.m128i_i64[0], 0x20019u, v19, v18);
      }
      else
      {
        PublishersRegKey = 14;
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&pExceptionObject);
    }
    if ( v17 )
      RegCloseKey(v17);
  }
  if ( PublishersRegKey == 2 )
  {
LABEL_30:
    if ( hkey )
      RegCloseKey(hkey);
    return 0;
  }
  if ( PublishersRegKey )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        &WPP_e40e9425320d341abfed50516b3c9004_Traceguids,
        PublishersRegKey);
    }
    pExceptionObject.m128i_i64[0] = (__int64)word_14003838A;
    pExceptionObject.m128i_i64[1] = 0;
    v121 = 0;
    v122 = PublishersRegKey;
    v123 = -1;
    v124 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"Count", 0x10u, 0, &pvData, &pcbData);
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      v23 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF__guid_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, (_DWORD)v22, v3 + 16, *(_QWORD *)(v3 + 72), ValueW);
          v23 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 4) != 0 && *((_BYTE *)v23 + 25) >= 2u )
          WPP_SF_d(v23[2], 52, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, 15010);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0x3AA2u, v22, 861);
      throw (EvtException *)&pExceptionObject;
    }
    goto LABEL_30;
  }
  v24 = pvData;
  if ( pvData > 8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF__guid_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, (_DWORD)v22, v3 + 16, *(_QWORD *)(v3 + 72), pvData);
      v24 = pvData;
    }
    _o__ultow_s(v24, &pExceptionObject, 11, 10);
    eventlog::ai::WarningMessage((eventlog::ai *)0x51, *(_QWORD *)(v3 + 72), *(_QWORD *)(v3 + 40), &pExceptionObject);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, 15010);
    }
    EvtException::EvtException((EvtException *)v117, 0x3AA2u, v25, 876);
    throw (EvtException *)v117;
  }
  v26 = pvData;
  v27 = v2[1];
  v28 = *v2;
  v29 = (const char *)0xAAAAAAAAAAAAAAABLL;
  v30 = 0xAAAAAAAAAAAAAAABuLL * ((v27 - *v2) >> 4);
  if ( pvData > v30 )
  {
    v34 = 0xAAAAAAAAAAAAAAABuLL * ((v2[2] - v28) >> 4);
    if ( pvData > v34 )
    {
      v35 = 7 * (v34 >> 2) + 8;
      if ( v35 < pvData )
        v35 = pvData;
      if ( v35 > 0x2AAAAAAAAAAAAAALL )
        v35 = 0x2AAAAAAAAAAAAAALL;
      if ( pvData <= v35 )
      {
        v36 = 48 * v35;
        v37 = (char *)operator new(48 * v35, v28);
        v39 = v37;
        pExceptionObject.m128i_i64[0] = (__int64)v37;
        if ( v37 )
        {
          pExceptionObject.m128i_i64[1] = (__int64)v37;
          v40 = &v37[v36];
          v121 = (__int64)&v37[v36];
          if ( v37 != (char *)-1LL )
          {
            v41 = *v2;
            v42 = 0xAAAAAAAAAAAAAAABuLL * ((v116[1] - v41) >> 4);
            for ( i = 0; i != v42; i = v44 + 1 )
              ChannelReference::ChannelReference(&v39[48 * i], (char *)v41 + 48 * i);
            utl::_RangeDestroyApc<utl::allocator<ChannelReference>>(v38, v39, 0);
            v2 = v116;
            v45 = &v39[16 * ((v116[1] - *v116) >> 4)];
            utl::vector<ChannelReference,utl::allocator<ChannelReference>>::_Uninit(v116);
            *v2 = (const struct std::nothrow_t *)v39;
            v2[1] = (const struct std::nothrow_t *)v45;
            v2[2] = (const struct std::nothrow_t *)v40;
            pExceptionObject = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
            v121 = -1;
            utl::vector<ChannelReference,utl::allocator<ChannelReference>>::_Uninit(&pExceptionObject);
            v3 = v115;
            goto LABEL_76;
          }
        }
        else
        {
          pExceptionObject = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
          v121 = -1;
        }
        utl::vector<ChannelReference,utl::allocator<ChannelReference>>::_Uninit(&pExceptionObject);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)v117, 0xEu, v29, 881);
      throw (EvtException *)v117;
    }
LABEL_76:
    v46 = v2[1];
    for ( j = 0; j != v26 - v30; j = v49 + 1 )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((char *)v46 + 48 * j);
      *(_QWORD *)(v48 + 32) = 0;
      *(_DWORD *)(v48 + 40) = 0;
    }
    v2[1] = (const struct std::nothrow_t *)((char *)*v2 + 48 * v26);
    goto LABEL_87;
  }
  v31 = (const struct std::nothrow_t *)((char *)v28 + 48 * pvData);
  v2[1] = v31;
  v32 = (__int64)((unsigned __int128)((v27 - v31) * (__int128)0x2AAAAAAAAAAAAAABLL) >> 64) >> 3;
  v33 = (v32 >> 63) + v32;
  if ( v33 )
  {
    do
    {
      --v33;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((char *)v31 + 48 * v33);
    }
    while ( v33 );
LABEL_87:
    LODWORD(v24) = pvData;
  }
  wcscpy(SubKey, L"0");
  v50 = 0;
  while ( 1 )
  {
    v112 = v50;
    if ( v50 >= (unsigned int)v24 )
      break;
    v51 = (__int64)*v2 + 48 * v50;
    *(_DWORD *)(v51 + 36) = v50;
    SubKey[0] = v50 + 48;
    v52 = *(void **)(v3 + 8);
    hKey = 0;
    if ( v52 == (void *)-1LL )
      v53 = RegOpenKeyExW(hkey, SubKey, 0, 0x20019u, &hKey);
    else
      v53 = RegOpenKeyTransactedW(hkey, SubKey, 0, 0x20019u, &hKey, v52, 0);
    v55 = v53;
    if ( v53 == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF__guid_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_QWORD *)(v3 + 72), (__int64)SubKey, 2);
      }
      eventlog::ai::WarningMessage((eventlog::ai *)0x52, *(_QWORD *)(v3 + 72), *(_QWORD *)(v3 + 40));
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, 15010);
      }
      EvtException::EvtException((EvtException *)v117, 0x3AA2u, v107, 905);
      throw (EvtException *)v117;
    }
    if ( v53 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, v53);
      }
      EvtException::EvtException((EvtException *)v117, v55, v54, 910);
      throw (EvtException *)v117;
    }
    v56 = hKey;
    cbData = 2 * ((__int64)(*(_QWORD *)(v51 + 8) - *(_QWORD *)v51) >> 1);
    pcbData = 0;
    while ( 1 )
    {
      v57 = RegQueryValueExW(v56, &ValueName, 0, &pcbData, *(LPBYTE *)v51, &cbData);
      if ( v57 != 234 )
        break;
      v58 = (unsigned __int64)cbData >> 1;
      v59 = *(char **)(v51 + 8);
      v60 = *(LPBYTE *)v51;
      v61 = (__int64)&v59[-*(_QWORD *)v51] >> 1;
      if ( v61 < v58 )
      {
        v62 = (_QWORD *)(v51 + 16);
        if ( v60 == (LPBYTE)(v51 + 16) )
          v63 = 7;
        else
          v63 = (__int64)(*v62 - (_QWORD)v60) >> 1;
        if ( v58 > v63 )
        {
          if ( v60 == (LPBYTE)v62 )
            v64 = 7;
          else
            v64 = (__int64)(*v62 - (_QWORD)v60) >> 1;
          v65 = 2 * v64 + 1;
          if ( v65 < v58 )
            v65 = (unsigned __int64)cbData >> 1;
          if ( v65 > 0x3FFFFFFFFFFFFFF7LL )
            v65 = 0x3FFFFFFFFFFFFFF7LL;
          if ( v58 > v65
            || (v66 = (v65 + 8) & 0xFFFFFFFFFFFFFFF8uLL, v66 > 0x7FFFFFFFFFFFFFFFLL)
            || (v67 = 2 * v66, v118 = 2 * v66, v68 = GetProcessHeap(), (v69 = (char *)HeapAlloc(v68, 0, v67)) == 0) )
          {
            v102 = (_WORD *)(*(_QWORD *)v51 + 2 * v61);
            *(_QWORD *)(v51 + 8) = v102;
            *v102 = 0;
            goto LABEL_160;
          }
          v70 = *(LPBYTE *)v51;
          v119 = 2 * ((__int64)(*(_QWORD *)(v51 + 8) - *(_QWORD *)v51) >> 1);
          memcpy_0(v69, v70, v119 + 2);
          v71 = *(LPBYTE *)v51;
          if ( *(_QWORD **)v51 != v62 )
          {
            v72 = GetProcessHeap();
            HeapFree(v72, 0, v71);
          }
          *(_QWORD *)v51 = v69;
          *v62 = &v69[v118 - 2];
          v59 = &v69[v119];
        }
        v73 = v58 - v61;
        if ( v58 != v61 )
        {
          v74 = v59;
          while ( v73 )
          {
            *(_WORD *)v74 = 0;
            v74 += 2;
            --v73;
          }
        }
      }
      v75 = (_WORD *)(*(_QWORD *)v51 + 2 * v58);
      *(_QWORD *)(v51 + 8) = v75;
      *v75 = 0;
    }
    if ( v57 || pcbData - 1 > 1 )
    {
LABEL_160:
      v103 = v115;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF__guid_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_QWORD *)(v115 + 72), (__int64)SubKey, 0);
      }
      eventlog::ai::WarningMessage((eventlog::ai *)0x53, *(_QWORD *)(v103 + 72), *(_QWORD *)(v103 + 40), SubKey);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, 15010);
      }
      EvtException::EvtException((EvtException *)v117, 0x3AA2u, v104, 922);
      throw (EvtException *)v117;
    }
    v76 = wcsnlen(*(const wchar_t **)v51, (unsigned __int64)cbData >> 1);
    v77 = *(char **)(v51 + 8);
    v78 = *(LPBYTE *)v51;
    v79 = (__int64)&v77[-*(_QWORD *)v51] >> 1;
    if ( v79 < v76 )
    {
      v80 = (_QWORD *)(v51 + 16);
      if ( v78 == (LPBYTE)(v51 + 16) )
        v81 = 7;
      else
        v81 = (__int64)(*v80 - (_QWORD)v78) >> 1;
      if ( v76 > v81 )
      {
        if ( v78 == (LPBYTE)v80 )
          v82 = 7;
        else
          v82 = (__int64)(*v80 - (_QWORD)v78) >> 1;
        v83 = 2 * v82 + 1;
        if ( v83 < v76 )
          v83 = v76;
        if ( v83 > 0x3FFFFFFFFFFFFFF7LL )
          v83 = 0x3FFFFFFFFFFFFFF7LL;
        if ( v76 > v83
          || (v84 = (v83 + 8) & 0xFFFFFFFFFFFFFFF8uLL, v84 > 0x7FFFFFFFFFFFFFFFLL)
          || (v85 = 2 * v84,
              v86 = (char *)operator new(2 * v84, (const struct std::nothrow_t *)0x3FFFFFFFFFFFFFF7LL),
              (v87 = v86) == 0) )
        {
          v90 = (_WORD *)(*(_QWORD *)v51 + 2 * v79);
          goto LABEL_142;
        }
        v88 = 2 * ((__int64)(*(_QWORD *)(v51 + 8) - *(_QWORD *)v51) >> 1);
        memcpy_0(v86, *(const void **)v51, v88 + 2);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v51);
        *(_QWORD *)v51 = v87;
        *v80 = &v87[v85 - 2];
        v77 = &v87[v88];
      }
      v89 = v76 - v79;
      if ( v76 != v79 )
      {
        while ( v89 )
        {
          *(_WORD *)v77 = 0;
          v77 += 2;
          --v89;
        }
      }
    }
    v90 = (_WORD *)(*(_QWORD *)v51 + 2 * v76);
LABEL_142:
    *(_QWORD *)(v51 + 8) = v90;
    *v90 = 0;
    v91 = *(LPBYTE *)v51;
    v92 = -1;
    do
      ++v92;
    while ( *(_WORD *)&v91[2 * v92] );
    if ( !v92 || (unsigned __int64)(v92 + 1) > 0x100 )
    {
LABEL_187:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, 15000);
      }
      pExceptionObject.m128i_i64[0] = (__int64)word_14003838A;
      pExceptionObject.m128i_i64[1] = 0;
      v121 = 0;
      v122 = 15000;
      v123 = -1;
      v124 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    v93 = &v91[2 * v92];
    while ( v91 != v93 )
    {
      v94 = *(unsigned __int16 *)v91;
      if ( (unsigned int)v94 <= 0x3F )
      {
        v95 = 0xD40004C4FFFFFFFFuLL;
        if ( _bittest64((const __int64 *)&v95, v94) )
          goto LABEL_187;
      }
      if ( (_DWORD)v94 == 92 || (_DWORD)v94 == 124 )
        goto LABEL_187;
      v91 += 2;
    }
    pcbData = 4;
    v96 = RegGetValueW(hKey, 0, L"Flags", 0x10u, 0, (PVOID)(v51 + 40), &pcbData);
    v98 = v96;
    if ( (v96 & 0xFFFFFFFD) != 0 )
    {
      v106 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF__guid_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_QWORD *)(v115 + 72), (__int64)SubKey, v96);
          v106 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v106 != &WPP_GLOBAL_Control && (*((_BYTE *)v106 + 28) & 4) != 0 && *((_BYTE *)v106 + 25) >= 2u )
          WPP_SF_d(v106[2], 63, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, v98);
      }
      EvtException::EvtException((EvtException *)v117, v98, v97, 932);
      throw (EvtException *)v117;
    }
    pcbData = 4;
    v99 = RegGetValueW(hKey, 0, L"Id", 0x10u, 0, (PVOID)(v51 + 32), &pcbData);
    v101 = v99;
    if ( (v99 & 0xFFFFFFFD) != 0 )
    {
      v105 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF__guid_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_QWORD *)(v115 + 72), (__int64)SubKey, v99);
          v105 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v105 != &WPP_GLOBAL_Control && (*((_BYTE *)v105 + 28) & 4) != 0 && *((_BYTE *)v105 + 25) >= 2u )
          WPP_SF_d(v105[2], 65, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, v101);
      }
      EvtException::EvtException((EvtException *)v117, v101, v100, 940);
      throw (EvtException *)v117;
    }
    if ( hKey )
      RegCloseKey(hKey);
    v50 = v112 + 1;
    LODWORD(v24) = pvData;
    v2 = v116;
    v3 = v115;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return 1;
}

```

## disassembly

```asm
0x140003b50  mov     [rsp-8+arg_10], rbx
0x140003b55  push    rbp
0x140003b56  push    rsi
0x140003b57  push    rdi
0x140003b58  push    r12
0x140003b5a  push    r13
0x140003b5c  push    r14
0x140003b5e  push    r15
0x140003b60  lea     rbp, [rsp-27h]
0x140003b65  sub     rsp, 0E0h
0x140003b6c  mov     rax, cs:__security_cookie
0x140003b73  xor     rax, rsp
0x140003b76  mov     [rbp+57h+var_38], rax
0x140003b7a  mov     r12, rdx
0x140003b7d  mov     [rbp+57h+var_A0], rdx
0x140003b81  mov     r14, rcx
0x140003b84  mov     [rbp+57h+var_A8], rcx
0x140003b88  mov     rbx, [rdx]
0x140003b8b  mov     rcx, [rdx+8]
0x140003b8f  mov     [rdx+8], rbx
0x140003b93  sub     rcx, rbx
0x140003b96  mov     r15, 2AAAAAAAAAAAAAABh
0x140003ba0  mov     rax, r15
0x140003ba3  imul    rcx
0x140003ba6  mov     rdi, rdx
0x140003ba9  sar     rdi, 3
0x140003bad  mov     rax, rdi
0x140003bb0  shr     rax, 3Fh
0x140003bb4  add     rdi, rax
0x140003bb7  jz      short loc_140003BED
0x140003bb9  dec     rdi
0x140003bbc  lea     rax, [rdi+rdi*2]
0x140003bc0  shl     rax, 4
0x140003bc4  mov     rsi, [rax+rbx]
0x140003bc8  add     rax, 10h
0x140003bcc  add     rax, rbx
0x140003bcf  cmp     rsi, rax
0x140003bd2  jz      short loc_140003BE8
0x140003bd4  call    cs:__imp_GetProcessHeap
0x140003bda  mov     rcx, rax; hHeap
0x140003bdd  mov     r8, rsi; lpMem
0x140003be0  xor     edx, edx; dwFlags
0x140003be2  call    cs:__imp_HeapFree
0x140003be8  test    rdi, rdi
0x140003beb  jnz     short loc_140003BB9
0x140003bed  cmp     byte ptr [r14+88h], 0
0x140003bf5  jnz     loc_140003DDB
0x140003bfb  mov     rax, [r14+20h]
0x140003bff  test    rax, rax
0x140003c02  jz      loc_140003CC5
0x140003c08  mov     rdi, [rax+0B8h]
0x140003c0f  test    rdi, rdi
0x140003c12  jz      loc_140003CC5
0x140003c18  mov     ebx, [rdi+8]
0x140003c1b  mov     edx, ebx
0x140003c1d  mov     rcx, r12
0x140003c20  call    ?reserve@?$vector@UChannelReference@@V?$allocator@UChannelReference@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<ChannelReference,utl::allocator<ChannelReference>>::reserve(unsigned __int64)
0x140003c25  xor     esi, esi
0x140003c27  mov     [rbp+57h+cbData], esi
0x140003c2a  cmp     esi, ebx
0x140003c2c  jnb     loc_140004AA1
0x140003c32  mov     eax, esi
0x140003c34  lea     rcx, [rax+rax*2]
0x140003c38  mov     rax, [rdi]
0x140003c3b  lea     rdx, [rax+rcx*8]
0x140003c3f  lea     rax, [rdx+10h]
0x140003c43  lea     r8, [rdx+14h]
0x140003c47  mov     [rsp+110h+phkResult], rax
0x140003c4c  lea     r9, [rbp+57h+cbData]
0x140003c50  mov     rcx, r12
0x140003c53  call    ??$emplace_back@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEBKAEAKAEBK$0A@@?$vector@UChannelReference@@V?$allocator@UChannelReference@@@utl@@@utl@@QEAA_NAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@1@AEBKAEAK1@Z; utl::vector<ChannelReference,utl::allocator<ChannelReference>>::emplace_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,ulong const &,ulong &,ulong const &,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,ulong const &,ulong &,ulong const &)
0x140003c58  test    al, al
0x140003c5a  jz      short loc_140003C66
0x140003c5c  lea     eax, [rsi+1]
0x140003c5f  mov     [rbp+57h+cbData], eax
0x140003c62  mov     esi, eax
0x140003c64  jmp     short loc_140003C2A
0x140003c66  lea     rbx, WPP_GLOBAL_Control
0x140003c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c74  cmp     rcx, rbx
0x140003c77  jz      short loc_140003CA0
0x140003c79  test    byte ptr [rcx+1Ch], 4
0x140003c7d  jz      short loc_140003CA0
0x140003c7f  cmp     byte ptr [rcx+19h], 2
0x140003c83  jb      short loc_140003CA0
0x140003c85  mov     edx, 30h ; '0'
0x140003c8a  mov     r9d, 0Eh
0x140003c90  lea     r8, WPP_e40e9425320d341abfed50516b3c9004_Traceguids
0x140003c97  mov     rcx, [rcx+10h]
0x140003c9b  call    WPP_SF_d
0x140003ca0  mov     edx, 0Eh; unsigned int
0x140003ca5  mov     r9d, 304h; int
0x140003cab  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140003caf  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140003cb4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140003cbb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140003cbf  call    _CxxThrowException_0
0x140003cc5  xor     r13d, r13d
0x140003cc8  mov     [rbp+57h+hkey], r13
0x140003ccc  mov     rcx, [r14]; hKey
0x140003ccf  mov     rdx, [r14+8]
0x140003cd3  test    rcx, rcx
0x140003cd6  jz      short loc_140003D2B
0x140003cd8  mov     [rbp+57h+hkey], r13
0x140003cdc  lea     rax, [rbp+57h+hkey]
0x140003ce0  mov     r9d, 20019h; samDesired
0x140003ce6  xor     r8d, r8d; ulOptions
0x140003ce9  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140003ced  jz      short loc_140003D12
0x140003cef  mov     [rsp+110h+pExtendedParemeter], r13; pExtendedParemeter
0x140003cf4  mov     [rsp+110h+hTransaction], rdx; hTransaction
0x140003cf9  mov     [rsp+110h+phkResult], rax; phkResult
0x140003cfe  lea     rdx, aChannelreferen_0; "ChannelReferences"
0x140003d05  call    cs:__imp_RegOpenKeyTransactedW
0x140003d0b  mov     edi, eax
0x140003d0d  jmp     loc_140003DC7
0x140003d12  mov     [rsp+110h+phkResult], rax; phkResult
0x140003d17  lea     rdx, aChannelreferen_0; "ChannelReferences"
0x140003d1e  call    cs:__imp_RegOpenKeyExW
0x140003d24  mov     edi, eax
0x140003d26  jmp     loc_140003DC7
0x140003d2b  mov     [rbp+57h+hKey], r13
0x140003d2f  lea     rcx, [rbp+57h+hKey]
0x140003d33  call    GetPublishersRegKey
0x140003d38  mov     edi, eax
0x140003d3a  mov     rbx, [rbp+57h+hKey]
0x140003d3e  test    eax, eax
0x140003d40  jnz     short loc_140003DB9
0x140003d42  lea     rcx, [rbp+57h+pExceptionObject]
0x140003d46  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140003d4b  mov     rdx, [r14+28h]
0x140003d4f  mov     r8, [r14+30h]
0x140003d53  sub     r8, rdx
0x140003d56  sar     r8, 1
0x140003d59  lea     rcx, [rbp+57h+pExceptionObject]
0x140003d5d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140003d62  test    al, al
0x140003d64  jz      short loc_140003DAB
0x140003d66  mov     r8d, 12h
0x140003d6c  lea     rdx, aChannelreferen; "\\ChannelReferences"
0x140003d73  lea     rcx, [rbp+57h+pExceptionObject]
0x140003d77  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140003d7c  test    al, al
0x140003d7e  jz      short loc_140003DAB
0x140003d80  mov     rdi, [r14+8]
0x140003d84  lea     rcx, [rbp+57h+hkey]
0x140003d88  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140003d8d  mov     [rsp+110h+phkResult], rdi; void *
0x140003d92  mov     r9, rax; HKEY *
0x140003d95  mov     r8d, 20019h; unsigned int
0x140003d9b  mov     rdx, qword ptr [rbp+57h+pExceptionObject]; wchar_t *
0x140003d9f  mov     rcx, rbx; HKEY
0x140003da2  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x140003da7  mov     edi, eax
0x140003da9  jmp     short loc_140003DB0
0x140003dab  mov     edi, 0Eh
0x140003db0  lea     rcx, [rbp+57h+pExceptionObject]
0x140003db4  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140003db9  test    rbx, rbx
0x140003dbc  jz      short loc_140003DC7
0x140003dbe  mov     rcx, rbx; hKey
0x140003dc1  call    cs:__imp_RegCloseKey
0x140003dc7  cmp     edi, 2
0x140003dca  jnz     short loc_140003E04
0x140003dcc  mov     rcx, [rbp+57h+hkey]; hKey
0x140003dd0  test    rcx, rcx
0x140003dd3  jz      short loc_140003DDB
0x140003dd5  call    cs:__imp_RegCloseKey
0x140003ddb  xor     al, al
0x140003ddd  mov     rcx, [rbp+57h+var_38]
0x140003de1  xor     rcx, rsp; StackCookie
0x140003de4  call    __security_check_cookie
0x140003de9  mov     rbx, [rsp+110h+arg_10]
0x140003df1  add     rsp, 0E0h
0x140003df8  pop     r15
0x140003dfa  pop     r14
0x140003dfc  pop     r13
0x140003dfe  pop     r12
0x140003e00  pop     rdi
0x140003e01  pop     rsi
0x140003e02  pop     rbp
0x140003e03  retn
0x140003e04  test    edi, edi
0x140003e06  jz      short loc_140003E72
0x140003e08  lea     rbx, WPP_GLOBAL_Control
0x140003e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e16  cmp     rcx, rbx
0x140003e19  jz      short loc_140003E3F
0x140003e1b  test    byte ptr [rcx+1Ch], 4
0x140003e1f  jz      short loc_140003E3F
0x140003e21  cmp     byte ptr [rcx+19h], 2
0x140003e25  jb      short loc_140003E3F
0x140003e27  mov     edx, 31h ; '1'
0x140003e2c  mov     r9d, edi
0x140003e2f  lea     r8, WPP_e40e9425320d341abfed50516b3c9004_Traceguids
0x140003e36  mov     rcx, [rcx+10h]
0x140003e3a  call    WPP_SF_d
0x140003e3f  lea     rax, word_14003838A
0x140003e46  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x140003e4a  mov     qword ptr [rbp+57h+pExceptionObject+8], r13
0x140003e4e  mov     [rbp+57h+var_50], r13
0x140003e52  mov     [rbp+57h+var_48], edi
0x140003e55  mov     [rbp+57h+var_44], 0FFFFFFFFFFFFFFFFh
0x140003e5d  mov     [rbp+57h+var_3C], 0
0x140003e61  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140003e68  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140003e6c  call    _CxxThrowException_0
0x140003e72  mov     [rbp+57h+pvData], r13d
0x140003e76  mov     [rbp+57h+pcbData], 4
0x140003e7d  lea     rax, [rbp+57h+pcbData]
0x140003e81  mov     [rsp+110h+pExtendedParemeter], rax; pcbData
0x140003e86  lea     rax, [rbp+57h+pvData]
0x140003e8a  mov     [rsp+110h+hTransaction], rax; pvData
0x140003e8f  mov     [rsp+110h+phkResult], r13; pdwType
0x140003e94  mov     r9d, 10h; dwFlags
0x140003e9a  lea     r8, aCount_0; "Count"
0x140003ea1  xor     edx, edx; lpSubKey
0x140003ea3  mov     rcx, [rbp+57h+hkey]; hkey
0x140003ea7  call    cs:__imp_RegGetValueW
0x140003ead  test    eax, eax
0x140003eaf  jz      loc_140003F54
0x140003eb5  cmp     eax, 2
0x140003eb8  jz      loc_140003DCC
0x140003ebe  lea     rbx, WPP_GLOBAL_Control
0x140003ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ecc  cmp     rcx, rbx
0x140003ecf  jz      short loc_140003F2F
0x140003ed1  test    byte ptr [rcx+1Ch], 4
0x140003ed5  jz      short loc_140003F03
0x140003ed7  cmp     byte ptr [rcx+19h], 3
0x140003edb  jb      short loc_140003F03
0x140003edd  lea     r9, [r14+10h]
0x140003ee1  mov     edx, 33h ; '3'
0x140003ee6  mov     dword ptr [rsp+110h+hTransaction], eax
0x140003eea  mov     rax, [r14+48h]
0x140003eee  mov     [rsp+110h+phkResult], rax
0x140003ef3  mov     rcx, [rcx+10h]
0x140003ef7  call    WPP_SF__guid_SD
0x140003efc  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f03  cmp     rcx, rbx
0x140003f06  jz      short loc_140003F2F
0x140003f08  test    byte ptr [rcx+1Ch], 4
0x140003f0c  jz      short loc_140003F2F
0x140003f0e  cmp     byte ptr [rcx+19h], 2
0x140003f12  jb      short loc_140003F2F
0x140003f14  mov     edx, 34h ; '4'
0x140003f19  mov     r9d, 3AA2h
0x140003f1f  lea     r8, WPP_e40e9425320d341abfed50516b3c9004_Traceguids
0x140003f26  mov     rcx, [rcx+10h]
0x140003f2a  call    WPP_SF_d
0x140003f2f  mov     edx, 3AA2h; unsigned int
0x140003f34  mov     r9d, 35Dh; int
0x140003f3a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140003f3e  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140003f43  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140003f4a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140003f4e  call    _CxxThrowException_0
0x140003f54  mov     ecx, [rbp+57h+pvData]
0x140003f57  cmp     ecx, 8
0x140003f5a  jbe     loc_140004025
0x140003f60  lea     rbx, WPP_GLOBAL_Control
0x140003f67  mov     rdi, cs:WPP_GLOBAL_Control
0x140003f6e  cmp     rdi, rbx
0x140003f71  jz      short loc_140003FA1
0x140003f73  test    byte ptr [rdi+1Ch], 4
0x140003f77  jz      short loc_140003FA1
0x140003f79  cmp     byte ptr [rdi+19h], 3
0x140003f7d  jb      short loc_140003FA1
0x140003f7f  lea     r9, [r14+10h]
0x140003f83  mov     edx, 35h ; '5'
0x140003f88  mov     dword ptr [rsp+110h+hTransaction], ecx
0x140003f8c  mov     rax, [r14+48h]
0x140003f90  mov     [rsp+110h+phkResult], rax
0x140003f95  mov     rcx, [rdi+10h]
0x140003f99  call    WPP_SF__guid_SD
0x140003f9e  mov     ecx, [rbp+57h+pvData]
0x140003fa1  mov     r9d, 0Ah
0x140003fa7  mov     r8d, 0Bh
0x140003fad  lea     rdx, [rbp+57h+pExceptionObject]
0x140003fb1  call    cs:__imp__o__ultow_s
0x140003fb7  lea     r9, [rbp+57h+pExceptionObject]
0x140003fbb  mov     r8, [r14+28h]
0x140003fbf  mov     rdx, [r14+48h]; unsigned int
0x140003fc3  mov     ecx, 51h ; 'Q'; this
0x140003fc8  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x140003fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140003fd4  cmp     rcx, rbx
0x140003fd7  jz      short loc_140004000
0x140003fd9  test    byte ptr [rcx+1Ch], 4
0x140003fdd  jz      short loc_140004000
0x140003fdf  cmp     byte ptr [rcx+19h], 2
0x140003fe3  jb      short loc_140004000
0x140003fe5  mov     edx, 36h ; '6'
0x140003fea  mov     r9d, 3AA2h
0x140003ff0  lea     r8, WPP_e40e9425320d341abfed50516b3c9004_Traceguids
0x140003ff7  mov     rcx, [rcx+10h]
0x140003ffb  call    WPP_SF_d
0x140004000  mov     edx, 3AA2h; unsigned int
0x140004005  mov     r9d, 36Ch; int
0x14000400b  lea     rcx, [rbp+57h+var_98]; this
  ... truncated ...
```
