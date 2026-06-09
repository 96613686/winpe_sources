# sub_1800ACECF

- ea: `0x1800acecf`
- end: `0x1800acedb`
- name: `sub_1800ACECF`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800ace3e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800acecf`

## pseudocode

```c
__int64 sub_1800ACECF()
{
  return sub_1800ACE3E();
}

```

## disassembly

```asm
0x1800acecf  lea     rax, CoTaskMemAlloc
0x1800aced6  jmp     sub_1800ACE3E
```
