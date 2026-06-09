# operator new(unsigned __int64)

- ea: `0x14000111c`
- end: `0x140001155`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000115c`
- `0x140003440`
- `0x140003540`
- `0x140005c80`

## callees

- `0x14000111c`
- `0x140001d1e`
- `0x140001e00`

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
0x14000111c  mov     [rsp+arg_0], rbx
0x140001121  push    rdi
0x140001122  sub     rsp, 20h
0x140001126  mov     rdi, rcx
0x140001129  jmp     short loc_14000113A
0x14000112b  mov     rcx, rdi
0x14000112e  call    _o__callnewh_0
0x140001133  test    eax, eax
0x140001135  jz      short loc_140001147
0x140001137  mov     rcx, rdi; Size
0x14000113a  call    _o_malloc_0
0x14000113f  mov     rbx, rax
0x140001142  test    rax, rax
0x140001145  jz      short loc_14000112B
0x140001147  mov     rax, rbx
0x14000114a  mov     rbx, [rsp+28h+arg_0]
0x14000114f  add     rsp, 20h
0x140001153  pop     rdi
0x140001154  retn
```
