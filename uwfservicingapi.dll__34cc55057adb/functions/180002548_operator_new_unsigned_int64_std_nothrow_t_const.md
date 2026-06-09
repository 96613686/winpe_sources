# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180002548`
- end: `0x180002567`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002570`
- `0x180003c6c`

## callees

- `0x180001a38`
- `0x180002548`

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
0x180002548  sub     rsp, 38h
0x18000254c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002555  call    ??2@YAPEAX_K@Z
0x18000255a  nop
0x18000255b  jmp     short loc_180002562
0x18000255d  mov     rax, [rsp+38h+arg_10]
0x180002562  add     rsp, 38h
0x180002566  retn
```
