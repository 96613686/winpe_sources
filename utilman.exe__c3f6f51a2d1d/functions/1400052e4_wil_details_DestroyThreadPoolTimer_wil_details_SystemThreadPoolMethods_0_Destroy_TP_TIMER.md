# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1400052e4`
- end: `0x140005329`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140004884`
- `0x140009c88`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140005309`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140005309`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000531d`
- `KERNEL32!SetThreadpoolTimer` at `0x1400052f5`
- `KERNEL32!SetThreadpoolTimer` at `0x1400052f5`

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
0x1400052e4  push    rbx
0x1400052e6  sub     rsp, 20h
0x1400052ea  xor     r9d, r9d; msWindowLength
0x1400052ed  xor     r8d, r8d; msPeriod
0x1400052f0  xor     edx, edx; pftDueTime
0x1400052f2  mov     rbx, rcx
0x1400052f5  call    cs:__imp_SetThreadpoolTimer
0x1400052fc  nop     dword ptr [rax+rax+00h]
0x140005301  mov     edx, 1; fCancelPendingCallbacks
0x140005306  mov     rcx, rbx; pti
0x140005309  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005310  nop     dword ptr [rax+rax+00h]
0x140005315  mov     rcx, rbx
0x140005318  add     rsp, 20h
0x14000531c  pop     rbx
0x14000531d  jmp     cs:__imp_CloseThreadpoolTimer
```
