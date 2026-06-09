# LOG_SVC_ADMIN::PipeFlushTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18000c8f0`
- end: `0x18000c93c`
- name: `?PipeFlushTimerCallback@LOG_SVC_ADMIN@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `76`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, __int64 Timer)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c670`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c930`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c930`

## pseudocode

```c
void __fastcall LOG_SVC_ADMIN::PipeFlushTimerCallback(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, __int64 Timer)
{
  struct _TP_TIMER *v4; // rcx
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  pftDueTime = 0;
  STTABLE::Iterate(
    (STTABLE *)(Context + 175),
    (void (*)(struct STTABLE_ITEM *, unsigned __int64, int *))LOG_SVC_ADMIN::FlushPipeIter,
    Timer);
  v4 = (struct _TP_TIMER *)Context[234];
  pftDueTime = (struct _FILETIME)-300000000LL;
  SetThreadpoolTimer(v4, &pftDueTime, 0, 0);
}

```

## disassembly

```asm
0x18000c8f0  push    rbx
0x18000c8f2  sub     rsp, 20h
0x18000c8f6  mov     rbx, rdx
0x18000c8f9  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0
0x18000c902  lea     rcx, [rdx+578h]; this
0x18000c909  lea     rdx, ?FlushPipeIter@LOG_SVC_ADMIN@@CAXPEAVSTTABLE_ITEM@@_KPEAH@Z; void (*)(struct STTABLE_ITEM *, unsigned __int64, int *)
0x18000c910  call    ?Iterate@STTABLE@@QEAAXP6AXPEAVSTTABLE_ITEM@@_KPEAH@Z1@Z; STTABLE::Iterate(void (*)(STTABLE_ITEM *,unsigned __int64,int *),unsigned __int64)
0x18000c915  mov     rcx, [rbx+750h]; pti
0x18000c91c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000c921  xor     r9d, r9d; msWindowLength
0x18000c924  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x18000c92d  xor     r8d, r8d; msPeriod
0x18000c930  call    cs:__imp_SetThreadpoolTimer
0x18000c936  add     rsp, 20h
0x18000c93a  pop     rbx
0x18000c93b  retn
```
