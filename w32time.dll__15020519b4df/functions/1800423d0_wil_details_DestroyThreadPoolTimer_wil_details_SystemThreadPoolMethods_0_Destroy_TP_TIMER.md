# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800423d0`
- end: `0x180042418`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `72`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18003a320`
- `0x18003a610`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800423f5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800423f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180042404`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180042404`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800423e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800423e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x1800423d0  push    rbx
0x1800423d2  sub     rsp, 20h
0x1800423d6  mov     rbx, rcx
0x1800423d9  xor     r9d, r9d; msWindowLength
0x1800423dc  xor     r8d, r8d; msPeriod
0x1800423df  xor     edx, edx; pftDueTime
0x1800423e1  call    cs:__imp_SetThreadpoolTimer
0x1800423e8  nop     dword ptr [rax+rax+00h]
0x1800423ed  mov     edx, 1; fCancelPendingCallbacks
0x1800423f2  mov     rcx, rbx; pti
0x1800423f5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800423fc  nop     dword ptr [rax+rax+00h]
0x180042401  mov     rcx, rbx; pti
0x180042404  call    cs:__imp_CloseThreadpoolTimer
0x18004240b  nop     dword ptr [rax+rax+00h]
0x180042410  nop
0x180042411  add     rsp, 20h
0x180042415  pop     rbx
0x180042416  retn
```
