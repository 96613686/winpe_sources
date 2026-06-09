# VidCurrentProcessIsAdmin

- ea: `0x1400768e0`
- end: `0x140076937`
- name: `VidCurrentProcessIsAdmin`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400769d8`
- `0x1400fa3ac`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400768ea`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400768ea`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400768f9`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400768f9`
- `ntoskrnl!SeTokenIsAdmin` at `0x14007690b`
- `ntoskrnl!SeTokenIsAdmin` at `0x14007690b`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14007691d`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14007691d`

## pseudocode

```c
__int64 VidCurrentProcessIsAdmin()
{
  struct _KPROCESS *CurrentProcess; // rax
  PACCESS_TOKEN v1; // rdi
  unsigned int IsAdmin; // ebx

  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  v1 = PsReferencePrimaryToken(CurrentProcess);
  IsAdmin = SeTokenIsAdmin(v1);
  PsDereferencePrimaryToken(v1);
  return IsAdmin;
}

```

## disassembly

```asm
0x1400768e0  mov     [rsp+arg_0], rbx
0x1400768e5  push    rdi
0x1400768e6  sub     rsp, 20h
0x1400768ea  call    cs:__imp_PsGetCurrentProcess
0x1400768f1  nop     dword ptr [rax+rax+00h]
0x1400768f6  mov     rcx, rax; Process
0x1400768f9  call    cs:__imp_PsReferencePrimaryToken
0x140076900  nop     dword ptr [rax+rax+00h]
0x140076905  mov     rcx, rax; Token
0x140076908  mov     rdi, rax
0x14007690b  call    cs:__imp_SeTokenIsAdmin
0x140076912  nop     dword ptr [rax+rax+00h]
0x140076917  mov     rcx, rdi; PrimaryToken
0x14007691a  movzx   ebx, al
0x14007691d  call    cs:__imp_PsDereferencePrimaryToken
0x140076924  nop     dword ptr [rax+rax+00h]
0x140076929  mov     eax, ebx
0x14007692b  mov     rbx, [rsp+28h+arg_0]
0x140076930  add     rsp, 20h
0x140076934  pop     rdi
0x140076935  retn
```
