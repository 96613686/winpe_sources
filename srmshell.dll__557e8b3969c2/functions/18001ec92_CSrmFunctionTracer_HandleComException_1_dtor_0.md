# _CSrmFunctionTracer::HandleComException_::_1_::dtor$0

- ea: `0x18001ec92`
- end: `0x18001ec9e`
- name: `_CSrmFunctionTracer::HandleComException_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016518`

## pseudocode

```c
void __fastcall CSrmFunctionTracer::HandleComException_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CSrmDebugInfo::~CSrmDebugInfo(*(CSrmDebugInfo **)(a2 + 256));
}

```

## disassembly

```asm
0x18001ec92  mov     rcx, [rdx+100h]; this
0x18001ec99  jmp     ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
```
