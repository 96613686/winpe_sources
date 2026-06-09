# WcCleanupSiloContext

- ea: `0x14001d360`
- end: `0x14001d389`
- name: `WcCleanupSiloContext`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14001d56c`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14001d376`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001d376`

## pseudocode

```c
NTSTATUS __fastcall WcCleanupSiloContext(__int64 a1)
{
  WcClearUnionTable((PRTL_AVL_TABLE)(a1 + 112));
  return ExDeleteResourceLite((PERESOURCE)(a1 + 8));
}

```

## disassembly

```asm
0x14001d360  push    rbx
0x14001d362  sub     rsp, 20h
0x14001d366  mov     rbx, rcx
0x14001d369  add     rcx, 70h ; 'p'; Table
0x14001d36d  call    WcClearUnionTable
0x14001d372  lea     rcx, [rbx+8]; Resource
0x14001d376  call    cs:__imp_ExDeleteResourceLite
0x14001d37d  nop     dword ptr [rax+rax+00h]
0x14001d382  add     rsp, 20h
0x14001d386  pop     rbx
0x14001d387  retn
```
