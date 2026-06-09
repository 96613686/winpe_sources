# UdfUpdateValidDataLength

- ea: `0x14001978c`
- end: `0x1400197a8`
- name: `UdfUpdateValidDataLength`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x1400010f0`

## callees

- `0x14001978c`

## import_xrefs

- `ntoskrnl!CcSetFileSizes` at `0x140019794`
- `ntoskrnl!CcSetFileSizes` at `0x140019794`

## pseudocode

```c
void __fastcall UdfUpdateValidDataLength(struct _FILE_OBJECT *a1, struct _CC_FILE_SIZES *a2)
{
  CcSetFileSizes(a1, a2 + 1);
}

```

## disassembly

```asm
0x14001978c  sub     rsp, 28h
0x140019790  add     rdx, 18h; FileSizes
0x140019794  call    cs:__imp_CcSetFileSizes
0x14001979b  nop     dword ptr [rax+rax+00h]
0x1400197a0  jmp     short $+2
0x1400197a2  add     rsp, 28h
0x1400197a6  retn
```
