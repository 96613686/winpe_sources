# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001deb0`
- end: `0x18001dee4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001d694`
- `0x1800225a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001decf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001decf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001dec1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001dec1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001dedd`

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
0x18001deb0  push    rbx
0x18001deb2  sub     rsp, 20h
0x18001deb6  xor     r9d, r9d; msWindowLength
0x18001deb9  xor     r8d, r8d; msPeriod
0x18001debc  xor     edx, edx; pftDueTime
0x18001debe  mov     rbx, rcx
0x18001dec1  call    cs:__imp_SetThreadpoolTimer
0x18001dec7  mov     edx, 1; fCancelPendingCallbacks
0x18001decc  mov     rcx, rbx; pti
0x18001decf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001ded5  mov     rcx, rbx
0x18001ded8  add     rsp, 20h
0x18001dedc  pop     rbx
0x18001dedd  jmp     cs:__imp_CloseThreadpoolTimer
```
