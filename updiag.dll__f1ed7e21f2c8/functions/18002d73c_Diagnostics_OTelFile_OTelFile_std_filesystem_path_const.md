# Diagnostics::OTelFile::OTelFile(std::filesystem::path const &)

- ea: `0x18002d73c`
- end: `0x18002d989`
- name: `??0OTelFile@Diagnostics@@QEAA@AEBVpath@filesystem@std@@@Z`
- size: `589`
- prototype: `Diagnostics::OTelFile *__fastcall(Diagnostics::OTelFile *this, const struct std::filesystem::path *)`
- caller_count: `18`
- callee_count: `18`
- tags: ``

## callers

- `0x18002e380`
- `0x180031aa0`
- `0x180033e10`
- `0x1800380bc`
- `0x180041b20`
- `0x180042030`
- `0x1800421d0`
- `0x1800423d0`
- `0x1800425d0`
- `0x180043340`
- `0x180043d60`
- `0x1800446c0`
- `0x180044c10`
- `0x180045560`
- `0x180045760`
- `0x180045cb0`
- `0x180052894`
- `0x180069800`

## callees

- `0x1800153b0`
- `0x18001613c`
- `0x18001639c`
- `0x180018b04`
- `0x180018bec`
- `0x180018e64`
- `0x18002d73c`
- `0x18003b2d0`
- `0x180046f7c`
- `0x180047060`
- `0x180047af8`
- `0x180051754`
- `0x18006847c`
- `0x180068a70`
- `0x180079720`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## string_xrefs

- `0x18002d966`: `Failed to open log folder\file: %ls\%ls`

## pseudocode

```c
Diagnostics::OTelFile *__fastcall Diagnostics::OTelFile::OTelFile(
        Diagnostics::OTelFile *this,
        const struct std::filesystem::path *a2)
{
  char *v3; // rbx
  __int64 v4; // rcx
  char *v5; // rbx
  void (__fastcall ***v6)(_QWORD, __int64); // rax
  void (__fastcall ***v7)(_QWORD, __int64); // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  const char *v11; // rax
  _BYTE v12[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct std::locale::_Locimp *v13; // [rsp+48h] [rbp-B8h]
  _OWORD v14[2]; // [rsp+50h] [rbp-B0h] BYREF
  Diagnostics::OTelFile *v15; // [rsp+70h] [rbp-90h]
  _BYTE v16[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v17; // [rsp+80h] [rbp-80h]
  _QWORD v18[36]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v15 = this;
  *(_QWORD *)this = &Diagnostics::OTelFile::`vftable';
  v3 = (char *)this + 8;
  std::wstring::wstring((char *)this + 8, a2);
  std::wfstream::wfstream((char *)this + 40);
  *((_BYTE *)this + 320) = 0;
  *((_BYTE *)this + 664) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_DWORD *)this + 174) = 0;
  memset(v18, 0, 0x118u);
  std::wfstream::wfstream(v18);
  std::wfstream::open<0,std::filesystem::path>(v18, v3, 11);
  if ( !v18[19] )
  {
    std::wfstream::open<0,std::filesystem::path>(v18, v3, 1);
    *((_BYTE *)this + 320) = 1;
    if ( !v18[19] )
    {
      v9 = std::wstring::c_str(v3);
      v10 = std::filesystem::current_path(v14);
      v11 = (const char *)std::wstring::c_str(v10);
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x3E,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelFile.hpp",
        (const char *)2,
        (unsigned int)"Failed to open log folder\\file: %ls\\%ls",
        v11,
        v9);
    }
  }
  v4 = *(int *)(v18[0] + 4LL);
  v5 = (char *)v18 + v4;
  v13 = std::locale::_Locimp::_New_Locimp(v4);
  memset(v14, 0, sizeof(v14));
  std::string::_Construct<1,char const *>(v14, &word_1800A006A, 0);
  std::locale::_Construct(v12, v14);
  std::string::~string(v14);
  std::wios::imbue(v5, v16, v12);
  if ( v17 )
  {
    v6 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v6 )
      (**v6)(v6, 1);
  }
  if ( v13 )
  {
    v7 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v7 )
      (**v7)(v7, 1);
  }
  std::wfstream::_Assign_rv((char *)this + 40, v18);
  std::wfstream::~wfstream<wchar_t,std::char_traits<wchar_t>>(&v18[23]);
  v18[23] = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)&v18[23]);
  return this;
}

```

## disassembly

```asm
0x18002d73c  mov     [rsp-8+arg_10], rbx
0x18002d741  push    rbp
0x18002d742  push    rsi
0x18002d743  push    rdi
0x18002d744  lea     rbp, [rsp-0C0h]
0x18002d74c  sub     rsp, 1C0h
0x18002d753  mov     rax, cs:__security_cookie
0x18002d75a  xor     rax, rsp
0x18002d75d  mov     [rbp+0D0h+var_20], rax
0x18002d764  mov     rdi, rcx
0x18002d767  mov     [rsp+1D0h+var_160], rcx
0x18002d76c  lea     rax, ??_7OTelFile@Diagnostics@@6B@; const Diagnostics::OTelFile::`vftable'
0x18002d773  mov     [rcx], rax
0x18002d776  lea     rbx, [rcx+8]
0x18002d77a  mov     rcx, rbx
0x18002d77d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002d782  nop
0x18002d783  lea     rcx, [rdi+28h]
0x18002d787  call    ??0?$basic_fstream@_WU?$char_traits@_W@std@@@std@@QEAA@XZ; std::wfstream::wfstream(void)
0x18002d78c  nop
0x18002d78d  mov     byte ptr [rdi+140h], 0
0x18002d794  mov     byte ptr [rdi+298h], 0
0x18002d79b  mov     qword ptr [rdi+2A0h], 0
0x18002d7a6  mov     qword ptr [rdi+2A8h], 0
0x18002d7b1  mov     qword ptr [rdi+2B0h], 0
0x18002d7bc  mov     dword ptr [rdi+2B8h], 0
0x18002d7c6  xor     edx, edx; Val
0x18002d7c8  mov     r8d, 118h; Size
0x18002d7ce  lea     rcx, [rbp+0D0h+var_140]; void *
0x18002d7d2  call    memset
0x18002d7d7  lea     rcx, [rbp+0D0h+var_140]
0x18002d7db  call    ??0?$basic_fstream@_WU?$char_traits@_W@std@@@std@@QEAA@XZ; std::wfstream::wfstream(void)
0x18002d7e0  nop
0x18002d7e1  mov     r8d, 0Bh
0x18002d7e7  mov     rdx, rbx
0x18002d7ea  lea     rcx, [rbp+0D0h+var_140]
0x18002d7ee  call    ??$open@$0A@Vpath@filesystem@std@@@?$basic_fstream@_WU?$char_traits@_W@std@@@std@@QEAAXAEBVpath@filesystem@1@HH@Z; std::wfstream::open<0,std::filesystem::path>(std::filesystem::path const &,int,int)
0x18002d7f3  cmp     [rbp+0D0h+var_A8], 0
0x18002d7f8  jnz     short loc_18002D81E
0x18002d7fa  mov     r8d, 1
0x18002d800  mov     rdx, rbx
0x18002d803  lea     rcx, [rbp+0D0h+var_140]
0x18002d807  call    ??$open@$0A@Vpath@filesystem@std@@@?$basic_fstream@_WU?$char_traits@_W@std@@@std@@QEAAXAEBVpath@filesystem@1@HH@Z; std::wfstream::open<0,std::filesystem::path>(std::filesystem::path const &,int,int)
0x18002d80c  mov     byte ptr [rdi+140h], 1
0x18002d813  cmp     [rbp+0D0h+var_A8], 0
0x18002d818  jz      loc_18002D937
0x18002d81e  mov     rax, [rbp+0D0h+var_140]
0x18002d822  movsxd  rcx, dword ptr [rax+4]; bool
0x18002d826  lea     rbx, [rbp+0D0h+var_140]
0x18002d82a  add     rbx, rcx
0x18002d82d  call    ?_New_Locimp@_Locimp@locale@std@@CAPEAV123@_N@Z; std::locale::_Locimp::_New_Locimp(bool)
0x18002d832  mov     [rsp+1D0h+var_188], rax
0x18002d837  xorps   xmm0, xmm0
0x18002d83a  movups  [rsp+1D0h+var_180], xmm0
0x18002d83f  xorps   xmm1, xmm1
0x18002d842  movdqu  [rsp+1D0h+var_170], xmm1
0x18002d848  xor     r8d, r8d
0x18002d84b  lea     rdx, word_1800A006A
0x18002d852  lea     rcx, [rsp+1D0h+var_180]
0x18002d857  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002d85c  nop
0x18002d85d  lea     rdx, [rsp+1D0h+var_180]
0x18002d862  lea     rcx, [rsp+1D0h+var_190]
0x18002d867  call    ?_Construct@locale@std@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@H@Z; std::locale::_Construct(std::string const &,int)
0x18002d86c  nop
0x18002d86d  lea     rcx, [rsp+1D0h+var_180]
0x18002d872  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002d877  nop
0x18002d878  lea     r8, [rsp+1D0h+var_190]
0x18002d87d  lea     rdx, [rsp+1D0h+var_158]
0x18002d882  mov     rcx, rbx
0x18002d885  call    ?imbue@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z; std::wios::imbue(std::locale const &)
0x18002d88a  mov     rcx, [rbp+0D0h+var_150]
0x18002d88e  test    rcx, rcx
0x18002d891  jz      short loc_18002D8B8
0x18002d893  mov     rax, [rcx]
0x18002d896  mov     rax, [rax+10h]
0x18002d89a  call    _guard_dispatch_icall
0x18002d89f  mov     rcx, rax
0x18002d8a2  test    rax, rax
0x18002d8a5  jz      short loc_18002D8B8
0x18002d8a7  mov     rax, [rax]
0x18002d8aa  mov     edx, 1
0x18002d8af  mov     rax, [rax]
0x18002d8b2  call    _guard_dispatch_icall
0x18002d8b7  nop
0x18002d8b8  mov     rcx, [rsp+1D0h+var_188]
0x18002d8bd  test    rcx, rcx
0x18002d8c0  jz      short loc_18002D8E6
0x18002d8c2  mov     rax, [rcx]
0x18002d8c5  mov     rax, [rax+10h]
0x18002d8c9  call    _guard_dispatch_icall
0x18002d8ce  mov     rcx, rax
0x18002d8d1  test    rax, rax
0x18002d8d4  jz      short loc_18002D8E6
0x18002d8d6  mov     rax, [rax]
0x18002d8d9  mov     edx, 1
0x18002d8de  mov     rax, [rax]
0x18002d8e1  call    _guard_dispatch_icall
0x18002d8e6  lea     rdx, [rbp+0D0h+var_140]
0x18002d8ea  lea     rcx, [rdi+28h]
0x18002d8ee  call    ?_Assign_rv@?$basic_fstream@_WU?$char_traits@_W@std@@@std@@QEAAX$$QEAV12@@Z; std::wfstream::_Assign_rv(std::wfstream &&)
0x18002d8f3  nop
0x18002d8f4  lea     rcx, [rbp+0D0h+var_88]
0x18002d8f8  call    ??1?$basic_fstream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wfstream::~wfstream<wchar_t,std::char_traits<wchar_t>>(void)
0x18002d8fd  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18002d904  mov     [rbp+0D0h+var_88], rax
0x18002d908  lea     rcx, [rbp+0D0h+var_88]; this
0x18002d90c  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18002d911  nop
0x18002d912  mov     rax, rdi
0x18002d915  mov     rcx, [rbp+0D0h+var_20]
0x18002d91c  xor     rcx, rsp; StackCookie
0x18002d91f  call    __security_check_cookie
0x18002d924  mov     rbx, [rsp+1D0h+arg_10]
0x18002d92c  add     rsp, 1C0h
0x18002d933  pop     rdi
0x18002d934  pop     rsi
0x18002d935  pop     rbp
0x18002d936  retn
0x18002d937  mov     rcx, rbx
0x18002d93a  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002d93f  mov     rbx, rax
0x18002d942  lea     rcx, [rsp+1D0h+var_180]
0x18002d947  call    ?current_path@filesystem@std@@YA?AVpath@12@XZ; std::filesystem::current_path(void)
0x18002d94c  nop
0x18002d94d  mov     rcx, rax
0x18002d950  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002d955  mov     rcx, [rbp+0D8h]; this
0x18002d95c  mov     [rsp+1D0h+var_1A0], rbx
0x18002d961  mov     [rsp+1D0h+var_1A8], rax; char *
0x18002d966  lea     rax, aFailedToOpenLo; "Failed to open log folder\\file: %ls\\%"...
0x18002d96d  mov     qword ptr [rsp+1D0h+var_1B0], rax; unsigned int
0x18002d972  mov     r9d, 2; char *
0x18002d978  lea     r8, aCW1SSrcCalliop_11; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x18002d97f  lea     edx, [r9+3Ch]; void *
0x18002d983  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
