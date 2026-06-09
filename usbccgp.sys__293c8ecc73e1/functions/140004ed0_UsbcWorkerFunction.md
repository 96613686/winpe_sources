# UsbcWorkerFunction

- ea: `0x140004ed0`
- end: `0x140004f43`
- name: `UsbcWorkerFunction`
- size: `115`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400054a0`
- `0x140014d50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004f30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004f30`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004f1c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004f1c`
- `ntoskrnl!IoFreeWorkItem` at `0x140004eee`
- `ntoskrnl!IoFreeWorkItem` at `0x140004eee`

## pseudocode

```c
void __fastcall UsbcWorkerFunction(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  (*((void (__fastcall **)(_QWORD, _QWORD))Context + 2))(*((_QWORD *)Context + 1), *((_QWORD *)Context + 4));
  IoFreeWorkItem(*((PIO_WORKITEM *)Context + 3));
  UsbcReleaseRemoveLock(*((_QWORD *)Context + 1), *((_QWORD *)Context + 2));
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(*((_QWORD *)Context + 1) + 200LL), *((PVOID *)Context + 2), 0x20u);
  ExFreePoolWithTag(Context, 0x43627355u);
}

```

## disassembly

```asm
0x140004ed0  push    rbx
0x140004ed2  sub     rsp, 20h
0x140004ed6  mov     rax, [rdx+10h]
0x140004eda  mov     rbx, rdx
0x140004edd  mov     rdx, [rdx+20h]
0x140004ee1  mov     rcx, [rbx+8]
0x140004ee5  call    _guard_dispatch_icall
0x140004eea  mov     rcx, [rbx+18h]; IoWorkItem
0x140004eee  call    cs:__imp_IoFreeWorkItem
0x140004ef5  nop     dword ptr [rax+rax+00h]
0x140004efa  mov     rdx, [rbx+10h]
0x140004efe  mov     rcx, [rbx+8]
0x140004f02  call    UsbcReleaseRemoveLock
0x140004f07  mov     rcx, [rbx+8]
0x140004f0b  mov     r8d, 20h ; ' '; RemlockSize
0x140004f11  mov     rdx, [rbx+10h]; Tag
0x140004f15  add     rcx, 0C8h; RemoveLock
0x140004f1c  call    cs:__imp_IoReleaseRemoveLockEx
0x140004f23  nop     dword ptr [rax+rax+00h]
0x140004f28  mov     edx, 43627355h; Tag
0x140004f2d  mov     rcx, rbx; P
0x140004f30  call    cs:__imp_ExFreePoolWithTag
0x140004f37  nop     dword ptr [rax+rax+00h]
0x140004f3c  add     rsp, 20h
0x140004f40  pop     rbx
0x140004f41  retn
```
