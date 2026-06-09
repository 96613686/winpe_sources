# ChatStoreChangedEventSink::_Uninitialize(void)

- ea: `0x18002d424`
- end: `0x18002d5dc`
- name: `?_Uninitialize@ChatStoreChangedEventSink@@AEAAXXZ`
- size: `440`
- prototype: `void __fastcall(ChatStoreChangedEventSink *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e800`

## callees

- `0x18002d424`
- `0x18002d6a4`
- `0x18006db44`
- `0x180072ccc`
- `0x1800889b4`
- `0x1800ee264`
- `0x1800f2398`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002d4db`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002d557`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002d4db`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002d557`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002d4ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002d530`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002d4ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002d530`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d43e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d43e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d5d5`

## pseudocode

```c
void __fastcall ChatStoreChangedEventSink::_Uninitialize(ChatStoreChangedEventSink *this)
{
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // r8
  __int64 *v5; // rdi
  int v6; // eax
  __int64 v7; // r8
  __int64 *v8; // rdi
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  WINBOOL fPending; // [rsp+60h] [rbp+30h] BYREF
  LPVOID Context; // [rsp+68h] [rbp+38h] BYREF
  __int64 v16; // [rsp+70h] [rbp+40h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v2 = *((_QWORD *)this + 2);
  if ( v2 && *((_DWORD *)this + 32) )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, ChatStoreChangedEventSink *))(*(_QWORD *)v2 + 192LL))(v2, this);
    if ( v3 < 0 )
      Log_HREvent_34((unsigned int)v3, 0, v4, 237);
    *((_DWORD *)this + 32) = 0;
    fPending = 0;
    Context = 0;
    InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
    v5 = (__int64 *)Context;
    if ( !Context )
    {
      RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
      v16 = 0;
      InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
      v5 = qword_18015DCE0;
      tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v16);
    }
    v6 = RcsFileTransferProgressTracker::UnregisterFromFileTransferProgressChanges(
           (RcsFileTransferProgressTracker *)(v5 + 30),
           (ChatStoreChangedEventSink *)((char *)this + 8));
    if ( v6 < 0 )
      Log_HREvent_34((unsigned int)v6, 0, v7, 242);
    fPending = 0;
    Context = 0;
    InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
    v8 = (__int64 *)Context;
    if ( !Context )
    {
      RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
      v16 = 0;
      InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
      v8 = qword_18015DCE0;
      tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v16);
    }
    v9 = RcsMultipartMessageTracker::RegisterForFileTransferProgressChanges(
           (RcsMultipartMessageTracker *)(v8 + 90),
           (ChatStoreChangedEventSink *)((char *)this + 8));
    if ( v9 < 0 )
      Log_HREvent_34((unsigned int)v9, 0, v10, 245);
  }
  v11 = *((_QWORD *)this + 2);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *((_QWORD *)this + 2) = 0;
  }
  v12 = *((_QWORD *)this + 13);
  v13 = *((_QWORD *)this + 14) - v12;
  *((_QWORD *)this + 14) = v12;
  utl::_RangeDestroyApc<utl::allocator<ATL::CComPtr<ChatApp>>>(v11, v12, v13 >> 3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
}

```

## disassembly

```asm
0x18002d424  mov     [rsp-28h+arg_18], rbx
0x18002d429  push    rbp
0x18002d42a  push    rsi
0x18002d42b  push    rdi
0x18002d42c  push    r12
0x18002d42e  push    r14
0x18002d430  mov     rbp, rsp
0x18002d433  sub     rsp, 30h
0x18002d437  mov     rbx, rcx
0x18002d43a  add     rcx, 40h ; '@'; lpCriticalSection
0x18002d43e  call    cs:__imp_EnterCriticalSection
0x18002d444  mov     rcx, [rbx+10h]
0x18002d448  test    rcx, rcx
0x18002d44b  jz      loc_18002D58C
0x18002d451  cmp     dword ptr [rbx+80h], 0
0x18002d458  jz      loc_18002D58C
0x18002d45e  mov     rax, [rcx]
0x18002d461  mov     rdx, rbx
0x18002d464  mov     rax, [rax+0C0h]
0x18002d46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d470  test    eax, eax
0x18002d472  jns     short loc_18002D483
0x18002d474  xor     edx, edx
0x18002d476  mov     r9d, 0EDh
0x18002d47c  mov     ecx, eax
0x18002d47e  call    Log_HREvent_34
0x18002d483  lea     r9, [rbp+Context]; lpContext
0x18002d487  mov     dword ptr [rbx+80h], 0
0x18002d491  lea     r8, [rbp+fPending]; fPending
0x18002d495  mov     [rbp+fPending], 0
0x18002d49c  xor     edx, edx; dwFlags
0x18002d49e  mov     [rbp+Context], 0
0x18002d4a6  lea     rcx, stru_18015DCD8; lpInitOnce
0x18002d4ad  call    cs:__imp_InitOnceBeginInitialize
0x18002d4b3  mov     rdi, [rbp+Context]
0x18002d4b7  lea     r12, qword_18015DCE0
0x18002d4be  test    rdi, rdi
0x18002d4c1  jnz     short loc_18002D4ED
0x18002d4c3  mov     rcx, r12; this
0x18002d4c6  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x18002d4cb  mov     r8, r12; lpContext
0x18002d4ce  mov     [rbp+arg_10], rdi
0x18002d4d2  xor     edx, edx; dwFlags
0x18002d4d4  lea     rcx, stru_18015DCD8; lpInitOnce
0x18002d4db  call    cs:__imp_InitOnceComplete
0x18002d4e1  lea     rcx, [rbp+arg_10]
0x18002d4e5  mov     rdi, r12
0x18002d4e8  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x18002d4ed  lea     rcx, [rdi+0F0h]; this
0x18002d4f4  lea     rdx, [rbx+8]; struct RcsFileTransferProgressChangeNotification *
0x18002d4f8  call    ?UnregisterFromFileTransferProgressChanges@RcsFileTransferProgressTracker@@QEAAJPEAURcsFileTransferProgressChangeNotification@@@Z; RcsFileTransferProgressTracker::UnregisterFromFileTransferProgressChanges(RcsFileTransferProgressChangeNotification *)
0x18002d4fd  test    eax, eax
0x18002d4ff  jns     short loc_18002D510
0x18002d501  xor     edx, edx
0x18002d503  mov     r9d, 0F2h
0x18002d509  mov     ecx, eax
0x18002d50b  call    Log_HREvent_34
0x18002d510  lea     r9, [rbp+Context]; lpContext
0x18002d514  mov     [rbp+fPending], 0
0x18002d51b  lea     r8, [rbp+fPending]; fPending
0x18002d51f  mov     [rbp+Context], 0
0x18002d527  xor     edx, edx; dwFlags
0x18002d529  lea     rcx, stru_18015DCD8; lpInitOnce
0x18002d530  call    cs:__imp_InitOnceBeginInitialize
0x18002d536  mov     rdi, [rbp+Context]
0x18002d53a  test    rdi, rdi
0x18002d53d  jnz     short loc_18002D569
0x18002d53f  mov     rcx, r12; this
0x18002d542  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x18002d547  mov     r8, r12; lpContext
0x18002d54a  mov     [rbp+arg_10], rdi
0x18002d54e  xor     edx, edx; dwFlags
0x18002d550  lea     rcx, stru_18015DCD8; lpInitOnce
0x18002d557  call    cs:__imp_InitOnceComplete
0x18002d55d  lea     rcx, [rbp+arg_10]
0x18002d561  mov     rdi, r12
0x18002d564  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x18002d569  lea     rcx, [rdi+2D0h]; this
0x18002d570  lea     rdx, [rbx+8]; struct RcsFileTransferProgressChangeNotification *
0x18002d574  call    ?RegisterForFileTransferProgressChanges@RcsMultipartMessageTracker@@QEAAJPEAURcsFileTransferProgressChangeNotification@@@Z; RcsMultipartMessageTracker::RegisterForFileTransferProgressChanges(RcsFileTransferProgressChangeNotification *)
0x18002d579  test    eax, eax
0x18002d57b  jns     short loc_18002D58C
0x18002d57d  xor     edx, edx
0x18002d57f  mov     r9d, 0F5h
0x18002d585  mov     ecx, eax
0x18002d587  call    Log_HREvent_34
0x18002d58c  mov     rcx, [rbx+10h]
0x18002d590  test    rcx, rcx
0x18002d593  jz      short loc_18002D5A9
0x18002d595  mov     rax, [rcx]
0x18002d598  mov     rax, [rax+10h]
0x18002d59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5a1  mov     qword ptr [rbx+10h], 0
0x18002d5a9  mov     rdx, [rbx+68h]
0x18002d5ad  mov     r8, [rbx+70h]
0x18002d5b1  sub     r8, rdx
0x18002d5b4  mov     [rbx+70h], rdx
0x18002d5b8  sar     r8, 3
0x18002d5bc  call    ??$_RangeDestroyApc@V?$allocator@V?$CComPtr@VChatApp@@@ATL@@@utl@@@utl@@YAXAEAV?$allocator@V?$CComPtr@VChatApp@@@ATL@@@0@PEAV?$CComPtr@VChatApp@@@ATL@@_K@Z; utl::_RangeDestroyApc<utl::allocator<ATL::CComPtr<ChatApp>>>(utl::allocator<ATL::CComPtr<ChatApp>> &,ATL::CComPtr<ChatApp> *,unsigned __int64)
0x18002d5c1  lea     rcx, [rbx+40h]
0x18002d5c5  mov     rbx, [rsp+30h+arg_18]
0x18002d5ca  add     rsp, 30h
0x18002d5ce  pop     r14
0x18002d5d0  pop     r12
0x18002d5d2  pop     rdi
0x18002d5d3  pop     rsi
0x18002d5d4  pop     rbp
0x18002d5d5  jmp     cs:__imp_LeaveCriticalSection
```
