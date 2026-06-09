# operator new(unsigned __int64)

- ea: `0x180001064`
- end: `0x180001095`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180001238`
- `0x1800022b0`
- `0x180002700`
- `0x180003798`
- `0x1800037d8`
- `0x180003c20`

## callees

- `0x180001064`
- `0x180001398`
- `0x180001f06`

## import_xrefs

- `msvcrt!malloc` at `0x18000107e`
- `msvcrt!malloc` at `0x18000107e`

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
0x180001064  push    rbx
0x180001066  sub     rsp, 20h
0x18000106a  mov     rbx, rcx
0x18000106d  jmp     short loc_18000107E
0x18000106f  mov     rcx, rbx; Size
0x180001072  call    _callnewh_0
0x180001077  test    eax, eax
0x180001079  jz      short loc_18000108F
0x18000107b  mov     rcx, rbx; Size
0x18000107e  call    cs:__imp_malloc
0x180001084  test    rax, rax
0x180001087  jz      short loc_18000106F
0x180001089  add     rsp, 20h
0x18000108d  pop     rbx
0x18000108e  retn
0x18000108f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
