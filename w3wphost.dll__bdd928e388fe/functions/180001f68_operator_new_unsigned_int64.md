# operator new(unsigned __int64)

- ea: `0x180001f68`
- end: `0x180001fa1`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x180001480`
- `0x180003150`
- `0x1800032a8`
- `0x180003340`
- `0x180004750`
- `0x180004ad4`
- `0x1800051dc`
- `0x1800062a0`
- `0x180006830`
- `0x180009630`
- `0x18000a638`
- `0x18000a9b4`
- `0x18000b1d0`
- `0x18000b50c`

## callees

- `0x180001f68`
- `0x1800024a8`
- `0x1800024b4`

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
0x180001f68  mov     [rsp+arg_0], rbx
0x180001f6d  push    rdi
0x180001f6e  sub     rsp, 20h
0x180001f72  mov     rdi, rcx
0x180001f75  jmp     short loc_180001F86
0x180001f77  mov     rcx, rdi; Size
0x180001f7a  call    _callnewh_0
0x180001f7f  test    eax, eax
0x180001f81  jz      short loc_180001F93
0x180001f83  mov     rcx, rdi; Size
0x180001f86  call    malloc_0
0x180001f8b  mov     rbx, rax
0x180001f8e  test    rax, rax
0x180001f91  jz      short loc_180001F77
0x180001f93  mov     rax, rbx
0x180001f96  mov     rbx, [rsp+28h+arg_0]
0x180001f9b  add     rsp, 20h
0x180001f9f  pop     rdi
0x180001fa0  retn
```
