# operator new(unsigned __int64)

- ea: `0x1800012e4`
- end: `0x18000131d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800012d8`
- `0x18000448c`
- `0x1800045b0`
- `0x18000dfe8`

## callees

- `0x1800012e4`
- `0x180001802`
- `0x180001c5c`

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
0x1800012e4  mov     [rsp+arg_0], rbx
0x1800012e9  push    rdi
0x1800012ea  sub     rsp, 20h
0x1800012ee  mov     rdi, rcx
0x1800012f1  jmp     short loc_180001302
0x1800012f3  mov     rcx, rdi; Size
0x1800012f6  call    _callnewh_0
0x1800012fb  test    eax, eax
0x1800012fd  jz      short loc_18000130F
0x1800012ff  mov     rcx, rdi; Size
0x180001302  call    malloc_0
0x180001307  mov     rbx, rax
0x18000130a  test    rax, rax
0x18000130d  jz      short loc_1800012F3
0x18000130f  mov     rax, rbx
0x180001312  mov     rbx, [rsp+28h+arg_0]
0x180001317  add     rsp, 20h
0x18000131b  pop     rdi
0x18000131c  retn
```
