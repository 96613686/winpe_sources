# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180002ecc`
- end: `0x180002ee8`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x180008da8`
- `0x180008e98`
- `0x180009930`
- `0x180009a44`
- `0x180009ed4`
- `0x18000a614`
- `0x18000ac44`
- `0x18000afe0`
- `0x18000b208`
- `0x18000b6d8`
- `0x18000b770`
- `0x18000b954`
- `0x18000bcd4`
- `0x18000d1c0`
- `0x18000d588`
- `0x18000d8d4`
- `0x18000de0c`
- `0x18000e838`
- `0x18000ea18`

## callees

- `0x180002ecc`
- `0x180003744`

## pseudocode

```c
void *__fastcall operator new[](unsigned __int64 a1, const struct std::nothrow_t *a2)
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
0x180002ecc  sub     rsp, 38h
0x180002ed0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180002ed9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002ede  jmp     short loc_180002EE2
0x180002ee0  xor     eax, eax
0x180002ee2  add     rsp, 38h
0x180002ee6  retn
```
