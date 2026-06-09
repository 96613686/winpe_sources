# _encoded_null

- ea: `0x180003868`
- end: `0x180003871`
- name: `_encoded_null`
- size: `9`
- prototype: `PVOID()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000361c`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000386a`

## pseudocode

```c
PVOID encoded_null()
{
  return EncodePointer(0);
}

```

## disassembly

```asm
0x180003868  xor     ecx, ecx
0x18000386a  jmp     cs:__imp_EncodePointer
```
