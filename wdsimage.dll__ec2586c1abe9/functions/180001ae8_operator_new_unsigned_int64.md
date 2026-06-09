# operator new(unsigned __int64)

- ea: `0x180001ae8`
- end: `0x180001b19`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001588`
- `0x180001cc8`
- `0x180010326`

## callees

- `0x180001ae8`
- `0x180001e28`
- `0x18000244e`

## import_xrefs

- `msvcrt!malloc` at `0x180001b02`
- `msvcrt!malloc` at `0x180001b02`

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
0x180001ae8  push    rbx
0x180001aea  sub     rsp, 20h
0x180001aee  mov     rbx, rcx
0x180001af1  jmp     short loc_180001B02
0x180001af3  mov     rcx, rbx; Size
0x180001af6  call    _callnewh_0
0x180001afb  test    eax, eax
0x180001afd  jz      short loc_180001B13
0x180001aff  mov     rcx, rbx; Size
0x180001b02  call    cs:__imp_malloc
0x180001b08  test    rax, rax
0x180001b0b  jz      short loc_180001AF3
0x180001b0d  add     rsp, 20h
0x180001b11  pop     rbx
0x180001b12  retn
0x180001b13  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
