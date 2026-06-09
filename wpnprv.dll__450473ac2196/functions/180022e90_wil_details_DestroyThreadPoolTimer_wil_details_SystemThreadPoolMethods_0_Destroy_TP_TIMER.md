# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180022e90`
- end: `0x180022ec4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800211b4`
- `0x18002f044`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022ebd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022eaf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022eaf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022ea1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022ea1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180022e90  push    rbx
0x180022e92  sub     rsp, 20h
0x180022e96  xor     r9d, r9d; msWindowLength
0x180022e99  xor     r8d, r8d; msPeriod
0x180022e9c  xor     edx, edx; pftDueTime
0x180022e9e  mov     rbx, rcx
0x180022ea1  call    cs:__imp_SetThreadpoolTimer
0x180022ea7  mov     edx, 1; fCancelPendingCallbacks
0x180022eac  mov     rcx, rbx; pti
0x180022eaf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180022eb5  mov     rcx, rbx
0x180022eb8  add     rsp, 20h
0x180022ebc  pop     rbx
0x180022ebd  jmp     cs:__imp_CloseThreadpoolTimer
```
