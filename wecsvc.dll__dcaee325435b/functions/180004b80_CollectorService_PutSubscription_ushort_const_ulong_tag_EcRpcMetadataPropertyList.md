# CollectorService::PutSubscription(ushort const *,ulong,tag_EcRpcMetadataPropertyList &)

- ea: `0x180004b80`
- end: `0x180005264`
- name: `?PutSubscription@CollectorService@@QEAAXPEBGKAEAUtag_EcRpcMetadataPropertyList@@@Z`
- size: `1764`
- prototype: `void __fastcall(CollectorService *this, const unsigned __int16 *, __int64, struct tag_EcRpcMetadataPropertyList *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800036b0`

## callees

- `0x18000195c`
- `0x1800024f0`
- `0x1800032dc`
- `0x180003430`
- `0x180003810`
- `0x180003be8`
- `0x180003d10`
- `0x180003e6c`
- `0x180004b80`
- `0x18000526c`
- `0x180005d7c`
- `0x1800062d4`
- `0x180006370`
- `0x1800064e0`
- `0x18000a938`
- `0x1800145cc`
- `0x18001483c`
- `0x180015134`
- `0x1800165c0`
- `0x18001fe50`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800050b6`
- `RPCRT4!RpcRevertToSelf` at `0x180004c75`
- `RPCRT4!RpcRevertToSelf` at `0x1800050b6`
- `RPCRT4!RpcImpersonateClient` at `0x180004bc2`
- `RPCRT4!RpcImpersonateClient` at `0x180004bc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004da9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004da9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005031`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005151`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005031`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005151`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004e60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004e60`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004f3e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004f3e`

## string_xrefs

- `0x180004c15`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x180004d16`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x180004eb1`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x180004f8f`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x180004f32`: `SubscriptionWasCreated`

## pseudocode

```c
void __fastcall CollectorService::PutSubscription(
        CollectorService *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct tag_EcRpcMetadataPropertyList *a4)
{
  unsigned int v7; // eax
  unsigned int v8; // ebx
  _DWORD *v9; // rax
  int v10; // ecx
  SubscriptionConfigWriter *v11; // rax
  struct _SECURITY_ATTRIBUTES *v12; // r8
  HKEY v13; // r9
  volatile signed __int32 *v14; // rbx
  const WCHAR *v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // edi
  unsigned int v18; // eax
  unsigned int v19; // edi
  __int64 v20; // rdx
  const unsigned __int16 *v21; // rbx
  unsigned int i; // edx
  char v23; // di
  __int64 v24; // rcx
  HKEY v25; // r8
  const unsigned __int16 *v26; // r9
  SubscriptionConfigSnapshot *v27; // rax
  SubscriptionConfigSnapshot *v28; // rax
  unsigned int v29; // edi
  __int64 v30; // rbx
  const unsigned __int16 *v31; // r8
  unsigned int j; // edi
  const unsigned __int16 *v33; // r8
  const unsigned __int16 *phkResult; // [rsp+20h] [rbp-268h]
  BYTE Data[8]; // [rsp+40h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-240h] BYREF
  _BYTE *v37; // [rsp+50h] [rbp-238h]
  volatile signed __int32 *v38; // [rsp+58h] [rbp-230h] BYREF
  const unsigned __int16 *v39; // [rsp+60h] [rbp-228h]
  __int128 v40; // [rsp+68h] [rbp-220h] BYREF
  __int64 v41; // [rsp+78h] [rbp-210h]
  __int128 v42; // [rsp+80h] [rbp-208h] BYREF
  __int64 v43; // [rsp+90h] [rbp-1F8h]
  SubscriptionManager **v44; // [rsp+98h] [rbp-1F0h]
  char *v45; // [rsp+A0h] [rbp-1E8h]
  char v46[8]; // [rsp+A8h] [rbp-1E0h] BYREF
  RPC_STATUS (__stdcall *v47)(); // [rsp+B0h] [rbp-1D8h]
  void **pExceptionObject; // [rsp+B8h] [rbp-1D0h] BYREF
  char v49; // [rsp+C0h] [rbp-1C8h]
  const char *v50; // [rsp+C8h] [rbp-1C0h]
  __int64 v51; // [rsp+D0h] [rbp-1B8h]
  __int64 v52; // [rsp+D8h] [rbp-1B0h]
  unsigned int v53; // [rsp+E0h] [rbp-1A8h]
  int v54; // [rsp+E4h] [rbp-1A4h]
  int v55; // [rsp+E8h] [rbp-1A0h]
  void **v56; // [rsp+F0h] [rbp-198h] BYREF
  char v57; // [rsp+F8h] [rbp-190h]
  const char *v58; // [rsp+100h] [rbp-188h]
  __int64 v59; // [rsp+108h] [rbp-180h]
  __int64 v60; // [rsp+110h] [rbp-178h]
  int v61; // [rsp+118h] [rbp-170h]
  int v62; // [rsp+11Ch] [rbp-16Ch]
  int v63; // [rsp+120h] [rbp-168h]
  void **v64; // [rsp+128h] [rbp-160h] BYREF
  char v65; // [rsp+130h] [rbp-158h]
  const char *v66; // [rsp+138h] [rbp-150h]
  __int64 v67; // [rsp+140h] [rbp-148h]
  __int64 v68; // [rsp+148h] [rbp-140h]
  unsigned int v69; // [rsp+150h] [rbp-138h]
  int v70; // [rsp+154h] [rbp-134h]
  int v71; // [rsp+158h] [rbp-130h]
  void **v72; // [rsp+160h] [rbp-128h] BYREF
  char v73; // [rsp+168h] [rbp-120h]
  const char *v74; // [rsp+170h] [rbp-118h]
  __int64 v75; // [rsp+178h] [rbp-110h]
  __int64 v76; // [rsp+180h] [rbp-108h]
  unsigned int v77; // [rsp+188h] [rbp-100h]
  int v78; // [rsp+18Ch] [rbp-FCh]
  int v79; // [rsp+190h] [rbp-F8h]
  void **v80; // [rsp+198h] [rbp-F0h] BYREF
  char v81; // [rsp+1A0h] [rbp-E8h]
  const char *v82; // [rsp+1A8h] [rbp-E0h]
  __int64 v83; // [rsp+1B0h] [rbp-D8h]
  __int64 v84; // [rsp+1B8h] [rbp-D0h]
  int v85; // [rsp+1C0h] [rbp-C8h]
  int v86; // [rsp+1C4h] [rbp-C4h]
  int v87; // [rsp+1C8h] [rbp-C0h]
  void **v88; // [rsp+1D0h] [rbp-B8h] BYREF
  char v89; // [rsp+1D8h] [rbp-B0h]
  const char *v90; // [rsp+1E0h] [rbp-A8h]
  __int64 v91; // [rsp+1E8h] [rbp-A0h]
  __int64 v92; // [rsp+1F0h] [rbp-98h]
  int v93; // [rsp+1F8h] [rbp-90h]
  int v94; // [rsp+1FCh] [rbp-8Ch]
  int v95; // [rsp+200h] [rbp-88h]
  __int128 v96; // [rsp+208h] [rbp-80h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+218h] [rbp-70h] BYREF
  wmi::Exception *v98; // [rsp+238h] [rbp-50h] BYREF
  wmi::Exception *v99; // [rsp+240h] [rbp-48h] BYREF

  v44 = (SubscriptionManager **)this;
  v39 = a2;
  CollectorService::WaitForInit(this);
  v7 = RpcImpersonateClient(0);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, v7);
    }
    v49 = 0;
    v50 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v51 = 0;
    v52 = 0;
    v53 = v8;
    v54 = -1;
    v55 = 445;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v46[0] = 0;
  v47 = RpcRevertToSelf;
  v9 = (_DWORD *)*((_QWORD *)a4 + 1);
  if ( v9[6] )
  {
    if ( v9[6] != 7
      || v9[12] != 6
      || v9[18] != 5
      || v9[24] != 6
      || v9[30] != 6
      || (v10 = v9[14], v10 != v9[8])
      || v10 != v9[20]
      || v10 != v9[26]
      || v10 != v9[32] )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 87);
      }
      v57 = 0;
      v58 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
      v59 = 0;
      v60 = 0;
      v61 = 87;
      v62 = -1;
      v63 = 466;
      v56 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v56;
    }
  }
  v42 = 0;
  v43 = 0;
  v40 = 0;
  v41 = 0;
  v45 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v38 = 0;
  v11 = (SubscriptionConfigWriter *)operator new(0x30u);
  v37 = v11;
  if ( v11 )
    v14 = (volatile signed __int32 *)((SubscriptionConfigWriter *(__stdcall *)(SubscriptionConfigWriter *, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *, HKEY, const unsigned __int16 *, struct tag_EcRpcMetadataPropertyList *))SubscriptionConfigWriter::SubscriptionConfigWriter)(
                                       v11,
                                       a2,
                                       v12,
                                       v13,
                                       phkResult,
                                       a4);
  else
    v14 = 0;
  v37 = v14;
  if ( v14 )
    _InterlockedIncrement(v14 + 2);
  wmi::AutoRef<AbstractEventProcessor>::Release(&v38);
  v38 = v14;
  std::wstring::wstring(lpSubKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector");
  std::wstring::append(lpSubKey, L"\\Subscriptions");
  hKey = 0;
  v15 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] >= (LPCWSTR)8 )
    v15 = lpSubKey[0];
  v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0x2001Fu, &hKey);
  v17 = v16;
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, v16);
    }
    v65 = 0;
    v66 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v67 = 0;
    v68 = 0;
    v69 = v17;
    v70 = -1;
    v71 = 499;
    v64 = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&v64;
  }
  *(_DWORD *)Data = 1;
  v18 = RegSetValueExW(hKey, L"SubscriptionWasCreated", 0, 4u, Data, 4u);
  v19 = v18;
  if ( v18 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, v18);
    }
    v73 = 0;
    v74 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v75 = 0;
    v76 = 0;
    v77 = v19;
    v78 = -1;
    v79 = 517;
    v72 = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&v72;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    SubscriptionConfigWriter::Save((HKEY *)v14);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &wmi::Exception `RTTI Type Descriptor', &v98) )
    {
      if ( v37[40] )
        RegDeleteKeyRecursive(hKey, v39);
      throw;
    }
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  LOBYTE(v20) = 1;
  std::wstring::_Tidy(lpSubKey, v20, 0);
  wmi::AutoRef<AbstractEventProcessor>::Release(&v38);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v21 = 0;
  for ( i = 0; i < *(_DWORD *)a4; ++i )
  {
    if ( i - 1 > 4 && (*(_BYTE *)(*((_QWORD *)a4 + 1) + 24LL * i + 4) & 1) != 0 )
    {
      v23 = 1;
      goto LABEL_52;
    }
  }
  v23 = 0;
  v24 = (__int64)(*((_QWORD *)&v42 + 1) - v42) >> 5;
  if ( v24 + ((__int64)(*((_QWORD *)&v40 + 1) - v40) >> 5) == 1 )
  {
    v21 = (const unsigned __int16 *)v42;
    if ( !v24 )
      v21 = (const unsigned __int16 *)v40;
    if ( *((_QWORD *)v21 + 3) >= 8u )
      v21 = *(const unsigned __int16 **)v21;
  }
LABEL_52:
  v46[0] = 1;
  RpcRevertToSelf();
  *(_QWORD *)Data = 0;
  v96 = 0;
  v45 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    ((void (__stdcall *)(SubscriptionConfigReader *, const unsigned __int16 *, HKEY, const unsigned __int16 *))SubscriptionConfigReader::SubscriptionConfigReader)(
      (SubscriptionConfigReader *)lpSubKey,
      a2,
      v25,
      v26);
    v27 = (SubscriptionConfigSnapshot *)operator new(0x20u);
    v37 = v27;
    if ( v27 )
      v28 = ((SubscriptionConfigSnapshot *(__stdcall *)(SubscriptionConfigSnapshot *, const struct SubscriptionConfigReader *, const unsigned __int16 *, struct tag_EcRpcMetadataPropertyList *, bool, bool, bool))SubscriptionConfigSnapshot::SubscriptionConfigSnapshot)(
              v27,
              (const struct SubscriptionConfigReader *)lpSubKey,
              v21,
              (struct tag_EcRpcMetadataPropertyList *)&v96,
              1,
              1,
              1);
    else
      v28 = 0;
    wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(Data, v28);
    ConfigBase::~ConfigBase((ConfigBase *)lpSubKey);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &wmi::Exception `RTTI Type Descriptor', &v99) )
    {
      SubscriptionManager::RetractSubscription(*v44, v39);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 15080);
      }
      v89 = 0;
      v90 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
      v91 = 0;
      v92 = 0;
      v93 = 15080;
      v94 = -1;
      v95 = 588;
      v88 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v88;
    }
  }
  if ( __eh34_try(-1, 4) )
  {
    __eh34_scope_strut(4);
    if ( v23 || v21 )
    {
      SubscriptionManager::AssertSubscription(
        *(SubscriptionManager **)this,
        a2,
        v21,
        (const struct SubscriptionReadData *)(*(_QWORD *)Data + 16LL));
    }
    else
    {
      v29 = 0;
      v30 = *(_QWORD *)Data;
      while ( v29 < (unsigned __int64)((__int64)(*((_QWORD *)&v42 + 1) - v42) >> 5) )
      {
        v31 = (const unsigned __int16 *)(32LL * v29 + v42);
        if ( *((_QWORD *)v31 + 3) >= 8u )
          v31 = *(const unsigned __int16 **)v31;
        SubscriptionManager::AssertSubscription(
          *(SubscriptionManager **)this,
          a2,
          v31,
          (const struct SubscriptionReadData *)(v30 + 16));
        ++v29;
      }
      for ( j = 0; j < (unsigned __int64)((__int64)(*((_QWORD *)&v40 + 1) - v40) >> 5); ++j )
      {
        v33 = (const unsigned __int16 *)(32LL * j + v40);
        if ( *((_QWORD *)v33 + 3) >= 8u )
          v33 = *(const unsigned __int16 **)v33;
        SubscriptionManager::AssertSubscription(
          *(SubscriptionManager **)this,
          a2,
          v33,
          (const struct SubscriptionReadData *)(v30 + 16));
      }
    }
  }
  if ( __eh34_catch(4) )
  {
    if ( __eh34_catch_type(4, &wmi::Exception `RTTI Type Descriptor', 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 15080);
      }
      v81 = 0;
      v82 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
      v83 = 0;
      v84 = 0;
      v85 = 15080;
      v86 = -1;
      v87 = 618;
      v80 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v80;
    }
  }
  wmi::AutoRef<AbstractEventProcessor>::Release(Data);
  std::vector<std::wstring>::_Tidy(&v40);
  std::vector<std::wstring>::_Tidy(&v42);
  wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v46);
}

```

## disassembly

```asm
0x180004b80  push    rbx
0x180004b82  push    rsi
0x180004b83  push    rdi
0x180004b84  push    r12
0x180004b86  push    r13
0x180004b88  push    r14
0x180004b8a  push    r15
0x180004b8c  sub     rsp, 250h
0x180004b93  mov     rax, cs:__security_cookie
0x180004b9a  xor     rax, rsp
0x180004b9d  mov     [rsp+288h+var_40], rax
0x180004ba5  mov     r14, r9
0x180004ba8  mov     r15, rdx
0x180004bab  mov     r12, rcx
0x180004bae  mov     [rsp+288h+var_1F0], rcx
0x180004bb6  mov     [rsp+288h+var_228], rdx
0x180004bbb  call    ?WaitForInit@CollectorService@@AEAAXXZ; CollectorService::WaitForInit(void)
0x180004bc0  xor     ecx, ecx; BindingHandle
0x180004bc2  call    cs:__imp_RpcImpersonateClient
0x180004bc8  mov     ebx, eax
0x180004bca  xor     r13d, r13d
0x180004bcd  test    eax, eax
0x180004bcf  jz      loc_180004C75
0x180004bd5  lea     rcx, WPP_GLOBAL_Control
0x180004bdc  mov     r10, cs:WPP_GLOBAL_Control
0x180004be3  cmp     r10, rcx
0x180004be6  jz      short loc_180004C0D
0x180004be8  test    byte ptr [r10+1Ch], 10h
0x180004bed  jz      short loc_180004C0D
0x180004bef  cmp     byte ptr [r10+19h], 2
0x180004bf4  jb      short loc_180004C0D
0x180004bf6  lea     edx, [r13+0Eh]
0x180004bfa  mov     r9d, eax
0x180004bfd  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180004c04  mov     rcx, [r10+10h]
0x180004c08  call    WPP_SF_D
0x180004c0d  mov     [rsp+288h+var_1C8], r13b
0x180004c15  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180004c1c  mov     [rsp+288h+var_1C0], rax
0x180004c24  mov     [rsp+288h+var_1B8], r13
0x180004c2c  mov     [rsp+288h+var_1B0], r13
0x180004c34  mov     [rsp+288h+var_1A8], ebx
0x180004c3b  mov     [rsp+288h+var_1A4], 0FFFFFFFFh
0x180004c46  mov     [rsp+288h+var_1A0], 1BDh
0x180004c51  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180004c58  mov     [rsp+288h+pExceptionObject], rax
0x180004c60  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180004c67  lea     rcx, [rsp+288h+pExceptionObject]; pExceptionObject
0x180004c6f  call    _CxxThrowException_0
0x180004c75  mov     rax, cs:__imp_RpcRevertToSelf
0x180004c7c  mov     [rsp+288h+var_1E0], r13b
0x180004c84  mov     [rsp+288h+var_1D8], rax
0x180004c8c  mov     rax, [r14+8]
0x180004c90  cmp     [rax+18h], r13d
0x180004c94  jz      loc_180004D7A
0x180004c9a  cmp     dword ptr [rax+18h], 7
0x180004c9e  jnz     short loc_180004CD6
0x180004ca0  cmp     dword ptr [rax+30h], 6
0x180004ca4  jnz     short loc_180004CD6
0x180004ca6  cmp     dword ptr [rax+48h], 5
0x180004caa  jnz     short loc_180004CD6
0x180004cac  cmp     dword ptr [rax+60h], 6
0x180004cb0  jnz     short loc_180004CD6
0x180004cb2  cmp     dword ptr [rax+78h], 6
0x180004cb6  jnz     short loc_180004CD6
0x180004cb8  mov     ecx, [rax+38h]
0x180004cbb  cmp     ecx, [rax+20h]
0x180004cbe  jnz     short loc_180004CD6
0x180004cc0  cmp     ecx, [rax+50h]
0x180004cc3  jnz     short loc_180004CD6
0x180004cc5  cmp     ecx, [rax+68h]
0x180004cc8  jnz     short loc_180004CD6
0x180004cca  cmp     ecx, [rax+80h]
0x180004cd0  jz      loc_180004D7A
0x180004cd6  lea     rcx, WPP_GLOBAL_Control
0x180004cdd  mov     rax, cs:WPP_GLOBAL_Control
0x180004ce4  cmp     rax, rcx
0x180004ce7  jz      short loc_180004D0E
0x180004ce9  test    byte ptr [rax+1Ch], 10h
0x180004ced  jz      short loc_180004D0E
0x180004cef  cmp     byte ptr [rax+19h], 2
0x180004cf3  jb      short loc_180004D0E
0x180004cf5  mov     edx, 0Fh
0x180004cfa  lea     r9d, [rdx+48h]
0x180004cfe  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180004d05  mov     rcx, [rax+10h]
0x180004d09  call    WPP_SF_D
0x180004d0e  mov     [rsp+288h+var_190], r13b
0x180004d16  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180004d1d  mov     [rsp+288h+var_188], rax
0x180004d25  mov     [rsp+288h+var_180], r13
0x180004d2d  mov     [rsp+288h+var_178], r13
0x180004d35  mov     [rsp+288h+var_170], 57h ; 'W'
0x180004d40  mov     [rsp+288h+var_16C], 0FFFFFFFFh
0x180004d4b  mov     [rsp+288h+var_168], 1D2h
0x180004d56  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180004d5d  mov     [rsp+288h+var_198], rax
0x180004d65  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180004d6c  lea     rcx, [rsp+288h+var_198]; pExceptionObject
0x180004d74  call    _CxxThrowException_0
0x180004d7a  xorps   xmm0, xmm0
0x180004d7d  movdqu  [rsp+288h+var_208], xmm0
0x180004d86  mov     [rsp+288h+var_1F8], r13
0x180004d8e  movdqu  [rsp+288h+var_220], xmm0
0x180004d94  mov     [rsp+288h+var_210], r13
0x180004d99  lea     rsi, [r12+18h]
0x180004d9e  mov     [rsp+288h+var_1E8], rsi
0x180004da6  mov     rcx, rsi; lpCriticalSection
0x180004da9  call    cs:__imp_EnterCriticalSection
0x180004daf  nop
0x180004db0  mov     [rsp+288h+var_230], r13
0x180004db5  mov     ecx, 30h ; '0'; dwBytes
0x180004dba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004dbf  mov     [rsp+288h+var_238], rax
0x180004dc4  test    rax, rax
0x180004dc7  jz      short loc_180004DDE
0x180004dc9  mov     qword ptr [rsp+288h+cbData], r14; struct tag_EcRpcMetadataPropertyList *
0x180004dce  mov     rdx, r15; unsigned __int16 *
0x180004dd1  mov     rcx, rax; this
0x180004dd4  call    ??0SubscriptionConfigWriter@@QEAA@PEBGPEAU_SECURITY_ATTRIBUTES@@PEAUHKEY__@@0AEAUtag_EcRpcMetadataPropertyList@@@Z; SubscriptionConfigWriter::SubscriptionConfigWriter(ushort const *,_SECURITY_ATTRIBUTES *,HKEY__ *,ushort const *,tag_EcRpcMetadataPropertyList &)
0x180004dd9  mov     rbx, rax
0x180004ddc  jmp     short loc_180004DE1
0x180004dde  mov     rbx, r13
0x180004de1  mov     [rsp+288h+var_238], rbx
0x180004de6  test    rbx, rbx
0x180004de9  jz      short loc_180004DEF
0x180004deb  lock inc dword ptr [rbx+8]
0x180004def  lea     rcx, [rsp+288h+var_230]
0x180004df4  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180004df9  mov     [rsp+288h+var_230], rbx
0x180004dfe  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180004e05  lea     rcx, [rsp+288h+lpSubKey]
0x180004e0d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180004e12  nop
0x180004e13  lea     rdx, aSubscriptions; "\\Subscriptions"
0x180004e1a  lea     rcx, [rsp+288h+lpSubKey]
0x180004e22  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180004e27  mov     [rsp+288h+hKey], r13
0x180004e2c  lea     rdx, [rsp+288h+lpSubKey]
0x180004e34  cmp     [rsp+288h+var_58], 8
0x180004e3d  cmovnb  rdx, [rsp+288h+lpSubKey]; lpSubKey
0x180004e46  lea     rax, [rsp+288h+hKey]
0x180004e4b  mov     [rsp+288h+phkResult], rax; phkResult
0x180004e50  mov     r9d, 2001Fh; samDesired
0x180004e56  xor     r8d, r8d; ulOptions
0x180004e59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004e60  call    cs:__imp_RegOpenKeyExW
0x180004e66  mov     edi, eax
0x180004e68  test    eax, eax
0x180004e6a  jz      loc_180004F11
0x180004e70  lea     rcx, WPP_GLOBAL_Control
0x180004e77  mov     r10, cs:WPP_GLOBAL_Control
0x180004e7e  cmp     r10, rcx
0x180004e81  jz      short loc_180004EA9
0x180004e83  test    byte ptr [r10+1Ch], 10h
0x180004e88  jz      short loc_180004EA9
0x180004e8a  cmp     byte ptr [r10+19h], 2
0x180004e8f  jb      short loc_180004EA9
0x180004e91  mov     edx, 10h
0x180004e96  mov     r9d, eax
0x180004e99  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180004ea0  mov     rcx, [r10+10h]
0x180004ea4  call    WPP_SF_D
0x180004ea9  mov     [rsp+288h+var_158], r13b
0x180004eb1  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180004eb8  mov     [rsp+288h+var_150], rax
0x180004ec0  mov     [rsp+288h+var_148], r13
0x180004ec8  mov     [rsp+288h+var_140], r13
0x180004ed0  mov     [rsp+288h+var_138], edi
0x180004ed7  mov     [rsp+288h+var_134], 0FFFFFFFFh
0x180004ee2  mov     [rsp+288h+var_130], 1F3h
0x180004eed  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180004ef4  mov     [rsp+288h+var_160], rax
0x180004efc  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180004f03  lea     rcx, [rsp+288h+var_160]; pExceptionObject
0x180004f0b  call    _CxxThrowException_0
0x180004f11  mov     dword ptr [rsp+288h+Data], 1
0x180004f19  mov     ecx, 4
0x180004f1e  mov     [rsp+288h+cbData], ecx; cbData
0x180004f22  lea     rax, [rsp+288h+Data]
0x180004f27  mov     [rsp+288h+phkResult], rax; lpData
0x180004f2c  mov     r9d, ecx; dwType
0x180004f2f  xor     r8d, r8d; Reserved
0x180004f32  lea     rdx, ValueName; "SubscriptionWasCreated"
0x180004f39  mov     rcx, [rsp+288h+hKey]; hKey
0x180004f3e  call    cs:__imp_RegSetValueExW
0x180004f44  mov     edi, eax
0x180004f46  test    eax, eax
0x180004f48  jz      loc_180004FEF
0x180004f4e  lea     rcx, WPP_GLOBAL_Control
0x180004f55  mov     r10, cs:WPP_GLOBAL_Control
0x180004f5c  cmp     r10, rcx
0x180004f5f  jz      short loc_180004F87
0x180004f61  test    byte ptr [r10+1Ch], 10h
0x180004f66  jz      short loc_180004F87
0x180004f68  cmp     byte ptr [r10+19h], 2
0x180004f6d  jb      short loc_180004F87
0x180004f6f  mov     edx, 11h
0x180004f74  mov     r9d, eax
0x180004f77  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180004f7e  mov     rcx, [r10+10h]
0x180004f82  call    WPP_SF_D
0x180004f87  mov     [rsp+288h+var_120], r13b
0x180004f8f  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180004f96  mov     [rsp+288h+var_118], rax
0x180004f9e  mov     [rsp+288h+var_110], r13
0x180004fa6  mov     [rsp+288h+var_108], r13
0x180004fae  mov     [rsp+288h+var_100], edi
0x180004fb5  mov     [rsp+288h+var_FC], 0FFFFFFFFh
0x180004fc0  mov     [rsp+288h+var_F8], 205h
0x180004fcb  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180004fd2  mov     [rsp+288h+var_128], rax
0x180004fda  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180004fe1  lea     rcx, [rsp+288h+var_128]; pExceptionObject
0x180004fe9  call    _CxxThrowException_0
0x180004fef  lea     r8, [rsp+288h+var_208]
0x180004ff7  lea     rdx, [rsp+288h+var_220]
0x180004ffc  mov     rcx, rbx; this
0x180004fff  call    ?Save@SubscriptionConfigWriter@@QEAAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z; SubscriptionConfigWriter::Save(std::vector<std::wstring> &,std::vector<std::wstring> &)
0x180005004  nop
0x180005005  lea     rcx, [rsp+288h+hKey]; this
0x18000500a  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18000500f  nop
0x180005010  xor     r8d, r8d
0x180005013  mov     dl, 1
0x180005015  lea     rcx, [rsp+288h+lpSubKey]
0x18000501d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180005022  nop
0x180005023  lea     rcx, [rsp+288h+var_230]
0x180005028  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x18000502d  nop
0x18000502e  mov     rcx, rsi; lpCriticalSection
0x180005031  call    cs:__imp_LeaveCriticalSection
0x180005037  mov     rbx, r13
0x18000503a  mov     edx, r13d
0x18000503d  cmp     edx, [r14]
0x180005040  jnb     short loc_180005064
0x180005042  lea     eax, [rdx-1]
0x180005045  cmp     eax, 4
0x180005048  jbe     short loc_18000505B
0x18000504a  mov     eax, edx
0x18000504c  lea     rcx, [rax+rax*2]
0x180005050  mov     rax, [r14+8]
0x180005054  test    byte ptr [rax+rcx*8+4], 1
0x180005059  jnz     short loc_18000505F
0x18000505b  inc     edx
0x18000505d  jmp     short loc_18000503D
0x18000505f  mov     dil, 1
0x180005062  jmp     short loc_1800050AE
0x180005064  mov     dil, r13b
0x180005067  mov     rcx, qword ptr [rsp+288h+var_208+8]
0x18000506f  sub     rcx, qword ptr [rsp+288h+var_208]
0x180005077  sar     rcx, 5
0x18000507b  mov     rax, qword ptr [rsp+288h+var_220+8]
0x180005080  sub     rax, qword ptr [rsp+288h+var_220]
0x180005085  sar     rax, 5
0x180005089  add     rax, rcx
0x18000508c  cmp     rax, 1
0x180005090  jnz     short loc_1800050AE
0x180005092  test    rcx, rcx
0x180005095  mov     rbx, qword ptr [rsp+288h+var_208]
0x18000509d  jnz     short loc_1800050A4
0x18000509f  mov     rbx, qword ptr [rsp+288h+var_220]
0x1800050a4  cmp     qword ptr [rbx+18h], 8
0x1800050a9  jb      short loc_1800050AE
0x1800050ab  mov     rbx, [rbx]
0x1800050ae  mov     [rsp+288h+var_1E0], 1
0x1800050b6  call    cs:__imp_RpcRevertToSelf
0x1800050bc  mov     qword ptr [rsp+288h+Data], r13
0x1800050c1  xorps   xmm0, xmm0
0x1800050c4  movups  [rsp+288h+var_80], xmm0
0x1800050cc  mov     [rsp+288h+var_1E8], rsi
0x1800050d4  mov     rcx, rsi; lpCriticalSection
0x1800050d7  call    cs:__imp_EnterCriticalSection
0x1800050dd  nop
0x1800050de  mov     rdx, r15; unsigned __int16 *
0x1800050e1  lea     rcx, [rsp+288h+lpSubKey]; this
0x1800050e9  call    ??0SubscriptionConfigReader@@QEAA@PEBGPEAUHKEY__@@0@Z; SubscriptionConfigReader::SubscriptionConfigReader(ushort const *,HKEY__ *,ushort const *)
0x1800050ee  nop
0x1800050ef  mov     ecx, 20h ; ' '; dwBytes
0x1800050f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800050f9  mov     [rsp+288h+var_238], rax
0x1800050fe  test    rax, rax
0x180005101  jz      short loc_18000512F
0x180005103  mov     [rsp+288h+var_258], 1; bool
0x180005108  mov     byte ptr [rsp+288h+cbData], 1; bool
0x18000510d  mov     byte ptr [rsp+288h+phkResult], 1; bool
0x180005112  lea     r9, [rsp+288h+var_80]; struct tag_EcRpcMetadataPropertyList *
0x18000511a  mov     r8, rbx; unsigned __int16 *
0x18000511d  lea     rdx, [rsp+288h+lpSubKey]; struct SubscriptionConfigReader *
0x180005125  mov     rcx, rax; this
0x180005128  call    ??0SubscriptionConfigSnapshot@@QEAA@AEBVSubscriptionConfigReader@@PEBGAEAUtag_EcRpcMetadataPropertyList@@_N33@Z; SubscriptionConfigSnapshot::SubscriptionConfigSnapshot(SubscriptionConfigReader const &,ushort const *,tag_EcRpcMetadataPropertyList &,bool,bool,bool)
0x18000512d  jmp     short loc_180005132
0x18000512f  mov     rax, r13
0x180005132  mov     rdx, rax
0x180005135  lea     rcx, [rsp+288h+Data]
0x18000513a  call    ??4?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAAAEAV01@PEAVSubscriptionConfigSnapshot@@@Z; wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(SubscriptionConfigSnapshot *)
0x18000513f  nop
0x180005140  lea     rcx, [rsp+288h+lpSubKey]; this
0x180005148  call    ??1ConfigBase@@UEAA@XZ; ConfigBase::~ConfigBase(void)
  ... truncated ...
```
