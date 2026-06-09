# [thunk]:SXWriter::AddRef`adjustor{24}' (void)

- ea: `0x100407c10`
- end: `0x100407c19`
- name: `?AddRef@SXWriter@@WBI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x100408240`

## pseudocode

```c
__int64 __fastcall SXWriter::AddRef(__int64 a1)
{
  return SXWriter::AddRef((SXWriter *)(a1 - 24));
}

```

## disassembly

```asm
0x100407c10  sub     rcx, 18h; this
0x100407c14  jmp     ?AddRef@SXWriter@@UEAAKXZ; SXWriter::AddRef(void)
```
