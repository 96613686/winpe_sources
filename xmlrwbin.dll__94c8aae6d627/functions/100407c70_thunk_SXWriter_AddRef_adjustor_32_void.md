# [thunk]:SXWriter::AddRef`adjustor{32}' (void)

- ea: `0x100407c70`
- end: `0x100407c79`
- name: `?AddRef@SXWriter@@WCA@EAAKXZ`
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
  return SXWriter::AddRef((SXWriter *)(a1 - 32));
}

```

## disassembly

```asm
0x100407c70  sub     rcx, 20h ; ' '; this
0x100407c74  jmp     ?AddRef@SXWriter@@UEAAKXZ; SXWriter::AddRef(void)
```
