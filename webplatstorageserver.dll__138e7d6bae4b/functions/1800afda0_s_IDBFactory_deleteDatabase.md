# s_IDBFactory_deleteDatabase

- ea: `0x1800afda0`
- end: `0x1800b01fd`
- name: `s_IDBFactory_deleteDatabase`
- size: `1117`
- prototype: `__int64 __usercall@<rax>(struct _RPC_ASYNC_STATE *@<rcx>, struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 *)`
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x18000e1c0`
- `0x18001c800`
- `0x1800273f0`
- `0x180029a64`
- `0x180029e74`
- `0x18002e8f4`
- `0x18002ee6c`
- `0x180037d40`
- `0x18003cd20`
- `0x180050e84`
- `0x180052364`
- `0x18005a058`
- `0x18005a254`
- `0x18005bb90`
- `0x18005c28c`
- `0x180080fb0`
- `0x1800814bc`
- `0x1800a785c`
- `0x1800a7e74`
- `0x1800afda0`
- `0x1800b0bcc`
- `0x1800b26e4`
- `0x1800b2710`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800afeab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b00e4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800afeab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b00e4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800afe78`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800afe78`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800b00cb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800b00cb`

## string_xrefs

- `0x1800afe09`: `IDB_IDBFactory_deleteDatabase`
- `0x1800afdfc`: `RPC IDBFact_deleteDatabase`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
int __fastcall s_IDBFactory_deleteDatabase(
        struct _RPC_ASYNC_STATE *a1,
        void *a2,
        CIndexedDBServerFactoryWithSecurityContext **a3,
        const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *a4,
        struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 *a5)
{
  const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *v5; // r14
  CIndexedDBServerFactoryWithSecurityContext **v6; // r15
  struct _RPC_ASYNC_STATE *v7; // r12
  unsigned int v8; // esi
  LONGLONG v9; // rbx
  int ClientContextFlags; // r13d
  void *v11; // r12
  int v12; // eax
  __int64 v13; // rcx
  __int64 Instance; // rax
  __int64 v15; // rsi
  __int64 PackageName; // r8
  _QWORD *v17; // rax
  void (__fastcall ***v18)(_QWORD, _QWORD); // rsi
  __int64 v19; // r8
  const char *v20; // r9
  RPC_STATUS v21; // r14d
  const struct _tlgProvider_t *v22; // rax
  wil *v24; // rcx
  int Reply; // [rsp+30h] [rbp-2B8h] BYREF
  unsigned int v26; // [rsp+34h] [rbp-2B4h] BYREF
  int v27; // [rsp+38h] [rbp-2B0h] BYREF
  void *v28; // [rsp+40h] [rbp-2A8h] BYREF
  void (__fastcall *v29)(__int64, void **, __int64); // [rsp+48h] [rbp-2A0h] BYREF
  void *v30; // [rsp+50h] [rbp-298h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp-290h] BYREF
  struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 *v32; // [rsp+60h] [rbp-288h]
  const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *v33; // [rsp+68h] [rbp-280h] BYREF
  void (__fastcall ***v34)(_QWORD, void (__fastcall **)(__int64, void **, __int64)); // [rsp+70h] [rbp-278h] BYREF
  struct CRpcCallAbortedNotificationHelper *v35; // [rsp+78h] [rbp-270h] BYREF
  struct _RPC_ASYNC_STATE *v36; // [rsp+80h] [rbp-268h]
  LARGE_INTEGER v37; // [rsp+88h] [rbp-260h] BYREF
  LARGE_INTEGER Frequency; // [rsp+90h] [rbp-258h] BYREF
  void (__fastcall *v39)(_QWORD, void (__fastcall **)(__int64, void **, __int64)); // [rsp+98h] [rbp-250h]
  LONGLONG v40; // [rsp+A0h] [rbp-248h]
  struct _RPC_ASYNC_STATE *v41; // [rsp+A8h] [rbp-240h]
  CIndexedDBServerFactoryWithSecurityContext **v42; // [rsp+B0h] [rbp-238h]
  struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 *v43; // [rsp+B8h] [rbp-230h] BYREF
  std::_Ref_count_base *v44; // [rsp+C0h] [rbp-228h]
  _OWORD v45[2]; // [rsp+D0h] [rbp-218h] BYREF
  _QWORD v46[42]; // [rsp+F0h] [rbp-1F8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+240h] [rbp-A8h] BYREF
  void **v48; // [rsp+260h] [rbp-88h]
  __int64 v49; // [rsp+268h] [rbp-80h]
  unsigned int *v50; // [rsp+270h] [rbp-78h]
  __int64 v51; // [rsp+278h] [rbp-70h]
  int *v52; // [rsp+280h] [rbp-68h]
  __int64 v53; // [rsp+288h] [rbp-60h]
  const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 **v54; // [rsp+290h] [rbp-58h]
  __int64 v55; // [rsp+298h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v5 = a4;
  v6 = a3;
  v30 = a2;
  v7 = a1;
  v36 = a1;
  v41 = a1;
  v42 = a3;
  v33 = a4;
  v32 = a5;
  SetThreadName((WCHAR *)L"RPC IDBFact_deleteDatabase");
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v46,
    "IDB_IDBFactory_deleteDatabase");
  v46[0] = &IndexedDbTraceLogging::IDB_IDBFactory_deleteDatabase::`vftable';
  IndexedDbTraceLogging::IDB_IDBFactory_deleteDatabase::StartActivity(
    (IndexedDbTraceLogging::IDB_IDBFactory_deleteDatabase *)v46,
    v6,
    v5,
    a5);
  Reply = -2147024809;
  v8 = 0;
  v26 = 0;
  PerformanceCount.QuadPart = 0;
  v37.QuadPart = 0;
  v9 = 0;
  v40 = 0;
  Frequency.QuadPart = 0;
  QueryPerformanceFrequency(&Frequency);
  if ( v6 )
  {
    v28 = 0;
    v35 = 0;
    ClientContextFlags = CIndexedDBServerFactoryWithSecurityContext::GetClientContextFlags(v6[2], &v26);
    v27 = ClientContextFlags;
    QueryPerformanceCounter(&PerformanceCount);
    Reply = CRpcCallAbortedNotification::StartListening(&v35, v7, v30, &v28);
    if ( Reply < 0 )
      goto LABEL_15;
    v11 = v28;
    v12 = IndexedDbFactorySession::DeleteDatabase((IndexedDbFactorySession *)v6, v5, v28, 1);
    Reply = v12;
    if ( v12 == -2140082173 )
    {
      Instance = WebPlatStorageClientManager::GetInstance(v13);
      try
      {
        v15 = *(_QWORD *)Instance;
        v29 = *(void (__fastcall **)(__int64, void **, __int64))(**(_QWORD **)Instance + 8LL);
        PackageName = ClientIdentity::s_GetPackageName((__int64)v45);
        v29(v15, &v30, PackageName);
        std::wstring::~wstring(v45);
        v17 = (_QWORD *)(**(__int64 (__fastcall ***)(void *, struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 **))v30)(
                          v30,
                          &v43);
        (*(void (__fastcall **)(_QWORD, void (__fastcall ****)(_QWORD, void (__fastcall **)(__int64, void **, __int64)), struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 *))(*(_QWORD *)*v17 + 72LL))(
          *v17,
          &v34,
          v32);
        if ( v44 )
          std::_Ref_count_base::_Decref(v44);
        v18 = (void (__fastcall ***)(_QWORD, _QWORD))v34;
        v39 = **v34;
        v32 = (struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 *)operator new(0x38u);
        v43 = v32;
        gsl::span<unsigned short const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(
          v45,
          *((_QWORD *)v5 + 1),
          *(unsigned int *)v5);
        v29 = (void (__fastcall *)(__int64, void **, __int64))IndexedDbBlockedEvent::IndexedDbBlockedEvent(
                                                                v32,
                                                                v45,
                                                                v19,
                                                                -1);
        v39(v18, &v29);
        std::unique_ptr<IEventSubchannel>::~unique_ptr<IEventSubchannel>(&v29);
        Reply = 0;
        std::unique_ptr<IEventSubchannel>::~unique_ptr<IEventSubchannel>(&v34);
        if ( v30 )
          std::default_delete<IWebPlatStorageClientReference>::operator()();
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x1E1,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\server\\rpcapi.cxx",
          v20);
        Reply = wil::ResultFromCaughtException(v24);
        v9 = v40;
        v11 = v28;
        ClientContextFlags = v27;
        v36 = v41;
        v6 = v42;
        v5 = v33;
      }
      v12 = Reply;
      if ( Reply < 0 )
      {
LABEL_13:
        if ( ClientContextFlags >= 0 )
        {
          v8 = v26;
          CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(v26, v12, 0);
LABEL_16:
          CRpcCallAbortedNotification::StopListening((CRpcCallAbortedNotification *)&v35);
          v7 = v36;
          goto LABEL_17;
        }
LABEL_15:
        v8 = v26;
        goto LABEL_16;
      }
      v12 = IndexedDbFactorySession::DeleteDatabase((IndexedDbFactorySession *)v6, v5, v11, 0);
      Reply = v12;
    }
    if ( v12 >= 0 )
      goto LABEL_15;
    goto LABEL_13;
  }
LABEL_17:
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v46, (unsigned int)Reply);
  v21 = RpcAsyncCompleteCall(v7, &Reply);
  if ( PerformanceCount.QuadPart > 0 )
  {
    QueryPerformanceCounter(&v37);
    v9 = 1000000 * (v37.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart;
  }
  v22 = StorageServerProvider::Provider();
  if ( *(_DWORD *)v22 > 5u )
  {
    v33 = (const struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *)v9;
    v27 = v8;
    v26 = v21;
    LODWORD(v28) = Reply;
    v54 = &v33;
    v55 = 8;
    v52 = &v27;
    v53 = 4;
    v50 = &v26;
    v51 = 4;
    v48 = &v28;
    v49 = 4;
    tlgWriteTransfer_EventWriteTransfer((int)v22, (int)&word_1800F253E, 0, 0, 6u, &v47);
  }
  IndexedDbTraceLogging::IDB_IDBFactory_deleteDatabase::~IDB_IDBFactory_deleteDatabase((IndexedDbTraceLogging::IDB_IDBFactory_deleteDatabase *)v46);
  return SetThreadName((WCHAR *)&word_1800D6108);
}

```

## disassembly

```asm
0x1800afda0  push    rbx
0x1800afda2  push    rsi
0x1800afda3  push    r12
0x1800afda5  push    r13
0x1800afda7  push    r14
0x1800afda9  push    r15
0x1800afdab  sub     rsp, 2B8h
0x1800afdb2  mov     rax, cs:__security_cookie
0x1800afdb9  xor     rax, rsp
0x1800afdbc  mov     [rsp+2E8h+var_40], rax
0x1800afdc4  mov     r14, r9
0x1800afdc7  mov     r15, r8
0x1800afdca  mov     [rsp+2E8h+var_298], rdx
0x1800afdcf  mov     r12, rcx
0x1800afdd2  mov     [rsp+2E8h+var_268], rcx
0x1800afdda  mov     [rsp+2E8h+var_240], rcx
0x1800afde2  mov     [rsp+2E8h+var_238], r8
0x1800afdea  mov     [rsp+2E8h+var_280], r9
0x1800afdef  mov     rbx, [rsp+2E8h+arg_20]
0x1800afdf7  mov     [rsp+2E8h+var_288], rbx
0x1800afdfc  lea     rcx, aRpcIdbfactDele; "RPC IDBFact_deleteDatabase"
0x1800afe03  call    SetThreadName
0x1800afe08  nop
0x1800afe09  lea     rdx, aIdbIdbfactoryD; "IDB_IDBFactory_deleteDatabase"
0x1800afe10  lea     rcx, [rsp+2E8h+var_1F8]
0x1800afe18  call    ??0?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800afe1d  lea     rax, ??_7IDB_IDBFactory_deleteDatabase@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBFactory_deleteDatabase::`vftable'
0x1800afe24  mov     [rsp+2E8h+var_1F8], rax
0x1800afe2c  mov     r9, rbx; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 *
0x1800afe2f  mov     r8, r14; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *
0x1800afe32  mov     rdx, r15; void *
0x1800afe35  lea     rcx, [rsp+2E8h+var_1F8]; this
0x1800afe3d  call    ?StartActivity@IDB_IDBFactory_deleteDatabase@IndexedDbTraceLogging@@QEAAXPEAXAEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@AEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003@@@Z; IndexedDbTraceLogging::IDB_IDBFactory_deleteDatabase::StartActivity(void *,__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const &,__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 const &)
0x1800afe42  nop
0x1800afe43  mov     [rsp+2E8h+Reply], 80070057h
0x1800afe4b  xor     esi, esi
0x1800afe4d  mov     [rsp+2E8h+var_2B4], esi
0x1800afe51  mov     qword ptr [rsp+2E8h+PerformanceCount], rsi
0x1800afe56  mov     qword ptr [rsp+2E8h+var_260], rsi
0x1800afe5e  xor     ebx, ebx
0x1800afe60  mov     [rsp+2E8h+var_248], rbx
0x1800afe68  mov     qword ptr [rsp+2E8h+Frequency], rbx
0x1800afe70  lea     rcx, [rsp+2E8h+Frequency]; lpFrequency
0x1800afe78  call    cs:__imp_QueryPerformanceFrequency
0x1800afe7e  test    r15, r15
0x1800afe81  jz      loc_1800B00B2
0x1800afe87  mov     [rsp+2E8h+var_2A8], rbx
0x1800afe8c  mov     [rsp+2E8h+var_270], rbx
0x1800afe91  lea     rdx, [rsp+2E8h+var_2B4]; unsigned int *
0x1800afe96  mov     rcx, [r15+10h]; this
0x1800afe9a  call    ?GetClientContextFlags@CIndexedDBServerFactoryWithSecurityContext@@QEAAJPEAK@Z; CIndexedDBServerFactoryWithSecurityContext::GetClientContextFlags(ulong *)
0x1800afe9f  mov     r13d, eax
0x1800afea2  mov     [rsp+2E8h+var_2B0], eax
0x1800afea6  lea     rcx, [rsp+2E8h+PerformanceCount]; lpPerformanceCount
0x1800afeab  call    cs:__imp_QueryPerformanceCounter
0x1800afeb1  lea     r9, [rsp+2E8h+var_2A8]; void **
0x1800afeb6  mov     r8, [rsp+2E8h+var_298]; void *
0x1800afebb  mov     rdx, r12; struct _RPC_ASYNC_STATE *
0x1800afebe  lea     rcx, [rsp+2E8h+var_270]; this
0x1800afec3  call    ?StartListening@CRpcCallAbortedNotification@@QEAAJPEAU_RPC_ASYNC_STATE@@PEAXPEAPEAX@Z; CRpcCallAbortedNotification::StartListening(_RPC_ASYNC_STATE *,void *,void * *)
0x1800afec8  mov     [rsp+2E8h+Reply], eax
0x1800afecc  test    eax, eax
0x1800afece  js      loc_1800B009C
0x1800afed4  mov     r9b, 1; bool
0x1800afed7  mov     r12, [rsp+2E8h+var_2A8]
0x1800afedc  mov     r8, r12; void *
0x1800afedf  mov     rdx, r14; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *
0x1800afee2  mov     rcx, r15; this
0x1800afee5  call    ?DeleteDatabase@IndexedDbFactorySession@@QEAAJAEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@PEAX_N@Z; IndexedDbFactorySession::DeleteDatabase(__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const &,void *,bool)
0x1800afeea  mov     [rsp+2E8h+Reply], eax
0x1800afeee  cmp     eax, 8070F003h
0x1800afef3  jnz     loc_1800B007F
0x1800afef9  call    ?GetInstance@WebPlatStorageClientManager@@SAAEAV?$unique_ptr@VWebPlatStorageClientManager@@U?$default_delete@VWebPlatStorageClientManager@@@std@@@std@@XZ; WebPlatStorageClientManager::GetInstance(void)
0x1800afefe  mov     rsi, [rax]
0x1800aff01  mov     rax, [rsi]
0x1800aff04  mov     rax, [rax+8]
0x1800aff08  mov     [rsp+2E8h+var_2A0], rax
0x1800aff0d  lea     rcx, [rsp+2E8h+var_218]
0x1800aff15  call    ?s_GetPackageName@ClientIdentity@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ClientIdentity::s_GetPackageName(void)
0x1800aff1a  nop
0x1800aff1b  mov     r8, rax
0x1800aff1e  lea     rdx, [rsp+2E8h+var_298]
0x1800aff23  mov     rcx, rsi
0x1800aff26  mov     rax, [rsp+2E8h+var_2A0]
0x1800aff2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff30  nop
0x1800aff31  lea     rcx, [rsp+2E8h+var_218]; void *
0x1800aff39  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800aff3e  mov     rcx, [rsp+2E8h+var_298]
0x1800aff43  mov     rax, [rcx]
0x1800aff46  lea     rdx, [rsp+2E8h+var_230]
0x1800aff4e  mov     rax, [rax]
0x1800aff51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff56  nop
0x1800aff57  mov     rcx, [rax]
0x1800aff5a  mov     rax, [rcx]
0x1800aff5d  mov     r8, [rsp+2E8h+var_288]
0x1800aff62  lea     rdx, [rsp+2E8h+var_278]
0x1800aff67  mov     rax, [rax+48h]
0x1800aff6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aff70  nop
0x1800aff71  mov     rcx, [rsp+2E8h+var_228]; this
0x1800aff79  test    rcx, rcx
0x1800aff7c  jz      short loc_1800AFF83
0x1800aff7e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800aff83  mov     rsi, [rsp+2E8h+var_278]
0x1800aff88  mov     rax, [rsi]
0x1800aff8b  mov     rax, [rax]
0x1800aff8e  mov     [rsp+2E8h+var_250], rax
0x1800aff96  mov     ecx, 38h ; '8'; Size
0x1800aff9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800affa0  mov     [rsp+2E8h+var_288], rax
0x1800affa5  mov     [rsp+2E8h+var_230], rax
0x1800affad  mov     r8d, [r14]
0x1800affb0  mov     rdx, [r14+8]
0x1800affb4  lea     rcx, [rsp+2E8h+var_218]
0x1800affbc  call    ??$?0_K@?$storage_type@V?$extent_type@$0?0@details@gsl@@@?$span@$$CBG$0?0@gsl@@QEAA@PEBG_K@Z; gsl::span<ushort const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(ushort const *,unsigned __int64)
0x1800affc1  movaps  xmm0, [rsp+2E8h+var_218]
0x1800affc9  movdqa  [rsp+2E8h+var_218], xmm0
0x1800affd2  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800affd6  lea     rdx, [rsp+2E8h+var_218]
0x1800affde  mov     rcx, [rsp+2E8h+var_288]
0x1800affe3  call    ??0IndexedDbBlockedEvent@@QEAA@V?$basic_string_span@$$CBG$0?0@gsl@@_J1@Z; IndexedDbBlockedEvent::IndexedDbBlockedEvent(gsl::basic_string_span<ushort const,-1>,__int64,__int64)
0x1800affe8  nop
0x1800affe9  mov     [rsp+2E8h+var_2A0], rax
0x1800affee  lea     rdx, [rsp+2E8h+var_2A0]
0x1800afff3  mov     rcx, rsi
0x1800afff6  mov     rax, [rsp+2E8h+var_250]
0x1800afffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0003  nop
0x1800b0004  lea     rcx, [rsp+2E8h+var_2A0]
0x1800b0009  call    ??1?$unique_ptr@UIEventSubchannel@@U?$default_delete@UIEventSubchannel@@@std@@@std@@QEAA@XZ; std::unique_ptr<IEventSubchannel>::~unique_ptr<IEventSubchannel>(void)
0x1800b000e  mov     [rsp+2E8h+Reply], 0
0x1800b0016  lea     rcx, [rsp+2E8h+var_278]
0x1800b001b  call    ??1?$unique_ptr@UIEventSubchannel@@U?$default_delete@UIEventSubchannel@@@std@@@std@@QEAA@XZ; std::unique_ptr<IEventSubchannel>::~unique_ptr<IEventSubchannel>(void)
0x1800b0020  nop
0x1800b0021  mov     rdx, [rsp+2E8h+var_298]
0x1800b0026  test    rdx, rdx
0x1800b0029  jz      short loc_1800B0031
0x1800b002b  call    ??R?$default_delete@UIWebPlatStorageClientReference@@@std@@QEBAXPEAUIWebPlatStorageClientReference@@@Z; std::default_delete<IWebPlatStorageClientReference>::operator()(IWebPlatStorageClientReference *)
0x1800b0030  nop
0x1800b0031  jmp     short loc_1800B0062
0x1800b0033  mov     rbx, [rsp+2E8h+var_248]
0x1800b003b  mov     r12, [rsp+2E8h+var_2A8]
0x1800b0040  mov     r13d, [rsp+2E8h+var_2B0]
0x1800b0045  mov     rax, [rsp+2E8h+var_240]
0x1800b004d  mov     [rsp+2E8h+var_268], rax
0x1800b0055  mov     r15, [rsp+2E8h+var_238]
0x1800b005d  mov     r14, [rsp+2E8h+var_280]
0x1800b0062  mov     eax, [rsp+2E8h+Reply]
0x1800b0066  test    eax, eax
0x1800b0068  js      short loc_1800B0085
0x1800b006a  xor     r9d, r9d; bool
0x1800b006d  mov     r8, r12; void *
0x1800b0070  mov     rdx, r14; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *
0x1800b0073  mov     rcx, r15; this
0x1800b0076  call    ?DeleteDatabase@IndexedDbFactorySession@@QEAAJAEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@PEAX_N@Z; IndexedDbFactorySession::DeleteDatabase(__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const &,void *,bool)
0x1800b007b  mov     [rsp+2E8h+Reply], eax
0x1800b007f  mov     ecx, eax
0x1800b0081  test    eax, eax
0x1800b0083  jns     short loc_1800B009C
0x1800b0085  test    r13d, r13d
0x1800b0088  js      short loc_1800B009C
0x1800b008a  xor     r8d, r8d; struct CWxString *
0x1800b008d  mov     edx, eax; int
0x1800b008f  mov     esi, [rsp+2E8h+var_2B4]
0x1800b0093  mov     ecx, esi; unsigned int
0x1800b0095  call    ?HandleCorruptionIfDetected@CIndexedDBServerPhysicalDBManager@@SAXKJPEAVCWxString@@@Z; CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(ulong,long,CWxString *)
0x1800b009a  jmp     short loc_1800B00A0
0x1800b009c  mov     esi, [rsp+2E8h+var_2B4]
0x1800b00a0  lea     rcx, [rsp+2E8h+var_270]; this
0x1800b00a5  call    ?StopListening@CRpcCallAbortedNotification@@AEAAXXZ; CRpcCallAbortedNotification::StopListening(void)
0x1800b00aa  mov     r12, [rsp+2E8h+var_268]
0x1800b00b2  mov     edx, [rsp+2E8h+Reply]
0x1800b00b6  lea     rcx, [rsp+2E8h+var_1F8]
0x1800b00be  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800b00c3  lea     rdx, [rsp+2E8h+Reply]; Reply
0x1800b00c8  mov     rcx, r12; pAsync
0x1800b00cb  call    cs:__imp_RpcAsyncCompleteCall
0x1800b00d1  mov     r14d, eax
0x1800b00d4  cmp     qword ptr [rsp+2E8h+PerformanceCount], 0
0x1800b00da  jle     short loc_1800B010B
0x1800b00dc  lea     rcx, [rsp+2E8h+var_260]; lpPerformanceCount
0x1800b00e4  call    cs:__imp_QueryPerformanceCounter
0x1800b00ea  mov     rax, qword ptr [rsp+2E8h+var_260]
0x1800b00f2  sub     rax, qword ptr [rsp+2E8h+PerformanceCount]
0x1800b00f7  imul    rax, 0F4240h
0x1800b00fe  cqo
0x1800b0100  idiv    qword ptr [rsp+2E8h+Frequency]
0x1800b0108  mov     rbx, rax
0x1800b010b  call    ?Provider@StorageServerProvider@@SAPEBU_tlgProvider_t@@XZ; StorageServerProvider::Provider(void)
0x1800b0110  mov     ecx, [rax]
0x1800b0112  cmp     ecx, 5
0x1800b0115  jbe     loc_1800B01C0
0x1800b011b  mov     [rsp+2E8h+var_280], rbx
0x1800b0120  mov     [rsp+2E8h+var_2B0], esi
0x1800b0124  mov     [rsp+2E8h+var_2B4], r14d
0x1800b0129  mov     ecx, [rsp+2E8h+Reply]
0x1800b012d  mov     dword ptr [rsp+2E8h+var_2A8], ecx
0x1800b0131  lea     rcx, [rsp+2E8h+var_280]
0x1800b0136  mov     [rsp+2E8h+var_58], rcx
0x1800b013e  mov     [rsp+2E8h+var_50], 8
0x1800b014a  lea     rcx, [rsp+2E8h+var_2B0]
0x1800b014f  mov     [rsp+2E8h+var_68], rcx
0x1800b0157  mov     [rsp+2E8h+var_60], 4
0x1800b0163  lea     rcx, [rsp+2E8h+var_2B4]
0x1800b0168  mov     [rsp+2E8h+var_78], rcx
0x1800b0170  mov     [rsp+2E8h+var_70], 4
0x1800b017c  lea     rcx, [rsp+2E8h+var_2A8]
0x1800b0181  mov     [rsp+2E8h+var_88], rcx
0x1800b0189  mov     [rsp+2E8h+var_80], 4
0x1800b0195  lea     rcx, [rsp+2E8h+var_A8]
0x1800b019d  mov     [rsp+2E8h+var_2C0], rcx; PEVENT_DATA_DESCRIPTOR
0x1800b01a2  mov     [rsp+2E8h+var_2C8], 6; ULONG
0x1800b01aa  xor     r9d, r9d; int
0x1800b01ad  xor     r8d, r8d; int
0x1800b01b0  lea     rdx, word_1800F253E; int
0x1800b01b7  mov     rcx, rax; int
0x1800b01ba  call    _tlgWriteTransfer_EventWriteTransfer
0x1800b01bf  nop
0x1800b01c0  lea     rcx, [rsp+2E8h+var_1F8]; this
0x1800b01c8  call    ??1IDB_IDBFactory_deleteDatabase@IndexedDbTraceLogging@@QEAA@XZ; IndexedDbTraceLogging::IDB_IDBFactory_deleteDatabase::~IDB_IDBFactory_deleteDatabase(void)
0x1800b01cd  nop
0x1800b01ce  lea     rcx, word_1800D6108; lpWideCharStr
0x1800b01d5  call    SetThreadName
0x1800b01da  nop
0x1800b01db  mov     rcx, [rsp+2E8h+var_40]
0x1800b01e3  xor     rcx, rsp; StackCookie
0x1800b01e6  call    __security_check_cookie
0x1800b01eb  add     rsp, 2B8h
0x1800b01f2  pop     r15
0x1800b01f4  pop     r14
0x1800b01f6  pop     r13
0x1800b01f8  pop     r12
0x1800b01fa  pop     rsi
0x1800b01fb  pop     rbx
0x1800b01fc  retn
```
