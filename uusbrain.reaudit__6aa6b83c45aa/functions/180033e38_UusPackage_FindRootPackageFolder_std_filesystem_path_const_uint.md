# UusPackage::FindRootPackageFolder(std::filesystem::path const &,uint)

- ea: `0x180033e38`
- end: `0x1800340b9`
- name: `?FindRootPackageFolder@UusPackage@@CA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@3@I@Z`
- size: `641`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180037064`
- `0x1800396d4`

## callees

- `0x180025aa0`
- `0x180025c5c`
- `0x180027228`
- `0x1800286d0`
- `0x180028728`
- `0x180028810`
- `0x180029158`
- `0x1800295e8`
- `0x180029644`
- `0x180033e38`
- `0x1800427d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall UusPackage::FindRootPackageFolder(__int64 a1, std::filesystem *a2, const wchar_t *a3)
{
  unsigned int v3; // r14d
  std::filesystem *v5; // rcx
  const wchar_t *v6; // rdi
  const wchar_t *root_name_end; // rax
  const wchar_t *v8; // rdx
  __int64 v9; // r11
  const wchar_t *v10; // rcx
  _BYTE *v11; // rax
  int v12; // edi
  int v13; // esi
  __int64 *v14; // rax
  struct std::error_code *v15; // r8
  bool v16; // al
  const struct std::filesystem::path *v17; // r9
  __int128 *v18; // rax
  __int128 v19; // xmm2
  __m128i v20; // xmm3
  char v22[8]; // [rsp+28h] [rbp-D8h] BYREF
  void ***v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  _BYTE v25[32]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v26[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[32]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+A0h] [rbp-60h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-50h]
  __int128 v30; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v31; // [rsp+D0h] [rbp-30h]
  _BYTE Src[32]; // [rsp+E0h] [rbp-20h] BYREF

  v3 = (unsigned int)a3;
  v24 = a1;
  v5 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v5 = *(std::filesystem **)a2;
  v6 = (const wchar_t *)((char *)v5 + 2 * *((_QWORD *)a2 + 2));
  root_name_end = std::filesystem::_Find_root_name_end(v5, v6, a3);
  if ( root_name_end != v6 )
  {
    do
    {
      if ( *root_name_end != 92 && *root_name_end != 47 )
        break;
      ++root_name_end;
    }
    while ( root_name_end != v8 );
  }
  if ( root_name_end == v8 )
    goto LABEL_13;
  do
  {
    v10 = v8 - 1;
    if ( *(v8 - 1) == 92 )
      break;
    if ( *v10 == 47 )
      break;
    --v8;
  }
  while ( root_name_end != v10 );
  if ( v6 == v8 )
  {
LABEL_13:
    v11 = (_BYTE *)std::filesystem::path::parent_path(v9, v27);
    v12 = 2;
  }
  else
  {
    std::wstring::wstring(v25, v9);
    v11 = v25;
    v12 = 1;
  }
  std::wstring::wstring(&v28, v11);
  if ( (v12 & 2) != 0 )
  {
    v12 &= ~2u;
    std::wstring::_Tidy_deallocate(v27);
  }
  if ( (v12 & 1) != 0 )
  {
    v12 &= ~1u;
    std::wstring::_Tidy_deallocate(v25);
  }
  v13 = 0;
  while ( 1 )
  {
    v14 = &UusPackage::_filenameBom;
    if ( (unsigned __int64)qword_1800638E8 > 7 )
      v14 = (__int64 *)UusPackage::_filenameBom;
    v26[0] = v14;
    v26[1] = qword_1800638E0;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v25, v26);
    v12 |= 8u;
    std::filesystem::operator/(Src, &v28, v25);
    std::wstring::_Tidy_deallocate(v25);
    *(_QWORD *)v22 = 0;
    v23 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    v16 = std::filesystem::exists((std::filesystem *)Src, (const struct std::filesystem::path *)v22, v15);
    if ( *(_DWORD *)v22 )
      std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v22, (const struct std::error_code *)Src, v17);
    if ( v16 )
      break;
    std::filesystem::path::parent_path(&v28, &v30);
    v18 = &v28;
    if ( si128.m128i_i64[1] > 7uLL )
      v18 = (__int128 *)v28;
    v26[2] = v18;
    v26[3] = si128.m128i_i64[0];
    if ( !(unsigned int)std::filesystem::path::compare((std::filesystem *)&v30) )
    {
      *(_BYTE *)(a1 + 32) = 0;
      std::wstring::_Tidy_deallocate(&v30);
      goto LABEL_30;
    }
    v19 = v30;
    v20 = v31;
    v30 = v28;
    v31 = si128;
    v28 = v19;
    si128 = v20;
    std::wstring::_Tidy_deallocate(&v30);
    std::wstring::_Tidy_deallocate(Src);
    if ( ++v13 > v3 )
    {
      *(_BYTE *)(a1 + 32) = 0;
      goto LABEL_31;
    }
  }
  *(_OWORD *)a1 = v28;
  *(__m128i *)(a1 + 16) = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v28) = 0;
  *(_BYTE *)(a1 + 32) = 1;
LABEL_30:
  std::wstring::_Tidy_deallocate(Src);
LABEL_31:
  std::wstring::_Tidy_deallocate(&v28);
  return a1;
}

```

## disassembly

```asm
0x180033e38  mov     [rsp-8+arg_10], rbx
0x180033e3d  push    rbp
0x180033e3e  push    rsi
0x180033e3f  push    rdi
0x180033e40  push    r14
0x180033e42  push    r15
0x180033e44  lea     rbp, [rsp-10h]
0x180033e49  sub     rsp, 110h
0x180033e50  mov     rax, cs:__security_cookie
0x180033e57  xor     rax, rsp
0x180033e5a  mov     [rbp+30h+var_30], rax
0x180033e5e  mov     r14d, r8d
0x180033e61  mov     r11, rdx
0x180033e64  mov     rbx, rcx
0x180033e67  mov     [rsp+130h+var_F8], rcx
0x180033e6c  xor     r15d, r15d
0x180033e6f  mov     [rsp+130h+var_110], r15d
0x180033e74  mov     rcx, rdx
0x180033e77  cmp     qword ptr [rdx+18h], 7
0x180033e7c  jbe     short loc_180033E81
0x180033e7e  mov     rcx, [rdx]; this
0x180033e81  mov     rax, [rdx+10h]
0x180033e85  lea     rdi, [rcx+rax*2]
0x180033e89  mov     rdx, rdi; wchar_t *
0x180033e8c  call    ?_Find_root_name_end@filesystem@std@@YAPEB_WQEB_W0@Z; std::filesystem::_Find_root_name_end(wchar_t const * const,wchar_t const * const)
0x180033e91  cmp     rax, rdi
0x180033e94  jz      short loc_180033EAB
0x180033e96  cmp     word ptr [rax], 5Ch ; '\'
0x180033e9a  jz      short loc_180033EA2
0x180033e9c  cmp     word ptr [rax], 2Fh ; '/'
0x180033ea0  jnz     short loc_180033EAB
0x180033ea2  add     rax, 2
0x180033ea6  cmp     rax, rdx
0x180033ea9  jnz     short loc_180033E96
0x180033eab  cmp     rax, rdx
0x180033eae  jz      short loc_180033EE6
0x180033eb0  lea     rcx, [rdx-2]
0x180033eb4  cmp     word ptr [rcx], 5Ch ; '\'
0x180033eb8  jz      short loc_180033EC8
0x180033eba  cmp     word ptr [rcx], 2Fh ; '/'
0x180033ebe  jz      short loc_180033EC8
0x180033ec0  mov     rdx, rcx
0x180033ec3  cmp     rax, rcx
0x180033ec6  jnz     short loc_180033EB0
0x180033ec8  cmp     rdi, rdx
0x180033ecb  jz      short loc_180033EE6
0x180033ecd  mov     rdx, r11
0x180033ed0  lea     rcx, [rsp+130h+var_F0]
0x180033ed5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180033eda  lea     rax, [rsp+130h+var_F0]
0x180033edf  mov     edi, 1
0x180033ee4  jmp     short loc_180033EF8
0x180033ee6  lea     rdx, [rbp+30h+var_B0]
0x180033eea  mov     rcx, r11
0x180033eed  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x180033ef2  nop
0x180033ef3  mov     edi, 2
0x180033ef8  mov     [rsp+130h+var_110], edi
0x180033efc  mov     rdx, rax
0x180033eff  lea     rcx, [rbp+30h+var_90]
0x180033f03  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180033f08  nop
0x180033f09  test    dil, 2
0x180033f0d  jz      short loc_180033F1C
0x180033f0f  and     edi, 0FFFFFFFDh
0x180033f12  lea     rcx, [rbp+30h+var_B0]
0x180033f16  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033f1b  nop
0x180033f1c  test    dil, 1
0x180033f20  jz      short loc_180033F2F
0x180033f22  and     edi, 0FFFFFFFEh
0x180033f25  lea     rcx, [rsp+130h+var_F0]
0x180033f2a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033f2f  mov     esi, r15d
0x180033f32  mov     rcx, cs:qword_1800638E0
0x180033f39  lea     rax, ?_filenameBom@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_filenameBom
0x180033f40  cmp     cs:qword_1800638E8, 7
0x180033f48  cmova   rax, cs:?_filenameBom@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_filenameBom
0x180033f50  mov     [rsp+130h+var_D0], rax
0x180033f55  mov     [rsp+130h+var_C8], rcx
0x180033f5a  lea     rdx, [rsp+130h+var_D0]
0x180033f5f  lea     rcx, [rsp+130h+var_F0]
0x180033f64  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180033f69  or      edi, 8
0x180033f6c  lea     r8, [rsp+130h+var_F0]; void *
0x180033f71  lea     rdx, [rbp+30h+var_90]; void *
0x180033f75  lea     rcx, [rbp+30h+Src]; Src
0x180033f79  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180033f7e  nop
0x180033f7f  lea     rcx, [rsp+130h+var_F0]
0x180033f84  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033f89  mov     qword ptr [rsp+130h+var_108], r15
0x180033f8e  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180033f95  mov     [rsp+130h+var_100], rax
0x180033f9a  lea     rdx, [rsp+130h+var_108]; struct std::filesystem::path *
0x180033f9f  lea     rcx, [rbp+30h+Src]; this
0x180033fa3  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x180033fa8  cmp     dword ptr [rsp+130h+var_108], r15d
0x180033fad  jnz     loc_1800340A3
0x180033fb3  test    al, al
0x180033fb5  jnz     loc_180034045
0x180033fbb  lea     rdx, [rbp+30h+var_70]
0x180033fbf  lea     rcx, [rbp+30h+var_90]
0x180033fc3  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x180033fc8  lea     rax, [rbp+30h+var_90]
0x180033fcc  cmp     qword ptr [rbp+30h+var_80+8], 7
0x180033fd1  cmova   rax, qword ptr [rbp+30h+var_90]
0x180033fd6  mov     [rsp+130h+var_C0], rax
0x180033fdb  mov     rax, qword ptr [rbp+30h+var_80]
0x180033fdf  mov     [rsp+130h+var_B8], rax
0x180033fe4  lea     rdx, [rsp+130h+var_C0]
0x180033fe9  lea     rcx, [rbp+30h+var_70]; this
0x180033fed  call    ?compare@path@filesystem@std@@QEBAHV?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; std::filesystem::path::compare(std::wstring_view)
0x180033ff2  lea     rcx, [rbp+30h+var_70]
0x180033ff6  test    eax, eax
0x180033ff8  jz      short loc_18003403A
0x180033ffa  movups  xmm2, [rbp+30h+var_70]
0x180033ffe  movups  xmm3, [rbp+30h+var_60]
0x180034002  movups  xmm0, [rbp+30h+var_90]
0x180034006  movups  [rbp+30h+var_70], xmm0
0x18003400a  movups  xmm1, [rbp+30h+var_80]
0x18003400e  movups  [rbp+30h+var_60], xmm1
0x180034012  movups  [rbp+30h+var_90], xmm2
0x180034016  movups  [rbp+30h+var_80], xmm3
0x18003401a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003401f  nop
0x180034020  lea     rcx, [rbp+30h+Src]
0x180034024  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034029  inc     esi
0x18003402b  cmp     esi, r14d
0x18003402e  jbe     loc_180033F32
0x180034034  mov     [rbx+20h], r15b
0x180034038  jmp     short loc_180034074
0x18003403a  mov     [rbx+20h], r15b
0x18003403e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034043  jmp     short loc_18003406A
0x180034045  movups  xmm0, [rbp+30h+var_90]
0x180034049  movups  xmmword ptr [rbx], xmm0
0x18003404c  movups  xmm1, [rbp+30h+var_80]
0x180034050  movups  xmmword ptr [rbx+10h], xmm1
0x180034054  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18003405c  movdqu  [rbp+30h+var_80], xmm0
0x180034061  mov     word ptr [rbp+30h+var_90], r15w
0x180034066  mov     byte ptr [rbx+20h], 1
0x18003406a  lea     rcx, [rbp+30h+Src]
0x18003406e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034073  nop
0x180034074  lea     rcx, [rbp+30h+var_90]
0x180034078  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003407d  mov     rax, rbx
0x180034080  mov     rcx, [rbp+30h+var_30]
0x180034084  xor     rcx, rsp; StackCookie
0x180034087  call    __security_check_cookie
0x18003408c  mov     rbx, [rsp+130h+arg_10]
0x180034094  add     rsp, 110h
0x18003409b  pop     r15
0x18003409d  pop     r14
0x18003409f  pop     rdi
0x1800340a0  pop     rsi
0x1800340a1  pop     rbp
0x1800340a2  retn
0x1800340a3  lea     r8, [rbp+30h+Src]; struct std::error_code *
0x1800340a7  lea     rdx, [rsp+130h+var_108]; char *
0x1800340ac  lea     rcx, aExists; "exists"
0x1800340b3  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
