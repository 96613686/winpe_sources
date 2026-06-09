# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800266a0`
- end: `0x1800266bf`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `36`
- callee_count: `2`
- tags: ``

## callers

- `0x180002960`
- `0x180002c70`
- `0x180004c60`
- `0x180005f18`
- `0x180006488`
- `0x180008f4c`
- `0x180008ff0`
- `0x18000a5a4`
- `0x18000aa44`
- `0x18000b178`
- `0x18000b560`
- `0x18000c4f0`
- `0x18000e528`
- `0x18000e65c`
- `0x18000e7c8`
- `0x18000f1f4`
- `0x18000f688`
- `0x1800122a4`
- `0x180012c98`
- `0x1800141c4`
- `0x180016548`
- `0x180016904`
- `0x180018240`
- `0x1800186a0`
- `0x180018b90`
- `0x180018da4`
- `0x180018f20`
- `0x1800191c0`
- `0x180019a3c`
- `0x18001a514`
- `0x18001a9ec`
- `0x18001b118`
- `0x1800224d4`
- `0x180023c50`
- `0x180023e54`
- `0x180026694`

## callees

- `0x18001a998`
- `0x1800266a0`

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
0x1800266a0  sub     rsp, 38h
0x1800266a4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800266ad  call    ??2@YAPEAX_K@Z
0x1800266b2  nop
0x1800266b3  jmp     short loc_1800266BA
0x1800266b5  mov     rax, [rsp+38h+arg_10]
0x1800266ba  add     rsp, 38h
0x1800266be  retn
```
