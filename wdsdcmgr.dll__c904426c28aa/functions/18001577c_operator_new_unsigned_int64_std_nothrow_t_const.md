# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x18001577c`
- end: `0x18001579b`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003acc`
- `0x18000a644`
- `0x18000b47c`
- `0x18000ba74`
- `0x180013760`
- `0x1800157a4`

## callees

- `0x180015068`
- `0x18001577c`

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
0x18001577c  sub     rsp, 38h
0x180015780  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180015789  call    ??2@YAPEAX_K@Z
0x18001578e  nop
0x18001578f  jmp     short loc_180015796
0x180015791  mov     rax, [rsp+38h+arg_10]
0x180015796  add     rsp, 38h
0x18001579a  retn
```
