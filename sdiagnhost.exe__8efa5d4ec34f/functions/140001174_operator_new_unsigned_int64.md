# operator new(unsigned __int64)

- ea: `0x140001174`
- end: `0x1400011a5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140001ed8`
- `0x140002238`
- `0x140002c40`
- `0x140006d2c`
- `0x1400078f6`

## callees

- `0x140001174`
- `0x140001318`
- `0x1400017e5`

## import_xrefs

- `msvcrt!malloc` at `0x14000118e`
- `msvcrt!malloc` at `0x14000118e`

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
0x140001174  push    rbx
0x140001176  sub     rsp, 20h
0x14000117a  mov     rbx, rcx
0x14000117d  jmp     short loc_14000118E
0x14000117f  mov     rcx, rbx; Size
0x140001182  call    _callnewh_0
0x140001187  test    eax, eax
0x140001189  jz      short loc_14000119F
0x14000118b  mov     rcx, rbx; Size
0x14000118e  call    cs:__imp_malloc
0x140001194  test    rax, rax
0x140001197  jz      short loc_14000117F
0x140001199  add     rsp, 20h
0x14000119d  pop     rbx
0x14000119e  retn
0x14000119f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
