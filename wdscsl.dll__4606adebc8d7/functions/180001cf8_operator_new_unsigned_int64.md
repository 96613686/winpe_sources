# operator new(unsigned __int64)

- ea: `0x180001cf8`
- end: `0x180001d29`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800017d8`
- `0x180001ed8`
- `0x18000db76`

## callees

- `0x180001cf8`
- `0x180002038`
- `0x18000265e`

## import_xrefs

- `msvcrt!malloc` at `0x180001d12`
- `msvcrt!malloc` at `0x180001d12`

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
0x180001cf8  push    rbx
0x180001cfa  sub     rsp, 20h
0x180001cfe  mov     rbx, rcx
0x180001d01  jmp     short loc_180001D12
0x180001d03  mov     rcx, rbx; Size
0x180001d06  call    _callnewh_0
0x180001d0b  test    eax, eax
0x180001d0d  jz      short loc_180001D23
0x180001d0f  mov     rcx, rbx; Size
0x180001d12  call    cs:__imp_malloc
0x180001d18  test    rax, rax
0x180001d1b  jz      short loc_180001D03
0x180001d1d  add     rsp, 20h
0x180001d21  pop     rbx
0x180001d22  retn
0x180001d23  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
