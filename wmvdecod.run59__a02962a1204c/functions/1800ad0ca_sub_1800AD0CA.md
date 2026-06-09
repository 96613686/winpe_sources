# sub_1800AD0CA

- ea: `0x1800ad0ca`
- end: `0x1800ad0d6`
- name: `sub_1800AD0CA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800ad04b`

## import_xrefs

- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800ad0ca`

## pseudocode

```c
__int64 sub_1800AD0CA()
{
  return sub_1800AD04B();
}

```

## disassembly

```asm
0x1800ad0ca  lea     rax, AvRevertMmThreadCharacteristics
0x1800ad0d1  jmp     sub_1800AD04B
```
