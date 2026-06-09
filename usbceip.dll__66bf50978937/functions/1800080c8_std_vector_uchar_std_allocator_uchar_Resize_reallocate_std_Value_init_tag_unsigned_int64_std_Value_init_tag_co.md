# std::vector<uchar,std::allocator<uchar>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x1800080c8`
- end: `0x18000819a`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `210`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `7`
- callee_count: `8`
- tags: ``

## callers

- `0x180008290`
- `0x180008c74`
- `0x180009b24`
- `0x18000a698`
- `0x18000af94`
- `0x18000b358`
- `0x18000b464`

## callees

- `0x180002e6e`
- `0x180004060`
- `0x180004e18`
- `0x1800080c8`
- `0x180008218`
- `0x1800085c4`
- `0x1800085f8`
- `0x18000feb4`

## pseudocode

```c
__int64 __fastcall std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(
        _QWORD *a1,
        unsigned __int64 a2)
{
  __int64 v4; // rsi
  size_t v5; // r12
  char *v6; // rax
  char *v7; // rdi
  char *v8; // r15
  size_t v9; // r8
  _QWORD *v10; // rdx
  _QWORD *v11; // rcx
  _QWORD v13[13]; // [rsp+20h] [rbp-68h] BYREF

  if ( a2 > 0x7FFFFFFFFFFFFFFFLL )
    std::vector<unsigned short>::_Xlength();
  v4 = a1[1] - *a1;
  v5 = std::vector<unsigned char>::_Calculate_growth();
  v6 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v5);
  v13[0] = a1;
  v13[2] = v5;
  v7 = &v6[v4];
  v8 = v6;
  v13[3] = &v6[v4];
  memset_0(&v6[v4], 0, a2 - v4);
  v9 = a1[1] - *a1;
  v10 = (_QWORD *)*a1;
  v13[4] = &v7[a2 - v4];
  memmove_0(v8, v10, v9);
  v11 = (_QWORD *)*a1;
  v13[1] = 0;
  if ( v11 )
    std::_Deallocate<16>(v11, a1[2] - (_QWORD)v11);
  *a1 = v8;
  a1[1] = &v8[a2];
  a1[2] = &v8[v5];
  return std::vector<unsigned char>::_Reallocation_guard::~_Reallocation_guard(v13);
}

```

## disassembly

```asm
0x1800080c8  push    rbx
0x1800080ca  push    rbp
0x1800080cb  push    rsi
0x1800080cc  push    rdi
0x1800080cd  push    r12
0x1800080cf  push    r14
0x1800080d1  push    r15
0x1800080d3  sub     rsp, 50h
0x1800080d7  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800080e1  mov     rbp, rdx
0x1800080e4  mov     r14, rcx
0x1800080e7  cmp     rdx, rax
0x1800080ea  ja      loc_180008194
0x1800080f0  mov     rsi, [rcx+8]
0x1800080f4  sub     rsi, [rcx]
0x1800080f7  call    ?_Calculate_growth@?$vector@EV?$allocator@E@std@@@std@@AEBA_K_K@Z; std::vector<uchar>::_Calculate_growth(unsigned __int64)
0x1800080fc  mov     rcx, rax
0x1800080ff  mov     r12, rax
0x180008102  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180008107  mov     rbx, rbp
0x18000810a  mov     [rsp+88h+var_68], r14
0x18000810f  sub     rbx, rsi
0x180008112  mov     [rsp+88h+var_58], r12
0x180008117  mov     r8, rbx; Size
0x18000811a  xor     edx, edx; Val
0x18000811c  lea     rdi, [rsi+rax]
0x180008120  mov     r15, rax
0x180008123  mov     rcx, rdi; void *
0x180008126  mov     [rsp+88h+var_50], rdi
0x18000812b  call    memset_0
0x180008130  mov     r8, [r14+8]
0x180008134  lea     rcx, [rbx+rdi]
0x180008138  sub     r8, [r14]; Size
0x18000813b  mov     rdx, [r14]; Src
0x18000813e  mov     [rsp+88h+var_48], rcx
0x180008143  mov     rcx, r15; void *
0x180008146  call    memmove_0
0x18000814b  mov     rcx, [r14]
0x18000814e  mov     [rsp+88h+var_60], 0
0x180008157  test    rcx, rcx
0x18000815a  jz      short loc_180008168
0x18000815c  mov     rdx, [r14+10h]
0x180008160  sub     rdx, rcx
0x180008163  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180008168  mov     [r14], r15
0x18000816b  lea     rax, [r15+rbp]
0x18000816f  mov     [r14+8], rax
0x180008173  lea     rcx, [rsp+88h+var_68]
0x180008178  lea     rax, [r15+r12]
0x18000817c  mov     [r14+10h], rax
0x180008180  call    ??1_Reallocation_guard@?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::_Reallocation_guard::~_Reallocation_guard(void)
0x180008185  add     rsp, 50h
0x180008189  pop     r15
0x18000818b  pop     r14
0x18000818d  pop     r12
0x18000818f  pop     rdi
0x180008190  pop     rsi
0x180008191  pop     rbp
0x180008192  pop     rbx
0x180008193  retn
0x180008194  call    ?_Xlength@?$vector@GV?$allocator@G@std@@@std@@CAXXZ; std::vector<ushort>::_Xlength(void)
```
