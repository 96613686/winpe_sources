# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000abc0`
- end: `0x18000abf4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800060c0`
- `0x1800069bc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000abed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000abd1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000abd1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000abdf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000abdf`

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
0x18000abc0  push    rbx
0x18000abc2  sub     rsp, 20h
0x18000abc6  xor     r9d, r9d; msWindowLength
0x18000abc9  xor     r8d, r8d; msPeriod
0x18000abcc  xor     edx, edx; pftDueTime
0x18000abce  mov     rbx, rcx
0x18000abd1  call    cs:__imp_SetThreadpoolTimer
0x18000abd7  mov     edx, 1; fCancelPendingCallbacks
0x18000abdc  mov     rcx, rbx; pti
0x18000abdf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000abe5  mov     rcx, rbx
0x18000abe8  add     rsp, 20h
0x18000abec  pop     rbx
0x18000abed  jmp     cs:__imp_CloseThreadpoolTimer
```
