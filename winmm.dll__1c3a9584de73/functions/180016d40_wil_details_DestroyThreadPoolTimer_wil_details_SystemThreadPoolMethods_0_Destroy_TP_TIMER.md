# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180016d40`
- end: `0x180016d74`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800064a4`
- `0x180006518`
- `0x18000660c`
- `0x1800066c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016d5f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016d5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016d51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016d51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016d6d`

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
0x180016d40  push    rbx
0x180016d42  sub     rsp, 20h
0x180016d46  xor     r9d, r9d; msWindowLength
0x180016d49  xor     r8d, r8d; msPeriod
0x180016d4c  xor     edx, edx; pftDueTime
0x180016d4e  mov     rbx, rcx
0x180016d51  call    cs:__imp_SetThreadpoolTimer
0x180016d57  mov     edx, 1; fCancelPendingCallbacks
0x180016d5c  mov     rcx, rbx; pti
0x180016d5f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016d65  mov     rcx, rbx
0x180016d68  add     rsp, 20h
0x180016d6c  pop     rbx
0x180016d6d  jmp     cs:__imp_CloseThreadpoolTimer
```
