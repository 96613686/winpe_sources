# ChatStoreChangedEventSink::Advise(ServiceDataSession *)

- ea: `0x1800af9f0`
- end: `0x1800afd35`
- name: `?Advise@ChatStoreChangedEventSink@@QEAAJPEAVServiceDataSession@@@Z`
- size: `837`
- prototype: `__int64 __fastcall(ChatStoreChangedEventSink *__hidden this, struct ServiceDataSession *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800033c0`

## callees

- `0x1800072f4`
- `0x180008ee8`
- `0x18000e1f8`
- `0x180030948`
- `0x180066af8`
- `0x18006db44`
- `0x180072ccc`
- `0x1800841c8`
- `0x1800889b4`
- `0x1800aa334`
- `0x1800ab09c`
- `0x1800af9f0`
- `0x1800edf18`
- `0x1800f2398`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800afc6e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800afcd9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800afc6e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800afcd9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800afc44`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800afcb6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800afc44`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800afcb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800afa12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800afa63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800afa12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800afa63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800afac3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800afb2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800afd1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800afac3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800afb2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800afd1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800afa85`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800afa85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afa9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afa9c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800afa3b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800afa3b`

## pseudocode

```c
__int64 __fastcall ChatStoreChangedEventSink::Advise(ChatStoreChangedEventSink *this, struct ServiceDataSession *a2)
{
  HRESULT Instance; // eax
  __int64 v5; // r8
  unsigned int v6; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  _QWORD *v11; // rax
  char v12; // bl
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 *v19; // rbx
  int v20; // eax
  __int64 v21; // r8
  __int64 *v22; // rbx
  int v23; // eax
  __int64 v24; // r8
  __m128i si128; // [rsp+30h] [rbp-28h] BYREF
  __int64 v27; // [rsp+40h] [rbp-18h]
  __int64 fPending; // [rsp+A0h] [rbp+48h] BYREF
  struct ServiceDataSession *v29; // [rsp+A8h] [rbp+50h] BYREF
  LPVOID Context; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v31; // [rsp+B8h] [rbp+60h] BYREF

  v29 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_QWORD *)this + 2)
    || (Instance = CoCreateInstance(
                     &GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7,
                     0,
                     0x17u,
                     &GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c,
                     (LPVOID *)this + 2),
        v6 = Instance,
        Instance >= 0) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    if ( !*((_QWORD *)this + 17) )
    {
      EventW = CreateEventW(0, 1, 1, 0);
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::reset((char *)this + 136, EventW);
      if ( !*((_QWORD *)this + 17) )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        v10 = 36;
        goto LABEL_9;
      }
    }
    v11 = utl::find<utl::_ArrayIt<ATL::CComPtr<ServiceDataSession>>,ServiceDataSession *>(
            &fPending,
            *((_QWORD **)this + 13),
            *((_QWORD **)this + 14),
            &v29);
    if ( v9 != *v11 )
    {
      v6 = -2147020579;
      v10 = 42;
LABEL_9:
      Log_HREvent_34(v6, 0, v9, v10);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      goto LABEL_37;
    }
    ATL::CComPtrBase<RcsComposingStatusTracker::ChatOpenedWorkItem>::CComPtrBase<RcsComposingStatusTracker::ChatOpenedWorkItem>(
      &fPending,
      a2);
    v12 = utl::vector<ATL::CComPtr<EmailServerSearchJob>,utl::allocator<ATL::CComPtr<EmailServerSearchJob>>>::push_back(
            (char *)this + 104,
            &fPending);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&fPending);
    if ( !v12 )
    {
      v6 = -2147024882;
      v10 = 44;
      goto LABEL_9;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    if ( !*((_DWORD *)this + 32) )
    {
      v27 = -1;
      si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      LODWORD(fPending) = -1;
      if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::emplace_back<unsigned int,0>(
                               &si128,
                               &fPending) )
      {
        v14 = 50;
LABEL_17:
        v6 = -2147024882;
        v15 = 0;
        v16 = 2147942414LL;
LABEL_18:
        Log_HREvent_34(v16, v15, v13, v14);
        utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&si128);
        goto LABEL_37;
      }
      LODWORD(fPending) = 3;
      if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::emplace_back<unsigned int,0>(
                               &si128,
                               &fPending) )
      {
        v14 = 51;
        goto LABEL_17;
      }
      LODWORD(fPending) = 4;
      if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::emplace_back<unsigned int,0>(
                               &si128,
                               &fPending) )
      {
        v14 = 52;
        goto LABEL_17;
      }
      v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, ChatStoreChangedEventSink *))(**((_QWORD **)this + 2)
                                                                                             + 184LL))(
              *((_QWORD *)this + 2),
              (si128.m128i_i64[1] - si128.m128i_i64[0]) >> 2,
              si128.m128i_i64[0],
              this);
      v6 = v17;
      if ( v17 < 0 )
      {
        v14 = 54;
        v15 = 1;
        v16 = (unsigned int)v17;
        goto LABEL_18;
      }
      *((_DWORD *)this + 32) = 1;
      if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x20) != 0 )
        McTemplateU0x_EventWriteTransfer(v18, ChatStoreChangedAdvise, this);
      LODWORD(fPending) = 0;
      Context = 0;
      InitOnceBeginInitialize(&stru_18015DCD8, 0, (PBOOL)&fPending, &Context);
      v19 = (__int64 *)Context;
      if ( !Context )
      {
        RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
        v31 = 0;
        InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
        v19 = qword_18015DCE0;
        tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v31);
      }
      v20 = RcsFileTransferProgressTracker::RegisterForFileTransferProgressChanges(
              (RcsFileTransferProgressTracker *)(v19 + 30),
              (ChatStoreChangedEventSink *)((char *)this + 8));
      if ( v20 < 0 )
        Log_HREvent_34((unsigned int)v20, 0, v21, 62);
      LODWORD(fPending) = 0;
      Context = 0;
      InitOnceBeginInitialize(&stru_18015DCD8, 0, (PBOOL)&fPending, &Context);
      v22 = (__int64 *)Context;
      if ( !Context )
      {
        RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
        v31 = 0;
        InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
        v22 = qword_18015DCE0;
        tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v31);
      }
      v23 = RcsMultipartMessageTracker::RegisterForFileTransferProgressChanges(
              (RcsMultipartMessageTracker *)(v22 + 90),
              (ChatStoreChangedEventSink *)((char *)this + 8));
      if ( v23 < 0 )
        Log_HREvent_34((unsigned int)v23, 0, v24, 65);
      utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&si128);
    }
    v6 = 0;
    goto LABEL_37;
  }
  Log_HREvent_34((unsigned int)Instance, 1, v5, 27);
LABEL_37:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return v6;
}

```

## disassembly

```asm
0x1800af9f0  mov     [rsp-40h+arg_8], rdx
0x1800af9f5  push    rbp
0x1800af9f6  push    rbx
0x1800af9f7  push    rsi
0x1800af9f8  push    rdi
0x1800af9f9  push    r12
0x1800af9fb  push    r13
0x1800af9fd  push    r14
0x1800af9ff  push    r15
0x1800afa01  mov     rbp, rsp
0x1800afa04  sub     rsp, 58h
0x1800afa08  mov     rdi, rcx
0x1800afa0b  mov     r12, rdx
0x1800afa0e  add     rcx, 40h ; '@'; lpCriticalSection
0x1800afa12  call    cs:__imp_EnterCriticalSection
0x1800afa18  lea     r15, [rdi+10h]
0x1800afa1c  cmp     qword ptr [r15], 0
0x1800afa20  jnz     short loc_1800AFA5C
0x1800afa22  xor     edx, edx; pUnkOuter
0x1800afa24  mov     [rsp+58h+ppv], r15; ppv
0x1800afa29  lea     r9, _GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c; riid
0x1800afa30  lea     rcx, _GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7; rclsid
0x1800afa37  lea     r8d, [rdx+17h]; dwClsContext
0x1800afa3b  call    cs:__imp_CoCreateInstance
0x1800afa41  mov     ebx, eax
0x1800afa43  test    eax, eax
0x1800afa45  jns     short loc_1800AFA5C
0x1800afa47  mov     edx, 1
0x1800afa4c  mov     ecx, eax
0x1800afa4e  lea     r9d, [rdx+1Ah]
0x1800afa52  call    Log_HREvent_34
0x1800afa57  jmp     loc_1800AFD18
0x1800afa5c  lea     r14, [rdi+18h]
0x1800afa60  mov     rcx, r14; lpCriticalSection
0x1800afa63  call    cs:__imp_EnterCriticalSection
0x1800afa69  lea     rbx, [rdi+88h]
0x1800afa70  mov     esi, 1
0x1800afa75  cmp     qword ptr [rbx], 0
0x1800afa79  jnz     short loc_1800AFACE
0x1800afa7b  xor     r9d, r9d; lpName
0x1800afa7e  mov     r8d, esi; bInitialState
0x1800afa81  mov     edx, esi; bManualReset
0x1800afa83  xor     ecx, ecx; lpEventAttributes
0x1800afa85  call    cs:__imp_CreateEventW
0x1800afa8b  mov     rdx, rax
0x1800afa8e  mov     rcx, rbx
0x1800afa91  call    ?reset@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::reset(void *)
0x1800afa96  cmp     qword ptr [rbx], 0
0x1800afa9a  jnz     short loc_1800AFACE
0x1800afa9c  call    cs:__imp_GetLastError
0x1800afaa2  mov     ebx, eax
0x1800afaa4  test    eax, eax
0x1800afaa6  jle     short loc_1800AFAB1
0x1800afaa8  movzx   ebx, ax
0x1800afaab  or      ebx, 80070000h
0x1800afab1  mov     r9d, 24h ; '$'
0x1800afab7  xor     edx, edx
0x1800afab9  mov     ecx, ebx
0x1800afabb  call    Log_HREvent_34
0x1800afac0  mov     rcx, r14; lpCriticalSection
0x1800afac3  call    cs:__imp_LeaveCriticalSection
0x1800afac9  jmp     loc_1800AFD18
0x1800aface  mov     r8, [rdi+70h]
0x1800afad2  lea     r9, [rbp+arg_8]
0x1800afad6  mov     rdx, [rdi+68h]
0x1800afada  lea     rcx, [rbp+fPending]
0x1800afade  call    ??$find@V?$_ArrayIt@V?$CComPtr@VServiceDataSession@@@ATL@@@utl@@PEAVServiceDataSession@@@utl@@YA?AV?$_ArrayIt@V?$CComPtr@VServiceDataSession@@@ATL@@@0@V10@0AEBQEAVServiceDataSession@@@Z; utl::find<utl::_ArrayIt<ATL::CComPtr<ServiceDataSession>>,ServiceDataSession *>(utl::_ArrayIt<ATL::CComPtr<ServiceDataSession>>,utl::_ArrayIt<ATL::CComPtr<ServiceDataSession>>,ServiceDataSession * const &)
0x1800afae3  cmp     r8, [rax]
0x1800afae6  jz      short loc_1800AFAF5
0x1800afae8  mov     ebx, 800710DDh
0x1800afaed  mov     r9d, 2Ah ; '*'
0x1800afaf3  jmp     short loc_1800AFAB7
0x1800afaf5  mov     rdx, r12
0x1800afaf8  lea     rcx, [rbp+fPending]
0x1800afafc  call    ??0?$CComPtrBase@VChatOpenedWorkItem@RcsComposingStatusTracker@@@ATL@@IEAA@PEAVChatOpenedWorkItem@RcsComposingStatusTracker@@@Z; ATL::CComPtrBase<RcsComposingStatusTracker::ChatOpenedWorkItem>::CComPtrBase<RcsComposingStatusTracker::ChatOpenedWorkItem>(RcsComposingStatusTracker::ChatOpenedWorkItem *)
0x1800afb01  lea     rdx, [rbp+fPending]
0x1800afb05  lea     rcx, [rdi+68h]
0x1800afb09  call    ?push_back@?$vector@V?$CComPtr@VEmailServerSearchJob@@@ATL@@V?$allocator@V?$CComPtr@VEmailServerSearchJob@@@ATL@@@utl@@@utl@@QEAA_N$$QEAV?$CComPtr@VEmailServerSearchJob@@@ATL@@@Z; utl::vector<ATL::CComPtr<EmailServerSearchJob>,utl::allocator<ATL::CComPtr<EmailServerSearchJob>>>::push_back(ATL::CComPtr<EmailServerSearchJob> &&)
0x1800afb0e  lea     rcx, [rbp+fPending]
0x1800afb12  mov     bl, al
0x1800afb14  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800afb19  xor     r12d, r12d
0x1800afb1c  test    bl, bl
0x1800afb1e  jnz     short loc_1800AFB2C
0x1800afb20  mov     ebx, 8007000Eh
0x1800afb25  lea     r9d, [r12+2Ch]
0x1800afb2a  jmp     short loc_1800AFAB7
0x1800afb2c  mov     rcx, r14; lpCriticalSection
0x1800afb2f  call    cs:__imp_LeaveCriticalSection
0x1800afb35  cmp     [rdi+80h], r12d
0x1800afb3c  jnz     loc_1800AFD15
0x1800afb42  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800afb4a  lea     rdx, [rbp+fPending]
0x1800afb4e  lea     rcx, [rbp+var_28]
0x1800afb52  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFFh
0x1800afb5a  movdqu  [rbp+var_28], xmm0
0x1800afb5f  mov     dword ptr [rbp+fPending], 0FFFFFFFFh
0x1800afb66  call    ??$emplace_back@I$0A@@?$vector@KV?$allocator@K@utl@@@utl@@QEAA_N$$QEAI@Z; utl::vector<ulong,utl::allocator<ulong>>::emplace_back<uint,0>(uint &&)
0x1800afb6b  test    al, al
0x1800afb6d  jnz     short loc_1800AFB91
0x1800afb6f  mov     r9d, 32h ; '2'
0x1800afb75  mov     ebx, 8007000Eh
0x1800afb7a  xor     edx, edx
0x1800afb7c  mov     ecx, ebx
0x1800afb7e  call    Log_HREvent_34
0x1800afb83  lea     rcx, [rbp+var_28]
0x1800afb87  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x1800afb8c  jmp     loc_1800AFD18
0x1800afb91  lea     rdx, [rbp+fPending]
0x1800afb95  mov     dword ptr [rbp+fPending], 3
0x1800afb9c  lea     rcx, [rbp+var_28]
0x1800afba0  call    ??$emplace_back@I$0A@@?$vector@KV?$allocator@K@utl@@@utl@@QEAA_N$$QEAI@Z; utl::vector<ulong,utl::allocator<ulong>>::emplace_back<uint,0>(uint &&)
0x1800afba5  test    al, al
0x1800afba7  jnz     short loc_1800AFBB1
0x1800afba9  mov     r9d, 33h ; '3'
0x1800afbaf  jmp     short loc_1800AFB75
0x1800afbb1  lea     rdx, [rbp+fPending]
0x1800afbb5  mov     dword ptr [rbp+fPending], 4
0x1800afbbc  lea     rcx, [rbp+var_28]
0x1800afbc0  call    ??$emplace_back@I$0A@@?$vector@KV?$allocator@K@utl@@@utl@@QEAA_N$$QEAI@Z; utl::vector<ulong,utl::allocator<ulong>>::emplace_back<uint,0>(uint &&)
0x1800afbc5  test    al, al
0x1800afbc7  jnz     short loc_1800AFBD1
0x1800afbc9  mov     r9d, 34h ; '4'
0x1800afbcf  jmp     short loc_1800AFB75
0x1800afbd1  mov     rcx, [r15]
0x1800afbd4  mov     r9, rdi
0x1800afbd7  mov     r8, qword ptr [rbp+var_28]
0x1800afbdb  mov     rdx, qword ptr [rbp+var_28+8]
0x1800afbdf  sub     rdx, r8
0x1800afbe2  mov     rax, [rcx]
0x1800afbe5  sar     rdx, 2
0x1800afbe9  mov     rax, [rax+0B8h]
0x1800afbf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afbf5  mov     ebx, eax
0x1800afbf7  test    eax, eax
0x1800afbf9  jns     short loc_1800AFC0A
0x1800afbfb  mov     r9d, 36h ; '6'
0x1800afc01  mov     edx, esi
0x1800afc03  mov     ecx, eax
0x1800afc05  jmp     loc_1800AFB7E
0x1800afc0a  mov     [rdi+80h], esi
0x1800afc10  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits, 20h
0x1800afc17  jz      short loc_1800AFC28
0x1800afc19  mov     r8, rdi
0x1800afc1c  lea     rdx, ChatStoreChangedAdvise
0x1800afc23  call    McTemplateU0x_EventWriteTransfer
0x1800afc28  lea     r14, stru_18015DCD8
0x1800afc2f  mov     dword ptr [rbp+fPending], r12d
0x1800afc33  mov     rcx, r14; lpInitOnce
0x1800afc36  mov     [rbp+Context], r12
0x1800afc3a  lea     r9, [rbp+Context]; lpContext
0x1800afc3e  xor     edx, edx; dwFlags
0x1800afc40  lea     r8, [rbp+fPending]; fPending
0x1800afc44  call    cs:__imp_InitOnceBeginInitialize
0x1800afc4a  mov     rbx, [rbp+Context]
0x1800afc4e  lea     rsi, qword_18015DCE0
0x1800afc55  test    rbx, rbx
0x1800afc58  jnz     short loc_1800AFC80
0x1800afc5a  mov     rcx, rsi; this
0x1800afc5d  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800afc62  mov     r8, rsi; lpContext
0x1800afc65  mov     [rbp+arg_18], r12
0x1800afc69  xor     edx, edx; dwFlags
0x1800afc6b  mov     rcx, r14; lpInitOnce
0x1800afc6e  call    cs:__imp_InitOnceComplete
0x1800afc74  lea     rcx, [rbp+arg_18]
0x1800afc78  mov     rbx, rsi
0x1800afc7b  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800afc80  lea     rcx, [rbx+0F0h]; this
0x1800afc87  lea     rdx, [rdi+8]; struct RcsFileTransferProgressChangeNotification *
0x1800afc8b  call    ?RegisterForFileTransferProgressChanges@RcsFileTransferProgressTracker@@QEAAJPEAURcsFileTransferProgressChangeNotification@@@Z; RcsFileTransferProgressTracker::RegisterForFileTransferProgressChanges(RcsFileTransferProgressChangeNotification *)
0x1800afc90  test    eax, eax
0x1800afc92  jns     short loc_1800AFCA1
0x1800afc94  xor     edx, edx
0x1800afc96  mov     ecx, eax
0x1800afc98  lea     r9d, [rdx+3Eh]
0x1800afc9c  call    Log_HREvent_34
0x1800afca1  lea     r9, [rbp+Context]; lpContext
0x1800afca5  mov     dword ptr [rbp+fPending], r12d
0x1800afca9  lea     r8, [rbp+fPending]; fPending
0x1800afcad  mov     [rbp+Context], r12
0x1800afcb1  xor     edx, edx; dwFlags
0x1800afcb3  mov     rcx, r14; lpInitOnce
0x1800afcb6  call    cs:__imp_InitOnceBeginInitialize
0x1800afcbc  mov     rbx, [rbp+Context]
0x1800afcc0  test    rbx, rbx
0x1800afcc3  jnz     short loc_1800AFCEB
0x1800afcc5  mov     rcx, rsi; this
0x1800afcc8  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800afccd  mov     r8, rsi; lpContext
0x1800afcd0  mov     [rbp+arg_18], r12
0x1800afcd4  xor     edx, edx; dwFlags
0x1800afcd6  mov     rcx, r14; lpInitOnce
0x1800afcd9  call    cs:__imp_InitOnceComplete
0x1800afcdf  lea     rcx, [rbp+arg_18]
0x1800afce3  mov     rbx, rsi
0x1800afce6  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800afceb  lea     rcx, [rbx+2D0h]; this
0x1800afcf2  lea     rdx, [rdi+8]; struct RcsFileTransferProgressChangeNotification *
0x1800afcf6  call    ?RegisterForFileTransferProgressChanges@RcsMultipartMessageTracker@@QEAAJPEAURcsFileTransferProgressChangeNotification@@@Z; RcsMultipartMessageTracker::RegisterForFileTransferProgressChanges(RcsFileTransferProgressChangeNotification *)
0x1800afcfb  test    eax, eax
0x1800afcfd  jns     short loc_1800AFD0C
0x1800afcff  xor     edx, edx
0x1800afd01  mov     ecx, eax
0x1800afd03  lea     r9d, [rdx+41h]
0x1800afd07  call    Log_HREvent_34
0x1800afd0c  lea     rcx, [rbp+var_28]
0x1800afd10  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x1800afd15  mov     ebx, r12d
0x1800afd18  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800afd1c  call    cs:__imp_LeaveCriticalSection
0x1800afd22  mov     eax, ebx
0x1800afd24  add     rsp, 58h
0x1800afd28  pop     r15
0x1800afd2a  pop     r14
0x1800afd2c  pop     r13
0x1800afd2e  pop     r12
0x1800afd30  pop     rdi
0x1800afd31  pop     rsi
0x1800afd32  pop     rbx
0x1800afd33  pop     rbp
0x1800afd34  retn
```
