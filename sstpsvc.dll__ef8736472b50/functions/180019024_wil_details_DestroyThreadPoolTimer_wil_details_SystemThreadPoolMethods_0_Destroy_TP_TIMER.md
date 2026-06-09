# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180019024`
- end: `0x180019069`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800187c0`
- `0x18001c9b8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019049`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019049`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001905d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019035`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019035`

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
0x180019024  push    rbx
0x180019026  sub     rsp, 20h
0x18001902a  xor     r9d, r9d; msWindowLength
0x18001902d  xor     r8d, r8d; msPeriod
0x180019030  xor     edx, edx; pftDueTime
0x180019032  mov     rbx, rcx
0x180019035  call    cs:__imp_SetThreadpoolTimer
0x18001903c  nop     dword ptr [rax+rax+00h]
0x180019041  mov     edx, 1; fCancelPendingCallbacks
0x180019046  mov     rcx, rbx; pti
0x180019049  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180019050  nop     dword ptr [rax+rax+00h]
0x180019055  mov     rcx, rbx
0x180019058  add     rsp, 20h
0x18001905c  pop     rbx
0x18001905d  jmp     cs:__imp_CloseThreadpoolTimer
```
