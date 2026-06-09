# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18005cf10`
- end: `0x18005cf44`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18004e610`
- `0x18004e660`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005cf21`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005cf21`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005cf2f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005cf2f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005cf3d`

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
0x18005cf10  push    rbx
0x18005cf12  sub     rsp, 20h
0x18005cf16  xor     r9d, r9d; msWindowLength
0x18005cf19  xor     r8d, r8d; msPeriod
0x18005cf1c  xor     edx, edx; pftDueTime
0x18005cf1e  mov     rbx, rcx
0x18005cf21  call    cs:__imp_SetThreadpoolTimer
0x18005cf27  mov     edx, 1; fCancelPendingCallbacks
0x18005cf2c  mov     rcx, rbx; pti
0x18005cf2f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005cf35  mov     rcx, rbx
0x18005cf38  add     rsp, 20h
0x18005cf3c  pop     rbx
0x18005cf3d  jmp     cs:__imp_CloseThreadpoolTimer
```
