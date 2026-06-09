# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x180006780`
- end: `0x18000679c`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005f68`
- `0x1800062d4`
- `0x180006418`
- `0x180006508`
- `0x1800065d0`
- `0x1800066c4`

## callees

- `0x180001976`
- `0x180006780`

## pseudocode

```c
void *__fastcall std::char_traits<unsigned short>::copy(void *a1, const void *a2, __int64 a3)
{
  if ( a3 )
    return memcpy_0(a1, a2, 2 * a3);
  return a1;
}

```

## disassembly

```asm
0x180006780  sub     rsp, 28h
0x180006784  test    r8, r8
0x180006787  jz      short loc_180006794
0x180006789  add     r8, r8; Size
0x18000678c  call    memcpy_0
0x180006791  mov     rcx, rax
0x180006794  mov     rax, rcx
0x180006797  add     rsp, 28h
0x18000679b  retn
```
