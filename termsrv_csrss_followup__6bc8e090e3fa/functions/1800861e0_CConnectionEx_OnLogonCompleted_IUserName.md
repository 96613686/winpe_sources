# CConnectionEx::OnLogonCompleted(IUserName *)

- ea: `0x1800861e0`
- end: `0x1800866f1`
- name: `?OnLogonCompleted@CConnectionEx@@UEAAJPEAUIUserName@@@Z`
- size: `1297`
- prototype: `__int64 __fastcall(CConnectionEx *__hidden this, struct IUserName *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800095a0`
- `0x180009940`
- `0x18000c2a0`
- `0x180012750`
- `0x1800139c0`
- `0x180014808`
- `0x180015020`
- `0x180015310`
- `0x180015938`
- `0x180029784`
- `0x180029930`
- `0x180033f60`
- `0x180034e64`
- `0x18007e580`
- `0x1800832ac`
- `0x1800861e0`
- `0x1800889f0`
- `0x1800cae70`
- `0x1800caedc`
- `0x1800ce010`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1800865d9`
- `ntdll!RtlCompareMemory` at `0x1800865d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180086343`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180086343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086690`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800866a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180086690`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800866a6`

## string_xrefs

- `0x180086628`: `CHelper::ConvertWRdsConnectionSettingToUserConfig failed: 0x%x in %s`
- `0x1800864b7`: `CHelper::ConvertUserConfigToWRdsConnectionSetting failed: 0x%x in %s`
- `0x18008662f`: `CConnectionEx::OnLogonCompleted`
- `0x18008650a`: `LogonNotify is being called more than once during a connection`
- `0x180086542`: `Calling ptrIWRdsProtocolConnection->LogonNotify`
- `0x18008659d`: `ptrIWRdsProtocolConnection->LogonNotify failed: 0x%x in %s`

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
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
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
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v33, (CConnectionEx *)((char *)this + 18520));
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
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v31);
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
        v14 = (int)v27;
        v17 = *((_DWORD *)v27 + 512);
        if ( (v17 & 1) != 0 )
        {
          if ( (unsigned int)dword_18012E170 > 3 )
          {
            v27 = "LogonNotify is being called more than once during a connection";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v14,
              (unsigned int)&byte_1801143C7,
              v15,
              v16,
              (__int64)&v27);
          }
        }
        else
        {
          *((_DWORD *)v27 + 512) = v17 | 1;
        }
      }
      if ( (unsigned int)dword_18012E170 > 5 )
      {
        v27 = "Calling ptrIWRdsProtocolConnection->LogonNotify";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v14,
          (unsigned int)&word_1801143A6,
          v15,
          v16,
          (__int64)&v27);
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
            &CrimsonHelper::s_instance,
            EVENT_LISTENER_MODIFIED_SETTINGS,
            (char *)this + 1696);
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
0x1800861e0  mov     [rsp-8+arg_10], rbx
0x1800861e5  push    rbp
0x1800861e6  push    rsi
0x1800861e7  push    rdi
0x1800861e8  push    r13
0x1800861ea  push    r14
0x1800861ec  lea     rbp, [rsp-1180h]
0x1800861f4  mov     eax, 1280h
0x1800861f9  call    _alloca_probe
0x1800861fe  sub     rsp, rax
0x180086201  mov     rax, cs:__security_cookie
0x180086208  xor     rax, rsp
0x18008620b  mov     [rbp+11A0h+var_30], rax
0x180086212  mov     rsi, rdx
0x180086215  mov     rdi, rcx
0x180086218  mov     [rsp+12A0h+var_1260], 0
0x180086221  mov     [rsp+12A0h+pv], 0
0x18008622a  mov     [rsp+12A0h+var_1248], 0
0x180086233  mov     [rsp+12A0h+var_1238], 0
0x18008623c  movups  xmm0, xmmword ptr [rcx+436Ch]
0x180086243  movdqu  [rbp+11A0h+var_11A0], xmm0
0x180086248  mov     eax, [rcx+437Ch]
0x18008624e  mov     [rbp+11A0h+var_1190], eax
0x180086251  mov     [rsp+12A0h+var_1258], 0
0x180086259  mov     r13d, 0EB8h
0x18008625f  mov     r8d, r13d; Size
0x180086262  xor     edx, edx; Val
0x180086264  lea     rcx, [rbp+11A0h+Source1]; void *
0x18008626b  call    memset_0
0x180086270  lea     rdx, [rdi+4858h]; struct CResource *
0x180086277  lea     rcx, [rsp+12A0h+var_1230]; this
0x18008627c  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180086281  nop
0x180086282  mov     rax, [rsi]
0x180086285  lea     rdx, [rsp+12A0h+var_1258]
0x18008628a  mov     rcx, rsi
0x18008628d  mov     rax, [rax+68h]
0x180086291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086296  mov     ebx, eax
0x180086298  test    eax, eax
0x18008629a  jns     short loc_1800862A8
0x18008629c  lea     rdx, aPusernameIscon; "pUserName->IsConnectedUser failed: 0x%x"...
0x1800862a3  jmp     loc_18008662F
0x1800862a8  mov     rax, [rsi]
0x1800862ab  lea     rdx, [rsp+12A0h+pv]
0x1800862b0  mov     rcx, rsi
0x1800862b3  cmp     [rsp+12A0h+var_1258], 0
0x1800862b8  jz      short loc_1800862FB
0x1800862ba  mov     rax, [rax+38h]
0x1800862be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800862c3  mov     ebx, eax
0x1800862c5  test    eax, eax
0x1800862c7  jns     short loc_1800862D5
0x1800862c9  lea     rdx, aPusernameGetin; "pUserName->GetInternetPrincipalStr fail"...
0x1800862d0  jmp     loc_18008662F
0x1800862d5  mov     rax, [rsi]
0x1800862d8  lea     rdx, [rsp+12A0h+var_1248]
0x1800862dd  mov     rcx, rsi
0x1800862e0  mov     rax, [rax+40h]
0x1800862e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800862e9  mov     ebx, eax
0x1800862eb  test    eax, eax
0x1800862ed  jns     short loc_18008633C
0x1800862ef  lea     rdx, aPusernameGetin_0; "pUserName->GetInternetProviderStr faile"...
0x1800862f6  jmp     loc_18008662F
0x1800862fb  mov     rax, [rax+28h]
0x1800862ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086304  mov     ebx, eax
0x180086306  test    eax, eax
0x180086308  jns     short loc_180086316
0x18008630a  lea     rdx, aPusernameGetus_0; "pUserName->GetUserStr failed: 0x%x in %"...
0x180086311  jmp     loc_18008662F
0x180086316  mov     rax, [rsi]
0x180086319  lea     rdx, [rsp+12A0h+var_1248]
0x18008631e  mov     rcx, rsi
0x180086321  mov     rax, [rax+30h]
0x180086325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008632a  mov     ebx, eax
0x18008632c  test    eax, eax
0x18008632e  jns     short loc_18008633C
0x180086330  lea     rdx, aPusernameGetdo; "pUserName->GetDomainStr failed: 0x%x in"...
0x180086337  jmp     loc_18008662F
0x18008633c  mov     rax, [rsi]
0x18008633f  mov     rbx, [rax+50h]
0x180086343  call    cs:__imp_GetCurrentProcessId
0x18008634a  nop     dword ptr [rax+rax+00h]
0x18008634f  lea     r8, [rsp+12A0h+var_1238]
0x180086354  mov     edx, eax
0x180086356  mov     rcx, rsi
0x180086359  mov     rax, rbx
0x18008635c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086361  mov     [rsp+12A0h+var_1240], 0
0x18008636a  lea     rcx, [rsp+12A0h+var_1240]; struct IRemoteConnectionManager **
0x18008636f  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180086374  mov     rcx, [rsp+12A0h+var_1240]
0x180086379  mov     rax, [rcx]
0x18008637c  mov     rax, [rax+100h]
0x180086383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086388  mov     ebx, eax
0x18008638a  lea     rcx, [rsp+12A0h+var_1240]; void *
0x18008638f  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180086394  test    ebx, ebx
0x180086396  jz      loc_18008648B
0x18008639c  xor     edx, edx; Val
0x18008639e  mov     r8d, 80h; Size
0x1800863a4  lea     rcx, [rbp+11A0h+var_1180]; void *
0x1800863a8  call    memset_0
0x1800863ad  lea     rcx, [rdi+3DA4h]; struct _WTS_SOCKADDR *
0x1800863b4  lea     rdx, [rbp+11A0h+var_1180]; struct sockaddr_storage *
0x1800863b8  call    ?WTSConvertWTSSockAddrToSockAddrStorage@CHelper@@SAJPEAU_WTS_SOCKADDR@@PEAUsockaddr_storage@@@Z; CHelper::WTSConvertWTSSockAddrToSockAddrStorage(_WTS_SOCKADDR *,sockaddr_storage *)
0x1800863bd  test    eax, eax
0x1800863bf  jns     short loc_1800863DA
0x1800863c1  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x1800863c8  jz      loc_18008648B
0x1800863ce  lea     rdx, aChelperWtsconv; "CHelper::WTSConvertWTSSockAddrToSockAdd"...
0x1800863d5  jmp     loc_180086481
0x1800863da  mov     rax, [rsp+12A0h+pv]
0x1800863df  mov     [rsp+12A0h+var_1280], rax
0x1800863e4  mov     r9, [rsp+12A0h+var_1248]
0x1800863e9  lea     r8, aSS_0; "%s\\%s"
0x1800863f0  mov     edx, 208h; unsigned __int64
0x1800863f5  lea     rcx, [rbp+11A0h+var_240]; unsigned __int16 *
0x1800863fc  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180086401  test    eax, eax
0x180086403  jns     short loc_180086417
0x180086405  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x18008640c  jz      short loc_18008648B
0x18008640e  lea     rdx, aStringcbprintf; "StringCbPrintf failed"
0x180086415  jmp     short loc_180086481
0x180086417  movaps  xmm0, xmmword ptr [rbp+11A0h+var_1180.ss_family]
0x18008641b  movaps  xmmword ptr [rbp+11A0h+var_1220.ss_family], xmm0
0x18008641f  movaps  xmm1, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2]
0x180086423  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2], xmm1
0x180086427  movaps  xmm0, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2+10h]
0x18008642b  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2+10h], xmm0
0x18008642f  movaps  xmm1, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2+20h]
0x180086433  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2+20h], xmm1
0x180086437  movaps  xmm0, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2+30h]
0x18008643b  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2+30h], xmm0
0x18008643f  movaps  xmm1, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2+40h]
0x180086443  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2+40h], xmm1
0x180086447  movaps  xmm0, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2+50h]
0x18008644e  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2+50h], xmm0
0x180086452  movaps  xmm1, xmmword ptr [rbp+11A0h+var_1180.__ss_pad2+60h]
0x180086459  movaps  xmmword ptr [rbp+11A0h+var_1220.__ss_pad2+60h], xmm1
0x18008645d  lea     rdx, [rbp+11A0h+var_240]; unsigned __int16 *
0x180086464  lea     rcx, [rbp+11A0h+var_1220]; struct sockaddr_storage
0x180086468  call    ?UALInstrument@CHelper@@SAJUsockaddr_storage@@PEBG@Z; CHelper::UALInstrument(sockaddr_storage,ushort const *)
0x18008646d  test    eax, eax
0x18008646f  jns     short loc_18008648B
0x180086471  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x180086478  jz      short loc_18008648B
0x18008647a  lea     rdx, aUalinstrumentF; "UALInstrument failed"
0x180086481  mov     ecx, 2; int
0x180086486  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008648b  lea     rsi, [rdi+2FF0h]
0x180086492  mov     dword ptr [rsi], 1
0x180086498  lea     r14, [rdi+2600h]
0x18008649f  mov     r8d, [rdi+708h]; unsigned int
0x1800864a6  mov     rdx, r14; struct _USERCONFIGW *
0x1800864a9  mov     rcx, rsi; struct _WRDS_CONNECTION_SETTINGS *
0x1800864ac  call    ?ConvertUserConfigToWRdsConnectionSetting@CHelper@@SAJPEAU_WRDS_CONNECTION_SETTINGS@@PEAU_USERCONFIGW@@K@Z; CHelper::ConvertUserConfigToWRdsConnectionSetting(_WRDS_CONNECTION_SETTINGS *,_USERCONFIGW *,ulong)
0x1800864b1  mov     ebx, eax
0x1800864b3  test    eax, eax
0x1800864b5  jns     short loc_1800864C3
0x1800864b7  lea     rdx, aChelperConvert_2; "CHelper::ConvertUserConfigToWRdsConnect"...
0x1800864be  jmp     loc_18008662F
0x1800864c3  lea     rcx, [rbp+11A0h+Source1]; void *
0x1800864ca  mov     rdx, rsi; Src
0x1800864cd  mov     r8, r13; Size
0x1800864d0  call    memcpy_0
0x1800864d5  lea     rcx, [rdi+4838h]
0x1800864dc  lea     r8, [rsp+12A0h+var_1260]
0x1800864e1  mov     edx, [rdi+437Ch]
0x1800864e7  call    ?Find@?$CDwordHashMap@PEAU_EventSyncContext@CConnectionEx@@@@QEAAHKPEAPEAU_EventSyncContext@CConnectionEx@@@Z; CDwordHashMap<CConnectionEx::_EventSyncContext *>::Find(ulong,CConnectionEx::_EventSyncContext * *)
0x1800864ec  test    eax, eax
0x1800864ee  jz      short loc_180086537
0x1800864f0  mov     rcx, [rsp+12A0h+var_1260]
0x1800864f5  mov     eax, [rcx+800h]
0x1800864fb  test    al, 1
0x1800864fd  jz      short loc_18008652E
0x1800864ff  mov     eax, cs:dword_18012E170
0x180086505  cmp     eax, 3
0x180086508  jbe     short loc_180086537
0x18008650a  lea     rax, aLogonnotifyIsB; "LogonNotify is being called more than o"...
0x180086511  mov     [rsp+12A0h+var_1260], rax
0x180086516  lea     rax, [rsp+12A0h+var_1260]
0x18008651b  mov     [rsp+12A0h+var_1280], rax
0x180086520  lea     rdx, byte_1801143C7
0x180086527  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008652c  jmp     short loc_180086537
0x18008652e  or      eax, 1
0x180086531  mov     [rcx+800h], eax
0x180086537  mov     eax, cs:dword_18012E170
0x18008653d  cmp     eax, 5
0x180086540  jbe     short loc_180086564
0x180086542  lea     rax, aCallingPtriwrd; "Calling ptrIWRdsProtocolConnection->Log"...
0x180086549  mov     [rsp+12A0h+var_1260], rax
0x18008654e  lea     rax, [rsp+12A0h+var_1260]
0x180086553  mov     [rsp+12A0h+var_1280], rax
0x180086558  lea     rdx, word_1801143A6
0x18008655f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180086564  mov     rcx, [rdi+638h]
0x18008656b  mov     rax, [rcx]
0x18008656e  mov     [rsp+12A0h+var_1278], rsi
0x180086573  lea     rdx, [rbp+11A0h+var_11A0]
0x180086577  mov     [rsp+12A0h+var_1280], rdx
0x18008657c  mov     r9, [rsp+12A0h+var_1248]
0x180086581  mov     r8, [rsp+12A0h+pv]
0x180086586  mov     rdx, [rsp+12A0h+var_1238]
0x18008658b  mov     rax, [rax+80h]
0x180086592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086597  mov     ebx, eax
0x180086599  test    eax, eax
0x18008659b  jns     short loc_1800865A9
0x18008659d  lea     rdx, aPtriwrdsprotoc; "ptrIWRdsProtocolConnection->LogonNotify"...
0x1800865a4  jmp     loc_18008662F
0x1800865a9  test    rsi, rsi
0x1800865ac  jnz     short loc_1800865CC
0x1800865ae  lea     r9, aCconnectionexL; "CConnectionEx::LogEventLogIfSettingsCha"...
0x1800865b5  mov     r8d, 80070057h
0x1800865bb  lea     rdx, aInvalidParamet; "Invalid Parameters failed: 0x%x in %s"
0x1800865c2  lea     ecx, [rsi+8]; int
0x1800865c5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800865ca  jmp     short loc_180086617
0x1800865cc  mov     r8, r13; Length
0x1800865cf  mov     rdx, rsi; Source2
0x1800865d2  lea     rcx, [rbp+11A0h+Source1]; Source1
0x1800865d9  call    cs:__imp_RtlCompareMemory
0x1800865e0  nop     dword ptr [rax+rax+00h]
0x1800865e5  cmp     rax, r13
0x1800865e8  jnz     short loc_1800865FD
0x1800865ea  lea     rdx, aNoDifference; "No difference"
0x1800865f1  mov     ecx, 1; int
0x1800865f6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800865fb  jmp     short loc_180086617
0x1800865fd  lea     r8, [rdi+6A0h]
0x180086604  lea     rdx, EVENT_LISTENER_MODIFIED_SETTINGS
0x18008660b  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; CrimsonHelper CrimsonHelper::s_instance
0x180086612  call    ??$RaiseEvent@PEBG@CrimsonHelper@@QEAAKAEBU_EVENT_DESCRIPTOR@@PEBG@Z; CrimsonHelper::RaiseEvent<ushort const *>(_EVENT_DESCRIPTOR const &,ushort const *)
0x180086617  mov     rdx, rsi; struct _WRDS_CONNECTION_SETTINGS *
0x18008661a  mov     rcx, r14; struct _USERCONFIGW *
0x18008661d  call    ?ConvertWRdsConnectionSettingToUserConfig@CHelper@@SAJPEAU_USERCONFIGW@@PEAU_WRDS_CONNECTION_SETTINGS@@@Z; CHelper::ConvertWRdsConnectionSettingToUserConfig(_USERCONFIGW *,_WRDS_CONNECTION_SETTINGS *)
0x180086622  mov     ebx, eax
0x180086624  test    eax, eax
0x180086626  jns     short loc_180086643
0x180086628  lea     rdx, aChelperConvert_7; "CHelper::ConvertWRdsConnectionSettingTo"...
0x18008662f  lea     r9, aCconnectionexO_1; "CConnectionEx::OnLogonCompleted"
0x180086636  mov     r8d, eax
0x180086639  mov     ecx, 8; int
0x18008663e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180086643  mov     ecx, 100h
0x180086648  mov     edx, ecx
0x18008664a  lea     rax, [rdi+3858h]
0x180086651  mov     byte ptr [rax], 0
0x180086654  inc     rax
0x180086657  sub     rdx, 1
0x18008665b  jnz     short loc_180086651
0x18008665d  lea     eax, [rdx+0Fh]
0x180086660  add     rdi, 2656h
0x180086667  mov     byte ptr [rdi], 0
0x18008666a  inc     rdi
0x18008666d  sub     rax, 1
0x180086671  jnz     short loc_180086667
0x180086673  lea     rax, [rbp+11A0h+var_898]
0x18008667a  mov     byte ptr [rax], 0
0x18008667d  inc     rax
0x180086680  sub     rcx, 1
0x180086684  jnz     short loc_18008667A
0x180086686  mov     rcx, [rsp+12A0h+pv]; pv
0x18008668b  test    rcx, rcx
0x18008668e  jz      short loc_18008669C
0x180086690  call    cs:__imp_CoTaskMemFree
0x180086697  nop     dword ptr [rax+rax+00h]
0x18008669c  mov     rcx, [rsp+12A0h+var_1248]; pv
0x1800866a1  test    rcx, rcx
0x1800866a4  jz      short loc_1800866B3
0x1800866a6  call    cs:__imp_CoTaskMemFree
0x1800866ad  nop     dword ptr [rax+rax+00h]
0x1800866b2  nop
0x1800866b3  lea     rcx, [rsp+12A0h+var_1230]; this
0x1800866b8  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800866bd  nop
0x1800866be  lea     rcx, [rsp+12A0h+var_1238]; this
0x1800866c3  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x1800866c8  mov     eax, ebx
0x1800866ca  mov     rcx, [rbp+11A0h+var_30]
0x1800866d1  xor     rcx, rsp; StackCookie
0x1800866d4  call    __security_check_cookie
0x1800866d9  mov     rbx, [rsp+12A0h+arg_10]
0x1800866e1  add     rsp, 1280h
0x1800866e8  pop     r14
0x1800866ea  pop     r13
0x1800866ec  pop     rdi
0x1800866ed  pop     rsi
0x1800866ee  pop     rbp
0x1800866ef  retn
```
