# _CUsbDevice::GetConfiguationDescriptor_::_1_::dtor$0

- ea: `0x18001050b`
- end: `0x180010517`
- name: `_CUsbDevice::GetConfiguationDescriptor_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003cb8`

## pseudocode

```c
void __fastcall CUsbDevice::GetConfiguationDescriptor_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 168));
}

```

## disassembly

```asm
0x18001050b  lea     rcx, [rdx+0A8h]; this
0x180010512  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
