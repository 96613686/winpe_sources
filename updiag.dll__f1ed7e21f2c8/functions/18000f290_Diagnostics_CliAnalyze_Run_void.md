# Diagnostics::CliAnalyze::Run(void)

- ea: `0x18000f290`
- end: `0x18000fae1`
- name: `?Run@CliAnalyze@Diagnostics@@QEAAXXZ`
- size: `2129`
- prototype: `void __fastcall(Diagnostics::CliAnalyze *__hidden this)`
- caller_count: `1`
- callee_count: `31`
- tags: `installer_update`

## callers

- `0x18000ef98`

## callees

- `0x180008a2c`
- `0x180009548`
- `0x18000ee04`
- `0x18000eec4`
- `0x18000f290`
- `0x18000fb00`
- `0x18000fcbc`
- `0x18000fd6c`
- `0x18000fef4`
- `0x18001014c`
- `0x18001046c`
- `0x1800106e8`
- `0x18001095c`
- `0x180010998`
- `0x1800116e4`
- `0x180011be4`
- `0x180015fb0`
- `0x180016e7c`
- `0x18001759c`
- `0x180017e08`
- `0x180018014`
- `0x18001815c`
- `0x1800185a8`
- `0x180018660`
- `0x180018854`
- `0x180018ce0`
- `0x180018d28`
- `0x180018eec`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000f3c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000f3c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f44d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f49e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f7ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f928`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f9d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f9e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f44d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f49e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f7ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f928`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f9d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000f9e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f46b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f8dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f99b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f46b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f8dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000f99b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f355`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f355`

## pseudocode

```c
void __fastcall Diagnostics::CliAnalyze::Run(Diagnostics::CliAnalyze *this)
{
  HSTRING v1; // rsi
  Diagnostics::CliAnalyze *v2; // r14
  UINT32 v3; // r15d
  PCWSTR v4; // rbx
  PCWSTR v5; // r12
  HLOCAL v6; // rbx
  char v7; // r13
  HRESULT v8; // eax
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  HSTRING v12; // r14
  PCWSTR StringRawBuffer; // rax
  __int64 v14; // rax
  HSTRING v15; // rbx
  HSTRING v16; // rdi
  HSTRING v17; // rax
  const WCHAR *v18; // r12
  __int64 v19; // r14
  HSTRING v20; // r13
  __int64 v21; // r15
  HSTRING v22; // rbx
  const WCHAR *v23; // r9
  int v24; // r10d
  __int64 v25; // rdx
  HSTRING *v26; // rax
  void **v27; // r14
  _WORD *v28; // r15
  __int64 v29; // rbx
  __int64 v30; // rax
  unsigned int OutputTypeForFile; // eax
  unsigned int OutputType; // eax
  HSTRING v33; // rcx
  __int64 v34; // rax
  PCWSTR v35; // rcx
  unsigned int v36; // eax
  HSTRING v37; // rcx
  __int64 v38; // r8
  PCWSTR v39; // rax
  __int64 v40; // rax
  __int64 ResourceString; // rdx
  __int64 v42; // rax
  unsigned int v43; // eax
  int v44; // [rsp+20h] [rbp-288h]
  const char *v45; // [rsp+28h] [rbp-280h]
  HSTRING v46; // [rsp+38h] [rbp-270h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-268h] BYREF
  __int64 v48; // [rsp+48h] [rbp-260h]
  const WCHAR *v49; // [rsp+50h] [rbp-258h] BYREF
  __int64 v50; // [rsp+58h] [rbp-250h]
  PCWSTR v51; // [rsp+60h] [rbp-248h] BYREF
  __int64 v52; // [rsp+68h] [rbp-240h]
  _BYTE v53[32]; // [rsp+70h] [rbp-238h] BYREF
  _BYTE v54[32]; // [rsp+90h] [rbp-218h] BYREF
  UINT32 length[4]; // [rsp+B0h] [rbp-1F8h] BYREF
  HSTRING v56[2]; // [rsp+C0h] [rbp-1E8h] BYREF
  HSTRING string[2]; // [rsp+D0h] [rbp-1D8h] BYREF
  HSTRING v58[2]; // [rsp+E0h] [rbp-1C8h] BYREF
  __int64 v59; // [rsp+F0h] [rbp-1B8h]
  HSTRING v60; // [rsp+100h] [rbp-1A8h] BYREF
  __int128 v61; // [rsp+108h] [rbp-1A0h] BYREF
  __int64 v62; // [rsp+118h] [rbp-190h]
  _OWORD v63[21]; // [rsp+120h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  v1 = (HSTRING)this;
  v58[0] = (HSTRING)this;
  v2 = this;
  hMem = this;
  v3 = 0;
  length[0] = 0;
  v61 = 0;
  v62 = 0;
  Diagnostics::CliAnalyze::GetAnalyzerNames(this, &v61);
  if ( *((_BYTE *)v2 + 536) )
  {
    v5 = (PCWSTR)*((_QWORD *)&v61 + 1);
    v4 = (PCWSTR)v61;
    if ( (_QWORD)v61 == *((_QWORD *)&v61 + 1) )
    {
      DiagUtils::GetMessageW(&hMem, 1073742825);
      v6 = hMem;
      if ( hMem )
        std::operator<<<wchar_t,std::char_traits<wchar_t>>(&std::wcout, hMem);
      if ( v6 )
        LocalFree(v6);
    }
    else
    {
      v7 = 1;
      v49 = (const WCHAR *)*((_QWORD *)&v61 + 1);
      while ( 1 )
      {
        v51 = v4;
        if ( v4 == v5 )
          break;
        if ( !v7 )
          std::endl<wchar_t,std::char_traits<wchar_t>>(&std::wcout);
        v7 = 0;
        *(_OWORD *)v56 = *(_OWORD *)v4;
        Diagnostics::CliAnalyze::PrintAnalyzerTitle(v1, v56);
        try
        {
          string[0] = 0;
          v8 = WindowsCreateString(*(PCNZWCH *)v4, *((_QWORD *)v4 + 1), string);
          if ( v8 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x103,
              (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
              (const char *)(unsigned int)v8,
              v44);
          v60 = 0;
          v9 = (__int64 *)*((_QWORD *)v2 + 77);
          v10 = *v9;
          v60 = 0;
          v11 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, HSTRING *))(v10 + 56))(v9, string[0], &v60);
          if ( v11 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x105,
              (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\inc\\UpDiag.hpp",
              (const char *)(unsigned int)v11,
              v44);
          v12 = v60;
          v60 = 0;
          v56[0] = v12;
          v3 |= 1u;
          length[0] = v3;
          if ( string[0] )
            WindowsDeleteString(string[0]);
          if ( v12 )
          {
            LODWORD(string[0]) = 0;
            StringRawBuffer = WindowsGetStringRawBuffer(v12, (UINT32 *)string);
            if ( LODWORD(string[0]) )
            {
              v14 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(
                      &std::wcout,
                      StringRawBuffer,
                      LODWORD(string[0]));
              std::endl<wchar_t,std::char_traits<wchar_t>>(v14);
            }
          }
          if ( v12 )
            WindowsDeleteString(v12);
        }
        catch ( ... )
        {
          v7 = 0;
          v4 = v51;
          v5 = v49;
          v3 = length[0];
          v1 = v58[0];
        }
        v4 += 8;
        v2 = (Diagnostics::CliAnalyze *)hMem;
      }
    }
  }
  else if ( *((_BYTE *)v1 + 537) )
  {
    if ( (_QWORD)v61 != *((_QWORD *)&v61 + 1) )
    {
      ResourceString = DiagUtils::LoadResourceString(v53, 4001);
      v42 = std::operator<<<wchar_t>(&std::wcerr, ResourceString);
      std::wostream::operator<<(v42);
      std::filesystem::path::~path((std::filesystem::path *)v53);
      v43 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0xD6,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\cmdline\\CliAnalyze.hpp",
        (const char *)v43,
        (int)"Cannot specify multiple analyzers to list",
        v45);
    }
    *(_OWORD *)v58 = 0;
    v59 = 0;
    UpdateDiagnostics::update_diagnostics::GetAnalyzerList(v1 + 152, v58);
    v15 = v58[0];
    v16 = v58[1];
    while ( v15 != v16 )
    {
      v17 = v15;
      if ( *((_QWORD *)v15 + 3) > 7u )
        v17 = *(HSTRING *)v15;
      v56[0] = v17;
      v56[1] = *((HSTRING *)v15 + 2);
      Diagnostics::CliAnalyze::PrintAnalyzerTitle(v1, v56);
      v15 += 8;
    }
    std::vector<std::filesystem::path>::~vector<std::filesystem::path>(v58);
  }
  else
  {
    v18 = (const WCHAR *)*((_QWORD *)v1 + 72);
    if ( v18 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v18[v19] );
    }
    else
    {
      v19 = 0;
      v18 = 0;
    }
    v20 = (HSTRING)*((_QWORD *)v1 + 74);
    if ( v20 )
    {
      v21 = -1;
      do
        ++v21;
      while ( *((_WORD *)v20 + v21) );
    }
    else
    {
      v21 = 0;
      v20 = 0;
    }
    memset(v63, 0, 0x148u);
    DWORD2(v63[0]) = 0;
    BYTE12(v63[0]) = 0;
    BYTE8(v63[4]) = 0;
    LODWORD(v63[3]) = 0;
    *((_QWORD *)&v63[3] + 1) = "RunCliAnalyze";
    *(_QWORD *)&v63[4] = 0;
    LODWORD(v63[5]) = 0;
    v63[15] = 0;
    memset((char *)&v63[5] + 8, 0, 0x98u);
    LODWORD(v63[16]) = 1;
    *((_QWORD *)&v63[16] + 1) = 0;
    *(_QWORD *)&v63[17] = (char *)v63 + 8;
    *((_QWORD *)&v63[17] + 1) = 0;
    *(_QWORD *)&v63[18] = 0;
    *((_QWORD *)&v63[18] + 1) = v63;
    *(_QWORD *)&v63[19] = 0;
    DWORD2(v63[19]) = 0;
    *(_QWORD *)&v63[20] = &v63[3];
    *(_QWORD *)&v63[0] = &Diagnostics::Telemetry4Diag::RunCliAnalyze::`vftable';
    Diagnostics::Telemetry4Diag::RunCliAnalyze::StartActivity(
      (Diagnostics::Telemetry4Diag::RunCliAnalyze *)v63,
      *((const wchar_t **)v1 + 2));
    v22 = 0;
    v46 = 0;
    v23 = (const WCHAR *)*((_QWORD *)v1 + 73);
    v24 = (int)hMem;
    if ( v23 )
    {
      v25 = -1;
      do
        ++v25;
      while ( v23[v25] );
      v56[0] = v20;
      v56[1] = (HSTRING)v21;
      v49 = v18;
      v50 = v19;
      hMem = (HLOCAL)v61;
      v48 = (__int64)(*((_QWORD *)&v61 + 1) - v61) >> 4;
      v51 = v23;
      v52 = v25;
      v26 = (HSTRING *)UpdateDiagnostics::update_diagnostics::RunAnalyzersOffline(
                         v24 + 608,
                         (unsigned int)v58,
                         (unsigned int)&v51,
                         (unsigned int)&hMem,
                         (__int64)&v49,
                         (__int64)v56);
    }
    else
    {
      v56[0] = v20;
      v56[1] = (HSTRING)v21;
      v49 = v18;
      v50 = v19;
      hMem = (HLOCAL)v61;
      v48 = (__int64)(*((_QWORD *)&v61 + 1) - v61) >> 4;
      v26 = (HSTRING *)UpdateDiagnostics::update_diagnostics::RunAnalyzers(
                         v24 + 608,
                         (unsigned int)v58,
                         (unsigned int)&hMem,
                         (unsigned int)&v49,
                         (__int64)v56);
    }
    if ( &v46 != v26 )
    {
      v22 = *v26;
      v46 = *v26;
      *v26 = 0;
    }
    if ( v58[0] )
      WindowsDeleteString(v58[0]);
    v27 = (void **)(v1 + 136);
    if ( *((_QWORD *)v1 + 68) )
    {
      while ( v27 != (void **)(v1 + 142) )
      {
        v28 = *v27;
        if ( !*v27 )
          break;
        v29 = -1;
        v30 = -1;
        do
          ++v30;
        while ( v28[v30] );
        v49 = (const WCHAR *)*v27;
        v50 = v30;
        std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v54, &v49);
        OutputTypeForFile = Diagnostics::CliAnalyze::GetOutputTypeForFile(v54);
        OutputType = Diagnostics::CliAnalyze::GetOutputType(v1, OutputTypeForFile);
        Diagnostics::CliAnalyze::TransformOutput(v1, v58, &v46, OutputType);
        std::wstring::~wstring(v54);
        do
          ++v29;
        while ( v28[v29] );
        hMem = v28;
        v48 = v29;
        std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v53, &hMem);
        v22 = v46;
        v33 = v46;
        if ( LOBYTE(v58[1]) )
          v33 = v58[0];
        if ( v33 )
        {
          length[0] = 0;
          v35 = WindowsGetStringRawBuffer(v33, length);
          v34 = length[0];
        }
        else
        {
          v34 = 0;
          v35 = 0;
        }
        v51 = v35;
        v52 = v34;
        Diagnostics::CliAnalyze::WriteToFile(&v51, v53);
        std::wstring::~wstring(v53);
        if ( LOBYTE(v58[1]) && v58[0] )
          WindowsDeleteString(v58[0]);
        ++v27;
      }
    }
    else
    {
      v36 = Diagnostics::CliAnalyze::GetOutputType(v1, 1);
      Diagnostics::CliAnalyze::TransformOutput(v1, v56, &v46, v36);
      v22 = v46;
      v37 = v46;
      if ( LOBYTE(v56[1]) )
        v37 = v56[0];
      if ( v37 )
      {
        length[0] = 0;
        v39 = WindowsGetStringRawBuffer(v37, length);
        v38 = length[0];
      }
      else
      {
        v38 = 0;
        v39 = 0;
      }
      v40 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(&std::wcout, v39, v38);
      std::endl<wchar_t,std::char_traits<wchar_t>>(v40);
      if ( LOBYTE(v56[1]) && v56[0] )
        WindowsDeleteString(v56[0]);
    }
    if ( v22 )
      WindowsDeleteString(v22);
    *(_QWORD *)&v63[0] = &Diagnostics::Telemetry4Diag::RunCliAnalyze::`vftable';
    wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v63);
    wil::ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Diagnostics::Telemetry4Diag,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v63);
  }
  std::vector<std::wstring_view>::~vector<std::wstring_view>(&v61);
}

```

## disassembly

```asm
0x18000f290  mov     r11, rsp
0x18000f293  mov     [r11+10h], rbx
0x18000f297  mov     [r11+18h], rsi
0x18000f29b  push    rdi
0x18000f29c  push    r12
0x18000f29e  push    r13
0x18000f2a0  push    r14
0x18000f2a2  push    r15
0x18000f2a4  sub     rsp, 280h
0x18000f2ab  mov     rax, cs:__security_cookie
0x18000f2b2  xor     rax, rsp
0x18000f2b5  mov     [rsp+2A8h+var_38], rax
0x18000f2bd  mov     rsi, rcx
0x18000f2c0  mov     [rsp+2A8h+var_1C8], rcx
0x18000f2c8  mov     r14, rcx
0x18000f2cb  mov     [rsp+2A8h+hMem], rcx
0x18000f2d0  xor     edi, edi
0x18000f2d2  mov     r15d, edi
0x18000f2d5  mov     [rsp+2A8h+length], edi
0x18000f2dc  xorps   xmm0, xmm0
0x18000f2df  xor     eax, eax
0x18000f2e1  movups  [rsp+2A8h+var_1A0], xmm0
0x18000f2e9  mov     [r11-190h], rax
0x18000f2f0  lea     rdx, [r11-1A0h]
0x18000f2f7  call    ?GetAnalyzerNames@CliAnalyze@Diagnostics@@AEAA?AV?$vector@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$allocator@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@@std@@XZ; Diagnostics::CliAnalyze::GetAnalyzerNames(void)
0x18000f2fc  nop
0x18000f2fd  cmp     [r14+218h], dil
0x18000f304  jz      loc_18000F4D6
0x18000f30a  mov     rbx, qword ptr [rsp+2A8h+var_1A0]
0x18000f312  mov     r12, qword ptr [rsp+2A8h+var_1A0+8]
0x18000f31a  cmp     rbx, r12
0x18000f31d  jnz     short loc_18000F360
0x18000f31f  mov     edx, 400003E9h
0x18000f324  lea     rcx, [rsp+2A8h+hMem]
0x18000f329  call    ?GetMessageW@DiagUtils@@SA?AV?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@K@Z; DiagUtils::GetMessageW(ulong)
0x18000f32e  nop
0x18000f32f  mov     rbx, [rsp+2A8h+hMem]
0x18000f334  test    rbx, rbx
0x18000f337  jz      short loc_18000F349
0x18000f339  mov     rdx, rbx
0x18000f33c  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x18000f343  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18000f348  nop
0x18000f349  test    rbx, rbx
0x18000f34c  jz      loc_18000FA18
0x18000f352  mov     rcx, rbx; hMem
0x18000f355  call    cs:__imp_LocalFree
0x18000f35b  jmp     loc_18000FA18
0x18000f360  mov     r13b, 1
0x18000f363  mov     [rsp+2A8h+var_258], r12
0x18000f368  mov     [rsp+2A8h+var_248], rbx
0x18000f36d  cmp     rbx, r12
0x18000f370  jz      loc_18000FA18
0x18000f376  test    r13b, r13b
0x18000f379  jnz     short loc_18000F387
0x18000f37b  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x18000f382  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x18000f387  mov     r13b, dil
0x18000f38a  mov     [rsp+2A8h+var_278], dil
0x18000f38f  movups  xmm0, xmmword ptr [rbx]
0x18000f392  movdqu  xmmword ptr [rsp+2A8h+var_1E8], xmm0
0x18000f39b  lea     rdx, [rsp+2A8h+var_1E8]
0x18000f3a3  mov     rcx, rsi
0x18000f3a6  call    ?PrintAnalyzerTitle@CliAnalyze@Diagnostics@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Diagnostics::CliAnalyze::PrintAnalyzerTitle(std::wstring_view)
0x18000f3ab  nop
0x18000f3ac  mov     [rsp+2A8h+string], rdi
0x18000f3b4  lea     r8, [rsp+2A8h+string]; string
0x18000f3bc  mov     rdx, [rbx+8]; length
0x18000f3c0  mov     rcx, [rbx]; sourceString
0x18000f3c3  call    cs:__imp_WindowsCreateString
0x18000f3c9  mov     rcx, [rsp+2A8h]; this
0x18000f3d1  test    eax, eax
0x18000f3d3  js      loc_18000FA52
0x18000f3d9  mov     [rsp+2A8h+var_1A8], rdi
0x18000f3e1  mov     rcx, [r14+268h]
0x18000f3e8  mov     rax, [rcx]
0x18000f3eb  mov     [rsp+2A8h+var_1A8], rdi
0x18000f3f3  lea     r8, [rsp+2A8h+var_1A8]
0x18000f3fb  mov     rdx, [rsp+2A8h+string]
0x18000f403  mov     rax, [rax+38h]
0x18000f407  call    _guard_dispatch_icall
0x18000f40c  mov     rcx, [rsp+2A8h]; this
0x18000f414  test    eax, eax
0x18000f416  js      loc_18000FA67
0x18000f41c  mov     r14, [rsp+2A8h+var_1A8]
0x18000f424  mov     [rsp+2A8h+var_1A8], rdi
0x18000f42c  mov     [rsp+2A8h+var_1E8], r14
0x18000f434  or      r15d, 1
0x18000f438  mov     [rsp+2A8h+length], r15d
0x18000f440  mov     rcx, [rsp+2A8h+string]; string
0x18000f448  test    rcx, rcx
0x18000f44b  jz      short loc_18000F454
0x18000f44d  call    cs:__imp_WindowsDeleteString
0x18000f453  nop
0x18000f454  test    r14, r14
0x18000f457  jz      short loc_18000F496
0x18000f459  mov     dword ptr [rsp+2A8h+string], edi
0x18000f460  lea     rdx, [rsp+2A8h+string]; length
0x18000f468  mov     rcx, r14; string
0x18000f46b  call    cs:__imp_WindowsGetStringRawBuffer
0x18000f471  mov     r8d, dword ptr [rsp+2A8h+string]
0x18000f479  test    r8, r8
0x18000f47c  jz      short loc_18000F496
0x18000f47e  mov     rdx, rax
0x18000f481  lea     rcx, ?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcout
0x18000f488  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x18000f48d  mov     rcx, rax
0x18000f490  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x18000f495  nop
0x18000f496  test    r14, r14
0x18000f499  jz      short loc_18000F4A5
0x18000f49b  mov     rcx, r14; string
0x18000f49e  call    cs:__imp_WindowsDeleteString
0x18000f4a4  nop
0x18000f4a5  jmp     short loc_18000F4C8
0x18000f4a7  xor     edi, edi
0x18000f4a9  mov     r13b, [rsp+2A8h+var_278]
0x18000f4ae  mov     rbx, [rsp+2A8h+var_248]
0x18000f4b3  mov     r12, [rsp+2A8h+var_258]
0x18000f4b8  mov     r15d, [rsp+2A8h+length]
0x18000f4c0  mov     rsi, [rsp+2A8h+var_1C8]
0x18000f4c8  add     rbx, 10h
0x18000f4cc  mov     r14, [rsp+2A8h+hMem]
0x18000f4d1  jmp     loc_18000F368
0x18000f4d6  cmp     [rsi+219h], dil
0x18000f4dd  jz      loc_18000F581
0x18000f4e3  mov     rax, qword ptr [rsp+2A8h+var_1A0+8]
0x18000f4eb  cmp     qword ptr [rsp+2A8h+var_1A0], rax
0x18000f4f3  jnz     loc_18000FA7C
0x18000f4f9  xorps   xmm0, xmm0
0x18000f4fc  xor     eax, eax
0x18000f4fe  movups  xmmword ptr [rsp+2A8h+var_1C8], xmm0
0x18000f506  mov     [rsp+2A8h+var_1B8], rax
0x18000f50e  lea     rcx, [rsi+260h]
0x18000f515  lea     rdx, [rsp+2A8h+var_1C8]
0x18000f51d  call    ?GetAnalyzerList@update_diagnostics@UpdateDiagnostics@@QEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ; UpdateDiagnostics::update_diagnostics::GetAnalyzerList(void)
0x18000f522  nop
0x18000f523  mov     rbx, [rsp+2A8h+var_1C8]
0x18000f52b  mov     rdi, [rsp+2A8h+var_1C8+8]
0x18000f533  jmp     short loc_18000F56A
0x18000f535  mov     rax, rbx
0x18000f538  cmp     qword ptr [rbx+18h], 7
0x18000f53d  jbe     short loc_18000F542
0x18000f53f  mov     rax, [rbx]
0x18000f542  mov     [rsp+2A8h+var_1E8], rax
0x18000f54a  mov     rax, [rbx+10h]
0x18000f54e  mov     [rsp+2A8h+var_1E8+8], rax
0x18000f556  lea     rdx, [rsp+2A8h+var_1E8]
0x18000f55e  mov     rcx, rsi
0x18000f561  call    ?PrintAnalyzerTitle@CliAnalyze@Diagnostics@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Diagnostics::CliAnalyze::PrintAnalyzerTitle(std::wstring_view)
0x18000f566  add     rbx, 20h ; ' '
0x18000f56a  cmp     rbx, rdi
0x18000f56d  jnz     short loc_18000F535
0x18000f56f  lea     rcx, [rsp+2A8h+var_1C8]
0x18000f577  call    ??1?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@QEAA@XZ; std::vector<std::filesystem::path>::~vector<std::filesystem::path>(void)
0x18000f57c  jmp     loc_18000FA18
0x18000f581  mov     r12, [rsi+240h]
0x18000f588  test    r12, r12
0x18000f58b  jz      short loc_18000F59D
0x18000f58d  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000f591  inc     r14
0x18000f594  cmp     [r12+r14*2], di
0x18000f599  jnz     short loc_18000F591
0x18000f59b  jmp     short loc_18000F5A3
0x18000f59d  mov     r14, rdi
0x18000f5a0  mov     r12, rdi
0x18000f5a3  mov     r13, [rsi+250h]
0x18000f5aa  test    r13, r13
0x18000f5ad  jz      short loc_18000F5C0
0x18000f5af  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000f5b3  inc     r15
0x18000f5b6  cmp     [r13+r15*2+0], di
0x18000f5bc  jnz     short loc_18000F5B3
0x18000f5be  jmp     short loc_18000F5C6
0x18000f5c0  mov     r15, rdi
0x18000f5c3  mov     r13, rdi
0x18000f5c6  xor     edx, edx; Val
0x18000f5c8  mov     r8d, 148h; Size
0x18000f5ce  lea     rcx, [rsp+2A8h+var_188]; void *
0x18000f5d6  call    memset
0x18000f5db  nop
0x18000f5dc  mov     [rsp+2A8h+var_180], edi
0x18000f5e3  mov     [rsp+2A8h+var_17C], dil
0x18000f5eb  mov     [rsp+2A8h+var_140], dil
0x18000f5f3  mov     [rsp+2A8h+var_158], edi
0x18000f5fa  lea     rax, aRunclianalyze; "RunCliAnalyze"
0x18000f601  mov     [rsp+2A8h+var_150], rax
0x18000f609  mov     [rsp+2A8h+var_148], rdi
0x18000f611  mov     [rsp+2A8h+var_138], edi
0x18000f618  xorps   xmm0, xmm0
0x18000f61b  movdqa  [rsp+2A8h+var_98], xmm0
0x18000f624  xor     edx, edx; Val
0x18000f626  mov     r8d, 98h; Size
0x18000f62c  lea     rcx, [rsp+2A8h+var_130]; void *
0x18000f634  call    memset
0x18000f639  mov     [rsp+2A8h+var_88], 1
0x18000f644  xor     eax, eax
0x18000f646  mov     [rsp+2A8h+var_80], rax
0x18000f64e  lea     rax, [rsp+2A8h+var_180]
0x18000f656  mov     [rsp+2A8h+var_78], rax
0x18000f65e  mov     [rsp+2A8h+var_70], rdi
0x18000f666  mov     [rsp+2A8h+var_68], rdi
0x18000f66e  lea     rax, [rsp+2A8h+var_188]
0x18000f676  mov     [rsp+2A8h+var_60], rax
0x18000f67e  mov     [rsp+2A8h+var_58], rdi
0x18000f686  mov     [rsp+2A8h+var_50], edi
0x18000f68d  lea     rax, [rsp+2A8h+var_158]
0x18000f695  mov     [rsp+2A8h+var_48], rax
0x18000f69d  lea     rax, ??_7RunCliAnalyze@Telemetry4Diag@Diagnostics@@6B@; const Diagnostics::Telemetry4Diag::RunCliAnalyze::`vftable'
0x18000f6a4  mov     [rsp+2A8h+var_188], rax
0x18000f6ac  mov     rdx, [rsi+10h]; wchar_t *
0x18000f6b0  lea     rcx, [rsp+2A8h+var_188]; this
0x18000f6b8  call    ?StartActivity@RunCliAnalyze@Telemetry4Diag@Diagnostics@@QEAAXPEB_W@Z; Diagnostics::Telemetry4Diag::RunCliAnalyze::StartActivity(wchar_t const *)
0x18000f6bd  nop
0x18000f6be  mov     rbx, rdi
0x18000f6c1  mov     [rsp+2A8h+var_270], rbx
0x18000f6c6  mov     r9, [rsi+248h]
0x18000f6cd  mov     r10, [rsp+2A8h+hMem]
0x18000f6d2  test    r9, r9
0x18000f6d5  jz      loc_18000F765
0x18000f6db  mov     rax, qword ptr [rsp+2A8h+var_1A0+8]
0x18000f6e3  mov     r8, qword ptr [rsp+2A8h+var_1A0]
0x18000f6eb  sub     rax, r8
0x18000f6ee  sar     rax, 4
0x18000f6f2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000f6f6  inc     rdx
0x18000f6f9  cmp     [r9+rdx*2], di
0x18000f6fe  jnz     short loc_18000F6F6
0x18000f700  mov     [rsp+2A8h+var_1E8], r13
0x18000f708  mov     [rsp+2A8h+var_1E8+8], r15
0x18000f710  mov     [rsp+2A8h+var_258], r12
0x18000f715  mov     [rsp+2A8h+var_250], r14
0x18000f71a  mov     [rsp+2A8h+hMem], r8
0x18000f71f  mov     [rsp+2A8h+var_260], rax
0x18000f724  mov     [rsp+2A8h+var_248], r9
0x18000f729  mov     [rsp+2A8h+var_240], rdx
0x18000f72e  lea     rax, [rsp+2A8h+var_1E8]
0x18000f736  mov     [rsp+2A8h+var_280], rax
0x18000f73b  lea     rax, [rsp+2A8h+var_258]
0x18000f740  mov     qword ptr [rsp+2A8h+var_288], rax
0x18000f745  lea     r9, [rsp+2A8h+hMem]
0x18000f74a  lea     r8, [rsp+2A8h+var_248]
0x18000f74f  lea     rdx, [rsp+2A8h+var_1C8]
0x18000f757  lea     rcx, [r10+260h]
0x18000f75e  call    ?RunAnalyzersOffline@update_diagnostics@UpdateDiagnostics@@QEAA?AUhstring_view@2@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@5@00@Z; UpdateDiagnostics::update_diagnostics::RunAnalyzersOffline(std::wstring_view,std::span<std::wstring_view const,-1>,std::wstring_view,std::wstring_view)
0x18000f763  jmp     short loc_18000F7CB
0x18000f765  mov     [rsp+2A8h+var_1E8], r13
0x18000f76d  mov     [rsp+2A8h+var_1E8+8], r15
0x18000f775  mov     [rsp+2A8h+var_258], r12
0x18000f77a  mov     [rsp+2A8h+var_250], r14
0x18000f77f  mov     rax, qword ptr [rsp+2A8h+var_1A0]
0x18000f787  mov     [rsp+2A8h+hMem], rax
0x18000f78c  mov     rcx, qword ptr [rsp+2A8h+var_1A0+8]
0x18000f794  sub     rcx, rax
0x18000f797  sar     rcx, 4
0x18000f79b  mov     [rsp+2A8h+var_260], rcx
0x18000f7a0  lea     rax, [rsp+2A8h+var_1E8]
0x18000f7a8  mov     qword ptr [rsp+2A8h+var_288], rax
0x18000f7ad  lea     r9, [rsp+2A8h+var_258]
0x18000f7b2  lea     r8, [rsp+2A8h+hMem]
0x18000f7b7  lea     rdx, [rsp+2A8h+var_1C8]
0x18000f7bf  lea     rcx, [r10+260h]
0x18000f7c6  call    ?RunAnalyzers@update_diagnostics@UpdateDiagnostics@@QEAA?AUhstring_view@2@V?$span@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z; UpdateDiagnostics::update_diagnostics::RunAnalyzers(std::span<std::wstring_view const,-1>,std::wstring_view,std::wstring_view)
0x18000f7cb  lea     rcx, [rsp+2A8h+var_270]
0x18000f7d0  cmp     rcx, rax
0x18000f7d3  jz      short loc_18000F7E0
0x18000f7d5  mov     rbx, [rax]
0x18000f7d8  mov     [rsp+2A8h+var_270], rbx
0x18000f7dd  mov     [rax], rdi
0x18000f7e0  mov     rcx, [rsp+2A8h+var_1C8]; string
0x18000f7e8  test    rcx, rcx
0x18000f7eb  jz      short loc_18000F7F3
0x18000f7ed  call    cs:__imp_WindowsDeleteString
0x18000f7f3  lea     r14, [rsi+220h]
0x18000f7fa  cmp     [r14], rdi
0x18000f7fd  jz      loc_18000F940
0x18000f803  lea     r12, [r14+18h]
0x18000f807  jmp     loc_18000F932
0x18000f80c  mov     r15, [r14]
0x18000f80f  test    r15, r15
0x18000f812  jz      loc_18000F9DF
0x18000f818  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f81c  mov     rax, rbx
0x18000f81f  inc     rax
0x18000f822  cmp     [r15+rax*2], di
0x18000f827  jnz     short loc_18000F81F
0x18000f829  mov     [rsp+2A8h+var_258], r15
0x18000f82e  mov     [rsp+2A8h+var_250], rax
0x18000f833  lea     rdx, [rsp+2A8h+var_258]
0x18000f838  lea     rcx, [rsp+2A8h+var_218]
0x18000f840  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x18000f845  nop
0x18000f846  lea     rcx, [rsp+2A8h+var_218]
0x18000f84e  call    ?GetOutputTypeForFile@CliAnalyze@Diagnostics@@CA?AW4OutputType@12@AEBVpath@filesystem@std@@@Z; Diagnostics::CliAnalyze::GetOutputTypeForFile(std::filesystem::path const &)
0x18000f853  mov     edx, eax
0x18000f855  mov     rcx, rsi
0x18000f858  call    ?GetOutputType@CliAnalyze@Diagnostics@@AEBA?AW4OutputType@12@W4312@@Z; Diagnostics::CliAnalyze::GetOutputType(Diagnostics::CliAnalyze::OutputType)
0x18000f85d  mov     r9d, eax
0x18000f860  lea     r8, [rsp+2A8h+var_270]
0x18000f865  lea     rdx, [rsp+2A8h+var_1C8]
  ... truncated ...
```
