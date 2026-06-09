# ESEWriteRecordPropData(TableHandleInfo *,UnifiedStoreCursorLocation &,utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>> &,utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>> &,utl::vector<ulong,utl::allocator<ulong>> const &,ulong,ulong *)

- ea: `0x18002b4b0`
- end: `0x18002bcf6`
- name: `?ESEWriteRecordPropData@@YAJPEAUTableHandleInfo@@AEAVUnifiedStoreCursorLocation@@AEAV?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@utl@@@utl@@2AEBV?$vector@KV?$allocator@K@utl@@@4@KPEAK@Z`
- size: `2118`
- prototype: `__int64 __usercall@<rax>(struct TableHandleInfo *@<rcx>, UnifiedStoreCursorLocation *this@<rdx>, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ac20`
- `0x180096ef0`

## callees

- `0x1800029e0`
- `0x1800068f0`
- `0x18000ab20`
- `0x18000f530`
- `0x180011ed0`
- `0x18001a180`
- `0x18001cba0`
- `0x18001d98c`
- `0x18002b4b0`
- `0x180050bb0`
- `0x18006f180`
- `0x1800740f8`
- `0x1800c5092`
- `0x1800c50aa`
- `0x1800c50f0`

## import_xrefs

- `ESENT!JetSetColumns` at `0x18002b5a7`
- `ESENT!JetSetColumns` at `0x18002b5a7`
- `ESENT!JetEscrowUpdate` at `0x18002b757`
- `ESENT!JetEscrowUpdate` at `0x18002b757`
- `ESENT!JetPrepareUpdate` at `0x18002b554`
- `ESENT!JetPrepareUpdate` at `0x18002b79a`
- `ESENT!JetPrepareUpdate` at `0x18002b9a0`
- `ESENT!JetPrepareUpdate` at `0x18002bb75`
- `ESENT!JetPrepareUpdate` at `0x18002bbb3`
- `ESENT!JetPrepareUpdate` at `0x18002bc1b`
- `ESENT!JetPrepareUpdate` at `0x18002bc86`
- `ESENT!JetPrepareUpdate` at `0x18002bcc6`
- `ESENT!JetPrepareUpdate` at `0x18002b554`
- `ESENT!JetPrepareUpdate` at `0x18002b79a`
- `ESENT!JetPrepareUpdate` at `0x18002b9a0`
- `ESENT!JetPrepareUpdate` at `0x18002bb75`
- `ESENT!JetPrepareUpdate` at `0x18002bbb3`
- `ESENT!JetPrepareUpdate` at `0x18002bc1b`
- `ESENT!JetPrepareUpdate` at `0x18002bc86`
- `ESENT!JetPrepareUpdate` at `0x18002bcc6`
- `ESENT!JetUpdate` at `0x18002b5fc`
- `ESENT!JetUpdate` at `0x18002b847`
- `ESENT!JetUpdate` at `0x18002b5fc`
- `ESENT!JetUpdate` at `0x18002b847`

## string_xrefs

- `0x18002b6aa`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002b6fc`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002b772`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002b7f4`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002b96e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002ba52`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002ba84`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002bade`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002bb0d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002bb34`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002bb4d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18002ba35`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`
- `0x18002b7b1`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x18002b7d0`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x18002b9d0`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x18002bb8c`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x18002bbca`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x18002bc32`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x18002bc9d`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x18002bcdd`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall ESEWriteRecordPropData(
        struct TableHandleInfo *a1,
        void **this,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        unsigned int a6,
        void *a7)
{
  bool v7; // zf
  JET_SESID v10; // rbp
  JET_TABLEID v12; // r12
  int v14; // eax
  unsigned int v15; // edi
  __int64 v16; // rax
  _QWORD *v17; // r15
  __int64 v18; // rcx
  JET_ERR v19; // eax
  int v20; // ebp
  int v21; // r12d
  JET_SETCOLUMN *v22; // r8
  unsigned __int64 v23; // r9
  JET_SESID v24; // r12
  JET_ERR v25; // eax
  unsigned int i; // esi
  _DWORD *v27; // r13
  unsigned int j; // esi
  int v29; // r12d
  unsigned int HresultFromJetError; // eax
  __int64 v32; // r9
  unsigned int v33; // ebx
  JET_ERR v34; // eax
  unsigned int v35; // eax
  __int64 v36; // r9
  JET_TABLEID v37; // rdx
  JET_SESID v38; // rcx
  JET_ERR v39; // eax
  unsigned int v40; // eax
  JET_ERR v41; // eax
  __int64 v42; // rcx
  unsigned int IdProp; // eax
  ColumnIdMappings *v44; // rcx
  int v45; // eax
  int v46; // eax
  int v47; // eax
  __int64 v48; // rdx
  unsigned int v49; // eax
  int v50; // eax
  unsigned int v51; // esi
  JET_ERR v52; // eax
  __int64 v53; // rdx
  __int64 v54; // r9
  __int64 v55; // r9
  __int64 v56; // rdx
  __int64 v57; // rcx
  JET_ERR v58; // eax
  unsigned int v59; // eax
  JET_ERR v60; // eax
  unsigned int v61; // eax
  JET_ERR v62; // eax
  unsigned int v63; // eax
  JET_ERR v64; // eax
  unsigned int v65; // eax
  JET_ERR v66; // eax
  unsigned int v67; // eax
  struct JET_RETINFO *pcbOldActual; // [rsp+38h] [rbp-4B0h]
  JET_TABLEID tableid; // [rsp+50h] [rbp-498h]
  unsigned int pcbActual; // [rsp+58h] [rbp-490h] BYREF
  int v71; // [rsp+5Ch] [rbp-48Ch] BYREF
  JET_SESID sesid; // [rsp+60h] [rbp-488h]
  unsigned int v73; // [rsp+68h] [rbp-480h]
  size_t Size; // [rsp+70h] [rbp-478h] BYREF
  int v75; // [rsp+78h] [rbp-470h]
  void *v76; // [rsp+80h] [rbp-468h]
  _QWORD *v77; // [rsp+88h] [rbp-460h]
  _BYTE pvBookmark[1008]; // [rsp+A0h] [rbp-448h] BYREF

  v7 = *(_DWORD *)this == 0;
  v10 = *((_QWORD *)a1 + 1);
  v12 = *((_QWORD *)a1 + 2);
  v76 = a7;
  v77 = a5;
  sesid = v10;
  tableid = v12;
  if ( v7 )
  {
    v52 = JetPrepareUpdate(v10, v12, 0);
    v15 = 0;
    if ( v52 )
    {
      v20 = 0;
      if ( v52 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v52);
        v32 = 1487;
        goto LABEL_28;
      }
    }
    else
    {
      v20 = 1;
    }
    v18 = 1;
    v17 = a3 + 1;
    pcbActual = 1;
    v21 = 1;
  }
  else
  {
    v14 = UnistoreJetGotoBookmarkEx(a1, (const struct UnifiedStoreCursorLocation *)this, 0);
    v15 = v14;
    if ( v14 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v14,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        859);
      Log_UnistoreHREvent_0(
        v15,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        1492);
      return v15;
    }
    v16 = a3[1];
    v17 = a3 + 1;
    v15 = 0;
    v18 = 0;
    pcbActual = 0;
    if ( *a3 != v16 )
    {
      v19 = JetPrepareUpdate(v10, v12, 2u);
      if ( !v19 )
      {
        v20 = 1;
LABEL_6:
        v21 = 1;
        v18 = 0;
        goto LABEL_7;
      }
      v20 = 0;
      if ( v19 >= 0 )
        goto LABEL_6;
      HresultFromJetError = MakeHresultFromJetError(v19);
      v32 = 1496;
LABEL_28:
      v33 = HresultFromJetError;
      Log_UnistoreHREvent_0(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        v32);
      return v33;
    }
    v20 = 0;
    v21 = 0;
  }
LABEL_7:
  v22 = (JET_SETCOLUMN *)*a3;
  if ( *a3 != *v17 )
  {
    v23 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*v17 - (_QWORD)v22) >> 3);
    if ( v23 > 0xFFFFFFFF )
    {
      Log_UnistoreHREvent_0(
        2147942934LL,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        1505);
      if ( v20 )
      {
        v58 = JetPrepareUpdate(sesid, tableid, 3u);
        if ( v58 < 0 )
        {
          v59 = MakeHresultFromJetError(v58);
          Log_UnistoreHREvent_0(
            v59,
            0,
            "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
            577);
        }
      }
      return 2147942934LL;
    }
    v71 = JetSetColumns(sesid, tableid, v22, v23);
    CheckCorruption(v71);
    if ( v71 < 0 )
    {
      v33 = MakeHresultFromJetError(v71);
      Log_UnistoreHREvent_0(
        v33,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        1506);
      if ( v20 )
      {
        v37 = tableid;
        v38 = sesid;
LABEL_39:
        v39 = JetPrepareUpdate(v38, v37, 3u);
        if ( v39 < 0 )
        {
          v40 = MakeHresultFromJetError(v39);
          Log_UnistoreHREvent_0(
            v40,
            0,
            "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
            577);
        }
        return v33;
      }
      return v33;
    }
    v18 = pcbActual;
  }
  if ( !(_DWORD)v18 )
  {
    if ( v21 )
    {
      if ( !v20 )
        Log_AssertionEvent(v18, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h", 561);
      v24 = sesid;
      v25 = JetUpdate(sesid, tableid, 0, 0, 0);
      if ( !v25 )
      {
        v20 = 0;
        goto LABEL_17;
      }
      if ( v25 < 0 )
      {
        v33 = MakeHresultFromJetError(v25);
        Log_UnistoreHREvent_0(
          v33,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
          1542);
        if ( v20 )
        {
          v37 = tableid;
          goto LABEL_38;
        }
        return v33;
      }
    }
    else
    {
      v24 = sesid;
    }
LABEL_17:
    for ( i = 0; i < 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a4[1] - *a4) >> 3); ++i )
    {
      v34 = JetEscrowUpdate(
              *((_QWORD *)a1 + 1),
              *((_QWORD *)a1 + 2),
              *(_DWORD *)(*a4 + 40LL * i),
              *(void **)(*a4 + 40LL * i + 8),
              *(_DWORD *)(*a4 + 40LL * i + 16),
              0,
              0,
              0,
              1u);
      if ( v34 < 0 )
      {
        v35 = MakeHresultFromJetError(v34);
        v36 = 1556;
        goto LABEL_36;
      }
    }
    v27 = v76;
    if ( v76 )
      memset_0(v76, 0, 4LL * a6);
    for ( j = 0; j < 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*v17 - *a3) >> 3); ++j )
    {
      v29 = MakeHresultFromJetError(*(_DWORD *)(*a3 + 40LL * j + 32));
      if ( v27 )
      {
        v53 = *(unsigned int *)(*v77 + 4LL * j);
        if ( (int)v27[v53] >= 0 )
          v27[v53] = v29;
      }
      if ( v29 < 0 && (v15 & 0x80000000) == 0 )
      {
        v15 = v29;
        if ( !v27 )
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v29,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
            1583);
          if ( v20 )
          {
            v64 = JetPrepareUpdate(sesid, tableid, 3u);
            if ( v64 < 0 )
            {
              v65 = MakeHresultFromJetError(v64);
              Log_UnistoreHREvent_0(
                v65,
                0,
                "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
                577);
            }
          }
          return (unsigned int)v29;
        }
      }
    }
    if ( v20 )
    {
      v66 = JetPrepareUpdate(sesid, tableid, 3u);
      if ( v66 < 0 )
      {
        v67 = MakeHresultFromJetError(v66);
        Log_UnistoreHREvent_0(
          v67,
          0,
          "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
          577);
      }
    }
    return v15;
  }
  pcbActual = 0;
  if ( !v20 )
    Log_AssertionEvent(v18, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h", 561);
  v24 = sesid;
  v41 = JetUpdate(sesid, tableid, pvBookmark, 0x3E9u, &pcbActual);
  if ( v41 )
  {
    if ( v41 < 0 )
    {
      v35 = MakeHresultFromJetError(v41);
      v36 = 1513;
      goto LABEL_36;
    }
  }
  else
  {
    v20 = 0;
  }
  v42 = *(unsigned int *)a1;
  Size = 0;
  v75 = 0;
  IdProp = GetIdProp(v42);
  v45 = ColumnIdMappings::PropIdToColumnId(v44, a1, IdProp, (struct ColumnDetails *)&Size);
  v73 = v45;
  if ( v45 >= 0 )
  {
    v46 = CommsESE_JetGotoBookmark(v24, tableid, pvBookmark, pcbActual);
    if ( v46 >= 0 )
    {
      v71 = 0;
      v47 = CommsESE_JetRetrieveColumn(v24, tableid, Size, &v71, 4u, 0, 1u, pcbOldActual);
      if ( v47 < 0 )
      {
        v51 = MakeHresultFromJetError(v47);
        v55 = 1533;
        v56 = 0;
        v57 = v51;
      }
      else
      {
        v48 = pcbActual;
        Size = pcbActual;
        v73 = v71;
        *(_DWORD *)this = 0;
        if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::_Resize<,0>(this + 1, v48) )
        {
          if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::_Resize<,0>(this + 4, 0) )
          {
            memcpy_0(this[1], pvBookmark, Size);
            v49 = v73;
            *((_DWORD *)this + 1) = v73;
            if ( v49 != -1 )
              *(_DWORD *)this = 1;
            Size = (size_t)a1 + 24;
            v50 = UnifiedStoreCursorLocation::CopyTo(
                    (UnifiedStoreCursorLocation *)this,
                    (struct TableHandleInfo *)((char *)a1 + 24),
                    1);
            v51 = v50;
            if ( v50 >= 0 )
              goto LABEL_17;
            Log_UnistoreHREvent_0(
              (unsigned int)v50,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
              1536);
            *(_DWORD *)Size = 0;
            goto LABEL_57;
          }
          v54 = 445;
        }
        else
        {
          v54 = 444;
        }
        v51 = -2147024882;
        Log_UnistoreHREvent_0(
          2147942414LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
          v54);
        v55 = 1535;
        v56 = 1;
        v57 = 2147942414LL;
      }
      Log_UnistoreHREvent_0(
        v57,
        v56,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        v55);
      *((_DWORD *)a1 + 6) = 0;
LABEL_57:
      if ( v20 )
      {
        v62 = JetPrepareUpdate(v24, tableid, 3u);
        if ( v62 < 0 )
        {
          v63 = MakeHresultFromJetError(v62);
          Log_UnistoreHREvent_0(
            v63,
            0,
            "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
            577);
        }
      }
      return v51;
    }
    v35 = MakeHresultFromJetError(v46);
    v36 = 1518;
LABEL_36:
    v33 = v35;
    Log_UnistoreHREvent_0(
      v35,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      v36);
    if ( v20 )
    {
      v37 = tableid;
LABEL_38:
      v38 = v24;
      goto LABEL_39;
    }
    return v33;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)v45,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
    1516);
  if ( v20 )
  {
    v60 = JetPrepareUpdate(v24, tableid, 3u);
    if ( v60 < 0 )
    {
      v61 = MakeHresultFromJetError(v60);
      Log_UnistoreHREvent_0(
        v61,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
        577);
    }
  }
  return v73;
}

```

## disassembly

```asm
0x18002b4b0  push    rbx
0x18002b4b2  push    rbp
0x18002b4b3  push    rsi
0x18002b4b4  push    rdi
0x18002b4b5  push    r12
0x18002b4b7  push    r13
0x18002b4b9  push    r14
0x18002b4bb  push    r15
0x18002b4bd  sub     rsp, 4A8h
0x18002b4c4  mov     rax, cs:__security_cookie
0x18002b4cb  xor     rax, rsp
0x18002b4ce  mov     [rsp+4E8h+var_58], rax
0x18002b4d6  cmp     dword ptr [rdx], 0
0x18002b4d9  mov     r13, r9
0x18002b4dc  mov     rax, [rsp+4E8h+arg_30]
0x18002b4e4  mov     r14, r8
0x18002b4e7  mov     rbp, [rcx+8]
0x18002b4eb  mov     rsi, rdx
0x18002b4ee  mov     r12, [rcx+10h]
0x18002b4f2  mov     rbx, rcx
0x18002b4f5  mov     [rsp+4E8h+var_468], rax
0x18002b4fd  mov     rax, [rsp+4E8h+arg_20]
0x18002b505  mov     [rsp+4E8h+var_460], rax
0x18002b50d  mov     [rsp+4E8h+sesid], rbp
0x18002b512  mov     [rsp+4E8h+tableid], r12
0x18002b517  jz      loc_18002B997
0x18002b51d  xor     r8d, r8d; int *
0x18002b520  call    ?UnistoreJetGotoBookmarkEx@@YAJPEAUTableHandleInfo@@AEBVUnifiedStoreCursorLocation@@PEAH@Z; UnistoreJetGotoBookmarkEx(TableHandleInfo *,UnifiedStoreCursorLocation const &,int *)
0x18002b525  mov     edi, eax
0x18002b527  test    eax, eax
0x18002b529  js      loc_18002BB2E
0x18002b52f  mov     rax, [r14+8]
0x18002b533  lea     r15, [r14+8]
0x18002b537  xor     edi, edi
0x18002b539  mov     ecx, edi
0x18002b53b  mov     [rsp+4E8h+var_490], ecx
0x18002b53f  cmp     [r14], rax
0x18002b542  jz      loc_18002B6E2
0x18002b548  mov     r8d, 2; prep
0x18002b54e  mov     rdx, r12; tableid
0x18002b551  mov     rcx, rbp; sesid
0x18002b554  call    cs:__imp_JetPrepareUpdate
0x18002b55a  test    eax, eax
0x18002b55c  jnz     loc_18002BAA8
0x18002b562  mov     ebp, 1
0x18002b567  mov     r12d, 1
0x18002b56d  mov     ecx, edi
0x18002b56f  mov     r8, [r14]; psetcolumn
0x18002b572  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002b57c  mov     r9, [r15]
0x18002b57f  mov     edx, 0FFFFFFFFh
0x18002b584  cmp     r8, r9
0x18002b587  jz      short loc_18002B5C8
0x18002b589  sub     r9, r8
0x18002b58c  sar     r9, 3
0x18002b590  imul    r9, rax; csetcolumn
0x18002b594  cmp     r9, rdx
0x18002b597  ja      loc_18002B6F6
0x18002b59d  mov     rdx, [rsp+4E8h+tableid]; tableid
0x18002b5a2  mov     rcx, [rsp+4E8h+sesid]; sesid
0x18002b5a7  call    cs:__imp_JetSetColumns
0x18002b5ad  mov     ecx, eax; int
0x18002b5af  mov     [rsp+4E8h+var_48C], eax
0x18002b5b3  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x18002b5b8  mov     ecx, [rsp+4E8h+var_48C]; int
0x18002b5bc  test    ecx, ecx
0x18002b5be  js      loc_18002BAD3
0x18002b5c4  mov     ecx, [rsp+4E8h+var_490]
0x18002b5c8  test    ecx, ecx
0x18002b5ca  jnz     loc_18002B816
0x18002b5d0  test    r12d, r12d
0x18002b5d3  jz      loc_18002B6EC
0x18002b5d9  test    ebp, ebp
0x18002b5db  jz      loc_18002B7CA
0x18002b5e1  mov     rsi, [rsp+4E8h+tableid]
0x18002b5e6  xor     r9d, r9d; cbBookmark
0x18002b5e9  mov     r12, [rsp+4E8h+sesid]
0x18002b5ee  mov     rdx, rsi; tableid
0x18002b5f1  mov     rcx, r12; sesid
0x18002b5f4  mov     [rsp+4E8h+pcbActual], rdi; pcbActual
0x18002b5f9  xor     r8d, r8d; pvBookmark
0x18002b5fc  call    cs:__imp_JetUpdate
0x18002b602  test    eax, eax
0x18002b604  jnz     loc_18002B7E1
0x18002b60a  mov     ebp, edi
0x18002b60c  mov     esi, edi
0x18002b60e  mov     rdx, [r13+0]
0x18002b612  mov     r8, 0CCCCCCCCCCCCCCCDh
0x18002b61c  mov     rax, [r13+8]
0x18002b620  sub     rax, rdx
0x18002b623  mov     ecx, esi
0x18002b625  sar     rax, 3
0x18002b629  imul    rax, r8
0x18002b62d  cmp     rcx, rax
0x18002b630  jb      loc_18002B721
0x18002b636  mov     r13, [rsp+4E8h+var_468]
0x18002b63e  test    r13, r13
0x18002b641  jnz     loc_18002BA05
0x18002b647  mov     esi, edi
0x18002b649  mov     rdx, [r14]
0x18002b64c  mov     rax, [r15]
0x18002b64f  sub     rax, rdx
0x18002b652  mov     ebx, esi
0x18002b654  sar     rax, 3
0x18002b658  imul    rax, r8
0x18002b65c  cmp     rbx, rax
0x18002b65f  jnb     short loc_18002B691
0x18002b661  lea     rcx, [rbx+rbx*4]
0x18002b665  mov     ecx, [rdx+rcx*8+20h]; int
0x18002b669  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18002b66e  mov     r12d, eax
0x18002b671  test    r13, r13
0x18002b674  jnz     loc_18002B9E1
0x18002b67a  test    r12d, r12d
0x18002b67d  js      loc_18002BC5D
0x18002b683  inc     esi
0x18002b685  mov     r8, 0CCCCCCCCCCCCCCCDh
0x18002b68f  jmp     short loc_18002B649
0x18002b691  test    ebp, ebp
0x18002b693  jnz     loc_18002BCB6
0x18002b699  mov     eax, edi
0x18002b69b  jmp     short loc_18002B6BE
0x18002b69d  mov     ecx, eax; int
0x18002b69f  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18002b6a4  mov     r9d, 5D8h
0x18002b6aa  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002b6b1  xor     edx, edx
0x18002b6b3  mov     ecx, eax
0x18002b6b5  mov     ebx, eax
0x18002b6b7  call    Log_UnistoreHREvent_0
0x18002b6bc  mov     eax, ebx
0x18002b6be  mov     rcx, [rsp+4E8h+var_58]
0x18002b6c6  xor     rcx, rsp; StackCookie
0x18002b6c9  call    __security_check_cookie
0x18002b6ce  add     rsp, 4A8h
0x18002b6d5  pop     r15
0x18002b6d7  pop     r14
0x18002b6d9  pop     r13
0x18002b6db  pop     r12
0x18002b6dd  pop     rdi
0x18002b6de  pop     rsi
0x18002b6df  pop     rbp
0x18002b6e0  pop     rbx
0x18002b6e1  retn
0x18002b6e2  mov     ebp, edi
0x18002b6e4  mov     r12d, edi
0x18002b6e7  jmp     loc_18002B56F
0x18002b6ec  mov     r12, [rsp+4E8h+sesid]
0x18002b6f1  jmp     loc_18002B60C
0x18002b6f6  mov     r9d, 5E1h
0x18002b6fc  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002b703  mov     edx, 1
0x18002b708  mov     ecx, 80070216h
0x18002b70d  call    Log_UnistoreHREvent_0
0x18002b712  test    ebp, ebp
0x18002b714  jnz     loc_18002BB65
0x18002b71a  mov     eax, 80070216h
0x18002b71f  jmp     short loc_18002B6BE
0x18002b721  lea     rax, [rcx+rcx*4]
0x18002b725  mov     [rsp+4E8h+grbit], 1; grbit
0x18002b72d  mov     r9, [rdx+rax*8+8]; pv
0x18002b732  lea     r8, [rdx+rax*8]
0x18002b736  mov     eax, [rdx+rax*8+10h]
0x18002b73a  mov     r8d, [r8]; columnid
0x18002b73d  mov     rdx, [rbx+10h]; tableid
0x18002b741  mov     rcx, [rbx+8]; sesid
0x18002b745  mov     [rsp+4E8h+pcbOldActual], rdi; pcbOldActual
0x18002b74a  mov     [rsp+4E8h+cbOldMax], edi; cbOldMax
0x18002b74e  mov     [rsp+4E8h+pvOld], rdi; pvOld
0x18002b753  mov     dword ptr [rsp+4E8h+pcbActual], eax; cbMax
0x18002b757  call    cs:__imp_JetEscrowUpdate
0x18002b75d  test    eax, eax
0x18002b75f  jns     loc_18002BC56
0x18002b765  mov     ecx, eax; int
0x18002b767  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18002b76c  mov     r9d, 614h
0x18002b772  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002b779  xor     edx, edx
0x18002b77b  mov     ecx, eax
0x18002b77d  mov     ebx, eax
0x18002b77f  call    Log_UnistoreHREvent_0
0x18002b784  test    ebp, ebp
0x18002b786  jz      loc_18002B6BC
0x18002b78c  mov     rdx, [rsp+4E8h+tableid]; tableid
0x18002b791  mov     rcx, r12; sesid
0x18002b794  mov     r8d, 3; prep
0x18002b79a  call    cs:__imp_JetPrepareUpdate
0x18002b7a0  test    eax, eax
0x18002b7a2  jns     loc_18002B6BC
0x18002b7a8  mov     ecx, eax; int
0x18002b7aa  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18002b7af  mov     ecx, eax
0x18002b7b1  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x18002b7b8  mov     r9d, 241h
0x18002b7be  xor     edx, edx
0x18002b7c0  call    Log_UnistoreHREvent_0
0x18002b7c5  jmp     loc_18002B6BC
0x18002b7ca  mov     r8d, 231h
0x18002b7d0  lea     rdx, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x18002b7d7  call    Log_AssertionEvent
0x18002b7dc  jmp     loc_18002B5E1
0x18002b7e1  jns     loc_18002B60C
0x18002b7e7  mov     ecx, eax; int
0x18002b7e9  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18002b7ee  mov     r9d, 606h
0x18002b7f4  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002b7fb  xor     edx, edx
0x18002b7fd  mov     ecx, eax
0x18002b7ff  mov     ebx, eax
0x18002b801  call    Log_UnistoreHREvent_0
0x18002b806  test    ebp, ebp
0x18002b808  jz      loc_18002B6BC
0x18002b80e  mov     rdx, rsi
0x18002b811  jmp     loc_18002B791
0x18002b816  mov     [rsp+4E8h+var_490], edi
0x18002b81a  test    ebp, ebp
0x18002b81c  jz      loc_18002B9CA
0x18002b822  mov     r12, [rsp+4E8h+sesid]
0x18002b827  lea     rax, [rsp+4E8h+var_490]
0x18002b82c  mov     rdx, [rsp+4E8h+tableid]; tableid
0x18002b831  lea     r8, [rsp+4E8h+pvBookmark]; pvBookmark
0x18002b839  mov     rcx, r12; sesid
0x18002b83c  mov     [rsp+4E8h+pcbActual], rax; pcbActual
0x18002b841  mov     r9d, 3E9h; cbBookmark
0x18002b847  call    cs:__imp_JetUpdate
0x18002b84d  test    eax, eax
0x18002b84f  jnz     loc_18002BA66
0x18002b855  mov     ebp, edi
0x18002b857  mov     ecx, [rbx]
0x18002b859  xor     eax, eax
0x18002b85b  mov     [rsp+4E8h+Size], rax
0x18002b860  mov     [rsp+4E8h+var_470], eax
0x18002b864  call    ?GetIdProp@@YAKW4US_TABLEID@@@Z; GetIdProp(US_TABLEID)
0x18002b869  mov     r8d, eax; unsigned int
0x18002b86c  lea     r9, [rsp+4E8h+Size]; struct ColumnDetails *
0x18002b871  mov     rdx, rbx; struct TableHandleInfo *
0x18002b874  call    ?PropIdToColumnId@ColumnIdMappings@@QEAAJQEAUTableHandleInfo@@KPEAUColumnDetails@@@Z; ColumnIdMappings::PropIdToColumnId(TableHandleInfo * const,ulong,ColumnDetails *)
0x18002b879  mov     [rsp+4E8h+var_480], eax
0x18002b87d  test    eax, eax
0x18002b87f  js      loc_18002BA7E
0x18002b885  mov     r9d, [rsp+4E8h+var_490]; unsigned int
0x18002b88a  lea     r8, [rsp+4E8h+pvBookmark]; void *
0x18002b892  mov     rdx, [rsp+4E8h+tableid]; unsigned __int64
0x18002b897  mov     rcx, r12; unsigned __int64
0x18002b89a  call    ?CommsESE_JetGotoBookmark@@YAJ_K0PEAXK@Z; CommsESE_JetGotoBookmark(unsigned __int64,unsigned __int64,void *,ulong)
0x18002b89f  test    eax, eax
0x18002b8a1  js      loc_18002BBE3
0x18002b8a7  mov     r8d, dword ptr [rsp+4E8h+Size]; unsigned int
0x18002b8ac  lea     r9, [rsp+4E8h+var_48C]; void *
0x18002b8b1  mov     rdx, [rsp+4E8h+tableid]; unsigned __int64
0x18002b8b6  mov     rcx, r12; unsigned __int64
0x18002b8b9  mov     [rsp+4E8h+cbOldMax], 1; JET_GRBIT
0x18002b8c1  mov     [rsp+4E8h+pvOld], rdi; unsigned int *
0x18002b8c6  mov     dword ptr [rsp+4E8h+pcbActual], 4; unsigned int
0x18002b8ce  mov     [rsp+4E8h+var_48C], edi
0x18002b8d2  call    ?CommsESE_JetRetrieveColumn@@YAJ_K0KPEAXKPEAKKPEAUJET_RETINFO@@@Z; CommsESE_JetRetrieveColumn(unsigned __int64,unsigned __int64,ulong,void *,ulong,ulong *,ulong,JET_RETINFO *)
0x18002b8d7  test    eax, eax
0x18002b8d9  js      loc_18002BBF5
0x18002b8df  mov     ecx, [rsp+4E8h+var_490]
0x18002b8e3  mov     eax, [rsp+4E8h+var_48C]
0x18002b8e7  mov     edx, ecx
0x18002b8e9  mov     [rsp+4E8h+Size], rcx
0x18002b8ee  lea     rcx, [rsi+8]
0x18002b8f2  mov     [rsp+4E8h+var_480], eax
0x18002b8f6  mov     [rsi], edi
0x18002b8f8  call    ??$_Resize@$$V$0A@@?$vector@EV?$allocator@E@utl@@@utl@@AEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::_Resize<,0>(unsigned __int64)
0x18002b8fd  test    al, al
0x18002b8ff  jz      loc_18002BA2A
0x18002b905  lea     rcx, [rsi+20h]
0x18002b909  xor     edx, edx
0x18002b90b  call    ??$_Resize@$$V$0A@@?$vector@EV?$allocator@E@utl@@@utl@@AEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::_Resize<,0>(unsigned __int64)
0x18002b910  test    al, al
0x18002b912  jz      loc_18002BC4B
0x18002b918  mov     r8, [rsp+4E8h+Size]; Size
0x18002b91d  lea     rdx, [rsp+4E8h+pvBookmark]; Src
0x18002b925  mov     rcx, [rsi+8]; void *
0x18002b929  call    memcpy_0
0x18002b92e  mov     eax, [rsp+4E8h+var_480]
0x18002b932  mov     ecx, 0FFFFFFFFh
0x18002b937  mov     [rsi+4], eax
0x18002b93a  cmp     eax, ecx
0x18002b93c  jz      short loc_18002B944
0x18002b93e  mov     dword ptr [rsi], 1
0x18002b944  lea     rax, [rbx+18h]
0x18002b948  mov     r8d, 1; int
0x18002b94e  mov     rdx, rax; struct UnifiedStoreCursorLocation *
0x18002b951  mov     [rsp+4E8h+Size], rax
0x18002b956  mov     rcx, rsi; this
0x18002b959  call    ?CopyTo@UnifiedStoreCursorLocation@@QEBAJAEAV1@H@Z; UnifiedStoreCursorLocation::CopyTo(UnifiedStoreCursorLocation &,int)
0x18002b95e  mov     esi, eax
0x18002b960  test    eax, eax
0x18002b962  jns     loc_18002B60C
0x18002b968  mov     r9d, 600h
0x18002b96e  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002b975  mov     edx, 1
0x18002b97a  mov     ecx, eax
0x18002b97c  call    Log_UnistoreHREvent_0
0x18002b981  mov     rax, [rsp+4E8h+Size]
0x18002b986  mov     [rax], edi
0x18002b988  test    ebp, ebp
  ... truncated ...
```
