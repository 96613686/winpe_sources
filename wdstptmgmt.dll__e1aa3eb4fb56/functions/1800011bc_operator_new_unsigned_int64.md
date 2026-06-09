# operator new(unsigned __int64)

- ea: `0x1800011bc`
- end: `0x1800011ed`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011b0`
- `0x180001398`
- `0x1800029b8`
- `0x1800061fc`
- `0x180006b88`
- `0x180006cc4`
- `0x180007f84`
- `0x1800080b0`
- `0x1800081d0`
- `0x180008a30`
- `0x180009e50`
- `0x18000b2d0`
- `0x18000cd08`
- `0x18000f204`
- `0x18000ff30`
- `0x180011128`
- `0x180011220`
- `0x180011344`
- `0x1800148c0`
- `0x180015530`
- `0x1800162d0`
- `0x1800174c4`
- `0x180018410`
- `0x180018db0`
- `0x180019750`
- `0x18001eb03`

## callees

- `0x1800011bc`
- `0x1800014f8`
- `0x18000261c`

## import_xrefs

- `msvcrt!malloc` at `0x1800011d6`
- `msvcrt!malloc` at `0x1800011d6`

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
0x1800011bc  push    rbx
0x1800011be  sub     rsp, 20h
0x1800011c2  mov     rbx, rcx
0x1800011c5  jmp     short loc_1800011D6
0x1800011c7  mov     rcx, rbx; Size
0x1800011ca  call    _callnewh_0
0x1800011cf  test    eax, eax
0x1800011d1  jz      short loc_1800011E7
0x1800011d3  mov     rcx, rbx; Size
0x1800011d6  call    cs:__imp_malloc
0x1800011dc  test    rax, rax
0x1800011df  jz      short loc_1800011C7
0x1800011e1  add     rsp, 20h
0x1800011e5  pop     rbx
0x1800011e6  retn
0x1800011e7  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
