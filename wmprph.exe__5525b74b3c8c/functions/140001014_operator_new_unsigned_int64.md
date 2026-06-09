# operator new(unsigned __int64)

- ea: `0x140001014`
- end: `0x14000104d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x140001054`
- `0x14000310c`
- `0x1400039b0`
- `0x140004360`
- `0x1400045fc`
- `0x1400050b8`
- `0x1400054f0`
- `0x140009710`
- `0x140009d70`
- `0x14000ac24`
- `0x14000ad2c`
- `0x14000ae30`

## callees

- `0x140001014`
- `0x140001c2a`
- `0x140001cea`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = o_malloc_0(Size);
    if ( v2 || !(unsigned int)o__callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x140001014  mov     [rsp+arg_0], rbx
0x140001019  push    rdi
0x14000101a  sub     rsp, 20h
0x14000101e  mov     rdi, rcx
0x140001021  jmp     short loc_140001032
0x140001023  mov     rcx, rdi
0x140001026  call    _o__callnewh_0
0x14000102b  test    eax, eax
0x14000102d  jz      short loc_14000103F
0x14000102f  mov     rcx, rdi; Size
0x140001032  call    _o_malloc_0
0x140001037  mov     rbx, rax
0x14000103a  test    rax, rax
0x14000103d  jz      short loc_140001023
0x14000103f  mov     rax, rbx
0x140001042  mov     rbx, [rsp+28h+arg_0]
0x140001047  add     rsp, 20h
0x14000104b  pop     rdi
0x14000104c  retn
```
