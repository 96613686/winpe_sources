# [thunk]:SXReader::AddRef`adjustor{1464}' (void)

- ea: `0x100406430`
- end: `0x10040643c`
- name: `?AddRef@SXReader@@WFLI@EAAKXZ`
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
  return SXReader::AddRef((SXReader *)(a1 - 1464));
}

```

## disassembly

```asm
0x100406430  sub     rcx, 5B8h; this
0x100406437  jmp     ?AddRef@SXReader@@UEAAKXZ; SXReader::AddRef(void)
```
