# _encoded_null

- ea: `0x180001ff8`
- end: `0x180002001`
- name: `_encoded_null`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001dac`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180001ffa`

## pseudocode

```c
PVOID encoded_null()
{
  return EncodePointer(0);
}

```

## disassembly

```asm
0x180001ff8  xor     ecx, ecx
0x180001ffa  jmp     cs:__imp_EncodePointer
```
