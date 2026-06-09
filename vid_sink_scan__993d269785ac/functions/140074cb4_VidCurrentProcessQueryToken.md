# VidCurrentProcessQueryToken

- ea: `0x140074cb4`
- end: `0x140074d15`
- name: `VidCurrentProcessQueryToken`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400f795c`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140074cc1`
- `ntoskrnl!PsGetCurrentProcess` at `0x140074cc1`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140074cd0`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140074cd0`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140074cfb`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140074cfb`
- `ntoskrnl!SeQueryInformationToken` at `0x140074cea`
- `ntoskrnl!SeQueryInformationToken` at `0x140074cea`

## pseudocode

```c
__int64 __fastcall VidCurrentProcessQueryToken(__int64 a1, PVOID *a2)
{
  struct _KPROCESS *CurrentProcess; // rax
  PACCESS_TOKEN v4; // rdi

  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  v4 = PsReferencePrimaryToken(CurrentProcess);
  LODWORD(a2) = SeQueryInformationToken(v4, TokenOwner, a2);
  PsDereferencePrimaryToken(v4);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x140074cb4  mov     [rsp+arg_0], rbx
0x140074cb9  push    rdi
0x140074cba  sub     rsp, 20h
0x140074cbe  mov     rbx, rdx
0x140074cc1  call    cs:__imp_PsGetCurrentProcess
0x140074cc8  nop     dword ptr [rax+rax+00h]
0x140074ccd  mov     rcx, rax; Process
0x140074cd0  call    cs:__imp_PsReferencePrimaryToken
0x140074cd7  nop     dword ptr [rax+rax+00h]
0x140074cdc  mov     r8, rbx; TokenInformation
0x140074cdf  mov     edx, 4; TokenInformationClass
0x140074ce4  mov     rcx, rax; Token
0x140074ce7  mov     rdi, rax
0x140074cea  call    cs:__imp_SeQueryInformationToken
0x140074cf1  nop     dword ptr [rax+rax+00h]
0x140074cf6  mov     rcx, rdi; PrimaryToken
0x140074cf9  mov     ebx, eax
0x140074cfb  call    cs:__imp_PsDereferencePrimaryToken
0x140074d02  nop     dword ptr [rax+rax+00h]
0x140074d07  mov     eax, ebx
0x140074d09  mov     rbx, [rsp+28h+arg_0]
0x140074d0e  add     rsp, 20h
0x140074d12  pop     rdi
0x140074d13  retn
```
