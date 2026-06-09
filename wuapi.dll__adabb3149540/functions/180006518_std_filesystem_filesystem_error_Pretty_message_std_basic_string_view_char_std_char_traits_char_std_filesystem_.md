# std::filesystem::filesystem_error::_Pretty_message(std::basic_string_view<char,std::char_traits<char>>,std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x180006518`
- end: `0x180006802`
- name: `?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z`
- size: `746`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18000642c`

## callees

- `0x180006518`
- `0x1800080d4`
- `0x180008230`
- `0x180008664`
- `0x180008e10`
- `0x1800092e0`
- `0x180009414`
- `0x18000fba6`
- `0x18000fce0`
- `0x1800100d4`
- `0x180015e40`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800066f8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800066f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(Srca, v8);
  v10 = (const char *)a4;
  if ( (unsigned __int64)a4[3] > 7 )
    v10 = *a4;
  v27 = v10;
  v28 = (__int64)a4[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(v31, v8);
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
  std::string::~string(v31);
  std::string::~string(Srca);
  return Src;
}

```

## disassembly

```asm
0x180006518  mov     [rsp-8+arg_10], rbx
0x18000651d  push    rbp
0x18000651e  push    rsi
0x18000651f  push    rdi
0x180006520  push    r12
0x180006522  push    r13
0x180006524  push    r14
0x180006526  push    r15
0x180006528  lea     rbp, [rsp-27h]
0x18000652d  sub     rsp, 0A0h
0x180006534  mov     rax, cs:__security_cookie
0x18000653b  xor     rax, rsp
0x18000653e  mov     [rbp+57h+var_40], rax
0x180006542  mov     rbx, r9
0x180006545  mov     rsi, r8
0x180006548  mov     r15, rdx
0x18000654b  mov     rdi, rcx
0x18000654e  mov     [rbp+57h+var_88], rcx
0x180006552  xor     r13d, r13d
0x180006555  mov     [rbp+57h+var_90], r13d
0x180006559  xorps   xmm0, xmm0
0x18000655c  movups  xmmword ptr [rcx], xmm0
0x18000655f  mov     [rcx+10h], r13
0x180006563  lea     r12d, [r13+0Fh]
0x180006567  mov     [rcx+18h], r12
0x18000656b  mov     [rcx], r13b
0x18000656e  mov     [rbp+57h+var_90], 1
0x180006575  call    ___lc_codepage_func
0x18000657a  mov     r14d, 0FDE9h
0x180006580  cmp     eax, r14d
0x180006583  cmovnz  r14d, r13d
0x180006587  mov     rax, rsi
0x18000658a  cmp     qword ptr [rsi+18h], 7
0x18000658f  jbe     short loc_180006594
0x180006591  mov     rax, [rsi]
0x180006594  mov     [rbp+57h+var_A0], rax
0x180006598  mov     rax, [rsi+10h]
0x18000659c  mov     [rbp+57h+var_98], rax
0x1800065a0  lea     r8, [rbp+57h+var_A0]
0x1800065a4  mov     edx, r14d; CodePage
0x1800065a7  lea     rcx, [rbp+57h+Src]; Src
0x1800065ab  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::wstring_view,std::allocator<char> const &)
0x1800065b0  nop
0x1800065b1  mov     rax, rbx
0x1800065b4  cmp     qword ptr [rbx+18h], 7
0x1800065b9  jbe     short loc_1800065BE
0x1800065bb  mov     rax, [rbx]
0x1800065be  mov     [rbp+57h+var_A0], rax
0x1800065c2  mov     rax, [rbx+10h]
0x1800065c6  mov     [rbp+57h+var_98], rax
0x1800065ca  lea     r8, [rbp+57h+var_A0]
0x1800065ce  mov     edx, r14d; CodePage
0x1800065d1  lea     rcx, [rbp+57h+var_80]; Src
0x1800065d5  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::wstring_view,std::allocator<char> const &)
0x1800065da  nop
0x1800065db  mov     rax, [rbp+57h+var_70]
0x1800065df  neg     rax
0x1800065e2  sbb     rcx, rcx
0x1800065e5  and     ecx, 4
0x1800065e8  lea     rax, [rcx+4]
0x1800065ec  add     rax, [r15+8]
0x1800065f0  add     rax, [rbp+57h+Size]
0x1800065f4  add     rax, [rbp+57h+var_70]
0x1800065f8  mov     rsi, [rdi+10h]
0x1800065fc  cmp     rsi, rax
0x1800065ff  ja      short loc_180006672
0x180006601  cmp     [rdi+18h], rax
0x180006605  jz      short loc_180006672
0x180006607  jnb     short loc_18000661D
0x180006609  sub     rax, rsi
0x18000660c  mov     rdx, rax
0x18000660f  mov     rcx, rdi; Src
0x180006612  call    ??$_Reallocate_grow_by@V_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@@Z; std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(unsigned __int64,_lambda_9013ee9e23efe4882b67eff5b0ecf103_)
0x180006617  mov     [rdi+10h], rsi
0x18000661b  jmp     short loc_180006672
0x18000661d  cmp     rax, r12
0x180006620  ja      short loc_180006672
0x180006622  cmp     [rdi+18h], r12
0x180006626  jbe     short loc_180006672
0x180006628  mov     rbx, [rdi]
0x18000662b  lea     r8, [rsi+1]; Size
0x18000662f  mov     rdx, rbx; Src
0x180006632  mov     rcx, rdi; void *
0x180006635  call    memmove
0x18000663a  mov     rdx, [rdi+18h]
0x18000663e  inc     rdx
0x180006641  cmp     rdx, 1000h
0x180006648  jb      short loc_180006666
0x18000664a  add     rdx, 27h ; '''; struct std::nothrow_t *
0x18000664e  mov     rax, [rbx-8]
0x180006652  sub     rbx, rax
0x180006655  sub     rbx, 8
0x180006659  cmp     rbx, 1Fh
0x18000665d  ja      loc_1800066E9
0x180006663  mov     rbx, rax
0x180006666  mov     rcx, rbx; void *
0x180006669  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000666e  mov     [rdi+18h], r12
0x180006672  mov     rdx, r15
0x180006675  mov     rcx, rdi
0x180006678  call    ??$?YV?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@@Z; std::string::operator+=<std::string_view,0>(std::string_view const &)
0x18000667d  lea     rax, asc_180018E88; ": \""
0x180006684  mov     [rbp+57h+var_A0], rax
0x180006688  mov     [rbp+57h+var_98], 3
0x180006690  lea     rdx, [rbp+57h+var_A0]
0x180006694  mov     rcx, rdi
0x180006697  call    ??$?YV?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@@Z; std::string::operator+=<std::string_view,0>(std::string_view const &)
0x18000669c  mov     rsi, [rbp+57h+Size]
0x1800066a0  lea     r9, [rbp+57h+Src]
0x1800066a4  cmp     [rbp+57h+var_48], r12
0x1800066a8  cmova   r9, [rbp+57h+Src]
0x1800066ad  mov     rcx, [rdi+10h]
0x1800066b1  mov     rax, [rdi+18h]
0x1800066b5  sub     rax, rcx
0x1800066b8  cmp     rsi, rax
0x1800066bb  ja      short loc_1800066FF
0x1800066bd  lea     rax, [rcx+rsi]
0x1800066c1  mov     [rdi+10h], rax
0x1800066c5  mov     rax, rdi
0x1800066c8  cmp     [rdi+18h], r12
0x1800066cc  jbe     short loc_1800066D1
0x1800066ce  mov     rax, [rdi]
0x1800066d1  lea     rbx, [rax+rcx]
0x1800066d5  mov     r8, rsi; Size
0x1800066d8  mov     rdx, r9; Src
0x1800066db  mov     rcx, rbx; void *
0x1800066de  call    memmove
0x1800066e3  mov     [rbx+rsi], r13b
0x1800066e7  jmp     short loc_18000670F
0x1800066e9  mov     [rsp+0D0h+Reserved], r13; Reserved
0x1800066ee  xor     r9d, r9d; LineNo
0x1800066f1  xor     r8d, r8d; FileName
0x1800066f4  xor     edx, edx; FunctionName
0x1800066f6  xor     ecx, ecx; Expression
0x1800066f8  call    cs:__imp__invoke_watson
0x1800066ff  mov     [rsp+0D0h+Reserved], rsi; Size
0x180006704  mov     rdx, rsi
0x180006707  mov     rcx, rdi; Src
0x18000670a  call    ??$_Reallocate_grow_by@V_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(unsigned __int64,_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64)
0x18000670f  cmp     [rbp+57h+var_70], r13
0x180006713  jz      short loc_180006792
0x180006715  lea     rax, asc_180018E8C; "\", \""
0x18000671c  mov     [rbp+57h+var_A0], rax
0x180006720  mov     [rbp+57h+var_98], 4
0x180006728  lea     rdx, [rbp+57h+var_A0]
0x18000672c  mov     rcx, rdi
0x18000672f  call    ??$?YV?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@@Z; std::string::operator+=<std::string_view,0>(std::string_view const &)
0x180006734  mov     rbx, [rbp+57h+var_70]
0x180006738  lea     r9, [rbp+57h+var_80]
0x18000673c  cmp     [rbp+57h+var_68], r12
0x180006740  cmova   r9, [rbp+57h+var_80]
0x180006745  mov     r14, [rdi+10h]
0x180006749  mov     rax, [rdi+18h]
0x18000674d  sub     rax, r14
0x180006750  cmp     rbx, rax
0x180006753  ja      short loc_180006782
0x180006755  lea     rax, [rbx+r14]
0x180006759  mov     [rdi+10h], rax
0x18000675d  mov     rsi, rdi
0x180006760  cmp     [rdi+18h], r12
0x180006764  jbe     short loc_180006769
0x180006766  mov     rsi, [rdi]
0x180006769  lea     rcx, [rsi+r14]; void *
0x18000676d  mov     r8, rbx; Size
0x180006770  mov     rdx, r9; Src
0x180006773  call    memmove
0x180006778  lea     rax, [rsi+rbx]
0x18000677c  mov     [rax+r14], r13b
0x180006780  jmp     short loc_180006792
0x180006782  mov     [rsp+0D0h+Reserved], rbx; Size
0x180006787  mov     rdx, rbx
0x18000678a  mov     rcx, rdi; Src
0x18000678d  call    ??$_Reallocate_grow_by@V_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_65e615be2a453ca0576c979606f46740_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64>(unsigned __int64,_lambda_65e615be2a453ca0576c979606f46740_,char const *,unsigned __int64)
0x180006792  mov     rcx, [rdi+10h]
0x180006796  cmp     rcx, [rdi+18h]
0x18000679a  jnb     short loc_1800067B8
0x18000679c  lea     rax, [rcx+1]
0x1800067a0  mov     [rdi+10h], rax
0x1800067a4  mov     rax, rdi
0x1800067a7  cmp     [rdi+18h], r12
0x1800067ab  jbe     short loc_1800067B0
0x1800067ad  mov     rax, [rdi]
0x1800067b0  mov     word ptr [rax+rcx], 22h ; '"'
0x1800067b6  jmp     short loc_1800067C4
0x1800067b8  mov     r9b, 22h ; '"'
0x1800067bb  mov     rcx, rdi; Src
0x1800067be  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x1800067c3  nop
0x1800067c4  lea     rcx, [rbp+57h+var_80]
0x1800067c8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800067cd  nop
0x1800067ce  lea     rcx, [rbp+57h+Src]
0x1800067d2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800067d7  mov     rax, rdi
0x1800067da  mov     rcx, [rbp+57h+var_40]
0x1800067de  xor     rcx, rsp; StackCookie
0x1800067e1  call    __security_check_cookie
0x1800067e6  mov     rbx, [rsp+0D0h+arg_10]
0x1800067ee  add     rsp, 0A0h
0x1800067f5  pop     r15
0x1800067f7  pop     r14
0x1800067f9  pop     r13
0x1800067fb  pop     r12
0x1800067fd  pop     rdi
0x1800067fe  pop     rsi
0x1800067ff  pop     rbp
0x180006800  retn
```
