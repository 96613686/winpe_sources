# operator new(unsigned __int64)

- ea: `0x180002484`
- end: `0x1800024c0`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180002460`
- `0x180008328`
- `0x1800099ec`
- `0x180009ae8`
- `0x180009be8`

## callees

- `0x180002484`
- `0x180002948`
- `0x180002970`
- `0x1800029f6`
- `0x180002a90`

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
0x180002484  push    rbx
0x180002486  sub     rsp, 20h
0x18000248a  mov     rbx, rcx
0x18000248d  jmp     short loc_18000249E
0x18000248f  mov     rcx, rbx
0x180002492  call    _o__callnewh_0
0x180002497  test    eax, eax
0x180002499  jz      short loc_1800024AE
0x18000249b  mov     rcx, rbx; Size
0x18000249e  call    _o_malloc_0
0x1800024a3  test    rax, rax
0x1800024a6  jz      short loc_18000248F
0x1800024a8  add     rsp, 20h
0x1800024ac  pop     rbx
0x1800024ad  retn
0x1800024ae  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800024b2  jz      short loc_1800024BA
0x1800024b4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800024ba  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
