# _CSrmFunctionTracer::TranslateComErrorV_::_1_::dtor$10

- ea: `0x18001d264`
- end: `0x18001d270`
- name: `_CSrmFunctionTracer::TranslateComErrorV_::_1_::dtor$10`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004c74`

## pseudocode

```c
__int64 __fastcall CSrmFunctionTracer::TranslateComErrorV_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  return ATL::CComPtrBase<IFsrmPropertyDefinition2>::~CComPtrBase<IFsrmPropertyDefinition2>((__int64 *)(a2 + 80));
}

```

## disassembly

```asm
0x18001d264  lea     rcx, [rdx+50h]
0x18001d26b  jmp     ??1?$CComPtrBase@UIFsrmPropertyDefinition2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFsrmPropertyDefinition2>::~CComPtrBase<IFsrmPropertyDefinition2>(void)
```
