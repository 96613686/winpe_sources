# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)

- ea: `0x180007344`
- end: `0x1800073b4`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800074ac`
- `0x1800076e4`
- `0x180007930`
- `0x180007a34`
- `0x180007dfc`
- `0x1800087e8`

## callees

- `0x180002adc`
- `0x180007344`
- `0x18000a244`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Allocate_for_capacity<0>(__int64 a1, _QWORD *a2)
{
  size_t v3; // rcx
  _QWORD *result; // rax
  void *v5; // rax
  void *v6; // rcx

  if ( ++*a2 > 0x7FFFFFFFFFFFFFFFuLL )
    goto LABEL_11;
  v3 = 2LL * *a2;
  if ( !v3 )
  {
    result = 0;
    goto LABEL_10;
  }
  if ( v3 < 0x1000 )
  {
    result = operator new(v3);
    goto LABEL_10;
  }
  if ( v3 + 39 < v3 )
LABEL_11:
    __scrt_throw_std_bad_array_new_length();
  v5 = operator new(v3 + 39);
  v6 = v5;
  if ( !v5 )
    __fastfail(5u);
  result = (_QWORD *)(((unsigned __int64)v5 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(result - 1) = v6;
LABEL_10:
  --*a2;
  return result;
}

```

## disassembly

```asm
0x180007344  push    rbx
0x180007346  sub     rsp, 20h
0x18000734a  inc     qword ptr [rdx]
0x18000734d  mov     rax, 7FFFFFFFFFFFFFFFh
0x180007357  mov     rcx, [rdx]
0x18000735a  mov     rbx, rdx
0x18000735d  cmp     rcx, rax
0x180007360  ja      short loc_1800073AE
0x180007362  add     rcx, rcx; Size
0x180007365  jnz     short loc_18000736B
0x180007367  xor     eax, eax
0x180007369  jmp     short loc_1800073A5
0x18000736b  cmp     rcx, 1000h
0x180007372  jb      short loc_1800073A0
0x180007374  lea     rax, [rcx+27h]
0x180007378  cmp     rax, rcx
0x18000737b  jbe     short loc_1800073AE
0x18000737d  mov     rcx, rax; Size
0x180007380  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007385  mov     rcx, rax
0x180007388  test    rax, rax
0x18000738b  jnz     short loc_180007392
0x18000738d  lea     ecx, [rax+5]
0x180007390  int     29h; Win8: RtlFailFast(ecx)
0x180007392  add     rax, 27h ; '''
0x180007396  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000739a  mov     [rax-8], rcx
0x18000739e  jmp     short loc_1800073A5
0x1800073a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800073a5  dec     qword ptr [rbx]
0x1800073a8  add     rsp, 20h
0x1800073ac  pop     rbx
0x1800073ad  retn
0x1800073ae  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
