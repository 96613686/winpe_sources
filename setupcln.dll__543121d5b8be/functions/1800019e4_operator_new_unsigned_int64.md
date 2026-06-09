# operator new(unsigned __int64)

- ea: `0x1800019e4`
- end: `0x180001a15`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180001cc8`
- `0x180003ac4`
- `0x1800047e0`
- `0x1800048f0`
- `0x180005080`
- `0x1800082b4`
- `0x1800083d8`
- `0x180008988`
- `0x180008ad0`
- `0x1800132f3`

## callees

- `0x1800019e4`
- `0x180001e28`
- `0x180002abd`

## import_xrefs

- `msvcrt!malloc` at `0x1800019fe`
- `msvcrt!malloc` at `0x1800019fe`

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
0x1800019e4  push    rbx
0x1800019e6  sub     rsp, 20h
0x1800019ea  mov     rbx, rcx
0x1800019ed  jmp     short loc_1800019FE
0x1800019ef  mov     rcx, rbx; Size
0x1800019f2  call    _callnewh_0
0x1800019f7  test    eax, eax
0x1800019f9  jz      short loc_180001A0F
0x1800019fb  mov     rcx, rbx; Size
0x1800019fe  call    cs:__imp_malloc
0x180001a04  test    rax, rax
0x180001a07  jz      short loc_1800019EF
0x180001a09  add     rsp, 20h
0x180001a0d  pop     rbx
0x180001a0e  retn
0x180001a0f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
