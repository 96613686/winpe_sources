# operator new(unsigned __int64)

- ea: `0x1800018e4`
- end: `0x180001920`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180001928`
- `0x180002670`
- `0x1800034a0`
- `0x18000358c`
- `0x180003680`
- `0x180006f84`

## callees

- `0x1800018e4`
- `0x1800021d4`
- `0x1800021fc`
- `0x1800025aa`
- `0x180002640`

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
0x1800018e4  push    rbx
0x1800018e6  sub     rsp, 20h
0x1800018ea  mov     rbx, rcx
0x1800018ed  jmp     short loc_1800018FE
0x1800018ef  mov     rcx, rbx
0x1800018f2  call    _o__callnewh_0
0x1800018f7  test    eax, eax
0x1800018f9  jz      short loc_18000190E
0x1800018fb  mov     rcx, rbx; Size
0x1800018fe  call    _o_malloc_0
0x180001903  test    rax, rax
0x180001906  jz      short loc_1800018EF
0x180001908  add     rsp, 20h
0x18000190c  pop     rbx
0x18000190d  retn
0x18000190e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001912  jz      short loc_18000191A
0x180001914  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18000191a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
