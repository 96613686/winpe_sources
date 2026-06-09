# ComCallAutoCancel::~ComCallAutoCancel(void)

- ea: `0x1400071d4`
- end: `0x1400071f9`
- name: `??1ComCallAutoCancel@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000ad50`
- `0x14000adb0`

## callees

- `0x1400071d4`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1400071e6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1400071e6`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1400071ee`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1400071ee`

## pseudocode

```c
void __fastcall ComCallAutoCancel::~ComCallAutoCancel(HANDLE *this)
{
  if ( *this )
  {
    DeleteTimerQueueTimer(0, *this, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    CoDisableCallCancellation(0);
  }
}

```

## disassembly

```asm
0x1400071d4  sub     rsp, 28h
0x1400071d8  mov     rdx, [rcx]; Timer
0x1400071db  test    rdx, rdx
0x1400071de  jz      short loc_1400071F4
0x1400071e0  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1400071e4  xor     ecx, ecx; TimerQueue
0x1400071e6  call    cs:__imp_DeleteTimerQueueTimer
0x1400071ec  xor     ecx, ecx; pReserved
0x1400071ee  call    cs:__imp_CoDisableCallCancellation
0x1400071f4  add     rsp, 28h
0x1400071f8  retn
```
