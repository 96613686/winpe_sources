# sub_1800AD0DC

- ea: `0x1800ad0dc`
- end: `0x1800ad0e8`
- name: `sub_1800AD0DC`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800ad04b`

## import_xrefs

- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800ad0dc`

## pseudocode

```c
__int64 sub_1800AD0DC()
{
  return sub_1800AD04B();
}

```

## disassembly

```asm
0x1800ad0dc  lea     rax, AvSetMmThreadCharacteristicsW
0x1800ad0e3  jmp     sub_1800AD04B
```
