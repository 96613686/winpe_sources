# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001d98`
- end: `0x180001db7`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001d8c`
- `0x18000a7f8`
- `0x18000fe78`
- `0x180010f64`
- `0x180011224`

## callees

- `0x1800011d0`
- `0x180001d98`

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
0x180001d98  sub     rsp, 38h
0x180001d9c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001da5  call    ??2@YAPEAX_K@Z
0x180001daa  nop
0x180001dab  jmp     short loc_180001DB2
0x180001dad  mov     rax, [rsp+38h+arg_10]
0x180001db2  add     rsp, 38h
0x180001db6  retn
```
