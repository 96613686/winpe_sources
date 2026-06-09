# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180002160`
- end: `0x18000217f`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800020f4`

## callees

- `0x180002004`
- `0x180002160`

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
0x180002160  sub     rsp, 38h
0x180002164  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000216d  call    ??2@YAPEAX_K@Z
0x180002172  nop
0x180002173  jmp     short loc_18000217A
0x180002175  mov     rax, [rsp+38h+arg_10]
0x18000217a  add     rsp, 38h
0x18000217e  retn
```
