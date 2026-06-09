# [thunk]:SXWriter::AddRef`adjustor{48}' (void)

- ea: `0x100407d10`
- end: `0x100407d19`
- name: `?AddRef@SXWriter@@WDA@EAAKXZ`
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
  return SXWriter::AddRef((SXWriter *)(a1 - 48));
}

```

## disassembly

```asm
0x100407d10  sub     rcx, 30h ; '0'; this
0x100407d14  jmp     ?AddRef@SXWriter@@UEAAKXZ; SXWriter::AddRef(void)
```
