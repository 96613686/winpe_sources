# WorkThreadManager::CThread::ThreadProc(void)

- ea: `0x180019474`
- end: `0x18001972c`
- name: `?ThreadProc@CThread@WorkThreadManager@@AEAAXXZ`
- size: `696`
- prototype: `void __fastcall(WorkThreadManager::CThread *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180018624`
- `0x180019430`

## callees

- `0x18000a6a0`
- `0x18000d6bc`
- `0x18000f808`
- `0x18000f888`
- `0x180019474`
- `0x180019734`
- `0x180019840`
- `0x180019918`
- `0x180019bd4`
- `0x180019cc0`
- `0x180019cec`
- `0x180019e38`
- `0x180068720`
- `0x18006cfb0`
- `0x18006d148`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019720`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180019720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019487`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019487`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800196ff`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800196ff`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800195d0`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x180019605`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x180019605`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x18001962d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x18001962d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180019652`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180019652`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x180019637`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x180019637`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WorkThreadManager::CThread::ThreadProc(WorkThreadManager::CThread *this)
{
  DWORD CurrentThreadId; // eax
  _lambda_103564c3136a6d89c1bf4e8d5a4b0eab_ *v3; // rax
  int v4; // eax
  void *v5; // rdx
  wil::details *v6; // rcx
  WorkThreadManager::TaskData *v7; // rcx
  bool v8; // di
  bool v9; // zf
  void *v10; // rcx
  void *v11; // rdx
  wil::details *v12; // rcx
  __int64 v13; // rax
  MSG Msg; // [rsp+30h] [rbp-30h] BYREF
  DWORD dwindex; // [rsp+88h] [rbp+28h] BYREF
  HANDLE pHandles; // [rsp+90h] [rbp+30h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  *((_DWORD *)this + 20) = CurrentThreadId;
  *(_DWORD *)(*((_QWORD *)this + 14) + 16LL) = CurrentThreadId;
  *(_DWORD *)(*((_QWORD *)this + 15) + 16LL) = *((_DWORD *)this + 20);
  v3 = _lambda_103564c3136a6d89c1bf4e8d5a4b0eab_::_lambda_103564c3136a6d89c1bf4e8d5a4b0eab_(
         (_lambda_103564c3136a6d89c1bf4e8d5a4b0eab_ *)&dwindex,
         this);
  v4 = _lambda_103564c3136a6d89c1bf4e8d5a4b0eab_::operator()(v3);
  *((_DWORD *)this + 11) = v4;
  if ( v4 < 0 )
  {
    if ( *((_QWORD *)this + 7) )
    {
      v13 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
              &dwindex,
              (char *)this + 56);
      WorkThreadManager::s_AttachAndRecoverTask(v13);
    }
    v10 = (void *)*((_QWORD *)this + 20);
    if ( v10 )
      SetEvent(v10);
    _InterlockedDecrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
    WorkThreadManager::s_TryRemoveThread(this, 1, 0);
    WorkThreadManager::TaskList::Clear((WorkThreadManager::CThread *)((char *)this + 24));
    v12 = (wil::details *)*((_QWORD *)this + 6);
    if ( v12 )
      wil::details::SetEvent(v12, v11);
  }
  else
  {
    v6 = (wil::details *)*((_QWORD *)this + 6);
    if ( v6 )
      wil::details::SetEvent(v6, v5);
    v7 = (WorkThreadManager::TaskData *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = 0;
    if ( v7 )
      WorkThreadManager::TaskData::`scalar deleting destructor'(v7, (unsigned int)v5);
    *((_BYTE *)this + 88) = 0;
    _InterlockedDecrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
    v8 = 1;
    do
    {
      while ( 1 )
      {
        if ( !*((_QWORD *)this + 24) )
        {
          v9 = *((_DWORD *)this + 21) == 1;
          if ( *((int *)this + 21) > 1 )
          {
            pHandles = (HANDLE)*((_QWORD *)this + 13);
            if ( (unsigned __int8)IsSetWindowsHookExWPresent() )
            {
              if ( MsgWaitForMultipleObjectsEx(1u, &pHandles, 0xFFFFFFFF, 0x1CFFu, 6u) == -1 )
                GetLastError();
              memset(&Msg, 0, sizeof(Msg));
              while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
              {
                *((_BYTE *)this + 88) = 1;
                TranslateMessage(&Msg);
                DispatchMessageW(&Msg);
                *((_BYTE *)this + 88) = 0;
              }
            }
            else
            {
              dwindex = 0;
              CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
            }
            v9 = *((_DWORD *)this + 21) == 1;
          }
          if ( v9 )
          {
            v8 = 1;
            if ( *((_BYTE *)this + 40) || *((int *)this + 33) > 1 )
            {
              WorkThreadManager::CThread::WaitForWork(this, (unsigned int)v5);
            }
            else if ( byte_1800DE905 )
            {
              if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsLingering) <= 0xA )
              {
                WorkThreadManager::CThread::WaitForWork(this, (unsigned int)v5);
                v8 = 0;
              }
              _InterlockedDecrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsLingering);
            }
          }
          if ( !*((_QWORD *)this + 24) )
            break;
        }
        WorkThreadManager::CThread::RunCurrentTaskUnderLock((RTL_SRWLOCK *)this);
        WorkThreadManager::s_ClearOrGetNextTask(this);
      }
    }
    while ( *((int *)this + 21) > 1 || *((int *)this + 33) > 1 || !WorkThreadManager::s_TryRemoveThread(this, 0, v8) );
  }
  SHSetThreadRef(0);
  *((_QWORD *)this + 17) = 0;
  *((_DWORD *)this + 32) = 0x7FFFFFFF;
  SetTlsSlotData(0);
  CoUninitialize();
}

```

## disassembly

```asm
0x180019474  mov     [rsp-18h+arg_18], rbx
0x180019479  push    rbp
0x18001947a  push    rdi
0x18001947b  push    r14
0x18001947d  mov     rbp, rsp
0x180019480  sub     rsp, 60h
0x180019484  mov     rbx, rcx
0x180019487  call    cs:__imp_GetCurrentThreadId
0x18001948d  mov     [rbx+50h], eax
0x180019490  mov     r14d, 1
0x180019496  mov     [rbp+arg_0], r14b
0x18001949a  mov     rdx, [rbx+70h]
0x18001949e  mov     [rdx+10h], eax
0x1800194a1  mov     rdx, [rbx+78h]
0x1800194a5  mov     eax, [rbx+50h]
0x1800194a8  mov     [rdx+10h], eax
0x1800194ab  mov     rdx, rbx; struct WorkThreadManager::CThread *
0x1800194ae  lea     rcx, [rbp+dwindex]; this
0x1800194b2  call    ??0_lambda_103564c3136a6d89c1bf4e8d5a4b0eab_@@QEAA@PEAVCThread@WorkThreadManager@@@Z; _lambda_103564c3136a6d89c1bf4e8d5a4b0eab_::_lambda_103564c3136a6d89c1bf4e8d5a4b0eab_(WorkThreadManager::CThread *)
0x1800194b7  mov     rcx, rax
0x1800194ba  call    ??R_lambda_103564c3136a6d89c1bf4e8d5a4b0eab_@@QEBA@XZ; _lambda_103564c3136a6d89c1bf4e8d5a4b0eab_::operator()(void)
0x1800194bf  mov     [rbx+2Ch], eax
0x1800194c2  test    eax, eax
0x1800194c4  js      loc_180019686
0x1800194ca  mov     rcx, [rbx+30h]; this
0x1800194ce  test    rcx, rcx
0x1800194d1  jnz     loc_180019672
0x1800194d7  mov     rcx, [rbx+38h]; this
0x1800194db  mov     qword ptr [rbx+38h], 0
0x1800194e3  test    rcx, rcx
0x1800194e6  jnz     loc_18001967C
0x1800194ec  mov     byte ptr [rbx+58h], 0
0x1800194f0  lock dec cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x1800194f7  mov     dil, r14b
0x1800194fa  cmp     qword ptr [rbx+0C0h], 0
0x180019502  jnz     short loc_180019562
0x180019504  cmp     [rbx+54h], r14d
0x180019508  jg      loc_1800195D7
0x18001950e  jnz     short loc_180019558
0x180019510  mov     dil, r14b
0x180019513  cmp     byte ptr [rbx+28h], 0
0x180019517  jnz     loc_180019665
0x18001951d  cmp     [rbx+84h], r14d
0x180019524  jg      loc_180019665
0x18001952a  cmp     cs:byte_1800DE905, 0
0x180019531  jz      short loc_180019558
0x180019533  mov     eax, r14d
0x180019536  lock xadd cs:?s_cThreadsLingering@WorkThreadManager@@0KA, eax; ulong WorkThreadManager::s_cThreadsLingering
0x18001953e  add     eax, r14d
0x180019541  cmp     eax, 0Ah
0x180019544  ja      short loc_180019551
0x180019546  mov     rcx, rbx; this
0x180019549  call    ?WaitForWork@CThread@WorkThreadManager@@AEAAXK@Z; WorkThreadManager::CThread::WaitForWork(ulong)
0x18001954e  xor     dil, dil
0x180019551  lock dec cs:?s_cThreadsLingering@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsLingering
0x180019558  cmp     qword ptr [rbx+0C0h], 0
0x180019560  jz      short loc_180019574
0x180019562  mov     rcx, rbx; this
0x180019565  call    ?RunCurrentTaskUnderLock@CThread@WorkThreadManager@@QEAAXXZ; WorkThreadManager::CThread::RunCurrentTaskUnderLock(void)
0x18001956a  mov     rcx, rbx; struct WorkThreadManager::CThread *
0x18001956d  call    ?s_ClearOrGetNextTask@WorkThreadManager@@CAXPEAVCThread@1@@Z; WorkThreadManager::s_ClearOrGetNextTask(WorkThreadManager::CThread *)
0x180019572  jmp     short loc_1800194FA
0x180019574  cmp     [rbx+54h], r14d
0x180019578  jg      short loc_1800194FA
0x18001957a  cmp     [rbx+84h], r14d
0x180019581  jg      loc_1800194FA
0x180019587  mov     r8b, dil; bool
0x18001958a  xor     edx, edx; bool
0x18001958c  mov     rcx, rbx; struct WorkThreadManager::CThread *
0x18001958f  call    ?s_TryRemoveThread@WorkThreadManager@@CA_NPEAVCThread@1@_N1@Z; WorkThreadManager::s_TryRemoveThread(WorkThreadManager::CThread *,bool,bool)
0x180019594  test    al, al
0x180019596  jz      loc_1800194FA
0x18001959c  xor     ecx, ecx; punk
0x18001959e  call    SHSetThreadRef
0x1800195a3  mov     qword ptr [rbx+88h], 0
0x1800195ae  mov     dword ptr [rbx+80h], 7FFFFFFFh
0x1800195b8  xor     ecx, ecx; lpTlsValue
0x1800195ba  call    SetTlsSlotData
0x1800195bf  nop
0x1800195c0  mov     rbx, [rsp+60h+arg_18]
0x1800195c8  add     rsp, 60h
0x1800195cc  pop     r14
0x1800195ce  pop     rdi
0x1800195cf  pop     rbp
0x1800195d0  jmp     cs:__imp_CoUninitialize
0x1800195d7  mov     rax, [rbx+68h]
0x1800195db  mov     [rbp+pHandles], rax
0x1800195df  call    IsSetWindowsHookExWPresent
0x1800195e4  test    al, al
0x1800195e6  jz      loc_1800196E0
0x1800195ec  mov     [rsp+60h+dwFlags], 6; dwFlags
0x1800195f4  mov     r9d, 1CFFh; dwWakeMask
0x1800195fa  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800195fe  lea     rdx, [rbp+pHandles]; pHandles
0x180019602  mov     ecx, r14d; nCount
0x180019605  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x18001960b  cmp     eax, 0FFFFFFFFh
0x18001960e  jz      loc_1800196D5
0x180019614  xorps   xmm0, xmm0
0x180019617  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x18001961b  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x18001961f  movups  xmmword ptr [rbp+Msg.time], xmm0
0x180019623  jmp     short loc_180019641
0x180019625  mov     [rbx+58h], r14b
0x180019629  lea     rcx, [rbp+Msg]; lpMsg
0x18001962d  call    cs:__imp_TranslateMessage
0x180019633  lea     rcx, [rbp+Msg]; lpMsg
0x180019637  call    cs:__imp_DispatchMessageW
0x18001963d  mov     byte ptr [rbx+58h], 0
0x180019641  mov     [rsp+60h+dwFlags], r14d; wRemoveMsg
0x180019646  xor     r9d, r9d; wMsgFilterMax
0x180019649  xor     r8d, r8d; wMsgFilterMin
0x18001964c  xor     edx, edx; hWnd
0x18001964e  lea     rcx, [rbp+Msg]; lpMsg
0x180019652  call    cs:__imp_PeekMessageW
0x180019658  test    eax, eax
0x18001965a  jnz     short loc_180019625
0x18001965c  cmp     [rbx+54h], r14d
0x180019660  jmp     loc_18001950E
0x180019665  mov     rcx, rbx; this
0x180019668  call    ?WaitForWork@CThread@WorkThreadManager@@AEAAXK@Z; WorkThreadManager::CThread::WaitForWork(ulong)
0x18001966d  jmp     loc_180019558
0x180019672  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180019677  jmp     loc_1800194D7
0x18001967c  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x180019681  jmp     loc_1800194EC
0x180019686  lea     rdx, [rbx+38h]
0x18001968a  cmp     qword ptr [rdx], 0
0x18001968e  jnz     short loc_18001970A
0x180019690  mov     rcx, [rbx+0A0h]; hEvent
0x180019697  test    rcx, rcx
0x18001969a  jnz     loc_180019720
0x1800196a0  lock dec cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x1800196a7  xor     r8d, r8d; bool
0x1800196aa  mov     dl, r14b; bool
0x1800196ad  mov     rcx, rbx; struct WorkThreadManager::CThread *
0x1800196b0  call    ?s_TryRemoveThread@WorkThreadManager@@CA_NPEAVCThread@1@_N1@Z; WorkThreadManager::s_TryRemoveThread(WorkThreadManager::CThread *,bool,bool)
0x1800196b5  lea     rcx, [rbx+18h]; this
0x1800196b9  call    ?Clear@TaskList@WorkThreadManager@@QEAAXXZ; WorkThreadManager::TaskList::Clear(void)
0x1800196be  mov     rcx, [rbx+30h]; this
0x1800196c2  test    rcx, rcx
0x1800196c5  jz      loc_18001959C
0x1800196cb  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1800196d0  jmp     loc_18001959C
0x1800196d5  call    cs:__imp_GetLastError
0x1800196db  jmp     loc_180019614
0x1800196e0  mov     [rbp+dwindex], 0
0x1800196e7  lea     rax, [rbp+dwindex]
0x1800196eb  mov     qword ptr [rsp+60h+dwFlags], rax; lpdwindex
0x1800196f0  lea     r9, [rbp+pHandles]; pHandles
0x1800196f4  mov     r8d, r14d; cHandles
0x1800196f7  or      edx, 0FFFFFFFFh; dwTimeout
0x1800196fa  mov     ecx, 8; dwFlags
0x1800196ff  call    cs:__imp_CoWaitForMultipleHandles
0x180019705  jmp     loc_18001965C
0x18001970a  lea     rcx, [rbp+dwindex]
0x18001970e  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180019713  mov     rcx, rax
0x180019716  call    ?s_AttachAndRecoverTask@WorkThreadManager@@CAXV?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@@Z; WorkThreadManager::s_AttachAndRecoverTask(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>)
0x18001971b  jmp     loc_180019690
0x180019720  call    cs:__imp_SetEvent
0x180019726  jmp     loc_1800196A0
```
