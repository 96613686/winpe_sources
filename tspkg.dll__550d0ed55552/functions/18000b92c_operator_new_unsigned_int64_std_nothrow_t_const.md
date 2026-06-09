# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x18000b92c`
- end: `0x18000b948`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001160`
- `0x180002e50`
- `0x180003ea0`
- `0x180007c40`
- `0x180014a84`

## callees

- `0x18000b92c`
- `0x18000bdf0`

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
0x18000b92c  sub     rsp, 38h
0x18000b930  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000b939  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b93e  jmp     short loc_18000B942
0x18000b940  xor     eax, eax
0x18000b942  add     rsp, 38h
0x18000b946  retn
```
