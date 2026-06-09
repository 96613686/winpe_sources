# PowerDownDevice

- ea: `0x140006cc8`
- end: `0x140006e1f`
- name: `PowerDownDevice`
- size: `343`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140006ae0`
- `0x14001977c`
- `0x14005ccc0`

## callees

- `0x140005308`
- `0x140006cc8`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140006dd9`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140006dd9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006d38`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006d38`
- `ntoskrnl!IoQueueWorkItem` at `0x140006daf`
- `ntoskrnl!IoQueueWorkItem` at `0x140006daf`
- `ntoskrnl!IoAllocateWorkItem` at `0x140006d7a`
- `ntoskrnl!IoAllocateWorkItem` at `0x140006d7a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140006d18`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140006d18`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006deb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006deb`

## pseudocode

```c
__int64 __fastcall PowerDownDevice(PVOID Context, int a2, __int64 a3)
{
  __int64 v5; // rcx
  NTSTATUS v6; // ebp
  __int64 v7; // r8
  KIRQL v8; // r15
  __int64 v9; // rcx
  struct _IO_WORKITEM *WorkItem; // rax

  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
    McTemplateK0p_EtwWriteTransfer(Context, USBVideo_PowerDownDevice_Start, a3, 0);
  v6 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)Context + 24, IdleDetectWorkItem, File, 1u, 0x20u);
  if ( v6 >= 0 )
  {
    v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 27);
    if ( !a2 )
      --*((_BYTE *)Context + 2);
    if ( (*((_DWORD *)Context + 210) || !*((_BYTE *)Context + 2))
      && !*((_BYTE *)Context + 1)
      && !*((_DWORD *)Context + 56) )
    {
      v9 = *((_QWORD *)Context + 3);
      if ( *(_DWORD *)(v9 + 56) == 1 )
      {
        WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(v9 + 24));
        if ( WorkItem )
        {
          *((_QWORD *)Context + 30) = WorkItem;
          *((_DWORD *)Context + 56) = 1;
          IoQueueWorkItem(WorkItem, IdleDetectWorkItem, DelayedWorkQueue, Context);
LABEL_15:
          KeReleaseSpinLock((PKSPIN_LOCK)Context + 27, v8);
          goto LABEL_16;
        }
        *((_DWORD *)Context + 56) = 0;
      }
    }
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)Context + 24, IdleDetectWorkItem, 0x20u);
    goto LABEL_15;
  }
LABEL_16:
  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
    McTemplateK0p_EtwWriteTransfer(v5, USBVideo_PowerDownDevice_Stop, v7, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140006cc8  push    rbx
0x140006cca  push    rbp
0x140006ccb  push    rsi
0x140006ccc  push    rdi
0x140006ccd  push    r14
0x140006ccf  push    r15
0x140006cd1  sub     rsp, 38h
0x140006cd5  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x140006cdc  mov     edi, edx
0x140006cde  mov     rbx, rcx
0x140006ce1  jz      short loc_140006CF2
0x140006ce3  xor     r9d, r9d
0x140006ce6  lea     rdx, USBVideo_PowerDownDevice_Start
0x140006ced  call    McTemplateK0p_EtwWriteTransfer
0x140006cf2  lea     rsi, [rbx+300h]
0x140006cf9  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x140006d01  mov     rcx, rsi; RemoveLock
0x140006d04  lea     r8, File; File
0x140006d0b  mov     r9d, 1; Line
0x140006d11  lea     rdx, IdleDetectWorkItem; Tag
0x140006d18  call    cs:__imp_IoAcquireRemoveLockEx
0x140006d1f  nop     dword ptr [rax+rax+00h]
0x140006d24  mov     ebp, eax
0x140006d26  test    eax, eax
0x140006d28  js      loc_140006DF7
0x140006d2e  lea     r14, [rbx+0D8h]
0x140006d35  mov     rcx, r14; SpinLock
0x140006d38  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006d3f  nop     dword ptr [rax+rax+00h]
0x140006d44  mov     r15b, al
0x140006d47  test    edi, edi
0x140006d49  jnz     short loc_140006D4E
0x140006d4b  dec     byte ptr [rbx+2]
0x140006d4e  cmp     dword ptr [rbx+348h], 0
0x140006d55  jnz     short loc_140006D5D
0x140006d57  cmp     byte ptr [rbx+2], 0
0x140006d5b  jnz     short loc_140006DC9
0x140006d5d  cmp     byte ptr [rbx+1], 0
0x140006d61  jnz     short loc_140006DC9
0x140006d63  cmp     dword ptr [rbx+0E0h], 0
0x140006d6a  jnz     short loc_140006DC9
0x140006d6c  mov     rcx, [rbx+18h]
0x140006d70  cmp     dword ptr [rcx+38h], 1
0x140006d74  jnz     short loc_140006DC9
0x140006d76  mov     rcx, [rcx+18h]; DeviceObject
0x140006d7a  call    cs:__imp_IoAllocateWorkItem
0x140006d81  nop     dword ptr [rax+rax+00h]
0x140006d86  lea     rdx, IdleDetectWorkItem; WorkerRoutine
0x140006d8d  test    rax, rax
0x140006d90  jz      short loc_140006DBD
0x140006d92  mov     r9, rbx; Context
0x140006d95  mov     [rbx+0F0h], rax
0x140006d9c  mov     r8d, 1; QueueType
0x140006da2  mov     dword ptr [rbx+0E0h], 1
0x140006dac  mov     rcx, rax; IoWorkItem
0x140006daf  call    cs:__imp_IoQueueWorkItem
0x140006db6  nop     dword ptr [rax+rax+00h]
0x140006dbb  jmp     short loc_140006DE5
0x140006dbd  mov     dword ptr [rbx+0E0h], 0
0x140006dc7  jmp     short loc_140006DD0
0x140006dc9  lea     rdx, IdleDetectWorkItem; Tag
0x140006dd0  mov     r8d, 20h ; ' '; RemlockSize
0x140006dd6  mov     rcx, rsi; RemoveLock
0x140006dd9  call    cs:__imp_IoReleaseRemoveLockEx
0x140006de0  nop     dword ptr [rax+rax+00h]
0x140006de5  mov     dl, r15b; NewIrql
0x140006de8  mov     rcx, r14; SpinLock
0x140006deb  call    cs:__imp_KeReleaseSpinLock
0x140006df2  nop     dword ptr [rax+rax+00h]
0x140006df7  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x140006dfe  jz      short loc_140006E0F
0x140006e00  xor     r9d, r9d
0x140006e03  lea     rdx, USBVideo_PowerDownDevice_Stop
0x140006e0a  call    McTemplateK0p_EtwWriteTransfer
0x140006e0f  mov     eax, ebp
0x140006e11  add     rsp, 38h
0x140006e15  pop     r15
0x140006e17  pop     r14
0x140006e19  pop     rdi
0x140006e1a  pop     rsi
0x140006e1b  pop     rbp
0x140006e1c  pop     rbx
0x140006e1d  retn
```
