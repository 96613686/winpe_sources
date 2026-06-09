# JobStore::InitJobStore(void)

- ea: `0x18006c234`
- end: `0x18006c5b1`
- name: `?InitJobStore@JobStore@@AEAAJXZ`
- size: `893`
- prototype: `__int64 __fastcall(JobStore *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006b3ac`

## callees

- `0x180001520`
- `0x180001630`
- `0x18000dc30`
- `0x1800265c4`
- `0x1800290f0`
- `0x180039d00`
- `0x180052584`
- `0x180054084`
- `0x180056450`
- `0x18005b124`
- `0x18006b190`
- `0x18006b590`
- `0x18006b940`
- `0x18006c0c8`
- `0x18006c234`
- `0x18006c5b8`
- `0x18006e92c`
- `0x180070288`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006c330`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006c330`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006c2c4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006c2c4`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18006c39e`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18006c39e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18006c44d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18006c44d`

## string_xrefs

- `0x18006c407`: `%SystemRoot%\System32\Tasks`
- `0x18006c424`: `%SystemRoot%\System32\Tasks_Migrated`
- `0x18006c253`: `Configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JobStore::InitJobStore(JobStore *this)
{
  unsigned __int16 **v1; // rdi
  const WCHAR *v2; // rdx
  LSTATUS v3; // eax
  int inited; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned __int16 *EventW; // rsi
  int v8; // edx
  tsched *v9; // rcx
  __int64 v10; // rax
  unsigned __int16 **v11; // rsi
  JobStore *v12; // rcx
  JobStore *v13; // rcx
  int v14; // ebx
  int v15; // r8d
  int v16; // r9d
  int v17; // r8d
  int v18; // r9d
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-28h] BYREF
  JobStore *v21; // [rsp+A0h] [rbp+28h] BYREF
  unsigned __int8 v22; // [rsp+A8h] [rbp+30h] BYREF
  int v23; // [rsp+B0h] [rbp+38h] BYREF
  const WCHAR **v24; // [rsp+B8h] [rbp+40h] BYREF

  v21 = this;
  v1 = (unsigned __int16 **)JobStore::m_pCommonStore;
  JobStore::InitConfig(JobStore::m_pCommonStore);
  _bstr_t::_bstr_t((_bstr_t *)&v24, L"Configuration");
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = tsched::StoreSecurity::g_pConfigKeySecurity;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  if ( v24 )
    v2 = *v24;
  else
    v2 = 0;
  v3 = RegCreateKeyExW((HKEY)v1[2], v2, 0, 0, 0, 0x20019u, &SecurityAttributes, (PHKEY)v1 + 5, 0);
  inited = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      inited = (unsigned __int16)v3 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 13;
LABEL_11:
      WPP_SF_d(v5[2], v6, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, (unsigned int)inited);
    }
  }
  else
  {
    EventW = (unsigned __int16 *)CreateEventW(0, 0, 0, 0);
    wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)(v1 + 6));
    v1[6] = EventW;
    if ( EventW )
    {
      v10 = RegisterWaitForSingleObjectEx(EventW, JobStore::ConfigurationChangeCallback, v1, 0xFFFFFFFFLL, 128);
      v1[7] = (unsigned __int16 *)v10;
      if ( v10 )
      {
        JobStore::ConfigurationChangeCallback(v1, 0);
        inited = JobStore::ExpandEnvironmentString(L"%SystemRoot%\\System32\\Tasks");
        if ( inited >= 0 )
        {
          v11 = v1 + 1;
          inited = JobStore::ExpandEnvironmentString(L"%SystemRoot%\\System32\\Tasks_Migrated");
          if ( inited >= 0 )
          {
            if ( JobStore::GetUseXmlStore((JobStore *)v1)
              && PathFileExistsW(*v11)
              && !(unsigned int)JobStore::IsMigrationCleanupCompleted((JobStore *)v1) )
            {
              v22 = 0;
              LOBYTE(v21) = 0;
              inited = JobStore::TakeBackupRestorePermissions(v12, &v22, (unsigned __int8 *)&v21);
              if ( inited < 0 )
                goto LABEL_44;
              v14 = JobStore::CopyDirectoryWithPermissionsRecursive((JobStore *)v1, *v11, *v1);
              if ( v14 < 0 )
              {
                v13 = (JobStore *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids);
                }
                if ( (unsigned int)dword_1800BC358 > 4 && (unsigned __int8)tlgKeywordOn(v13, 0x400000000001LL) )
                {
                  v23 = v14;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                    (_DWORD)v13,
                    (unsigned int)&unk_1800AD830,
                    v15,
                    v16,
                    (__int64)&v23);
                }
              }
              if ( (unsigned int)dword_1800BC358 > 4 && (unsigned __int8)tlgKeywordOn(v13, 0x400000000001LL) )
              {
                v23 = v14;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (_DWORD)v13,
                  (unsigned int)byte_1800AD8AB,
                  v17,
                  v18,
                  (__int64)&v23);
              }
              JobStore::DropBackupRestorePermissions(v13, v22, (unsigned __int8)v21);
            }
            inited = JobStore::InitKnownTreeFolder(
                       (HKEY *)v1,
                       L"\\",
                       L"O:SYG:SYD:PAI(A;CI;FA;;;BA)(A;OI;FRFWSDWDWO;;;BA)(A;CI;FA;;;SY)(A;OI;FRFWSDWDWO;;;SY)(A;CI;FW;;;A"
                        "U)(A;CI;FW;;;NS)(A;CI;FW;;;LS)(A;OICIIO;FA;;;CO)");
            if ( inited >= 0 )
            {
              inited = JobStore::InitKnownTreeFolder(
                         (HKEY *)v1,
                         L"\\Microsoft",
                         L"O:SYG:SYD:PAI(A;CI;FA;;;BA)(A;OI;0x1f019f;;;BA)(A;CI;FA;;;SY)(A;OI;0x1f019f;;;SY)(A;OICI;FR;;;A"
                          "U)(A;OICI;FR;;;LS)(A;OICI;FR;;;NS)(A;OICIIO;FA;;;CO)S:AI");
              if ( inited >= 0 )
              {
                inited = JobStore::InitKnownTreeFolder(
                           (HKEY *)v1,
                           L"\\Microsoft\\Windows",
                           L"O:SYG:SYD:AI(A;CIID;FA;;;BA)(A;OIIOID;0x1f019f;;;BA)(A;CIID;FA;;;SY)(A;OIIOID;0x1f019f;;;SY)("
                            "A;OICIID;FR;;;AU)(A;OICIID;FR;;;LS)(A;OICIID;FR;;;NS)(A;OICIIOID;FA;;;CO)S:AI");
                if ( inited >= 0 )
                  inited = 0;
              }
            }
          }
        }
      }
      else
      {
        inited = -2147467259;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids);
        }
      }
    }
    else
    {
      inited = tsched::GetLastHrError(v9, v8);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 14;
        goto LABEL_11;
      }
    }
  }
LABEL_44:
  _bstr_t::~_bstr_t((_bstr_t *)&v24);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18006c234  mov     [rsp-20h+arg_0], rcx
0x18006c239  push    rbp
0x18006c23a  push    rbx
0x18006c23b  push    rsi
0x18006c23c  push    rdi
0x18006c23d  mov     rbp, rsp
0x18006c240  sub     rsp, 78h
0x18006c244  mov     rdi, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x18006c24b  mov     rcx, rdi; this
0x18006c24e  call    ?InitConfig@JobStore@@AEAAXXZ; JobStore::InitConfig(void)
0x18006c253  lea     rdx, aConfiguration; "Configuration"
0x18006c25a  lea     rcx, [rbp+arg_18]; this
0x18006c25e  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006c263  nop
0x18006c264  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x18006c26c  mov     rax, cs:?g_pConfigKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pConfigKeySecurity
0x18006c273  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x18006c277  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], 0
0x18006c27f  mov     rax, [rbp+arg_18]
0x18006c283  test    rax, rax
0x18006c286  jz      short loc_18006C28D
0x18006c288  mov     rdx, [rax]
0x18006c28b  jmp     short loc_18006C28F
0x18006c28d  xor     edx, edx; lpSubKey
0x18006c28f  lea     rax, [rdi+28h]
0x18006c293  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18006c29c  mov     [rsp+78h+phkResult], rax; phkResult
0x18006c2a1  lea     rax, [rbp+SecurityAttributes]
0x18006c2a5  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18006c2aa  mov     [rsp+78h+samDesired], 20019h; samDesired
0x18006c2b2  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18006c2ba  xor     r9d, r9d; lpClass
0x18006c2bd  xor     r8d, r8d; Reserved
0x18006c2c0  mov     rcx, [rdi+10h]; hKey
0x18006c2c4  call    cs:__imp_RegCreateKeyExW
0x18006c2ca  mov     ebx, eax
0x18006c2cc  test    eax, eax
0x18006c2ce  jz      short loc_18006C326
0x18006c2d0  jle     short loc_18006C2DB
0x18006c2d2  movzx   ebx, ax
0x18006c2d5  or      ebx, 80070000h
0x18006c2db  lea     rax, WPP_GLOBAL_Control
0x18006c2e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c2e9  cmp     rcx, rax
0x18006c2ec  jz      loc_18006C59D
0x18006c2f2  test    dword ptr [rcx+1Ch], 40000h
0x18006c2f9  jz      loc_18006C59D
0x18006c2ff  cmp     byte ptr [rcx+19h], 2
0x18006c303  jb      loc_18006C59D
0x18006c309  mov     edx, 0Dh
0x18006c30e  mov     r9d, ebx
0x18006c311  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18006c318  mov     rcx, [rcx+10h]
0x18006c31c  call    WPP_SF_d
0x18006c321  jmp     loc_18006C59D
0x18006c326  xor     r9d, r9d; lpName
0x18006c329  xor     r8d, r8d; bInitialState
0x18006c32c  xor     edx, edx; bManualReset
0x18006c32e  xor     ecx, ecx; lpEventAttributes
0x18006c330  call    cs:__imp_CreateEventW
0x18006c336  mov     rsi, rax
0x18006c339  lea     rcx, [rdi+30h]; this
0x18006c33d  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18006c342  mov     [rdi+30h], rsi
0x18006c346  test    rsi, rsi
0x18006c349  jnz     short loc_18006C385
0x18006c34b  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006c350  mov     ebx, eax
0x18006c352  lea     rax, WPP_GLOBAL_Control
0x18006c359  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c360  cmp     rcx, rax
0x18006c363  jz      loc_18006C59D
0x18006c369  test    dword ptr [rcx+1Ch], 40000h
0x18006c370  jz      loc_18006C59D
0x18006c376  cmp     byte ptr [rcx+19h], 2
0x18006c37a  jb      loc_18006C59D
0x18006c380  lea     edx, [rsi+0Eh]
0x18006c383  jmp     short loc_18006C30E
0x18006c385  mov     [rsp+78h+dwOptions], 80h
0x18006c38d  or      r9d, 0FFFFFFFFh
0x18006c391  mov     r8, rdi
0x18006c394  lea     rdx, ?ConfigurationChangeCallback@JobStore@@CAXPEAXE@Z; JobStore::ConfigurationChangeCallback(void *,uchar)
0x18006c39b  mov     rcx, rsi
0x18006c39e  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18006c3a4  mov     [rdi+38h], rax
0x18006c3a8  test    rax, rax
0x18006c3ab  jnz     short loc_18006C3FA
0x18006c3ad  mov     ebx, 80004005h
0x18006c3b2  lea     rax, WPP_GLOBAL_Control
0x18006c3b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c3c0  cmp     rcx, rax
0x18006c3c3  jz      loc_18006C59D
0x18006c3c9  test    dword ptr [rcx+1Ch], 40000h
0x18006c3d0  jz      loc_18006C59D
0x18006c3d6  cmp     byte ptr [rcx+19h], 2
0x18006c3da  jb      loc_18006C59D
0x18006c3e0  mov     edx, 0Fh
0x18006c3e5  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18006c3ec  mov     rcx, [rcx+10h]
0x18006c3f0  call    WPP_SF_
0x18006c3f5  jmp     loc_18006C59D
0x18006c3fa  xor     edx, edx; unsigned __int8
0x18006c3fc  mov     rcx, rdi; void *
0x18006c3ff  call    ?ConfigurationChangeCallback@JobStore@@CAXPEAXE@Z; JobStore::ConfigurationChangeCallback(void *,uchar)
0x18006c404  mov     rdx, rdi
0x18006c407  lea     rcx, aSystemrootSyst_3; "%SystemRoot%\\System32\\Tasks"
0x18006c40e  call    ?ExpandEnvironmentString@JobStore@@SAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::ExpandEnvironmentString(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x18006c413  mov     ebx, eax
0x18006c415  test    eax, eax
0x18006c417  js      loc_18006C59D
0x18006c41d  lea     rsi, [rdi+8]
0x18006c421  mov     rdx, rsi
0x18006c424  lea     rcx, aSystemrootSyst_2; "%SystemRoot%\\System32\\Tasks_Migrated"
0x18006c42b  call    ?ExpandEnvironmentString@JobStore@@SAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::ExpandEnvironmentString(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x18006c430  mov     ebx, eax
0x18006c432  test    eax, eax
0x18006c434  js      loc_18006C59D
0x18006c43a  mov     rcx, rdi; this
0x18006c43d  call    ?GetUseXmlStore@JobStore@@QEBAEXZ; JobStore::GetUseXmlStore(void)
0x18006c442  test    al, al
0x18006c444  jz      loc_18006C547
0x18006c44a  mov     rcx, [rsi]; pszPath
0x18006c44d  call    cs:__imp_PathFileExistsW
0x18006c453  test    eax, eax
0x18006c455  jz      loc_18006C547
0x18006c45b  mov     rcx, rdi; this
0x18006c45e  call    ?IsMigrationCleanupCompleted@JobStore@@QEBAHXZ; JobStore::IsMigrationCleanupCompleted(void)
0x18006c463  test    eax, eax
0x18006c465  jnz     loc_18006C547
0x18006c46b  mov     [rbp+arg_8], al
0x18006c46e  mov     byte ptr [rbp+arg_0], al
0x18006c471  lea     r8, [rbp+arg_0]; unsigned __int8 *
0x18006c475  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x18006c479  call    ?TakeBackupRestorePermissions@JobStore@@AEBAJPEAE0@Z; JobStore::TakeBackupRestorePermissions(uchar *,uchar *)
0x18006c47e  mov     ebx, eax
0x18006c480  test    eax, eax
0x18006c482  js      loc_18006C59D
0x18006c488  mov     r8, [rdi]; unsigned __int16 *
0x18006c48b  mov     rdx, [rsi]; unsigned __int16 *
0x18006c48e  mov     rcx, rdi; this
0x18006c491  call    ?CopyDirectoryWithPermissionsRecursive@JobStore@@QEBAJPEAG0@Z; JobStore::CopyDirectoryWithPermissionsRecursive(ushort *,ushort *)
0x18006c496  mov     ebx, eax
0x18006c498  mov     rsi, 400000000001h
0x18006c4a2  test    eax, eax
0x18006c4a4  jns     short loc_18006C50C
0x18006c4a6  lea     rax, WPP_GLOBAL_Control
0x18006c4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c4b4  cmp     rcx, rax
0x18006c4b7  jz      short loc_18006C4DD
0x18006c4b9  test    dword ptr [rcx+1Ch], 40000h
0x18006c4c0  jz      short loc_18006C4DD
0x18006c4c2  cmp     byte ptr [rcx+19h], 2
0x18006c4c6  jb      short loc_18006C4DD
0x18006c4c8  mov     edx, 10h
0x18006c4cd  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18006c4d4  mov     rcx, [rcx+10h]
0x18006c4d8  call    WPP_SF_
0x18006c4dd  mov     eax, cs:dword_1800BC358
0x18006c4e3  cmp     eax, 4
0x18006c4e6  jbe     short loc_18006C50C
0x18006c4e8  mov     rdx, rsi
0x18006c4eb  call    _tlgKeywordOn
0x18006c4f0  test    al, al
0x18006c4f2  jz      short loc_18006C50C
0x18006c4f4  mov     [rbp+arg_10], ebx
0x18006c4f7  lea     rax, [rbp+arg_10]
0x18006c4fb  mov     qword ptr [rsp+78h+dwOptions], rax
0x18006c500  lea     rdx, unk_1800AD830
0x18006c507  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006c50c  mov     eax, cs:dword_1800BC358
0x18006c512  cmp     eax, 4
0x18006c515  jbe     short loc_18006C53B
0x18006c517  mov     rdx, rsi
0x18006c51a  call    _tlgKeywordOn
0x18006c51f  test    al, al
0x18006c521  jz      short loc_18006C53B
0x18006c523  mov     [rbp+arg_10], ebx
0x18006c526  lea     rax, [rbp+arg_10]
0x18006c52a  mov     qword ptr [rsp+78h+dwOptions], rax
0x18006c52f  lea     rdx, byte_1800AD8AB
0x18006c536  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006c53b  mov     r8b, byte ptr [rbp+arg_0]; unsigned __int8
0x18006c53f  mov     dl, [rbp+arg_8]; unsigned __int8
0x18006c542  call    ?DropBackupRestorePermissions@JobStore@@AEBAJEE@Z; JobStore::DropBackupRestorePermissions(uchar,uchar)
0x18006c547  lea     r8, aOSygSydPaiACiF_0; "O:SYG:SYD:PAI(A;CI;FA;;;BA)(A;OI;FRFWSD"...
0x18006c54e  lea     rdx, asc_1800A3DA8; "\\"
0x18006c555  mov     rcx, rdi; this
0x18006c558  call    ?InitKnownTreeFolder@JobStore@@AEAAJPEBG0@Z; JobStore::InitKnownTreeFolder(ushort const *,ushort const *)
0x18006c55d  mov     ebx, eax
0x18006c55f  test    eax, eax
0x18006c561  js      short loc_18006C59D
0x18006c563  lea     r8, aOSygSydPaiACiF; "O:SYG:SYD:PAI(A;CI;FA;;;BA)(A;OI;0x1f01"...
0x18006c56a  lea     rdx, aMicrosoft; "\\Microsoft"
0x18006c571  mov     rcx, rdi; this
0x18006c574  call    ?InitKnownTreeFolder@JobStore@@AEAAJPEBG0@Z; JobStore::InitKnownTreeFolder(ushort const *,ushort const *)
0x18006c579  mov     ebx, eax
0x18006c57b  test    eax, eax
0x18006c57d  js      short loc_18006C59D
0x18006c57f  lea     r8, aOSygSydAiACiid; "O:SYG:SYD:AI(A;CIID;FA;;;BA)(A;OIIOID;0"...
0x18006c586  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows"
0x18006c58d  mov     rcx, rdi; this
0x18006c590  call    ?InitKnownTreeFolder@JobStore@@AEAAJPEBG0@Z; JobStore::InitKnownTreeFolder(ushort const *,ushort const *)
0x18006c595  mov     ebx, eax
0x18006c597  test    eax, eax
0x18006c599  js      short loc_18006C59D
0x18006c59b  xor     ebx, ebx
0x18006c59d  lea     rcx, [rbp+arg_18]; this
0x18006c5a1  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18006c5a6  mov     eax, ebx
0x18006c5a8  add     rsp, 78h
0x18006c5ac  pop     rdi
0x18006c5ad  pop     rsi
0x18006c5ae  pop     rbx
0x18006c5af  pop     rbp
0x18006c5b0  retn
```
