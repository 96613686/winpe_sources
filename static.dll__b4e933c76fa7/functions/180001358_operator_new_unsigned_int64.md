# operator new(unsigned __int64)

- ea: `0x180001358`
- end: `0x180001391`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180001010`
- `0x180002850`
- `0x180002dd8`
- `0x180003bbc`
- `0x180004590`
- `0x1800054f0`
- `0x180005e30`
- `0x180005f18`

## callees

- `0x180001358`
- `0x180001882`
- `0x18000188e`

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
0x180001358  mov     [rsp+arg_0], rbx
0x18000135d  push    rdi
0x18000135e  sub     rsp, 20h
0x180001362  mov     rdi, rcx
0x180001365  jmp     short loc_180001376
0x180001367  mov     rcx, rdi; Size
0x18000136a  call    _callnewh_0
0x18000136f  test    eax, eax
0x180001371  jz      short loc_180001383
0x180001373  mov     rcx, rdi; Size
0x180001376  call    malloc_0
0x18000137b  mov     rbx, rax
0x18000137e  test    rax, rax
0x180001381  jz      short loc_180001367
0x180001383  mov     rax, rbx
0x180001386  mov     rbx, [rsp+28h+arg_0]
0x18000138b  add     rsp, 20h
0x18000138f  pop     rdi
0x180001390  retn
```
