# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x18000d740`
- end: `0x18000d75c`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `23`
- callee_count: `2`
- tags: ``

## callers

- `0x180001940`
- `0x180002bf0`
- `0x180004c90`
- `0x180005060`
- `0x180006ba0`
- `0x180007970`
- `0x180008510`
- `0x1800093a0`
- `0x18000db20`
- `0x18000dbd0`
- `0x18000e130`
- `0x18000f5d0`
- `0x1800110b0`
- `0x180011100`
- `0x180011480`
- `0x180011510`
- `0x180013630`
- `0x1800136b0`
- `0x180014330`
- `0x1800143b0`
- `0x180014520`
- `0x180014910`
- `0x180014b50`

## callees

- `0x18000be0c`
- `0x18000d740`

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
0x18000d740  sub     rsp, 38h
0x18000d744  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000d74d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d752  jmp     short loc_18000D756
0x18000d754  xor     eax, eax
0x18000d756  add     rsp, 38h
0x18000d75a  retn
```
