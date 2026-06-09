# WimRenameOnSystemThread

- ea: `0x14002b9c0`
- end: `0x14002ba84`
- name: `WimRenameOnSystemThread`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14002bdec`
- `0x14003c578`

## callees

- `0x1400119c0`
- `0x14002b9c0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002ba6a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002ba6a`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002b9e9`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002b9e9`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002ba48`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002ba48`
- `ntoskrnl!KeInitializeEvent` at `0x14002ba10`
- `ntoskrnl!KeInitializeEvent` at `0x14002ba10`

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
0x14002b9c0  push    rbx
0x14002b9c2  push    rbp
0x14002b9c3  push    rsi
0x14002b9c4  push    rdi
0x14002b9c5  sub     rsp, 78h
0x14002b9c9  mov     rsi, rdx
0x14002b9cc  mov     rdi, r8
0x14002b9cf  xor     edx, edx; Val
0x14002b9d1  mov     rbp, rcx
0x14002b9d4  lea     rcx, [rsp+98h+Context]; void *
0x14002b9d9  lea     r8d, [rdx+40h]; Size
0x14002b9dd  call    memset
0x14002b9e2  mov     rcx, cs:DeviceObject; DeviceObject
0x14002b9e9  call    cs:__imp_IoAllocateWorkItem
0x14002b9f0  nop     dword ptr [rax+rax+00h]
0x14002b9f5  mov     rbx, rax
0x14002b9f8  test    rax, rax
0x14002b9fb  jnz     short loc_14002BA04
0x14002b9fd  mov     eax, 0C000009Ah
0x14002ba02  jmp     short loc_14002BA7A
0x14002ba04  xor     r8d, r8d; State
0x14002ba07  lea     rcx, [rsp+98h+Event]; Event
0x14002ba0c  lea     edx, [r8+1]; Type
0x14002ba10  call    cs:__imp_KeInitializeEvent
0x14002ba17  nop     dword ptr [rax+rax+00h]
0x14002ba1c  lea     r9, [rsp+98h+Context]; Context
0x14002ba21  mov     [rsp+98h+Context], rbp
0x14002ba26  mov     r8d, 1; QueueType
0x14002ba2c  mov     [rsp+98h+var_60], rsi
0x14002ba31  lea     rdx, WimPerformRenameWorker; WorkerRoutine
0x14002ba38  mov     [rsp+98h+var_58], rdi
0x14002ba3d  mov     rcx, rbx; IoWorkItem
0x14002ba40  mov     [rsp+98h+var_50], 30h ; '0'
0x14002ba48  call    cs:__imp_IoQueueWorkItemEx
0x14002ba4f  nop     dword ptr [rax+rax+00h]
0x14002ba54  xor     r9d, r9d; Alertable
0x14002ba57  mov     [rsp+98h+Timeout], 0; Timeout
0x14002ba60  xor     r8d, r8d; WaitMode
0x14002ba63  lea     rcx, [rsp+98h+Event]; Object
0x14002ba68  xor     edx, edx; WaitReason
0x14002ba6a  call    cs:__imp_KeWaitForSingleObject
0x14002ba71  nop     dword ptr [rax+rax+00h]
0x14002ba76  mov     eax, [rsp+98h+var_30]
0x14002ba7a  add     rsp, 78h
0x14002ba7e  pop     rdi
0x14002ba7f  pop     rsi
0x14002ba80  pop     rbp
0x14002ba81  pop     rbx
0x14002ba82  retn
```
