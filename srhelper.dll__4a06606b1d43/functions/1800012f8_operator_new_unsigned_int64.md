# operator new(unsigned __int64)

- ea: `0x1800012f8`
- end: `0x180001331`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x1800012ec`
- `0x1800029d8`
- `0x180002e9c`
- `0x1800044ac`
- `0x1800080d0`
- `0x1800081c0`
- `0x18000a790`
- `0x18000ab80`
- `0x18000af70`

## callees

- `0x1800012f8`
- `0x180001812`
- `0x180001c6c`

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
0x1800012f8  mov     [rsp+arg_0], rbx
0x1800012fd  push    rdi
0x1800012fe  sub     rsp, 20h
0x180001302  mov     rdi, rcx
0x180001305  jmp     short loc_180001316
0x180001307  mov     rcx, rdi; Size
0x18000130a  call    _callnewh_0
0x18000130f  test    eax, eax
0x180001311  jz      short loc_180001323
0x180001313  mov     rcx, rdi; Size
0x180001316  call    malloc_0
0x18000131b  mov     rbx, rax
0x18000131e  test    rax, rax
0x180001321  jz      short loc_180001307
0x180001323  mov     rax, rbx
0x180001326  mov     rbx, [rsp+28h+arg_0]
0x18000132b  add     rsp, 20h
0x18000132f  pop     rdi
0x180001330  retn
```
