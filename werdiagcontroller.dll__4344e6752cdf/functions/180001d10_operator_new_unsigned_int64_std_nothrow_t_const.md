# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001d10`
- end: `0x180001d2c`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800040b4`
- `0x180004a70`
- `0x180005990`
- `0x180005a9c`

## callees

- `0x180001d10`
- `0x180001d40`

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
0x180001d10  sub     rsp, 38h
0x180001d14  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001d1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001d22  jmp     short loc_180001D26
0x180001d24  xor     eax, eax
0x180001d26  add     rsp, 38h
0x180001d2a  retn
```
