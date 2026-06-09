# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180001934`
- end: `0x180001950`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800057e8`
- `0x180005dac`
- `0x180005fe8`
- `0x180007214`
- `0x180008f70`
- `0x180009554`
- `0x180009770`
- `0x1800098dc`
- `0x18000ac28`
- `0x18000bf70`

## callees

- `0x180001928`
- `0x180001934`

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
0x180001934  sub     rsp, 38h
0x180001938  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001941  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180001946  jmp     short loc_18000194A
0x180001948  xor     eax, eax
0x18000194a  add     rsp, 38h
0x18000194e  retn
```
