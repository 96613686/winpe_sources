# operator new(unsigned __int64)

- ea: `0x180001374`
- end: `0x1800013a5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `45`
- callee_count: `3`
- tags: ``

## callers

- `0x1800024a8`
- `0x180005360`
- `0x18000acfc`
- `0x18000adfc`
- `0x18000aed8`
- `0x18000afd0`
- `0x180010154`
- `0x1800120a0`
- `0x1800128f0`
- `0x1800144f0`
- `0x180018c2c`
- `0x18001a9f8`
- `0x18001cbd0`
- `0x18001cc1c`
- `0x18001cc68`
- `0x18001ccb4`
- `0x18001cd10`
- `0x18001cd64`
- `0x18001cdb8`
- `0x18001cf14`
- `0x18001d118`
- `0x18001d208`
- `0x18001ee4c`
- `0x1800201a4`
- `0x180020460`
- `0x1800206bc`
- `0x180021090`
- `0x180024dc0`
- `0x180028384`
- `0x1800283d0`
- `0x18002841c`
- `0x180028468`
- `0x1800284bc`
- `0x180028510`
- `0x180028564`
- `0x180028848`
- `0x180028e5c`
- `0x180029e24`
- `0x18002b244`
- `0x18002bdf0`
- `0x18002d8e4`
- `0x18002eb60`
- `0x18002ebd8`
- `0x18003215c`
- `0x1800321ec`

## callees

- `0x180001374`
- `0x180001518`
- `0x180001cee`

## import_xrefs

- `msvcrt!malloc` at `0x18000138e`
- `msvcrt!malloc` at `0x18000138e`

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
0x180001374  push    rbx
0x180001376  sub     rsp, 20h
0x18000137a  mov     rbx, rcx
0x18000137d  jmp     short loc_18000138E
0x18000137f  mov     rcx, rbx; Size
0x180001382  call    _callnewh_0
0x180001387  test    eax, eax
0x180001389  jz      short loc_18000139F
0x18000138b  mov     rcx, rbx; Size
0x18000138e  call    cs:__imp_malloc
0x180001394  test    rax, rax
0x180001397  jz      short loc_18000137F
0x180001399  add     rsp, 20h
0x18000139d  pop     rbx
0x18000139e  retn
0x18000139f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
