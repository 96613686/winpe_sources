# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x1800400bc`
- end: `0x1800400ed`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18003e8d8`
- `0x1800441b0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800400e6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800400d8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800400d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800400ca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800400ca`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolWait<0>::Destroy(PTP_WAIT pwa)
{
  SetThreadpoolWait(pwa, 0, 0);
  WaitForThreadpoolWaitCallbacks(pwa, 1);
  CloseThreadpoolWait(pwa);
}

```

## disassembly

```asm
0x1800400bc  push    rbx
0x1800400be  sub     rsp, 20h
0x1800400c2  xor     r8d, r8d; pftTimeout
0x1800400c5  xor     edx, edx; h
0x1800400c7  mov     rbx, rcx
0x1800400ca  call    cs:__imp_SetThreadpoolWait
0x1800400d0  mov     edx, 1; fCancelPendingCallbacks
0x1800400d5  mov     rcx, rbx; pwa
0x1800400d8  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800400de  mov     rcx, rbx
0x1800400e1  add     rsp, 20h
0x1800400e5  pop     rbx
0x1800400e6  jmp     cs:__imp_CloseThreadpoolWait
```
