# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180036654`
- end: `0x180036699`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800282cc`
- `0x18002b79c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036665`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036665`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003668d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036679`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036679`

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
0x180036654  push    rbx
0x180036656  sub     rsp, 20h
0x18003665a  xor     r9d, r9d; msWindowLength
0x18003665d  xor     r8d, r8d; msPeriod
0x180036660  xor     edx, edx; pftDueTime
0x180036662  mov     rbx, rcx
0x180036665  call    cs:__imp_SetThreadpoolTimer
0x18003666c  nop     dword ptr [rax+rax+00h]
0x180036671  mov     edx, 1; fCancelPendingCallbacks
0x180036676  mov     rcx, rbx; pti
0x180036679  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180036680  nop     dword ptr [rax+rax+00h]
0x180036685  mov     rcx, rbx
0x180036688  add     rsp, 20h
0x18003668c  pop     rbx
0x18003668d  jmp     cs:__imp_CloseThreadpoolTimer
```
