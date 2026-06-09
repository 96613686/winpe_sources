# operator new(unsigned __int64)

- ea: `0x180001fd4`
- end: `0x180002005`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ad8`
- `0x1800021a8`
- `0x180011f06`

## callees

- `0x180001fd4`
- `0x180002308`
- `0x18000292e`

## import_xrefs

- `msvcrt!malloc` at `0x180001fee`
- `msvcrt!malloc` at `0x180001fee`

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
0x180001fd4  push    rbx
0x180001fd6  sub     rsp, 20h
0x180001fda  mov     rbx, rcx
0x180001fdd  jmp     short loc_180001FEE
0x180001fdf  mov     rcx, rbx; Size
0x180001fe2  call    _callnewh_0
0x180001fe7  test    eax, eax
0x180001fe9  jz      short loc_180001FFF
0x180001feb  mov     rcx, rbx; Size
0x180001fee  call    cs:__imp_malloc
0x180001ff4  test    rax, rax
0x180001ff7  jz      short loc_180001FDF
0x180001ff9  add     rsp, 20h
0x180001ffd  pop     rbx
0x180001ffe  retn
0x180001fff  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
