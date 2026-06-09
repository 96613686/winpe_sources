# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001527c`
- end: `0x1800152c1`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800102c0`
- `0x18001033c`
- `0x1800118f8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800152b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001528d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001528d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800152a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800152a1`

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
0x18001527c  push    rbx
0x18001527e  sub     rsp, 20h
0x180015282  xor     r9d, r9d; msWindowLength
0x180015285  xor     r8d, r8d; msPeriod
0x180015288  xor     edx, edx; pftDueTime
0x18001528a  mov     rbx, rcx
0x18001528d  call    cs:__imp_SetThreadpoolTimer
0x180015294  nop     dword ptr [rax+rax+00h]
0x180015299  mov     edx, 1; fCancelPendingCallbacks
0x18001529e  mov     rcx, rbx; pti
0x1800152a1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800152a8  nop     dword ptr [rax+rax+00h]
0x1800152ad  mov     rcx, rbx
0x1800152b0  add     rsp, 20h
0x1800152b4  pop     rbx
0x1800152b5  jmp     cs:__imp_CloseThreadpoolTimer
```
