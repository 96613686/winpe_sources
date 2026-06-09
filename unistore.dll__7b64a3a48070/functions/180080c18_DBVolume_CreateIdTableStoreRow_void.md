# DBVolume::_CreateIdTableStoreRow(void)

- ea: `0x180080c18`
- end: `0x180080f34`
- name: `?_CreateIdTableStoreRow@DBVolume@@IEAAJXZ`
- size: `796`
- prototype: `__int64 __fastcall(DBVolume *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d4a0`

## callees

- `0x180002b80`
- `0x1800068f0`
- `0x18000866c`
- `0x1800086bc`
- `0x180008ff0`
- `0x18000f530`
- `0x180012100`
- `0x180013618`
- `0x180019c3c`
- `0x180058298`
- `0x18005a018`
- `0x180080c18`
- `0x1800c50aa`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180080e4a`
- `ESENT!JetPrepareUpdate` at `0x180080edb`
- `ESENT!JetPrepareUpdate` at `0x180080e4a`
- `ESENT!JetPrepareUpdate` at `0x180080edb`

## string_xrefs

- `0x180080c97`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180080d14`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180080d74`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180080e21`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180080e65`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x180080eee`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall DBVolume::_CreateIdTableStoreRow(DBVolume *this)
{
  int TableHandle; // eax
  unsigned int v3; // r8d
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r9
  const char *v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  unsigned int HresultFromJetError; // eax
  __int64 v17; // r9
  JET_ERR v18; // eax
  int v19; // eax
  int v20; // eax
  JET_ERR v21; // eax
  unsigned int v22; // eax
  JET_SESID sesid; // [rsp+30h] [rbp-69h] BYREF
  JET_TABLEID tableid; // [rsp+38h] [rbp-61h]
  int v26; // [rsp+40h] [rbp-59h]
  __int128 v27; // [rsp+48h] [rbp-51h] BYREF
  int v28; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v29[2]; // [rsp+60h] [rbp-39h] BYREF
  __int64 v30; // [rsp+70h] [rbp-29h] BYREF
  struct TableHandleInfo *v31[2]; // [rsp+80h] [rbp-19h] BYREF
  struct JET_SETCOLUMN v32; // [rsp+90h] [rbp-9h] BYREF
  int v33; // [rsp+B8h] [rbp+1Fh]
  int *v34; // [rsp+C0h] [rbp+27h]
  int v35; // [rsp+C8h] [rbp+2Fh]
  int v36; // [rsp+D4h] [rbp+3Bh]
  int v37; // [rsp+108h] [rbp+6Fh] BYREF
  int v38; // [rsp+110h] [rbp+77h] BYREF
  unsigned int v39; // [rsp+118h] [rbp+7Fh] BYREF

  v29[0] = 0;
  v29[1] = 0;
  *(_OWORD *)v31 = 0;
  TableHandle = GetTableHandle(0, 0, this, v29, v31);
  v4 = TableHandle;
  if ( TableHandle < 0 )
  {
    v5 = 4773;
LABEL_6:
    v6 = (unsigned int)TableHandle;
LABEL_7:
    Log_UnistoreHREvent_0(
      v6,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v5);
    goto LABEL_37;
  }
  v37 = 5;
  TableHandle = UnistoreJetMove(v31[0], 0x7FFFFFFF, v3);
  v4 = TableHandle;
  if ( TableHandle != -2147024871 )
  {
    if ( TableHandle < 0 )
    {
      v5 = 4779;
      goto LABEL_6;
    }
    v38 = 0;
    v39 = 0;
    TableHandle = GetDwordPropFromTableCursor(v31[0], 17170435, &v38, &v39);
    v4 = TableHandle;
    if ( TableHandle < 0 )
    {
      v5 = 4783;
      goto LABEL_6;
    }
    if ( v38 )
    {
      if ( v39 + 1 < v39 )
      {
        v4 = -2147024362;
        v37 = -1;
        v6 = 2147942934LL;
        v5 = 4787;
        goto LABEL_7;
      }
      v37 = v39 + 1;
    }
  }
  v27 = 0;
  v7 = GetTableHandle(53, 0, this, v29, &v27);
  v4 = v7;
  if ( v7 < 0 )
  {
    v9 = 4792;
    v10 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp";
    v11 = 1;
LABEL_15:
    v12 = (unsigned int)v7;
LABEL_16:
    Log_UnistoreHREvent_0(v12, v11, v10, v9);
LABEL_17:
    auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v27);
    goto LABEL_37;
  }
  v30 = 0;
  if ( !(unsigned int)ColumnIdMappings::PropIdToColumnId(v8, 53, 17170435, &v30) )
  {
    v9 = 4795;
    v11 = 0;
LABEL_21:
    v4 = -2147418113;
    v10 = "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp";
    v12 = 2147549183LL;
    goto LABEL_16;
  }
  sesid = 0;
  LODWORD(tableid) = 0;
  v14 = ColumnIdMappings::PropIdToColumnId(v13, 53, 279511043, &sesid);
  v11 = 0;
  if ( !v14 )
  {
    v9 = 4798;
    goto LABEL_21;
  }
  memset_0(&v32, 0, 0x50u);
  v32.columnid = v30;
  v32.cbData = 4;
  v32.pvData = &v28;
  v35 = 4;
  v33 = sesid;
  v34 = &v37;
  v28 = 0;
  v32.itagSequence = 1;
  v36 = 1;
  sesid = *(_QWORD *)(v27 + 8);
  tableid = *(_QWORD *)(v27 + 16);
  v26 = 0;
  v15 = auto_JET_PREPARE::Prepare((auto_JET_PREPARE *)&sesid, 0);
  if ( v15 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v15);
    v17 = 4815;
    goto LABEL_26;
  }
  v19 = CommsESE_JetSetColumns(*(_QWORD *)(v27 + 8), *(_QWORD *)(v27 + 16), &v32, 2u);
  if ( v19 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v19);
    v17 = 4816;
    goto LABEL_26;
  }
  v20 = auto_JET_PREPARE::Update((auto_JET_PREPARE *)&sesid, 0, 0, 0);
  if ( v20 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v20);
    v17 = 4817;
LABEL_26:
    v4 = HresultFromJetError;
    Log_UnistoreHREvent_0(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v17);
    if ( !v26 )
      goto LABEL_17;
    v18 = JetPrepareUpdate(sesid, tableid, 3u);
    if ( v18 >= 0 )
      goto LABEL_17;
    v7 = MakeHresultFromJetError(v18);
    v9 = 577;
    v10 = "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h";
    v11 = 0;
    goto LABEL_15;
  }
  if ( v26 )
  {
    v21 = JetPrepareUpdate(sesid, tableid, 3u);
    if ( v21 < 0 )
    {
      v22 = MakeHresultFromJetError(v21);
      Log_UnistoreHREvent_0(
        v22,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
        577);
    }
  }
  auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v27);
  v4 = 0;
LABEL_37:
  auto_TableHandle::~auto_TableHandle((auto_TableHandle *)v31);
  auto_DBSession::~auto_DBSession((auto_DBSession *)v29);
  return v4;
}

```

## disassembly

```asm
0x180080c18  mov     [rsp-8+arg_0], rbx
0x180080c1d  push    rbp
0x180080c1e  push    rsi
0x180080c1f  push    rdi
0x180080c20  lea     rbp, [rsp-47h]
0x180080c25  sub     rsp, 0E0h
0x180080c2c  mov     rdi, rcx
0x180080c2f  lea     rax, [rbp+57h+var_70]
0x180080c33  xor     esi, esi
0x180080c35  mov     [rsp+0F0h+var_D0], rax
0x180080c3a  xorps   xmm0, xmm0
0x180080c3d  mov     [rbp+57h+var_90], rsi
0x180080c41  mov     r8, rcx
0x180080c44  mov     [rbp+57h+var_88], rsi
0x180080c48  xor     ecx, ecx
0x180080c4a  lea     r9, [rbp+57h+var_90]
0x180080c4e  xor     edx, edx
0x180080c50  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180080c55  call    ?GetTableHandle@@YAJW4US_TABLEID@@KPEAVIDBVolume@@AEAVauto_DBSession@@AEAVauto_TableHandle@@@Z
0x180080c5a  mov     ebx, eax
0x180080c5c  test    eax, eax
0x180080c5e  jns     short loc_180080C68
0x180080c60  mov     r9d, 12A5h
0x180080c66  jmp     short loc_180080C90
0x180080c68  mov     rcx, [rbp+57h+var_70]; struct TableHandleInfo *
0x180080c6c  mov     edx, 7FFFFFFFh; int
0x180080c71  mov     [rbp+57h+arg_8], 5
0x180080c78  call    ?UnistoreJetMove@@YAJPEAUTableHandleInfo@@JK@Z
0x180080c7d  mov     ebx, eax
0x180080c7f  cmp     eax, 80070019h
0x180080c84  jz      short loc_180080CE4
0x180080c86  test    eax, eax
0x180080c88  jns     short loc_180080CA8
0x180080c8a  mov     r9d, 12ABh
0x180080c90  mov     ecx, eax
0x180080c92  mov     edx, 1
0x180080c97  lea     r8, aOnecoreuapBase_18
0x180080c9e  call    Log_UnistoreHREvent_0
0x180080ca3  jmp     loc_180080F0D
0x180080ca8  mov     rcx, [rbp+57h+var_70]
0x180080cac  lea     r9, [rbp+57h+arg_18]
0x180080cb0  lea     r8, [rbp+57h+arg_10]
0x180080cb4  mov     [rbp+57h+arg_10], esi
0x180080cb7  mov     edx, 1060003h
0x180080cbc  mov     [rbp+57h+arg_18], esi
0x180080cbf  call    GetDwordPropFromTableCursor
0x180080cc4  mov     ebx, eax
0x180080cc6  test    eax, eax
0x180080cc8  jns     short loc_180080CD2
0x180080cca  mov     r9d, 12AFh
0x180080cd0  jmp     short loc_180080C90
0x180080cd2  cmp     [rbp+57h+arg_10], esi
0x180080cd5  jz      short loc_180080CE4
0x180080cd7  mov     eax, [rbp+57h+arg_18]
0x180080cda  lea     ecx, [rax+1]
0x180080cdd  cmp     ecx, eax
0x180080cdf  jb      short loc_180080D33
0x180080ce1  mov     [rbp+57h+arg_8], ecx
0x180080ce4  xor     edx, edx
0x180080ce6  lea     rax, [rbp+57h+var_A8]
0x180080cea  mov     r8, rdi
0x180080ced  mov     [rsp+0F0h+var_D0], rax
0x180080cf2  xorps   xmm0, xmm0
0x180080cf5  lea     r9, [rbp+57h+var_90]
0x180080cf9  movdqu  [rbp+57h+var_A8], xmm0
0x180080cfe  lea     edi, [rdx+35h]
0x180080d01  mov     ecx, edi
0x180080d03  call    ?GetTableHandle@@YAJW4US_TABLEID@@KPEAVIDBVolume@@AEAVauto_DBSession@@AEAVauto_TableHandle@@@Z
0x180080d08  mov     ebx, eax
0x180080d0a  test    eax, eax
0x180080d0c  jns     short loc_180080D4C
0x180080d0e  mov     r9d, 12B8h
0x180080d14  lea     r8, aOnecoreuapBase_18
0x180080d1b  lea     edx, [rdi-34h]
0x180080d1e  mov     ecx, eax
0x180080d20  call    Log_UnistoreHREvent_0
0x180080d25  lea     rcx, [rbp+57h+var_A8]; this
0x180080d29  call    ??1auto_TableHandle@@QEAA@XZ
0x180080d2e  jmp     loc_180080F0D
0x180080d33  mov     ebx, 80070216h
0x180080d38  mov     [rbp+57h+arg_8], 0FFFFFFFFh
0x180080d3f  mov     ecx, ebx
0x180080d41  mov     r9d, 12B3h
0x180080d47  jmp     loc_180080C92
0x180080d4c  xor     eax, eax
0x180080d4e  lea     r9, [rbp+57h+var_80]
0x180080d52  mov     r8d, 1060003h
0x180080d58  mov     [rbp+57h+var_80], rax
0x180080d5c  mov     edx, edi
0x180080d5e  call    ?PropIdToColumnId@ColumnIdMappings@@QEAAHW4US_TABLEID@@KPEAUColumnDetails@@@Z
0x180080d63  test    eax, eax
0x180080d65  jnz     short loc_180080D7F
0x180080d67  mov     r9d, 12BBh
0x180080d6d  xor     edx, edx
0x180080d6f  mov     ebx, 8000FFFFh
0x180080d74  lea     r8, aOnecoreuapBase_18
0x180080d7b  mov     ecx, ebx
0x180080d7d  jmp     short loc_180080D20
0x180080d7f  xor     eax, eax
0x180080d81  lea     r9, [rbp+57h+sesid]
0x180080d85  mov     r8d, 10A90003h
0x180080d8b  mov     [rbp+57h+sesid], rax
0x180080d8f  mov     edx, edi
0x180080d91  mov     dword ptr [rbp+57h+tableid], eax
0x180080d94  call    ?PropIdToColumnId@ColumnIdMappings@@QEAAHW4US_TABLEID@@KPEAUColumnDetails@@@Z
0x180080d99  xor     edx, edx; Val
0x180080d9b  test    eax, eax
0x180080d9d  jnz     short loc_180080DA7
0x180080d9f  mov     r9d, 12BEh
0x180080da5  jmp     short loc_180080D6F
0x180080da7  mov     r8d, 50h ; 'P'; Size
0x180080dad  lea     rcx, [rbp+57h+var_60]; void *
0x180080db1  call    memset_0
0x180080db6  mov     eax, dword ptr [rbp+57h+var_80]
0x180080db9  mov     ecx, 4
0x180080dbe  mov     [rbp+57h+var_60.columnid], eax
0x180080dc1  xor     edx, edx; unsigned int
0x180080dc3  mov     [rbp+57h+var_60.cbData], ecx
0x180080dc6  lea     rax, [rbp+57h+var_98]
0x180080dca  mov     [rbp+57h+var_60.pvData], rax
0x180080dce  mov     eax, dword ptr [rbp+57h+sesid]
0x180080dd1  mov     [rbp+57h+var_28], ecx
0x180080dd4  mov     rcx, qword ptr [rbp+57h+var_A8]
0x180080dd8  mov     [rbp+57h+var_38], eax
0x180080ddb  lea     rax, [rbp+57h+arg_8]
0x180080ddf  mov     [rbp+57h+var_30], rax
0x180080de3  mov     [rbp+57h+var_98], esi
0x180080de6  mov     [rbp+57h+var_60.itagSequence], 1
0x180080ded  mov     [rbp+57h+var_1C], 1
0x180080df4  mov     rax, [rcx+8]
0x180080df8  mov     [rbp+57h+sesid], rax
0x180080dfc  mov     rax, [rcx+10h]
0x180080e00  lea     rcx, [rbp+57h+sesid]; this
0x180080e04  mov     [rbp+57h+tableid], rax
0x180080e08  mov     [rbp+57h+var_B0], esi
0x180080e0b  call    ?Prepare@auto_JET_PREPARE@@QEAAJK@Z
0x180080e10  test    eax, eax
0x180080e12  jns     short loc_180080E73
0x180080e14  mov     ecx, eax; int
0x180080e16  call    ?MakeHresultFromJetError@@YAJJ@Z
0x180080e1b  mov     r9d, 12CFh
0x180080e21  lea     r8, aOnecoreuapBase_18
0x180080e28  xor     edx, edx
0x180080e2a  mov     ecx, eax
0x180080e2c  mov     ebx, eax
0x180080e2e  call    Log_UnistoreHREvent_0
0x180080e33  cmp     [rbp+57h+var_B0], esi
0x180080e36  jz      loc_180080D25
0x180080e3c  mov     rdx, [rbp+57h+tableid]; tableid
0x180080e40  mov     r8d, 3; prep
0x180080e46  mov     rcx, [rbp+57h+sesid]; sesid
0x180080e4a  call    cs:__imp_JetPrepareUpdate
0x180080e50  test    eax, eax
0x180080e52  jns     loc_180080D25
0x180080e58  mov     ecx, eax; int
0x180080e5a  call    ?MakeHresultFromJetError@@YAJJ@Z
0x180080e5f  mov     r9d, 241h
0x180080e65  lea     r8, aOnecoreuapBase_50
0x180080e6c  xor     edx, edx
0x180080e6e  jmp     loc_180080D1E
0x180080e73  mov     rcx, qword ptr [rbp+57h+var_A8]
0x180080e77  lea     r8, [rbp+57h+var_60]; struct JET_SETCOLUMN *
0x180080e7b  mov     r9d, 2; unsigned int
0x180080e81  mov     rdx, [rcx+10h]; unsigned __int64
0x180080e85  mov     rcx, [rcx+8]; unsigned __int64
0x180080e89  call    ?CommsESE_JetSetColumns@@YAJ_K0PEAUJET_SETCOLUMN@@K@Z
0x180080e8e  test    eax, eax
0x180080e90  jns     short loc_180080EA1
0x180080e92  mov     ecx, eax; int
0x180080e94  call    ?MakeHresultFromJetError@@YAJJ@Z
0x180080e99  mov     r9d, 12D0h
0x180080e9f  jmp     short loc_180080E21
0x180080ea1  xor     r9d, r9d; unsigned int *
0x180080ea4  lea     rcx, [rbp+57h+sesid]; this
0x180080ea8  xor     r8d, r8d; unsigned int
0x180080eab  xor     edx, edx; void *
0x180080ead  call    ?Update@auto_JET_PREPARE@@QEAAJPEAXKPEAK@Z
0x180080eb2  test    eax, eax
0x180080eb4  jns     short loc_180080EC8
0x180080eb6  mov     ecx, eax; int
0x180080eb8  call    ?MakeHresultFromJetError@@YAJJ@Z
0x180080ebd  mov     r9d, 12D1h
0x180080ec3  jmp     loc_180080E21
0x180080ec8  cmp     [rbp+57h+var_B0], esi
0x180080ecb  jz      short loc_180080F02
0x180080ecd  mov     rdx, [rbp+57h+tableid]; tableid
0x180080ed1  mov     r8d, 3; prep
0x180080ed7  mov     rcx, [rbp+57h+sesid]; sesid
0x180080edb  call    cs:__imp_JetPrepareUpdate
0x180080ee1  test    eax, eax
0x180080ee3  jns     short loc_180080F02
0x180080ee5  mov     ecx, eax; int
0x180080ee7  call    ?MakeHresultFromJetError@@YAJJ@Z
0x180080eec  mov     ecx, eax
0x180080eee  lea     r8, aOnecoreuapBase_50
0x180080ef5  mov     r9d, 241h
0x180080efb  xor     edx, edx
0x180080efd  call    Log_UnistoreHREvent_0
0x180080f02  lea     rcx, [rbp+57h+var_A8]; this
0x180080f06  call    ??1auto_TableHandle@@QEAA@XZ
0x180080f0b  mov     ebx, esi
0x180080f0d  lea     rcx, [rbp+57h+var_70]; this
0x180080f11  call    ??1auto_TableHandle@@QEAA@XZ
0x180080f16  lea     rcx, [rbp+57h+var_90]; this
0x180080f1a  call    ??1auto_DBSession@@QEAA@XZ
0x180080f1f  mov     eax, ebx
0x180080f21  mov     rbx, [rsp+0F0h+arg_0]
0x180080f29  add     rsp, 0E0h
0x180080f30  pop     rdi
0x180080f31  pop     rsi
0x180080f32  pop     rbp
0x180080f33  retn
```
