# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140014030`
- end: `0x140014075`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140011968`
- `0x14001e9dc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140014069`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014041`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014041`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140014055`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140014055`

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
0x140014030  push    rbx
0x140014032  sub     rsp, 20h
0x140014036  xor     r9d, r9d; msWindowLength
0x140014039  xor     r8d, r8d; msPeriod
0x14001403c  xor     edx, edx; pftDueTime
0x14001403e  mov     rbx, rcx
0x140014041  call    cs:__imp_SetThreadpoolTimer
0x140014048  nop     dword ptr [rax+rax+00h]
0x14001404d  mov     edx, 1; fCancelPendingCallbacks
0x140014052  mov     rcx, rbx; pti
0x140014055  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14001405c  nop     dword ptr [rax+rax+00h]
0x140014061  mov     rcx, rbx
0x140014064  add     rsp, 20h
0x140014068  pop     rbx
0x140014069  jmp     cs:__imp_CloseThreadpoolTimer
```
