# operator new(unsigned __int64)

- ea: `0x140001170`
- end: `0x1400011a9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400011bc`
- `0x14000343c`

## callees

- `0x140001170`
- `0x140001db6`
- `0x140001e82`

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
0x140001170  mov     [rsp+arg_0], rbx
0x140001175  push    rdi
0x140001176  sub     rsp, 20h
0x14000117a  mov     rdi, rcx
0x14000117d  jmp     short loc_14000118E
0x14000117f  mov     rcx, rdi
0x140001182  call    _o__callnewh_0
0x140001187  test    eax, eax
0x140001189  jz      short loc_14000119B
0x14000118b  mov     rcx, rdi; Size
0x14000118e  call    _o_malloc_0
0x140001193  mov     rbx, rax
0x140001196  test    rax, rax
0x140001199  jz      short loc_14000117F
0x14000119b  mov     rax, rbx
0x14000119e  mov     rbx, [rsp+28h+arg_0]
0x1400011a3  add     rsp, 20h
0x1400011a7  pop     rdi
0x1400011a8  retn
```
