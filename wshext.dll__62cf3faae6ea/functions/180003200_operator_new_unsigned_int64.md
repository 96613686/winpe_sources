# operator new(unsigned __int64)

- ea: `0x180003200`
- end: `0x180003239`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x180001b30`
- `0x180001fd0`
- `0x180002f90`
- `0x180004f90`
- `0x180005fa0`
- `0x180006df0`
- `0x180008178`
- `0x180008a04`
- `0x180009078`
- `0x1800091fc`
- `0x1800093c0`
- `0x180009e90`
- `0x18000a490`
- `0x18000a848`

## callees

- `0x180003200`
- `0x180003a24`
- `0x180003a3c`

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
0x180003200  mov     [rsp+arg_0], rbx
0x180003205  push    rdi
0x180003206  sub     rsp, 20h
0x18000320a  mov     rdi, rcx
0x18000320d  jmp     short loc_18000321E
0x18000320f  mov     rcx, rdi; Size
0x180003212  call    _callnewh_0
0x180003217  test    eax, eax
0x180003219  jz      short loc_18000322B
0x18000321b  mov     rcx, rdi; Size
0x18000321e  call    malloc_0
0x180003223  mov     rbx, rax
0x180003226  test    rax, rax
0x180003229  jz      short loc_18000320F
0x18000322b  mov     rax, rbx
0x18000322e  mov     rbx, [rsp+28h+arg_0]
0x180003233  add     rsp, 20h
0x180003237  pop     rdi
0x180003238  retn
```
