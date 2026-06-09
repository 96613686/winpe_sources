# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)

- ea: `0x140007000`
- end: `0x140007070`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140007168`
- `0x1400073a0`
- `0x1400075ec`
- `0x1400076f0`
- `0x140007ab8`
- `0x1400084a4`

## callees

- `0x1400023fc`
- `0x140007000`
- `0x14000a1d8`

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
0x140007000  push    rbx
0x140007002  sub     rsp, 20h
0x140007006  inc     qword ptr [rdx]
0x140007009  mov     rax, 7FFFFFFFFFFFFFFFh
0x140007013  mov     rcx, [rdx]
0x140007016  mov     rbx, rdx
0x140007019  cmp     rcx, rax
0x14000701c  ja      short loc_14000706A
0x14000701e  add     rcx, rcx; Size
0x140007021  jnz     short loc_140007027
0x140007023  xor     eax, eax
0x140007025  jmp     short loc_140007061
0x140007027  cmp     rcx, 1000h
0x14000702e  jb      short loc_14000705C
0x140007030  lea     rax, [rcx+27h]
0x140007034  cmp     rax, rcx
0x140007037  jbe     short loc_14000706A
0x140007039  mov     rcx, rax; Size
0x14000703c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007041  mov     rcx, rax
0x140007044  test    rax, rax
0x140007047  jnz     short loc_14000704E
0x140007049  lea     ecx, [rax+5]
0x14000704c  int     29h; Win8: RtlFailFast(ecx)
0x14000704e  add     rax, 27h ; '''
0x140007052  and     rax, 0FFFFFFFFFFFFFFE0h
0x140007056  mov     [rax-8], rcx
0x14000705a  jmp     short loc_140007061
0x14000705c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007061  dec     qword ptr [rbx]
0x140007064  add     rsp, 20h
0x140007068  pop     rbx
0x140007069  retn
0x14000706a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
