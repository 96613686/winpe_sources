# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180048464`
- end: `0x1800484a9`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180032b0c`
- `0x180042ac4`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180048475`
- `KERNEL32!SetThreadpoolTimer` at `0x180048475`
- `KERNEL32!CloseThreadpoolTimer` at `0x18004849d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180048489`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180048489`

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
0x180048464  push    rbx
0x180048466  sub     rsp, 20h
0x18004846a  xor     r9d, r9d; msWindowLength
0x18004846d  xor     r8d, r8d; msPeriod
0x180048470  xor     edx, edx; pftDueTime
0x180048472  mov     rbx, rcx
0x180048475  call    cs:__imp_SetThreadpoolTimer
0x18004847c  nop     dword ptr [rax+rax+00h]
0x180048481  mov     edx, 1; fCancelPendingCallbacks
0x180048486  mov     rcx, rbx; pti
0x180048489  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180048490  nop     dword ptr [rax+rax+00h]
0x180048495  mov     rcx, rbx
0x180048498  add     rsp, 20h
0x18004849c  pop     rbx
0x18004849d  jmp     cs:__imp_CloseThreadpoolTimer
```
