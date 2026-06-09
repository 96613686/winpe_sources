# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001ad8`
- end: `0x180001af7`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180001acc`
- `0x180004dc0`
- `0x180004f14`
- `0x180005000`
- `0x18000523c`
- `0x1800054e4`
- `0x180005e44`
- `0x180008aa0`

## callees

- `0x180001ad8`
- `0x180001fd4`

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
0x180001ad8  sub     rsp, 38h
0x180001adc  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001ae5  call    ??2@YAPEAX_K@Z
0x180001aea  nop
0x180001aeb  jmp     short loc_180001AF2
0x180001aed  mov     rax, [rsp+38h+arg_10]
0x180001af2  add     rsp, 38h
0x180001af6  retn
```
