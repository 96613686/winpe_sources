# operator new(unsigned __int64)

- ea: `0x180035e74`
- end: `0x180035eb0`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x18002a720`
- `0x18002ec30`
- `0x18002eec0`
- `0x1800322d0`
- `0x180036530`
- `0x18003653c`
- `0x180037e90`
- `0x180038420`
- `0x180038ee0`
- `0x18003a7f0`
- `0x18003b160`

## callees

- `0x180035e74`
- `0x180036758`
- `0x180036780`
- `0x180036aee`
- `0x180036b80`

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
0x180035e74  push    rbx
0x180035e76  sub     rsp, 20h
0x180035e7a  mov     rbx, rcx
0x180035e7d  jmp     short loc_180035E8E
0x180035e7f  mov     rcx, rbx
0x180035e82  call    _o__callnewh_0
0x180035e87  test    eax, eax
0x180035e89  jz      short loc_180035E9E
0x180035e8b  mov     rcx, rbx; Size
0x180035e8e  call    _o_malloc_0
0x180035e93  test    rax, rax
0x180035e96  jz      short loc_180035E7F
0x180035e98  add     rsp, 20h
0x180035e9c  pop     rbx
0x180035e9d  retn
0x180035e9e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180035ea2  jz      short loc_180035EAA
0x180035ea4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180035eaa  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
