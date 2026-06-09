# SetDefaultLanguage(ushort)

- ea: `0x100438960`
- end: `0x100438ec9`
- name: `?SetDefaultLanguage@@YA_NG@Z`
- size: `1385`
- prototype: `bool __fastcall(unsigned __int16)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1004369a0`

## callees

- `0x100401010`
- `0x1004010b0`
- `0x100401580`
- `0x100401aa0`
- `0x100402ec0`
- `0x100438960`
- `0x1004403d0`
- `0x10044aa30`
- `0x10044ba40`
- `0x10044bad0`

## import_xrefs

- `sqlmin!?reconfig@@YAXPEAVBaseXact@@KHHH@Z` at `0x100438d84`
- `sqlmin!?reconfig@@YAXPEAVBaseXact@@KHHH@Z` at `0x100438d84`
- `sqlmin!?Open@AutoOpenDB@@QEAAXPEAVBaseXact@@KKH@Z` at `0x100438b85`
- `sqlmin!?Open@AutoOpenDB@@QEAAXPEAVBaseXact@@KKH@Z` at `0x100438b85`
- `sqlmin!?CloseDB@AutoOpenDB@@AEAAXXZ` at `0x100438e06`
- `sqlmin!?CloseDB@AutoOpenDB@@AEAAXXZ` at `0x100438e06`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100438b66`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x100438b66`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100438bb6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100438e73`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100438bb6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100438e73`
- `sqldk!SystemThread_TlsOffset` at `0x100438a4c`
- `sqldk!SystemThread_TlsOffset` at `0x100438b9d`
- `sqldk!SystemThread_TlsOffset` at `0x100438e5a`
- `sqldk!SystemThread_TlsIndex` at `0x100438a3b`
- `sqldk!SystemThread_TlsIndex` at `0x100438b94`
- `sqldk!SystemThread_TlsIndex` at `0x100438e51`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100438e89`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100438e89`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100438ae0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100438bfe`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100438c96`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100438ae0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100438bfe`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x100438c96`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004389b3`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x1004389b3`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x1004389ea`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x100438bcc`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x100438bcc`

## string_xrefs

- `0x100438ce9`: `set deadlock_priority 10DECLARE @LangID AS smallint SELECT @LangID=langid FROM syslanguages WHERE lcid=%ld IF (@LangID IS NULL) BEGIN 	RAISERROR(15127, 20, -1) WITH LOG END EXEC sp_configure N'default language', @LangID EXEC sp_configure N'default full-text language', %ld `
- `0x100438d0f`: `set deadlock_priority 10EXEC sp_configure N'show advanced options', %ld `
- `0x100438ad4`: `rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SetDefaultLanguage(unsigned __int16 a1)
{
  unsigned __int16 v1; // r12
  struct __crt_locale_pointers *DefaultLocale; // r13
  unsigned __int8 v3; // di
  char v4; // r14
  __int64 v5; // r8
  char v6; // bl
  unsigned __int16 MasterDbId; // ax
  __int64 v8; // rbx
  __int64 v9; // rcx
  struct IExecSql *ExecSql; // rbx
  int v11; // r14d
  int v12; // esi
  char v13; // di
  int v14; // eax
  int v15; // eax
  struct BaseXact *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rcx
  int (*v20)(int, int, int, int, char *); // [rsp+20h] [rbp-1158h]
  struct Worker *v21; // [rsp+28h] [rbp-1150h]
  char v22; // [rsp+50h] [rbp-1128h]
  int v23; // [rsp+54h] [rbp-1124h]
  int v26; // [rsp+68h] [rbp-1110h] BYREF
  int v27; // [rsp+6Ch] [rbp-110Ch] BYREF
  int v28; // [rsp+70h] [rbp-1108h]
  __int128 v29; // [rsp+78h] [rbp-1100h]
  int v30; // [rsp+88h] [rbp-10F0h]
  __int64 v31; // [rsp+90h] [rbp-10E8h] BYREF
  int v32; // [rsp+98h] [rbp-10E0h]
  struct __crt_locale_pointers *v33; // [rsp+A0h] [rbp-10D8h]
  __int64 v34; // [rsp+A8h] [rbp-10D0h]
  _DWORD v35[6]; // [rsp+B0h] [rbp-10C8h] BYREF
  int v36; // [rsp+C8h] [rbp-10B0h] BYREF
  __int64 v37; // [rsp+D0h] [rbp-10A8h]
  __int64 v38; // [rsp+D8h] [rbp-10A0h]
  __int64 v39; // [rsp+E0h] [rbp-1098h]
  __int64 v40; // [rsp+E8h] [rbp-1090h]
  __int64 v41; // [rsp+F0h] [rbp-1088h]
  struct IExecSql *v42; // [rsp+F8h] [rbp-1080h]
  _BYTE v43[16]; // [rsp+100h] [rbp-1078h] BYREF
  _BYTE v44[48]; // [rsp+110h] [rbp-1068h] BYREF
  wchar_t Buffer[2048]; // [rsp+140h] [rbp-1038h] BYREF

  v41 = -2;
  v1 = a1;
  DefaultLocale = GetDefaultLocale();
  v33 = DefaultLocale;
  v3 = 1;
  v4 = 0;
  while ( !v4 )
  {
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v44, 0xCu, 5u, 0, hdl_backout, 0);
      v22 = 1;
      v26 = 0;
      v27 = 0;
      v29 = 0;
      v28 = 1;
      v5 = 8LL * SystemThread_TlsIndex;
      v34 = *(_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v5));
      *(_QWORD *)&v29 = *(_QWORD *)(v34 + 144);
      v34 = *(_QWORD *)(SystemThread_TlsOffset + *(_QWORD *)((char *)NtCurrentTeb()->ThreadLocalStoragePointer + v5));
      v6 = *(_BYTE *)(v34 + 152);
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v29 + 464LL))(v29) )
      {
        if ( v6 && (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v29 + 488LL))(v29) )
          utassert_fail(
            1u,
            "rwMode == CMsqlXact::ReadOnly || ctrOption == CMsqlXact::SupportCTR || !m_pMsqlXact->FSupportsCTR ()",
            "automsqlxact.cpp",
            235,
            0);
        (*(void (__fastcall **)(_QWORD, __int64, __int64, int *))(*(_QWORD *)v29 + 232LL))(v29, 2, 1, &v27);
        v28 = 1;
        v26 = 3;
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, const wchar_t *, __int64))(*(_QWORD *)v29 + 8LL))(
          v29,
          L"SetDefaultLanguage",
          36);
        v26 = 1;
      }
      v31 = 0;
      v32 = 0;
      MasterDbId = GetMasterDbId();
      AutoOpenDB::Open((AutoOpenDB *)&v31, 0, MasterDbId, 0, 1);
      v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v9 = *(_QWORD *)(v8 + 256);
      if ( !v9 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v9 = *(_QWORD *)(v8 + 256);
      }
      ExecSql = CreateExecSql(*(struct IMemObj **)(v9 + 1000), 0);
      v42 = ExecSql;
      if ( !ExecSql )
        utassert_fail(1u, "pExecSql", "setup.cpp", 901, 0);
      (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 48LL))(ExecSql);
      v11 = 0;
      v30 = 0;
      v12 = v23;
      while ( v11 < 4 )
      {
        if ( v1 && v1 != 1033 || v11 >= 3 )
        {
          v13 = 0;
          switch ( v11 )
          {
            case 0:
              LODWORD(v20) = 1;
              v15 = StringCchPrintf_lW(
                      Buffer,
                      0x800u,
                      L"set deadlock_priority 10EXEC sp_configure N'show advanced options', %ld ",
                      DefaultLocale,
                      v20);
              goto LABEL_31;
            case 1:
              LODWORD(v21) = v1;
              LODWORD(v20) = v1;
              v15 = StringCchPrintf_lW(
                      Buffer,
                      0x800u,
                      L"set deadlock_priority 10DECLARE @LangID AS smallint SELECT @LangID=langid FROM syslanguages WHERE "
                       "lcid=%ld IF (@LangID IS NULL) BEGIN \tRAISERROR(15127, 20, -1) WITH LOG END EXEC sp_configure N'd"
                       "efault language', @LangID EXEC sp_configure N'default full-text language', %ld ",
                      DefaultLocale,
                      v20,
                      v21);
              goto LABEL_31;
            case 2:
              v15 = StringCchPrintf_lW(
                      Buffer,
                      0x800u,
                      L"set deadlock_priority 10EXEC sp_configure N'show advanced options', %ld ",
                      DefaultLocale,
                      0);
LABEL_31:
              v23 = v15;
              v13 = 1;
              goto LABEL_32;
          }
          if ( v11 != 3 )
          {
            utassert_fail(1u, "FALSE", "setup.cpp", 978, "Invalid switch value");
            goto LABEL_33;
          }
          v14 = 1033;
          if ( v1 )
            v14 = v1;
          LODWORD(v20) = v14;
          v15 = StringCchPrintf_lW(
                  Buffer,
                  0x800u,
                  L"set deadlock_priority 10DECLARE @LanguageName AS nvarchar(128) SELECT @LanguageName=name FROM sys.sysl"
                   "anguages WHERE lcid=%ld IF (@LanguageName IS NULL) BEGIN \tRAISERROR(15127, 20, -1) WITH LOG END DECL"
                   "ARE @AlterLogin AS nvarchar(128) = 'ALTER LOGIN [sa] WITH DEFAULT_LANGUAGE = ' + @LanguageName EXEC s"
                   "p_executesql @AlterLogin",
                  DefaultLocale,
                  v20);
          v23 = v15;
LABEL_32:
          v12 = v15;
LABEL_33:
          CheckHrFailAndExit(v12, "String format error in SetDefaultLanguage");
          if ( !(*(unsigned int (__fastcall **)(struct IExecSql *, wchar_t *, _QWORD))(*(_QWORD *)ExecSql + 8LL))(
                  ExecSql,
                  Buffer,
                  0) )
          {
            v3 = 0;
            v22 = 0;
            goto LABEL_39;
          }
          if ( v13 )
          {
            v16 = (struct BaseXact *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v29 + 432LL))(v29);
            reconfig(v16, 4u, 0, 1, 0);
          }
          v30 = ++v11;
        }
        else
        {
          v30 = ++v11;
        }
      }
      v3 = 1;
LABEL_39:
      if ( v3 )
      {
        CAutoMsqlXact::CommitNestedXact((CAutoMsqlXact *)&v26, 0);
        scierrlog(0xC324u, a1);
      }
      else
      {
        scierrlog(0xC325u, a1);
      }
      v4 = 1;
      if ( ExecSql )
        (*(void (__fastcall **)(struct IExecSql *, __int64))(*(_QWORD *)ExecSql + 224LL))(ExecSql, 1);
      if ( v31 )
        AutoOpenDB::CloseDB((AutoOpenDB *)&v31);
      CAutoMsqlXact::~CAutoMsqlXact((CAutoMsqlXact *)&v26);
      ExcHandler::~ExcHandler((ExcHandler *)v44);
    }
    catch ( SQLError v35 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v43, (const struct SQLError *)v35);
        if ( v35[0] / 100 == 12 && v35[0] == 1205 )
        {
          ExceptionPassOn((const struct SQLError *)v35);
        }
        else
        {
          v36 = 4195594;
          v37 = 0;
          v39 = 0;
          v38 = 0;
          v40 = 0;
          SOS_Task::Sleep(250, &v36);
        }
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v43);
      }
      catch ( ShortStackException )
      {
      }
      DefaultLocale = v33;
      v3 = v22;
      v4 = 1;
      v12 = v23;
      v1 = a1;
    }
    v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v18 = *(_QWORD *)(v17 + 256);
    if ( !v18 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v18 = *(_QWORD *)(v17 + 256);
    }
    if ( *(_DWORD *)(v18 + 556) )
      ExceptionPostCatchActions((struct Worker *)v18);
    v23 = v12;
  }
  return v3;
}

```

## disassembly

```asm
0x100438960  push    rdi
0x100438962  push    r12
0x100438964  push    r13
0x100438966  push    r14
0x100438968  push    r15
0x10043896a  mov     eax, 1150h
0x10043896f  call    _alloca_probe
0x100438974  sub     rsp, rax
0x100438977  mov     [rsp+1178h+var_1088], 0FFFFFFFFFFFFFFFEh
0x100438983  mov     [rsp+1178h+arg_8], rbx
0x10043898b  mov     [rsp+1178h+arg_10], rsi
0x100438993  mov     rax, cs:__security_cookie
0x10043899a  xor     rax, rsp
0x10043899d  mov     [rsp+1178h+var_38], rax
0x1004389a5  movzx   r12d, cx
0x1004389a9  mov     [rsp+1178h+var_1118], cx
0x1004389ae  mov     [rsp+1178h+var_1120], cx
0x1004389b3  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x1004389b9  mov     r13, rax
0x1004389bc  mov     [rsp+1178h+var_10D8], rax
0x1004389c4  mov     dil, 1
0x1004389c7  xor     r14b, r14b
0x1004389ca  xor     r15d, r15d
0x1004389cd  mov     [rsp+1178h+var_1126], r14b
0x1004389d2  mov     [rsp+1178h+var_1128], dil
0x1004389d7  test    r14b, r14b
0x1004389da  jnz     loc_100438E98
0x1004389e0  mov     edx, 0Ch; unsigned __int16
0x1004389e5  mov     [rsp+1178h+var_1150], r15; struct Worker *
0x1004389ea  mov     rax, cs:__imp_?hdl_backout@@YAHHHHHPEAD@Z; hdl_backout(int,int,int,int,char *)
0x1004389f1  mov     [rsp+1178h+var_1158], rax; int (*)(int, int, int, int, char *)
0x1004389f6  xor     r9d, r9d; unsigned __int8
0x1004389f9  mov     r8b, 5; unsigned __int8
0x1004389fc  lea     rcx, [rsp+1178h+var_1068]; this
0x100438a04  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x100438a09  nop
0x100438a0a  mov     [rsp+1178h+var_1128], 1
0x100438a0f  mov     [rsp+1178h+var_1110], r15d
0x100438a14  mov     [rsp+1178h+var_110C], r15d
0x100438a19  mov     [rsp+1178h+var_1108], 1
0x100438a21  xorps   xmm0, xmm0
0x100438a24  movdqu  [rsp+1178h+var_1100], xmm0
0x100438a2a  mov     [rsp+1178h+var_1108], 1
0x100438a32  mov     rdx, gs:58h
0x100438a3b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100438a42  mov     ecx, [rax]
0x100438a44  lea     r8, ds:0[rcx*8]
0x100438a4c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100438a53  mov     ecx, [rax]
0x100438a55  mov     rax, [r8+rdx]
0x100438a59  mov     rax, [rcx+rax]
0x100438a5d  mov     [rsp+1178h+var_10D0], rax
0x100438a65  mov     rax, [rax+90h]
0x100438a6c  mov     qword ptr [rsp+1178h+var_1100], rax
0x100438a71  mov     rax, gs:58h
0x100438a7a  mov     rax, [r8+rax]
0x100438a7e  mov     rcx, [rcx+rax]
0x100438a82  mov     [rsp+1178h+var_10D0], rcx
0x100438a8a  movzx   ebx, byte ptr [rcx+98h]
0x100438a91  mov     edi, r15d
0x100438a94  test    bl, bl
0x100438a96  setnz   dil
0x100438a9a  mov     rcx, qword ptr [rsp+1178h+var_1100]
0x100438a9f  mov     rax, [rcx]
0x100438aa2  call    qword ptr [rax+1D0h]
0x100438aa8  test    al, al
0x100438aaa  jz      short loc_100438B14
0x100438aac  test    bl, bl
0x100438aae  jz      short loc_100438AE6
0x100438ab0  mov     rcx, qword ptr [rsp+1178h+var_1100]
0x100438ab5  mov     rax, [rcx]
0x100438ab8  call    qword ptr [rax+1E8h]
0x100438abe  test    al, al
0x100438ac0  jz      short loc_100438AE6
0x100438ac2  mov     [rsp+1178h+var_1158], r15
0x100438ac7  mov     r9d, 0EBh
0x100438acd  lea     r8, aAutomsqlxactCp; "automsqlxact.cpp"
0x100438ad4  lea     rdx, ?szExpression@?9??BeginNestedXact@CAutoMsqlXact@@QEAAXPEB_WHW4ReadWriteMode@CMsqlXact@@W4DistributionMode@4@W4NestedXactOption@4@W4CTRSupportOption@4@@Z@4QBDB; "rwMode == CMsqlXact::ReadOnly || ctrOpt"...
0x100438adb  mov     ecx, 1
0x100438ae0  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100438ae6  mov     rcx, qword ptr [rsp+1178h+var_1100]
0x100438aeb  mov     rax, [rcx]
0x100438aee  lea     r9, [rsp+1178h+var_110C]
0x100438af3  mov     edx, 2
0x100438af8  lea     r8d, [rdx-1]
0x100438afc  call    qword ptr [rax+0E8h]
0x100438b02  mov     [rsp+1178h+var_1108], 1
0x100438b0a  mov     [rsp+1178h+var_1110], 3
0x100438b12  jmp     short loc_100438B56
0x100438b14  mov     rcx, qword ptr [rsp+1178h+var_1100]
0x100438b19  mov     rax, [rcx]
0x100438b1c  mov     [rsp+1178h+var_1138], edi
0x100438b20  mov     [rsp+1178h+var_1140], r15
0x100438b25  mov     [rsp+1178h+var_1148], 0
0x100438b2a  mov     dword ptr [rsp+1178h+var_1150], 1
0x100438b32  mov     dword ptr [rsp+1178h+var_1158], 2
0x100438b3a  mov     r9d, 1
0x100438b40  lea     r8d, [r9+23h]
0x100438b44  lea     rdx, aSetdefaultlang; "SetDefaultLanguage"
0x100438b4b  call    qword ptr [rax+8]
0x100438b4e  mov     [rsp+1178h+var_1110], 1
0x100438b56  mov     [rsp+1178h+var_10E8], r15
0x100438b5e  mov     [rsp+1178h+var_10E0], r15d
0x100438b66  call    cs:__imp_?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x100438b6c  movzx   r8d, ax
0x100438b70  mov     dword ptr [rsp+1178h+var_1158], 1
0x100438b78  xor     r9d, r9d
0x100438b7b  xor     edx, edx
0x100438b7d  lea     rcx, [rsp+1178h+var_10E8]
0x100438b85  call    cs:__imp_?Open@AutoOpenDB@@QEAAXPEAVBaseXact@@KKH@Z; AutoOpenDB::Open(BaseXact *,ulong,ulong,int)
0x100438b8b  mov     rdx, gs:58h
0x100438b94  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100438b9b  mov     ecx, [rax]
0x100438b9d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100438ba4  mov     ebx, [rax]
0x100438ba6  add     rbx, [rdx+rcx*8]
0x100438baa  mov     rcx, [rbx+100h]
0x100438bb1  test    rcx, rcx
0x100438bb4  jnz     short loc_100438BC3
0x100438bb6  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100438bbc  mov     rcx, [rbx+100h]
0x100438bc3  xor     edx, edx
0x100438bc5  mov     rcx, [rcx+3E8h]
0x100438bcc  call    cs:__imp_?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z; CreateExecSql(IMemObj *,ICallerParse *)
0x100438bd2  mov     rbx, rax
0x100438bd5  mov     [rsp+1178h+var_1080], rax
0x100438bdd  test    rax, rax
0x100438be0  jnz     short loc_100438C04
0x100438be2  mov     [rsp+1178h+var_1158], r15
0x100438be7  mov     r9d, 385h
0x100438bed  lea     r8, aSetupCpp; "setup.cpp"
0x100438bf4  lea     rdx, aPexecsql; "pExecSql"
0x100438bfb  lea     ecx, [rax+1]
0x100438bfe  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100438c04  mov     rax, [rbx]
0x100438c07  mov     rcx, rbx
0x100438c0a  call    qword ptr [rax+30h]
0x100438c0d  mov     r14d, r15d
0x100438c10  mov     [rsp+1178h+var_10F0], r15d
0x100438c18  mov     esi, [rsp+1178h+var_1124]
0x100438c1c  nop     dword ptr [rax+00h]
0x100438c20  cmp     r14d, 4
0x100438c24  jge     loc_100438DA4
0x100438c2a  mov     ecx, 409h
0x100438c2f  cmp     r15w, r12w
0x100438c33  jz      short loc_100438C3B
0x100438c35  cmp     cx, r12w
0x100438c39  jnz     short loc_100438C4E
0x100438c3b  cmp     r14d, 3
0x100438c3f  jge     short loc_100438C4E
0x100438c41  inc     r14d
0x100438c44  mov     [rsp+1178h+var_10F0], r14d
0x100438c4c  jmp     short loc_100438C20
0x100438c4e  xor     dil, dil
0x100438c51  mov     [rsp+1178h+var_1127], dil
0x100438c56  mov     eax, r14d
0x100438c59  test    r14d, r14d
0x100438c5c  jz      loc_100438D04
0x100438c62  sub     eax, 1
0x100438c65  jz      short loc_100438CDA
0x100438c67  sub     eax, 1
0x100438c6a  jz      short loc_100438CD3
0x100438c6c  cmp     eax, 1
0x100438c6f  jz      short loc_100438CA1
0x100438c71  lea     rax, aInvalidSwitchV; "Invalid switch value"
0x100438c78  mov     [rsp+1178h+var_1158], rax
0x100438c7d  mov     r9d, 3D2h
0x100438c83  lea     r8, aSetupCpp; "setup.cpp"
0x100438c8a  lea     rdx, aFalse_0; "FALSE"
0x100438c91  mov     ecx, 1
0x100438c96  call    cs:__imp_?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x100438c9c  jmp     loc_100438D36
0x100438ca1  cmp     r15w, r12w
0x100438ca5  mov     eax, ecx
0x100438ca7  jz      short loc_100438CAD
0x100438ca9  movzx   eax, r12w
0x100438cad  mov     dword ptr [rsp+1178h+var_1158], eax
0x100438cb1  mov     r9, r13; struct __crt_locale_pointers *
0x100438cb4  lea     r8, aSetDeadlockPri_4; "set deadlock_priority 10DECLARE @Langua"...
0x100438cbb  mov     edx, 800h; unsigned __int64
0x100438cc0  lea     rcx, [rsp+1178h+Buffer]; Buffer
0x100438cc8  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100438ccd  mov     [rsp+1178h+var_1124], eax
0x100438cd1  jmp     short loc_100438D34
0x100438cd3  mov     [rsp+1178h+var_1158], r15
0x100438cd8  jmp     short loc_100438D0C
0x100438cda  movzx   eax, r12w
0x100438cde  mov     dword ptr [rsp+1178h+var_1150], eax
0x100438ce2  mov     dword ptr [rsp+1178h+var_1158], eax
0x100438ce6  mov     r9, r13; struct __crt_locale_pointers *
0x100438ce9  lea     r8, aSetDeadlockPri_2; "set deadlock_priority 10DECLARE @LangID"...
0x100438cf0  mov     edx, 800h; unsigned __int64
0x100438cf5  lea     rcx, [rsp+1178h+Buffer]; Buffer
0x100438cfd  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100438d02  jmp     short loc_100438D28
0x100438d04  mov     dword ptr [rsp+1178h+var_1158], 1
0x100438d0c  mov     r9, r13; struct __crt_locale_pointers *
0x100438d0f  lea     r8, aSetDeadlockPri_0; "set deadlock_priority 10EXEC sp_configu"...
0x100438d16  mov     edx, 800h; unsigned __int64
0x100438d1b  lea     rcx, [rsp+1178h+Buffer]; Buffer
0x100438d23  call    ?StringCchPrintf_lW@@YAJPEA_W_KPEB_WPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lW(wchar_t *,unsigned __int64,wchar_t const *,__crt_locale_pointers *,...)
0x100438d28  mov     [rsp+1178h+var_1124], eax
0x100438d2c  mov     dil, 1
0x100438d2f  mov     [rsp+1178h+var_1127], dil
0x100438d34  mov     esi, eax
0x100438d36  lea     rdx, aStringFormatEr_0; "String format error in SetDefaultLangua"...
0x100438d3d  mov     ecx, esi; int
0x100438d3f  call    ?CheckHrFailAndExit@@YAXJPEBD@Z; CheckHrFailAndExit(long,char const *)
0x100438d44  mov     rax, [rbx]
0x100438d47  xor     r8d, r8d
0x100438d4a  lea     rdx, [rsp+1178h+Buffer]
0x100438d52  mov     rcx, rbx
0x100438d55  call    qword ptr [rax+8]
0x100438d58  test    eax, eax
0x100438d5a  jz      short loc_100438D9A
0x100438d5c  test    dil, dil
0x100438d5f  jz      short loc_100438D8A
0x100438d61  mov     rcx, qword ptr [rsp+1178h+var_1100]
0x100438d66  mov     rax, [rcx]
0x100438d69  call    qword ptr [rax+1B0h]
0x100438d6f  mov     rcx, rax
0x100438d72  mov     dword ptr [rsp+1178h+var_1158], r15d
0x100438d77  mov     r9d, 1
0x100438d7d  xor     r8d, r8d
0x100438d80  lea     edx, [r9+3]
0x100438d84  call    cs:__imp_?reconfig@@YAXPEAVBaseXact@@KHHH@Z; reconfig(BaseXact *,ulong,int,int,int)
0x100438d8a  inc     r14d
0x100438d8d  mov     [rsp+1178h+var_10F0], r14d
0x100438d95  jmp     loc_100438C20
0x100438d9a  xor     dil, dil
0x100438d9d  mov     [rsp+1178h+var_1128], dil
0x100438da2  jmp     short loc_100438DA9
0x100438da4  movzx   edi, [rsp+1178h+var_1128]
0x100438da9  movzx   r14d, [rsp+1178h+var_1120]
0x100438daf  test    dil, dil
0x100438db2  jz      short loc_100438DC7
0x100438db4  xor     edx, edx; bool
0x100438db6  lea     rcx, [rsp+1178h+var_1110]; this
0x100438dbb  call    ?CommitNestedXact@CAutoMsqlXact@@QEAAX_N@Z; CAutoMsqlXact::CommitNestedXact(bool)
0x100438dc0  mov     ecx, 0C324h
0x100438dc5  jmp     short loc_100438DCC
0x100438dc7  mov     ecx, 0C325h; unsigned int
0x100438dcc  mov     edx, r14d
0x100438dcf  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100438dd4  mov     r14b, 1
0x100438dd7  mov     [rsp+1178h+var_1126], r14b
0x100438ddc  test    rbx, rbx
0x100438ddf  jz      short loc_100438DF3
0x100438de1  mov     rax, [rbx]
0x100438de4  mov     edx, 1
0x100438de9  mov     rcx, rbx
0x100438dec  call    qword ptr [rax+0E0h]
0x100438df2  nop
0x100438df3  cmp     [rsp+1178h+var_10E8], 0
0x100438dfc  jz      short loc_100438E0D
0x100438dfe  lea     rcx, [rsp+1178h+var_10E8]
0x100438e06  call    cs:__imp_?CloseDB@AutoOpenDB@@AEAAXXZ; AutoOpenDB::CloseDB(void)
0x100438e0c  nop
0x100438e0d  lea     rcx, [rsp+1178h+var_1110]; this
0x100438e12  call    ??1CAutoMsqlXact@@QEAA@XZ; CAutoMsqlXact::~CAutoMsqlXact(void)
0x100438e17  nop
0x100438e18  lea     rcx, [rsp+1178h+var_1068]; this
0x100438e20  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x100438e25  nop
0x100438e26  jmp     short loc_100438E48
0x100438e28  xor     r15d, r15d
0x100438e2b  mov     r13, [rsp+1178h+var_10D8]
0x100438e33  movzx   edi, [rsp+1178h+var_1128]
0x100438e38  movzx   r14d, [rsp+1178h+var_1126]
0x100438e3e  mov     esi, [rsp+1178h+var_1124]
0x100438e42  movzx   r12d, [rsp+1178h+var_1118]
0x100438e48  mov     rdx, gs:58h
0x100438e51  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100438e58  mov     ecx, [rax]
0x100438e5a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100438e61  mov     ebx, [rax]
0x100438e63  add     rbx, [rdx+rcx*8]
0x100438e67  mov     rcx, [rbx+100h]
0x100438e6e  test    rcx, rcx
0x100438e71  jnz     short loc_100438E80
0x100438e73  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100438e79  mov     rcx, [rbx+100h]
0x100438e80  cmp     dword ptr [rcx+22Ch], 0
0x100438e87  jz      short loc_100438E8F
0x100438e89  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x100438e8f  mov     [rsp+1178h+var_1124], esi
0x100438e93  jmp     loc_1004389CD
0x100438e98  movzx   eax, dil
0x100438e9c  mov     rcx, [rsp+1178h+var_38]
0x100438ea4  xor     rcx, rsp; StackCookie
0x100438ea7  call    __security_check_cookie
0x100438eac  lea     r11, [rsp+1178h+var_28]
0x100438eb4  mov     rbx, [r11+38h]
0x100438eb8  mov     rsi, [r11+40h]
0x100438ebc  mov     rsp, r11
0x100438ebf  pop     r15
0x100438ec1  pop     r14
0x100438ec3  pop     r13
0x100438ec5  pop     r12
0x100438ec7  pop     rdi
  ... truncated ...
```
