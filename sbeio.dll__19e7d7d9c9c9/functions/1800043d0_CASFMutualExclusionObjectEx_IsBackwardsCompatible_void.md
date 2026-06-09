# CASFMutualExclusionObjectEx::IsBackwardsCompatible(void)

- ea: `0x1800043d0`
- end: `0x1800043d3`
- name: `?IsBackwardsCompatible@CASFMutualExclusionObjectEx@@UEAAHXZ`
- size: `3`
- prototype: `__int64 __fastcall(CASFMutualExclusionObjectEx *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001844`

## pseudocode

```c
__int64 __fastcall CASFMutualExclusionObjectEx::IsBackwardsCompatible(CASFMutualExclusionObjectEx *this)
{
  return 0;
}

```

## disassembly

```asm
0x1800043d0  xor     eax, eax
0x1800043d2  retn
```
