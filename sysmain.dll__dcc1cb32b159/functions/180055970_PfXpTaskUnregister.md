# PfXpTaskUnregister

- ea: `0x180055970`
- end: `0x180055a89`
- name: `PfXpTaskUnregister`
- size: `281`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180055800`
- `0x180058b30`
- `0x18006f594`
- `0x180071384`

## callees

- `0x180055970`
- `0x180058d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055982`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800559bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055a30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055982`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800559bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055a30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800559a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055a18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055a71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800559a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055a18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055a71`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800559b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800559b4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800559ee`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800559ee`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055a00`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055a68`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055a00`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055a68`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180055a27`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180055a27`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180055a0f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180055a0f`

## pseudocode

```c
__int64 __fastcall PfXpTaskUnregister(LPCRITICAL_SECTION lpCriticalSection)
{
  LONG *p_LockCount; // rax
  unsigned int v3; // edi
  LONG *v4; // rsi
  HANDLE OwningThread; // rdx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  EnterCriticalSection(lpCriticalSection);
  p_LockCount = &lpCriticalSection[1].LockCount;
  if ( lpCriticalSection[1].LockCount == 52942 )
    goto LABEL_2;
  switch ( *p_LockCount )
  {
    case 52945:
      LeaveCriticalSection(lpCriticalSection);
      WaitForSingleObject(lpCriticalSection[1].DebugInfo, 0xFFFFFFFF);
      EnterCriticalSection(lpCriticalSection);
LABEL_2:
      v3 = 0;
      goto LABEL_15;
    case 52944:
      v4 = &lpCriticalSection[1].LockCount;
      break;
    case 52943:
      v4 = &lpCriticalSection[1].LockCount;
      break;
    default:
      v3 = 5023;
      goto LABEL_15;
  }
  *p_LockCount = 52945;
  ResetEvent(lpCriticalSection[1].DebugInfo);
  v3 = 0;
  if ( lpCriticalSection[1].OwningThread )
    SetEvent((HANDLE)lpCriticalSection[1].SpinCount);
  SetThreadpoolWait((PTP_WAIT)lpCriticalSection[2].DebugInfo, 0, 0);
  LeaveCriticalSection(lpCriticalSection);
  WaitForThreadpoolWaitCallbacks((PTP_WAIT)lpCriticalSection[2].DebugInfo, 1);
  EnterCriticalSection(lpCriticalSection);
  OwningThread = lpCriticalSection[1].OwningThread;
  if ( OwningThread )
  {
    PfsIdleTaskMgrUnregister(
      *(_QWORD *)&PfSvcGlobals + 4104LL,
      OwningThread,
      lpCriticalSection[1].LockSemaphore,
      lpCriticalSection[1].SpinCount);
    lpCriticalSection[1].OwningThread = 0;
  }
  DebugInfo = lpCriticalSection[1].DebugInfo;
  *v4 = 52942;
  SetEvent(DebugInfo);
LABEL_15:
  LeaveCriticalSection(lpCriticalSection);
  return v3;
}

```

## disassembly

```asm
0x180055970  mov     [rsp+arg_0], rbx
0x180055975  mov     [rsp+arg_8], rsi
0x18005597a  push    rdi
0x18005597b  sub     rsp, 20h
0x18005597f  mov     rbx, rcx
0x180055982  call    cs:__imp_EnterCriticalSection
0x180055988  lea     rax, [rbx+30h]
0x18005598c  cmp     dword ptr [rax], 0CECEh
0x180055992  jnz     short loc_18005599B
0x180055994  xor     edi, edi
0x180055996  jmp     loc_180055A6E
0x18005599b  mov     ecx, 0CED1h
0x1800559a0  cmp     [rax], ecx
0x1800559a2  jnz     short loc_1800559C5
0x1800559a4  mov     rcx, rbx; lpCriticalSection
0x1800559a7  call    cs:__imp_LeaveCriticalSection
0x1800559ad  mov     rcx, [rbx+28h]; hHandle
0x1800559b1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800559b4  call    cs:__imp_WaitForSingleObject
0x1800559ba  mov     rcx, rbx; lpCriticalSection
0x1800559bd  call    cs:__imp_EnterCriticalSection
0x1800559c3  jmp     short loc_180055994
0x1800559c5  cmp     dword ptr [rax], 0CED0h
0x1800559cb  jz      short loc_1800559DF
0x1800559cd  cmp     dword ptr [rax], 0CECFh
0x1800559d3  jz      short loc_1800559E5
0x1800559d5  mov     edi, 139Fh
0x1800559da  jmp     loc_180055A6E
0x1800559df  lea     rsi, [rbx+30h]
0x1800559e3  jmp     short loc_1800559E8
0x1800559e5  mov     rsi, rax
0x1800559e8  mov     [rax], ecx
0x1800559ea  mov     rcx, [rbx+28h]; hEvent
0x1800559ee  call    cs:__imp_ResetEvent
0x1800559f4  xor     edi, edi
0x1800559f6  cmp     [rbx+38h], rdi
0x1800559fa  jz      short loc_180055A06
0x1800559fc  mov     rcx, [rbx+48h]; hEvent
0x180055a00  call    cs:__imp_SetEvent
0x180055a06  mov     rcx, [rbx+50h]; pwa
0x180055a0a  xor     r8d, r8d; pftTimeout
0x180055a0d  xor     edx, edx; h
0x180055a0f  call    cs:__imp_SetThreadpoolWait
0x180055a15  mov     rcx, rbx; lpCriticalSection
0x180055a18  call    cs:__imp_LeaveCriticalSection
0x180055a1e  mov     rcx, [rbx+50h]; pwa
0x180055a22  mov     edx, 1; fCancelPendingCallbacks
0x180055a27  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180055a2d  mov     rcx, rbx; lpCriticalSection
0x180055a30  call    cs:__imp_EnterCriticalSection
0x180055a36  mov     rdx, [rbx+38h]
0x180055a3a  test    rdx, rdx
0x180055a3d  jz      short loc_180055A5E
0x180055a3f  mov     rcx, cs:PfSvcGlobals
0x180055a46  mov     r9, [rbx+48h]
0x180055a4a  add     rcx, 1008h
0x180055a51  mov     r8, [rbx+40h]
0x180055a55  call    PfsIdleTaskMgrUnregister
0x180055a5a  mov     [rbx+38h], rdi
0x180055a5e  mov     rcx, [rbx+28h]; hEvent
0x180055a62  mov     dword ptr [rsi], 0CECEh
0x180055a68  call    cs:__imp_SetEvent
0x180055a6e  mov     rcx, rbx; lpCriticalSection
0x180055a71  call    cs:__imp_LeaveCriticalSection
0x180055a77  mov     rbx, [rsp+28h+arg_0]
0x180055a7c  mov     eax, edi
0x180055a7e  mov     rsi, [rsp+28h+arg_8]
0x180055a83  add     rsp, 20h
0x180055a87  pop     rdi
0x180055a88  retn
```
