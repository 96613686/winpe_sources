# _SharedDataManager::QueuePersonalizationUpdate_::_1_::dtor$0

- ea: `0x18000f1ba`
- end: `0x18000f1c6`
- name: `_SharedDataManager::QueuePersonalizationUpdate_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180004910`

## pseudocode

```c
void __fastcall SharedDataManager::QueuePersonalizationUpdate_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::unique_ptr<HrtfPersonalizationParams>::~unique_ptr<HrtfPersonalizationParams>((HrtfPersonalizationParams **)(a2 + 96));
}

```

## disassembly

```asm
0x18000f1ba  lea     rcx, [rdx+60h]
0x18000f1c1  jmp     ??1?$unique_ptr@UHrtfPersonalizationParams@@U?$default_delete@UHrtfPersonalizationParams@@@std@@@std@@QEAA@XZ; std::unique_ptr<HrtfPersonalizationParams>::~unique_ptr<HrtfPersonalizationParams>(void)
```
