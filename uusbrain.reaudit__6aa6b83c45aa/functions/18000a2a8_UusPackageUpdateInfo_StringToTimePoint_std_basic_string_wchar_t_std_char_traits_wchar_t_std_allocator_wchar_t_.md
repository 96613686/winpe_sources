# UusPackageUpdateInfo::StringToTimePoint(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18000a2a8`
- end: `0x18000a4bf`
- name: `?StringToTimePoint@UusPackageUpdateInfo@@CA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x18000e7ac`

## callees

- `0x180009c50`
- `0x180009e1c`
- `0x18000a2a8`
- `0x18000deb8`
- `0x18000e210`
- `0x18000e3d8`
- `0x180010428`
- `0x18001044c`
- `0x18001052c`
- `0x180017ea8`
- `0x180018000`
- `0x1800240ac`
- `0x180027618`
- `0x18004259a`
- `0x1800427d0`
- `0x180044848`
- `0x180047ab0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall UusPackageUpdateInfo::StringToTimePoint(_QWORD *a1, __int64 a2)
{
  const wchar_t *v4; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  _QWORD pExceptionObject[2]; // [rsp+28h] [rbp-D8h] BYREF
  const wchar_t *v10; // [rsp+38h] [rbp-C8h]
  _BYTE v11[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[32]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v13[16]; // [rsp+80h] [rbp-80h] BYREF
  tm Tm; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v15[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v16[240]; // [rsp+1C0h] [rbp+C0h] BYREF

  memset(v13, 0, 0xF8u);
  *(_QWORD *)&v13[0] = &std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::istream'};
  *(_QWORD *)&v13[1] = &std::wostringstream::`vbtable';
  memset(&v13[10], 0, 20);
  *((_QWORD *)&v13[11] + 1) = 0;
  memset(&v13[12], 0, 50);
  *((_QWORD *)&v13[9] + 1) = &std::wios::`vftable';
  std::wiostream::basic_iostream<wchar_t>(v13, (char *)&v13[1] + 8);
  *(_QWORD *)((char *)v13 + *(int *)(*(_QWORD *)&v13[0] + 4LL)) = &std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vftable';
  *(_DWORD *)&v12[*(int *)(*(_QWORD *)&v13[0] + 4LL) + 28] = *(_DWORD *)(*(_QWORD *)&v13[0] + 4LL) - 152;
  std::wstringbuf::wstringbuf((char *)&v13[1] + 8, a2, 3);
  memset(&Tm, 0, sizeof(Tm));
  pExceptionObject[0] = &Tm;
  v4 = L"%Y-%m-%dT%TZ";
  pExceptionObject[1] = L"%Y-%m-%dT%TZ";
  v10 = L"%Y-%m-%dT%TZ";
  if ( aYMDtTz[0] )
  {
    do
      ++v4;
    while ( *v4 );
    v10 = v4;
  }
  std::operator>><wchar_t,std::char_traits<wchar_t>>(v13, pExceptionObject);
  if ( (*((_BYTE *)&v13[1] + *(int *)(*(_QWORD *)&v13[0] + 4LL)) & 6) != 0 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::__autoclassinit2(v15);
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v15);
    v6 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v16, L"Unable to parse time from ");
    std::operator<<<wchar_t>(v6, a2);
    v7 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v15, v11);
    v8 = UnicodeToMultiByte(v12, v7);
    std::runtime_error::runtime_error(pExceptionObject, v8);
    throw (std::runtime_error *)pExceptionObject;
  }
  *a1 = 10000000 * mkgmtime64(&Tm);
  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>((char *)&v13[9] + 8);
  *((_QWORD *)&v13[9] + 1) = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)((char *)&v13[9] + 8));
  return a1;
}

```

## disassembly

```asm
0x18000a2a8  mov     [rsp-8+arg_10], rbx
0x18000a2ad  mov     [rsp-8+arg_18], rsi
0x18000a2b2  push    rbp
0x18000a2b3  push    rdi
0x18000a2b4  push    r14
0x18000a2b6  lea     rbp, [rsp-1C0h]
0x18000a2be  sub     rsp, 2C0h
0x18000a2c5  mov     rax, cs:__security_cookie
0x18000a2cc  xor     rax, rsp
0x18000a2cf  mov     [rbp+1D0h+var_20], rax
0x18000a2d6  mov     rdi, rdx
0x18000a2d9  mov     rbx, rcx
0x18000a2dc  xor     esi, esi
0x18000a2de  mov     [rsp+2D0h+var_2B0], esi
0x18000a2e2  xor     edx, edx; Val
0x18000a2e4  mov     r8d, 0F8h; Size
0x18000a2ea  lea     rcx, [rbp+1D0h+var_250]; void *
0x18000a2ee  call    memset
0x18000a2f3  lea     rax, ??_8?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@7B?$basic_istream@DU?$char_traits@D@std@@@1@@; const std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbtable'{for `std::istream'}
0x18000a2fa  mov     [rbp+1D0h+var_250], rax
0x18000a2fe  lea     rax, ??_8?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@7B@; const std::wostringstream::`vbtable'
0x18000a305  mov     [rbp+1D0h+var_240], rax
0x18000a309  mov     [rbp+1D0h+var_1B0], rsi
0x18000a30d  mov     [rbp+1D0h+var_1A8], rsi
0x18000a311  mov     [rbp+1D0h+var_1A0], esi
0x18000a314  mov     [rbp+1D0h+var_198], rsi
0x18000a318  xorps   xmm0, xmm0
0x18000a31b  movdqa  [rbp+1D0h+var_190], xmm0
0x18000a320  xorps   xmm1, xmm1
0x18000a323  movdqa  [rbp+1D0h+var_180], xmm1
0x18000a328  lea     r14, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18000a32f  mov     [rbp+1D0h+var_1B8], r14
0x18000a333  movdqa  [rbp+1D0h+var_170], xmm0
0x18000a338  mov     [rbp+1D0h+var_160], si
0x18000a33c  mov     [rsp+2D0h+var_2B0], 1
0x18000a344  lea     rdx, [rbp+1D0h+var_238]
0x18000a348  lea     rcx, [rbp+1D0h+var_250]
0x18000a34c  call    ??0?$basic_iostream@_WU?$char_traits@_W@std@@@std@@QEAA@PEAV?$basic_streambuf@_WU?$char_traits@_W@std@@@1@@Z; std::wiostream::basic_iostream<wchar_t>(std::wstreambuf *)
0x18000a351  nop
0x18000a352  mov     rax, [rbp+1D0h+var_250]
0x18000a356  movsxd  rcx, dword ptr [rax+4]
0x18000a35a  lea     rax, ??_7?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@6B@; const std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vftable'
0x18000a361  mov     [rbp+rcx+1D0h+var_250], rax
0x18000a366  mov     rax, [rbp+1D0h+var_250]
0x18000a36a  movsxd  rcx, dword ptr [rax+4]
0x18000a36e  lea     edx, [rcx-98h]
0x18000a374  mov     [rsp+rcx+2D0h+var_254], edx
0x18000a378  lea     r8d, [rsi+3]
0x18000a37c  mov     rdx, rdi
0x18000a37f  lea     rcx, [rbp+1D0h+var_238]
0x18000a383  call    ??0?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::wstringbuf::wstringbuf(std::wstring const &,int)
0x18000a388  nop
0x18000a389  xorps   xmm0, xmm0
0x18000a38c  xor     eax, eax
0x18000a38e  movups  xmmword ptr [rbp+1D0h+Tm.tm_sec], xmm0
0x18000a395  movups  xmmword ptr [rbp+1D0h+Tm.tm_mon], xmm0
0x18000a39c  mov     [rbp+1D0h+Tm.tm_isdst], eax
0x18000a3a2  lea     rax, [rbp+1D0h+Tm]
0x18000a3a9  mov     [rsp+2D0h+pExceptionObject], rax
0x18000a3ae  lea     rax, aYMDtTz; "%Y-%m-%dT%TZ"
0x18000a3b5  mov     [rsp+2D0h+var_2A0], rax
0x18000a3ba  mov     [rsp+2D0h+var_298], rax
0x18000a3bf  cmp     word ptr cs:aYMDtTz, si; "%Y-%m-%dT%TZ"
0x18000a3c6  jz      short loc_18000A3D6
0x18000a3c8  add     rax, 2
0x18000a3cc  cmp     [rax], si
0x18000a3cf  jnz     short loc_18000A3C8
0x18000a3d1  mov     [rsp+2D0h+var_298], rax
0x18000a3d6  lea     rdx, [rsp+2D0h+pExceptionObject]
0x18000a3db  lea     rcx, [rbp+1D0h+var_250]
0x18000a3df  call    ??$?5_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_istream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBU?$_Timeobj@_WPEAUtm@@@0@@Z; std::operator>><wchar_t,std::char_traits<wchar_t>>(std::wistream &,std::_Timeobj<wchar_t,tm *> const &)
0x18000a3e4  mov     rax, [rbp+1D0h+var_250]
0x18000a3e8  movsxd  rcx, dword ptr [rax+4]
0x18000a3ec  test    byte ptr [rbp+rcx+1D0h+var_240], 6
0x18000a3f1  jnz     short loc_18000A449
0x18000a3f3  lea     rcx, [rbp+1D0h+Tm]; Tm
0x18000a3fa  call    _mkgmtime64
0x18000a3ff  imul    rcx, rax, 989680h
0x18000a406  mov     [rbx], rcx
0x18000a409  lea     rcx, [rbp+1D0h+var_1B8]
0x18000a40d  call    ??1?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x18000a412  mov     [rbp+1D0h+var_1B8], r14
0x18000a416  lea     rcx, [rbp+1D0h+var_1B8]; this
0x18000a41a  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x18000a41f  mov     rax, rbx
0x18000a422  mov     rcx, [rbp+1D0h+var_20]
0x18000a429  xor     rcx, rsp; StackCookie
0x18000a42c  call    __security_check_cookie
0x18000a431  lea     r11, [rsp+2D0h+var_10]
0x18000a439  mov     rbx, [r11+30h]
0x18000a43d  mov     rsi, [r11+38h]
0x18000a441  mov     rsp, r11
0x18000a444  pop     r14
0x18000a446  pop     rdi
0x18000a447  pop     rbp
0x18000a448  retn
0x18000a449  lea     rcx, [rbp+1D0h+var_120]
0x18000a450  call    ?__autoclassinit2@?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::__autoclassinit2(unsigned __int64)
0x18000a455  lea     rcx, [rbp+1D0h+var_120]
0x18000a45c  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x18000a461  nop
0x18000a462  lea     rdx, aUnableToParseT; "Unable to parse time from "
0x18000a469  lea     rcx, [rbp+1D0h+var_110]
0x18000a470  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18000a475  mov     rcx, rax
0x18000a478  mov     rdx, rdi
0x18000a47b  call    ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x18000a480  lea     rdx, [rsp+2D0h+var_290]
0x18000a485  lea     rcx, [rbp+1D0h+var_120]
0x18000a48c  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x18000a491  nop
0x18000a492  mov     rdx, rax
0x18000a495  lea     rcx, [rsp+2D0h+var_270]
0x18000a49a  call    UnicodeToMultiByte
0x18000a49f  nop
0x18000a4a0  mov     rdx, rax
0x18000a4a3  lea     rcx, [rsp+2D0h+pExceptionObject]
0x18000a4a8  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18000a4ad  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000a4b4  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x18000a4b9  call    _CxxThrowException
```
