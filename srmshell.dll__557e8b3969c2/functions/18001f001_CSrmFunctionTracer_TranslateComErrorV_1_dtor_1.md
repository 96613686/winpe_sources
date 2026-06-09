# _CSrmFunctionTracer::TranslateComErrorV_::_1_::dtor$1

- ea: `0x18001f001`
- end: `0x18001f00d`
- name: `_CSrmFunctionTracer::TranslateComErrorV_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016670`

## pseudocode

```c
void __fastcall CSrmFunctionTracer::TranslateComErrorV_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CSrmOutputBuffer::~CSrmOutputBuffer((CSrmOutputBuffer *)(a2 + 96));
}

```

## disassembly

```asm
0x18001f001  lea     rcx, [rdx+60h]; this
0x18001f008  jmp     ??1CSrmOutputBuffer@@QEAA@XZ; CSrmOutputBuffer::~CSrmOutputBuffer(void)
```
