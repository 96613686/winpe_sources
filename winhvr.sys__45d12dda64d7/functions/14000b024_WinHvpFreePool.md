# WinHvpFreePool

- ea: `0x14000b024`
- end: `0x14000b03a`
- name: `WinHvpFreePool`
- size: `22`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140005c8c`
- `0x140005e60`
- `0x1400222f0`
- `0x140022f88`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x14000b028`
- `ntoskrnl!ExFreePool` at `0x14000b028`

## pseudocode

```c
void __fastcall WinHvpFreePool(void *a1)
{
  ExFreePool(a1);
}

```

## disassembly

```asm
0x14000b024  sub     rsp, 28h
0x14000b028  call    cs:__imp_ExFreePool
0x14000b02f  nop     dword ptr [rax+rax+00h]
0x14000b034  add     rsp, 28h
0x14000b038  retn
```
