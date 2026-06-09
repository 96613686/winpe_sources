# operator new(unsigned __int64)

- ea: `0x1800011dc`
- end: `0x18000120d`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x180001214`
- `0x1800013c8`
- `0x180003e64`
- `0x180003f88`
- `0x1800040ac`
- `0x1800041d0`
- `0x1800042dc`
- `0x1800043e8`
- `0x180004500`
- `0x180007860`
- `0x1800085ac`
- `0x180009ca0`
- `0x18000af74`
- `0x18000c428`
- `0x18000cf6c`
- `0x180010ff4`
- `0x180012913`

## callees

- `0x1800011dc`
- `0x180001528`
- `0x1800024d6`

## import_xrefs

- `msvcrt!malloc` at `0x1800011f6`
- `msvcrt!malloc` at `0x1800011f6`

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
0x1800011dc  push    rbx
0x1800011de  sub     rsp, 20h
0x1800011e2  mov     rbx, rcx
0x1800011e5  jmp     short loc_1800011F6
0x1800011e7  mov     rcx, rbx; Size
0x1800011ea  call    _callnewh_0
0x1800011ef  test    eax, eax
0x1800011f1  jz      short loc_180001207
0x1800011f3  mov     rcx, rbx; Size
0x1800011f6  call    cs:__imp_malloc
0x1800011fc  test    rax, rax
0x1800011ff  jz      short loc_1800011E7
0x180001201  add     rsp, 20h
0x180001205  pop     rbx
0x180001206  retn
0x180001207  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
