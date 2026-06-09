# _CRecoExt::CommitText_::_1_::dtor$0

- ea: `0x180003c94`
- end: `0x180003ca0`
- name: `_CRecoExt::CommitText_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003798`

## pseudocode

```c
__int64 __fastcall CRecoExt::CommitText_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CQuickStringW<64>::~CQuickStringW<64>(a2 + 64);
}

```

## disassembly

```asm
0x180003c94  lea     rcx, [rdx+40h]
0x180003c9b  jmp     ??1?$CQuickStringW@$0EA@@@UEAA@XZ; CQuickStringW<64>::~CQuickStringW<64>(void)
```
