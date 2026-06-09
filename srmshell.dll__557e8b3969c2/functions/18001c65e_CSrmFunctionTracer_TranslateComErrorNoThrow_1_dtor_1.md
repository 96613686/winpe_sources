# _CSrmFunctionTracer::TranslateComErrorNoThrow_::_1_::dtor$1

- ea: `0x18001c65e`
- end: `0x18001c66a`
- name: `_CSrmFunctionTracer::TranslateComErrorNoThrow_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016518`

## pseudocode

```c
void __fastcall CSrmFunctionTracer::TranslateComErrorNoThrow_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CSrmDebugInfo::~CSrmDebugInfo(*(CSrmDebugInfo **)(a2 + 48));
}

```

## disassembly

```asm
0x18001c65e  mov     rcx, [rdx+30h]; this
0x18001c665  jmp     ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
```
