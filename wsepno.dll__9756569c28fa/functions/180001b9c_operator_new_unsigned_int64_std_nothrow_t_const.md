# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180001b9c`
- end: `0x180001bb8`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180006040`
- `0x1800068e0`
- `0x180006b50`
- `0x1800077f0`

## callees

- `0x180001b9c`
- `0x18000207c`

## pseudocode

```c
void *__fastcall operator new[](unsigned __int64 a1, const struct std::nothrow_t *a2)
{
  void *result; // rax

  try
  {
    result = operator new[](a1);
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
0x180001b9c  sub     rsp, 38h
0x180001ba0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001ba9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180001bae  jmp     short loc_180001BB2
0x180001bb0  xor     eax, eax
0x180001bb2  add     rsp, 38h
0x180001bb6  retn
```
