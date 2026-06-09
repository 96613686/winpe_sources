# [thunk]:SXReader::Release`adjustor{1456}' (void)

- ea: `0x100406450`
- end: `0x10040645c`
- name: `?Release@SXReader@@WFLA@EAAKXZ`
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
  return SXReader::Release((SXReader *)(a1 - 1456));
}

```

## disassembly

```asm
0x100406450  sub     rcx, 5B0h; this
0x100406457  jmp     ?Release@SXReader@@UEAAKXZ; SXReader::Release(void)
```
