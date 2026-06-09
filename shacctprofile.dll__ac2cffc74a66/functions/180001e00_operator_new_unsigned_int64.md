# operator new(unsigned __int64)

- ea: `0x180001e00`
- end: `0x180001e39`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000260c`
- `0x180005f80`
- `0x180006460`

## callees

- `0x180001e00`
- `0x180002ae6`
- `0x180002b6a`

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
0x180001e00  mov     [rsp+arg_0], rbx
0x180001e05  push    rdi
0x180001e06  sub     rsp, 20h
0x180001e0a  mov     rdi, rcx
0x180001e0d  jmp     short loc_180001E1E
0x180001e0f  mov     rcx, rdi
0x180001e12  call    _o__callnewh_0
0x180001e17  test    eax, eax
0x180001e19  jz      short loc_180001E2B
0x180001e1b  mov     rcx, rdi; Size
0x180001e1e  call    _o_malloc_0
0x180001e23  mov     rbx, rax
0x180001e26  test    rax, rax
0x180001e29  jz      short loc_180001E0F
0x180001e2b  mov     rax, rbx
0x180001e2e  mov     rbx, [rsp+28h+arg_0]
0x180001e33  add     rsp, 20h
0x180001e37  pop     rdi
0x180001e38  retn
```
