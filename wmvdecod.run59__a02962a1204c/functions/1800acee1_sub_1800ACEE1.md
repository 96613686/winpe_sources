# sub_1800ACEE1

- ea: `0x1800acee1`
- end: `0x1800aceed`
- name: `sub_1800ACEE1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800ace3e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800acee1`

## pseudocode

```c
__int64 sub_1800ACEE1()
{
  return sub_1800ACE3E();
}

```

## disassembly

```asm
0x1800acee1  lea     rax, PropVariantCopy
0x1800acee8  jmp     sub_1800ACE3E
```
