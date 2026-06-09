# operator new(unsigned __int64)

- ea: `0x180002090`
- end: `0x1800020c9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x1800014a0`
- `0x180003340`
- `0x1800034ac`
- `0x180003540`
- `0x180004b20`
- `0x180004ee4`
- `0x18000561c`
- `0x1800068bc`
- `0x180006ea4`
- `0x18000a0f4`
- `0x18000b000`
- `0x18000b34c`
- `0x18000b708`
- `0x18000bfa0`
- `0x18000c320`

## callees

- `0x180002090`
- `0x1800025c8`
- `0x1800025d4`

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
0x180002090  mov     [rsp+arg_0], rbx
0x180002095  push    rdi
0x180002096  sub     rsp, 20h
0x18000209a  mov     rdi, rcx
0x18000209d  jmp     short loc_1800020AE
0x18000209f  mov     rcx, rdi; Size
0x1800020a2  call    _callnewh_0
0x1800020a7  test    eax, eax
0x1800020a9  jz      short loc_1800020BB
0x1800020ab  mov     rcx, rdi; Size
0x1800020ae  call    malloc_0
0x1800020b3  mov     rbx, rax
0x1800020b6  test    rax, rax
0x1800020b9  jz      short loc_18000209F
0x1800020bb  mov     rax, rbx
0x1800020be  mov     rbx, [rsp+28h+arg_0]
0x1800020c3  add     rsp, 20h
0x1800020c7  pop     rdi
0x1800020c8  retn
```
