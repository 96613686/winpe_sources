# RegisterForSessionChangeNotifications(_REDIRECTION_CONTEXT *)

- ea: `0x1800062f0`
- end: `0x1800063ef`
- name: `?RegisterForSessionChangeNotifications@@YAHPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007940`

## callees

- `0x1800062f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006302`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006328`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006302`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006328`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006376`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800063c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006376`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800063c0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000639a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000639a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180006347`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180006356`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180006387`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800063e7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180006347`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180006356`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180006387`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800063e7`
- `ntdll!RtlDllShutdownInProgress` at `0x180006312`
- `ntdll!RtlDllShutdownInProgress` at `0x180006334`
- `ntdll!RtlDllShutdownInProgress` at `0x180006312`
- `ntdll!RtlDllShutdownInProgress` at `0x180006334`
- `WINSTA!WinStationRegisterCurrentSessionNotificationEvent` at `0x1800063b1`
- `WINSTA!WinStationRegisterCurrentSessionNotificationEvent` at `0x1800063b1`
- `WINSTA!WinStationUnRegisterNotificationEvent` at `0x180006365`
- `WINSTA!WinStationUnRegisterNotificationEvent` at `0x180006365`

## pseudocode

```c
__int64 __fastcall RegisterForSessionChangeNotifications(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v2; // esi

  EnterCriticalSection(lpCriticalSection);
  if ( LOBYTE(lpCriticalSection[1].DebugInfo) || RtlDllShutdownInProgress() )
    goto LABEL_12;
  v2 = 1;
  EnterCriticalSection(lpCriticalSection);
  if ( !LOBYTE(lpCriticalSection[1].DebugInfo) && !RtlDllShutdownInProgress() )
  {
    SetThreadpoolWait((PTP_WAIT)lpCriticalSection[2].OwningThread, 0, 0);
    SetThreadpoolWait((PTP_WAIT)lpCriticalSection[2].SpinCount, 0, 0);
  }
  if ( lpCriticalSection[3].DebugInfo )
  {
    WinStationUnRegisterNotificationEvent();
    lpCriticalSection[3].DebugInfo = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  SetThreadpoolWait((PTP_WAIT)lpCriticalSection[2].SpinCount, lpCriticalSection[2].LockSemaphore, 0);
  if ( !lpCriticalSection[3].DebugInfo )
  {
    if ( WaitForSingleObject(*(HANDLE *)&lpCriticalSection[2].LockCount, 0) )
    {
      SetThreadpoolWait((PTP_WAIT)lpCriticalSection[2].OwningThread, *(HANDLE *)&lpCriticalSection[2].LockCount, 0);
      goto LABEL_11;
    }
    v2 = WinStationRegisterCurrentSessionNotificationEvent(
           lpCriticalSection[2].LockSemaphore,
           15,
           &lpCriticalSection[3]);
    if ( !v2 )
LABEL_12:
      v2 = 0;
  }
LABEL_11:
  LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x1800062f0  mov     [rsp+arg_0], rbx
0x1800062f5  mov     [rsp+arg_8], rsi
0x1800062fa  push    rdi
0x1800062fb  sub     rsp, 20h
0x1800062ff  mov     rbx, rcx
0x180006302  call    cs:__imp_EnterCriticalSection
0x180006308  cmp     byte ptr [rbx+28h], 0
0x18000630c  jnz     loc_1800063D8
0x180006312  call    cs:__imp_RtlDllShutdownInProgress
0x180006318  test    al, al
0x18000631a  jnz     loc_1800063D8
0x180006320  mov     rcx, rbx; lpCriticalSection
0x180006323  mov     esi, 1
0x180006328  call    cs:__imp_EnterCriticalSection
0x18000632e  cmp     byte ptr [rbx+28h], 0
0x180006332  jnz     short loc_18000635C
0x180006334  call    cs:__imp_RtlDllShutdownInProgress
0x18000633a  test    al, al
0x18000633c  jnz     short loc_18000635C
0x18000633e  mov     rcx, [rbx+60h]; pwa
0x180006342  xor     r8d, r8d; pftTimeout
0x180006345  xor     edx, edx; h
0x180006347  call    cs:__imp_SetThreadpoolWait
0x18000634d  mov     rcx, [rbx+70h]; pwa
0x180006351  xor     r8d, r8d; pftTimeout
0x180006354  xor     edx, edx; h
0x180006356  call    cs:__imp_SetThreadpoolWait
0x18000635c  mov     rcx, [rbx+78h]
0x180006360  test    rcx, rcx
0x180006363  jz      short loc_180006373
0x180006365  call    cs:__imp_WinStationUnRegisterNotificationEvent
0x18000636b  mov     qword ptr [rbx+78h], 0
0x180006373  mov     rcx, rbx; lpCriticalSection
0x180006376  call    cs:__imp_LeaveCriticalSection
0x18000637c  mov     rdx, [rbx+68h]; h
0x180006380  xor     r8d, r8d; pftTimeout
0x180006383  mov     rcx, [rbx+70h]; pwa
0x180006387  call    cs:__imp_SetThreadpoolWait
0x18000638d  cmp     qword ptr [rbx+78h], 0
0x180006392  jnz     short loc_1800063BD
0x180006394  mov     rcx, [rbx+58h]; hHandle
0x180006398  xor     edx, edx; dwMilliseconds
0x18000639a  call    cs:__imp_WaitForSingleObject
0x1800063a0  test    eax, eax
0x1800063a2  jnz     short loc_1800063DC
0x1800063a4  mov     rcx, [rbx+68h]
0x1800063a8  lea     r8, [rbx+78h]
0x1800063ac  mov     edx, 0Fh
0x1800063b1  call    cs:__imp_WinStationRegisterCurrentSessionNotificationEvent
0x1800063b7  mov     esi, eax
0x1800063b9  test    eax, eax
0x1800063bb  jz      short loc_1800063D8
0x1800063bd  mov     rcx, rbx; lpCriticalSection
0x1800063c0  call    cs:__imp_LeaveCriticalSection
0x1800063c6  mov     rbx, [rsp+28h+arg_0]
0x1800063cb  mov     eax, esi
0x1800063cd  mov     rsi, [rsp+28h+arg_8]
0x1800063d2  add     rsp, 20h
0x1800063d6  pop     rdi
0x1800063d7  retn
0x1800063d8  xor     esi, esi
0x1800063da  jmp     short loc_1800063BD
0x1800063dc  mov     rdx, [rbx+58h]; h
0x1800063e0  xor     r8d, r8d; pftTimeout
0x1800063e3  mov     rcx, [rbx+60h]; pwa
0x1800063e7  call    cs:__imp_SetThreadpoolWait
0x1800063ed  jmp     short loc_1800063BD
```
