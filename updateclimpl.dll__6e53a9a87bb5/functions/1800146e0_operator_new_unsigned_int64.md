# operator new(unsigned __int64)

- ea: `0x1800146e0`
- end: `0x18001471c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180009f10`
- `0x18000aaec`
- `0x18000d518`
- `0x18000dcac`
- `0x18000ecf8`
- `0x18000ee04`
- `0x18000fd24`

## callees

- `0x18000d4f0`
- `0x18000db38`
- `0x180010150`
- `0x1800102b0`
- `0x1800146e0`

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
        std::_Xbad_alloc();
      __scrt_throw_std_bad_array_new_length();
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800146e0  push    rbx
0x1800146e2  sub     rsp, 20h
0x1800146e6  mov     rbx, rcx
0x1800146e9  jmp     short loc_1800146FA
0x1800146eb  mov     rcx, rbx
0x1800146ee  call    _o__callnewh_0
0x1800146f3  test    eax, eax
0x1800146f5  jz      short loc_18001470A
0x1800146f7  mov     rcx, rbx; Size
0x1800146fa  call    _o_malloc_0
0x1800146ff  test    rax, rax
0x180014702  jz      short loc_1800146EB
0x180014704  add     rsp, 20h
0x180014708  pop     rbx
0x180014709  retn
0x18001470a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001470e  jz      short loc_180014716
0x180014710  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180014716  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
