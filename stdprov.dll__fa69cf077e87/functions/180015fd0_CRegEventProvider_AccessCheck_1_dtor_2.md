# _CRegEventProvider::AccessCheck_::_1_::dtor$2

- ea: `0x180015fd0`
- end: `0x180015fdc`
- name: `_CRegEventProvider::AccessCheck_::_1_::dtor$2`
- size: `12`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000bb54`

## pseudocode

```c
void *__fastcall CRegEventProvider::AccessCheck_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(
           (QL_LEVEL_1_RPN_EXPRESSION **)(a2 + 88),
           a2);
}

```

## disassembly

```asm
0x180015fd0  lea     rcx, [rdx+58h]
0x180015fd7  jmp     ??1?$CDeleteMe@UQL_LEVEL_1_RPN_EXPRESSION@@@@QEAA@XZ; CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>::~CDeleteMe<QL_LEVEL_1_RPN_EXPRESSION>(void)
```
