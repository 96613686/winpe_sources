# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x180013814`
- end: `0x18001381c`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `8`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180012ae8`
- `0x1800134bc`
- `0x180013610`
- `0x1800136c0`

## callees

- `0x18001d1c2`

## pseudocode

```c
void *__fastcall std::char_traits<unsigned short>::copy(void *a1, const void *a2, __int64 a3)
{
  return memcpy_0(a1, a2, 2 * a3);
}

```

## disassembly

```asm
0x180013814  add     r8, r8; Size
0x180013817  jmp     memcpy_0
```
