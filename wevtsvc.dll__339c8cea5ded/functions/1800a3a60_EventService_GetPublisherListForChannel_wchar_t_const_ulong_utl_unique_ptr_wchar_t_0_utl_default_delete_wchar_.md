# EventService::GetPublisherListForChannel(wchar_t const *,ulong &,utl::unique_ptr<wchar_t * [0],utl::default_delete<wchar_t * [0]>> *,utl::unique_ptr<_GUID [0],utl::default_delete<_GUID [0]>> *)

- ea: `0x1800a3a60`
- end: `0x1800a495d`
- name: `?GetPublisherListForChannel@EventService@@QEAAXPEB_WAEAKPEAV?$unique_ptr@$$BY0A@PEA_WU?$default_delete@$$BY0A@PEA_W@utl@@@utl@@PEAV?$unique_ptr@$$BY0A@U_GUID@@U?$default_delete@$$BY0A@U_GUID@@@utl@@@3@@Z`
- size: `3837`
- prototype: `RPC_STATUS __fastcall(RTL_SRWLOCK *, const WCHAR *, _DWORD *, void **, __int64)`
- caller_count: `3`
- callee_count: `42`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000349c`
- `0x180061724`
- `0x1800a9050`

## callees

- `0x180003de0`
- `0x180006488`
- `0x1800064f0`
- `0x180006650`
- `0x180006770`
- `0x180006fb0`
- `0x180008870`
- `0x1800092c4`
- `0x180017128`
- `0x180017b60`
- `0x180017b98`
- `0x18001c320`
- `0x18002c6f4`
- `0x18002d934`
- `0x18002de70`
- `0x18003d1dc`
- `0x180053ddc`
- `0x180054848`
- `0x18006c144`
- `0x180074c48`
- `0x180074d40`
- `0x180075f00`
- `0x180077a5c`
- `0x180079ff4`
- `0x180083e64`
- `0x1800882e0`
- `0x18008b5b0`
- `0x18008bc9c`
- `0x18008d8a8`
- `0x180090d74`
- `0x180092008`
- `0x180092c6c`
- `0x180092d78`
- `0x18009aee0`
- `0x18009bb88`
- `0x18009f870`
- `0x1800a0fbc`
- `0x1800a19d8`
- `0x1800a3a60`
- `0x1800d334c`
- `0x1800d3364`
- `0x1800d3370`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a3fce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a405a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a3fce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a405a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a3f07`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a409c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a3f07`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a409c`
- `RPCRT4!RpcImpersonateClient` at `0x1800a3b01`
- `RPCRT4!RpcImpersonateClient` at `0x1800a3b01`
- `RPCRT4!RpcRevertToSelf` at `0x1800a444c`
- `RPCRT4!RpcRevertToSelf` at `0x1800a444c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
RPC_STATUS __fastcall EventService::GetPublisherListForChannel(
        RTL_SRWLOCK *a1,
        const WCHAR *a2,
        _DWORD *a3,
        void **a4,
        __int64 a5)
{
  void **v5; // r12
  __int64 v8; // r13
  RPC_STATUS result; // eax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned int LegacyChannelRegPath; // eax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  void *v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // r8
  const char *v21; // r8
  const char *v22; // r8
  const char *v23; // r8
  char *v24; // rbx
  __int64 v25; // r12
  __int64 v26; // r15
  __int64 *v27; // rax
  HKEY v28; // r15
  const char *v29; // r8
  const char *v30; // r8
  unsigned int v31; // r12d
  __int64 v32; // rbx
  const char *v33; // r8
  const char *v34; // r8
  HKEY *v35; // rbx
  HKEY *CurrentPublisherKey; // rax
  unsigned int v37; // ecx
  __int16 v38; // bx
  HKEY *v39; // rax
  const char *v40; // r8
  const char *v41; // r8
  __int64 v42; // r15
  __int64 v43; // r9
  __int64 v44; // rbx
  unsigned __int64 v45; // rax
  unsigned __int64 v46; // rbx
  unsigned __int64 v47; // rbx
  void *v48; // rcx
  void **unique_for; // rax
  void *v50; // rdx
  void *v51; // rcx
  const char *v52; // r8
  void **v53; // r13
  void *v54; // rax
  void *v55; // rcx
  const char *v56; // r8
  unsigned __int64 i; // rdx
  __int64 v58; // rcx
  unsigned __int64 j; // rdx
  unsigned __int64 v60; // rbx
  void *v61; // rcx
  __int64 v62; // rax
  unsigned int v63; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  char v65; // [rsp+40h] [rbp-C0h]
  char v66; // [rsp+41h] [rbp-BFh]
  WCHAR SubKey[2]; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v68; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v69; // [rsp+50h] [rbp-B0h]
  __int64 *v70; // [rsp+58h] [rbp-A8h]
  __int64 v71; // [rsp+60h] [rbp-A0h]
  HKEY v72; // [rsp+68h] [rbp-98h] BYREF
  void **v73; // [rsp+70h] [rbp-90h] BYREF
  HKEY v74; // [rsp+78h] [rbp-88h] BYREF
  __int64 v75; // [rsp+80h] [rbp-80h] BYREF
  void *v76; // [rsp+88h] [rbp-78h] BYREF
  char *v77; // [rsp+90h] [rbp-70h]
  _WORD v78[8]; // [rsp+98h] [rbp-68h] BYREF
  LPCWCH lpString2; // [rsp+A8h] [rbp-58h] BYREF
  _WORD *v80; // [rsp+B0h] [rbp-50h]
  _WORD v81[12]; // [rsp+B8h] [rbp-48h] BYREF
  void *v82; // [rsp+D0h] [rbp-30h] BYREF
  void *v83; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v84; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v85[2]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v86[2]; // [rsp+100h] [rbp+0h] BYREF
  __m128i si128; // [rsp+110h] [rbp+10h] BYREF
  __int64 v88; // [rsp+120h] [rbp+20h]
  _BYTE pExceptionObject[40]; // [rsp+128h] [rbp+28h] BYREF
  LPCWCH lpString1; // [rsp+150h] [rbp+50h]
  __int128 v91; // [rsp+158h] [rbp+58h] BYREF
  wchar_t *v92[2]; // [rsp+168h] [rbp+68h] BYREF
  _WORD v93[8]; // [rsp+178h] [rbp+78h] BYREF
  _QWORD v94[2]; // [rsp+188h] [rbp+88h] BYREF
  _WORD v95[8]; // [rsp+198h] [rbp+98h] BYREF
  _DWORD *v96; // [rsp+1A8h] [rbp+A8h]
  __int128 Buf1; // [rsp+1B0h] [rbp+B0h] BYREF
  HKEY v98[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  void *Src; // [rsp+1D0h] [rbp+D0h]
  __int64 v100; // [rsp+1D8h] [rbp+D8h]
  __int64 v101; // [rsp+1E0h] [rbp+E0h]
  _BYTE v102[520]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v103[16]; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int128 v104; // [rsp+400h] [rbp+300h]
  int v105; // [rsp+410h] [rbp+310h]
  int v106; // [rsp+414h] [rbp+314h]

  v5 = a4;
  v73 = a4;
  v96 = a3;
  lpString1 = a2;
  v84 = a5;
  EventService::WaitForInit(a1);
  *a3 = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  *((_QWORD *)&Buf1 + 1) = v8;
  v85[0] = a2;
  v85[1] = v8;
  result = ShouldSkipLegacyChannelKey(v85);
  if ( !(_BYTE)result )
  {
    v10 = RpcImpersonateClient(0);
    v11 = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v10);
      }
      EvtException::EvtException((EvtException *)&lpString2, v11);
      throw (EvtException *)&lpString2;
    }
    v66 = 1;
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v88 = -1;
    utl::vector<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>,utl::allocator<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>>>::_GrowMinimum(&si128);
    v68 = (__int64)&v68;
    v69 = &v68;
    v70 = &v68;
    v71 = 0;
    v94[0] = v95;
    v94[1] = v95;
    v95[0] = 0;
    v72 = 0;
    v92[0] = v93;
    v92[1] = v93;
    v93[0] = 0;
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
    *(_QWORD *)&Buf1 = a2;
    *((_QWORD *)&Buf1 + 1) = v13;
    LegacyChannelRegPath = RegistryPaths::GetLegacyChannelRegPath(v12, &Buf1, &v72, v92);
    v15 = LegacyChannelRegPath;
    if ( LegacyChannelRegPath )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          129,
          &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
          LegacyChannelRegPath);
      }
      EvtException::EvtException((EvtException *)&lpString2, v15);
      throw (EvtException *)&lpString2;
    }
    *(__m128i *)v98 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffff0000000000000000);
    Src = (void *)&pszFormat;
    v100 = 0;
    v101 = 0;
    memset_0(v102, 0, 0x200u);
    v16 = RegistryKeyEnumerator::Reset((RegistryKeyEnumerator *)v98, v72, v92[0], (void *)0xFFFFFFFFFFFFFFFFLL);
    v17 = v16;
    if ( v16 )
    {
      if ( v16 != 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v62 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::c_str(v92);
          utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>::basic_string_view<wchar_t,utl::char_traits<wchar_t>>(
            v86,
            v62);
          WPP_SF__utlwsv_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            130,
            (unsigned int)&WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
            (unsigned int)v86,
            v17);
        }
        EvtException::EvtException((EvtException *)&lpString2, v17);
        throw (EvtException *)&lpString2;
      }
    }
    else
    {
      LODWORD(v101) = HIDWORD(v101);
      while ( RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v98) != 259 )
      {
        v18 = Src;
        v19 = v100;
        if ( (unsigned int)RegReadStringValueNoThrow(v98[0]) )
        {
          utl::make_unique_for_overwrite<wchar_t [0],0>(&hKey, v19 + 1);
          if ( !hKey )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
            }
            EvtException::EvtException((EvtException *)&lpString2, 0xEu, v22, 2801);
            throw (EvtException *)&lpString2;
          }
          memcpy_0(hKey, v18, 2 * v19 + 2);
          v91 = 0;
          if ( !(unsigned __int8)utl::vector<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>,utl::allocator<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>>>::emplace_back<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID &,0>(
                                   &si128,
                                   &hKey,
                                   &v91) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
            }
            EvtException::EvtException((EvtException *)&lpString2, 0xEu, v23, 2808);
            throw (EvtException *)&lpString2;
          }
          utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&hKey);
        }
        else
        {
          Buf1 = 0;
          if ( tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(
                 &Buf1,
                 v94) )
          {
            utl::_Tree<_GUID,_GUID,GuidLess,utl::allocator<_GUID>,0>::_InsertImpl<_GUID const &>(&v68, v86, v20, &Buf1);
            if ( !v86[0] )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
              }
              EvtException::EvtException((EvtException *)&lpString2, 0xEu, v21, 2792);
              throw (EvtException *)&lpString2;
            }
          }
        }
      }
    }
    v76 = v78;
    v77 = (char *)v78;
    v78[0] = 0;
    lpString2 = v81;
    v80 = v81;
    v81[0] = 0;
    PublisherConfigEnumerator::PublisherConfigEnumerator(
      (PublisherConfigEnumerator *)v103,
      (void *)0xFFFFFFFFFFFFFFFFLL);
    v105 = v106;
    if ( RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v103) != 259 )
    {
      while ( 1 )
      {
        if ( (unsigned __int8)PublisherConfigEnumerator::GetCurrentPublisherName(v103, &v76) )
        {
          v24 = v77;
          if ( v76 != v77 )
          {
            Buf1 = 0;
            v25 = v104;
            v91 = v104;
            v26 = *((_QWORD *)&v104 + 1);
            if ( *((_QWORD *)&v104 + 1)
              && tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(&Buf1, &v91) )
            {
              if ( v70 == &v68
                || (v27 = (__int64 *)utl::_Tree<_GUID,_GUID,GuidLess,utl::allocator<_GUID>,0>::_LowerBoundNonEmpty<_GUID>(
                                       &v68,
                                       &Buf1),
                    v27 == &v68) )
              {
                v28 = 0;
LABEL_32:
                GetRegCacheProviderNodebyGuid(&v75, &Buf1);
                if ( v75 && (v28 = *(HKEY *)(v75 + 184)) != 0 )
                {
                  v31 = *((_DWORD *)v28 + 2);
                  v32 = 0;
                  if ( v31 )
                  {
                    while ( CompareStringOrdinal(
                              lpString1,
                              v8,
                              *(LPCWCH *)(*(_QWORD *)v28 + 24 * v32),
                              *(_DWORD *)(*(_QWORD *)v28 + 24 * v32 + 8),
                              1) != 2 )
                    {
                      v32 = (unsigned int)(v32 + 1);
                      if ( (unsigned int)v32 >= v31 )
                        goto LABEL_37;
                    }
                    utl::make_unique_for_overwrite<wchar_t [0],0>(&v83, ((v77 - (_BYTE *)v76) >> 1) + 1);
                    if ( !v83 )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          137,
                          &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
                          14);
                      }
                      EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v33, 2881);
                      throw (EvtException *)pExceptionObject;
                    }
                    memcpy_0(v83, v76, 2 * ((v77 - (_BYTE *)v76) >> 1) + 2);
                    if ( !(unsigned __int8)utl::vector<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>,utl::allocator<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>>>::emplace_back<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID &,0>(
                                             &si128,
                                             &v83,
                                             &Buf1) )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          138,
                          &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
                          14);
                      }
                      EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v34, 2888);
                      throw (EvtException *)pExceptionObject;
                    }
                    utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v83);
                  }
                }
                else
                {
                  hKey = v28;
                  v35 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
                  CurrentPublisherKey = (HKEY *)PublisherConfigEnumerator::GetCurrentPublisherKey(v103, v85);
                  LODWORD(v35) = RegOpenKeyExW(*CurrentPublisherKey, L"ChannelReferences", 0, 0x20019u, v35);
                  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v85);
                  if ( !(_DWORD)v35 )
                  {
                    v63 = (unsigned int)v28;
                    if ( !(unsigned int)RegReadDWORDValueNoThrow(hKey, 0, L"Count", &v63) )
                    {
                      v37 = v63;
                      if ( v63 > 8 )
                        v37 = 8;
                      v63 = v37;
                      wcscpy(SubKey, L"0");
                      v38 = (__int16)v28;
                      if ( v37 )
                      {
                        while ( 1 )
                        {
                          SubKey[0] = v38 + 48;
                          v74 = v28;
                          v39 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v74);
                          if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, v39)
                            && !(unsigned int)RegReadStringValueNoThrow(v74)
                            && CompareStringOrdinal(lpString1, v8, lpString2, v80 - lpString2, 1) == 2 )
                          {
                            break;
                          }
                          tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v74);
                          if ( (unsigned __int16)++v38 >= v63 )
                            goto LABEL_54;
                        }
                        utl::make_unique_for_overwrite<wchar_t [0],0>(&v72, ((v77 - (_BYTE *)v76) >> 1) + 1);
                        if ( !v72 )
                        {
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              139,
                              &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
                              14);
                          }
                          EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v40, 2945);
                          throw (EvtException *)pExceptionObject;
                        }
                        memcpy_0(v72, v76, 2 * ((v77 - (_BYTE *)v76) >> 1) + 2);
                        if ( !(unsigned __int8)utl::vector<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>,utl::allocator<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>>>::emplace_back<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID &,0>(
                                                 &si128,
                                                 &v72,
                                                 &Buf1) )
                        {
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              140,
                              &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
                              14);
                          }
                          EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v41, 2952);
                          throw (EvtException *)pExceptionObject;
                        }
                        utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v72);
                        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v74);
                      }
                    }
                  }
LABEL_54:
                  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
                }
LABEL_37:
                wmi::AutoRef<PublisherMetadata>::Release(&v75);
                goto LABEL_59;
              }
              v28 = 0;
              if ( memcmp_0(&Buf1, v27 + 3, 0x10u) < 0 )
                goto LABEL_32;
              utl::make_unique_for_overwrite<wchar_t [0],0>(&v82, ((v24 - (_BYTE *)v76) >> 1) + 1);
              if ( !v82 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    135,
                    &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
                    14);
                }
                EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v29, 2844);
                throw (EvtException *)pExceptionObject;
              }
              memcpy_0(v82, v76, 2 * ((v77 - (_BYTE *)v76) >> 1) + 2);
              if ( !(unsigned __int8)utl::vector<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>,utl::allocator<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>>>::emplace_back<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID &,0>(
                                       &si128,
                                       &v82,
                                       &Buf1) )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    136,
                    &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
                    14);
                }
                EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v30, 2851);
                throw (EvtException *)pExceptionObject;
              }
              utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v82);
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              v86[0] = v25;
              v86[1] = v26;
              WPP_SF__utlwsv_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                134,
                &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
                v86);
            }
          }
        }
LABEL_59:
        if ( RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v103) == 259 )
        {
          v5 = v73;
          break;
        }
      }
    }
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v103);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpString2);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v76);
    v42 = si128.m128i_i64[0];
    LOBYTE(v43) = v65;
    v44 = si128.m128i_i64[1];
    utl::_SortImp_utl::_ArrayIt_utl::pair_utl::unique_ptr_wchar_t__0__utl::default_delete_wchar_t__0______GUID______int64__EventService::GetPublisherListForChannel_::_2_::_lambda_2___(
      si128.m128i_i64[0],
      si128.m128i_i64[1],
      0xAAAAAAAAAAAAAAABuLL * ((si128.m128i_i64[1] - si128.m128i_i64[0]) >> 3),
      v43);
    v73 = (void **)v44;
    v85[0] = v42;
    utl::_UniqueImp_utl::_ArrayIt_utl::pair_utl::unique_ptr_wchar_t__0__utl::default_delete_wchar_t__0______GUID_____EventService::GetPublisherListForChannel_::_2_::_lambda_3____(
      &v75,
      v85,
      &v73);
    v45 = 0xAAAAAAAAAAAAAAABuLL * ((v75 - v42) >> 3);
    v46 = 0xFFFFFFFFLL;
    if ( v45 <= 0xFFFFFFFF )
    {
      if ( !v45 )
      {
        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v98);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v92);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v94);
        v47 = (unsigned __int64)v70;
        if ( v70 == &v68 )
        {
LABEL_95:
          utl::vector<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>,utl::allocator<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>>>::_Uninit(&si128);
          return RpcRevertToSelf();
        }
        while ( 1 )
        {
          while ( *(void ***)(v47 + 8) != &utl::_TreeSentinel )
            v47 = *(_QWORD *)(v47 + 8);
LABEL_69:
          if ( *(void ***)(v47 + 16) == &utl::_TreeSentinel )
            break;
          v47 = *(_QWORD *)(v47 + 16);
        }
        while ( 1 )
        {
          v48 = (void *)v47;
          v47 = *(_QWORD *)v47 & 0xFFFFFFFFFFFFFFFEuLL;
          operator delete(v48);
          if ( (__int64 *)v47 == &v68 )
            break;
          if ( *(void ***)(v47 + 8) != &utl::_TreeSentinel )
          {
            *(_QWORD *)(v47 + 8) = &utl::_TreeSentinel;
            goto LABEL_69;
          }
        }
LABEL_94:
        v68 = (__int64)&v68;
        v71 = 0;
        v70 = &v68;
        v69 = &v68;
        goto LABEL_95;
      }
      v46 = 0xAAAAAAAAAAAAAAABuLL * ((v75 - v42) >> 3);
    }
    if ( v5 )
    {
      unique_for = (void **)utl::make_unique_for_overwrite<wchar_t * [0],0>(&v73, v46);
      v50 = *unique_for;
      *unique_for = 0;
      v51 = *v5;
      *v5 = v50;
      if ( v51 )
        operator delete(v51);
      utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v73);
      if ( !*v5 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v52, 2986);
        throw (EvtException *)pExceptionObject;
      }
    }
    v53 = (void **)v84;
    if ( v84 )
    {
      v54 = MIDL_user_allocate(saturated_mul(v46, 0x10u));
      v84 = 0;
      v55 = *v53;
      *v53 = v54;
      if ( v55 )
        operator delete(v55);
      utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v84);
      if ( !*v53 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v56, 2995);
        throw (EvtException *)pExceptionObject;
      }
    }
    if ( v5 )
    {
      for ( i = 0; i < v46; ++i )
      {
        v58 = *(_QWORD *)(v42 + 24 * i);
        *(_QWORD *)(v42 + 24 * i) = 0;
        *((_QWORD *)*v5 + i) = v58;
      }
    }
    if ( v53 )
    {
      for ( j = 0; j < v46; ++j )
        *((_OWORD *)*v53 + j) = *(_OWORD *)(v42 + 24 * j + 8);
    }
    *v96 = v46;
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v98);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v92);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v94);
    v60 = (unsigned __int64)v70;
    if ( v70 == &v68 )
      goto LABEL_95;
    while ( 1 )
    {
      while ( *(void ***)(v60 + 8) != &utl::_TreeSentinel )
        v60 = *(_QWORD *)(v60 + 8);
LABEL_92:
      if ( *(void ***)(v60 + 16) == &utl::_TreeSentinel )
        break;
      v60 = *(_QWORD *)(v60 + 16);
    }
    while ( 1 )
    {
      v61 = (void *)v60;
      v60 = *(_QWORD *)v60 & 0xFFFFFFFFFFFFFFFEuLL;
      operator delete(v61);
      if ( (__int64 *)v60 == &v68 )
        goto LABEL_94;
      if ( *(void ***)(v60 + 8) != &utl::_TreeSentinel )
      {
        *(_QWORD *)(v60 + 8) = &utl::_TreeSentinel;
        goto LABEL_92;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800a3a60  push    rbp
0x1800a3a62  push    rbx
0x1800a3a63  push    rsi
0x1800a3a64  push    rdi
0x1800a3a65  push    r12
0x1800a3a67  push    r13
0x1800a3a69  push    r15
0x1800a3a6b  lea     rbp, [rsp-530h]
0x1800a3a73  sub     rsp, 630h
0x1800a3a7a  mov     rax, cs:__security_cookie
0x1800a3a81  xor     rax, rsp
0x1800a3a84  mov     [rbp+560h+var_40], rax
0x1800a3a8b  mov     r12, r9
0x1800a3a8e  mov     [rsp+660h+var_5F0], r9
0x1800a3a93  mov     rbx, r8
0x1800a3a96  mov     [rbp+560h+var_4B8], rbx
0x1800a3a9d  mov     rdi, rdx
0x1800a3aa0  mov     [rbp+560h+lpString1], rdx
0x1800a3aa4  mov     rax, [rbp+560h+arg_20]
0x1800a3aab  mov     [rbp+560h+var_580], rax
0x1800a3aaf  call    ?WaitForInit@EventService@@AEAAXXZ; EventService::WaitForInit(void)
0x1800a3ab4  xor     r15d, r15d
0x1800a3ab7  mov     [rbx], r15d
0x1800a3aba  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800a3abe  mov     r13, rsi
0x1800a3ac1  inc     r13
0x1800a3ac4  cmp     [rdi+r13*2], r15w
0x1800a3ac9  jnz     short loc_1800A3AC1
0x1800a3acb  mov     dword ptr [rbp+560h+Buf1+8], r13d
0x1800a3ad2  mov     rax, r13
0x1800a3ad5  shr     rax, 20h
0x1800a3ad9  mov     dword ptr [rbp+560h+Buf1+0Ch], eax
0x1800a3adf  mov     [rbp+560h+var_570], rdi
0x1800a3ae3  mov     rax, qword ptr [rbp+560h+Buf1+8]
0x1800a3aea  mov     [rbp+560h+var_568], rax
0x1800a3aee  lea     rcx, [rbp+560h+var_570]
0x1800a3af2  call    ?ShouldSkipLegacyChannelKey@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; ShouldSkipLegacyChannelKey(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800a3af7  test    al, al
0x1800a3af9  jnz     loc_1800A4452
0x1800a3aff  xor     ecx, ecx; BindingHandle
0x1800a3b01  call    cs:__imp_RpcImpersonateClient
0x1800a3b07  mov     ebx, eax
0x1800a3b09  test    eax, eax
0x1800a3b0b  jnz     loc_1800A45A0
0x1800a3b11  mov     [rsp+660h+var_61F], 1
0x1800a3b16  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800a3b1e  movdqu  [rbp+560h+var_550], xmm0
0x1800a3b23  mov     [rbp+560h+var_540], rsi
0x1800a3b27  lea     rcx, [rbp+560h+var_550]
0x1800a3b2b  call    ?_GrowMinimum@?$vector@U?$pair@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@U_GUID@@@utl@@V?$allocator@U?$pair@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@U_GUID@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>,utl::allocator<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>>>::_GrowMinimum(unsigned __int64)
0x1800a3b30  lea     rax, [rsp+660h+var_618]
0x1800a3b35  mov     [rsp+660h+var_618], rax
0x1800a3b3a  lea     rax, [rsp+660h+var_618]
0x1800a3b3f  mov     [rsp+660h+var_610], rax
0x1800a3b44  mov     [rsp+660h+var_608], rax
0x1800a3b49  mov     [rsp+660h+var_600], r15
0x1800a3b4e  lea     rax, [rbp+560h+var_4C8]
0x1800a3b55  mov     [rbp+560h+var_4D8], rax
0x1800a3b5c  lea     rax, [rbp+560h+var_4C8]
0x1800a3b63  mov     [rbp+560h+var_4D0], rax
0x1800a3b6a  mov     [rbp+560h+var_4C8], r15w
0x1800a3b72  mov     [rsp+660h+var_5F8], r15
0x1800a3b77  lea     rax, [rbp+560h+var_4E8]
0x1800a3b7b  mov     [rbp+560h+var_4F8], rax
0x1800a3b7f  lea     rax, [rbp+560h+var_4E8]
0x1800a3b83  mov     [rbp+560h+var_4F0], rax
0x1800a3b87  mov     [rbp+560h+var_4E8], r15w
0x1800a3b8c  mov     rax, rsi
0x1800a3b8f  inc     rax
0x1800a3b92  cmp     [rdi+rax*2], r15w
0x1800a3b97  jnz     short loc_1800A3B8F
0x1800a3b99  mov     qword ptr [rbp+560h+Buf1], rdi
0x1800a3ba0  mov     qword ptr [rbp+560h+Buf1+8], rax
0x1800a3ba7  lea     r9, [rbp+560h+var_4F8]
0x1800a3bab  lea     r8, [rsp+660h+var_5F8]
0x1800a3bb0  lea     rdx, [rbp+560h+Buf1]
0x1800a3bb7  call    ?GetLegacyChannelRegPath@RegistryPaths@@QEBAKV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@@Z; RegistryPaths::GetLegacyChannelRegPath(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800a3bbc  mov     ebx, eax
0x1800a3bbe  test    eax, eax
0x1800a3bc0  jnz     loc_1800A45F6
0x1800a3bc6  movdqa  xmm0, cs:__xmm@ffffffffffffffff0000000000000000
0x1800a3bce  movdqa  xmmword ptr [rbp+560h+var_4A0], xmm0
0x1800a3bd6  lea     rax, pszFormat
0x1800a3bdd  mov     [rbp+560h+Src], rax
0x1800a3be4  mov     [rbp+560h+var_488], r15
0x1800a3beb  mov     [rbp+560h+var_480], r15
0x1800a3bf2  xor     edx, edx; Val
0x1800a3bf4  mov     r8d, 200h; Size
0x1800a3bfa  lea     rcx, [rbp+560h+var_478]; void *
0x1800a3c01  call    memset_0
0x1800a3c06  nop
0x1800a3c07  mov     r9, rsi; void *
0x1800a3c0a  mov     r8, [rbp+560h+var_4F8]; wchar_t *
0x1800a3c0e  mov     rdx, [rsp+660h+var_5F8]; HKEY
0x1800a3c13  lea     rcx, [rbp+560h+var_4A0]; this
0x1800a3c1a  call    ?Reset@RegistryKeyEnumerator@@QEAAJPEAUHKEY__@@PEB_WPEAX@Z; RegistryKeyEnumerator::Reset(HKEY__ *,wchar_t const *,void *)
0x1800a3c1f  mov     ebx, eax
0x1800a3c21  mov     esi, 103h
0x1800a3c26  test    eax, eax
0x1800a3c28  jz      short loc_1800A3C38
0x1800a3c2a  cmp     eax, 2
0x1800a3c2d  jnz     loc_1800A44CA
0x1800a3c33  jmp     loc_1800A3D27
0x1800a3c38  mov     eax, dword ptr [rbp+560h+var_480+4]
0x1800a3c3e  mov     dword ptr [rbp+560h+var_480], eax
0x1800a3c44  jmp     loc_1800A3D13
0x1800a3c49  mov     rdi, [rbp+560h+Src]
0x1800a3c50  mov     rbx, [rbp+560h+var_488]
0x1800a3c57  lea     r9, [rbp+560h+var_4D8]
0x1800a3c5e  lea     r8, aProviderguid; "ProviderGuid"
0x1800a3c65  mov     rdx, rdi
0x1800a3c68  mov     rcx, [rbp+560h+var_4A0]; hKey
0x1800a3c6f  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800a3c74  test    eax, eax
0x1800a3c76  jnz     short loc_1800A3CBB
0x1800a3c78  xorps   xmm0, xmm0
0x1800a3c7b  movups  [rbp+560h+Buf1], xmm0
0x1800a3c82  lea     rdx, [rbp+560h+var_4D8]
0x1800a3c89  lea     rcx, [rbp+560h+Buf1]
0x1800a3c90  call    ??$string_to_guid@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(_GUID *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x1800a3c95  test    rax, rax
0x1800a3c98  jz      short loc_1800A3D13
0x1800a3c9a  lea     r9, [rbp+560h+Buf1]
0x1800a3ca1  lea     rdx, [rbp+560h+var_560]
0x1800a3ca5  lea     rcx, [rsp+660h+var_618]
0x1800a3caa  call    ??$_InsertImpl@AEBU_GUID@@@?$_Tree@U_GUID@@U1@VGuidLess@@V?$allocator@U_GUID@@@utl@@$0A@@utl@@AEAA?AU?$pair@V?$_TreeConstIt@U_GUID@@@utl@@_N@1@PEAU?$_TreeNode@U_GUID@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,_GUID,GuidLess,utl::allocator<_GUID>,0>::_InsertImpl<_GUID const &>(utl::_TreeNode<_GUID> *,_GUID const &)
0x1800a3caf  cmp     [rbp+560h+var_560], r15
0x1800a3cb3  jz      loc_1800A4541
0x1800a3cb9  jmp     short loc_1800A3D13
0x1800a3cbb  lea     rdx, [rbx+1]
0x1800a3cbf  lea     rcx, [rsp+660h+hKey]
0x1800a3cc4  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1800a3cc9  nop
0x1800a3cca  mov     rcx, [rsp+660h+hKey]; void *
0x1800a3ccf  test    rcx, rcx
0x1800a3cd2  jz      loc_1800A46AB
0x1800a3cd8  lea     r8, ds:2[rbx*2]; Size
0x1800a3ce0  mov     rdx, rdi; Src
0x1800a3ce3  call    memcpy_0
0x1800a3ce8  xorps   xmm0, xmm0
0x1800a3ceb  movups  [rbp+560h+var_508], xmm0
0x1800a3cef  lea     r8, [rbp+560h+var_508]
0x1800a3cf3  lea     rdx, [rsp+660h+hKey]
0x1800a3cf8  lea     rcx, [rbp+560h+var_550]
0x1800a3cfc  call    ??$emplace_back@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@AEAU_GUID@@$0A@@?$vector@U?$pair@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@U_GUID@@@utl@@V?$allocator@U?$pair@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@U_GUID@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@1@AEAU_GUID@@@Z; utl::vector<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>,utl::allocator<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>>>::emplace_back<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID &,0>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&,_GUID &)
0x1800a3d01  test    al, al
0x1800a3d03  jz      loc_1800A464C
0x1800a3d09  lea     rcx, [rsp+660h+hKey]
0x1800a3d0e  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x1800a3d13  lea     rcx, [rbp+560h+var_4A0]; this
0x1800a3d1a  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x1800a3d1f  cmp     eax, esi
0x1800a3d21  jnz     loc_1800A3C49
0x1800a3d27  lea     rax, [rbp+560h+var_5C8]
0x1800a3d2b  mov     [rbp+560h+var_5D8], rax
0x1800a3d2f  lea     rax, [rbp+560h+var_5C8]
0x1800a3d33  mov     [rbp+560h+var_5D0], rax
0x1800a3d37  mov     [rbp+560h+var_5C8], r15w
0x1800a3d3c  lea     rax, [rbp+560h+var_5A8]
0x1800a3d40  mov     [rbp+560h+lpString2], rax
0x1800a3d44  lea     rax, [rbp+560h+var_5A8]
0x1800a3d48  mov     [rbp+560h+var_5B0], rax
0x1800a3d4c  mov     [rbp+560h+var_5A8], r15w
0x1800a3d51  or      rdx, 0FFFFFFFFFFFFFFFFh; void *
0x1800a3d55  lea     rcx, [rbp+560h+var_270]; this
0x1800a3d5c  call    ??0PublisherConfigEnumerator@@QEAA@PEAX@Z; PublisherConfigEnumerator::PublisherConfigEnumerator(void *)
0x1800a3d61  nop
0x1800a3d62  mov     eax, [rbp+560h+var_24C]
0x1800a3d68  mov     [rbp+560h+var_250], eax
0x1800a3d6e  lea     rcx, [rbp+560h+var_270]; this
0x1800a3d75  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x1800a3d7a  lea     rsi, WPP_GLOBAL_Control
0x1800a3d81  mov     edi, 8
0x1800a3d86  cmp     eax, 103h
0x1800a3d8b  jz      loc_1800A41A3
0x1800a3d91  lea     rdx, [rbp+560h+var_5D8]
0x1800a3d95  lea     rcx, [rbp+560h+var_270]
0x1800a3d9c  call    ?GetCurrentPublisherName@PublisherConfigEnumerator@@QEAA_NAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PublisherConfigEnumerator::GetCurrentPublisherName(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800a3da1  test    al, al
0x1800a3da3  jz      loc_1800A4187
0x1800a3da9  mov     rbx, [rbp+560h+var_5D0]
0x1800a3dad  cmp     [rbp+560h+var_5D8], rbx
0x1800a3db1  jz      loc_1800A4187
0x1800a3db7  xorps   xmm0, xmm0
0x1800a3dba  movups  [rbp+560h+Buf1], xmm0
0x1800a3dc1  mov     r12, qword ptr [rbp+560h+var_260]
0x1800a3dc8  mov     qword ptr [rbp+560h+var_508], r12
0x1800a3dcc  mov     r15, qword ptr [rbp+560h+var_260+8]
0x1800a3dd3  mov     qword ptr [rbp+560h+var_508+8], r15
0x1800a3dd7  test    r15, r15
0x1800a3dda  jz      loc_1800A414B
0x1800a3de0  lea     rdx, [rbp+560h+var_508]
0x1800a3de4  lea     rcx, [rbp+560h+Buf1]
0x1800a3deb  call    ??$string_to_guid@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@@Z; tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(_GUID *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800a3df0  test    rax, rax
0x1800a3df3  jz      loc_1800A414B
0x1800a3df9  lea     rax, [rsp+660h+var_618]
0x1800a3dfe  cmp     [rsp+660h+var_608], rax
0x1800a3e03  jz      loc_1800A3EAC
0x1800a3e09  lea     rdx, [rbp+560h+Buf1]
0x1800a3e10  lea     rcx, [rsp+660h+var_618]
0x1800a3e15  call    ??$_LowerBoundNonEmpty@U_GUID@@@?$_Tree@U_GUID@@U1@VGuidLess@@V?$allocator@U_GUID@@@utl@@$0A@@utl@@AEBAPEAU?$_TreeNode@U_GUID@@@1@AEBU_GUID@@@Z; utl::_Tree<_GUID,_GUID,GuidLess,utl::allocator<_GUID>,0>::_LowerBoundNonEmpty<_GUID>(_GUID const &)
0x1800a3e1a  lea     rcx, [rsp+660h+var_618]
0x1800a3e1f  cmp     rax, rcx
0x1800a3e22  jz      loc_1800A3EAC
0x1800a3e28  lea     rdx, [rax+18h]; Buf2
0x1800a3e2c  mov     r8d, 10h; Size
0x1800a3e32  lea     rcx, [rbp+560h+Buf1]; Buf1
0x1800a3e39  call    memcmp_0
0x1800a3e3e  xor     r15d, r15d
0x1800a3e41  test    eax, eax
0x1800a3e43  js      short loc_1800A3EAF
0x1800a3e45  sub     rbx, [rbp+560h+var_5D8]
0x1800a3e49  sar     rbx, 1
0x1800a3e4c  lea     rdx, [rbx+1]
0x1800a3e50  lea     rcx, [rbp+560h+var_590]
0x1800a3e54  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1800a3e59  nop
0x1800a3e5a  mov     rcx, [rbp+560h+var_590]; void *
0x1800a3e5e  test    rcx, rcx
0x1800a3e61  jz      loc_1800A475F
0x1800a3e67  mov     r8, [rbp+560h+var_5D0]
0x1800a3e6b  mov     rdx, [rbp+560h+var_5D8]; Src
0x1800a3e6f  sub     r8, rdx
0x1800a3e72  sar     r8, 1
0x1800a3e75  lea     r8, ds:2[r8*2]; Size
0x1800a3e7d  call    memcpy_0
0x1800a3e82  lea     r8, [rbp+560h+Buf1]
0x1800a3e89  lea     rdx, [rbp+560h+var_590]
0x1800a3e8d  lea     rcx, [rbp+560h+var_550]
0x1800a3e91  call    ??$emplace_back@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@AEAU_GUID@@$0A@@?$vector@U?$pair@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@U_GUID@@@utl@@V?$allocator@U?$pair@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@U_GUID@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@1@AEAU_GUID@@@Z; utl::vector<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>,utl::allocator<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>>>::emplace_back<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID &,0>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&,_GUID &)
0x1800a3e96  test    al, al
0x1800a3e98  jz      loc_1800A470A
0x1800a3e9e  lea     rcx, [rbp+560h+var_590]
0x1800a3ea2  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x1800a3ea7  jmp     loc_1800A4187
0x1800a3eac  xor     r15d, r15d
0x1800a3eaf  lea     rdx, [rbp+560h+Buf1]
0x1800a3eb6  lea     rcx, [rbp+560h+var_5E0]
0x1800a3eba  call    ?GetRegCacheProviderNodebyGuid@@YA?AV?$AutoRef@UREG_CACHE_PROVIDERNODE@@@wmi@@PEBU_GUID@@@Z; GetRegCacheProviderNodebyGuid(_GUID const *)
0x1800a3ebf  nop
0x1800a3ec0  mov     rax, [rbp+560h+var_5E0]
0x1800a3ec4  test    rax, rax
0x1800a3ec7  jz      loc_1800A3F94
0x1800a3ecd  mov     r15, [rax+0B8h]
0x1800a3ed4  test    r15, r15
0x1800a3ed7  jz      loc_1800A3F94
0x1800a3edd  mov     r12d, [r15+8]
0x1800a3ee1  xor     ebx, ebx
0x1800a3ee3  test    r12d, r12d
0x1800a3ee6  jz      short loc_1800A3F19
0x1800a3ee8  lea     rcx, [rbx+rbx*2]
0x1800a3eec  mov     r8, [r15]
0x1800a3eef  mov     [rsp+660h+bIgnoreCase], 1; bIgnoreCase
0x1800a3ef7  mov     r9d, [r8+rcx*8+8]; cchCount2
0x1800a3efc  mov     r8, [r8+rcx*8]; lpString2
0x1800a3f00  mov     edx, r13d; cchCount1
0x1800a3f03  mov     rcx, [rbp+560h+lpString1]; lpString1
0x1800a3f07  call    cs:__imp_CompareStringOrdinal
0x1800a3f0d  cmp     eax, 2
0x1800a3f10  jz      short loc_1800A3F2A
0x1800a3f12  inc     ebx
0x1800a3f14  cmp     ebx, r12d
0x1800a3f17  jb      short loc_1800A3EE8
0x1800a3f19  xor     r15d, r15d
0x1800a3f1c  lea     rcx, [rbp+560h+var_5E0]
0x1800a3f20  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x1800a3f25  jmp     loc_1800A4187
0x1800a3f2a  mov     rdx, [rbp+560h+var_5D0]
0x1800a3f2e  sub     rdx, [rbp+560h+var_5D8]
0x1800a3f32  sar     rdx, 1
0x1800a3f35  inc     rdx
0x1800a3f38  lea     rcx, [rbp+560h+var_588]
0x1800a3f3c  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1800a3f41  nop
0x1800a3f42  mov     rcx, [rbp+560h+var_588]; void *
0x1800a3f46  xor     r15d, r15d
0x1800a3f49  test    rcx, rcx
0x1800a3f4c  jz      loc_1800A4809
0x1800a3f52  mov     r8, [rbp+560h+var_5D0]
0x1800a3f56  mov     rdx, [rbp+560h+var_5D8]; Src
0x1800a3f5a  sub     r8, rdx
0x1800a3f5d  sar     r8, 1
0x1800a3f60  lea     r8, ds:2[r8*2]; Size
0x1800a3f68  call    memcpy_0
0x1800a3f6d  lea     r8, [rbp+560h+Buf1]
0x1800a3f74  lea     rdx, [rbp+560h+var_588]
0x1800a3f78  lea     rcx, [rbp+560h+var_550]
0x1800a3f7c  call    ??$emplace_back@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@AEAU_GUID@@$0A@@?$vector@U?$pair@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@U_GUID@@@utl@@V?$allocator@U?$pair@V?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@U_GUID@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@1@AEAU_GUID@@@Z; utl::vector<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>,utl::allocator<utl::pair<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID>>>::emplace_back<utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>,_GUID &,0>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&,_GUID &)
0x1800a3f81  test    al, al
0x1800a3f83  jz      loc_1800A47B4
0x1800a3f89  lea     rcx, [rbp+560h+var_588]
0x1800a3f8d  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x1800a3f92  jmp     short loc_1800A3F1C
0x1800a3f94  mov     [rsp+660h+hKey], r15
0x1800a3f99  lea     rcx, [rsp+660h+hKey]
0x1800a3f9e  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800a3fa3  mov     rbx, rax
0x1800a3fa6  lea     rdx, [rbp+560h+var_570]
0x1800a3faa  lea     rcx, [rbp+560h+var_270]
  ... truncated ...
```
