# std::filesystem::filesystem_error::_Pretty_message(std::basic_string_view<char,std::char_traits<char>>,std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x140009dcc`
- end: `0x14000a16a`
- name: `?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z`
- size: `926`
- prototype: `_QWORD *__fastcall(_QWORD *Src, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1400083c4`

## callees

- `0x140001848`
- `0x140002130`
- `0x1400023c4`
- `0x140007240`
- `0x140007498`
- `0x14000780c`
- `0x140007980`
- `0x14000875c`
- `0x140009dcc`
- `0x14000ac74`
- `0x14000ac80`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::filesystem_error::_Pretty_message(_QWORD *Src, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  UINT v8; // r14d
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r14
  _BYTE *v15; // rdi
  _BYTE *v16; // rcx
  __int64 v17; // rdi
  _QWORD *v18; // r14
  __int64 v19; // r8
  __int64 v20; // rdi
  _QWORD *v21; // rsi
  __int64 v22; // r8
  size_t v23; // rdi
  void **v24; // r9
  __int64 v25; // rsi
  _QWORD *v26; // r14
  __int64 v27; // r8
  __int64 v28; // rcx
  char *v29; // rdx
  size_t v30; // rdi
  void **v31; // r9
  __int64 v32; // rsi
  _QWORD *v33; // r14
  unsigned __int64 v34; // rcx
  _QWORD *v35; // rax
  _QWORD *v37; // [rsp+40h] [rbp-29h] BYREF
  __int64 v38; // [rsp+48h] [rbp-21h]
  _QWORD *v39; // [rsp+50h] [rbp-19h]
  void *v40[2]; // [rsp+58h] [rbp-11h] BYREF
  size_t v41; // [rsp+68h] [rbp-1h]
  unsigned __int64 v42; // [rsp+70h] [rbp+7h]
  void *Srca[2]; // [rsp+78h] [rbp+Fh] BYREF
  size_t Size; // [rsp+88h] [rbp+1Fh]
  unsigned __int64 v45; // [rsp+90h] [rbp+27h]

  v39 = Src;
  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 15;
  *(_BYTE *)Src = 0;
  v8 = _std_fs_code_page();
  if ( a3[3] <= 7u )
    v9 = a3;
  else
    v9 = (_QWORD *)*a3;
  v37 = v9;
  v38 = a3[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    Srca,
    v8,
    (__int64)&v37);
  if ( a4[3] <= 7u )
    v10 = a4;
  else
    v10 = (_QWORD *)*a4;
  v37 = v10;
  v38 = a4[2];
  std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(
    v40,
    v8,
    (__int64)&v37);
  v12 = *(_QWORD *)(a2 + 8);
  v13 = (((unsigned __int128)-(__int128)v41 >> 64) & 4) + 4 + v41 + v12 + Size;
  v14 = Src[2];
  if ( v14 <= v13 && Src[3] != v13 )
  {
    if ( Src[3] >= v13 )
    {
      if ( v13 <= 0xF && Src[3] > 0xFu )
      {
        v15 = (_BYTE *)*Src;
        memcpy_0(Src, (const void *)*Src, v14 + 1);
        if ( (unsigned __int64)(Src[3] + 1LL) < 0x1000 )
        {
          v16 = v15;
        }
        else
        {
          v16 = (_BYTE *)*((_QWORD *)v15 - 1);
          if ( (unsigned __int64)(v15 - v16 - 8) > 0x1F )
            __fastfail(5u);
        }
        operator delete(v16);
        Src[3] = 15;
      }
    }
    else
    {
      std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(Src);
      Src[2] = v14;
    }
  }
  v17 = Src[2];
  if ( v12 > Src[3] - v17 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
      (void **)Src,
      v12,
      v11,
      *(const void **)a2,
      v12);
  }
  else
  {
    Src[2] = v17 + v12;
    if ( Src[3] <= 0xFu )
      v18 = Src;
    else
      v18 = (_QWORD *)*Src;
    memmove_0((char *)v18 + v17, *(const void **)a2, v12);
    *((_BYTE *)v18 + v17 + v12) = 0;
  }
  v20 = Src[2];
  if ( (unsigned __int64)(Src[3] - v20) < 3 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
      (void **)Src,
      3u,
      v19,
      ": \"",
      3u);
  }
  else
  {
    Src[2] = v20 + 3;
    if ( Src[3] <= 0xFu )
      v21 = Src;
    else
      v21 = (_QWORD *)*Src;
    memmove_0((char *)v21 + v20, ": \"", 3u);
    *((_BYTE *)v21 + v20 + 3) = 0;
  }
  v23 = Size;
  v24 = Srca;
  if ( v45 > 0xF )
    v24 = (void **)Srca[0];
  v25 = Src[2];
  if ( Size > Src[3] - v25 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
      (void **)Src,
      Size,
      v22,
      v24,
      Size);
  }
  else
  {
    Src[2] = v25 + Size;
    if ( Src[3] <= 0xFu )
      v26 = Src;
    else
      v26 = (_QWORD *)*Src;
    memmove_0((char *)v26 + v25, v24, v23);
    *((_BYTE *)v26 + v25 + v23) = 0;
  }
  if ( v41 )
  {
    v28 = Src[2];
    if ( (unsigned __int64)(Src[3] - v28) < 4 )
    {
      std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
        (void **)Src,
        4u,
        v27,
        "\", \"",
        4u);
    }
    else
    {
      Src[2] = v28 + 4;
      if ( Src[3] <= 0xFu )
        v29 = (char *)Src;
      else
        v29 = (char *)*Src;
      strcpy(&v29[v28], "\", \"");
    }
    v30 = v41;
    v31 = v40;
    if ( v42 > 0xF )
      v31 = (void **)v40[0];
    v32 = Src[2];
    if ( v41 > Src[3] - v32 )
    {
      std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(
        (void **)Src,
        v41,
        v27,
        v31,
        v41);
    }
    else
    {
      Src[2] = v32 + v41;
      if ( Src[3] <= 0xFu )
        v33 = Src;
      else
        v33 = (_QWORD *)*Src;
      memmove_0((char *)v33 + v32, v31, v30);
      *((_BYTE *)v33 + v32 + v30) = 0;
    }
  }
  v34 = Src[2];
  if ( v34 >= Src[3] )
  {
    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src);
  }
  else
  {
    Src[2] = v34 + 1;
    if ( Src[3] <= 0xFu )
      v35 = Src;
    else
      v35 = (_QWORD *)*Src;
    *(_WORD *)((char *)v35 + v34) = 34;
  }
  std::string::~string((char **)v40);
  std::string::~string((char **)Srca);
  return Src;
}

```

## disassembly

```asm
0x140009dcc  mov     [rsp-8+arg_10], rbx
0x140009dd1  mov     [rsp-8+arg_18], rsi
0x140009dd6  push    rbp
0x140009dd7  push    rdi
0x140009dd8  push    r12
0x140009dda  push    r14
0x140009ddc  push    r15
0x140009dde  lea     rbp, [rsp-37h]
0x140009de3  sub     rsp, 0A0h
0x140009dea  mov     rax, cs:__security_cookie
0x140009df1  xor     rax, rsp
0x140009df4  mov     [rbp+57h+var_28], rax
0x140009df8  mov     rsi, r9
0x140009dfb  mov     rdi, r8
0x140009dfe  mov     r15, rdx
0x140009e01  mov     rbx, rcx
0x140009e04  mov     [rbp+57h+var_70], rcx
0x140009e08  mov     [rbp+57h+var_90], 0
0x140009e0f  xorps   xmm0, xmm0
0x140009e12  movups  xmmword ptr [rcx], xmm0
0x140009e15  mov     qword ptr [rcx+10h], 0
0x140009e1d  mov     r12d, 0Fh
0x140009e23  mov     [rcx+18h], r12
0x140009e27  mov     byte ptr [rcx], 0
0x140009e2a  mov     [rbp+57h+var_90], 1
0x140009e31  call    __std_fs_code_page
0x140009e36  mov     r14d, eax
0x140009e39  cmp     qword ptr [rdi+18h], 7
0x140009e3e  jbe     short loc_140009E45
0x140009e40  mov     rax, [rdi]
0x140009e43  jmp     short loc_140009E48
0x140009e45  mov     rax, rdi
0x140009e48  mov     [rbp+57h+var_80], rax
0x140009e4c  mov     rax, [rdi+10h]
0x140009e50  mov     [rbp+57h+var_78], rax
0x140009e54  lea     r8, [rbp+57h+var_80]
0x140009e58  mov     edx, r14d; CodePage
0x140009e5b  lea     rcx, [rbp+57h+Src]; Src
0x140009e5f  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x140009e64  nop
0x140009e65  cmp     qword ptr [rsi+18h], 7
0x140009e6a  jbe     short loc_140009E71
0x140009e6c  mov     rax, [rsi]
0x140009e6f  jmp     short loc_140009E74
0x140009e71  mov     rax, rsi
0x140009e74  mov     [rbp+57h+var_80], rax
0x140009e78  mov     rax, [rsi+10h]
0x140009e7c  mov     [rbp+57h+var_78], rax
0x140009e80  lea     r8, [rbp+57h+var_80]
0x140009e84  mov     edx, r14d; CodePage
0x140009e87  lea     rcx, [rbp+57h+var_68]; Src
0x140009e8b  call    ??$_Convert_wide_to_narrow_replace_chars@U?$char_traits@D@std@@V?$allocator@D@2@@filesystem@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@W4__std_code_page@@V?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@D@1@@Z; std::filesystem::_Convert_wide_to_narrow_replace_chars<std::char_traits<char>,std::allocator<char>>(__std_code_page,std::basic_string_view<ushort>,std::allocator<char> const &)
0x140009e90  nop
0x140009e91  mov     rax, [rbp+57h+var_58]
0x140009e95  neg     rax
0x140009e98  sbb     rdx, rdx
0x140009e9b  and     edx, 4
0x140009e9e  add     rdx, 4
0x140009ea2  mov     rsi, [r15+8]
0x140009ea6  mov     rax, [rbp+57h+Size]
0x140009eaa  add     rax, rsi
0x140009ead  add     rax, [rbp+57h+var_58]
0x140009eb1  add     rax, rdx
0x140009eb4  mov     r14, [rbx+10h]
0x140009eb8  cmp     r14, rax
0x140009ebb  ja      short loc_140009F30
0x140009ebd  cmp     [rbx+18h], rax
0x140009ec1  jz      short loc_140009F30
0x140009ec3  jnb     short loc_140009ED9
0x140009ec5  sub     rax, r14
0x140009ec8  mov     rdx, rax
0x140009ecb  mov     rcx, rbx; Src
0x140009ece  call    ??$_Reallocate_grow_by@V_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@$$V@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_9013ee9e23efe4882b67eff5b0ecf103_@@@Z; std::string::_Reallocate_grow_by<_lambda_9013ee9e23efe4882b67eff5b0ecf103_,>(unsigned __int64,_lambda_9013ee9e23efe4882b67eff5b0ecf103_)
0x140009ed3  mov     [rbx+10h], r14
0x140009ed7  jmp     short loc_140009F30
0x140009ed9  cmp     rax, r12
0x140009edc  ja      short loc_140009F30
0x140009ede  cmp     [rbx+18h], r12
0x140009ee2  jbe     short loc_140009F30
0x140009ee4  mov     rdi, [rbx]
0x140009ee7  lea     r8, [r14+1]; Size
0x140009eeb  mov     rdx, rdi; Src
0x140009eee  mov     rcx, rbx; void *
0x140009ef1  call    memcpy_0
0x140009ef6  mov     rdx, [rbx+18h]
0x140009efa  inc     rdx; unsigned __int64
0x140009efd  cmp     rdx, 1000h
0x140009f04  jb      short loc_140009F24
0x140009f06  mov     rcx, [rdi-8]
0x140009f0a  sub     rdi, rcx
0x140009f0d  sub     rdi, 8
0x140009f11  cmp     rdi, 1Fh
0x140009f15  ja      short loc_140009F1D
0x140009f17  add     rdx, 27h ; '''
0x140009f1b  jmp     short loc_140009F27
0x140009f1d  mov     ecx, 5
0x140009f22  int     29h; Win8: RtlFailFast(ecx)
0x140009f24  mov     rcx, rdi; void *
0x140009f27  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009f2c  mov     [rbx+18h], r12
0x140009f30  mov     rdi, [rbx+10h]
0x140009f34  mov     rax, [rbx+18h]
0x140009f38  sub     rax, rdi
0x140009f3b  cmp     rsi, rax
0x140009f3e  ja      short loc_140009F70
0x140009f40  lea     rax, [rdi+rsi]
0x140009f44  mov     [rbx+10h], rax
0x140009f48  cmp     [rbx+18h], r12
0x140009f4c  jbe     short loc_140009F53
0x140009f4e  mov     r14, [rbx]
0x140009f51  jmp     short loc_140009F56
0x140009f53  mov     r14, rbx
0x140009f56  lea     rcx, [rdi+r14]; void *
0x140009f5a  mov     r8, rsi; Size
0x140009f5d  mov     rdx, [r15]; Src
0x140009f60  call    memmove_0
0x140009f65  lea     rax, [rdi+rsi]
0x140009f69  mov     byte ptr [rax+r14], 0
0x140009f6e  jmp     short loc_140009F83
0x140009f70  mov     [rsp+0C0h+var_A0], rsi; Size
0x140009f75  mov     r9, [r15]
0x140009f78  mov     rdx, rsi
0x140009f7b  mov     rcx, rbx; Src
0x140009f7e  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x140009f83  mov     rdi, [rbx+10h]
0x140009f87  mov     rax, [rbx+18h]
0x140009f8b  sub     rax, rdi
0x140009f8e  mov     edx, 3
0x140009f93  cmp     rax, rdx
0x140009f96  jb      short loc_140009FC8
0x140009f98  lea     rax, [rdi+3]
0x140009f9c  mov     [rbx+10h], rax
0x140009fa0  cmp     [rbx+18h], r12
0x140009fa4  jbe     short loc_140009FAB
0x140009fa6  mov     rsi, [rbx]
0x140009fa9  jmp     short loc_140009FAE
0x140009fab  mov     rsi, rbx
0x140009fae  lea     rcx, [rdi+rsi]; void *
0x140009fb2  mov     r8, rdx; Size
0x140009fb5  lea     rdx, asc_14000DEB0; ": \""
0x140009fbc  call    memmove_0
0x140009fc1  mov     byte ptr [rdi+rsi+3], 0
0x140009fc6  jmp     short loc_140009FDC
0x140009fc8  mov     [rsp+0C0h+var_A0], rdx; Size
0x140009fcd  lea     r9, asc_14000DEB0; ": \""
0x140009fd4  mov     rcx, rbx; Src
0x140009fd7  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x140009fdc  mov     rdi, [rbp+57h+Size]
0x140009fe0  lea     r9, [rbp+57h+Src]
0x140009fe4  cmp     [rbp+57h+var_30], r12
0x140009fe8  cmova   r9, [rbp+57h+Src]
0x140009fed  mov     rsi, [rbx+10h]
0x140009ff1  mov     rax, [rbx+18h]
0x140009ff5  sub     rax, rsi
0x140009ff8  cmp     rdi, rax
0x140009ffb  ja      short loc_14000A02C
0x140009ffd  lea     rax, [rsi+rdi]
0x14000a001  mov     [rbx+10h], rax
0x14000a005  cmp     [rbx+18h], r12
0x14000a009  jbe     short loc_14000A010
0x14000a00b  mov     r14, [rbx]
0x14000a00e  jmp     short loc_14000A013
0x14000a010  mov     r14, rbx
0x14000a013  lea     rcx, [rsi+r14]; void *
0x14000a017  mov     r8, rdi; Size
0x14000a01a  mov     rdx, r9; Src
0x14000a01d  call    memmove_0
0x14000a022  lea     rax, [rsi+r14]
0x14000a026  mov     byte ptr [rax+rdi], 0
0x14000a02a  jmp     short loc_14000A03C
0x14000a02c  mov     [rsp+0C0h+var_A0], rdi; Size
0x14000a031  mov     rdx, rdi
0x14000a034  mov     rcx, rbx; Src
0x14000a037  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x14000a03c  cmp     [rbp+57h+var_58], 0
0x14000a041  jz      loc_14000A0F7
0x14000a047  mov     rcx, [rbx+10h]
0x14000a04b  mov     rax, [rbx+18h]
0x14000a04f  sub     rax, rcx
0x14000a052  mov     edx, 4
0x14000a057  cmp     rax, rdx
0x14000a05a  jb      short loc_14000A082
0x14000a05c  lea     rax, [rcx+4]
0x14000a060  mov     [rbx+10h], rax
0x14000a064  cmp     [rbx+18h], r12
0x14000a068  jbe     short loc_14000A06F
0x14000a06a  mov     rdx, [rbx]
0x14000a06d  jmp     short loc_14000A072
0x14000a06f  mov     rdx, rbx
0x14000a072  mov     eax, dword ptr cs:asc_14000DEB4; "\", \""
0x14000a078  mov     [rcx+rdx], eax
0x14000a07b  mov     byte ptr [rcx+rdx+4], 0
0x14000a080  jmp     short loc_14000A096
0x14000a082  mov     [rsp+0C0h+var_A0], rdx; Size
0x14000a087  lea     r9, asc_14000DEB4; "\", \""
0x14000a08e  mov     rcx, rbx; Src
0x14000a091  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x14000a096  mov     rdi, [rbp+57h+var_58]
0x14000a09a  lea     r9, [rbp+57h+var_68]
0x14000a09e  cmp     [rbp+57h+var_50], r12
0x14000a0a2  cmova   r9, [rbp+57h+var_68]
0x14000a0a7  mov     rsi, [rbx+10h]
0x14000a0ab  mov     rax, [rbx+18h]
0x14000a0af  sub     rax, rsi
0x14000a0b2  cmp     rdi, rax
0x14000a0b5  ja      short loc_14000A0E7
0x14000a0b7  lea     rax, [rsi+rdi]
0x14000a0bb  mov     [rbx+10h], rax
0x14000a0bf  cmp     [rbx+18h], r12
0x14000a0c3  jbe     short loc_14000A0CA
0x14000a0c5  mov     r14, [rbx]
0x14000a0c8  jmp     short loc_14000A0CD
0x14000a0ca  mov     r14, rbx
0x14000a0cd  lea     rcx, [rsi+r14]; void *
0x14000a0d1  mov     r8, rdi; Size
0x14000a0d4  mov     rdx, r9; Src
0x14000a0d7  call    memmove_0
0x14000a0dc  lea     rax, [rsi+rdi]
0x14000a0e0  mov     byte ptr [rax+r14], 0
0x14000a0e5  jmp     short loc_14000A0F7
0x14000a0e7  mov     [rsp+0C0h+var_A0], rdi; Size
0x14000a0ec  mov     rdx, rdi
0x14000a0ef  mov     rcx, rbx; Src
0x14000a0f2  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x14000a0f7  mov     rcx, [rbx+10h]
0x14000a0fb  cmp     rcx, [rbx+18h]
0x14000a0ff  jnb     short loc_14000A11F
0x14000a101  lea     rax, [rcx+1]
0x14000a105  mov     [rbx+10h], rax
0x14000a109  cmp     [rbx+18h], r12
0x14000a10d  jbe     short loc_14000A114
0x14000a10f  mov     rax, [rbx]
0x14000a112  jmp     short loc_14000A117
0x14000a114  mov     rax, rbx
0x14000a117  mov     word ptr [rcx+rax], 22h ; '"'
0x14000a11d  jmp     short loc_14000A12B
0x14000a11f  mov     r9b, 22h ; '"'
0x14000a122  mov     rcx, rbx; Src
0x14000a125  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x14000a12a  nop
0x14000a12b  lea     rcx, [rbp+57h+var_68]
0x14000a12f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000a134  nop
0x14000a135  lea     rcx, [rbp+57h+Src]
0x14000a139  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000a13e  mov     rax, rbx
0x14000a141  mov     rcx, [rbp+57h+var_28]
0x14000a145  xor     rcx, rsp; StackCookie
0x14000a148  call    __security_check_cookie
0x14000a14d  lea     r11, [rsp+0C0h+var_20]
0x14000a155  mov     rbx, [r11+40h]
0x14000a159  mov     rsi, [r11+48h]
0x14000a15d  mov     rsp, r11
0x14000a160  pop     r15
0x14000a162  pop     r14
0x14000a164  pop     r12
0x14000a166  pop     rdi
0x14000a167  pop     rbp
0x14000a168  retn
```
