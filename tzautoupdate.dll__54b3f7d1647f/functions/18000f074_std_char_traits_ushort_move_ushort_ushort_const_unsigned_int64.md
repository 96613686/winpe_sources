# std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)

- ea: `0x18000f074`
- end: `0x18000f090`
- name: `?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e4a0`
- `0x18000ef38`
- `0x18000f098`

## callees

- `0x180002992`
- `0x18000f074`

## pseudocode

```c
void *__fastcall std::char_traits<unsigned short>::move(void *a1, const void *a2, __int64 a3)
{
  if ( a3 )
    return memmove_0(a1, a2, 2 * a3);
  return a1;
}

```

## disassembly

```asm
0x18000f074  sub     rsp, 28h
0x18000f078  test    r8, r8
0x18000f07b  jz      short loc_18000F088
0x18000f07d  add     r8, r8; Size
0x18000f080  call    memmove_0
0x18000f085  mov     rcx, rax
0x18000f088  mov     rax, rcx
0x18000f08b  add     rsp, 28h
0x18000f08f  retn
```
