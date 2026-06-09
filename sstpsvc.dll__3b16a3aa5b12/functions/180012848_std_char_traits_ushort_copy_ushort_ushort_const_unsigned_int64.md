# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x180012848`
- end: `0x180012850`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `8`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180011b54`
- `0x1800124fc`
- `0x180012644`
- `0x1800126f4`

## callees

- `0x18001bca2`

## pseudocode

```c
void *__fastcall std::char_traits<unsigned short>::copy(void *a1, const void *a2, __int64 a3)
{
  return memcpy_0(a1, a2, 2 * a3);
}

```

## disassembly

```asm
0x180012848  add     r8, r8; Size
0x18001284b  jmp     memcpy_0
```
