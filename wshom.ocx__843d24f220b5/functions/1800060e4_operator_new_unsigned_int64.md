# operator new(unsigned __int64)

- ea: `0x1800060e4`
- end: `0x18000611d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x1800013f0`
- `0x1800018a0`
- `0x180001c30`
- `0x18000419c`
- `0x1800042f4`
- `0x18000564c`
- `0x1800059f8`
- `0x180007f00`
- `0x180007f90`
- `0x180008080`
- `0x180008930`
- `0x180009354`
- `0x180009cf0`
- `0x18000b2f8`
- `0x18000b50c`
- `0x18000bdc0`
- `0x18000c00c`
- `0x18000c128`
- `0x18000c2f8`
- `0x18000c3ec`
- `0x18000ca00`
- `0x18000d6a0`
- `0x18000df6c`
- `0x18000e5b4`

## callees

- `0x1800060e4`
- `0x180006914`
- `0x180006920`

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
0x1800060e4  mov     [rsp+arg_0], rbx
0x1800060e9  push    rdi
0x1800060ea  sub     rsp, 20h
0x1800060ee  mov     rdi, rcx
0x1800060f1  jmp     short loc_180006102
0x1800060f3  mov     rcx, rdi; Size
0x1800060f6  call    _callnewh_0
0x1800060fb  test    eax, eax
0x1800060fd  jz      short loc_18000610F
0x1800060ff  mov     rcx, rdi; Size
0x180006102  call    malloc_0
0x180006107  mov     rbx, rax
0x18000610a  test    rax, rax
0x18000610d  jz      short loc_1800060F3
0x18000610f  mov     rax, rbx
0x180006112  mov     rbx, [rsp+28h+arg_0]
0x180006117  add     rsp, 20h
0x18000611b  pop     rdi
0x18000611c  retn
```
