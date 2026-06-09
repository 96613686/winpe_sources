# std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)

- ea: `0x18000eb88`
- end: `0x18000eba4`
- name: `?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000e594`
- `0x18000e8cc`
- `0x18000e968`
- `0x18000ea14`
- `0x18000eae0`
- `0x18000f098`
- `0x180015870`
- `0x180015938`

## callees

- `0x180002986`
- `0x18000eb88`

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
0x18000eb88  sub     rsp, 28h
0x18000eb8c  test    r8, r8
0x18000eb8f  jz      short loc_18000EB9C
0x18000eb91  add     r8, r8; Size
0x18000eb94  call    memcpy_0
0x18000eb99  mov     rcx, rax
0x18000eb9c  mov     rax, rcx
0x18000eb9f  add     rsp, 28h
0x18000eba3  retn
```
