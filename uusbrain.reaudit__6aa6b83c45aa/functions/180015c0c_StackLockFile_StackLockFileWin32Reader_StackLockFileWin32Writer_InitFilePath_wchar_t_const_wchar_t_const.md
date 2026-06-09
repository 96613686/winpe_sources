# _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::InitFilePath(wchar_t const *,wchar_t const *)

- ea: `0x180015c0c`
- end: `0x180015de4`
- name: `?InitFilePath@?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@CA?AVpath@filesystem@std@@PEB_W0@Z`
- size: `472`
- prototype: `__int64 __fastcall(struct std::error_code *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18000e888`

## callees

- `0x180015c0c`
- `0x1800236e0`
- `0x180024a7c`
- `0x180027228`
- `0x1800286d0`
- `0x180028b6c`
- `0x180028e4c`
- `0x180028ec4`
- `0x1800295e8`
- `0x180029644`

## string_xrefs

- `0x180015dc3`: `create_directories`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct std::error_code *__fastcall _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::InitFilePath(
        struct std::error_code *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // rdi
  __int64 v6; // rax
  struct std::error_code *v7; // r8
  bool v8; // al
  struct std::error_code *v9; // r8
  const struct std::filesystem::path *v10; // r9
  const struct std::filesystem::path *v11; // r9
  __int64 *v12; // rax
  _WORD *v13; // rax
  unsigned __int64 v14; // rcx
  struct std::error_code *v15; // rax
  char v17[8]; // [rsp+20h] [rbp-60h] BYREF
  void ***v18; // [rsp+28h] [rbp-58h]
  int v19; // [rsp+30h] [rbp-50h]
  _QWORD v20[5]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-20h] BYREF

  v20[4] = a1;
  v19 = 0;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(a2 + 2 * v6) );
  *(_QWORD *)v17 = a2;
  v18 = (void ***)v6;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(a1, v17);
  v19 = 3;
  *(_QWORD *)v17 = 0;
  v18 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v8 = std::filesystem::exists(a1, (const struct std::filesystem::path *)v17, v7);
  if ( *(_DWORD *)v17 )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v17, a1, v10);
  if ( !v8 )
  {
    *(_QWORD *)v17 = 0;
    v18 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    std::filesystem::create_directories(a1, (const struct std::filesystem::path *)v17, v9);
    if ( *(_DWORD *)v17 )
      std::filesystem::_Throw_fs_error((std::filesystem *)"create_directories", v17, a1, v11);
  }
  do
    ++v5;
  while ( *(_WORD *)(a3 + 2 * v5) );
  *(_QWORD *)v17 = a3;
  v18 = (void ***)v5;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v21, v17);
  v19 = 7;
  std::filesystem::path::operator/=(a1, v21);
  std::wstring::_Tidy_deallocate(v21);
  v12 = &_StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::_extensionLockFile;
  if ( (unsigned __int64)qword_180063AE8 > 7 )
    v12 = (__int64 *)_StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::_extensionLockFile;
  *(_QWORD *)v17 = v12;
  v18 = (void ***)qword_180063AE0;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v20, v17);
  v19 = 15;
  std::filesystem::path::replace_extension(a1);
  if ( v20[2] )
  {
    v13 = v20;
    if ( v20[3] > 7u )
      v13 = (_WORD *)v20[0];
    if ( *v13 != 46 )
    {
      v14 = *((_QWORD *)a1 + 2);
      if ( v14 >= *((_QWORD *)a1 + 3) )
      {
        std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(a1);
      }
      else
      {
        *((_QWORD *)a1 + 2) = v14 + 1;
        v15 = a1;
        if ( *((_QWORD *)a1 + 3) > 7u )
          v15 = *(struct std::error_code **)a1;
        *(_DWORD *)((char *)v15 + 2 * v14) = 46;
      }
    }
  }
  std::wstring::append(a1);
  std::wstring::_Tidy_deallocate(v20);
  return a1;
}

```

## disassembly

```asm
0x180015c0c  mov     [rsp-18h+arg_8], rbx
0x180015c11  mov     [rsp-18h+arg_10], rsi
0x180015c16  mov     [rsp-18h+arg_18], rdi
0x180015c1b  push    rbp
0x180015c1c  push    r14
0x180015c1e  push    r15
0x180015c20  mov     rbp, rsp
0x180015c23  sub     rsp, 80h
0x180015c2a  mov     rsi, r8
0x180015c2d  mov     rbx, rcx
0x180015c30  mov     [rbp+var_28], rcx
0x180015c34  xor     r14d, r14d
0x180015c37  mov     [rbp+var_50], r14d
0x180015c3b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180015c3f  mov     rax, rdi
0x180015c42  inc     rax
0x180015c45  cmp     [rdx+rax*2], r14w
0x180015c4a  jnz     short loc_180015C42
0x180015c4c  mov     qword ptr [rbp+var_60], rdx
0x180015c50  mov     [rbp+var_58], rax
0x180015c54  lea     rdx, [rbp+var_60]
0x180015c58  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180015c5d  mov     [rbp+var_50], 3
0x180015c64  mov     qword ptr [rbp+var_60], r14
0x180015c68  lea     r15, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180015c6f  mov     [rbp+var_58], r15
0x180015c73  lea     rdx, [rbp+var_60]; struct std::filesystem::path *
0x180015c77  mov     rcx, rbx; this
0x180015c7a  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x180015c7f  cmp     dword ptr [rbp+var_60], r14d
0x180015c83  jnz     loc_180015DD0
0x180015c89  test    al, al
0x180015c8b  jnz     short loc_180015CAB
0x180015c8d  mov     qword ptr [rbp+var_60], r14
0x180015c91  mov     [rbp+var_58], r15
0x180015c95  lea     rdx, [rbp+var_60]; struct std::filesystem::path *
0x180015c99  mov     rcx, rbx; this
0x180015c9c  call    ?create_directories@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::create_directories(std::filesystem::path const &,std::error_code &)
0x180015ca1  cmp     dword ptr [rbp+var_60], r14d
0x180015ca5  jnz     loc_180015DBC
0x180015cab  inc     rdi
0x180015cae  cmp     [rsi+rdi*2], r14w
0x180015cb3  jnz     short loc_180015CAB
0x180015cb5  mov     qword ptr [rbp+var_60], rsi
0x180015cb9  mov     [rbp+var_58], rdi
0x180015cbd  lea     rdx, [rbp+var_60]
0x180015cc1  lea     rcx, [rbp+var_20]
0x180015cc5  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180015cca  mov     [rbp+var_50], 7
0x180015cd1  lea     rdx, [rbp+var_20]; void *
0x180015cd5  mov     rcx, rbx; Src
0x180015cd8  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x180015cdd  nop
0x180015cde  lea     rcx, [rbp+var_20]
0x180015ce2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015ce7  mov     rcx, cs:qword_180063AE0
0x180015cee  lea     rax, ?_extensionLockFile@?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::_extensionLockFile
0x180015cf5  cmp     cs:qword_180063AE8, 7
0x180015cfd  cmova   rax, cs:?_extensionLockFile@?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::_extensionLockFile
0x180015d05  mov     qword ptr [rbp+var_60], rax
0x180015d09  mov     [rbp+var_58], rcx
0x180015d0d  lea     rdx, [rbp+var_60]
0x180015d11  lea     rcx, [rbp+var_48]
0x180015d15  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180015d1a  mov     [rbp+var_50], 0Fh
0x180015d21  mov     rcx, rbx; this
0x180015d24  call    ?replace_extension@path@filesystem@std@@QEAAAEAV123@XZ; std::filesystem::path::replace_extension(void)
0x180015d29  mov     rdi, [rbp+var_38]
0x180015d2d  test    rdi, rdi
0x180015d30  jz      short loc_180015D79
0x180015d32  lea     rax, [rbp+var_48]
0x180015d36  cmp     [rbp+var_30], 7
0x180015d3b  cmova   rax, [rbp+var_48]
0x180015d40  mov     r9d, 2Eh ; '.'
0x180015d46  cmp     [rax], r9w
0x180015d4a  jz      short loc_180015D79
0x180015d4c  mov     rcx, [rbx+10h]
0x180015d50  cmp     rcx, [rbx+18h]
0x180015d54  jnb     short loc_180015D71
0x180015d56  lea     rax, [rcx+1]
0x180015d5a  mov     [rbx+10h], rax
0x180015d5e  mov     rax, rbx
0x180015d61  cmp     qword ptr [rbx+18h], 7
0x180015d66  jbe     short loc_180015D6B
0x180015d68  mov     rax, [rbx]
0x180015d6b  mov     [rax+rcx*2], r9d
0x180015d6f  jmp     short loc_180015D79
0x180015d71  mov     rcx, rbx; Src
0x180015d74  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x180015d79  lea     rdx, [rbp+var_48]
0x180015d7d  cmp     [rbp+var_30], 7
0x180015d82  cmova   rdx, [rbp+var_48]
0x180015d87  mov     r8, rdi
0x180015d8a  mov     rcx, rbx; Src
0x180015d8d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180015d92  nop
0x180015d93  lea     rcx, [rbp+var_48]
0x180015d97  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015d9c  mov     rax, rbx
0x180015d9f  lea     r11, [rsp+80h+var_s0]
0x180015da7  mov     rbx, [r11+28h]
0x180015dab  mov     rsi, [r11+30h]
0x180015daf  mov     rdi, [r11+38h]
0x180015db3  mov     rsp, r11
0x180015db6  pop     r15
0x180015db8  pop     r14
0x180015dba  pop     rbp
0x180015dbb  retn
0x180015dbc  mov     r8, rbx; struct std::error_code *
0x180015dbf  lea     rdx, [rbp+var_60]; char *
0x180015dc3  lea     rcx, aCreateDirector; "create_directories"
0x180015dca  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x180015dd0  mov     r8, rbx; struct std::error_code *
0x180015dd3  lea     rdx, [rbp+var_60]; char *
0x180015dd7  lea     rcx, aExists; "exists"
0x180015dde  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
