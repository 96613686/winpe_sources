# EventService::GetPublisherMetadata(wchar_t const *,ulong,ulong,tag_EvtRpcVariantList &)

- ea: `0x18003a2e4`
- end: `0x18003b069`
- name: `?GetPublisherMetadata@EventService@@QEAAPEAV?$ClientObjectWrapper@VPublisherMetadata@@@@PEB_WKKAEAUtag_EvtRpcVariantList@@@Z`
- size: `3461`
- prototype: `wmi::RefBase *__fastcall(RTL_SRWLOCK *, __int64, unsigned int, __int16, _QWORD *)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x18007c7f0`

## callees

- `0x180003de0`
- `0x18000bf10`
- `0x180014bd0`
- `0x180016250`
- `0x180017128`
- `0x180017b60`
- `0x180017b98`
- `0x180019d28`
- `0x18001c320`
- `0x18002c6f4`
- `0x18002d204`
- `0x18002de70`
- `0x18002de9c`
- `0x1800341a4`
- `0x180034704`
- `0x180038c28`
- `0x180038e74`
- `0x18003a24c`
- `0x18003a2e4`
- `0x18003b070`
- `0x18003ce74`
- `0x18005de2c`
- `0x18006cca8`
- `0x18006da88`
- `0x18006e3b0`
- `0x18006ef14`
- `0x18007000c`
- `0x180073c54`
- `0x18007feac`
- `0x1800909cc`
- `0x180092008`
- `0x18009aee0`
- `0x18009bb88`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003a7d7`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003ac31`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003a7d7`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18003ac31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a7a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003abfe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a7a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003abfe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a7f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ac51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ac7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003acdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a7f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ac51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ac7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003acdb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a39a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a39a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a6d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a6d5`
- `RPCRT4!RpcImpersonateClient` at `0x18003a374`
- `RPCRT4!RpcImpersonateClient` at `0x18003a374`
- `RPCRT4!RpcRevertToSelf` at `0x18003a3d3`
- `RPCRT4!RpcRevertToSelf` at `0x18003a3d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
wmi::RefBase *__fastcall EventService::GetPublisherMetadata(
        RTL_SRWLOCK *a1,
        __int64 a2,
        unsigned int a3,
        __int16 a4,
        _QWORD *a5)
{
  char v5; // di^1
  void *v9; // rax
  void *v10; // rbx
  unsigned int v11; // ebx
  RTL_SRWLOCK *v12; // rsi
  __int64 v13; // rax
  wmi::RefBase *v14; // r14
  __int64 v15; // rbx
  char v16; // al
  char v17; // al
  char v18; // al
  wmi::RefBase *v19; // rax
  volatile signed __int32 *v20; // r12
  void *v21; // rax
  char *v22; // rdi
  struct HKEY__ *v23; // rcx
  __int64 v24; // rbx
  void *v26; // rax
  wmi::RefBase *v27; // rbx
  __int64 v28; // rdi
  HKEY v29; // rbx
  BYTE *lpData; // rcx
  LSTATUS v31; // eax
  size_t v32; // rax
  struct HKEY__ *v33; // rbx
  struct HKEY__ *v34; // rdi
  char *v35; // r14
  _BYTE *v36; // r13
  __int64 v37; // rcx
  char *v38; // rax
  struct HKEY__ *v39; // r8
  HKEY v40; // rcx
  _DWORD *v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rcx
  char *v44; // rdx
  unsigned int v45; // edx
  unsigned int ChannelMsgID; // eax
  char *v47; // rax
  void *v48; // rbx
  void *v49; // rdi
  __int64 i; // r14
  char *v51; // r8
  DWORD v52; // eax
  HKEY v53; // rbx
  BYTE *v54; // rcx
  LSTATUS Value; // eax
  size_t v56; // rax
  bool v57; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v58; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v60; // [rsp+49h] [rbp-B7h]
  void *v61; // [rsp+50h] [rbp-B0h] BYREF
  signed __int64 v62; // [rsp+58h] [rbp-A8h]
  __int128 v63; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v65; // [rsp+78h] [rbp-88h]
  char *v66; // [rsp+80h] [rbp-80h]
  wmi::RefBase *v67; // [rsp+88h] [rbp-78h] BYREF
  void *v68[2]; // [rsp+90h] [rbp-70h] BYREF
  HKEY v69; // [rsp+A0h] [rbp-60h]
  int v70; // [rsp+A8h] [rbp-58h]
  int v71; // [rsp+ACh] [rbp-54h]
  int v72; // [rsp+B0h] [rbp-50h]
  char v73; // [rsp+B4h] [rbp-4Ch]
  int v74; // [rsp+B8h] [rbp-48h] BYREF
  char *v75; // [rsp+C0h] [rbp-40h]
  __int128 pExceptionObject; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v77; // [rsp+D8h] [rbp-28h]
  int v78; // [rsp+E0h] [rbp-20h]
  int v79; // [rsp+E4h] [rbp-1Ch]
  int v80; // [rsp+E8h] [rbp-18h]
  void *v81; // [rsp+F0h] [rbp-10h] BYREF
  char *v82; // [rsp+F8h] [rbp-8h]
  char *v83; // [rsp+100h] [rbp+0h]
  LPBYTE v84; // [rsp+108h] [rbp+8h] BYREF
  __int64 v85; // [rsp+110h] [rbp+10h]
  char v86; // [rsp+118h] [rbp+18h] BYREF
  void *v87; // [rsp+128h] [rbp+28h] BYREF
  void *v88; // [rsp+130h] [rbp+30h]
  char *v89; // [rsp+138h] [rbp+38h]
  LPBYTE v90; // [rsp+140h] [rbp+40h] BYREF
  __int64 v91; // [rsp+148h] [rbp+48h]
  char v92; // [rsp+150h] [rbp+50h] BYREF
  void *v93; // [rsp+160h] [rbp+60h] BYREF
  char *v94; // [rsp+168h] [rbp+68h]
  char *v95; // [rsp+170h] [rbp+70h]
  void *v96; // [rsp+178h] [rbp+78h] BYREF
  __int64 v97; // [rsp+180h] [rbp+80h]
  __int64 v98; // [rsp+188h] [rbp+88h]
  void *v99; // [rsp+190h] [rbp+90h] BYREF
  struct HKEY__ *v100; // [rsp+198h] [rbp+98h]
  void *v101[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  char v102; // [rsp+1B8h] [rbp+B8h] BYREF
  void *v103; // [rsp+1C8h] [rbp+C8h]
  RTL_SRWLOCK *v104; // [rsp+1D0h] [rbp+D0h]
  volatile signed __int32 *v105; // [rsp+1D8h] [rbp+D8h]
  HKEY hKey[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v107; // [rsp+1F0h] [rbp+F0h]
  __int64 v108; // [rsp+200h] [rbp+100h] BYREF
  char v109[32]; // [rsp+208h] [rbp+108h] BYREF
  char v110[32]; // [rsp+228h] [rbp+128h] BYREF
  _BYTE v111[40]; // [rsp+248h] [rbp+148h] BYREF

  v5 = HIBYTE(a4);
  v61 = a5;
  EventService::WaitForInit(a1);
  *(_OWORD *)a5 = 0;
  v9 = operator new(0x2B8u);
  v10 = v9;
  if ( v9 )
  {
    memset_0(v9, 0, 0x2B8u);
    __builtin_array_init_helper<tag_EvtRpcVariant>(v10, 29);
  }
  else
  {
    v10 = 0;
  }
  v103 = v10;
  a5[1] = v10;
  *(_DWORD *)a5 = 29;
  if ( !a2 )
  {
    EventRendering::GetWinmetaPublisherMetadata(&v67, a3);
    v26 = MIDL_user_allocate(0x18u);
    v27 = v67;
    if ( v26 )
      v28 = ClientObjectWrapper<PublisherMetadata>::ClientObjectWrapper<PublisherMetadata>(v26, 5, v67);
    else
      v28 = 0;
    v61 = (void *)v28;
    if ( !v28 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
      }
      *(_OWORD *)v68 = 0;
      v69 = 0;
      v70 = 14;
      v71 = -1;
      v72 = 3058;
      throw (EvtException *)v68;
    }
    if ( v27 )
      wmi::RefBase::Release(v27);
    return (wmi::RefBase *)v28;
  }
  v11 = RpcImpersonateClient(0);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v11);
    }
    v68[0] = (void *)&byte_1800EC961;
    v68[1] = 0;
    v69 = 0;
    v70 = v11;
    v71 = -1;
    v72 = -1;
    v73 = 0;
    throw (EvtException *)v68;
  }
  v60 = 1;
  v12 = a1 + 59;
  v104 = v12;
  AcquireSRWLockExclusive(v12);
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(a2 + 2 * v13) );
  *(_QWORD *)&v63 = a2;
  *((_QWORD *)&v63 + 1) = v13;
  PublisherConfigReader::PublisherConfigReader((PublisherConfigReader *)hKey);
  RpcRevertToSelf();
  v14 = 0;
  v60 = 0;
  v57 = 0;
  if ( PublisherConfigReader::GetEnabled((PublisherConfigReader *)hKey, &v57) && !v57 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 15037);
    }
    *(_OWORD *)v68 = 0;
    v69 = 0;
    v70 = 15037;
    v71 = -1;
    v72 = 3095;
    throw (EvtException *)v68;
  }
  v63 = v107;
  InitializeMetadataProp_2(a5, 0, &v63);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v90);
  v15 = v108;
  if ( v108 )
  {
    v16 = 0;
    if ( (*(_DWORD *)(v108 + 192) & 0x200) != 0 )
    {
      v16 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
              &v90,
              *(_QWORD *)(v108 + 40),
              *(_QWORD *)(v108 + 48));
      v15 = v108;
    }
    if ( !v16 )
      goto LABEL_14;
  }
  else
  {
    v53 = hKey[0];
    v54 = v90;
    cbData[0] = 2 * ((v91 - (__int64)v90) >> 1);
    Type[0] = 0;
    v58 = 0;
    while ( 1 )
    {
      Value = RegQueryValueExW(v53, L"ResourceFileName", 0, Type, v54, cbData);
      if ( Value != 234 )
        break;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                               &v90,
                               (unsigned __int64)cbData[0] >> 1) )
        goto LABEL_114;
      v54 = v90;
    }
    if ( Value )
    {
LABEL_114:
      if ( v58 )
        RegCloseKey(v58);
      goto LABEL_13;
    }
    if ( Type[0] - 1 > 1 )
    {
      tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v58);
      goto LABEL_13;
    }
    v56 = wcsnlen((const wchar_t *)v90, (unsigned __int64)cbData[0] >> 1);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(&v90, v56);
    if ( v58 )
      RegCloseKey(v58);
  }
  *(_QWORD *)&v63 = v90;
  *((_QWORD *)&v63 + 1) = (v91 - (__int64)v90) >> 1;
  InitializeMetadataProp_0(a5, 1, &v63);
LABEL_13:
  v15 = v108;
LABEL_14:
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v101);
  if ( !v15 )
  {
    if ( (unsigned int)RegReadStringValueNoThrow(hKey[0]) )
      goto LABEL_19;
    goto LABEL_18;
  }
  v17 = 0;
  if ( (*(_DWORD *)(v15 + 192) & 0x400) != 0 )
  {
    v17 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
            v101,
            *(_QWORD *)(v15 + 72),
            *(_QWORD *)(v15 + 80));
    v15 = v108;
  }
  if ( v17 )
  {
LABEL_18:
    *(void **)&v63 = v101[0];
    *((_QWORD *)&v63 + 1) = ((char *)v101[1] - (char *)v101[0]) >> 1;
    InitializeMetadataProp_0(a5, 2, &v63);
LABEL_19:
    v15 = v108;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v84);
  if ( v15 )
  {
    v18 = 0;
    if ( (*(_DWORD *)(v15 + 192) & 0x100) != 0 )
      v18 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
              &v84,
              *(_QWORD *)(v15 + 56),
              *(_QWORD *)(v15 + 64));
    if ( !v18 )
      goto LABEL_24;
  }
  else if ( v111[32] )
  {
    v29 = hKey[0];
    lpData = v84;
    cbData[0] = 2 * ((v85 - (__int64)v84) >> 1);
    Type[0] = 0;
    v58 = 0;
    while ( 1 )
    {
      v31 = RegQueryValueExW(v29, L"EventMessageFile", 0, Type, lpData, cbData);
      if ( v31 != 234 )
        break;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                               &v84,
                               (unsigned __int64)cbData[0] >> 1) )
        goto LABEL_110;
      lpData = v84;
    }
    if ( v31 )
    {
LABEL_110:
      if ( v58 )
        RegCloseKey(v58);
      goto LABEL_24;
    }
    if ( Type[0] - 1 > 1 )
    {
      tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v58);
      goto LABEL_24;
    }
    v32 = wcsnlen((const wchar_t *)v84, (unsigned __int64)cbData[0] >> 1);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(&v84, v32);
    if ( v58 )
      RegCloseKey(v58);
  }
  else if ( (unsigned int)RegReadStringValueNoThrow(hKey[0]) )
  {
    goto LABEL_24;
  }
  *(_QWORD *)&v63 = v84;
  *((_QWORD *)&v63 + 1) = (v85 - (__int64)v84) >> 1;
  InitializeMetadataProp_0(a5, 3, &v63);
LABEL_24:
  v19 = (wmi::RefBase *)operator new(0x180u);
  v67 = v19;
  if ( v19 )
    v20 = (volatile signed __int32 *)PublisherMetadata::PublisherMetadata(
                                       v19,
                                       (const struct PublisherConfigReader *)hKey,
                                       a3,
                                       (v5 & 1) == 0);
  else
    v20 = 0;
  v105 = v20;
  if ( v20 )
    _InterlockedIncrement(v20 + 2);
  v21 = MIDL_user_allocate(0x18u);
  if ( v21 )
    v14 = (wmi::RefBase *)ClientObjectWrapper<PublisherMetadata>::ClientObjectWrapper<PublisherMetadata>(v21, 5, v20);
  v67 = v14;
  *(_QWORD *)&v63 = v14;
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
    }
    pExceptionObject = 0;
    v77 = 0;
    v78 = 14;
    v79 = -1;
    v80 = 3141;
    throw (EvtException *)&pExceptionObject;
  }
  utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(&v99);
  if ( (unsigned __int8)PublisherConfigReader::GetChannelReferencesWithLegacyChannels(hKey, &v99) )
  {
    utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(&v87);
    utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(v68);
    utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(&v96);
    utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(&v93);
    utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(&v81);
    v33 = (struct HKEY__ *)v99;
    v34 = v100;
    v35 = (char *)v88;
    v36 = v87;
    v58 = (HKEY)v68[1];
    v37 = v97;
    *(_QWORD *)cbData = v97;
    v75 = v94;
    v38 = v82;
    while ( 1 )
    {
      v66 = v38;
      if ( v33 == v34 )
        break;
      if ( v35 == v89 )
      {
        *(_QWORD *)Type = (char *)v33 - v36;
        if ( !(unsigned __int8)utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Grow(&v87) )
          goto LABEL_118;
        v39 = v33;
        v35 = (char *)v88;
        v36 = v87;
        v37 = *(_QWORD *)Type;
        if ( *(_QWORD *)Type < (unsigned __int64)((_BYTE *)v88 - (_BYTE *)v87) )
          v39 = (struct HKEY__ *)((char *)v87 + *(_QWORD *)Type);
      }
      else
      {
        v39 = v33;
      }
      if ( !(unsigned __int8)utl::allocator_traits<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::construct<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &>(
                               v37,
                               v35,
                               v39) )
      {
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
LABEL_118:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
        }
        pExceptionObject = 0;
        v77 = 0;
        v78 = 14;
        v79 = -1;
        v80 = 3159;
        throw (EvtException *)&pExceptionObject;
      }
      v35 += 32;
      v88 = v35;
      v40 = v58;
      if ( v58 == v69 )
      {
        if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_PushBackOne2<unsigned long const &>(
                                 v68,
                                 v33 + 9) )
          goto LABEL_118;
        v58 = (HKEY)v68[1];
      }
      else
      {
        *(_DWORD *)v58 = v33[9];
        v58 = v40 + 1;
        v68[1] = v40 + 1;
      }
      v41 = v33 + 8;
      v42 = *(_QWORD *)cbData;
      if ( *(_QWORD *)cbData == v98 )
      {
        if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_PushBackOne2<unsigned long const &>(
                                 &v96,
                                 v41) )
          goto LABEL_118;
        v43 = v97;
      }
      else
      {
        **(_DWORD **)cbData = *v41;
        v43 = v42 + 4;
        v97 = v43;
      }
      *(_QWORD *)cbData = v43;
      v44 = v75;
      if ( v75 == v95 )
      {
        if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_PushBackOne2<unsigned long const &>(
                                 &v93,
                                 v33 + 10) )
          goto LABEL_118;
        v75 = v94;
      }
      else
      {
        *(_DWORD *)(struct HKEY__ *)v75 = v33[10];
        v75 = v44 + 4;
        v94 = v44 + 4;
      }
      v37 = 0xFFFFFFFFLL;
      v74 = -1;
      v45 = *((_DWORD *)v33 + 9);
      Type[0] = -1;
      if ( v45 != -1 )
      {
        ChannelMsgID = PublisherMetadata::GetChannelMsgID((PublisherMetadata *)v20, v45);
        v37 = ChannelMsgID;
        v74 = ChannelMsgID;
        Type[0] = ChannelMsgID;
      }
      v47 = v66;
      if ( v66 == v83 )
      {
        v66 = (char *)((char *)&v74 - (_BYTE *)v81);
        if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_Grow(&v81) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
          }
          pExceptionObject = 0;
          v77 = 0;
          v78 = 14;
          v79 = -1;
          v80 = 3170;
          throw (EvtException *)&pExceptionObject;
        }
        v51 = v82;
        v37 = (__int64)v66;
        if ( (unsigned __int64)v66 < v82 - (_BYTE *)v81 )
          v52 = *(_DWORD *)&v66[(_QWORD)v81];
        else
          v52 = Type[0];
        *(_DWORD *)v82 = v52;
        v38 = v51 + 4;
      }
      else
      {
        *(_DWORD *)v66 = v37;
        v38 = v47 + 4;
      }
      v82 = v38;
      v33 += 12;
    }
    *(_QWORD *)Type = v36;
    v65 = (v35 - v36) >> 5;
    v48 = v61;
    InitializeMetadataProp_1(v61, 7, Type);
    v61 = v68[0];
    v62 = ((char *)v58 - (char *)v68[0]) >> 2;
    InitializeMetadataProp(v48, 8, &v61);
    v61 = v96;
    v62 = (__int64)(*(_QWORD *)cbData - (_QWORD)v96) >> 2;
    InitializeMetadataProp(v48, 9, &v61);
    v61 = v93;
    v62 = (v75 - (_BYTE *)v93) >> 2;
    InitializeMetadataProp(v48, 10, &v61);
    v49 = v81;
    v61 = v81;
    v62 = (v66 - (_BYTE *)v81) >> 2;
    InitializeMetadataProp(v48, 11, &v61);
    if ( v49 != (void *)-1LL )
      operator delete(v49);
    if ( v93 != (void *)-1LL )
      operator delete(v93);
    if ( v96 != (void *)-1LL )
      operator delete(v96);
    if ( v68[0] != (void *)-1LL )
      operator delete(v68[0]);
    if ( v36 != (_BYTE *)-1LL )
    {
      for ( i = (v35 - v36) >> 5;
            i;
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v36[32 * i]) )
      {
        --i;
      }
      operator delete(v36);
    }
    v14 = v67;
  }
  v22 = (char *)v99;
  if ( v99 != (void *)-1LL )
  {
    v23 = v100;
    v100 = (struct HKEY__ *)v99;
    v24 = ((char *)v23 - (_BYTE *)v99) / 48;
    if ( v24 )
    {
      do
      {
        --v24;
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v22[48 * v24]);
      }
      while ( v24 );
      v22 = (char *)v99;
    }
    operator delete(v22);
  }
  if ( v20 )
    wmi::RefBase::Release((wmi::RefBase *)v20);
  if ( v84 != (LPBYTE)&v86 )
    operator delete(v84);
  if ( v101[0] != &v102 )
    operator delete(v101[0]);
  if ( v90 != (LPBYTE)&v92 )
    operator delete(v90);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v111);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v110);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v109);
  wmi::AutoRef<PublisherMetadata>::Release(&v108);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
  ReleaseSRWLockExclusive(v12);
  return v14;
}

```

## disassembly

```asm
0x18003a2e4  mov     [rsp-8+arg_8], rbx
0x18003a2e9  push    rbp
0x18003a2ea  push    rsi
0x18003a2eb  push    rdi
0x18003a2ec  push    r12
0x18003a2ee  push    r13
0x18003a2f0  push    r14
0x18003a2f2  push    r15
0x18003a2f4  lea     rbp, [rsp-180h]
0x18003a2fc  sub     rsp, 280h
0x18003a303  mov     rax, cs:__security_cookie
0x18003a30a  xor     rax, rsp
0x18003a30d  mov     [rbp+1B0h+var_40], rax
0x18003a314  mov     edi, r9d
0x18003a317  mov     r13d, r8d
0x18003a31a  mov     r14, rdx
0x18003a31d  mov     rsi, rcx
0x18003a320  mov     r12, [rbp+1B0h+arg_20]
0x18003a327  mov     [rsp+2B0h+var_260], r12
0x18003a32c  call    ?WaitForInit@EventService@@AEAAXXZ; EventService::WaitForInit(void)
0x18003a331  xorps   xmm0, xmm0
0x18003a334  movups  xmmword ptr [r12], xmm0
0x18003a339  mov     ecx, 2B8h; dwBytes
0x18003a33e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a343  mov     rbx, rax
0x18003a346  xor     r15d, r15d
0x18003a349  test    rax, rax
0x18003a34c  jnz     loc_18003AD43
0x18003a352  mov     ebx, r15d
0x18003a355  mov     [rbp+1B0h+var_E8], rbx
0x18003a35c  mov     [r12+8], rbx
0x18003a361  mov     dword ptr [r12], 1Dh
0x18003a369  test    r14, r14
0x18003a36c  jz      loc_18003A709
0x18003a372  xor     ecx, ecx; BindingHandle
0x18003a374  call    cs:__imp_RpcImpersonateClient
0x18003a37a  mov     ebx, eax
0x18003a37c  test    eax, eax
0x18003a37e  jnz     loc_18003ADD0
0x18003a384  mov     [rsp+2B0h+var_267], 1
0x18003a389  add     rsi, 1D8h
0x18003a390  mov     [rbp+1B0h+var_E0], rsi
0x18003a397  mov     rcx, rsi; SRWLock
0x18003a39a  call    cs:__imp_AcquireSRWLockExclusive
0x18003a3a0  nop
0x18003a3a1  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003a3a5  mov     rax, r15
0x18003a3a8  xor     ecx, ecx
0x18003a3aa  inc     rax
0x18003a3ad  cmp     [r14+rax*2], cx
0x18003a3b2  jnz     short loc_18003A3AA
0x18003a3b4  mov     qword ptr [rsp+2B0h+var_250], r14
0x18003a3b9  mov     qword ptr [rsp+2B0h+var_250+8], rax
0x18003a3be  mov     r8, r15
0x18003a3c1  lea     rdx, [rsp+2B0h+var_250]
0x18003a3c6  lea     rcx, [rbp+1B0h+hKey]; this
0x18003a3cd  call    ??0PublisherConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z; PublisherConfigReader::PublisherConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x18003a3d2  nop
0x18003a3d3  call    cs:__imp_RpcRevertToSelf
0x18003a3d9  xor     r14d, r14d
0x18003a3dc  mov     [rsp+2B0h+var_267], r14b
0x18003a3e1  mov     [rsp+2B0h+var_280], r14b
0x18003a3e6  lea     rdx, [rsp+2B0h+var_280]; bool *
0x18003a3eb  lea     rcx, [rbp+1B0h+hKey]; this
0x18003a3f2  call    ?GetEnabled@PublisherConfigReader@@QEBA_NAEA_N@Z; PublisherConfigReader::GetEnabled(bool &)
0x18003a3f7  test    al, al
0x18003a3f9  jnz     loc_18003AE41
0x18003a3ff  movaps  xmm0, [rbp+1B0h+var_C0]
0x18003a406  movdqu  [rsp+2B0h+var_250], xmm0
0x18003a40c  lea     r8, [rsp+2B0h+var_250]
0x18003a411  xor     edx, edx
0x18003a413  mov     rcx, r12
0x18003a416  call    InitializeMetadataProp_2
0x18003a41b  lea     rcx, [rbp+1B0h+var_170]; void *
0x18003a41f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18003a424  nop
0x18003a425  mov     rbx, [rbp+1B0h+var_B0]
0x18003a42c  test    rbx, rbx
0x18003a42f  jz      loc_18003ABB8
0x18003a435  mov     al, r14b
0x18003a438  test    dword ptr [rbx+0C0h], 200h
0x18003a442  jz      short loc_18003A45C
0x18003a444  mov     r8, [rbx+30h]
0x18003a448  mov     rdx, [rbx+28h]
0x18003a44c  lea     rcx, [rbp+1B0h+var_170]
0x18003a450  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18003a455  mov     rbx, [rbp+1B0h+var_B0]
0x18003a45c  test    al, al
0x18003a45e  jz      short loc_18003A491
0x18003a460  mov     rax, [rbp+1B0h+var_170]
0x18003a464  mov     qword ptr [rsp+2B0h+var_250], rax
0x18003a469  mov     rcx, [rbp+1B0h+var_168]
0x18003a46d  sub     rcx, rax
0x18003a470  sar     rcx, 1
0x18003a473  mov     qword ptr [rsp+2B0h+var_250+8], rcx
0x18003a478  lea     r8, [rsp+2B0h+var_250]
0x18003a47d  mov     edx, 1
0x18003a482  mov     rcx, r12
0x18003a485  call    InitializeMetadataProp_0
0x18003a48a  mov     rbx, [rbp+1B0h+var_B0]
0x18003a491  lea     rcx, [rbp+1B0h+var_108]; void *
0x18003a498  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18003a49d  nop
0x18003a49e  test    rbx, rbx
0x18003a4a1  jz      loc_18003AEC6
0x18003a4a7  mov     al, r14b
0x18003a4aa  test    dword ptr [rbx+0C0h], 400h
0x18003a4b4  jz      short loc_18003A4D1
0x18003a4b6  mov     r8, [rbx+50h]
0x18003a4ba  mov     rdx, [rbx+48h]
0x18003a4be  lea     rcx, [rbp+1B0h+var_108]
0x18003a4c5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18003a4ca  mov     rbx, [rbp+1B0h+var_B0]
0x18003a4d1  test    al, al
0x18003a4d3  jz      short loc_18003A50C
0x18003a4d5  mov     rax, [rbp+1B0h+var_108]
0x18003a4dc  mov     qword ptr [rsp+2B0h+var_250], rax
0x18003a4e1  mov     rcx, [rbp+1B0h+var_100]
0x18003a4e8  sub     rcx, rax
0x18003a4eb  sar     rcx, 1
0x18003a4ee  mov     qword ptr [rsp+2B0h+var_250+8], rcx
0x18003a4f3  lea     r8, [rsp+2B0h+var_250]
0x18003a4f8  mov     edx, 2
0x18003a4fd  mov     rcx, r12
0x18003a500  call    InitializeMetadataProp_0
0x18003a505  mov     rbx, [rbp+1B0h+var_B0]
0x18003a50c  lea     rcx, [rbp+1B0h+var_1A8]; void *
0x18003a510  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18003a515  nop
0x18003a516  test    rbx, rbx
0x18003a519  jz      loc_18003A751
0x18003a51f  mov     al, r14b
0x18003a522  test    dword ptr [rbx+0C0h], 100h
0x18003a52c  jz      short loc_18003A53F
0x18003a52e  mov     r8, [rbx+40h]
0x18003a532  mov     rdx, [rbx+38h]
0x18003a536  lea     rcx, [rbp+1B0h+var_1A8]
0x18003a53a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18003a53f  test    al, al
0x18003a541  jnz     loc_18003A7F9
0x18003a547  shr     edi, 8
0x18003a54a  not     dil
0x18003a54d  and     dil, 1
0x18003a551  mov     ecx, 180h; dwBytes
0x18003a556  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a55b  mov     [rbp+1B0h+var_228], rax
0x18003a55f  test    rax, rax
0x18003a562  jz      loc_18003A828
0x18003a568  movzx   r8d, r13w; unsigned __int16
0x18003a56c  mov     r9b, dil; bool
0x18003a56f  lea     rdx, [rbp+1B0h+hKey]; struct PublisherConfigReader *
0x18003a576  mov     rcx, rax; this
0x18003a579  call    ??0PublisherMetadata@@QEAA@AEBVPublisherConfigReader@@G_N@Z; PublisherMetadata::PublisherMetadata(PublisherConfigReader const &,ushort,bool)
0x18003a57e  mov     r12, rax
0x18003a581  mov     [rbp+1B0h+var_D8], r12
0x18003a588  test    r12, r12
0x18003a58b  jz      short loc_18003A593
0x18003a58d  lock inc dword ptr [r12+8]
0x18003a593  mov     ecx, 18h; size
0x18003a598  call    MIDL_user_allocate
0x18003a59d  test    rax, rax
0x18003a5a0  jnz     loc_18003AC89
0x18003a5a6  mov     [rbp+1B0h+var_228], r14
0x18003a5aa  mov     qword ptr [rsp+2B0h+var_250], r14
0x18003a5af  xor     r13d, r13d
0x18003a5b2  test    r14, r14
0x18003a5b5  jz      loc_18003AFFE
0x18003a5bb  lea     rcx, [rbp+1B0h+var_120]; void *
0x18003a5c2  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x18003a5c7  nop
0x18003a5c8  lea     rdx, [rbp+1B0h+var_120]
0x18003a5cf  lea     rcx, [rbp+1B0h+hKey]
0x18003a5d6  call    ?GetChannelReferencesWithLegacyChannels@PublisherConfigReader@@QEBA_NAEAV?$vector@UChannelReference@@V?$allocator@UChannelReference@@@utl@@@utl@@@Z; PublisherConfigReader::GetChannelReferencesWithLegacyChannels(utl::vector<ChannelReference,utl::allocator<ChannelReference>> &)
0x18003a5db  test    al, al
0x18003a5dd  jnz     loc_18003A830
0x18003a5e3  mov     rdi, [rbp+1B0h+var_120]
0x18003a5ea  cmp     rdi, r15
0x18003a5ed  jz      short loc_18003A648
0x18003a5ef  mov     rcx, [rbp+1B0h+var_118]
0x18003a5f6  mov     [rbp+1B0h+var_118], rdi
0x18003a5fd  sub     rcx, rdi
0x18003a600  mov     rax, 2AAAAAAAAAAAAAABh
0x18003a60a  imul    rcx
0x18003a60d  mov     rbx, rdx
0x18003a610  sar     rbx, 3
0x18003a614  mov     rax, rbx
0x18003a617  shr     rax, 3Fh
0x18003a61b  add     rbx, rax
0x18003a61e  jz      short loc_18003A63F
0x18003a620  dec     rbx
0x18003a623  lea     rcx, [rbx+rbx*2]
0x18003a627  shl     rcx, 4
0x18003a62b  add     rcx, rdi; void *
0x18003a62e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003a633  test    rbx, rbx
0x18003a636  jnz     short loc_18003A620
0x18003a638  mov     rdi, [rbp+1B0h+var_120]
0x18003a63f  mov     rcx, rdi; void *
0x18003a642  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a647  nop
0x18003a648  test    r12, r12
0x18003a64b  jz      short loc_18003A656
0x18003a64d  mov     rcx, r12; this
0x18003a650  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18003a655  nop
0x18003a656  lea     rax, [rbp+1B0h+var_198]
0x18003a65a  mov     rcx, [rbp+1B0h+var_1A8]; void *
0x18003a65e  cmp     rcx, rax
0x18003a661  jz      short loc_18003A669
0x18003a663  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a668  nop
0x18003a669  lea     rax, [rbp+1B0h+var_F8]
0x18003a670  mov     rcx, [rbp+1B0h+var_108]; void *
0x18003a677  cmp     rcx, rax
0x18003a67a  jz      short loc_18003A682
0x18003a67c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a681  nop
0x18003a682  lea     rax, [rbp+1B0h+var_160]
0x18003a686  mov     rcx, [rbp+1B0h+var_170]; void *
0x18003a68a  cmp     rcx, rax
0x18003a68d  jz      short loc_18003A695
0x18003a68f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a694  nop
0x18003a695  lea     rcx, [rbp+1B0h+var_68]; void *
0x18003a69c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003a6a1  lea     rcx, [rbp+1B0h+var_88]; void *
0x18003a6a8  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003a6ad  lea     rcx, [rbp+1B0h+var_A8]; void *
0x18003a6b4  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18003a6b9  lea     rcx, [rbp+1B0h+var_B0]
0x18003a6c0  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18003a6c5  lea     rcx, [rbp+1B0h+hKey]
0x18003a6cc  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18003a6d1  nop
0x18003a6d2  mov     rcx, rsi; SRWLock
0x18003a6d5  call    cs:__imp_ReleaseSRWLockExclusive
0x18003a6db  nop
0x18003a6dc  mov     rax, r14
0x18003a6df  mov     rcx, [rbp+1B0h+var_40]
0x18003a6e6  xor     rcx, rsp; StackCookie
0x18003a6e9  call    __security_check_cookie
0x18003a6ee  mov     rbx, [rsp+2B0h+arg_8]
0x18003a6f6  add     rsp, 280h
0x18003a6fd  pop     r15
0x18003a6ff  pop     r14
0x18003a701  pop     r13
0x18003a703  pop     r12
0x18003a705  pop     rdi
0x18003a706  pop     rsi
0x18003a707  pop     rbp
0x18003a708  retn
0x18003a709  mov     edx, r13d
0x18003a70c  lea     rcx, [rbp+1B0h+var_228]
0x18003a710  call    ?GetWinmetaPublisherMetadata@EventRendering@@YA?AV?$AutoRef@VPublisherMetadata@@@wmi@@K@Z; EventRendering::GetWinmetaPublisherMetadata(ulong)
0x18003a715  nop
0x18003a716  mov     ecx, 18h; size
0x18003a71b  call    MIDL_user_allocate
0x18003a720  mov     rbx, [rbp+1B0h+var_228]
0x18003a724  test    rax, rax
0x18003a727  jnz     loc_18003ACA1
0x18003a72d  mov     rdi, r15
0x18003a730  mov     [rsp+2B0h+var_260], rdi
0x18003a735  test    rdi, rdi
0x18003a738  jz      loc_18003AD65
0x18003a73e  test    rbx, rbx
0x18003a741  jz      short loc_18003A74C
0x18003a743  mov     rcx, rbx; this
0x18003a746  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18003a74b  nop
0x18003a74c  mov     rax, rdi
0x18003a74f  jmp     short loc_18003A6DF
0x18003a751  cmp     [rbp+1B0h+var_48], r14b
0x18003a758  jz      loc_18003AF13
0x18003a75e  mov     rbx, [rbp+1B0h+hKey]
0x18003a765  mov     rax, [rbp+1B0h+var_1A0]
0x18003a769  mov     rcx, [rbp+1B0h+var_1A8]
0x18003a76d  sub     rax, rcx
0x18003a770  sar     rax, 1
0x18003a773  add     eax, eax
0x18003a775  mov     [rsp+2B0h+cbData], eax
0x18003a779  mov     [rsp+2B0h+Type], r14d
0x18003a77e  mov     [rsp+2B0h+var_278], r14
0x18003a783  lea     rax, [rsp+2B0h+cbData]
0x18003a788  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18003a78d  mov     [rsp+2B0h+lpData], rcx; lpData
0x18003a792  lea     r9, [rsp+2B0h+Type]; lpType
0x18003a797  xor     r8d, r8d; lpReserved
0x18003a79a  lea     rdx, aEventmessagefi; "EventMessageFile"
0x18003a7a1  mov     rcx, rbx; hKey
0x18003a7a4  call    cs:__imp_RegQueryValueExW
0x18003a7aa  cmp     eax, 0EAh
0x18003a7af  jz      loc_18003AC5C
0x18003a7b5  test    eax, eax
0x18003a7b7  jnz     loc_18003AC70
0x18003a7bd  mov     eax, [rsp+2B0h+Type]
0x18003a7c1  dec     eax
0x18003a7c3  cmp     eax, 1
0x18003a7c6  ja      loc_18003AF04
0x18003a7cc  mov     edx, [rsp+2B0h+cbData]
0x18003a7d0  shr     rdx, 1; MaxCount
  ... truncated ...
```
