# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001bd88`
- end: `0x18001bdbc`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001b8dc`
- `0x18001ce40`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bd99`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bd99`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001bdb5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001bda7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001bda7`

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
0x18001bd88  push    rbx
0x18001bd8a  sub     rsp, 20h
0x18001bd8e  xor     r9d, r9d; msWindowLength
0x18001bd91  xor     r8d, r8d; msPeriod
0x18001bd94  xor     edx, edx; pftDueTime
0x18001bd96  mov     rbx, rcx
0x18001bd99  call    cs:__imp_SetThreadpoolTimer
0x18001bd9f  mov     edx, 1; fCancelPendingCallbacks
0x18001bda4  mov     rcx, rbx; pti
0x18001bda7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001bdad  mov     rcx, rbx
0x18001bdb0  add     rsp, 20h
0x18001bdb4  pop     rbx
0x18001bdb5  jmp     cs:__imp_CloseThreadpoolTimer
```
