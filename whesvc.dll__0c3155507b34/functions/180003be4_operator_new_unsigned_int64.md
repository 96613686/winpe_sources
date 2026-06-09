# operator new(unsigned __int64)

- ea: `0x180003be4`
- end: `0x180003c20`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `34`
- callee_count: `5`
- tags: ``

## callers

- `0x180001cb0`
- `0x180001f30`
- `0x180002e90`
- `0x18000370c`
- `0x180003bd8`
- `0x18000f944`
- `0x18000fa50`
- `0x18000fc50`
- `0x18000fd74`
- `0x18000ff00`
- `0x1800101f4`
- `0x180010b9c`
- `0x180012194`
- `0x180014398`
- `0x180014f94`
- `0x180015d70`
- `0x180016208`
- `0x180016b28`
- `0x180016d44`
- `0x180017a54`
- `0x1800181b4`
- `0x1800183f8`
- `0x180018664`
- `0x1800187bc`
- `0x180018c10`
- `0x18001a100`
- `0x18001a534`
- `0x18001aa34`
- `0x18001abc4`
- `0x18001b084`
- `0x18001c9c8`
- `0x1800227bc`
- `0x180025780`
- `0x180025dcc`

## callees

- `0x180003be4`
- `0x180003c28`
- `0x180003cb6`
- `0x180003d5c`
- `0x180017158`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = o_malloc_0(Size);
    if ( result )
      break;
    if ( !(unsigned int)o__callnewh_0(i) )
    {
      if ( i != -1 )
        __scrt_throw_std_bad_alloc();
      __scrt_throw_std_bad_array_new_length();
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003be4  push    rbx
0x180003be6  sub     rsp, 20h
0x180003bea  mov     rbx, rcx
0x180003bed  jmp     short loc_180003BFE
0x180003bef  mov     rcx, rbx
0x180003bf2  call    _o__callnewh_0
0x180003bf7  test    eax, eax
0x180003bf9  jz      short loc_180003C0E
0x180003bfb  mov     rcx, rbx; Size
0x180003bfe  call    _o_malloc_0
0x180003c03  test    rax, rax
0x180003c06  jz      short loc_180003BEF
0x180003c08  add     rsp, 20h
0x180003c0c  pop     rbx
0x180003c0d  retn
0x180003c0e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180003c12  jz      short loc_180003C1A
0x180003c14  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180003c1a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
