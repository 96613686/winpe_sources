# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x1400551c4`
- end: `0x1400551f5`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14005303c`
- `0x14005beb0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400551d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400551d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1400551ee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1400551e0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1400551e0`

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
0x1400551c4  push    rbx
0x1400551c6  sub     rsp, 20h
0x1400551ca  xor     r8d, r8d; pftTimeout
0x1400551cd  xor     edx, edx; h
0x1400551cf  mov     rbx, rcx
0x1400551d2  call    cs:__imp_SetThreadpoolWait
0x1400551d8  mov     edx, 1; fCancelPendingCallbacks
0x1400551dd  mov     rcx, rbx; pwa
0x1400551e0  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1400551e6  mov     rcx, rbx
0x1400551e9  add     rsp, 20h
0x1400551ed  pop     rbx
0x1400551ee  jmp     cs:__imp_CloseThreadpoolWait
```
