# Microsoft::Diagnostics::SqlConnection::SqlConnection(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::SqlConnection::Options const &)

- ea: `0x1800e98c0`
- end: `0x1800e9bf8`
- name: `??0SqlConnection@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBUOptions@012@@Z`
- size: `824`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x18021db28`
- `0x1802e26d8`

## callees

- `0x180015030`
- `0x180015228`
- `0x180015330`
- `0x180015564`
- `0x18001d160`
- `0x18001d200`
- `0x18001e638`
- `0x18001ee94`
- `0x180020fbc`
- `0x180035698`
- `0x180038870`
- `0x180070aa4`
- `0x1800bab28`
- `0x1800babec`
- `0x1800bac14`
- `0x1800bac3c`
- `0x1800bae3c`
- `0x1800bc2e0`
- `0x1800e98c0`
- `0x1800e9c00`
- `0x180114174`
- `0x18012de40`
- `0x180222930`

## import_xrefs

- `winsqlite3!sqlite3_open` at `0x1800e9a38`
- `winsqlite3!sqlite3_open` at `0x1800e9a38`
- `winsqlite3!sqlite3_open16` at `0x1800e99be`
- `winsqlite3!sqlite3_open16` at `0x1800e99be`
- `winsqlite3!sqlite3_extended_result_codes` at `0x1800e9ba3`
- `winsqlite3!sqlite3_extended_result_codes` at `0x1800e9ba3`
- `winsqlite3!sqlite3_open_v2` at `0x1800e9a56`
- `winsqlite3!sqlite3_open_v2` at `0x1800e9a56`

## string_xrefs

- `0x1800e998b`: `onecore\base\telemetry\utc\service\include\Sqlite.h`
- `0x1800e9b65`: `onecore\base\telemetry\utc\service\include\Sqlite.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
Microsoft::Diagnostics::SqlConnection *__fastcall Microsoft::Diagnostics::SqlConnection::SqlConnection(
        Microsoft::Diagnostics::SqlConnection *this,
        _QWORD *a2,
        _BYTE *a3)
{
  char *v6; // r14
  __int64 v7; // r15
  void *appended; // rax
  __int128 v9; // xmm6
  _QWORD *v10; // rcx
  unsigned int v11; // eax
  int v12; // eax
  __int128 v13; // xmm6
  char **v14; // rcx
  unsigned int v15; // eax
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  const char *v20; // rax
  __int128 v21; // xmm6
  unsigned int v22; // eax
  int v24; // [rsp+28h] [rbp-E0h]
  char *v25[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v26[3]; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v27[16]; // [rsp+68h] [rbp-A0h] BYREF
  Microsoft::Diagnostics::SqlConnection *v28; // [rsp+78h] [rbp-90h]
  _BYTE v29[32]; // [rsp+80h] [rbp-88h] BYREF
  char *v30[3]; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int64 v31; // [rsp+B8h] [rbp-50h]
  _QWORD Src[6]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v33[48]; // [rsp+F0h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v28 = this;
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_BYTE *)this + 32) = 0;
  v6 = (char *)this + 40;
  std::wstring::wstring((__int64)this + 40, a2);
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)Src);
  v7 = a2[1];
  if ( v7 )
  {
    *(_OWORD *)v25 = *(_OWORD *)a2;
    appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(Src);
    Microsoft::Diagnostics::WideStringStream::operator<<(appended);
  }
  if ( a3[1] )
  {
    *(_OWORD *)v25 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, &v26[1]);
    Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(v30, v25);
    v13 = *(_OWORD *)std::wstring::operator std::wstring_view(v6, v27);
    v14 = v30;
    if ( a3[3] )
    {
      if ( v31 > 0xF )
        v14 = (char **)v30[0];
      v15 = sqlite3_open_v2(v14, this, 1, 0);
    }
    else
    {
      if ( v31 > 0xF )
        v14 = (char **)v30[0];
      v15 = sqlite3_open(v14, this);
    }
    *(_OWORD *)v25 = v13;
    v16 = Microsoft::Diagnostics::VerifySqlCall(v15, v25);
    Microsoft::Diagnostics::SqlConnection::ValidateOpenSqlConnection(this, v16);
    std::string::_Tidy_deallocate(v30);
  }
  else
  {
    if ( a3[3] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\Sqlite.h",
        (const char *)0x80004001LL,
        v24);
    v9 = *(_OWORD *)std::wstring::operator std::wstring_view(v6, &v26[1]);
    v10 = Src;
    if ( Src[3] > 7u )
      v10 = (_QWORD *)Src[0];
    v11 = sqlite3_open16(v10, this);
    *(_OWORD *)v25 = v9;
    v12 = Microsoft::Diagnostics::VerifySqlCall(v11, v25);
    Microsoft::Diagnostics::SqlConnection::ValidateOpenSqlConnection(this, v12);
  }
  if ( v7 && !*a3 )
  {
    *(_OWORD *)&v26[1] = *(_OWORD *)std::wstring::operator std::wstring_view(v6, v27);
    v25[0] = "PRAGMA quick_check;";
    v25[1] = (char *)19;
    Microsoft::Diagnostics::SqliteStatement::SqliteStatement((__int64)v33, this, (__int64)v25);
    v17 = Microsoft::Diagnostics::SqliteStatement::Bind<>(v33, v25);
    v18 = Microsoft::Diagnostics::SqliteBoundStatement::Step(v17, v29);
    v19 = Microsoft::Diagnostics::SqliteQueryResult::Next<std::string_view>(v18, &v26[1]);
    std::string::string(v30, v19);
    std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v29);
    std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v25);
    if ( (unsigned __int8)std::operator!=<char>(v30, "ok") )
    {
      v20 = (const char *)v30;
      if ( v31 > 0xF )
        v20 = v30[0];
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\Sqlite.h",
        (const char *)0x87C52301LL,
        (int)"%hs",
        v20);
    }
    std::string::_Tidy_deallocate(v30);
    Microsoft::Diagnostics::SqliteStatement::~SqliteStatement((Microsoft::Diagnostics::SqliteStatement *)v33);
  }
  v21 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v27);
  v22 = sqlite3_extended_result_codes(*(_QWORD *)this, 1);
  *(_OWORD *)&v26[1] = v21;
  Microsoft::Diagnostics::VerifySqlCall(v22, &v26[1]);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  return this;
}

```

## disassembly

```asm
0x1800e98c0  mov     rax, rsp
0x1800e98c3  mov     [rax+18h], rbx
0x1800e98c7  push    rbp
0x1800e98c8  push    rsi
0x1800e98c9  push    rdi
0x1800e98ca  push    r14
0x1800e98cc  push    r15
0x1800e98ce  lea     rbp, [rax-58h]
0x1800e98d2  sub     rsp, 130h
0x1800e98d9  movaps  xmmword ptr [rax-38h], xmm6
0x1800e98dd  mov     rax, cs:__security_cookie
0x1800e98e4  xor     rax, rsp
0x1800e98e7  mov     [rbp+50h+var_38], rax
0x1800e98eb  mov     rdi, r8
0x1800e98ee  mov     rsi, rdx
0x1800e98f1  mov     rbx, rcx
0x1800e98f4  mov     [rsp+150h+var_E0], rcx
0x1800e98f9  mov     qword ptr [rcx], 0
0x1800e9900  mov     dword ptr [rcx+8], 0
0x1800e9907  mov     qword ptr [rcx+10h], 0
0x1800e990f  mov     qword ptr [rcx+18h], 0
0x1800e9917  mov     byte ptr [rcx+20h], 0
0x1800e991b  lea     r14, [rcx+28h]
0x1800e991f  mov     rcx, r14
0x1800e9922  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1800e9927  nop
0x1800e9928  lea     rcx, [rbp+50h+Src]; this
0x1800e992c  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x1800e9931  nop
0x1800e9932  mov     r15, [rsi+8]
0x1800e9936  test    r15, r15
0x1800e9939  jz      short loc_1800E9970
0x1800e993b  movaps  xmm0, xmmword ptr [rsi]
0x1800e993e  movdqa  xmmword ptr [rsp+150h+var_128+8], xmm0
0x1800e9944  lea     rdx, [rsp+150h+var_128+8]
0x1800e9949  lea     rcx, [rbp+50h+Src]; Src
0x1800e994d  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1800e9952  lea     rcx, aEventstoreDb; "\\EventStore.db"
0x1800e9959  lea     rdx, Src
0x1800e9960  cmp     byte ptr [rdi+2], 0
0x1800e9964  cmovz   rdx, rcx
0x1800e9968  mov     rcx, rax; Src
0x1800e996b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1800e9970  mov     esi, 1
0x1800e9975  cmp     byte ptr [rdi+1], 0
0x1800e9979  jnz     short loc_1800E99EB
0x1800e997b  mov     rcx, [rbp+58h]; this
0x1800e997f  cmp     byte ptr [rdi+3], 0
0x1800e9983  jz      short loc_1800E999D
0x1800e9985  mov     r9d, 80004001h; char *
0x1800e998b  lea     r8, aOnecoreBaseTel_132; "onecore\\base\\telemetry\\utc\\service"...
0x1800e9992  mov     edx, 16Eh; void *
0x1800e9997  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800e999d  lea     rdx, [rsp+150h+var_108+8]
0x1800e99a2  mov     rcx, r14
0x1800e99a5  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800e99aa  movups  xmm6, xmmword ptr [rax]
0x1800e99ad  lea     rcx, [rbp+50h+Src]
0x1800e99b1  cmp     [rbp+50h+var_80], 7
0x1800e99b6  cmova   rcx, [rbp+50h+Src]
0x1800e99bb  mov     rdx, rbx
0x1800e99be  call    cs:__imp_sqlite3_open16
0x1800e99c5  nop     dword ptr [rax+rax+00h]
0x1800e99ca  movdqu  xmmword ptr [rsp+150h+var_128+8], xmm6
0x1800e99d0  lea     rdx, [rsp+150h+var_128+8]
0x1800e99d5  mov     ecx, eax
0x1800e99d7  call    ?VerifySqlCall@Diagnostics@Microsoft@@YAJHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::VerifySqlCall(int,std::wstring_view)
0x1800e99dc  mov     edx, eax; int
0x1800e99de  mov     rcx, rbx; this
0x1800e99e1  call    ?ValidateOpenSqlConnection@SqlConnection@Diagnostics@Microsoft@@QEAAXJ@Z; Microsoft::Diagnostics::SqlConnection::ValidateOpenSqlConnection(long)
0x1800e99e6  jmp     loc_1800E9A88
0x1800e99eb  lea     rdx, [rsp+150h+var_108+8]
0x1800e99f0  lea     rcx, [rbp+50h+Src]
0x1800e99f4  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800e99f9  movups  xmm0, xmmword ptr [rax]
0x1800e99fc  movdqu  xmmword ptr [rsp+150h+var_128+8], xmm0
0x1800e9a02  lea     rdx, [rsp+150h+var_128+8]
0x1800e9a07  lea     rcx, [rbp+50h+var_B8]
0x1800e9a0b  call    ?WideStringToMultiByteString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(std::wstring_view,ulong)
0x1800e9a10  nop
0x1800e9a11  lea     rdx, [rsp+150h+var_F0]
0x1800e9a16  mov     rcx, r14
0x1800e9a19  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800e9a1e  movups  xmm6, xmmword ptr [rax]
0x1800e9a21  lea     rcx, [rbp+50h+var_B8]
0x1800e9a25  mov     rdx, rbx
0x1800e9a28  cmp     byte ptr [rdi+3], 0
0x1800e9a2c  jnz     short loc_1800E9A46
0x1800e9a2e  cmp     [rbp+50h+var_A0], 0Fh
0x1800e9a33  cmova   rcx, [rbp+50h+var_B8]
0x1800e9a38  call    cs:__imp_sqlite3_open
0x1800e9a3f  nop     dword ptr [rax+rax+00h]
0x1800e9a44  jmp     short loc_1800E9A62
0x1800e9a46  cmp     [rbp+50h+var_A0], 0Fh
0x1800e9a4b  cmova   rcx, [rbp+50h+var_B8]
0x1800e9a50  xor     r9d, r9d
0x1800e9a53  mov     r8d, esi
0x1800e9a56  call    cs:__imp_sqlite3_open_v2
0x1800e9a5d  nop     dword ptr [rax+rax+00h]
0x1800e9a62  movdqu  xmmword ptr [rsp+150h+var_128+8], xmm6
0x1800e9a68  lea     rdx, [rsp+150h+var_128+8]
0x1800e9a6d  mov     ecx, eax
0x1800e9a6f  call    ?VerifySqlCall@Diagnostics@Microsoft@@YAJHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::VerifySqlCall(int,std::wstring_view)
0x1800e9a74  mov     edx, eax; int
0x1800e9a76  mov     rcx, rbx; this
0x1800e9a79  call    ?ValidateOpenSqlConnection@SqlConnection@Diagnostics@Microsoft@@QEAAXJ@Z; Microsoft::Diagnostics::SqlConnection::ValidateOpenSqlConnection(long)
0x1800e9a7e  nop
0x1800e9a7f  lea     rcx, [rbp+50h+var_B8]; void *
0x1800e9a83  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e9a88  test    r15, r15
0x1800e9a8b  jz      loc_1800E9B8A
0x1800e9a91  cmp     byte ptr [rdi], 0
0x1800e9a94  jnz     loc_1800E9B8A
0x1800e9a9a  lea     rdx, [rsp+150h+var_F0]
0x1800e9a9f  mov     rcx, r14
0x1800e9aa2  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800e9aa7  movups  xmm0, xmmword ptr [rax]
0x1800e9aaa  movdqu  xmmword ptr [rsp+150h+var_108+8], xmm0
0x1800e9ab0  lea     rax, aPragmaQuickChe; "PRAGMA quick_check;"
0x1800e9ab7  mov     [rsp+150h+var_128+8], rax
0x1800e9abc  mov     [rsp+150h+var_118], 13h
0x1800e9ac5  lea     r9, [rsp+150h+var_108+8]
0x1800e9aca  lea     r8, [rsp+150h+var_128+8]
0x1800e9acf  mov     rdx, rbx
0x1800e9ad2  lea     rcx, [rbp+50h+var_68]
0x1800e9ad6  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x1800e9adb  nop
0x1800e9adc  lea     rdx, [rsp+150h+var_128+8]
0x1800e9ae1  lea     rcx, [rbp+50h+var_68]
0x1800e9ae5  call    ??$Bind@$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA?AVSqliteBoundStatement@12@XZ; Microsoft::Diagnostics::SqliteStatement::Bind<>(void)
0x1800e9aea  nop
0x1800e9aeb  lea     rdx, [rsp+150h+var_D8]
0x1800e9af0  mov     rcx, rax
0x1800e9af3  call    ?Step@SqliteBoundStatement@Diagnostics@Microsoft@@QEAA?AV?$optional@VSqliteQueryResult@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::SqliteBoundStatement::Step(void)
0x1800e9af8  nop
0x1800e9af9  lea     rdx, [rsp+150h+var_108+8]
0x1800e9afe  mov     rcx, rax
0x1800e9b01  call    ??$Next@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@SqliteQueryResult@Diagnostics@Microsoft@@QEAA?AV?$basic_string_view@DU?$char_traits@D@std@@@std@@XZ; Microsoft::Diagnostics::SqliteQueryResult::Next<std::string_view>(void)
0x1800e9b06  mov     rdx, rax
0x1800e9b09  lea     rcx, [rbp+50h+var_B8]
0x1800e9b0d  call    ??$?0V?$basic_string_view@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV?$basic_string_view@DU?$char_traits@D@std@@@1@AEBV?$allocator@D@1@@Z; std::string::string(std::string_view const &,std::allocator<char> const &)
0x1800e9b12  nop
0x1800e9b13  lea     rcx, [rsp+150h+var_D8]
0x1800e9b18  call    ??1?$_Optional_destruct_base@VSqliteQueryResult@Diagnostics@Microsoft@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(void)
0x1800e9b1d  nop
0x1800e9b1e  lea     rcx, [rsp+150h+var_128+8]; void *
0x1800e9b23  call    ??1?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(void)
0x1800e9b28  lea     rdx, aOk_0; "ok"
0x1800e9b2f  lea     rcx, [rbp+50h+var_B8]
0x1800e9b33  call    ??$?9DU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD@Z; std::operator!=<char>(std::string const &,char const * const)
0x1800e9b38  test    al, al
0x1800e9b3a  jz      short loc_1800E9B77
0x1800e9b3c  lea     rax, [rbp+50h+var_B8]
0x1800e9b40  cmp     [rbp+50h+var_A0], 0Fh
0x1800e9b45  cmova   rax, [rbp+50h+var_B8]
0x1800e9b4a  mov     rcx, [rbp+58h]; this
0x1800e9b4e  mov     [rsp+150h+var_128], rax; char *
0x1800e9b53  lea     rax, aHs; "%hs"
0x1800e9b5a  mov     qword ptr [rsp+150h+var_130], rax; int
0x1800e9b5f  mov     r9d, 87C52301h; char *
0x1800e9b65  lea     r8, aOnecoreBaseTel_132; "onecore\\base\\telemetry\\utc\\service"...
0x1800e9b6c  mov     edx, 185h; void *
0x1800e9b71  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800e9b77  lea     rcx, [rbp+50h+var_B8]; void *
0x1800e9b7b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e9b80  nop
0x1800e9b81  lea     rcx, [rbp+50h+var_68]; this
0x1800e9b85  call    ??1SqliteStatement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::SqliteStatement::~SqliteStatement(void)
0x1800e9b8a  lea     rdx, [rsp+150h+var_F0]
0x1800e9b8f  lea     rcx, unk_18043B600
0x1800e9b96  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800e9b9b  movups  xmm6, xmmword ptr [rax]
0x1800e9b9e  mov     edx, esi
0x1800e9ba0  mov     rcx, [rbx]
0x1800e9ba3  call    cs:__imp_sqlite3_extended_result_codes
0x1800e9baa  nop     dword ptr [rax+rax+00h]
0x1800e9baf  movdqu  xmmword ptr [rsp+150h+var_108+8], xmm6
0x1800e9bb5  lea     rdx, [rsp+150h+var_108+8]
0x1800e9bba  mov     ecx, eax
0x1800e9bbc  call    ?VerifySqlCall@Diagnostics@Microsoft@@YAJHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::VerifySqlCall(int,std::wstring_view)
0x1800e9bc1  nop
0x1800e9bc2  lea     rcx, [rbp+50h+Src]; this
0x1800e9bc6  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800e9bcb  nop
0x1800e9bcc  mov     rax, rbx
0x1800e9bcf  mov     rcx, [rbp+50h+var_38]
0x1800e9bd3  xor     rcx, rsp; StackCookie
0x1800e9bd6  call    __security_check_cookie
0x1800e9bdb  lea     r11, [rsp+150h+var_20]
0x1800e9be3  mov     rbx, [r11+40h]
0x1800e9be7  movaps  xmm6, xmmword ptr [r11-10h]
0x1800e9bec  mov     rsp, r11
0x1800e9bef  pop     r15
0x1800e9bf1  pop     r14
0x1800e9bf3  pop     rdi
0x1800e9bf4  pop     rsi
0x1800e9bf5  pop     rbp
0x1800e9bf6  retn
```
