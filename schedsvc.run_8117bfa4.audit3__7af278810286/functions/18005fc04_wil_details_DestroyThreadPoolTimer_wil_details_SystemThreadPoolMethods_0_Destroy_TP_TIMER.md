# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18005fc04`
- end: `0x18005fc49`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180050a1c`
- `0x180050a78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005fc15`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005fc15`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005fc29`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005fc29`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005fc3d`

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
0x18005fc04  push    rbx
0x18005fc06  sub     rsp, 20h
0x18005fc0a  xor     r9d, r9d; msWindowLength
0x18005fc0d  xor     r8d, r8d; msPeriod
0x18005fc10  xor     edx, edx; pftDueTime
0x18005fc12  mov     rbx, rcx
0x18005fc15  call    cs:__imp_SetThreadpoolTimer
0x18005fc1c  nop     dword ptr [rax+rax+00h]
0x18005fc21  mov     edx, 1; fCancelPendingCallbacks
0x18005fc26  mov     rcx, rbx; pti
0x18005fc29  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005fc30  nop     dword ptr [rax+rax+00h]
0x18005fc35  mov     rcx, rbx
0x18005fc38  add     rsp, 20h
0x18005fc3c  pop     rbx
0x18005fc3d  jmp     cs:__imp_CloseThreadpoolTimer
```
