# WFDSConMgr::CInitStackStateWork::StartMiracast(void)

- ea: `0x180056344`
- end: `0x18005677d`
- name: `?StartMiracast@CInitStackStateWork@WFDSConMgr@@IEAAXXZ`
- size: `1081`
- prototype: `void __fastcall(WFDSConMgr::CInitStackStateWork *__hidden this)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180056d70`

## callees

- `0x180002600`
- `0x180002ffc`
- `0x18000475c`
- `0x180004c7c`
- `0x1800059c0`
- `0x180006740`
- `0x180006780`
- `0x180006c60`
- `0x180008a10`
- `0x180010018`
- `0x18001d18c`
- `0x18002c714`
- `0x18002cd1c`
- `0x180039ec4`
- `0x180039fec`
- `0x18003a004`
- `0x18003a14c`
- `0x18003a198`
- `0x18003a684`
- `0x18003a6cc`
- `0x180042a9c`
- `0x1800430d4`
- `0x180053d40`
- `0x180053da8`
- `0x180053fd8`
- `0x180054050`
- `0x18005420c`
- `0x180054284`
- `0x1800542fc`
- `0x180056344`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180056440`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180056440`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800565c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800565c5`

## string_xrefs

- `0x1800566ec`: `Miracast token not acquired, bad state for connection complete`
- `0x180056705`: `WFDSConMgr::CRemoteDevice::TrySetMiracastResourceTokenActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WFDSConMgr::CInitStackStateWork::StartMiracast(void **this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax
  WFDSConMgr::CWFDSessionHandle *MiracastWFDHandle; // rax
  _QWORD *v5; // rax
  RTL_SRWLOCK *v6; // rbx
  char Ptr; // bl
  unsigned int v8; // esi
  _QWORD *v9; // rax
  WFDSConMgr::CWFDSessionHandle *v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  struct WFDSConMgr::CMiracastHelper *MiracastHelper; // rbx
  LPCRITICAL_SECTION v14; // r12
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  WFDSConMgr::CRemoteDevice *v17; // rcx
  struct WFDSConMgr::CMiracastHelper *v18; // rax
  struct WFDSConMgr::CMiracastHelper *v19; // rbx
  struct WFDSConMgr::CMiracastHelper *v20; // rbx
  struct WFDSConMgr::IConfigHelper *ConfigHelper; // r14
  struct WFDSConMgr::ISessionTelemetryManager *TelemetryManager; // rax
  __int64 v23; // r15
  struct WFDSConMgr::ISessionTelemetryManager *v24; // rax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  struct WFDSConMgr::CSessionStateMachine *StateMachine; // rax
  _QWORD *v30; // rax
  _QWORD *v31; // rax
  struct WFDSConMgr::CMiracastHelper *v32; // rax
  RTL_SRWLOCK *v33; // rbx
  PVOID v34; // rcx
  char v35[8]; // [rsp+40h] [rbp-C0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v37; // [rsp+58h] [rbp-A8h]
  PSRWLOCK SRWLock[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v39[256]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v40[256]; // [rsp+170h] [rbp+70h] BYREF

  v2 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
         lpCriticalSection,
         (__int64)this);
  WFDSConMgr::TryCatchTelemetry__lambda_87202338bfbc849d035474e0b5bc921e___(v2);
  WFDSConMgr::CRemoteDevice::GetImpersonationProvider(this[4]);
  if ( (unsigned int)WFDSConMgr::CRemoteDevice::GetDafProviderTypeForConnection(this[4]) == 1 )
  {
    memset_0(v40, 0, sizeof(v40));
    memset_0(v39, 0, sizeof(v39));
    v3 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
           lpCriticalSection,
           (__int64)this);
    WFDSConMgr::TryCatchTelemetry__lambda_7da16f445860925c641da08f9f049ae5___(v3);
    MiracastWFDHandle = WFDSConMgr::CRemoteDevice::GetMiracastWFDHandle((WFDSConMgr::CRemoteDevice *)this[4]);
    WFDSConMgr::CWFDSessionHandle::GetSessionEndpointPairs(
      MiracastWFDHandle,
      (struct _WFD_SESSION_ENDPOINT_PAIR *)v40,
      (struct _WFD_SESSION_ENDPOINT_PAIR *)v39);
    v5 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
           lpCriticalSection,
           (__int64)this);
    WFDSConMgr::TryCatchTelemetry__lambda_a14c32c6f5c5e2e057c2a2154e8a2cc3___(v5);
  }
  v6 = (RTL_SRWLOCK *)this[4];
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(
    (__int64)SRWLock,
    v6 + 6);
  Ptr = (char)v6[98].Ptr;
  if ( LOBYTE(SRWLock[1]) && SRWLock[0] )
    ReleaseSRWLockShared(SRWLock[0]);
  v8 = 3;
  if ( Ptr )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_5715219f333a32af0405bc0f43c43705_Traceguids, this);
    }
  }
  else if ( (unsigned int)WFDSConMgr::CRemoteDevice::GetDafProviderTypeForConnection(this[4]) == 1 )
  {
    v9 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
           lpCriticalSection,
           (__int64)this);
    WFDSConMgr::TryCatchTelemetry__lambda_f1bdde2aa1df9dd9bc864cce874a5a03___(v9);
    memset(SRWLock, 0, 12);
    v10 = WFDSConMgr::CRemoteDevice::GetMiracastWFDHandle((WFDSConMgr::CRemoteDevice *)this[4]);
    WFDSConMgr::CWFDSessionHandle::ConfigureFirewallForSession(
      v10,
      (const struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *)SRWLock);
    v11 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
            lpCriticalSection,
            (__int64)this);
    WFDSConMgr::TryCatchTelemetry__lambda_a14c32c6f5c5e2e057c2a2154e8a2cc3___(v11);
  }
  v12 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
          lpCriticalSection,
          (__int64)this);
  WFDSConMgr::TryCatchTelemetry__lambda_f852e96258be2a2f3a10a9bc08c7064a___(v12);
  *((_BYTE *)this + 96) = 0;
  MiracastHelper = WFDSConMgr::CRemoteDevice::GetMiracastHelper((WFDSConMgr::CRemoteDevice *)this[4]);
  (*(void (__fastcall **)(void *))(*(_QWORD *)this[4] + 40LL))(this[4]);
  v14 = lpCriticalSection[1];
  WFDSConMgr::CMiracastHelper::QueryMiracastDeviceArrival(MiracastHelper);
  v15 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
          lpCriticalSection,
          (__int64)this);
  WFDSConMgr::TryCatchTelemetry__lambda_a14c32c6f5c5e2e057c2a2154e8a2cc3___(v15);
  v16 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
          lpCriticalSection,
          (__int64)this);
  WFDSConMgr::TryCatchTelemetry__lambda_fd4245d1c10abeec18c27d2f31b96085___(v16);
  v17 = (WFDSConMgr::CRemoteDevice *)this[4];
  if ( (*((_BYTE *)v17 + 412) & 2) != 0 )
  {
    v18 = WFDSConMgr::CRemoteDevice::GetMiracastHelper(v17);
    v19 = v18;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids, v18, 1);
    }
    WFDSConMgr::CriticalSection::Lock((char *)v19 + 104, lpCriticalSection);
    *((_BYTE *)v19 + 288) = 1;
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
  }
  v35[0] = 0;
  v20 = WFDSConMgr::CRemoteDevice::GetMiracastHelper((WFDSConMgr::CRemoteDevice *)this[4]);
  ConfigHelper = WFDSConMgr::CRemoteDevice::GetConfigHelper((WFDSConMgr::CRemoteDevice *)this[4]);
  TelemetryManager = WFDSConMgr::CRemoteDevice::GetTelemetryManager((WFDSConMgr::CRemoteDevice *)this[4]);
  v23 = (*(__int64 (__fastcall **)(struct WFDSConMgr::ISessionTelemetryManager *))(*(_QWORD *)TelemetryManager + 344LL))(TelemetryManager);
  v24 = WFDSConMgr::CRemoteDevice::GetTelemetryManager((WFDSConMgr::CRemoteDevice *)this[4]);
  v25 = (*(__int64 (__fastcall **)(struct WFDSConMgr::ISessionTelemetryManager *))(*(_QWORD *)v24 + 352LL))(v24);
  if ( !v25 )
  {
LABEL_25:
    v8 = 0;
    goto LABEL_26;
  }
  v26 = v25 - 1;
  if ( v26 )
  {
    v27 = v26 - 1;
    if ( v27 )
    {
      v28 = v27 - 1;
      if ( v28 )
      {
        if ( v28 == 1 )
          goto LABEL_26;
        goto LABEL_25;
      }
    }
    v8 = 2;
  }
  else
  {
    v8 = 1;
  }
LABEL_26:
  StateMachine = WFDSConMgr::CRemoteDevice::GetStateMachine((WFDSConMgr::CRemoteDevice *)this[4]);
  WFDSConMgr::CMiracastHelper::StartMiracastDevice(
    v20,
    ((unsigned __int64)StateMachine + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)StateMachine >> 64),
    v8,
    v23,
    v14,
    ConfigHelper,
    v35);
  v30 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
          lpCriticalSection,
          (__int64)this);
  WFDSConMgr::TryCatchTelemetry__lambda_a14c32c6f5c5e2e057c2a2154e8a2cc3___(v30);
  v31 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
          lpCriticalSection,
          (__int64)this);
  WFDSConMgr::TryCatchTelemetry__lambda_3eab280324ea6edccb4f389fd5615c5f___(v31);
  v32 = WFDSConMgr::CRemoteDevice::GetMiracastHelper((WFDSConMgr::CRemoteDevice *)this[4]);
  std::wstring::operator=(this + 7, (char *)v32 + 224);
  v33 = (RTL_SRWLOCK *)this[4];
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(
    (__int64)SRWLock,
    v33 + 6);
  v34 = v33[117].Ptr;
  if ( !v34 )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CRemoteDevice::TrySetMiracastResourceTokenActive",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\remotedevice.cpp",
      29,
      L"Miracast token not acquired, bad state for connection complete",
      v33);
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)v34 + 8LL))(v34);
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(SRWLock);
  if ( v37 )
    std::_Ref_count_base::_Decref(v37);
}

```

## disassembly

```asm
0x180056344  mov     [rsp-8+arg_8], rbx
0x180056349  mov     [rsp-8+arg_10], rsi
0x18005634e  push    rbp
0x18005634f  push    rdi
0x180056350  push    r12
0x180056352  push    r14
0x180056354  push    r15
0x180056356  lea     rbp, [rsp-180h]
0x18005635e  sub     rsp, 280h
0x180056365  mov     rax, cs:__security_cookie
0x18005636c  xor     rax, rsp
0x18005636f  mov     [rbp+1A0h+var_30], rax
0x180056376  mov     rdi, rcx
0x180056379  mov     rdx, rcx
0x18005637c  lea     rcx, [rsp+2A0h+lpCriticalSection]
0x180056381  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180056386  mov     rcx, rax
0x180056389  call    WFDSConMgr__TryCatchTelemetry__lambda_87202338bfbc849d035474e0b5bc921e___
0x18005638e  lea     rdx, [rsp+2A0h+var_250]
0x180056393  mov     rcx, [rdi+20h]; void *
0x180056397  call    ?GetImpersonationProvider@CRemoteDevice@WFDSConMgr@@QEAA?AV?$shared_ptr@VIImpersonationProvider@WFDSConMgr@@@std@@XZ; WFDSConMgr::CRemoteDevice::GetImpersonationProvider(void)
0x18005639c  nop
0x18005639d  mov     rcx, [rdi+20h]
0x1800563a1  call    ?GetDafProviderTypeForConnection@CRemoteDevice@WFDSConMgr@@QEBA?AW4DafProvider@2@XZ; WFDSConMgr::CRemoteDevice::GetDafProviderTypeForConnection(void)
0x1800563a6  mov     r14d, 1
0x1800563ac  cmp     eax, r14d
0x1800563af  jnz     short loc_180056417
0x1800563b1  mov     ebx, 100h
0x1800563b6  mov     r8d, ebx; Size
0x1800563b9  xor     edx, edx; Val
0x1800563bb  lea     rcx, [rbp+1A0h+var_130]; void *
0x1800563bf  call    memset_0
0x1800563c4  mov     r8d, ebx; Size
0x1800563c7  xor     edx, edx; Val
0x1800563c9  lea     rcx, [rsp+2A0h+var_230]; void *
0x1800563ce  call    memset_0
0x1800563d3  mov     rdx, rdi
0x1800563d6  lea     rcx, [rsp+2A0h+lpCriticalSection]
0x1800563db  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800563e0  mov     rcx, rax
0x1800563e3  call    WFDSConMgr__TryCatchTelemetry__lambda_7da16f445860925c641da08f9f049ae5___
0x1800563e8  mov     rcx, [rdi+20h]; this
0x1800563ec  call    ?GetMiracastWFDHandle@CRemoteDevice@WFDSConMgr@@QEBAAEBVCWFDSessionHandle@2@XZ; WFDSConMgr::CRemoteDevice::GetMiracastWFDHandle(void)
0x1800563f1  lea     r8, [rsp+2A0h+var_230]; struct _WFD_SESSION_ENDPOINT_PAIR *
0x1800563f6  lea     rdx, [rbp+1A0h+var_130]; struct _WFD_SESSION_ENDPOINT_PAIR *
0x1800563fa  mov     rcx, rax; this
0x1800563fd  call    ?GetSessionEndpointPairs@CWFDSessionHandle@WFDSConMgr@@QEBAXAEAU_WFD_SESSION_ENDPOINT_PAIR@@0@Z; WFDSConMgr::CWFDSessionHandle::GetSessionEndpointPairs(_WFD_SESSION_ENDPOINT_PAIR &,_WFD_SESSION_ENDPOINT_PAIR &)
0x180056402  mov     rdx, rdi
0x180056405  lea     rcx, [rsp+2A0h+lpCriticalSection]
0x18005640a  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18005640f  mov     rcx, rax
0x180056412  call    WFDSConMgr__TryCatchTelemetry__lambda_a14c32c6f5c5e2e057c2a2154e8a2cc3___
0x180056417  mov     rbx, [rdi+20h]
0x18005641b  lea     rdx, [rbx+30h]
0x18005641f  lea     rcx, [rsp+2A0h+SRWLock]
0x180056424  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(WFDSConMgr::ReadersWriterLock &)
0x180056429  mov     bl, [rbx+310h]
0x18005642f  cmp     [rsp+2A0h+var_238], 0
0x180056434  jz      short loc_180056446
0x180056436  mov     rcx, [rsp+2A0h+SRWLock]; SRWLock
0x18005643b  test    rcx, rcx
0x18005643e  jz      short loc_180056446
0x180056440  call    cs:__imp_ReleaseSRWLockShared
0x180056446  lea     r15, WPP_GLOBAL_Control
0x18005644d  mov     esi, 3
0x180056452  test    bl, bl
0x180056454  jz      short loc_18005648A
0x180056456  mov     rcx, cs:WPP_GLOBAL_Control
0x18005645d  cmp     rcx, r15
0x180056460  jz      loc_1800564E9
0x180056466  cmp     [rcx+19h], sil
0x18005646a  jb      short loc_1800564E9
0x18005646c  test    [rcx+1Ch], r14b
0x180056470  jz      short loc_1800564E9
0x180056472  lea     edx, [rsi+17h]
0x180056475  mov     r9, rdi
0x180056478  lea     r8, WPP_5715219f333a32af0405bc0f43c43705_Traceguids
0x18005647f  mov     rcx, [rcx+10h]
0x180056483  call    WPP_SF_q
0x180056488  jmp     short loc_1800564E9
0x18005648a  mov     rcx, [rdi+20h]
0x18005648e  call    ?GetDafProviderTypeForConnection@CRemoteDevice@WFDSConMgr@@QEBA?AW4DafProvider@2@XZ; WFDSConMgr::CRemoteDevice::GetDafProviderTypeForConnection(void)
0x180056493  cmp     eax, r14d
0x180056496  jnz     short loc_1800564E9
0x180056498  mov     rdx, rdi
0x18005649b  lea     rcx, [rsp+2A0h+lpCriticalSection]
0x1800564a0  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800564a5  mov     rcx, rax
0x1800564a8  call    WFDSConMgr__TryCatchTelemetry__lambda_f1bdde2aa1df9dd9bc864cce874a5a03___
0x1800564ad  mov     [rsp+2A0h+SRWLock+4], 0
0x1800564b6  mov     dword ptr [rsp+2A0h+SRWLock], 0
0x1800564be  mov     rcx, [rdi+20h]; this
0x1800564c2  call    ?GetMiracastWFDHandle@CRemoteDevice@WFDSConMgr@@QEBAAEBVCWFDSessionHandle@2@XZ; WFDSConMgr::CRemoteDevice::GetMiracastWFDHandle(void)
0x1800564c7  lea     rdx, [rsp+2A0h+SRWLock]; struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *
0x1800564cc  mov     rcx, rax; this
0x1800564cf  call    ?ConfigureFirewallForSession@CWFDSessionHandle@WFDSConMgr@@QEBAXAEBU_WFD_FIREWALL_CONFIGURATION_PARAMETERS@@@Z; WFDSConMgr::CWFDSessionHandle::ConfigureFirewallForSession(_WFD_FIREWALL_CONFIGURATION_PARAMETERS const &)
0x1800564d4  mov     rdx, rdi
0x1800564d7  lea     rcx, [rsp+2A0h+lpCriticalSection]
0x1800564dc  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800564e1  mov     rcx, rax
0x1800564e4  call    WFDSConMgr__TryCatchTelemetry__lambda_a14c32c6f5c5e2e057c2a2154e8a2cc3___
0x1800564e9  mov     rdx, rdi
0x1800564ec  lea     rcx, [rsp+2A0h+lpCriticalSection]
0x1800564f1  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800564f6  mov     rcx, rax
0x1800564f9  call    WFDSConMgr__TryCatchTelemetry__lambda_f852e96258be2a2f3a10a9bc08c7064a___
0x1800564fe  xor     eax, eax
0x180056500  xchg    al, [rdi+60h]
0x180056503  mov     rcx, [rdi+20h]; this
0x180056507  call    ?GetMiracastHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVCMiracastHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetMiracastHelper(void)
0x18005650c  mov     rbx, rax
0x18005650f  mov     rcx, [rdi+20h]
0x180056513  mov     rdx, [rcx]
0x180056516  mov     rax, [rdx+28h]
0x18005651a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005651f  mov     r12, [rsp+2A0h+var_250]
0x180056524  mov     r8, r12
0x180056527  mov     rdx, rax
0x18005652a  mov     rcx, rbx; void *
0x18005652d  call    ?QueryMiracastDeviceArrival@CMiracastHelper@WFDSConMgr@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVIImpersonationProvider@2@@Z; WFDSConMgr::CMiracastHelper::QueryMiracastDeviceArrival(std::wstring const &,WFDSConMgr::IImpersonationProvider const &)
0x180056532  mov     rdx, rdi
0x180056535  lea     rcx, [rsp+2A0h+lpCriticalSection]
0x18005653a  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18005653f  mov     rcx, rax
0x180056542  call    WFDSConMgr__TryCatchTelemetry__lambda_a14c32c6f5c5e2e057c2a2154e8a2cc3___
0x180056547  mov     rdx, rdi
0x18005654a  lea     rcx, [rsp+2A0h+lpCriticalSection]
0x18005654f  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180056554  mov     rcx, rax
0x180056557  call    WFDSConMgr__TryCatchTelemetry__lambda_fd4245d1c10abeec18c27d2f31b96085___
0x18005655c  mov     rcx, [rdi+20h]; this
0x180056560  test    byte ptr [rcx+19Ch], 2
0x180056567  jz      short loc_1800565CB
0x180056569  call    ?GetMiracastHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVCMiracastHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetMiracastHelper(void)
0x18005656e  mov     rbx, rax
0x180056571  mov     rcx, cs:WPP_GLOBAL_Control
0x180056578  cmp     rcx, r15
0x18005657b  jz      short loc_1800565A6
0x18005657d  cmp     byte ptr [rcx+19h], 4
0x180056581  jb      short loc_1800565A6
0x180056583  test    [rcx+1Ch], r14b
0x180056587  jz      short loc_1800565A6
0x180056589  mov     edx, 19h
0x18005658e  mov     dword ptr [rsp+2A0h+var_280], r14d
0x180056593  mov     r9, rax
0x180056596  lea     r8, WPP_6cc5b45fc4293079b9a0068da4d853bc_Traceguids
0x18005659d  mov     rcx, [rcx+10h]
0x1800565a1  call    WPP_SF_qD
0x1800565a6  lea     rcx, [rbx+68h]
0x1800565aa  lea     rdx, [rsp+2A0h+lpCriticalSection]
0x1800565af  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x1800565b4  mov     [rbx+120h], r14b
0x1800565bb  mov     rcx, [rsp+2A0h+lpCriticalSection]; lpCriticalSection
0x1800565c0  test    rcx, rcx
0x1800565c3  jz      short loc_1800565CB
0x1800565c5  call    cs:__imp_LeaveCriticalSection
0x1800565cb  mov     [rsp+2A0h+var_260], 0
0x1800565d0  mov     rcx, [rdi+20h]; this
0x1800565d4  call    ?GetMiracastHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVCMiracastHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetMiracastHelper(void)
0x1800565d9  mov     rbx, rax
0x1800565dc  mov     rcx, [rdi+20h]; this
0x1800565e0  call    ?GetConfigHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVIConfigHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetConfigHelper(void)
0x1800565e5  mov     r14, rax
0x1800565e8  mov     rcx, [rdi+20h]; this
0x1800565ec  call    ?GetTelemetryManager@CRemoteDevice@WFDSConMgr@@QEAAAEAVISessionTelemetryManager@2@XZ; WFDSConMgr::CRemoteDevice::GetTelemetryManager(void)
0x1800565f1  mov     rdx, rax
0x1800565f4  mov     rcx, [rax]
0x1800565f7  mov     rax, [rcx+158h]
0x1800565fe  mov     rcx, rdx
0x180056601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056606  mov     r15, rax
0x180056609  mov     rcx, [rdi+20h]; this
0x18005660d  call    ?GetTelemetryManager@CRemoteDevice@WFDSConMgr@@QEAAAEAVISessionTelemetryManager@2@XZ; WFDSConMgr::CRemoteDevice::GetTelemetryManager(void)
0x180056612  mov     rdx, rax
0x180056615  mov     rcx, [rax]
0x180056618  mov     rax, [rcx+160h]
0x18005661f  mov     rcx, rdx
0x180056622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056627  test    eax, eax
0x180056629  jz      short loc_18005664B
0x18005662b  sub     eax, 1
0x18005662e  jz      loc_180056721
0x180056634  sub     eax, 1
0x180056637  jz      loc_180056717
0x18005663d  sub     eax, 1
0x180056640  jz      loc_180056717
0x180056646  cmp     eax, 1
0x180056649  jz      short loc_18005664D
0x18005664b  xor     esi, esi
0x18005664d  mov     rcx, [rdi+20h]; this
0x180056651  call    ?GetStateMachine@CRemoteDevice@WFDSConMgr@@QEAAAEAVCSessionStateMachine@2@XZ; WFDSConMgr::CRemoteDevice::GetStateMachine(void)
0x180056656  lea     rcx, [rax+8]
0x18005665a  neg     rax
0x18005665d  sbb     rdx, rdx
0x180056660  and     rdx, rcx
0x180056663  lea     rax, [rsp+2A0h+var_260]
0x180056668  mov     [rsp+2A0h+var_270], rax
0x18005666d  mov     [rsp+2A0h+var_278], r14
0x180056672  mov     [rsp+2A0h+var_280], r12
0x180056677  mov     r9, r15
0x18005667a  mov     r8d, esi
0x18005667d  mov     rcx, rbx
0x180056680  call    ?StartMiracastDevice@CMiracastHelper@WFDSConMgr@@QEAAXPEAVIMiracastDisplayListener@2@W4MIRACAST_CONNECTION_ORIGIN@@AEBU_GUID@@AEBVIImpersonationProvider@2@AEBVIConfigHelper@2@AEA_N@Z; WFDSConMgr::CMiracastHelper::StartMiracastDevice(WFDSConMgr::IMiracastDisplayListener *,MIRACAST_CONNECTION_ORIGIN,_GUID const &,WFDSConMgr::IImpersonationProvider const &,WFDSConMgr::IConfigHelper const &,bool &)
0x180056685  mov     rdx, rdi
0x180056688  lea     rcx, [rsp+2A0h+lpCriticalSection]
0x18005668d  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180056692  mov     rcx, rax
0x180056695  call    WFDSConMgr__TryCatchTelemetry__lambda_a14c32c6f5c5e2e057c2a2154e8a2cc3___
0x18005669a  mov     rdx, rdi
0x18005669d  lea     rcx, [rsp+2A0h+lpCriticalSection]
0x1800566a2  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800566a7  mov     rcx, rax
0x1800566aa  call    WFDSConMgr__TryCatchTelemetry__lambda_3eab280324ea6edccb4f389fd5615c5f___
0x1800566af  mov     rcx, [rdi+20h]; this
0x1800566b3  call    ?GetMiracastHelper@CRemoteDevice@WFDSConMgr@@QEAAAEAVCMiracastHelper@2@XZ; WFDSConMgr::CRemoteDevice::GetMiracastHelper(void)
0x1800566b8  lea     rdx, [rax+0E0h]
0x1800566bf  lea     rcx, [rdi+38h]
0x1800566c3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800566c8  mov     rbx, [rdi+20h]
0x1800566cc  lea     rdx, [rbx+30h]
0x1800566d0  lea     rcx, [rsp+2A0h+SRWLock]
0x1800566d5  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(WFDSConMgr::ReadersWriterLock &)
0x1800566da  nop
0x1800566db  mov     rcx, [rbx+3A8h]
0x1800566e2  test    rcx, rcx
0x1800566e5  jnz     short loc_18005672B
0x1800566e7  mov     [rsp+2A0h+var_278], rbx; void *
0x1800566ec  lea     rax, aMiracastTokenN; "Miracast token not acquired, bad state "...
0x1800566f3  mov     [rsp+2A0h+var_280], rax; unsigned __int16 *
0x1800566f8  mov     r9d, 21Dh; char
0x1800566fe  lea     r8, aOnecoreuapNetW_17; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180056705  lea     rdx, aWfdsconmgrCrem_21; "WFDSConMgr::CRemoteDevice::TrySetMiraca"...
0x18005670c  mov     ecx, 8007139Fh; char
0x180056711  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180056717  mov     esi, 2
0x18005671c  jmp     loc_18005664D
0x180056721  mov     esi, 1
0x180056726  jmp     loc_18005664D
0x18005672b  mov     rax, [rcx]
0x18005672e  mov     rax, [rax+8]
0x180056732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056737  nop
0x180056738  lea     rcx, [rsp+2A0h+SRWLock]
0x18005673d  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x180056742  nop
0x180056743  mov     rcx, [rsp+2A0h+var_248]; this
0x180056748  test    rcx, rcx
0x18005674b  jz      short loc_180056752
0x18005674d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180056752  mov     rcx, [rbp+1A0h+var_30]
0x180056759  xor     rcx, rsp; StackCookie
0x18005675c  call    __security_check_cookie
0x180056761  lea     r11, [rsp+2A0h+var_20]
0x180056769  mov     rbx, [r11+38h]
0x18005676d  mov     rsi, [r11+40h]
0x180056771  mov     rsp, r11
0x180056774  pop     r15
0x180056776  pop     r14
0x180056778  pop     r12
0x18005677a  pop     rdi
0x18005677b  pop     rbp
0x18005677c  retn
```
