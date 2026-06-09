# operator new(unsigned __int64)

- ea: `0x18000246c`
- end: `0x1800024a8`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `19`
- callee_count: `5`
- tags: ``

## callers

- `0x180002fbc`
- `0x180003130`
- `0x180003360`
- `0x180004e18`
- `0x1800057d8`
- `0x1800063f0`
- `0x1800071ac`
- `0x180007aa8`
- `0x180007afc`
- `0x180008290`
- `0x1800097ec`
- `0x1800099cc`
- `0x180009c50`
- `0x180009d50`
- `0x180009e50`
- `0x18000aa38`
- `0x18000ab84`
- `0x18000af00`
- `0x18000e1c4`

## callees

- `0x18000246c`
- `0x180002a48`
- `0x180002a70`
- `0x180002dc6`
- `0x180002e56`

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
0x18000246c  push    rbx
0x18000246e  sub     rsp, 20h
0x180002472  mov     rbx, rcx
0x180002475  jmp     short loc_180002486
0x180002477  mov     rcx, rbx
0x18000247a  call    _o__callnewh_0
0x18000247f  test    eax, eax
0x180002481  jz      short loc_180002496
0x180002483  mov     rcx, rbx; Size
0x180002486  call    _o_malloc_0
0x18000248b  test    rax, rax
0x18000248e  jz      short loc_180002477
0x180002490  add     rsp, 20h
0x180002494  pop     rbx
0x180002495  retn
0x180002496  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000249a  jz      short loc_1800024A2
0x18000249c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800024a2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
