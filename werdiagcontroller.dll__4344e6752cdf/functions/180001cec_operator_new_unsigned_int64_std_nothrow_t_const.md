# operator new[](unsigned __int64,std::nothrow_t const &)

- ea: `0x180001cec`
- end: `0x180001d08`
- name: `??_U@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b58`
- `0x1800052d0`

## callees

- `0x180001cec`
- `0x180001d34`

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
0x180001cec  sub     rsp, 38h
0x180001cf0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001cf9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180001cfe  jmp     short loc_180001D02
0x180001d00  xor     eax, eax
0x180001d02  add     rsp, 38h
0x180001d06  retn
```
