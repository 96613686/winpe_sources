# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180002460`
- end: `0x18000247c`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800066dc`
- `0x18000677c`
- `0x180006d64`
- `0x180006e08`
- `0x180006ea0`
- `0x1800077a4`
- `0x180007850`
- `0x180009190`

## callees

- `0x180002460`
- `0x180002484`

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
0x180002460  sub     rsp, 38h
0x180002464  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000246d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002472  jmp     short loc_180002476
0x180002474  xor     eax, eax
0x180002476  add     rsp, 38h
0x18000247a  retn
```
