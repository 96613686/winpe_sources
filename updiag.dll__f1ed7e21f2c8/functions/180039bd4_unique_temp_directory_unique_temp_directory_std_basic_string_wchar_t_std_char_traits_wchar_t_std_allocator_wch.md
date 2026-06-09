# unique_temp_directory::unique_temp_directory(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180039bd4`
- end: `0x180039d9d`
- name: `??0unique_temp_directory@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `457`
- prototype: `struct std::error_code *__fastcall(struct std::error_code *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180039e64`

## callees

- `0x180018d28`
- `0x180018eec`
- `0x180039bd4`
- `0x180061b98`
- `0x180064504`
- `0x180064774`
- `0x180066034`
- `0x18006704c`
- `0x1800691dc`
- `0x180069224`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180039c29`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180039c29`

## string_xrefs

- `0x180039d90`: `create_directories`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct std::error_code *__fastcall unique_temp_directory::unique_temp_directory(struct std::error_code *a1)
{
  _WORD *v2; // rdx
  __int64 v3; // rax
  __int128 *v4; // rax
  __int64 v5; // rdi
  struct std::error_code *v6; // r8
  const struct std::filesystem::path *v7; // r9
  char v9[8]; // [rsp+20h] [rbp-79h] BYREF
  void ***v10; // [rsp+28h] [rbp-71h]
  _BYTE Src[32]; // [rsp+30h] [rbp-69h] BYREF
  struct std::error_code *v12; // [rsp+50h] [rbp-49h]
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp-41h] BYREF
  __int128 v14; // [rsp+60h] [rbp-39h] BYREF
  __int128 v15; // [rsp+70h] [rbp-29h]
  _BYTE v16[32]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v17[42]; // [rsp+A0h] [rbp+7h] BYREF
  _BYTE v18[6]; // [rsp+CAh] [rbp+31h] BYREF

  v12 = a1;
  *(_OWORD *)a1 = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 7;
  *(_WORD *)a1 = 0;
  *((_BYTE *)a1 + 32) = 1;
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  if ( PerformanceCount.QuadPart >= 0 )
  {
    v2 = (_WORD *)std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v18);
  }
  else
  {
    v2 = (_WORD *)(std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v18) - 2);
    *v2 = 45;
  }
  std::wstring::wstring(Src, v2, v18);
  v3 = std::wstring::insert(Src);
  v14 = 0;
  v15 = 0;
  v14 = *(_OWORD *)v3;
  v15 = *(_OWORD *)(v3 + 16);
  *(_WORD *)v3 = 0;
  *(_QWORD *)(v3 + 16) = 0;
  *(_QWORD *)(v3 + 24) = 7;
  std::wstring::~wstring(Src);
  std::filesystem::temp_directory_path(v16);
  v4 = &v14;
  if ( *((_QWORD *)&v15 + 1) > 7u )
    v4 = (__int128 *)v14;
  *(_QWORD *)v9 = v4;
  v10 = (void ***)v15;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(Src, v9);
  v5 = std::filesystem::operator/(v17, v16, Src);
  if ( a1 != (struct std::error_code *)v5 )
  {
    std::wstring::~wstring(a1);
    *(_OWORD *)a1 = *(_OWORD *)v5;
    *((_OWORD *)a1 + 1) = *(_OWORD *)(v5 + 16);
    *(_QWORD *)(v5 + 16) = 0;
    *(_QWORD *)(v5 + 24) = 7;
    *(_WORD *)v5 = 0;
  }
  std::wstring::~wstring(v17);
  std::wstring::~wstring(Src);
  *(_QWORD *)v9 = 0;
  v10 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  std::filesystem::create_directories(a1, (const struct std::filesystem::path *)v9, v6);
  if ( *(_DWORD *)v9 )
    std::filesystem::_Throw_fs_error((std::filesystem *)"create_directories", v9, a1, v7);
  std::wstring::~wstring(v16);
  std::wstring::~wstring(&v14);
  return a1;
}

```

## disassembly

```asm
0x180039bd4  mov     [rsp-8+arg_10], rbx
0x180039bd9  mov     [rsp-8+arg_18], rsi
0x180039bde  push    rbp
0x180039bdf  push    rdi
0x180039be0  push    r14
0x180039be2  lea     rbp, [rsp-47h]
0x180039be7  sub     rsp, 0E0h
0x180039bee  mov     rax, cs:__security_cookie
0x180039bf5  xor     rax, rsp
0x180039bf8  mov     [rbp+57h+var_20], rax
0x180039bfc  mov     rdi, rdx
0x180039bff  mov     rbx, rcx
0x180039c02  mov     [rbp+57h+var_A0], rcx
0x180039c06  xor     esi, esi
0x180039c08  xorps   xmm0, xmm0
0x180039c0b  movups  xmmword ptr [rcx], xmm0
0x180039c0e  mov     [rcx+10h], rsi
0x180039c12  lea     r14d, [rsi+7]
0x180039c16  mov     [rcx+18h], r14
0x180039c1a  mov     [rcx], si
0x180039c1d  mov     byte ptr [rcx+20h], 1
0x180039c21  mov     qword ptr [rbp+57h+PerformanceCount], rsi
0x180039c25  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180039c29  call    cs:__imp_QueryPerformanceCounter
0x180039c2f  mov     rdx, qword ptr [rbp+57h+PerformanceCount]
0x180039c33  lea     rcx, [rbp+57h+var_26]
0x180039c37  test    rdx, rdx
0x180039c3a  jns     short loc_180039C4F
0x180039c3c  neg     rdx
0x180039c3f  call    ??$_UIntegral_to_buff@_W_K@std@@YAPEA_WPEA_W_K@Z; std::_UIntegral_to_buff<wchar_t,unsigned __int64>(wchar_t *,unsigned __int64)
0x180039c44  lea     rdx, [rax-2]
0x180039c48  mov     word ptr [rdx], 2Dh ; '-'
0x180039c4d  jmp     short loc_180039C57
0x180039c4f  call    ??$_UIntegral_to_buff@_W_K@std@@YAPEA_WPEA_W_K@Z; std::_UIntegral_to_buff<wchar_t,unsigned __int64>(wchar_t *,unsigned __int64)
0x180039c54  mov     rdx, rax
0x180039c57  lea     r8, [rbp+57h+var_26]
0x180039c5b  lea     rcx, [rbp+57h+Src]
0x180039c5f  call    ??$?0PEA_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEA_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t *,wchar_t *,std::allocator<wchar_t> const &)
0x180039c64  nop
0x180039c65  mov     r9, [rdi+10h]
0x180039c69  cmp     [rdi+18h], r14
0x180039c6d  jbe     short loc_180039C72
0x180039c6f  mov     rdi, [rdi]
0x180039c72  mov     r8, rdi
0x180039c75  lea     rcx, [rbp+57h+Src]; Src
0x180039c79  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_KQEB_W0@Z; std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)
0x180039c7e  xorps   xmm0, xmm0
0x180039c81  movups  [rbp+57h+var_90], xmm0
0x180039c85  xorps   xmm1, xmm1
0x180039c88  movdqu  [rbp+57h+var_80], xmm1
0x180039c8d  movups  xmm0, xmmword ptr [rax]
0x180039c90  movups  [rbp+57h+var_90], xmm0
0x180039c94  movups  xmm1, xmmword ptr [rax+10h]
0x180039c98  movups  [rbp+57h+var_80], xmm1
0x180039c9c  mov     [rax], si
0x180039c9f  mov     [rax+10h], rsi
0x180039ca3  mov     [rax+18h], r14
0x180039ca7  lea     rcx, [rbp+57h+Src]
0x180039cab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039cb0  lea     rcx, [rbp+57h+var_70]
0x180039cb4  call    ?temp_directory_path@filesystem@std@@YA?AVpath@12@XZ; std::filesystem::temp_directory_path(void)
0x180039cb9  nop
0x180039cba  lea     rax, [rbp+57h+var_90]
0x180039cbe  cmp     qword ptr [rbp+57h+var_80+8], r14
0x180039cc2  cmova   rax, qword ptr [rbp+57h+var_90]
0x180039cc7  mov     qword ptr [rbp+57h+var_D0], rax
0x180039ccb  mov     rax, qword ptr [rbp+57h+var_80]
0x180039ccf  mov     [rbp+57h+var_C8], rax
0x180039cd3  lea     rdx, [rbp+57h+var_D0]
0x180039cd7  lea     rcx, [rbp+57h+Src]
0x180039cdb  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x180039ce0  nop
0x180039ce1  lea     r8, [rbp+57h+Src]; void *
0x180039ce5  lea     rdx, [rbp+57h+var_70]; void *
0x180039ce9  lea     rcx, [rbp+57h+var_50]; Src
0x180039ced  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180039cf2  mov     rdi, rax
0x180039cf5  cmp     rbx, rax
0x180039cf8  jz      short loc_180039D1B
0x180039cfa  mov     rcx, rbx
0x180039cfd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039d02  movups  xmm0, xmmword ptr [rdi]
0x180039d05  movups  xmmword ptr [rbx], xmm0
0x180039d08  movups  xmm1, xmmword ptr [rdi+10h]
0x180039d0c  movups  xmmword ptr [rbx+10h], xmm1
0x180039d10  mov     [rdi+10h], rsi
0x180039d14  mov     [rdi+18h], r14
0x180039d18  mov     [rdi], si
0x180039d1b  lea     rcx, [rbp+57h+var_50]
0x180039d1f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039d24  nop
0x180039d25  lea     rcx, [rbp+57h+Src]
0x180039d29  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039d2e  mov     qword ptr [rbp+57h+var_D0], rsi
0x180039d32  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180039d39  mov     [rbp+57h+var_C8], rax
0x180039d3d  lea     rdx, [rbp+57h+var_D0]; struct std::filesystem::path *
0x180039d41  mov     rcx, rbx; this
0x180039d44  call    ?create_directories@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::create_directories(std::filesystem::path const &,std::error_code &)
0x180039d49  cmp     dword ptr [rbp+57h+var_D0], esi
0x180039d4c  jnz     short loc_180039D89
0x180039d4e  lea     rcx, [rbp+57h+var_70]
0x180039d52  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039d57  nop
0x180039d58  lea     rcx, [rbp+57h+var_90]
0x180039d5c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039d61  nop
0x180039d62  mov     rax, rbx
0x180039d65  mov     rcx, [rbp+57h+var_20]
0x180039d69  xor     rcx, rsp; StackCookie
0x180039d6c  call    __security_check_cookie
0x180039d71  lea     r11, [rsp+0F0h+var_10]
0x180039d79  mov     rbx, [r11+30h]
0x180039d7d  mov     rsi, [r11+38h]
0x180039d81  mov     rsp, r11
0x180039d84  pop     r14
0x180039d86  pop     rdi
0x180039d87  pop     rbp
0x180039d88  retn
0x180039d89  mov     r8, rbx; struct std::error_code *
0x180039d8c  lea     rdx, [rbp+57h+var_D0]; char *
0x180039d90  lea     rcx, aCreateDirector; "create_directories"
0x180039d97  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
```
