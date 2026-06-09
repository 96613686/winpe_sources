# ComTaskMgrWnd::MsgPumpThreadProc(void *)

- ea: `0x140003270`
- end: `0x140003587`
- name: `?MsgPumpThreadProc@ComTaskMgrWnd@@CAKPEAX@Z`
- size: `791`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140003270`
- `0x140003590`
- `0x1400036b0`
- `0x14000384c`
- `0x140003a70`
- `0x140003b10`
- `0x140007418`
- `0x140009b24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003569`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003295`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003457`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003295`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003457`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003475`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003475`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003574`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003574`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x1400033c8`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x1400033c8`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x1400033ac`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x1400033fb`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x1400034ea`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x1400033ac`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x1400033fb`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x1400034ea`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x1400033d3`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x1400033d3`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1400032de`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1400032de`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x1400034aa`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x1400034aa`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassW` at `0x140003501`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassW` at `0x140003501`

## pseudocode

```c
__int64 __fastcall ComTaskMgrWnd::MsgPumpThreadProc(PVOID Parameter)
{
  int Wnd; // eax
  ComTaskMgrWnd *v2; // rcx
  int v3; // ebx
  char v4; // bl
  DWORD v5; // eax
  int v6; // edx
  RTL_SRWLOCK *v7; // rbx
  BOOL IsDebuggerBreakForTaskHangEnabled; // eax
  DWORD v9; // edx
  DWORD v10; // eax
  char *Ptr; // rcx
  ComTaskMgrWnd *v12; // rbx
  const WCHAR *v13; // rcx
  tagMSG Msg; // [rsp+30h] [rbp-68h] BYREF
  struct tagMSG v16; // [rsp+60h] [rbp-38h] BYREF

  Wnd = ComTaskMgrWnd::CreateWnd(ComTaskMgrBase::s_pVirtualSingleton);
  v2 = ComTaskMgrBase::s_pVirtualSingleton;
  v3 = Wnd;
  *((_DWORD *)ComTaskMgrBase::s_pVirtualSingleton + 8) = Wnd;
  SetEvent(*((HANDLE *)v2 + 5));
  if ( v3 < 0 )
    return 0;
  v4 = 1;
  do
  {
    v5 = MsgWaitForMultipleObjects(1u, (const HANDLE *)ComTaskMgrBase::s_pVirtualSingleton + 7, 0, 0xFFFFFFFF, 0x1DFFu);
    if ( !v5 )
      break;
    if ( v5 == 1 )
    {
      memset(&Msg, 0, sizeof(Msg));
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
        if ( Msg.message == 18 )
          v4 = 0;
      }
    }
    else if ( v5 == -1 )
    {
      break;
    }
  }
  while ( v4 );
  v7 = (RTL_SRWLOCK *)ComTaskMgrBase::s_pVirtualSingleton;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids,
      (_DWORD)ComTaskMgrBase::s_pVirtualSingleton,
      (__int64)L"LateShutdown");
  if ( _InterlockedCompareExchange(&dword_1400159E4, 0, 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)&ShutdownMgr::s_sync, 0xFFFFFFFF) == 1 )
  {
    SetEvent((HANDLE)_InterlockedCompareExchange64(&ShutdownMgr::s_hEvent, -1, -1));
  }
  _InterlockedCompareExchange64(&ShutdownMgr::s_hEvent, -1, -1);
  if ( !dword_140015A18 )
  {
    if ( dword_140015A14 || !ComTaskMgrWnd::CleanupSet::Size(v7 + 9) )
      goto LABEL_28;
    goto LABEL_10;
  }
  if ( !dword_140015A14 )
  {
    if ( v7[8].Ptr )
    {
      while ( 1 )
      {
        IsDebuggerBreakForTaskHangEnabled = ComTaskMgrBase::IsDebuggerBreakForTaskHangEnabled();
        v9 = 30000;
        if ( !IsDebuggerBreakForTaskHangEnabled )
          v9 = -1;
        v10 = WaitForSingleObject(v7[8].Ptr, v9);
        if ( !v10 )
          break;
        if ( v10 != 258 )
        {
          GetLastError();
          break;
        }
        ComTaskMgrBase::DebuggerBreakForTaskHang(0);
      }
      Ptr = (char *)v7[8].Ptr;
      if ( (unsigned __int64)(Ptr - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(Ptr);
        v7[8].Ptr = 0;
      }
      goto LABEL_28;
    }
    if ( ComTaskMgrWnd::CleanupSet::Size(v7 + 9) )
LABEL_10:
      ComTaskMgrWnd::ShutdownTasksWorker((ComTaskMgrWnd *)v7);
  }
LABEL_28:
  v12 = ComTaskMgrBase::s_pVirtualSingleton;
  dword_140015A14 = 1;
  DestroyWindow(*((HWND *)ComTaskMgrBase::s_pVirtualSingleton + 3));
  *(_OWORD *)&v16.hwnd = 0;
  *((_QWORD *)v12 + 3) = 0;
  memset(&v16.wParam, 0, 32);
  while ( PeekMessageW(&v16, 0, 0, 0, 1u) )
    ;
  v13 = (const WCHAR *)*((unsigned __int16 *)v12 + 8);
  if ( (_WORD)v13 )
  {
    UnregisterClassW(v13, *((HINSTANCE *)v12 + 1));
    *((_WORD *)v12 + 8) = 0;
  }
  ComTaskMgrBase::WaitForShutdownGuards();
  return 0;
}

```

## disassembly

```asm
0x140003270  push    rbx
0x140003272  sub     rsp, 90h
0x140003279  mov     rcx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; this
0x140003280  call    ?CreateWnd@ComTaskMgrWnd@@AEAAJXZ; ComTaskMgrWnd::CreateWnd(void)
0x140003285  mov     rcx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x14000328c  mov     ebx, eax
0x14000328e  mov     [rcx+20h], eax
0x140003291  mov     rcx, [rcx+28h]; hEvent
0x140003295  call    cs:__imp_SetEvent
0x14000329b  test    ebx, ebx
0x14000329d  js      loc_140003512
0x1400032a3  mov     [rsp+98h+arg_0], rsi
0x1400032ab  mov     bl, 1
0x1400032ad  mov     [rsp+98h+arg_10], rdi
0x1400032b5  mov     edi, 0FFFFFFFFh
0x1400032ba  nop     word ptr [rax+rax+00h]
0x1400032c0  mov     rdx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x1400032c7  mov     r9d, edi; dwMilliseconds
0x1400032ca  add     rdx, 38h ; '8'; pHandles
0x1400032ce  mov     [rsp+98h+dwWakeMask], 1DFFh; dwWakeMask
0x1400032d6  xor     r8d, r8d; fWaitAll
0x1400032d9  mov     ecx, 1; nCount
0x1400032de  call    cs:__imp_MsgWaitForMultipleObjects
0x1400032e4  test    eax, eax
0x1400032e6  jnz     loc_140003380
0x1400032ec  mov     rbx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x1400032f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400032fa  lea     rax, WPP_GLOBAL_Control
0x140003301  cmp     rcx, rax
0x140003304  jnz     loc_140003407
0x14000330a  xor     ecx, ecx
0x14000330c  mov     eax, 1
0x140003311  lock cmpxchg cs:dword_1400159E4, ecx
0x140003319  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x140003320  test    eax, eax
0x140003322  jnz     loc_140003435
0x140003328  mov     rax, rsi
0x14000332b  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rsi; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x140003334  cmp     cs:dword_140015A18, 0
0x14000333b  mov     rsi, [rsp+98h+arg_0]
0x140003343  jz      loc_14000351D
0x140003349  cmp     cs:dword_140015A14, 0
0x140003350  jnz     loc_140003495
0x140003356  cmp     qword ptr [rbx+40h], 0
0x14000335b  jnz     loc_140003462
0x140003361  lea     rcx, [rbx+48h]; SRWLock
0x140003365  call    ?Size@CleanupSet@ComTaskMgrWnd@@QEAA_KXZ; ComTaskMgrWnd::CleanupSet::Size(void)
0x14000336a  test    rax, rax
0x14000336d  jz      loc_140003495
0x140003373  mov     rcx, rbx; this
0x140003376  call    ?ShutdownTasksWorker@ComTaskMgrWnd@@AEAAJXZ; ComTaskMgrWnd::ShutdownTasksWorker(void)
0x14000337b  jmp     loc_140003495
0x140003380  cmp     eax, 1
0x140003383  jnz     loc_140003549
0x140003389  xorps   xmm0, xmm0
0x14000338c  mov     [rsp+98h+dwWakeMask], eax; wRemoveMsg
0x140003390  xor     r9d, r9d; wMsgFilterMax
0x140003393  lea     rcx, [rsp+98h+Msg]; lpMsg
0x140003398  xor     r8d, r8d; wMsgFilterMin
0x14000339b  xor     edx, edx; hWnd
0x14000339d  movups  xmmword ptr [rsp+98h+Msg.hwnd], xmm0
0x1400033a2  movups  xmmword ptr [rsp+98h+Msg.wParam], xmm0
0x1400033a7  movups  xmmword ptr [rsp+98h+Msg.time], xmm0
0x1400033ac  call    cs:__imp_PeekMessageW
0x1400033b2  test    eax, eax
0x1400033b4  jnz     short loc_1400033C3
0x1400033b6  test    bl, bl
0x1400033b8  jnz     loc_1400032C0
0x1400033be  jmp     loc_1400032EC
0x1400033c3  lea     rcx, [rsp+98h+Msg]; lpMsg
0x1400033c8  call    cs:__imp_TranslateMessage
0x1400033ce  lea     rcx, [rsp+98h+Msg]; lpMsg
0x1400033d3  call    cs:__imp_DispatchMessageW
0x1400033d9  xor     eax, eax
0x1400033db  movzx   ebx, bl
0x1400033de  cmp     [rsp+98h+Msg.message], 12h
0x1400033e3  lea     rcx, [rsp+98h+Msg]; lpMsg
0x1400033e8  mov     [rsp+98h+dwWakeMask], 1; wRemoveMsg
0x1400033f0  cmovz   ebx, eax
0x1400033f3  xor     r9d, r9d; wMsgFilterMax
0x1400033f6  xor     r8d, r8d; wMsgFilterMin
0x1400033f9  xor     edx, edx; hWnd
0x1400033fb  call    cs:__imp_PeekMessageW
0x140003401  test    eax, eax
0x140003403  jz      short loc_1400033B6
0x140003405  jmp     short loc_1400033C3
0x140003407  test    byte ptr [rcx+1Ch], 4
0x14000340b  jz      loc_14000330A
0x140003411  mov     rcx, [rcx+10h]
0x140003415  lea     rax, aLateshutdown; "LateShutdown"
0x14000341c  mov     r9, rbx
0x14000341f  mov     qword ptr [rsp+98h+dwWakeMask], rax
0x140003424  lea     r8, WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids
0x14000342b  call    WPP_SF_qS
0x140003430  jmp     loc_14000330A
0x140003435  mov     eax, esi
0x140003437  lock xadd cs:?s_sync@ShutdownMgr@@0USync@1@A, eax; ShutdownMgr::Sync ShutdownMgr::s_sync
0x14000343f  cmp     eax, 1
0x140003442  jnz     loc_140003328
0x140003448  mov     rax, rsi
0x14000344b  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rsi; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x140003454  mov     rcx, rax; hEvent
0x140003457  call    cs:__imp_SetEvent
0x14000345d  jmp     loc_140003328
0x140003462  call    ?IsDebuggerBreakForTaskHangEnabled@ComTaskMgrBase@@KAHXZ; ComTaskMgrBase::IsDebuggerBreakForTaskHangEnabled(void)
0x140003467  mov     rcx, [rbx+40h]; hHandle
0x14000346b  test    eax, eax
0x14000346d  mov     edx, 7530h
0x140003472  cmovz   edx, edi; dwMilliseconds
0x140003475  call    cs:__imp_WaitForSingleObject
0x14000347b  test    eax, eax
0x14000347d  jnz     loc_140003556
0x140003483  mov     rcx, [rbx+40h]; hObject
0x140003487  lea     rax, [rcx-1]
0x14000348b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000348f  jbe     loc_140003574
0x140003495  mov     rbx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x14000349c  mov     cs:dword_140015A14, 1
0x1400034a6  mov     rcx, [rbx+18h]; hWnd
0x1400034aa  call    cs:__imp_DestroyWindow
0x1400034b0  mov     rdi, [rsp+98h+arg_10]
0x1400034b8  xorps   xmm0, xmm0
0x1400034bb  movups  xmmword ptr [rsp+98h+var_38.hwnd], xmm0
0x1400034c0  mov     qword ptr [rbx+18h], 0
0x1400034c8  movups  xmmword ptr [rsp+98h+var_38.wParam], xmm0
0x1400034cd  movups  xmmword ptr [rsp+98h+var_38.time], xmm0
0x1400034d5  xor     r9d, r9d; wMsgFilterMax
0x1400034d8  mov     [rsp+98h+dwWakeMask], 1; wRemoveMsg
0x1400034e0  xor     r8d, r8d; wMsgFilterMin
0x1400034e3  lea     rcx, [rsp+98h+var_38]; lpMsg
0x1400034e8  xor     edx, edx; hWnd
0x1400034ea  call    cs:__imp_PeekMessageW
0x1400034f0  test    eax, eax
0x1400034f2  jnz     short loc_1400034D5
0x1400034f4  movzx   ecx, word ptr [rbx+10h]; lpClassName
0x1400034f8  cmp     ax, cx
0x1400034fb  jz      short loc_14000350D
0x1400034fd  mov     rdx, [rbx+8]; hInstance
0x140003501  call    cs:__imp_UnregisterClassW
0x140003507  xor     eax, eax
0x140003509  mov     [rbx+10h], ax
0x14000350d  call    ?WaitForShutdownGuards@ComTaskMgrBase@@KAJXZ; ComTaskMgrBase::WaitForShutdownGuards(void)
0x140003512  xor     eax, eax
0x140003514  add     rsp, 90h
0x14000351b  pop     rbx
0x14000351c  retn
0x14000351d  cmp     cs:dword_140015A14, 0
0x140003524  jnz     loc_140003495
0x14000352a  lea     rcx, [rbx+48h]; SRWLock
0x14000352e  call    ?Size@CleanupSet@ComTaskMgrWnd@@QEAA_KXZ; ComTaskMgrWnd::CleanupSet::Size(void)
0x140003533  test    rax, rax
0x140003536  jz      loc_140003495
0x14000353c  mov     rcx, rbx; this
0x14000353f  call    ?ShutdownTasksWorker@ComTaskMgrWnd@@AEAAJXZ; ComTaskMgrWnd::ShutdownTasksWorker(void)
0x140003544  jmp     loc_140003495
0x140003549  cmp     eax, edi
0x14000354b  jz      loc_1400032EC
0x140003551  jmp     loc_1400033B6
0x140003556  cmp     eax, 102h
0x14000355b  jnz     short loc_140003569
0x14000355d  xor     ecx, ecx; int
0x14000355f  call    ?DebuggerBreakForTaskHang@ComTaskMgrBase@@KAXH@Z; ComTaskMgrBase::DebuggerBreakForTaskHang(int)
0x140003564  jmp     loc_140003462
0x140003569  call    cs:__imp_GetLastError
0x14000356f  jmp     loc_140003483
0x140003574  call    cs:__imp_CloseHandle
0x14000357a  mov     qword ptr [rbx+40h], 0
0x140003582  jmp     loc_140003495
```
