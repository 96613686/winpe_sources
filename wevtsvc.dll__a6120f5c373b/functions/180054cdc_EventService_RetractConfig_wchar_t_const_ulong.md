# EventService::RetractConfig(wchar_t const *,ulong)

- ea: `0x180054cdc`
- end: `0x180055725`
- name: `?RetractConfig@EventService@@QEAAXPEB_WK@Z`
- size: `2633`
- prototype: `void __fastcall(RTL_SRWLOCK *this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18007e550`

## callees

- `0x1800057f4`
- `0x180006770`
- `0x180014bd0`
- `0x180017128`
- `0x180017b60`
- `0x180017b98`
- `0x18001c320`
- `0x180020abc`
- `0x18002d6dc`
- `0x18003b0e8`
- `0x18003cb1c`
- `0x18003d170`
- `0x180054cdc`
- `0x18005572c`
- `0x180055b58`
- `0x1800583fc`
- `0x18005af7c`
- `0x18005c040`
- `0x18005c418`
- `0x180083b84`
- `0x1800885cc`
- `0x18008b038`
- `0x180092008`
- `0x18009aee0`
- `0x1800a1a10`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055151`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055151`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800550a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800554c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800550a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800554c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180055658`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180055665`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180055658`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180055665`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800556c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800556cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800556c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800556cf`
- `RPCRT4!RpcImpersonateClient` at `0x180054fe1`
- `RPCRT4!RpcImpersonateClient` at `0x1800553f3`
- `RPCRT4!RpcImpersonateClient` at `0x180054fe1`
- `RPCRT4!RpcImpersonateClient` at `0x1800553f3`
- `RPCRT4!RpcRevertToSelf` at `0x180055158`
- `RPCRT4!RpcRevertToSelf` at `0x18005560f`
- `RPCRT4!RpcRevertToSelf` at `0x180055158`
- `RPCRT4!RpcRevertToSelf` at `0x18005560f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall EventService::RetractConfig(RTL_SRWLOCK *this, const wchar_t *a2, int a3)
{
  RTL_SRWLOCK *v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  unsigned int v8; // r14d
  __int64 v9; // rcx
  unsigned int v10; // r14d
  unsigned int v11; // r14d
  unsigned int v12; // r14d
  __int64 v13; // rcx
  unsigned int WinevtRegPath; // ebx
  unsigned int v15; // ebx
  HKEY *v16; // rax
  unsigned int v17; // ebx
  unsigned int v18; // edx
  unsigned int v19; // r8d
  struct _SECURITY_ATTRIBUTES *v20; // r9
  PublisherConfigReader *v21; // rcx
  __int64 v22; // rdx
  __int64 i; // rbx
  PublisherMetadata *v24; // rcx
  __int64 v25; // rax
  void *v26; // [rsp+28h] [rbp-400h]
  HKEY phkResult; // [rsp+30h] [rbp-3F8h] BYREF
  char v28; // [rsp+39h] [rbp-3EFh]
  HKEY hKey[2]; // [rsp+40h] [rbp-3E8h] BYREF
  RTL_SRWLOCK *v30; // [rsp+50h] [rbp-3D8h]
  __int64 v31; // [rsp+58h] [rbp-3D0h] BYREF
  _QWORD v32[3]; // [rsp+60h] [rbp-3C8h] BYREF
  unsigned int v33; // [rsp+78h] [rbp-3B0h]
  int v34; // [rsp+7Ch] [rbp-3ACh]
  int v35; // [rsp+80h] [rbp-3A8h]
  char v36; // [rsp+84h] [rbp-3A4h]
  _QWORD v37[3]; // [rsp+88h] [rbp-3A0h] BYREF
  unsigned int v38; // [rsp+A0h] [rbp-388h]
  int v39; // [rsp+A4h] [rbp-384h]
  int v40; // [rsp+A8h] [rbp-380h]
  char v41; // [rsp+ACh] [rbp-37Ch]
  _QWORD v42[3]; // [rsp+B0h] [rbp-378h] BYREF
  unsigned int v43; // [rsp+C8h] [rbp-360h]
  int v44; // [rsp+CCh] [rbp-35Ch]
  int v45; // [rsp+D0h] [rbp-358h]
  char v46; // [rsp+D4h] [rbp-354h]
  _QWORD v47[3]; // [rsp+D8h] [rbp-350h] BYREF
  unsigned int v48; // [rsp+F0h] [rbp-338h]
  int v49; // [rsp+F4h] [rbp-334h]
  int v50; // [rsp+F8h] [rbp-330h]
  char v51; // [rsp+FCh] [rbp-32Ch]
  _QWORD v52[3]; // [rsp+100h] [rbp-328h] BYREF
  unsigned int v53; // [rsp+118h] [rbp-310h]
  int v54; // [rsp+11Ch] [rbp-30Ch]
  int v55; // [rsp+120h] [rbp-308h]
  char v56; // [rsp+124h] [rbp-304h]
  _QWORD v57[3]; // [rsp+128h] [rbp-300h] BYREF
  unsigned int v58; // [rsp+140h] [rbp-2E8h]
  int v59; // [rsp+144h] [rbp-2E4h]
  int v60; // [rsp+148h] [rbp-2E0h]
  char v61; // [rsp+14Ch] [rbp-2DCh]
  _QWORD v62[3]; // [rsp+150h] [rbp-2D8h] BYREF
  unsigned int v63; // [rsp+168h] [rbp-2C0h]
  int v64; // [rsp+16Ch] [rbp-2BCh]
  int v65; // [rsp+170h] [rbp-2B8h]
  char v66; // [rsp+174h] [rbp-2B4h]
  LPCWSTR lpSubKey[2]; // [rsp+178h] [rbp-2B0h] BYREF
  char v68; // [rsp+188h] [rbp-2A0h] BYREF
  __int128 pExceptionObject; // [rsp+198h] [rbp-290h] BYREF
  __int64 v70; // [rsp+1A8h] [rbp-280h]
  int v71; // [rsp+1B0h] [rbp-278h]
  int v72; // [rsp+1B4h] [rbp-274h]
  int v73; // [rsp+1B8h] [rbp-270h]
  __int128 v74; // [rsp+1C0h] [rbp-268h] BYREF
  __int64 v75; // [rsp+1D0h] [rbp-258h]
  int v76; // [rsp+1D8h] [rbp-250h]
  int v77; // [rsp+1DCh] [rbp-24Ch]
  int v78; // [rsp+1E0h] [rbp-248h]
  __int128 v79; // [rsp+1E8h] [rbp-240h] BYREF
  __int64 v80; // [rsp+1F8h] [rbp-230h]
  int v81; // [rsp+200h] [rbp-228h]
  int v82; // [rsp+204h] [rbp-224h]
  int v83; // [rsp+208h] [rbp-220h]
  __int128 v84; // [rsp+210h] [rbp-218h] BYREF
  __int64 v85; // [rsp+220h] [rbp-208h]
  int v86; // [rsp+228h] [rbp-200h]
  int v87; // [rsp+22Ch] [rbp-1FCh]
  int v88; // [rsp+230h] [rbp-1F8h]
  LPCWSTR v89[4]; // [rsp+238h] [rbp-1F0h] BYREF
  void *v90[2]; // [rsp+258h] [rbp-1D0h] BYREF
  char v91; // [rsp+268h] [rbp-1C0h] BYREF
  _BYTE v92[40]; // [rsp+278h] [rbp-1B0h] BYREF
  struct _GUID v93; // [rsp+2A0h] [rbp-188h] BYREF
  _BYTE v94[16]; // [rsp+2B0h] [rbp-178h] BYREF
  struct _GUID v95; // [rsp+2C0h] [rbp-168h] BYREF
  char v96; // [rsp+3F8h] [rbp-30h]
  char v97; // [rsp+3FFh] [rbp-29h]

  v5 = this;
  v30 = this;
  hKey[0] = (HKEY)a2;
  EventService::WaitForInit(this);
  if ( BYTE4(v5[60].Ptr) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 50);
    }
    pExceptionObject = 0;
    v70 = 0;
    v71 = 50;
    v72 = -1;
    v73 = 2012;
    throw (EvtException *)&pExceptionObject;
  }
  if ( a3 )
  {
    v93 = 0;
    v31 = 0;
    if ( !tlx::string_to_guid<wchar_t const *>(&v93, hKey) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 13);
      }
      v79 = 0;
      v80 = 0;
      v81 = 13;
      v82 = -1;
      v83 = 2065;
      throw (EvtException *)&v79;
    }
    phkResult = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v89);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v92);
    WinevtRegPath = RegistryPaths::GetWinevtRegPath(v13, &phkResult, v89, v92);
    if ( WinevtRegPath )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          99,
          &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids,
          WinevtRegPath);
      }
      v52[0] = &byte_1800EC961;
      v52[1] = 0;
      v52[2] = 0;
      v53 = WinevtRegPath;
      v54 = -1;
      v55 = -1;
      v56 = 0;
      throw (EvtException *)v52;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v89) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
      }
      v84 = 0;
      v85 = 0;
      v86 = 14;
      v87 = -1;
      v88 = 2074;
      throw (EvtException *)&v84;
    }
    v15 = RpcImpersonateClient(0);
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v15);
      }
      v57[0] = &byte_1800EC961;
      v57[1] = 0;
      v57[2] = 0;
      v58 = v15;
      v59 = -1;
      v60 = -1;
      v61 = 0;
      throw (EvtException *)v57;
    }
    v28 = 1;
    hKey[0] = 0;
    v16 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
    v17 = RegOpenKeyExW(phkResult, v89[0], 0, 0x10000u, v16);
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v17);
      }
      v62[0] = &byte_1800EC961;
      v62[1] = 0;
      v62[2] = 0;
      v63 = v17;
      v64 = -1;
      v65 = -1;
      v66 = 0;
      throw (EvtException *)v62;
    }
    phkResult = 0;
    if ( (unsigned int)PublisherConfigReader::TryGetPublisherConfigReader(&phkResult, &v93) )
    {
      RemoveRegCacheProviderNode(&v93);
    }
    else
    {
      v21 = (PublisherConfigReader *)phkResult;
      phkResult = 0;
      if ( v21 )
        PublisherConfigReader::`scalar deleting destructor'(v21, v18);
      PublisherConfigWriter::PublisherConfigWriter((PublisherConfigWriter *)v94, &v93, v19, v20, hKey[0], v26);
      v96 = 0;
      v97 = 1;
      PublisherConfigWriter::Save((PublisherConfigWriter *)v94);
      RemoveRegCacheProviderNode(&v95);
      PublisherConfigWriter::~PublisherConfigWriter((PublisherConfigWriter *)v94);
    }
    utl::unique_ptr<PublisherConfigReader,utl::default_delete<PublisherConfigReader>>::~unique_ptr<PublisherConfigReader,utl::default_delete<PublisherConfigReader>>(&phkResult);
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
    RpcRevertToSelf();
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      *(struct _GUID *)hKey = v93;
      ChannelManager::RetractPublisherFromChannels(v5 + 45, (struct _GUID *)hKey);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &EvtException `RTTI Type Descriptor', 0) )
      {
        v5 = v30;
        __eh34_try_continuation(0, &EvtException `RTTI Type Descriptor', &loc_180055638);
      }
    }
    PublisherManager::ReleasePublisher((PublisherManager *)&v5[29], &v93);
    AcquireSRWLockExclusive(v5 + 59);
    AcquireSRWLockExclusive(&ClientObjectWrapper<PublisherMetadata>::s_cs);
    for ( i = qword_180111A08;
          (void **)i != &ClientObjectWrapper<PublisherMetadata>::s_objects;
          i = utl::_TreeNodeHeader<Log *>::_Traverse(i, v22) )
    {
      v24 = *(PublisherMetadata **)(i + 24);
      v25 = *(_QWORD *)&v93.Data1 - *((_QWORD *)v24 + 43);
      if ( *(_QWORD *)&v93.Data1 == *((_QWORD *)v24 + 43) )
        v25 = *(_QWORD *)v93.Data4 - *((_QWORD *)v24 + 44);
      if ( !v25 )
        PublisherMetadata::Disconnect(v24);
      LOBYTE(v22) = 1;
    }
    ReleaseSRWLockExclusive(&ClientObjectWrapper<PublisherMetadata>::s_cs);
    ReleaseSRWLockExclusive(v5 + 59);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v92);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v89);
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v31);
  }
  else
  {
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    *(_QWORD *)&v93.Data1 = a2;
    *(_QWORD *)v93.Data4 = v7;
    v8 = ScanForInvalidChars(&v93, 15000);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v8);
      }
      v32[0] = &byte_1800EC961;
      v32[1] = 0;
      v32[2] = 0;
      v33 = v8;
      v34 = -1;
      v35 = -1;
      v36 = 0;
      throw (EvtException *)v32;
    }
    hKey[0] = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v90);
    v10 = RegistryPaths::GetWinevtRegPath(v9, hKey, lpSubKey, v90);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v10);
      }
      v37[0] = &byte_1800EC961;
      v37[1] = 0;
      v37[2] = 0;
      v38 = v10;
      v39 = -1;
      v40 = -1;
      v41 = 0;
      throw (EvtException *)v37;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(lpSubKey) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, 14);
      }
      v74 = 0;
      v75 = 0;
      v76 = 14;
      v77 = -1;
      v78 = 2027;
      throw (EvtException *)&v74;
    }
    v11 = RpcImpersonateClient(0);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v11);
      }
      v42[0] = &byte_1800EC961;
      v42[1] = 0;
      v42[2] = 0;
      v43 = v11;
      v44 = -1;
      v45 = -1;
      v46 = 0;
      throw (EvtException *)v42;
    }
    v28 = 1;
    phkResult = 0;
    v12 = RegOpenKeyExW(hKey[0], lpSubKey[0], 0, 0x10000u, &phkResult);
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids, v12);
      }
      v47[0] = &byte_1800EC961;
      v47[1] = 0;
      v47[2] = 0;
      v48 = v12;
      v49 = -1;
      v50 = -1;
      v51 = 0;
      throw (EvtException *)v47;
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    RpcRevertToSelf();
    do
      ++v6;
    while ( a2[v6] );
    *(_QWORD *)&v93.Data1 = a2;
    *(_QWORD *)v93.Data4 = v6;
    ChannelManager::RetractChannel(v5 + 45);
    if ( v90[0] != &v91 )
      operator delete(v90[0]);
    if ( (char *)lpSubKey[0] != &v68 )
      operator delete((void *)lpSubKey[0]);
  }
}

```

## disassembly

```asm
0x180054cdc  mov     [rsp+arg_10], rbx
0x180054ce1  mov     [rsp+arg_18], rsi
0x180054ce6  push    rdi
0x180054ce7  push    r14
0x180054ce9  push    r15
0x180054ceb  sub     rsp, 410h
0x180054cf2  mov     rax, cs:__security_cookie
0x180054cf9  xor     rax, rsp
0x180054cfc  mov     [rsp+428h+var_28], rax
0x180054d04  mov     ebx, r8d
0x180054d07  mov     r15, rdx
0x180054d0a  mov     rdi, rcx
0x180054d0d  mov     [rsp+428h+var_3D8], rcx
0x180054d12  mov     [rsp+428h+hKey], rdx
0x180054d17  call    ?WaitForInit@EventService@@AEAAXXZ; EventService::WaitForInit(void)
0x180054d1c  xor     esi, esi
0x180054d1e  cmp     [rdi+1E4h], sil
0x180054d25  jz      loc_180054DAB
0x180054d2b  lea     rax, WPP_GLOBAL_Control
0x180054d32  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d39  cmp     rcx, rax
0x180054d3c  jz      short loc_180054D61
0x180054d3e  test    byte ptr [rcx+1Ch], 8
0x180054d42  jz      short loc_180054D61
0x180054d44  cmp     byte ptr [rcx+19h], 2
0x180054d48  jb      short loc_180054D61
0x180054d4a  lea     edx, [rsi+5Ch]
0x180054d4d  lea     r9d, [rsi+32h]
0x180054d51  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180054d58  mov     rcx, [rcx+10h]
0x180054d5c  call    WPP_SF_d
0x180054d61  xorps   xmm0, xmm0
0x180054d64  movdqu  [rsp+428h+pExceptionObject], xmm0
0x180054d6d  mov     [rsp+428h+var_280], rsi
0x180054d75  mov     [rsp+428h+var_278], 32h ; '2'
0x180054d80  mov     [rsp+428h+var_274], 0FFFFFFFFh
0x180054d8b  mov     [rsp+428h+var_270], 7DCh
0x180054d96  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180054d9d  lea     rcx, [rsp+428h+pExceptionObject]; pExceptionObject
0x180054da5  call    _CxxThrowException_0
0x180054dab  test    ebx, ebx
0x180054dad  jnz     loc_1800551CB
0x180054db3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180054db7  mov     rax, rbx
0x180054dba  inc     rax
0x180054dbd  cmp     [r15+rax*2], si
0x180054dc2  jnz     short loc_180054DBA
0x180054dc4  mov     qword ptr [rsp+428h+var_188.Data1], r15
0x180054dcc  mov     qword ptr [rsp+428h+var_188.Data4], rax
0x180054dd4  mov     edx, 3A98h
0x180054dd9  lea     rcx, [rsp+428h+var_188]
0x180054de1  call    ScanForInvalidChars
0x180054de6  mov     r14d, eax
0x180054de9  test    eax, eax
0x180054deb  jz      short loc_180054E68
0x180054ded  lea     rax, WPP_GLOBAL_Control
0x180054df4  mov     rcx, cs:WPP_GLOBAL_Control
0x180054dfb  cmp     rcx, rax
0x180054dfe  jz      short loc_180054E24
0x180054e00  test    byte ptr [rcx+1Ch], 8
0x180054e04  jz      short loc_180054E24
0x180054e06  cmp     byte ptr [rcx+19h], 2
0x180054e0a  jb      short loc_180054E24
0x180054e0c  mov     edx, 5Dh ; ']'
0x180054e11  mov     r9d, r14d
0x180054e14  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180054e1b  mov     rcx, [rcx+10h]
0x180054e1f  call    WPP_SF_d
0x180054e24  lea     rax, byte_1800EC961
0x180054e2b  mov     [rsp+428h+var_3C8], rax
0x180054e30  mov     [rsp+428h+var_3C0], rsi
0x180054e35  mov     [rsp+428h+var_3B8], rsi
0x180054e3a  mov     [rsp+428h+var_3B0], r14d
0x180054e3f  mov     [rsp+428h+var_3AC], 0FFFFFFFFh
0x180054e47  mov     [rsp+428h+var_3A8], ebx
0x180054e4e  mov     [rsp+428h+var_3A4], sil
0x180054e56  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180054e5d  lea     rcx, [rsp+428h+var_3C8]; pExceptionObject
0x180054e62  call    _CxxThrowException_0
0x180054e68  mov     [rsp+428h+hKey], rsi
0x180054e6d  lea     rcx, [rsp+428h+lpSubKey]; void *
0x180054e75  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180054e7a  nop
0x180054e7b  lea     rcx, [rsp+428h+var_1D0]; void *
0x180054e83  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180054e88  nop
0x180054e89  lea     r9, [rsp+428h+var_1D0]
0x180054e91  lea     r8, [rsp+428h+lpSubKey]
0x180054e99  lea     rdx, [rsp+428h+hKey]
0x180054e9e  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180054ea3  mov     r14d, eax
0x180054ea6  test    eax, eax
0x180054ea8  jz      loc_180054F3B
0x180054eae  lea     rax, WPP_GLOBAL_Control
0x180054eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ebc  cmp     rcx, rax
0x180054ebf  jz      short loc_180054EE5
0x180054ec1  test    byte ptr [rcx+1Ch], 8
0x180054ec5  jz      short loc_180054EE5
0x180054ec7  cmp     byte ptr [rcx+19h], 2
0x180054ecb  jb      short loc_180054EE5
0x180054ecd  mov     edx, 5Eh ; '^'
0x180054ed2  mov     r9d, r14d
0x180054ed5  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180054edc  mov     rcx, [rcx+10h]
0x180054ee0  call    WPP_SF_d
0x180054ee5  lea     rax, byte_1800EC961
0x180054eec  mov     [rsp+428h+var_3A0], rax
0x180054ef4  mov     [rsp+428h+var_398], rsi
0x180054efc  mov     [rsp+428h+var_390], rsi
0x180054f04  mov     [rsp+428h+var_388], r14d
0x180054f0c  mov     [rsp+428h+var_384], 0FFFFFFFFh
0x180054f17  mov     [rsp+428h+var_380], ebx
0x180054f1e  mov     [rsp+428h+var_37C], sil
0x180054f26  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180054f2d  lea     rcx, [rsp+428h+var_3A0]; pExceptionObject
0x180054f35  call    _CxxThrowException_0
0x180054f3b  mov     r8d, 9
0x180054f41  lea     rdx, aChannels; "\\Channels"
0x180054f48  lea     rcx, [rsp+428h+lpSubKey]
0x180054f50  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180054f55  test    al, al
0x180054f57  jnz     loc_180054FDF
0x180054f5d  lea     rax, WPP_GLOBAL_Control
0x180054f64  mov     rcx, cs:WPP_GLOBAL_Control
0x180054f6b  cmp     rcx, rax
0x180054f6e  jz      short loc_180054F95
0x180054f70  test    byte ptr [rcx+1Ch], 8
0x180054f74  jz      short loc_180054F95
0x180054f76  cmp     byte ptr [rcx+19h], 2
0x180054f7a  jb      short loc_180054F95
0x180054f7c  mov     edx, 5Fh ; '_'
0x180054f81  lea     r9d, [rdx-51h]
0x180054f85  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180054f8c  mov     rcx, [rcx+10h]
0x180054f90  call    WPP_SF_d
0x180054f95  xorps   xmm0, xmm0
0x180054f98  movdqu  [rsp+428h+var_268], xmm0
0x180054fa1  mov     [rsp+428h+var_258], rsi
0x180054fa9  mov     [rsp+428h+var_250], 0Eh
0x180054fb4  mov     [rsp+428h+var_24C], 0FFFFFFFFh
0x180054fbf  mov     [rsp+428h+var_248], 7EBh
0x180054fca  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180054fd1  lea     rcx, [rsp+428h+var_268]; pExceptionObject
0x180054fd9  call    _CxxThrowException_0
0x180054fdf  xor     ecx, ecx; BindingHandle
0x180054fe1  call    cs:__imp_RpcImpersonateClient
0x180054fe7  mov     r14d, eax
0x180054fea  test    eax, eax
0x180054fec  jz      loc_18005507F
0x180054ff2  lea     rax, WPP_GLOBAL_Control
0x180054ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x180055000  cmp     rcx, rax
0x180055003  jz      short loc_180055029
0x180055005  test    byte ptr [rcx+1Ch], 8
0x180055009  jz      short loc_180055029
0x18005500b  cmp     byte ptr [rcx+19h], 2
0x18005500f  jb      short loc_180055029
0x180055011  mov     edx, 60h ; '`'
0x180055016  mov     r9d, r14d
0x180055019  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180055020  mov     rcx, [rcx+10h]
0x180055024  call    WPP_SF_d
0x180055029  lea     rax, byte_1800EC961
0x180055030  mov     [rsp+428h+var_378], rax
0x180055038  mov     [rsp+428h+var_370], rsi
0x180055040  mov     [rsp+428h+var_368], rsi
0x180055048  mov     [rsp+428h+var_360], r14d
0x180055050  mov     [rsp+428h+var_35C], 0FFFFFFFFh
0x18005505b  mov     [rsp+428h+var_358], ebx
0x180055062  mov     [rsp+428h+var_354], sil
0x18005506a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180055071  lea     rcx, [rsp+428h+var_378]; pExceptionObject
0x180055079  call    _CxxThrowException_0
0x18005507f  mov     [rsp+428h+var_3EF], 1
0x180055084  mov     [rsp+428h+var_3F8], rsi
0x180055089  lea     rax, [rsp+428h+var_3F8]
0x18005508e  mov     [rsp+428h+phkResult], rax; phkResult
0x180055093  mov     r9d, 10000h; samDesired
0x180055099  xor     r8d, r8d; ulOptions
0x18005509c  mov     rdx, [rsp+428h+lpSubKey]; lpSubKey
0x1800550a4  mov     rcx, [rsp+428h+hKey]; hKey
0x1800550a9  call    cs:__imp_RegOpenKeyExW
0x1800550af  mov     r14d, eax
0x1800550b2  test    eax, eax
0x1800550b4  jz      loc_180055147
0x1800550ba  lea     rax, WPP_GLOBAL_Control
0x1800550c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800550c8  cmp     rcx, rax
0x1800550cb  jz      short loc_1800550F1
0x1800550cd  test    byte ptr [rcx+1Ch], 8
0x1800550d1  jz      short loc_1800550F1
0x1800550d3  cmp     byte ptr [rcx+19h], 2
0x1800550d7  jb      short loc_1800550F1
0x1800550d9  mov     edx, 61h ; 'a'
0x1800550de  mov     r9d, r14d
0x1800550e1  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800550e8  mov     rcx, [rcx+10h]
0x1800550ec  call    WPP_SF_d
0x1800550f1  lea     rax, byte_1800EC961
0x1800550f8  mov     [rsp+428h+var_350], rax
0x180055100  mov     [rsp+428h+var_348], rsi
0x180055108  mov     [rsp+428h+var_340], rsi
0x180055110  mov     [rsp+428h+var_338], r14d
0x180055118  mov     [rsp+428h+var_334], 0FFFFFFFFh
0x180055123  mov     [rsp+428h+var_330], ebx
0x18005512a  mov     [rsp+428h+var_32C], sil
0x180055132  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180055139  lea     rcx, [rsp+428h+var_350]; pExceptionObject
0x180055141  call    _CxxThrowException_0
0x180055147  mov     rcx, [rsp+428h+var_3F8]; hKey
0x18005514c  test    rcx, rcx
0x18005514f  jz      short loc_180055158
0x180055151  call    cs:__imp_RegCloseKey
0x180055157  nop
0x180055158  call    cs:__imp_RpcRevertToSelf
0x18005515e  inc     rbx
0x180055161  cmp     [r15+rbx*2], si
0x180055166  jnz     short loc_18005515E
0x180055168  mov     qword ptr [rsp+428h+var_188.Data1], r15
0x180055170  mov     qword ptr [rsp+428h+var_188.Data4], rbx
0x180055178  lea     rcx, [rdi+168h]; SRWLock
0x18005517f  lea     rdx, [rsp+428h+var_188]
0x180055187  call    ?RetractChannel@ChannelManager@@QEAAXV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; ChannelManager::RetractChannel(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x18005518c  nop
0x18005518d  lea     rax, [rsp+428h+var_1C0]
0x180055195  mov     rcx, [rsp+428h+var_1D0]; void *
0x18005519d  cmp     rcx, rax
0x1800551a0  jz      short loc_1800551A8
0x1800551a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800551a7  nop
0x1800551a8  lea     rax, [rsp+428h+var_2A0]
0x1800551b0  mov     rcx, [rsp+428h+lpSubKey]; void *
0x1800551b8  cmp     rcx, rax
0x1800551bb  jz      loc_1800556FC
0x1800551c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800551c6  jmp     loc_1800556FC
0x1800551cb  xorps   xmm0, xmm0
0x1800551ce  movups  xmmword ptr [rsp+428h+var_188.Data1], xmm0
0x1800551d6  mov     [rsp+428h+var_3D0], rsi
0x1800551db  lea     rdx, [rsp+428h+hKey]
0x1800551e0  lea     rcx, [rsp+428h+var_188]
0x1800551e8  call    ??$string_to_guid@PEB_W@tlx@@YAPEB_WPEAU_GUID@@AEBQEB_W@Z; tlx::string_to_guid<wchar_t const *>(_GUID *,wchar_t const * const &)
0x1800551ed  test    rax, rax
0x1800551f0  jnz     loc_180055278
0x1800551f6  lea     rax, WPP_GLOBAL_Control
0x1800551fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180055204  cmp     rcx, rax
0x180055207  jz      short loc_18005522E
0x180055209  test    byte ptr [rcx+1Ch], 8
0x18005520d  jz      short loc_18005522E
0x18005520f  cmp     byte ptr [rcx+19h], 2
0x180055213  jb      short loc_18005522E
0x180055215  mov     edx, 62h ; 'b'
0x18005521a  lea     r9d, [rdx-55h]
0x18005521e  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x180055225  mov     rcx, [rcx+10h]
0x180055229  call    WPP_SF_d
0x18005522e  xorps   xmm0, xmm0
0x180055231  movdqu  [rsp+428h+var_240], xmm0
0x18005523a  mov     [rsp+428h+var_230], rsi
0x180055242  mov     [rsp+428h+var_228], 0Dh
0x18005524d  mov     [rsp+428h+var_224], 0FFFFFFFFh
0x180055258  mov     [rsp+428h+var_220], 811h
0x180055263  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18005526a  lea     rcx, [rsp+428h+var_240]; pExceptionObject
0x180055272  call    _CxxThrowException_0
0x180055278  mov     [rsp+428h+var_3F8], rsi
0x18005527d  lea     rcx, [rsp+428h+var_1F0]; void *
0x180055285  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18005528a  nop
0x18005528b  lea     rcx, [rsp+428h+var_1B0]; void *
0x180055293  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180055298  nop
0x180055299  lea     r9, [rsp+428h+var_1B0]
0x1800552a1  lea     r8, [rsp+428h+var_1F0]
0x1800552a9  lea     rdx, [rsp+428h+var_3F8]
0x1800552ae  call    ?GetWinevtRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; RegistryPaths::GetWinevtRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800552b3  mov     ebx, eax
0x1800552b5  test    eax, eax
0x1800552b7  jz      loc_18005534D
0x1800552bd  lea     rax, WPP_GLOBAL_Control
0x1800552c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800552cb  cmp     rcx, rax
0x1800552ce  jz      short loc_1800552F4
0x1800552d0  test    byte ptr [rcx+1Ch], 8
0x1800552d4  jz      short loc_1800552F4
0x1800552d6  cmp     byte ptr [rcx+19h], 2
0x1800552da  jb      short loc_1800552F4
0x1800552dc  mov     edx, 63h ; 'c'
0x1800552e1  mov     r9d, ebx
0x1800552e4  lea     r8, WPP_4ca14dff85cd3471ba70228bb878e517_Traceguids
0x1800552eb  mov     rcx, [rcx+10h]
0x1800552ef  call    WPP_SF_d
0x1800552f4  lea     rax, byte_1800EC961
0x1800552fb  mov     [rsp+428h+var_328], rax
0x180055303  mov     [rsp+428h+var_320], rsi
0x18005530b  mov     [rsp+428h+var_318], rsi
0x180055313  mov     [rsp+428h+var_310], ebx
0x18005531a  mov     [rsp+428h+var_30C], 0FFFFFFFFh
  ... truncated ...
```
