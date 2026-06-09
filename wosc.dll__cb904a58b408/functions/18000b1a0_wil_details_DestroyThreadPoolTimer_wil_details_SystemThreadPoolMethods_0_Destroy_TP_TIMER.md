# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000b1a0`
- end: `0x18000b1d4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a2cc`
- `0x180011b74`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b1cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b1b1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b1b1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b1bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b1bf`

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
0x18000b1a0  push    rbx
0x18000b1a2  sub     rsp, 20h
0x18000b1a6  xor     r9d, r9d; msWindowLength
0x18000b1a9  xor     r8d, r8d; msPeriod
0x18000b1ac  xor     edx, edx; pftDueTime
0x18000b1ae  mov     rbx, rcx
0x18000b1b1  call    cs:__imp_SetThreadpoolTimer
0x18000b1b7  mov     edx, 1; fCancelPendingCallbacks
0x18000b1bc  mov     rcx, rbx; pti
0x18000b1bf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b1c5  mov     rcx, rbx
0x18000b1c8  add     rsp, 20h
0x18000b1cc  pop     rbx
0x18000b1cd  jmp     cs:__imp_CloseThreadpoolTimer
```
