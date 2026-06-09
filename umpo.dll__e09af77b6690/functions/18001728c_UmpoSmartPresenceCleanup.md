# UmpoSmartPresenceCleanup

- ea: `0x18001728c`
- end: `0x180017355`
- name: `UmpoSmartPresenceCleanup`
- size: `201`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180015280`

## callees

- `0x180009ad0`
- `0x18001728c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180017304`
- `ntdll!RtlFreeHeap` at `0x180017304`
- `ntdll!DbgPrint` at `0x18001732d`
- `ntdll!DbgPrint` at `0x18001732d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800172ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800172ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800172bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800172c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800172bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800172c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017343`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017343`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800172d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800172e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800172d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800172e2`

## pseudocode

```c
void UmpoSmartPresenceCleanup()
{
  if ( UmpoSmartPresenceEnabled )
  {
    UmpoSmartPresenceFreeIntervals();
    WaitForThreadpoolWaitCallbacks(UmpoTimeUpdateWork, 1);
    CloseThreadpoolWait(UmpoTimeUpdateWork);
    CloseThreadpoolWait(UmpoTimerWork);
    CloseHandle(hObject);
    CloseHandle(h);
    UmpoSmartPresenceEnabled = 0;
    if ( UmpoNullSid )
    {
      RtlFreeHeap(UmpoHeapHandle, 0, UmpoNullSid);
      UmpoNullSid = 0;
    }
    if ( (UmpoDebug & 2) != 0 )
      DbgPrint("%s: Disabled support\n", "UmpoSmartPresenceCleanup");
  }
  if ( byte_180024808 )
  {
    DeleteCriticalSection(&UmpoSmartPresenceLock);
    byte_180024808 = 0;
  }
}

```

## disassembly

```asm
0x18001728c  sub     rsp, 28h
0x180017290  cmp     cs:UmpoSmartPresenceEnabled, 0
0x180017297  jz      loc_180017333
0x18001729d  call    UmpoSmartPresenceFreeIntervals
0x1800172a2  mov     rcx, cs:UmpoTimeUpdateWork; pwa
0x1800172a9  mov     edx, 1; fCancelPendingCallbacks
0x1800172ae  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800172b4  mov     rcx, cs:UmpoTimeUpdateWork; pwa
0x1800172bb  call    cs:__imp_CloseThreadpoolWait
0x1800172c1  mov     rcx, cs:UmpoTimerWork; pwa
0x1800172c8  call    cs:__imp_CloseThreadpoolWait
0x1800172ce  mov     rcx, cs:hObject; hObject
0x1800172d5  call    cs:__imp_CloseHandle
0x1800172db  mov     rcx, cs:h; hObject
0x1800172e2  call    cs:__imp_CloseHandle
0x1800172e8  mov     r8, cs:UmpoNullSid; P
0x1800172ef  mov     cs:UmpoSmartPresenceEnabled, 0
0x1800172f6  test    r8, r8
0x1800172f9  jz      short loc_180017315
0x1800172fb  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180017302  xor     edx, edx; Flags
0x180017304  call    cs:__imp_RtlFreeHeap
0x18001730a  mov     cs:UmpoNullSid, 0
0x180017315  mov     eax, cs:UmpoDebug
0x18001731b  test    al, 2
0x18001731d  jz      short loc_180017333
0x18001731f  lea     rdx, aUmposmartprese_4; "UmpoSmartPresenceCleanup"
0x180017326  lea     rcx, aSDisabledSuppo; "%s: Disabled support\n"
0x18001732d  call    cs:__imp_DbgPrint
0x180017333  cmp     cs:byte_180024808, 0
0x18001733a  jz      short loc_180017350
0x18001733c  lea     rcx, UmpoSmartPresenceLock; lpCriticalSection
0x180017343  call    cs:__imp_DeleteCriticalSection
0x180017349  mov     cs:byte_180024808, 0
0x180017350  add     rsp, 28h
0x180017354  retn
```
