# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x140002174`
- end: `0x140002190`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140011bb0`
- `0x140012c80`
- `0x1400142b8`
- `0x140014604`

## callees

- `0x140001b9c`
- `0x140002174`

## pseudocode

```c
void *__fastcall operator new[](size_t a1, const struct std::nothrow_t *a2)
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
0x140002174  sub     rsp, 38h
0x140002178  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x140002181  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140002186  jmp     short loc_14000218A
0x140002188  xor     eax, eax
0x14000218a  add     rsp, 38h
0x14000218e  retn
```
