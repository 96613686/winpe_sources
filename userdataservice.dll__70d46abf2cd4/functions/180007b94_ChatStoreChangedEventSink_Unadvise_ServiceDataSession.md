# ChatStoreChangedEventSink::Unadvise(ServiceDataSession *)

- ea: `0x180007b94`
- end: `0x180007df1`
- name: `?Unadvise@ChatStoreChangedEventSink@@QEAAXPEAVServiceDataSession@@@Z`
- size: `605`
- prototype: `void __fastcall(ChatStoreChangedEventSink *__hidden this, struct ServiceDataSession *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180005fa0`

## callees

- `0x1800072f4`
- `0x180007b94`
- `0x180069b08`
- `0x18006db44`
- `0x180072ccc`
- `0x1800889b4`
- `0x1800aa2c8`
- `0x1800ee264`
- `0x1800eefdc`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007cc8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007dda`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007cc8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180007dda`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180007c9e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180007d1a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180007c9e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180007d1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007c40`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180007c40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007bb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007bc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007bb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007bc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007bdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007be5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007bdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007be5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c4a`

## pseudocode

```c
void __fastcall ChatStoreChangedEventSink::Unadvise(ChatStoreChangedEventSink *this, struct ServiceDataSession *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  struct ServiceDataSession **v5; // r8
  signed int LastError; // eax
  __int64 v7; // r8
  bool v8; // sf
  __int64 *v9; // rbx
  int v10; // eax
  __int64 v11; // r8
  __int64 *v12; // r14
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  WINBOOL fPending; // [rsp+70h] [rbp+40h] BYREF
  LPVOID Context; // [rsp+80h] [rbp+50h] BYREF
  char *v18; // [rsp+88h] [rbp+58h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = (struct ServiceDataSession **)*((_QWORD *)this + 13);
  if ( v5 != *((struct ServiceDataSession ***)this + 14) )
  {
    while ( *((struct ServiceDataSession ***)this + 14) != v5 )
    {
      if ( *v5 == a2 )
      {
        if ( *((struct ServiceDataSession ***)this + 14) == v5 )
          break;
        utl::vector<ATL::CComPtr<ServiceDataSession>,utl::allocator<ATL::CComPtr<ServiceDataSession>>>::erase(
          (char *)this + 104,
          &fPending,
          v5);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
        if ( *((_QWORD *)this + 13) == *((_QWORD *)this + 14) && *((_DWORD *)this + 32) )
        {
          v13 = (*(__int64 (__fastcall **)(_QWORD, ChatStoreChangedEventSink *))(**((_QWORD **)this + 2) + 192LL))(
                  *((_QWORD *)this + 2),
                  this);
          if ( v13 < 0 )
            Log_HREvent_34((unsigned int)v13, 0, v15, 97);
          *((_DWORD *)this + 32) = 0;
          if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x20) != 0 )
            McTemplateU0x_EventWriteTransfer(v14, ChatStoreChangedUnadvise, this);
          ATL::CComPtrBase<IPOutlookItemCollection2>::Release((char *)this + 16);
          fPending = 0;
          Context = 0;
          InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
          v9 = (__int64 *)Context;
          if ( !Context )
          {
            RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
            v18 = 0;
            InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
            v9 = qword_18015DCE0;
            tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v18);
          }
          v10 = RcsFileTransferProgressTracker::UnregisterFromFileTransferProgressChanges(
                  (RcsFileTransferProgressTracker *)(v9 + 30),
                  (ChatStoreChangedEventSink *)((char *)this + 8));
          if ( v10 < 0 )
            Log_HREvent_34((unsigned int)v10, 0, v11, 106);
          fPending = 0;
          Context = 0;
          InitOnceBeginInitialize(&stru_18015DCD8, 0, &fPending, &Context);
          v12 = (__int64 *)Context;
          if ( !Context )
          {
            RcsServiceManager::RcsServiceManager((RcsServiceManager *)qword_18015DCE0);
            v18 = 0;
            InitOnceComplete(&stru_18015DCD8, 0, qword_18015DCE0);
            v12 = qword_18015DCE0;
            tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v18);
          }
          v18 = (char *)this + 8;
          EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 94));
          utl::list<RcsFileTransferProgressChangeNotification *,utl::allocator<RcsFileTransferProgressChangeNotification *>>::remove(
            v12 + 100,
            &v18);
          LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 94));
        }
        LeaveCriticalSection(v2);
        if ( WaitForSingleObject(*((HANDLE *)this + 17), 0xFFFFFFFF) )
        {
          LastError = GetLastError();
          v8 = LastError < 0;
          if ( LastError > 0 )
          {
            LastError = (unsigned __int16)LastError | 0x80070000;
            v8 = LastError < 0;
          }
          if ( v8 )
            Log_HREvent_34((unsigned int)LastError, 0, v7, 113);
        }
        return;
      }
      ++v5;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180007b94  push    rbp
0x180007b96  push    rbx
0x180007b97  push    rsi
0x180007b98  push    rdi
0x180007b99  push    r13
0x180007b9b  push    r14
0x180007b9d  push    r15
0x180007b9f  mov     rbp, rsp
0x180007ba2  sub     rsp, 30h
0x180007ba6  lea     rdi, [rcx+40h]
0x180007baa  mov     rsi, rcx
0x180007bad  mov     rcx, rdi; lpCriticalSection
0x180007bb0  mov     r15, rdx
0x180007bb3  call    cs:__imp_EnterCriticalSection
0x180007bb9  lea     rbx, [rsi+18h]
0x180007bbd  mov     rcx, rbx; lpCriticalSection
0x180007bc0  call    cs:__imp_EnterCriticalSection
0x180007bc6  lea     r14, [rsi+68h]
0x180007bca  mov     r8, [r14]
0x180007bcd  cmp     r8, [r14+8]
0x180007bd1  jz      short loc_180007BD9
0x180007bd3  cmp     [r14+8], r8
0x180007bd7  jnz     short loc_180007BFA
0x180007bd9  mov     rcx, rbx; lpCriticalSection
0x180007bdc  call    cs:__imp_LeaveCriticalSection
0x180007be2  mov     rcx, rdi; lpCriticalSection
0x180007be5  call    cs:__imp_LeaveCriticalSection
0x180007beb  add     rsp, 30h
0x180007bef  pop     r15
0x180007bf1  pop     r14
0x180007bf3  pop     r13
0x180007bf5  pop     rdi
0x180007bf6  pop     rsi
0x180007bf7  pop     rbx
0x180007bf8  pop     rbp
0x180007bf9  retn
0x180007bfa  cmp     [r8], r15
0x180007bfd  jz      short loc_180007C05
0x180007bff  add     r8, 8
0x180007c03  jmp     short loc_180007BD3
0x180007c05  cmp     [r14+8], r8
0x180007c09  jz      short loc_180007BD9
0x180007c0b  lea     rdx, [rbp+fPending]
0x180007c0f  mov     rcx, r14
0x180007c12  call    ?erase@?$vector@V?$CComPtr@VServiceDataSession@@@ATL@@V?$allocator@V?$CComPtr@VServiceDataSession@@@ATL@@@utl@@@utl@@QEAA?AV?$_ArrayIt@V?$CComPtr@VServiceDataSession@@@ATL@@@2@V?$_ArrayConstIt@V?$CComPtr@VServiceDataSession@@@ATL@@@2@@Z; utl::vector<ATL::CComPtr<ServiceDataSession>,utl::allocator<ATL::CComPtr<ServiceDataSession>>>::erase(utl::_ArrayConstIt<ATL::CComPtr<ServiceDataSession>>)
0x180007c17  mov     rcx, rbx; lpCriticalSection
0x180007c1a  call    cs:__imp_LeaveCriticalSection
0x180007c20  mov     rax, [r14+8]
0x180007c24  cmp     [r14], rax
0x180007c27  jz      loc_180007D5F
0x180007c2d  mov     rcx, rdi; lpCriticalSection
0x180007c30  call    cs:__imp_LeaveCriticalSection
0x180007c36  mov     rcx, [rsi+88h]; hHandle
0x180007c3d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007c40  call    cs:__imp_WaitForSingleObject
0x180007c46  test    eax, eax
0x180007c48  jz      short loc_180007BEB
0x180007c4a  call    cs:__imp_GetLastError
0x180007c50  test    eax, eax
0x180007c52  jle     short loc_180007C5E
0x180007c54  movzx   eax, ax
0x180007c57  or      eax, 80070000h
0x180007c5c  test    eax, eax
0x180007c5e  jns     short loc_180007BEB
0x180007c60  xor     edx, edx
0x180007c62  mov     ecx, eax
0x180007c64  lea     r9d, [rdx+71h]
0x180007c68  call    Log_HREvent_34
0x180007c6d  jmp     loc_180007BEB
0x180007c72  lea     rcx, [rsi+10h]
0x180007c76  call    ?Release@?$CComPtrBase@UIPOutlookItemCollection2@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPOutlookItemCollection2>::Release(void)
0x180007c7b  lea     r14, stru_18015DCD8
0x180007c82  mov     [rbp+fPending], 0
0x180007c89  mov     rcx, r14; lpInitOnce
0x180007c8c  mov     [rbp+Context], 0
0x180007c94  lea     r9, [rbp+Context]; lpContext
0x180007c98  xor     edx, edx; dwFlags
0x180007c9a  lea     r8, [rbp+fPending]; fPending
0x180007c9e  call    cs:__imp_InitOnceBeginInitialize
0x180007ca4  mov     rbx, [rbp+Context]
0x180007ca8  lea     r13, qword_18015DCE0
0x180007caf  test    rbx, rbx
0x180007cb2  jnz     short loc_180007CDA
0x180007cb4  mov     rcx, r13; this
0x180007cb7  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x180007cbc  mov     r8, r13; lpContext
0x180007cbf  mov     [rbp+arg_18], rbx
0x180007cc3  xor     edx, edx; dwFlags
0x180007cc5  mov     rcx, r14; lpInitOnce
0x180007cc8  call    cs:__imp_InitOnceComplete
0x180007cce  lea     rcx, [rbp+arg_18]
0x180007cd2  mov     rbx, r13
0x180007cd5  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x180007cda  lea     r15, [rsi+8]
0x180007cde  mov     rdx, r15; struct RcsFileTransferProgressChangeNotification *
0x180007ce1  lea     rcx, [rbx+0F0h]; this
0x180007ce8  call    ?UnregisterFromFileTransferProgressChanges@RcsFileTransferProgressTracker@@QEAAJPEAURcsFileTransferProgressChangeNotification@@@Z; RcsFileTransferProgressTracker::UnregisterFromFileTransferProgressChanges(RcsFileTransferProgressChangeNotification *)
0x180007ced  test    eax, eax
0x180007cef  jns     short loc_180007CFE
0x180007cf1  xor     edx, edx
0x180007cf3  mov     ecx, eax
0x180007cf5  lea     r9d, [rdx+6Ah]
0x180007cf9  call    Log_HREvent_34
0x180007cfe  lea     r9, [rbp+Context]; lpContext
0x180007d02  mov     [rbp+fPending], 0
0x180007d09  lea     r8, [rbp+fPending]; fPending
0x180007d0d  mov     [rbp+Context], 0
0x180007d15  xor     edx, edx; dwFlags
0x180007d17  mov     rcx, r14; lpInitOnce
0x180007d1a  call    cs:__imp_InitOnceBeginInitialize
0x180007d20  mov     r14, [rbp+Context]
0x180007d24  test    r14, r14
0x180007d27  jz      loc_180007DBE
0x180007d2d  lea     rbx, [r14+2F0h]
0x180007d34  mov     [rbp+arg_18], r15
0x180007d38  mov     rcx, rbx; lpCriticalSection
0x180007d3b  call    cs:__imp_EnterCriticalSection
0x180007d41  lea     rcx, [r14+320h]
0x180007d48  lea     rdx, [rbp+arg_18]
0x180007d4c  call    ?remove@?$list@PEAURcsFileTransferProgressChangeNotification@@V?$allocator@PEAURcsFileTransferProgressChangeNotification@@@utl@@@utl@@QEAA_KAEBQEAURcsFileTransferProgressChangeNotification@@@Z; utl::list<RcsFileTransferProgressChangeNotification *,utl::allocator<RcsFileTransferProgressChangeNotification *>>::remove(RcsFileTransferProgressChangeNotification * const &)
0x180007d51  mov     rcx, rbx; lpCriticalSection
0x180007d54  call    cs:__imp_LeaveCriticalSection
0x180007d5a  jmp     loc_180007C2D
0x180007d5f  cmp     dword ptr [rsi+80h], 0
0x180007d66  jz      loc_180007C2D
0x180007d6c  mov     rcx, [rsi+10h]
0x180007d70  mov     rdx, rsi
0x180007d73  mov     rax, [rcx]
0x180007d76  mov     rax, [rax+0C0h]
0x180007d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d82  test    eax, eax
0x180007d84  jns     short loc_180007D93
0x180007d86  xor     edx, edx
0x180007d88  mov     ecx, eax
0x180007d8a  lea     r9d, [rdx+61h]
0x180007d8e  call    Log_HREvent_34
0x180007d93  mov     dword ptr [rsi+80h], 0
0x180007d9d  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits, 20h
0x180007da4  jz      loc_180007C72
0x180007daa  mov     r8, rsi
0x180007dad  lea     rdx, ChatStoreChangedUnadvise
0x180007db4  call    McTemplateU0x_EventWriteTransfer
0x180007db9  jmp     loc_180007C72
0x180007dbe  mov     rcx, r13; this
0x180007dc1  call    ??0RcsServiceManager@@QEAA@XZ; RcsServiceManager::RcsServiceManager(void)
0x180007dc6  mov     r8, r13; lpContext
0x180007dc9  mov     [rbp+arg_18], 0
0x180007dd1  xor     edx, edx; dwFlags
0x180007dd3  lea     rcx, stru_18015DCD8; lpInitOnce
0x180007dda  call    cs:__imp_InitOnceComplete
0x180007de0  lea     rcx, [rbp+arg_18]
0x180007de4  mov     r14, r13
0x180007de7  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x180007dec  jmp     loc_180007D2D
```
