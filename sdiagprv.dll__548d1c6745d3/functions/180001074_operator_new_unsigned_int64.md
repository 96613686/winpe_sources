# operator new(unsigned __int64)

- ea: `0x180001074`
- end: `0x1800010ad`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x18000101c`
- `0x180001eb0`
- `0x180001f10`
- `0x180001f90`
- `0x180003fb8`
- `0x1800064b4`
- `0x180006cd0`
- `0x1800083ec`
- `0x180008710`
- `0x1800087e0`
- `0x180009da0`
- `0x18000c018`
- `0x18000d244`
- `0x18000e7f4`
- `0x18000fac8`
- `0x180011c80`
- `0x1800125e8`
- `0x180016858`
- `0x180016c78`

## callees

- `0x180001074`
- `0x1800015ec`
- `0x1800015f8`

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
0x180001074  mov     [rsp+arg_0], rbx
0x180001079  push    rdi
0x18000107a  sub     rsp, 20h
0x18000107e  mov     rdi, rcx
0x180001081  jmp     short loc_180001092
0x180001083  mov     rcx, rdi; Size
0x180001086  call    _callnewh_0
0x18000108b  test    eax, eax
0x18000108d  jz      short loc_18000109F
0x18000108f  mov     rcx, rdi; Size
0x180001092  call    malloc_0
0x180001097  mov     rbx, rax
0x18000109a  test    rax, rax
0x18000109d  jz      short loc_180001083
0x18000109f  mov     rax, rbx
0x1800010a2  mov     rbx, [rsp+28h+arg_0]
0x1800010a7  add     rsp, 20h
0x1800010ab  pop     rdi
0x1800010ac  retn
```
