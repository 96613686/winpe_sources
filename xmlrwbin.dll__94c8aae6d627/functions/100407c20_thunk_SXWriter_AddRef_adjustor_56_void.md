# [thunk]:SXWriter::AddRef`adjustor{56}' (void)

- ea: `0x100407c20`
- end: `0x100407c29`
- name: `?AddRef@SXWriter@@WDI@EAAKXZ`
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
  return SXWriter::AddRef((SXWriter *)(a1 - 56));
}

```

## disassembly

```asm
0x100407c20  sub     rcx, 38h ; '8'; this
0x100407c24  jmp     ?AddRef@SXWriter@@UEAAKXZ; SXWriter::AddRef(void)
```
