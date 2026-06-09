# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x180005510`
- end: `0x180005567`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `87`
- prototype: `_QWORD *__fastcall(size_t)`
- caller_count: `38`
- callee_count: `3`
- tags: ``

## callers

- `0x1800055d8`
- `0x180005680`
- `0x1800057ac`
- `0x180007564`
- `0x1800075f8`
- `0x180007678`
- `0x180007770`
- `0x18000787c`
- `0x180007988`
- `0x180007ab8`
- `0x180007de8`
- `0x18000de40`
- `0x1800135d4`
- `0x180014768`
- `0x180015c20`
- `0x180015cc0`
- `0x180017248`
- `0x180017380`
- `0x18001755c`
- `0x180017620`
- `0x18001a43c`
- `0x18001a4cc`
- `0x18001a58c`
- `0x18001cecc`
- `0x180020874`
- `0x180020f40`
- `0x1800212f4`
- `0x1800214d0`
- `0x1800217a4`
- `0x18002186c`
- `0x180026290`
- `0x1800263bc`
- `0x180029040`
- `0x1800293f4`
- `0x180029570`
- `0x180029690`
- `0x180029ab8`
- `0x180029c40`

## callees

- `0x1800024cc`
- `0x180005510`
- `0x18000664c`

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
0x180005510  sub     rsp, 28h
0x180005514  test    rcx, rcx
0x180005517  jnz     short loc_180005520
0x180005519  xor     eax, eax
0x18000551b  add     rsp, 28h
0x18000551f  retn
0x180005520  cmp     rcx, 1000h
0x180005527  jb      short loc_180005558
0x180005529  lea     rax, [rcx+27h]
0x18000552d  cmp     rax, rcx
0x180005530  jbe     short loc_180005561
0x180005532  mov     rcx, rax; Size
0x180005535  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000553a  mov     rcx, rax
0x18000553d  test    rax, rax
0x180005540  jnz     short loc_180005547
0x180005542  lea     ecx, [rax+5]; Size
0x180005545  int     29h; Win8: RtlFailFast(ecx)
0x180005547  add     rax, 27h ; '''
0x18000554b  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000554f  mov     [rax-8], rcx
0x180005553  add     rsp, 28h
0x180005557  retn
0x180005558  add     rsp, 28h
0x18000555c  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005561  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
