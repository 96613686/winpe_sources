# u8_ippsCopy_8u

- ea: `0x18003a034`
- end: `0x18003a044`
- name: `u8_ippsCopy_8u`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18004ef90`
- `0x18004f090`

## callees

- `0x180063410`

## pseudocode

```c
__int64 __fastcall u8_ippsCopy_8u(const __m128i *a1, __m128i *a2, __int64 a3)
{
  u8_ownsCopy_8u(a1, a2, a3);
  return 0;
}

```

## disassembly

```asm
0x18003a034  sub     rsp, 28h
0x18003a038  call    u8_ownsCopy_8u
0x18003a03d  xor     eax, eax
0x18003a03f  add     rsp, 28h
0x18003a043  retn
```
