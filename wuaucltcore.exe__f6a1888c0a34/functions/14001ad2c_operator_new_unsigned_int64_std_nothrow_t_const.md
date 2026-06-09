# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x14001ad2c`
- end: `0x14001ad48`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x140005f84`
- `0x1400074c8`
- `0x140011530`
- `0x1400116e0`
- `0x140011b50`
- `0x140015c4c`
- `0x140016318`
- `0x14001671c`
- `0x140016b20`
- `0x140016ef8`
- `0x1400174fc`
- `0x1400178a0`
- `0x140017db0`

## callees

- `0x14001ad2c`
- `0x14001ad50`

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
0x14001ad2c  sub     rsp, 38h
0x14001ad30  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14001ad39  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001ad3e  jmp     short loc_14001AD42
0x14001ad40  xor     eax, eax
0x14001ad42  add     rsp, 38h
0x14001ad46  retn
```
