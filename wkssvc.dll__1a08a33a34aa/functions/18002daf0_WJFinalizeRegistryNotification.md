# WJFinalizeRegistryNotification

- ea: `0x18002daf0`
- end: `0x18002dbf8`
- name: `WJFinalizeRegistryNotification`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002e6ac`

## callees

- `0x18002daf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dba9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dbc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dbc5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002db6f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002db6f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002db4a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002db4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002db5f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002db5f`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002db07`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002db35`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002db95`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002db07`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002db35`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002db95`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002dbec`

## string_xrefs

- `0x18002daf9`: `WJFinalizeRegistryNotification`
- `0x18002db27`: `WJFinalizeRegistryNotification`
- `0x18002db7f`: `WJFinalizeRegistryNotification`
- `0x18002dbd9`: `WJFinalizeRegistryNotification`
- `0x18002db2e`: `AutoJoinSvc/%s: Canceling thread pool wait for %s registry key change notifications.`
- `0x18002db86`: `AutoJoinSvc/%s: Thread pool wait for %s registry key change notifications is cancelled.`

## pseudocode

```c
__int64 __fastcall WJFinalizeRegistryNotification(__int64 a1)
{
  __int64 v2; // r8
  void *v3; // rcx

  DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: started", L"WJFinalizeRegistryNotification");
  if ( a1 )
  {
    if ( *(_QWORD *)(a1 + 16) )
    {
      DsrWriteAutoJoinSvcDebugEvent(
        L"AutoJoinSvc/%s: Canceling thread pool wait for %s registry key change notifications.",
        L"WJFinalizeRegistryNotification",
        *(_QWORD *)(a1 + 32));
      SetThreadpoolWait(*(PTP_WAIT *)(a1 + 16), 0, 0);
      WaitForThreadpoolWaitCallbacks(*(PTP_WAIT *)(a1 + 16), 1);
      CloseThreadpoolWait(*(PTP_WAIT *)(a1 + 16));
      v2 = *(_QWORD *)(a1 + 32);
      *(_QWORD *)(a1 + 16) = 0;
      DsrWriteAutoJoinSvcDebugEvent(
        L"AutoJoinSvc/%s: Thread pool wait for %s registry key change notifications is cancelled.",
        L"WJFinalizeRegistryNotification",
        v2);
    }
    if ( *(_QWORD *)a1 )
    {
      RegCloseKey(*(HKEY *)a1);
      *(_QWORD *)a1 = 0;
    }
    v3 = *(void **)(a1 + 8);
    if ( v3 )
    {
      CloseHandle(v3);
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
  return DsrWriteAutoJoinSvcDebugEvent(L"AutoJoinSvc/%s: finished", L"WJFinalizeRegistryNotification");
}

```

## disassembly

```asm
0x18002daf0  push    rbx
0x18002daf2  sub     rsp, 20h
0x18002daf6  mov     rbx, rcx
0x18002daf9  lea     rdx, aWjfinalizeregi; "WJFinalizeRegistryNotification"
0x18002db00  lea     rcx, aAutojoinsvcSSt_1; "AutoJoinSvc/%s: started"
0x18002db07  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002db0e  nop     dword ptr [rax+rax+00h]
0x18002db13  test    rbx, rbx
0x18002db16  jz      loc_18002DBD9
0x18002db1c  cmp     qword ptr [rbx+10h], 0
0x18002db21  jz      short loc_18002DBA1
0x18002db23  mov     r8, [rbx+20h]
0x18002db27  lea     rdx, aWjfinalizeregi; "WJFinalizeRegistryNotification"
0x18002db2e  lea     rcx, aAutojoinsvcSCa_1; "AutoJoinSvc/%s: Canceling thread pool w"...
0x18002db35  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002db3c  nop     dword ptr [rax+rax+00h]
0x18002db41  mov     rcx, [rbx+10h]; pwa
0x18002db45  xor     r8d, r8d; pftTimeout
0x18002db48  xor     edx, edx; h
0x18002db4a  call    cs:__imp_SetThreadpoolWait
0x18002db51  nop     dword ptr [rax+rax+00h]
0x18002db56  mov     rcx, [rbx+10h]; pwa
0x18002db5a  mov     edx, 1; fCancelPendingCallbacks
0x18002db5f  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18002db66  nop     dword ptr [rax+rax+00h]
0x18002db6b  mov     rcx, [rbx+10h]; pwa
0x18002db6f  call    cs:__imp_CloseThreadpoolWait
0x18002db76  nop     dword ptr [rax+rax+00h]
0x18002db7b  mov     r8, [rbx+20h]
0x18002db7f  lea     rdx, aWjfinalizeregi; "WJFinalizeRegistryNotification"
0x18002db86  lea     rcx, aAutojoinsvcSTh; "AutoJoinSvc/%s: Thread pool wait for %s"...
0x18002db8d  mov     qword ptr [rbx+10h], 0
0x18002db95  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002db9c  nop     dword ptr [rax+rax+00h]
0x18002dba1  mov     rcx, [rbx]; hKey
0x18002dba4  test    rcx, rcx
0x18002dba7  jz      short loc_18002DBBC
0x18002dba9  call    cs:__imp_RegCloseKey
0x18002dbb0  nop     dword ptr [rax+rax+00h]
0x18002dbb5  mov     qword ptr [rbx], 0
0x18002dbbc  mov     rcx, [rbx+8]; hObject
0x18002dbc0  test    rcx, rcx
0x18002dbc3  jz      short loc_18002DBD9
0x18002dbc5  call    cs:__imp_CloseHandle
0x18002dbcc  nop     dword ptr [rax+rax+00h]
0x18002dbd1  mov     qword ptr [rbx+8], 0
0x18002dbd9  lea     rdx, aWjfinalizeregi; "WJFinalizeRegistryNotification"
0x18002dbe0  lea     rcx, aAutojoinsvcSFi; "AutoJoinSvc/%s: finished"
0x18002dbe7  add     rsp, 20h
0x18002dbeb  pop     rbx
0x18002dbec  jmp     cs:__imp_DsrWriteAutoJoinSvcDebugEvent
```
