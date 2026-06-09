# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180041400`
- end: `0x180041445`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180039c68`
- `0x180039cc4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180041439`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180041425`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180041425`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180041411`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180041411`

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
0x180041400  push    rbx
0x180041402  sub     rsp, 20h
0x180041406  xor     r9d, r9d; msWindowLength
0x180041409  xor     r8d, r8d; msPeriod
0x18004140c  xor     edx, edx; pftDueTime
0x18004140e  mov     rbx, rcx
0x180041411  call    cs:__imp_SetThreadpoolTimer
0x180041418  nop     dword ptr [rax+rax+00h]
0x18004141d  mov     edx, 1; fCancelPendingCallbacks
0x180041422  mov     rcx, rbx; pti
0x180041425  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004142c  nop     dword ptr [rax+rax+00h]
0x180041431  mov     rcx, rbx
0x180041434  add     rsp, 20h
0x180041438  pop     rbx
0x180041439  jmp     cs:__imp_CloseThreadpoolTimer
```
