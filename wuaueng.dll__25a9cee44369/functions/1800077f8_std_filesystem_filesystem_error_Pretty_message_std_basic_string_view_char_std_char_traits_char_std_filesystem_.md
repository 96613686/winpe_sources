# std::filesystem::filesystem_error::_Pretty_message(std::basic_string_view<char,std::char_traits<char>>,std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x1800077f8`
- end: `0x180007ae2`
- name: `?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z`
- size: `746`
- prototype: `_QWORD *__fastcall(_QWORD *Src, __int64, const char **, const char **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180007ae8`

## callees

- `0x180007280`
- `0x1800073dc`
- `0x1800074f0`
- `0x180007574`
- `0x1800076c4`
- `0x1800077f8`
- `0x180007ee8`
- `0x18000fb56`
- `0x18000fc90`
- `0x180010084`
- `0x180015df0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800079d8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800079d8`

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
0x1800077f8  mov     [rsp-8+arg_10], rbx
0x1800077fd  push    rbp
0x1800077fe  push    rsi
0x1800077ff  push    rdi
0x180007800  push    r12
0x180007802  push    r13
0x180007804  push    r14
0x180007806  push    r15
0x180007808  lea     rbp, [rsp-27h]
0x18000780d  sub     rsp, 0A0h
0x180007814  mov     rax, cs:__security_cookie
0x18000781b  xor     rax, rsp
0x18000781e  mov     [rbp+57h+var_40], rax
0x180007822  mov     rbx, r9
0x180007825  mov     rsi, r8
0x180007828  mov     r15, rdx
0x18000782b  mov     rdi, rcx
0x18000782e  mov     [rbp+57h+var_88], rcx
0x180007832  xor     r13d, r13d
0x180007835  mov     [rbp+57h+var_90], r13d
0x180007839  xorps   xmm0, xmm0
0x18000783c  movups  xmmword ptr [rcx], xmm0
0x18000783f  mov     [rcx+10h], r13
0x180007843  lea     r12d, [r13+0Fh]
0x180007847  mov     [rcx+18h], r12
0x18000784b  mov     [rcx], r13b
0x18000784e  mov     [rbp+57h+var_90], 1
0x180007855  call    ___lc_codepage_func
0x18000785a  mov     r14d, 0FDE9h
0x180007860  cmp     eax, r14d
0x180007863  cmovnz  r14d, r13d
0x180007867  mov     rax, rsi
0x18000786a  cmp     qword ptr [rsi+18h], 7
0x18000786f  jbe     short loc_180007874
0x180007871  mov     rax, [rsi]
0x180007874  mov     [rbp+57h+var_A0], rax
0x180007878  mov     rax, [rsi+10h]
0x18000787c  mov     [rbp+57h+var_98], rax
0x180007880  lea     r8, [rbp+57h+var_A0]
0x180007884  mov     edx, r14d; CodePage
0x180007887  lea     rcx, [rbp+57h+Src]; Src
0x18000788b  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::wstring_view,std::allocator<char> const &)
0x180007890  nop
0x180007891  mov     rax, rbx
0x180007894  cmp     qword ptr [rbx+18h], 7
0x180007899  jbe     short loc_18000789E
0x18000789b  mov     rax, [rbx]
0x18000789e  mov     [rbp+57h+var_A0], rax
0x1800078a2  mov     rax, [rbx+10h]
0x1800078a6  mov     [rbp+57h+var_98], rax
0x1800078aa  lea     r8, [rbp+57h+var_A0]
0x1800078ae  mov     edx, r14d; CodePage
0x1800078b1  lea     rcx, [rbp+57h+var_80]; Src
0x1800078b5  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::wstring_view,std::allocator<char> const &)
0x1800078ba  nop
0x1800078bb  mov     rax, [rbp+57h+var_70]
0x1800078bf  neg     rax
0x1800078c2  sbb     rcx, rcx
0x1800078c5  and     ecx, 4
0x1800078c8  lea     rax, [rcx+4]
0x1800078cc  add     rax, [r15+8]
0x1800078d0  add     rax, [rbp+57h+Size]
0x1800078d4  add     rax, [rbp+57h+var_70]
0x1800078d8  mov     rsi, [rdi+10h]
0x1800078dc  cmp     rsi, rax
0x1800078df  ja      short loc_180007952
0x1800078e1  cmp     [rdi+18h], rax
0x1800078e5  jz      short loc_180007952
0x1800078e7  jnb     short loc_1800078FD
0x1800078e9  sub     rax, rsi
0x1800078ec  mov     rdx, rax
0x1800078ef  mov     rcx, rdi; Src
0x1800078f2  call    ??$_Reallocate_grow_by@V_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@@Z; std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(unsigned __int64,_lambda_9013ee9e23efe4882b67eff5b0ecf103_)
0x1800078f7  mov     [rdi+10h], rsi
0x1800078fb  jmp     short loc_180007952
0x1800078fd  cmp     rax, r12
0x180007900  ja      short loc_180007952
0x180007902  cmp     [rdi+18h], r12
0x180007906  jbe     short loc_180007952
0x180007908  mov     rbx, [rdi]
0x18000790b  lea     r8, [rsi+1]; Size
0x18000790f  mov     rdx, rbx; Src
0x180007912  mov     rcx, rdi; void *
0x180007915  call    memmove
0x18000791a  mov     rdx, [rdi+18h]
0x18000791e  inc     rdx
0x180007921  cmp     rdx, 1000h
0x180007928  jb      short loc_180007946
0x18000792a  add     rdx, 27h ; '''; struct std::nothrow_t *
0x18000792e  mov     rax, [rbx-8]
0x180007932  sub     rbx, rax
0x180007935  sub     rbx, 8
0x180007939  cmp     rbx, 1Fh
0x18000793d  ja      loc_1800079C9
0x180007943  mov     rbx, rax
0x180007946  mov     rcx, rbx; void *
0x180007949  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000794e  mov     [rdi+18h], r12
0x180007952  mov     rdx, r15
0x180007955  mov     rcx, rdi
0x180007958  call    ??$?YV?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@@Z; std::string::operator+=<std::string_view,0>(std::string_view const &)
0x18000795d  lea     rax, asc_180019068; ": \""
0x180007964  mov     [rbp+57h+var_A0], rax
0x180007968  mov     [rbp+57h+var_98], 3
0x180007970  lea     rdx, [rbp+57h+var_A0]
0x180007974  mov     rcx, rdi
0x180007977  call    ??$?YV?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@@Z; std::string::operator+=<std::string_view,0>(std::string_view const &)
0x18000797c  mov     rsi, [rbp+57h+Size]
0x180007980  lea     r9, [rbp+57h+Src]
0x180007984  cmp     [rbp+57h+var_48], r12
0x180007988  cmova   r9, [rbp+57h+Src]
0x18000798d  mov     rcx, [rdi+10h]
0x180007991  mov     rax, [rdi+18h]
0x180007995  sub     rax, rcx
0x180007998  cmp     rsi, rax
0x18000799b  ja      short loc_1800079DF
0x18000799d  lea     rax, [rcx+rsi]
0x1800079a1  mov     [rdi+10h], rax
0x1800079a5  mov     rax, rdi
0x1800079a8  cmp     [rdi+18h], r12
0x1800079ac  jbe     short loc_1800079B1
0x1800079ae  mov     rax, [rdi]
0x1800079b1  lea     rbx, [rax+rcx]
0x1800079b5  mov     r8, rsi; Size
0x1800079b8  mov     rdx, r9; Src
0x1800079bb  mov     rcx, rbx; void *
0x1800079be  call    memmove
0x1800079c3  mov     [rbx+rsi], r13b
0x1800079c7  jmp     short loc_1800079EF
0x1800079c9  mov     [rsp+0D0h+Reserved], r13; Reserved
0x1800079ce  xor     r9d, r9d; LineNo
0x1800079d1  xor     r8d, r8d; FileName
0x1800079d4  xor     edx, edx; FunctionName
0x1800079d6  xor     ecx, ecx; Expression
0x1800079d8  call    cs:__imp__invoke_watson
0x1800079df  mov     [rsp+0D0h+Reserved], rsi; Size
0x1800079e4  mov     rdx, rsi
0x1800079e7  mov     rcx, rdi; Src
0x1800079ea  call    ??$_Reallocate_grow_by@V_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(unsigned __int64,_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64)
0x1800079ef  cmp     [rbp+57h+var_70], r13
0x1800079f3  jz      short loc_180007A72
0x1800079f5  lea     rax, asc_18001906C; "\", \""
0x1800079fc  mov     [rbp+57h+var_A0], rax
0x180007a00  mov     [rbp+57h+var_98], 4
0x180007a08  lea     rdx, [rbp+57h+var_A0]
0x180007a0c  mov     rcx, rdi
0x180007a0f  call    ??$?YV?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@@Z; std::string::operator+=<std::string_view,0>(std::string_view const &)
0x180007a14  mov     rbx, [rbp+57h+var_70]
0x180007a18  lea     r9, [rbp+57h+var_80]
0x180007a1c  cmp     [rbp+57h+var_68], r12
0x180007a20  cmova   r9, [rbp+57h+var_80]
0x180007a25  mov     r14, [rdi+10h]
0x180007a29  mov     rax, [rdi+18h]
0x180007a2d  sub     rax, r14
0x180007a30  cmp     rbx, rax
0x180007a33  ja      short loc_180007A62
0x180007a35  lea     rax, [rbx+r14]
0x180007a39  mov     [rdi+10h], rax
0x180007a3d  mov     rsi, rdi
0x180007a40  cmp     [rdi+18h], r12
0x180007a44  jbe     short loc_180007A49
0x180007a46  mov     rsi, [rdi]
0x180007a49  lea     rcx, [rsi+r14]; void *
0x180007a4d  mov     r8, rbx; Size
0x180007a50  mov     rdx, r9; Src
0x180007a53  call    memmove
0x180007a58  lea     rax, [rsi+rbx]
0x180007a5c  mov     [rax+r14], r13b
0x180007a60  jmp     short loc_180007A72
0x180007a62  mov     [rsp+0D0h+Reserved], rbx; Size
0x180007a67  mov     rdx, rbx
0x180007a6a  mov     rcx, rdi; Src
0x180007a6d  call    ??$_Reallocate_grow_by@V_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(unsigned __int64,_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64)
0x180007a72  mov     rcx, [rdi+10h]
0x180007a76  cmp     rcx, [rdi+18h]
0x180007a7a  jnb     short loc_180007A98
0x180007a7c  lea     rax, [rcx+1]
0x180007a80  mov     [rdi+10h], rax
0x180007a84  mov     rax, rdi
0x180007a87  cmp     [rdi+18h], r12
0x180007a8b  jbe     short loc_180007A90
0x180007a8d  mov     rax, [rdi]
0x180007a90  mov     word ptr [rax+rcx], 22h ; '"'
0x180007a96  jmp     short loc_180007AA4
0x180007a98  mov     r9b, 22h ; '"'
0x180007a9b  mov     rcx, rdi; Src
0x180007a9e  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x180007aa3  nop
0x180007aa4  lea     rcx, [rbp+57h+var_80]
0x180007aa8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180007aad  nop
0x180007aae  lea     rcx, [rbp+57h+Src]
0x180007ab2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180007ab7  mov     rax, rdi
0x180007aba  mov     rcx, [rbp+57h+var_40]
0x180007abe  xor     rcx, rsp; StackCookie
0x180007ac1  call    __security_check_cookie
0x180007ac6  mov     rbx, [rsp+0D0h+arg_10]
0x180007ace  add     rsp, 0A0h
0x180007ad5  pop     r15
0x180007ad7  pop     r14
0x180007ad9  pop     r13
0x180007adb  pop     r12
0x180007add  pop     rdi
0x180007ade  pop     rsi
0x180007adf  pop     rbp
0x180007ae0  retn
```
