# WimCreateSystemVolumeInfoWork

- ea: `0x14002b2f0`
- end: `0x14002b342`
- name: `WimCreateSystemVolumeInfoWork`
- size: `82`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002b31b`
- `ntoskrnl!KeSetEvent` at `0x14002b31b`
- `ntoskrnl!RtlCreateSystemVolumeInformationFolder` at `0x14002b304`
- `ntoskrnl!RtlCreateSystemVolumeInformationFolder` at `0x14002b304`
- `ntoskrnl!IoFreeWorkItem` at `0x14002b32a`
- `ntoskrnl!IoFreeWorkItem` at `0x14002b32a`

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
0x14002b2f0  mov     [rsp+arg_0], rbx
0x14002b2f5  push    rdi
0x14002b2f6  sub     rsp, 20h
0x14002b2fa  mov     rcx, [rdx+18h]; VolumeRootPath
0x14002b2fe  mov     rdi, r8
0x14002b301  mov     rbx, rdx
0x14002b304  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x14002b30b  nop     dword ptr [rax+rax+00h]
0x14002b310  xor     r8d, r8d; Wait
0x14002b313  xor     edx, edx; Increment
0x14002b315  mov     rcx, rbx; Event
0x14002b318  mov     [rbx+20h], eax
0x14002b31b  call    cs:__imp_KeSetEvent
0x14002b322  nop     dword ptr [rax+rax+00h]
0x14002b327  mov     rcx, rdi; IoWorkItem
0x14002b32a  call    cs:__imp_IoFreeWorkItem
0x14002b331  nop     dword ptr [rax+rax+00h]
0x14002b336  mov     rbx, [rsp+28h+arg_0]
0x14002b33b  add     rsp, 20h
0x14002b33f  pop     rdi
0x14002b340  retn
```
