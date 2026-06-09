# operator new(unsigned __int64)

- ea: `0x140007f24`
- end: `0x140007f55`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x140001968`
- `0x140002b40`
- `0x140005880`
- `0x140006210`
- `0x140006bd0`
- `0x1400072bc`
- `0x1400080f8`
- `0x140009910`
- `0x14000af97`

## callees

- `0x140007f24`
- `0x140008258`
- `0x1400088fc`

## import_xrefs

- `msvcrt!malloc` at `0x140007f3e`
- `msvcrt!malloc` at `0x140007f3e`

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
0x140007f24  push    rbx
0x140007f26  sub     rsp, 20h
0x140007f2a  mov     rbx, rcx
0x140007f2d  jmp     short loc_140007F3E
0x140007f2f  mov     rcx, rbx; Size
0x140007f32  call    _callnewh_0
0x140007f37  test    eax, eax
0x140007f39  jz      short loc_140007F4F
0x140007f3b  mov     rcx, rbx; Size
0x140007f3e  call    cs:__imp_malloc
0x140007f44  test    rax, rax
0x140007f47  jz      short loc_140007F2F
0x140007f49  add     rsp, 20h
0x140007f4d  pop     rbx
0x140007f4e  retn
0x140007f4f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
