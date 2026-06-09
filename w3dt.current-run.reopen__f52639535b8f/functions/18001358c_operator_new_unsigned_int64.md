# operator new(unsigned __int64)

- ea: `0x18001358c`
- end: `0x1800135c5`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001770`
- `0x180015660`
- `0x180015b2c`

## callees

- `0x18001358c`
- `0x180013ab2`
- `0x180013abe`

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
0x18001358c  mov     [rsp+arg_0], rbx
0x180013591  push    rdi
0x180013592  sub     rsp, 20h
0x180013596  mov     rdi, rcx
0x180013599  jmp     short loc_1800135AA
0x18001359b  mov     rcx, rdi; Size
0x18001359e  call    _callnewh_0
0x1800135a3  test    eax, eax
0x1800135a5  jz      short loc_1800135B7
0x1800135a7  mov     rcx, rdi; Size
0x1800135aa  call    malloc_0
0x1800135af  mov     rbx, rax
0x1800135b2  test    rax, rax
0x1800135b5  jz      short loc_18001359B
0x1800135b7  mov     rax, rbx
0x1800135ba  mov     rbx, [rsp+28h+arg_0]
0x1800135bf  add     rsp, 20h
0x1800135c3  pop     rdi
0x1800135c4  retn
```
