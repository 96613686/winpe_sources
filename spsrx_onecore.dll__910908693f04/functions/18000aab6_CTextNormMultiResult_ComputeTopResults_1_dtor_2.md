# _CTextNormMultiResult::ComputeTopResults_::_1_::dtor$2

- ea: `0x18000aab6`
- end: `0x18000aac2`
- name: `_CTextNormMultiResult::ComputeTopResults_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800091b8`

## pseudocode

```c
void __fastcall CTextNormMultiResult::ComputeTopResults_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CSpClassFactory::~CSpClassFactory((CSpClassFactory *)(a2 + 192));
}

```

## disassembly

```asm
0x18000aab6  lea     rcx, [rdx+0C0h]; this
0x18000aabd  jmp     ??1CSpClassFactory@@UEAA@XZ; CSpClassFactory::~CSpClassFactory(void)
```
