# [thunk]:SXReader::Release`adjustor{1464}' (void)

- ea: `0x100406410`
- end: `0x10040641c`
- name: `?Release@SXReader@@WFLI@EAAKXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100404880`

## pseudocode

```c
__int64 __fastcall SXReader::Release(__int64 a1)
{
  return SXReader::Release((SXReader *)(a1 - 1464));
}

```

## disassembly

```asm
0x100406410  sub     rcx, 5B8h; this
0x100406417  jmp     ?Release@SXReader@@UEAAKXZ; SXReader::Release(void)
```
