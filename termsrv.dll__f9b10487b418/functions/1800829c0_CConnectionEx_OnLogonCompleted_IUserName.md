# CConnectionEx::OnLogonCompleted(IUserName *)

- ea: `0x1800829c0`
- end: `0x180082eb8`
- name: `?OnLogonCompleted@CConnectionEx@@UEAAJPEAUIUserName@@@Z`
- size: `1272`
- prototype: `__int64 __fastcall(CConnectionEx *__hidden this, struct IUserName *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009ee0`
- `0x18000a210`
- `0x18000c2f0`
- `0x180011f80`
- `0x180013150`
- `0x180013e38`
- `0x1800148d0`
- `0x1800148f0`
- `0x180014ea8`
- `0x180028218`
- `0x1800283c0`
- `0x1800321f0`
- `0x1800330c4`
- `0x18007aea0`
- `0x18007fb10`
- `0x1800829c0`
- `0x18008510c`
- `0x1800c4da0`
- `0x1800c4e0c`
- `0x1800c8010`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180082db3`
- `ntdll!RtlCompareMemory` at `0x180082db3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180082b23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180082b23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e74`

## string_xrefs

- `0x180082dfc`: `CHelper::ConvertWRdsConnectionSettingToUserConfig failed: 0x%x in %s`
- `0x180082c91`: `CHelper::ConvertUserConfigToWRdsConnectionSetting failed: 0x%x in %s`
- `0x180082e03`: `CConnectionEx::OnLogonCompleted`
- `0x180082ce4`: `LogonNotify is being called more than once during a connection`
- `0x180082d1c`: `Calling ptrIWRdsProtocolConnection->LogonNotify`
- `0x180082d77`: `ptrIWRdsProtocolConnection->LogonNotify failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CConnectionEx::OnLogonCompleted(CConnectionEx *this, struct IUserName *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  void (__fastcall *v11)(struct IUserName *, _QWORD, __int64 *); // rbx
  DWORD CurrentProcessId; // eax
  int v13; // eax
  const unsigned __int16 *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rdx
  char *v22; // rax
  __int64 v23; // rax
  char *v24; // rdi
  char *v25; // rax
  const char *v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v30; // [rsp+58h] [rbp-A8h] BYREF
  struct IRemoteConnectionManager *v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v33[16]; // [rsp+70h] [rbp-90h] BYREF
  struct sockaddr_storage v34; // [rsp+80h] [rbp-80h] BYREF
  __int128 v35; // [rsp+100h] [rbp+0h] BYREF
  int v36; // [rsp+110h] [rbp+10h]
  sockaddr_storage v37; // [rsp+120h] [rbp+20h] BYREF
  _BYTE Source1[2152]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v39; // [rsp+A08h] [rbp+908h] BYREF
  unsigned __int16 v40[264]; // [rsp+1060h] [rbp+F60h] BYREF

  v27 = 0;
  pv = 0;
  v30 = 0;
  v32 = 0;
  v35 = *(_OWORD *)((char *)this + 17260);
  v36 = *((_DWORD *)this + 4319);
  v28 = 0;
  memset_0(Source1, 0, 0xEB8u);
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v33, (struct _RTL_RESOURCE *)((char *)this + 18520));
  v4 = (*(__int64 (__fastcall **)(struct IUserName *, int *))(*(_QWORD *)a2 + 104LL))(a2, &v28);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = *(_QWORD *)a2;
    if ( v28 )
    {
      v7 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(v6 + 56))(a2, &pv);
      v5 = v7;
      if ( v7 < 0 )
      {
        _DbgPrintMessage(
          8,
          "pUserName->GetInternetPrincipalStr failed: 0x%x in %s",
          (unsigned int)v7,
          "CConnectionEx::OnLogonCompleted");
        goto LABEL_40;
      }
      v8 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)a2 + 64LL))(a2, &v30);
      v5 = v8;
      if ( v8 < 0 )
      {
        _DbgPrintMessage(
          8,
          "pUserName->GetInternetProviderStr failed: 0x%x in %s",
          (unsigned int)v8,
          "CConnectionEx::OnLogonCompleted");
        goto LABEL_40;
      }
    }
    else
    {
      v9 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(v6 + 40))(a2, &pv);
      v5 = v9;
      if ( v9 < 0 )
      {
        _DbgPrintMessage(
          8,
          "pUserName->GetUserStr failed: 0x%x in %s",
          (unsigned int)v9,
          "CConnectionEx::OnLogonCompleted");
        goto LABEL_40;
      }
      v10 = (*(__int64 (__fastcall **)(struct IUserName *, LPVOID *))(*(_QWORD *)a2 + 48LL))(a2, &v30);
      v5 = v10;
      if ( v10 < 0 )
      {
        _DbgPrintMessage(
          8,
          "pUserName->GetDomainStr failed: 0x%x in %s",
          (unsigned int)v10,
          "CConnectionEx::OnLogonCompleted");
        goto LABEL_40;
      }
    }
    v11 = *(void (__fastcall **)(struct IUserName *, _QWORD, __int64 *))(*(_QWORD *)a2 + 80LL);
    CurrentProcessId = GetCurrentProcessId();
    v11(a2, CurrentProcessId, &v32);
    v31 = 0;
    GetInstanceOfRemoteConnectionManager(&v31);
    LODWORD(v11) = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *))(*(_QWORD *)v31 + 256LL))(v31);
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)&v31);
    if ( (_DWORD)v11 )
    {
      memset_0(&v37, 0, sizeof(v37));
      if ( CHelper::WTSConvertWTSSockAddrToSockAddrStorage((struct _WTS_SOCKADDR *)((char *)this + 15780), &v37) >= 0 )
      {
        if ( (int)StringCbPrintfW(v40, 0x208u, L"%s\\%s", v30, pv) >= 0 )
        {
          v34 = v37;
          if ( (int)CHelper::UALInstrument(&v34, v40) < 0 && (g_DebugTraceComponent & 4) != 0 )
            _DbgPrintMessage(2, "UALInstrument failed");
        }
        else if ( (g_DebugTraceComponent & 4) != 0 )
        {
          _DbgPrintMessage(2, "StringCbPrintf failed");
        }
      }
      else if ( (g_DebugTraceComponent & 4) != 0 )
      {
        _DbgPrintMessage(2, "CHelper::WTSConvertWTSSockAddrToSockAddrStorage failed");
      }
    }
    *((_DWORD *)this + 3068) = 1;
    v13 = CHelper::ConvertUserConfigToWRdsConnectionSetting(
            (struct _WRDS_CONNECTION_SETTINGS *)((char *)this + 12272),
            (CConnectionEx *)((char *)this + 9728),
            *((_DWORD *)this + 450));
    v5 = v13;
    if ( v13 >= 0 )
    {
      memcpy_0(Source1, (char *)this + 12272, 0xEB8u);
      if ( (unsigned int)CDwordHashMap<CConnectionEx::_EventSyncContext *>::Find(
                           (char *)this + 18488,
                           *((unsigned int *)this + 4319),
                           &v27) )
      {
        v14 = (const unsigned __int16 *)v27;
        v17 = *((_DWORD *)v27 + 512);
        if ( (v17 & 1) != 0 )
        {
          if ( (unsigned int)dword_180128170 > 3 )
          {
            v27 = "LogonNotify is being called more than once during a connection";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              (__int64)v14,
              (unsigned __int8 *)&byte_18010E347,
              v15,
              v16,
              (const unsigned __int16 **)&v27);
          }
        }
        else
        {
          *((_DWORD *)v27 + 512) = v17 | 1;
        }
      }
      if ( (unsigned int)dword_180128170 > 5 )
      {
        v27 = "Calling ptrIWRdsProtocolConnection->LogonNotify";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (__int64)v14,
          (unsigned __int8 *)&word_18010E326,
          v15,
          v16,
          (const unsigned __int16 **)&v27);
      }
      v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID, LPVOID, __int128 *, char *))(**((_QWORD **)this + 199)
                                                                                           + 128LL))(
              *((_QWORD *)this + 199),
              v32,
              pv,
              v30,
              &v35,
              (char *)this + 12272);
      v5 = v18;
      if ( v18 >= 0 )
      {
        if ( this == (CConnectionEx *)-12272LL )
        {
          _DbgPrintMessage(
            8,
            "Invalid Parameters failed: 0x%x in %s",
            -2147024809,
            "CConnectionEx::LogEventLogIfSettingsChanged");
        }
        else if ( RtlCompareMemory(Source1, (char *)this + 12272, 0xEB8u) == 3768 )
        {
          _DbgPrintMessage(1, "No difference");
        }
        else
        {
          CrimsonHelper::RaiseEvent<unsigned short const *>(
            (__int64)&CrimsonHelper::s_instance,
            (__int64)EVENT_LISTENER_MODIFIED_SETTINGS,
            (__int64)this + 1696);
        }
        v19 = CHelper::ConvertWRdsConnectionSettingToUserConfig(
                (CConnectionEx *)((char *)this + 9728),
                (struct _WRDS_CONNECTION_SETTINGS *)((char *)this + 12272));
        v5 = v19;
        if ( v19 < 0 )
          _DbgPrintMessage(
            8,
            "CHelper::ConvertWRdsConnectionSettingToUserConfig failed: 0x%x in %s",
            (unsigned int)v19,
            "CConnectionEx::OnLogonCompleted");
      }
      else
      {
        _DbgPrintMessage(
          8,
          "ptrIWRdsProtocolConnection->LogonNotify failed: 0x%x in %s",
          (unsigned int)v18,
          "CConnectionEx::OnLogonCompleted");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "CHelper::ConvertUserConfigToWRdsConnectionSetting failed: 0x%x in %s",
        (unsigned int)v13,
        "CConnectionEx::OnLogonCompleted");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "pUserName->IsConnectedUser failed: 0x%x in %s",
      (unsigned int)v4,
      "CConnectionEx::OnLogonCompleted");
  }
LABEL_40:
  v20 = 256;
  v21 = 256;
  v22 = (char *)this + 14424;
  do
  {
    *v22++ = 0;
    --v21;
  }
  while ( v21 );
  v23 = 15;
  v24 = (char *)this + 9814;
  do
  {
    *v24++ = 0;
    --v23;
  }
  while ( v23 );
  v25 = &v39;
  do
  {
    *v25++ = 0;
    --v20;
  }
  while ( v20 );
  if ( pv )
    CoTaskMemFree(pv);
  if ( v30 )
    CoTaskMemFree(v30);
  CAutoLock::Unlock((CAutoLock *)v33);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&v32);
  return v5;
}

```

## disassembly

```asm
0x1800829c0  mov     [rsp-8+arg_10], rbx
0x1800829c5  push    rbp
0x1800829c6  push    rsi
0x1800829c7  push    rdi
0x1800829c8  push    r13
0x1800829ca  push    r14
0x1800829cc  lea     rbp, [rsp-1180h]
0x1800829d4  mov     eax, 1280h
0x1800829d9  call    _alloca_probe
0x1800829de  sub     rsp, rax
0x1800829e1  mov     rax, cs:__security_cookie
0x1800829e8  xor     rax, rsp
0x1800829eb  mov     [rbp+11A0h+var_30], rax
0x1800829f2  mov     rsi, rdx
0x1800829f5  mov     rdi, rcx
0x1800829f8  mov     [rsp+12A0h+var_1260], 0
0x180082a01  mov     [rsp+12A0h+pv], 0
0x180082a0a  mov     [rsp+12A0h+var_1248], 0
0x180082a13  mov     [rsp+12A0h+var_1238], 0
0x180082a1c  movups  xmm0, xmmword ptr [rcx+436Ch]
0x180082a23  movdqu  [rbp+11A0h+var_11A0], xmm0
0x180082a28  mov     eax, [rcx+437Ch]
0x180082a2e  mov     [rbp+11A0h+var_1190], eax
0x180082a31  mov     [rsp+12A0h+var_1258], 0
0x180082a39  mov     r13d, 0EB8h
0x180082a3f  mov     r8d, r13d; Size
0x180082a42  xor     edx, edx; Val
0x180082a44  lea     rcx, [rbp+11A0h+Source1]; void *
0x180082a4b  call    memset_0
0x180082a50  lea     rdx, [rdi+4858h]; struct CResource *
0x180082a57  lea     rcx, [rsp+12A0h+var_1230]; this
0x180082a5c  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180082a61  nop
0x180082a62  mov     rax, [rsi]
0x180082a65  lea     rdx, [rsp+12A0h+var_1258]
0x180082a6a  mov     rcx, rsi
0x180082a6d  mov     rax, [rax+68h]
0x180082a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082a76  mov     ebx, eax
0x180082a78  test    eax, eax
0x180082a7a  jns     short loc_180082A88
0x180082a7c  lea     rdx, aPusernameIscon; "pUserName->IsConnectedUser failed: 0x%x"...
0x180082a83  jmp     loc_180082E03
0x180082a88  mov     rax, [rsi]
0x180082a8b  lea     rdx, [rsp+12A0h+pv]
0x180082a90  mov     rcx, rsi
0x180082a93  cmp     [rsp+12A0h+var_1258], 0
0x180082a98  jz      short loc_180082ADB
0x180082a9a  mov     rax, [rax+38h]
0x180082a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082aa3  mov     ebx, eax
0x180082aa5  test    eax, eax
0x180082aa7  jns     short loc_180082AB5
0x180082aa9  lea     rdx, aPusernameGetin; "pUserName->GetInternetPrincipalStr fail"...
0x180082ab0  jmp     loc_180082E03
0x180082ab5  mov     rax, [rsi]
0x180082ab8  lea     rdx, [rsp+12A0h+var_1248]
0x180082abd  mov     rcx, rsi
0x180082ac0  mov     rax, [rax+40h]
0x180082ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ac9  mov     ebx, eax
0x180082acb  test    eax, eax
0x180082acd  jns     short loc_180082B1C
0x180082acf  lea     rdx, aPusernameGetin_0; "pUserName->GetInternetProviderStr faile"...
0x180082ad6  jmp     loc_180082E03
0x180082adb  mov     rax, [rax+28h]
0x180082adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ae4  mov     ebx, eax
0x180082ae6  test    eax, eax
0x180082ae8  jns     short loc_180082AF6
0x180082aea  lea     rdx, aPusernameGetus_0; "pUserName->GetUserStr failed: 0x%x in %"...
0x180082af1  jmp     loc_180082E03
0x180082af6  mov     rax, [rsi]
0x180082af9  lea     rdx, [rsp+12A0h+var_1248]
0x180082afe  mov     rcx, rsi
0x180082b01  mov     rax, [rax+30h]
0x180082b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b0a  mov     ebx, eax
0x180082b0c  test    eax, eax
0x180082b0e  jns     short loc_180082B1C
0x180082b10  lea     rdx, aPusernameGetdo; "pUserName->GetDomainStr failed: 0x%x in"...
0x180082b17  jmp     loc_180082E03
0x180082b1c  mov     rax, [rsi]
0x180082b1f  mov     rbx, [rax+50h]
0x180082b23  call    cs:__imp_GetCurrentProcessId
0x180082b29  lea     r8, [rsp+12A0h+var_1238]
0x180082b2e  mov     edx, eax
0x180082b30  mov     rcx, rsi
0x180082b33  mov     rax, rbx
0x180082b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b3b  mov     [rsp+12A0h+var_1240], 0
0x180082b44  lea     rcx, [rsp+12A0h+var_1240]; struct IRemoteConnectionManager **
0x180082b49  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180082b4e  mov     rcx, [rsp+12A0h+var_1240]
0x180082b53  mov     rax, [rcx]
0x180082b56  mov     rax, [rax+100h]
0x180082b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b62  mov     ebx, eax
0x180082b64  lea     rcx, [rsp+12A0h+var_1240]; void *
0x180082b69  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180082b6e  test    ebx, ebx
0x180082b70  jz      loc_180082C65
0x180082b76  xor     edx, edx; Val
0x180082b78  mov     r8d, 80h; Size
0x180082b7e  lea     rcx, [rbp+11A0h+var_1180]; void *
0x180082b82  call    memset_0
0x180082b87  lea     rcx, [rdi+3DA4h]; struct _WTS_SOCKADDR *
0x180082b8e  lea     rdx, [rbp+11A0h+var_1180]; struct sockaddr_storage *
0x180082b92  call    ?WTSConvertWTSSockAddrToSockAddrStorage@CHelper@@SAJPEAU_WTS_SOCKADDR@@PEAUsockaddr_storage@@@Z; CHelper::WTSConvertWTSSockAddrToSockAddrStorage(_WTS_SOCKADDR *,sockaddr_storage *)
0x180082b97  test    eax, eax
0x180082b99  jns     short loc_180082BB4
0x180082b9b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x180082ba2  jz      loc_180082C65
0x180082ba8  lea     rdx, aChelperWtsconv; "CHelper::WTSConvertWTSSockAddrToSockAdd"...
0x180082baf  jmp     loc_180082C5B
0x180082bb4  mov     rax, [rsp+12A0h+pv]
0x180082bb9  mov     [rsp+12A0h+var_1280], rax
0x180082bbe  mov     r9, [rsp+12A0h+var_1248]
0x180082bc3  lea     r8, aSS_0; "%s\\%s"
0x180082bca  mov     edx, 208h; unsigned __int64
0x180082bcf  lea     rcx, [rbp+11A0h+var_240]; unsigned __int16 *
0x180082bd6  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180082bdb  test    eax, eax
0x180082bdd  jns     short loc_180082BF1
0x180082bdf  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x180082be6  jz      short loc_180082C65
0x180082be8  lea     rdx, aStringcbprintf; "StringCbPrintf failed"
0x180082bef  jmp     short loc_180082C5B
0x180082bf1  movaps  xmm0, xmmword ptr [rbp+11A0h+var_1180.ss_family]
0x180082bf5  movaps  xmmword ptr [rbp+11A0h+var_1220.ss_family], xmm0
0x180082bf9  movaps  xmm1, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2]
0x180082bfd  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2], xmm1
0x180082c01  movaps  xmm0, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2+10h]
0x180082c05  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2+10h], xmm0
0x180082c09  movaps  xmm1, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2+20h]
0x180082c0d  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2+20h], xmm1
0x180082c11  movaps  xmm0, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2+30h]
0x180082c15  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2+30h], xmm0
0x180082c19  movaps  xmm1, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2+40h]
0x180082c1d  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2+40h], xmm1
0x180082c21  movaps  xmm0, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2+50h]
0x180082c28  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2+50h], xmm0
0x180082c2c  movaps  xmm1, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2+60h]
0x180082c33  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2+60h], xmm1
0x180082c37  lea     rdx, [rbp+11A0h+var_240]; unsigned __int16 *
0x180082c3e  lea     rcx, [rbp+11A0h+var_1220]; struct sockaddr_storage
0x180082c42  call    ?UALInstrument@CHelper@@SAJUsockaddr_storage@@PEBG@Z; CHelper::UALInstrument(sockaddr_storage,ushort const *)
0x180082c47  test    eax, eax
0x180082c49  jns     short loc_180082C65
0x180082c4b  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x180082c52  jz      short loc_180082C65
0x180082c54  lea     rdx, aUalinstrumentF; "UALInstrument failed"
0x180082c5b  mov     ecx, 2; int
0x180082c60  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180082c65  lea     rsi, [rdi+2FF0h]
0x180082c6c  mov     dword ptr [rsi], 1
0x180082c72  lea     r14, [rdi+2600h]
0x180082c79  mov     r8d, [rdi+708h]; unsigned int
0x180082c80  mov     rdx, r14; struct _USERCONFIGW *
0x180082c83  mov     rcx, rsi; struct _WRDS_CONNECTION_SETTINGS *
0x180082c86  call    ?ConvertUserConfigToWRdsConnectionSetting@CHelper@@SAJPEAU_WRDS_CONNECTION_SETTINGS@@PEAU_USERCONFIGW@@K@Z; CHelper::ConvertUserConfigToWRdsConnectionSetting(_WRDS_CONNECTION_SETTINGS *,_USERCONFIGW *,ulong)
0x180082c8b  mov     ebx, eax
0x180082c8d  test    eax, eax
0x180082c8f  jns     short loc_180082C9D
0x180082c91  lea     rdx, aChelperConvert_2; "CHelper::ConvertUserConfigToWRdsConnect"...
0x180082c98  jmp     loc_180082E03
0x180082c9d  lea     rcx, [rbp+11A0h+Source1]; void *
0x180082ca4  mov     rdx, rsi; Src
0x180082ca7  mov     r8, r13; Size
0x180082caa  call    memcpy_0
0x180082caf  lea     rcx, [rdi+4838h]
0x180082cb6  lea     r8, [rsp+12A0h+var_1260]
0x180082cbb  mov     edx, [rdi+437Ch]
0x180082cc1  call    ?Find@?$CDwordHashMap@PEAU_EventSyncContext@CConnectionEx@@@@QEAAHKPEAPEAU_EventSyncContext@CConnectionEx@@@Z; CDwordHashMap<CConnectionEx::_EventSyncContext *>::Find(ulong,CConnectionEx::_EventSyncContext * *)
0x180082cc6  test    eax, eax
0x180082cc8  jz      short loc_180082D11
0x180082cca  mov     rcx, [rsp+12A0h+var_1260]
0x180082ccf  mov     eax, [rcx+800h]
0x180082cd5  test    al, 1
0x180082cd7  jz      short loc_180082D08
0x180082cd9  mov     eax, cs:dword_180128170
0x180082cdf  cmp     eax, 3
0x180082ce2  jbe     short loc_180082D11
0x180082ce4  lea     rax, aLogonnotifyIsB; "LogonNotify is being called more than o"...
0x180082ceb  mov     [rsp+12A0h+var_1260], rax
0x180082cf0  lea     rax, [rsp+12A0h+var_1260]
0x180082cf5  mov     [rsp+12A0h+var_1280], rax
0x180082cfa  lea     rdx, byte_18010E347
0x180082d01  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180082d06  jmp     short loc_180082D11
0x180082d08  or      eax, 1
0x180082d0b  mov     [rcx+800h], eax
0x180082d11  mov     eax, cs:dword_180128170
0x180082d17  cmp     eax, 5
0x180082d1a  jbe     short loc_180082D3E
0x180082d1c  lea     rax, aCallingPtriwrd; "Calling ptrIWRdsProtocolConnection->Log"...
0x180082d23  mov     [rsp+12A0h+var_1260], rax
0x180082d28  lea     rax, [rsp+12A0h+var_1260]
0x180082d2d  mov     [rsp+12A0h+var_1280], rax
0x180082d32  lea     rdx, word_18010E326
0x180082d39  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180082d3e  mov     rcx, [rdi+638h]
0x180082d45  mov     rax, [rcx]
0x180082d48  mov     [rsp+12A0h+var_1278], rsi
0x180082d4d  lea     rdx, [rbp+11A0h+var_11A0]
0x180082d51  mov     [rsp+12A0h+var_1280], rdx
0x180082d56  mov     r9, [rsp+12A0h+var_1248]
0x180082d5b  mov     r8, [rsp+12A0h+pv]
0x180082d60  mov     rdx, [rsp+12A0h+var_1238]
0x180082d65  mov     rax, [rax+80h]
0x180082d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082d71  mov     ebx, eax
0x180082d73  test    eax, eax
0x180082d75  jns     short loc_180082D83
0x180082d77  lea     rdx, aPtriwrdsprotoc; "ptrIWRdsProtocolConnection->LogonNotify"...
0x180082d7e  jmp     loc_180082E03
0x180082d83  test    rsi, rsi
0x180082d86  jnz     short loc_180082DA6
0x180082d88  lea     r9, aCconnectionexL; "CConnectionEx::LogEventLogIfSettingsCha"...
0x180082d8f  mov     r8d, 80070057h
0x180082d95  lea     rdx, aInvalidParamet; "Invalid Parameters failed: 0x%x in %s"
0x180082d9c  lea     ecx, [rsi+8]; int
0x180082d9f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180082da4  jmp     short loc_180082DEB
0x180082da6  mov     r8, r13; Length
0x180082da9  mov     rdx, rsi; Source2
0x180082dac  lea     rcx, [rbp+11A0h+Source1]; Source1
0x180082db3  call    cs:__imp_RtlCompareMemory
0x180082db9  cmp     rax, r13
0x180082dbc  jnz     short loc_180082DD1
0x180082dbe  lea     rdx, aNoDifference; "No difference"
0x180082dc5  mov     ecx, 1; int
0x180082dca  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180082dcf  jmp     short loc_180082DEB
0x180082dd1  lea     r8, [rdi+6A0h]
0x180082dd8  lea     rdx, EVENT_LISTENER_MODIFIED_SETTINGS
0x180082ddf  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180082de6  call    ??$RaiseEvent@PEBG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEBG@Z; CrimsonHelper::RaiseEvent<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const *)
0x180082deb  mov     rdx, rsi; struct _WRDS_CONNECTION_SETTINGS *
0x180082dee  mov     rcx, r14; struct _USERCONFIGW *
0x180082df1  call    ?ConvertWRdsConnectionSettingToUserConfig@CHelper@@SAJPEAU_USERCONFIGW@@PEAU_WRDS_CONNECTION_SETTINGS@@@Z; CHelper::ConvertWRdsConnectionSettingToUserConfig(_USERCONFIGW *,_WRDS_CONNECTION_SETTINGS *)
0x180082df6  mov     ebx, eax
0x180082df8  test    eax, eax
0x180082dfa  jns     short loc_180082E17
0x180082dfc  lea     rdx, aChelperConvert_7; "CHelper::ConvertWRdsConnectionSettingTo"...
0x180082e03  lea     r9, aCconnectionexO_1; "CConnectionEx::OnLogonCompleted"
0x180082e0a  mov     r8d, eax
0x180082e0d  mov     ecx, 8; int
0x180082e12  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180082e17  mov     ecx, 100h
0x180082e1c  mov     edx, ecx
0x180082e1e  lea     rax, [rdi+3858h]
0x180082e25  mov     byte ptr [rax], 0
0x180082e28  inc     rax
0x180082e2b  sub     rdx, 1
0x180082e2f  jnz     short loc_180082E25
0x180082e31  lea     eax, [rdx+0Fh]
0x180082e34  add     rdi, 2656h
0x180082e3b  mov     byte ptr [rdi], 0
0x180082e3e  inc     rdi
0x180082e41  sub     rax, 1
0x180082e45  jnz     short loc_180082E3B
0x180082e47  lea     rax, [rbp+11A0h+var_898]
0x180082e4e  mov     byte ptr [rax], 0
0x180082e51  inc     rax
0x180082e54  sub     rcx, 1
0x180082e58  jnz     short loc_180082E4E
0x180082e5a  mov     rcx, [rsp+12A0h+pv]; pv
0x180082e5f  test    rcx, rcx
0x180082e62  jz      short loc_180082E6A
0x180082e64  call    cs:__imp_CoTaskMemFree
0x180082e6a  mov     rcx, [rsp+12A0h+var_1248]; pv
0x180082e6f  test    rcx, rcx
0x180082e72  jz      short loc_180082E7B
0x180082e74  call    cs:__imp_CoTaskMemFree
0x180082e7a  nop
0x180082e7b  lea     rcx, [rsp+12A0h+var_1230]; this
0x180082e80  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180082e85  nop
0x180082e86  lea     rcx, [rsp+12A0h+var_1238]; this
0x180082e8b  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x180082e90  mov     eax, ebx
0x180082e92  mov     rcx, [rbp+11A0h+var_30]
0x180082e99  xor     rcx, rsp; StackCookie
0x180082e9c  call    __security_check_cookie
0x180082ea1  mov     rbx, [rsp+12A0h+arg_10]
0x180082ea9  add     rsp, 1280h
0x180082eb0  pop     r14
0x180082eb2  pop     r13
0x180082eb4  pop     rdi
0x180082eb5  pop     rsi
0x180082eb6  pop     rbp
0x180082eb7  retn
```
