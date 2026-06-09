# _SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor$6

- ea: `0x18000f0f3`
- end: `0x18000f103`
- name: `_SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor$6`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180004a40`

## pseudocode

```c
__int64 __fastcall SharedDataManager::GetPersonalizationParamsFromDefaultConfiguration_::_1_::dtor_6(
        __int64 a1,
        __int64 a2)
{
  return std::vector<HrtfDataDesc>::_Tidy(*(_QWORD *)(a2 + 88) + 56LL);
}

```

## disassembly

```asm
0x18000f0f3  mov     rcx, [rdx+58h]
0x18000f0fa  add     rcx, 38h ; '8'
0x18000f0fe  jmp     ?_Tidy@?$vector@UHrtfDataDesc@@V?$allocator@UHrtfDataDesc@@@std@@@std@@IEAAXXZ; std::vector<HrtfDataDesc>::_Tidy(void)
```
