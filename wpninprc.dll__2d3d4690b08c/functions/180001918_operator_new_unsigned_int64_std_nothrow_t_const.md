# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001918`
- end: `0x180001934`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005990`
- `0x180006070`

## callees

- `0x180001918`
- `0x180001db8`

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
0x180001918  sub     rsp, 38h
0x18000191c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001925  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000192a  jmp     short loc_18000192E
0x18000192c  xor     eax, eax
0x18000192e  add     rsp, 38h
0x180001932  retn
```
