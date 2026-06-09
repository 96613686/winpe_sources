# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x18000195c`
- end: `0x18000197b`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180001984`
- `0x180002108`
- `0x180002c24`
- `0x1800034b8`
- `0x180003a18`
- `0x180004054`
- `0x1800042f0`
- `0x180010a9c`
- `0x180012790`
- `0x180015144`
- `0x1800162d4`
- `0x180018a14`
- `0x18001b0cc`

## callees

- `0x18000195c`
- `0x18001b024`

## pseudocode

```c
void *__fastcall operator new(unsigned __int64 a1, const struct std::nothrow_t *a2)
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
0x18000195c  sub     rsp, 38h
0x180001960  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001969  call    ??2@YAPEAX_K@Z
0x18000196e  nop
0x18000196f  jmp     short loc_180001976
0x180001971  mov     rax, [rsp+38h+arg_10]
0x180001976  add     rsp, 38h
0x18000197a  retn
```
