# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180037ed0`
- end: `0x180037f04`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180020414`
- `0x180033a78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180037ee1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180037ee1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180037efd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180037eef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180037eef`

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
0x180037ed0  push    rbx
0x180037ed2  sub     rsp, 20h
0x180037ed6  xor     r9d, r9d; msWindowLength
0x180037ed9  xor     r8d, r8d; msPeriod
0x180037edc  xor     edx, edx; pftDueTime
0x180037ede  mov     rbx, rcx
0x180037ee1  call    cs:__imp_SetThreadpoolTimer
0x180037ee7  mov     edx, 1; fCancelPendingCallbacks
0x180037eec  mov     rcx, rbx; pti
0x180037eef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180037ef5  mov     rcx, rbx
0x180037ef8  add     rsp, 20h
0x180037efc  pop     rbx
0x180037efd  jmp     cs:__imp_CloseThreadpoolTimer
```
