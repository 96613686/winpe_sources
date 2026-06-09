# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800015d8`
- end: `0x1800015f7`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800016b8`
- `0x180007120`
- `0x1800081d0`
- `0x180008494`
- `0x18000d57c`
- `0x18000e724`
- `0x1800100e0`
- `0x180010100`
- `0x180013654`
- `0x180013700`

## callees

- `0x1800015d8`
- `0x180001bc8`

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
0x1800015d8  sub     rsp, 38h
0x1800015dc  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800015e5  call    ??2@YAPEAX_K@Z
0x1800015ea  nop
0x1800015eb  jmp     short loc_1800015F2
0x1800015ed  mov     rax, [rsp+38h+arg_10]
0x1800015f2  add     rsp, 38h
0x1800015f6  retn
```
