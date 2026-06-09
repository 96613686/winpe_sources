# operator new(unsigned __int64)

- ea: `0x1800011b8`
- end: `0x1800011f1`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011ac`
- `0x180002364`
- `0x180003fbc`
- `0x18000415c`
- `0x1800045f8`
- `0x1800046d0`
- `0x180004fd0`
- `0x180005240`
- `0x180005e28`
- `0x180006c40`
- `0x180008880`
- `0x18000b190`
- `0x18000b6f8`
- `0x18000baa0`
- `0x18000bf3c`
- `0x18000c1e0`
- `0x18000c30c`
- `0x18000d9b0`
- `0x180010c90`
- `0x180010d30`

## callees

- `0x1800011b8`
- `0x1800016d2`
- `0x180001c25`

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
0x1800011b8  mov     [rsp+arg_0], rbx
0x1800011bd  push    rdi
0x1800011be  sub     rsp, 20h
0x1800011c2  mov     rdi, rcx
0x1800011c5  jmp     short loc_1800011D6
0x1800011c7  mov     rcx, rdi; Size
0x1800011ca  call    _callnewh_0
0x1800011cf  test    eax, eax
0x1800011d1  jz      short loc_1800011E3
0x1800011d3  mov     rcx, rdi; Size
0x1800011d6  call    malloc_0
0x1800011db  mov     rbx, rax
0x1800011de  test    rax, rax
0x1800011e1  jz      short loc_1800011C7
0x1800011e3  mov     rax, rbx
0x1800011e6  mov     rbx, [rsp+28h+arg_0]
0x1800011eb  add     rsp, 20h
0x1800011ef  pop     rdi
0x1800011f0  retn
```
