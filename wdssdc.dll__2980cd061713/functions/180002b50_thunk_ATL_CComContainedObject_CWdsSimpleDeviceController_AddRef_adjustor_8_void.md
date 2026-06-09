# [thunk]:ATL::CComContainedObject<CWdsSimpleDeviceController>::AddRef`adjustor{8}' (void)

- ea: `0x180002b50`
- end: `0x180002b59`
- name: `?AddRef@?$CComContainedObject@VCWdsSimpleDeviceController@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002b30`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWdsSimpleDeviceController>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CWdsSimpleDeviceController>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180002b50  sub     rcx, 8
0x180002b54  jmp     ?AddRef@?$CComContainedObject@VCWdsSimpleDeviceController@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CWdsSimpleDeviceController>::AddRef(void)
```
