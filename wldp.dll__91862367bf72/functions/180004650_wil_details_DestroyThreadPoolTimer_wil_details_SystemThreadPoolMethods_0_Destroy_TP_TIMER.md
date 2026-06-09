# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180004650`
- end: `0x180004685`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180004400`
- `0x180004600`
- `0x18001840c`
- `0x18001933c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004661`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004661`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004678`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004678`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000466f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000466f`

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
0x180004650  push    rbx
0x180004652  sub     rsp, 20h
0x180004656  mov     rbx, rcx
0x180004659  xor     r9d, r9d; msWindowLength
0x18000465c  xor     r8d, r8d; msPeriod
0x18000465f  xor     edx, edx; pftDueTime
0x180004661  call    cs:__imp_SetThreadpoolTimer
0x180004667  mov     edx, 1; fCancelPendingCallbacks
0x18000466c  mov     rcx, rbx; pti
0x18000466f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004675  mov     rcx, rbx; pti
0x180004678  call    cs:__imp_CloseThreadpoolTimer
0x18000467e  nop
0x18000467f  add     rsp, 20h
0x180004683  pop     rbx
0x180004684  retn
```
