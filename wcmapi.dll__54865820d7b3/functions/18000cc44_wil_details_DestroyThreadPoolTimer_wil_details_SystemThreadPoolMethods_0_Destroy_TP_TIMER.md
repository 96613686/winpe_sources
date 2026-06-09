# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000cc44`
- end: `0x18000cc89`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bf4c`
- `0x180010ef4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cc69`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cc69`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cc55`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cc55`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cc7d`

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
0x18000cc44  push    rbx
0x18000cc46  sub     rsp, 20h
0x18000cc4a  xor     r9d, r9d; msWindowLength
0x18000cc4d  xor     r8d, r8d; msPeriod
0x18000cc50  xor     edx, edx; pftDueTime
0x18000cc52  mov     rbx, rcx
0x18000cc55  call    cs:__imp_SetThreadpoolTimer
0x18000cc5c  nop     dword ptr [rax+rax+00h]
0x18000cc61  mov     edx, 1; fCancelPendingCallbacks
0x18000cc66  mov     rcx, rbx; pti
0x18000cc69  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cc70  nop     dword ptr [rax+rax+00h]
0x18000cc75  mov     rcx, rbx
0x18000cc78  add     rsp, 20h
0x18000cc7c  pop     rbx
0x18000cc7d  jmp     cs:__imp_CloseThreadpoolTimer
```
