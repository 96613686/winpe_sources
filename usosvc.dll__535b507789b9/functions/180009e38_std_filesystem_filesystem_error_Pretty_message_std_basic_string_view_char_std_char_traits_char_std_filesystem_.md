# std::filesystem::filesystem_error::_Pretty_message(std::basic_string_view<char,std::char_traits<char>>,std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x180009e38`
- end: `0x18000a1d6`
- name: `?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z`
- size: `926`
- prototype: `_QWORD *__fastcall(_QWORD *Src, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180008708`

## callees

- `0x180001d2c`
- `0x1800026d0`
- `0x180002aa0`
- `0x180007584`
- `0x1800077dc`
- `0x180007b50`
- `0x180007cc4`
- `0x180008aa0`
- `0x180009e38`
- `0x18000e454`
- `0x18000e460`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::filesystem_error::_Pretty_message(_QWORD *Src, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  UINT v8; // r14d
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  size_t v11; // rsi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r14
  _BYTE *v14; // rdi
  _BYTE *v15; // rcx
  __int64 v16; // rdi
  _QWORD *v17; // r14
  __int64 v18; // rdi
  _QWORD *v19; // rsi
  size_t v20; // rdi
  void **v21; // r9
  __int64 v22; // rsi
  _QWORD *v23; // r14
  __int64 v24; // rcx
  char *v25; // rdx
  size_t v26; // rdi
  void **v27; // r9
  __int64 v28; // rsi
  _QWORD *v29; // r14
  unsigned __int64 v30; // rcx
  _QWORD *v31; // rax
  _QWORD *v33; // [rsp+40h] [rbp-29h] BYREF
  __int64 v34; // [rsp+48h] [rbp-21h]
  _QWORD *v35; // [rsp+50h] [rbp-19h]
  void *v36[2]; // [rsp+58h] [rbp-11h] BYREF
  size_t v37; // [rsp+68h] [rbp-1h]
  unsigned __int64 v38; // [rsp+70h] [rbp+7h]
  void *Srca[2]; // [rsp+78h] [rbp+Fh] BYREF
  size_t Size; // [rsp+88h] [rbp+1Fh]
  unsigned __int64 v41; // [rsp+90h] [rbp+27h]

  v35 = Src;
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  v8 = _std_fs_code_page();
  if ( a3[3] <= 7u )
    v9 = a3;
  else
    v9 = (_QWORD *)*a3;
  v33 = v9;
  v34 = a3[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    Srca,
    v8,
    (__int64)&v33);
  if ( a4[3] <= 7u )
    v10 = a4;
  else
    v10 = (_QWORD *)*a4;
  v33 = v10;
  v34 = a4[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    v36,
    v8,
    (__int64)&v33);
  v11 = *(_QWORD *)(a2 + 8);
  v12 = (((unsigned __int128)-(__int128)v37 >> 64) & 4) + 4 + v37 + v11 + Size;
  v13 = Src[2];
  if ( v13 <= v12 && Src[3] != v12 )
  {
    if ( Src[3] >= v12 )
    {
      if ( v12 <= 0xF && Src[3] > 0xFu )
      {
        v14 = (_BYTE *)*Src;
        memcpy_0(Src, (const void *)*Src, v13 + 1);
        if ( (unsigned __int64)(Src[3] + 1LL) < 0x1000 )
        {
          v15 = v14;
        }
        else
        {
          v15 = (_BYTE *)*((_QWORD *)v14 - 1);
          if ( (unsigned __int64)(v14 - v15 - 8) > 0x1F )
            __fastfail(5u);
        }
        operator delete(v15);
        Src[3] = 15;
      }
    }
    else
    {
      std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(Src);
      Src[2] = v13;
    }
  }
  v16 = Src[2];
  if ( v11 > Src[3] - v16 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(Src, v11);
  }
  else
  {
    Src[2] = v16 + v11;
    if ( Src[3] <= 0xFu )
      v17 = Src;
    else
      v17 = (_QWORD *)*Src;
    memmove_0((char *)v17 + v16, *(const void **)a2, v11);
    *((_BYTE *)v17 + v16 + v11) = 0;
  }
  v18 = Src[2];
  if ( (unsigned __int64)(Src[3] - v18) < 3 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(Src, 3u);
  }
  else
  {
    Src[2] = v18 + 3;
    if ( Src[3] <= 0xFu )
      v19 = Src;
    else
      v19 = (_QWORD *)*Src;
    memmove_0((char *)v19 + v18, ": \"", 3u);
    *((_BYTE *)v19 + v18 + 3) = 0;
  }
  v20 = Size;
  v21 = Srca;
  if ( v41 > 0xF )
    v21 = (void **)Srca[0];
  v22 = Src[2];
  if ( Size > Src[3] - v22 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(Src, Size);
  }
  else
  {
    Src[2] = v22 + Size;
    if ( Src[3] <= 0xFu )
      v23 = Src;
    else
      v23 = (_QWORD *)*Src;
    memmove_0((char *)v23 + v22, v21, v20);
    *((_BYTE *)v23 + v22 + v20) = 0;
  }
  if ( v37 )
  {
    v24 = Src[2];
    if ( (unsigned __int64)(Src[3] - v24) < 4 )
    {
      std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(Src, 4u);
    }
    else
    {
      Src[2] = v24 + 4;
      if ( Src[3] <= 0xFu )
        v25 = (char *)Src;
      else
        v25 = (char *)*Src;
      strcpy(&v25[v24], "\", \"");
    }
    v26 = v37;
    v27 = v36;
    if ( v38 > 0xF )
      v27 = (void **)v36[0];
    v28 = Src[2];
    if ( v37 > Src[3] - v28 )
    {
      std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
        Src,
        v37);
    }
    else
    {
      Src[2] = v28 + v37;
      if ( Src[3] <= 0xFu )
        v29 = Src;
      else
        v29 = (_QWORD *)*Src;
      memmove_0((char *)v29 + v28, v27, v26);
      *((_BYTE *)v29 + v28 + v26) = 0;
    }
  }
  v30 = Src[2];
  if ( v30 >= Src[3] )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src);
  }
  else
  {
    Src[2] = v30 + 1;
    if ( Src[3] <= 0xFu )
      v31 = Src;
    else
      v31 = (_QWORD *)*Src;
    *(_WORD *)((char *)v31 + v30) = 34;
  }
  std::string::~string((char **)v36);
  std::string::~string((char **)Srca);
  return Src;
}

```

## disassembly

```asm
0x180009e38  mov     [rsp-8+arg_10], rbx
0x180009e3d  mov     [rsp-8+arg_18], rsi
0x180009e42  push    rbp
0x180009e43  push    rdi
0x180009e44  push    r12
0x180009e46  push    r14
0x180009e48  push    r15
0x180009e4a  lea     rbp, [rsp-37h]
0x180009e4f  sub     rsp, 0A0h
0x180009e56  mov     rax, cs:__security_cookie
0x180009e5d  xor     rax, rsp
0x180009e60  mov     [rbp+57h+var_28], rax
0x180009e64  mov     rsi, r9
0x180009e67  mov     rdi, r8
0x180009e6a  mov     r15, rdx
0x180009e6d  mov     rbx, rcx
0x180009e70  mov     [rbp+57h+var_70], rcx
0x180009e74  mov     [rbp+57h+var_90], 0
0x180009e7b  xorps   xmm0, xmm0
0x180009e7e  movups  xmmword ptr [rcx], xmm0
0x180009e81  mov     qword ptr [rcx+10h], 0
0x180009e89  mov     r12d, 0Fh
0x180009e8f  mov     [rcx+18h], r12
0x180009e93  mov     byte ptr [rcx], 0
0x180009e96  mov     [rbp+57h+var_90], 1
0x180009e9d  call    __std_fs_code_page
0x180009ea2  mov     r14d, eax
0x180009ea5  cmp     qword ptr [rdi+18h], 7
0x180009eaa  jbe     short loc_180009EB1
0x180009eac  mov     rax, [rdi]
0x180009eaf  jmp     short loc_180009EB4
0x180009eb1  mov     rax, rdi
0x180009eb4  mov     [rbp+57h+var_80], rax
0x180009eb8  mov     rax, [rdi+10h]
0x180009ebc  mov     [rbp+57h+var_78], rax
0x180009ec0  lea     r8, [rbp+57h+var_80]
0x180009ec4  mov     edx, r14d; CodePage
0x180009ec7  lea     rcx, [rbp+57h+Src]; Src
0x180009ecb  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x180009ed0  nop
0x180009ed1  cmp     qword ptr [rsi+18h], 7
0x180009ed6  jbe     short loc_180009EDD
0x180009ed8  mov     rax, [rsi]
0x180009edb  jmp     short loc_180009EE0
0x180009edd  mov     rax, rsi
0x180009ee0  mov     [rbp+57h+var_80], rax
0x180009ee4  mov     rax, [rsi+10h]
0x180009ee8  mov     [rbp+57h+var_78], rax
0x180009eec  lea     r8, [rbp+57h+var_80]
0x180009ef0  mov     edx, r14d; CodePage
0x180009ef3  lea     rcx, [rbp+57h+var_68]; Src
0x180009ef7  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x180009efc  nop
0x180009efd  mov     rax, [rbp+57h+var_58]
0x180009f01  neg     rax
0x180009f04  sbb     rdx, rdx
0x180009f07  and     edx, 4
0x180009f0a  add     rdx, 4
0x180009f0e  mov     rsi, [r15+8]
0x180009f12  mov     rax, [rbp+57h+Size]
0x180009f16  add     rax, rsi
0x180009f19  add     rax, [rbp+57h+var_58]
0x180009f1d  add     rax, rdx
0x180009f20  mov     r14, [rbx+10h]
0x180009f24  cmp     r14, rax
0x180009f27  ja      short loc_180009F9C
0x180009f29  cmp     [rbx+18h], rax
0x180009f2d  jz      short loc_180009F9C
0x180009f2f  jnb     short loc_180009F45
0x180009f31  sub     rax, r14
0x180009f34  mov     rdx, rax
0x180009f37  mov     rcx, rbx; Src
0x180009f3a  call    ??$_Reallocate_grow_by@V_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@@Z; std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(unsigned __int64,_lambda_9013ee9e23efe4882b67eff5b0ecf103_)
0x180009f3f  mov     [rbx+10h], r14
0x180009f43  jmp     short loc_180009F9C
0x180009f45  cmp     rax, r12
0x180009f48  ja      short loc_180009F9C
0x180009f4a  cmp     [rbx+18h], r12
0x180009f4e  jbe     short loc_180009F9C
0x180009f50  mov     rdi, [rbx]
0x180009f53  lea     r8, [r14+1]; Size
0x180009f57  mov     rdx, rdi; Src
0x180009f5a  mov     rcx, rbx; void *
0x180009f5d  call    memcpy_0
0x180009f62  mov     rdx, [rbx+18h]
0x180009f66  inc     rdx; unsigned __int64
0x180009f69  cmp     rdx, 1000h
0x180009f70  jb      short loc_180009F90
0x180009f72  mov     rcx, [rdi-8]
0x180009f76  sub     rdi, rcx
0x180009f79  sub     rdi, 8
0x180009f7d  cmp     rdi, 1Fh
0x180009f81  ja      short loc_180009F89
0x180009f83  add     rdx, 27h ; '''
0x180009f87  jmp     short loc_180009F93
0x180009f89  mov     ecx, 5
0x180009f8e  int     29h; Win8: RtlFailFast(ecx)
0x180009f90  mov     rcx, rdi; void *
0x180009f93  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f98  mov     [rbx+18h], r12
0x180009f9c  mov     rdi, [rbx+10h]
0x180009fa0  mov     rax, [rbx+18h]
0x180009fa4  sub     rax, rdi
0x180009fa7  cmp     rsi, rax
0x180009faa  ja      short loc_180009FDC
0x180009fac  lea     rax, [rdi+rsi]
0x180009fb0  mov     [rbx+10h], rax
0x180009fb4  cmp     [rbx+18h], r12
0x180009fb8  jbe     short loc_180009FBF
0x180009fba  mov     r14, [rbx]
0x180009fbd  jmp     short loc_180009FC2
0x180009fbf  mov     r14, rbx
0x180009fc2  lea     rcx, [rdi+r14]; void *
0x180009fc6  mov     r8, rsi; Size
0x180009fc9  mov     rdx, [r15]; Src
0x180009fcc  call    memmove_0
0x180009fd1  lea     rax, [rdi+rsi]
0x180009fd5  mov     byte ptr [rax+r14], 0
0x180009fda  jmp     short loc_180009FEF
0x180009fdc  mov     [rsp+0C0h+var_A0], rsi; Size
0x180009fe1  mov     r9, [r15]
0x180009fe4  mov     rdx, rsi
0x180009fe7  mov     rcx, rbx; Src
0x180009fea  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x180009fef  mov     rdi, [rbx+10h]
0x180009ff3  mov     rax, [rbx+18h]
0x180009ff7  sub     rax, rdi
0x180009ffa  mov     edx, 3
0x180009fff  cmp     rax, rdx
0x18000a002  jb      short loc_18000A034
0x18000a004  lea     rax, [rdi+3]
0x18000a008  mov     [rbx+10h], rax
0x18000a00c  cmp     [rbx+18h], r12
0x18000a010  jbe     short loc_18000A017
0x18000a012  mov     rsi, [rbx]
0x18000a015  jmp     short loc_18000A01A
0x18000a017  mov     rsi, rbx
0x18000a01a  lea     rcx, [rdi+rsi]; void *
0x18000a01e  mov     r8, rdx; Size
0x18000a021  lea     rdx, asc_180010F78; ": \""
0x18000a028  call    memmove_0
0x18000a02d  mov     byte ptr [rdi+rsi+3], 0
0x18000a032  jmp     short loc_18000A048
0x18000a034  mov     [rsp+0C0h+var_A0], rdx; Size
0x18000a039  lea     r9, asc_180010F78; ": \""
0x18000a040  mov     rcx, rbx; Src
0x18000a043  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x18000a048  mov     rdi, [rbp+57h+Size]
0x18000a04c  lea     r9, [rbp+57h+Src]
0x18000a050  cmp     [rbp+57h+var_30], r12
0x18000a054  cmova   r9, [rbp+57h+Src]
0x18000a059  mov     rsi, [rbx+10h]
0x18000a05d  mov     rax, [rbx+18h]
0x18000a061  sub     rax, rsi
0x18000a064  cmp     rdi, rax
0x18000a067  ja      short loc_18000A098
0x18000a069  lea     rax, [rsi+rdi]
0x18000a06d  mov     [rbx+10h], rax
0x18000a071  cmp     [rbx+18h], r12
0x18000a075  jbe     short loc_18000A07C
0x18000a077  mov     r14, [rbx]
0x18000a07a  jmp     short loc_18000A07F
0x18000a07c  mov     r14, rbx
0x18000a07f  lea     rcx, [rsi+r14]; void *
0x18000a083  mov     r8, rdi; Size
0x18000a086  mov     rdx, r9; Src
0x18000a089  call    memmove_0
0x18000a08e  lea     rax, [rsi+r14]
0x18000a092  mov     byte ptr [rax+rdi], 0
0x18000a096  jmp     short loc_18000A0A8
0x18000a098  mov     [rsp+0C0h+var_A0], rdi; Size
0x18000a09d  mov     rdx, rdi
0x18000a0a0  mov     rcx, rbx; Src
0x18000a0a3  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x18000a0a8  cmp     [rbp+57h+var_58], 0
0x18000a0ad  jz      loc_18000A163
0x18000a0b3  mov     rcx, [rbx+10h]
0x18000a0b7  mov     rax, [rbx+18h]
0x18000a0bb  sub     rax, rcx
0x18000a0be  mov     edx, 4
0x18000a0c3  cmp     rax, rdx
0x18000a0c6  jb      short loc_18000A0EE
0x18000a0c8  lea     rax, [rcx+4]
0x18000a0cc  mov     [rbx+10h], rax
0x18000a0d0  cmp     [rbx+18h], r12
0x18000a0d4  jbe     short loc_18000A0DB
0x18000a0d6  mov     rdx, [rbx]
0x18000a0d9  jmp     short loc_18000A0DE
0x18000a0db  mov     rdx, rbx
0x18000a0de  mov     eax, dword ptr cs:asc_180010F7C; "\", \""
0x18000a0e4  mov     [rcx+rdx], eax
0x18000a0e7  mov     byte ptr [rcx+rdx+4], 0
0x18000a0ec  jmp     short loc_18000A102
0x18000a0ee  mov     [rsp+0C0h+var_A0], rdx; Size
0x18000a0f3  lea     r9, asc_180010F7C; "\", \""
0x18000a0fa  mov     rcx, rbx; Src
0x18000a0fd  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x18000a102  mov     rdi, [rbp+57h+var_58]
0x18000a106  lea     r9, [rbp+57h+var_68]
0x18000a10a  cmp     [rbp+57h+var_50], r12
0x18000a10e  cmova   r9, [rbp+57h+var_68]
0x18000a113  mov     rsi, [rbx+10h]
0x18000a117  mov     rax, [rbx+18h]
0x18000a11b  sub     rax, rsi
0x18000a11e  cmp     rdi, rax
0x18000a121  ja      short loc_18000A153
0x18000a123  lea     rax, [rsi+rdi]
0x18000a127  mov     [rbx+10h], rax
0x18000a12b  cmp     [rbx+18h], r12
0x18000a12f  jbe     short loc_18000A136
0x18000a131  mov     r14, [rbx]
0x18000a134  jmp     short loc_18000A139
0x18000a136  mov     r14, rbx
0x18000a139  lea     rcx, [rsi+r14]; void *
0x18000a13d  mov     r8, rdi; Size
0x18000a140  mov     rdx, r9; Src
0x18000a143  call    memmove_0
0x18000a148  lea     rax, [rsi+rdi]
0x18000a14c  mov     byte ptr [rax+r14], 0
0x18000a151  jmp     short loc_18000A163
0x18000a153  mov     [rsp+0C0h+var_A0], rdi; Size
0x18000a158  mov     rdx, rdi
0x18000a15b  mov     rcx, rbx; Src
0x18000a15e  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x18000a163  mov     rcx, [rbx+10h]
0x18000a167  cmp     rcx, [rbx+18h]
0x18000a16b  jnb     short loc_18000A18B
0x18000a16d  lea     rax, [rcx+1]
0x18000a171  mov     [rbx+10h], rax
0x18000a175  cmp     [rbx+18h], r12
0x18000a179  jbe     short loc_18000A180
0x18000a17b  mov     rax, [rbx]
0x18000a17e  jmp     short loc_18000A183
0x18000a180  mov     rax, rbx
0x18000a183  mov     word ptr [rcx+rax], 22h ; '"'
0x18000a189  jmp     short loc_18000A197
0x18000a18b  mov     r9b, 22h ; '"'
0x18000a18e  mov     rcx, rbx; Src
0x18000a191  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x18000a196  nop
0x18000a197  lea     rcx, [rbp+57h+var_68]
0x18000a19b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000a1a0  nop
0x18000a1a1  lea     rcx, [rbp+57h+Src]
0x18000a1a5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000a1aa  mov     rax, rbx
0x18000a1ad  mov     rcx, [rbp+57h+var_28]
0x18000a1b1  xor     rcx, rsp; StackCookie
0x18000a1b4  call    __security_check_cookie
0x18000a1b9  lea     r11, [rsp+0C0h+var_20]
0x18000a1c1  mov     rbx, [r11+40h]
0x18000a1c5  mov     rsi, [r11+48h]
0x18000a1c9  mov     rsp, r11
0x18000a1cc  pop     r15
0x18000a1ce  pop     r14
0x18000a1d0  pop     r12
0x18000a1d2  pop     rdi
0x18000a1d3  pop     rbp
0x18000a1d4  retn
```
