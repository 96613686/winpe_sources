# UpdateCallHistoryItemFromUdmProperties(UdmObjectId const &,CallHistoryDataSession *,ulong,UdmPropertyValue *)

- ea: `0x1800e2aec`
- end: `0x1800e2f50`
- name: `?UpdateCallHistoryItemFromUdmProperties@@YAJAEBUUdmObjectId@@PEAVCallHistoryDataSession@@KPEAUUdmPropertyValue@@@Z`
- size: `1124`
- prototype: `int(const struct UdmObjectId *, struct CallHistoryDataSession *, unsigned int, struct UdmPropertyValue *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e1468`

## callees

- `0x1800049f0`
- `0x180008f0c`
- `0x18000e1f8`
- `0x180012988`
- `0x18003bf04`
- `0x18005e048`
- `0x18006b13c`
- `0x180075f98`
- `0x1800765d0`
- `0x180076604`
- `0x180076664`
- `0x18008eb80`
- `0x1800a0174`
- `0x1800a1270`
- `0x1800a1568`
- `0x1800a55ac`
- `0x1800d8b0c`
- `0x1800da0d0`
- `0x1800dbc30`
- `0x1800e1380`
- `0x1800e2758`
- `0x1800e2aec`
- `0x18012c76a`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x1800e2bf9`
- `ESENT!JetOpenTableA` at `0x1800e2bf9`
- `ESENT!JetSetColumns` at `0x1800e2d2b`
- `ESENT!JetSetColumns` at `0x1800e2d2b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800e2c24`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800e2c24`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e2c38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e2c38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e2c2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e2c2d`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x1800e2c15`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x1800e2c15`

## string_xrefs

- `0x1800e2d06`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800e2b95`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800e2d9f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800e2ea9`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800e2efc`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`

## pseudocode

```c
__int64 __fastcall UpdateCallHistoryItemFromUdmProperties(
        const struct UdmObjectId *a1,
        DatabaseVolumeSession **a2,
        __int64 a3,
        struct UdmPropertyValue *a4)
{
  __int64 v6; // xmm0_8
  int JetUpdateColumnsFromUdmProperties; // eax
  unsigned int v8; // edi
  __int64 v9; // r9
  JET_SESID v10; // rcx
  JET_DBID v11; // edx
  RTL_SRWLOCK *v12; // rdi
  JET_ERR v13; // eax
  unsigned int v14; // edx
  DatabaseVolumeSession *v15; // rax
  int v16; // eax
  int v17; // r8d
  DatabaseVolumeSession *v18; // rcx
  int v19; // ecx
  __int64 v20; // rcx
  JET_ERR v21; // eax
  unsigned __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // xmm0_8
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // rcx
  unsigned int HresultFromJetError; // ebx
  __int64 v30; // [rsp+40h] [rbp-79h] BYREF
  RTL_SRWLOCK *v31; // [rsp+48h] [rbp-71h]
  JET_SESID sesid; // [rsp+50h] [rbp-69h] BYREF
  JET_TABLEID tableid; // [rsp+58h] [rbp-61h] BYREF
  unsigned int csetcolumn[2]; // [rsp+60h] [rbp-59h] BYREF
  int v35; // [rsp+68h] [rbp-51h]
  DatabaseVolumeSession *v36; // [rsp+70h] [rbp-49h] BYREF
  __int128 v37; // [rsp+78h] [rbp-41h]
  __int64 v38; // [rsp+88h] [rbp-31h]
  DatabaseVolumeSession *v39; // [rsp+90h] [rbp-29h]
  JET_TABLEID v40; // [rsp+98h] [rbp-21h]
  int v41; // [rsp+A0h] [rbp-19h]
  JET_SETCOLUMN *psetcolumn[3]; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v43[3]; // [rsp+D8h] [rbp+1Fh] BYREF
  unsigned int v44; // [rsp+120h] [rbp+67h] BYREF

  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(psetcolumn);
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v43);
  v6 = *(_QWORD *)a1;
  v35 = *((_DWORD *)a1 + 2);
  *(_QWORD *)csetcolumn = v6;
  JetUpdateColumnsFromUdmProperties = GenerateJetUpdateColumnsFromUdmProperties(
                                        (struct CallHistoryDataSession *)a2,
                                        (__int64)psetcolumn,
                                        (__int64)v43);
  v8 = JetUpdateColumnsFromUdmProperties;
  if ( JetUpdateColumnsFromUdmProperties < 0 )
  {
    v9 = 4273;
LABEL_5:
    Log_HREvent(
      (unsigned int)JetUpdateColumnsFromUdmProperties,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      v9);
    goto LABEL_37;
  }
  csetcolumn[0] = 0;
  JetUpdateColumnsFromUdmProperties = ULongLongToULong(
                                        0xCCCCCCCCCCCCCCCDuLL * (((char *)psetcolumn[1] - (char *)psetcolumn[0]) >> 3),
                                        csetcolumn);
  v8 = JetUpdateColumnsFromUdmProperties;
  if ( JetUpdateColumnsFromUdmProperties < 0 )
  {
    v9 = 4276;
    goto LABEL_5;
  }
  v10 = (JET_SESID)a2[256];
  v11 = *((_DWORD *)a2 + 514);
  v12 = (RTL_SRWLOCK *)((char *)a2[255] + 120);
  v31 = v12;
  v30 = 0;
  sesid = v10;
  tableid = -1;
  v13 = JetOpenTableA(v10, v11, "CallHistory", 0, 0, 8u, &tableid);
  if ( v13 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v13);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      4287);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v30);
    utl::vector<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::_Uninit(v43);
    utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(psetcolumn);
    return HresultFromJetError;
  }
  while ( 1 )
  {
    if ( HIDWORD(v30) >= 2 )
    {
      AcquireSRWLockExclusive(v12);
      LODWORD(v30) = 2;
    }
    else
    {
      if ( !TryAcquireSRWLockShared(v12) )
      {
        Sleep(0x64u);
        AcquireSRWLockShared(v12);
      }
      LODWORD(v30) = 1;
    }
    v15 = a2[256];
    *(_QWORD *)&v37 = tableid;
    v40 = tableid;
    v36 = v15;
    *((_QWORD *)&v37 + 1) = v15;
    v38 = 0;
    v39 = v15;
    v41 = 0;
    v16 = UpdateContext::Start((UpdateContext *)&v36, v14);
    v8 = v16;
    if ( v16 < 0 )
    {
      v26 = 4294;
      goto LABEL_33;
    }
    v18 = a2[256];
    v44 = 0;
    v16 = SeekIndexToKey<unsigned long>((_DWORD)v18, tableid, v17, (int)a1 + 8, (__int64)&v44, 0);
    v8 = v16;
    if ( v16 < 0 )
    {
      v26 = 4302;
LABEL_33:
      v27 = 1;
      goto LABEL_34;
    }
    if ( !v44 )
    {
      if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10) != 0 )
        McTemplateU0pqq_EventWriteTransfer(
          v19,
          (unsigned int)UpdateCallNotFound,
          (_DWORD)a2,
          *((_DWORD *)a1 + 1),
          *((_DWORD *)a1 + 2));
      v8 = -2147023728;
      v26 = 4307;
      v28 = 2147943568LL;
      v27 = 0;
      goto LABEL_35;
    }
    v44 = 0;
    v16 = UpdateContext::MaybePrepare((UpdateContext *)&v36, 2u, (int *)&v44);
    v8 = v16;
    if ( v16 < 0 )
    {
      v26 = 4312;
      goto LABEL_33;
    }
    if ( !v44 )
      break;
    BackoffContext::NeedsBackoff((BackoffContext *)&v30);
    UpdateContext::~UpdateContext((UpdateContext *)&v36);
    BackoffContext::Unlock((BackoffContext *)&v30);
    if ( (_DWORD)v30 )
      Log_AssertionEvent_2(
        v20,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        2208);
    v12 = v31;
  }
  v21 = JetSetColumns(sesid, tableid, psetcolumn[0], csetcolumn[0]);
  if ( v21 < 0 )
  {
    v16 = MakeHresultFromJetError(v21);
    v8 = v16;
    v26 = 4320;
    v27 = 0;
LABEL_34:
    v28 = (unsigned int)v16;
LABEL_35:
    Log_HREvent(
      v28,
      v27,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      v26);
    UpdateContext::~UpdateContext((UpdateContext *)&v36);
    BackoffContext::Unlock((BackoffContext *)&v30);
    goto LABEL_36;
  }
  v16 = UpdateContext::CommitUpdate((UpdateContext *)&v36, 1u);
  v8 = v16;
  if ( v16 < 0 )
  {
    v26 = 4322;
    goto LABEL_33;
  }
  UpdateContext::~UpdateContext((UpdateContext *)&v36);
  BackoffContext::Unlock((BackoffContext *)&v30);
  v22 = (unsigned __int64)a2[256];
  *(_QWORD *)csetcolumn = 0;
  v44 = 1114116;
  v23 = ReadCallEntryProps(
          (struct CallHistoryDataSession *)a2,
          v22,
          tableid,
          1u,
          &v44,
          (struct UdmPropertyValue **)csetcolumn);
  v8 = v23;
  if ( v23 >= 0 )
  {
    memset_0(&v36, 0, 0x48u);
    v24 = *(_QWORD *)a1;
    HIDWORD(v37) = *((_DWORD *)a1 + 2);
    LODWORD(v36) = 1;
    LODWORD(v37) = 2;
    *(_QWORD *)((char *)&v37 + 4) = v24;
    v38 = *(_QWORD *)(*(_QWORD *)csetcolumn + 8LL);
    DatabaseVolumeSession::PushNotify(a2[255], (const struct UdmNotifyStructure *)&v36);
    CallHistoryDataSession::FlushUpdates((CallHistoryDataSession *)a2);
    auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(csetcolumn);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
    BackoffContext::Unlock((BackoffContext *)&v30);
    utl::vector<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::_Uninit(v43);
    utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(psetcolumn);
    return 0;
  }
  Log_HREvent(
    (unsigned int)v23,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
    4338);
  auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(csetcolumn);
LABEL_36:
  auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
  BackoffContext::Unlock((BackoffContext *)&v30);
LABEL_37:
  utl::vector<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::_Uninit(v43);
  utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(psetcolumn);
  return v8;
}

```

## disassembly

```asm
0x1800e2aec  mov     [rsp-8+arg_8], rbx
0x1800e2af1  mov     [rsp-8+arg_10], rsi
0x1800e2af6  push    rbp
0x1800e2af7  push    rdi
0x1800e2af8  push    r12
0x1800e2afa  push    r14
0x1800e2afc  push    r15
0x1800e2afe  lea     rbp, [rsp-37h]
0x1800e2b03  sub     rsp, 0F0h
0x1800e2b0a  mov     r15, rcx
0x1800e2b0d  mov     rsi, rdx
0x1800e2b10  lea     rcx, [rbp+57h+psetcolumn]
0x1800e2b14  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800e2b19  lea     rcx, [rbp+57h+var_38]
0x1800e2b1d  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800e2b22  mov     eax, [r15+8]
0x1800e2b26  lea     rdx, [rbp+57h+csetcolumn]
0x1800e2b2a  movsd   xmm0, qword ptr [r15]
0x1800e2b2f  mov     rcx, rsi; struct CallHistoryDataSession *
0x1800e2b32  mov     [rbp+57h+var_A8], eax
0x1800e2b35  lea     rax, [rbp+57h+var_38]
0x1800e2b39  mov     qword ptr [rsp+110h+grbit], rax; __int64
0x1800e2b3e  lea     rax, [rbp+57h+psetcolumn]
0x1800e2b42  mov     qword ptr [rsp+110h+cbParameters], rax; __int64
0x1800e2b47  movsd   qword ptr [rbp+57h+csetcolumn], xmm0
0x1800e2b4c  call    ?GenerateJetUpdateColumnsFromUdmProperties@@YAJPEAVCallHistoryDataSession@@UUdmObjectId@@KPEAUUdmPropertyValue@@PEAV?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@utl@@@utl@@PEAV?$vector@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@V?$allocator@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@utl@@@5@@Z; GenerateJetUpdateColumnsFromUdmProperties(CallHistoryDataSession *,UdmObjectId,ulong,UdmPropertyValue *,utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>> *,utl::vector<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>>> *)
0x1800e2b51  xor     r12d, r12d
0x1800e2b54  mov     edi, eax
0x1800e2b56  test    eax, eax
0x1800e2b58  jns     short loc_1800E2B62
0x1800e2b5a  mov     r9d, 10B1h
0x1800e2b60  jmp     short loc_1800E2B95
0x1800e2b62  mov     rcx, [rbp+57h+var_48]
0x1800e2b66  lea     rdx, [rbp+57h+csetcolumn]; unsigned int *
0x1800e2b6a  sub     rcx, [rbp+57h+psetcolumn]
0x1800e2b6e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800e2b78  sar     rcx, 3
0x1800e2b7c  imul    rcx, rax; unsigned __int64
0x1800e2b80  mov     [rbp+57h+csetcolumn], r12d
0x1800e2b84  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800e2b89  mov     edi, eax
0x1800e2b8b  test    eax, eax
0x1800e2b8d  jns     short loc_1800E2BAD
0x1800e2b8f  mov     r9d, 10B4h
0x1800e2b95  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e2b9c  mov     edx, 1
0x1800e2ba1  mov     ecx, eax
0x1800e2ba3  call    Log_HREvent
0x1800e2ba8  jmp     loc_1800E2ED9
0x1800e2bad  mov     rdi, [rsi+7F8h]
0x1800e2bb4  lea     rax, [rbp+57h+tableid]
0x1800e2bb8  mov     rcx, [rsi+800h]; sesid
0x1800e2bbf  lea     r8, ?UdmTableName_CallHistory@@3QBDB; "CallHistory"
0x1800e2bc6  mov     edx, [rsi+808h]; dbid
0x1800e2bcc  add     rdi, 78h ; 'x'
0x1800e2bd0  mov     [rsp+110h+ptableid], rax; ptableid
0x1800e2bd5  xor     r9d, r9d; pvParameters
0x1800e2bd8  mov     [rsp+110h+grbit], 8; grbit
0x1800e2be0  mov     [rbp+57h+var_C8], rdi
0x1800e2be4  mov     [rsp+110h+cbParameters], r12d; cbParameters
0x1800e2be9  mov     [rbp+57h+var_D0], r12
0x1800e2bed  mov     [rbp+57h+sesid], rcx
0x1800e2bf1  mov     [rbp+57h+tableid], 0FFFFFFFFFFFFFFFFh
0x1800e2bf9  call    cs:__imp_JetOpenTableA
0x1800e2bff  test    eax, eax
0x1800e2c01  js      loc_1800E2EEF
0x1800e2c07  mov     ebx, 1
0x1800e2c0c  cmp     dword ptr [rbp+57h+var_D0+4], 2
0x1800e2c10  mov     rcx, rdi; SRWLock
0x1800e2c13  jnb     short loc_1800E2C38
0x1800e2c15  call    cs:__imp_TryAcquireSRWLockShared
0x1800e2c1b  test    al, al
0x1800e2c1d  jnz     short loc_1800E2C33
0x1800e2c1f  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800e2c24  call    cs:__imp_Sleep
0x1800e2c2a  mov     rcx, rdi; SRWLock
0x1800e2c2d  call    cs:__imp_AcquireSRWLockShared
0x1800e2c33  mov     dword ptr [rbp+57h+var_D0], ebx
0x1800e2c36  jmp     short loc_1800E2C45
0x1800e2c38  call    cs:__imp_AcquireSRWLockExclusive
0x1800e2c3e  mov     dword ptr [rbp+57h+var_D0], 2
0x1800e2c45  mov     rcx, [rbp+57h+tableid]
0x1800e2c49  mov     rax, [rsi+800h]
0x1800e2c50  mov     [rbp+57h+var_98], rcx
0x1800e2c54  mov     [rbp+57h+var_78], rcx
0x1800e2c58  lea     rcx, [rbp+57h+var_A0]; this
0x1800e2c5c  mov     [rbp+57h+var_A0], rax
0x1800e2c60  mov     [rbp+57h+var_90], rax
0x1800e2c64  mov     [rbp+57h+var_88], r12
0x1800e2c68  mov     [rbp+57h+var_80], rax
0x1800e2c6c  mov     [rbp+57h+var_70], r12d
0x1800e2c70  call    ?Start@UpdateContext@@QEAAJK@Z; UpdateContext::Start(ulong)
0x1800e2c75  mov     edi, eax
0x1800e2c77  test    eax, eax
0x1800e2c79  js      loc_1800E2E9F
0x1800e2c7f  mov     rdx, [rbp+57h+tableid]
0x1800e2c83  lea     rax, [rbp+57h+arg_0]
0x1800e2c87  mov     rcx, [rsi+800h]
0x1800e2c8e  lea     r9, [r15+8]
0x1800e2c92  mov     [rsp+110h+grbit], r12d
0x1800e2c97  mov     qword ptr [rsp+110h+cbParameters], rax
0x1800e2c9c  mov     [rbp+57h+arg_0], r12d
0x1800e2ca0  call    ??$SeekIndexToKey@K@@YAJ_K0PEBUIndexDefinition@@AEBKPEAHK@Z; SeekIndexToKey<ulong>(unsigned __int64,unsigned __int64,IndexDefinition const *,ulong const &,int *,ulong)
0x1800e2ca5  mov     edi, eax
0x1800e2ca7  test    eax, eax
0x1800e2ca9  js      loc_1800E2E97
0x1800e2caf  cmp     [rbp+57h+arg_0], r12d
0x1800e2cb3  jz      loc_1800E2E62
0x1800e2cb9  lea     r8, [rbp+57h+arg_0]; int *
0x1800e2cbd  mov     [rbp+57h+arg_0], r12d
0x1800e2cc1  mov     edx, 2; unsigned int
0x1800e2cc6  lea     rcx, [rbp+57h+var_A0]; this
0x1800e2cca  call    ?MaybePrepare@UpdateContext@@QEAAJKPEAH@Z; UpdateContext::MaybePrepare(ulong,int *)
0x1800e2ccf  mov     edi, eax
0x1800e2cd1  test    eax, eax
0x1800e2cd3  js      loc_1800E2E5A
0x1800e2cd9  cmp     [rbp+57h+arg_0], r12d
0x1800e2cdd  jz      short loc_1800E2D1B
0x1800e2cdf  lea     rcx, [rbp+57h+var_D0]; this
0x1800e2ce3  call    ?NeedsBackoff@BackoffContext@@QEAAXXZ; BackoffContext::NeedsBackoff(void)
0x1800e2ce8  lea     rcx, [rbp+57h+var_A0]; this
0x1800e2cec  call    ??1UpdateContext@@QEAA@XZ; UpdateContext::~UpdateContext(void)
0x1800e2cf1  lea     rcx, [rbp+57h+var_D0]; this
0x1800e2cf5  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800e2cfa  cmp     dword ptr [rbp+57h+var_D0], r12d
0x1800e2cfe  jz      short loc_1800E2D12
0x1800e2d00  mov     r8d, 8A0h
0x1800e2d06  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e2d0d  call    Log_AssertionEvent_2
0x1800e2d12  mov     rdi, [rbp+57h+var_C8]
0x1800e2d16  jmp     loc_1800E2C0C
0x1800e2d1b  mov     r9d, [rbp+57h+csetcolumn]; csetcolumn
0x1800e2d1f  mov     r8, [rbp+57h+psetcolumn]; psetcolumn
0x1800e2d23  mov     rdx, [rbp+57h+tableid]; tableid
0x1800e2d27  mov     rcx, [rbp+57h+sesid]; sesid
0x1800e2d2b  call    cs:__imp_JetSetColumns
0x1800e2d31  test    eax, eax
0x1800e2d33  js      loc_1800E2E47
0x1800e2d39  mov     edx, ebx; unsigned int
0x1800e2d3b  lea     rcx, [rbp+57h+var_A0]; this
0x1800e2d3f  call    ?CommitUpdate@UpdateContext@@QEAAJK@Z; UpdateContext::CommitUpdate(ulong)
0x1800e2d44  mov     edi, eax
0x1800e2d46  test    eax, eax
0x1800e2d48  js      loc_1800E2E3F
0x1800e2d4e  lea     rcx, [rbp+57h+var_A0]; this
0x1800e2d52  call    ??1UpdateContext@@QEAA@XZ; UpdateContext::~UpdateContext(void)
0x1800e2d57  lea     rcx, [rbp+57h+var_D0]; this
0x1800e2d5b  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800e2d60  mov     r8, [rbp+57h+tableid]; unsigned __int64
0x1800e2d64  lea     rax, [rbp+57h+csetcolumn]
0x1800e2d68  mov     rdx, [rsi+800h]; unsigned __int64
0x1800e2d6f  mov     r9d, ebx; unsigned int
0x1800e2d72  mov     qword ptr [rsp+110h+grbit], rax; struct UdmPropertyValue **
0x1800e2d77  mov     rcx, rsi; struct CallHistoryDataSession *
0x1800e2d7a  lea     rax, [rbp+57h+arg_0]
0x1800e2d7e  mov     qword ptr [rbp+57h+csetcolumn], r12
0x1800e2d82  mov     qword ptr [rsp+110h+cbParameters], rax; unsigned int *
0x1800e2d87  mov     [rbp+57h+arg_0], 110004h
0x1800e2d8e  call    ?ReadCallEntryProps@@YAJPEAVCallHistoryDataSession@@_K1KQEBKPEAPEAUUdmPropertyValue@@@Z; ReadCallEntryProps(CallHistoryDataSession *,unsigned __int64,unsigned __int64,ulong,ulong const * const,UdmPropertyValue * *)
0x1800e2d93  mov     edi, eax
0x1800e2d95  test    eax, eax
0x1800e2d97  jns     short loc_1800E2DBD
0x1800e2d99  mov     r9d, 10F2h
0x1800e2d9f  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e2da6  mov     edx, ebx
0x1800e2da8  mov     ecx, eax
0x1800e2daa  call    Log_HREvent
0x1800e2daf  lea     rcx, [rbp+57h+csetcolumn]
0x1800e2db3  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800e2db8  jmp     loc_1800E2EC7
0x1800e2dbd  xor     edx, edx; Val
0x1800e2dbf  lea     rcx, [rbp+57h+var_A0]; void *
0x1800e2dc3  lea     r8d, [rdx+48h]; Size
0x1800e2dc7  call    memset_0
0x1800e2dcc  mov     eax, [r15+8]
0x1800e2dd0  lea     rdx, [rbp+57h+var_A0]; struct UdmNotifyStructure *
0x1800e2dd4  movsd   xmm0, qword ptr [r15]
0x1800e2dd9  mov     dword ptr [rbp+57h+var_90+4], eax
0x1800e2ddc  mov     rax, qword ptr [rbp+57h+csetcolumn]
0x1800e2de0  mov     dword ptr [rbp+57h+var_A0], ebx
0x1800e2de3  mov     dword ptr [rbp+57h+var_98], 2
0x1800e2dea  movsd   [rbp+57h+var_98+4], xmm0
0x1800e2def  mov     rcx, [rax+8]
0x1800e2df3  mov     [rbp+57h+var_88], rcx
0x1800e2df7  mov     rcx, [rsi+7F8h]; this
0x1800e2dfe  call    ?PushNotify@DatabaseVolumeSession@@QEAAXAEBUUdmNotifyStructure@@@Z; DatabaseVolumeSession::PushNotify(UdmNotifyStructure const &)
0x1800e2e03  mov     rcx, rsi; this
0x1800e2e06  call    ?FlushUpdates@CallHistoryDataSession@@QEAAXXZ; CallHistoryDataSession::FlushUpdates(void)
0x1800e2e0b  lea     rcx, [rbp+57h+csetcolumn]
0x1800e2e0f  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800e2e14  lea     rcx, [rbp+57h+sesid]; this
0x1800e2e18  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800e2e1d  lea     rcx, [rbp+57h+var_D0]; this
0x1800e2e21  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800e2e26  lea     rcx, [rbp+57h+var_38]
0x1800e2e2a  call    ?_Uninit@?$vector@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@V?$allocator@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@utl@@@utl@@AEAAXXZ; utl::vector<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::_Uninit(void)
0x1800e2e2f  lea     rcx, [rbp+57h+psetcolumn]
0x1800e2e33  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x1800e2e38  xor     eax, eax
0x1800e2e3a  jmp     loc_1800E2F34
0x1800e2e3f  mov     r9d, 10E2h
0x1800e2e45  jmp     short loc_1800E2EA5
0x1800e2e47  mov     ecx, eax; int
0x1800e2e49  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800e2e4e  mov     edi, eax
0x1800e2e50  mov     r9d, 10E0h
0x1800e2e56  xor     edx, edx
0x1800e2e58  jmp     short loc_1800E2EA7
0x1800e2e5a  mov     r9d, 10D8h
0x1800e2e60  jmp     short loc_1800E2EA5
0x1800e2e62  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits, 10h
0x1800e2e69  jz      short loc_1800E2E86
0x1800e2e6b  mov     eax, [r15+8]
0x1800e2e6f  lea     rdx, UpdateCallNotFound
0x1800e2e76  mov     r9d, [r15+4]
0x1800e2e7a  mov     r8, rsi
0x1800e2e7d  mov     [rsp+110h+cbParameters], eax
0x1800e2e81  call    McTemplateU0pqq_EventWriteTransfer
0x1800e2e86  mov     edi, 80070490h
0x1800e2e8b  mov     r9d, 10D3h
0x1800e2e91  mov     ecx, edi
0x1800e2e93  xor     edx, edx
0x1800e2e95  jmp     short loc_1800E2EA9
0x1800e2e97  mov     r9d, 10CEh
0x1800e2e9d  jmp     short loc_1800E2EA5
0x1800e2e9f  mov     r9d, 10C6h
0x1800e2ea5  mov     edx, ebx
0x1800e2ea7  mov     ecx, eax
0x1800e2ea9  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e2eb0  call    Log_HREvent
0x1800e2eb5  lea     rcx, [rbp+57h+var_A0]; this
0x1800e2eb9  call    ??1UpdateContext@@QEAA@XZ; UpdateContext::~UpdateContext(void)
0x1800e2ebe  lea     rcx, [rbp+57h+var_D0]; this
0x1800e2ec2  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800e2ec7  lea     rcx, [rbp+57h+sesid]; this
0x1800e2ecb  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800e2ed0  lea     rcx, [rbp+57h+var_D0]; this
0x1800e2ed4  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800e2ed9  lea     rcx, [rbp+57h+var_38]
0x1800e2edd  call    ?_Uninit@?$vector@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@V?$allocator@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@utl@@@utl@@AEAAXXZ; utl::vector<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::_Uninit(void)
0x1800e2ee2  lea     rcx, [rbp+57h+psetcolumn]
0x1800e2ee6  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x1800e2eeb  mov     eax, edi
0x1800e2eed  jmp     short loc_1800E2F34
0x1800e2eef  mov     ecx, eax; int
0x1800e2ef1  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800e2ef6  mov     r9d, 10BFh
0x1800e2efc  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800e2f03  xor     edx, edx
0x1800e2f05  mov     ecx, eax
0x1800e2f07  mov     ebx, eax
0x1800e2f09  call    Log_HREvent
0x1800e2f0e  lea     rcx, [rbp+57h+sesid]; this
0x1800e2f12  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800e2f17  lea     rcx, [rbp+57h+var_D0]; this
0x1800e2f1b  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800e2f20  lea     rcx, [rbp+57h+var_38]
0x1800e2f24  call    ?_Uninit@?$vector@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@V?$allocator@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@utl@@@utl@@AEAAXXZ; utl::vector<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::_Uninit(void)
0x1800e2f29  lea     rcx, [rbp+57h+psetcolumn]
0x1800e2f2d  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x1800e2f32  mov     eax, ebx
0x1800e2f34  lea     r11, [rsp+110h+var_20]
0x1800e2f3c  mov     rbx, [r11+38h]
0x1800e2f40  mov     rsi, [r11+40h]
0x1800e2f44  mov     rsp, r11
0x1800e2f47  pop     r15
0x1800e2f49  pop     r14
0x1800e2f4b  pop     r12
0x1800e2f4d  pop     rdi
0x1800e2f4e  pop     rbp
0x1800e2f4f  retn
```
