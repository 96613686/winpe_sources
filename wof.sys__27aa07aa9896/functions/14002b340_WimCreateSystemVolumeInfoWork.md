# WimCreateSystemVolumeInfoWork

- ea: `0x14002b340`
- end: `0x14002b392`
- name: `WimCreateSystemVolumeInfoWork`
- size: `82`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002b36b`
- `ntoskrnl!KeSetEvent` at `0x14002b36b`
- `ntoskrnl!RtlCreateSystemVolumeInformationFolder` at `0x14002b354`
- `ntoskrnl!RtlCreateSystemVolumeInformationFolder` at `0x14002b354`
- `ntoskrnl!IoFreeWorkItem` at `0x14002b37a`
- `ntoskrnl!IoFreeWorkItem` at `0x14002b37a`

## pseudocode

```c
void __fastcall WimCreateSystemVolumeInfoWork(PVOID IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  *((_DWORD *)Context + 8) = RtlCreateSystemVolumeInformationFolder(*((PCUNICODE_STRING *)Context + 3));
  KeSetEvent((PRKEVENT)Context, 0, 0);
  IoFreeWorkItem(IoWorkItem);
}

```

## disassembly

```asm
0x14002b340  mov     [rsp+arg_0], rbx
0x14002b345  push    rdi
0x14002b346  sub     rsp, 20h
0x14002b34a  mov     rcx, [rdx+18h]; VolumeRootPath
0x14002b34e  mov     rdi, r8
0x14002b351  mov     rbx, rdx
0x14002b354  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x14002b35b  nop     dword ptr [rax+rax+00h]
0x14002b360  xor     r8d, r8d; Wait
0x14002b363  xor     edx, edx; Increment
0x14002b365  mov     rcx, rbx; Event
0x14002b368  mov     [rbx+20h], eax
0x14002b36b  call    cs:__imp_KeSetEvent
0x14002b372  nop     dword ptr [rax+rax+00h]
0x14002b377  mov     rcx, rdi; IoWorkItem
0x14002b37a  call    cs:__imp_IoFreeWorkItem
0x14002b381  nop     dword ptr [rax+rax+00h]
0x14002b386  mov     rbx, [rsp+28h+arg_0]
0x14002b38b  add     rsp, 20h
0x14002b38f  pop     rdi
0x14002b390  retn
```
