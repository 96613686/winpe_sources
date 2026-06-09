# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140008ed0`
- end: `0x140008f04`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000a860`
- `0x140064c60`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008efd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008ee1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008ee1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008eef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008eef`

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
0x140008ed0  push    rbx
0x140008ed2  sub     rsp, 20h
0x140008ed6  xor     r9d, r9d; msWindowLength
0x140008ed9  xor     r8d, r8d; msPeriod
0x140008edc  xor     edx, edx; pftDueTime
0x140008ede  mov     rbx, rcx
0x140008ee1  call    cs:__imp_SetThreadpoolTimer
0x140008ee7  mov     edx, 1; fCancelPendingCallbacks
0x140008eec  mov     rcx, rbx; pti
0x140008eef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008ef5  mov     rcx, rbx
0x140008ef8  add     rsp, 20h
0x140008efc  pop     rbx
0x140008efd  jmp     cs:__imp_CloseThreadpoolTimer
```
