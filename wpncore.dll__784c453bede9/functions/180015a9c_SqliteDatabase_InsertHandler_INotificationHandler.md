# SqliteDatabase::InsertHandler(INotificationHandler *)

- ea: `0x180015a9c`
- end: `0x180016243`
- name: `?InsertHandler@SqliteDatabase@@AEAAXPEAUINotificationHandler@@@Z`
- size: `1959`
- prototype: `void __fastcall(SqliteDatabase *__hidden this, struct INotificationHandler *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000aa38`

## callees

- `0x180006038`
- `0x18000c4a8`
- `0x18000e5f4`
- `0x180011b10`
- `0x180014340`
- `0x18001592c`
- `0x180015a9c`
- `0x18001624c`
- `0x180016900`
- `0x18002b744`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001618a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800161a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800161da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800161f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016210`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001618a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800161a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800161da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800161f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016210`
- `winsqlite3!sqlite3_bind_null` at `0x180015d21`
- `winsqlite3!sqlite3_bind_null` at `0x180015d86`
- `winsqlite3!sqlite3_bind_null` at `0x180015d21`
- `winsqlite3!sqlite3_bind_null` at `0x180015d86`
- `winsqlite3!sqlite3_bind_blob` at `0x18001611c`
- `winsqlite3!sqlite3_bind_blob` at `0x18001611c`
- `winsqlite3!sqlite3_bind_text16` at `0x180015beb`
- `winsqlite3!sqlite3_bind_text16` at `0x180015c51`
- `winsqlite3!sqlite3_bind_text16` at `0x180015cbd`
- `winsqlite3!sqlite3_bind_text16` at `0x180015df2`
- `winsqlite3!sqlite3_bind_text16` at `0x180015e5e`
- `winsqlite3!sqlite3_bind_text16` at `0x180015beb`
- `winsqlite3!sqlite3_bind_text16` at `0x180015c51`
- `winsqlite3!sqlite3_bind_text16` at `0x180015cbd`
- `winsqlite3!sqlite3_bind_text16` at `0x180015df2`
- `winsqlite3!sqlite3_bind_text16` at `0x180015e5e`

## string_xrefs

- `0x180015b2e`: `INSERT INTO [NotificationHandler] ([PrimaryId], [WNSId], [HandlerType],[WNFEventName], [SystemDataPropertySet], [CreatedTime], [ModifiedTime], [ParentId], [ContainerSid]) VALUES (?,?,?,?,?,datetime('now'),datetime('now'),?,?)`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall SqliteDatabase::InsertHandler(SqliteDatabase *this, struct INotificationHandler *a2)
{
  __int64 v4; // rax
  std::_Ref_count_base *v5; // rcx
  volatile signed __int32 *v6; // rax
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rax
  std::_Ref_count_base *v9; // rcx
  std::_Ref_count_base *v10; // rdx
  std::_Ref_count_base *v11; // rcx
  std::_Ref_count_base *v12; // rbx
  std::_Ref_count_base *v13; // rbx
  int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  int v17; // eax
  signed int v18; // eax
  int v19; // eax
  signed int v20; // eax
  int v21; // eax
  signed int v22; // eax
  int v23; // eax
  signed int v24; // eax
  int v25; // eax
  signed int v26; // eax
  unsigned int v27; // eax
  signed int v28; // eax
  __int64 v29; // rcx
  int v30; // [rsp+20h] [rbp-99h]
  std::_Ref_count_base *v31[2]; // [rsp+30h] [rbp-89h] BYREF
  std::_Ref_count_base *v32[2]; // [rsp+40h] [rbp-79h]
  std::_Ref_count_base *v33[2]; // [rsp+50h] [rbp-69h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-59h] BYREF
  __int64 v35; // [rsp+68h] [rbp-51h]
  __int64 v36; // [rsp+70h] [rbp-49h]
  LPVOID v37; // [rsp+78h] [rbp-41h] BYREF
  __int64 v38; // [rsp+80h] [rbp-39h]
  __int64 v39; // [rsp+88h] [rbp-31h]
  LPVOID v40; // [rsp+90h] [rbp-29h] BYREF
  __int64 v41; // [rsp+98h] [rbp-21h]
  __int64 v42; // [rsp+A0h] [rbp-19h]
  LPVOID v43; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-9h]
  __int64 v45; // [rsp+B8h] [rbp-1h]
  LPVOID v46; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v47; // [rsp+C8h] [rbp+Fh]
  __int64 v48; // [rsp+D0h] [rbp+17h]
  __int64 v49; // [rsp+D8h] [rbp+1Fh] BYREF
  std::_Ref_count_base *v50; // [rsp+E0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  __int64 v52; // [rsp+120h] [rbp+67h] BYREF
  __int64 v53; // [rsp+128h] [rbp+6Fh] BYREF
  std::_Ref_count_base **v54; // [rsp+130h] [rbp+77h]

  *(_OWORD *)v33 = 0;
  v4 = *((_QWORD *)this + 7);
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 6);
  v33[0] = v5;
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 7);
  v33[1] = (std::_Ref_count_base *)v6;
  v54 = v33;
  *(_OWORD *)v31 = 0;
  *(_OWORD *)v32 = 0;
  if ( v6 )
  {
    _InterlockedIncrement(v6 + 2);
    v6 = (volatile signed __int32 *)v33[1];
    v5 = v33[0];
  }
  v31[0] = v5;
  v7 = (volatile signed __int32 *)v31[1];
  v31[1] = (std::_Ref_count_base *)v6;
  if ( v7 && !_InterlockedDecrement(v7 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
    std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v7);
  }
  v8 = Database::PrepareFromCache(
         v31[0],
         &v49,
         "INSERT INTO [NotificationHandler] ([PrimaryId], [WNSId], [HandlerType],[WNFEventName], [SystemDataPropertySet],"
         " [CreatedTime], [ModifiedTime], [ParentId], [ContainerSid]) VALUES (?,?,?,?,?,datetime('now'),datetime('now'),?,?)");
  v9 = *(std::_Ref_count_base **)v8;
  v10 = *(std::_Ref_count_base **)(v8 + 8);
  *(_QWORD *)v8 = 0;
  *(_QWORD *)(v8 + 8) = 0;
  v32[0] = v9;
  v11 = v32[1];
  v32[1] = v10;
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  v12 = v50;
  if ( v50 && _InterlockedExchangeAdd((volatile signed __int32 *)v50 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))v12)(v12);
    std::_Ref_count_base::_Decwref(v12);
  }
  v13 = v33[1];
  if ( v33[1] && _InterlockedExchangeAdd((volatile signed __int32 *)v33[1] + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))v13)(v13);
    std::_Ref_count_base::_Decwref(v13);
  }
  v46 = 0;
  v47 = -1;
  v48 = -1;
  v14 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 24LL))(a2, &v46);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xADC,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v14,
      v30);
  if ( !*(_QWORD *)v32[0] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)0x8007139FLL,
      v30);
  v15 = sqlite3_bind_text16(*(_QWORD *)v32[0], 1, v46, 0xFFFFFFFFLL);
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x87AF0000;
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v15,
      -1);
  v43 = 0;
  v44 = -1;
  v45 = -1;
  (*(void (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 56LL))(a2, &v43);
  if ( !*(_QWORD *)v32[0] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)0x8007139FLL,
      -1);
  v16 = sqlite3_bind_text16(*(_QWORD *)v32[0], 2, v43, 0xFFFFFFFFLL);
  if ( v16 > 0 )
    v16 = (unsigned __int16)v16 | 0x87AF0000;
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v16,
      -1);
  v40 = 0;
  v41 = -1;
  v42 = -1;
  v17 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 48LL))(a2, &v40);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAE4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v17,
      -1);
  if ( !*(_QWORD *)v32[0] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)0x8007139FLL,
      -1);
  v18 = sqlite3_bind_text16(*(_QWORD *)v32[0], 3, v40, 0xFFFFFFFFLL);
  if ( v18 > 0 )
    v18 = (unsigned __int16)v18 | 0x87AF0000;
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v18,
      -1);
  v53 = 0;
  v19 = (*(__int64 (__fastcall **)(struct INotificationHandler *, __int64 *))(*(_QWORD *)a2 + 64LL))(a2, &v53);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAE8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v19,
      -1);
  if ( v53 )
  {
    Statement::Bind(v32[0], 4, v53);
  }
  else
  {
    if ( !*(_QWORD *)v32[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)0x8007139FLL,
        -1);
    v20 = sqlite3_bind_null(*(_QWORD *)v32[0], (unsigned int)(v53 + 4));
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x87AF0000;
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)(unsigned int)v20,
        -1);
  }
  v52 = 0;
  v21 = (*(__int64 (__fastcall **)(struct INotificationHandler *, __int64 *))(*(_QWORD *)a2 + 80LL))(a2, &v52);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAEC,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v21,
      -1);
  if ( v52 )
  {
    WpnDatabaseHelpers::VectorFromStream(&v49, v52);
    if ( !*(_QWORD *)v32[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)0x8007139FLL,
        -1);
    v28 = sqlite3_bind_blob(*(_QWORD *)v32[0], 5, v49, (unsigned int)((_DWORD)v50 - v49));
    if ( v28 > 0 )
      v28 = (unsigned __int16)v28 | 0x87AF0000;
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)(unsigned int)v28,
        -1);
    std::vector<unsigned char>::_Tidy(&v49);
  }
  else
  {
    if ( !*(_QWORD *)v32[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)0x8007139FLL,
        -1);
    v22 = sqlite3_bind_null(*(_QWORD *)v32[0], 5);
    if ( v22 > 0 )
      v22 = (unsigned __int16)v22 | 0x87AF0000;
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)(unsigned int)v22,
        -1);
  }
  v37 = 0;
  v38 = -1;
  v39 = -1;
  v23 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &v37);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAF0,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v23,
      -1);
  if ( !*(_QWORD *)v32[0] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)0x8007139FLL,
      -1);
  v24 = sqlite3_bind_text16(*(_QWORD *)v32[0], 6, v37, 0xFFFFFFFFLL);
  if ( v24 > 0 )
    v24 = (unsigned __int16)v24 | 0x87AF0000;
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v24,
      -1);
  pv = 0;
  v35 = -1;
  v36 = -1;
  v25 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 104LL))(a2, &pv);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAF4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v25,
      -1);
  if ( !*(_QWORD *)v32[0] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)0x8007139FLL,
      -1);
  v26 = sqlite3_bind_text16(*(_QWORD *)v32[0], 7, pv, 0xFFFFFFFFLL);
  if ( v26 > 0 )
    v26 = (unsigned __int16)v26 | 0x87AF0000;
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v26,
      -1);
  if ( !*(_QWORD *)v32[0] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)0x8007139FLL,
      -1);
  v27 = Statement::dal_step(*(struct sqlite3_stmt **)v32[0]);
  if ( v27 != -2018574235 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)v27,
      -1);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v35 = 0;
  v36 = 0;
  if ( v37 )
  {
    CoTaskMemFree(v37);
    v37 = 0;
  }
  v38 = 0;
  v39 = 0;
  v29 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  if ( v40 )
  {
    CoTaskMemFree(v40);
    v40 = 0;
  }
  v41 = 0;
  v42 = 0;
  if ( v43 )
  {
    CoTaskMemFree(v43);
    v43 = 0;
  }
  v44 = 0;
  v45 = 0;
  if ( v46 )
  {
    CoTaskMemFree(v46);
    v46 = 0;
  }
  v47 = 0;
  v48 = 0;
  AutoAddToCache::~AutoAddToCache((AutoAddToCache *)v31);
}

```

## disassembly

```asm
0x180015a9c  mov     [rsp-8+arg_18], rbx
0x180015aa1  push    rbp
0x180015aa2  push    rsi
0x180015aa3  push    rdi
0x180015aa4  push    r14
0x180015aa6  push    r15
0x180015aa8  lea     rbp, [rsp-37h]
0x180015aad  sub     rsp, 0F0h
0x180015ab4  mov     rdi, rdx
0x180015ab7  mov     rdx, rcx
0x180015aba  xorps   xmm0, xmm0
0x180015abd  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x180015ac2  mov     rax, [rcx+38h]
0x180015ac6  xor     esi, esi
0x180015ac8  test    rax, rax
0x180015acb  jz      short loc_180015AD1
0x180015acd  lock inc dword ptr [rax+8]
0x180015ad1  mov     rcx, [rcx+30h]
0x180015ad5  mov     [rbp+57h+var_C0], rcx
0x180015ad9  mov     rax, [rdx+38h]
0x180015add  mov     [rbp+57h+var_C0+8], rax
0x180015ae1  lea     rdx, [rbp+57h+var_C0]
0x180015ae5  mov     [rbp+57h+arg_10], rdx
0x180015ae9  movdqu  xmmword ptr [rsp+110h+var_E0], xmm0
0x180015aef  movdqu  xmmword ptr [rbp+57h+var_D0], xmm0
0x180015af4  test    rax, rax
0x180015af7  jz      short loc_180015B05
0x180015af9  lock inc dword ptr [rax+8]
0x180015afd  mov     rax, [rbp+57h+var_C0+8]
0x180015b01  mov     rcx, [rbp+57h+var_C0]
0x180015b05  mov     [rsp+110h+var_E0], rcx
0x180015b0a  mov     rbx, [rsp+110h+var_E0+8]
0x180015b0f  mov     [rsp+110h+var_E0+8], rax
0x180015b14  or      r14, 0FFFFFFFFFFFFFFFFh
0x180015b18  test    rbx, rbx
0x180015b1b  jz      short loc_180015B2E
0x180015b1d  mov     eax, r14d
0x180015b20  lock xadd [rbx+8], eax
0x180015b25  add     eax, r14d
0x180015b28  jz      loc_1800160A0
0x180015b2e  lea     r8, aInsertIntoNoti_2; "INSERT INTO [NotificationHandler] ([Pri"...
0x180015b35  lea     rdx, [rbp+57h+var_38]
0x180015b39  mov     rcx, [rsp+110h+var_E0]
0x180015b3e  call    ?PrepareFromCache@Database@@QEAA?AV?$shared_ptr@VStatement@@@std@@PEBD@Z; Database::PrepareFromCache(char const *)
0x180015b43  mov     rcx, [rax]
0x180015b46  mov     rdx, [rax+8]
0x180015b4a  mov     [rax], rsi
0x180015b4d  mov     [rax+8], rsi
0x180015b51  mov     [rbp+57h+var_D0], rcx
0x180015b55  mov     rcx, [rbp+57h+var_D0+8]; this
0x180015b59  mov     [rbp+57h+var_D0+8], rdx
0x180015b5d  test    rcx, rcx
0x180015b60  jz      short loc_180015B67
0x180015b62  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015b67  mov     rbx, [rbp+57h+var_30]
0x180015b6b  test    rbx, rbx
0x180015b6e  jz      short loc_180015B81
0x180015b70  mov     eax, r14d
0x180015b73  lock xadd [rbx+8], eax
0x180015b78  add     eax, r14d
0x180015b7b  jz      loc_1800160BB
0x180015b81  mov     rbx, [rbp+57h+var_C0+8]
0x180015b85  test    rbx, rbx
0x180015b88  jz      short loc_180015B9B
0x180015b8a  mov     eax, r14d
0x180015b8d  lock xadd [rbx+8], eax
0x180015b92  add     eax, r14d
0x180015b95  jz      loc_1800160D6
0x180015b9b  mov     [rbp+57h+var_50], rsi
0x180015b9f  mov     [rbp+57h+var_48], r14
0x180015ba3  mov     [rbp+57h+var_40], r14
0x180015ba7  mov     rax, [rdi]
0x180015baa  lea     rdx, [rbp+57h+var_50]
0x180015bae  mov     rcx, rdi
0x180015bb1  mov     rax, [rax+18h]
0x180015bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bba  mov     rcx, [rbp+5Fh]; this
0x180015bbe  test    eax, eax
0x180015bc0  js      loc_180015F59
0x180015bc6  mov     rax, [rbp+57h+var_D0]
0x180015bca  mov     rcx, [rax]
0x180015bcd  mov     rax, [rbp+5Fh]
0x180015bd1  test    rcx, rcx
0x180015bd4  jz      loc_180015EB7
0x180015bda  mov     qword ptr [rsp+110h+var_F0], r14; int
0x180015bdf  mov     r9d, r14d
0x180015be2  mov     r8, [rbp+57h+var_50]
0x180015be6  mov     edx, 1
0x180015beb  call    cs:__imp_sqlite3_bind_text16
0x180015bf1  mov     r15d, 87AF0000h
0x180015bf7  test    eax, eax
0x180015bf9  jle     short loc_180015C01
0x180015bfb  movzx   eax, ax
0x180015bfe  or      eax, r15d
0x180015c01  mov     rcx, [rbp+5Fh]; this
0x180015c05  test    eax, eax
0x180015c07  js      loc_180015F6E
0x180015c0d  mov     [rbp+57h+var_68], rsi
0x180015c11  mov     [rbp+57h+var_60], r14
0x180015c15  mov     [rbp+57h+var_58], r14
0x180015c19  mov     rax, [rdi]
0x180015c1c  lea     rdx, [rbp+57h+var_68]
0x180015c20  mov     rcx, rdi
0x180015c23  mov     rax, [rax+38h]
0x180015c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c2c  mov     rax, [rbp+57h+var_D0]
0x180015c30  mov     rcx, [rax]
0x180015c33  mov     rax, [rbp+5Fh]
0x180015c37  test    rcx, rcx
0x180015c3a  jz      loc_180015ED2
0x180015c40  mov     qword ptr [rsp+110h+var_F0], r14; int
0x180015c45  mov     r9d, r14d
0x180015c48  mov     r8, [rbp+57h+var_68]
0x180015c4c  mov     edx, 2
0x180015c51  call    cs:__imp_sqlite3_bind_text16
0x180015c57  test    eax, eax
0x180015c59  jle     short loc_180015C61
0x180015c5b  movzx   eax, ax
0x180015c5e  or      eax, r15d
0x180015c61  mov     rcx, [rbp+5Fh]; this
0x180015c65  test    eax, eax
0x180015c67  js      loc_180015F83
0x180015c6d  mov     [rbp+57h+var_80], rsi
0x180015c71  mov     [rbp+57h+var_78], r14
0x180015c75  mov     [rbp+57h+var_70], r14
0x180015c79  mov     rax, [rdi]
0x180015c7c  lea     rdx, [rbp+57h+var_80]
0x180015c80  mov     rcx, rdi
0x180015c83  mov     rax, [rax+30h]
0x180015c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c8c  mov     rcx, [rbp+5Fh]; this
0x180015c90  test    eax, eax
0x180015c92  js      loc_180015F98
0x180015c98  mov     rax, [rbp+57h+var_D0]
0x180015c9c  mov     rcx, [rax]
0x180015c9f  mov     rax, [rbp+5Fh]
0x180015ca3  test    rcx, rcx
0x180015ca6  jz      loc_180015EED
0x180015cac  mov     qword ptr [rsp+110h+var_F0], r14; int
0x180015cb1  mov     r9d, r14d
0x180015cb4  mov     r8, [rbp+57h+var_80]
0x180015cb8  mov     edx, 3
0x180015cbd  call    cs:__imp_sqlite3_bind_text16
0x180015cc3  test    eax, eax
0x180015cc5  jle     short loc_180015CCD
0x180015cc7  movzx   eax, ax
0x180015cca  or      eax, r15d
0x180015ccd  mov     rcx, [rbp+5Fh]; this
0x180015cd1  test    eax, eax
0x180015cd3  js      loc_180015FAD
0x180015cd9  mov     [rbp+57h+arg_8], rsi
0x180015cdd  mov     rax, [rdi]
0x180015ce0  lea     rdx, [rbp+57h+arg_8]
0x180015ce4  mov     rcx, rdi
0x180015ce7  mov     rax, [rax+40h]
0x180015ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cf0  mov     rcx, [rbp+5Fh]; this
0x180015cf4  test    eax, eax
0x180015cf6  js      loc_180015FC2
0x180015cfc  mov     r8, [rbp+57h+arg_8]; __int64
0x180015d00  mov     rcx, [rbp+57h+var_D0]; this
0x180015d04  test    r8, r8
0x180015d07  jnz     loc_180016172
0x180015d0d  mov     rcx, [rcx]
0x180015d10  mov     rax, [rbp+5Fh]
0x180015d14  test    rcx, rcx
0x180015d17  jz      loc_180016040
0x180015d1d  lea     edx, [r8+4]
0x180015d21  call    cs:__imp_sqlite3_bind_null
0x180015d27  test    eax, eax
0x180015d29  jle     short loc_180015D31
0x180015d2b  movzx   eax, ax
0x180015d2e  or      eax, r15d
0x180015d31  mov     rcx, [rbp+5Fh]; this
0x180015d35  test    eax, eax
0x180015d37  js      loc_18001605B
0x180015d3d  mov     [rbp+57h+arg_0], rsi
0x180015d41  mov     rax, [rdi]
0x180015d44  lea     rdx, [rbp+57h+arg_0]
0x180015d48  mov     rcx, rdi
0x180015d4b  mov     rax, [rax+50h]
0x180015d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d54  mov     rcx, [rbp+5Fh]; this
0x180015d58  test    eax, eax
0x180015d5a  js      loc_180015FD7
0x180015d60  mov     rdx, [rbp+57h+arg_0]
0x180015d64  mov     rbx, [rbp+57h+var_D0]
0x180015d68  test    rdx, rdx
0x180015d6b  jnz     loc_1800160F1
0x180015d71  mov     rcx, [rbx]
0x180015d74  mov     rax, [rbp+5Fh]
0x180015d78  test    rcx, rcx
0x180015d7b  jz      loc_180016070
0x180015d81  mov     edx, 5
0x180015d86  call    cs:__imp_sqlite3_bind_null
0x180015d8c  test    eax, eax
0x180015d8e  jle     short loc_180015D96
0x180015d90  movzx   eax, ax
0x180015d93  or      eax, r15d
0x180015d96  mov     rcx, [rbp+5Fh]; this
0x180015d9a  test    eax, eax
0x180015d9c  js      loc_18001608B
0x180015da2  mov     [rbp+57h+var_98], rsi
0x180015da6  mov     [rbp+57h+var_90], r14
0x180015daa  mov     [rbp+57h+var_88], r14
0x180015dae  mov     rax, [rdi]
0x180015db1  lea     rdx, [rbp+57h+var_98]
0x180015db5  mov     rcx, rdi
0x180015db8  mov     rax, [rax+28h]
0x180015dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dc1  mov     rcx, [rbp+5Fh]; this
0x180015dc5  test    eax, eax
0x180015dc7  js      loc_180015FEC
0x180015dcd  mov     rax, [rbp+57h+var_D0]
0x180015dd1  mov     rcx, [rax]
0x180015dd4  mov     rax, [rbp+5Fh]
0x180015dd8  test    rcx, rcx
0x180015ddb  jz      loc_180015F08
0x180015de1  mov     qword ptr [rsp+110h+var_F0], r14; int
0x180015de6  mov     r9d, r14d
0x180015de9  mov     r8, [rbp+57h+var_98]
0x180015ded  mov     edx, 6
0x180015df2  call    cs:__imp_sqlite3_bind_text16
0x180015df8  test    eax, eax
0x180015dfa  jle     short loc_180015E02
0x180015dfc  movzx   eax, ax
0x180015dff  or      eax, r15d
0x180015e02  mov     rcx, [rbp+5Fh]; this
0x180015e06  test    eax, eax
0x180015e08  js      loc_180016001
0x180015e0e  mov     [rbp+57h+pv], rsi
0x180015e12  mov     [rbp+57h+var_A8], r14
0x180015e16  mov     [rbp+57h+var_A0], r14
0x180015e1a  mov     rax, [rdi]
0x180015e1d  lea     rdx, [rbp+57h+pv]
0x180015e21  mov     rcx, rdi
0x180015e24  mov     rax, [rax+68h]
0x180015e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e2d  mov     rcx, [rbp+5Fh]; this
0x180015e31  test    eax, eax
0x180015e33  js      loc_180016016
0x180015e39  mov     rax, [rbp+57h+var_D0]
0x180015e3d  mov     rcx, [rax]
0x180015e40  mov     rax, [rbp+5Fh]
0x180015e44  test    rcx, rcx
0x180015e47  jz      loc_180015F23
0x180015e4d  mov     qword ptr [rsp+110h+var_F0], r14; int
0x180015e52  mov     r9d, r14d
0x180015e55  mov     r8, [rbp+57h+pv]
0x180015e59  mov     edx, 7
0x180015e5e  call    cs:__imp_sqlite3_bind_text16
0x180015e64  test    eax, eax
0x180015e66  jle     short loc_180015E6E
0x180015e68  movzx   eax, ax
0x180015e6b  or      eax, r15d
0x180015e6e  mov     rcx, [rbp+5Fh]; this
0x180015e72  test    eax, eax
0x180015e74  js      loc_18001602B
0x180015e7a  mov     rax, [rbp+57h+var_D0]
0x180015e7e  mov     rcx, [rax]; struct sqlite3_stmt *
0x180015e81  mov     rax, [rbp+5Fh]
0x180015e85  test    rcx, rcx
0x180015e88  jz      loc_180015F3E
0x180015e8e  call    ?dal_step@Statement@@SAJPEAUsqlite3_stmt@@@Z; Statement::dal_step(sqlite3_stmt *)
0x180015e93  cmp     eax, 87AF0065h
0x180015e98  jz      loc_180016181
0x180015e9e  mov     rcx, [rbp+5Fh]; this
0x180015ea2  mov     r9d, eax; char *
0x180015ea5  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180015eac  mov     edx, 53h ; 'S'; void *
0x180015eb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015eb7  mov     r9d, 8007139Fh; char *
0x180015ebd  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180015ec4  mov     edx, 100h; void *
0x180015ec9  mov     rcx, rax; this
0x180015ecc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015ed2  mov     r9d, 8007139Fh; char *
0x180015ed8  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180015edf  mov     edx, 100h; void *
0x180015ee4  mov     rcx, rax; this
0x180015ee7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015eed  mov     r9d, 8007139Fh; char *
0x180015ef3  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180015efa  mov     edx, 100h; void *
0x180015eff  mov     rcx, rax; this
0x180015f02  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015f08  mov     r9d, 8007139Fh; char *
0x180015f0e  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180015f15  mov     edx, 100h; void *
0x180015f1a  mov     rcx, rax; this
0x180015f1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015f23  mov     r9d, 8007139Fh; char *
0x180015f29  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180015f30  mov     edx, 100h; void *
0x180015f35  mov     rcx, rax; this
0x180015f38  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015f3e  mov     r9d, 8007139Fh; char *
0x180015f44  lea     r8, aOnecoreuapBase_149; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180015f4b  mov     edx, 4Ch ; 'L'; void *
0x180015f50  mov     rcx, rax; this
  ... truncated ...
```
