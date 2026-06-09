# operator new(unsigned __int64)

- ea: `0x180002adc`
- end: `0x180002b18`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180007344`
- `0x1800073bc`
- `0x1800077dc`
- `0x180007b50`
- `0x180007cc4`
- `0x180007f3c`
- `0x1800080a4`
- `0x180009bf0`
- `0x18000c0b0`

## callees

- `0x180002adc`
- `0x180003060`
- `0x1800030e6`
- `0x180003180`
- `0x18000a244`

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
0x180002adc  push    rbx
0x180002ade  sub     rsp, 20h
0x180002ae2  mov     rbx, rcx
0x180002ae5  jmp     short loc_180002AF6
0x180002ae7  mov     rcx, rbx
0x180002aea  call    _o__callnewh_0
0x180002aef  test    eax, eax
0x180002af1  jz      short loc_180002B06
0x180002af3  mov     rcx, rbx; Size
0x180002af6  call    _o_malloc_0
0x180002afb  test    rax, rax
0x180002afe  jz      short loc_180002AE7
0x180002b00  add     rsp, 20h
0x180002b04  pop     rbx
0x180002b05  retn
0x180002b06  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002b0a  jz      short loc_180002B12
0x180002b0c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002b12  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
