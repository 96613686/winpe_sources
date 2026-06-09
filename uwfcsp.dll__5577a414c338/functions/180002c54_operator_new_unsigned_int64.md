# operator new(unsigned __int64)

- ea: `0x180002c54`
- end: `0x180002c85`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180002c8c`
- `0x180002e38`
- `0x180007310`
- `0x180008dcc`
- `0x18000d1bc`
- `0x18000e8d4`
- `0x180019010`
- `0x18001a323`

## callees

- `0x180002c54`
- `0x180002f98`
- `0x180003ef8`

## import_xrefs

- `msvcrt!malloc` at `0x180002c6e`
- `msvcrt!malloc` at `0x180002c6e`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
      std::_Xbad_alloc();
  }
  return result;
}

```

## disassembly

```asm
0x180002c54  push    rbx
0x180002c56  sub     rsp, 20h
0x180002c5a  mov     rbx, rcx
0x180002c5d  jmp     short loc_180002C6E
0x180002c5f  mov     rcx, rbx; Size
0x180002c62  call    _callnewh_0
0x180002c67  test    eax, eax
0x180002c69  jz      short loc_180002C7F
0x180002c6b  mov     rcx, rbx; Size
0x180002c6e  call    cs:__imp_malloc
0x180002c74  test    rax, rax
0x180002c77  jz      short loc_180002C5F
0x180002c79  add     rsp, 20h
0x180002c7d  pop     rbx
0x180002c7e  retn
0x180002c7f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
