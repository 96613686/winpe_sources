# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001a108`
- end: `0x18001a13c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800093e8`
- `0x18000ad10`
- `0x1800102e8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001a135`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001a119`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001a119`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001a127`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001a127`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x18001a108  push    rbx
0x18001a10a  sub     rsp, 20h
0x18001a10e  xor     r9d, r9d; msWindowLength
0x18001a111  xor     r8d, r8d; msPeriod
0x18001a114  xor     edx, edx; pftDueTime
0x18001a116  mov     rbx, rcx
0x18001a119  call    cs:__imp_SetThreadpoolTimer
0x18001a11f  mov     edx, 1; fCancelPendingCallbacks
0x18001a124  mov     rcx, rbx; pti
0x18001a127  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001a12d  mov     rcx, rbx
0x18001a130  add     rsp, 20h
0x18001a134  pop     rbx
0x18001a135  jmp     cs:__imp_CloseThreadpoolTimer
```
