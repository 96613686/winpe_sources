# std::filesystem::filesystem_error::filesystem_error(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::filesystem::path const &,std::error_code)

- ea: `0x18000642c`
- end: `0x1800064fa`
- name: `??0filesystem_error@filesystem@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBVpath@12@Verror_code@2@@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006948`

## callees

- `0x18000576c`
- `0x180006358`
- `0x18000642c`
- `0x180006518`
- `0x1800085e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::filesystem::filesystem_error::filesystem_error(
        __int64 a1,
        __int64 a2,
        const struct std::filesystem::path *a3,
        __int128 *a4)
{
  const char *v6; // rcx
  __int64 v7; // rax
  __int128 v9; // [rsp+20h] [rbp-30h] BYREF
  _OWORD v10[2]; // [rsp+30h] [rbp-20h] BYREF

  v9 = *a4;
  std::_System_error::_System_error(a1, &v9, a2);
  *(_QWORD *)a1 = &std::filesystem::filesystem_error::`vftable';
  std::filesystem::path::path((std::filesystem::path *)(a1 + 40), a3);
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 7;
  *(_WORD *)(a1 + 72) = 0;
  v10[0] = 0;
  v10[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v10[0]) = 0;
  v6 = "Unknown exception";
  if ( *(_QWORD *)(a1 + 8) )
    v6 = *(const char **)(a1 + 8);
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  *(_QWORD *)&v9 = v6;
  *((_QWORD *)&v9 + 1) = v7;
  std::filesystem::filesystem_error::_Pretty_message(
    (_QWORD *)(a1 + 104),
    (__int64)&v9,
    (const char **)a3,
    (const char **)v10);
  std::wstring::~wstring(v10);
  return a1;
}

```

## disassembly

```asm
0x18000642c  mov     [rsp-8+arg_8], rbx
0x180006431  mov     [rsp-8+arg_10], rdi
0x180006436  mov     [rsp-8+arg_0], rcx
0x18000643b  push    rbp
0x18000643c  mov     rbp, rsp
0x18000643f  sub     rsp, 50h
0x180006443  mov     rdi, r8
0x180006446  mov     rbx, rcx
0x180006449  movaps  xmm0, xmmword ptr [r9]
0x18000644d  movdqa  [rbp+var_30], xmm0
0x180006452  mov     r8, rdx
0x180006455  lea     rdx, [rbp+var_30]
0x180006459  call    ??0_System_error@std@@IEAA@Verror_code@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_System_error::_System_error(std::error_code,std::string const &)
0x18000645e  nop
0x18000645f  lea     rax, ??_7filesystem_error@filesystem@std@@6B@; const std::filesystem::filesystem_error::`vftable'
0x180006466  mov     [rbx], rax
0x180006469  lea     rcx, [rbx+28h]; this
0x18000646d  mov     rdx, rdi; struct std::filesystem::path *
0x180006470  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180006475  nop
0x180006476  xorps   xmm0, xmm0
0x180006479  movups  xmmword ptr [rbx+48h], xmm0
0x18000647d  xor     edx, edx
0x18000647f  mov     [rbx+58h], rdx
0x180006483  mov     qword ptr [rbx+60h], 7
0x18000648b  mov     [rbx+48h], dx
0x18000648f  movups  [rbp+var_20], xmm0
0x180006493  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000649b  movdqu  [rbp+var_10], xmm1
0x1800064a0  mov     word ptr [rbp+var_20], dx
0x1800064a4  lea     rcx, aUnknownExcepti; "Unknown exception"
0x1800064ab  cmp     [rbx+8], rdx
0x1800064af  cmovnz  rcx, [rbx+8]
0x1800064b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800064b8  inc     rax
0x1800064bb  cmp     [rcx+rax], dl
0x1800064be  jnz     short loc_1800064B8
0x1800064c0  mov     qword ptr [rbp+var_30], rcx
0x1800064c4  mov     qword ptr [rbp+var_30+8], rax
0x1800064c8  lea     rcx, [rbx+68h]; Src
0x1800064cc  lea     r9, [rbp+var_20]
0x1800064d0  mov     r8, rdi
0x1800064d3  lea     rdx, [rbp+var_30]
0x1800064d7  call    ?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z; std::filesystem::filesystem_error::_Pretty_message(std::string_view,std::filesystem::path const &,std::filesystem::path const &)
0x1800064dc  nop
0x1800064dd  lea     rcx, [rbp+var_20]
0x1800064e1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800064e6  nop
0x1800064e7  mov     rax, rbx
0x1800064ea  mov     rbx, [rsp+50h+arg_8]
0x1800064ef  mov     rdi, [rsp+50h+arg_10]
0x1800064f4  add     rsp, 50h
0x1800064f8  pop     rbp
0x1800064f9  retn
```
