# operator new(unsigned __int64)

- ea: `0x180001e90`
- end: `0x180001ecc`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x1800016e0`
- `0x180001ed4`
- `0x180003a84`
- `0x18000e22c`
- `0x18000e47c`
- `0x18000e5bc`
- `0x18000f7dc`
- `0x180014030`
- `0x1800169b8`

## callees

- `0x180001e90`
- `0x1800024b8`
- `0x1800027f2`
- `0x180002890`
- `0x18000c5ac`

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
0x180001e90  push    rbx
0x180001e92  sub     rsp, 20h
0x180001e96  mov     rbx, rcx
0x180001e99  jmp     short loc_180001EAA
0x180001e9b  mov     rcx, rbx
0x180001e9e  call    _o__callnewh_0
0x180001ea3  test    eax, eax
0x180001ea5  jz      short loc_180001EBA
0x180001ea7  mov     rcx, rbx; Size
0x180001eaa  call    _o_malloc_0
0x180001eaf  test    rax, rax
0x180001eb2  jz      short loc_180001E9B
0x180001eb4  add     rsp, 20h
0x180001eb8  pop     rbx
0x180001eb9  retn
0x180001eba  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001ebe  jz      short loc_180001EC6
0x180001ec0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001ec6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
