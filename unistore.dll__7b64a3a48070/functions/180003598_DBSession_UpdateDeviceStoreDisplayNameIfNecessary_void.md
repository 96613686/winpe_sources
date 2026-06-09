# DBSession::_UpdateDeviceStoreDisplayNameIfNecessary(void)

- ea: `0x180003598`
- end: `0x1800039ef`
- name: `?_UpdateDeviceStoreDisplayNameIfNecessary@DBSession@@AEAAJXZ`
- size: `1111`
- prototype: `__int64 __fastcall(DBSession *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180001f94`

## callees

- `0x180002ed0`
- `0x180002fbc`
- `0x180003420`
- `0x180003518`
- `0x180003598`
- `0x180003b3c`
- `0x1800068f0`
- `0x18000b350`
- `0x18000f530`
- `0x180012098`
- `0x1800131c8`
- `0x180013504`
- `0x180028ef4`
- `0x18002ac20`
- `0x18006f180`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003844`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000384c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000388d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800038ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000391d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003844`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000384c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000388d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800038ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000391d`
- `ESENT!JetRollback` at `0x180003859`
- `ESENT!JetRollback` at `0x180003859`
- `ESENT!JetCommitTransaction2` at `0x18000379b`
- `ESENT!JetCommitTransaction2` at `0x1800037e9`
- `ESENT!JetCommitTransaction2` at `0x18000379b`
- `ESENT!JetCommitTransaction2` at `0x1800037e9`
- `ESENT!JetBeginTransaction2` at `0x1800036ba`
- `ESENT!JetBeginTransaction2` at `0x1800036ba`

## string_xrefs

- `0x1800036d3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x1800038c5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180003945`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180003960`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x18000397b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x18000392e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x18000375c`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`
- `0x180003999`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\jetinterop.h`

## pseudocode

```c
__int64 __fastcall DBSession::_UpdateDeviceStoreDisplayNameIfNecessary(DBSession *this)
{
  __int64 v2; // rcx
  int v3; // ebx
  int v4; // eax
  int DeviceStoreDefaultName; // eax
  JET_SESID v6; // rsi
  int v7; // r14d
  int v8; // r15d
  JET_ERR v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // edi
  int v18; // edi
  int v19; // eax
  JET_ERR v20; // eax
  unsigned int HresultFromJetError; // eax
  __int64 v22; // r9
  __int64 v23; // r9
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-69h] BYREF
  JET_SESID v28; // [rsp+38h] [rbp-61h] BYREF
  __int64 v29; // [rsp+40h] [rbp-59h]
  __int64 v30; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int64 v31; // [rsp+50h] [rbp-49h] BYREF
  _QWORD v32[3]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v33[24]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v34[104]; // [rsp+88h] [rbp-11h] BYREF
  unsigned int v35; // [rsp+100h] [rbp+67h] BYREF
  unsigned int v36; // [rsp+108h] [rbp+6Fh] BYREF
  unsigned int v37; // [rsp+110h] [rbp+77h] BYREF
  HLOCAL v38; // [rsp+118h] [rbp+7Fh] BYREF

  v30 = *((_QWORD *)this + 27);
  v31 = -1;
  TableHandleInfo::TableHandleInfo((TableHandleInfo *)v33);
  v3 = DBSession::_OpenDeviceStore(this, &v31, (struct TableHandleInfo *)v33);
  if ( v3 == -2147024871 )
    goto LABEL_45;
  if ( g_breakOnJetError == -1305 )
    Log_AssertionEvent(
      v2,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
      25);
  if ( v3 == -2134375143 )
    goto LABEL_45;
  if ( v3 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v3,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      304);
LABEL_52:
    UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation((UnifiedStoreCursorLocation *)v34);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v30);
    return (unsigned int)v3;
  }
  v36 = 805896203;
  v35 = 0;
  v37 = 1;
  v38 = 0;
  v4 = ESEReadRecordProps((struct TableHandleInfo *)v33, 0, &v37, &v36, (unsigned __int8 **)&v38, &v35);
  v3 = v4;
  if ( v4 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v4,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      319);
LABEL_50:
    if ( v38 )
      LocalFree(v38);
    goto LABEL_52;
  }
  if ( (*((_WORD *)v38 + 3) & 0x100) == 0 && *((_DWORD *)v38 + 2) )
  {
    if ( v38 )
      LocalFree(v38);
LABEL_45:
    UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation((UnifiedStoreCursorLocation *)v34);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v30);
    return 0;
  }
  hMem = 0;
  DeviceStoreDefaultName = GetDeviceStoreDefaultName((unsigned __int16 **)&hMem);
  v3 = DeviceStoreDefaultName;
  if ( DeviceStoreDefaultName < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)DeviceStoreDefaultName,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      328);
LABEL_49:
    auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&hMem);
    goto LABEL_50;
  }
  v6 = *((_QWORD *)this + 27);
  v7 = 0;
  v32[0] = 805371935;
  v32[2] = 0;
  v8 = 0;
  v32[1] = hMem;
  v28 = v6;
  v29 = 0;
  v9 = JetBeginTransaction2(v6, 0);
  if ( !v9 )
  {
    v7 = 1;
    LODWORD(v29) = 1;
    goto LABEL_19;
  }
  if ( v9 >= 0 )
  {
LABEL_19:
    v13 = ESEWriteRecordProps(
            (struct TableHandleInfo *)v33,
            (struct UnifiedStoreCursorLocation *)v34,
            0,
            1u,
            (struct _USPROPVAL *)v32,
            0);
    v3 = v13;
    if ( v13 < 0 )
    {
      v23 = 344;
      v24 = 1;
    }
    else
    {
      if ( !v7 )
        Log_AssertionEvent(v14, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h", 463);
      if ( v6 == -1 )
        Log_AssertionEvent(v14, "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h", 464);
      v15 = JetCommitTransaction2(v6, 1, 120000, 0);
      v17 = v15;
      if ( !v15 )
      {
        LODWORD(v29) = 0;
        goto LABEL_26;
      }
      auto_JET_TRANSACTION::Rollback((auto_JET_TRANSACTION *)&v28);
      if ( v17 >= 0 )
      {
        v8 = HIDWORD(v29);
        v15 = v29;
        v6 = v28;
LABEL_26:
        if ( v15 )
        {
          if ( v8 )
          {
            if ( v6 == -1 )
              Log_AssertionEvent(
                v16,
                "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
                464);
            v18 = JetCommitTransaction2(v6, 0, 0, 0);
            if ( !v18 )
              goto LABEL_32;
            auto_JET_TRANSACTION::Rollback((auto_JET_TRANSACTION *)&v28);
            if ( v18 >= 0 )
              goto LABEL_32;
            HresultFromJetError = MakeHresultFromJetError(v18);
            v22 = 431;
            goto LABEL_41;
          }
          v20 = JetRollback(v6, 0);
          if ( v20 < 0 )
          {
            HresultFromJetError = MakeHresultFromJetError(v20);
            v22 = 435;
LABEL_41:
            Log_UnistoreHREvent_0(
              HresultFromJetError,
              0,
              "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
              v22);
          }
        }
LABEL_32:
        if ( hMem )
          LocalFree(hMem);
        if ( v38 )
          LocalFree(v38);
        UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation((UnifiedStoreCursorLocation *)v34);
        v19 = auto_JET_TABLEID::close((auto_JET_TABLEID *)&v30);
        if ( v19 < 0 )
        {
          v26 = MakeHresultFromJetError(v19);
          Log_UnistoreHREvent_0(
            v26,
            0,
            "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
            261);
        }
        return 0;
      }
      v13 = MakeHresultFromJetError(v17);
      v3 = v13;
      v23 = 347;
      v24 = 0;
    }
    Log_UnistoreHREvent_0(
      (unsigned int)v13,
      v24,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      v23);
    auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v28);
    goto LABEL_49;
  }
  v10 = MakeHresultFromJetError(v9);
  Log_UnistoreHREvent_0(
    v10,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
    336);
  auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)&v28);
  if ( hMem )
    LocalFree(hMem);
  if ( v38 )
    LocalFree(v38);
  UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation((UnifiedStoreCursorLocation *)v34);
  v11 = auto_JET_TABLEID::close((auto_JET_TABLEID *)&v30);
  if ( v11 < 0 )
  {
    v25 = MakeHresultFromJetError(v11);
    Log_UnistoreHREvent_0(
      v25,
      0,
      "onecoreuap\\base\\AppModel\\UserDataAccess\\PublishedInternal\\Inc\\jetinterop.h",
      261);
  }
  return v10;
}

```

## disassembly

```asm
0x180003598  push    rbp
0x18000359a  push    rbx
0x18000359b  push    rsi
0x18000359c  push    rdi
0x18000359d  push    r14
0x18000359f  push    r15
0x1800035a1  lea     rbp, [rsp-2Fh]
0x1800035a6  sub     rsp, 0C8h
0x1800035ad  mov     rax, [rcx+0D8h]
0x1800035b4  mov     rsi, rcx
0x1800035b7  lea     rcx, [rbp+57h+var_80]; this
0x1800035bb  mov     [rbp+57h+var_A8], rax
0x1800035bf  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFFh
0x1800035c7  call    ??0TableHandleInfo@@QEAA@XZ; TableHandleInfo::TableHandleInfo(void)
0x1800035cc  lea     r8, [rbp+57h+var_80]; struct TableHandleInfo *
0x1800035d0  mov     rcx, rsi; this
0x1800035d3  lea     rdx, [rbp+57h+var_A0]; unsigned __int64 *
0x1800035d7  call    ?_OpenDeviceStore@DBSession@@AEAAJPEA_KPEAUTableHandleInfo@@@Z; DBSession::_OpenDeviceStore(unsigned __int64 *,TableHandleInfo *)
0x1800035dc  mov     ebx, eax
0x1800035de  cmp     eax, 80070019h
0x1800035e3  jz      loc_180003893
0x1800035e9  cmp     cs:?g_breakOnJetError@@3JA, 0FFFFFAE7h; long g_breakOnJetError
0x1800035f3  jz      loc_180003928
0x1800035f9  cmp     ebx, 80C80519h
0x1800035ff  jz      loc_180003893
0x180003605  test    ebx, ebx
0x180003607  js      loc_18000393F
0x18000360d  lea     rax, [rbp+57h+arg_0]
0x180003611  mov     [rbp+57h+arg_8], 3009000Bh
0x180003618  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x18000361d  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x180003621  lea     rax, [rbp+57h+arg_18]
0x180003625  mov     [rbp+57h+arg_0], 0
0x18000362c  mov     edi, 1
0x180003631  mov     [rsp+0F0h+var_D0], rax; unsigned __int8 **
0x180003636  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x18000363a  mov     [rbp+57h+arg_10], edi
0x18000363d  xor     edx, edx; unsigned int
0x18000363f  mov     [rbp+57h+arg_18], 0
0x180003647  lea     rcx, [rbp+57h+var_80]; struct TableHandleInfo *
0x18000364b  call    ?ESEReadRecordProps@@YAJPEAUTableHandleInfo@@KPEAK1PEAPEAE1@Z; ESEReadRecordProps(TableHandleInfo *,ulong,ulong *,ulong *,uchar * *,ulong *)
0x180003650  mov     ebx, eax
0x180003652  test    eax, eax
0x180003654  js      loc_18000395A
0x18000365a  mov     rcx, [rbp+57h+arg_18]; hMem
0x18000365e  mov     eax, 100h
0x180003663  test    [rcx+6], ax
0x180003667  jz      loc_18000387E
0x18000366d  lea     rcx, [rbp+57h+hMem]; unsigned __int16 **
0x180003671  mov     [rbp+57h+hMem], 0
0x180003679  call    ?GetDeviceStoreDefaultName@@YAJPEAPEAG@Z; GetDeviceStoreDefaultName(ushort * *)
0x18000367e  mov     ebx, eax
0x180003680  test    eax, eax
0x180003682  js      loc_180003975
0x180003688  mov     rsi, [rsi+0D8h]
0x18000368f  xor     r14d, r14d
0x180003692  mov     rax, [rbp+57h+hMem]
0x180003696  mov     rcx, rsi; sesid
0x180003699  xor     edx, edx; grbit
0x18000369b  mov     [rbp+57h+var_98], 3001001Fh
0x1800036a3  mov     [rbp+57h+var_88], 0
0x1800036ab  xor     r15d, r15d
0x1800036ae  mov     [rbp+57h+var_90], rax
0x1800036b2  mov     [rbp+57h+var_B8], rsi
0x1800036b6  mov     [rbp+57h+var_B0], r14
0x1800036ba  call    cs:__imp_JetBeginTransaction2
0x1800036c0  test    eax, eax
0x1800036c2  jz      short loc_18000372B
0x1800036c4  jns     short loc_180003731
0x1800036c6  mov     ecx, eax; int
0x1800036c8  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800036cd  mov     r9d, 150h
0x1800036d3  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800036da  xor     edx, edx
0x1800036dc  mov     ecx, eax
0x1800036de  mov     edi, eax
0x1800036e0  call    Log_UnistoreHREvent_0
0x1800036e5  lea     rcx, [rbp+57h+var_B8]; this
0x1800036e9  call    ??1auto_JET_TRANSACTION@@QEAA@XZ; auto_JET_TRANSACTION::~auto_JET_TRANSACTION(void)
0x1800036ee  mov     rcx, [rbp+57h+hMem]; hMem
0x1800036f2  test    rcx, rcx
0x1800036f5  jz      short loc_1800036FD
0x1800036f7  call    cs:__imp_LocalFree
0x1800036fd  mov     rcx, [rbp+57h+arg_18]; hMem
0x180003701  test    rcx, rcx
0x180003704  jnz     loc_18000391D
0x18000370a  lea     rcx, [rbp+57h+var_68]; this
0x18000370e  call    ??1UnifiedStoreCursorLocation@@QEAA@XZ; UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation(void)
0x180003713  lea     rcx, [rbp+57h+var_A8]; this
0x180003717  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x18000371c  test    eax, eax
0x18000371e  js      loc_180003990
0x180003724  mov     eax, edi
0x180003726  jmp     loc_180003834
0x18000372b  mov     r14d, edi
0x18000372e  mov     dword ptr [rbp+57h+var_B0], edi
0x180003731  lea     rax, [rbp+57h+var_98]
0x180003735  mov     [rsp+0F0h+var_C8], r15; unsigned int *
0x18000373a  mov     r9d, edi; unsigned int
0x18000373d  mov     [rsp+0F0h+var_D0], rax; struct _USPROPVAL *
0x180003742  xor     r8d, r8d; unsigned __int16 *
0x180003745  lea     rdx, [rbp+57h+var_68]; struct UnifiedStoreCursorLocation *
0x180003749  lea     rcx, [rbp+57h+var_80]; struct TableHandleInfo *
0x18000374d  call    ?ESEWriteRecordProps@@YAJPEAUTableHandleInfo@@AEAVUnifiedStoreCursorLocation@@PEBGKPEAU_USPROPVAL@@PEAK@Z; ESEWriteRecordProps(TableHandleInfo *,UnifiedStoreCursorLocation &,ushort const *,ulong,_USPROPVAL *,ulong *)
0x180003752  mov     ebx, eax
0x180003754  test    eax, eax
0x180003756  js      loc_1800039B2
0x18000375c  lea     rbx, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x180003763  test    r14d, r14d
0x180003766  jnz     short loc_180003776
0x180003768  mov     r8d, 1CFh
0x18000376e  mov     rdx, rbx
0x180003771  call    Log_AssertionEvent
0x180003776  mov     r14d, 1D0h
0x18000377c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180003780  jnz     short loc_18000378D
0x180003782  mov     r8d, r14d
0x180003785  mov     rdx, rbx
0x180003788  call    Log_AssertionEvent
0x18000378d  xor     r9d, r9d
0x180003790  mov     r8d, 1D4C0h
0x180003796  mov     edx, edi
0x180003798  mov     rcx, rsi
0x18000379b  call    cs:__imp_JetCommitTransaction2
0x1800037a1  mov     edi, eax
0x1800037a3  test    eax, eax
0x1800037a5  jnz     loc_1800038A7
0x1800037ab  mov     dword ptr [rbp+57h+var_B0], eax
0x1800037ae  test    eax, eax
0x1800037b0  jz      short loc_180003806
0x1800037b2  test    r15d, r15d
0x1800037b5  jz      loc_180003854
0x1800037bb  test    eax, eax
0x1800037bd  jnz     short loc_1800037CD
0x1800037bf  mov     r8d, 1CFh
0x1800037c5  mov     rdx, rbx
0x1800037c8  call    Log_AssertionEvent
0x1800037cd  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800037d1  jnz     short loc_1800037DE
0x1800037d3  mov     r8d, r14d
0x1800037d6  mov     rdx, rbx
0x1800037d9  call    Log_AssertionEvent
0x1800037de  xor     r9d, r9d
0x1800037e1  xor     r8d, r8d
0x1800037e4  xor     edx, edx
0x1800037e6  mov     rcx, rsi
0x1800037e9  call    cs:__imp_JetCommitTransaction2
0x1800037ef  mov     edi, eax
0x1800037f1  test    eax, eax
0x1800037f3  jz      short loc_180003806
0x1800037f5  lea     rcx, [rbp+57h+var_B8]; this
0x1800037f9  call    ?Rollback@auto_JET_TRANSACTION@@QEAAXXZ; auto_JET_TRANSACTION::Rollback(void)
0x1800037fe  test    edi, edi
0x180003800  js      loc_1800039BF
0x180003806  mov     rcx, [rbp+57h+hMem]; hMem
0x18000380a  test    rcx, rcx
0x18000380d  jnz     short loc_180003844
0x18000380f  mov     rcx, [rbp+57h+arg_18]; hMem
0x180003813  test    rcx, rcx
0x180003816  jnz     short loc_18000384C
0x180003818  lea     rcx, [rbp+57h+var_68]; this
0x18000381c  call    ??1UnifiedStoreCursorLocation@@QEAA@XZ; UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation(void)
0x180003821  lea     rcx, [rbp+57h+var_A8]; this
0x180003825  call    ?close@auto_JET_TABLEID@@QEAAJXZ; auto_JET_TABLEID::close(void)
0x18000382a  test    eax, eax
0x18000382c  js      loc_1800039D1
0x180003832  xor     eax, eax
0x180003834  add     rsp, 0C8h
0x18000383b  pop     r15
0x18000383d  pop     r14
0x18000383f  pop     rdi
0x180003840  pop     rsi
0x180003841  pop     rbx
0x180003842  pop     rbp
0x180003843  retn
0x180003844  call    cs:__imp_LocalFree
0x18000384a  jmp     short loc_18000380F
0x18000384c  call    cs:__imp_LocalFree
0x180003852  jmp     short loc_180003818
0x180003854  xor     edx, edx; grbit
0x180003856  mov     rcx, rsi; sesid
0x180003859  call    cs:__imp_JetRollback
0x18000385f  test    eax, eax
0x180003861  jns     short loc_180003806
0x180003863  mov     ecx, eax; int
0x180003865  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18000386a  mov     r9d, 1B3h
0x180003870  mov     r8, rbx
0x180003873  xor     edx, edx
0x180003875  mov     ecx, eax
0x180003877  call    Log_UnistoreHREvent_0
0x18000387c  jmp     short loc_180003806
0x18000387e  cmp     dword ptr [rcx+8], 0
0x180003882  jz      loc_18000366D
0x180003888  test    rcx, rcx
0x18000388b  jz      short loc_180003893
0x18000388d  call    cs:__imp_LocalFree
0x180003893  lea     rcx, [rbp+57h+var_68]; this
0x180003897  call    ??1UnifiedStoreCursorLocation@@QEAA@XZ; UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation(void)
0x18000389c  lea     rcx, [rbp+57h+var_A8]; this
0x1800038a0  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800038a5  jmp     short loc_180003832
0x1800038a7  lea     rcx, [rbp+57h+var_B8]; this
0x1800038ab  call    ?Rollback@auto_JET_TRANSACTION@@QEAAXXZ; auto_JET_TRANSACTION::Rollback(void)
0x1800038b0  test    edi, edi
0x1800038b2  jns     short loc_18000390D
0x1800038b4  mov     ecx, edi; int
0x1800038b6  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800038bb  mov     ebx, eax
0x1800038bd  mov     r9d, 15Bh
0x1800038c3  xor     edx, edx
0x1800038c5  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800038cc  mov     ecx, eax
0x1800038ce  call    Log_UnistoreHREvent_0
0x1800038d3  lea     rcx, [rbp+57h+var_B8]; this
0x1800038d7  call    ??1auto_JET_TRANSACTION@@QEAA@XZ; auto_JET_TRANSACTION::~auto_JET_TRANSACTION(void)
0x1800038dc  lea     rcx, [rbp+57h+hMem]
0x1800038e0  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x1800038e5  mov     rcx, [rbp+57h+arg_18]; hMem
0x1800038e9  test    rcx, rcx
0x1800038ec  jz      short loc_1800038F4
0x1800038ee  call    cs:__imp_LocalFree
0x1800038f4  lea     rcx, [rbp+57h+var_68]; this
0x1800038f8  call    ??1UnifiedStoreCursorLocation@@QEAA@XZ; UnifiedStoreCursorLocation::~UnifiedStoreCursorLocation(void)
0x1800038fd  lea     rcx, [rbp+57h+var_A8]; this
0x180003901  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x180003906  mov     eax, ebx
0x180003908  jmp     loc_180003834
0x18000390d  mov     r15d, dword ptr [rbp+57h+var_B0+4]
0x180003911  mov     eax, dword ptr [rbp+57h+var_B0]
0x180003914  mov     rsi, [rbp+57h+var_B8]
0x180003918  jmp     loc_1800037AE
0x18000391d  call    cs:__imp_LocalFree
0x180003923  jmp     loc_18000370A
0x180003928  mov     r8d, 19h
0x18000392e  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180003935  call    Log_AssertionEvent
0x18000393a  jmp     loc_1800035F9
0x18000393f  mov     r9d, 130h
0x180003945  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000394c  mov     edx, 1
0x180003951  mov     ecx, ebx
0x180003953  call    Log_UnistoreHREvent_0
0x180003958  jmp     short loc_1800038F4
0x18000395a  mov     r9d, 13Fh
0x180003960  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180003967  mov     edx, edi
0x180003969  mov     ecx, eax
0x18000396b  call    Log_UnistoreHREvent_0
0x180003970  jmp     loc_1800038E5
0x180003975  mov     r9d, 148h
0x18000397b  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180003982  mov     edx, edi
0x180003984  mov     ecx, eax
0x180003986  call    Log_UnistoreHREvent_0
0x18000398b  jmp     loc_1800038DC
0x180003990  mov     ecx, eax; int
0x180003992  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180003997  mov     ecx, eax
0x180003999  lea     r8, aOnecoreuapBase_50; "onecoreuap\\base\\AppModel\\UserDataAcc"...
0x1800039a0  mov     r9d, 105h
0x1800039a6  xor     edx, edx
0x1800039a8  call    Log_UnistoreHREvent_0
0x1800039ad  jmp     loc_180003724
0x1800039b2  mov     r9d, 158h
0x1800039b8  mov     edx, edi
0x1800039ba  jmp     loc_1800038C5
0x1800039bf  mov     ecx, edi; int
0x1800039c1  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800039c6  mov     r9d, 1AFh
0x1800039cc  jmp     loc_180003870
0x1800039d1  mov     ecx, eax; int
0x1800039d3  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800039d8  mov     ecx, eax
0x1800039da  mov     r9d, 105h
0x1800039e0  mov     r8, rbx
0x1800039e3  xor     edx, edx
0x1800039e5  call    Log_UnistoreHREvent_0
0x1800039ea  jmp     loc_180003832
```
