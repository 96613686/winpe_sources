# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001b58`
- end: `0x180001b77`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c3c`
- `0x180006604`
- `0x1800066a8`

## callees

- `0x180001634`
- `0x180001b58`

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
0x180001b58  sub     rsp, 38h
0x180001b5c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001b65  call    ??2@YAPEAX_K@Z
0x180001b6a  nop
0x180001b6b  jmp     short loc_180001B72
0x180001b6d  mov     rax, [rsp+38h+arg_10]
0x180001b72  add     rsp, 38h
0x180001b76  retn
```
