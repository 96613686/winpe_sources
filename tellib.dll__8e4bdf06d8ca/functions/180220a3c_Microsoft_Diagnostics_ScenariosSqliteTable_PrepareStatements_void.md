# Microsoft::Diagnostics::ScenariosSqliteTable::PrepareStatements(void)

- ea: `0x180220a3c`
- end: `0x180221c56`
- name: `?PrepareStatements@ScenariosSqliteTable@Diagnostics@Microsoft@@AEAAXXZ`
- size: `4634`
- prototype: `void __fastcall(Microsoft::Diagnostics::ScenariosSqliteTable *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18022062c`

## callees

- `0x18001cf30`
- `0x180020fbc`
- `0x18003fd8c`
- `0x1800bab28`
- `0x1800bb24c`
- `0x1800bc1b8`
- `0x18012de64`
- `0x18021daf4`

## string_xrefs

- `0x180220c06`: `DELETE FROM Scenarios WHERE Hash = ?1`
- `0x180220df5`: `UPDATE Triggers SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x180220dbb`: `UPDATE Triggers SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x180220e56`: `DELETE FROM Triggers WHERE Hash = ?1`
- `0x180221003`: `DELETE FROM Filters WHERE Hash = ?1`
- `0x180220fc9`: `UPDATE Filters SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x180220f8f`: `UPDATE Filters SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x180221199`: `DELETE FROM Actions WHERE Hash = ?1`
- `0x18022115f`: `UPDATE Actions SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x180221125`: `UPDATE Actions SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x1802212fc`: `UPDATE TraceProfiles SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x180221450`: `INSERT INTO Configurations (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)`
- `0x1802213e6`: `SELECT COUNT(1) FROM Configurations WHERE Hash = ?1`
- `0x18022139c`: `DELETE FROM TraceProfiles WHERE Hash = ?1`
- `0x180221336`: `UPDATE TraceProfiles SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x18022154c`: `UPDATE Configurations SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x180221512`: `UPDATE Configurations SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x1802214d8`: `SELECT RefCount FROM Configurations WHERE Hash = ?1`
- `0x18022149e`: `SELECT Type, BinaryRepresentation FROM Configurations WHERE Hash = ?1`
- `0x1802215b1`: `DELETE FROM Configurations WHERE Hash = ?1`
- `0x1802217cb`: `DELETE FROM TelemetryEvents WHERE Hash = ?1`
- `0x180221769`: `UPDATE TelemetryEvents SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x18022172e`: `UPDATE TelemetryEvents SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x1802219e0`: `DELETE FROM ScenarioStateModels WHERE Hash = ?1`
- `0x18022197f`: `UPDATE ScenarioStateModels SET RefCount = RefCount - 1 WHERE Hash = ?1`
- `0x180221945`: `UPDATE ScenarioStateModels SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x180221b4f`: `UPDATE Transitions SET RefCount = RefCount + 1 WHERE Hash = ?1`
- `0x180221bea`: `DELETE FROM Transitions WHERE Hash = ?1`
- `0x180221b89`: `UPDATE Transitions SET RefCount = RefCount - 1 WHERE Hash = ?1`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
void __fastcall Microsoft::Diagnostics::ScenariosSqliteTable::PrepareStatements(
        Microsoft::Diagnostics::ScenariosSqliteTable *this)
{
  _QWORD *v2; // rbx
  __int64 v3; // r10
  _QWORD *v4; // rbx
  __int64 v5; // r10
  __int64 v6; // rax
  __int64 v7; // rax
  _QWORD *v8; // rbx
  __int64 v9; // r10
  __int64 v10; // rax
  _QWORD *v11; // rbx
  __int64 v12; // r10
  _QWORD *v13; // rbx
  __int64 v14; // r10
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // rbx
  __int64 v19; // r10
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  _QWORD *v35; // rbx
  __int64 v36; // r10
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  _QWORD *v41; // rbx
  __int64 v42; // r10
  __int64 v43; // rax
  _QWORD *v44; // rbx
  __int64 v45; // r10
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  _QWORD *v50; // rbx
  __int64 v51; // r10
  __int64 v52; // rax
  _QWORD *v53; // rbx
  __int64 v54; // r10
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  _QWORD *v59; // rbx
  __int64 v60; // r10
  __int64 v61; // rax
  _QWORD *v62; // rbx
  __int64 v63; // r10
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  _QWORD *v68; // rbx
  __int64 v69; // r10
  __int64 v70; // rax
  __int64 v71; // rax
  _QWORD *v72; // rbx
  __int64 v73; // r10
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  _QWORD *v77; // rbx
  __int64 v78; // r10
  _BYTE v79[16]; // [rsp+20h] [rbp-69h] BYREF
  const char *v80; // [rsp+30h] [rbp-59h] BYREF
  __int64 v81; // [rsp+38h] [rbp-51h]
  __int128 v82; // [rsp+40h] [rbp-49h]
  _BYTE v83[8]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v84[8]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v85[8]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v86[8]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v87[8]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v88[8]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v89[8]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v90[8]; // [rsp+88h] [rbp-1h] BYREF
  _BYTE v91[80]; // [rsp+90h] [rbp+7h] BYREF
  void *v92; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v93; // [rsp+F8h] [rbp+6Fh] BYREF
  char v94; // [rsp+100h] [rbp+77h] BYREF
  char v95; // [rsp+108h] [rbp+7Fh] BYREF

  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v91, (char *)this + 200);
  v2 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "SELECT COUNT(1) FROM Scenarios WHERE Hash = ?1";
  v81 = 46;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v3, v2, (__int64)&v80);
  LOWORD(v92) = 0;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v4 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "INSERT INTO Scenarios (Hash,NamespaceHash,BinaryRepresentation)VALUES (?1,?2,?3)";
  v81 = 80;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v5, v4, (__int64)&v80);
  LOWORD(v92) = 1;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v6 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
         &v93,
         *((_QWORD *)this + 5),
         "SELECT NamespaceHash FROM Scenarios WHERE Hash = ?1");
  LOWORD(v92) = 2;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v6);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v7 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
         &v93,
         *((_QWORD *)this + 5),
         "SELECT NamespaceHash, BinaryRepresentation FROM Scenarios WHERE Hash = ?1");
  LOWORD(v92) = 3;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v7);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v8 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "DELETE FROM Scenarios WHERE Hash = ?1";
  v81 = 37;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v9, v8, (__int64)&v80);
  LOWORD(v92) = 4;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v10 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM Triggers WHERE Hash = ?1");
  LOWORD(v92) = 5;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v10);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v11 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "INSERT INTO Triggers (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)";
  v81 = 82;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v12, v11, (__int64)&v80);
  LOWORD(v92) = 6;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v13 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "SELECT Type, BinaryRepresentation FROM Triggers WHERE Hash = ?1";
  v81 = 63;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v14, v13, (__int64)&v80);
  LOWORD(v92) = 7;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v15 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM Triggers WHERE Hash = ?1");
  LOWORD(v92) = 8;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v15);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v16 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Triggers SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 9;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v16);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v17 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Triggers SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 10;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v17);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v18 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "DELETE FROM Triggers WHERE Hash = ?1";
  v81 = 36;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v19, v18, (__int64)&v80);
  LOWORD(v92) = 11;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v20 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM Filters WHERE Hash = ?1");
  LOWORD(v92) = 12;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v20);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v21 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "INSERT INTO Filters (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)");
  LOWORD(v92) = 13;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v21);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v22 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT Type, BinaryRepresentation FROM Filters WHERE Hash = ?1");
  LOWORD(v92) = 14;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v22);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v23 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM Filters WHERE Hash = ?1");
  LOWORD(v92) = 15;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v23);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v24 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Filters SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 16;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v24);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v25 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Filters SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 17;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v25);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v26 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "DELETE FROM Filters WHERE Hash = ?1");
  LOWORD(v92) = 18;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v26);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v27 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM Actions WHERE Hash = ?1");
  LOWORD(v92) = 19;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v27);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v28 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "INSERT INTO Actions (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)");
  LOWORD(v92) = 20;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v28);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v29 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT Type, BinaryRepresentation FROM Actions WHERE Hash = ?1");
  LOWORD(v92) = 21;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v29);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v30 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM Actions WHERE Hash = ?1");
  LOWORD(v92) = 22;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v30);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v31 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Actions SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 23;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v31);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v32 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Actions SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 24;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v32);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v33 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "DELETE FROM Actions WHERE Hash = ?1");
  LOWORD(v92) = 25;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v33);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v34 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM TraceProfiles WHERE Hash = ?1");
  LOWORD(v92) = 40;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v34);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v35 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "INSERT INTO TraceProfiles (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)";
  v81 = 87;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v36, v35, (__int64)&v80);
  LOWORD(v92) = 41;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v37 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT Type, BinaryRepresentation FROM TraceProfiles WHERE Hash = ?1");
  LOWORD(v92) = 42;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v37);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v38 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM TraceProfiles WHERE Hash = ?1");
  LOWORD(v92) = 43;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v38);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v39 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE TraceProfiles SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 44;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v39);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v40 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE TraceProfiles SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 45;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v40);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v41 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "DELETE FROM TraceProfiles WHERE Hash = ?1";
  v81 = 41;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v42, v41, (__int64)&v80);
  LOWORD(v92) = 46;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v43 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM Configurations WHERE Hash = ?1");
  LOWORD(v92) = 47;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v43);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v44 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "INSERT INTO Configurations (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)";
  v81 = 88;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v45, v44, (__int64)&v80);
  LOWORD(v92) = 48;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v46 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT Type, BinaryRepresentation FROM Configurations WHERE Hash = ?1");
  LOWORD(v92) = 49;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v46);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v47 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM Configurations WHERE Hash = ?1");
  LOWORD(v92) = 50;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v47);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v48 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Configurations SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 51;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v48);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v49 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE Configurations SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 52;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v49);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v50 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "DELETE FROM Configurations WHERE Hash = ?1";
  v81 = 42;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v51, v50, (__int64)&v80);
  LOWORD(v92) = 53;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v52 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM TelemetryEvents WHERE Hash = ?1");
  LOWORD(v92) = 54;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v52);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v53 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "INSERT INTO TelemetryEvents (Hash,Type,RefCount,BinaryRepresentation)VALUES (?1,?2,?3,?4)";
  v81 = 89;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v54, v53, (__int64)&v80);
  LOWORD(v92) = 55;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v55 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT Type, BinaryRepresentation FROM TelemetryEvents WHERE Hash = ?1");
  LOWORD(v92) = 56;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v55);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v56 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM TelemetryEvents WHERE Hash = ?1");
  LOWORD(v92) = 57;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v56);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v57 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE TelemetryEvents SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 59;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v57);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v58 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v93,
          *((_QWORD *)this + 5),
          "UPDATE TelemetryEvents SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 58;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v58);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v59 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "DELETE FROM TelemetryEvents WHERE Hash = ?1";
  v81 = 43;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v60, v59, (__int64)&v80);
  LOWORD(v92) = 60;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v61 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v94,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM ScenarioStateModels WHERE Hash = ?1");
  LOWORD(v92) = 26;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v61);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v94);
  v62 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "INSERT INTO ScenarioStateModels (Hash,RefCount,BinaryRepresentation)VALUES (?1,?2,?3)";
  v81 = 85;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v63, v62, (__int64)&v80);
  LOWORD(v92) = 27;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v64 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          &v95,
          *((_QWORD *)this + 5),
          "SELECT BinaryRepresentation FROM ScenarioStateModels WHERE Hash = ?1");
  LOWORD(v92) = 28;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v64);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v95);
  v65 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v83,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM ScenarioStateModels WHERE Hash = ?1");
  LOWORD(v92) = 29;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v65);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v83);
  v66 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v84,
          *((_QWORD *)this + 5),
          "UPDATE ScenarioStateModels SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 30;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v66);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v84);
  v67 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v85,
          *((_QWORD *)this + 5),
          "UPDATE ScenarioStateModels SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 31;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v67);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v85);
  v68 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "DELETE FROM ScenarioStateModels WHERE Hash = ?1";
  v81 = 47;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v69, v68, (__int64)&v80);
  LOWORD(v92) = 32;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v70 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v86,
          *((_QWORD *)this + 5),
          "SELECT COUNT(1) FROM Transitions WHERE Hash = ?1");
  LOWORD(v92) = 33;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v70);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v86);
  v71 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v87,
          *((_QWORD *)this + 5),
          "INSERT INTO Transitions (Hash,RefCount,BinaryRepresentation)VALUES (?1,?2,?3)");
  LOWORD(v92) = 34;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v71);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v87);
  v72 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "SELECT BinaryRepresentation FROM Transitions WHERE Hash = ?1";
  v81 = 60;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v73, v72, (__int64)&v80);
  LOWORD(v92) = 35;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  v74 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v88,
          *((_QWORD *)this + 5),
          "SELECT RefCount FROM Transitions WHERE Hash = ?1");
  LOWORD(v92) = 36;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v74);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v88);
  v75 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v89,
          *((_QWORD *)this + 5),
          "UPDATE Transitions SET RefCount = RefCount + 1 WHERE Hash = ?1");
  LOWORD(v92) = 37;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v75);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v89);
  v76 = std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&void wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(
          v90,
          *((_QWORD *)this + 5),
          "UPDATE Transitions SET RefCount = RefCount - 1 WHERE Hash = ?1");
  LOWORD(v92) = 38;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    v76);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(v90);
  v77 = (_QWORD *)*((_QWORD *)this + 5);
  v92 = operator new(0x30u);
  v82 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043B600, v79);
  v80 = "DELETE FROM Transitions WHERE Hash = ?1";
  v81 = 39;
  v93 = Microsoft::Diagnostics::SqliteStatement::SqliteStatement(v78, v77, (__int64)&v80);
  LOWORD(v92) = 39;
  std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<enum Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(
    (char *)this + 280,
    v79,
    &v92,
    &v93);
  std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(&v93);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v91);
}

```

## disassembly

```asm
0x180220a3c  push    rbp
0x180220a3e  push    rbx
0x180220a3f  push    rsi
0x180220a40  push    rdi
0x180220a41  push    r12
0x180220a43  push    r13
0x180220a45  push    r14
0x180220a47  push    r15
0x180220a49  lea     rbp, [rsp-1Fh]
0x180220a4e  sub     rsp, 0A8h
0x180220a55  mov     rdi, rcx
0x180220a58  lea     rdx, [rcx+0C8h]
0x180220a5f  lea     rcx, [rbp+57h+var_50]
0x180220a63  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x180220a68  nop
0x180220a69  lea     rsi, [rdi+118h]
0x180220a70  mov     rbx, [rdi+28h]
0x180220a74  mov     r15d, 30h ; '0'
0x180220a7a  mov     ecx, r15d; Size
0x180220a7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180220a82  mov     r10, rax
0x180220a85  mov     [rbp+57h+arg_0], rax
0x180220a89  lea     rdx, [rbp+57h+var_C0]
0x180220a8d  lea     r14, unk_18043B600
0x180220a94  mov     rcx, r14
0x180220a97  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180220a9c  movups  xmm0, xmmword ptr [rax]
0x180220a9f  movdqu  [rbp+57h+var_A0], xmm0
0x180220aa4  lea     rax, aSelectCount1Fr_3; "SELECT COUNT(1) FROM Scenarios WHERE Ha"...
0x180220aab  mov     [rbp+57h+var_B0], rax
0x180220aaf  lea     r13d, [r15-2]
0x180220ab3  mov     [rbp+57h+var_A8], r13
0x180220ab7  lea     r9, [rbp+57h+var_A0]
0x180220abb  lea     r8, [rbp+57h+var_B0]
0x180220abf  mov     rdx, rbx
0x180220ac2  mov     rcx, r10
0x180220ac5  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x180220aca  nop
0x180220acb  mov     [rbp+57h+arg_8], rax
0x180220acf  xor     eax, eax
0x180220ad1  mov     word ptr [rbp+57h+arg_0], ax
0x180220ad5  lea     r9, [rbp+57h+arg_8]
0x180220ad9  lea     r8, [rbp+57h+arg_0]
0x180220add  lea     rdx, [rbp+57h+var_C0]
0x180220ae1  mov     rcx, rsi
0x180220ae4  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x180220ae9  nop
0x180220aea  lea     rcx, [rbp+57h+arg_8]
0x180220aee  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x180220af3  mov     rbx, [rdi+28h]
0x180220af7  mov     ecx, r15d; Size
0x180220afa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180220aff  mov     r10, rax
0x180220b02  mov     [rbp+57h+arg_0], rax
0x180220b06  lea     rdx, [rbp+57h+var_C0]
0x180220b0a  mov     rcx, r14
0x180220b0d  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180220b12  movups  xmm0, xmmword ptr [rax]
0x180220b15  movdqu  [rbp+57h+var_A0], xmm0
0x180220b1a  lea     rax, aInsertIntoScen_0; "INSERT INTO Scenarios (Hash,NamespaceHa"...
0x180220b21  mov     [rbp+57h+var_B0], rax
0x180220b25  mov     [rbp+57h+var_A8], 50h ; 'P'
0x180220b2d  lea     r9, [rbp+57h+var_A0]
0x180220b31  lea     r8, [rbp+57h+var_B0]
0x180220b35  mov     rdx, rbx
0x180220b38  mov     rcx, r10
0x180220b3b  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x180220b40  nop
0x180220b41  mov     [rbp+57h+arg_8], rax
0x180220b45  lea     eax, [r15-2Fh]
0x180220b49  mov     word ptr [rbp+57h+arg_0], ax
0x180220b4d  lea     r9, [rbp+57h+arg_8]
0x180220b51  lea     r8, [rbp+57h+arg_0]
0x180220b55  lea     rdx, [rbp+57h+var_C0]
0x180220b59  mov     rcx, rsi
0x180220b5c  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x180220b61  nop
0x180220b62  lea     rcx, [rbp+57h+arg_8]
0x180220b66  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x180220b6b  lea     r8, aSelectNamespac; "SELECT NamespaceHash FROM Scenarios WHE"...
0x180220b72  mov     rdx, [rdi+28h]
0x180220b76  lea     rcx, [rbp+57h+arg_8]
0x180220b7a  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x180220b7f  nop
0x180220b80  lea     ecx, [r15-2Eh]
0x180220b84  mov     word ptr [rbp+57h+arg_0], cx
0x180220b88  mov     r9, rax
0x180220b8b  lea     r8, [rbp+57h+arg_0]
0x180220b8f  lea     rdx, [rbp+57h+var_C0]
0x180220b93  mov     rcx, rsi
0x180220b96  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x180220b9b  nop
0x180220b9c  lea     rcx, [rbp+57h+arg_8]
0x180220ba0  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x180220ba5  lea     r8, aSelectNamespac_0; "SELECT NamespaceHash, BinaryRepresentat"...
0x180220bac  mov     rdx, [rdi+28h]
0x180220bb0  lea     rcx, [rbp+57h+arg_8]
0x180220bb4  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x180220bb9  nop
0x180220bba  lea     ecx, [r15-2Dh]
0x180220bbe  mov     word ptr [rbp+57h+arg_0], cx
0x180220bc2  mov     r9, rax
0x180220bc5  lea     r8, [rbp+57h+arg_0]
0x180220bc9  lea     rdx, [rbp+57h+var_C0]
0x180220bcd  mov     rcx, rsi
0x180220bd0  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x180220bd5  nop
0x180220bd6  lea     rcx, [rbp+57h+arg_8]
0x180220bda  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x180220bdf  mov     rbx, [rdi+28h]
0x180220be3  mov     ecx, r15d; Size
0x180220be6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180220beb  mov     r10, rax
0x180220bee  mov     [rbp+57h+arg_0], rax
0x180220bf2  lea     rdx, [rbp+57h+var_C0]
0x180220bf6  mov     rcx, r14
0x180220bf9  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180220bfe  movups  xmm0, xmmword ptr [rax]
0x180220c01  movdqu  [rbp+57h+var_A0], xmm0
0x180220c06  lea     rax, aDeleteFromScen_0; "DELETE FROM Scenarios WHERE Hash = ?1"
0x180220c0d  mov     [rbp+57h+var_B0], rax
0x180220c11  mov     [rbp+57h+var_A8], 25h ; '%'
0x180220c19  lea     r9, [rbp+57h+var_A0]
0x180220c1d  lea     r8, [rbp+57h+var_B0]
0x180220c21  mov     rdx, rbx
0x180220c24  mov     rcx, r10
0x180220c27  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x180220c2c  nop
0x180220c2d  mov     [rbp+57h+arg_8], rax
0x180220c31  lea     eax, [r15-2Ch]
0x180220c35  mov     word ptr [rbp+57h+arg_0], ax
0x180220c39  lea     r9, [rbp+57h+arg_8]
0x180220c3d  lea     r8, [rbp+57h+arg_0]
0x180220c41  lea     rdx, [rbp+57h+var_C0]
0x180220c45  mov     rcx, rsi
0x180220c48  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x180220c4d  nop
0x180220c4e  lea     rcx, [rbp+57h+arg_8]
0x180220c52  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x180220c57  lea     r8, aSelectCount1Fr_1; "SELECT COUNT(1) FROM Triggers WHERE Has"...
0x180220c5e  mov     rdx, [rdi+28h]
0x180220c62  lea     rcx, [rbp+57h+arg_8]
0x180220c66  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x180220c6b  nop
0x180220c6c  lea     ecx, [r15-2Bh]
0x180220c70  mov     word ptr [rbp+57h+arg_0], cx
0x180220c74  mov     r9, rax
0x180220c77  lea     r8, [rbp+57h+arg_0]
0x180220c7b  lea     rdx, [rbp+57h+var_C0]
0x180220c7f  mov     rcx, rsi
0x180220c82  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x180220c87  nop
0x180220c88  lea     rcx, [rbp+57h+arg_8]
0x180220c8c  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x180220c91  mov     rbx, [rdi+28h]
0x180220c95  mov     ecx, r15d; Size
0x180220c98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180220c9d  mov     r10, rax
0x180220ca0  mov     [rbp+57h+arg_0], rax
0x180220ca4  lea     rdx, [rbp+57h+var_C0]
0x180220ca8  mov     rcx, r14
0x180220cab  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180220cb0  movups  xmm0, xmmword ptr [rax]
0x180220cb3  movdqu  [rbp+57h+var_A0], xmm0
0x180220cb8  lea     rax, aInsertIntoTrig; "INSERT INTO Triggers (Hash,Type,RefCoun"...
0x180220cbf  mov     [rbp+57h+var_B0], rax
0x180220cc3  mov     [rbp+57h+var_A8], 52h ; 'R'
0x180220ccb  lea     r9, [rbp+57h+var_A0]
0x180220ccf  lea     r8, [rbp+57h+var_B0]
0x180220cd3  mov     rdx, rbx
0x180220cd6  mov     rcx, r10
0x180220cd9  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x180220cde  nop
0x180220cdf  mov     [rbp+57h+arg_8], rax
0x180220ce3  lea     eax, [r15-2Ah]
0x180220ce7  mov     word ptr [rbp+57h+arg_0], ax
0x180220ceb  lea     r9, [rbp+57h+arg_8]
0x180220cef  lea     r8, [rbp+57h+arg_0]
0x180220cf3  lea     rdx, [rbp+57h+var_C0]
0x180220cf7  mov     rcx, rsi
0x180220cfa  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x180220cff  nop
0x180220d00  lea     rcx, [rbp+57h+arg_8]
0x180220d04  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x180220d09  mov     rbx, [rdi+28h]
0x180220d0d  mov     ecx, r15d; Size
0x180220d10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180220d15  mov     r10, rax
0x180220d18  mov     [rbp+57h+arg_0], rax
0x180220d1c  lea     rdx, [rbp+57h+var_C0]
0x180220d20  mov     rcx, r14
0x180220d23  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180220d28  movups  xmm0, xmmword ptr [rax]
0x180220d2b  movdqu  [rbp+57h+var_A0], xmm0
0x180220d30  lea     rax, aSelectTypeBina_0; "SELECT Type, BinaryRepresentation FROM "...
0x180220d37  mov     [rbp+57h+var_B0], rax
0x180220d3b  mov     [rbp+57h+var_A8], 3Fh ; '?'
0x180220d43  lea     r9, [rbp+57h+var_A0]
0x180220d47  lea     r8, [rbp+57h+var_B0]
0x180220d4b  mov     rdx, rbx
0x180220d4e  mov     rcx, r10
0x180220d51  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x180220d56  nop
0x180220d57  mov     [rbp+57h+arg_8], rax
0x180220d5b  lea     eax, [r15-29h]
0x180220d5f  mov     word ptr [rbp+57h+arg_0], ax
0x180220d63  lea     r9, [rbp+57h+arg_8]
0x180220d67  lea     r8, [rbp+57h+arg_0]
0x180220d6b  lea     rdx, [rbp+57h+var_C0]
0x180220d6f  mov     rcx, rsi
0x180220d72  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x180220d77  nop
0x180220d78  lea     rcx, [rbp+57h+arg_8]
0x180220d7c  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x180220d81  lea     r8, aSelectRefcount_6; "SELECT RefCount FROM Triggers WHERE Has"...
0x180220d88  mov     rdx, [rdi+28h]
0x180220d8c  lea     rcx, [rbp+57h+arg_8]
0x180220d90  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x180220d95  nop
0x180220d96  lea     ecx, [r15-28h]
0x180220d9a  mov     word ptr [rbp+57h+arg_0], cx
0x180220d9e  mov     r9, rax
0x180220da1  lea     r8, [rbp+57h+arg_0]
0x180220da5  lea     rdx, [rbp+57h+var_C0]
0x180220da9  mov     rcx, rsi
0x180220dac  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x180220db1  nop
0x180220db2  lea     rcx, [rbp+57h+arg_8]
0x180220db6  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x180220dbb  lea     r8, aUpdateTriggers; "UPDATE Triggers SET RefCount = RefCount"...
0x180220dc2  mov     rdx, [rdi+28h]
0x180220dc6  lea     rcx, [rbp+57h+arg_8]
0x180220dca  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x180220dcf  nop
0x180220dd0  lea     ecx, [r15-27h]
0x180220dd4  mov     word ptr [rbp+57h+arg_0], cx
0x180220dd8  mov     r9, rax
0x180220ddb  lea     r8, [rbp+57h+arg_0]
0x180220ddf  lea     rdx, [rbp+57h+var_C0]
0x180220de3  mov     rcx, rsi
0x180220de6  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x180220deb  nop
0x180220dec  lea     rcx, [rbp+57h+arg_8]
0x180220df0  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x180220df5  lea     r8, aUpdateTriggers_0; "UPDATE Triggers SET RefCount = RefCount"...
0x180220dfc  mov     rdx, [rdi+28h]
0x180220e00  lea     rcx, [rbp+57h+arg_8]
0x180220e04  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x180220e09  nop
0x180220e0a  lea     ecx, [r15-26h]
0x180220e0e  mov     word ptr [rbp+57h+arg_0], cx
0x180220e12  mov     r9, rax
0x180220e15  lea     r8, [rbp+57h+arg_0]
0x180220e19  lea     rdx, [rbp+57h+var_C0]
0x180220e1d  mov     rcx, rsi
0x180220e20  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x180220e25  nop
0x180220e26  lea     rcx, [rbp+57h+arg_8]
0x180220e2a  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x180220e2f  mov     rbx, [rdi+28h]
0x180220e33  mov     ecx, r15d; Size
0x180220e36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180220e3b  mov     r10, rax
0x180220e3e  mov     [rbp+57h+arg_0], rax
0x180220e42  lea     rdx, [rbp+57h+var_C0]
0x180220e46  mov     rcx, r14
0x180220e49  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180220e4e  movups  xmm0, xmmword ptr [rax]
0x180220e51  movdqu  [rbp+57h+var_A0], xmm0
0x180220e56  lea     rax, aDeleteFromTrig; "DELETE FROM Triggers WHERE Hash = ?1"
0x180220e5d  mov     [rbp+57h+var_B0], rax
0x180220e61  mov     [rbp+57h+var_A8], 24h ; '$'
0x180220e69  lea     r9, [rbp+57h+var_A0]
0x180220e6d  lea     r8, [rbp+57h+var_B0]
0x180220e71  mov     rdx, rbx
0x180220e74  mov     rcx, r10
0x180220e77  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x180220e7c  nop
0x180220e7d  mov     [rbp+57h+arg_8], rax
0x180220e81  lea     eax, [r15-25h]
0x180220e85  mov     word ptr [rbp+57h+arg_0], ax
0x180220e89  lea     r9, [rbp+57h+arg_8]
0x180220e8d  lea     r8, [rbp+57h+arg_0]
0x180220e91  lea     rdx, [rbp+57h+var_C0]
0x180220e95  mov     rcx, rsi
0x180220e98  call    ??$emplace@W4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@U?$less@VScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@@6@V?$allocator@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@V?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAW4_enumerated@ScenarioDbObjectQuery@EnumDetails@Diagnostics@Microsoft@@$$QEAV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>,std::less<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery>,std::allocator<std::pair<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery const,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>>,0>>::emplace<Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>>(Microsoft::Diagnostics::EnumDetails::ScenarioDbObjectQuery::_enumerated &&,std::unique_ptr<Microsoft::Diagnostics::SqliteStatement> &&)
0x180220e9d  nop
0x180220e9e  lea     rcx, [rbp+57h+arg_8]
0x180220ea2  call    ??1?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqliteStatement>::~unique_ptr<Microsoft::Diagnostics::SqliteStatement>(void)
0x180220ea7  lea     r8, aSelectCount1Fr_5; "SELECT COUNT(1) FROM Filters WHERE Hash"...
0x180220eae  mov     rdx, [rdi+28h]
0x180220eb2  lea     rcx, [rbp+57h+arg_8]
0x180220eb6  call    ??$make_unique@VSqliteStatement@Diagnostics@Microsoft@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD$0A@@std@@YA?AV?$unique_ptr@VSqliteStatement@Diagnostics@Microsoft@@U?$default_delete@VSqliteStatement@Diagnostics@Microsoft@@@std@@@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAY0EO@$$CBD@Z; std::make_unique<Microsoft::Diagnostics::SqliteStatement,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78],0>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> &,char const (&)[78])
0x180220ebb  nop
0x180220ebc  lea     ecx, [r15-24h]
0x180220ec0  mov     word ptr [rbp+57h+arg_0], cx
0x180220ec4  mov     r9, rax
0x180220ec7  lea     r8, [rbp+57h+arg_0]
0x180220ecb  lea     rdx, [rbp+57h+var_C0]
0x180220ecf  mov     rcx, rsi
  ... truncated ...
```
