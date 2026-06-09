# operator new(unsigned __int64)

- ea: `0x180002c20`
- end: `0x180002c5c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180002c64`
- `0x180002c88`
- `0x180006074`
- `0x18000618c`
- `0x1800062b0`
- `0x18000b080`

## callees

- `0x180002c20`
- `0x180003234`
- `0x18000325c`
- `0x1800032f2`
- `0x180003390`

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
0x180002c20  push    rbx
0x180002c22  sub     rsp, 20h
0x180002c26  mov     rbx, rcx
0x180002c29  jmp     short loc_180002C3A
0x180002c2b  mov     rcx, rbx
0x180002c2e  call    _o__callnewh_0
0x180002c33  test    eax, eax
0x180002c35  jz      short loc_180002C4A
0x180002c37  mov     rcx, rbx; Size
0x180002c3a  call    _o_malloc_0
0x180002c3f  test    rax, rax
0x180002c42  jz      short loc_180002C2B
0x180002c44  add     rsp, 20h
0x180002c48  pop     rbx
0x180002c49  retn
0x180002c4a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002c4e  jz      short loc_180002C56
0x180002c50  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002c56  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
