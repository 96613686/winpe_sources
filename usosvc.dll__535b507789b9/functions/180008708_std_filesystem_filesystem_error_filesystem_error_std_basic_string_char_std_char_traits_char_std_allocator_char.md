# std::filesystem::filesystem_error::filesystem_error(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::filesystem::path const &,std::error_code)

- ea: `0x180008708`
- end: `0x1800087e0`
- name: `??0filesystem_error@filesystem@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBVpath@12@Verror_code@2@@Z`
- size: `216`
- prototype: `__int64 __fastcall(__int64, __int64, const struct std::filesystem::path *, __int128 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a26c`

## callees

- `0x1800026d0`
- `0x18000837c`
- `0x180008708`
- `0x1800087e8`
- `0x180008b08`
- `0x180009e38`

## pseudocode

```c
__int64 __fastcall std::filesystem::filesystem_error::filesystem_error(
        __int64 a1,
        __int64 a2,
        const struct std::filesystem::path *a3,
        __int128 *a4)
{
  const char *v6; // rax
  __int64 v7; // rcx
  __int128 v9; // [rsp+20h] [rbp-50h] BYREF
  __int64 v10; // [rsp+30h] [rbp-40h]
  _OWORD v11[2]; // [rsp+40h] [rbp-30h] BYREF

  v10 = a1;
  v9 = *a4;
  std::_System_error::_System_error(a1, &v9, a2);
  *(_QWORD *)a1 = &std::filesystem::filesystem_error::`vftable';
  std::filesystem::path::path((std::filesystem::path *)(a1 + 40), a3);
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 7;
  *(_WORD *)(a1 + 72) = 0;
  v11[0] = 0;
  v11[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v11[0]) = 0;
  v6 = "Unknown exception";
  if ( *(_QWORD *)(a1 + 8) )
    v6 = *(const char **)(a1 + 8);
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  *(_QWORD *)&v9 = v6;
  *((_QWORD *)&v9 + 1) = v7;
  std::filesystem::filesystem_error::_Pretty_message((void *)(a1 + 104));
  std::wstring::~wstring(v11);
  return a1;
}

```

## disassembly

```asm
0x180008708  push    rbp
0x18000870a  push    rbx
0x18000870b  push    rdi
0x18000870c  mov     rbp, rsp
0x18000870f  sub     rsp, 70h
0x180008713  mov     rax, cs:__security_cookie
0x18000871a  xor     rax, rsp
0x18000871d  mov     [rbp+var_10], rax
0x180008721  mov     rdi, r8
0x180008724  mov     rbx, rcx
0x180008727  mov     [rbp+var_40], rcx
0x18000872b  movaps  xmm0, xmmword ptr [r9]
0x18000872f  movdqa  [rbp+var_50], xmm0
0x180008734  mov     r8, rdx
0x180008737  lea     rdx, [rbp+var_50]
0x18000873b  call    ??0_System_error@std@@IEAA@Verror_code@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_System_error::_System_error(std::error_code,std::string const &)
0x180008740  nop
0x180008741  lea     rax, ??_7filesystem_error@filesystem@std@@6B@; const std::filesystem::filesystem_error::`vftable'
0x180008748  mov     [rbx], rax
0x18000874b  lea     rcx, [rbx+28h]; this
0x18000874f  mov     rdx, rdi; struct std::filesystem::path *
0x180008752  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180008757  nop
0x180008758  xorps   xmm0, xmm0
0x18000875b  movups  xmmword ptr [rbx+48h], xmm0
0x18000875f  xor     edx, edx
0x180008761  mov     [rbx+58h], rdx
0x180008765  mov     qword ptr [rbx+60h], 7
0x18000876d  mov     [rbx+48h], dx
0x180008771  movups  [rbp+var_30], xmm0
0x180008775  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000877d  movdqu  [rbp+var_20], xmm1
0x180008782  mov     word ptr [rbp+var_30], dx
0x180008786  lea     rax, aUnknownExcepti; "Unknown exception"
0x18000878d  cmp     [rbx+8], rdx
0x180008791  cmovnz  rax, [rbx+8]
0x180008796  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000879a  inc     rcx
0x18000879d  cmp     [rax+rcx], dl
0x1800087a0  jnz     short loc_18000879A
0x1800087a2  mov     qword ptr [rbp+var_50], rax
0x1800087a6  mov     qword ptr [rbp+var_50+8], rcx
0x1800087aa  lea     rcx, [rbx+68h]; Src
0x1800087ae  lea     r9, [rbp+var_30]
0x1800087b2  mov     r8, rdi
0x1800087b5  lea     rdx, [rbp+var_50]
0x1800087b9  call    ?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z; std::filesystem::filesystem_error::_Pretty_message(std::string_view,std::filesystem::path const &,std::filesystem::path const &)
0x1800087be  nop
0x1800087bf  lea     rcx, [rbp+var_30]
0x1800087c3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800087c8  nop
0x1800087c9  mov     rax, rbx
0x1800087cc  mov     rcx, [rbp+var_10]
0x1800087d0  xor     rcx, rsp; StackCookie
0x1800087d3  call    __security_check_cookie
0x1800087d8  add     rsp, 70h
0x1800087dc  pop     rdi
0x1800087dd  pop     rbx
0x1800087de  pop     rbp
0x1800087df  retn
```
