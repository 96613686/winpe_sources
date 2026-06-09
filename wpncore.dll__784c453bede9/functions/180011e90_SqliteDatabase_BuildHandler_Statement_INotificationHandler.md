# SqliteDatabase::BuildHandler(Statement *,INotificationHandler * *)

- ea: `0x180011e90`
- end: `0x18001328b`
- name: `?BuildHandler@SqliteDatabase@@AEAA_NPEAVStatement@@PEAPEAUINotificationHandler@@@Z`
- size: `5115`
- prototype: `bool __fastcall(SqliteDatabase *__hidden this, struct Statement *, struct INotificationHandler **)`
- caller_count: `5`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008530`
- `0x1800087d0`
- `0x180008920`
- `0x1800aa120`
- `0x1800b5b90`

## callees

- `0x18000522c`
- `0x18000de40`
- `0x18000e090`
- `0x18000e5f4`
- `0x18000f8d8`
- `0x18000f9d4`
- `0x180011618`
- `0x180011800`
- `0x180011970`
- `0x180011b10`
- `0x180011e6c`
- `0x180011e90`
- `0x1800132a0`
- `0x180013360`
- `0x1800a4810`
- `0x1800b99f0`
- `0x1800b9a20`
- `0x1800b9ecc`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001250e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012b6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012c53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012d72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001250e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012b6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012c53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012d72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012e77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012f27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012f90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001301f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012e77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012f27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012f90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18001301f`
- `winsqlite3!sqlite3_column_int64` at `0x18001211f`
- `winsqlite3!sqlite3_column_int64` at `0x1800123d2`
- `winsqlite3!sqlite3_column_int64` at `0x18001211f`
- `winsqlite3!sqlite3_column_int64` at `0x1800123d2`
- `winsqlite3!sqlite3_column_int` at `0x180011fca`
- `winsqlite3!sqlite3_column_int` at `0x180011fca`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800125c8`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800125c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall SqliteDatabase::BuildHandler(
        SqliteDatabase *this,
        struct sqlite3_stmt **a2,
        struct INotificationHandler **a3)
{
  struct sqlite3_stmt **v3; // r14
  __int128 v4; // xmm0
  void *v5; // rdx
  unsigned int v6; // r12d
  unsigned int v7; // edx
  unsigned int v8; // r15d
  __m128i si128; // xmm6
  _BYTE *v10; // rdi
  _BYTE *v11; // rsi
  int v12; // eax
  __int64 ColumnText16; // rbx
  int v14; // r15d
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 ColumnBlob; // rbx
  void *v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rbx
  __int16 *v21; // rbx
  NotificationSettings *v22; // rcx
  void *v23; // rax
  NotificationSettings *v24; // rax
  NotificationSettings *v25; // r13
  unsigned __int64 v26; // r14
  unsigned __int64 v27; // rdi
  unsigned __int64 v28; // r8
  __int64 (__fastcall *v29)(char *, _QWORD *, BOOL); // rsi
  BOOL v30; // edi
  _QWORD *v31; // rax
  int v32; // eax
  _WORD *v33; // rax
  _WORD *v34; // rdx
  unsigned __int64 v35; // rcx
  __int16 v36; // ax
  _WORD *v37; // rcx
  __int16 *v38; // rsi
  __int16 *v39; // r13
  __int16 *v40; // rbx
  unsigned __int8 v41; // di
  IStream *v42; // r12
  struct Statement *v43; // rax
  __int16 *v44; // r14
  void (__stdcall *v45)(GUID, void *); // rdi
  __int16 *v46; // r15
  __int16 *v47; // rsi
  __int16 *v48; // rbx
  NotificationHandler *v49; // rax
  NotificationHandler *v50; // rax
  NotificationHandler *v51; // r13
  _QWORD *v52; // r12
  unsigned __int64 v53; // r13
  unsigned __int64 v54; // rdi
  unsigned __int64 v55; // r8
  __int64 v56; // r9
  int v57; // ebx
  void *v58; // rax
  NotificationSettings *v59; // rcx
  NotificationHandler v61; // rcx
  NotificationHandler v62; // rcx
  void (__stdcall *v63)(GUID, void *); // rbx
  NotificationHandler v64; // rcx
  NotificationHandler *v65; // r12
  unsigned __int64 v66; // r13
  unsigned __int64 v67; // rbx
  unsigned __int64 v68; // r8
  __int64 v69; // r9
  unsigned __int64 v70; // rsi
  unsigned __int64 v71; // rbx
  unsigned __int64 v72; // r8
  __int64 v73; // r9
  LPVOID *v74; // r15
  unsigned __int64 v75; // rsi
  unsigned __int64 v76; // rbx
  unsigned __int64 v77; // r8
  __int64 v78; // rdx
  unsigned __int64 v79; // rsi
  LPVOID v80; // rax
  _WORD *v81; // rax
  _WORD *v82; // rdx
  unsigned __int64 v83; // rcx
  __int16 v84; // ax
  _WORD *v85; // rcx
  int v86; // eax
  void (__stdcall *v87)(GUID, void *); // rax
  _WORD *v88; // rdx
  unsigned __int64 v89; // rcx
  __int16 v90; // ax
  _WORD *v91; // rcx
  void (__stdcall *v92)(GUID, void *); // rax
  _WORD *v93; // rdx
  unsigned __int64 v94; // rcx
  __int16 v95; // ax
  _WORD *v96; // rcx
  _WORD *v97; // rax
  int v98; // edx
  _WORD *v99; // rdx
  unsigned __int64 v100; // rcx
  __int16 v101; // ax
  _WORD *v102; // rcx
  unsigned __int64 v103; // r12
  void (__stdcall *v104)(GUID, void *); // rax
  NotificationHandler *v105; // rcx
  unsigned __int64 v106; // rdi
  void (__stdcall *v107)(GUID, void *); // rax
  unsigned __int64 v108; // rdi
  void (__stdcall *v109)(GUID, void *); // rax
  unsigned __int64 v110; // rdi
  LPVOID v111; // rax
  int v112; // [rsp+20h] [rbp-E0h]
  void *v113; // [rsp+28h] [rbp-D8h] BYREF
  NotificationHandler *v114; // [rsp+30h] [rbp-D0h]
  NotificationSettings *v115; // [rsp+38h] [rbp-C8h]
  BYTE *pInit; // [rsp+40h] [rbp-C0h] BYREF
  IStream *v117; // [rsp+48h] [rbp-B8h]
  void *v118; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v119; // [rsp+58h] [rbp-A8h] BYREF
  void (__stdcall *v120)(GUID, void *); // [rsp+60h] [rbp-A0h]
  unsigned __int64 v121; // [rsp+68h] [rbp-98h] BYREF
  void *v122; // [rsp+70h] [rbp-90h] BYREF
  struct Statement *v123; // [rsp+78h] [rbp-88h]
  IStream *v124; // [rsp+80h] [rbp-80h]
  void *Block; // [rsp+88h] [rbp-78h] BYREF
  void (__stdcall *v126)(GUID, void *); // [rsp+90h] [rbp-70h]
  _BYTE *v127; // [rsp+98h] [rbp-68h]
  void *v128[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v129; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v130; // [rsp+B8h] [rbp-48h]
  __int128 v131; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v132; // [rsp+D0h] [rbp-30h]
  __int128 v133; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v134; // [rsp+F0h] [rbp-10h]
  __int128 v135; // [rsp+100h] [rbp+0h] BYREF
  __int128 v136; // [rsp+110h] [rbp+10h]
  __int128 v137; // [rsp+120h] [rbp+20h] BYREF
  __int128 v138; // [rsp+130h] [rbp+30h]
  __int128 v139; // [rsp+140h] [rbp+40h] BYREF
  __int128 v140; // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v121 = (unsigned __int64)a3;
  v3 = a2;
  v123 = (struct Statement *)a2;
  *a3 = 0;
  v115 = 0;
  v4 = 0;
  v131 = 0;
  v132 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v131);
  v139 = v4;
  v140 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v139);
  v133 = v4;
  v134 = 0;
  std::wstring::_Construct_empty(&v133);
  v113 = v5;
  *(double *)&v4 = std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>(&Block);
  v137 = v4;
  v138 = 0;
  *(double *)&v4 = std::wstring::_Construct_empty(&v137);
  v135 = v4;
  v136 = 0;
  std::wstring::_Construct_empty(&v135);
  v6 = 1;
  LOBYTE(v112) = v7;
  v8 = v7;
  LODWORD(v114) = v7;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v10 = v127;
  v118 = v127;
  v120 = v126;
  v11 = Block;
  for ( pInit = (BYTE *)Block; ; v11 = pInit )
  {
    if ( !*v3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
        (const char *)0x8007139FLL,
        v112);
    v12 = Statement::dal_step(*v3);
    if ( v12 != -2018574236 )
      break;
    if ( v6 != 1 )
      goto LABEL_64;
    LOBYTE(v112) = 1;
    v6 = sqlite3_column_int(*v3, 9);
    LODWORD(v117) = v6;
    ColumnText16 = Statement::GetColumnText16(v3, v128, 0);
    if ( &v131 == (__int128 *)ColumnText16 )
    {
      v14 = 0;
    }
    else
    {
      if ( v132.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(v131, 2 * v132.m128i_i64[1] + 2);
      v132 = si128;
      v14 = 0;
      LOWORD(v131) = 0;
      v131 = *(_OWORD *)ColumnText16;
      v132 = *(__m128i *)(ColumnText16 + 16);
      *(_QWORD *)(ColumnText16 + 16) = 0;
      *(_QWORD *)(ColumnText16 + 24) = 7;
      *(_WORD *)ColumnText16 = 0;
    }
    if ( v130 > 7 )
      std::_Deallocate<16>(v128[0], 2 * v130 + 2);
    v15 = Statement::GetColumnText16(v3, v128, 1);
    if ( &v139 != (__int128 *)v15 )
    {
      if ( *((_QWORD *)&v140 + 1) > 7u )
        std::_Deallocate<16>(v139, 2LL * *((_QWORD *)&v140 + 1) + 2);
      v139 = *(_OWORD *)v15;
      v140 = *(_OWORD *)(v15 + 16);
      *(_QWORD *)(v15 + 16) = 0;
      *(_QWORD *)(v15 + 24) = 7;
      *(_WORD *)v15 = 0;
    }
    if ( v130 > 7 )
      std::_Deallocate<16>(v128[0], 2 * v130 + 2);
    v16 = Statement::GetColumnText16(v3, v128, 2);
    if ( &v133 != (__int128 *)v16 )
    {
      if ( *((_QWORD *)&v134 + 1) > 7u )
        std::_Deallocate<16>(v133, 2LL * *((_QWORD *)&v134 + 1) + 2);
      v133 = *(_OWORD *)v16;
      v134 = *(_OWORD *)(v16 + 16);
      *(_QWORD *)(v16 + 16) = 0;
      *(_QWORD *)(v16 + 24) = 7;
      *(_WORD *)v16 = 0;
    }
    if ( v130 > 7 )
      std::_Deallocate<16>(v128[0], 2 * v130 + 2);
    v113 = (void *)sqlite3_column_int64(*v3, 3);
    ColumnBlob = Statement::GetColumnBlob(v3, v128, 4);
    if ( &Block != (void **)ColumnBlob )
    {
      if ( v11 )
      {
        pInit = (BYTE *)(v10 - v11);
        v118 = v11;
        if ( (unsigned __int64)(v10 - v11) >= 0x1000 )
        {
          std::_Adjust_manually_vector_aligned(&v118, (unsigned __int64 *)&pInit);
          v11 = v118;
        }
        operator delete(v11);
      }
      pInit = *(BYTE **)ColumnBlob;
      Block = pInit;
      v120 = *(void (__stdcall **)(GUID, void *))(ColumnBlob + 8);
      v126 = v120;
      v118 = *(void **)(ColumnBlob + 16);
      v127 = v118;
      *(_QWORD *)ColumnBlob = 0;
      *(_QWORD *)(ColumnBlob + 8) = 0;
      *(_QWORD *)(ColumnBlob + 16) = 0;
    }
    v18 = v128[0];
    if ( v128[0] )
    {
      v119 = v129 - (unsigned __int64)v128[0];
      v122 = v128[0];
      if ( v129 - (unsigned __int64)v128[0] >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v122, &v119);
        v18 = v122;
      }
      operator delete(v18);
    }
    v19 = Statement::GetColumnText16(v3, v128, 5);
    if ( &v137 != (__int128 *)v19 )
    {
      if ( *((_QWORD *)&v138 + 1) > 7u )
        std::_Deallocate<16>(v137, 2LL * *((_QWORD *)&v138 + 1) + 2);
      v137 = *(_OWORD *)v19;
      v138 = *(_OWORD *)(v19 + 16);
      *(_QWORD *)(v19 + 16) = 0;
      *(_QWORD *)(v19 + 24) = 7;
      *(_WORD *)v19 = 0;
    }
    if ( v130 > 7 )
      std::_Deallocate<16>(v128[0], 2 * v130 + 2);
    v20 = Statement::GetColumnText16(v3, v128, 6);
    if ( &v135 != (__int128 *)v20 )
    {
      if ( *((_QWORD *)&v136 + 1) > 7u )
        std::_Deallocate<16>(v135, 2LL * *((_QWORD *)&v136 + 1) + 2);
      v135 = *(_OWORD *)v20;
      v136 = *(_OWORD *)(v20 + 16);
      *(_QWORD *)(v20 + 16) = 0;
      *(_QWORD *)(v20 + 24) = 7;
      *(_WORD *)v20 = 0;
    }
    if ( v130 > 7 )
      std::_Deallocate<16>(v128[0], 2 * v130 + 2);
    v21 = (__int16 *)&v131;
    if ( v132.m128i_i64[1] > 7uLL )
      v21 = (__int16 *)v131;
    v22 = v115;
    if ( v115 )
    {
      v115 = 0;
      (*(void (__fastcall **)(NotificationSettings *))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v115 = 0;
    v23 = operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    v119 = (unsigned __int64)v23;
    v122 = v23;
    if ( !v23 )
    {
      v14 = -2147024882;
      goto LABEL_62;
    }
    v124 = (IStream *)v23;
    v24 = NotificationSettings::NotificationSettings((NotificationSettings *)v23);
    v25 = v24;
    v119 = 0;
    if ( !v21 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)v24 + 48);
      goto LABEL_194;
    }
    v26 = -1;
    do
      ++v26;
    while ( v21[v26] );
    v27 = v26 + 1;
    if ( v26 + 1 < v26 )
    {
LABEL_57:
      v14 = -2147024362;
      goto LABEL_58;
    }
    v28 = *((_QWORD *)v24 + 8);
    if ( v28 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount((char *)v24 + 48);
      if ( *((_QWORD *)v25 + 6) )
        v28 = *((_QWORD *)v25 + 7) + 1LL;
      else
        v28 = 0;
      *((_QWORD *)v25 + 8) = v28;
    }
    if ( v28 )
    {
      if ( v27 > v28 )
      {
        v124 = 0;
        v79 = 2 * v28;
        if ( !is_mul_ok(v28, 2u) )
          goto LABEL_57;
        if ( v28 > 0x800 )
          v79 = v28 + 2048;
        if ( v27 > v79 )
          v79 = v26 + 1;
        v80 = CoTaskMemRealloc(*((LPVOID *)v25 + 6), 2 * v79);
        if ( !v80 )
        {
          v14 = -2147024882;
          goto LABEL_59;
        }
        v14 = 0;
        *((_QWORD *)v25 + 8) = v79;
        *((_QWORD *)v25 + 6) = v80;
      }
    }
    else
    {
      v124 = 0;
      if ( !is_mul_ok(v27, 2u) )
        goto LABEL_57;
      v33 = CoTaskMemAlloc(2 * v27);
      if ( v33 )
      {
        *((_QWORD *)v25 + 8) = v27;
        *((_QWORD *)v25 + 6) = v33;
        *v33 = 0;
      }
      else
      {
        v14 = -2147024882;
      }
      if ( v14 < 0 )
        goto LABEL_59;
    }
    if ( v26 == -1 )
      goto LABEL_88;
    v34 = (_WORD *)*((_QWORD *)v25 + 6);
    if ( v27 > 0x7FFFFFFF )
    {
      *v34 = 0;
LABEL_88:
      *((_QWORD *)v25 + 7) = v26;
      goto LABEL_58;
    }
    if ( v26 <= 0x7FFFFFFE )
    {
      v35 = v26;
      do
      {
        if ( !v35 )
          break;
        v36 = *v21;
        if ( !*v21 )
          break;
        ++v21;
        *v34++ = v36;
        --v35;
        --v27;
      }
      while ( v27 );
      v37 = v34 - 1;
      if ( v27 )
        v37 = v34;
      *v37 = 0;
      goto LABEL_88;
    }
    *v34 = 0;
    *((_QWORD *)v25 + 7) = v26;
LABEL_58:
    if ( v14 >= 0 )
    {
      v14 = 0;
LABEL_194:
      if ( v25 )
        (*(void (__fastcall **)(NotificationSettings *))(*(_QWORD *)v25 + 8LL))(v25);
      v115 = v25;
      if ( v25 )
        (*(void (__fastcall **)(NotificationSettings *))(*(_QWORD *)v25 + 16LL))(v25);
      goto LABEL_61;
    }
LABEL_59:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationsettings.cpp",
      (const char *)(unsigned int)v14,
      v112);
    if ( v25 )
      (*(void (__fastcall **)(NotificationSettings *))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_61:
    v6 = (unsigned int)v117;
LABEL_62:
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB8C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v14,
        v112);
    v3 = (struct sqlite3_stmt **)v123;
    v8 = (unsigned int)v114;
LABEL_64:
    if ( v6 )
    {
      v29 = *(__int64 (__fastcall **)(char *, _QWORD *, BOOL))(*((_QWORD *)v115 + 4) + 40LL);
      v30 = sqlite3_column_int64(*v3, 8) != 0;
      v31 = (_QWORD *)Statement::GetColumnText16(v3, v128, 7);
      if ( v31[3] > 7u )
        v31 = (_QWORD *)*v31;
      v32 = v29((char *)v115 + 32, v31, v30);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB93,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
          (const char *)(unsigned int)v32,
          v112);
      if ( v130 > 7 )
        std::_Deallocate<16>(v128[0], 2 * v130 + 2);
    }
    LODWORD(v114) = ++v8;
    if ( v8 >= v6 )
      goto LABEL_90;
    v10 = v118;
  }
  if ( v12 != -2018574235 && v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\sqlitewrapper\\statement.cpp",
      (const char *)(unsigned int)v12,
      v112);
LABEL_90:
  v38 = (__int16 *)v139;
  v39 = (__int16 *)v133;
  v40 = (__int16 *)v137;
  v41 = v112;
  if ( !(_BYTE)v112 )
    goto LABEL_121;
  v42 = SHCreateMemStream(pInit, (int)v120 - (int)pInit);
  v117 = v42;
  v124 = v42;
  v43 = (struct Statement *)&v135;
  if ( *((_QWORD *)&v136 + 1) > 7u )
    v43 = (struct Statement *)v135;
  v123 = v43;
  v44 = (__int16 *)&v137;
  if ( *((_QWORD *)&v138 + 1) > 7u )
    v44 = v40;
  v45 = (void (__stdcall *)(GUID, void *))v115;
  v46 = (__int16 *)&v139;
  if ( *((_QWORD *)&v140 + 1) > 7u )
    v46 = v38;
  v47 = (__int16 *)&v133;
  if ( *((_QWORD *)&v134 + 1) > 7u )
    v47 = v39;
  v48 = (__int16 *)&v131;
  if ( v132.m128i_i64[1] > 7uLL )
    v48 = (__int16 *)v131;
  *(_QWORD *)v121 = 0;
  v49 = (NotificationHandler *)operator new(0xE0u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v49 )
  {
    v57 = -2147024882;
    goto LABEL_117;
  }
  v50 = NotificationHandler::NotificationHandler(v49);
  v51 = v50;
  v114 = v50;
  if ( v45 )
    v45 = (void (__stdcall *)(GUID, void *))((char *)v45 + 32);
  v120 = v45;
  v52 = v50 + 6;
  if ( !v48 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v50 + 6);
LABEL_142:
    if ( v51[9] != v45 )
    {
      if ( v45 )
        (*(void (__fastcall **)(void (__stdcall *)(GUID *__struct_ptr, void *)))(*(_QWORD *)v45 + 8LL))(v45);
      v61 = v51[9];
      v51[9] = v45;
      if ( v61 )
        (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v61 + 16LL))(v61);
    }
    v62 = v51[10];
    if ( v62 )
    {
      v51[10] = 0;
      (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v62 + 16LL))(v62);
    }
    v63 = (void (__stdcall *)(GUID, void *))v117;
    if ( (char *)v51[11] != (char *)v117 )
    {
      if ( v117 )
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v117 + 8LL))(v117);
      v64 = v51[11];
      v51[11] = v63;
      if ( v64 )
        (*(void (__fastcall **)(NotificationHandler))(*(_QWORD *)v64 + 16LL))(v64);
    }
    v51[21] = (NotificationHandler)v113;
    v65 = v51 + 12;
    if ( !v47 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v51 + 12);
LABEL_164:
      if ( !v46 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v51 + 15);
LABEL_173:
        v74 = (LPVOID *)(v51 + 18);
        if ( !v44 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v51 + 18);
          goto LABEL_219;
        }
        v75 = -1;
        do
          ++v75;
        while ( v44[v75] );
        v76 = v75 + 1;
        if ( v75 + 1 < v75 )
          goto LABEL_180;
        v77 = (unsigned __int64)v51[20];
        if ( v77 == -1 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v51 + 18);
          if ( *v74 )
            v77 = (unsigned __int64)v51[19] + 1;
          else
            v77 = 0;
          v51[20] = (NotificationHandler)v77;
        }
        if ( v77 )
        {
          v73 = 0;
          if ( v76 > v77 )
          {
            v113 = 0;
            v110 = 2 * v77;
            if ( !is_mul_ok(v77, 2u) )
              goto LABEL_180;
            if ( v77 > 0x800 )
              v110 = v77 + 2048;
            if ( v76 > v110 )
              v110 = v75 + 1;
            v111 = CoTaskMemRealloc(*v74, 2 * v110);
            if ( !v111 )
            {
              v73 = 2147942414LL;
              goto LABEL_182;
            }
            v73 = 0;
            v51[20] = (NotificationHandler)v110;
            *v74 = v111;
          }
        }
        else
        {
          v113 = 0;
          if ( !is_mul_ok(v76, 2u) )
          {
LABEL_180:
            v73 = 2147942934LL;
            goto LABEL_181;
          }
          v97 = CoTaskMemAlloc(2 * v76);
          if ( v97 )
          {
            v98 = 0;
            v51[20] = (NotificationHandler)v76;
            *v74 = v97;
            *v97 = 0;
          }
          else
          {
            v98 = -2147024882;
          }
          v73 = (unsigned int)v98;
          if ( v98 < 0 )
            goto LABEL_182;
        }
        if ( v75 != -1 )
        {
          v99 = *v74;
          if ( v76 > 0x7FFFFFFF )
          {
            *v99 = 0;
          }
          else
          {
            if ( v75 > 0x7FFFFFFE )
            {
              *v99 = 0;
              v51[19] = (NotificationHandler)v75;
LABEL_181:
              if ( (int)v73 < 0 )
              {
LABEL_182:
                v57 = v73;
                v78 = 42;
                goto LABEL_183;
              }
LABEL_219:
              v86 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                      v51 + 22,
                      v123,
                      -1);
              v57 = v86;
              if ( v86 >= 0 )
              {
                v57 = (*(__int64 (__fastcall **)(NotificationHandler *, GUID *, unsigned __int64))*v51)(
                        v51,
                        &GUID_23eb7394_4610_4807_baec_9a72f86ffa0b,
                        v121);
                (*((void (__fastcall **)(NotificationHandler *))*v51 + 2))(v51);
                goto LABEL_116;
              }
              v73 = (unsigned int)v86;
              v78 = 43;
LABEL_183:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v78,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationhandler.cpp",
                (const char *)v73,
                v112);
              goto LABEL_114;
            }
            v100 = v75;
            do
            {
              if ( !v100 )
                break;
              v101 = *v44;
              if ( !*v44 )
                break;
              ++v44;
              *v99++ = v101;
              --v100;
              --v76;
            }
            while ( v76 );
            v102 = v99 - 1;
            if ( v76 )
              v102 = v99;
            *v102 = 0;
          }
        }
        v51[19] = (NotificationHandler)v75;
        goto LABEL_181;
      }
      v70 = -1;
      do
        ++v70;
      while ( v46[v70] );
      v71 = v70 + 1;
      if ( v70 + 1 < v70 )
        goto LABEL_171;
      v72 = (unsigned __int64)v51[17];
      if ( v72 == -1 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v51 + 15);
        if ( v51[15] )
          v72 = (unsigned __int64)v51[16] + 1;
        else
          v72 = 0;
        v51[17] = (NotificationHandler)v72;
      }
      if ( v72 )
      {
        v73 = 0;
        if ( v71 > v72 )
        {
          v113 = 0;
          v108 = 2 * v72;
          if ( !is_mul_ok(v72, 2u) )
            goto LABEL_171;
          if ( v72 > 0x800 )
            v108 = v72 + 2048;
          if ( v71 > v108 )
            v108 = v70 + 1;
          v109 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(v51[15], 2 * v108);
          if ( !v109 )
          {
            v73 = 2147942414LL;
            goto LABEL_318;
          }
          v73 = 0;
          v51[17] = (NotificationHandler)v108;
          v51[15] = v109;
        }
      }
      else
      {
        v113 = 0;
        if ( !is_mul_ok(v71, 2u) )
        {
LABEL_171:
          v73 = 2147942934LL;
          goto LABEL_172;
        }
        v92 = (void (__stdcall *)(GUID, void *))CoTaskMemAlloc(2 * v71);
        if ( v92 )
        {
          v73 = 0;
          v51[17] = (NotificationHandler)v71;
          v51[15] = v92;
          *(_WORD *)v92 = 0;
        }
        else
        {
          v73 = 2147942414LL;
        }
        if ( (int)v73 < 0 )
          goto LABEL_318;
      }
      if ( v70 != -1 )
      {
        v93 = v51[15];
        if ( v71 > 0x7FFFFFFF )
        {
          *v93 = 0;
        }
        else
        {
          if ( v70 > 0x7FFFFFFE )
          {
            *v93 = 0;
            v51[16] = (NotificationHandler)v70;
LABEL_172:
            if ( (int)v73 >= 0 )
              goto LABEL_173;
LABEL_318:
            v57 = v73;
            v78 = 41;
            goto LABEL_183;
          }
          v94 = v70;
          do
          {
            if ( !v94 )
              break;
            v95 = *v46;
            if ( !*v46 )
              break;
            ++v46;
            *v93++ = v95;
            --v94;
            --v71;
          }
          while ( v71 );
          v96 = v93 - 1;
          if ( v71 )
            v96 = v93;
          *v96 = 0;
        }
      }
      v51[16] = (NotificationHandler)v70;
      goto LABEL_172;
    }
    v66 = -1;
    do
      ++v66;
    while ( v47[v66] );
    v67 = v66 + 1;
    if ( v66 + 1 < v66 )
      goto LABEL_161;
    v68 = (unsigned __int64)v65[2];
    if ( v68 == -1 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v65);
      if ( *v65 )
        v68 = (unsigned __int64)v65[1] + 1;
      else
        v68 = 0;
      v65[2] = (NotificationHandler)v68;
    }
    if ( v68 )
    {
      v69 = 0;
      if ( v67 > v68 )
      {
        v113 = 0;
        v106 = 2 * v68;
        if ( !is_mul_ok(v68, 2u) )
          goto LABEL_161;
        if ( v68 > 0x800 )
          v106 = v68 + 2048;
        if ( v67 > v106 )
          v106 = v66 + 1;
        v107 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(*v65, 2 * v106);
        if ( !v107 )
        {
          v69 = 2147942414LL;
          goto LABEL_315;
        }
        v69 = 0;
        v65[2] = (NotificationHandler)v106;
        *v65 = v107;
      }
    }
    else
    {
      v113 = 0;
      if ( !is_mul_ok(v67, 2u) )
      {
LABEL_161:
        v69 = 2147942934LL;
        goto LABEL_162;
      }
      v87 = (void (__stdcall *)(GUID, void *))CoTaskMemAlloc(2 * v67);
      if ( v87 )
      {
        v69 = 0;
        v65[2] = (NotificationHandler)v67;
        *v65 = v87;
        *(_WORD *)v87 = 0;
      }
      else
      {
        v69 = 2147942414LL;
      }
      if ( (int)v69 < 0 )
        goto LABEL_315;
    }
    if ( v66 != -1 )
    {
      v88 = *v65;
      if ( v67 > 0x7FFFFFFF )
      {
        *v88 = 0;
      }
      else
      {
        if ( v66 > 0x7FFFFFFE )
        {
          *v88 = 0;
          v65[1] = (NotificationHandler)v66;
LABEL_162:
          if ( (int)v69 >= 0 )
          {
            v51 = v114;
            goto LABEL_164;
          }
LABEL_315:
          v57 = v69;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x28,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationhandler.cpp",
            (const char *)v69,
            v112);
          v51 = v114;
          goto LABEL_114;
        }
        v89 = v66;
        do
        {
          if ( !v89 )
            break;
          v90 = *v47;
          if ( !*v47 )
            break;
          ++v47;
          *v88++ = v90;
          --v89;
          --v67;
        }
        while ( v67 );
        v91 = v88 - 1;
        if ( v67 )
          v91 = v88;
        *v91 = 0;
      }
    }
    v65[1] = (NotificationHandler)v66;
    goto LABEL_162;
  }
  v53 = -1;
  do
    ++v53;
  while ( v48[v53] );
  v54 = v53 + 1;
  if ( v53 + 1 < v53 )
  {
LABEL_111:
    v56 = 2147942934LL;
    goto LABEL_112;
  }
  v55 = (unsigned __int64)v50[8];
  if ( v55 == -1 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v50 + 6);
    if ( *v52 )
      v55 = v52[1] + 1LL;
    else
      v55 = 0;
    v52[2] = v55;
  }
  if ( v55 )
  {
    v56 = 0;
    if ( v54 <= v55 )
      goto LABEL_205;
    v103 = 2 * v55;
    if ( is_mul_ok(v55, 2u) )
    {
      if ( v55 > 0x800 )
        v103 = v55 + 2048;
      if ( v54 > v103 )
        v103 = v53 + 1;
      v104 = (void (__stdcall *)(GUID, void *))CoTaskMemRealloc(v114[6], 2 * v103);
      if ( v104 )
      {
        v56 = 0;
        v105 = v114;
        v114[8] = (NotificationHandler)v103;
        v52 = v105 + 6;
        v105[6] = v104;
        goto LABEL_205;
      }
      v56 = 2147942414LL;
      goto LABEL_113;
    }
    goto LABEL_111;
  }
  v119 = 0;
  if ( !is_mul_ok(v54, 2u) )
    goto LABEL_111;
  v81 = CoTaskMemAlloc(2 * v54);
  if ( v81 )
  {
    v56 = 0;
    v52[2] = v54;
    *v52 = v81;
    *v81 = 0;
  }
  else
  {
    v56 = 2147942414LL;
  }
  if ( (int)v56 < 0 )
    goto LABEL_113;
LABEL_205:
  if ( v53 == -1 )
    goto LABEL_215;
  v82 = (_WORD *)*v52;
  if ( v54 > 0x7FFFFFFF )
  {
    *v82 = 0;
    goto LABEL_215;
  }
  if ( v53 > 0x7FFFFFFE )
  {
    *v82 = 0;
    v52[1] = v53;
  }
  else
  {
    v83 = v53;
    do
    {
      if ( !v83 )
        break;
      v84 = *v48;
      if ( !*v48 )
        break;
      ++v48;
      *v82++ = v84;
      --v83;
      --v54;
    }
    while ( v54 );
    v85 = v82 - 1;
    if ( v54 )
      v85 = v82;
    *v85 = 0;
LABEL_215:
    v52[1] = v53;
  }
LABEL_112:
  if ( (int)v56 >= 0 )
  {
    v45 = v120;
    v51 = v114;
    goto LABEL_142;
  }
LABEL_113:
  v57 = v56;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\notificationhandler.cpp",
    (const char *)v56,
    v112);
  v51 = v114;
LABEL_114:
  if ( v51 )
    (*((void (__fastcall **)(NotificationHandler *))*v51 + 2))(v51);
LABEL_116:
  v39 = (__int16 *)v133;
  v42 = v117;
LABEL_117:
  if ( v57 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBA6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v57,
      v112);
  if ( v42 )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v42 + 16LL))(v42);
  v40 = (__int16 *)v137;
  v38 = (__int16 *)v139;
  v41 = v112;
LABEL_121:
  if ( *((_QWORD *)&v136 + 1) > 7u )
    std::_Deallocate<16>(v135, 2LL * *((_QWORD *)&v136 + 1) + 2);
  if ( *((_QWORD *)&v138 + 1) > 7u )
    std::_Deallocate<16>(v40, 2LL * *((_QWORD *)&v138 + 1) + 2);
  v58 = pInit;
  if ( pInit )
  {
    v121 = (_BYTE *)v118 - pInit;
    v113 = pInit;
    if ( (unsigned __int64)((_BYTE *)v118 - pInit) >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v113, &v121);
      v58 = v113;
    }
    operator delete(v58);
  }
  if ( *((_QWORD *)&v134 + 1) > 7u )
    std::_Deallocate<16>(v39, 2LL * *((_QWORD *)&v134 + 1) + 2);
  if ( *((_QWORD *)&v140 + 1) > 7u )
    std::_Deallocate<16>(v38, 2LL * *((_QWORD *)&v140 + 1) + 2);
  if ( v132.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v131, 2 * v132.m128i_i64[1] + 2);
  v132 = si128;
  LOWORD(v131) = 0;
  v59 = v115;
  if ( v115 )
  {
    v115 = 0;
    (*(void (__fastcall **)(NotificationSettings *))(*(_QWORD *)v59 + 16LL))(v59);
  }
  return v41;
}

```

## disassembly

```asm
0x180011e90  mov     [rsp-8+arg_0], rbx
0x180011e95  push    rbp
0x180011e96  push    rsi
0x180011e97  push    rdi
0x180011e98  push    r12
0x180011e9a  push    r13
0x180011e9c  push    r14
0x180011e9e  push    r15
0x180011ea0  lea     rbp, [rsp-80h]
0x180011ea5  sub     rsp, 180h
0x180011eac  movaps  [rsp+1B0h+var_40], xmm6
0x180011eb4  mov     rax, cs:__security_cookie
0x180011ebb  xor     rax, rsp
0x180011ebe  mov     [rbp+0B0h+var_50], rax
0x180011ec2  mov     [rsp+1B0h+var_148], r8
0x180011ec7  mov     r14, rdx
0x180011eca  mov     [rsp+1B0h+var_138], rdx
0x180011ecf  xor     edx, edx
0x180011ed1  mov     [r8], rdx
0x180011ed4  mov     [rsp+1B0h+var_178], rdx
0x180011ed9  xorps   xmm0, xmm0
0x180011edc  movups  [rbp+0B0h+var_F0], xmm0
0x180011ee0  xorps   xmm1, xmm1
0x180011ee3  movdqu  [rbp+0B0h+var_E0], xmm1
0x180011ee8  lea     rcx, [rbp+0B0h+var_F0]
0x180011eec  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180011ef1  nop
0x180011ef2  movups  [rbp+0B0h+var_70], xmm0
0x180011ef6  movdqu  [rbp+0B0h+var_60], xmm1
0x180011efb  lea     rcx, [rbp+0B0h+var_70]
0x180011eff  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180011f04  nop
0x180011f05  movups  [rbp+0B0h+var_D0], xmm0
0x180011f09  movdqu  [rbp+0B0h+var_C0], xmm1
0x180011f0e  lea     rcx, [rbp+0B0h+var_D0]
0x180011f12  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180011f17  nop
0x180011f18  mov     [rsp+1B0h+var_188], rdx
0x180011f1d  lea     rcx, [rbp+0B0h+Block]
0x180011f21  call    ??$?0AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>(std::allocator<std::pair<ulong const,std::shared_ptr<TileSession>>> const &)
0x180011f26  nop
0x180011f27  movups  [rbp+0B0h+var_90], xmm0
0x180011f2b  movdqu  [rbp+0B0h+var_80], xmm1
0x180011f30  lea     rcx, [rbp+0B0h+var_90]
0x180011f34  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180011f39  nop
0x180011f3a  movups  [rbp+0B0h+var_B0], xmm0
0x180011f3e  movdqu  [rbp+0B0h+var_A0], xmm1
0x180011f43  lea     rcx, [rbp+0B0h+var_B0]
0x180011f47  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180011f4c  nop
0x180011f4d  mov     r12d, 1
0x180011f53  mov     byte ptr [rsp+1B0h+var_190], dl; int
0x180011f57  mov     r15d, edx
0x180011f5a  mov     dword ptr [rsp+1B0h+var_180], edx
0x180011f5e  mov     r13d, 8007000Eh
0x180011f64  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180011f6c  mov     rdi, [rbp+0B0h+var_118]
0x180011f70  mov     [rsp+1B0h+var_160], rdi
0x180011f75  mov     rdx, [rbp+0B0h+var_120]
0x180011f79  mov     [rsp+1B0h+var_150], rdx
0x180011f7e  mov     rsi, [rbp+0B0h+Block]
0x180011f82  mov     [rsp+1B0h+pInit], rsi
0x180011f87  nop     word ptr [rax+rax+00000000h]
0x180011f90  mov     rcx, [r14]; struct sqlite3_stmt *
0x180011f93  mov     rax, [rbp+0B8h]
0x180011f9a  test    rcx, rcx
0x180011f9d  jz      loc_180012458
0x180011fa3  call    ?dal_step@Statement@@SAJPEAUsqlite3_stmt@@@Z; Statement::dal_step(sqlite3_stmt *)
0x180011fa8  cmp     eax, 87AF0064h
0x180011fad  jnz     loc_180012849
0x180011fb3  cmp     r12d, 1
0x180011fb7  jnz     loc_1800123B8
0x180011fbd  mov     byte ptr [rsp+1B0h+var_190], r12b; int
0x180011fc2  mov     edx, 9
0x180011fc7  mov     rcx, [r14]
0x180011fca  call    cs:__imp_sqlite3_column_int
0x180011fd0  mov     r12d, eax
0x180011fd3  mov     dword ptr [rsp+1B0h+var_168], eax
0x180011fd7  xor     r8d, r8d
0x180011fda  lea     rdx, [rbp+0B0h+var_110]
0x180011fde  mov     rcx, r14
0x180011fe1  call    ?GetColumnText16@Statement@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Statement::GetColumnText16(int)
0x180011fe6  mov     rbx, rax
0x180011fe9  lea     rax, [rbp+0B0h+var_F0]
0x180011fed  cmp     rax, rbx
0x180011ff0  jz      loc_180013192
0x180011ff6  mov     rdx, qword ptr [rbp+0B0h+var_E0+8]
0x180011ffa  cmp     rdx, 7
0x180011ffe  jbe     short loc_180012011
0x180012000  lea     rdx, ds:2[rdx*2]
0x180012008  mov     rcx, qword ptr [rbp+0B0h+var_F0]
0x18001200c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012011  movdqu  [rbp+0B0h+var_E0], xmm6
0x180012016  xor     r15d, r15d
0x180012019  mov     word ptr [rbp+0B0h+var_F0], r15w
0x18001201e  movups  xmm0, xmmword ptr [rbx]
0x180012021  movups  [rbp+0B0h+var_F0], xmm0
0x180012025  movups  xmm1, xmmword ptr [rbx+10h]
0x180012029  movups  [rbp+0B0h+var_E0], xmm1
0x18001202d  mov     [rbx+10h], r15
0x180012031  mov     qword ptr [rbx+18h], 7
0x180012039  mov     [rbx], r15w
0x18001203d  mov     rdx, [rbp+0B0h+var_F8]
0x180012041  cmp     rdx, 7
0x180012045  ja      loc_180012488
0x18001204b  mov     r8d, 1
0x180012051  lea     rdx, [rbp+0B0h+var_110]
0x180012055  mov     rcx, r14
0x180012058  call    ?GetColumnText16@Statement@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Statement::GetColumnText16(int)
0x18001205d  mov     rbx, rax
0x180012060  lea     rax, [rbp+0B0h+var_70]
0x180012064  cmp     rax, rbx
0x180012067  jz      short loc_1800120A3
0x180012069  mov     rdx, qword ptr [rbp+0B0h+var_60+8]
0x18001206d  cmp     rdx, 7
0x180012071  jbe     short loc_180012084
0x180012073  lea     rdx, ds:2[rdx*2]
0x18001207b  mov     rcx, qword ptr [rbp+0B0h+var_70]
0x18001207f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012084  movups  xmm0, xmmword ptr [rbx]
0x180012087  movups  [rbp+0B0h+var_70], xmm0
0x18001208b  movups  xmm1, xmmword ptr [rbx+10h]
0x18001208f  movups  [rbp+0B0h+var_60], xmm1
0x180012093  mov     [rbx+10h], r15
0x180012097  mov     qword ptr [rbx+18h], 7
0x18001209f  mov     [rbx], r15w
0x1800120a3  mov     rdx, [rbp+0B0h+var_F8]
0x1800120a7  cmp     rdx, 7
0x1800120ab  ja      loc_18001249E
0x1800120b1  mov     r8d, 2
0x1800120b7  lea     rdx, [rbp+0B0h+var_110]
0x1800120bb  mov     rcx, r14
0x1800120be  call    ?GetColumnText16@Statement@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Statement::GetColumnText16(int)
0x1800120c3  mov     rbx, rax
0x1800120c6  lea     rax, [rbp+0B0h+var_D0]
0x1800120ca  cmp     rax, rbx
0x1800120cd  jz      short loc_180012109
0x1800120cf  mov     rdx, qword ptr [rbp+0B0h+var_C0+8]
0x1800120d3  cmp     rdx, 7
0x1800120d7  jbe     short loc_1800120EA
0x1800120d9  lea     rdx, ds:2[rdx*2]
0x1800120e1  mov     rcx, qword ptr [rbp+0B0h+var_D0]
0x1800120e5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800120ea  movups  xmm0, xmmword ptr [rbx]
0x1800120ed  movups  [rbp+0B0h+var_D0], xmm0
0x1800120f1  movups  xmm1, xmmword ptr [rbx+10h]
0x1800120f5  movups  [rbp+0B0h+var_C0], xmm1
0x1800120f9  mov     [rbx+10h], r15
0x1800120fd  mov     qword ptr [rbx+18h], 7
0x180012105  mov     [rbx], r15w
0x180012109  mov     rdx, [rbp+0B0h+var_F8]
0x18001210d  cmp     rdx, 7
0x180012111  ja      loc_1800124B4
0x180012117  mov     edx, 3
0x18001211c  mov     rcx, [r14]
0x18001211f  call    cs:__imp_sqlite3_column_int64
0x180012125  mov     [rsp+1B0h+var_188], rax
0x18001212a  mov     r8d, 4
0x180012130  lea     rdx, [rbp+0B0h+var_110]
0x180012134  mov     rcx, r14
0x180012137  call    ?GetColumnBlob@Statement@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@H@Z; Statement::GetColumnBlob(int)
0x18001213c  mov     rbx, rax
0x18001213f  lea     rax, [rbp+0B0h+Block]
0x180012143  cmp     rax, rbx
0x180012146  jz      short loc_1800121A3
0x180012148  test    rsi, rsi
0x18001214b  jz      short loc_180012172
0x18001214d  sub     rdi, rsi
0x180012150  mov     [rsp+1B0h+pInit], rdi
0x180012155  mov     [rsp+1B0h+var_160], rsi
0x18001215a  cmp     rdi, 1000h
0x180012161  jnb     loc_18001319A
0x180012167  mov     rdx, rdi
0x18001216a  mov     rcx, rsi; Block
0x18001216d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012172  mov     rax, [rbx]
0x180012175  mov     [rsp+1B0h+pInit], rax
0x18001217a  mov     [rbp+0B0h+Block], rax
0x18001217e  mov     rdi, [rbx+8]
0x180012182  mov     [rsp+1B0h+var_150], rdi
0x180012187  mov     [rbp+0B0h+var_120], rdi
0x18001218b  mov     rax, [rbx+10h]
0x18001218f  mov     [rsp+1B0h+var_160], rax
0x180012194  mov     [rbp+0B0h+var_118], rax
0x180012198  mov     [rbx], r15
0x18001219b  mov     [rbx+8], r15
0x18001219f  mov     [rbx+10h], r15
0x1800121a3  mov     rcx, [rbp+0B0h+var_110]; Block
0x1800121a7  test    rcx, rcx
0x1800121aa  jz      short loc_1800121CF
0x1800121ac  mov     rdx, [rbp+0B0h+var_100]
0x1800121b0  sub     rdx, rcx
0x1800121b3  mov     [rsp+1B0h+var_158], rdx
0x1800121b8  mov     [rsp+1B0h+var_140], rcx
0x1800121bd  cmp     rdx, 1000h
0x1800121c4  jnb     loc_1800131B8
0x1800121ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800121cf  mov     r8d, 5
0x1800121d5  lea     rdx, [rbp+0B0h+var_110]
0x1800121d9  mov     rcx, r14
0x1800121dc  call    ?GetColumnText16@Statement@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Statement::GetColumnText16(int)
0x1800121e1  mov     rbx, rax
0x1800121e4  lea     rax, [rbp+0B0h+var_90]
0x1800121e8  cmp     rax, rbx
0x1800121eb  jz      short loc_180012227
0x1800121ed  mov     rdx, qword ptr [rbp+0B0h+var_80+8]
0x1800121f1  cmp     rdx, 7
0x1800121f5  jbe     short loc_180012208
0x1800121f7  lea     rdx, ds:2[rdx*2]
0x1800121ff  mov     rcx, qword ptr [rbp+0B0h+var_90]
0x180012203  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012208  movups  xmm0, xmmword ptr [rbx]
0x18001220b  movups  [rbp+0B0h+var_90], xmm0
0x18001220f  movups  xmm1, xmmword ptr [rbx+10h]
0x180012213  movups  [rbp+0B0h+var_80], xmm1
0x180012217  mov     [rbx+10h], r15
0x18001221b  mov     qword ptr [rbx+18h], 7
0x180012223  mov     [rbx], r15w
0x180012227  mov     rdx, [rbp+0B0h+var_F8]
0x18001222b  cmp     rdx, 7
0x18001222f  ja      loc_1800124CA
0x180012235  mov     r8d, 6
0x18001223b  lea     rdx, [rbp+0B0h+var_110]
0x18001223f  mov     rcx, r14
0x180012242  call    ?GetColumnText16@Statement@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; Statement::GetColumnText16(int)
0x180012247  mov     rbx, rax
0x18001224a  lea     rax, [rbp+0B0h+var_B0]
0x18001224e  cmp     rax, rbx
0x180012251  jz      short loc_18001228D
0x180012253  mov     rdx, qword ptr [rbp+0B0h+var_A0+8]
0x180012257  cmp     rdx, 7
0x18001225b  jbe     short loc_18001226E
0x18001225d  lea     rdx, ds:2[rdx*2]
0x180012265  mov     rcx, qword ptr [rbp+0B0h+var_B0]
0x180012269  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001226e  movups  xmm0, xmmword ptr [rbx]
0x180012271  movups  [rbp+0B0h+var_B0], xmm0
0x180012275  movups  xmm1, xmmword ptr [rbx+10h]
0x180012279  movups  [rbp+0B0h+var_A0], xmm1
0x18001227d  mov     [rbx+10h], r15
0x180012281  mov     qword ptr [rbx+18h], 7
0x180012289  mov     [rbx], r15w
0x18001228d  mov     rdx, [rbp+0B0h+var_F8]
0x180012291  cmp     rdx, 7
0x180012295  ja      loc_1800124E0
0x18001229b  lea     rbx, [rbp+0B0h+var_F0]
0x18001229f  cmp     qword ptr [rbp+0B0h+var_E0+8], 7
0x1800122a4  cmova   rbx, qword ptr [rbp+0B0h+var_F0]
0x1800122a9  mov     rcx, [rsp+1B0h+var_178]
0x1800122ae  test    rcx, rcx
0x1800122b1  jz      short loc_1800122C5
0x1800122b3  mov     [rsp+1B0h+var_178], r15
0x1800122b8  mov     rax, [rcx]
0x1800122bb  mov     rax, [rax+10h]
0x1800122bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122c4  nop
0x1800122c5  mov     [rsp+1B0h+var_178], r15
0x1800122ca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800122d1  mov     ecx, 90h; unsigned __int64
0x1800122d6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800122db  mov     [rsp+1B0h+var_158], rax
0x1800122e0  mov     [rsp+1B0h+var_140], rax
0x1800122e5  test    rax, rax
0x1800122e8  jz      loc_18001259A
0x1800122ee  mov     [rbp+0B0h+var_130], rax
0x1800122f2  mov     rcx, rax; this
0x1800122f5  call    ??0NotificationSettings@@QEAA@XZ; NotificationSettings::NotificationSettings(void)
0x1800122fa  mov     r13, rax
0x1800122fd  mov     [rsp+1B0h+var_158], r15
0x180012302  test    rbx, rbx
0x180012305  jz      loc_180012EC0
0x18001230b  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180012312  inc     r14
0x180012315  cmp     word ptr [rbx+r14*2], 0
0x18001231b  jnz     short loc_180012312
0x18001231d  lea     rdi, [r14+1]
0x180012321  cmp     rdi, r14
0x180012324  jb      short loc_180012352
0x180012326  mov     r8, [rax+40h]
0x18001232a  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001232e  jz      loc_180012B46
0x180012334  test    r8, r8
0x180012337  jnz     loc_180012A90
0x18001233d  mov     [rbp+0B0h+var_130], r15
0x180012341  mov     eax, 2
0x180012346  mul     rdi
0x180012349  test    rdx, rdx
0x18001234c  jz      loc_18001250B
0x180012352  mov     r15d, 80070216h
0x180012358  test    r15d, r15d
0x18001235b  jns     loc_180012B0D
0x180012361  mov     rcx, [rbp+0B8h]; this
0x180012368  mov     r9d, r15d; char *
0x18001236b  lea     r8, aOnecoreuapBase_151; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180012372  mov     edx, 10h; void *
0x180012377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001237c  nop
0x18001237d  test    r13, r13
0x180012380  jz      short loc_180012393
  ... truncated ...
```
