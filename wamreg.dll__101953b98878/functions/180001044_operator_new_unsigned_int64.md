# operator new(unsigned __int64)

- ea: `0x180001044`
- end: `0x18000107d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ac0`
- `0x180002930`
- `0x180003380`
- `0x180004470`
- `0x180004540`
- `0x180004864`
- `0x1800053d8`
- `0x1800058a0`
- `0x180005cfc`
- `0x180005f74`

## callees

- `0x180001044`
- `0x180001801`
- `0x18000180d`

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
0x180001044  mov     [rsp+arg_0], rbx
0x180001049  push    rdi
0x18000104a  sub     rsp, 20h
0x18000104e  mov     rdi, rcx
0x180001051  jmp     short loc_180001062
0x180001053  mov     rcx, rdi; Size
0x180001056  call    _callnewh_0
0x18000105b  test    eax, eax
0x18000105d  jz      short loc_18000106F
0x18000105f  mov     rcx, rdi; Size
0x180001062  call    malloc_0
0x180001067  mov     rbx, rax
0x18000106a  test    rax, rax
0x18000106d  jz      short loc_180001053
0x18000106f  mov     rax, rbx
0x180001072  mov     rbx, [rsp+28h+arg_0]
0x180001077  add     rsp, 20h
0x18000107b  pop     rdi
0x18000107c  retn
```
