# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800030bc`
- end: `0x1800030db`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000322c`
- `0x180009408`
- `0x180009498`
- `0x18000adb8`
- `0x18000b5dc`
- `0x180010df0`

## callees

- `0x180002fec`
- `0x1800030bc`

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
0x1800030bc  sub     rsp, 38h
0x1800030c0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800030c9  call    ??2@YAPEAX_K@Z
0x1800030ce  nop
0x1800030cf  jmp     short loc_1800030D6
0x1800030d1  mov     rax, [rsp+38h+arg_10]
0x1800030d6  add     rsp, 38h
0x1800030da  retn
```
