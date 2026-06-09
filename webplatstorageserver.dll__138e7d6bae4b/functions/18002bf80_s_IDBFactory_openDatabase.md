# s_IDBFactory_openDatabase

- ea: `0x18002bf80`
- end: `0x18002c99f`
- name: `s_IDBFactory_openDatabase`
- size: `2591`
- prototype: `__int64 __fastcall(struct _RPC_ASYNC_STATE *, void *, void *, struct CIndexedDBServerTransaction *, __int64, struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 *, void **, void **, struct __MIDL_RPCIndexedDB_0008 *)`
- caller_count: `0`
- callee_count: `40`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800086cc`
- `0x18000a8f4`
- `0x18000e1c0`
- `0x18001c800`
- `0x1800247ac`
- `0x1800273f0`
- `0x180028b6c`
- `0x180029e74`
- `0x18002b480`
- `0x18002bf80`
- `0x18002c9b0`
- `0x18002c9e0`
- `0x18002ca90`
- `0x18002cbac`
- `0x18002e340`
- `0x18002ee6c`
- `0x18003cd20`
- `0x18004552c`
- `0x1800456b8`
- `0x1800457c0`
- `0x180045c4c`
- `0x180045f5c`
- `0x180046014`
- `0x1800466ac`
- `0x180050e40`
- `0x180055594`
- `0x18005a058`
- `0x18005a254`
- `0x18005bb90`
- `0x18005c28c`
- `0x180080fb0`
- `0x1800814bc`
- `0x180081b40`
- `0x1800afac0`
- `0x1800afc40`
- `0x1800b0bcc`
- `0x1800b2710`
- `0x1800b29d0`
- `0x1800b2a40`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c445`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c445`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c477`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c477`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c238`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c255`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c238`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c5af`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002c160`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002c160`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18002c61e`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18002c61e`

## string_xrefs

- `0x18002c038`: `IDB_IDBFactory_openDatabase`
- `0x18002c00f`: `RPC IDBFact_openDatabase`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall s_IDBFactory_openDatabase(
        struct _RPC_ASYNC_STATE *a1,
        void *a2,
        void *a3,
        struct CIndexedDBServerTransaction *a4,
        __int64 a5,
        struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 *a6,
        void **a7,
        void **a8,
        struct __MIDL_RPCIndexedDB_0008 *a9)
{
  void **v11; // r15
  void **v12; // r12
  struct __MIDL_RPCIndexedDB_0008 *v13; // r13
  char *v15; // rsi
  HANDLE EventW; // rax
  HANDLE v17; // rax
  __int64 v18; // rcx
  signed int v19; // edi
  _UNKNOWN **i; // rcx
  char v21; // r14
  __int64 v22; // r12
  volatile signed __int32 *v23; // rdi
  CIndexedDBServerOpenRequestQueueEntry *v24; // r14
  int v25; // r15d
  __int64 v26; // rax
  _QWORD *v27; // r12
  void *v28; // rax
  __int64 v29; // rcx
  int v30; // r15d
  CIndexedDBServerTransaction *v31; // r15
  signed int LastError; // eax
  RPC_STATUS v33; // eax
  __int64 Instance; // rax
  __int64 v35; // r15
  void (__fastcall *v36)(__int64, unsigned int *, __int64); // r12
  __int64 PackageName; // rax
  _QWORD *v38; // rax
  void *v39; // r15
  RTL_SRWLOCK *v40; // r12
  __int64 v41; // r8
  const char *v42; // r9
  int v43; // r9d
  int v44; // r15d
  struct CIndexedDBServerTransaction **v45; // r12
  struct CIndexedDBServerDatabaseClientConnection **v46; // r15
  wil *v47; // rcx
  int Reply; // [rsp+50h] [rbp-278h] BYREF
  bool v49; // [rsp+54h] [rbp-274h]
  unsigned int v50[2]; // [rsp+58h] [rbp-270h] BYREF
  void **v51; // [rsp+60h] [rbp-268h]
  PSRWLOCK SRWLock; // [rsp+68h] [rbp-260h] BYREF
  CIndexedDBServerTransaction *v53; // [rsp+70h] [rbp-258h] BYREF
  void **v54; // [rsp+78h] [rbp-250h]
  void *v55; // [rsp+80h] [rbp-248h] BYREF
  struct CIndexedDBServerDatabaseClientConnection *v56; // [rsp+88h] [rbp-240h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+90h] [rbp-238h] BYREF
  struct CIndexedDBServerTransaction *v58; // [rsp+98h] [rbp-230h] BYREF
  volatile signed __int32 *v59; // [rsp+A0h] [rbp-228h] BYREF
  PSRWLOCK v60; // [rsp+A8h] [rbp-220h] BYREF
  std::_Ref_count_base *v61; // [rsp+B0h] [rbp-218h]
  void *v62; // [rsp+B8h] [rbp-210h]
  PRPC_ASYNC_STATE pAsync; // [rsp+C0h] [rbp-208h]
  struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 *v64; // [rsp+C8h] [rbp-200h]
  char *v65; // [rsp+D0h] [rbp-1F8h]
  struct _RPC_ASYNC_STATE *v66; // [rsp+D8h] [rbp-1F0h]
  struct __MIDL_RPCIndexedDB_0008 *v67; // [rsp+E0h] [rbp-1E8h]
  RPC_ASYNC_NOTIFICATION_INFO NotificationInfo; // [rsp+E8h] [rbp-1E0h] BYREF
  _QWORD v69[4]; // [rsp+110h] [rbp-1B8h] BYREF
  void **v70; // [rsp+130h] [rbp-198h] BYREF
  int v71; // [rsp+138h] [rbp-190h] BYREF
  char v72; // [rsp+13Ch] [rbp-18Ch]
  int v73; // [rsp+160h] [rbp-168h] BYREF
  const char *v74; // [rsp+168h] [rbp-160h]
  __int64 v75; // [rsp+170h] [rbp-158h]
  char v76; // [rsp+178h] [rbp-150h]
  int v77; // [rsp+180h] [rbp-148h]
  char v78[152]; // [rsp+188h] [rbp-140h] BYREF
  __int64 v79; // [rsp+220h] [rbp-A8h]
  __int64 v80; // [rsp+228h] [rbp-A0h]
  int v81; // [rsp+230h] [rbp-98h]
  __int64 v82; // [rsp+238h] [rbp-90h]
  int *v83; // [rsp+240h] [rbp-88h]
  __int64 v84; // [rsp+248h] [rbp-80h]
  __int64 v85; // [rsp+250h] [rbp-78h]
  void ***v86; // [rsp+258h] [rbp-70h]
  __int64 v87; // [rsp+260h] [rbp-68h]
  int v88; // [rsp+268h] [rbp-60h]
  int *v89; // [rsp+270h] [rbp-58h]
  char v90; // [rsp+278h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  v58 = a4;
  v55 = a3;
  Binding = a2;
  pAsync = a1;
  v66 = a1;
  v64 = a6;
  v11 = a7;
  v54 = a7;
  v12 = a8;
  v51 = a8;
  v13 = a9;
  v67 = a9;
  SetThreadName(L"RPC IDBFact_openDatabase");
  v71 = 0;
  v72 = 0;
  v76 = 0;
  v73 = 0;
  v74 = "IDB_IDBFactory_openDatabase";
  v75 = 0;
  v77 = 0;
  v79 = 0;
  v80 = 0;
  memset_0(v78, 0, sizeof(v78));
  v81 = 1;
  v82 = 0;
  v83 = &v71;
  v84 = 0;
  v85 = 0;
  v86 = &v70;
  v87 = 0;
  v88 = 0;
  v89 = &v73;
  v90 = 0;
  v70 = &IndexedDbTraceLogging::IDB_IDBFactory_openDatabase::`vftable';
  IndexedDbTraceLogging::IDB_IDBFactory_openDatabase::StartActivity(
    (IndexedDbTraceLogging::IDB_IDBFactory_openDatabase *)&v70,
    a3,
    a4,
    a5,
    a6);
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a9 )
  {
    *(_OWORD *)a9 = 0;
    *((_OWORD *)a9 + 1) = 0;
    *((_OWORD *)a9 + 2) = 0;
    *((_QWORD *)a9 + 6) = 0;
  }
  Reply = -2147024809;
  if ( !a3 || !a7 || !a8 || !a9 )
    goto LABEL_8;
  v15 = (char *)operator new(0x30u);
  *(_DWORD *)v15 = 1;
  *((_QWORD *)v15 + 1) = v15 + 8;
  *((_QWORD *)v15 + 2) = v15 + 8;
  *((_QWORD *)v15 + 3) = 0;
  *((_QWORD *)v15 + 4) = 0;
  *((_QWORD *)v15 + 5) = 0;
  v65 = v15;
  v62 = 0;
  CRpcCallAbortedNotificationHelper::Close((CRpcCallAbortedNotificationHelper *)v15);
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)v15 + 4) = EventW;
  if ( EventW )
  {
    v17 = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)v15 + 5) = v17;
    if ( v17 )
    {
      v19 = -2147467259;
      memset(&NotificationInfo.NotificationRoutine + 1, 0, 24);
      NotificationInfo.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)CRpcCallAbortedNotificationHelper::s_NotificationRoutine;
      CThreadSafeLinkedList<CRpcCallAbortedNotificationHelper,CDoubleLink<CRpcCallAbortedNotificationHelper,&public: static int CRpcCallAbortedNotificationHelper::CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset(void)>>::AddToList(
        v18,
        v15);
      CLock::Lock((CLock *)&qword_180111C48);
      if ( *((char **)v15 + 1) == v15 + 8 )
      {
        v21 = 0;
      }
      else
      {
        for ( i = (_UNKNOWN **)g_lstCallNotifications; ; i = (_UNKNOWN **)*i )
        {
          v21 = 0;
          if ( i == &g_lstCallNotifications )
            break;
          if ( v15 == (char *)(i - 1) )
          {
            v21 = 1;
            break;
          }
        }
      }
      CLock::Unlock((CLock *)&qword_180111C48);
      if ( v21 )
      {
        pAsync->UserInfo = v15;
        v33 = RpcServerSubscribeForNotification(
                Binding,
                RpcNotificationCallCancel|RpcNotificationClientDisconnect,
                RpcNotificationTypeCallback,
                &NotificationInfo);
        v19 = v33;
        if ( v33 > 0 )
          v19 = (unsigned __int16)v33 | 0x80070000;
        if ( v19 >= 0 )
        {
          *((_QWORD *)v15 + 3) = Binding;
          v62 = (void *)*((_QWORD *)v15 + 4);
          Reply = v19;
LABEL_25:
          v22 = *((_QWORD *)v55 + 2);
          v49 = a5 != 0;
          *(_OWORD *)a9 = 0;
          *((_OWORD *)a9 + 1) = 0;
          *((_OWORD *)a9 + 2) = 0;
          *((_QWORD *)a9 + 6) = 0;
          v23 = 0;
          v56 = 0;
          v24 = 0;
          Binding = 0;
          v53 = 0;
          v25 = 0;
          LODWORD(v59) = 0;
          SRWLock = 0;
          v26 = *(_QWORD *)(v22 + 88);
          if ( v26 )
          {
            v50[0] = *(_DWORD *)(v26 + 52);
            v60 = (PSRWLOCK)&qword_1800D76F0;
            v61 = 0;
            if ( (*(int (__fastcall **)(_QWORD, PSRWLOCK *))(**(_QWORD **)(v22 + 8) + 24LL))(*(_QWORD *)(v22 + 8), &v60) >= 0 )
              CIndexedDBServerPhysicalDBManager::DeleteEdpFilesAsNeeded(v50[0], (struct CWxString *)&v60);
            CWxString::_Release((CWxString *)&v60);
          }
          v50[0] = CIndexedDBServerFactoryWithSecurityContext::GetDatabaseHelper(
                     v22,
                     *(unsigned int *)v58,
                     *((_QWORD *)v58 + 1),
                     v55,
                     &SRWLock);
          if ( (v50[0] & 0x80000000) == 0 )
          {
            v50[0] = CIndexedDBServerDatabase::ProcessOpenRequest(
                       (CIndexedDBServerDatabase *)SRWLock,
                       v62,
                       v49,
                       a5,
                       (enum INDEXED_DB_DATABASE_OPEN_RESULT *)&v59,
                       a9,
                       &v56,
                       &v53,
                       (struct CIndexedDBServerOpenRequestQueueEntry **)&Binding);
            CIndexedDBServerDatabase::DecrementInUseCount((CIndexedDBServerDatabase *)SRWLock);
            v23 = (volatile signed __int32 *)v56;
            v24 = (CIndexedDBServerOpenRequestQueueEntry *)Binding;
            v25 = (int)v59;
          }
          if ( v23 )
          {
            v27 = operator new(0x18u);
            v69[0] = v27;
            *v27 = 0;
            v27[1] = 0;
            v28 = v55;
            if ( *((_QWORD *)v55 + 4) )
            {
              *v27 = *((_QWORD *)v55 + 3);
              v29 = *((_QWORD *)v28 + 4);
              v27[1] = v29;
              _InterlockedIncrement((volatile signed __int32 *)(v29 + 12));
            }
            v27[2] = v23;
            SRWLock = (PSRWLOCK)*((_QWORD *)v28 + 3);
            v59 = v23;
            AcquireSRWLockExclusive(SRWLock);
            v60 = SRWLock;
            std::deque<wil::com_ptr_t<CIndexedDBServerDatabaseClientConnection,wil::err_exception_policy>>::_Emplace_back_internal<CIndexedDBServerDatabaseClientConnection * &>(
              &SRWLock[1],
              &v59);
            if ( SRWLock )
              ReleaseSRWLockExclusive(SRWLock);
            std::unique_ptr<IndexedDbFactorySession::DatabaseConnectionRegistration>::reset(v23 + 58, v27);
          }
          Reply = v50[0];
          v50[0] = 0;
          if ( Reply < 0 )
          {
            if ( (int)CIndexedDBServerFactoryWithSecurityContext::GetClientContextFlags(
                        *((CIndexedDBServerFactoryWithSecurityContext **)v55 + 2),
                        v50) >= 0 )
              CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(v50[0], v43, 0);
            if ( (int)(Reply + 0x80000000) >= 0 && Reply != -2140082173 )
            {
              v12 = v51;
LABEL_47:
              v11 = v54;
              goto LABEL_48;
            }
          }
          v30 = v25 - 1;
          if ( v30 )
          {
            v44 = v30 - 1;
            if ( !v44 )
            {
              _InterlockedIncrement(v23 + 16);
              *v54 = (void *)v23;
              v31 = v53;
              _InterlockedIncrement((volatile signed __int32 *)v53 + 22);
              v12 = v51;
              *v51 = v31;
              goto LABEL_41;
            }
            if ( v44 == 1 )
            {
              try
              {
                Instance = WebPlatStorageClientManager::GetInstance();
                v35 = *(_QWORD *)Instance;
                v36 = *(void (__fastcall **)(__int64, unsigned int *, __int64))(**(_QWORD **)Instance + 8LL);
                PackageName = ClientIdentity::s_GetPackageName(v69);
                v36(v35, v50, PackageName);
                std::wstring::~wstring(v69);
                v38 = (_QWORD *)(***(__int64 (__fastcall ****)(_QWORD, PSRWLOCK *))v50)(*(_QWORD *)v50, &v60);
                (*(void (__fastcall **)(_QWORD, void **, struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 *))(*(_QWORD *)*v38 + 72LL))(
                  *v38,
                  &v55,
                  v64);
                if ( v61 )
                  std::_Ref_count_base::_Decref(v61);
                v39 = v55;
                v64 = **(struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 ***)v55;
                v40 = (RTL_SRWLOCK *)operator new(0x38u);
                v60 = v40;
                gsl::span<unsigned short const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(
                  v69,
                  *((_QWORD *)v58 + 1),
                  *(unsigned int *)v58);
                SRWLock = (PSRWLOCK)IndexedDbBlockedEvent::IndexedDbBlockedEvent(v40, v69, v41, a5);
                ((void (__fastcall *)(void *, PSRWLOCK *))v64)(v39, &SRWLock);
                std::unique_ptr<IEventSubchannel>::~unique_ptr<IEventSubchannel>(&SRWLock);
                Reply = 0;
                std::unique_ptr<IEventSubchannel>::~unique_ptr<IEventSubchannel>(&v55);
              }
              catch ( ... )
              {
                wil::details::in1diag3::Log_CaughtException(
                  retaddr,
                  (void *)0x13B,
                  (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\server\\rpcapi.cxx",
                  v42);
                Reply = wil::ResultFromCaughtException(v47);
                v15 = v65;
                v23 = (volatile signed __int32 *)v56;
                v24 = (CIndexedDBServerOpenRequestQueueEntry *)Binding;
                pAsync = v66;
                v13 = v67;
                goto LABEL_77;
              }
              if ( *(_QWORD *)v50 )
                std::default_delete<IWebPlatStorageClientReference>::operator()();
LABEL_77:
              v45 = (struct CIndexedDBServerTransaction **)v51;
              v46 = (struct CIndexedDBServerDatabaseClientConnection **)v54;
              if ( Reply >= 0 )
              {
                v58 = 0;
                Reply = CIndexedDBServerOpenRequestQueueEntry::OpenDatabaseAfterOnBlocked(v24, v62, v13, &v56, &v58);
                v50[0] = 0;
                if ( Reply >= 0 )
                {
                  v23 = (volatile signed __int32 *)v56;
                  if ( v56 )
                  {
                    *v46 = v56;
                    v23 = 0;
                  }
                  if ( v58 )
                    *v45 = v58;
                  CIndexedDBServerOpenRequestQueueEntry::Close(v24);
                  CIndexedDBServerFactoryWithSecurityContext::Release(v24);
                  v24 = 0;
                }
                else
                {
                  if ( CIndexedDBServerOpenRequestQueueEntry::GetClientContextFlags(v24, v50) >= 0 )
                    CIndexedDBServerPhysicalDBManager::HandleCorruptionIfDetected(v50[0], Reply, 0);
                  v23 = (volatile signed __int32 *)v56;
                }
              }
            }
            else
            {
              Reply = -2147467259;
            }
          }
          else
          {
            _InterlockedIncrement(v23 + 16);
            *v54 = (void *)v23;
          }
          v31 = v53;
          v12 = v51;
LABEL_41:
          if ( v24 )
            CIndexedDBServerFactoryWithSecurityContext::Release(v24);
          if ( v23 )
            CIndexedDBServerFactoryWithSecurityContext::Release((CIndexedDBServerFactoryWithSecurityContext *)v23);
          if ( v31 )
            CIndexedDBServerTransaction::Release(v31);
          goto LABEL_47;
        }
      }
      goto LABEL_23;
    }
  }
  LastError = GetLastError();
  v19 = LastError;
  if ( LastError > 0 )
    v19 = (unsigned __int16)LastError | 0x80070000;
  if ( v19 < 0 )
LABEL_23:
    CRpcCallAbortedNotificationHelper::Close((CRpcCallAbortedNotificationHelper *)v15);
  Reply = v19;
  if ( v19 >= 0 )
    goto LABEL_25;
LABEL_48:
  if ( v15 && (int)CRpcCallAbortedNotificationHelper::Close((CRpcCallAbortedNotificationHelper *)v15) >= 0 )
    CRpcCallAbortedNotificationHelper::Release((CRpcCallAbortedNotificationHelper *)v15);
  if ( Reply < 0 )
  {
LABEL_8:
    wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      &v70,
      (unsigned int)Reply);
    goto LABEL_9;
  }
  IndexedDbTraceLogging::IDB_IDBFactory_openDatabase::Stop(
    (IndexedDbTraceLogging::IDB_IDBFactory_openDatabase *)&v70,
    *v11,
    *v12,
    v13);
LABEL_9:
  if ( RpcAsyncCompleteCall(pAsync, &Reply) )
  {
    INDEXED_DB_TRANSACTION_HANDLE_SERIALIZE_rundown((CIndexedDBServerTransaction *)*v12);
    INDEXED_DB_DATABASE_HANDLE_SERIALIZE_rundown(*v11);
  }
  v70 = &IndexedDbTraceLogging::IDB_IDBFactory_openDatabase::`vftable';
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v70);
  wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(&v70);
  return SetThreadName(&word_1800D6108);
}

```

## disassembly

```asm
0x18002bf80  push    rbx
0x18002bf82  push    rsi
0x18002bf83  push    rdi
0x18002bf84  push    r12
0x18002bf86  push    r13
0x18002bf88  push    r14
0x18002bf8a  push    r15
0x18002bf8c  sub     rsp, 290h
0x18002bf93  mov     rax, cs:__security_cookie
0x18002bf9a  xor     rax, rsp
0x18002bf9d  mov     [rsp+2C8h+var_40], rax
0x18002bfa5  mov     rsi, r9
0x18002bfa8  mov     [rsp+2C8h+var_230], r9
0x18002bfb0  mov     rdi, r8
0x18002bfb3  mov     [rsp+2C8h+var_248], r8
0x18002bfbb  mov     [rsp+2C8h+Binding], rdx
0x18002bfc3  mov     [rsp+2C8h+pAsync], rcx
0x18002bfcb  mov     [rsp+2C8h+var_1F0], rcx
0x18002bfd3  mov     r14, [rsp+2C8h+arg_28]
0x18002bfdb  mov     [rsp+2C8h+var_200], r14
0x18002bfe3  mov     r15, [rsp+2C8h+arg_30]
0x18002bfeb  mov     [rsp+2C8h+var_250], r15
0x18002bff0  mov     r12, [rsp+2C8h+arg_38]
0x18002bff8  mov     [rsp+2C8h+var_268], r12
0x18002bffd  mov     r13, [rsp+2C8h+arg_40]
0x18002c005  mov     [rsp+2C8h+var_1E8], r13
0x18002c00d  xor     ebx, ebx
0x18002c00f  lea     rcx, aRpcIdbfactOpen; "RPC IDBFact_openDatabase"
0x18002c016  call    SetThreadName
0x18002c01b  nop
0x18002c01c  mov     [rsp+2C8h+var_190], ebx
0x18002c023  mov     [rsp+2C8h+var_18C], bl
0x18002c02a  mov     [rsp+2C8h+var_150], bl
0x18002c031  mov     [rsp+2C8h+var_168], ebx
0x18002c038  lea     rax, aIdbIdbfactoryO; "IDB_IDBFactory_openDatabase"
0x18002c03f  mov     [rsp+2C8h+var_160], rax
0x18002c047  mov     [rsp+2C8h+var_158], rbx
0x18002c04f  mov     [rsp+2C8h+var_148], ebx
0x18002c056  mov     [rsp+2C8h+var_A8], rbx
0x18002c05e  mov     [rsp+2C8h+var_A0], rbx
0x18002c066  xor     edx, edx; Val
0x18002c068  mov     r8d, 98h; Size
0x18002c06e  lea     rcx, [rsp+2C8h+var_140]; void *
0x18002c076  call    memset_0
0x18002c07b  mov     [rsp+2C8h+var_98], 1
0x18002c086  xor     eax, eax
0x18002c088  mov     [rsp+2C8h+var_90], rax
0x18002c090  lea     rax, [rsp+2C8h+var_190]
0x18002c098  mov     [rsp+2C8h+var_88], rax
0x18002c0a0  mov     [rsp+2C8h+var_80], rbx
0x18002c0a8  mov     [rsp+2C8h+var_78], rbx
0x18002c0b0  lea     rax, [rsp+2C8h+var_198]
0x18002c0b8  mov     [rsp+2C8h+var_70], rax
0x18002c0c0  mov     [rsp+2C8h+var_68], rbx
0x18002c0c8  mov     [rsp+2C8h+var_60], ebx
0x18002c0cf  lea     rax, [rsp+2C8h+var_168]
0x18002c0d7  mov     [rsp+2C8h+var_58], rax
0x18002c0df  mov     [rsp+2C8h+var_50], bl
0x18002c0e6  lea     rax, ??_7IDB_IDBFactory_openDatabase@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBFactory_openDatabase::`vftable'
0x18002c0ed  mov     [rsp+2C8h+var_198], rax
0x18002c0f5  mov     [rsp+2C8h+var_2A8], r14; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 *
0x18002c0fa  mov     r9, [rsp+2C8h+arg_20]; __int64
0x18002c102  mov     r8, rsi; struct __MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 *
0x18002c105  mov     rdx, rdi; void *
0x18002c108  lea     rcx, [rsp+2C8h+var_198]; this
0x18002c110  call    ?StartActivity@IDB_IDBFactory_openDatabase@IndexedDbTraceLogging@@QEAAXPEAXAEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001@@_JAEBU__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003@@@Z; IndexedDbTraceLogging::IDB_IDBFactory_openDatabase::StartActivity(void *,__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0001 const &,__int64,__MIDL___MIDL_itf_rpcwebplatstorageshared_0000_0000_0003 const &)
0x18002c115  nop
0x18002c116  test    r15, r15
0x18002c119  jnz     loc_18002C793
0x18002c11f  test    r12, r12
0x18002c122  jnz     loc_18002C79B
0x18002c128  test    r13, r13
0x18002c12b  jnz     loc_18002C7A4
0x18002c131  mov     [rsp+2C8h+Reply], 80070057h
0x18002c139  test    rdi, rdi
0x18002c13c  jnz     loc_18002C1C8
0x18002c142  mov     edx, [rsp+2C8h+Reply]
0x18002c146  lea     rcx, [rsp+2C8h+var_198]
0x18002c14e  call    ?Stop@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002c153  lea     rdx, [rsp+2C8h+Reply]; Reply
0x18002c158  mov     rcx, [rsp+2C8h+pAsync]; pAsync
0x18002c160  call    cs:__imp_RpcAsyncCompleteCall
0x18002c166  test    eax, eax
0x18002c168  jnz     loc_18002C988
0x18002c16e  lea     rax, ??_7IDB_IDBFactory_openDatabase@IndexedDbTraceLogging@@6B@; const IndexedDbTraceLogging::IDB_IDBFactory_openDatabase::`vftable'
0x18002c175  mov     [rsp+2C8h+var_198], rax
0x18002c17d  lea     rcx, [rsp+2C8h+var_198]
0x18002c185  call    ?Destroy@?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002c18a  lea     rcx, [rsp+2C8h+var_198]
0x18002c192  call    ??1?$ActivityBase@VStorageServerProvider@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageServerProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002c197  nop
0x18002c198  lea     rcx, word_1800D6108; lpWideCharStr
0x18002c19f  call    SetThreadName
0x18002c1a4  nop
0x18002c1a5  mov     rcx, [rsp+2C8h+var_40]
0x18002c1ad  xor     rcx, rsp; StackCookie
0x18002c1b0  call    __security_check_cookie
0x18002c1b5  add     rsp, 290h
0x18002c1bc  pop     r15
0x18002c1be  pop     r14
0x18002c1c0  pop     r13
0x18002c1c2  pop     r12
0x18002c1c4  pop     rdi
0x18002c1c5  pop     rsi
0x18002c1c6  pop     rbx
0x18002c1c7  retn
0x18002c1c8  test    r15, r15
0x18002c1cb  jz      loc_18002C142
0x18002c1d1  test    r12, r12
0x18002c1d4  jz      loc_18002C142
0x18002c1da  test    r13, r13
0x18002c1dd  jz      loc_18002C142
0x18002c1e3  mov     [rsp+2C8h+var_1F8], rbx
0x18002c1eb  mov     ecx, 30h ; '0'; Size
0x18002c1f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c1f5  mov     rsi, rax
0x18002c1f8  mov     edi, 1
0x18002c1fd  mov     [rax], edi
0x18002c1ff  lea     r14, [rax+8]
0x18002c203  mov     [r14], r14
0x18002c206  mov     [r14+8], r14
0x18002c20a  mov     [rax+18h], rbx
0x18002c20e  mov     [rax+20h], rbx
0x18002c212  mov     [rax+28h], rbx
0x18002c216  mov     [rsp+2C8h+var_1F8], rax
0x18002c21e  mov     [rsp+2C8h+var_210], rbx
0x18002c226  mov     rcx, rax; this
0x18002c229  call    ?Close@CRpcCallAbortedNotificationHelper@@QEAAJXZ; CRpcCallAbortedNotificationHelper::Close(void)
0x18002c22e  xor     r9d, r9d; lpName
0x18002c231  xor     r8d, r8d; bInitialState
0x18002c234  mov     edx, edi; bManualReset
0x18002c236  xor     ecx, ecx; lpEventAttributes
0x18002c238  call    cs:__imp_CreateEventW
0x18002c23e  mov     [rsi+20h], rax
0x18002c242  test    rax, rax
0x18002c245  jz      loc_18002C5AF
0x18002c24b  xor     r9d, r9d; lpName
0x18002c24e  xor     r8d, r8d; bInitialState
0x18002c251  xor     edx, edx; bManualReset
0x18002c253  xor     ecx, ecx; lpEventAttributes
0x18002c255  call    cs:__imp_CreateEventW
0x18002c25b  mov     [rsi+28h], rax
0x18002c25f  test    rax, rax
0x18002c262  jz      loc_18002C5AF
0x18002c268  mov     edi, 80004005h
0x18002c26d  xorps   xmm0, xmm0
0x18002c270  xor     eax, eax
0x18002c272  movups  xmmword ptr [rsp+2C8h+NotificationInfo+8], xmm0
0x18002c27a  mov     qword ptr [rsp+2C8h+NotificationInfo+18h], rax
0x18002c282  lea     rax, ?s_NotificationRoutine@CRpcCallAbortedNotificationHelper@@CAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z; CRpcCallAbortedNotificationHelper::s_NotificationRoutine(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)
0x18002c289  mov     qword ptr [rsp+2C8h+NotificationInfo], rax
0x18002c291  mov     rdx, rsi
0x18002c294  call    ?AddToList@?$CThreadSafeLinkedList@VCRpcCallAbortedNotificationHelper@@V?$CDoubleLink@VCRpcCallAbortedNotificationHelper@@$1?CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset@1@SAHXZ@@@@QEAAXPEAVCRpcCallAbortedNotificationHelper@@@Z; CThreadSafeLinkedList<CRpcCallAbortedNotificationHelper,CDoubleLink<CRpcCallAbortedNotificationHelper,&CRpcCallAbortedNotificationHelper::CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset(void)>>::AddToList(CRpcCallAbortedNotificationHelper *)
0x18002c299  lea     rcx, qword_180111C48; this
0x18002c2a0  call    ?Lock@CLock@@QEAAHXZ; CLock::Lock(void)
0x18002c2a5  cmp     [r14], r14
0x18002c2a8  jz      loc_18002C527
0x18002c2ae  mov     rcx, cs:?g_lstCallNotifications@@3V?$CThreadSafeLinkedList@VCRpcCallAbortedNotificationHelper@@V?$CDoubleLink@VCRpcCallAbortedNotificationHelper@@$1?CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset@1@SAHXZ@@@@A; CThreadSafeLinkedList<CRpcCallAbortedNotificationHelper,CDoubleLink<CRpcCallAbortedNotificationHelper,&CRpcCallAbortedNotificationHelper::CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset(void)>> g_lstCallNotifications
0x18002c2b5  mov     r14b, bl
0x18002c2b8  lea     rax, ?g_lstCallNotifications@@3V?$CThreadSafeLinkedList@VCRpcCallAbortedNotificationHelper@@V?$CDoubleLink@VCRpcCallAbortedNotificationHelper@@$1?CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset@1@SAHXZ@@@@A; CThreadSafeLinkedList<CRpcCallAbortedNotificationHelper,CDoubleLink<CRpcCallAbortedNotificationHelper,&CRpcCallAbortedNotificationHelper::CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset(void)>> g_lstCallNotifications
0x18002c2bf  cmp     rcx, rax
0x18002c2c2  jz      short loc_18002C2D4
0x18002c2c4  lea     rax, [rcx-8]
0x18002c2c8  cmp     rsi, rax
0x18002c2cb  jnz     loc_18002C7C1
0x18002c2d1  mov     r14b, 1
0x18002c2d4  lea     rcx, qword_180111C48; this
0x18002c2db  call    ?Unlock@CLock@@QEAAHXZ; CLock::Unlock(void)
0x18002c2e0  test    r14b, r14b
0x18002c2e3  jnz     loc_18002C5F6
0x18002c2e9  mov     rcx, rsi; this
0x18002c2ec  call    ?Close@CRpcCallAbortedNotificationHelper@@QEAAJXZ; CRpcCallAbortedNotificationHelper::Close(void)
0x18002c2f1  mov     [rsp+2C8h+Reply], edi
0x18002c2f5  test    edi, edi
0x18002c2f7  js      loc_18002C4E8
0x18002c2fd  mov     r12, [rsp+2C8h+var_248]
0x18002c305  mov     r12, [r12+10h]
0x18002c30a  cmp     [rsp+2C8h+arg_20], rbx
0x18002c312  setnz   [rsp+2C8h+var_274]
0x18002c317  xorps   xmm0, xmm0
0x18002c31a  xor     eax, eax
0x18002c31c  movups  xmmword ptr [r13+0], xmm0
0x18002c321  movups  xmmword ptr [r13+10h], xmm0
0x18002c326  movups  xmmword ptr [r13+20h], xmm0
0x18002c32b  mov     [r13+30h], rax
0x18002c32f  mov     rdi, rbx
0x18002c332  mov     [rsp+2C8h+var_240], rbx
0x18002c33a  mov     r14, rbx
0x18002c33d  mov     [rsp+2C8h+Binding], rbx
0x18002c345  mov     [rsp+2C8h+var_258], rbx
0x18002c34a  mov     r15d, ebx
0x18002c34d  mov     dword ptr [rsp+2C8h+var_228], ebx
0x18002c354  mov     [rsp+2C8h+SRWLock], rbx
0x18002c359  mov     rax, [r12+58h]
0x18002c35e  test    rax, rax
0x18002c361  jz      short loc_18002C3B0
0x18002c363  mov     eax, [rax+34h]
0x18002c366  mov     [rsp+2C8h+var_270], eax
0x18002c36a  lea     rcx, qword_1800D76F0
0x18002c371  mov     [rsp+2C8h+var_220], rcx
0x18002c379  mov     [rsp+2C8h+var_218], rbx
0x18002c381  mov     rcx, [r12+8]
0x18002c386  mov     rax, [rcx]
0x18002c389  lea     rdx, [rsp+2C8h+var_220]
0x18002c391  mov     rax, [rax+18h]
0x18002c395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c39a  test    eax, eax
0x18002c39c  jns     loc_18002C7E5
0x18002c3a2  lea     rcx, [rsp+2C8h+var_220]; this
0x18002c3aa  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x18002c3af  nop
0x18002c3b0  lea     rax, [rsp+2C8h+SRWLock]
0x18002c3b5  mov     [rsp+2C8h+var_2A8], rax
0x18002c3ba  mov     r9, [rsp+2C8h+var_248]
0x18002c3c2  mov     rdx, [rsp+2C8h+var_230]
0x18002c3ca  mov     r8, [rdx+8]
0x18002c3ce  mov     edx, [rdx]
0x18002c3d0  mov     rcx, r12
0x18002c3d3  call    ?GetDatabaseHelper@CIndexedDBServerFactoryWithSecurityContext@@IEAAJKPEBGAEBV?$shared_ptr@UIQuotaSession@@@std@@PEAPEAVCIndexedDBServerDatabase@@@Z; CIndexedDBServerFactoryWithSecurityContext::GetDatabaseHelper(ulong,ushort const *,std::shared_ptr<IQuotaSession> const &,CIndexedDBServerDatabase * *)
0x18002c3d8  mov     [rsp+2C8h+var_270], eax
0x18002c3dc  test    eax, eax
0x18002c3de  jns     loc_18002C52F
0x18002c3e4  test    rdi, rdi
0x18002c3e7  jz      loc_18002C48D
0x18002c3ed  mov     ecx, 18h; Size
0x18002c3f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c3f7  mov     r12, rax
0x18002c3fa  mov     [rsp+2C8h+var_1B8], rax
0x18002c402  mov     [rax], rbx
0x18002c405  mov     [rax+8], rbx
0x18002c409  mov     rax, [rsp+2C8h+var_248]
0x18002c411  cmp     [rax+20h], rbx
0x18002c415  jz      short loc_18002C42C
0x18002c417  mov     rcx, [rax+18h]
0x18002c41b  mov     [r12], rcx
0x18002c41f  mov     rcx, [rax+20h]
0x18002c423  mov     [r12+8], rcx
0x18002c428  lock inc dword ptr [rcx+0Ch]
0x18002c42c  mov     [r12+10h], rdi
0x18002c431  mov     rax, [rax+18h]
0x18002c435  mov     [rsp+2C8h+SRWLock], rax
0x18002c43a  mov     [rsp+2C8h+var_228], rdi
0x18002c442  mov     rcx, rax; SRWLock
0x18002c445  call    cs:__imp_AcquireSRWLockExclusive
0x18002c44b  mov     rcx, [rsp+2C8h+SRWLock]
0x18002c450  mov     [rsp+2C8h+var_220], rcx
0x18002c458  add     rcx, 8
0x18002c45c  lea     rdx, [rsp+2C8h+var_228]
0x18002c464  call    ??$_Emplace_back_internal@AEAPEAVCIndexedDBServerDatabaseClientConnection@@@?$deque@V?$com_ptr_t@VCIndexedDBServerDatabaseClientConnection@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCIndexedDBServerDatabaseClientConnection@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXAEAPEAVCIndexedDBServerDatabaseClientConnection@@@Z; std::deque<wil::com_ptr_t<CIndexedDBServerDatabaseClientConnection,wil::err_exception_policy>>::_Emplace_back_internal<CIndexedDBServerDatabaseClientConnection * &>(CIndexedDBServerDatabaseClientConnection * &)
0x18002c469  nop
0x18002c46a  mov     rax, [rsp+2C8h+SRWLock]
0x18002c46f  test    rax, rax
0x18002c472  jz      short loc_18002C47E
0x18002c474  mov     rcx, rax; SRWLock
0x18002c477  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c47d  nop
0x18002c47e  lea     rcx, [rdi+0E8h]
0x18002c485  mov     rdx, r12
0x18002c488  call    ?reset@?$unique_ptr@VDatabaseConnectionRegistration@IndexedDbFactorySession@@U?$default_delete@VDatabaseConnectionRegistration@IndexedDbFactorySession@@@std@@@std@@QEAAXPEAVDatabaseConnectionRegistration@IndexedDbFactorySession@@@Z; std::unique_ptr<IndexedDbFactorySession::DatabaseConnectionRegistration>::reset(IndexedDbFactorySession::DatabaseConnectionRegistration *)
0x18002c48d  mov     r9d, [rsp+2C8h+var_270]
0x18002c492  mov     [rsp+2C8h+Reply], r9d
0x18002c497  mov     [rsp+2C8h+var_270], ebx
0x18002c49b  test    r9d, r9d
0x18002c49e  js      loc_18002C7FB
0x18002c4a4  sub     r15d, 1
0x18002c4a8  jnz     loc_18002C82D
0x18002c4ae  lock inc dword ptr [rdi+40h]
0x18002c4b2  mov     r15, [rsp+2C8h+var_250]
0x18002c4b7  mov     [r15], rdi
0x18002c4ba  mov     r15, [rsp+2C8h+var_258]
0x18002c4bf  mov     r12, [rsp+2C8h+var_268]
0x18002c4c4  test    r14, r14
0x18002c4c7  jnz     loc_18002C96E
0x18002c4cd  test    rdi, rdi
0x18002c4d0  jz      short loc_18002C4DA
0x18002c4d2  mov     rcx, rdi; this
0x18002c4d5  call    ?Release@CIndexedDBServerFactoryWithSecurityContext@@QEAAKXZ; CIndexedDBServerFactoryWithSecurityContext::Release(void)
0x18002c4da  test    r15, r15
0x18002c4dd  jnz     loc_18002C97B
0x18002c4e3  mov     r15, [rsp+2C8h+var_250]
0x18002c4e8  test    rsi, rsi
0x18002c4eb  jz      short loc_18002C501
0x18002c4ed  mov     rcx, rsi; this
0x18002c4f0  call    ?Close@CRpcCallAbortedNotificationHelper@@QEAAJXZ; CRpcCallAbortedNotificationHelper::Close(void)
0x18002c4f5  test    eax, eax
0x18002c4f7  js      short loc_18002C501
0x18002c4f9  mov     rcx, rsi; this
0x18002c4fc  call    ?Release@CRpcCallAbortedNotificationHelper@@QEAAKXZ; CRpcCallAbortedNotificationHelper::Release(void)
0x18002c501  cmp     [rsp+2C8h+Reply], ebx
0x18002c505  jl      loc_18002C142
0x18002c50b  mov     r9, r13; struct __MIDL_RPCIndexedDB_0008 *
0x18002c50e  mov     r8, [r12]; void *
0x18002c512  mov     rdx, [r15]; void *
0x18002c515  lea     rcx, [rsp+2C8h+var_198]; this
0x18002c51d  call    ?Stop@IDB_IDBFactory_openDatabase@IndexedDbTraceLogging@@QEAAXPEAX0AEBU__MIDL_RPCIndexedDB_0008@@@Z; IndexedDbTraceLogging::IDB_IDBFactory_openDatabase::Stop(void *,void *,__MIDL_RPCIndexedDB_0008 const &)
0x18002c522  jmp     loc_18002C153
0x18002c527  mov     r14b, bl
0x18002c52a  jmp     loc_18002C2D4
0x18002c52f  lea     rax, [rsp+2C8h+Binding]
0x18002c537  mov     [rsp+2C8h+var_288], rax; struct CIndexedDBServerOpenRequestQueueEntry **
  ... truncated ...
```
