# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002266c`
- end: `0x1800226a0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180017580`
- `0x1800175d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022699`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002268b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002268b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002267d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002267d`

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
0x18002266c  push    rbx
0x18002266e  sub     rsp, 20h
0x180022672  xor     r9d, r9d; msWindowLength
0x180022675  xor     r8d, r8d; msPeriod
0x180022678  xor     edx, edx; pftDueTime
0x18002267a  mov     rbx, rcx
0x18002267d  call    cs:__imp_SetThreadpoolTimer
0x180022683  mov     edx, 1; fCancelPendingCallbacks
0x180022688  mov     rcx, rbx; pti
0x18002268b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180022691  mov     rcx, rbx
0x180022694  add     rsp, 20h
0x180022698  pop     rbx
0x180022699  jmp     cs:__imp_CloseThreadpoolTimer
```
