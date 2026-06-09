# operator new(unsigned __int64)

- ea: `0x180001f4c`
- end: `0x180001f85`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180001160`
- `0x180001590`
- `0x180001870`
- `0x180002ab8`
- `0x180002ddc`
- `0x180002f8c`
- `0x1800037c0`
- `0x180003fb0`

## callees

- `0x180001f4c`
- `0x180002472`
- `0x18000247e`

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
0x180001f4c  mov     [rsp+arg_0], rbx
0x180001f51  push    rdi
0x180001f52  sub     rsp, 20h
0x180001f56  mov     rdi, rcx
0x180001f59  jmp     short loc_180001F6A
0x180001f5b  mov     rcx, rdi; Size
0x180001f5e  call    _callnewh_0
0x180001f63  test    eax, eax
0x180001f65  jz      short loc_180001F77
0x180001f67  mov     rcx, rdi; Size
0x180001f6a  call    malloc_0
0x180001f6f  mov     rbx, rax
0x180001f72  test    rax, rax
0x180001f75  jz      short loc_180001F5B
0x180001f77  mov     rax, rbx
0x180001f7a  mov     rbx, [rsp+28h+arg_0]
0x180001f7f  add     rsp, 20h
0x180001f83  pop     rdi
0x180001f84  retn
```
