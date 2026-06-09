# std::filesystem::filesystem_error::_Pretty_message(std::basic_string_view<char,std::char_traits<char>>,std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x180002358`
- end: `0x180002642`
- name: `?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z`
- size: `746`
- prototype: `_QWORD *__fastcall(_QWORD *Src, __int64, const char **, const char **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18000226c`

## callees

- `0x180002358`
- `0x180004168`
- `0x1800042c4`
- `0x180004d90`
- `0x18000509c`
- `0x1800051d0`
- `0x180007b40`
- `0x18000ec0d`
- `0x18000ed40`
- `0x18000ed64`
- `0x180015870`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002538`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180002538`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::filesystem_error::_Pretty_message(
        _QWORD *Src,
        __int64 a2,
        const char **a3,
        const char **a4)
{
  UINT v8; // r14d
  const char *v9; // rax
  const char *v10; // rax
  size_t v11; // rax
  size_t v12; // rsi
  _QWORD *v13; // rbx
  const struct std::nothrow_t *v14; // rdx
  size_t v15; // rsi
  void **v16; // r9
  __int64 v17; // rcx
  _QWORD *v18; // rax
  char *v19; // rbx
  size_t v20; // rbx
  void **v21; // r9
  __int64 v22; // r14
  _QWORD *v23; // rsi
  unsigned __int64 v24; // rcx
  _QWORD *v25; // rax
  const char *v27; // [rsp+30h] [rbp-49h] BYREF
  __int64 v28; // [rsp+38h] [rbp-41h]
  int v29; // [rsp+40h] [rbp-39h]
  _QWORD *v30; // [rsp+48h] [rbp-31h]
  void *v31[2]; // [rsp+50h] [rbp-29h] BYREF
  size_t v32; // [rsp+60h] [rbp-19h]
  unsigned __int64 v33; // [rsp+68h] [rbp-11h]
  void *Srca[2]; // [rsp+70h] [rbp-9h] BYREF
  size_t Size; // [rsp+80h] [rbp+7h]
  unsigned __int64 v36; // [rsp+88h] [rbp+Fh]

  v30 = Src;
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  v29 = 1;
  v8 = 65001;
  if ( __lc_codepage_func() != 65001 )
    v8 = 0;
  v9 = (const char *)a3;
  if ( (unsigned __int64)a3[3] > 7 )
    v9 = *a3;
  v27 = v9;
  v28 = (__int64)a3[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    Srca,
    v8,
    (__int64)&v27);
  v10 = (const char *)a4;
  if ( (unsigned __int64)a4[3] > 7 )
    v10 = *a4;
  v27 = v10;
  v28 = (__int64)a4[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    v31,
    v8,
    (__int64)&v27);
  v11 = v32 + Size + *(_QWORD *)(a2 + 8) + (v32 != 0 ? 8LL : 4LL);
  v12 = Src[2];
  if ( v12 <= v11 && Src[3] != v11 )
  {
    if ( Src[3] >= v11 )
    {
      if ( v11 <= 0xF && Src[3] > 0xFu )
      {
        v13 = (_QWORD *)*Src;
        memmove(Src, (const void *)*Src, v12 + 1);
        v14 = (const struct std::nothrow_t *)(Src[3] + 1LL);
        if ( (unsigned __int64)v14 >= 0x1000 )
        {
          v14 = (const struct std::nothrow_t *)(Src[3] + 40LL);
          if ( (unsigned __int64)v13 - *(v13 - 1) - 8 > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
          v13 = (_QWORD *)*(v13 - 1);
        }
        operator delete(v13, v14);
        Src[3] = 15;
      }
    }
    else
    {
      std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(Src);
      Src[2] = v12;
    }
  }
  std::string::operator+=<std::string_view,0>(Src, a2);
  v27 = ": \"";
  v28 = 3;
  std::string::operator+=<std::string_view,0>(Src, &v27);
  v15 = Size;
  v16 = Srca;
  if ( v36 > 0xF )
    v16 = (void **)Srca[0];
  v17 = Src[2];
  if ( Size > Src[3] - v17 )
  {
    std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(Src, Size);
  }
  else
  {
    Src[2] = v17 + Size;
    v18 = Src;
    if ( Src[3] > 0xFu )
      v18 = (_QWORD *)*Src;
    v19 = (char *)v18 + v17;
    memmove((char *)v18 + v17, v16, v15);
    v19[v15] = 0;
  }
  if ( v32 )
  {
    v27 = "\", \"";
    v28 = 4;
    std::string::operator+=<std::string_view,0>(Src, &v27);
    v20 = v32;
    v21 = v31;
    if ( v33 > 0xF )
      v21 = (void **)v31[0];
    v22 = Src[2];
    if ( v32 > Src[3] - v22 )
    {
      std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(
        Src,
        v32);
    }
    else
    {
      Src[2] = v32 + v22;
      v23 = Src;
      if ( Src[3] > 0xFu )
        v23 = (_QWORD *)*Src;
      memmove((char *)v23 + v22, v21, v20);
      *((_BYTE *)v23 + v20 + v22) = 0;
    }
  }
  v24 = Src[2];
  if ( v24 >= Src[3] )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src);
  }
  else
  {
    Src[2] = v24 + 1;
    v25 = Src;
    if ( Src[3] > 0xFu )
      v25 = (_QWORD *)*Src;
    *(_WORD *)((char *)v25 + v24) = 34;
  }
  std::string::~string((__int64)v31);
  std::string::~string((__int64)Srca);
  return Src;
}

```

## disassembly

```asm
0x180002358  mov     [rsp-8+arg_10], rbx
0x18000235d  push    rbp
0x18000235e  push    rsi
0x18000235f  push    rdi
0x180002360  push    r12
0x180002362  push    r13
0x180002364  push    r14
0x180002366  push    r15
0x180002368  lea     rbp, [rsp-27h]
0x18000236d  sub     rsp, 0A0h
0x180002374  mov     rax, cs:__security_cookie
0x18000237b  xor     rax, rsp
0x18000237e  mov     [rbp+57h+var_40], rax
0x180002382  mov     rbx, r9
0x180002385  mov     rsi, r8
0x180002388  mov     r15, rdx
0x18000238b  mov     rdi, rcx
0x18000238e  mov     [rbp+57h+var_88], rcx
0x180002392  xor     r13d, r13d
0x180002395  mov     [rbp+57h+var_90], r13d
0x180002399  xorps   xmm0, xmm0
0x18000239c  movups  xmmword ptr [rcx], xmm0
0x18000239f  mov     [rcx+10h], r13
0x1800023a3  lea     r12d, [r13+0Fh]
0x1800023a7  mov     [rcx+18h], r12
0x1800023ab  mov     [rcx], r13b
0x1800023ae  mov     [rbp+57h+var_90], 1
0x1800023b5  call    ___lc_codepage_func
0x1800023ba  mov     r14d, 0FDE9h
0x1800023c0  cmp     eax, r14d
0x1800023c3  cmovnz  r14d, r13d
0x1800023c7  mov     rax, rsi
0x1800023ca  cmp     qword ptr [rsi+18h], 7
0x1800023cf  jbe     short loc_1800023D4
0x1800023d1  mov     rax, [rsi]
0x1800023d4  mov     [rbp+57h+var_A0], rax
0x1800023d8  mov     rax, [rsi+10h]
0x1800023dc  mov     [rbp+57h+var_98], rax
0x1800023e0  lea     r8, [rbp+57h+var_A0]
0x1800023e4  mov     edx, r14d; CodePage
0x1800023e7  lea     rcx, [rbp+57h+Src]; Src
0x1800023eb  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::wstring_view,std::allocator<char> const &)
0x1800023f0  nop
0x1800023f1  mov     rax, rbx
0x1800023f4  cmp     qword ptr [rbx+18h], 7
0x1800023f9  jbe     short loc_1800023FE
0x1800023fb  mov     rax, [rbx]
0x1800023fe  mov     [rbp+57h+var_A0], rax
0x180002402  mov     rax, [rbx+10h]
0x180002406  mov     [rbp+57h+var_98], rax
0x18000240a  lea     r8, [rbp+57h+var_A0]
0x18000240e  mov     edx, r14d; CodePage
0x180002411  lea     rcx, [rbp+57h+var_80]; Src
0x180002415  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::wstring_view,std::allocator<char> const &)
0x18000241a  nop
0x18000241b  mov     rax, [rbp+57h+var_70]
0x18000241f  neg     rax
0x180002422  sbb     rcx, rcx
0x180002425  and     ecx, 4
0x180002428  lea     rax, [rcx+4]
0x18000242c  add     rax, [r15+8]
0x180002430  add     rax, [rbp+57h+Size]
0x180002434  add     rax, [rbp+57h+var_70]
0x180002438  mov     rsi, [rdi+10h]
0x18000243c  cmp     rsi, rax
0x18000243f  ja      short loc_1800024B2
0x180002441  cmp     [rdi+18h], rax
0x180002445  jz      short loc_1800024B2
0x180002447  jnb     short loc_18000245D
0x180002449  sub     rax, rsi
0x18000244c  mov     rdx, rax
0x18000244f  mov     rcx, rdi; Src
0x180002452  call    ??$_Reallocate_grow_by@V_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@@Z; std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(unsigned __int64,_lambda_9013ee9e23efe4882b67eff5b0ecf103_)
0x180002457  mov     [rdi+10h], rsi
0x18000245b  jmp     short loc_1800024B2
0x18000245d  cmp     rax, r12
0x180002460  ja      short loc_1800024B2
0x180002462  cmp     [rdi+18h], r12
0x180002466  jbe     short loc_1800024B2
0x180002468  mov     rbx, [rdi]
0x18000246b  lea     r8, [rsi+1]; Size
0x18000246f  mov     rdx, rbx; Src
0x180002472  mov     rcx, rdi; void *
0x180002475  call    memmove
0x18000247a  mov     rdx, [rdi+18h]
0x18000247e  inc     rdx
0x180002481  cmp     rdx, 1000h
0x180002488  jb      short loc_1800024A6
0x18000248a  add     rdx, 27h ; '''; struct std::nothrow_t *
0x18000248e  mov     rax, [rbx-8]
0x180002492  sub     rbx, rax
0x180002495  sub     rbx, 8
0x180002499  cmp     rbx, 1Fh
0x18000249d  ja      loc_180002529
0x1800024a3  mov     rbx, rax
0x1800024a6  mov     rcx, rbx; void *
0x1800024a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800024ae  mov     [rdi+18h], r12
0x1800024b2  mov     rdx, r15
0x1800024b5  mov     rcx, rdi
0x1800024b8  call    ??$?YV?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@@Z; std::string::operator+=<std::string_view,0>(std::string_view const &)
0x1800024bd  lea     rax, asc_180017B80; ": \""
0x1800024c4  mov     [rbp+57h+var_A0], rax
0x1800024c8  mov     [rbp+57h+var_98], 3
0x1800024d0  lea     rdx, [rbp+57h+var_A0]
0x1800024d4  mov     rcx, rdi
0x1800024d7  call    ??$?YV?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@@Z; std::string::operator+=<std::string_view,0>(std::string_view const &)
0x1800024dc  mov     rsi, [rbp+57h+Size]
0x1800024e0  lea     r9, [rbp+57h+Src]
0x1800024e4  cmp     [rbp+57h+var_48], r12
0x1800024e8  cmova   r9, [rbp+57h+Src]
0x1800024ed  mov     rcx, [rdi+10h]
0x1800024f1  mov     rax, [rdi+18h]
0x1800024f5  sub     rax, rcx
0x1800024f8  cmp     rsi, rax
0x1800024fb  ja      short loc_18000253F
0x1800024fd  lea     rax, [rcx+rsi]
0x180002501  mov     [rdi+10h], rax
0x180002505  mov     rax, rdi
0x180002508  cmp     [rdi+18h], r12
0x18000250c  jbe     short loc_180002511
0x18000250e  mov     rax, [rdi]
0x180002511  lea     rbx, [rax+rcx]
0x180002515  mov     r8, rsi; Size
0x180002518  mov     rdx, r9; Src
0x18000251b  mov     rcx, rbx; void *
0x18000251e  call    memmove
0x180002523  mov     [rbx+rsi], r13b
0x180002527  jmp     short loc_18000254F
0x180002529  mov     [rsp+0D0h+Reserved], r13; Reserved
0x18000252e  xor     r9d, r9d; LineNo
0x180002531  xor     r8d, r8d; FileName
0x180002534  xor     edx, edx; FunctionName
0x180002536  xor     ecx, ecx; Expression
0x180002538  call    cs:__imp__invoke_watson
0x18000253f  mov     [rsp+0D0h+Reserved], rsi; Size
0x180002544  mov     rdx, rsi
0x180002547  mov     rcx, rdi; Src
0x18000254a  call    ??$_Reallocate_grow_by@V_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(unsigned __int64,_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64)
0x18000254f  cmp     [rbp+57h+var_70], r13
0x180002553  jz      short loc_1800025D2
0x180002555  lea     rax, asc_180017B84; "\", \""
0x18000255c  mov     [rbp+57h+var_A0], rax
0x180002560  mov     [rbp+57h+var_98], 4
0x180002568  lea     rdx, [rbp+57h+var_A0]
0x18000256c  mov     rcx, rdi
0x18000256f  call    ??$?YV?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@@Z; std::string::operator+=<std::string_view,0>(std::string_view const &)
0x180002574  mov     rbx, [rbp+57h+var_70]
0x180002578  lea     r9, [rbp+57h+var_80]
0x18000257c  cmp     [rbp+57h+var_68], r12
0x180002580  cmova   r9, [rbp+57h+var_80]
0x180002585  mov     r14, [rdi+10h]
0x180002589  mov     rax, [rdi+18h]
0x18000258d  sub     rax, r14
0x180002590  cmp     rbx, rax
0x180002593  ja      short loc_1800025C2
0x180002595  lea     rax, [rbx+r14]
0x180002599  mov     [rdi+10h], rax
0x18000259d  mov     rsi, rdi
0x1800025a0  cmp     [rdi+18h], r12
0x1800025a4  jbe     short loc_1800025A9
0x1800025a6  mov     rsi, [rdi]
0x1800025a9  lea     rcx, [rsi+r14]; void *
0x1800025ad  mov     r8, rbx; Size
0x1800025b0  mov     rdx, r9; Src
0x1800025b3  call    memmove
0x1800025b8  lea     rax, [rsi+rbx]
0x1800025bc  mov     [rax+r14], r13b
0x1800025c0  jmp     short loc_1800025D2
0x1800025c2  mov     [rsp+0D0h+Reserved], rbx; Size
0x1800025c7  mov     rdx, rbx
0x1800025ca  mov     rcx, rdi; Src
0x1800025cd  call    ??$_Reallocate_grow_by@V_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(unsigned __int64,_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64)
0x1800025d2  mov     rcx, [rdi+10h]
0x1800025d6  cmp     rcx, [rdi+18h]
0x1800025da  jnb     short loc_1800025F8
0x1800025dc  lea     rax, [rcx+1]
0x1800025e0  mov     [rdi+10h], rax
0x1800025e4  mov     rax, rdi
0x1800025e7  cmp     [rdi+18h], r12
0x1800025eb  jbe     short loc_1800025F0
0x1800025ed  mov     rax, [rdi]
0x1800025f0  mov     word ptr [rax+rcx], 22h ; '"'
0x1800025f6  jmp     short loc_180002604
0x1800025f8  mov     r9b, 22h ; '"'
0x1800025fb  mov     rcx, rdi; Src
0x1800025fe  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x180002603  nop
0x180002604  lea     rcx, [rbp+57h+var_80]
0x180002608  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000260d  nop
0x18000260e  lea     rcx, [rbp+57h+Src]
0x180002612  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180002617  mov     rax, rdi
0x18000261a  mov     rcx, [rbp+57h+var_40]
0x18000261e  xor     rcx, rsp; StackCookie
0x180002621  call    __security_check_cookie
0x180002626  mov     rbx, [rsp+0D0h+arg_10]
0x18000262e  add     rsp, 0A0h
0x180002635  pop     r15
0x180002637  pop     r14
0x180002639  pop     r13
0x18000263b  pop     r12
0x18000263d  pop     rdi
0x18000263e  pop     rsi
0x18000263f  pop     rbp
0x180002640  retn
```
