# operator new(unsigned __int64)

- ea: `0x180007a64`
- end: `0x180007a9d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x180006cfc`
- `0x18000f1f8`
- `0x18000fce4`
- `0x180012690`
- `0x180012a78`
- `0x180012c20`
- `0x1800133f0`
- `0x180013990`
- `0x1800144a4`
- `0x180014698`
- `0x180014898`
- `0x180015050`

## callees

- `0x180006ee1`
- `0x180007a64`
- `0x180007afc`

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
0x180007a64  mov     [rsp+arg_0], rbx
0x180007a69  push    rdi
0x180007a6a  sub     rsp, 20h
0x180007a6e  mov     rdi, rcx
0x180007a71  jmp     short loc_180007A82
0x180007a73  mov     rcx, rdi; Size
0x180007a76  call    _callnewh_0
0x180007a7b  test    eax, eax
0x180007a7d  jz      short loc_180007A8F
0x180007a7f  mov     rcx, rdi; Size
0x180007a82  call    malloc_0
0x180007a87  mov     rbx, rax
0x180007a8a  test    rax, rax
0x180007a8d  jz      short loc_180007A73
0x180007a8f  mov     rax, rbx
0x180007a92  mov     rbx, [rsp+28h+arg_0]
0x180007a97  add     rsp, 20h
0x180007a9b  pop     rdi
0x180007a9c  retn
```
