# XPartDisableInterruptCallbacks

- ea: `0x140012bdc`
- end: `0x140012c0b`
- name: `XPartDisableInterruptCallbacks`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140007270`
- `0x140012a68`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140012be9`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140012be9`
- `ntoskrnl!ExRundownCompleted` at `0x140012bf8`
- `ntoskrnl!ExRundownCompleted` at `0x140012bf8`

## pseudocode

```c
void __fastcall XPartDisableInterruptCallbacks(struct _EX_RUNDOWN_REF *a1)
{
  struct _EX_RUNDOWN_REF *v1; // rbx

  v1 = a1 + 6;
  ExWaitForRundownProtectionRelease(a1 + 6);
  ExRundownCompleted(v1);
}

```

## disassembly

```asm
0x140012bdc  push    rbx
0x140012bde  sub     rsp, 20h
0x140012be2  lea     rbx, [rcx+30h]
0x140012be6  mov     rcx, rbx; RunRef
0x140012be9  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140012bf0  nop     dword ptr [rax+rax+00h]
0x140012bf5  mov     rcx, rbx; RunRef
0x140012bf8  call    cs:__imp_ExRundownCompleted
0x140012bff  nop     dword ptr [rax+rax+00h]
0x140012c04  add     rsp, 20h
0x140012c08  pop     rbx
0x140012c09  retn
```
