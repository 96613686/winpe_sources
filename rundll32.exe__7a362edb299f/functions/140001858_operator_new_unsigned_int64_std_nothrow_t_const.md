# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x140001858`
- end: `0x140001874`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002be0`
- `0x140005b90`
- `0x14000678c`

## callees

- `0x140001858`
- `0x140001e84`

## pseudocode

```c
void *__fastcall operator new[](unsigned __int64 a1, const struct std::nothrow_t *a2)
{
  void *result; // rax

  try
  {
    result = operator new[](a1);
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
0x140001858  sub     rsp, 38h
0x14000185c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140001865  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000186a  jmp     short loc_14000186E
0x14000186c  xor     eax, eax
0x14000186e  add     rsp, 38h
0x140001872  retn
```
