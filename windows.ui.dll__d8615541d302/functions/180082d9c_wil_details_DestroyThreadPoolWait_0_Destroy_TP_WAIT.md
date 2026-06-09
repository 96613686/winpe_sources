# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180082d9c`
- end: `0x180082dcd`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180081058`
- `0x180088854`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180082daa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180082daa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180082dc6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180082db8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180082db8`

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
0x180082d9c  push    rbx
0x180082d9e  sub     rsp, 20h
0x180082da2  xor     r8d, r8d; pftTimeout
0x180082da5  xor     edx, edx; h
0x180082da7  mov     rbx, rcx
0x180082daa  call    cs:__imp_SetThreadpoolWait
0x180082db0  mov     edx, 1; fCancelPendingCallbacks
0x180082db5  mov     rcx, rbx; pwa
0x180082db8  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180082dbe  mov     rcx, rbx
0x180082dc1  add     rsp, 20h
0x180082dc5  pop     rbx
0x180082dc6  jmp     cs:__imp_CloseThreadpoolWait
```
