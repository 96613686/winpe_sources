# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800017d8`
- end: `0x1800017f7`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018dc`
- `0x1800067a4`
- `0x1800077f4`
- `0x180009b30`
- `0x18000c190`
- `0x18000c8bc`
- `0x18000d1b0`

## callees

- `0x1800017d8`
- `0x180001cf8`

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
0x1800017d8  sub     rsp, 38h
0x1800017dc  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800017e5  call    ??2@YAPEAX_K@Z
0x1800017ea  nop
0x1800017eb  jmp     short loc_1800017F2
0x1800017ed  mov     rax, [rsp+38h+arg_10]
0x1800017f2  add     rsp, 38h
0x1800017f6  retn
```
