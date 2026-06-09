# DBVolume::_UpdatePrimaryIdTableFromKey(void)

- ea: `0x180019584`
- end: `0x180019c35`
- name: `?_UpdatePrimaryIdTableFromKey@DBVolume@@IEAAJXZ`
- size: `1713`
- prototype: `__int64 __fastcall(DBVolume *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001a834`

## callees

- `0x180003420`
- `0x180003518`
- `0x1800068f0`
- `0x18000866c`
- `0x1800086bc`
- `0x180008ff0`
- `0x18000f530`
- `0x180010ea0`
- `0x180013524`
- `0x180013618`
- `0x180019584`
- `0x180019c3c`
- `0x18001a180`
- `0x18001a2c0`
- `0x18001cba0`
- `0x18001d98c`
- `0x180058298`
- `0x18005a018`
- `0x18006f180`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019715`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180019715`
- `ESENT!JetRollback` at `0x1800199d0`
- `ESENT!JetRollback` at `0x180019a6b`
- `ESENT!JetRollback` at `0x1800199d0`
- `ESENT!JetRollback` at `0x180019a6b`
- `ESENT!JetCommitTransaction2` at `0x1800198e9`
- `ESENT!JetCommitTransaction2` at `0x180019932`
- `ESENT!JetCommitTransaction2` at `0x1800198e9`
- `ESENT!JetCommitTransaction2` at `0x180019932`
- `ESENT!JetBeginTransaction2` at `0x180019676`
- `ESENT!JetBeginTransaction2` at `0x180019676`
- `ESENT!JetPrepareUpdate` at `0x180019ac7`
- `ESENT!JetPrepareUpdate` at `0x180019b2e`
- `ESENT!JetPrepareUpdate` at `0x180019bbe`
- `ESENT!JetPrepareUpdate` at `0x180019ac7`
- `ESENT!JetPrepareUpdate` at `0x180019b2e`
- `ESENT!JetPrepareUpdate` at `0x180019bbe`

## string_xrefs

- `0x1800195f5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180019895`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180019976`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180019a4d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180019b04`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180019b81`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180019bfc`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180019911`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x18001999a`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x1800199ae`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x1800199eb`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x180019a03`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x180019a82`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x180019ade`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x180019b49`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x180019bd5`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall DBVolume::_UpdatePrimaryIdTableFromKey(HKEY *this)
{
  int TableHandle; // eax
  ColumnIdMappings *v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // r9
  int v7; // r14d
  int v8; // r15d
  JET_SESID v9; // rbx
  JET_ERR v10; // eax
  JET_COLUMNID v11; // r12d
  unsigned int v12; // r8d
  __int64 i; // rcx
  int v14; // ecx
  unsigned int v15; // r8d
  int v16; // eax
  int DwordPropFromTableCursor; // esi
  HKEY v18; // rcx
  LSTATUS ValueW; // eax
  bool v20; // sf
  int Key; // eax
  int v22; // eax
  __int64 v23; // r9
  int v24; // eax
  __int64 v25; // rcx
  int v26; // edi
  int v27; // ebx
  unsigned int HresultFromJetError; // eax
  __int64 v29; // r9
  const char *v30; // r8
  JET_ERR v31; // eax
  unsigned int v32; // eax
  __int64 v33; // r9
  JET_ERR v34; // eax
  unsigned int v35; // eax
  JET_ERR v36; // eax
  unsigned int v37; // eax
  JET_ERR v38; // eax
  JET_ERR v39; // eax
  __int64 v40; // rcx
  const char *v41; // r8
  __int64 v42; // r9
  __int64 v43; // rdx
  unsigned int v44; // [rsp+40h] [rbp-99h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-95h] BYREF
  JET_SESID v46; // [rsp+48h] [rbp-91h] BYREF
  __int64 v47; // [rsp+50h] [rbp-89h]
  DWORD pvData; // [rsp+58h] [rbp-81h] BYREF
  JET_SESID sesid; // [rsp+60h] [rbp-79h] BYREF
  JET_TABLEID tableid; // [rsp+68h] [rbp-71h]
  int v51; // [rsp+70h] [rbp-69h]
  struct TableHandleInfo *v52[2]; // [rsp+78h] [rbp-61h] BYREF
  int v53; // [rsp+88h] [rbp-51h] BYREF
  _QWORD v54[2]; // [rsp+90h] [rbp-49h] BYREF
  JET_SETCOLUMN v55; // [rsp+A0h] [rbp-39h] BYREF
  WCHAR Value[16]; // [rsp+C8h] [rbp-11h] BYREF

  v54[0] = 0;
  sesid = 0;
  LODWORD(tableid) = 0;
  v54[1] = 0;
  *(_OWORD *)v52 = 0;
  TableHandle = GetTableHandle(53, 0, this, v54, v52);
  v4 = TableHandle;
  if ( TableHandle < 0 )
  {
    v5 = 3906;
LABEL_3:
    Log_UnistoreHREvent_0(
      (unsigned int)TableHandle,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v5);
    goto LABEL_4;
  }
  TableHandle = ColumnIdMappings::PropIdToColumnId(v3, v52[0], 0x10A90003u, (struct ColumnDetails *)&sesid);
  v4 = TableHandle;
  if ( TableHandle < 0 )
  {
    v5 = 3907;
    goto LABEL_3;
  }
  v7 = 0;
  v47 = 0;
  v8 = 0;
  v9 = *((_QWORD *)v52[0] + 1);
  v46 = v9;
  v10 = JetBeginTransaction2(v9, 0);
  if ( v10 )
  {
    if ( v10 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v10);
      v29 = 3911;
      goto LABEL_46;
    }
  }
  else
  {
    v7 = 1;
    LODWORD(v47) = 1;
  }
  v11 = sesid;
  v12 = 0;
  for ( i = 0; ; i = v12 )
  {
    v44 = v12;
    if ( (unsigned int)i >= 0x36 )
    {
      if ( !v7 )
        Log_AssertionEvent(i, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h", 463);
      if ( v9 == -1 )
        Log_AssertionEvent(i, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h", 464);
      v24 = JetCommitTransaction2(v9, 0, 0, 0);
      v26 = v24;
      if ( v24 )
      {
        auto_JET_TRANSACTION::Rollback((auto_JET_TRANSACTION *)&v46);
        if ( v26 < 0 )
        {
          HresultFromJetError = MakeHresultFromJetError(v26);
          v29 = 3993;
          goto LABEL_46;
        }
        v8 = HIDWORD(v47);
        v24 = v47;
        v9 = v46;
      }
      else
      {
        LODWORD(v47) = 0;
      }
      if ( v24 )
      {
        if ( v8 )
        {
          if ( v9 == -1 )
            Log_AssertionEvent(
              v25,
              "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
              464);
          v27 = JetCommitTransaction2(v9, 0, 0, 0);
          if ( !v27 )
            goto LABEL_44;
          auto_JET_TRANSACTION::Rollback((auto_JET_TRANSACTION *)&v46);
          if ( v27 >= 0 )
            goto LABEL_44;
          v32 = MakeHresultFromJetError(v27);
          v33 = 431;
          goto LABEL_52;
        }
        v31 = JetRollback(v9, 0);
        if ( v31 < 0 )
        {
          v32 = MakeHresultFromJetError(v31);
          v33 = 435;
LABEL_52:
          Log_UnistoreHREvent_0(
            v32,
            0,
            "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
            v33);
        }
      }
LABEL_44:
      auto_TableHandle::~auto_TableHandle((auto_TableHandle *)v52);
      auto_DBSession::~auto_DBSession((auto_DBSession *)v54);
      return 0;
    }
    if ( ((unsigned int)GetIdProp(i) != 17170435 || !v14) && v14 != 6 )
    {
      pvData = 0;
      v16 = StringCchPrintfW(Value, 0x10u, L"%d", v15);
      DwordPropFromTableCursor = v16;
      if ( v16 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v16,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          3930);
        if ( v7 )
        {
          v34 = JetRollback(v9, 0);
          if ( v34 < 0 )
          {
            v35 = MakeHresultFromJetError(v34);
            Log_UnistoreHREvent_0(
              v35,
              0,
              "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
              435);
          }
        }
        goto LABEL_31;
      }
      v18 = this[31];
      pcbData = 4;
      ValueW = RegGetValueW(v18, 0, Value, 0x20000018u, 0, &pvData, &pcbData);
      v20 = ValueW < 0;
      if ( ValueW > 0 )
        v20 = 1;
      if ( v20 )
        goto LABEL_16;
      Key = CommsESE_JetMakeKey(*((_QWORD *)v52[0] + 1), *((_QWORD *)v52[0] + 2), &v44, 4u, 0x101u);
      if ( Key < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(Key);
        v29 = 3944;
LABEL_46:
        v30 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp";
        v4 = HresultFromJetError;
LABEL_47:
        Log_UnistoreHREvent_0(HresultFromJetError, 0, v30, v29);
LABEL_48:
        auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v46);
        goto LABEL_4;
      }
      DwordPropFromTableCursor = UnistoreJetSeek(v52[0], 1u);
      if ( DwordPropFromTableCursor != -2147024871 )
      {
        if ( DwordPropFromTableCursor < 0 )
        {
          v42 = 3955;
        }
        else
        {
          DwordPropFromTableCursor = UnifiedStoreCursorLocation::CopyTo(
                                       (struct TableHandleInfo *)((char *)v52[0] + 24),
                                       (struct UnifiedStoreCursorLocation *)&this[8 * (unsigned __int64)v44 + 33],
                                       0);
          if ( DwordPropFromTableCursor < 0 )
          {
            v42 = 3957;
          }
          else
          {
            v53 = 0;
            pcbData = 0;
            DwordPropFromTableCursor = GetDwordPropFromTableCursor(v52[0], 279511043, &v53, &pcbData);
            if ( DwordPropFromTableCursor >= 0 )
            {
              if ( pvData > pcbData && pvData - pcbData <= 0x7D0 )
              {
                memset(&v55, 0, sizeof(v55));
                v51 = 0;
                sesid = *((_QWORD *)v52[0] + 1);
                tableid = *((_QWORD *)v52[0] + 2);
                DwordPropFromTableCursor = auto_JET_PREPARE::Prepare((auto_JET_PREPARE *)&sesid, 2u);
                if ( DwordPropFromTableCursor < 0 )
                {
                  v23 = 3972;
                  goto LABEL_29;
                }
                v55.columnid = v11;
                v55.itagSequence = 1;
                v55.pvData = &pvData;
                v55.cbData = 4;
                v22 = CommsESE_JetSetColumns(*((_QWORD *)v52[0] + 1), *((_QWORD *)v52[0] + 2), &v55, 1u);
                if ( v22 < 0 )
                {
                  v4 = MakeHresultFromJetError(v22);
                  Log_UnistoreHREvent_0(
                    v4,
                    0,
                    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                    3983);
                  if ( v51 )
                  {
                    v38 = JetPrepareUpdate(sesid, tableid, 3u);
                    if ( v38 < 0 )
                    {
                      HresultFromJetError = MakeHresultFromJetError(v38);
                      v29 = 577;
                      v30 = "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h";
                      goto LABEL_47;
                    }
                  }
                  goto LABEL_48;
                }
                DwordPropFromTableCursor = auto_JET_PREPARE::Update((auto_JET_PREPARE *)&sesid, 0, 0, 0);
                if ( DwordPropFromTableCursor < 0 )
                {
                  v23 = 3985;
LABEL_29:
                  Log_UnistoreHREvent_0(
                    (unsigned int)DwordPropFromTableCursor,
                    1,
                    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
                    v23);
                  if ( v51 )
                  {
                    v39 = JetPrepareUpdate(sesid, tableid, 3u);
                    if ( v39 < 0 )
                    {
                      v40 = (unsigned int)MakeHresultFromJetError(v39);
                      v41 = "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h";
                      v42 = 577;
                      v43 = 0;
                      goto LABEL_77;
                    }
                  }
                  goto LABEL_30;
                }
                LODWORD(this[8 * v44 + 32]) = pvData;
                if ( v51 )
                {
                  v36 = JetPrepareUpdate(sesid, tableid, 3u);
                  if ( v36 < 0 )
                  {
                    v37 = MakeHresultFromJetError(v36);
                    Log_UnistoreHREvent_0(
                      v37,
                      0,
                      "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
                      577);
                  }
                }
              }
LABEL_16:
              v15 = v44;
              goto LABEL_17;
            }
            v42 = 3961;
          }
        }
        v41 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp";
        v43 = 1;
        v40 = (unsigned int)DwordPropFromTableCursor;
LABEL_77:
        Log_UnistoreHREvent_0(v40, v43, v41, v42);
LABEL_30:
        auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v46);
LABEL_31:
        v4 = DwordPropFromTableCursor;
        goto LABEL_4;
      }
      v15 = v44;
      if ( v44 )
        break;
    }
LABEL_17:
    v12 = v15 + 1;
  }
  Log_UnistoreHREvent_0(
    2147942425LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
    3949);
  auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v46);
  v4 = -2147024871;
LABEL_4:
  auto_TableHandle::~auto_TableHandle((auto_TableHandle *)v52);
  auto_DBSession::~auto_DBSession((auto_DBSession *)v54);
  return v4;
}

```

## disassembly

```asm
0x180019584  push    rbp
0x180019586  push    rbx
0x180019587  push    rsi
0x180019588  push    rdi
0x180019589  push    r12
0x18001958b  push    r13
0x18001958d  push    r14
0x18001958f  push    r15
0x180019591  lea     rbp, [rsp-1Fh]
0x180019596  sub     rsp, 0F8h
0x18001959d  mov     rax, cs:__security_cookie
0x1800195a4  xor     rax, rsp
0x1800195a7  mov     [rbp+57h+var_48], rax
0x1800195ab  xor     eax, eax
0x1800195ad  mov     [rbp+57h+var_A0], 0
0x1800195b5  xor     edx, edx
0x1800195b7  mov     [rbp+57h+sesid], rax
0x1800195bb  mov     dword ptr [rbp+57h+tableid], eax
0x1800195be  lea     r9, [rbp+57h+var_A0]
0x1800195c2  mov     r13, rcx
0x1800195c5  mov     [rbp+57h+var_98], 0
0x1800195cd  xorps   xmm0, xmm0
0x1800195d0  lea     rax, [rbp+57h+var_B8]
0x1800195d4  mov     r8, rcx
0x1800195d7  mov     [rsp+130h+pdwType], rax
0x1800195dc  lea     ecx, [rdx+35h]
0x1800195df  movdqu  xmmword ptr [rbp+57h+var_B8], xmm0
0x1800195e4  call    ?GetTableHandle@@YAJW4US_TABLEID@@KPEAVIDBVolume@@AEAVauto_DBSession@@AEAVauto_TableHandle@@@Z; GetTableHandle(US_TABLEID,ulong,IDBVolume *,auto_DBSession &,auto_TableHandle &)
0x1800195e9  mov     ebx, eax
0x1800195eb  test    eax, eax
0x1800195ed  jns     short loc_18001963C
0x1800195ef  mov     r9d, 0F42h
0x1800195f5  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800195fc  mov     edx, 1
0x180019601  mov     ecx, eax
0x180019603  call    Log_UnistoreHREvent_0
0x180019608  lea     rcx, [rbp+57h+var_B8]; this
0x18001960c  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x180019611  lea     rcx, [rbp+57h+var_A0]; this
0x180019615  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x18001961a  mov     eax, ebx
0x18001961c  mov     rcx, [rbp+57h+var_48]
0x180019620  xor     rcx, rsp; StackCookie
0x180019623  call    __security_check_cookie
0x180019628  add     rsp, 0F8h
0x18001962f  pop     r15
0x180019631  pop     r14
0x180019633  pop     r13
0x180019635  pop     r12
0x180019637  pop     rdi
0x180019638  pop     rsi
0x180019639  pop     rbx
0x18001963a  pop     rbp
0x18001963b  retn
0x18001963c  mov     rdx, [rbp+57h+var_B8]; struct TableHandleInfo *
0x180019640  lea     r9, [rbp+57h+sesid]; struct ColumnDetails *
0x180019644  mov     r8d, 10A90003h; unsigned int
0x18001964a  call    ?PropIdToColumnId@ColumnIdMappings@@QEAAJQEAUTableHandleInfo@@KPEAUColumnDetails@@@Z; ColumnIdMappings::PropIdToColumnId(TableHandleInfo * const,ulong,ColumnDetails *)
0x18001964f  mov     ebx, eax
0x180019651  test    eax, eax
0x180019653  js      loc_180019B55
0x180019659  mov     rax, [rbp+57h+var_B8]
0x18001965d  xor     r14d, r14d
0x180019660  xor     edx, edx; grbit
0x180019662  mov     [rsp+130h+var_E0], r14
0x180019667  xor     r15d, r15d
0x18001966a  mov     rbx, [rax+8]
0x18001966e  mov     rcx, rbx; sesid
0x180019671  mov     [rsp+130h+var_E8], rbx
0x180019676  call    cs:__imp_JetBeginTransaction2
0x18001967c  lea     edi, [r14+1]
0x180019680  test    eax, eax
0x180019682  jz      loc_1800199BF
0x180019688  js      loc_180019969
0x18001968e  mov     r12d, dword ptr [rbp+57h+sesid]
0x180019692  xor     r8d, r8d
0x180019695  xor     ecx, ecx
0x180019697  mov     [rsp+130h+var_F0], r8d
0x18001969c  cmp     ecx, 36h ; '6'
0x18001969f  jnb     loc_1800198C0
0x1800196a5  call    ?GetIdProp@@YAKW4US_TABLEID@@@Z; GetIdProp(US_TABLEID)
0x1800196aa  cmp     eax, 1060003h
0x1800196af  jz      loc_180019B60
0x1800196b5  cmp     ecx, 6
0x1800196b8  jz      short loc_180019730
0x1800196ba  mov     r9d, r8d
0x1800196bd  mov     [rsp+130h+var_D8], r15d
0x1800196c2  lea     r8, aD; "%d"
0x1800196c9  mov     edx, 10h; unsigned __int64
0x1800196ce  lea     rcx, [rbp+57h+Value]; unsigned __int16 *
0x1800196d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800196d7  mov     esi, eax
0x1800196d9  test    eax, eax
0x1800196db  js      loc_180019A47
0x1800196e1  mov     rcx, [r13+0F8h]; hkey
0x1800196e8  lea     rax, [rsp+130h+var_EC]
0x1800196ed  mov     [rsp+130h+pcbData], rax; pcbData
0x1800196f2  lea     r8, [rbp+57h+Value]; lpValue
0x1800196f6  lea     rax, [rsp+130h+var_D8]
0x1800196fb  mov     [rsp+130h+var_EC], 4
0x180019703  mov     [rsp+130h+pvData], rax; pvData
0x180019708  mov     r9d, 20000018h; dwFlags
0x18001970e  xor     edx, edx; lpSubKey
0x180019710  mov     [rsp+130h+pdwType], r15; pdwType
0x180019715  call    cs:__imp_RegGetValueW
0x18001971b  test    eax, eax
0x18001971d  jle     short loc_180019729
0x18001971f  movzx   eax, ax
0x180019722  or      eax, 80070000h
0x180019727  test    eax, eax
0x180019729  jns     short loc_18001973B
0x18001972b  mov     r8d, [rsp+130h+var_F0]
0x180019730  add     r8d, edi
0x180019733  mov     ecx, r8d
0x180019736  jmp     loc_180019697
0x18001973b  mov     rcx, [rbp+57h+var_B8]
0x18001973f  lea     r8, [rsp+130h+var_F0]; void *
0x180019744  mov     r9d, 4; unsigned int
0x18001974a  mov     dword ptr [rsp+130h+pdwType], 101h; JET_GRBIT
0x180019752  mov     rdx, [rcx+10h]; unsigned __int64
0x180019756  mov     rcx, [rcx+8]; unsigned __int64
0x18001975a  call    ?CommsESE_JetMakeKey@@YAJ_K0PEBXKK@Z; CommsESE_JetMakeKey(unsigned __int64,unsigned __int64,void const *,ulong,ulong)
0x18001975f  test    eax, eax
0x180019761  js      loc_180019C11
0x180019767  mov     rcx, [rbp+57h+var_B8]; struct TableHandleInfo *
0x18001976b  mov     edx, edi; unsigned int
0x18001976d  call    ?UnistoreJetSeek@@YAJPEAUTableHandleInfo@@K@Z; UnistoreJetSeek(TableHandleInfo *,ulong)
0x180019772  mov     esi, eax
0x180019774  mov     eax, 80070019h
0x180019779  cmp     esi, eax
0x18001977b  jz      loc_180019B6D
0x180019781  test    esi, esi
0x180019783  js      loc_180019BF6
0x180019789  mov     edx, [rsp+130h+var_F0]
0x18001978d  xor     r8d, r8d; int
0x180019790  mov     rcx, [rbp+57h+var_B8]
0x180019794  shl     rdx, 6
0x180019798  add     rcx, 18h; this
0x18001979c  add     rdx, 108h
0x1800197a3  add     rdx, r13; struct UnifiedStoreCursorLocation *
0x1800197a6  call    ?CopyTo@UnifiedStoreCursorLocation@@QEBAJAEAV1@H@Z; UnifiedStoreCursorLocation::CopyTo(UnifiedStoreCursorLocation &,int)
0x1800197ab  mov     esi, eax
0x1800197ad  test    eax, eax
0x1800197af  js      loc_180019BEE
0x1800197b5  mov     rcx, [rbp+57h+var_B8]
0x1800197b9  lea     r9, [rsp+130h+var_EC]
0x1800197be  lea     r8, [rbp+57h+var_A8]
0x1800197c2  mov     [rbp+57h+var_A8], r15d
0x1800197c6  mov     edx, 10A90003h
0x1800197cb  mov     [rsp+130h+var_EC], r15d
0x1800197d0  call    GetDwordPropFromTableCursor
0x1800197d5  mov     esi, eax
0x1800197d7  test    eax, eax
0x1800197d9  js      loc_180019BE6
0x1800197df  mov     eax, [rsp+130h+var_D8]
0x1800197e3  cmp     eax, [rsp+130h+var_EC]
0x1800197e7  jbe     loc_18001972B
0x1800197ed  sub     eax, [rsp+130h+var_EC]
0x1800197f1  cmp     eax, 7D0h
0x1800197f6  ja      loc_18001972B
0x1800197fc  mov     rcx, [rbp+57h+var_B8]
0x180019800  xor     eax, eax
0x180019802  xorps   xmm0, xmm0
0x180019805  mov     qword ptr [rbp+57h+var_90.err], rax
0x180019809  movups  xmmword ptr [rbp+57h+var_90.columnid], xmm0
0x18001980d  mov     edx, 2; unsigned int
0x180019812  mov     [rbp+57h+var_C0], r15d
0x180019816  movups  xmmword ptr [rbp+57h+var_90.cbData], xmm0
0x18001981a  mov     rax, [rcx+8]
0x18001981e  mov     [rbp+57h+sesid], rax
0x180019822  mov     rax, [rcx+10h]
0x180019826  lea     rcx, [rbp+57h+sesid]; this
0x18001982a  mov     [rbp+57h+tableid], rax
0x18001982e  call    ?Prepare@auto_JET_PREPARE@@QEAAJK@Z; auto_JET_PREPARE::Prepare(ulong)
0x180019833  mov     esi, eax
0x180019835  test    eax, eax
0x180019837  js      loc_180019BA5
0x18001983d  mov     rcx, [rbp+57h+var_B8]
0x180019841  lea     rax, [rsp+130h+var_D8]
0x180019846  mov     [rbp+57h+var_90.columnid], r12d
0x18001984a  lea     r8, [rbp+57h+var_90]; struct JET_SETCOLUMN *
0x18001984e  mov     [rbp+57h+var_90.itagSequence], edi
0x180019851  mov     r9d, edi; unsigned int
0x180019854  mov     [rbp+57h+var_90.pvData], rax
0x180019858  mov     [rbp+57h+var_90.cbData], 4
0x18001985f  mov     rdx, [rcx+10h]; unsigned __int64
0x180019863  mov     rcx, [rcx+8]; unsigned __int64
0x180019867  call    ?CommsESE_JetSetColumns@@YAJ_K0PEAUJET_SETCOLUMN@@K@Z; CommsESE_JetSetColumns(unsigned __int64,unsigned __int64,JET_SETCOLUMN *,ulong)
0x18001986c  test    eax, eax
0x18001986e  js      loc_180019AF7
0x180019874  xor     r9d, r9d; unsigned int *
0x180019877  lea     rcx, [rbp+57h+sesid]; this
0x18001987b  xor     r8d, r8d; unsigned int
0x18001987e  xor     edx, edx; void *
0x180019880  call    ?Update@auto_JET_PREPARE@@QEAAJPEAXKPEAK@Z; auto_JET_PREPARE::Update(void *,ulong,ulong *)
0x180019885  mov     esi, eax
0x180019887  test    eax, eax
0x180019889  jns     loc_180019A9B
0x18001988f  mov     r9d, 0F91h
0x180019895  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001989c  mov     edx, edi
0x18001989e  mov     ecx, esi
0x1800198a0  call    Log_UnistoreHREvent_0
0x1800198a5  cmp     [rbp+57h+var_C0], r15d
0x1800198a9  jnz     loc_180019BB0
0x1800198af  lea     rcx, [rsp+130h+var_E8]; this
0x1800198b4  call    ??1auto_JET_TRANSACTION@@QEAA@XZ; auto_JET_TRANSACTION::~auto_JET_TRANSACTION(void)
0x1800198b9  mov     ebx, esi
0x1800198bb  jmp     loc_180019608
0x1800198c0  mov     esi, 1CFh
0x1800198c5  test    r14d, r14d
0x1800198c8  jz      loc_180019997
0x1800198ce  mov     r14d, 1D0h
0x1800198d4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800198d8  jz      loc_1800199AB
0x1800198de  xor     r9d, r9d
0x1800198e1  xor     r8d, r8d
0x1800198e4  xor     edx, edx
0x1800198e6  mov     rcx, rbx
0x1800198e9  call    cs:__imp_JetCommitTransaction2
0x1800198ef  mov     edi, eax
0x1800198f1  test    eax, eax
0x1800198f3  jnz     loc_180019A14
0x1800198f9  mov     dword ptr [rsp+130h+var_E0], eax
0x1800198fd  test    eax, eax
0x1800198ff  jz      short loc_180019950
0x180019901  test    r15d, r15d
0x180019904  jz      loc_1800199CB
0x18001990a  test    eax, eax
0x18001990c  jnz     short loc_18001991D
0x18001990e  mov     r8d, esi
0x180019911  lea     rdx, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180019918  call    Log_AssertionEvent
0x18001991d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180019921  jz      loc_180019A00
0x180019927  xor     r9d, r9d
0x18001992a  xor     r8d, r8d
0x18001992d  xor     edx, edx
0x18001992f  mov     rcx, rbx
0x180019932  call    cs:__imp_JetCommitTransaction2
0x180019938  mov     ebx, eax
0x18001993a  test    eax, eax
0x18001993c  jz      short loc_180019950
0x18001993e  lea     rcx, [rsp+130h+var_E8]; this
0x180019943  call    ?Rollback@auto_JET_TRANSACTION@@QEAAXXZ; auto_JET_TRANSACTION::Rollback(void)
0x180019948  test    ebx, ebx
0x18001994a  js      loc_180019C23
0x180019950  lea     rcx, [rbp+57h+var_B8]; this
0x180019954  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x180019959  lea     rcx, [rbp+57h+var_A0]; this
0x18001995d  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x180019962  xor     eax, eax
0x180019964  jmp     loc_18001961C
0x180019969  mov     ecx, eax; int
0x18001996b  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180019970  mov     r9d, 0F47h
0x180019976  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001997d  mov     ebx, eax
0x18001997f  xor     edx, edx
0x180019981  mov     ecx, eax
0x180019983  call    Log_UnistoreHREvent_0
0x180019988  lea     rcx, [rsp+130h+var_E8]; this
0x18001998d  call    ??1auto_JET_TRANSACTION@@QEAA@XZ; auto_JET_TRANSACTION::~auto_JET_TRANSACTION(void)
0x180019992  jmp     loc_180019608
0x180019997  mov     r8d, esi
0x18001999a  lea     rdx, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800199a1  call    Log_AssertionEvent
0x1800199a6  jmp     loc_1800198CE
0x1800199ab  mov     r8d, r14d
0x1800199ae  lea     rdx, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800199b5  call    Log_AssertionEvent
0x1800199ba  jmp     loc_1800198DE
0x1800199bf  mov     r14d, edi
0x1800199c2  mov     dword ptr [rsp+130h+var_E0], edi
0x1800199c6  jmp     loc_18001968E
0x1800199cb  xor     edx, edx; grbit
0x1800199cd  mov     rcx, rbx; sesid
0x1800199d0  call    cs:__imp_JetRollback
0x1800199d6  test    eax, eax
0x1800199d8  jns     loc_180019950
0x1800199de  mov     ecx, eax; int
0x1800199e0  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800199e5  mov     r9d, 1B3h
0x1800199eb  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800199f2  xor     edx, edx
0x1800199f4  mov     ecx, eax
0x1800199f6  call    Log_UnistoreHREvent_0
0x1800199fb  jmp     loc_180019950
0x180019a00  mov     r8d, r14d
0x180019a03  lea     rdx, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180019a0a  call    Log_AssertionEvent
0x180019a0f  jmp     loc_180019927
0x180019a14  lea     rcx, [rsp+130h+var_E8]; this
0x180019a19  call    ?Rollback@auto_JET_TRANSACTION@@QEAAXXZ; auto_JET_TRANSACTION::Rollback(void)
0x180019a1e  test    edi, edi
0x180019a20  js      short loc_180019A35
0x180019a22  mov     r15d, dword ptr [rsp+130h+var_E0+4]
0x180019a27  mov     eax, dword ptr [rsp+130h+var_E0]
0x180019a2b  mov     rbx, [rsp+130h+var_E8]
0x180019a30  jmp     loc_1800198FD
  ... truncated ...
```
