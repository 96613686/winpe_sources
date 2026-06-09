# [thunk]:SXReader::AddRef`adjustor{1456}' (void)

- ea: `0x100406480`
- end: `0x10040648c`
- name: `?AddRef@SXReader@@WFLA@EAAKXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100404860`

## pseudocode

```c
__int64 __fastcall SXReader::AddRef(__int64 a1)
{
  return SXReader::AddRef((SXReader *)(a1 - 1456));
}

```

## disassembly

```asm
0x100406480  sub     rcx, 5B0h; this
0x100406487  jmp     ?AddRef@SXReader@@UEAAKXZ; SXReader::AddRef(void)
```
