# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x180004e18`
- end: `0x180004e6f`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `87`
- prototype: `_QWORD *__fastcall(size_t)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180004f98`
- `0x180006848`
- `0x1800068f0`
- `0x180006a88`
- `0x1800080b8`
- `0x1800080c8`
- `0x18000a130`
- `0x18000a294`
- `0x18000bab4`

## callees

- `0x18000246c`
- `0x180004e18`
- `0x1800059e0`

## pseudocode

```c
_QWORD *__fastcall std::_Allocate<16,std::_Default_allocate_traits>(size_t a1)
{
  _QWORD *result; // rax
  void *v2; // rax
  void *v3; // rcx

  if ( !a1 )
    return 0;
  if ( a1 < 0x1000 )
    return operator new(a1);
  if ( a1 + 39 < a1 )
    std::_Throw_bad_array_new_length();
  v2 = operator new(a1 + 39);
  v3 = v2;
  if ( !v2 )
    __fastfail(5u);
  result = (_QWORD *)(((unsigned __int64)v2 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(result - 1) = v3;
  return result;
}

```

## disassembly

```asm
0x180004e18  sub     rsp, 28h
0x180004e1c  test    rcx, rcx
0x180004e1f  jnz     short loc_180004E28
0x180004e21  xor     eax, eax
0x180004e23  add     rsp, 28h
0x180004e27  retn
0x180004e28  cmp     rcx, 1000h
0x180004e2f  jb      short loc_180004E60
0x180004e31  lea     rax, [rcx+27h]
0x180004e35  cmp     rax, rcx
0x180004e38  jbe     short loc_180004E69
0x180004e3a  mov     rcx, rax; Size
0x180004e3d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004e42  mov     rcx, rax
0x180004e45  test    rax, rax
0x180004e48  jnz     short loc_180004E4F
0x180004e4a  lea     ecx, [rax+5]; Size
0x180004e4d  int     29h; Win8: RtlFailFast(ecx)
0x180004e4f  add     rax, 27h ; '''
0x180004e53  and     rax, 0FFFFFFFFFFFFFFE0h
0x180004e57  mov     [rax-8], rcx
0x180004e5b  add     rsp, 28h
0x180004e5f  retn
0x180004e60  add     rsp, 28h
0x180004e64  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004e69  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
