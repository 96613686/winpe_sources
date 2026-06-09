# ImportContactsManager::Shutdown(void)

- ea: `0x18002e778`
- end: `0x18002e7fa`
- name: `?Shutdown@ImportContactsManager@@QEAAXXZ`
- size: `130`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002e070`
- `0x18009ae8c`

## callees

- `0x18002e778`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e78a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e78a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e7ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e7ab`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x18002e7e4`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x18002e7e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002e7be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002e7be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002e7d5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18002e7d5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002e7cc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002e7cc`

## pseudocode

```c
void __fastcall ImportContactsManager::Shutdown(LPCRITICAL_SECTION lpCriticalSection)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdi
  struct _TP_WAIT *v3; // rsi

  EnterCriticalSection(lpCriticalSection);
  DebugInfo = lpCriticalSection[1].DebugInfo;
  lpCriticalSection[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)-1LL;
  v3 = *(struct _TP_WAIT **)&lpCriticalSection[1].LockCount;
  *(_QWORD *)&lpCriticalSection[1].LockCount = 0;
  LeaveCriticalSection(lpCriticalSection);
  if ( v3 )
  {
    SetThreadpoolWait(v3, 0, 0);
    WaitForThreadpoolWaitCallbacks(v3, 1);
    CloseThreadpoolWait(v3);
  }
  if ( DebugInfo != (PRTL_CRITICAL_SECTION_DEBUG)-1LL )
    FindCloseChangeNotification(DebugInfo);
}

```

## disassembly

```asm
0x18002e778  mov     [rsp+arg_0], rbx
0x18002e77d  mov     [rsp+arg_8], rsi
0x18002e782  push    rdi
0x18002e783  sub     rsp, 20h
0x18002e787  mov     rbx, rcx
0x18002e78a  call    cs:__imp_EnterCriticalSection
0x18002e790  mov     rdi, [rbx+28h]
0x18002e794  mov     rcx, rbx; lpCriticalSection
0x18002e797  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x18002e79f  mov     rsi, [rbx+30h]
0x18002e7a3  mov     qword ptr [rbx+30h], 0
0x18002e7ab  call    cs:__imp_LeaveCriticalSection
0x18002e7b1  test    rsi, rsi
0x18002e7b4  jz      short loc_18002E7DB
0x18002e7b6  xor     r8d, r8d; pftTimeout
0x18002e7b9  xor     edx, edx; h
0x18002e7bb  mov     rcx, rsi; pwa
0x18002e7be  call    cs:__imp_SetThreadpoolWait
0x18002e7c4  mov     edx, 1; fCancelPendingCallbacks
0x18002e7c9  mov     rcx, rsi; pwa
0x18002e7cc  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18002e7d2  mov     rcx, rsi; pwa
0x18002e7d5  call    cs:__imp_CloseThreadpoolWait
0x18002e7db  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002e7df  jz      short loc_18002E7EA
0x18002e7e1  mov     rcx, rdi; hChangeHandle
0x18002e7e4  call    cs:__imp_FindCloseChangeNotification
0x18002e7ea  mov     rbx, [rsp+28h+arg_0]
0x18002e7ef  mov     rsi, [rsp+28h+arg_8]
0x18002e7f4  add     rsp, 20h
0x18002e7f8  pop     rdi
0x18002e7f9  retn
```
