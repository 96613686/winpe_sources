# DataCleanupManager::Shutdown(void)

- ea: `0x18002e358`
- end: `0x18002e3db`
- name: `?Shutdown@DataCleanupManager@@QEAAXXZ`
- size: `131`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002e070`
- `0x18009b208`

## callees

- `0x18002e358`
- `0x18007e1a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e381`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e381`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e39d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e39d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e3b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002e3b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002e3ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002e3ca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002e3c1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002e3c1`

## pseudocode

```c
void __fastcall DataCleanupManager::Shutdown(LPCRITICAL_SECTION lpCriticalSection)
{
  HANDLE *p_OwningThread; // rdi
  struct _TP_TIMER *v3; // rdi

  p_OwningThread = &lpCriticalSection[1].OwningThread;
  if ( lpCriticalSection[1].OwningThread )
  {
    tlx::auto_xxx<void *,unsigned long (*)(void *),&unsigned long PowerSettingUnregisterNotification(void *),0>::_Delete(&lpCriticalSection[1].OwningThread);
    *p_OwningThread = 0;
  }
  EnterCriticalSection(lpCriticalSection);
  LODWORD(lpCriticalSection[1].DebugInfo) = 0;
  v3 = *(struct _TP_TIMER **)&lpCriticalSection[1].LockCount;
  *(_QWORD *)&lpCriticalSection[1].LockCount = 0;
  LeaveCriticalSection(lpCriticalSection);
  if ( v3 )
  {
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v3, 1);
    CloseThreadpoolTimer(v3);
  }
}

```

## disassembly

```asm
0x18002e358  mov     [rsp+arg_0], rbx
0x18002e35d  push    rdi
0x18002e35e  sub     rsp, 20h
0x18002e362  lea     rdi, [rcx+38h]
0x18002e366  mov     rbx, rcx
0x18002e369  cmp     qword ptr [rdi], 0
0x18002e36d  jz      short loc_18002E37E
0x18002e36f  mov     rcx, rdi
0x18002e372  call    ?_Delete@?$auto_xxx@PEAXP6AKPEAX@Z$1?PowerSettingUnregisterNotification@@YAK0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,ulong (*)(void *),&PowerSettingUnregisterNotification(void *),0>::_Delete(void)
0x18002e377  mov     qword ptr [rdi], 0
0x18002e37e  mov     rcx, rbx; lpCriticalSection
0x18002e381  call    cs:__imp_EnterCriticalSection
0x18002e387  mov     dword ptr [rbx+28h], 0
0x18002e38e  mov     rcx, rbx; lpCriticalSection
0x18002e391  mov     rdi, [rbx+30h]
0x18002e395  mov     qword ptr [rbx+30h], 0
0x18002e39d  call    cs:__imp_LeaveCriticalSection
0x18002e3a3  test    rdi, rdi
0x18002e3a6  jz      short loc_18002E3D0
0x18002e3a8  xor     r9d, r9d; msWindowLength
0x18002e3ab  xor     r8d, r8d; msPeriod
0x18002e3ae  xor     edx, edx; pftDueTime
0x18002e3b0  mov     rcx, rdi; pti
0x18002e3b3  call    cs:__imp_SetThreadpoolTimer
0x18002e3b9  mov     edx, 1; fCancelPendingCallbacks
0x18002e3be  mov     rcx, rdi; pti
0x18002e3c1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002e3c7  mov     rcx, rdi; pti
0x18002e3ca  call    cs:__imp_CloseThreadpoolTimer
0x18002e3d0  mov     rbx, [rsp+28h+arg_0]
0x18002e3d5  add     rsp, 20h
0x18002e3d9  pop     rdi
0x18002e3da  retn
```
