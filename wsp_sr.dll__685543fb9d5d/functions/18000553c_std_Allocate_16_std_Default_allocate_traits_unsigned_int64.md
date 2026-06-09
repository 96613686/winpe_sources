# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x18000553c`
- end: `0x180005595`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `89`
- prototype: ``
- caller_count: `38`
- callee_count: `3`
- tags: ``

## callers

- `0x180005604`
- `0x1800056ac`
- `0x1800057e0`
- `0x18000763c`
- `0x1800076d0`
- `0x180007754`
- `0x18000784c`
- `0x18000795c`
- `0x180007a68`
- `0x180007b98`
- `0x180007f1c`
- `0x18000dd40`
- `0x180013444`
- `0x1800134d4`
- `0x180015ad0`
- `0x180015b70`
- `0x180017140`
- `0x180017320`
- `0x1800173e4`
- `0x180018f28`
- `0x18001a4dc`
- `0x18001a598`
- `0x18001c2d4`
- `0x18001cfe8`
- `0x1800209d4`
- `0x1800210a0`
- `0x180021480`
- `0x180021660`
- `0x18002193c`
- `0x180021a08`
- `0x1800265d0`
- `0x180026700`
- `0x1800294c4`
- `0x180029884`
- `0x180029a10`
- `0x180029b30`
- `0x180029f64`
- `0x18002a0f0`

## callees

- `0x1800024fc`
- `0x18000553c`
- `0x180006694`

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
0x18000553c  sub     rsp, 28h
0x180005540  test    rcx, rcx
0x180005543  jnz     short loc_18000554D
0x180005545  xor     eax, eax
0x180005547  add     rsp, 28h
0x18000554b  retn
0x18000554d  cmp     rcx, 1000h
0x180005554  jb      short loc_180005586
0x180005556  lea     rax, [rcx+27h]
0x18000555a  cmp     rax, rcx
0x18000555d  jbe     short loc_18000558F
0x18000555f  mov     rcx, rax; Size
0x180005562  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005567  mov     rcx, rax
0x18000556a  test    rax, rax
0x18000556d  jnz     short loc_180005574
0x18000556f  lea     ecx, [rax+5]; Size
0x180005572  int     29h; Win8: RtlFailFast(ecx)
0x180005574  add     rax, 27h ; '''
0x180005578  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000557c  mov     [rax-8], rcx
0x180005580  add     rsp, 28h
0x180005584  retn
0x180005586  add     rsp, 28h
0x18000558a  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000558f  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
