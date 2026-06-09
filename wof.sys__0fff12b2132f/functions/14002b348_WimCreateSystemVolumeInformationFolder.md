# WimCreateSystemVolumeInformationFolder

- ea: `0x14002b348`
- end: `0x14002b3fb`
- name: `WimCreateSystemVolumeInformationFolder`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14003ca60`

## callees

- `0x14002b348`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002b3df`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002b3df`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002b370`
- `ntoskrnl!IoAllocateWorkItem` at `0x14002b370`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002b3bd`
- `ntoskrnl!IoQueueWorkItemEx` at `0x14002b3bd`
- `ntoskrnl!KeInitializeEvent` at `0x14002b397`
- `ntoskrnl!KeInitializeEvent` at `0x14002b397`

## pseudocode

```c
__int64 __fastcall WimCreateSystemVolumeInformationFolder(__int64 a1)
{
  struct _IO_WORKITEM *WorkItem; // rbx
  _BYTE Event[32]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v5; // [rsp+50h] [rbp-18h]

  memset(Event, 0, sizeof(Event));
  v5 = 0;
  WorkItem = IoAllocateWorkItem(DeviceObject);
  if ( !WorkItem )
    return 3221225626LL;
  KeInitializeEvent((PRKEVENT)Event, SynchronizationEvent, 0);
  *(_QWORD *)&Event[24] = a1;
  IoQueueWorkItemEx(WorkItem, (PIO_WORKITEM_ROUTINE_EX)WimCreateSystemVolumeInfoWork, DelayedWorkQueue, Event);
  KeWaitForSingleObject(Event, Executive, 0, 0, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002b348  mov     [rsp+arg_0], rbx
0x14002b34d  push    rdi
0x14002b34e  sub     rsp, 60h
0x14002b352  xorps   xmm0, xmm0
0x14002b355  mov     rdi, rcx
0x14002b358  mov     rcx, cs:DeviceObject; DeviceObject
0x14002b35f  xor     eax, eax
0x14002b361  movups  xmmword ptr [rsp+68h+Event], xmm0
0x14002b366  mov     [rsp+68h+var_18], rax
0x14002b36b  movups  xmmword ptr [rsp+68h+Event+10h], xmm0
0x14002b370  call    cs:__imp_IoAllocateWorkItem
0x14002b377  nop     dword ptr [rax+rax+00h]
0x14002b37c  mov     rbx, rax
0x14002b37f  test    rax, rax
0x14002b382  jnz     short loc_14002B38B
0x14002b384  mov     eax, 0C000009Ah
0x14002b389  jmp     short loc_14002B3EF
0x14002b38b  xor     r8d, r8d; State
0x14002b38e  lea     rcx, [rsp+68h+Event]; Event
0x14002b393  lea     edx, [r8+1]; Type
0x14002b397  call    cs:__imp_KeInitializeEvent
0x14002b39e  nop     dword ptr [rax+rax+00h]
0x14002b3a3  lea     r9, [rsp+68h+Event]; Context
0x14002b3a8  mov     qword ptr [rsp+68h+Event+18h], rdi
0x14002b3ad  mov     r8d, 1; QueueType
0x14002b3b3  lea     rdx, WimCreateSystemVolumeInfoWork; WorkerRoutine
0x14002b3ba  mov     rcx, rbx; IoWorkItem
0x14002b3bd  call    cs:__imp_IoQueueWorkItemEx
0x14002b3c4  nop     dword ptr [rax+rax+00h]
0x14002b3c9  xor     r9d, r9d; Alertable
0x14002b3cc  mov     [rsp+68h+Timeout], 0; Timeout
0x14002b3d5  xor     r8d, r8d; WaitMode
0x14002b3d8  lea     rcx, [rsp+68h+Event]; Object
0x14002b3dd  xor     edx, edx; WaitReason
0x14002b3df  call    cs:__imp_KeWaitForSingleObject
0x14002b3e6  nop     dword ptr [rax+rax+00h]
0x14002b3eb  mov     eax, dword ptr [rsp+68h+var_18]
0x14002b3ef  mov     rbx, [rsp+68h+arg_0]
0x14002b3f4  add     rsp, 60h
0x14002b3f8  pop     rdi
0x14002b3f9  retn
```
