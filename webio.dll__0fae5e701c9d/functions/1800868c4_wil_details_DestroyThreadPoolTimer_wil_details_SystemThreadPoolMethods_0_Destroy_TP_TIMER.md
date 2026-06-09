# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800868c4`
- end: `0x180086909`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18006f808`
- `0x18006f864`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800868d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800868d5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800868fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800868e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800868e9`

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
0x1800868c4  push    rbx
0x1800868c6  sub     rsp, 20h
0x1800868ca  xor     r9d, r9d; msWindowLength
0x1800868cd  xor     r8d, r8d; msPeriod
0x1800868d0  xor     edx, edx; pftDueTime
0x1800868d2  mov     rbx, rcx
0x1800868d5  call    cs:__imp_SetThreadpoolTimer
0x1800868dc  nop     dword ptr [rax+rax+00h]
0x1800868e1  mov     edx, 1; fCancelPendingCallbacks
0x1800868e6  mov     rcx, rbx; pti
0x1800868e9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800868f0  nop     dword ptr [rax+rax+00h]
0x1800868f5  mov     rcx, rbx
0x1800868f8  add     rsp, 20h
0x1800868fc  pop     rbx
0x1800868fd  jmp     cs:__imp_CloseThreadpoolTimer
```
