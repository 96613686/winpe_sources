# ComTaskMgrWnd::Shutdown(int)

- ea: `0x140003880`
- end: `0x140003a69`
- name: `?Shutdown@ComTaskMgrWnd@@AEAAJH@Z`
- size: `489`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400031a0`

## callees

- `0x14000384c`
- `0x140003880`
- `0x140003a70`
- `0x140003b10`
- `0x140007418`
- `0x1400096c4`
- `0x140009b24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003a0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003a0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000390d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000390d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400038ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400038ff`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003992`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003992`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400039b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400039b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003a56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003a56`

## pseudocode

```c
__int64 __fastcall ComTaskMgrWnd::Shutdown(RTL_SRWLOCK *this, int a2)
{
  unsigned int ShutdownTasksThread; // ebx
  PVOID v5; // rdi
  ComTaskMgrWnd *v6; // rcx
  const wchar_t *v7; // rax
  BOOL IsDebuggerBreakForTaskHangEnabled; // eax
  DWORD v9; // edx
  DWORD v10; // eax
  char *Ptr; // rcx
  signed int LastError; // eax

  ShutdownTasksThread = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v7 = L"EarlyShutdown";
    if ( !a2 )
      v7 = L"LateShutdown";
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)L"LateShutdown",
      (unsigned int)WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids,
      (_DWORD)this,
      (__int64)v7);
  }
  if ( _InterlockedCompareExchange(&dword_1400159E4, 0, 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)&ShutdownMgr::s_sync, 0xFFFFFFFF) == 1 )
  {
    SetEvent((HANDLE)_InterlockedCompareExchange64(&ShutdownMgr::s_hEvent, -1, -1));
  }
  _InterlockedCompareExchange64(&ShutdownMgr::s_hEvent, -1, -1);
  if ( !dword_140015A18 )
  {
    if ( !dword_140015A14 && ComTaskMgrWnd::CleanupSet::Size(this + 9) )
    {
      v6 = (ComTaskMgrWnd *)this;
      if ( !a2 )
        goto LABEL_9;
      ShutdownTasksThread = ComTaskMgrWnd::CreateShutdownTasksThread((ComTaskMgrWnd *)this);
      goto LABEL_25;
    }
LABEL_24:
    if ( !a2 )
      goto LABEL_21;
LABEL_25:
    dword_140015A18 = 1;
    return ShutdownTasksThread;
  }
  if ( dword_140015A14 )
    goto LABEL_24;
  if ( a2 )
    goto LABEL_25;
  if ( this[8].Ptr )
  {
    while ( 1 )
    {
      IsDebuggerBreakForTaskHangEnabled = ComTaskMgrBase::IsDebuggerBreakForTaskHangEnabled();
      v9 = 30000;
      if ( !IsDebuggerBreakForTaskHangEnabled )
        v9 = -1;
      v10 = WaitForSingleObject(this[8].Ptr, v9);
      if ( !v10 )
        break;
      if ( v10 != 258 )
      {
        LastError = GetLastError();
        ShutdownTasksThread = LastError;
        if ( LastError > 0 )
          ShutdownTasksThread = (unsigned __int16)LastError | 0x80070000;
        if ( (ShutdownTasksThread & 0x80000000) == 0 )
          ShutdownTasksThread = -2147467259;
        break;
      }
      ComTaskMgrBase::DebuggerBreakForTaskHang(0);
    }
    Ptr = (char *)this[8].Ptr;
    if ( (unsigned __int64)(Ptr - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(Ptr);
      this[8].Ptr = 0;
    }
    goto LABEL_21;
  }
  AcquireSRWLockExclusive(this + 9);
  v5 = this[11].Ptr;
  ReleaseSRWLockExclusive(this + 9);
  if ( !v5 )
  {
LABEL_21:
    dword_140015A14 = 1;
    return ShutdownTasksThread;
  }
  v6 = (ComTaskMgrWnd *)this;
LABEL_9:
  ShutdownTasksThread = ComTaskMgrWnd::ShutdownTasksWorker(v6);
  dword_140015A14 = 1;
  return ShutdownTasksThread;
}

```

## disassembly

```asm
0x140003880  push    rbx
0x140003882  push    rbp
0x140003883  push    rsi
0x140003884  push    rdi
0x140003885  sub     rsp, 38h
0x140003889  mov     edi, edx
0x14000388b  mov     rbp, rcx
0x14000388e  xor     ebx, ebx
0x140003890  mov     rcx, cs:WPP_GLOBAL_Control
0x140003897  lea     rax, WPP_GLOBAL_Control
0x14000389e  cmp     rcx, rax
0x1400038a1  jnz     loc_140003935
0x1400038a7  xor     ecx, ecx
0x1400038a9  mov     eax, 1
0x1400038ae  lock cmpxchg cs:dword_1400159E4, ecx
0x1400038b6  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1400038bd  test    eax, eax
0x1400038bf  jnz     loc_140003970
0x1400038c5  mov     rax, rsi
0x1400038c8  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rsi; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x1400038d1  cmp     cs:dword_140015A18, ebx
0x1400038d7  jz      loc_1400039DD
0x1400038dd  cmp     cs:dword_140015A14, ebx
0x1400038e3  jnz     loc_1400039F3
0x1400038e9  test    edi, edi
0x1400038eb  jnz     loc_1400039F7
0x1400038f1  cmp     [rbp+40h], rbx
0x1400038f5  jnz     loc_14000399D
0x1400038fb  lea     rcx, [rbp+48h]; SRWLock
0x1400038ff  call    cs:__imp_AcquireSRWLockExclusive
0x140003905  mov     rdi, [rbp+58h]
0x140003909  lea     rcx, [rbp+48h]; SRWLock
0x14000390d  call    cs:__imp_ReleaseSRWLockExclusive
0x140003913  test    rdi, rdi
0x140003916  jz      loc_1400039D1
0x14000391c  mov     rcx, rbp; this
0x14000391f  call    ?ShutdownTasksWorker@ComTaskMgrWnd@@AEAAJXZ; ComTaskMgrWnd::ShutdownTasksWorker(void)
0x140003924  mov     ebx, eax
0x140003926  mov     cs:dword_140015A14, 1
0x140003930  jmp     loc_140003A01
0x140003935  test    byte ptr [rcx+1Ch], 4
0x140003939  jz      loc_1400038A7
0x14000393f  mov     rcx, [rcx+10h]
0x140003943  lea     rdx, aLateshutdown; "LateShutdown"
0x14000394a  test    edi, edi
0x14000394c  lea     rax, aEarlyshutdown; "EarlyShutdown"
0x140003953  mov     r9, rbp
0x140003956  lea     r8, WPP_70d3f6ab2bd730cad06006a8dcaaa1a7_Traceguids
0x14000395d  cmovz   rax, rdx
0x140003961  mov     [rsp+58h+var_38], rax
0x140003966  call    WPP_SF_qS
0x14000396b  jmp     loc_1400038A7
0x140003970  mov     eax, esi
0x140003972  lock xadd cs:?s_sync@ShutdownMgr@@0USync@1@A, eax; ShutdownMgr::Sync ShutdownMgr::s_sync
0x14000397a  cmp     eax, 1
0x14000397d  jnz     loc_1400038C5
0x140003983  mov     rax, rsi
0x140003986  lock cmpxchg cs:?s_hEvent@ShutdownMgr@@0VInterlockedAutoHandle@@A, rsi; InterlockedAutoHandle ShutdownMgr::s_hEvent
0x14000398f  mov     rcx, rax; hEvent
0x140003992  call    cs:__imp_SetEvent
0x140003998  jmp     loc_1400038C5
0x14000399d  mov     edi, 0FFFFFFFFh
0x1400039a2  call    ?IsDebuggerBreakForTaskHangEnabled@ComTaskMgrBase@@KAHXZ; ComTaskMgrBase::IsDebuggerBreakForTaskHangEnabled(void)
0x1400039a7  mov     rcx, [rbp+40h]; hHandle
0x1400039ab  test    eax, eax
0x1400039ad  mov     edx, 7530h
0x1400039b2  cmovz   edx, edi; dwMilliseconds
0x1400039b5  call    cs:__imp_WaitForSingleObject
0x1400039bb  test    eax, eax
0x1400039bd  jnz     short loc_140003A38
0x1400039bf  mov     rcx, [rbp+40h]; hObject
0x1400039c3  lea     rax, [rcx-1]
0x1400039c7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400039cb  jbe     loc_140003A56
0x1400039d1  mov     cs:dword_140015A14, 1
0x1400039db  jmp     short loc_140003A01
0x1400039dd  cmp     cs:dword_140015A14, ebx
0x1400039e3  jnz     short loc_1400039F3
0x1400039e5  lea     rcx, [rbp+48h]; SRWLock
0x1400039e9  call    ?Size@CleanupSet@ComTaskMgrWnd@@QEAA_KXZ; ComTaskMgrWnd::CleanupSet::Size(void)
0x1400039ee  test    rax, rax
0x1400039f1  jnz     short loc_140003A24
0x1400039f3  test    edi, edi
0x1400039f5  jz      short loc_1400039D1
0x1400039f7  mov     cs:dword_140015A18, 1
0x140003a01  mov     eax, ebx
0x140003a03  add     rsp, 38h
0x140003a07  pop     rdi
0x140003a08  pop     rsi
0x140003a09  pop     rbp
0x140003a0a  pop     rbx
0x140003a0b  retn
0x140003a0c  call    cs:__imp_GetLastError
0x140003a12  mov     ebx, eax
0x140003a14  test    eax, eax
0x140003a16  jg      short loc_140003A4B
0x140003a18  test    ebx, ebx
0x140003a1a  mov     eax, 80004005h
0x140003a1f  cmovns  ebx, eax
0x140003a22  jmp     short loc_1400039BF
0x140003a24  mov     rcx, rbp; this
0x140003a27  test    edi, edi
0x140003a29  jz      loc_14000391F
0x140003a2f  call    ?CreateShutdownTasksThread@ComTaskMgrWnd@@AEAAJXZ; ComTaskMgrWnd::CreateShutdownTasksThread(void)
0x140003a34  mov     ebx, eax
0x140003a36  jmp     short loc_1400039F7
0x140003a38  cmp     eax, 102h
0x140003a3d  jnz     short loc_140003A0C
0x140003a3f  xor     ecx, ecx; int
0x140003a41  call    ?DebuggerBreakForTaskHang@ComTaskMgrBase@@KAXH@Z; ComTaskMgrBase::DebuggerBreakForTaskHang(int)
0x140003a46  jmp     loc_1400039A2
0x140003a4b  movzx   ebx, ax
0x140003a4e  or      ebx, 80070000h
0x140003a54  jmp     short loc_140003A18
0x140003a56  call    cs:__imp_CloseHandle
0x140003a5c  mov     qword ptr [rbp+40h], 0
0x140003a64  jmp     loc_1400039D1
```
