# std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)

- ea: `0x180006874`
- end: `0x180006890`
- name: `?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z`
- size: `28`
- prototype: `void *__fastcall(void *, const void *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005e60`
- `0x1800067a4`

## callees

- `0x180001982`
- `0x180006874`

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
0x180006874  sub     rsp, 28h
0x180006878  test    r8, r8
0x18000687b  jz      short loc_180006888
0x18000687d  add     r8, r8; Size
0x180006880  call    memmove_0
0x180006885  mov     rcx, rax
0x180006888  mov     rax, rcx
0x18000688b  add     rsp, 28h
0x18000688f  retn
```
