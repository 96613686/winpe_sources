# VidCurrentProcessIsAdmin

- ea: `0x140075a04`
- end: `0x140075a5b`
- name: `VidCurrentProcessIsAdmin`
- size: `87`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140075afc`
- `0x1400f795c`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140075a0e`
- `ntoskrnl!PsGetCurrentProcess` at `0x140075a0e`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140075a1d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140075a1d`
- `ntoskrnl!SeTokenIsAdmin` at `0x140075a2f`
- `ntoskrnl!SeTokenIsAdmin` at `0x140075a2f`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140075a41`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140075a41`

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
0x140075a04  mov     [rsp+arg_0], rbx
0x140075a09  push    rdi
0x140075a0a  sub     rsp, 20h
0x140075a0e  call    cs:__imp_PsGetCurrentProcess
0x140075a15  nop     dword ptr [rax+rax+00h]
0x140075a1a  mov     rcx, rax; Process
0x140075a1d  call    cs:__imp_PsReferencePrimaryToken
0x140075a24  nop     dword ptr [rax+rax+00h]
0x140075a29  mov     rcx, rax; Token
0x140075a2c  mov     rdi, rax
0x140075a2f  call    cs:__imp_SeTokenIsAdmin
0x140075a36  nop     dword ptr [rax+rax+00h]
0x140075a3b  mov     rcx, rdi; PrimaryToken
0x140075a3e  movzx   ebx, al
0x140075a41  call    cs:__imp_PsDereferencePrimaryToken
0x140075a48  nop     dword ptr [rax+rax+00h]
0x140075a4d  mov     eax, ebx
0x140075a4f  mov     rbx, [rsp+28h+arg_0]
0x140075a54  add     rsp, 20h
0x140075a58  pop     rdi
0x140075a59  retn
```
