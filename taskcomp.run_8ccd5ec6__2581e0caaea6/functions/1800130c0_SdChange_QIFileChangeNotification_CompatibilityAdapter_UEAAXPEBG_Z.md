# ?SdChange@?QIFileChangeNotification@@CompatibilityAdapter@@UEAAXPEBG@Z

- ea: `0x1800130c0`
- end: `0x18001380e`
- name: `?SdChange@?QIFileChangeNotification@@CompatibilityAdapter@@UEAAXPEBG@Z`
- size: `1870`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001ee0`
- `0x180005010`
- `0x180005224`
- `0x180005a38`
- `0x180005c10`
- `0x180006764`
- `0x180006dd8`
- `0x180007988`
- `0x180007994`
- `0x180009ccc`
- `0x18000a0f0`
- `0x18000a384`
- `0x18000a478`
- `0x18000a890`
- `0x18000af88`
- `0x18000c588`
- `0x18000cf80`
- `0x18000d0e8`
- `0x180011894`
- `0x1800130c0`
- `0x180024cd0`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013148`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180013148`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800131a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001323e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013335`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001340e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800134e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001358d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013640`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013757`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800131a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001323e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013335`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001340e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800134e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001358d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013640`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013757`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800132aa`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180013397`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800132aa`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180013397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134a0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001346d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001346d`

## string_xrefs

- `0x18001366a`: `SeRestorePrivilege`
- `0x180013271`: `SeSecurityPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall _SdChange__QIFileChangeNotification__CompatibilityAdapter__UEAAXPEBG_Z(
        __int64 a1,
        unsigned __int16 *a2)
{
  HANDLE *v5; // r12
  int v6; // eax
  unsigned __int16 *v7; // rdx
  int v8; // eax
  DWORD LastError; // eax
  void *v10; // rax
  PSECURITY_DESCRIPTOR v11; // rbx
  DWORD v12; // eax
  __int64 v13; // rcx
  DWORD v14; // eax
  int appended; // eax
  int v16; // eax
  __int64 v17; // rcx
  unsigned __int16 *v18; // rsi
  unsigned int v19; // r9d
  int v20; // eax
  signed int v21; // r13d
  const struct _EVENT_DESCRIPTOR *v22; // rdx
  unsigned __int16 *v23; // rbx
  EventManager *v24; // rcx
  const unsigned __int16 *lpnLengthNeeded; // [rsp+20h] [rbp-6E8h]
  void *v26; // [rsp+28h] [rbp-6E0h]
  const struct _GUID *v27; // [rsp+30h] [rbp-6D8h]
  _BYTE v28[4]; // [rsp+40h] [rbp-6C8h] BYREF
  int v29; // [rsp+44h] [rbp-6C4h]
  __int64 v30; // [rsp+48h] [rbp-6C0h] BYREF
  DWORD nLengthNeeded[2]; // [rsp+50h] [rbp-6B8h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+58h] [rbp-6B0h] BYREF
  ULONG StringSecurityDescriptorLen; // [rsp+60h] [rbp-6A8h] BYREF
  void *DuplicateTokenHandle; // [rsp+68h] [rbp-6A0h] BYREF
  RpcSession *v35; // [rsp+70h] [rbp-698h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+78h] [rbp-690h] BYREF
  void *v37; // [rsp+80h] [rbp-688h] BYREF
  unsigned __int16 *v38; // [rsp+88h] [rbp-680h]
  unsigned __int16 *v39; // [rsp+90h] [rbp-678h]
  HANDLE *v40; // [rsp+98h] [rbp-670h]
  _BYTE v41[528]; // [rsp+A0h] [rbp-668h] BYREF
  WCHAR FileName[264]; // [rsp+2B0h] [rbp-458h] BYREF
  unsigned __int16 v43[264]; // [rsp+4C0h] [rbp-248h] BYREF

  v38 = a2;
  v39 = a2;
  v29 = 0;
  v30 = 0;
  if ( !CompatibilityAdapter::GetAdapter() )
    return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v30);
  TaskLock::TaskLock((TaskLock *)v41, a2);
  v5 = (HANDLE *)(a1 + 16);
  v40 = v5;
  WaitForSingleObject(*v5, 0xFFFFFFFF);
  v6 = SignatureStore::Exists(a2);
  v29 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
        (unsigned int)v6);
    }
LABEL_8:
    ReleaseMutex(*v5);
    TaskLock::~TaskLock((TaskLock *)v41);
    return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v30);
  }
  memset_0(FileName, 0, 0x20Au);
  v8 = tsched::SafePathAppend((tsched *)FileName, v7, (unsigned int)g_TasksFolderInfo, a2, lpnLengthNeeded);
  v29 = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
        (unsigned int)v8);
    }
    goto LABEL_8;
  }
  pSecurityDescriptor = 0;
  ImpersonateSelfWithPrivilege::ImpersonateSelfWithPrivilege(&DuplicateTokenHandle, L"SeSecurityPrivilege");
  nLengthNeeded[0] = 0;
  if ( !GetFileSecurityW(FileName, 0xFu, 0, 0, nLengthNeeded) && GetLastError() != 122 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, LastError);
    }
    ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege((ImpersonateSelfWithPrivilege *)&DuplicateTokenHandle);
    operator delete(0);
    ReleaseMutex(*v5);
    TaskLock::~TaskLock((TaskLock *)v41);
    return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v30);
  }
  v10 = operator new[](nLengthNeeded[0]);
  wmi::AutoVectorPtr<unsigned char>::operator=(&pSecurityDescriptor, v10);
  v11 = pSecurityDescriptor;
  if ( !GetFileSecurityW(FileName, 0xFu, pSecurityDescriptor, nLengthNeeded[0], nLengthNeeded) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, v12);
    }
    ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege((ImpersonateSelfWithPrivilege *)&DuplicateTokenHandle);
    operator delete(v11);
    ReleaseMutex(*v5);
    TaskLock::~TaskLock((TaskLock *)v41);
    return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v30);
  }
  ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege((ImpersonateSelfWithPrivilege *)&DuplicateTokenHandle);
  StringSecurityDescriptor = 0;
  StringSecurityDescriptorLen = 0;
  if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(
          v11,
          1u,
          0xFu,
          &StringSecurityDescriptor,
          &StringSecurityDescriptorLen) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, v14);
    }
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&StringSecurityDescriptor);
    operator delete(v11);
    ReleaseMutex(*v5);
    TaskLock::~TaskLock((TaskLock *)v41);
    return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v30);
  }
  *(_QWORD *)nLengthNeeded = 0;
  appended = CompatibilityAdapter::Append_A_FX_SY(v13, StringSecurityDescriptor, nLengthNeeded);
  v29 = appended;
  if ( appended < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
        (unsigned int)appended);
    }
LABEL_39:
    operator delete(*(void **)nLengthNeeded);
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&StringSecurityDescriptor);
    operator delete(v11);
    ReleaseMutex(*v5);
    TaskLock::~TaskLock((TaskLock *)v41);
    return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v30);
  }
  memset_0(v43, 0, 0x20Au);
  v16 = FilenameToUri(a2, v43);
  v29 = v16;
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
        (unsigned int)v16);
    }
    goto LABEL_39;
  }
  ImpersonateSelfWithPrivilege::ImpersonateSelfWithPrivilege(&v37, L"SeRestorePrivilege");
  CompatibilityAdapter::GetSession(v17, &v35);
  v18 = *(unsigned __int16 **)nLengthNeeded;
  SdSettingGuard::SdSettingGuard((SdSettingGuard *)v28, v43, *(const unsigned __int16 **)nLengthNeeded);
  v20 = RpcSession::SetSecurity(v35, v43, v18, v19);
  v21 = v20;
  v29 = v20;
  if ( v20 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
      (unsigned int)v20);
  }
  SdSettingGuard::~SdSettingGuard((SdSettingGuard *)v28);
  if ( v35 )
    wmi::RefBase::Release(v35);
  v35 = 0;
  ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege((ImpersonateSelfWithPrivilege *)&v37);
  operator delete(v18);
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&StringSecurityDescriptor);
  operator delete(v11);
  ReleaseMutex(*v5);
  TaskLock::~TaskLock((TaskLock *)v41);
  v23 = v38;
  if ( v21 < 0 )
  {
    v24 = (EventManager *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids,
        (unsigned int)v21);
    }
    EventManager::EvtReport(v24, v22, 0, v23, v21, v26, v27);
  }
  return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v30);
}

```

## disassembly

```asm
0x1800130c0  mov     [rsp+arg_10], rbx
0x1800130c5  push    rsi
0x1800130c6  push    rdi
0x1800130c7  push    r12
0x1800130c9  push    r13
0x1800130cb  push    r14
0x1800130cd  sub     rsp, 6E0h
0x1800130d4  mov     rax, cs:__security_cookie
0x1800130db  xor     rax, rsp
0x1800130de  mov     [rsp+708h+var_38], rax
0x1800130e6  mov     rsi, rdx
0x1800130e9  mov     [rsp+708h+var_680], rdx
0x1800130f1  mov     r12, rcx
0x1800130f4  mov     [rsp+708h+var_678], rdx
0x1800130fc  mov     [rsp+708h+var_6C4], 0
0x180013104  xor     edi, edi
0x180013106  mov     [rsp+708h+var_6C0], rdi
0x18001310b  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x180013110  test    rax, rax
0x180013113  jnz     short loc_180013124
0x180013115  lea     rcx, [rsp+708h+var_6C0]
0x18001311a  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001311f  jmp     loc_1800137E5
0x180013124  mov     rdx, rsi; unsigned __int16 *
0x180013127  lea     rcx, [rsp+708h+var_668]; this
0x18001312f  call    ??0TaskLock@@QEAA@PEBG@Z; TaskLock::TaskLock(ushort const *)
0x180013134  nop
0x180013135  add     r12, 10h
0x180013139  mov     [rsp+708h+var_670], r12
0x180013141  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013144  mov     rcx, [r12]; hHandle
0x180013148  call    cs:__imp_WaitForSingleObject
0x18001314f  nop     dword ptr [rax+rax+00h]
0x180013154  nop
0x180013155  mov     rcx, rsi; unsigned __int16 *
0x180013158  call    ?Exists@SignatureStore@@SAJPEBG@Z; SignatureStore::Exists(ushort const *)
0x18001315d  mov     [rsp+708h+var_6C4], eax
0x180013161  test    eax, eax
0x180013163  jns     short loc_1800131CB
0x180013165  lea     r14, WPP_GLOBAL_Control
0x18001316c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013173  cmp     rcx, r14
0x180013176  jz      short loc_18001319D
0x180013178  test    byte ptr [rcx+1Ch], 2
0x18001317c  jz      short loc_18001319D
0x18001317e  cmp     byte ptr [rcx+19h], 2
0x180013182  jb      short loc_18001319D
0x180013184  mov     edx, 11h
0x180013189  mov     r9d, eax
0x18001318c  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180013193  mov     rcx, [rcx+10h]
0x180013197  call    WPP_SF_d
0x18001319c  nop
0x18001319d  mov     rcx, [r12]; hMutex
0x1800131a1  call    cs:__imp_ReleaseMutex
0x1800131a8  nop     dword ptr [rax+rax+00h]
0x1800131ad  nop
0x1800131ae  lea     rcx, [rsp+708h+var_668]; this
0x1800131b6  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x1800131bb  nop
0x1800131bc  lea     rcx, [rsp+708h+var_6C0]
0x1800131c1  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800131c6  jmp     loc_1800137E5
0x1800131cb  mov     r13d, 20Ah
0x1800131d1  mov     r8d, r13d; Size
0x1800131d4  xor     edx, edx; Val
0x1800131d6  lea     rcx, [rsp+708h+FileName]; void *
0x1800131de  call    memset_0
0x1800131e3  mov     r9, rsi; unsigned __int16 *
0x1800131e6  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned int
0x1800131ed  lea     rcx, [rsp+708h+FileName]; this
0x1800131f5  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x1800131fa  mov     [rsp+708h+var_6C4], eax
0x1800131fe  test    eax, eax
0x180013200  jns     short loc_180013268
0x180013202  lea     r14, WPP_GLOBAL_Control
0x180013209  mov     rcx, cs:WPP_GLOBAL_Control
0x180013210  cmp     rcx, r14
0x180013213  jz      short loc_18001323A
0x180013215  test    byte ptr [rcx+1Ch], 2
0x180013219  jz      short loc_18001323A
0x18001321b  cmp     byte ptr [rcx+19h], 2
0x18001321f  jb      short loc_18001323A
0x180013221  mov     edx, 12h
0x180013226  mov     r9d, eax
0x180013229  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180013230  mov     rcx, [rcx+10h]
0x180013234  call    WPP_SF_d
0x180013239  nop
0x18001323a  mov     rcx, [r12]; hMutex
0x18001323e  call    cs:__imp_ReleaseMutex
0x180013245  nop     dword ptr [rax+rax+00h]
0x18001324a  nop
0x18001324b  lea     rcx, [rsp+708h+var_668]; this
0x180013253  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180013258  nop
0x180013259  lea     rcx, [rsp+708h+var_6C0]
0x18001325e  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180013263  jmp     loc_1800137E5
0x180013268  mov     [rsp+708h+pSecurityDescriptor], 0
0x180013271  lea     rdx, aSesecuritypriv; "SeSecurityPrivilege"
0x180013278  lea     rcx, [rsp+708h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18001327d  call    ??0ImpersonateSelfWithPrivilege@@QEAA@PEBG@Z; ImpersonateSelfWithPrivilege::ImpersonateSelfWithPrivilege(ushort const *)
0x180013282  nop
0x180013283  mov     [rsp+708h+nLengthNeeded], 0
0x18001328b  lea     rax, [rsp+708h+nLengthNeeded]
0x180013290  mov     [rsp+708h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180013295  xor     r9d, r9d; nLength
0x180013298  xor     r8d, r8d; pSecurityDescriptor
0x18001329b  lea     r14d, [r9+0Fh]
0x18001329f  mov     edx, r14d; RequestedInformation
0x1800132a2  lea     rcx, [rsp+708h+FileName]; lpFileName
0x1800132aa  call    cs:__imp_GetFileSecurityW
0x1800132b1  nop     dword ptr [rax+rax+00h]
0x1800132b6  test    eax, eax
0x1800132b8  jnz     loc_18001335F
0x1800132be  call    cs:__imp_GetLastError
0x1800132c5  nop     dword ptr [rax+rax+00h]
0x1800132ca  cmp     eax, 7Ah ; 'z'
0x1800132cd  jz      loc_18001335F
0x1800132d3  lea     r14, WPP_GLOBAL_Control
0x1800132da  mov     rax, cs:WPP_GLOBAL_Control
0x1800132e1  cmp     rax, r14
0x1800132e4  jz      short loc_18001331E
0x1800132e6  test    byte ptr [rax+1Ch], 2
0x1800132ea  jz      short loc_18001331E
0x1800132ec  cmp     byte ptr [rax+19h], 2
0x1800132f0  jb      short loc_18001331E
0x1800132f2  call    cs:__imp_GetLastError
0x1800132f9  nop     dword ptr [rax+rax+00h]
0x1800132fe  mov     edx, 13h
0x180013303  mov     r9d, eax
0x180013306  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x18001330d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013314  mov     rcx, [rcx+10h]
0x180013318  call    WPP_SF_d
0x18001331d  nop
0x18001331e  lea     rcx, [rsp+708h+DuplicateTokenHandle]; this
0x180013323  call    ??1ImpersonateSelfWithPrivilege@@QEAA@XZ; ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege(void)
0x180013328  nop
0x180013329  xor     ecx, ecx; Block
0x18001332b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013330  nop
0x180013331  mov     rcx, [r12]; hMutex
0x180013335  call    cs:__imp_ReleaseMutex
0x18001333c  nop     dword ptr [rax+rax+00h]
0x180013341  nop
0x180013342  lea     rcx, [rsp+708h+var_668]; this
0x18001334a  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x18001334f  nop
0x180013350  lea     rcx, [rsp+708h+var_6C0]
0x180013355  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001335a  jmp     loc_1800137E5
0x18001335f  mov     ecx, [rsp+708h+nLengthNeeded]; unsigned __int64
0x180013363  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180013368  mov     rdx, rax
0x18001336b  lea     rcx, [rsp+708h+pSecurityDescriptor]
0x180013370  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x180013375  lea     rax, [rsp+708h+nLengthNeeded]
0x18001337a  mov     [rsp+708h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001337f  mov     r9d, [rsp+708h+nLengthNeeded]; nLength
0x180013384  mov     rbx, [rsp+708h+pSecurityDescriptor]
0x180013389  mov     r8, rbx; pSecurityDescriptor
0x18001338c  mov     edx, r14d; RequestedInformation
0x18001338f  lea     rcx, [rsp+708h+FileName]; lpFileName
0x180013397  call    cs:__imp_GetFileSecurityW
0x18001339e  nop     dword ptr [rax+rax+00h]
0x1800133a3  test    eax, eax
0x1800133a5  jnz     loc_180013438
0x1800133ab  lea     r14, WPP_GLOBAL_Control
0x1800133b2  mov     rax, cs:WPP_GLOBAL_Control
0x1800133b9  cmp     rax, r14
0x1800133bc  jz      short loc_1800133F6
0x1800133be  test    byte ptr [rax+1Ch], 2
0x1800133c2  jz      short loc_1800133F6
0x1800133c4  cmp     byte ptr [rax+19h], 2
0x1800133c8  jb      short loc_1800133F6
0x1800133ca  call    cs:__imp_GetLastError
0x1800133d1  nop     dword ptr [rax+rax+00h]
0x1800133d6  mov     edx, 14h
0x1800133db  mov     r9d, eax
0x1800133de  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x1800133e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133ec  mov     rcx, [rcx+10h]
0x1800133f0  call    WPP_SF_d
0x1800133f5  nop
0x1800133f6  lea     rcx, [rsp+708h+DuplicateTokenHandle]; this
0x1800133fb  call    ??1ImpersonateSelfWithPrivilege@@QEAA@XZ; ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege(void)
0x180013400  nop
0x180013401  mov     rcx, rbx; Block
0x180013404  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013409  nop
0x18001340a  mov     rcx, [r12]; hMutex
0x18001340e  call    cs:__imp_ReleaseMutex
0x180013415  nop     dword ptr [rax+rax+00h]
0x18001341a  nop
0x18001341b  lea     rcx, [rsp+708h+var_668]; this
0x180013423  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180013428  nop
0x180013429  lea     rcx, [rsp+708h+var_6C0]
0x18001342e  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180013433  jmp     loc_1800137E5
0x180013438  lea     rcx, [rsp+708h+DuplicateTokenHandle]; this
0x18001343d  call    ??1ImpersonateSelfWithPrivilege@@QEAA@XZ; ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege(void)
0x180013442  mov     [rsp+708h+StringSecurityDescriptor], 0
0x18001344b  mov     [rsp+708h+StringSecurityDescriptorLen], 0
0x180013453  lea     rax, [rsp+708h+StringSecurityDescriptorLen]
0x180013458  mov     [rsp+708h+lpnLengthNeeded], rax; StringSecurityDescriptorLen
0x18001345d  lea     r9, [rsp+708h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180013462  mov     r8d, r14d; SecurityInformation
0x180013465  mov     edx, 1; RequestedStringSDRevision
0x18001346a  mov     rcx, rbx; SecurityDescriptor
0x18001346d  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180013474  nop     dword ptr [rax+rax+00h]
0x180013479  test    eax, eax
0x18001347b  jnz     loc_18001350E
0x180013481  lea     r14, WPP_GLOBAL_Control
0x180013488  mov     rax, cs:WPP_GLOBAL_Control
0x18001348f  cmp     rax, r14
0x180013492  jz      short loc_1800134CC
0x180013494  test    byte ptr [rax+1Ch], 2
0x180013498  jz      short loc_1800134CC
0x18001349a  cmp     byte ptr [rax+19h], 2
0x18001349e  jb      short loc_1800134CC
0x1800134a0  call    cs:__imp_GetLastError
0x1800134a7  nop     dword ptr [rax+rax+00h]
0x1800134ac  mov     edx, 15h
0x1800134b1  mov     r9d, eax
0x1800134b4  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x1800134bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134c2  mov     rcx, [rcx+10h]
0x1800134c6  call    WPP_SF_d
0x1800134cb  nop
0x1800134cc  lea     rcx, [rsp+708h+StringSecurityDescriptor]
0x1800134d1  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800134d6  nop
0x1800134d7  mov     rcx, rbx; Block
0x1800134da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800134df  nop
0x1800134e0  mov     rcx, [r12]; hMutex
0x1800134e4  call    cs:__imp_ReleaseMutex
0x1800134eb  nop     dword ptr [rax+rax+00h]
0x1800134f0  nop
0x1800134f1  lea     rcx, [rsp+708h+var_668]; this
0x1800134f9  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x1800134fe  nop
0x1800134ff  lea     rcx, [rsp+708h+var_6C0]
0x180013504  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180013509  jmp     loc_1800137E5
0x18001350e  mov     qword ptr [rsp+708h+nLengthNeeded], 0
0x180013517  lea     r8, [rsp+708h+nLengthNeeded]
0x18001351c  mov     rdx, [rsp+708h+StringSecurityDescriptor]
0x180013521  call    ?Append_A_FX_SY@CompatibilityAdapter@@AEAAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; CompatibilityAdapter::Append_A_FX_SY(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x180013526  mov     [rsp+708h+var_6C4], eax
0x18001352a  test    eax, eax
0x18001352c  jns     loc_1800135B7
0x180013532  lea     r14, WPP_GLOBAL_Control
0x180013539  mov     rcx, cs:WPP_GLOBAL_Control
0x180013540  cmp     rcx, r14
0x180013543  jz      short loc_18001356A
0x180013545  test    byte ptr [rcx+1Ch], 2
0x180013549  jz      short loc_18001356A
0x18001354b  cmp     byte ptr [rcx+19h], 2
0x18001354f  jb      short loc_18001356A
0x180013551  mov     edx, 16h
0x180013556  mov     r9d, eax
0x180013559  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180013560  mov     rcx, [rcx+10h]
0x180013564  call    WPP_SF_d
0x180013569  nop
0x18001356a  mov     rcx, qword ptr [rsp+708h+nLengthNeeded]; Block
0x18001356f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013574  nop
0x180013575  lea     rcx, [rsp+708h+StringSecurityDescriptor]
0x18001357a  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001357f  nop
0x180013580  mov     rcx, rbx; Block
0x180013583  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013588  nop
0x180013589  mov     rcx, [r12]; hMutex
0x18001358d  call    cs:__imp_ReleaseMutex
0x180013594  nop     dword ptr [rax+rax+00h]
0x180013599  nop
0x18001359a  lea     rcx, [rsp+708h+var_668]; this
0x1800135a2  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x1800135a7  nop
0x1800135a8  lea     rcx, [rsp+708h+var_6C0]
0x1800135ad  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800135b2  jmp     loc_1800137E5
0x1800135b7  mov     r8, r13; Size
0x1800135ba  xor     edx, edx; Val
0x1800135bc  lea     rcx, [rsp+708h+var_248]; void *
0x1800135c4  call    memset_0
0x1800135c9  lea     rdx, [rsp+708h+var_248]; unsigned __int16 *
0x1800135d1  mov     rcx, rsi; unsigned __int16 *
0x1800135d4  call    ?FilenameToUri@@YAJPEBGPEAG@Z; FilenameToUri(ushort const *,ushort *)
0x1800135d9  mov     [rsp+708h+var_6C4], eax
0x1800135dd  test    eax, eax
0x1800135df  jns     loc_18001366A
0x1800135e5  lea     r14, WPP_GLOBAL_Control
  ... truncated ...
```
