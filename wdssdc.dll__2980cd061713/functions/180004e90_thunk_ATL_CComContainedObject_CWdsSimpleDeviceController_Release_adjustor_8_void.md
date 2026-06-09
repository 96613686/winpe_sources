# [thunk]:ATL::CComContainedObject<CWdsSimpleDeviceController>::Release`adjustor{8}' (void)

- ea: `0x180004e90`
- end: `0x180004e99`
- name: `?Release@?$CComContainedObject@VCWdsSimpleDeviceController@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004e70`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWdsSimpleDeviceController>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CWdsSimpleDeviceController>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180004e90  sub     rcx, 8
0x180004e94  jmp     ?Release@?$CComContainedObject@VCWdsSimpleDeviceController@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CWdsSimpleDeviceController>::Release(void)
```
