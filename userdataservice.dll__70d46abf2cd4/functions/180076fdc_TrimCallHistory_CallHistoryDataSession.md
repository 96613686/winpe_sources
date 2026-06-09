# TrimCallHistory(CallHistoryDataSession *)

- ea: `0x180076fdc`
- end: `0x180077590`
- name: `?TrimCallHistory@@YAJPEAVCallHistoryDataSession@@@Z`
- size: `1460`
- prototype: `__int64 __fastcall(struct CallHistoryDataSession *)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180075fd4`
- `0x1800dbe0c`

## callees

- `0x180008f0c`
- `0x1800129a8`
- `0x180035670`
- `0x18003bf04`
- `0x180061540`
- `0x180066860`
- `0x180068698`
- `0x18006b13c`
- `0x180075f98`
- `0x180076664`
- `0x180076fdc`
- `0x1800a1270`
- `0x1800a1568`
- `0x1800db6b0`
- `0x1800db8c8`
- `0x1800dbb50`
- `0x1800dec9c`
- `0x1800decf0`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x180077102`
- `ESENT!JetOpenTableA` at `0x180077102`
- `ESENT!JetDelete` at `0x18007733d`
- `ESENT!JetDelete` at `0x18007733d`
- `ESENT!JetSetCurrentIndexA` at `0x180077191`
- `ESENT!JetSetCurrentIndexA` at `0x180077191`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180077129`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180077129`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180077142`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180077142`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180077132`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180077132`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18007711a`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18007711a`

## string_xrefs

- `0x18007702c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180077414`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180077497`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077528`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x180077545`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`

## pseudocode

```c
__int64 __fastcall TrimCallHistory(struct CallHistoryDataSession *a1)
{
  DatabaseVolumeSession *v2; // rcx
  __int64 v3; // rcx
  unsigned int Column; // r13d
  DatabaseVolumeSession *v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // r12d
  DatabaseVolumeSession *v8; // rcx
  __int64 v9; // rcx
  JET_SESID v10; // rcx
  JET_DBID v11; // edx
  RTL_SRWLOCK *v12; // rbx
  JET_ERR v13; // eax
  int v14; // eax
  unsigned int HresultFromJetError; // ebx
  JET_ERR v16; // eax
  int v17; // ebx
  unsigned int v18; // esi
  int v19; // r15d
  int v20; // eax
  int v21; // eax
  unsigned int v22; // edx
  __int64 v23; // rbx
  int v24; // eax
  JET_ERR v25; // eax
  int v26; // eax
  int v27; // eax
  unsigned int i; // ebx
  __int64 v29; // rcx
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v34; // r9
  __int64 v35; // rdx
  int v36; // [rsp+40h] [rbp-C0h] BYREF
  int v37; // [rsp+44h] [rbp-BCh] BYREF
  JET_SESID sesid; // [rsp+48h] [rbp-B8h] BYREF
  JET_TABLEID tableid; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  RTL_SRWLOCK *v41; // [rsp+60h] [rbp-A0h]
  int v42; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v43; // [rsp+6Ch] [rbp-94h] BYREF
  _QWORD v44[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v45; // [rsp+80h] [rbp-80h]
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v47[40]; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v48[180]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v49[256]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v2 = (DatabaseVolumeSession *)*((_QWORD *)a1 + 255);
  v36 = 0;
  Column = DatabaseVolumeSession::FindColumnEx(v2, (const struct ColumnDefinition *)&off_180130C60, &v36);
  if ( !v36 )
    Log_AssertionEvent_2(
      v3,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v5 = (DatabaseVolumeSession *)*((_QWORD *)a1 + 255);
  v36 = 0;
  v7 = DatabaseVolumeSession::FindColumnEx(v5, (const struct ColumnDefinition *)&UdmTableCols_CallHistory, &v36);
  if ( !v36 )
    Log_AssertionEvent_2(
      v6,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v8 = (DatabaseVolumeSession *)*((_QWORD *)a1 + 255);
  v36 = 0;
  v45 = DatabaseVolumeSession::FindColumnEx(v8, (const struct ColumnDefinition *)&off_180130F40, &v36);
  if ( !v36 )
    Log_AssertionEvent_2(
      v9,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      203);
  v10 = *((_QWORD *)a1 + 256);
  v11 = *((_DWORD *)a1 + 514);
  v12 = (RTL_SRWLOCK *)(*((_QWORD *)a1 + 255) + 120LL);
  v41 = v12;
  v40 = 0;
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
      1450);
  }
  else
  {
    while ( 1 )
    {
      if ( HIDWORD(v40) >= 2 )
      {
        AcquireSRWLockExclusive(v12);
        LODWORD(v40) = 2;
      }
      else
      {
        if ( !TryAcquireSRWLockShared(v12) )
        {
          Sleep(0x64u);
          AcquireSRWLockShared(v12);
        }
        LODWORD(v40) = 1;
      }
      v44[0] = *((_QWORD *)a1 + 256);
      v44[1] = 0;
      v14 = auto_JET_TRANSACTION::Begin((auto_JET_TRANSACTION *)v44, 0);
      HresultFromJetError = v14;
      if ( v14 < 0 )
        break;
      v36 = 0;
      v16 = JetSetCurrentIndexA(sesid, tableid, "ByTime");
      if ( v16 < 0 )
      {
        v14 = MakeHresultFromJetError(v16);
        HresultFromJetError = v14;
        v34 = 1462;
        v35 = 0;
        goto LABEL_58;
      }
      v14 = Move(sesid, tableid, 500, &v36);
      HresultFromJetError = v14;
      if ( v14 < 0 )
      {
        v34 = 1463;
        goto LABEL_57;
      }
      v17 = v36;
      if ( !v36 )
      {
        auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)v44);
        BackoffContext::Unlock((BackoffContext *)&v40);
        auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
        BackoffContext::Unlock((BackoffContext *)&v40);
        return 0;
      }
      v18 = 0;
      v19 = 0;
      `vector constructor iterator'(
        v47,
        0x20u,
        0xAu,
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>);
      memset_0(v48, 0, sizeof(v48));
      while ( v17 && v18 < 0xA )
      {
        v37 = 0;
        v46 = 0;
        v42 = 0;
        v20 = auto_JET_TABLEID::GetColumn((auto_JET_TABLEID *)&sesid, Column, &v46, 8u, &v37);
        if ( v20 < 0 )
        {
          v26 = MakeHresultFromJetError(v20);
          v30 = 1484;
          goto LABEL_49;
        }
        v21 = auto_JET_TABLEID::GetColumn((auto_JET_TABLEID *)&sesid, v7, &v42, 4u, &v37);
        if ( v21 < 0 )
        {
          v26 = MakeHresultFromJetError(v21);
          v30 = 1485;
          goto LABEL_49;
        }
        v22 = v45;
        v43 = 0;
        v23 = 9LL * v18;
        v48[2 * v23 + 5] = v42;
        *(_QWORD *)&v48[2 * v23 + 6] = v46;
        v48[2 * v23] = 1;
        *(_QWORD *)&v48[2 * v23 + 2] = 1;
        v48[2 * v23 + 4] = 1;
        v24 = auto_JET_TABLEID::GetColumn((auto_JET_TABLEID *)&sesid, v22, v49, 0x100u, &v43, &v37);
        if ( v24 < 0 )
        {
          v26 = MakeHresultFromJetError(v24);
          v30 = 1501;
          goto LABEL_49;
        }
        if ( v37 && v43 - 2 <= 0xFE )
        {
          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                   &v47[4 * v18],
                                   v49,
                                   (unsigned __int64)v43 >> 1) )
          {
            HresultFromJetError = -2147024882;
            v30 = 1506;
            v31 = 2147942414LL;
            v32 = 0;
            goto LABEL_51;
          }
          *(_QWORD *)&v48[18 * v18 + 8] = v47[4 * v18];
        }
        v25 = JetDelete(sesid, tableid);
        if ( v25 == -1102 )
        {
          v19 = 1;
        }
        else
        {
          if ( v25 < 0 )
          {
            v26 = MakeHresultFromJetError(v25);
            v30 = 1518;
LABEL_49:
            v32 = 0;
            HresultFromJetError = v26;
LABEL_50:
            v31 = (unsigned int)v26;
LABEL_51:
            Log_HREvent(
              v31,
              v32,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
              v30);
            `vector destructor iterator'(
              v47,
              0x20u,
              0xAu,
              utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit);
            goto LABEL_52;
          }
          ++v18;
        }
        v26 = Move(sesid, tableid, 1, &v36);
        HresultFromJetError = v26;
        if ( v26 < 0 )
        {
          v30 = 1522;
          v32 = 1;
          goto LABEL_50;
        }
        v17 = v36;
      }
      if ( v18 )
      {
        v27 = auto_JET_TRANSACTION::Commit((auto_JET_TRANSACTION *)v44, 1u);
        if ( v27 < 0 )
        {
          v26 = MakeHresultFromJetError(v27);
          v30 = 1528;
          goto LABEL_49;
        }
        for ( i = 0; i < v18; ++i )
          DatabaseVolumeSession::PushNotify(
            *((DatabaseVolumeSession **)a1 + 255),
            (const struct UdmNotifyStructure *)&v48[18 * i]);
      }
      if ( v19 )
        BackoffContext::NeedsBackoff((BackoffContext *)&v40);
      `vector destructor iterator'(
        v47,
        0x20u,
        0xAu,
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit);
      auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)v44);
      BackoffContext::Unlock((BackoffContext *)&v40);
      if ( (_DWORD)v40 )
        Log_AssertionEvent_2(
          v29,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
          2208);
      v12 = v41;
    }
    v34 = 1458;
LABEL_57:
    v35 = 1;
LABEL_58:
    Log_HREvent(
      (unsigned int)v14,
      v35,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      v34);
LABEL_52:
    auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)v44);
    BackoffContext::Unlock((BackoffContext *)&v40);
  }
  auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&sesid);
  BackoffContext::Unlock((BackoffContext *)&v40);
  return HresultFromJetError;
}

```

## disassembly

```asm
0x180076fdc  push    rbp
0x180076fde  push    rbx
0x180076fdf  push    rsi
0x180076fe0  push    rdi
0x180076fe1  push    r12
0x180076fe3  push    r13
0x180076fe5  push    r14
0x180076fe7  push    r15
0x180076fe9  lea     rbp, [rsp-4B8h]
0x180076ff1  sub     rsp, 5B8h
0x180076ff8  mov     rax, cs:__security_cookie
0x180076fff  xor     rax, rsp
0x180077002  mov     [rbp+4F0h+var_50], rax
0x180077009  mov     rdi, rcx
0x18007700c  lea     r8, [rsp+5F0h+var_5B0]; int *
0x180077011  mov     rcx, [rcx+7F8h]; this
0x180077018  lea     rdx, off_180130C60; struct ColumnDefinition *
0x18007701f  xor     r14d, r14d
0x180077022  mov     [rsp+5F0h+var_5B0], r14d
0x180077027  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z
0x18007702c  lea     rsi, aOnecoreuapBase_62
0x180077033  mov     r13d, eax
0x180077036  mov     ebx, 0CBh
0x18007703b  cmp     [rsp+5F0h+var_5B0], r14d
0x180077040  jnz     short loc_18007704D
0x180077042  mov     r8d, ebx
0x180077045  mov     rdx, rsi
0x180077048  call    Log_AssertionEvent_2
0x18007704d  mov     rcx, [rdi+7F8h]; this
0x180077054  lea     r8, [rsp+5F0h+var_5B0]; int *
0x180077059  lea     rdx, ?UdmTableCols_CallHistory@@3QBUColumnDefinition@@B; struct ColumnDefinition *
0x180077060  mov     [rsp+5F0h+var_5B0], r14d
0x180077065  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z
0x18007706a  mov     r12d, eax
0x18007706d  cmp     [rsp+5F0h+var_5B0], r14d
0x180077072  jnz     short loc_18007707F
0x180077074  mov     r8d, ebx
0x180077077  mov     rdx, rsi
0x18007707a  call    Log_AssertionEvent_2
0x18007707f  mov     rcx, [rdi+7F8h]; this
0x180077086  lea     r8, [rsp+5F0h+var_5B0]; int *
0x18007708b  lea     rdx, off_180130F40; struct ColumnDefinition *
0x180077092  mov     [rsp+5F0h+var_5B0], r14d
0x180077097  call    ?FindColumnEx@DatabaseVolumeSession@@QEBAKPEBUColumnDefinition@@PEAH@Z
0x18007709c  mov     [rbp+4F0h+var_570], eax
0x18007709f  cmp     [rsp+5F0h+var_5B0], r14d
0x1800770a4  jnz     short loc_1800770B1
0x1800770a6  mov     r8d, ebx
0x1800770a9  mov     rdx, rsi
0x1800770ac  call    Log_AssertionEvent_2
0x1800770b1  mov     rbx, [rdi+7F8h]
0x1800770b8  lea     rax, [rsp+5F0h+tableid]
0x1800770bd  mov     rcx, [rdi+800h]; sesid
0x1800770c4  lea     r8, ?UdmTableName_CallHistory@@3QBDB
0x1800770cb  mov     edx, [rdi+808h]; dbid
0x1800770d1  add     rbx, 78h ; 'x'
0x1800770d5  mov     [rsp+5F0h+ptableid], rax; ptableid
0x1800770da  xor     r9d, r9d; pvParameters
0x1800770dd  mov     [rsp+5F0h+grbit], 8; grbit
0x1800770e5  mov     [rsp+5F0h+var_590], rbx
0x1800770ea  mov     [rsp+5F0h+cbParameters], r14d; cbParameters
0x1800770ef  mov     [rsp+5F0h+var_598], r14
0x1800770f4  mov     [rsp+5F0h+sesid], rcx
0x1800770f9  mov     [rsp+5F0h+tableid], 0FFFFFFFFFFFFFFFFh
0x180077102  call    cs:__imp_JetOpenTableA
0x180077108  test    eax, eax
0x18007710a  js      loc_180077538
0x180077110  cmp     dword ptr [rsp+5F0h+var_598+4], 2
0x180077115  mov     rcx, rbx; SRWLock
0x180077118  jnb     short loc_180077142
0x18007711a  call    cs:__imp_TryAcquireSRWLockShared
0x180077120  test    al, al
0x180077122  jnz     short loc_180077138
0x180077124  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180077129  call    cs:__imp_Sleep
0x18007712f  mov     rcx, rbx; SRWLock
0x180077132  call    cs:__imp_AcquireSRWLockShared
0x180077138  mov     dword ptr [rsp+5F0h+var_598], 1
0x180077140  jmp     short loc_180077150
0x180077142  call    cs:__imp_AcquireSRWLockExclusive
0x180077148  mov     dword ptr [rsp+5F0h+var_598], 2
0x180077150  mov     rax, [rdi+800h]
0x180077157  lea     rcx, [rsp+5F0h+var_580]; this
0x18007715c  xor     edx, edx; unsigned int
0x18007715e  mov     [rsp+5F0h+var_580], rax
0x180077163  mov     [rsp+5F0h+var_578], 0
0x18007716c  call    ?Begin@auto_JET_TRANSACTION@@QEAAJK@Z
0x180077171  mov     ebx, eax
0x180077173  test    eax, eax
0x180077175  js      loc_18007751D
0x18007717b  mov     rdx, [rsp+5F0h+tableid]; tableid
0x180077180  lea     r8, ?UdmIdxName_CallHistory_ByTime@@3QBDB
0x180077187  mov     rcx, [rsp+5F0h+sesid]; sesid
0x18007718c  mov     [rsp+5F0h+var_5B0], r14d
0x180077191  call    cs:__imp_JetSetCurrentIndexA
0x180077197  test    eax, eax
0x180077199  js      loc_18007750A
0x18007719f  mov     rdx, [rsp+5F0h+tableid]; unsigned __int64
0x1800771a4  lea     r9, [rsp+5F0h+var_5B0]; int *
0x1800771a9  mov     rcx, [rsp+5F0h+sesid]; unsigned __int64
0x1800771ae  mov     r8d, 1F4h; int
0x1800771b4  call    ?Move@@YAJ_K0JPEAH@Z
0x1800771b9  mov     ebx, eax
0x1800771bb  test    eax, eax
0x1800771bd  js      loc_180077502
0x1800771c3  mov     ebx, [rsp+5F0h+var_5B0]
0x1800771c7  test    ebx, ebx
0x1800771c9  jz      loc_1800774D6
0x1800771cf  mov     edx, 20h ; ' '; unsigned __int64
0x1800771d4  lea     r9, ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; void *(*)(void *)
0x1800771db  lea     rcx, [rbp+4F0h+var_560]; void *
0x1800771df  mov     esi, r14d
0x1800771e2  mov     r15d, r14d
0x1800771e5  lea     r8d, [rdx-16h]; unsigned __int64
0x1800771e9  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z
0x1800771ee  xor     edx, edx; Val
0x1800771f0  lea     rcx, [rbp+4F0h+var_420]; void *
0x1800771f7  mov     r8d, 2D0h; Size
0x1800771fd  call    memset_0
0x180077202  test    ebx, ebx
0x180077204  jz      loc_18007738A
0x18007720a  cmp     esi, 0Ah
0x18007720d  jnb     loc_18007738A
0x180077213  lea     rax, [rsp+5F0h+var_5AC]
0x180077218  mov     [rsp+5F0h+var_5AC], r14d
0x18007721d  mov     r9d, 8; unsigned int
0x180077223  mov     qword ptr [rsp+5F0h+cbParameters], rax; int *
0x180077228  lea     r8, [rbp+4F0h+var_568]; void *
0x18007722c  mov     [rbp+4F0h+var_568], r14
0x180077230  mov     edx, r13d; unsigned int
0x180077233  mov     [rsp+5F0h+var_588], r14d
0x180077238  lea     rcx, [rsp+5F0h+sesid]; this
0x18007723d  call    ?GetColumn@auto_JET_TABLEID@@QEAAJKPEAXKPEAH@Z
0x180077242  test    eax, eax
0x180077244  js      loc_180077475
0x18007724a  lea     rax, [rsp+5F0h+var_5AC]
0x18007724f  mov     r9d, 4; unsigned int
0x180077255  lea     r8, [rsp+5F0h+var_588]; void *
0x18007725a  mov     qword ptr [rsp+5F0h+cbParameters], rax; int *
0x18007725f  mov     edx, r12d; unsigned int
0x180077262  lea     rcx, [rsp+5F0h+sesid]; this
0x180077267  call    ?GetColumn@auto_JET_TABLEID@@QEAAJKPEAXKPEAH@Z
0x18007726c  test    eax, eax
0x18007726e  js      loc_180077466
0x180077274  mov     eax, [rsp+5F0h+var_588]
0x180077278  lea     r8, [rbp+4F0h+var_150]; void *
0x18007727f  mov     edx, [rbp+4F0h+var_570]; unsigned int
0x180077282  mov     ecx, 1
0x180077287  mov     r14d, esi
0x18007728a  mov     r9d, 100h; unsigned int
0x180077290  mov     [rsp+5F0h+var_584], 0
0x180077298  lea     rbx, [r14+r14*8]
0x18007729c  mov     [rbp+rbx*8+4F0h+var_40C], eax
0x1800772a3  mov     rax, [rbp+4F0h+var_568]
0x1800772a7  mov     [rbp+rbx*8+4F0h+var_408], rax
0x1800772af  lea     rax, [rsp+5F0h+var_5AC]
0x1800772b4  mov     qword ptr [rsp+5F0h+grbit], rax; int *
0x1800772b9  lea     rax, [rsp+5F0h+var_584]
0x1800772be  mov     [rbp+rbx*8+4F0h+var_420], ecx
0x1800772c5  mov     [rbp+rbx*8+4F0h+var_418], rcx
0x1800772cd  mov     [rbp+rbx*8+4F0h+var_410], ecx
0x1800772d4  lea     rcx, [rsp+5F0h+sesid]; this
0x1800772d9  mov     qword ptr [rsp+5F0h+cbParameters], rax; unsigned int *
0x1800772de  call    ?GetColumn@auto_JET_TABLEID@@QEAAJKPEAXKPEAKPEAH@Z
0x1800772e3  test    eax, eax
0x1800772e5  js      loc_180077457
0x1800772eb  cmp     [rsp+5F0h+var_5AC], 0
0x1800772f0  jz      short loc_180077333
0x1800772f2  mov     ecx, [rsp+5F0h+var_584]
0x1800772f6  lea     eax, [rcx-2]
0x1800772f9  cmp     eax, 0FEh
0x1800772fe  ja      short loc_180077333
0x180077300  mov     r8d, ecx
0x180077303  shl     r14, 5
0x180077307  lea     rax, [rbp+4F0h+var_560]
0x18007730b  shr     r8, 1
0x18007730e  add     r14, rax
0x180077311  lea     rdx, [rbp+4F0h+var_150]
0x180077318  mov     rcx, r14
0x18007731b  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z
0x180077320  test    al, al
0x180077322  jz      loc_18007742A
0x180077328  mov     rax, [r14]
0x18007732b  mov     [rbp+rbx*8+4F0h+var_400], rax
0x180077333  mov     rdx, [rsp+5F0h+tableid]; tableid
0x180077338  mov     rcx, [rsp+5F0h+sesid]; sesid
0x18007733d  call    cs:__imp_JetDelete
0x180077343  xor     r14d, r14d
0x180077346  cmp     eax, 0FFFFFBB2h
0x18007734b  jnz     short loc_180077353
0x18007734d  lea     r15d, [r14+1]
0x180077351  jmp     short loc_18007735D
0x180077353  test    eax, eax
0x180077355  js      loc_180077448
0x18007735b  inc     esi
0x18007735d  mov     rdx, [rsp+5F0h+tableid]; unsigned __int64
0x180077362  lea     r9, [rsp+5F0h+var_5B0]; int *
0x180077367  mov     rcx, [rsp+5F0h+sesid]; unsigned __int64
0x18007736c  mov     r8d, 1; int
0x180077372  call    ?Move@@YAJ_K0JPEAH@Z
0x180077377  mov     ebx, eax
0x180077379  test    eax, eax
0x18007737b  js      loc_18007743B
0x180077381  mov     ebx, [rsp+5F0h+var_5B0]
0x180077385  jmp     loc_180077202
0x18007738a  test    esi, esi
0x18007738c  jz      short loc_1800773CB
0x18007738e  mov     edx, 1; unsigned int
0x180077393  lea     rcx, [rsp+5F0h+var_580]; this
0x180077398  call    ?Commit@auto_JET_TRANSACTION@@QEAAJK@Z
0x18007739d  test    eax, eax
0x18007739f  js      loc_180077484
0x1800773a5  mov     ebx, r14d
0x1800773a8  mov     eax, ebx
0x1800773aa  lea     rdx, [rbp+4F0h+var_420]
0x1800773b1  lea     rcx, [rax+rax*8]
0x1800773b5  lea     rdx, [rdx+rcx*8]; struct UdmNotifyStructure *
0x1800773b9  mov     rcx, [rdi+7F8h]; this
0x1800773c0  call    ?PushNotify@DatabaseVolumeSession@@QEAAXAEBUUdmNotifyStructure@@@Z
0x1800773c5  inc     ebx
0x1800773c7  cmp     ebx, esi
0x1800773c9  jb      short loc_1800773A8
0x1800773cb  test    r15d, r15d
0x1800773ce  jz      short loc_1800773DA
0x1800773d0  lea     rcx, [rsp+5F0h+var_598]; this
0x1800773d5  call    ?NeedsBackoff@BackoffContext@@QEAAXXZ
0x1800773da  mov     edx, 20h ; ' '; unsigned __int64
0x1800773df  lea     r9, ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; void (*)(void *)
0x1800773e6  lea     rcx, [rbp+4F0h+var_560]; void *
0x1800773ea  lea     r8d, [rdx-16h]; unsigned __int64
0x1800773ee  call    ??_I@YAXPEAX_K1P6AX0@Z@Z
0x1800773f3  lea     rcx, [rsp+5F0h+var_580]; this
0x1800773f8  call    ??1auto_JET_TRANSACTION@@QEAA@XZ
0x1800773fd  lea     rcx, [rsp+5F0h+var_598]; this
0x180077402  call    ?Unlock@BackoffContext@@QEAAXXZ
0x180077407  cmp     dword ptr [rsp+5F0h+var_598], r14d
0x18007740c  jz      short loc_180077420
0x18007740e  mov     r8d, 8A0h
0x180077414  lea     rdx, aOnecoreuapBase_62
0x18007741b  call    Log_AssertionEvent_2
0x180077420  mov     rbx, [rsp+5F0h+var_590]
0x180077425  jmp     loc_180077110
0x18007742a  mov     ebx, 8007000Eh
0x18007742f  mov     r9d, 5E2h
0x180077435  mov     ecx, ebx
0x180077437  xor     edx, edx
0x180077439  jmp     short loc_180077497
0x18007743b  mov     r9d, 5F2h
0x180077441  mov     edx, 1
0x180077446  jmp     short loc_180077495
0x180077448  mov     ecx, eax; int
0x18007744a  call    ?MakeHresultFromJetError@@YAJJ@Z
0x18007744f  mov     r9d, 5EEh
0x180077455  jmp     short loc_180077491
0x180077457  mov     ecx, eax; int
0x180077459  call    ?MakeHresultFromJetError@@YAJJ@Z
0x18007745e  mov     r9d, 5DDh
0x180077464  jmp     short loc_180077491
0x180077466  mov     ecx, eax; int
0x180077468  call    ?MakeHresultFromJetError@@YAJJ@Z
0x18007746d  mov     r9d, 5CDh
0x180077473  jmp     short loc_180077491
0x180077475  mov     ecx, eax; int
0x180077477  call    ?MakeHresultFromJetError@@YAJJ@Z
0x18007747c  mov     r9d, 5CCh
0x180077482  jmp     short loc_180077491
0x180077484  mov     ecx, eax; int
0x180077486  call    ?MakeHresultFromJetError@@YAJJ@Z
0x18007748b  mov     r9d, 5F8h
0x180077491  xor     edx, edx
0x180077493  mov     ebx, eax
0x180077495  mov     ecx, eax
0x180077497  lea     r8, aOnecoreuapBase_43
0x18007749e  call    Log_HREvent
0x1800774a3  mov     r8d, 0Ah; unsigned __int64
0x1800774a9  lea     r9, ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; void (*)(void *)
0x1800774b0  lea     rcx, [rbp+4F0h+var_560]; void *
0x1800774b4  lea     edx, [r8+16h]; unsigned __int64
0x1800774b8  call    ??_I@YAXPEAX_K1P6AX0@Z@Z
0x1800774bd  lea     rcx, [rsp+5F0h+var_580]; this
0x1800774c2  call    ??1auto_JET_TRANSACTION@@QEAA@XZ
0x1800774c7  lea     rcx, [rsp+5F0h+var_598]; this
0x1800774cc  call    ?Unlock@BackoffContext@@QEAAXXZ
0x1800774d1  jmp     loc_180077557
0x1800774d6  lea     rcx, [rsp+5F0h+var_580]; this
0x1800774db  call    ??1auto_JET_TRANSACTION@@QEAA@XZ
0x1800774e0  lea     rcx, [rsp+5F0h+var_598]; this
0x1800774e5  call    ?Unlock@BackoffContext@@QEAAXXZ
0x1800774ea  lea     rcx, [rsp+5F0h+sesid]; this
0x1800774ef  call    ??1auto_JET_TABLEID@@QEAA@XZ
0x1800774f4  lea     rcx, [rsp+5F0h+var_598]; this
0x1800774f9  call    ?Unlock@BackoffContext@@QEAAXXZ
0x1800774fe  xor     eax, eax
0x180077500  jmp     short loc_18007756D
0x180077502  mov     r9d, 5B7h
0x180077508  jmp     short loc_180077523
0x18007750a  mov     ecx, eax; int
0x18007750c  call    ?MakeHresultFromJetError@@YAJJ@Z
0x180077511  mov     ebx, eax
0x180077513  mov     r9d, 5B6h
  ... truncated ...
```
