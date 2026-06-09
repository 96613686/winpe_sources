# SqospFree

- ea: `0x140008a54`
- end: `0x140008a6f`
- name: `SqospFree`
- size: `27`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x14001223c`
- `0x1400122e0`
- `0x1400126f8`
- `0x140012c78`
- `0x140013cf8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008a5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008a5d`

## pseudocode

```c
void __fastcall SqospFree(void *a1)
{
  ExFreePoolWithTag(a1, 0x46535153u);
}

```

## disassembly

```asm
0x140008a54  sub     rsp, 28h
0x140008a58  mov     edx, 46535153h; Tag
0x140008a5d  call    cs:__imp_ExFreePoolWithTag
0x140008a64  nop     dword ptr [rax+rax+00h]
0x140008a69  add     rsp, 28h
0x140008a6d  retn
```
