# operator new(unsigned __int64)

- ea: `0x18000dae8`
- end: `0x18000db21`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x180001d4c`
- `0x180002c90`
- `0x1800048e0`
- `0x1800090c8`
- `0x18000b060`
- `0x18000b924`
- `0x18000baac`
- `0x18000d268`
- `0x18000fd48`
- `0x18000fdc8`
- `0x180010420`
- `0x180010638`

## callees

- `0x18000dae8`
- `0x18000e344`
- `0x18000e350`

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
0x18000dae8  mov     [rsp+arg_0], rbx
0x18000daed  push    rdi
0x18000daee  sub     rsp, 20h
0x18000daf2  mov     rdi, rcx
0x18000daf5  jmp     short loc_18000DB06
0x18000daf7  mov     rcx, rdi; Size
0x18000dafa  call    _callnewh_0
0x18000daff  test    eax, eax
0x18000db01  jz      short loc_18000DB13
0x18000db03  mov     rcx, rdi; Size
0x18000db06  call    malloc_0
0x18000db0b  mov     rbx, rax
0x18000db0e  test    rax, rax
0x18000db11  jz      short loc_18000DAF7
0x18000db13  mov     rax, rbx
0x18000db16  mov     rbx, [rsp+28h+arg_0]
0x18000db1b  add     rsp, 20h
0x18000db1f  pop     rdi
0x18000db20  retn
```
