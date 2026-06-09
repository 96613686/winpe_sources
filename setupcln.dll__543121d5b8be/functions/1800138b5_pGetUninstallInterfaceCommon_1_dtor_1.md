# _pGetUninstallInterfaceCommon_::_1_::dtor$1

- ea: `0x1800138b5`
- end: `0x1800138c1`
- name: `_pGetUninstallInterfaceCommon_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d9d0`

## pseudocode

```c
void __fastcall pGetUninstallInterfaceCommon_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  RAII::CAutoFreeLibrary::~CAutoFreeLibrary((RAII::CAutoFreeLibrary *)(a2 + 96));
}

```

## disassembly

```asm
0x1800138b5  lea     rcx, [rdx+60h]; this
0x1800138bc  jmp     ??1CAutoFreeLibrary@RAII@@UEAA@XZ; RAII::CAutoFreeLibrary::~CAutoFreeLibrary(void)
```
