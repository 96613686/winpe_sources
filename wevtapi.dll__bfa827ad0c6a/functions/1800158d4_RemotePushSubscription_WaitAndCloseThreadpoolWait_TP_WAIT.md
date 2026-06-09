# RemotePushSubscription::WaitAndCloseThreadpoolWait(_TP_WAIT *)

- ea: `0x1800158d4`
- end: `0x180015905`
- name: `?WaitAndCloseThreadpoolWait@RemotePushSubscription@@CAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `void __fastcall(PTP_WAIT pwa)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180014e40`
- `0x180014e88`
- `0x180015084`
- `0x1800158b8`
- `0x180016be4`
- `0x180017044`
- `0x180029210`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800158e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800158e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800158f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800158f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800158fe`

## pseudocode

```c
void __fastcall RemotePushSubscription::WaitAndCloseThreadpoolWait(PTP_WAIT pwa)
{
  SetThreadpoolWait(pwa, 0, 0);
  WaitForThreadpoolWaitCallbacks(pwa, 1);
  CloseThreadpoolWait(pwa);
}

```

## disassembly

```asm
0x1800158d4  push    rbx
0x1800158d6  sub     rsp, 20h
0x1800158da  xor     r8d, r8d; pftTimeout
0x1800158dd  xor     edx, edx; h
0x1800158df  mov     rbx, rcx
0x1800158e2  call    cs:__imp_SetThreadpoolWait
0x1800158e8  mov     edx, 1; fCancelPendingCallbacks
0x1800158ed  mov     rcx, rbx; pwa
0x1800158f0  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800158f6  mov     rcx, rbx
0x1800158f9  add     rsp, 20h
0x1800158fd  pop     rbx
0x1800158fe  jmp     cs:__imp_CloseThreadpoolWait
```
