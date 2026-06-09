# UusExclusion::Load(std::filesystem::path,std::optional<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>)

- ea: `0x180032fc8`
- end: `0x18003325c`
- name: `?Load@UusExclusion@@CA?AVvalue@json@web@@Vpath@filesystem@std@@V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@7@@Z`
- size: `660`
- prototype: `__int64 __fastcall(web::json::value *this, struct std::error_code *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180032760`

## callees

- `0x18000f914`
- `0x180017784`
- `0x1800240ac`
- `0x180024a44`
- `0x180027228`
- `0x1800286d0`
- `0x180029644`
- `0x1800296cc`
- `0x1800298d4`
- `0x18002dd88`
- `0x180032fc8`
- `0x1800427d0`
- `0x180047a30`
- `0x180047ab0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
web::json::value *__fastcall UusExclusion::Load(web::json::value *this, struct std::error_code *a2, __int64 a3)
{
  bool v6; // al
  const struct std::filesystem::path *v7; // r9
  struct std::error_code *v8; // rdx
  __int64 v9; // rax
  wchar_t *v11; // rax
  char v12[8]; // [rsp+30h] [rbp-178h] BYREF
  void ***v13; // [rsp+38h] [rbp-170h]
  web::json::value *v14; // [rsp+48h] [rbp-160h]
  __int64 v15; // [rsp+58h] [rbp-150h]
  struct std::error_code *v16; // [rsp+60h] [rbp-148h]
  int v17; // [rsp+6Ch] [rbp-13Ch]
  _QWORD v18[34]; // [rsp+70h] [rbp-138h] BYREF

  v14 = this;
  v16 = a2;
  v15 = a3;
  *(_QWORD *)v12 = 0;
  v13 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v6 = std::filesystem::exists(a2, (const struct std::filesystem::path *)v12, (struct std::error_code *)a3);
  if ( *(_DWORD *)v12 )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v12, a2, v7);
  if ( v6 )
  {
    memset(v18, 0, sizeof(v18));
    v8 = a2;
    if ( *((_QWORD *)a2 + 3) > 7u )
      v8 = *(struct std::error_code **)a2;
    std::wifstream::wifstream(v18, v8);
    *(_QWORD *)((char *)v18 + *(int *)(v18[0] + 4LL)) = &std::wifstream::`vftable';
    *(int *)((char *)&v17 + *(int *)(v18[0] + 4LL)) = *(_DWORD *)(v18[0] + 4LL) - 176;
    *(_QWORD *)v12 = 0;
    web::json::value::parse(v12, (__int64)v18);
    if ( !*(_BYTE *)(a3 + 32) )
    {
      v9 = *(_QWORD *)v12;
      *(_QWORD *)v12 = 0;
      *(_QWORD *)this = v9;
      std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(&v18[22]);
      v18[22] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v18[22]);
      std::wstring::_Tidy_deallocate((__int64)a2);
      if ( *(_BYTE *)(a3 + 32) )
        std::wstring::_Tidy_deallocate(a3);
      return this;
    }
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12, a3) )
    {
      if ( !*(_BYTE *)(a3 + 32) )
        std::_Throw_bad_optional_access();
      v11 = web::json::value::at(v12, a3);
      (***(void (__fastcall ****)(_QWORD, web::json::value *))v11)(*(_QWORD *)v11, this);
      if ( *(_QWORD *)v12 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v12 + 192LL))(*(_QWORD *)v12, 1);
      std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(&v18[22]);
      v18[22] = &std::wios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v18[22]);
      std::wstring::_Tidy_deallocate((__int64)a2);
      if ( *(_BYTE *)(a3 + 32) )
        std::wstring::_Tidy_deallocate(a3);
      return this;
    }
    if ( *(_QWORD *)v12 )
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v12 + 192LL))(*(_QWORD *)v12, 1);
    std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(&v18[22]);
    v18[22] = &std::wios::`vftable';
    std::ios_base::~ios_base((std::ios_base *)&v18[22]);
  }
  web::json::value::value(this);
  std::wstring::_Tidy_deallocate((__int64)a2);
  if ( *(_BYTE *)(a3 + 32) )
    std::wstring::_Tidy_deallocate(a3);
  return this;
}

```

## disassembly

```asm
0x180032fc8  push    rsi
0x180032fca  push    rdi
0x180032fcb  push    r14
0x180032fcd  sub     rsp, 190h
0x180032fd4  mov     rax, cs:__security_cookie
0x180032fdb  xor     rax, rsp
0x180032fde  mov     [rsp+1A8h+var_28], rax
0x180032fe6  mov     rdi, r8
0x180032fe9  mov     rsi, rdx
0x180032fec  mov     r14, rcx
0x180032fef  mov     [rsp+1A8h+var_160], rcx
0x180032ff4  mov     [rsp+1A8h+var_148], rdx
0x180032ff9  mov     [rsp+1A8h+var_150], r8
0x180032ffe  mov     qword ptr [rsp+1A8h+var_178], 0
0x180033007  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18003300e  mov     [rsp+1A8h+var_170], rax
0x180033013  lea     rdx, [rsp+1A8h+var_178]; struct std::filesystem::path *
0x180033018  mov     rcx, rsi; this
0x18003301b  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x180033020  cmp     dword ptr [rsp+1A8h+var_178], 0
0x180033025  jnz     loc_180033240
0x18003302b  test    al, al
0x18003302d  jz      loc_180033201
0x180033033  xor     edx, edx; Val
0x180033035  mov     r8d, 110h; Size
0x18003303b  lea     rcx, [rsp+1A8h+var_138]; void *
0x180033040  call    memset
0x180033045  mov     rdx, rsi
0x180033048  cmp     qword ptr [rsi+18h], 7
0x18003304d  jbe     short loc_180033052
0x18003304f  mov     rdx, [rsi]
0x180033052  lea     rcx, [rsp+1A8h+var_138]
0x180033057  call    ??0?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@QEAA@PEB_WHH@Z; std::wifstream::wifstream(wchar_t const *,int,int)
0x18003305c  mov     rax, [rsp+1A8h+var_138]
0x180033061  movsxd  rcx, dword ptr [rax+4]
0x180033065  lea     rax, ??_7?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@6B@; const std::wifstream::`vftable'
0x18003306c  mov     [rsp+rcx+1A8h+var_138], rax
0x180033071  mov     rax, [rsp+1A8h+var_138]
0x180033076  movsxd  rcx, dword ptr [rax+4]
0x18003307a  lea     edx, [rcx-0B0h]
0x180033080  mov     [rsp+rcx+1A8h+var_13C], edx
0x180033084  mov     qword ptr [rsp+1A8h+var_178], 0
0x18003308d  lea     rdx, [rsp+1A8h+var_138]
0x180033092  lea     rcx, [rsp+1A8h+var_178]
0x180033097  call    ?parse@value@json@web@@SA?AV123@AEAV?$basic_istream@_WU?$char_traits@_W@std@@@std@@@Z; web::json::value::parse(std::wistream &)
0x18003309c  nop
0x18003309d  cmp     byte ptr [rdi+20h], 0
0x1800330a1  jnz     short loc_1800330FD
0x1800330a3  mov     rax, qword ptr [rsp+1A8h+var_178]
0x1800330a8  mov     qword ptr [rsp+1A8h+var_178], 0
0x1800330b1  mov     [r14], rax
0x1800330b4  lea     rcx, [rsp+1A8h+var_88]
0x1800330bc  call    ??1?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(void)
0x1800330c1  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x1800330c8  mov     [rsp+1A8h+var_88], rax
0x1800330d0  lea     rcx, [rsp+1A8h+var_88]; this
0x1800330d8  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x1800330dd  nop
0x1800330de  mov     rcx, rsi
0x1800330e1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800330e6  nop
0x1800330e7  cmp     byte ptr [rdi+20h], 0
0x1800330eb  jz      short loc_1800330F5
0x1800330ed  mov     rcx, rdi
0x1800330f0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800330f5  mov     rax, r14
0x1800330f8  jmp     loc_180033224
0x1800330fd  mov     rcx, qword ptr [rsp+1A8h+var_178]
0x180033102  mov     rax, [rcx]
0x180033105  mov     rdx, rdi
0x180033108  mov     rax, [rax+8]
0x18003310c  call    _guard_dispatch_icall
0x180033111  test    al, al
0x180033113  jz      loc_1800331A7
0x180033119  cmp     byte ptr [rdi+20h], 0
0x18003311d  jz      loc_180033255
0x180033123  mov     rdx, rdi
0x180033126  lea     rcx, [rsp+1A8h+var_178]
0x18003312b  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180033130  mov     rcx, [rax]
0x180033133  mov     rax, [rcx]
0x180033136  mov     rdx, r14
0x180033139  mov     rax, [rax]
0x18003313c  call    _guard_dispatch_icall
0x180033141  nop
0x180033142  mov     rcx, qword ptr [rsp+1A8h+var_178]
0x180033147  test    rcx, rcx
0x18003314a  jz      short loc_180033161
0x18003314c  mov     rax, [rcx]
0x18003314f  mov     edx, 1
0x180033154  mov     rax, [rax+0C0h]
0x18003315b  call    _guard_dispatch_icall
0x180033160  nop
0x180033161  lea     rcx, [rsp+1A8h+var_88]
0x180033169  call    ??1?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(void)
0x18003316e  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x180033175  mov     [rsp+1A8h+var_88], rax
0x18003317d  lea     rcx, [rsp+1A8h+var_88]; this
0x180033185  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18003318a  nop
0x18003318b  mov     rcx, rsi
0x18003318e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033193  nop
0x180033194  cmp     byte ptr [rdi+20h], 0
0x180033198  jz      short loc_1800331A2
0x18003319a  mov     rcx, rdi
0x18003319d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800331a2  mov     rax, r14
0x1800331a5  jmp     short loc_180033224
0x1800331a7  mov     rcx, qword ptr [rsp+1A8h+var_178]
0x1800331ac  test    rcx, rcx
0x1800331af  jz      short loc_1800331C6
0x1800331b1  mov     rax, [rcx]
0x1800331b4  mov     edx, 1
0x1800331b9  mov     rax, [rax+0C0h]
0x1800331c0  call    _guard_dispatch_icall
0x1800331c5  nop
0x1800331c6  lea     rcx, [rsp+1A8h+var_88]
0x1800331ce  call    ??1?$basic_ifstream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wifstream::~wifstream<wchar_t,std::char_traits<wchar_t>>(void)
0x1800331d3  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x1800331da  mov     [rsp+1A8h+var_88], rax
0x1800331e2  lea     rcx, [rsp+1A8h+var_88]; this
0x1800331ea  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x1800331ef  nop
0x1800331f0  jmp     short loc_180033201
0x1800331f2  mov     r14, [rsp+1A8h+var_160]
0x1800331f7  mov     rsi, [rsp+1A8h+var_148]
0x1800331fc  mov     rdi, [rsp+1A8h+var_150]
0x180033201  mov     rcx, r14; this
0x180033204  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x180033209  nop
0x18003320a  mov     rcx, rsi
0x18003320d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033212  nop
0x180033213  cmp     byte ptr [rdi+20h], 0
0x180033217  jz      short loc_180033221
0x180033219  mov     rcx, rdi
0x18003321c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033221  mov     rax, r14
0x180033224  mov     rcx, [rsp+1A8h+var_28]
0x18003322c  xor     rcx, rsp; StackCookie
0x18003322f  call    __security_check_cookie
0x180033234  add     rsp, 190h
0x18003323b  pop     r14
0x18003323d  pop     rdi
0x18003323e  pop     rsi
0x18003323f  retn
0x180033240  mov     r8, rsi; struct std::error_code *
0x180033243  lea     rdx, [rsp+1A8h+var_178]; char *
0x180033248  lea     rcx, aExists; "exists"
0x18003324f  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x180033255  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
```
