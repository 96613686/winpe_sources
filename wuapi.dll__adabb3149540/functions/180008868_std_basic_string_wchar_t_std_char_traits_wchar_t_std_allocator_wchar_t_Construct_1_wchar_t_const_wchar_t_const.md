# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)

- ea: `0x180008868`
- end: `0x18000891f`
- name: `??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z`
- size: `183`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180006a74`
- `0x180006b3c`
- `0x180006d98`
- `0x180006f90`
- `0x180007158`
- `0x180007308`

## callees

- `0x1800055d4`
- `0x180008868`
- `0x180008fd0`
- `0x180015e40`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,wchar_t const *>(__int64 a1, const void *a2, unsigned __int64 a3)
{
  __int64 v5; // rdx
  _QWORD *v6; // rsi
  __int64 v7; // rbx
  __int64 result; // rax
  char *v9; // rax
  __int64 v10; // rcx
  char *v11; // rdi
  size_t v12; // rbx
  __int64 v13[5]; // [rsp+20h] [rbp-28h] BYREF

  v5 = 0x7FFFFFFFFFFFFFFELL;
  v6 = (_QWORD *)a1;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string((const char *)a1);
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
    v9 = (char *)std::wstring::_Allocate_for_capacity<0>(a1, v13);
    v10 = v13[0];
    v6[2] = a3;
    v11 = v9;
    v6[3] = v10;
    v12 = 2 * a3;
    *v6 = v9;
    memmove(v9, a2, v12);
    result = 0;
    *(_WORD *)&v11[v12] = 0;
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
0x180008868  mov     [rsp+arg_18], rbx
0x18000886d  push    rbp
0x18000886e  push    rsi
0x18000886f  push    rdi
0x180008870  sub     rsp, 30h
0x180008874  mov     rbp, rdx
0x180008877  mov     rbx, r8
0x18000887a  mov     rdx, 7FFFFFFFFFFFFFFEh
0x180008884  mov     rsi, rcx
0x180008887  cmp     r8, rdx
0x18000888a  ja      loc_180008919
0x180008890  cmp     rbx, 7
0x180008894  ja      short loc_1800088B8
0x180008896  mov     [rcx+10h], rbx
0x18000889a  mov     rdx, rbp; Src
0x18000889d  add     rbx, rbx
0x1800088a0  mov     qword ptr [rcx+18h], 7
0x1800088a8  mov     r8, rbx; Size
0x1800088ab  call    memmove
0x1800088b0  xor     eax, eax
0x1800088b2  mov     [rbx+rsi], ax
0x1800088b6  jmp     short loc_18000890C
0x1800088b8  mov     rax, rbx
0x1800088bb  or      rax, 7
0x1800088bf  cmp     rax, rdx
0x1800088c2  ja      short loc_1800088D3
0x1800088c4  mov     ecx, 0Ah
0x1800088c9  mov     rdx, rax
0x1800088cc  cmp     rax, rcx
0x1800088cf  cmovb   rdx, rcx
0x1800088d3  mov     [rsp+48h+var_28], rdx
0x1800088d8  lea     rdx, [rsp+48h+var_28]
0x1800088dd  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x1800088e2  mov     rcx, [rsp+48h+var_28]
0x1800088e7  mov     rdx, rbp; Src
0x1800088ea  mov     [rsi+10h], rbx
0x1800088ee  mov     rdi, rax
0x1800088f1  mov     [rsi+18h], rcx
0x1800088f5  add     rbx, rbx
0x1800088f8  mov     rcx, rax; void *
0x1800088fb  mov     [rsi], rax
0x1800088fe  mov     r8, rbx; Size
0x180008901  call    memmove
0x180008906  xor     eax, eax
0x180008908  mov     [rbx+rdi], ax
0x18000890c  mov     rbx, [rsp+48h+arg_18]
0x180008911  add     rsp, 30h
0x180008915  pop     rdi
0x180008916  pop     rsi
0x180008917  pop     rbp
0x180008918  retn
0x180008919  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
