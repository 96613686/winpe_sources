# operator new(unsigned __int64)

- ea: `0x1800011a0`
- end: `0x1800011d9`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `67`
- callee_count: `3`
- tags: ``

## callers

- `0x1800011ec`
- `0x180002710`
- `0x1800051c0`
- `0x1800077c0`
- `0x1800086d0`
- `0x180008ad0`
- `0x180008b5c`
- `0x180008c70`
- `0x180009820`
- `0x18000b780`
- `0x18000bb80`
- `0x18000bc60`
- `0x18000da40`
- `0x18000dab0`
- `0x18000db40`
- `0x18000e5c0`
- `0x18000ed10`
- `0x18000f320`
- `0x180010c14`
- `0x180010d00`
- `0x1800118f8`
- `0x180011fa4`
- `0x180012080`
- `0x180013a54`
- `0x180017588`
- `0x180017b68`
- `0x180017cf4`
- `0x180017ec4`
- `0x1800183f0`
- `0x180018480`
- `0x180018600`
- `0x180018700`
- `0x180018860`
- `0x1800188d0`
- `0x180018a30`
- `0x180018b30`
- `0x180018c80`
- `0x180018da0`
- `0x180018eb0`
- `0x180018f60`
- `0x180019080`
- `0x1800191b0`
- `0x180019390`
- `0x1800194a0`
- `0x1800195b0`
- `0x180019660`
- `0x180019780`
- `0x1800198f0`
- `0x180019a10`
- `0x180019aa0`

## callees

- `0x1800011a0`
- `0x180001e72`
- `0x180001f10`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = o_malloc_0(Size);
    if ( v2 || !(unsigned int)o__callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x1800011a0  mov     [rsp+arg_0], rbx
0x1800011a5  push    rdi
0x1800011a6  sub     rsp, 20h
0x1800011aa  mov     rdi, rcx
0x1800011ad  jmp     short loc_1800011BE
0x1800011af  mov     rcx, rdi
0x1800011b2  call    _o__callnewh_0
0x1800011b7  test    eax, eax
0x1800011b9  jz      short loc_1800011CB
0x1800011bb  mov     rcx, rdi; Size
0x1800011be  call    _o_malloc_0
0x1800011c3  mov     rbx, rax
0x1800011c6  test    rax, rax
0x1800011c9  jz      short loc_1800011AF
0x1800011cb  mov     rax, rbx
0x1800011ce  mov     rbx, [rsp+28h+arg_0]
0x1800011d3  add     rsp, 20h
0x1800011d7  pop     rdi
0x1800011d8  retn
```
