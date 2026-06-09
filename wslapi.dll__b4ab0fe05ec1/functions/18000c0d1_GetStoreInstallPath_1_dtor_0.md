# __GetStoreInstallPath_::_1_::dtor$0

- ea: `0x18000c0d1`
- end: `0x18000c0dd`
- name: `__GetStoreInstallPath_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008618`

## pseudocode

```c
void __fastcall _GetStoreInstallPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper((Microsoft::WRL::Wrappers::RoInitializeWrapper *)(a2 + 32));
}

```

## disassembly

```asm
0x18000c0d1  lea     rcx, [rdx+20h]; this
0x18000c0d8  jmp     ??1RoInitializeWrapper@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper(void)
```
