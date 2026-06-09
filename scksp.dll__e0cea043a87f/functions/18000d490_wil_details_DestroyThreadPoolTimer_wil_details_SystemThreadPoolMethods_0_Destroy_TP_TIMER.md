# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000d490`
- end: `0x18000d4c4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000cb9c`
- `0x180012608`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d4bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d4af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d4af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d4a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d4a1`

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
0x18000d490  push    rbx
0x18000d492  sub     rsp, 20h
0x18000d496  xor     r9d, r9d; msWindowLength
0x18000d499  xor     r8d, r8d; msPeriod
0x18000d49c  xor     edx, edx; pftDueTime
0x18000d49e  mov     rbx, rcx
0x18000d4a1  call    cs:__imp_SetThreadpoolTimer
0x18000d4a7  mov     edx, 1; fCancelPendingCallbacks
0x18000d4ac  mov     rcx, rbx; pti
0x18000d4af  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d4b5  mov     rcx, rbx
0x18000d4b8  add     rsp, 20h
0x18000d4bc  pop     rbx
0x18000d4bd  jmp     cs:__imp_CloseThreadpoolTimer
```
