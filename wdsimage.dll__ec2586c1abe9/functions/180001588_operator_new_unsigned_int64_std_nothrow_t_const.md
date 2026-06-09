# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x180001588`
- end: `0x1800015a7`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800015d8`
- `0x180003ff0`
- `0x180005920`
- `0x1800068e0`
- `0x180006d60`
- `0x180006e70`
- `0x1800071b0`
- `0x180007720`
- `0x180007aa0`
- `0x1800081b8`
- `0x180008820`
- `0x180008a10`
- `0x1800094b8`
- `0x180009cb4`
- `0x18000a948`
- `0x18000abe0`
- `0x18000c77c`

## callees

- `0x180001588`
- `0x180001ae8`

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
0x180001588  sub     rsp, 38h
0x18000158c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180001595  call    ??2@YAPEAX_K@Z
0x18000159a  nop
0x18000159b  jmp     short loc_1800015A2
0x18000159d  mov     rax, [rsp+38h+arg_10]
0x1800015a2  add     rsp, 38h
0x1800015a6  retn
```
