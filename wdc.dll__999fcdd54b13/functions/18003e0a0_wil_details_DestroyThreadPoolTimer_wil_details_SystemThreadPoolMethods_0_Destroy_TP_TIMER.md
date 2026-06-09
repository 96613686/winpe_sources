# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18003e0a0`
- end: `0x18003e0d4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180022df8`
- `0x180022e48`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18003e0b1`
- `KERNEL32!SetThreadpoolTimer` at `0x18003e0b1`
- `KERNEL32!CloseThreadpoolTimer` at `0x18003e0cd`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18003e0bf`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18003e0bf`

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
0x18003e0a0  push    rbx
0x18003e0a2  sub     rsp, 20h
0x18003e0a6  xor     r9d, r9d; msWindowLength
0x18003e0a9  xor     r8d, r8d; msPeriod
0x18003e0ac  xor     edx, edx; pftDueTime
0x18003e0ae  mov     rbx, rcx
0x18003e0b1  call    cs:__imp_SetThreadpoolTimer
0x18003e0b7  mov     edx, 1; fCancelPendingCallbacks
0x18003e0bc  mov     rcx, rbx; pti
0x18003e0bf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003e0c5  mov     rcx, rbx
0x18003e0c8  add     rsp, 20h
0x18003e0cc  pop     rbx
0x18003e0cd  jmp     cs:__imp_CloseThreadpoolTimer
```
