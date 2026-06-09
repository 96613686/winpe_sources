# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x18000260c`
- end: `0x180002628`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006180`
- `0x180006c70`
- `0x18000731c`

## callees

- `0x180001e00`
- `0x18000260c`

## pseudocode

```c
void *__fastcall operator new(size_t a1, const struct std::nothrow_t *a2)
{
  void *result; // rax

  try
  {
    result = operator new(a1);
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000260c  sub     rsp, 38h
0x180002610  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002619  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000261e  jmp     short loc_180002622
0x180002620  xor     eax, eax
0x180002622  add     rsp, 38h
0x180002626  retn
```
