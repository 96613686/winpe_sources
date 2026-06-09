# operator new(unsigned __int64)

- ea: `0x180001174`
- end: `0x1800011a5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011ac`
- `0x180001358`
- `0x1800025f0`
- `0x180005260`
- `0x180005f60`
- `0x180007580`
- `0x180007a48`
- `0x18000c973`

## callees

- `0x180001174`
- `0x1800014b8`
- `0x180002106`

## import_xrefs

- `msvcrt!malloc` at `0x18000118e`
- `msvcrt!malloc` at `0x18000118e`

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
0x180001174  push    rbx
0x180001176  sub     rsp, 20h
0x18000117a  mov     rbx, rcx
0x18000117d  jmp     short loc_18000118E
0x18000117f  mov     rcx, rbx; Size
0x180001182  call    _callnewh_0
0x180001187  test    eax, eax
0x180001189  jz      short loc_18000119F
0x18000118b  mov     rcx, rbx; Size
0x18000118e  call    cs:__imp_malloc
0x180001194  test    rax, rax
0x180001197  jz      short loc_18000117F
0x180001199  add     rsp, 20h
0x18000119d  pop     rbx
0x18000119e  retn
0x18000119f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
