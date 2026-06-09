# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)

- ea: `0x18000593c`
- end: `0x1800059f3`
- name: `??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, const void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x1800028b4`
- `0x18000297c`
- `0x180002bd8`
- `0x180002db0`
- `0x180002f78`
- `0x180003128`

## callees

- `0x18000593c`
- `0x180007818`
- `0x180007928`
- `0x180015870`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,wchar_t const *>(__int64 a1, const void *a2, unsigned __int64 a3)
{
  __int64 v5; // rdx
  _QWORD *v6; // rsi
  __int64 v7; // rbx
  __int64 result; // rax
  _QWORD *v9; // rax
  unsigned __int64 v10; // rcx
  _QWORD *v11; // rdi
  size_t v12; // rbx
  unsigned __int64 v13[5]; // [rsp+20h] [rbp-28h] BYREF

  v5 = 0x7FFFFFFFFFFFFFFELL;
  v6 = (_QWORD *)a1;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 > 7 )
  {
    if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      a1 = 10;
      v5 = a3 | 7;
      if ( (a3 | 7) < 0xA )
        v5 = 10;
    }
    v13[0] = v5;
    v9 = std::wstring::_Allocate_for_capacity<0>(a1, v13);
    v10 = v13[0];
    v6[2] = a3;
    v11 = v9;
    v6[3] = v10;
    v12 = 2 * a3;
    *v6 = v9;
    memmove(v9, a2, v12);
    result = 0;
    *(_WORD *)((char *)v11 + v12) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 16) = a3;
    v7 = 2 * a3;
    *(_QWORD *)(a1 + 24) = 7;
    memmove((void *)a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)v6 + v7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000593c  mov     [rsp+arg_18], rbx
0x180005941  push    rbp
0x180005942  push    rsi
0x180005943  push    rdi
0x180005944  sub     rsp, 30h
0x180005948  mov     rbp, rdx
0x18000594b  mov     rbx, r8
0x18000594e  mov     rdx, 7FFFFFFFFFFFFFFEh
0x180005958  mov     rsi, rcx
0x18000595b  cmp     r8, rdx
0x18000595e  ja      loc_1800059ED
0x180005964  cmp     rbx, 7
0x180005968  ja      short loc_18000598C
0x18000596a  mov     [rcx+10h], rbx
0x18000596e  mov     rdx, rbp; Src
0x180005971  add     rbx, rbx
0x180005974  mov     qword ptr [rcx+18h], 7
0x18000597c  mov     r8, rbx; Size
0x18000597f  call    memmove
0x180005984  xor     eax, eax
0x180005986  mov     [rbx+rsi], ax
0x18000598a  jmp     short loc_1800059E0
0x18000598c  mov     rax, rbx
0x18000598f  or      rax, 7
0x180005993  cmp     rax, rdx
0x180005996  ja      short loc_1800059A7
0x180005998  mov     ecx, 0Ah
0x18000599d  mov     rdx, rax
0x1800059a0  cmp     rax, rcx
0x1800059a3  cmovb   rdx, rcx
0x1800059a7  mov     [rsp+48h+var_28], rdx
0x1800059ac  lea     rdx, [rsp+48h+var_28]
0x1800059b1  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x1800059b6  mov     rcx, [rsp+48h+var_28]
0x1800059bb  mov     rdx, rbp; Src
0x1800059be  mov     [rsi+10h], rbx
0x1800059c2  mov     rdi, rax
0x1800059c5  mov     [rsi+18h], rcx
0x1800059c9  add     rbx, rbx
0x1800059cc  mov     rcx, rax; void *
0x1800059cf  mov     [rsi], rax
0x1800059d2  mov     r8, rbx; Size
0x1800059d5  call    memmove
0x1800059da  xor     eax, eax
0x1800059dc  mov     [rbx+rdi], ax
0x1800059e0  mov     rbx, [rsp+48h+arg_18]
0x1800059e5  add     rsp, 30h
0x1800059e9  pop     rdi
0x1800059ea  pop     rsi
0x1800059eb  pop     rbp
0x1800059ec  retn
0x1800059ed  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
