# operator new(unsigned __int64)

- ea: `0x1400023fc`
- end: `0x140002438`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x140007000`
- `0x140007078`
- `0x140007498`
- `0x14000780c`
- `0x140007980`
- `0x140007bf8`
- `0x140007d60`
- `0x14000a6a8`

## callees

- `0x1400023fc`
- `0x140002a84`
- `0x140002b46`
- `0x140002c20`
- `0x14000a1d8`

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
0x1400023fc  push    rbx
0x1400023fe  sub     rsp, 20h
0x140002402  mov     rbx, rcx
0x140002405  jmp     short loc_140002416
0x140002407  mov     rcx, rbx
0x14000240a  call    _o__callnewh_0
0x14000240f  test    eax, eax
0x140002411  jz      short loc_140002426
0x140002413  mov     rcx, rbx; Size
0x140002416  call    _o_malloc_0
0x14000241b  test    rax, rax
0x14000241e  jz      short loc_140002407
0x140002420  add     rsp, 20h
0x140002424  pop     rbx
0x140002425  retn
0x140002426  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000242a  jz      short loc_140002432
0x14000242c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140002432  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
