# operator new(unsigned __int64)

- ea: `0x180001344`
- end: `0x180001375`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180001518`
- `0x180002ccc`
- `0x1800043e0`
- `0x180004428`
- `0x180004970`
- `0x180005a30`
- `0x18000a420`
- `0x18000af50`

## callees

- `0x180001344`
- `0x180001678`
- `0x1800021a9`

## import_xrefs

- `msvcrt!malloc` at `0x18000135e`
- `msvcrt!malloc` at `0x18000135e`

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
0x180001344  push    rbx
0x180001346  sub     rsp, 20h
0x18000134a  mov     rbx, rcx
0x18000134d  jmp     short loc_18000135E
0x18000134f  mov     rcx, rbx; Size
0x180001352  call    _callnewh_0
0x180001357  test    eax, eax
0x180001359  jz      short loc_18000136F
0x18000135b  mov     rcx, rbx; Size
0x18000135e  call    cs:__imp_malloc
0x180001364  test    rax, rax
0x180001367  jz      short loc_18000134F
0x180001369  add     rsp, 20h
0x18000136d  pop     rbx
0x18000136e  retn
0x18000136f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
