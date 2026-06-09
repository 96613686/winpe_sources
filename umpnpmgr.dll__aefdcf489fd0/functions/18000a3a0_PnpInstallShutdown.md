# PnpInstallShutdown

- ea: `0x18000a3a0`
- end: `0x18000a69e`
- name: `PnpInstallShutdown`
- size: `766`
- prototype: `_BOOL8()`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ea20`
- `0x180013fb0`

## callees

- `0x18000a210`
- `0x18000a3a0`
- `0x18000a9e0`
- `0x1800106dc`
- `0x1800117d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a44d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a554`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a5fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018d10`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018d2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a44d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a554`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a5fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018d10`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018d2e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a3cc`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a51f`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a3cc`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a51f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a53e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a60c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a53e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a60c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a4b9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a4b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a652`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a652`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4d6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000a437`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000a437`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a57f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a598`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a619`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a57f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a598`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a619`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18000a46b`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x18000a46b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a406`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a40f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a406`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a40f`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18000a3e9`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18000a3e9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000a55f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000a55f`

## pseudocode

```c
_BOOL8 PnpInstallShutdown()
{
  DWORD LastError; // edi
  HANDLE CurrentProcess; // rbx
  HANDLE v2; // rax
  DWORD v3; // eax
  _QWORD *v4; // rcx
  __int64 v6; // rax
  HANDLE TargetHandle; // [rsp+70h] [rbp+8h] BYREF

  LastError = 0;
  TargetHandle = 0;
  WaitForMultipleObjectsEx(2u, &PnpInstallThreadLock, 0, 0xFFFFFFFF, 0);
  PnpInstallThreadExit = 1;
  if ( PnpNotifyHandle )
  {
    CM_Unregister_Notification();
    PnpNotifyHandle = 0;
  }
  if ( (char *)PnpInstallThread - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CurrentProcess = GetCurrentProcess();
    v2 = GetCurrentProcess();
    if ( !DuplicateHandle(v2, PnpInstallThread, CurrentProcess, &TargetHandle, 0, 0, 2u) )
      TargetHandle = 0;
  }
  ReleaseMutex(qword_1800239E8);
  if ( TargetHandle )
  {
    if ( !QueueUserAPC(guard_check_icall_nop, TargetHandle, 0)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
    }
    v3 = WaitForSingleObjectEx(TargetHandle, 0x1D4C0u, 0);
    if ( v3 )
    {
      if ( v3 == 258 )
      {
        LastError = 1460;
      }
      else if ( v3 == -1 )
      {
        LastError = GetLastError();
      }
      else
      {
        LastError = 13;
      }
    }
    CloseHandle(TargetHandle);
  }
  PnpInstallThread = 0;
  PnpInstallThreadExit = 0;
  WaitForMultipleObjectsEx(2u, &Handles, 0, 0xFFFFFFFF, 0);
  ServerInstallQueuingEnabled = 0;
  ServerInstallProcessingEnabled = 0;
  if ( SchedulerWaitEvents )
  {
    SetEvent(SchedulerWaitEvents);
    while ( PnpSchedulerThreadId )
    {
      ReleaseMutex(hMutex);
      Sleep(0x32u);
      pSetupBeginSynchronizedAccess(&Handles);
    }
    if ( SchedulerWaitEvents )
    {
      CloseHandle(SchedulerWaitEvents);
      SchedulerWaitEvents = 0;
    }
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( hSourceHandle )
  {
    CloseHandle(hSourceHandle);
    hSourceHandle = 0;
  }
  while ( 1 )
  {
    v4 = ServerInstallList;
    if ( ServerInstallList == &ServerInstallList )
      break;
    if ( *((PVOID **)ServerInstallList + 1) != &ServerInstallList
      || (v6 = *(_QWORD *)ServerInstallList, *(PVOID *)(*(_QWORD *)ServerInstallList + 8LL) != ServerInstallList) )
    {
      __fastfail(3u);
    }
    ServerInstallList = *(PVOID *)ServerInstallList;
    *(_QWORD *)(v6 + 8) = &ServerInstallList;
    FreeServerInstallEntry(v4);
  }
  ServerInstallListSize = 0;
  ServerInstallBatchComplete = 0;
  ServerInstallBatchTotal = 0;
  ServerInstallBatchTimeoutDetected = 0;
  ServerInstallUpdateStatus();
  ReleaseMutex(hMutex);
  if ( PnpNoPendingInstallEvents )
  {
    SetEvent(PnpNoPendingInstallEvents);
    CloseHandle(PnpNoPendingInstallEvents);
    PnpNoPendingInstallEvents = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x18000a3a0  push    rbx
0x18000a3a2  push    rsi
0x18000a3a3  push    rdi
0x18000a3a4  push    r14
0x18000a3a6  sub     rsp, 48h
0x18000a3aa  xor     esi, esi
0x18000a3ac  mov     edi, esi
0x18000a3ae  mov     [rsp+68h+TargetHandle], rsi
0x18000a3b3  mov     [rsp+68h+bAlertable], esi; bAlertable
0x18000a3b7  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000a3bd  xor     r8d, r8d; bWaitAll
0x18000a3c0  lea     rdx, PnpInstallThreadLock; lpHandles
0x18000a3c7  mov     ecx, 2; nCount
0x18000a3cc  call    cs:__imp_WaitForMultipleObjectsEx
0x18000a3d2  nop
0x18000a3d3  mov     cs:PnpInstallThreadExit, 1
0x18000a3dd  mov     rcx, cs:PnpNotifyHandle
0x18000a3e4  test    rcx, rcx
0x18000a3e7  jz      short loc_18000A3F6
0x18000a3e9  call    cs:__imp_CM_Unregister_Notification
0x18000a3ef  mov     cs:PnpNotifyHandle, rsi
0x18000a3f6  mov     rax, cs:PnpInstallThread
0x18000a3fd  dec     rax
0x18000a400  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a404  ja      short loc_18000A446
0x18000a406  call    cs:__imp_GetCurrentProcess
0x18000a40c  mov     rbx, rax
0x18000a40f  call    cs:__imp_GetCurrentProcess
0x18000a415  mov     rcx, rax; hSourceProcessHandle
0x18000a418  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18000a420  mov     [rsp+68h+bInheritHandle], esi; bInheritHandle
0x18000a424  mov     [rsp+68h+bAlertable], esi; dwDesiredAccess
0x18000a428  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x18000a42d  mov     r8, rbx; hTargetProcessHandle
0x18000a430  mov     rdx, cs:PnpInstallThread; hSourceHandle
0x18000a437  call    cs:__imp_DuplicateHandle
0x18000a43d  test    eax, eax
0x18000a43f  jnz     short loc_18000A446
0x18000a441  mov     [rsp+68h+TargetHandle], rsi
0x18000a446  mov     rcx, cs:qword_1800239E8; hMutex
0x18000a44d  call    cs:__imp_ReleaseMutex
0x18000a453  mov     rdx, [rsp+68h+TargetHandle]; hThread
0x18000a458  test    rdx, rdx
0x18000a45b  jz      loc_18000A4F2
0x18000a461  xor     r8d, r8d; dwData
0x18000a464  lea     rcx, _guard_check_icall_nop; pfnAPC
0x18000a46b  call    cs:__imp_QueueUserAPC
0x18000a471  test    eax, eax
0x18000a473  jnz     short loc_18000A4A5
0x18000a475  lea     rbx, WPP_GLOBAL_Control
0x18000a47c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a483  cmp     rcx, rbx
0x18000a486  jz      short loc_18000A4AC
0x18000a488  test    byte ptr [rcx+1Ch], 1
0x18000a48c  jz      short loc_18000A4AC
0x18000a48e  mov     edx, 21h ; '!'
0x18000a493  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000a49a  mov     rcx, [rcx+10h]
0x18000a49e  call    WPP_SF_
0x18000a4a3  jmp     short loc_18000A4AC
0x18000a4a5  lea     rbx, WPP_GLOBAL_Control
0x18000a4ac  xor     r8d, r8d; bAlertable
0x18000a4af  mov     edx, 1D4C0h; dwMilliseconds
0x18000a4b4  mov     rcx, [rsp+68h+TargetHandle]; hHandle
0x18000a4b9  call    cs:__imp_WaitForSingleObjectEx
0x18000a4bf  test    eax, eax
0x18000a4c1  jz      short loc_18000A4E5
0x18000a4c3  cmp     eax, 102h
0x18000a4c8  jnz     short loc_18000A4D1
0x18000a4ca  mov     edi, 5B4h
0x18000a4cf  jmp     short loc_18000A4E5
0x18000a4d1  cmp     eax, 0FFFFFFFFh
0x18000a4d4  jnz     short loc_18000A4E0
0x18000a4d6  call    cs:__imp_GetLastError
0x18000a4dc  mov     edi, eax
0x18000a4de  jmp     short loc_18000A4E5
0x18000a4e0  mov     edi, 0Dh
0x18000a4e5  mov     rcx, [rsp+68h+TargetHandle]; hObject
0x18000a4ea  call    cs:__imp_CloseHandle
0x18000a4f0  jmp     short loc_18000A4F9
0x18000a4f2  lea     rbx, WPP_GLOBAL_Control
0x18000a4f9  mov     cs:PnpInstallThread, rsi
0x18000a500  mov     cs:PnpInstallThreadExit, esi
0x18000a506  mov     [rsp+68h+bAlertable], esi; bAlertable
0x18000a50a  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000a510  xor     r8d, r8d; bWaitAll
0x18000a513  lea     rdx, Handles; lpHandles
0x18000a51a  mov     ecx, 2; nCount
0x18000a51f  call    cs:__imp_WaitForMultipleObjectsEx
0x18000a525  nop
0x18000a526  mov     cs:ServerInstallQueuingEnabled, esi
0x18000a52c  mov     cs:ServerInstallProcessingEnabled, esi
0x18000a532  mov     rcx, cs:SchedulerWaitEvents; hEvent
0x18000a539  test    rcx, rcx
0x18000a53c  jz      short loc_18000A58C
0x18000a53e  call    cs:__imp_SetEvent
0x18000a544  cmp     cs:PnpSchedulerThreadId, 0
0x18000a54b  jz      short loc_18000A573
0x18000a54d  mov     rcx, cs:hMutex; hMutex
0x18000a554  call    cs:__imp_ReleaseMutex
0x18000a55a  mov     ecx, 32h ; '2'; dwMilliseconds
0x18000a55f  call    cs:__imp_Sleep
0x18000a565  lea     rcx, Handles; lpHandles
0x18000a56c  call    pSetupBeginSynchronizedAccess
0x18000a571  jmp     short loc_18000A544
0x18000a573  mov     rcx, cs:SchedulerWaitEvents; hObject
0x18000a57a  test    rcx, rcx
0x18000a57d  jz      short loc_18000A58C
0x18000a57f  call    cs:__imp_CloseHandle
0x18000a585  mov     cs:SchedulerWaitEvents, rsi
0x18000a58c  mov     rcx, cs:hObject; hObject
0x18000a593  test    rcx, rcx
0x18000a596  jz      short loc_18000A5A5
0x18000a598  call    cs:__imp_CloseHandle
0x18000a59e  mov     cs:hObject, rsi
0x18000a5a5  mov     rcx, cs:hSourceHandle; hObject
0x18000a5ac  test    rcx, rcx
0x18000a5af  jz      short loc_18000A5BE
0x18000a5b1  call    cs:__imp_CloseHandle
0x18000a5b7  mov     cs:hSourceHandle, rsi
0x18000a5be  lea     r14, ServerInstallList
0x18000a5c5  mov     rcx, cs:ServerInstallList; P
0x18000a5cc  cmp     rcx, r14
0x18000a5cf  jnz     loc_18000A669
0x18000a5d5  mov     cs:ServerInstallListSize, esi
0x18000a5db  mov     cs:ServerInstallBatchComplete, esi
0x18000a5e1  mov     cs:ServerInstallBatchTotal, esi
0x18000a5e7  mov     cs:ServerInstallBatchTimeoutDetected, esi
0x18000a5ed  call    ServerInstallUpdateStatus
0x18000a5f2  nop
0x18000a5f3  mov     rcx, cs:hMutex; hMutex
0x18000a5fa  call    cs:__imp_ReleaseMutex
0x18000a600  mov     rcx, cs:PnpNoPendingInstallEvents; hEvent
0x18000a607  test    rcx, rcx
0x18000a60a  jz      short loc_18000A626
0x18000a60c  call    cs:__imp_SetEvent
0x18000a612  mov     rcx, cs:PnpNoPendingInstallEvents; hObject
0x18000a619  call    cs:__imp_CloseHandle
0x18000a61f  mov     cs:PnpNoPendingInstallEvents, rsi
0x18000a626  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a62d  cmp     rcx, rbx
0x18000a630  jz      short loc_18000A650
0x18000a632  test    dword ptr [rcx+1Ch], 10000000h
0x18000a639  jz      short loc_18000A650
0x18000a63b  mov     edx, 22h ; '"'
0x18000a640  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000a647  mov     rcx, [rcx+10h]
0x18000a64b  call    WPP_SF_
0x18000a650  mov     ecx, edi; dwErrCode
0x18000a652  call    cs:__imp_SetLastError
0x18000a658  mov     eax, esi
0x18000a65a  test    edi, edi
0x18000a65c  setz    al
0x18000a65f  add     rsp, 48h
0x18000a663  pop     r14
0x18000a665  pop     rdi
0x18000a666  pop     rsi
0x18000a667  pop     rbx
0x18000a668  retn
0x18000a669  cmp     [rcx+8], r14
0x18000a66d  jnz     short loc_18000A68D
0x18000a66f  mov     rax, [rcx]
0x18000a672  cmp     [rax+8], rcx
0x18000a676  jnz     short loc_18000A68D
0x18000a678  mov     cs:ServerInstallList, rax
0x18000a67f  mov     [rax+8], r14
0x18000a683  call    FreeServerInstallEntry
0x18000a688  jmp     loc_18000A5C5
0x18000a68d  mov     ecx, 3
0x18000a692  int     29h; Win8: RtlFailFast(ecx)
0x18000a694  add     rsp, 48h
0x18000a698  pop     r14
0x18000a69a  pop     rdi
0x18000a69b  pop     rsi
0x18000a69c  pop     rbx
0x18000a69d  retn
0x180018d00  push    rbp
0x180018d02  sub     rsp, 40h
0x180018d06  mov     rbp, rdx
0x180018d09  mov     rcx, cs:qword_1800239E8; hMutex
0x180018d10  call    cs:__imp_ReleaseMutex
0x180018d16  nop
0x180018d17  add     rsp, 40h
0x180018d1b  pop     rbp
0x180018d1c  retn
0x180018d1e  push    rbp
0x180018d20  sub     rsp, 40h
0x180018d24  mov     rbp, rdx
0x180018d27  mov     rcx, cs:hMutex; hMutex
0x180018d2e  call    cs:__imp_ReleaseMutex
0x180018d34  nop
0x180018d35  add     rsp, 40h
0x180018d39  pop     rbp
0x180018d3a  retn
```
