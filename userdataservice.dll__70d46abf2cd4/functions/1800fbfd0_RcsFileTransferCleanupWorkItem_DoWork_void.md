# RcsFileTransferCleanupWorkItem::DoWork(void)

- ea: `0x1800fbfd0`
- end: `0x1800fc2bb`
- name: `?DoWork@RcsFileTransferCleanupWorkItem@@MEAAJXZ`
- size: `747`
- prototype: `__int64 __fastcall(RcsFileTransferCleanupWorkItem *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180008ee8`
- `0x18001f230`
- `0x18006db44`
- `0x180072ccc`
- `0x1800849cc`
- `0x1800a8658`
- `0x1800fbc28`
- `0x1800fbfd0`
- `0x1800fc304`
- `0x1800fc378`
- `0x1800fc594`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fc12a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800fc12a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fc0fb`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800fc0fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fbfe8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fc030`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fbfe8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fc030`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fbffa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fc007`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fc05e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fc06c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fbffa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fc007`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fc05e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fc06c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800fc1f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800fc1f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fc097`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800fc097`

## pseudocode

```c
__int64 __fastcall RcsFileTransferCleanupWorkItem::DoWork(RcsFileTransferCleanupWorkItem *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  __int64 v4; // r8
  unsigned int v5; // edi
  HRESULT ProviderIdForImsClientId; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  const unsigned __int16 *i; // rbx
  RcsServiceManager *v10; // rdi
  int v11; // eax
  __int64 v12; // r8
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  DWORD TickCount; // eax
  unsigned __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  LPVOID ppv; // [rsp+30h] [rbp-40h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-38h] BYREF
  __int64 v23; // [rsp+40h] [rbp-30h] BYREF
  RcsFileTransferCleanupWorkItem *v24; // [rsp+48h] [rbp-28h] BYREF
  char v25; // [rsp+50h] [rbp-20h]
  _QWORD v26[3]; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v27; // [rsp+A0h] [rbp+30h] BYREF
  int v28; // [rsp+A8h] [rbp+38h] BYREF
  WINBOOL fPending; // [rsp+B0h] [rbp+40h] BYREF
  struct ISmMessage *v30; // [rsp+B8h] [rbp+48h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( !*((_DWORD *)this + 32) )
  {
    LeaveCriticalSection(v1);
    return 0;
  }
  LeaveCriticalSection(v1);
  v24 = this;
  v26[0] = v26;
  v25 = 1;
  v26[1] = v26;
  v26[2] = 0;
  EnterCriticalSection(v1);
  if ( !(unsigned __int8)utl::list<RcsFileTransferCleanupWorkItem::TrackingEntry,utl::allocator<RcsFileTransferCleanupWorkItem::TrackingEntry>>::assign(
                           v26,
                           (char *)this + 104) )
  {
    v5 = -2147024882;
    Log_HREvent_63(2147942414LL, 0, v4, 140);
    LeaveCriticalSection(v1);
    goto LABEL_36;
  }
  LeaveCriticalSection(v1);
  ppv = 0;
  ProviderIdForImsClientId = CoCreateInstance(
                               &GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7,
                               0,
                               0x17u,
                               &GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c,
                               &ppv);
  v5 = ProviderIdForImsClientId;
  if ( ProviderIdForImsClientId >= 0 )
  {
    for ( i = (const unsigned __int16 *)v26[0]; ; i = *(const unsigned __int16 **)i )
    {
      if ( i == (const unsigned __int16 *)v26 )
      {
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
        v5 = 0;
        goto LABEL_36;
      }
      v27 = -1;
      fPending = 0;
      Context = 0;
      InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
      v10 = (RcsServiceManager *)Context;
      if ( !Context )
      {
        RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
        v23 = 0;
        InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
        v10 = (RcsServiceManager *)qword_18015DCE0;
        tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v23);
      }
      ProviderIdForImsClientId = RcsServiceManager::GetProviderIdForImsClientId(
                                   v10,
                                   (const struct _GUID *)((char *)this + 132),
                                   &v27);
      v5 = ProviderIdForImsClientId;
      if ( ProviderIdForImsClientId < 0 )
      {
        v8 = 151;
        goto LABEL_7;
      }
      v30 = 0;
      v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, struct ISmMessage **))(*(_QWORD *)ppv + 112LL))(
              ppv,
              v27,
              i + 10,
              &v30);
      v5 = v11;
      if ( v11 < 0 )
      {
        v20 = 157;
        goto LABEL_33;
      }
      if ( !v30 )
        break;
      v28 = 0;
      v11 = (*(__int64 (__fastcall **)(struct ISmMessage *, int *))(*(_QWORD *)v30 + 544LL))(v30, &v28);
      v5 = v11;
      if ( v11 < 0 )
      {
        v20 = 168;
LABEL_33:
        Log_HREvent_63((unsigned int)v11, 1, v12, v20);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v30);
        goto LABEL_8;
      }
      if ( (unsigned int)(v28 - 1) > 1 )
      {
        v13 = RcsFileTransferCleanupWorkItem::RemoveFileTransferFromWatchlist(this, i + 10);
        if ( v13 >= 0 )
          goto LABEL_30;
        v15 = 174;
        goto LABEL_29;
      }
      TickCount = GetTickCount();
      v17 = TickCount - *((_DWORD *)i + 4);
      if ( TickCount < *((_DWORD *)i + 4) )
        v17 = (unsigned int)(v17 - 1);
      if ( (unsigned int)v17 >= 0x2710 )
      {
        v18 = RcsFileTransferCleanupWorkItem::_PerformCleanup((RcsFileTransferCleanupWorkItem *)v17, v30);
        if ( v18 < 0 )
          Log_HREvent_63((unsigned int)v18, 0, v19, 195);
        v13 = RcsFileTransferCleanupWorkItem::RemoveFileTransferFromWatchlist(this, i + 10);
        if ( v13 < 0 )
        {
          v15 = 196;
LABEL_29:
          Log_HREvent_63((unsigned int)v13, 0, v14, v15);
        }
      }
LABEL_30:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v30);
    }
    v13 = RcsFileTransferCleanupWorkItem::RemoveFileTransferFromWatchlist(this, i + 10);
    if ( v13 >= 0 )
      goto LABEL_30;
    v15 = 163;
    goto LABEL_29;
  }
  v8 = 144;
LABEL_7:
  Log_HREvent_63((unsigned int)ProviderIdForImsClientId, 1, v7, v8);
LABEL_8:
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppv);
LABEL_36:
  utl::list<RcsFileTransferCleanupWorkItem::TrackingEntry,utl::allocator<RcsFileTransferCleanupWorkItem::TrackingEntry>>::clear(v26);
  tlx::_UndoSolo__lambda_2cb0a9f5aa973e1337dc2325d65b2f95___::__UndoSolo__lambda_2cb0a9f5aa973e1337dc2325d65b2f95___(&v24);
  return v5;
}

```

## disassembly

```asm
0x1800fbfd0  push    rbp
0x1800fbfd2  push    rbx
0x1800fbfd3  push    rsi
0x1800fbfd4  push    rdi
0x1800fbfd5  push    r14
0x1800fbfd7  mov     rbp, rsp
0x1800fbfda  sub     rsp, 70h
0x1800fbfde  lea     rbx, [rcx+40h]
0x1800fbfe2  mov     rsi, rcx
0x1800fbfe5  mov     rcx, rbx; lpCriticalSection
0x1800fbfe8  call    cs:__imp_EnterCriticalSection
0x1800fbfee  cmp     dword ptr [rsi+80h], 0
0x1800fbff5  mov     rcx, rbx; lpCriticalSection
0x1800fbff8  jnz     short loc_1800FC007
0x1800fbffa  call    cs:__imp_LeaveCriticalSection
0x1800fc000  xor     eax, eax
0x1800fc002  jmp     loc_1800FC2B0
0x1800fc007  call    cs:__imp_LeaveCriticalSection
0x1800fc00d  lea     rax, [rbp+var_18]
0x1800fc011  mov     [rbp+var_28], rsi
0x1800fc015  mov     [rbp+var_18], rax
0x1800fc019  mov     rcx, rbx; lpCriticalSection
0x1800fc01c  lea     rax, [rbp+var_18]
0x1800fc020  mov     [rbp+var_20], 1
0x1800fc024  mov     [rbp+var_10], rax
0x1800fc028  mov     [rbp+var_8], 0
0x1800fc030  call    cs:__imp_EnterCriticalSection
0x1800fc036  lea     rdx, [rsi+68h]
0x1800fc03a  lea     rcx, [rbp+var_18]
0x1800fc03e  call    ?assign@?$list@UTrackingEntry@RcsFileTransferCleanupWorkItem@@V?$allocator@UTrackingEntry@RcsFileTransferCleanupWorkItem@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::list<RcsFileTransferCleanupWorkItem::TrackingEntry,utl::allocator<RcsFileTransferCleanupWorkItem::TrackingEntry>>::assign(utl::list<RcsFileTransferCleanupWorkItem::TrackingEntry,utl::allocator<RcsFileTransferCleanupWorkItem::TrackingEntry>> const &)
0x1800fc043  test    al, al
0x1800fc045  jnz     short loc_1800FC069
0x1800fc047  mov     edi, 8007000Eh
0x1800fc04c  xor     edx, edx
0x1800fc04e  mov     ecx, edi
0x1800fc050  mov     r9d, 8Ch
0x1800fc056  call    Log_HREvent_63
0x1800fc05b  mov     rcx, rbx; lpCriticalSection
0x1800fc05e  call    cs:__imp_LeaveCriticalSection
0x1800fc064  jmp     loc_1800FC29C
0x1800fc069  mov     rcx, rbx; lpCriticalSection
0x1800fc06c  call    cs:__imp_LeaveCriticalSection
0x1800fc072  xor     edx, edx; pUnkOuter
0x1800fc074  mov     [rbp+var_40], 0
0x1800fc07c  lea     rax, [rbp+var_40]
0x1800fc080  lea     r9, _GUID_75b53853_1060_4c3b_921d_0d71ec07ed3c; riid
0x1800fc087  mov     [rsp+70h+ppv], rax; ppv
0x1800fc08c  lea     rcx, _GUID_fb4d76fe_8863_4027_9d8a_4a00bedf74d7; rclsid
0x1800fc093  lea     r8d, [rdx+17h]; dwClsContext
0x1800fc097  call    cs:__imp_CoCreateInstance
0x1800fc09d  mov     edi, eax
0x1800fc09f  test    eax, eax
0x1800fc0a1  jns     short loc_1800FC0C3
0x1800fc0a3  mov     r9d, 90h
0x1800fc0a9  mov     edx, 1
0x1800fc0ae  mov     ecx, eax
0x1800fc0b0  call    Log_HREvent_63
0x1800fc0b5  lea     rcx, [rbp+var_40]
0x1800fc0b9  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800fc0be  jmp     loc_1800FC29C
0x1800fc0c3  mov     rbx, [rbp+var_18]
0x1800fc0c7  lea     rax, [rbp+var_18]
0x1800fc0cb  cmp     rbx, rax
0x1800fc0ce  jz      loc_1800FC291
0x1800fc0d4  lea     r9, [rbp+Context]; lpContext
0x1800fc0d8  mov     [rbp+arg_0], 0FFFFFFFFh
0x1800fc0df  lea     r8, [rbp+fPending]; fPending
0x1800fc0e3  mov     [rbp+fPending], 0
0x1800fc0ea  xor     edx, edx; dwFlags
0x1800fc0ec  mov     [rbp+Context], 0
0x1800fc0f4  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800fc0fb  call    cs:__imp_InitOnceBeginInitialize
0x1800fc101  mov     rdi, [rbp+Context]
0x1800fc105  test    rdi, rdi
0x1800fc108  jnz     short loc_1800FC140
0x1800fc10a  lea     rcx, qword_18015DCE0; this
0x1800fc111  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x1800fc116  lea     r8, qword_18015DCE0; lpContext
0x1800fc11d  mov     [rbp+var_30], rdi
0x1800fc121  xor     edx, edx; dwFlags
0x1800fc123  lea     rcx, stru_18015DCD8; lpInitOnce
0x1800fc12a  call    cs:__imp_InitOnceComplete
0x1800fc130  lea     rcx, [rbp+var_30]
0x1800fc134  lea     rdi, qword_18015DCE0
0x1800fc13b  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800fc140  lea     rdx, [rsi+84h]; struct _GUID *
0x1800fc147  mov     rcx, rdi; this
0x1800fc14a  lea     r8, [rbp+arg_0]; unsigned int *
0x1800fc14e  call    ?GetProviderIdForImsClientId@RcsServiceManager@@QEAAJAEBU_GUID@@AEAK@Z; RcsServiceManager::GetProviderIdForImsClientId(_GUID const &,ulong &)
0x1800fc153  mov     edi, eax
0x1800fc155  test    eax, eax
0x1800fc157  js      loc_1800FC286
0x1800fc15d  mov     rcx, [rbp+var_40]
0x1800fc161  lea     r14, [rbx+14h]
0x1800fc165  mov     edx, [rbp+arg_0]
0x1800fc168  lea     r9, [rbp+arg_18]
0x1800fc16c  mov     [rbp+arg_18], 0
0x1800fc174  mov     r8, r14
0x1800fc177  mov     rax, [rcx]
0x1800fc17a  mov     rax, [rax+70h]
0x1800fc17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc183  mov     edi, eax
0x1800fc185  test    eax, eax
0x1800fc187  js      loc_1800FC266
0x1800fc18d  mov     rcx, [rbp+arg_18]
0x1800fc191  test    rcx, rcx
0x1800fc194  jnz     short loc_1800FC1B4
0x1800fc196  mov     rdx, r14; unsigned __int16 *
0x1800fc199  mov     rcx, rsi; this
0x1800fc19c  call    ?RemoveFileTransferFromWatchlist@RcsFileTransferCleanupWorkItem@@QEAAJPEBG@Z; RcsFileTransferCleanupWorkItem::RemoveFileTransferFromWatchlist(ushort const *)
0x1800fc1a1  test    eax, eax
0x1800fc1a3  jns     loc_1800FC24D
0x1800fc1a9  mov     r9d, 0A3h
0x1800fc1af  jmp     loc_1800FC244
0x1800fc1b4  mov     [rbp+arg_8], 0
0x1800fc1bb  lea     rdx, [rbp+arg_8]
0x1800fc1bf  mov     rax, [rcx]
0x1800fc1c2  mov     rax, [rax+220h]
0x1800fc1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc1ce  mov     edi, eax
0x1800fc1d0  test    eax, eax
0x1800fc1d2  js      loc_1800FC25E
0x1800fc1d8  mov     eax, [rbp+arg_8]
0x1800fc1db  dec     eax
0x1800fc1dd  cmp     eax, 1
0x1800fc1e0  jbe     short loc_1800FC1F9
0x1800fc1e2  mov     rdx, r14; unsigned __int16 *
0x1800fc1e5  mov     rcx, rsi; this
0x1800fc1e8  call    ?RemoveFileTransferFromWatchlist@RcsFileTransferCleanupWorkItem@@QEAAJPEBG@Z; RcsFileTransferCleanupWorkItem::RemoveFileTransferFromWatchlist(ushort const *)
0x1800fc1ed  test    eax, eax
0x1800fc1ef  jns     short loc_1800FC24D
0x1800fc1f1  mov     r9d, 0AEh
0x1800fc1f7  jmp     short loc_1800FC244
0x1800fc1f9  call    cs:__imp_GetTickCount
0x1800fc1ff  mov     ecx, eax
0x1800fc201  sub     ecx, [rbx+10h]
0x1800fc204  cmp     eax, [rbx+10h]
0x1800fc207  jnb     short loc_1800FC20B
0x1800fc209  dec     ecx; this
0x1800fc20b  cmp     ecx, 2710h
0x1800fc211  jb      short loc_1800FC24D
0x1800fc213  mov     rdx, [rbp+arg_18]; struct ISmMessage *
0x1800fc217  call    ?_PerformCleanup@RcsFileTransferCleanupWorkItem@@IEAAJPEAUISmMessage@@@Z; RcsFileTransferCleanupWorkItem::_PerformCleanup(ISmMessage *)
0x1800fc21c  test    eax, eax
0x1800fc21e  jns     short loc_1800FC22F
0x1800fc220  xor     edx, edx
0x1800fc222  mov     r9d, 0C3h
0x1800fc228  mov     ecx, eax
0x1800fc22a  call    Log_HREvent_63
0x1800fc22f  mov     rdx, r14; unsigned __int16 *
0x1800fc232  mov     rcx, rsi; this
0x1800fc235  call    ?RemoveFileTransferFromWatchlist@RcsFileTransferCleanupWorkItem@@QEAAJPEBG@Z; RcsFileTransferCleanupWorkItem::RemoveFileTransferFromWatchlist(ushort const *)
0x1800fc23a  test    eax, eax
0x1800fc23c  jns     short loc_1800FC24D
0x1800fc23e  mov     r9d, 0C4h
0x1800fc244  xor     edx, edx
0x1800fc246  mov     ecx, eax
0x1800fc248  call    Log_HREvent_63
0x1800fc24d  lea     rcx, [rbp+arg_18]
0x1800fc251  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800fc256  mov     rbx, [rbx]
0x1800fc259  jmp     loc_1800FC0C7
0x1800fc25e  mov     r9d, 0A8h
0x1800fc264  jmp     short loc_1800FC26C
0x1800fc266  mov     r9d, 9Dh
0x1800fc26c  mov     edx, 1
0x1800fc271  mov     ecx, eax
0x1800fc273  call    Log_HREvent_63
0x1800fc278  lea     rcx, [rbp+arg_18]
0x1800fc27c  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800fc281  jmp     loc_1800FC0B5
0x1800fc286  mov     r9d, 97h
0x1800fc28c  jmp     loc_1800FC0A9
0x1800fc291  lea     rcx, [rbp+var_40]
0x1800fc295  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800fc29a  xor     edi, edi
0x1800fc29c  lea     rcx, [rbp+var_18]
0x1800fc2a0  call    ?clear@?$list@UTrackingEntry@RcsFileTransferCleanupWorkItem@@V?$allocator@UTrackingEntry@RcsFileTransferCleanupWorkItem@@@utl@@@utl@@QEAAXXZ; utl::list<RcsFileTransferCleanupWorkItem::TrackingEntry,utl::allocator<RcsFileTransferCleanupWorkItem::TrackingEntry>>::clear(void)
0x1800fc2a5  lea     rcx, [rbp+var_28]
0x1800fc2a9  call    tlx___UndoSolo__lambda_2cb0a9f5aa973e1337dc2325d65b2f95_______UndoSolo__lambda_2cb0a9f5aa973e1337dc2325d65b2f95___
0x1800fc2ae  mov     eax, edi
0x1800fc2b0  add     rsp, 70h
0x1800fc2b4  pop     r14
0x1800fc2b6  pop     rdi
0x1800fc2b7  pop     rsi
0x1800fc2b8  pop     rbx
0x1800fc2b9  pop     rbp
0x1800fc2ba  retn
```
