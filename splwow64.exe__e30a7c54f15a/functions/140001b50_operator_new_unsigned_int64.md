# operator new(unsigned __int64)

- ea: `0x140001b50`
- end: `0x140001b89`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x140001b9c`
- `0x140002198`
- `0x140003cf0`
- `0x140003de0`
- `0x140007a9c`
- `0x14000cca0`
- `0x14000fae0`
- `0x140010044`
- `0x140010400`
- `0x140010cac`
- `0x140010d98`
- `0x140010e70`
- `0x140010f8c`
- `0x140011bb0`
- `0x1400120f8`

## callees

- `0x140001b50`
- `0x140002792`
- `0x140002870`

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
0x140001b50  mov     [rsp+arg_0], rbx
0x140001b55  push    rdi
0x140001b56  sub     rsp, 20h
0x140001b5a  mov     rdi, rcx
0x140001b5d  jmp     short loc_140001B6E
0x140001b5f  mov     rcx, rdi
0x140001b62  call    _o__callnewh_0
0x140001b67  test    eax, eax
0x140001b69  jz      short loc_140001B7B
0x140001b6b  mov     rcx, rdi; Size
0x140001b6e  call    _o_malloc_0
0x140001b73  mov     rbx, rax
0x140001b76  test    rax, rax
0x140001b79  jz      short loc_140001B5F
0x140001b7b  mov     rax, rbx
0x140001b7e  mov     rbx, [rsp+28h+arg_0]
0x140001b83  add     rsp, 20h
0x140001b87  pop     rdi
0x140001b88  retn
```
