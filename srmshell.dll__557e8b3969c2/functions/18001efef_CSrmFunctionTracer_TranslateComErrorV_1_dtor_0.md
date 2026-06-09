# _CSrmFunctionTracer::TranslateComErrorV_::_1_::dtor$0

- ea: `0x18001efef`
- end: `0x18001effb`
- name: `_CSrmFunctionTracer::TranslateComErrorV_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016518`

## pseudocode

```c
void __fastcall CSrmFunctionTracer::TranslateComErrorV_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CSrmDebugInfo::~CSrmDebugInfo(*(CSrmDebugInfo **)(a2 + 616));
}

```

## disassembly

```asm
0x18001efef  mov     rcx, [rdx+268h]; this
0x18001eff6  jmp     ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
```
