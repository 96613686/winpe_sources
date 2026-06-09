# operator new(unsigned __int64)

- ea: `0x180007f50`
- end: `0x180007f89`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001830`
- `0x1800092b0`

## callees

- `0x180007f50`
- `0x180008466`
- `0x180008472`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = malloc_0(Size);
    if ( v2 || !callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x180007f50  mov     [rsp+arg_0], rbx
0x180007f55  push    rdi
0x180007f56  sub     rsp, 20h
0x180007f5a  mov     rdi, rcx
0x180007f5d  jmp     short loc_180007F6E
0x180007f5f  mov     rcx, rdi; Size
0x180007f62  call    _callnewh_0
0x180007f67  test    eax, eax
0x180007f69  jz      short loc_180007F7B
0x180007f6b  mov     rcx, rdi; Size
0x180007f6e  call    malloc_0
0x180007f73  mov     rbx, rax
0x180007f76  test    rax, rax
0x180007f79  jz      short loc_180007F5F
0x180007f7b  mov     rax, rbx
0x180007f7e  mov     rbx, [rsp+28h+arg_0]
0x180007f83  add     rsp, 20h
0x180007f87  pop     rdi
0x180007f88  retn
```
