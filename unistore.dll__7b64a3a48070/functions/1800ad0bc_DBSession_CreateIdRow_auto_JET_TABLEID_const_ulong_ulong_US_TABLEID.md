# DBSession::_CreateIdRow(auto_JET_TABLEID const &,ulong,ulong,US_TABLEID)

- ea: `0x1800ad0bc`
- end: `0x1800ad2d8`
- name: `?_CreateIdRow@DBSession@@IEAAJAEBVauto_JET_TABLEID@@KKW4US_TABLEID@@@Z`
- size: `540`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ace68`
- `0x1800ad2e0`

## callees

- `0x1800068f0`
- `0x18000f530`
- `0x180013618`
- `0x18001d98c`
- `0x180058298`
- `0x18005a018`
- `0x180063bcc`
- `0x1800ad0bc`
- `0x1800c50aa`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x1800ad205`
- `ESENT!JetPrepareUpdate` at `0x1800ad297`
- `ESENT!JetPrepareUpdate` at `0x1800ad205`
- `ESENT!JetPrepareUpdate` at `0x1800ad297`

## string_xrefs

- `0x1800ad1df`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x1800ad218`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x1800ad2aa`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall DBSession::_CreateIdRow(__int64 a1, JET_SESID *a2, JET_COLUMNID a3, int a4, unsigned int a5)
{
  unsigned int v5; // ebx
  bool v9; // sf
  int v10; // eax
  int v11; // eax
  unsigned int HresultFromJetError; // eax
  __int64 v13; // r9
  unsigned int v14; // ebx
  JET_ERR v15; // eax
  unsigned int v16; // eax
  int v18; // eax
  int v19; // eax
  JET_ERR v20; // eax
  unsigned int v21; // eax
  JET_SESID sesid; // [rsp+38h] [rbp-31h] BYREF
  JET_TABLEID tableid; // [rsp+40h] [rbp-29h]
  int v24; // [rsp+48h] [rbp-21h]
  struct JET_SETCOLUMN v25; // [rsp+58h] [rbp-11h] BYREF
  int v26; // [rsp+80h] [rbp+17h]
  __int64 *v27; // [rsp+88h] [rbp+1Fh]
  int v28; // [rsp+90h] [rbp+27h]
  int v29; // [rsp+9Ch] [rbp+33h]
  __int64 v30; // [rsp+C8h] [rbp+5Fh] BYREF

  v30 = a1;
  v5 = a5;
  if ( (unsigned int)GetIdProp(a5) != 65539 && v5 )
    return 0;
  memset_0(&v25, 0, 0x50u);
  v25.columnid = a3;
  v25.pvData = &a5;
  v25.itagSequence = 1;
  v25.cbData = 4;
  LODWORD(v30) = 0;
  if ( v5 )
  {
    if ( v5 == 50
      && (int)RegistryGetDWORD(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Unified Store",
                L"LastStoreGroupingId",
                (unsigned int *)&v30) >= 0 )
    {
      LODWORD(v30) = v30 + 1;
    }
  }
  else
  {
    v9 = (int)RegistryGetDWORD(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Unified Store",
                L"LastStoreId",
                (unsigned int *)&v30) < 0;
    v10 = v30;
    if ( !v9 )
    {
      v10 = v30 + 1;
      LODWORD(v30) = v30 + 1;
    }
    if ( (unsigned int)(v10 - 5) > 0x7FFFFFFB )
      LODWORD(v30) = 5;
  }
  v26 = a4;
  v27 = &v30;
  sesid = *a2;
  tableid = a2[1];
  v28 = 4;
  v29 = 1;
  v24 = 0;
  v11 = auto_JET_PREPARE::Prepare((auto_JET_PREPARE *)&sesid, 0);
  if ( v11 >= 0 )
  {
    v18 = CommsESE_JetSetColumns(*a2, a2[1], &v25, 2u);
    if ( v18 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v18);
      v13 = 1272;
      goto LABEL_13;
    }
    v19 = auto_JET_PREPARE::Update((auto_JET_PREPARE *)&sesid, 0, 0, 0);
    if ( v19 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v19);
      v13 = 1274;
      goto LABEL_13;
    }
    if ( v24 )
    {
      v20 = JetPrepareUpdate(sesid, tableid, 3u);
      if ( v20 < 0 )
      {
        v21 = MakeHresultFromJetError(v20);
        Log_UnistoreHREvent_0(
          v21,
          0,
          "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
          577);
      }
    }
    return 0;
  }
  HresultFromJetError = MakeHresultFromJetError(v11);
  v13 = 1270;
LABEL_13:
  v14 = HresultFromJetError;
  Log_UnistoreHREvent_0(
    HresultFromJetError,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
    v13);
  if ( v24 )
  {
    v15 = JetPrepareUpdate(sesid, tableid, 3u);
    if ( v15 < 0 )
    {
      v16 = MakeHresultFromJetError(v15);
      Log_UnistoreHREvent_0(
        v16,
        0,
        "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
        577);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x1800ad0bc  mov     rax, rsp
0x1800ad0bf  mov     [rax+10h], rbx
0x1800ad0c3  mov     [rax+18h], rsi
0x1800ad0c7  mov     [rax+8], rcx
0x1800ad0cb  push    rbp
0x1800ad0cc  push    rdi
0x1800ad0cd  push    r14
0x1800ad0cf  lea     rbp, [rax-57h]
0x1800ad0d3  sub     rsp, 0A0h
0x1800ad0da  mov     ebx, [rbp+4Fh+arg_20]
0x1800ad0dd  mov     r14d, r9d
0x1800ad0e0  mov     ecx, ebx
0x1800ad0e2  mov     esi, r8d
0x1800ad0e5  mov     rdi, rdx
0x1800ad0e8  call    ?GetIdProp@@YAKW4US_TABLEID@@@Z; GetIdProp(US_TABLEID)
0x1800ad0ed  cmp     eax, 10003h
0x1800ad0f2  jz      short loc_1800AD0FC
0x1800ad0f4  test    ebx, ebx
0x1800ad0f6  jnz     loc_1800AD2BE
0x1800ad0fc  xor     edx, edx; Val
0x1800ad0fe  lea     rcx, [rbp+4Fh+var_60]; void *
0x1800ad102  lea     r8d, [rdx+50h]; Size
0x1800ad106  call    memset_0
0x1800ad10b  mov     [rbp+4Fh+var_60.columnid], esi
0x1800ad10e  lea     rax, [rbp+4Fh+arg_20]
0x1800ad112  mov     [rbp+4Fh+var_60.pvData], rax
0x1800ad116  mov     esi, 1
0x1800ad11b  mov     [rbp+4Fh+var_60.itagSequence], esi
0x1800ad11e  mov     [rbp+4Fh+var_60.cbData], 4
0x1800ad125  mov     dword ptr [rbp+4Fh+arg_0], 0
0x1800ad12c  test    ebx, ebx
0x1800ad12e  jnz     short loc_1800AD16D
0x1800ad130  lea     r9, [rbp+4Fh+arg_0]; unsigned int *
0x1800ad134  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800ad13b  lea     r8, ?c_wszUnistoreRegistryLastStoreId@@3QBGB; "LastStoreId"
0x1800ad142  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x1800ad149  call    ?RegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; RegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ad14e  test    eax, eax
0x1800ad150  mov     eax, dword ptr [rbp+4Fh+arg_0]
0x1800ad153  js      short loc_1800AD15A
0x1800ad155  add     eax, esi
0x1800ad157  mov     dword ptr [rbp+4Fh+arg_0], eax
0x1800ad15a  add     eax, 0FFFFFFFBh
0x1800ad15d  cmp     eax, 7FFFFFFBh
0x1800ad162  jbe     short loc_1800AD197
0x1800ad164  mov     dword ptr [rbp+4Fh+arg_0], 5
0x1800ad16b  jmp     short loc_1800AD197
0x1800ad16d  cmp     ebx, 32h ; '2'
0x1800ad170  jnz     short loc_1800AD197
0x1800ad172  lea     r9, [rbp+4Fh+arg_0]; unsigned int *
0x1800ad176  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800ad17d  lea     r8, ?c_wszUnistoreRegistryLastStoreGroupingId@@3QBGB; "LastStoreGroupingId"
0x1800ad184  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x1800ad18b  call    ?RegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; RegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ad190  test    eax, eax
0x1800ad192  js      short loc_1800AD197
0x1800ad194  add     dword ptr [rbp+4Fh+arg_0], esi
0x1800ad197  lea     rax, [rbp+4Fh+arg_0]
0x1800ad19b  mov     [rbp+4Fh+var_38], r14d
0x1800ad19f  mov     [rbp+4Fh+var_30], rax
0x1800ad1a3  lea     rcx, [rbp+4Fh+sesid]; this
0x1800ad1a7  mov     rax, [rdi]
0x1800ad1aa  xor     edx, edx; unsigned int
0x1800ad1ac  mov     [rbp+4Fh+sesid], rax
0x1800ad1b0  mov     rax, [rdi+8]
0x1800ad1b4  mov     [rbp+4Fh+tableid], rax
0x1800ad1b8  mov     [rbp+4Fh+var_28], 4
0x1800ad1bf  mov     [rbp+4Fh+var_1C], esi
0x1800ad1c2  mov     [rbp+4Fh+var_70], 0
0x1800ad1c9  call    ?Prepare@auto_JET_PREPARE@@QEAAJK@Z; auto_JET_PREPARE::Prepare(ulong)
0x1800ad1ce  test    eax, eax
0x1800ad1d0  jns     short loc_1800AD233
0x1800ad1d2  mov     ecx, eax; int
0x1800ad1d4  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800ad1d9  mov     r9d, 4F6h
0x1800ad1df  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800ad1e6  xor     edx, edx
0x1800ad1e8  mov     ecx, eax
0x1800ad1ea  mov     ebx, eax
0x1800ad1ec  call    Log_UnistoreHREvent_0
0x1800ad1f1  cmp     [rbp+4Fh+var_70], 0
0x1800ad1f5  jz      short loc_1800AD22C
0x1800ad1f7  mov     rdx, [rbp+4Fh+tableid]; tableid
0x1800ad1fb  mov     r8d, 3; prep
0x1800ad201  mov     rcx, [rbp+4Fh+sesid]; sesid
0x1800ad205  call    cs:__imp_JetPrepareUpdate
0x1800ad20b  test    eax, eax
0x1800ad20d  jns     short loc_1800AD22C
0x1800ad20f  mov     ecx, eax; int
0x1800ad211  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800ad216  mov     ecx, eax
0x1800ad218  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800ad21f  mov     r9d, 241h
0x1800ad225  xor     edx, edx
0x1800ad227  call    Log_UnistoreHREvent_0
0x1800ad22c  mov     eax, ebx
0x1800ad22e  jmp     loc_1800AD2C0
0x1800ad233  mov     rdx, [rdi+8]; unsigned __int64
0x1800ad237  lea     r8, [rbp+4Fh+var_60]; struct JET_SETCOLUMN *
0x1800ad23b  mov     rcx, [rdi]; unsigned __int64
0x1800ad23e  mov     r9d, 2; unsigned int
0x1800ad244  call    ?CommsESE_JetSetColumns@@YAJ_K0PEAUJET_SETCOLUMN@@K@Z; CommsESE_JetSetColumns(unsigned __int64,unsigned __int64,JET_SETCOLUMN *,ulong)
0x1800ad249  test    eax, eax
0x1800ad24b  jns     short loc_1800AD25C
0x1800ad24d  mov     ecx, eax; int
0x1800ad24f  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800ad254  mov     r9d, 4F8h
0x1800ad25a  jmp     short loc_1800AD1DF
0x1800ad25c  xor     r9d, r9d; unsigned int *
0x1800ad25f  lea     rcx, [rbp+4Fh+sesid]; this
0x1800ad263  xor     r8d, r8d; unsigned int
0x1800ad266  xor     edx, edx; void *
0x1800ad268  call    ?Update@auto_JET_PREPARE@@QEAAJPEAXKPEAK@Z; auto_JET_PREPARE::Update(void *,ulong,ulong *)
0x1800ad26d  test    eax, eax
0x1800ad26f  jns     short loc_1800AD283
0x1800ad271  mov     ecx, eax; int
0x1800ad273  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800ad278  mov     r9d, 4FAh
0x1800ad27e  jmp     loc_1800AD1DF
0x1800ad283  cmp     [rbp+4Fh+var_70], 0
0x1800ad287  jz      short loc_1800AD2BE
0x1800ad289  mov     rdx, [rbp+4Fh+tableid]; tableid
0x1800ad28d  mov     r8d, 3; prep
0x1800ad293  mov     rcx, [rbp+4Fh+sesid]; sesid
0x1800ad297  call    cs:__imp_JetPrepareUpdate
0x1800ad29d  test    eax, eax
0x1800ad29f  jns     short loc_1800AD2BE
0x1800ad2a1  mov     ecx, eax; int
0x1800ad2a3  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800ad2a8  mov     ecx, eax
0x1800ad2aa  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800ad2b1  mov     r9d, 241h
0x1800ad2b7  xor     edx, edx
0x1800ad2b9  call    Log_UnistoreHREvent_0
0x1800ad2be  xor     eax, eax
0x1800ad2c0  lea     r11, [rsp+0B0h+var_10]
0x1800ad2c8  mov     rbx, [r11+28h]
0x1800ad2cc  mov     rsi, [r11+30h]
0x1800ad2d0  mov     rsp, r11
0x1800ad2d3  pop     r14
0x1800ad2d5  pop     rdi
0x1800ad2d6  pop     rbp
0x1800ad2d7  retn
```
