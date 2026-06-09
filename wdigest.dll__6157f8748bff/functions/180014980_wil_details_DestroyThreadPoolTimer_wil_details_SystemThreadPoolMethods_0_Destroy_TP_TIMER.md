# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180014980`
- end: `0x1800149b4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180011010`
- `0x180011060`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800149ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001499f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001499f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014991`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014991`

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
0x180014980  push    rbx
0x180014982  sub     rsp, 20h
0x180014986  xor     r9d, r9d; msWindowLength
0x180014989  xor     r8d, r8d; msPeriod
0x18001498c  xor     edx, edx; pftDueTime
0x18001498e  mov     rbx, rcx
0x180014991  call    cs:__imp_SetThreadpoolTimer
0x180014997  mov     edx, 1; fCancelPendingCallbacks
0x18001499c  mov     rcx, rbx; pti
0x18001499f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800149a5  mov     rcx, rbx
0x1800149a8  add     rsp, 20h
0x1800149ac  pop     rbx
0x1800149ad  jmp     cs:__imp_CloseThreadpoolTimer
```
