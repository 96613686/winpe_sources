# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18003ec4c`
- end: `0x18003ec80`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800377a4`
- `0x1800377f4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003ec79`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003ec6b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003ec6b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003ec5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003ec5d`

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
0x18003ec4c  push    rbx
0x18003ec4e  sub     rsp, 20h
0x18003ec52  xor     r9d, r9d; msWindowLength
0x18003ec55  xor     r8d, r8d; msPeriod
0x18003ec58  xor     edx, edx; pftDueTime
0x18003ec5a  mov     rbx, rcx
0x18003ec5d  call    cs:__imp_SetThreadpoolTimer
0x18003ec63  mov     edx, 1; fCancelPendingCallbacks
0x18003ec68  mov     rcx, rbx; pti
0x18003ec6b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003ec71  mov     rcx, rbx
0x18003ec74  add     rsp, 20h
0x18003ec78  pop     rbx
0x18003ec79  jmp     cs:__imp_CloseThreadpoolTimer
```
