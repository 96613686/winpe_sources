# _SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor$5

- ea: `0x18000f0e1`
- end: `0x18000f0ed`
- name: `_SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180004bfc`

## pseudocode

```c
void __fastcall SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor_5(
        __int64 a1,
        __int64 a2)
{
  HrtfDataDesc::~HrtfDataDesc(*(HrtfDataDesc **)(a2 + 88));
}

```

## disassembly

```asm
0x18000f0e1  mov     rcx, [rdx+58h]; this
0x18000f0e8  jmp     ??1HrtfDataDesc@@QEAA@XZ; HrtfDataDesc::~HrtfDataDesc(void)
```
