# [thunk]:SXWriter::AddRef`adjustor{8}' (void)

- ea: `0x100407cb0`
- end: `0x100407cb9`
- name: `?AddRef@SXWriter@@W7EAAKXZ`
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
  return SXWriter::AddRef((SXWriter *)(a1 - 8));
}

```

## disassembly

```asm
0x100407cb0  sub     rcx, 8; this
0x100407cb4  jmp     ?AddRef@SXWriter@@UEAAKXZ; SXWriter::AddRef(void)
```
