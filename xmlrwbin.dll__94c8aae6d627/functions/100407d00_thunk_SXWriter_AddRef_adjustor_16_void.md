# [thunk]:SXWriter::AddRef`adjustor{16}' (void)

- ea: `0x100407d00`
- end: `0x100407d09`
- name: `?AddRef@SXWriter@@WBA@EAAKXZ`
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
  return SXWriter::AddRef((SXWriter *)(a1 - 16));
}

```

## disassembly

```asm
0x100407d00  sub     rcx, 10h; this
0x100407d04  jmp     ?AddRef@SXWriter@@UEAAKXZ; SXWriter::AddRef(void)
```
