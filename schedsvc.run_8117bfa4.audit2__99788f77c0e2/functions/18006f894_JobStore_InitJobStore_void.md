# JobStore::InitJobStore(void)

- ea: `0x18006f894`
- end: `0x18006fc2a`
- name: `?InitJobStore@JobStore@@AEAAJXZ`
- size: `918`
- prototype: `__int64 __fastcall(JobStore *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006e8e4`

## callees

- `0x180001544`
- `0x180001658`
- `0x180011e40`
- `0x1800213d8`
- `0x180024730`
- `0x18003bd70`
- `0x180054c80`
- `0x180056954`
- `0x180058de4`
- `0x18005dcd4`
- `0x18006e6b0`
- `0x18006eb64`
- `0x18006ef3c`
- `0x18006f728`
- `0x18006f894`
- `0x18006fc30`
- `0x180072080`
- `0x180073b5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f996`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f996`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006f924`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006f924`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18006fa0a`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18006fa0a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18006fabf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18006fabf`

## string_xrefs

- `0x18006fa79`: `%SystemRoot%\System32\Tasks`
- `0x18006fa96`: `%SystemRoot%\System32\Tasks_Migrated`
- `0x18006f8b3`: `Configuration`

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
                if ( (unsigned int)dword_1800C0358 > 4 && (unsigned __int8)tlgKeywordOn(v13, 0x400000000001LL) )
                {
                  v23 = v14;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                    (_DWORD)v13,
                    (unsigned int)&unk_1800B1878,
                    v15,
                    v16,
                    (__int64)&v23);
                }
              }
              if ( (unsigned int)dword_1800C0358 > 4 && (unsigned __int8)tlgKeywordOn(v13, 0x400000000001LL) )
              {
                v23 = v14;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (_DWORD)v13,
                  (unsigned int)byte_1800B18F3,
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
0x18006f894  mov     [rsp-20h+arg_0], rcx
0x18006f899  push    rbp
0x18006f89a  push    rbx
0x18006f89b  push    rsi
0x18006f89c  push    rdi
0x18006f89d  mov     rbp, rsp
0x18006f8a0  sub     rsp, 78h
0x18006f8a4  mov     rdi, cs:?m_pCommonStore@JobStore@@0PEAV1@EA; JobStore * JobStore::m_pCommonStore
0x18006f8ab  mov     rcx, rdi; this
0x18006f8ae  call    ?InitConfig@JobStore@@AEAAXXZ; JobStore::InitConfig(void)
0x18006f8b3  lea     rdx, aConfiguration; "Configuration"
0x18006f8ba  lea     rcx, [rbp+arg_18]; this
0x18006f8be  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006f8c3  nop
0x18006f8c4  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x18006f8cc  mov     rax, cs:?g_pConfigKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pConfigKeySecurity
0x18006f8d3  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x18006f8d7  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], 0
0x18006f8df  mov     rax, [rbp+arg_18]
0x18006f8e3  test    rax, rax
0x18006f8e6  jz      short loc_18006F8ED
0x18006f8e8  mov     rdx, [rax]
0x18006f8eb  jmp     short loc_18006F8EF
0x18006f8ed  xor     edx, edx; lpSubKey
0x18006f8ef  lea     rax, [rdi+28h]
0x18006f8f3  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18006f8fc  mov     [rsp+78h+phkResult], rax; phkResult
0x18006f901  lea     rax, [rbp+SecurityAttributes]
0x18006f905  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18006f90a  mov     [rsp+78h+samDesired], 20019h; samDesired
0x18006f912  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18006f91a  xor     r9d, r9d; lpClass
0x18006f91d  xor     r8d, r8d; Reserved
0x18006f920  mov     rcx, [rdi+10h]; hKey
0x18006f924  call    cs:__imp_RegCreateKeyExW
0x18006f92b  nop     dword ptr [rax+rax+00h]
0x18006f930  mov     ebx, eax
0x18006f932  test    eax, eax
0x18006f934  jz      short loc_18006F98C
0x18006f936  jle     short loc_18006F941
0x18006f938  movzx   ebx, ax
0x18006f93b  or      ebx, 80070000h
0x18006f941  lea     rax, WPP_GLOBAL_Control
0x18006f948  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f94f  cmp     rcx, rax
0x18006f952  jz      loc_18006FC15
0x18006f958  test    dword ptr [rcx+1Ch], 40000h
0x18006f95f  jz      loc_18006FC15
0x18006f965  cmp     byte ptr [rcx+19h], 2
0x18006f969  jb      loc_18006FC15
0x18006f96f  mov     edx, 0Dh
0x18006f974  mov     r9d, ebx
0x18006f977  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18006f97e  mov     rcx, [rcx+10h]
0x18006f982  call    WPP_SF_d
0x18006f987  jmp     loc_18006FC15
0x18006f98c  xor     r9d, r9d; lpName
0x18006f98f  xor     r8d, r8d; bInitialState
0x18006f992  xor     edx, edx; bManualReset
0x18006f994  xor     ecx, ecx; lpEventAttributes
0x18006f996  call    cs:__imp_CreateEventW
0x18006f99d  nop     dword ptr [rax+rax+00h]
0x18006f9a2  mov     rsi, rax
0x18006f9a5  lea     rcx, [rdi+30h]; this
0x18006f9a9  call    ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
0x18006f9ae  mov     [rdi+30h], rsi
0x18006f9b2  test    rsi, rsi
0x18006f9b5  jnz     short loc_18006F9F1
0x18006f9b7  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006f9bc  mov     ebx, eax
0x18006f9be  lea     rax, WPP_GLOBAL_Control
0x18006f9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f9cc  cmp     rcx, rax
0x18006f9cf  jz      loc_18006FC15
0x18006f9d5  test    dword ptr [rcx+1Ch], 40000h
0x18006f9dc  jz      loc_18006FC15
0x18006f9e2  cmp     byte ptr [rcx+19h], 2
0x18006f9e6  jb      loc_18006FC15
0x18006f9ec  lea     edx, [rsi+0Eh]
0x18006f9ef  jmp     short loc_18006F974
0x18006f9f1  mov     [rsp+78h+dwOptions], 80h
0x18006f9f9  or      r9d, 0FFFFFFFFh
0x18006f9fd  mov     r8, rdi
0x18006fa00  lea     rdx, ?ConfigurationChangeCallback@JobStore@@CAXPEAXE@Z; JobStore::ConfigurationChangeCallback(void *,uchar)
0x18006fa07  mov     rcx, rsi
0x18006fa0a  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18006fa11  nop     dword ptr [rax+rax+00h]
0x18006fa16  mov     [rdi+38h], rax
0x18006fa1a  test    rax, rax
0x18006fa1d  jnz     short loc_18006FA6C
0x18006fa1f  mov     ebx, 80004005h
0x18006fa24  lea     rax, WPP_GLOBAL_Control
0x18006fa2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fa32  cmp     rcx, rax
0x18006fa35  jz      loc_18006FC15
0x18006fa3b  test    dword ptr [rcx+1Ch], 40000h
0x18006fa42  jz      loc_18006FC15
0x18006fa48  cmp     byte ptr [rcx+19h], 2
0x18006fa4c  jb      loc_18006FC15
0x18006fa52  mov     edx, 0Fh
0x18006fa57  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18006fa5e  mov     rcx, [rcx+10h]
0x18006fa62  call    WPP_SF_
0x18006fa67  jmp     loc_18006FC15
0x18006fa6c  xor     edx, edx; unsigned __int8
0x18006fa6e  mov     rcx, rdi; void *
0x18006fa71  call    ?ConfigurationChangeCallback@JobStore@@CAXPEAXE@Z; JobStore::ConfigurationChangeCallback(void *,uchar)
0x18006fa76  mov     rdx, rdi
0x18006fa79  lea     rcx, aSystemrootSyst_3; "%SystemRoot%\\System32\\Tasks"
0x18006fa80  call    ?ExpandEnvironmentString@JobStore@@SAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::ExpandEnvironmentString(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x18006fa85  mov     ebx, eax
0x18006fa87  test    eax, eax
0x18006fa89  js      loc_18006FC15
0x18006fa8f  lea     rsi, [rdi+8]
0x18006fa93  mov     rdx, rsi
0x18006fa96  lea     rcx, aSystemrootSyst_2; "%SystemRoot%\\System32\\Tasks_Migrated"
0x18006fa9d  call    ?ExpandEnvironmentString@JobStore@@SAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::ExpandEnvironmentString(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x18006faa2  mov     ebx, eax
0x18006faa4  test    eax, eax
0x18006faa6  js      loc_18006FC15
0x18006faac  mov     rcx, rdi; this
0x18006faaf  call    ?GetUseXmlStore@JobStore@@QEBAEXZ; JobStore::GetUseXmlStore(void)
0x18006fab4  test    al, al
0x18006fab6  jz      loc_18006FBBF
0x18006fabc  mov     rcx, [rsi]; pszPath
0x18006fabf  call    cs:__imp_PathFileExistsW
0x18006fac6  nop     dword ptr [rax+rax+00h]
0x18006facb  test    eax, eax
0x18006facd  jz      loc_18006FBBF
0x18006fad3  mov     rcx, rdi; this
0x18006fad6  call    ?IsMigrationCleanupCompleted@JobStore@@QEBAHXZ; JobStore::IsMigrationCleanupCompleted(void)
0x18006fadb  test    eax, eax
0x18006fadd  jnz     loc_18006FBBF
0x18006fae3  mov     [rbp+arg_8], al
0x18006fae6  mov     byte ptr [rbp+arg_0], al
0x18006fae9  lea     r8, [rbp+arg_0]; unsigned __int8 *
0x18006faed  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x18006faf1  call    ?TakeBackupRestorePermissions@JobStore@@AEBAJPEAE0@Z; JobStore::TakeBackupRestorePermissions(uchar *,uchar *)
0x18006faf6  mov     ebx, eax
0x18006faf8  test    eax, eax
0x18006fafa  js      loc_18006FC15
0x18006fb00  mov     r8, [rdi]; unsigned __int16 *
0x18006fb03  mov     rdx, [rsi]; unsigned __int16 *
0x18006fb06  mov     rcx, rdi; this
0x18006fb09  call    ?CopyDirectoryWithPermissionsRecursive@JobStore@@QEBAJPEAG0@Z; JobStore::CopyDirectoryWithPermissionsRecursive(ushort *,ushort *)
0x18006fb0e  mov     ebx, eax
0x18006fb10  mov     rsi, 400000000001h
0x18006fb1a  test    eax, eax
0x18006fb1c  jns     short loc_18006FB84
0x18006fb1e  lea     rax, WPP_GLOBAL_Control
0x18006fb25  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fb2c  cmp     rcx, rax
0x18006fb2f  jz      short loc_18006FB55
0x18006fb31  test    dword ptr [rcx+1Ch], 40000h
0x18006fb38  jz      short loc_18006FB55
0x18006fb3a  cmp     byte ptr [rcx+19h], 2
0x18006fb3e  jb      short loc_18006FB55
0x18006fb40  mov     edx, 10h
0x18006fb45  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18006fb4c  mov     rcx, [rcx+10h]
0x18006fb50  call    WPP_SF_
0x18006fb55  mov     eax, cs:dword_1800C0358
0x18006fb5b  cmp     eax, 4
0x18006fb5e  jbe     short loc_18006FB84
0x18006fb60  mov     rdx, rsi
0x18006fb63  call    _tlgKeywordOn
0x18006fb68  test    al, al
0x18006fb6a  jz      short loc_18006FB84
0x18006fb6c  mov     [rbp+arg_10], ebx
0x18006fb6f  lea     rax, [rbp+arg_10]
0x18006fb73  mov     qword ptr [rsp+78h+dwOptions], rax
0x18006fb78  lea     rdx, unk_1800B1878
0x18006fb7f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006fb84  mov     eax, cs:dword_1800C0358
0x18006fb8a  cmp     eax, 4
0x18006fb8d  jbe     short loc_18006FBB3
0x18006fb8f  mov     rdx, rsi
0x18006fb92  call    _tlgKeywordOn
0x18006fb97  test    al, al
0x18006fb99  jz      short loc_18006FBB3
0x18006fb9b  mov     [rbp+arg_10], ebx
0x18006fb9e  lea     rax, [rbp+arg_10]
0x18006fba2  mov     qword ptr [rsp+78h+dwOptions], rax
0x18006fba7  lea     rdx, byte_1800B18F3
0x18006fbae  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006fbb3  mov     r8b, byte ptr [rbp+arg_0]; unsigned __int8
0x18006fbb7  mov     dl, [rbp+arg_8]; unsigned __int8
0x18006fbba  call    ?DropBackupRestorePermissions@JobStore@@AEBAJEE@Z; JobStore::DropBackupRestorePermissions(uchar,uchar)
0x18006fbbf  lea     r8, aOSygSydPaiACiF_0; "O:SYG:SYD:PAI(A;CI;FA;;;BA)(A;OI;FRFWSD"...
0x18006fbc6  lea     rdx, asc_1800A7EC0; "\\"
0x18006fbcd  mov     rcx, rdi; this
0x18006fbd0  call    ?InitKnownTreeFolder@JobStore@@AEAAJPEBG0@Z; JobStore::InitKnownTreeFolder(ushort const *,ushort const *)
0x18006fbd5  mov     ebx, eax
0x18006fbd7  test    eax, eax
0x18006fbd9  js      short loc_18006FC15
0x18006fbdb  lea     r8, aOSygSydPaiACiF; "O:SYG:SYD:PAI(A;CI;FA;;;BA)(A;OI;0x1f01"...
0x18006fbe2  lea     rdx, aMicrosoft; "\\Microsoft"
0x18006fbe9  mov     rcx, rdi; this
0x18006fbec  call    ?InitKnownTreeFolder@JobStore@@AEAAJPEBG0@Z; JobStore::InitKnownTreeFolder(ushort const *,ushort const *)
0x18006fbf1  mov     ebx, eax
0x18006fbf3  test    eax, eax
0x18006fbf5  js      short loc_18006FC15
0x18006fbf7  lea     r8, aOSygSydAiACiid; "O:SYG:SYD:AI(A;CIID;FA;;;BA)(A;OIIOID;0"...
0x18006fbfe  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows"
0x18006fc05  mov     rcx, rdi; this
0x18006fc08  call    ?InitKnownTreeFolder@JobStore@@AEAAJPEBG0@Z; JobStore::InitKnownTreeFolder(ushort const *,ushort const *)
0x18006fc0d  mov     ebx, eax
0x18006fc0f  test    eax, eax
0x18006fc11  js      short loc_18006FC15
0x18006fc13  xor     ebx, ebx
0x18006fc15  lea     rcx, [rbp+arg_18]; this
0x18006fc19  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18006fc1e  mov     eax, ebx
0x18006fc20  add     rsp, 78h
0x18006fc24  pop     rdi
0x18006fc25  pop     rsi
0x18006fc26  pop     rbx
0x18006fc27  pop     rbp
0x18006fc28  retn
```
