# Diagnostics::SourceHandler_SQLite::ConvertData(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::filesystem::path const &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x180033e10`
- end: `0x180034618`
- name: `?ConvertData@SourceHandler_SQLite@Diagnostics@@UEAAIV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBVpath@filesystem@4@0@Z`
- size: `2056`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, loader_planting`

## callees

- `0x1800153b0`
- `0x180015c50`
- `0x18001639c`
- `0x180016e0c`
- `0x180018eec`
- `0x1800292f4`
- `0x18002a018`
- `0x18002a204`
- `0x18002d4ac`
- `0x18002d73c`
- `0x18002d990`
- `0x18002da90`
- `0x180033c68`
- `0x180033e10`
- `0x18003b03c`
- `0x18003b7d0`
- `0x18003bde8`
- `0x180046600`
- `0x180049870`
- `0x180051370`
- `0x180052598`
- `0x180061b98`
- `0x180066844`
- `0x1800670a4`
- `0x18008fdcc`
- `0x18008fe00`
- `0x1800961f0`

## import_xrefs

- `winsqlite3!sqlite3_column_count` at `0x180033fe9`
- `winsqlite3!sqlite3_column_count` at `0x180033fe9`
- `winsqlite3!sqlite3_errmsg` at `0x180033f20`
- `winsqlite3!sqlite3_errmsg` at `0x180033f20`
- `winsqlite3!sqlite3_prepare16_v2` at `0x180033f0c`
- `winsqlite3!sqlite3_prepare16_v2` at `0x180033f0c`
- `winsqlite3!sqlite3_finalize` at `0x1800345ea`
- `winsqlite3!sqlite3_finalize` at `0x1800345ea`
- `winsqlite3!sqlite3_column_text16` at `0x18003435a`
- `winsqlite3!sqlite3_column_text16` at `0x18003440a`
- `winsqlite3!sqlite3_column_text16` at `0x18003435a`
- `winsqlite3!sqlite3_column_text16` at `0x18003440a`
- `winsqlite3!sqlite3_step` at `0x180034338`
- `winsqlite3!sqlite3_step` at `0x180034338`
- `winsqlite3!sqlite3_column_name` at `0x18003405b`
- `winsqlite3!sqlite3_column_name` at `0x18003405b`

## string_xrefs

- `0x180033e61`: `Database is not open`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Diagnostics::SourceHandler_SQLite::ConvertData(
        __int64 a1,
        __int128 *a2,
        const struct std::filesystem::path *a3,
        __int64 *a4)
{
  unsigned __int64 v7; // r13
  int v8; // esi
  __int64 v9; // rbx
  __int64 v10; // r12
  unsigned int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rax
  WCHAR *v14; // rax
  __int64 result; // rax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int i; // ebx
  __int64 v21; // rax
  __int64 v22; // rcx
  void *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r15
  unsigned __int128 v29; // kr10_16
  unsigned __int64 v30; // rdx
  __int64 v31; // rdi
  __int64 v32; // rax
  __int64 v33; // r14
  unsigned __int64 j; // rsi
  unsigned __int64 v35; // rax
  unsigned int v36; // r14d
  _DWORD *v37; // rcx
  char v38; // si
  __int64 v39; // rbx
  char v40; // di
  const wchar_t *v41; // rax
  __int64 v42; // rsi
  __int64 *v43; // rdi
  __int64 v44; // rax
  __int64 *v45; // rcx
  __int64 *v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // rax
  unsigned int v50; // ebx
  int v51; // [rsp+20h] [rbp-578h]
  const char *v52; // [rsp+30h] [rbp-568h]
  char v53; // [rsp+40h] [rbp-558h]
  __int64 v54; // [rsp+48h] [rbp-550h] BYREF
  int v55; // [rsp+50h] [rbp-548h]
  __int64 v56; // [rsp+58h] [rbp-540h] BYREF
  __int128 v57; // [rsp+60h] [rbp-538h] BYREF
  __int128 v58; // [rsp+70h] [rbp-528h] BYREF
  __int64 v59; // [rsp+80h] [rbp-518h]
  __int128 *v60; // [rsp+88h] [rbp-510h]
  _QWORD v61[4]; // [rsp+90h] [rbp-508h] BYREF
  _QWORD v62[2]; // [rsp+B0h] [rbp-4E8h] BYREF
  _QWORD v63[2]; // [rsp+C0h] [rbp-4D8h] BYREF
  _QWORD v64[2]; // [rsp+D0h] [rbp-4C8h] BYREF
  _QWORD v65[2]; // [rsp+E0h] [rbp-4B8h] BYREF
  _QWORD v66[2]; // [rsp+F0h] [rbp-4A8h] BYREF
  __int64 v67; // [rsp+100h] [rbp-498h] BYREF
  WCHAR WideCharStr[8]; // [rsp+108h] [rbp-490h] BYREF
  __int128 v69; // [rsp+118h] [rbp-480h]
  __int128 v70; // [rsp+128h] [rbp-470h] BYREF
  __int64 v71; // [rsp+138h] [rbp-460h]
  _BYTE v72[336]; // [rsp+140h] [rbp-458h] BYREF
  _DWORD v73[176]; // [rsp+290h] [rbp-308h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+598h] [rbp+0h]

  v60 = a2;
  v59 = a1;
  v7 = 0;
  v8 = 0;
  LODWORD(v54) = 0;
  wil::details::in1diag3::Throw_HrIfNullMsg<sqlite3 *,0>(
    retaddr,
    44,
    "C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\SourceHandler_SQLite.hpp",
    2147500035LL,
    *(_QWORD *)(a1 + 72),
    "Database is not open");
  LOBYTE(v51) = a4[1] == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x2D,
    (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\SourceHandler_SQLite.hpp",
    (const char *)0x80070057LL,
    v51,
    (bool)"SQL filter cannot be empty",
    v52);
  memset(v73, 0, sizeof(v73));
  Diagnostics::OTelFile::OTelFile((Diagnostics::OTelFile *)v73, a3);
  v67 = 0;
  v9 = *a4;
  v10 = -1;
  v11 = sqlite3_prepare16_v2(*(_QWORD *)(a1 + 72), *a4, 0xFFFFFFFFLL, &v67);
  v12 = v11;
  if ( v11 )
  {
    v13 = sqlite3_errmsg(*(_QWORD *)(a1 + 72));
    *(_OWORD *)WideCharStr = 0;
    v69 = 0;
    do
      ++v10;
    while ( *(_BYTE *)(v13 + v10) );
    std::string::_Construct<1,char const *>(WideCharStr, v13, v10);
    v14 = WideCharStr;
    if ( *((_QWORD *)&v69 + 1) > 0xFu )
      v14 = *(WCHAR **)WideCharStr;
    wil::details::in1diag3::Log_Win32Msg(
      retaddr,
      (void *)0x3A,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\SourceHandler_SQLite.hpp",
      (const char *)v12,
      (unsigned int)"Failed with '%hs' while preparing SQL statement: %ls",
      (const char *)v14,
      v9);
    std::string::~string((__int64)WideCharStr);
    Diagnostics::OTelFile::~OTelFile((Diagnostics::OTelFile *)v73);
    return 0;
  }
  else
  {
    try
    {
      v16 = sqlite3_column_count(v67);
      v55 = v16;
      v70 = 0;
      v71 = 0;
      v56 = v16;
      if ( v16 )
      {
        if ( (unsigned __int64)v16 > 0x666666666666666LL )
          std::vector<Diagnostics::SourceHandler_Tsv<Diagnostics::TsvTraitsReportingEvents>::ColumnSpec,std::allocator<Diagnostics::SourceHandler_Tsv<Diagnostics::TsvTraitsReportingEvents>::ColumnSpec>>::_Xlength(
            v16,
            v17,
            v18,
            v19,
            0);
        std::vector<std::pair<std::wstring,enum Diagnostics::ColumnClassifier::ColumnType>>::_Reallocate<0>(&v70, &v56);
        v16 = v55;
      }
      for ( i = 0; (int)i < v16; ++i )
      {
        LODWORD(v54) = 0;
        v21 = sqlite3_column_name(v67, i);
        if ( v21 )
        {
          v22 = -1;
          do
            ++v22;
          while ( *(_BYTE *)(v21 + v22) );
          *(_QWORD *)&v57 = v21;
          *((_QWORD *)&v57 + 1) = v22;
          System::Convert::Utf8ToWideString(WideCharStr);
          v8 |= 1u;
        }
        else
        {
          v23 = (void *)std::to_wstring(v61, i);
          v24 = std::wstring::insert(v23);
          *(_OWORD *)WideCharStr = 0;
          v69 = 0;
          *(_OWORD *)WideCharStr = *(_OWORD *)v24;
          v69 = *(_OWORD *)(v24 + 16);
          *(_WORD *)v24 = 0;
          *(_QWORD *)(v24 + 16) = 0;
          *(_QWORD *)(v24 + 24) = 7;
          v8 |= 3u;
          std::wstring::~wstring((__int64)v61);
        }
        v25 = *((_QWORD *)&v70 + 1);
        if ( *((_QWORD *)&v70 + 1) == v71 )
        {
          std::vector<std::pair<std::wstring,enum Diagnostics::ColumnClassifier::ColumnType>>::_Emplace_reallocate<std::wstring,enum Diagnostics::ColumnClassifier::ColumnType>(
            &v70,
            *((_QWORD *)&v70 + 1),
            WideCharStr,
            &v54);
        }
        else
        {
          **((_OWORD **)&v70 + 1) = 0;
          *(_QWORD *)(v25 + 16) = 0;
          *(_QWORD *)(v25 + 24) = 0;
          *(_OWORD *)v25 = *(_OWORD *)WideCharStr;
          *(_OWORD *)(v25 + 16) = v69;
          WideCharStr[0] = 0;
          *(_QWORD *)&v69 = 0;
          *((_QWORD *)&v69 + 1) = 7;
          *(_DWORD *)(v25 + 32) = 0;
          *((_QWORD *)&v70 + 1) += 40LL;
        }
        std::wstring::~wstring((__int64)WideCharStr);
        v16 = v55;
      }
      v26 = v71;
      v71 = 0;
      v27 = *((_QWORD *)&v70 + 1);
      v54 = *((_QWORD *)&v70 + 1);
      v28 = v70;
      v70 = 0u;
      *(_QWORD *)WideCharStr = v28;
      *(_QWORD *)&WideCharStr[4] = v54;
      *(_QWORD *)&v69 = v26;
      v29 = Diagnostics::ColumnClassifier::_defaultPatterns;
      *(_QWORD *)&v57 = *((_QWORD *)&Diagnostics::ColumnClassifier::_defaultPatterns + 1);
      v30 = 0xCCCCCCCCCCCCCCCDuLL;
      while ( (_QWORD)v29 != *((_QWORD *)&v29 + 1) )
      {
        v31 = *(_QWORD *)(v29 + 8);
        v32 = *(_QWORD *)(v29 + 16);
        *(_QWORD *)&v58 = v32;
        while ( v31 != v32 )
        {
          v33 = 0;
          for ( j = 0; j < 0xCCCCCCCCCCCCCCCDuLL * ((v27 - v28) >> 3); ++j )
          {
            v56 = v28 + 40 * j;
            if ( !*(_DWORD *)(v56 + 32) )
            {
              if ( (unsigned __int8)std::regex_match<std::char_traits<wchar_t>,std::allocator<wchar_t>,wchar_t,std::regex_traits<wchar_t>>(
                                      v28 + 40 * j,
                                      v31) )
              {
                if ( *(_BYTE *)(v29 + 4) )
                {
                  ++v33;
                  v7 = j;
                }
                else
                {
                  Diagnostics::ColumnClassifier::ApplyPattern(v56, v29, v31);
                }
              }
              v27 = v54;
              v30 = 0xCCCCCCCCCCCCCCCDuLL;
            }
          }
          if ( v33 == 1 )
          {
            Diagnostics::ColumnClassifier::ApplyPattern(v28 + 40 * v7, v29, v31);
            v27 = v54;
            v7 = 0;
            v30 = 0xCCCCCCCCCCCCCCCDuLL;
            break;
          }
          v31 += 40;
          v32 = v58;
          v7 = 0;
        }
        v29 = __PAIR128__(v57, (__int64)v29 + 64);
      }
      v35 = 0xCCCCCCCCCCCCCCCDuLL * ((v27 - v28) >> 3);
      v36 = 0;
      if ( v35 )
      {
        v37 = (_DWORD *)(v28 + 32);
        while ( *v37 != 1 )
        {
          ++v7;
          v37 += 10;
          if ( v7 >= v35 )
            goto LABEL_43;
        }
        v38 = 1;
        v53 = 1;
      }
      else
      {
LABEL_43:
        v38 = 0;
        v53 = 0;
        LODWORD(v7) = v61[0];
      }
      v39 = v61[0];
      while ( (unsigned int)sqlite3_step(v67, v30) == 100 )
      {
        v40 = 0;
        if ( v38 )
        {
          v41 = (const wchar_t *)sqlite3_column_text16(v67, (unsigned int)v7);
          if ( v41 )
          {
            v39 = 10000 * o_wcstoll_0(v41, 0, 10);
            v40 = 1;
          }
        }
        memset(v72, 0, sizeof(v72));
        if ( v40 )
          v56 = v39;
        else
          v56 = *(_QWORD *)(v59 + 80);
        v57 = *(_OWORD *)&Diagnostics::OTelLogRecord::DefaultVersion;
        v58 = *v60;
        Diagnostics::OTelLogRecord::OTelLogRecord(v72, &v56, &v58, &v57);
        while ( (int)v36 < v55 )
        {
          v42 = sqlite3_column_text16(v67, v36);
          if ( v42 )
          {
            if ( 0xCCCCCCCCCCCCCCCDuLL * ((v54 - v28) >> 3) <= (int)v36 )
              std::vector<std::pair<std::wstring,enum Diagnostics::ColumnClassifier::ColumnType>>::_Xrange();
            v43 = (__int64 *)(v28 + 40LL * (int)v36);
            if ( *((_DWORD *)v43 + 8) != 1 )
            {
              if ( *((_DWORD *)v43 + 8) == 2 )
              {
                v46 = (__int64 *)(v28 + 40LL * (int)v36);
                if ( (unsigned __int64)v43[3] > 7 )
                  v46 = (__int64 *)*v43;
                *(_QWORD *)&v58 = v43 + 2;
                v47 = v43[2];
                v48 = -1;
                do
                  ++v48;
                while ( *(_WORD *)(v42 + 2 * v48) );
                *(_QWORD *)&v57 = v72;
                v64[0] = v46;
                v64[1] = v47;
                v65[0] = v42;
                v65[1] = v48;
                if ( !___TryExpandJsonAttributes_V_lambda_1___1__AddAttributesFromJson_OTelLogRecord_Diagnostics__QEAA_NV__basic_string_view__WU__char_traits__W_std___std__0_Z__OTelLogRecord_Diagnostics__CA_NV__basic_string_view__WU__char_traits__W_std___std____QEAV_lambda_1___1__AddAttributesFromJson_01_QEAA_N00_Z_0H_Z(
                        (__int64)v65,
                        (__int64)&v57,
                        (__int64)v64) )
                {
                  v49 = -1;
                  do
                    ++v49;
                  while ( *(_WORD *)(v42 + 2 * v49) );
                  if ( (unsigned __int64)v43[3] > 7 )
                    v43 = (__int64 *)*v43;
                  v66[0] = v42;
                  v66[1] = v49;
                  v61[0] = v43;
                  v61[1] = *(_QWORD *)v58;
                  Diagnostics::OTelLogRecord::AddAttribute(v72, v61, v66);
                }
              }
              else
              {
                v44 = -1;
                do
                  ++v44;
                while ( *(_WORD *)(v42 + 2 * v44) );
                v45 = (__int64 *)(v28 + 40LL * (int)v36);
                if ( (unsigned __int64)v43[3] > 7 )
                  v45 = (__int64 *)*v43;
                v62[0] = v42;
                v62[1] = v44;
                v63[0] = v45;
                v63[1] = v43[2];
                Diagnostics::OTelLogRecord::AddAttribute(v72, v63, v62);
              }
            }
          }
          ++v36;
        }
        Diagnostics::OTelFile::AppendLogRecord(
          (Diagnostics::OTelFile *)v73,
          (const struct Diagnostics::OTelLogRecord *)v72);
        Diagnostics::OTelLogRecord::~OTelLogRecord((Diagnostics::OTelLogRecord *)v72);
        v38 = v53;
        v36 = 0;
      }
      std::vector<std::pair<std::wstring,enum Diagnostics::ColumnClassifier::ColumnType>>::~vector<std::pair<std::wstring,enum Diagnostics::ColumnClassifier::ColumnType>>(WideCharStr);
      std::vector<std::pair<std::wstring,enum Diagnostics::ColumnClassifier::ColumnType>>::~vector<std::pair<std::wstring,enum Diagnostics::ColumnClassifier::ColumnType>>(&v70);
      sqlite3_finalize(v67);
      v50 = v73[174];
      Diagnostics::OTelFile::~OTelFile((Diagnostics::OTelFile *)v73);
      result = v50;
    }
    catch ( ... )
    {
      sqlite3_finalize(v67);
      throw;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180033e10  push    rbx
0x180033e12  push    rsi
0x180033e13  push    rdi
0x180033e14  push    r12
0x180033e16  push    r13
0x180033e18  push    r14
0x180033e1a  push    r15
0x180033e1c  sub     rsp, 560h
0x180033e23  mov     rax, cs:__security_cookie
0x180033e2a  xor     rax, rsp
0x180033e2d  mov     [rsp+598h+var_48], rax
0x180033e35  mov     rdi, r9
0x180033e38  mov     rbx, r8
0x180033e3b  mov     [rsp+598h+var_510], rdx
0x180033e43  mov     r14, rcx
0x180033e46  mov     [rsp+598h+var_518], rcx
0x180033e4e  xor     r13d, r13d
0x180033e51  mov     esi, r13d
0x180033e54  mov     dword ptr [rsp+598h+var_550], r13d
0x180033e59  mov     rcx, [rsp+598h]
0x180033e61  lea     rax, aDatabaseIsNotO; "Database is not open"
0x180033e68  mov     [rsp+598h+var_570], rax
0x180033e6d  mov     rax, [r14+48h]
0x180033e71  mov     qword ptr [rsp+598h+var_578], rax
0x180033e76  mov     r9d, 80004003h
0x180033e7c  lea     r15, aCW1SSrcCalliop_4; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x180033e83  mov     r8, r15
0x180033e86  lea     edx, [r13+2Ch]
0x180033e8a  call    ??$Throw_HrIfNullMsg@PEAUsqlite3@@$0A@@in1diag3@details@wil@@YAPEAUsqlite3@@PEAXIPEBDJPEAU3@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<sqlite3 *,0>(void *,uint,char const *,long,sqlite3 *,char const *,...)
0x180033e8f  cmp     [rdi+8], r13
0x180033e93  setz    al
0x180033e96  mov     rcx, [rsp+598h]; this
0x180033e9e  lea     rdx, aSqlFilterCanno; "SQL filter cannot be empty"
0x180033ea5  mov     [rsp+598h+var_570], rdx; bool
0x180033eaa  mov     byte ptr [rsp+598h+var_578], al; int
0x180033eae  mov     r9d, 80070057h; char *
0x180033eb4  mov     r8, r15; unsigned int
0x180033eb7  lea     edx, [r13+2Dh]; void *
0x180033ebb  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180033ec0  xor     edx, edx; Val
0x180033ec2  mov     r8d, 2C0h; Size
0x180033ec8  lea     rcx, [rsp+598h+var_308]; void *
0x180033ed0  call    memset
0x180033ed5  mov     rdx, rbx; struct std::filesystem::path *
0x180033ed8  lea     rcx, [rsp+598h+var_308]; this
0x180033ee0  call    ??0OTelFile@Diagnostics@@QEAA@AEBVpath@filesystem@std@@@Z; Diagnostics::OTelFile::OTelFile(std::filesystem::path const &)
0x180033ee5  nop
0x180033ee6  mov     [rsp+598h+var_498], r13
0x180033eee  mov     rbx, [rdi]
0x180033ef1  mov     qword ptr [rsp+598h+var_578], r13
0x180033ef6  lea     r9, [rsp+598h+var_498]
0x180033efe  or      r12, 0FFFFFFFFFFFFFFFFh
0x180033f02  mov     r8d, r12d
0x180033f05  mov     rdx, rbx
0x180033f08  mov     rcx, [r14+48h]
0x180033f0c  call    cs:__imp_sqlite3_prepare16_v2
0x180033f12  mov     edi, eax
0x180033f14  test    eax, eax
0x180033f16  jz      loc_180033FE1
0x180033f1c  mov     rcx, [r14+48h]
0x180033f20  call    cs:__imp_sqlite3_errmsg
0x180033f26  xorps   xmm0, xmm0
0x180033f29  movups  xmmword ptr [rsp+598h+WideCharStr], xmm0
0x180033f31  xorps   xmm1, xmm1
0x180033f34  movdqu  [rsp+598h+var_480], xmm1
0x180033f3d  inc     r12
0x180033f40  cmp     [rax+r12], r13b
0x180033f44  jnz     short loc_180033F3D
0x180033f46  mov     r8, r12
0x180033f49  mov     rdx, rax
0x180033f4c  lea     rcx, [rsp+598h+WideCharStr]
0x180033f54  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180033f59  lea     rax, [rsp+598h+WideCharStr]
0x180033f61  cmp     qword ptr [rsp+598h+var_480+8], 0Fh
0x180033f6a  cmova   rax, qword ptr [rsp+598h+WideCharStr]
0x180033f73  mov     rcx, [rsp+598h]; this
0x180033f7b  mov     [rsp+598h+var_568], rbx
0x180033f80  mov     [rsp+598h+var_570], rax; char *
0x180033f85  lea     rax, aFailedWithHsWh; "Failed with '%hs' while preparing SQL s"...
0x180033f8c  mov     qword ptr [rsp+598h+var_578], rax; unsigned int
0x180033f91  mov     r9d, edi; char *
0x180033f94  mov     r8, r15; unsigned int
0x180033f97  mov     edx, 3Ah ; ':'; void *
0x180033f9c  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180033fa1  lea     rcx, [rsp+598h+WideCharStr]
0x180033fa9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180033fae  nop
0x180033faf  lea     rcx, [rsp+598h+var_308]; this
0x180033fb7  call    ??1OTelFile@Diagnostics@@UEAA@XZ; Diagnostics::OTelFile::~OTelFile(void)
0x180033fbc  xor     eax, eax
0x180033fbe  mov     rcx, [rsp+598h+var_48]
0x180033fc6  xor     rcx, rsp; StackCookie
0x180033fc9  call    __security_check_cookie
0x180033fce  add     rsp, 560h
0x180033fd5  pop     r15
0x180033fd7  pop     r14
0x180033fd9  pop     r13
0x180033fdb  pop     r12
0x180033fdd  pop     rdi
0x180033fde  pop     rsi
0x180033fdf  pop     rbx
0x180033fe0  retn
0x180033fe1  mov     rcx, [rsp+598h+var_498]
0x180033fe9  call    cs:__imp_sqlite3_column_count
0x180033fef  mov     [rsp+598h+var_548], eax
0x180033ff3  xorps   xmm1, xmm1
0x180033ff6  movdqu  [rsp+598h+var_470], xmm1
0x180033fff  mov     [rsp+598h+var_460], r13
0x180034007  movsxd  rcx, eax
0x18003400a  mov     [rsp+598h+var_540], rcx
0x18003400f  test    eax, eax
0x180034011  jz      short loc_18003403C
0x180034013  mov     rax, 666666666666666h
0x18003401d  cmp     rcx, rax
0x180034020  ja      loc_18003460B
0x180034026  lea     rdx, [rsp+598h+var_540]
0x18003402b  lea     rcx, [rsp+598h+var_470]
0x180034033  call    ??$_Reallocate@$0A@@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4ColumnType@ColumnClassifier@Diagnostics@@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4ColumnType@ColumnClassifier@Diagnostics@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::pair<std::wstring,Diagnostics::ColumnClassifier::ColumnType>>::_Reallocate<0>(unsigned __int64 &)
0x180034038  mov     eax, [rsp+598h+var_548]
0x18003403c  mov     ebx, r13d
0x18003403f  mov     edi, 7
0x180034044  cmp     ebx, eax
0x180034046  jge     loc_180034198
0x18003404c  mov     dword ptr [rsp+598h+var_550], r13d
0x180034051  mov     edx, ebx
0x180034053  mov     rcx, [rsp+598h+var_498]
0x18003405b  call    cs:__imp_sqlite3_column_name
0x180034061  test    rax, rax
0x180034064  jz      short loc_180034096
0x180034066  mov     rcx, r12
0x180034069  inc     rcx
0x18003406c  cmp     [rax+rcx], r13b
0x180034070  jnz     short loc_180034069
0x180034072  mov     qword ptr [rsp+598h+var_538], rax
0x180034077  mov     qword ptr [rsp+598h+var_538+8], rcx
0x18003407c  mov     r8d, r12d
0x18003407f  lea     rdx, [rsp+598h+var_538]
0x180034084  lea     rcx, [rsp+598h+WideCharStr]; lpWideCharStr
0x18003408c  call    ?Utf8ToWideString@Convert@System@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@4@H@Z; System::Convert::Utf8ToWideString(std::string_view,int)
0x180034091  or      esi, 1
0x180034094  jmp     short loc_180034106
0x180034096  mov     edx, ebx
0x180034098  lea     rcx, [rsp+598h+var_508]
0x1800340a0  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x1800340a5  nop
0x1800340a6  mov     r9d, 6
0x1800340ac  lea     r8, aColumn; "Column"
0x1800340b3  mov     rcx, rax; Src
0x1800340b6  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_KQEB_W0@Z; std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800340bb  xorps   xmm0, xmm0
0x1800340be  movups  xmmword ptr [rsp+598h+WideCharStr], xmm0
0x1800340c6  xorps   xmm1, xmm1
0x1800340c9  movdqu  [rsp+598h+var_480], xmm1
0x1800340d2  movups  xmm0, xmmword ptr [rax]
0x1800340d5  movups  xmmword ptr [rsp+598h+WideCharStr], xmm0
0x1800340dd  movups  xmm1, xmmword ptr [rax+10h]
0x1800340e1  movups  [rsp+598h+var_480], xmm1
0x1800340e9  mov     [rax], r13w
0x1800340ed  mov     [rax+10h], r13
0x1800340f1  mov     [rax+18h], rdi
0x1800340f5  or      esi, 3
0x1800340f8  lea     rcx, [rsp+598h+var_508]
0x180034100  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034105  nop
0x180034106  mov     rdx, qword ptr [rsp+598h+var_470+8]
0x18003410e  cmp     rdx, [rsp+598h+var_460]
0x180034116  jz      short loc_180034165
0x180034118  xorps   xmm0, xmm0
0x18003411b  movups  xmmword ptr [rdx], xmm0
0x18003411e  mov     [rdx+10h], r13
0x180034122  mov     [rdx+18h], r13
0x180034126  movups  xmm0, xmmword ptr [rsp+598h+WideCharStr]
0x18003412e  movups  xmmword ptr [rdx], xmm0
0x180034131  movups  xmm1, [rsp+598h+var_480]
0x180034139  movups  xmmword ptr [rdx+10h], xmm1
0x18003413d  mov     [rsp+598h+WideCharStr], r13w
0x180034146  mov     qword ptr [rsp+598h+var_480], r13
0x18003414e  mov     qword ptr [rsp+598h+var_480+8], rdi
0x180034156  mov     [rdx+20h], r13d
0x18003415a  add     qword ptr [rsp+598h+var_470+8], 28h ; '('
0x180034163  jmp     short loc_180034180
0x180034165  lea     r9, [rsp+598h+var_550]
0x18003416a  lea     r8, [rsp+598h+WideCharStr]
0x180034172  lea     rcx, [rsp+598h+var_470]
0x18003417a  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4ColumnType@ColumnClassifier@Diagnostics@@@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4ColumnType@ColumnClassifier@Diagnostics@@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4ColumnType@ColumnClassifier@Diagnostics@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4ColumnType@ColumnClassifier@Diagnostics@@@1@QEAU21@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAW4ColumnType@ColumnClassifier@Diagnostics@@@Z; std::vector<std::pair<std::wstring,Diagnostics::ColumnClassifier::ColumnType>>::_Emplace_reallocate<std::wstring,Diagnostics::ColumnClassifier::ColumnType>(std::pair<std::wstring,Diagnostics::ColumnClassifier::ColumnType> * const,std::wstring &&,Diagnostics::ColumnClassifier::ColumnType &&)
0x18003417f  nop
0x180034180  lea     rcx, [rsp+598h+WideCharStr]
0x180034188  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003418d  inc     ebx
0x18003418f  mov     eax, [rsp+598h+var_548]
0x180034193  jmp     loc_180034044
0x180034198  xorps   xmm0, xmm0
0x18003419b  movups  xmmword ptr [rsp+598h+WideCharStr], xmm0
0x1800341a3  mov     rax, [rsp+598h+var_460]
0x1800341ab  mov     [rsp+598h+var_460], r13
0x1800341b3  mov     rcx, qword ptr [rsp+598h+var_470+8]
0x1800341bb  mov     [rsp+598h+var_550], rcx
0x1800341c0  mov     qword ptr [rsp+598h+var_470+8], r13
0x1800341c8  mov     r15, qword ptr [rsp+598h+var_470]
0x1800341d0  mov     qword ptr [rsp+598h+var_470], r13
0x1800341d8  mov     qword ptr [rsp+598h+WideCharStr], r15
0x1800341e0  mov     qword ptr [rsp+598h+WideCharStr+8], rcx
0x1800341e8  mov     qword ptr [rsp+598h+var_480], rax
0x1800341f0  mov     rbx, qword ptr cs:?_defaultPatterns@ColumnClassifier@Diagnostics@@0V?$vector@UColumnPattern@ColumnClassifier@Diagnostics@@V?$allocator@UColumnPattern@ColumnClassifier@Diagnostics@@@std@@@std@@B; std::vector<Diagnostics::ColumnClassifier::ColumnPattern> const Diagnostics::ColumnClassifier::_defaultPatterns
0x1800341f7  mov     rax, qword ptr cs:?_defaultPatterns@ColumnClassifier@Diagnostics@@0V?$vector@UColumnPattern@ColumnClassifier@Diagnostics@@V?$allocator@UColumnPattern@ColumnClassifier@Diagnostics@@@std@@@std@@B+8; std::vector<Diagnostics::ColumnClassifier::ColumnPattern> const Diagnostics::ColumnClassifier::_defaultPatterns
0x1800341fe  mov     qword ptr [rsp+598h+var_538], rax
0x180034203  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18003420d  cmp     rbx, rax
0x180034210  jz      loc_1800342E9
0x180034216  mov     rdi, [rbx+8]
0x18003421a  mov     rax, [rbx+10h]
0x18003421e  mov     qword ptr [rsp+598h+var_528], rax
0x180034223  cmp     rdi, rax
0x180034226  jz      loc_1800342CA
0x18003422c  mov     r14, r13
0x18003422f  xor     esi, esi
0x180034231  mov     rax, rcx
0x180034234  sub     rax, r15
0x180034237  sar     rax, 3
0x18003423b  imul    rax, rdx
0x18003423f  cmp     rsi, rax
0x180034242  jnb     short loc_180034298
0x180034244  lea     rax, [rsi+rsi*4]
0x180034248  lea     rax, [r15+rax*8]
0x18003424c  mov     [rsp+598h+var_540], rax
0x180034251  cmp     dword ptr [rax+20h], 0
0x180034255  jnz     short loc_180034293
0x180034257  mov     rdx, rdi
0x18003425a  mov     rcx, rax
0x18003425d  call    ??$regex_match@U?$char_traits@_W@std@@V?$allocator@_W@2@_WV?$regex_traits@_W@2@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV?$basic_regex@_WV?$regex_traits@_W@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_match<std::char_traits<wchar_t>,std::allocator<wchar_t>,wchar_t,std::regex_traits<wchar_t>>(std::wstring const &,std::basic_regex<wchar_t,std::regex_traits<wchar_t>> const &,std::regex_constants::match_flag_type)
0x180034262  test    al, al
0x180034264  jz      short loc_180034284
0x180034266  cmp     byte ptr [rbx+4], 0
0x18003426a  jz      short loc_180034274
0x18003426c  inc     r14
0x18003426f  mov     r13, rsi
0x180034272  jmp     short loc_180034284
0x180034274  mov     r8, rdi
0x180034277  mov     rdx, rbx
0x18003427a  mov     rcx, [rsp+598h+var_540]
0x18003427f  call    ?ApplyPattern@ColumnClassifier@Diagnostics@@CAXAEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4ColumnType@ColumnClassifier@Diagnostics@@@std@@AEBUColumnPattern@12@AEBV?$basic_regex@_WV?$regex_traits@_W@std@@@4@@Z; Diagnostics::ColumnClassifier::ApplyPattern(std::pair<std::wstring,Diagnostics::ColumnClassifier::ColumnType> &,Diagnostics::ColumnClassifier::ColumnPattern const &,std::basic_regex<wchar_t,std::regex_traits<wchar_t>> const &)
0x180034284  mov     rcx, [rsp+598h+var_550]
0x180034289  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x180034293  inc     rsi
0x180034296  jmp     short loc_180034231
0x180034298  cmp     r14, 1
0x18003429c  jnz     short loc_1800342D8
0x18003429e  lea     rax, ds:0[r13*4]
0x1800342a6  add     rax, r13
0x1800342a9  lea     rcx, [r15+rax*8]
0x1800342ad  mov     r8, rdi
0x1800342b0  mov     rdx, rbx
0x1800342b3  call    ?ApplyPattern@ColumnClassifier@Diagnostics@@CAXAEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4ColumnType@ColumnClassifier@Diagnostics@@@std@@AEBUColumnPattern@12@AEBV?$basic_regex@_WV?$regex_traits@_W@std@@@4@@Z; Diagnostics::ColumnClassifier::ApplyPattern(std::pair<std::wstring,Diagnostics::ColumnClassifier::ColumnType> &,Diagnostics::ColumnClassifier::ColumnPattern const &,std::basic_regex<wchar_t,std::regex_traits<wchar_t>> const &)
0x1800342b8  mov     rcx, [rsp+598h+var_550]
0x1800342bd  xor     r13d, r13d
0x1800342c0  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x1800342ca  add     rbx, 40h ; '@'
0x1800342ce  mov     rax, qword ptr [rsp+598h+var_538]
0x1800342d3  jmp     loc_18003420D
0x1800342d8  add     rdi, 28h ; '('
0x1800342dc  mov     rax, qword ptr [rsp+598h+var_528]
0x1800342e1  xor     r13d, r13d
0x1800342e4  jmp     loc_180034223
0x1800342e9  mov     rax, rcx
0x1800342ec  sub     rax, r15
0x1800342ef  sar     rax, 3
0x1800342f3  imul    rax, rdx
0x1800342f7  xor     r14d, r14d
0x1800342fa  test    rax, rax
0x1800342fd  jz      short loc_180034318
0x1800342ff  lea     rcx, [r15+20h]
0x180034303  cmp     dword ptr [rcx], 1
0x180034306  jz      loc_18003439E
0x18003430c  inc     r13
0x18003430f  add     rcx, 28h ; '('
0x180034313  cmp     r13, rax
0x180034316  jb      short loc_180034303
0x180034318  mov     sil, r14b
0x18003431b  mov     [rsp+598h+var_558], r14b
0x180034320  mov     r13, [rsp+598h+var_508]
0x180034328  mov     rbx, [rsp+598h+var_508]
0x180034330  mov     rcx, [rsp+598h+var_498]
0x180034338  call    cs:__imp_sqlite3_step
0x18003433e  cmp     eax, 64h ; 'd'
0x180034341  jnz     loc_1800345C6
0x180034347  mov     dil, r14b
0x18003434a  test    sil, sil
0x18003434d  jz      short loc_18003437D
0x18003434f  mov     edx, r13d
0x180034352  mov     rcx, [rsp+598h+var_498]
0x18003435a  call    cs:__imp_sqlite3_column_text16
0x180034360  test    rax, rax
0x180034363  jz      short loc_18003437D
0x180034365  xor     edx, edx; EndPtr
0x180034367  lea     r8d, [rdx+0Ah]; Radix
0x18003436b  mov     rcx, rax; String
0x18003436e  call    _o_wcstoll_0
0x180034373  imul    rbx, rax, 2710h
0x18003437a  mov     dil, 1
0x18003437d  xor     edx, edx; Val
  ... truncated ...
```
