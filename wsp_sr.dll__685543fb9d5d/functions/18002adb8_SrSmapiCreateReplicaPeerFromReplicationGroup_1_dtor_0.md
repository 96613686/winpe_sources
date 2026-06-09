# _SrSmapiCreateReplicaPeerFromReplicationGroup_::_1_::dtor$0

- ea: `0x18002adb8`
- end: `0x18002adc4`
- name: `_SrSmapiCreateReplicaPeerFromReplicationGroup_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a64`

## pseudocode

```c
__int64 __fastcall SrSmapiCreateReplicaPeerFromReplicationGroup_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 88);
}

```

## disassembly

```asm
0x18002adb8  lea     rcx, [rdx+58h]
0x18002adbf  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
