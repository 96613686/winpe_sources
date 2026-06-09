# Diagnostics::ConnectorCollection::ConvertData(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::filesystem::path const &,std::function<std::optional<std::filesystem::path> (std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)> const &)

- ea: `0x180069800`
- end: `0x180069b7e`
- name: `?ConvertData@ConnectorCollection@Diagnostics@@YAIV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBVpath@filesystem@4@AEBV?$function@$$A6A?AV?$optional@Vpath@filesystem@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@2@@Z@4@@Z`
- size: `894`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800377dc`

## callees

- `0x180016e0c`
- `0x1800185a8`
- `0x180018b04`
- `0x180018eec`
- `0x180028ed4`
- `0x18002d4ac`
- `0x18002d73c`
- `0x18002d990`
- `0x1800380bc`
- `0x1800381f0`
- `0x18004148c`
- `0x180046d94`
- `0x180069800`
- `0x180078da8`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## string_xrefs

- `0x1800698f9`: `Failed to create connector for: %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Diagnostics::ConnectorCollection::ConvertData(
        const char **a1,
        const struct std::filesystem::path *a2,
        __int64 a3)
{
  __m128i v6; // xmm6
  void **v7; // rdi
  void **v8; // rbx
  const char *v9; // rdi
  __int64 v10; // r9
  __int64 *i; // rbx
  __int64 *v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  int v17; // [rsp+28h] [rbp-E0h]
  int v18; // [rsp+28h] [rbp-E0h]
  __m128i v19; // [rsp+48h] [rbp-C0h] BYREF
  __m128i v20; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v22; // [rsp+70h] [rbp-98h] BYREF
  __int64 v23; // [rsp+80h] [rbp-88h]
  __int128 v24; // [rsp+88h] [rbp-80h] BYREF
  __int64 v25; // [rsp+98h] [rbp-70h]
  _OWORD v26[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v27; // [rsp+C0h] [rbp-48h]
  _BYTE v28[336]; // [rsp+C8h] [rbp-40h] BYREF
  char v29; // [rsp+218h] [rbp+110h]
  _DWORD v30[176]; // [rsp+228h] [rbp+120h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+540h] [rbp+438h]

  v6 = *(__m128i *)a1;
  v7 = (void **)&off_1800A12B0;
  do
  {
    v19 = v6;
    v20 = *(__m128i *)v7;
    if ( !(unsigned int)((__int64 (__fastcall *)(__m128i *, __m128i *))constexpr_sort::CompareOrdinal)(&v20, &v19) )
      break;
    v7 += 3;
  }
  while ( v7 != &Diagnostics::Connector_Uso_Working::`vftable' );
  v8 = 0;
  if ( v7 != &Diagnostics::Connector_Uso_Working::`vftable' )
    v8 = v7;
  v9 = *a1;
  LOBYTE(v17) = v8 == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x26,
    (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\ConnectorCollection.cpp",
    (const char *)0x8000000BLL,
    v17,
    (bool)"No connector factory found for: %ls",
    *a1);
  v21 = 0;
  v20 = v6;
  ((void (__fastcall *)(__int64 *, __m128i *))v8[2])(&v21, &v20);
  LOBYTE(v18) = v21 == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x28,
    (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\ConnectorCollection.cpp",
    (const char *)0x80004005LL,
    v18,
    (bool)"Failed to create connector for: %ls",
    v9);
  v24 = 0;
  v25 = 0;
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v21 + 16LL))(v21, &v24);
  v22 = 0;
  v23 = 0;
  std::vector<std::filesystem::path>::reserve(&v22, (__int64)(*((_QWORD *)&v24 + 1) - v24) >> 5);
  v12 = (__int64 *)*((_QWORD *)&v24 + 1);
  for ( i = (__int64 *)v24; i != v12; i += 4 )
  {
    v13 = (__int64)i;
    if ( (unsigned __int64)i[3] > 7 )
      v13 = *i;
    v19.m128i_i64[0] = v13;
    v19.m128i_i64[1] = i[2];
    v14 = *(_QWORD *)(a3 + 56);
    if ( !v14 )
      std::_Xbad_function_call();
    (*(void (__fastcall **)(__int64, _OWORD *, __m128i *))(*(_QWORD *)v14 + 16LL))(v14, v26, &v19);
    if ( (_BYTE)v27 )
    {
      if ( *((_QWORD *)&v22 + 1) == v23 )
      {
        std::vector<std::filesystem::path>::_Emplace_reallocate<std::filesystem::path const &>(
          (__int64 *)&v22,
          *((__int64 *)&v22 + 1),
          (__int64)v26);
      }
      else
      {
        std::wstring::wstring(*((__int64 *)&v22 + 1), (__int64)v26);
        *((_QWORD *)&v22 + 1) += 32LL;
      }
    }
    if ( (_BYTE)v27 )
      std::wstring::~wstring((__int64)v26);
  }
  if ( (_QWORD)v22 == *((_QWORD *)&v22 + 1) )
  {
    v15 = 0;
  }
  else
  {
    memset(v26, 0, sizeof(v26));
    v27 = 0;
    v19.m128i_i64[0] = v22;
    v19.m128i_i64[1] = (__int64)(*((_QWORD *)&v22 + 1) - v22) >> 5;
    v20 = 0;
    Diagnostics::OTelReader::OTelReader((__int64)v26, &v19, (struct std::error_code *)&v20, v10);
    memset(v30, 0, sizeof(v30));
    Diagnostics::OTelFile::OTelFile((Diagnostics::OTelFile *)v30, a2);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
    Diagnostics::OTelReader::ReadNextEvent(v26, v28);
    while ( v29 )
    {
      (*(void (__fastcall **)(__int64, _BYTE *, _DWORD *))(*(_QWORD *)v21 + 32LL))(v21, v28, v30);
      if ( v29 )
        Diagnostics::OTelLogRecord::~OTelLogRecord((Diagnostics::OTelLogRecord *)v28);
      Diagnostics::OTelReader::ReadNextEvent(v26, v28);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 40LL))(v21);
    v15 = v30[174];
    Diagnostics::OTelFile::~OTelFile((Diagnostics::OTelFile *)v30);
    std::vector<Diagnostics::OTelFile>::~vector<Diagnostics::OTelFile>(v26);
  }
  std::vector<std::filesystem::path>::~vector<std::filesystem::path>(&v22);
  std::vector<std::filesystem::path>::~vector<std::filesystem::path>(&v24);
  if ( v21 )
    (**(void (__fastcall ***)(__int64, __int64))v21)(v21, 1);
  return v15;
}

```

## disassembly

```asm
0x180069800  mov     rax, rsp
0x180069803  push    rbp
0x180069804  push    rbx
0x180069805  push    rsi
0x180069806  push    rdi
0x180069807  push    r13
0x180069809  push    r14
0x18006980b  push    r15
0x18006980d  lea     rbp, [rax-438h]
0x180069814  sub     rsp, 500h
0x18006981b  movaps  xmmword ptr [rax-48h], xmm6
0x18006981f  mov     rax, cs:__security_cookie
0x180069826  xor     rax, rsp
0x180069829  mov     [rbp+430h+var_50], rax
0x180069830  mov     r14, r8
0x180069833  mov     r15, rdx
0x180069836  mov     rsi, rcx
0x180069839  movaps  xmm6, xmmword ptr [rcx]
0x18006983c  lea     rdi, off_1800A12B0; "UpdateEventPattern.Other"
0x180069843  lea     r13, ??_7Connector_Uso_Working@Diagnostics@@6B@; const Diagnostics::Connector_Uso_Working::`vftable'
0x18006984a  movdqa  [rsp+530h+var_4F8+8], xmm6
0x180069850  movups  xmm0, xmmword ptr [rdi]
0x180069853  movdqu  [rsp+530h+var_4E8+8], xmm0
0x180069859  lea     rdx, [rsp+530h+var_4F8+8]
0x18006985e  lea     rcx, [rsp+530h+var_4E8+8]
0x180069863  lea     rax, ?CompareOrdinal@constexpr_sort@@YAHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; constexpr_sort::CompareOrdinal(std::wstring_view,std::wstring_view)
0x18006986a  call    _guard_dispatch_icall
0x18006986f  test    eax, eax
0x180069871  jz      short loc_18006987C
0x180069873  add     rdi, 18h
0x180069877  cmp     rdi, r13
0x18006987a  jnz     short loc_18006984A
0x18006987c  xor     ebx, ebx
0x18006987e  cmp     rdi, r13
0x180069881  cmovnz  rbx, rdi
0x180069885  mov     rdi, [rsi]
0x180069888  test    rbx, rbx
0x18006988b  setz    al
0x18006988e  mov     rcx, [rbp+438h]; this
0x180069895  mov     [rsp+30h], rdi; char *
0x18006989a  lea     rdx, aNoConnectorFac; "No connector factory found for: %ls"
0x1800698a1  mov     qword ptr [rsp+530h+var_508], rdx; bool
0x1800698a6  mov     byte ptr [rsp+530h+var_510], al; int
0x1800698aa  mov     r9d, 8000000Bh; char *
0x1800698b0  lea     r8, aCW1SSrcCalliop_10; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x1800698b7  mov     edx, 26h ; '&'; void *
0x1800698bc  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800698c1  mov     qword ptr [rsp+530h+var_4D0], 0
0x1800698ca  movdqa  [rsp+530h+var_4E8+8], xmm6
0x1800698d0  lea     rdx, [rsp+530h+var_4E8+8]
0x1800698d5  lea     rcx, [rsp+530h+var_4D0]
0x1800698da  mov     rax, [rbx+10h]
0x1800698de  call    _guard_dispatch_icall
0x1800698e3  nop
0x1800698e4  cmp     qword ptr [rsp+530h+var_4D0], 0
0x1800698ea  setz    al
0x1800698ed  mov     rcx, [rbp+438h]; this
0x1800698f4  mov     [rsp+30h], rdi; char *
0x1800698f9  lea     rdx, aFailedToCreate; "Failed to create connector for: %ls"
0x180069900  mov     qword ptr [rsp+530h+var_508], rdx; bool
0x180069905  mov     byte ptr [rsp+530h+var_510], al; int
0x180069909  mov     r9d, 80004005h; char *
0x18006990f  lea     r8, aCW1SSrcCalliop_10; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x180069916  mov     edx, 28h ; '('; void *
0x18006991b  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180069920  xorps   xmm0, xmm0
0x180069923  xor     eax, eax
0x180069925  movups  [rbp+430h+var_4B0], xmm0
0x180069929  mov     [rbp+430h+var_4A0], rax
0x18006992d  mov     rcx, qword ptr [rsp+530h+var_4D0]
0x180069932  mov     rax, [rcx]
0x180069935  lea     rdx, [rbp+430h+var_4B0]
0x180069939  mov     rax, [rax+10h]
0x18006993d  call    _guard_dispatch_icall
0x180069942  nop
0x180069943  xor     eax, eax
0x180069945  xorps   xmm1, xmm1
0x180069948  movdqu  [rsp+530h+var_4D0+8], xmm1
0x18006994e  mov     [rsp+530h+var_4B8], rax
0x180069953  mov     rdx, qword ptr [rbp+430h+var_4B0+8]
0x180069957  sub     rdx, qword ptr [rbp+430h+var_4B0]
0x18006995b  sar     rdx, 5
0x18006995f  lea     rcx, [rsp+530h+var_4D0+8]
0x180069964  call    ?reserve@?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@QEAAX_K@Z; std::vector<std::filesystem::path>::reserve(unsigned __int64)
0x180069969  mov     rbx, qword ptr [rbp+430h+var_4B0]
0x18006996d  mov     rdi, qword ptr [rbp+430h+var_4B0+8]
0x180069971  jmp     loc_1800699FF
0x180069976  mov     rax, rbx
0x180069979  cmp     qword ptr [rbx+18h], 7
0x18006997e  jbe     short loc_180069983
0x180069980  mov     rax, [rbx]
0x180069983  mov     qword ptr [rsp+530h+var_4F8+8], rax
0x180069988  mov     rax, [rbx+10h]
0x18006998c  mov     qword ptr [rsp+530h+var_4E8], rax
0x180069991  mov     rcx, [r14+38h]
0x180069995  test    rcx, rcx
0x180069998  jz      loc_180069B78
0x18006999e  mov     rax, [rcx]
0x1800699a1  lea     r8, [rsp+530h+var_4F8+8]
0x1800699a6  lea     rdx, [rbp+430h+var_498]
0x1800699aa  mov     rax, [rax+10h]
0x1800699ae  call    _guard_dispatch_icall
0x1800699b3  nop
0x1800699b4  cmp     byte ptr [rbp+430h+var_478], 0
0x1800699b8  jz      short loc_1800699EC
0x1800699ba  mov     rax, [rsp+530h+var_4C0]
0x1800699bf  cmp     rax, [rsp+530h+var_4B8]
0x1800699c4  jz      short loc_1800699DA
0x1800699c6  lea     rdx, [rbp+430h+var_498]
0x1800699ca  mov     rcx, rax
0x1800699cd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800699d2  add     [rsp+530h+var_4C0], 20h ; ' '
0x1800699d8  jmp     short loc_1800699EC
0x1800699da  lea     r8, [rbp+430h+var_498]
0x1800699de  mov     rdx, rax
0x1800699e1  lea     rcx, [rsp+530h+var_4D0+8]
0x1800699e6  call    ??$_Emplace_reallocate@AEBVpath@filesystem@std@@@?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@AEAAPEAVpath@filesystem@1@QEAV231@AEBV231@@Z; std::vector<std::filesystem::path>::_Emplace_reallocate<std::filesystem::path const &>(std::filesystem::path * const,std::filesystem::path const &)
0x1800699eb  nop
0x1800699ec  cmp     byte ptr [rbp+430h+var_478], 0
0x1800699f0  jz      short loc_1800699FB
0x1800699f2  lea     rcx, [rbp+430h+var_498]
0x1800699f6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800699fb  add     rbx, 20h ; ' '
0x1800699ff  cmp     rbx, rdi
0x180069a02  jnz     loc_180069976
0x180069a08  mov     rcx, qword ptr [rsp+530h+var_4D0+8]
0x180069a0d  mov     rax, [rsp+530h+var_4C0]
0x180069a12  cmp     rcx, rax
0x180069a15  jz      loc_180069B1C
0x180069a1b  xorps   xmm0, xmm0
0x180069a1e  xor     edx, edx
0x180069a20  movups  [rbp+430h+var_498], xmm0
0x180069a24  movups  [rbp+430h+var_488], xmm0
0x180069a28  mov     [rbp+430h+var_478], rdx
0x180069a2c  mov     qword ptr [rsp+530h+var_4F8+8], rcx
0x180069a31  sub     rax, rcx
0x180069a34  sar     rax, 5
0x180069a38  mov     qword ptr [rsp+530h+var_4E8], rax
0x180069a3d  movdqa  [rsp+530h+var_4E8+8], xmm0
0x180069a43  movaps  xmm1, [rsp+530h+var_4F8+8]
0x180069a48  movdqa  [rsp+530h+var_4F8+8], xmm1
0x180069a4e  lea     r8, [rsp+530h+var_4E8+8]
0x180069a53  lea     rdx, [rsp+530h+var_4F8+8]
0x180069a58  lea     rcx, [rbp+430h+var_498]
0x180069a5c  call    ??0OTelReader@Diagnostics@@QEAA@V?$span@$$CBVpath@filesystem@std@@$0?0@std@@V?$span@$$CBU?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBU?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@2@@std@@$0?0@2@@std@@$0?0@3@@Z; Diagnostics::OTelReader::OTelReader(std::span<std::filesystem::path const,-1>,std::span<std::pair<std::wstring_view,std::span<std::pair<std::wstring_view,std::span<std::wstring_view const,-1>> const,-1>> const,-1>)
0x180069a61  nop
0x180069a62  xor     edx, edx; Val
0x180069a64  mov     r8d, 2C0h; Size
0x180069a6a  lea     rcx, [rbp+430h+var_310]; void *
0x180069a71  call    memset
0x180069a76  mov     rdx, r15; struct std::filesystem::path *
0x180069a79  lea     rcx, [rbp+430h+var_310]; this
0x180069a80  call    ??0OTelFile@Diagnostics@@QEAA@AEBVpath@filesystem@std@@@Z; Diagnostics::OTelFile::OTelFile(std::filesystem::path const &)
0x180069a85  nop
0x180069a86  mov     rcx, qword ptr [rsp+530h+var_4D0]
0x180069a8b  mov     rax, [rcx]
0x180069a8e  mov     rax, [rax+18h]
0x180069a92  call    _guard_dispatch_icall
0x180069a97  lea     rdx, [rbp+430h+var_470]
0x180069a9b  lea     rcx, [rbp+430h+var_498]
0x180069a9f  call    ?ReadNextEvent@OTelReader@Diagnostics@@QEAA?AV?$optional@VOTelLogRecord@Diagnostics@@@std@@XZ; Diagnostics::OTelReader::ReadNextEvent(void)
0x180069aa4  jmp     short loc_180069AE3
0x180069aa6  mov     rcx, qword ptr [rsp+530h+var_4D0]
0x180069aab  mov     rax, [rcx]
0x180069aae  lea     r8, [rbp+430h+var_310]
0x180069ab5  lea     rdx, [rbp+430h+var_470]
0x180069ab9  mov     rax, [rax+20h]
0x180069abd  call    _guard_dispatch_icall
0x180069ac2  nop
0x180069ac3  cmp     [rbp+430h+var_320], 0
0x180069aca  jz      short loc_180069AD5
0x180069acc  lea     rcx, [rbp+430h+var_470]; this
0x180069ad0  call    ??1OTelLogRecord@Diagnostics@@QEAA@XZ; Diagnostics::OTelLogRecord::~OTelLogRecord(void)
0x180069ad5  lea     rdx, [rbp+430h+var_470]
0x180069ad9  lea     rcx, [rbp+430h+var_498]
0x180069add  call    ?ReadNextEvent@OTelReader@Diagnostics@@QEAA?AV?$optional@VOTelLogRecord@Diagnostics@@@std@@XZ; Diagnostics::OTelReader::ReadNextEvent(void)
0x180069ae2  nop
0x180069ae3  mov     al, [rbp+430h+var_320]
0x180069ae9  test    al, al
0x180069aeb  jnz     short loc_180069AA6
0x180069aed  mov     rcx, qword ptr [rsp+530h+var_4D0]
0x180069af2  mov     rax, [rcx]
0x180069af5  mov     rax, [rax+28h]
0x180069af9  call    _guard_dispatch_icall
0x180069afe  mov     ebx, [rbp+430h+var_58]
0x180069b04  lea     rcx, [rbp+430h+var_310]; this
0x180069b0b  call    ??1OTelFile@Diagnostics@@UEAA@XZ; Diagnostics::OTelFile::~OTelFile(void)
0x180069b10  nop
0x180069b11  lea     rcx, [rbp+430h+var_498]
0x180069b15  call    ??1?$vector@VOTelFile@Diagnostics@@V?$allocator@VOTelFile@Diagnostics@@@std@@@std@@QEAA@XZ; std::vector<Diagnostics::OTelFile>::~vector<Diagnostics::OTelFile>(void)
0x180069b1a  jmp     short loc_180069B1E
0x180069b1c  xor     ebx, ebx
0x180069b1e  lea     rcx, [rsp+530h+var_4D0+8]
0x180069b23  call    ??1?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@QEAA@XZ; std::vector<std::filesystem::path>::~vector<std::filesystem::path>(void)
0x180069b28  nop
0x180069b29  lea     rcx, [rbp+430h+var_4B0]
0x180069b2d  call    ??1?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@QEAA@XZ; std::vector<std::filesystem::path>::~vector<std::filesystem::path>(void)
0x180069b32  nop
0x180069b33  mov     rcx, qword ptr [rsp+530h+var_4D0]
0x180069b38  test    rcx, rcx
0x180069b3b  jz      short loc_180069B4D
0x180069b3d  mov     rdx, [rcx]
0x180069b40  mov     rax, [rdx]
0x180069b43  mov     edx, 1
0x180069b48  call    _guard_dispatch_icall
0x180069b4d  mov     eax, ebx
0x180069b4f  mov     rcx, [rbp+430h+var_50]
0x180069b56  xor     rcx, rsp; StackCookie
0x180069b59  call    __security_check_cookie
0x180069b5e  movaps  xmm6, [rsp+530h+var_48+8]
0x180069b66  add     rsp, 500h
0x180069b6d  pop     r15
0x180069b6f  pop     r14
0x180069b71  pop     r13
0x180069b73  pop     rdi
0x180069b74  pop     rsi
0x180069b75  pop     rbx
0x180069b76  pop     rbp
0x180069b77  retn
0x180069b78  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
