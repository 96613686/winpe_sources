# Diagnostics::CliAnalyze::WriteToFile(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::filesystem::path const &)

- ea: `0x18001014c`
- end: `0x180010466`
- name: `?WriteToFile@CliAnalyze@Diagnostics@@CAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBVpath@filesystem@4@@Z`
- size: `794`
- prototype: `void __fastcall(__m128i *, const char *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18000f290`

## callees

- `0x18001014c`
- `0x1800109f4`
- `0x180011be4`
- `0x180012cec`
- `0x180013f58`
- `0x1800140c0`
- `0x18001457c`
- `0x180014fa8`
- `0x180015198`
- `0x18001613c`
- `0x180016db0`
- `0x18008fe00`
- `0x1800957dc`
- `0x1800961f0`

## string_xrefs

- `0x1800102c2`: `Unable to open output file: %ws`
- `0x180010369`: `Failed to write to output file: %ws`

## pseudocode

```c
void __fastcall Diagnostics::CliAnalyze::WriteToFile(__m128i *a1, const char *a2)
{
  const char *v4; // rdi
  __int64 v5; // rcx
  int v6; // edx
  int v7; // edx
  const char *v8; // rdx
  __int64 v9; // rcx
  int v10; // edx
  int v11; // edx
  const char *v12; // rdx
  bool v13; // zf
  const struct std::error_code *v14; // rax
  const char *v15; // rdx
  const char *v16; // rdx
  const struct std::error_code *error_code; // rax
  const char *v18; // rdx
  _BYTE v19[16]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v21[17]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  memset(v21, 0, 0x108u);
  v4 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v4 = *(const char **)a2;
  *(_QWORD *)&v21[0] = &std::wfstream::`vbtable'{for `std::wostream'};
  memset(&v21[11], 0, 20);
  *((_QWORD *)&v21[12] + 1) = 0;
  memset(&v21[13], 0, 50);
  *((_QWORD *)&v21[10] + 1) = &std::wostream::`vftable';
  DWORD1(v21[10]) = 152;
  std::wios::init((char *)&v21[10] + 8, (char *)v21 + 8);
  *(_QWORD *)((char *)v21 + *(int *)(*(_QWORD *)&v21[0] + 4LL)) = &std::wofstream::`vftable';
  *(_DWORD *)&pExceptionObject[*(int *)(*(_QWORD *)&v21[0] + 4LL) + 36] = *(_DWORD *)(*(_QWORD *)&v21[0] + 4LL) - 168;
  std::wfilebuf::wfilebuf((char *)v21 + 8);
  if ( !std::wfilebuf::open((char *)v21 + 8, v4, 18) )
  {
    v5 = *(int *)(*(_QWORD *)&v21[0] + 4LL);
    v6 = *(_DWORD *)((_BYTE *)&v21[1] + v5) & 0x15 | (*(_QWORD *)((char *)&v21[4] + v5 + 8) == 0 ? 4 : 0) | 2;
    *(_DWORD *)((char *)&v21[1] + v5) = v6;
    v7 = *(_DWORD *)((_BYTE *)&v21[1] + v5 + 4) & v6;
    if ( v7 )
    {
      if ( (v7 & 4) != 0 )
      {
        v16 = "ios_base::badbit set";
      }
      else
      {
        v13 = (v7 & 2) == 0;
        v16 = "ios_base::failbit set";
        if ( v13 )
          v16 = "ios_base::eofbit set";
      }
      error_code = (const struct std::error_code *)std::make_error_code(v19, v16);
      std::ios_base::failure::failure((std::ios_base::failure *)pExceptionObject, v18, error_code);
      throw (std::ios_base::failure *)pExceptionObject;
    }
  }
  *(_QWORD *)((char *)v21 + *(int *)(*(_QWORD *)&v21[0] + 4LL)) = &std::wofstream::`vftable';
  *(_DWORD *)&pExceptionObject[*(int *)(*(_QWORD *)&v21[0] + 4LL) + 36] = *(_DWORD *)(*(_QWORD *)&v21[0] + 4LL) - 168;
  v8 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v8 = *(const char **)a2;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x187,
    (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\cmdline\\CliAnalyze.hpp",
    (const char *)(*((_QWORD *)&v21[8] + 1) == 0),
    "Unable to open output file: %ws",
    v8);
  std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(
    v21,
    a1->m128i_i64[0],
    _mm_srli_si128(*a1, 8).m128i_u64[0]);
  if ( !std::wfilebuf::close((char *)v21 + 8) )
  {
    v9 = *(int *)(*(_QWORD *)&v21[0] + 4LL);
    v10 = *(_DWORD *)((_BYTE *)&v21[1] + v9) & 0x15 | (*(_QWORD *)((char *)&v21[4] + v9 + 8) == 0 ? 4 : 0) | 2;
    *(_DWORD *)((char *)&v21[1] + v9) = v10;
    v11 = *(_DWORD *)((_BYTE *)&v21[1] + v9 + 4) & v10;
    if ( v11 )
    {
      if ( (v11 & 4) != 0 )
      {
        v12 = "ios_base::badbit set";
      }
      else
      {
        v13 = (v11 & 2) == 0;
        v12 = "ios_base::failbit set";
        if ( v13 )
          v12 = "ios_base::eofbit set";
      }
      v14 = (const struct std::error_code *)std::make_error_code(v19, v12);
      std::ios_base::failure::failure((std::ios_base::failure *)pExceptionObject, v15, v14);
      throw (std::ios_base::failure *)pExceptionObject;
    }
  }
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const char **)a2;
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x18C,
    (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\cmdline\\CliAnalyze.hpp",
    (const char *)((*((_BYTE *)&v21[1] + *(int *)(*(_QWORD *)&v21[0] + 4LL)) & 6) != 0),
    "Failed to write to output file: %ws",
    a2);
  std::wofstream::~wofstream<wchar_t,std::char_traits<wchar_t>>((char *)&v21[10] + 8);
  *((_QWORD *)&v21[10] + 1) = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)((char *)&v21[10] + 8));
}

```

## disassembly

```asm
0x18001014c  mov     [rsp-8+arg_10], rbx
0x180010151  push    rbp
0x180010152  push    rsi
0x180010153  push    rdi
0x180010154  push    r14
0x180010156  push    r15
0x180010158  lea     rbp, [rsp-90h]
0x180010160  sub     rsp, 190h
0x180010167  mov     rax, cs:__security_cookie
0x18001016e  xor     rax, rsp
0x180010171  mov     [rbp+0B0h+var_30], rax
0x180010178  mov     rbx, rdx
0x18001017b  mov     rsi, rcx
0x18001017e  xor     r14d, r14d
0x180010181  mov     [rsp+1B0h+var_180], r14d
0x180010186  xor     edx, edx; Val
0x180010188  mov     r8d, 108h; Size
0x18001018e  lea     rcx, [rsp+1B0h+var_140]; void *
0x180010193  call    memset
0x180010198  mov     rdi, rbx
0x18001019b  cmp     qword ptr [rbx+18h], 7
0x1800101a0  jbe     short loc_1800101A5
0x1800101a2  mov     rdi, [rbx]
0x1800101a5  lea     rax, ??_8?$basic_fstream@_WU?$char_traits@_W@std@@@std@@7B?$basic_ostream@_WU?$char_traits@_W@std@@@1@@; const std::wfstream::`vbtable'{for `std::wostream'}
0x1800101ac  mov     [rsp+1B0h+var_140], rax
0x1800101b1  mov     [rbp+0B0h+var_90], r14
0x1800101b5  mov     [rbp+0B0h+var_88], r14
0x1800101b9  mov     [rbp+0B0h+var_80], r14d
0x1800101bd  mov     [rbp+0B0h+var_78], r14
0x1800101c1  xorps   xmm0, xmm0
0x1800101c4  movdqa  [rbp+0B0h+var_70], xmm0
0x1800101c9  xorps   xmm1, xmm1
0x1800101cc  movdqa  [rbp+0B0h+var_60], xmm1
0x1800101d1  movdqa  [rbp+0B0h+var_50], xmm0
0x1800101d6  mov     [rbp+0B0h+var_40], r14w
0x1800101db  mov     [rsp+1B0h+var_180], 1
0x1800101e3  lea     rax, ??_7?$basic_ostream@_WU?$char_traits@_W@std@@@std@@6B@; const std::wostream::`vftable'
0x1800101ea  mov     [rbp+0B0h+var_98], rax
0x1800101ee  mov     [rbp+0B0h+var_9C], 98h
0x1800101f5  lea     rdx, [rsp+1B0h+var_138]
0x1800101fa  lea     rcx, [rbp+0B0h+var_98]
0x1800101fe  call    ?init@?$basic_ios@_WU?$char_traits@_W@std@@@std@@IEAAXPEAV?$basic_streambuf@_WU?$char_traits@_W@std@@@2@_N@Z; std::wios::init(std::wstreambuf *,bool)
0x180010203  nop
0x180010204  mov     rax, [rsp+1B0h+var_140]
0x180010209  movsxd  rcx, dword ptr [rax+4]
0x18001020d  lea     r15, ??_7?$basic_ofstream@_WU?$char_traits@_W@std@@@std@@6B@; const std::wofstream::`vftable'
0x180010214  mov     [rsp+rcx+1B0h+var_140], r15
0x180010219  mov     rax, [rsp+1B0h+var_140]
0x18001021e  movsxd  rcx, dword ptr [rax+4]
0x180010222  lea     r8d, [rcx-0A8h]
0x180010229  mov     [rsp+rcx+1B0h+var_144], r8d
0x18001022e  lea     rcx, [rsp+1B0h+var_138]
0x180010233  call    ??0?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@QEAA@XZ; std::wfilebuf::wfilebuf(void)
0x180010238  nop
0x180010239  mov     r8d, 12h
0x18001023f  mov     rdx, rdi
0x180010242  lea     rcx, [rsp+1B0h+var_138]
0x180010247  call    ?open@?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@QEAAPEAV12@PEB_WHH@Z; std::wfilebuf::open(wchar_t const *,int,int)
0x18001024c  test    rax, rax
0x18001024f  jnz     short loc_180010281
0x180010251  mov     rax, [rsp+1B0h+var_140]
0x180010256  movsxd  rcx, dword ptr [rax+4]
0x18001025a  mov     rax, [rbp+rcx+0B0h+var_F8]
0x18001025f  neg     rax
0x180010262  sbb     edx, edx
0x180010264  not     edx
0x180010266  and     edx, 4
0x180010269  or      edx, [rbp+rcx+0B0h+var_130]
0x18001026d  and     edx, 15h
0x180010270  or      edx, 2
0x180010273  mov     [rbp+rcx+0B0h+var_130], edx
0x180010277  and     edx, [rbp+rcx+0B0h+var_12C]
0x18001027b  jnz     loc_18001041A
0x180010281  mov     rax, [rsp+1B0h+var_140]
0x180010286  movsxd  rcx, dword ptr [rax+4]
0x18001028a  mov     [rsp+rcx+1B0h+var_140], r15
0x18001028f  mov     rax, [rsp+1B0h+var_140]
0x180010294  movsxd  rcx, dword ptr [rax+4]
0x180010298  lea     edx, [rcx-0A8h]
0x18001029e  mov     [rsp+rcx+1B0h+var_144], edx
0x1800102a2  mov     rdx, rbx
0x1800102a5  cmp     qword ptr [rbx+18h], 7
0x1800102aa  jbe     short loc_1800102AF
0x1800102ac  mov     rdx, [rbx]
0x1800102af  cmp     [rbp+0B0h+var_B8], r14
0x1800102b3  setz    al
0x1800102b6  mov     rcx, [rbp+0B8h]; this
0x1800102bd  mov     [rsp+1B0h+var_188], rdx; char *
0x1800102c2  lea     rdx, aUnableToOpenOu; "Unable to open output file: %ws"
0x1800102c9  mov     [rsp+1B0h+var_190], rdx; void *
0x1800102ce  movzx   r9d, al; char *
0x1800102d2  lea     r8, aCW1SSrcCalliop_3; "C:\\__w\\1\\s\\src\\Calliope\\libs\\cmd"...
0x1800102d9  mov     edx, 187h; void *
0x1800102de  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800102e3  movaps  xmm1, xmmword ptr [rsi]
0x1800102e6  movdqa  xmm0, xmm1
0x1800102ea  psrldq  xmm0, 8
0x1800102ef  movq    r8, xmm0
0x1800102f4  movq    rdx, xmm1
0x1800102f9  lea     rcx, [rsp+1B0h+var_140]
0x1800102fe  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180010303  lea     rcx, [rsp+1B0h+var_138]
0x180010308  call    ?close@?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@QEAAPEAV12@XZ; std::wfilebuf::close(void)
0x18001030d  test    rax, rax
0x180010310  jnz     short loc_180010342
0x180010312  mov     rax, [rsp+1B0h+var_140]
0x180010317  movsxd  rcx, dword ptr [rax+4]
0x18001031b  mov     rax, [rbp+rcx+0B0h+var_F8]
0x180010320  neg     rax
0x180010323  sbb     edx, edx
0x180010325  not     edx
0x180010327  and     edx, 4
0x18001032a  or      edx, [rbp+rcx+0B0h+var_130]
0x18001032e  and     edx, 15h
0x180010331  or      edx, 2
0x180010334  mov     [rbp+rcx+0B0h+var_130], edx
0x180010338  and     edx, [rbp+rcx+0B0h+var_12C]
0x18001033c  jnz     loc_1800103CE
0x180010342  cmp     qword ptr [rbx+18h], 7
0x180010347  jbe     short loc_18001034C
0x180010349  mov     rbx, [rbx]
0x18001034c  mov     rax, [rsp+1B0h+var_140]
0x180010351  movsxd  rcx, dword ptr [rax+4]
0x180010355  test    byte ptr [rbp+rcx+0B0h+var_130], 6
0x18001035a  setnz   al
0x18001035d  mov     rcx, [rbp+0B8h]; this
0x180010364  mov     [rsp+1B0h+var_188], rbx; char *
0x180010369  lea     rdx, aFailedToWriteT; "Failed to write to output file: %ws"
0x180010370  mov     [rsp+1B0h+var_190], rdx; void *
0x180010375  movzx   r9d, al; char *
0x180010379  lea     r8, aCW1SSrcCalliop_3; "C:\\__w\\1\\s\\src\\Calliope\\libs\\cmd"...
0x180010380  mov     edx, 18Ch; void *
0x180010385  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001038a  nop
0x18001038b  lea     rcx, [rbp+0B0h+var_98]
0x18001038f  call    ??1?$basic_ofstream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ; std::wofstream::~wofstream<wchar_t,std::char_traits<wchar_t>>(void)
0x180010394  lea     rax, ??_7?$basic_ios@_WU?$char_traits@_W@std@@@std@@6B@; const std::wios::`vftable'
0x18001039b  mov     [rbp+0B0h+var_98], rax
0x18001039f  lea     rcx, [rbp+0B0h+var_98]; this
0x1800103a3  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x1800103a8  mov     rcx, [rbp+0B0h+var_30]
0x1800103af  xor     rcx, rsp; StackCookie
0x1800103b2  call    __security_check_cookie
0x1800103b7  mov     rbx, [rsp+1B0h+arg_10]
0x1800103bf  add     rsp, 190h
0x1800103c6  pop     r15
0x1800103c8  pop     r14
0x1800103ca  pop     rdi
0x1800103cb  pop     rsi
0x1800103cc  pop     rbp
0x1800103cd  retn
0x1800103ce  test    dl, 4
0x1800103d1  jz      short loc_1800103DC
0x1800103d3  lea     rdx, aIosBaseBadbitS; "ios_base::badbit set"
0x1800103da  jmp     short loc_1800103F1
0x1800103dc  test    dl, 2
0x1800103df  lea     rdx, aIosBaseFailbit; "ios_base::failbit set"
0x1800103e6  lea     rax, aIosBaseEofbitS; "ios_base::eofbit set"
0x1800103ed  cmovz   rdx, rax
0x1800103f1  lea     rcx, [rsp+1B0h+var_178]
0x1800103f6  call    ?make_error_code@std@@YA?AVerror_code@1@W4io_errc@1@@Z; std::make_error_code(std::io_errc)
0x1800103fb  mov     r8, rax; struct std::error_code *
0x1800103fe  lea     rcx, [rsp+1B0h+pExceptionObject]; this
0x180010403  call    ??0failure@ios_base@std@@QEAA@PEBDAEBVerror_code@2@@Z; std::ios_base::failure::failure(char const *,std::error_code const &)
0x180010408  lea     rdx, _TI5?AVfailure@ios_base@std@@; pThrowInfo
0x18001040f  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180010414  call    _CxxThrowException
0x18001041a  test    dl, 4
0x18001041d  jz      short loc_180010428
0x18001041f  lea     rdx, aIosBaseBadbitS; "ios_base::badbit set"
0x180010426  jmp     short loc_18001043D
0x180010428  test    dl, 2
0x18001042b  lea     rdx, aIosBaseFailbit; "ios_base::failbit set"
0x180010432  lea     rax, aIosBaseEofbitS; "ios_base::eofbit set"
0x180010439  cmovz   rdx, rax
0x18001043d  lea     rcx, [rsp+1B0h+var_178]
0x180010442  call    ?make_error_code@std@@YA?AVerror_code@1@W4io_errc@1@@Z; std::make_error_code(std::io_errc)
0x180010447  mov     r8, rax; struct std::error_code *
0x18001044a  lea     rcx, [rsp+1B0h+pExceptionObject]; this
0x18001044f  call    ??0failure@ios_base@std@@QEAA@PEBDAEBVerror_code@2@@Z; std::ios_base::failure::failure(char const *,std::error_code const &)
0x180010454  lea     rdx, _TI5?AVfailure@ios_base@std@@; pThrowInfo
0x18001045b  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180010460  call    _CxxThrowException
```
