# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180007de4`
- end: `0x180007e29`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004928`
- `0x180004b74`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007e09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007e09`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007df5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007df5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007e1d`

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
0x180007de4  push    rbx
0x180007de6  sub     rsp, 20h
0x180007dea  xor     r9d, r9d; msWindowLength
0x180007ded  xor     r8d, r8d; msPeriod
0x180007df0  xor     edx, edx; pftDueTime
0x180007df2  mov     rbx, rcx
0x180007df5  call    cs:__imp_SetThreadpoolTimer
0x180007dfc  nop     dword ptr [rax+rax+00h]
0x180007e01  mov     edx, 1; fCancelPendingCallbacks
0x180007e06  mov     rcx, rbx; pti
0x180007e09  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007e10  nop     dword ptr [rax+rax+00h]
0x180007e15  mov     rcx, rbx
0x180007e18  add     rsp, 20h
0x180007e1c  pop     rbx
0x180007e1d  jmp     cs:__imp_CloseThreadpoolTimer
```
