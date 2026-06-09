# __GetStoreInstallPath_::_1_::dtor$6

- ea: `0x18000c12b`
- end: `0x18000c137`
- name: `__GetStoreInstallPath_::_1_::dtor$6`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800085f0`

## pseudocode

```c
void __fastcall _GetStoreInstallPath_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 80));
}

```

## disassembly

```asm
0x18000c12b  lea     rcx, [rdx+50h]; this
0x18000c132  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
