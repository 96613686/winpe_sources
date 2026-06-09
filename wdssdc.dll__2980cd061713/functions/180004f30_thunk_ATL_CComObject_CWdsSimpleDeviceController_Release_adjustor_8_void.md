# [thunk]:ATL::CComObject<CWdsSimpleDeviceController>::Release`adjustor{8}' (void)

- ea: `0x180004f30`
- end: `0x180004f39`
- name: `?Release@?$CComObject@VCWdsSimpleDeviceController@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004ea0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsSimpleDeviceController>::Release(__int64 a1)
{
  return ATL::CComObject<CWdsSimpleDeviceController>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180004f30  sub     rcx, 8
0x180004f34  jmp     ?Release@?$CComObject@VCWdsSimpleDeviceController@@@ATL@@UEAAKXZ; ATL::CComObject<CWdsSimpleDeviceController>::Release(void)
```
