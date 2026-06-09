# [thunk]:SXWriter::AddRef`adjustor{40}' (void)

- ea: `0x100407cc0`
- end: `0x100407cc9`
- name: `?AddRef@SXWriter@@WCI@EAAKXZ`
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
  return SXWriter::AddRef((SXWriter *)(a1 - 40));
}

```

## disassembly

```asm
0x100407cc0  sub     rcx, 28h ; '('; this
0x100407cc4  jmp     ?AddRef@SXWriter@@UEAAKXZ; SXWriter::AddRef(void)
```
