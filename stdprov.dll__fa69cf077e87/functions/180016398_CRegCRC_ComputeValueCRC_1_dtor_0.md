# _CRegCRC::ComputeValueCRC_::_1_::dtor$0

- ea: `0x180016398`
- end: `0x1800163a4`
- name: `_CRegCRC::ComputeValueCRC_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ba94`

## pseudocode

```c
__int64 __fastcall CRegCRC::ComputeValueCRC_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>::~ScopeGuardImpl1<void (*)(unsigned char *),RefHolder<unsigned char *>>(a2 + 72);
}

```

## disassembly

```asm
0x180016398  lea     rcx, [rdx+48h]
0x18001639f  jmp     ??1?$ScopeGuardImpl1@P6AXPEAE@ZV?$RefHolder@PEAE@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(uchar *),RefHolder<uchar *>>::~ScopeGuardImpl1<void (*)(uchar *),RefHolder<uchar *>>(void)
```
