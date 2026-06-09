# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180008390`
- end: `0x1800083c4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180007b84`
- `0x18000bfa8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800083af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800083af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800083a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800083a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800083bd`

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
0x180008390  push    rbx
0x180008392  sub     rsp, 20h
0x180008396  xor     r9d, r9d; msWindowLength
0x180008399  xor     r8d, r8d; msPeriod
0x18000839c  xor     edx, edx; pftDueTime
0x18000839e  mov     rbx, rcx
0x1800083a1  call    cs:__imp_SetThreadpoolTimer
0x1800083a7  mov     edx, 1; fCancelPendingCallbacks
0x1800083ac  mov     rcx, rbx; pti
0x1800083af  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800083b5  mov     rcx, rbx
0x1800083b8  add     rsp, 20h
0x1800083bc  pop     rbx
0x1800083bd  jmp     cs:__imp_CloseThreadpoolTimer
```
