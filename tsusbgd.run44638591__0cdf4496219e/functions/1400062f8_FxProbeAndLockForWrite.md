# FxProbeAndLockForWrite

- ea: `0x1400062f8`
- end: `0x14000631c`
- name: `FxProbeAndLockForWrite`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002c60`

## callees

- `0x1400062f8`

## import_xrefs

- `ntoskrnl!MmProbeAndLockPages` at `0x140006305`
- `ntoskrnl!MmProbeAndLockPages` at `0x140006305`

## pseudocode

```c
__int64 __fastcall FxProbeAndLockForWrite(struct _MDL *a1)
{
  MmProbeAndLockPages(a1, 1, IoWriteAccess);
  return 0;
}

```

## disassembly

```asm
0x1400062f8  sub     rsp, 28h
0x1400062fc  mov     r8d, 1; Operation
0x140006302  mov     dl, r8b; AccessMode
0x140006305  call    cs:__imp_MmProbeAndLockPages
0x14000630c  nop     dword ptr [rax+rax+00h]
0x140006311  nop
0x140006312  xor     eax, eax
0x140006314  jmp     short $+2
0x140006316  add     rsp, 28h
0x14000631a  retn
```
