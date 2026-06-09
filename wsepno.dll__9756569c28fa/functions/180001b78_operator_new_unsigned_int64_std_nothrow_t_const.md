# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001b78`
- end: `0x180001b94`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d80`
- `0x180007fd0`
- `0x1800080a0`
- `0x1800081e0`
- `0x18000c120`

## callees

- `0x180001b78`
- `0x180001bc0`

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
0x180001b78  sub     rsp, 38h
0x180001b7c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001b85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001b8a  jmp     short loc_180001B8E
0x180001b8c  xor     eax, eax
0x180001b8e  add     rsp, 38h
0x180001b92  retn
```
