# DeleteCallHistory(CallHistoryDataSession *,ulong,UdmObjectId const *,ulong,ushort const * *)

- ea: `0x1800dd204`
- end: `0x1800dd5ff`
- name: `?DeleteCallHistory@@YAJPEAVCallHistoryDataSession@@KPEBUUdmObjectId@@KPEAPEBG@Z`
- size: `1019`
- prototype: `__int64 __usercall@<rax>(struct CallHistoryDataSession *@<rcx>, unsigned int@<edx>, const struct UdmObjectId *@<r8>, unsigned int@<r9d>, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800dd0ec`
- `0x1800dda24`

## callees

- `0x1800049f0`
- `0x180008f0c`
- `0x18000e1f8`
- `0x18003bf04`
- `0x18006b13c`
- `0x180075f98`
- `0x180076664`
- `0x1800a0174`
- `0x1800a1270`
- `0x1800a1568`
- `0x1800db6b0`
- `0x1800db8c8`
- `0x1800dbb50`
- `0x1800dd204`
- `0x1800ddb0c`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x1800dd285`
- `ESENT!JetOpenTableA` at `0x1800dd285`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800dd310`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800dd310`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800dd329`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800dd329`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800dd319`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800dd319`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x1800dd301`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x1800dd301`

## string_xrefs

- `0x1800dd2ed`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800dd29c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800dd488`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`
- `0x1800dd597`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callhistory.cpp`

## pseudocode

```c
__int64 __fastcall DeleteCallHistory(
        struct CallHistoryDataSession *a1,
        unsigned int a2,
        const struct UdmObjectId *a3,
        __int64 a4,
        const unsigned __int16 **a5)
{
  const unsigned __int16 **v5; // r14
  JET_SESID v7; // rcx
  JET_DBID v9; // edx
  JET_ERR v10; // eax
  unsigned int v11; // ebx
  RTL_SRWLOCK *v12; // rbx
  unsigned int v13; // edi
  int v14; // r15d
  int v15; // edx
  __int64 v16; // rcx
  int v17; // eax
  int HresultFromJetError; // eax
  int v19; // r14d
  struct UdmNotifyStructure *v20; // rbx
  struct UdmNotifyStructure *v21; // rdi
  unsigned int i; // ebx
  int v23; // eax
  int v24; // edi
  __int64 v25; // r9
  __int64 v26; // rdx
  int v27; // eax
  DatabaseVolumeSession *v28; // rcx
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v32; // [rsp+4Ch] [rbp-B4h]
  RTL_SRWLOCK *v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v35[2]; // [rsp+60h] [rbp-A0h] BYREF
  JET_SESID v36; // [rsp+70h] [rbp-90h] BYREF
  JET_TABLEID ptableid; // [rsp+78h] [rbp-88h] BYREF
  struct UdmNotifyStructure *v38; // [rsp+80h] [rbp-80h] BYREF
  struct UdmNotifyStructure *v39; // [rsp+88h] [rbp-78h]
  const unsigned __int16 **v40; // [rsp+98h] [rbp-68h]
  const struct UdmObjectId *v41; // [rsp+A0h] [rbp-60h]
  _DWORD v42[20]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v43; // [rsp+100h] [rbp+0h]
  int v44; // [rsp+108h] [rbp+8h]

  v5 = a5;
  v7 = *((_QWORD *)a1 + 256);
  v41 = a3;
  v9 = *((_DWORD *)a1 + 514);
  v40 = a5;
  v36 = v7;
  ptableid = -1;
  v10 = JetOpenTableA(v7, v9, "CallHistory", 0, 0, 8u, &ptableid);
  if ( v10 >= 0 )
  {
    v12 = (RTL_SRWLOCK *)(*((_QWORD *)a1 + 255) + 120LL);
    v13 = 0;
    v33 = v12;
    v14 = 0;
    v32 = 0;
    LODWORD(v34) = 0;
    utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(&v38);
    while ( 1 )
    {
      LODWORD(v30) = 0;
      if ( v15 )
        Log_AssertionEvent_2(
          v16,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
          2208);
      if ( v13 >= 2 )
      {
        AcquireSRWLockExclusive(v12);
        v31 = 2;
      }
      else
      {
        if ( !TryAcquireSRWLockShared(v12) )
        {
          Sleep(0x64u);
          AcquireSRWLockShared(v12);
        }
        v31 = 1;
      }
      v35[0] = *((_QWORD *)a1 + 256);
      v35[1] = 0;
      v17 = auto_JET_TRANSACTION::Begin((auto_JET_TRANSACTION *)v35, 0);
      if ( v17 < 0 )
      {
        HresultFromJetError = MakeHresultFromJetError(v17);
        v25 = 1018;
        goto LABEL_35;
      }
      if ( a2 )
        break;
      v43 = 0;
      v44 = 0;
      HresultFromJetError = DeleteItemOfLines(
                              a1,
                              (struct auto_JET_TABLEID *)&v36,
                              (__int64)v5,
                              (__int64)&v38,
                              (__int64)&v34,
                              (__int64)&v30);
      v11 = HresultFromJetError;
      if ( HresultFromJetError < 0 )
      {
        v25 = 1032;
        v26 = 1;
LABEL_36:
        Log_HREvent(
          (unsigned int)HresultFromJetError,
          v26,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
          v25);
        auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)v35);
        BackoffContext::Unlock((BackoffContext *)&v31);
        utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v38);
        BackoffContext::Unlock((BackoffContext *)&v31);
        goto LABEL_37;
      }
      v19 = v30;
      v14 = 1;
      if ( !(_DWORD)v30 )
        goto LABEL_24;
LABEL_15:
      v20 = v38;
      v21 = v38;
      v39 = v38;
      BackoffContext::NeedsBackoff((BackoffContext *)&v31);
      auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)v35);
      BackoffContext::Unlock((BackoffContext *)&v31);
      if ( !v19 )
        goto LABEL_27;
      v12 = v33;
      v13 = v32;
      v15 = v31;
      v5 = v40;
    }
    for ( i = 0; i < a2; ++i )
    {
      v23 = DeleteItemOfLines(
              a1,
              (struct auto_JET_TABLEID *)&v36,
              (__int64)v5,
              (__int64)&v38,
              (__int64)&v34,
              (__int64)&v30);
      v24 = v23;
      if ( v23 < 0 )
      {
        Log_HREvent(
          (unsigned int)v23,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
          1047);
        auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)v35);
        BackoffContext::Unlock((BackoffContext *)&v31);
        utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v38);
        BackoffContext::Unlock((BackoffContext *)&v31);
        v11 = v24;
        goto LABEL_37;
      }
      v19 = v30;
      if ( (_DWORD)v30 )
        goto LABEL_15;
      v5 = v40;
    }
LABEL_24:
    v27 = auto_JET_TRANSACTION::Commit((auto_JET_TRANSACTION *)v35, 1u);
    if ( v27 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v27);
      v25 = 1059;
LABEL_35:
      v26 = 0;
      v11 = HresultFromJetError;
      goto LABEL_36;
    }
    auto_JET_TRANSACTION::~auto_JET_TRANSACTION((auto_JET_TRANSACTION *)v35);
    BackoffContext::Unlock((BackoffContext *)&v31);
    v21 = v39;
    v20 = v38;
LABEL_27:
    if ( (_DWORD)v34 )
    {
      if ( v14 )
      {
        memset_0(v42, 0, 0x48u);
        v28 = (DatabaseVolumeSession *)*((_QWORD *)a1 + 255);
        v42[0] = 1;
        v42[2] = 3;
        DatabaseVolumeSession::PushNotify(v28, (const struct UdmNotifyStructure *)v42);
      }
      else
      {
        while ( v20 != v21 )
        {
          DatabaseVolumeSession::PushNotify(*((DatabaseVolumeSession **)a1 + 255), v20);
          v20 = (struct UdmNotifyStructure *)((char *)v20 + 72);
        }
      }
      CallHistoryDataSession::FlushUpdates(a1);
    }
    utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(&v38);
    BackoffContext::Unlock((BackoffContext *)&v31);
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v36);
    return 0;
  }
  else
  {
    v11 = MakeHresultFromJetError(v10);
    Log_HREvent(
      v11,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callhistory.cpp",
      999);
LABEL_37:
    auto_JET_TABLEID::~auto_JET_TABLEID((auto_JET_TABLEID *)&v36);
    return v11;
  }
}

```

## disassembly

```asm
0x1800dd204  mov     [rsp-8+arg_8], rbx
0x1800dd209  push    rbp
0x1800dd20a  push    rsi
0x1800dd20b  push    rdi
0x1800dd20c  push    r12
0x1800dd20e  push    r13
0x1800dd210  push    r14
0x1800dd212  push    r15
0x1800dd214  lea     rbp, [rsp-20h]
0x1800dd219  sub     rsp, 120h
0x1800dd220  mov     rax, cs:__security_cookie
0x1800dd227  xor     rax, rsp
0x1800dd22a  mov     [rbp+50h+var_40], rax
0x1800dd22e  mov     r14, [rbp+50h+arg_20]
0x1800dd235  lea     rax, [rsp+150h+var_D8]
0x1800dd23a  mov     rsi, rcx
0x1800dd23d  mov     [rsp+150h+ptableid], rax; ptableid
0x1800dd242  mov     rcx, [rcx+800h]; sesid
0x1800dd249  mov     r13d, r9d
0x1800dd24c  mov     [rbp+50h+var_B0], r8
0x1800dd250  mov     r12d, edx
0x1800dd253  mov     [rsp+150h+grbit], 8; grbit
0x1800dd25b  lea     r8, ?UdmTableName_CallHistory@@3QBDB; "CallHistory"
0x1800dd262  mov     edx, [rsi+808h]; dbid
0x1800dd268  xor     r9d, r9d; pvParameters
0x1800dd26b  mov     [rbp+50h+var_B8], r14
0x1800dd26f  mov     [rsp+150h+var_E0], rcx
0x1800dd274  mov     [rsp+150h+var_D8], 0FFFFFFFFFFFFFFFFh
0x1800dd27d  mov     [rsp+150h+cbParameters], 0; cbParameters
0x1800dd285  call    cs:__imp_JetOpenTableA
0x1800dd28b  test    eax, eax
0x1800dd28d  jns     short loc_1800DD2B3
0x1800dd28f  mov     ecx, eax; int
0x1800dd291  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800dd296  mov     r9d, 3E7h
0x1800dd29c  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800dd2a3  xor     edx, edx
0x1800dd2a5  mov     ecx, eax
0x1800dd2a7  mov     ebx, eax
0x1800dd2a9  call    Log_HREvent
0x1800dd2ae  jmp     loc_1800DD5CC
0x1800dd2b3  mov     rbx, [rsi+7F8h]
0x1800dd2ba  lea     rcx, [rbp+50h+var_D0]
0x1800dd2be  add     rbx, 78h ; 'x'
0x1800dd2c2  xor     edx, edx
0x1800dd2c4  xor     edi, edi
0x1800dd2c6  mov     [rsp+150h+var_100], rbx
0x1800dd2cb  xor     r15d, r15d
0x1800dd2ce  mov     [rsp+150h+var_104], edi
0x1800dd2d2  mov     dword ptr [rsp+150h+var_F8], edx
0x1800dd2d6  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800dd2db  mov     dword ptr [rsp+150h+var_110], 0
0x1800dd2e3  test    edx, edx
0x1800dd2e5  jz      short loc_1800DD2F9
0x1800dd2e7  mov     r8d, 8A0h
0x1800dd2ed  lea     rdx, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800dd2f4  call    Log_AssertionEvent_2
0x1800dd2f9  mov     rcx, rbx; SRWLock
0x1800dd2fc  cmp     edi, 2
0x1800dd2ff  jnb     short loc_1800DD329
0x1800dd301  call    cs:__imp_TryAcquireSRWLockShared
0x1800dd307  test    al, al
0x1800dd309  jnz     short loc_1800DD31F
0x1800dd30b  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800dd310  call    cs:__imp_Sleep
0x1800dd316  mov     rcx, rbx; SRWLock
0x1800dd319  call    cs:__imp_AcquireSRWLockShared
0x1800dd31f  mov     [rsp+150h+var_108], 1
0x1800dd327  jmp     short loc_1800DD337
0x1800dd329  call    cs:__imp_AcquireSRWLockExclusive
0x1800dd32f  mov     [rsp+150h+var_108], 2
0x1800dd337  mov     rax, [rsi+800h]
0x1800dd33e  lea     rcx, [rsp+150h+var_F0]; this
0x1800dd343  xor     edx, edx; unsigned int
0x1800dd345  mov     [rsp+150h+var_F0], rax
0x1800dd34a  mov     [rsp+150h+var_E8], 0
0x1800dd353  call    ?Begin@auto_JET_TRANSACTION@@QEAAJK@Z; auto_JET_TRANSACTION::Begin(ulong)
0x1800dd358  test    eax, eax
0x1800dd35a  js      loc_1800DD586
0x1800dd360  test    r12d, r12d
0x1800dd363  jnz     loc_1800DD40D
0x1800dd369  xor     eax, eax
0x1800dd36b  lea     r8, [rbp+50h+var_50]
0x1800dd36f  mov     [rbp+50h+var_50], rax
0x1800dd373  lea     rdx, [rsp+150h+var_E0]; this
0x1800dd378  mov     [rbp+50h+var_48], eax
0x1800dd37b  mov     r9d, r13d
0x1800dd37e  lea     rax, [rsp+150h+var_110]
0x1800dd383  mov     rcx, rsi; struct CallHistoryDataSession *
0x1800dd386  mov     [rsp+150h+var_118], rax; __int64
0x1800dd38b  lea     rax, [rsp+150h+var_F8]
0x1800dd390  mov     [rsp+150h+ptableid], rax; __int64
0x1800dd395  lea     rax, [rbp+50h+var_D0]
0x1800dd399  mov     qword ptr [rsp+150h+grbit], rax; __int64
0x1800dd39e  mov     qword ptr [rsp+150h+cbParameters], r14; __int64
0x1800dd3a3  call    ?DeleteItemOfLines@@YAJPEAVCallHistoryDataSession@@AEAVauto_JET_TABLEID@@AEBUUdmObjectId@@KPEAPEBGPEAV?$vector@UUdmNotifyStructure@@V?$allocator@UUdmNotifyStructure@@@utl@@@utl@@PEAH5@Z; DeleteItemOfLines(CallHistoryDataSession *,auto_JET_TABLEID &,UdmObjectId const &,ulong,ushort const * *,utl::vector<UdmNotifyStructure,utl::allocator<UdmNotifyStructure>> *,int *,int *)
0x1800dd3a8  mov     ebx, eax
0x1800dd3aa  test    eax, eax
0x1800dd3ac  js      loc_1800DD472
0x1800dd3b2  mov     r14d, dword ptr [rsp+150h+var_110]
0x1800dd3b7  lea     r15d, [r12+1]
0x1800dd3bc  test    r14d, r14d
0x1800dd3bf  jz      loc_1800DD4C9
0x1800dd3c5  mov     rbx, [rbp+50h+var_D0]
0x1800dd3c9  lea     rcx, [rsp+150h+var_108]; this
0x1800dd3ce  mov     rdi, rbx
0x1800dd3d1  mov     [rbp+50h+var_C8], rbx
0x1800dd3d5  call    ?NeedsBackoff@BackoffContext@@QEAAXXZ; BackoffContext::NeedsBackoff(void)
0x1800dd3da  lea     rcx, [rsp+150h+var_F0]; this
0x1800dd3df  call    ??1auto_JET_TRANSACTION@@QEAA@XZ; auto_JET_TRANSACTION::~auto_JET_TRANSACTION(void)
0x1800dd3e4  lea     rcx, [rsp+150h+var_108]; this
0x1800dd3e9  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800dd3ee  test    r14d, r14d
0x1800dd3f1  jz      loc_1800DD50A
0x1800dd3f7  mov     rbx, [rsp+150h+var_100]
0x1800dd3fc  mov     edi, [rsp+150h+var_104]
0x1800dd400  mov     edx, [rsp+150h+var_108]
0x1800dd404  mov     r14, [rbp+50h+var_B8]
0x1800dd408  jmp     loc_1800DD2DB
0x1800dd40d  xor     ebx, ebx
0x1800dd40f  cmp     ebx, r12d
0x1800dd412  jnb     loc_1800DD4C9
0x1800dd418  mov     rax, [rbp+50h+var_B0]
0x1800dd41c  lea     rcx, [rbx+rbx*2]
0x1800dd420  mov     r9d, r13d
0x1800dd423  lea     rdx, [rsp+150h+var_E0]; this
0x1800dd428  lea     r8, [rax+rcx*4]
0x1800dd42c  mov     rcx, rsi; struct CallHistoryDataSession *
0x1800dd42f  lea     rax, [rsp+150h+var_110]
0x1800dd434  mov     [rsp+150h+var_118], rax; __int64
0x1800dd439  lea     rax, [rsp+150h+var_F8]
0x1800dd43e  mov     [rsp+150h+ptableid], rax; __int64
0x1800dd443  lea     rax, [rbp+50h+var_D0]
0x1800dd447  mov     qword ptr [rsp+150h+grbit], rax; __int64
0x1800dd44c  mov     qword ptr [rsp+150h+cbParameters], r14; __int64
0x1800dd451  call    ?DeleteItemOfLines@@YAJPEAVCallHistoryDataSession@@AEAVauto_JET_TABLEID@@AEBUUdmObjectId@@KPEAPEBGPEAV?$vector@UUdmNotifyStructure@@V?$allocator@UUdmNotifyStructure@@@utl@@@utl@@PEAH5@Z; DeleteItemOfLines(CallHistoryDataSession *,auto_JET_TABLEID &,UdmObjectId const &,ulong,ushort const * *,utl::vector<UdmNotifyStructure,utl::allocator<UdmNotifyStructure>> *,int *,int *)
0x1800dd456  mov     edi, eax
0x1800dd458  test    eax, eax
0x1800dd45a  js      short loc_1800DD482
0x1800dd45c  mov     r14d, dword ptr [rsp+150h+var_110]
0x1800dd461  test    r14d, r14d
0x1800dd464  jnz     loc_1800DD3C5
0x1800dd46a  mov     r14, [rbp+50h+var_B8]
0x1800dd46e  inc     ebx
0x1800dd470  jmp     short loc_1800DD40F
0x1800dd472  mov     r9d, 408h
0x1800dd478  mov     edx, 1
0x1800dd47d  jmp     loc_1800DD597
0x1800dd482  mov     r9d, 417h
0x1800dd488  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800dd48f  mov     edx, 1
0x1800dd494  mov     ecx, edi
0x1800dd496  call    Log_HREvent
0x1800dd49b  lea     rcx, [rsp+150h+var_F0]; this
0x1800dd4a0  call    ??1auto_JET_TRANSACTION@@QEAA@XZ; auto_JET_TRANSACTION::~auto_JET_TRANSACTION(void)
0x1800dd4a5  lea     rcx, [rsp+150h+var_108]; this
0x1800dd4aa  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800dd4af  lea     rcx, [rbp+50h+var_D0]
0x1800dd4b3  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x1800dd4b8  lea     rcx, [rsp+150h+var_108]; this
0x1800dd4bd  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800dd4c2  mov     ebx, edi
0x1800dd4c4  jmp     loc_1800DD5CC
0x1800dd4c9  mov     edx, 1; unsigned int
0x1800dd4ce  lea     rcx, [rsp+150h+var_F0]; this
0x1800dd4d3  call    ?Commit@auto_JET_TRANSACTION@@QEAAJK@Z; auto_JET_TRANSACTION::Commit(ulong)
0x1800dd4d8  test    eax, eax
0x1800dd4da  jns     short loc_1800DD4EE
0x1800dd4dc  mov     ecx, eax; int
0x1800dd4de  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800dd4e3  mov     r9d, 423h
0x1800dd4e9  jmp     loc_1800DD593
0x1800dd4ee  lea     rcx, [rsp+150h+var_F0]; this
0x1800dd4f3  call    ??1auto_JET_TRANSACTION@@QEAA@XZ; auto_JET_TRANSACTION::~auto_JET_TRANSACTION(void)
0x1800dd4f8  lea     rcx, [rsp+150h+var_108]; this
0x1800dd4fd  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800dd502  mov     rdi, [rbp+50h+var_C8]
0x1800dd506  mov     rbx, [rbp+50h+var_D0]
0x1800dd50a  cmp     dword ptr [rsp+150h+var_F8], 0
0x1800dd50f  jz      short loc_1800DD54B
0x1800dd511  test    r15d, r15d
0x1800dd514  jz      short loc_1800DD56C
0x1800dd516  xor     edx, edx; Val
0x1800dd518  lea     rcx, [rbp+50h+var_A0]; void *
0x1800dd51c  lea     r8d, [rdx+48h]; Size
0x1800dd520  call    memset_0
0x1800dd525  mov     rcx, [rsi+7F8h]; this
0x1800dd52c  lea     rdx, [rbp+50h+var_A0]; struct UdmNotifyStructure *
0x1800dd530  mov     [rbp+50h+var_A0], 1
0x1800dd537  mov     [rbp+50h+var_98], 3
0x1800dd53e  call    ?PushNotify@DatabaseVolumeSession@@QEAAXAEBUUdmNotifyStructure@@@Z; DatabaseVolumeSession::PushNotify(UdmNotifyStructure const &)
0x1800dd543  mov     rcx, rsi; this
0x1800dd546  call    ?FlushUpdates@CallHistoryDataSession@@QEAAXXZ; CallHistoryDataSession::FlushUpdates(void)
0x1800dd54b  lea     rcx, [rbp+50h+var_D0]
0x1800dd54f  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x1800dd554  lea     rcx, [rsp+150h+var_108]; this
0x1800dd559  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800dd55e  lea     rcx, [rsp+150h+var_E0]; this
0x1800dd563  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800dd568  xor     eax, eax
0x1800dd56a  jmp     short loc_1800DD5D8
0x1800dd56c  cmp     rbx, rdi
0x1800dd56f  jz      short loc_1800DD543
0x1800dd571  mov     rcx, [rsi+7F8h]; this
0x1800dd578  mov     rdx, rbx; struct UdmNotifyStructure *
0x1800dd57b  call    ?PushNotify@DatabaseVolumeSession@@QEAAXAEBUUdmNotifyStructure@@@Z; DatabaseVolumeSession::PushNotify(UdmNotifyStructure const &)
0x1800dd580  add     rbx, 48h ; 'H'
0x1800dd584  jmp     short loc_1800DD56C
0x1800dd586  mov     ecx, eax; int
0x1800dd588  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x1800dd58d  mov     r9d, 3FAh
0x1800dd593  xor     edx, edx
0x1800dd595  mov     ebx, eax
0x1800dd597  lea     r8, aOnecoreuapBase_43; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800dd59e  mov     ecx, eax
0x1800dd5a0  call    Log_HREvent
0x1800dd5a5  lea     rcx, [rsp+150h+var_F0]; this
0x1800dd5aa  call    ??1auto_JET_TRANSACTION@@QEAA@XZ; auto_JET_TRANSACTION::~auto_JET_TRANSACTION(void)
0x1800dd5af  lea     rcx, [rsp+150h+var_108]; this
0x1800dd5b4  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800dd5b9  lea     rcx, [rbp+50h+var_D0]
0x1800dd5bd  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x1800dd5c2  lea     rcx, [rsp+150h+var_108]; this
0x1800dd5c7  call    ?Unlock@BackoffContext@@QEAAXXZ; BackoffContext::Unlock(void)
0x1800dd5cc  lea     rcx, [rsp+150h+var_E0]; this
0x1800dd5d1  call    ??1auto_JET_TABLEID@@QEAA@XZ; auto_JET_TABLEID::~auto_JET_TABLEID(void)
0x1800dd5d6  mov     eax, ebx
0x1800dd5d8  mov     rcx, [rbp+50h+var_40]
0x1800dd5dc  xor     rcx, rsp; StackCookie
0x1800dd5df  call    __security_check_cookie
0x1800dd5e4  mov     rbx, [rsp+150h+arg_8]
0x1800dd5ec  add     rsp, 120h
0x1800dd5f3  pop     r15
0x1800dd5f5  pop     r14
0x1800dd5f7  pop     r13
0x1800dd5f9  pop     r12
0x1800dd5fb  pop     rdi
0x1800dd5fc  pop     rsi
0x1800dd5fd  pop     rbp
0x1800dd5fe  retn
```
