# VmbusSendInterfaceQueryCompletionRoutine

- ea: `0x14000ab50`
- end: `0x14000ab88`
- name: `VmbusSendInterfaceQueryCompletionRoutine`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000ab61`
- `ntoskrnl!KeSetEvent` at `0x14000ab61`
- `ntoskrnl!IoFreeIrp` at `0x14000ab70`
- `ntoskrnl!IoFreeIrp` at `0x14000ab70`

## pseudocode

```c
__int64 __fastcall VmbusSendInterfaceQueryCompletionRoutine(__int64 a1, IRP *a2, struct _KEVENT *a3)
{
  KeSetEvent(a3, 0, 0);
  IoFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000ab50  push    rbx
0x14000ab52  sub     rsp, 20h
0x14000ab56  mov     rcx, r8; Event
0x14000ab59  mov     rbx, rdx
0x14000ab5c  xor     r8d, r8d; Wait
0x14000ab5f  xor     edx, edx; Increment
0x14000ab61  call    cs:__imp_KeSetEvent
0x14000ab68  nop     dword ptr [rax+rax+00h]
0x14000ab6d  mov     rcx, rbx; Irp
0x14000ab70  call    cs:__imp_IoFreeIrp
0x14000ab77  nop     dword ptr [rax+rax+00h]
0x14000ab7c  mov     eax, 0C0000016h
0x14000ab81  add     rsp, 20h
0x14000ab85  pop     rbx
0x14000ab86  retn
```
