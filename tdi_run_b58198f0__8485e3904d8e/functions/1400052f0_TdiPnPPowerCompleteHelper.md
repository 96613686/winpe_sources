# TdiPnPPowerCompleteHelper

- ea: `0x1400052f0`
- end: `0x140005308`
- name: `TdiPnPPowerCompleteHelper`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400052f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400052f6`

## pseudocode

```c
void __fastcall TdiPnPPowerCompleteHelper(void *a1)
{
  ExFreePoolWithTag(a1, 0);
}

```

## disassembly

```asm
0x1400052f0  sub     rsp, 28h
0x1400052f4  xor     edx, edx; Tag
0x1400052f6  call    cs:__imp_ExFreePoolWithTag
0x1400052fd  nop     dword ptr [rax+rax+00h]
0x140005302  add     rsp, 28h
0x140005306  retn
```
