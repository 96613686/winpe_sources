# operator new(unsigned __int64)

- ea: `0x180001d40`
- end: `0x180001d7c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001d10`
- `0x180001d34`

## callees

- `0x180001c4e`
- `0x180001cae`
- `0x180001d40`
- `0x180001ef4`
- `0x180001f1c`

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
0x180001d40  push    rbx
0x180001d42  sub     rsp, 20h
0x180001d46  mov     rbx, rcx
0x180001d49  jmp     short loc_180001D5A
0x180001d4b  mov     rcx, rbx
0x180001d4e  call    _o__callnewh_0
0x180001d53  test    eax, eax
0x180001d55  jz      short loc_180001D6A
0x180001d57  mov     rcx, rbx; Size
0x180001d5a  call    _o_malloc_0
0x180001d5f  test    rax, rax
0x180001d62  jz      short loc_180001D4B
0x180001d64  add     rsp, 20h
0x180001d68  pop     rbx
0x180001d69  retn
0x180001d6a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001d6e  jz      short loc_180001D76
0x180001d70  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001d76  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
