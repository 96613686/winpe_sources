# _ATL::CComPtr_IErrorInfo_::_CComPtr_IErrorInfo__::_1_::dtor$0

- ea: `0x18001c089`
- end: `0x18001c095`
- name: `_ATL::CComPtr_IErrorInfo_::_CComPtr_IErrorInfo__::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004c74`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr_IErrorInfo_::_CComPtr_IErrorInfo__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtrBase<IFsrmPropertyDefinition2>::~CComPtrBase<IFsrmPropertyDefinition2>(*(__int64 **)(a2 + 48));
}

```

## disassembly

```asm
0x18001c089  mov     rcx, [rdx+30h]
0x18001c090  jmp     ??1?$CComPtrBase@UIFsrmPropertyDefinition2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFsrmPropertyDefinition2>::~CComPtrBase<IFsrmPropertyDefinition2>(void)
```
