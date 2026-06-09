# std::_WChar_traits<wchar_t>::compare(wchar_t const * const,wchar_t const * const,unsigned __int64)

- ea: `0x18000dc5c`
- end: `0x18000dc61`
- name: `?compare@?$_WChar_traits@_W@std@@SAHQEB_W0_K@Z`
- size: `5`
- prototype: `int __cdecl(const wchar_t *S1, const wchar_t *S2, size_t N)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007ec8`

## callees

- `0x18000e4ac`

## pseudocode

```c
// attributes: thunk
int __cdecl std::_WChar_traits<wchar_t>::compare(const wchar_t *S1, const wchar_t *S2, size_t N)
{
  return wmemcmp(S1, S2, N);
}

```

## disassembly

```asm
0x18000dc5c  jmp     wmemcmp
```
