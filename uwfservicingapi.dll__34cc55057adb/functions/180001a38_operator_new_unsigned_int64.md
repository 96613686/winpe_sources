# operator new(unsigned __int64)

- ea: `0x180001a38`
- end: `0x180001a69`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180001c18`
- `0x180002548`
- `0x180003260`
- `0x180005527`

## callees

- `0x180001a38`
- `0x180001d78`
- `0x180002491`

## import_xrefs

- `msvcrt!malloc` at `0x180001a52`
- `msvcrt!malloc` at `0x180001a52`

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
0x180001a38  push    rbx
0x180001a3a  sub     rsp, 20h
0x180001a3e  mov     rbx, rcx
0x180001a41  jmp     short loc_180001A52
0x180001a43  mov     rcx, rbx; Size
0x180001a46  call    _callnewh_0
0x180001a4b  test    eax, eax
0x180001a4d  jz      short loc_180001A63
0x180001a4f  mov     rcx, rbx; Size
0x180001a52  call    cs:__imp_malloc
0x180001a58  test    rax, rax
0x180001a5b  jz      short loc_180001A43
0x180001a5d  add     rsp, 20h
0x180001a61  pop     rbx
0x180001a62  retn
0x180001a63  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
