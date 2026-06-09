# PowerDownDeviceAfterSystemWake

- ea: `0x140011ab0`
- end: `0x140011bb8`
- name: `PowerDownDeviceAfterSystemWake`
- size: `264`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400104f0`

## callees

- `0x140011ab0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140011b8c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140011b8c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011b04`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011b04`
- `ntoskrnl!IoQueueWorkItem` at `0x140011b62`
- `ntoskrnl!IoQueueWorkItem` at `0x140011b62`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011b30`
- `ntoskrnl!IoAllocateWorkItem` at `0x140011b30`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140011ae4`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140011ae4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011b9e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011b9e`

## pseudocode

```c
__int64 __fastcall PowerDownDeviceAfterSystemWake(char *Context)
{
  struct _IO_REMOVE_LOCK *v1; // rdi
  NTSTATUS v3; // ebp
  KIRQL v4; // r14
  struct _IO_WORKITEM *WorkItem; // rax

  v1 = (struct _IO_REMOVE_LOCK *)(Context + 768);
  v3 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)Context + 24, IdleDetectWorkItem, File, 1u, 0x20u);
  if ( v3 >= 0 )
  {
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 27);
    if ( !Context[2] && !Context[1] && *((_DWORD *)Context + 56) == 3 )
    {
      WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(*((_QWORD *)Context + 3) + 24LL));
      if ( WorkItem )
      {
        *((_QWORD *)Context + 30) = WorkItem;
        *((_DWORD *)Context + 56) = 1;
        IoQueueWorkItem(WorkItem, IdleDetectWorkItem, DelayedWorkQueue, Context);
LABEL_9:
        KeReleaseSpinLock((PKSPIN_LOCK)Context + 27, v4);
        return (unsigned int)v3;
      }
      *((_DWORD *)Context + 56) = 0;
    }
    IoReleaseRemoveLockEx(v1, IdleDetectWorkItem, 0x20u);
    goto LABEL_9;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140011ab0  push    rbx
0x140011ab2  push    rbp
0x140011ab3  push    rsi
0x140011ab4  push    rdi
0x140011ab5  push    r14
0x140011ab7  sub     rsp, 30h
0x140011abb  lea     rdi, [rcx+300h]
0x140011ac2  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x140011aca  mov     rbx, rcx
0x140011acd  lea     r8, File; File
0x140011ad4  mov     rcx, rdi; RemoveLock
0x140011ad7  lea     rdx, IdleDetectWorkItem; Tag
0x140011ade  mov     r9d, 1; Line
0x140011ae4  call    cs:__imp_IoAcquireRemoveLockEx
0x140011aeb  nop     dword ptr [rax+rax+00h]
0x140011af0  mov     ebp, eax
0x140011af2  test    eax, eax
0x140011af4  js      loc_140011BAA
0x140011afa  lea     rsi, [rbx+0D8h]
0x140011b01  mov     rcx, rsi; SpinLock
0x140011b04  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011b0b  nop     dword ptr [rax+rax+00h]
0x140011b10  cmp     byte ptr [rbx+2], 0
0x140011b14  mov     r14b, al
0x140011b17  jnz     short loc_140011B7C
0x140011b19  cmp     byte ptr [rbx+1], 0
0x140011b1d  jnz     short loc_140011B7C
0x140011b1f  cmp     dword ptr [rbx+0E0h], 3
0x140011b26  jnz     short loc_140011B7C
0x140011b28  mov     rcx, [rbx+18h]
0x140011b2c  mov     rcx, [rcx+18h]; DeviceObject
0x140011b30  call    cs:__imp_IoAllocateWorkItem
0x140011b37  nop     dword ptr [rax+rax+00h]
0x140011b3c  lea     rdx, IdleDetectWorkItem; WorkerRoutine
0x140011b43  test    rax, rax
0x140011b46  jz      short loc_140011B70
0x140011b48  mov     r8d, 1; QueueType
0x140011b4e  mov     [rbx+0F0h], rax
0x140011b55  mov     r9, rbx; Context
0x140011b58  mov     [rbx+0E0h], r8d
0x140011b5f  mov     rcx, rax; IoWorkItem
0x140011b62  call    cs:__imp_IoQueueWorkItem
0x140011b69  nop     dword ptr [rax+rax+00h]
0x140011b6e  jmp     short loc_140011B98
0x140011b70  mov     dword ptr [rbx+0E0h], 0
0x140011b7a  jmp     short loc_140011B83
0x140011b7c  lea     rdx, IdleDetectWorkItem; Tag
0x140011b83  mov     r8d, 20h ; ' '; RemlockSize
0x140011b89  mov     rcx, rdi; RemoveLock
0x140011b8c  call    cs:__imp_IoReleaseRemoveLockEx
0x140011b93  nop     dword ptr [rax+rax+00h]
0x140011b98  mov     dl, r14b; NewIrql
0x140011b9b  mov     rcx, rsi; SpinLock
0x140011b9e  call    cs:__imp_KeReleaseSpinLock
0x140011ba5  nop     dword ptr [rax+rax+00h]
0x140011baa  mov     eax, ebp
0x140011bac  add     rsp, 30h
0x140011bb0  pop     r14
0x140011bb2  pop     rdi
0x140011bb3  pop     rsi
0x140011bb4  pop     rbp
0x140011bb5  pop     rbx
0x140011bb6  retn
```
