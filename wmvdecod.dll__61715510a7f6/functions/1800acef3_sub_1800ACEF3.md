# sub_1800ACEF3

- ea: `0x1800acef3`
- end: `0x1800aceff`
- name: `sub_1800ACEF3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800ace3e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800acef3`

## pseudocode

```c
__int64 sub_1800ACEF3()
{
  return sub_1800ACE3E();
}

```

## disassembly

```asm
0x1800acef3  lea     rax, CoCreateGuid
0x1800acefa  jmp     sub_1800ACE3E
```
