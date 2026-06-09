# _CUpdateCleanup::GetSpaceUsed_::_1_::dtor$1

- ea: `0x180003fbb`
- end: `0x180003fc7`
- name: `_CUpdateCleanup::GetSpaceUsed_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800031a8`

## pseudocode

```c
__int64 __fastcall CUpdateCleanup::GetSpaceUsed_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::set<enum _DismReleaseType>::~set<enum _DismReleaseType>(a2 + 48);
}

```

## disassembly

```asm
0x180003fbb  lea     rcx, [rdx+30h]
0x180003fc2  jmp     ??1?$set@W4_DismReleaseType@@U?$less@W4_DismReleaseType@@@std@@V?$allocator@W4_DismReleaseType@@@3@@std@@QEAA@XZ; std::set<_DismReleaseType>::~set<_DismReleaseType>(void)
```
