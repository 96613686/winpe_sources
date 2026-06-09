# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18004cfe4`
- end: `0x18004d029`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18003ff80`
- `0x18003ffdc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004d009`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004d009`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004cff5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004cff5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004d01d`

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
0x18004cfe4  push    rbx
0x18004cfe6  sub     rsp, 20h
0x18004cfea  xor     r9d, r9d; msWindowLength
0x18004cfed  xor     r8d, r8d; msPeriod
0x18004cff0  xor     edx, edx; pftDueTime
0x18004cff2  mov     rbx, rcx
0x18004cff5  call    cs:__imp_SetThreadpoolTimer
0x18004cffc  nop     dword ptr [rax+rax+00h]
0x18004d001  mov     edx, 1; fCancelPendingCallbacks
0x18004d006  mov     rcx, rbx; pti
0x18004d009  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004d010  nop     dword ptr [rax+rax+00h]
0x18004d015  mov     rcx, rbx
0x18004d018  add     rsp, 20h
0x18004d01c  pop     rbx
0x18004d01d  jmp     cs:__imp_CloseThreadpoolTimer
```
