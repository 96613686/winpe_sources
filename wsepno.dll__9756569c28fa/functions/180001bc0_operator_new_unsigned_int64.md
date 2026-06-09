# operator new(unsigned __int64)

- ea: `0x180001bc0`
- end: `0x180001bfc`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180001280`
- `0x1800012e0`
- `0x180001b78`
- `0x18000207c`

## callees

- `0x180001bc0`
- `0x180002088`
- `0x1800020b0`
- `0x180002136`
- `0x1800021d0`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = o_malloc_0(Size);
    if ( result )
      break;
    if ( !(unsigned int)o__callnewh_0(i) )
    {
      if ( i != -1 )
        __scrt_throw_std_bad_alloc();
      __scrt_throw_std_bad_array_new_length();
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001bc0  push    rbx
0x180001bc2  sub     rsp, 20h
0x180001bc6  mov     rbx, rcx
0x180001bc9  jmp     short loc_180001BDA
0x180001bcb  mov     rcx, rbx
0x180001bce  call    _o__callnewh_0
0x180001bd3  test    eax, eax
0x180001bd5  jz      short loc_180001BEA
0x180001bd7  mov     rcx, rbx; Size
0x180001bda  call    _o_malloc_0
0x180001bdf  test    rax, rax
0x180001be2  jz      short loc_180001BCB
0x180001be4  add     rsp, 20h
0x180001be8  pop     rbx
0x180001be9  retn
0x180001bea  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001bee  jz      short loc_180001BF6
0x180001bf0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001bf6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
