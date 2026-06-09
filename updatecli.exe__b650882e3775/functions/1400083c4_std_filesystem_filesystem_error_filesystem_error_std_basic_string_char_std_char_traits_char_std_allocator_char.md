# std::filesystem::filesystem_error::filesystem_error(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::filesystem::path const &,std::error_code)

- ea: `0x1400083c4`
- end: `0x14000849c`
- name: `??0filesystem_error@filesystem@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBVpath@12@Verror_code@2@@Z`
- size: `216`
- prototype: `__int64 __fastcall(__int64, __int64, const struct std::filesystem::path *, __int128 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000a200`

## callees

- `0x140002130`
- `0x140008038`
- `0x1400083c4`
- `0x1400084a4`
- `0x1400087c4`
- `0x140009dcc`

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
0x1400083c4  push    rbp
0x1400083c6  push    rbx
0x1400083c7  push    rdi
0x1400083c8  mov     rbp, rsp
0x1400083cb  sub     rsp, 70h
0x1400083cf  mov     rax, cs:__security_cookie
0x1400083d6  xor     rax, rsp
0x1400083d9  mov     [rbp+var_10], rax
0x1400083dd  mov     rdi, r8
0x1400083e0  mov     rbx, rcx
0x1400083e3  mov     [rbp+var_40], rcx
0x1400083e7  movaps  xmm0, xmmword ptr [r9]
0x1400083eb  movdqa  [rbp+var_50], xmm0
0x1400083f0  mov     r8, rdx
0x1400083f3  lea     rdx, [rbp+var_50]
0x1400083f7  call    ??0_System_error@std@@IEAA@Verror_code@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_System_error::_System_error(std::error_code,std::string const &)
0x1400083fc  nop
0x1400083fd  lea     rax, ??_7filesystem_error@filesystem@std@@6B@; const std::filesystem::filesystem_error::`vftable'
0x140008404  mov     [rbx], rax
0x140008407  lea     rcx, [rbx+28h]; this
0x14000840b  mov     rdx, rdi; struct std::filesystem::path *
0x14000840e  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x140008413  nop
0x140008414  xorps   xmm0, xmm0
0x140008417  movups  xmmword ptr [rbx+48h], xmm0
0x14000841b  xor     edx, edx
0x14000841d  mov     [rbx+58h], rdx
0x140008421  mov     qword ptr [rbx+60h], 7
0x140008429  mov     [rbx+48h], dx
0x14000842d  movups  [rbp+var_30], xmm0
0x140008431  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140008439  movdqu  [rbp+var_20], xmm1
0x14000843e  mov     word ptr [rbp+var_30], dx
0x140008442  lea     rax, aUnknownExcepti; "Unknown exception"
0x140008449  cmp     [rbx+8], rdx
0x14000844d  cmovnz  rax, [rbx+8]
0x140008452  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140008456  inc     rcx
0x140008459  cmp     [rax+rcx], dl
0x14000845c  jnz     short loc_140008456
0x14000845e  mov     qword ptr [rbp+var_50], rax
0x140008462  mov     qword ptr [rbp+var_50+8], rcx
0x140008466  lea     rcx, [rbx+68h]; Src
0x14000846a  lea     r9, [rbp+var_30]
0x14000846e  mov     r8, rdi
0x140008471  lea     rdx, [rbp+var_50]
0x140008475  call    ?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z; std::filesystem::filesystem_error::_Pretty_message(std::string_view,std::filesystem::path const &,std::filesystem::path const &)
0x14000847a  nop
0x14000847b  lea     rcx, [rbp+var_30]
0x14000847f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140008484  nop
0x140008485  mov     rax, rbx
0x140008488  mov     rcx, [rbp+var_10]
0x14000848c  xor     rcx, rsp; StackCookie
0x14000848f  call    __security_check_cookie
0x140008494  add     rsp, 70h
0x140008498  pop     rdi
0x140008499  pop     rbx
0x14000849a  pop     rbp
0x14000849b  retn
```
