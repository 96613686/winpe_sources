# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x140003230`
- end: `0x14000324c`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140004398`
- `0x1400044a8`
- `0x14000a804`
- `0x14000d7d8`
- `0x14000d87c`
- `0x14000d968`
- `0x14000e098`
- `0x140015604`
- `0x14001628c`
- `0x140018c4c`
- `0x140018d70`

## callees

- `0x140003230`
- `0x140003410`

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
0x140003230  sub     rsp, 38h
0x140003234  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000323d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003242  jmp     short loc_140003246
0x140003244  xor     eax, eax
0x140003246  add     rsp, 38h
0x14000324a  retn
```
