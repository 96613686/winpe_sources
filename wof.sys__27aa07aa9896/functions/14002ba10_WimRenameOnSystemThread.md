# WimRenameOnSystemThread

- ea: `0x14002ba10`
- end: `0x14002bad4`
- name: `WimRenameOnSystemThread`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002be3c`
- `0x14003c5c8`

## callees

- `0x1400119c0`
- `0x14002ba10`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002baba`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002baba`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002ba39`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002ba39`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002ba98`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002ba98`
- `ntoskrnl!KeInitializeEvent` at `0x14002ba60`
- `ntoskrnl!KeInitializeEvent` at `0x14002ba60`

## pseudocode

```c
__int64 __fastcall WimRenameOnSystemThread(__int64 a1, __int64 a2, __int64 a3)
{
  struct _IO_WORKITEM *WorkItem; // rbx
  _BYTE Context[96]; // [rsp+30h] [rbp-68h] BYREF

  memset(Context, 0, 0x40u);
  WorkItem = IoAllocateWorkItem(DeviceObject);
  if ( !WorkItem )
    return 3221225626LL;
  KeInitializeEvent((PRKEVENT)&Context[32], SynchronizationEvent, 0);
  *(_QWORD *)Context = a1;
  *(_QWORD *)&Context[8] = a2;
  *(_QWORD *)&Context[16] = a3;
  *(_DWORD *)&Context[24] = 48;
  IoQueueWorkItemEx(WorkItem, WimPerformRenameWorker, DelayedWorkQueue, Context);
  KeWaitForSingleObject(&Context[32], Executive, 0, 0, 0);
  return *(unsigned int *)&Context[56];
}

```

## disassembly

```asm
0x14002ba10  push    rbx
0x14002ba12  push    rbp
0x14002ba13  push    rsi
0x14002ba14  push    rdi
0x14002ba15  sub     rsp, 78h
0x14002ba19  mov     rsi, rdx
0x14002ba1c  mov     rdi, r8
0x14002ba1f  xor     edx, edx; Val
0x14002ba21  mov     rbp, rcx
0x14002ba24  lea     rcx, [rsp+98h+Context]; void *
0x14002ba29  lea     r8d, [rdx+40h]; Size
0x14002ba2d  call    memset
0x14002ba32  mov     rcx, cs:DeviceObject; DeviceObject
0x14002ba39  call    cs:__imp_IoAllocateWorkItem
0x14002ba40  nop     dword ptr [rax+rax+00h]
0x14002ba45  mov     rbx, rax
0x14002ba48  test    rax, rax
0x14002ba4b  jnz     short loc_14002BA54
0x14002ba4d  mov     eax, 0C000009Ah
0x14002ba52  jmp     short loc_14002BACA
0x14002ba54  xor     r8d, r8d; State
0x14002ba57  lea     rcx, [rsp+98h+Event]; Event
0x14002ba5c  lea     edx, [r8+1]; Type
0x14002ba60  call    cs:__imp_KeInitializeEvent
0x14002ba67  nop     dword ptr [rax+rax+00h]
0x14002ba6c  lea     r9, [rsp+98h+Context]; Context
0x14002ba71  mov     [rsp+98h+Context], rbp
0x14002ba76  mov     r8d, 1; QueueType
0x14002ba7c  mov     [rsp+98h+var_60], rsi
0x14002ba81  lea     rdx, WimPerformRenameWorker; WorkerRoutine
0x14002ba88  mov     [rsp+98h+var_58], rdi
0x14002ba8d  mov     rcx, rbx; IoWorkItem
0x14002ba90  mov     [rsp+98h+var_50], 30h ; '0'
0x14002ba98  call    cs:__imp_IoQueueWorkItemEx
0x14002ba9f  nop     dword ptr [rax+rax+00h]
0x14002baa4  xor     r9d, r9d; Alertable
0x14002baa7  mov     [rsp+98h+Timeout], 0; Timeout
0x14002bab0  xor     r8d, r8d; WaitMode
0x14002bab3  lea     rcx, [rsp+98h+Event]; Object
0x14002bab8  xor     edx, edx; WaitReason
0x14002baba  call    cs:__imp_KeWaitForSingleObject
0x14002bac1  nop     dword ptr [rax+rax+00h]
0x14002bac6  mov     eax, [rsp+98h+var_30]
0x14002baca  add     rsp, 78h
0x14002bace  pop     rdi
0x14002bacf  pop     rsi
0x14002bad0  pop     rbp
0x14002bad1  pop     rbx
0x14002bad2  retn
```
