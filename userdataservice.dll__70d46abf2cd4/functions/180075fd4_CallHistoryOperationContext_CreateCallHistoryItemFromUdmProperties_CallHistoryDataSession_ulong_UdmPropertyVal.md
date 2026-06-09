# CallHistoryOperationContext::CreateCallHistoryItemFromUdmProperties(CallHistoryDataSession *,ulong,UdmPropertyValue *,UdmObjectId *)

- ea: `0x180075fd4`
- end: `0x1800765c7`
- name: `?CreateCallHistoryItemFromUdmProperties@CallHistoryOperationContext@@AEAAJPEAVCallHistoryDataSession@@KPEAUUdmPropertyValue@@PEAUUdmObjectId@@@Z`
- size: `1523`
- prototype: `int(CallHistoryOperationContext *__hidden this, struct CallHistoryDataSession *, unsigned int, struct UdmPropertyValue *, struct UdmObjectId *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e1468`

## callees

- `0x1800049f0`
- `0x180008f0c`
- `0x18000e1f8`
- `0x18003bf04`
- `0x18005e048`
- `0x18005e1bc`
- `0x180066860`
- `0x18006f0a8`
- `0x180075f98`
- `0x180075fd4`
- `0x1800765d0`
- `0x180076604`
- `0x180076664`
- `0x180076fdc`
- `0x1800781f0`
- `0x1800977ac`
- `0x1800a1568`
- `0x1800d8624`
- `0x1800d8b0c`
- `0x1800dbc30`
- `0x1800deb88`
- `0x1800e1380`
- `0x1800e2758`
- `0x1800e3ea8`
- `0x1800e98c4`
- `0x180114cec`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x18007631f`
- `ESENT!JetOpenTableA` at `0x18007631f`
- `ESENT!JetSetColumns` at `0x1800763ea`
- `ESENT!JetSetColumns` at `0x1800763ea`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800761fb`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800761fb`

## string_xrefs

- `0x1800760a1`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800760ed`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18007613f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18007618d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800761d7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18007643d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180076059`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180076234`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180076336`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800763a4`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180076557`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`

## pseudocode

```c
__int64 __fastcall CallHistoryOperationContext::CreateCallHistoryItemFromUdmProperties(
        CallHistoryOperationContext *this,
        struct CallHistoryDataSession *a2,
        unsigned int a3,
        struct UdmPropertyValue *a4,
        struct UdmObjectId *a5)
{
  unsigned __int64 v6; // r12
  int JetUpdateColumnsFromUdmProperties; // eax
  __int64 HresultFromJetError; // rbx
  DatabaseVolumeSession *v10; // rcx
  __int64 v11; // rcx
  unsigned int Column; // esi
  DatabaseVolumeSession *v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // ebx
  __int64 ColumnIdInColumnsVector; // rax
  DatabaseVolumeSession *v17; // rcx
  const unsigned __int16 *v18; // r15
  __int64 v19; // rcx
  unsigned int v20; // ebx
  DatabaseVolumeSession *v21; // rcx
  __int64 v22; // rcx
  unsigned int v23; // ebx
  DatabaseVolumeSession *v24; // rcx
  __int64 v25; // rcx
  unsigned int v26; // ebx
  unsigned __int16 **v27; // rax
  int UniqueId; // eax
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rcx
  JET_DBID v32; // edx
  JET_ERR v33; // eax
  unsigned int v34; // edx
  unsigned __int64 v35; // rax
  int v36; // eax
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // rcx
  JET_ERR v40; // eax
  DatabaseVolumeSession *v41; // rcx
  __int64 v42; // rcx
  unsigned int v43; // ebx
  int v44; // eax
  unsigned int v45; // ebx
  struct UdmPropertyValue *PropByUdmPropId; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 *v49; // rax
  int v50; // eax
  unsigned int cbParameters; // [rsp+20h] [rbp-E0h]
  unsigned int ptableid; // [rsp+30h] [rbp-D0h]
  struct JET_RETINFO *v54; // [rsp+38h] [rbp-C8h]
  unsigned int csetcolumn; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  JET_SESID v57; // [rsp+50h] [rbp-B0h] BYREF
  JET_TABLEID v58; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v59; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v60; // [rsp+64h] [rbp-9Ch] BYREF
  int v61; // [rsp+68h] [rbp-98h] BYREF
  __int64 v62; // [rsp+70h] [rbp-90h] BYREF
  int v63; // [rsp+78h] [rbp-88h]
  JET_SETCOLUMN *psetcolumn[3]; // [rsp+80h] [rbp-80h] BYREF
  struct JET_SETCOLUMN sesid; // [rsp+98h] [rbp-68h] BYREF
  JET_TABLEID v66; // [rsp+C0h] [rbp-40h]
  int v67; // [rsp+C8h] [rbp-38h]
  __int64 v68[4]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v69[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v70; // [rsp+FCh] [rbp-4h]
  unsigned int v71; // [rsp+104h] [rbp+4h]
  __int64 v72[7]; // [rsp+108h] [rbp+8h] BYREF

  v6 = a3;
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(psetcolumn);
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v68);
  v62 = 0;
  v63 = 0;
  JetUpdateColumnsFromUdmProperties = GenerateJetUpdateColumnsFromUdmProperties(a2, (__int64)psetcolumn, (__int64)v68);
  LODWORD(HresultFromJetError) = JetUpdateColumnsFromUdmProperties;
  if ( JetUpdateColumnsFromUdmProperties < 0 )
  {
    Log_HREvent(
      (unsigned int)JetUpdateColumnsFromUdmProperties,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      4135);
    goto LABEL_62;
  }
  v10 = (DatabaseVolumeSession *)*((_QWORD *)a2 + 255);
  Block = 0;
  csetcolumn = 0;
  Column = DatabaseVolumeSession::FindColumnEx(v10, (const struct ColumnDefinition *)&off_180130F40, (int *)&csetcolumn);
  if ( !csetcolumn )
    Log_AssertionEvent_2(
      v11,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  if ( !FindColumnIdInColumnsVector(psetcolumn, Column) )
  {
    v13 = (DatabaseVolumeSession *)*((_QWORD *)a2 + 255);
    csetcolumn = 0;
    v15 = DatabaseVolumeSession::FindColumnEx(v13, (const struct ColumnDefinition *)&off_180130CA0, (int *)&csetcolumn);
    if ( !csetcolumn )
      Log_AssertionEvent_2(
        v14,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        203);
    ColumnIdInColumnsVector = FindColumnIdInColumnsVector(psetcolumn, v15);
    v17 = (DatabaseVolumeSession *)*((_QWORD *)a2 + 255);
    v62 = 0;
    v18 = (const unsigned __int16 *)ColumnIdInColumnsVector;
    csetcolumn = 0;
    v20 = DatabaseVolumeSession::FindColumnEx(v17, (const struct ColumnDefinition *)&off_180130E80, (int *)&csetcolumn);
    if ( !csetcolumn )
      Log_AssertionEvent_2(
        v19,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        203);
    HresultFromJetError = FindColumnIdInColumnsVector(psetcolumn, v20);
    if ( !HresultFromJetError )
    {
      v21 = (DatabaseVolumeSession *)*((_QWORD *)a2 + 255);
      csetcolumn = 0;
      v23 = DatabaseVolumeSession::FindColumnEx(
              v21,
              (const struct ColumnDefinition *)&off_180130C60,
              (int *)&csetcolumn);
      if ( !csetcolumn )
        Log_AssertionEvent_2(
          v22,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
          203);
      HresultFromJetError = FindColumnIdInColumnsVector(psetcolumn, v23);
      if ( !HresultFromJetError )
      {
        v24 = (DatabaseVolumeSession *)*((_QWORD *)a2 + 255);
        csetcolumn = 0;
        v26 = DatabaseVolumeSession::FindColumnEx(
                v24,
                (const struct ColumnDefinition *)&off_180130C80,
                (int *)&csetcolumn);
        if ( !csetcolumn )
          Log_AssertionEvent_2(
            v25,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
            203);
        HresultFromJetError = FindColumnIdInColumnsVector(psetcolumn, v26);
        if ( !HresultFromJetError )
        {
          GetSystemTimePreciseAsFileTime(&v62);
          HresultFromJetError = (__int64)&v62;
        }
      }
    }
    v27 = (unsigned __int16 **)tlx::replace<unsigned short,&void tlx::_delete_array<unsigned short>(unsigned short *)>((__int64)&Block);
    UniqueId = GenerateUniqueId(v18, (const struct _FILETIME *)HresultFromJetError, v27);
    LODWORD(HresultFromJetError) = UniqueId;
    if ( UniqueId < 0 )
    {
      v29 = 4174;
LABEL_20:
      v30 = 1;
      v31 = (unsigned int)UniqueId;
LABEL_21:
      Log_HREvent(
        v31,
        v30,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
        v29);
      goto LABEL_22;
    }
    memset(&sesid, 0, sizeof(sesid));
    UniqueId = InitSetColumn(&sesid, Column, (const unsigned __int16 *)Block);
    LODWORD(HresultFromJetError) = UniqueId;
    if ( UniqueId < 0 )
    {
      v29 = 4179;
      goto LABEL_20;
    }
    if ( !(unsigned __int8)utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>>::_PushBackOne<JET_SETCOLUMN const &>(
                             psetcolumn,
                             &sesid) )
    {
      LODWORD(HresultFromJetError) = -2147024882;
      v29 = 4180;
      v31 = 2147942414LL;
      v30 = 0;
      goto LABEL_21;
    }
  }
  csetcolumn = 0;
  UniqueId = ULongLongToULong(
               0xCCCCCCCCCCCCCCCDuLL * (((char *)psetcolumn[1] - (char *)psetcolumn[0]) >> 3),
               &csetcolumn);
  LODWORD(HresultFromJetError) = UniqueId;
  if ( UniqueId < 0 )
  {
    v29 = 4184;
    goto LABEL_20;
  }
  v32 = *((_DWORD *)a2 + 514);
  v57 = *((_QWORD *)a2 + 256);
  v58 = -1;
  v33 = JetOpenTableA(v57, v32, "CallHistory", 0, 0, 8u, &v58);
  if ( v33 < 0 )
  {
    HresultFromJetError = (unsigned int)MakeHresultFromJetError(v33);
    Log_HREvent(
      HresultFromJetError,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      4196);
LABEL_32:
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v57);
LABEL_22:
    if ( Block )
      operator delete(Block);
    goto LABEL_62;
  }
  v35 = *((_QWORD *)a2 + 256);
  sesid.pvData = (const void *)v58;
  v66 = v58;
  *(_QWORD *)&sesid.columnid = v35;
  *(_OWORD *)&sesid.cbData = v35;
  *(_QWORD *)&sesid.err = v35;
  v67 = 0;
  v61 = 0;
  v36 = UpdateContext::Start((UpdateContext *)&sesid, v34);
  LODWORD(HresultFromJetError) = v36;
  if ( v36 < 0 )
  {
    v37 = 4203;
LABEL_35:
    v38 = 1;
LABEL_36:
    v39 = (unsigned int)v36;
LABEL_37:
    Log_HREvent(
      v39,
      v38,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      v37);
    UpdateContext::~UpdateContext((UpdateContext *)&sesid);
    goto LABEL_32;
  }
  v36 = UpdateContext::MaybePrepare((UpdateContext *)&sesid, 0, &v61);
  LODWORD(HresultFromJetError) = v36;
  if ( v36 < 0 )
  {
    v37 = 4204;
    goto LABEL_35;
  }
  v40 = JetSetColumns(*(JET_SESID *)&sesid.columnid, (JET_TABLEID)sesid.pvData, psetcolumn[0], csetcolumn);
  if ( v40 < 0 )
  {
    v36 = MakeHresultFromJetError(v40);
    v37 = 4206;
LABEL_42:
    LODWORD(HresultFromJetError) = v36;
    v38 = 0;
    goto LABEL_36;
  }
  v41 = (DatabaseVolumeSession *)*((_QWORD *)a2 + 255);
  v60 = 0;
  v59 = 0;
  csetcolumn = 0;
  v43 = DatabaseVolumeSession::FindColumnEx(
          v41,
          (const struct ColumnDefinition *)&UdmTableCols_CallHistory,
          (int *)&csetcolumn);
  if ( !csetcolumn )
    Log_AssertionEvent_2(
      v42,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v44 = CommsESE_JetRetrieveColumn(*((_QWORD *)a2 + 256), v58, v43, &v60, cbParameters, &v59, ptableid, v54);
  if ( v44 < 0 )
  {
    v36 = MakeHresultFromJetError(v44);
    v37 = 4220;
    goto LABEL_42;
  }
  v38 = 0;
  if ( v59 != 4 )
  {
    LODWORD(HresultFromJetError) = -2147418113;
    v37 = 4222;
    v39 = 2147549183LL;
    goto LABEL_37;
  }
  v36 = UpdateContext::CommitUpdate((UpdateContext *)&sesid, 0);
  LODWORD(HresultFromJetError) = v36;
  if ( v36 < 0 )
  {
    v37 = 4223;
    goto LABEL_35;
  }
  v45 = v60;
  *((_DWORD *)a5 + 2) = v60;
  *(_DWORD *)a5 = 0;
  *((_DWORD *)a5 + 1) = 1;
  memset_0(v69, 0, 0x48u);
  v70 = *(_QWORD *)a5;
  v69[0] = 1;
  v69[2] = 0;
  v71 = v45;
  PropByUdmPropId = FindPropByUdmPropId(v6, a4, 0x110004u);
  if ( !PropByUdmPropId || (*(_DWORD *)PropByUdmPropId & 0x100) != 0 )
    v49 = &qword_18013BD08;
  else
    v49 = (__int64 *)((char *)PropByUdmPropId + 8);
  v72[0] = *v49;
  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x20) != 0 )
    McTemplateU0qm_EventWriteTransfer(v48, v47, v45, v72);
  DatabaseVolumeSession::PushNotify(*((DatabaseVolumeSession **)a2 + 255), (const struct UdmNotifyStructure *)v69);
  v50 = TrimCallHistory(a2);
  if ( v50 < 0 )
    Log_HREvent(
      (unsigned int)v50,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      4252);
  UpdateContext::~UpdateContext((UpdateContext *)&sesid);
  auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v57);
  if ( Block )
    operator delete(Block);
  LODWORD(HresultFromJetError) = 0;
LABEL_62:
  utl::vector<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&void Udm::FreeUdmPropVal(UdmPropertyValue *)>>>::_Uninit(v68);
  utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(psetcolumn);
  return (unsigned int)HresultFromJetError;
}

```

## disassembly

```asm
0x180075fd4  mov     [rsp-8+arg_0], rbx
0x180075fd9  push    rbp
0x180075fda  push    rsi
0x180075fdb  push    rdi
0x180075fdc  push    r12
0x180075fde  push    r13
0x180075fe0  push    r14
0x180075fe2  push    r15
0x180075fe4  lea     rbp, [rsp-50h]
0x180075fe9  sub     rsp, 150h
0x180075ff0  mov     rax, cs:__security_cookie
0x180075ff7  xor     rax, rsp
0x180075ffa  mov     [rbp+80h+var_40], rax
0x180075ffe  mov     r14, [rbp+80h+arg_20]
0x180076005  lea     rcx, [rbp+80h+psetcolumn]
0x180076009  mov     r13, r9
0x18007600c  mov     r12d, r8d
0x18007600f  mov     rdi, rdx
0x180076012  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x180076017  lea     rcx, [rbp+80h+var_B0]
0x18007601b  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x180076020  xor     ecx, ecx
0x180076022  lea     rax, [rbp+80h+var_B0]
0x180076026  mov     qword ptr [rsp+180h+grbit], rax; __int64
0x18007602b  lea     rdx, [rsp+180h+var_110]
0x180076030  lea     rax, [rbp+80h+psetcolumn]
0x180076034  mov     [rsp+180h+var_110], rcx
0x180076039  mov     [rsp+180h+var_108], ecx
0x18007603d  mov     rcx, rdi; struct CallHistoryDataSession *
0x180076040  mov     qword ptr [rsp+180h+cbParameters], rax; __int64
0x180076045  call    ?GenerateJetUpdateColumnsFromUdmProperties@@YAJPEAVCallHistoryDataSession@@UUdmObjectId@@KPEAUUdmPropertyValue@@PEAV?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@utl@@@utl@@PEAV?$vector@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@V?$allocator@U?$auto_struct@UUdmPropertyValue@@$1?FreeUdmPropVal@Udm@@YAXPEAU1@@Z@@@utl@@@5@@Z; GenerateJetUpdateColumnsFromUdmProperties(CallHistoryDataSession *,UdmObjectId,ulong,UdmPropertyValue *,utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>> *,utl::vector<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>,utl::allocator<auto_struct<UdmPropertyValue,&Udm::FreeUdmPropVal(UdmPropertyValue *)>>> *)
0x18007604a  xor     r15d, r15d
0x18007604d  mov     ebx, eax
0x18007604f  test    eax, eax
0x180076051  jns     short loc_180076070
0x180076053  mov     r9d, 1027h
0x180076059  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180076060  lea     edx, [r15+1]
0x180076064  mov     ecx, eax
0x180076066  call    Log_HREvent
0x18007606b  jmp     loc_18007658C
0x180076070  mov     rcx, [rdi+7F8h]; this
0x180076077  lea     r8, [rsp+180h+csetcolumn]; int *
0x18007607c  lea     rdx, off_180130F40; struct ColumnDefinition *
0x180076083  mov     [rsp+180h+Block], r15
0x180076088  mov     [rsp+180h+csetcolumn], r15d
0x18007608d  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180076092  mov     esi, eax
0x180076094  cmp     [rsp+180h+csetcolumn], r15d
0x180076099  jnz     short loc_1800760AD
0x18007609b  mov     r8d, 0CBh
0x1800760a1  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800760a8  call    Log_AssertionEvent_2
0x1800760ad  mov     edx, esi
0x1800760af  lea     rcx, [rbp+80h+psetcolumn]
0x1800760b3  call    _FindColumnIdInColumnsVector
0x1800760b8  test    rax, rax
0x1800760bb  jnz     loc_1800762A9
0x1800760c1  mov     rcx, [rdi+7F8h]; this
0x1800760c8  lea     r8, [rsp+180h+csetcolumn]; int *
0x1800760cd  lea     rdx, off_180130CA0; struct ColumnDefinition *
0x1800760d4  mov     [rsp+180h+csetcolumn], r15d
0x1800760d9  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x1800760de  mov     ebx, eax
0x1800760e0  cmp     [rsp+180h+csetcolumn], r15d
0x1800760e5  jnz     short loc_1800760F9
0x1800760e7  mov     r8d, 0CBh
0x1800760ed  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800760f4  call    Log_AssertionEvent_2
0x1800760f9  mov     edx, ebx
0x1800760fb  lea     rcx, [rbp+80h+psetcolumn]
0x1800760ff  call    _FindColumnIdInColumnsVector
0x180076104  mov     rcx, [rdi+7F8h]; this
0x18007610b  lea     r8, [rsp+180h+csetcolumn]; int *
0x180076110  lea     rdx, off_180130E80; struct ColumnDefinition *
0x180076117  mov     [rsp+180h+var_110], 0
0x180076120  mov     r15, rax
0x180076123  mov     [rsp+180h+csetcolumn], 0
0x18007612b  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x180076130  cmp     [rsp+180h+csetcolumn], 0
0x180076135  mov     ebx, eax
0x180076137  jnz     short loc_18007614B
0x180076139  mov     r8d, 0CBh
0x18007613f  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180076146  call    Log_AssertionEvent_2
0x18007614b  mov     edx, ebx
0x18007614d  lea     rcx, [rbp+80h+psetcolumn]
0x180076151  call    _FindColumnIdInColumnsVector
0x180076156  mov     rbx, rax
0x180076159  test    rax, rax
0x18007615c  jnz     loc_180076206
0x180076162  mov     rcx, [rdi+7F8h]; this
0x180076169  lea     r8, [rsp+180h+csetcolumn]; int *
0x18007616e  lea     rdx, off_180130C60; struct ColumnDefinition *
0x180076175  mov     [rsp+180h+csetcolumn], eax
0x180076179  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18007617e  cmp     [rsp+180h+csetcolumn], 0
0x180076183  mov     ebx, eax
0x180076185  jnz     short loc_180076199
0x180076187  mov     r8d, 0CBh
0x18007618d  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180076194  call    Log_AssertionEvent_2
0x180076199  mov     edx, ebx
0x18007619b  lea     rcx, [rbp+80h+psetcolumn]
0x18007619f  call    _FindColumnIdInColumnsVector
0x1800761a4  mov     rbx, rax
0x1800761a7  test    rax, rax
0x1800761aa  jnz     short loc_180076206
0x1800761ac  mov     rcx, [rdi+7F8h]; this
0x1800761b3  lea     r8, [rsp+180h+csetcolumn]; int *
0x1800761b8  lea     rdx, off_180130C80; struct ColumnDefinition *
0x1800761bf  mov     [rsp+180h+csetcolumn], eax
0x1800761c3  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x1800761c8  cmp     [rsp+180h+csetcolumn], 0
0x1800761cd  mov     ebx, eax
0x1800761cf  jnz     short loc_1800761E3
0x1800761d1  mov     r8d, 0CBh
0x1800761d7  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800761de  call    Log_AssertionEvent_2
0x1800761e3  mov     edx, ebx
0x1800761e5  lea     rcx, [rbp+80h+psetcolumn]
0x1800761e9  call    _FindColumnIdInColumnsVector
0x1800761ee  mov     rbx, rax
0x1800761f1  test    rax, rax
0x1800761f4  jnz     short loc_180076206
0x1800761f6  lea     rcx, [rsp+180h+var_110]
0x1800761fb  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180076201  lea     rbx, [rsp+180h+var_110]
0x180076206  lea     rcx, [rsp+180h+Block]
0x18007620b  call    ??$replace@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_array_ptr@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&tlx::_delete_array<ushort>(ushort *)>(tlx::auto_array_ptr<ushort,&tlx::_delete_array<ushort>(ushort *)> &)
0x180076210  mov     r8, rax; unsigned __int16 **
0x180076213  mov     rdx, rbx; struct _FILETIME *
0x180076216  mov     rcx, r15; unsigned __int16 *
0x180076219  call    ?GenerateUniqueId@@YAJPEBGAEBU_FILETIME@@PEAPEAG@Z; GenerateUniqueId(ushort const *,_FILETIME const &,ushort * *)
0x18007621e  xor     r15d, r15d
0x180076221  mov     ebx, eax
0x180076223  test    eax, eax
0x180076225  jns     short loc_180076258
0x180076227  mov     r9d, 104Eh
0x18007622d  mov     edx, 1
0x180076232  mov     ecx, eax
0x180076234  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007623b  call    Log_HREvent
0x180076240  mov     rcx, [rsp+180h+Block]; Block
0x180076245  test    rcx, rcx
0x180076248  jz      loc_18007658C
0x18007624e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180076253  jmp     loc_18007658C
0x180076258  mov     r8, [rsp+180h+Block]; unsigned __int16 *
0x18007625d  lea     rcx, [rbp+80h+sesid]; struct JET_SETCOLUMN *
0x180076261  xorps   xmm0, xmm0
0x180076264  xor     eax, eax
0x180076266  mov     edx, esi; unsigned int
0x180076268  mov     [rbp+80h+var_C8], rax
0x18007626c  movups  xmmword ptr [rbp+80h+sesid], xmm0
0x180076270  movups  [rbp+80h+var_D8], xmm0
0x180076274  call    ?InitSetColumn@@YAJPEAUJET_SETCOLUMN@@KPEBG@Z; InitSetColumn(JET_SETCOLUMN *,ulong,ushort const *)
0x180076279  mov     ebx, eax
0x18007627b  test    eax, eax
0x18007627d  jns     short loc_180076287
0x18007627f  mov     r9d, 1053h
0x180076285  jmp     short loc_18007622D
0x180076287  lea     rdx, [rbp+80h+sesid]
0x18007628b  lea     rcx, [rbp+80h+psetcolumn]
0x18007628f  call    ??$_PushBackOne@AEBUJET_SETCOLUMN@@@?$vector@UJET_SETCOLUMN@@V?$allocator@UJET_SETCOLUMN@@@utl@@@utl@@AEAA_NAEBUJET_SETCOLUMN@@@Z; utl::vector<JET_SETCOLUMN,utl::allocator<JET_SETCOLUMN>>::_PushBackOne<JET_SETCOLUMN const &>(JET_SETCOLUMN const &)
0x180076294  test    al, al
0x180076296  jnz     short loc_1800762A9
0x180076298  mov     ebx, 8007000Eh
0x18007629d  mov     r9d, 1054h
0x1800762a3  mov     ecx, ebx
0x1800762a5  xor     edx, edx
0x1800762a7  jmp     short loc_180076234
0x1800762a9  mov     rcx, [rbp+80h+var_F8]
0x1800762ad  lea     rdx, [rsp+180h+csetcolumn]; unsigned int *
0x1800762b2  sub     rcx, [rbp+80h+psetcolumn]
0x1800762b6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800762c0  sar     rcx, 3
0x1800762c4  imul    rcx, rax; unsigned __int64
0x1800762c8  mov     [rsp+180h+csetcolumn], r15d
0x1800762cd  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800762d2  mov     ebx, eax
0x1800762d4  test    eax, eax
0x1800762d6  jns     short loc_1800762E3
0x1800762d8  mov     r9d, 1058h
0x1800762de  jmp     loc_18007622D
0x1800762e3  mov     rcx, [rdi+800h]; sesid
0x1800762ea  lea     rax, [rsp+180h+var_128]
0x1800762ef  mov     edx, [rdi+808h]; dbid
0x1800762f5  lea     r8, ?UdmTableName_CallHistory@@3QBDB; "CallHistory"
0x1800762fc  mov     [rsp+180h+ptableid], rax; unsigned int
0x180076301  xor     r9d, r9d; pvParameters
0x180076304  mov     [rsp+180h+grbit], 8; grbit
0x18007630c  mov     [rsp+180h+cbParameters], r15d; unsigned int
0x180076311  mov     [rsp+180h+var_130], rcx
0x180076316  mov     [rsp+180h+var_128], 0FFFFFFFFFFFFFFFFh
0x18007631f  call    cs:__imp_JetOpenTableA
0x180076325  test    eax, eax
0x180076327  jns     short loc_180076357
0x180076329  mov     ecx, eax; int
0x18007632b  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180076330  mov     r9d, 1064h
0x180076336  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18007633d  xor     edx, edx
0x18007633f  mov     ecx, eax
0x180076341  mov     ebx, eax
0x180076343  call    Log_HREvent
0x180076348  lea     rcx, [rsp+180h+var_130]; this
0x18007634d  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x180076352  jmp     loc_180076240
0x180076357  mov     rcx, [rsp+180h+var_128]
0x18007635c  mov     rax, [rdi+800h]
0x180076363  mov     [rbp+80h+sesid+8], rcx
0x180076367  mov     [rbp+80h+var_C0], rcx
0x18007636b  lea     rcx, [rbp+80h+sesid]; this
0x18007636f  mov     [rbp+80h+sesid], rax
0x180076373  mov     qword ptr [rbp+80h+var_D8], rax
0x180076377  mov     qword ptr [rbp+80h+var_D8+8], 0
0x18007637f  mov     [rbp+80h+var_C8], rax
0x180076383  mov     [rbp+80h+var_B8], r15d
0x180076387  mov     [rsp+180h+var_118], r15d
0x18007638c  call    ?Start@UpdateContext@@QEAAJK@Z; UpdateContext::Start(ulong)
0x180076391  mov     ebx, eax
0x180076393  test    eax, eax
0x180076395  jns     short loc_1800763BB
0x180076397  mov     r9d, 106Bh
0x18007639d  mov     edx, 1
0x1800763a2  mov     ecx, eax
0x1800763a4  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800763ab  call    Log_HREvent
0x1800763b0  lea     rcx, [rbp+80h+sesid]; this
0x1800763b4  call    ??1UpdateContext@@QEAA@XZ; UpdateContext::~UpdateContext(void)
0x1800763b9  jmp     short loc_180076348
0x1800763bb  lea     r8, [rsp+180h+var_118]; int *
0x1800763c0  xor     edx, edx; unsigned int
0x1800763c2  lea     rcx, [rbp+80h+sesid]; this
0x1800763c6  call    ?MaybePrepare@UpdateContext@@QEAAJKPEAH@Z; UpdateContext::MaybePrepare(ulong,int *)
0x1800763cb  mov     ebx, eax
0x1800763cd  test    eax, eax
0x1800763cf  jns     short loc_1800763D9
0x1800763d1  mov     r9d, 106Ch
0x1800763d7  jmp     short loc_18007639D
0x1800763d9  mov     r9d, [rsp+180h+csetcolumn]; csetcolumn
0x1800763de  mov     r8, [rbp+80h+psetcolumn]; psetcolumn
0x1800763e2  mov     rdx, [rbp+80h+sesid+8]; tableid
0x1800763e6  mov     rcx, [rbp+80h+sesid]; sesid
0x1800763ea  call    cs:__imp_JetSetColumns
0x1800763f0  test    eax, eax
0x1800763f2  jns     short loc_180076407
0x1800763f4  mov     ecx, eax; int
0x1800763f6  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800763fb  mov     r9d, 106Eh
0x180076401  mov     ebx, eax
0x180076403  xor     edx, edx
0x180076405  jmp     short loc_1800763A2
0x180076407  mov     rcx, [rdi+7F8h]; this
0x18007640e  lea     r8, [rsp+180h+csetcolumn]; int *
0x180076413  lea     rdx, ?UdmTableCols_CallHistory@@3QBUColumnDefinition@@B; struct ColumnDefinition *
0x18007641a  mov     [rsp+180h+var_11C], r15d
0x18007641f  mov     [rsp+180h+var_120], r15d
0x180076424  mov     [rsp+180h+csetcolumn], r15d
0x180076429  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z; DatabaseVolumeSession::FindColumnEx(ColumnDefinition const *,int *)
0x18007642e  mov     ebx, eax
0x180076430  cmp     [rsp+180h+csetcolumn], r15d
0x180076435  jnz     short loc_180076449
0x180076437  mov     r8d, 0CBh
0x18007643d  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180076444  call    Log_AssertionEvent_2
0x180076449  mov     rdx, [rsp+180h+var_128]; unsigned __int64
0x18007644e  lea     rax, [rsp+180h+var_120]
0x180076453  mov     rcx, [rdi+800h]; unsigned __int64
0x18007645a  lea     r9, [rsp+180h+var_11C]; void *
0x18007645f  mov     r8d, ebx; unsigned int
0x180076462  mov     qword ptr [rsp+180h+grbit], rax; unsigned int *
0x180076467  call    ?CommsESE_JetRetrieveColumn@@YAJ_K0KPEAXKPEAKKPEAUJET_RETINFO@@@Z; CommsESE_JetRetrieveColumn(unsigned __int64,unsigned __int64,ulong,void *,ulong,ulong *,ulong,JET_RETINFO *)
0x18007646c  test    eax, eax
0x18007646e  jns     short loc_18007647F
0x180076470  mov     ecx, eax; int
0x180076472  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180076477  mov     r9d, 107Ch
0x18007647d  jmp     short loc_180076401
0x18007647f  xor     edx, edx; unsigned int
0x180076481  cmp     [rsp+180h+var_120], 4
0x180076486  jz      short loc_18007649A
0x180076488  mov     ebx, 8000FFFFh
0x18007648d  mov     r9d, 107Eh
0x180076493  mov     ecx, ebx
0x180076495  jmp     loc_1800763A4
0x18007649a  lea     rcx, [rbp+80h+sesid]; this
0x18007649e  call    ?CommitUpdate@UpdateContext@@QEAAJK@Z; UpdateContext::CommitUpdate(ulong)
0x1800764a3  mov     ebx, eax
0x1800764a5  test    eax, eax
0x1800764a7  jns     short loc_1800764B4
0x1800764a9  mov     r9d, 107Fh
0x1800764af  jmp     loc_18007639D
0x1800764b4  mov     ebx, [rsp+180h+var_11C]
0x1800764b8  lea     rcx, [rbp+80h+var_90]; void *
0x1800764bc  xor     edx, edx; Val
0x1800764be  mov     [r14+8], ebx
0x1800764c2  mov     [r14], r15d
0x1800764c5  mov     dword ptr [r14+4], 1
  ... truncated ...
```
