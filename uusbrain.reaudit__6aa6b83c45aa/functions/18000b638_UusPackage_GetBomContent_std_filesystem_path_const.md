# UusPackage::GetBomContent(std::filesystem::path const &)

- ea: `0x18000b638`
- end: `0x18000b9cd`
- name: `?GetBomContent@UusPackage@@CA?AVvalue@json@web@@AEBVpath@filesystem@std@@@Z`
- size: `917`
- prototype: `static struct web::json::value __high(const struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, installer_update`

## callers

- `0x18000ab24`

## callees

- `0x180008e30`
- `0x180009e1c`
- `0x18000b638`
- `0x18000b9d4`
- `0x18000dca4`
- `0x18000e4f0`
- `0x18000e668`
- `0x1800110c4`
- `0x180011d08`
- `0x180011d2c`
- `0x180011e0c`
- `0x1800124cc`
- `0x180012638`
- `0x1800127a4`
- `0x180018520`
- `0x1800186a8`
- `0x18001c550`
- `0x1800240ac`
- `0x180027228`
- `0x180028424`
- `0x1800286d0`
- `0x180029344`
- `0x18002df20`
- `0x1800424e6`
- `0x180042760`
- `0x1800427d0`
- `0x180044848`
- `0x180047ab0`

## string_xrefs

- `0x18000b8ad`: `Unable to open BOM file `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UusPackage::GetBomContent(__int64 a1, std::filesystem *a2, struct std::error_code *a3)
{
  bool v5; // al
  const struct std::filesystem::path *v6; // r9
  char *FileContentWin32A; // rbx
  __int64 v8; // rax
  wil *v9; // rcx
  const wchar_t *v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rbx
  int *v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rbx
  unsigned int *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  const char *v25; // rax
  int v26; // eax
  unsigned int v27; // [rsp+30h] [rbp-598h]
  char v31[8]; // [rsp+58h] [rbp-570h] BYREF
  void ***v32; // [rsp+60h] [rbp-568h]
  _BYTE v33[24]; // [rsp+78h] [rbp-550h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+90h] [rbp-538h] BYREF
  char v35[152]; // [rsp+A8h] [rbp-520h] BYREF
  _QWORD v36[12]; // [rsp+140h] [rbp-488h] BYREF
  _QWORD v37[32]; // [rsp+1A0h] [rbp-428h] BYREF
  _QWORD v38[34]; // [rsp+2A0h] [rbp-328h] BYREF
  _BYTE v39[16]; // [rsp+3B0h] [rbp-218h] BYREF
  _BYTE v40[240]; // [rsp+3C0h] [rbp-208h] BYREF
  char Buffer[256]; // [rsp+4B0h] [rbp-118h] BYREF

  *(_QWORD *)v31 = 0;
  v32 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v5 = std::filesystem::exists(a2, (const struct std::filesystem::path *)v31, a3);
  if ( *(_DWORD *)v31 )
    std::filesystem::_Throw_fs_error((std::filesystem *)"exists", v31, a2, v6);
  if ( !v5 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v33, "BOM file not found.");
    throw (std::runtime_error *)v33;
  }
  memset(v37, 0, 0xF8u);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v37);
  try
  {
    FileContentWin32A = UusPackage::GetFileContentWin32A(v35, (const WCHAR *)a2);
    if ( v37 != (_QWORD *)FileContentWin32A )
    {
      std::iostream::swap(v37, FileContentWin32A);
      std::stringbuf::_Tidy(&v37[3]);
      v8 = *((_QWORD *)FileContentWin32A + 16);
      *((_QWORD *)FileContentWin32A + 16) = 0;
      v37[16] = v8;
      LODWORD(v8) = *((_DWORD *)FileContentWin32A + 34);
      *((_DWORD *)FileContentWin32A + 34) = 0;
      LODWORD(v37[17]) = v8;
      std::streambuf::swap(&v37[3], FileContentWin32A + 24);
    }
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v36);
    v36[0] = &std::wios::`vftable';
    std::ios_base::~ios_base((std::ios_base *)v36);
  }
  catch ( ... )
  {
    v26 = wil::ResultFromCaughtException(v9);
    if ( v26 >= 0 )
      v26 = -2147467259;
    v27 = v26;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(&v37[19]);
    v37[19] = &std::wios::`vftable';
    std::ios_base::~ios_base((std::ios_base *)&v37[19]);
    memset(v38, 0, sizeof(v38));
    v11 = (const wchar_t *)a2;
    std::ifstream::ifstream(v38, a2);
    if ( !v38[18] )
    {
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::__autoclassinit2(v39);
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v39);
      v12 = std::operator<<<std::char_traits<char>>(v40, "Unable to open BOM file ");
      v13 = std::filesystem::operator<<<char,std::char_traits<char>>(v12, a2);
      v14 = std::operator<<<std::char_traits<char>>(v13, ": ");
      v15 = (int *)o__errno_0();
      v16 = strerror_s(Buffer, 0x100u, *v15);
      v17 = std::ostream::operator<<(v14, v16);
      v18 = std::operator<<<std::char_traits<char>>(v17, " (");
      v19 = (unsigned int *)o__errno_0();
      v20 = std::ostream::operator<<(v18, *v19);
      v21 = std::operator<<<std::char_traits<char>>(v20, " / WIN32=0x");
      v22 = std::ostream::operator<<(v21);
      v23 = std::ostream::operator<<(v22, v27);
      std::operator<<<std::char_traits<char>>(v23, ")");
      v24 = std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(v39, v31);
      v25 = (const char *)std::string::c_str(v24);
      std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, v25);
      throw (std::runtime_error *)pExceptionObject;
    }
    if ( *((_QWORD *)a2 + 3) > 7u )
      v11 = *(const wchar_t **)a2;
    uus::UndockedUpdateTelemetry::UusPackageIntermittentFailure(v11, v27);
    web::json::value::parse(a1, v38);
    std::ifstream::~ifstream<char,std::char_traits<char>>(&v38[22]);
    v38[22] = &std::wios::`vftable';
    std::ios_base::~ios_base((std::ios_base *)&v38[22]);
    return a1;
  }
  web::json::value::parse(a1, v37);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(&v37[19]);
  v37[19] = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)&v37[19]);
  return a1;
}

```

## disassembly

```asm
0x18000b638  mov     [rsp+arg_10], rbx
0x18000b63d  push    rsi
0x18000b63e  sub     rsp, 5C0h
0x18000b645  mov     rax, cs:__security_cookie
0x18000b64c  xor     rax, rsp
0x18000b64f  mov     [rsp+5C8h+var_18], rax
0x18000b657  mov     rbx, rdx
0x18000b65a  mov     rsi, rcx
0x18000b65d  mov     [rsp+5C8h+var_578], rdx
0x18000b662  mov     [rsp+5C8h+var_590], rcx
0x18000b667  mov     [rsp+5C8h+var_580], rdx
0x18000b66c  mov     qword ptr [rsp+5C8h+var_570], 0
0x18000b675  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18000b67c  mov     [rsp+5C8h+var_568], rax
0x18000b681  lea     rdx, [rsp+5C8h+var_570]; struct std::filesystem::path *
0x18000b686  mov     rcx, rbx; this
0x18000b689  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x18000b68e  cmp     dword ptr [rsp+5C8h+var_570], 0
0x18000b693  jnz     loc_18000B995
0x18000b699  test    al, al
0x18000b69b  jz      loc_18000B9AA
0x18000b6a1  xor     edx, edx; Val
0x18000b6a3  mov     r8d, 0F8h; Size
0x18000b6a9  lea     rcx, [rsp+5C8h+var_428]; void *
0x18000b6b1  call    memset
0x18000b6b6  lea     rcx, [rsp+5C8h+var_428]
0x18000b6be  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18000b6c3  nop
0x18000b6c4  mov     rdx, rbx; lpFileName
0x18000b6c7  lea     rcx, [rsp+5C8h+var_520]; void *
0x18000b6cf  call    ?GetFileContentWin32A@UusPackage@@CA?AV?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVpath@filesystem@3@@Z; UusPackage::GetFileContentWin32A(std::filesystem::path const &)
0x18000b6d4  mov     rbx, rax
0x18000b6d7  lea     rax, [rsp+5C8h+var_428]
0x18000b6df  cmp     rax, rbx
0x18000b6e2  jz      short loc_18000B743
0x18000b6e4  mov     rdx, rbx
0x18000b6e7  lea     rcx, [rsp+5C8h+var_428]
0x18000b6ef  call    ?swap@?$basic_iostream@DU?$char_traits@D@std@@@std@@IEAAXAEAV12@@Z; std::iostream::swap(std::iostream &)
0x18000b6f4  lea     rcx, [rsp+5C8h+var_410]
0x18000b6fc  call    ?_Tidy@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IEAAXXZ; std::stringbuf::_Tidy(void)
0x18000b701  mov     rax, [rbx+80h]
0x18000b708  mov     qword ptr [rbx+80h], 0
0x18000b713  mov     [rsp+5C8h+var_3A8], rax
0x18000b71b  mov     eax, [rbx+88h]
0x18000b721  mov     dword ptr [rbx+88h], 0
0x18000b72b  mov     [rsp+5C8h+var_3A0], eax
0x18000b732  lea     rdx, [rbx+18h]
0x18000b736  lea     rcx, [rsp+5C8h+var_410]
0x18000b73e  call    ?swap@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXAEAV12@@Z; std::streambuf::swap(std::streambuf &)
0x18000b743  lea     rcx, [rsp+5C8h+var_488]
0x18000b74b  call    ??1?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18000b750  lea     rbx, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18000b757  mov     [rsp+5C8h+var_488], rbx
0x18000b75f  lea     rcx, [rsp+5C8h+var_488]; this
0x18000b767  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18000b76c  nop
0x18000b76d  jmp     short loc_18000B782
0x18000b76f  cmp     [rsp+5C8h+var_598], 0
0x18000b774  jl      short loc_18000B7D9
0x18000b776  lea     rbx, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18000b77d  mov     rsi, [rsp+5C8h+var_590]
0x18000b782  lea     rdx, [rsp+5C8h+var_428]
0x18000b78a  mov     rcx, rsi
0x18000b78d  call    ?parse@value@json@web@@SA?AV123@AEAV?$basic_istream@DU?$char_traits@D@std@@@std@@@Z; web::json::value::parse(std::istream &)
0x18000b792  nop
0x18000b793  lea     rcx, [rsp+5C8h+var_390]
0x18000b79b  call    ??1?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18000b7a0  mov     [rsp+5C8h+var_390], rbx
0x18000b7a8  lea     rcx, [rsp+5C8h+var_390]; this
0x18000b7b0  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18000b7b5  mov     rax, rsi
0x18000b7b8  mov     rcx, [rsp+5C8h+var_18]
0x18000b7c0  xor     rcx, rsp; StackCookie
0x18000b7c3  call    __security_check_cookie
0x18000b7c8  mov     rbx, [rsp+5C8h+arg_10]
0x18000b7d0  add     rsp, 5C0h
0x18000b7d7  pop     rsi
0x18000b7d8  retn
0x18000b7d9  lea     rcx, [rsp+5C8h+var_390]
0x18000b7e1  call    ??1?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18000b7e6  lea     rbx, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18000b7ed  mov     [rsp+5C8h+var_390], rbx
0x18000b7f5  lea     rcx, [rsp+5C8h+var_390]; this
0x18000b7fd  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18000b802  xor     edx, edx; Val
0x18000b804  mov     r8d, 110h; Size
0x18000b80a  lea     rcx, [rsp+5C8h+var_328]; void *
0x18000b812  call    memset
0x18000b817  mov     rsi, [rsp+5C8h+var_580]
0x18000b81c  mov     rdx, rsi
0x18000b81f  lea     rcx, [rsp+5C8h+var_328]
0x18000b827  call    ??$?0Vpath@filesystem@std@@$0A@@?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@AEBVpath@filesystem@1@HH@Z; std::ifstream::ifstream(std::filesystem::path const &,int,int)
0x18000b82c  nop
0x18000b82d  cmp     [rsp+5C8h+var_298], 0
0x18000b836  jz      short loc_18000B892
0x18000b838  cmp     qword ptr [rsi+18h], 7
0x18000b83d  jbe     short loc_18000B847
0x18000b83f  mov     rax, [rsp+5C8h+var_578]
0x18000b844  mov     rsi, [rax]
0x18000b847  mov     edx, [rsp+5C8h+var_598]; int
0x18000b84b  mov     rcx, rsi; wchar_t *
0x18000b84e  call    ?UusPackageIntermittentFailure@UndockedUpdateTelemetry@uus@@SAXPEB_WJ@Z; uus::UndockedUpdateTelemetry::UusPackageIntermittentFailure(wchar_t const *,long)
0x18000b853  lea     rdx, [rsp+5C8h+var_328]
0x18000b85b  mov     rcx, [rsp+5C8h+var_590]
0x18000b860  call    ?parse@value@json@web@@SA?AV123@AEAV?$basic_istream@DU?$char_traits@D@std@@@std@@@Z; web::json::value::parse(std::istream &)
0x18000b865  nop
0x18000b866  lea     rcx, [rsp+5C8h+var_278]
0x18000b86e  call    ??1?$basic_ifstream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ifstream::~ifstream<char,std::char_traits<char>>(void)
0x18000b873  mov     [rsp+5C8h+var_278], rbx
0x18000b87b  lea     rcx, [rsp+5C8h+var_278]; this
0x18000b883  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18000b888  mov     rax, [rsp+5C8h+var_590]
0x18000b88d  jmp     loc_18000B7B8
0x18000b892  lea     rcx, [rsp+5C8h+var_218]
0x18000b89a  call    ?__autoclassinit2@?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::__autoclassinit2(unsigned __int64)
0x18000b89f  lea     rcx, [rsp+5C8h+var_218]
0x18000b8a7  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18000b8ac  nop
0x18000b8ad  lea     rdx, aUnableToOpenBo; "Unable to open BOM file "
0x18000b8b4  lea     rcx, [rsp+5C8h+var_208]
0x18000b8bc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18000b8c1  mov     rcx, rax
0x18000b8c4  mov     rdx, rsi
0x18000b8c7  call    ??$?6DU?$char_traits@D@std@@@filesystem@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@1@AEAV21@AEBVpath@01@@Z; std::filesystem::operator<<<char,std::char_traits<char>>(std::ostream &,std::filesystem::path const &)
0x18000b8cc  mov     rcx, rax
0x18000b8cf  lea     rdx, asc_180051F80; ": "
0x18000b8d6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18000b8db  mov     rbx, rax
0x18000b8de  call    _o__errno_0
0x18000b8e3  mov     r8d, [rax]; ErrorNumber
0x18000b8e6  mov     edx, 100h; SizeInBytes
0x18000b8eb  lea     rcx, [rsp+5C8h+Buffer]; Buffer
0x18000b8f3  call    strerror_s
0x18000b8f8  mov     edx, eax
0x18000b8fa  mov     rcx, rbx
0x18000b8fd  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z; std::ostream::operator<<(int)
0x18000b902  mov     rcx, rax
0x18000b905  lea     rdx, asc_1800511FC; " ("
0x18000b90c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18000b911  mov     rbx, rax
0x18000b914  call    _o__errno_0
0x18000b919  mov     edx, [rax]
0x18000b91b  mov     rcx, rbx
0x18000b91e  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z; std::ostream::operator<<(int)
0x18000b923  mov     rcx, rax
0x18000b926  lea     rdx, aWin320x; " / WIN32=0x"
0x18000b92d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18000b932  mov     rcx, rax
0x18000b935  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18000b93a  mov     edx, [rsp+5C8h+var_598]
0x18000b93e  mov     rcx, rax
0x18000b941  call    ??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18000b946  mov     rcx, rax
0x18000b949  lea     rdx, asc_1800511EC; ")"
0x18000b950  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18000b955  lea     rdx, [rsp+5C8h+var_570]
0x18000b95a  lea     rcx, [rsp+5C8h+var_218]
0x18000b962  call    ?str@?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(void)
0x18000b967  nop
0x18000b968  mov     rcx, rax
0x18000b96b  call    ?c_str@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAPEBDXZ; std::string::c_str(void)
0x18000b970  mov     rdx, rax; char *
0x18000b973  lea     rcx, [rsp+5C8h+pExceptionObject]; this
0x18000b97b  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000b980  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000b987  lea     rcx, [rsp+5C8h+pExceptionObject]; pExceptionObject
0x18000b98f  call    _CxxThrowException
0x18000b995  mov     r8, rbx; struct std::error_code *
0x18000b998  lea     rdx, [rsp+5C8h+var_570]; char *
0x18000b99d  lea     rcx, aExists; "exists"
0x18000b9a4  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x18000b9aa  lea     rdx, aBomFileNotFoun; "BOM file not found."
0x18000b9b1  lea     rcx, [rsp+5C8h+var_550]; this
0x18000b9b6  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000b9bb  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000b9c2  lea     rcx, [rsp+5C8h+var_550]; pExceptionObject
0x18000b9c7  call    _CxxThrowException
```
