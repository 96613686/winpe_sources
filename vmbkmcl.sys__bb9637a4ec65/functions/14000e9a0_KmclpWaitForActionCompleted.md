# KmclpWaitForActionCompleted

- ea: `0x14000e9a0`
- end: `0x14000e9d2`
- name: `KmclpWaitForActionCompleted`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14000e9bb`
- `ntoskrnl!IoQueueWorkItem` at `0x14000e9bb`

## pseudocode

```c
__int64 __fastcall KmclpWaitForActionCompleted(__int64 a1, __int64 a2, PIO_WORKITEM *a3)
{
  IoQueueWorkItem(a3[349], KmclpWaitForActionWorkerRoutine, DelayedWorkQueue, a3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000e9a0  sub     rsp, 28h
0x14000e9a4  mov     rcx, [r8+0AE8h]; IoWorkItem
0x14000e9ab  lea     rdx, KmclpWaitForActionWorkerRoutine; WorkerRoutine
0x14000e9b2  mov     r9, r8; Context
0x14000e9b5  mov     r8d, 1; QueueType
0x14000e9bb  call    cs:__imp_IoQueueWorkItem
0x14000e9c2  nop     dword ptr [rax+rax+00h]
0x14000e9c7  mov     eax, 0C0000016h
0x14000e9cc  add     rsp, 28h
0x14000e9d0  retn
```
