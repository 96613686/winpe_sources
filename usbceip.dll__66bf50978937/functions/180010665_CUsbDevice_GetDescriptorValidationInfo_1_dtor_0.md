# _CUsbDevice::GetDescriptorValidationInfo_::_1_::dtor$0

- ea: `0x180010665`
- end: `0x180010671`
- name: `_CUsbDevice::GetDescriptorValidationInfo_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180007248`

## pseudocode

```c
__int64 __fastcall CUsbDevice::GetDescriptorValidationInfo_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>((_QWORD *)(a2 + 96));
}

```

## disassembly

```asm
0x180010665  lea     rcx, [rdx+60h]
0x18001066c  jmp     ??1?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRegistryKey>::~unique_ptr<CRegistryKey>(void)
```
