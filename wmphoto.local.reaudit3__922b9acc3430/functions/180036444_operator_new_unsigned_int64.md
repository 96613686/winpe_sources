# operator new(unsigned __int64)

- ea: `0x180036444`
- end: `0x180036480`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x18002a8d0`
- `0x18002efc0`
- `0x18002f250`
- `0x1800327b0`
- `0x180036b00`
- `0x180036b0c`
- `0x1800384c0`
- `0x180038a70`
- `0x1800395a0`
- `0x18003af80`
- `0x18003b920`

## callees

- `0x180036444`
- `0x180036d28`
- `0x180036d50`
- `0x1800370be`
- `0x180037150`

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
0x180036444  push    rbx
0x180036446  sub     rsp, 20h
0x18003644a  mov     rbx, rcx
0x18003644d  jmp     short loc_18003645E
0x18003644f  mov     rcx, rbx
0x180036452  call    _o__callnewh_0
0x180036457  test    eax, eax
0x180036459  jz      short loc_18003646E
0x18003645b  mov     rcx, rbx; Size
0x18003645e  call    _o_malloc_0
0x180036463  test    rax, rax
0x180036466  jz      short loc_18003644F
0x180036468  add     rsp, 20h
0x18003646c  pop     rbx
0x18003646d  retn
0x18003646e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180036472  jz      short loc_18003647A
0x180036474  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18003647a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
