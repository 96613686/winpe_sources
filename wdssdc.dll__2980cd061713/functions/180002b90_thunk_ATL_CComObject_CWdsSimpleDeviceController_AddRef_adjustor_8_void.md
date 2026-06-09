# [thunk]:ATL::CComObject<CWdsSimpleDeviceController>::AddRef`adjustor{8}' (void)

- ea: `0x180002b90`
- end: `0x180002b99`
- name: `?AddRef@?$CComObject@VCWdsSimpleDeviceController@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002b60`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsSimpleDeviceController>::AddRef(__int64 a1)
{
  return ATL::CComObject<CWdsSimpleDeviceController>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180002b90  sub     rcx, 8
0x180002b94  jmp     ?AddRef@?$CComObject@VCWdsSimpleDeviceController@@@ATL@@UEAAKXZ; ATL::CComObject<CWdsSimpleDeviceController>::AddRef(void)
```
