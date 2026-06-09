# ?SdChange@?QIFileChangeNotification@@CompatibilityAdapter@@UEAAXPEBG@Z

- ea: `0x180012560`
- end: `0x180012c45`
- name: `?SdChange@?QIFileChangeNotification@@CompatibilityAdapter@@UEAAXPEBG@Z`
- size: `1765`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001e40`
- `0x180004da4`
- `0x180004f88`
- `0x180005750`
- `0x1800058f0`
- `0x18000635c`
- `0x1800069a8`
- `0x1800074c8`
- `0x1800074d4`
- `0x1800097dc`
- `0x180009ba0`
- `0x180009e0c`
- `0x180009edc`
- `0x18000a2c0`
- `0x18000a994`
- `0x18000bd7c`
- `0x18000c760`
- `0x18000c8b4`
- `0x180010e44`
- `0x180012560`
- `0x180023674`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800125e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800125e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001263b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800126d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800127b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012878`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001293c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800129db`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012a84`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012b95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001263b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800126d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800127b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012878`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001293c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800129db`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012a84`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012b95`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180012738`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001280d`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180012738`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001280d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001283a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001283a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800128fe`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800128d1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800128d1`

## string_xrefs

- `0x180012aa8`: `SeRestorePrivilege`
- `0x1800126ff`: `SeSecurityPrivilege`

## pseudocode

```c
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
  void *v25; // [rsp+28h] [rbp-6E0h]
  const struct _GUID *v26; // [rsp+30h] [rbp-6D8h]
  _BYTE v27[4]; // [rsp+40h] [rbp-6C8h] BYREF
  int v28; // [rsp+44h] [rbp-6C4h]
  __int64 v29; // [rsp+48h] [rbp-6C0h] BYREF
  DWORD nLengthNeeded[2]; // [rsp+50h] [rbp-6B8h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+58h] [rbp-6B0h] BYREF
  ULONG StringSecurityDescriptorLen; // [rsp+60h] [rbp-6A8h] BYREF
  void *DuplicateTokenHandle; // [rsp+68h] [rbp-6A0h] BYREF
  RpcSession *v34; // [rsp+70h] [rbp-698h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+78h] [rbp-690h] BYREF
  void *v36; // [rsp+80h] [rbp-688h] BYREF
  unsigned __int16 *v37; // [rsp+88h] [rbp-680h]
  unsigned __int16 *v38; // [rsp+90h] [rbp-678h]
  HANDLE *v39; // [rsp+98h] [rbp-670h]
  _BYTE v40[528]; // [rsp+A0h] [rbp-668h] BYREF
  WCHAR FileName[264]; // [rsp+2B0h] [rbp-458h] BYREF
  unsigned __int16 v42[264]; // [rsp+4C0h] [rbp-248h] BYREF

  v37 = a2;
  v38 = a2;
  v28 = 0;
  v29 = 0;
  if ( !CompatibilityAdapter::GetAdapter() )
    return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v29);
  TaskLock::TaskLock((TaskLock *)v40, a2);
  v5 = (HANDLE *)(a1 + 16);
  v39 = v5;
  WaitForSingleObject(*v5, 0xFFFFFFFF);
  v6 = SignatureStore::Exists(a2);
  v28 = v6;
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
    TaskLock::~TaskLock((TaskLock *)v40);
    return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v29);
  }
  memset_0(FileName, 0, 0x20Au);
  v8 = tsched::SafePathAppend((tsched *)FileName, v7, (tsched *)g_TasksFolderInfo, (tsched *)a2);
  v28 = v8;
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
    TaskLock::~TaskLock((TaskLock *)v40);
    return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v29);
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
    TaskLock::~TaskLock((TaskLock *)v40);
    return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v29);
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
    TaskLock::~TaskLock((TaskLock *)v40);
    return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v29);
  }
  *(_QWORD *)nLengthNeeded = 0;
  appended = CompatibilityAdapter::Append_A_FX_SY(v13, StringSecurityDescriptor, nLengthNeeded);
  v28 = appended;
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
    TaskLock::~TaskLock((TaskLock *)v40);
    return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v29);
  }
  memset_0(v42, 0, 0x20Au);
  v16 = FilenameToUri(a2, v42);
  v28 = v16;
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
  ImpersonateSelfWithPrivilege::ImpersonateSelfWithPrivilege(&v36, L"SeRestorePrivilege");
  CompatibilityAdapter::GetSession(v17, &v34);
  v18 = *(unsigned __int16 **)nLengthNeeded;
  SdSettingGuard::SdSettingGuard((SdSettingGuard *)v27, v42, *(const unsigned __int16 **)nLengthNeeded);
  v20 = RpcSession::SetSecurity(v34, v42, v18, v19);
  v21 = v20;
  v28 = v20;
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
  SdSettingGuard::~SdSettingGuard((SdSettingGuard *)v27);
  if ( v34 )
    wmi::RefBase::Release(v34);
  v34 = 0;
  ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege((ImpersonateSelfWithPrivilege *)&v36);
  operator delete(v18);
  tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&StringSecurityDescriptor);
  operator delete(v11);
  ReleaseMutex(*v5);
  TaskLock::~TaskLock((TaskLock *)v40);
  v23 = v37;
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
    EventManager::EvtReport(v24, v22, 0, v23, v21, v25, v26);
  }
  return tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&v29);
}

```

## disassembly

```asm
0x180012560  mov     [rsp+arg_10], rbx
0x180012565  push    rsi
0x180012566  push    rdi
0x180012567  push    r12
0x180012569  push    r13
0x18001256b  push    r14
0x18001256d  sub     rsp, 6E0h
0x180012574  mov     rax, cs:__security_cookie
0x18001257b  xor     rax, rsp
0x18001257e  mov     [rsp+708h+var_38], rax
0x180012586  mov     rsi, rdx
0x180012589  mov     [rsp+708h+var_680], rdx
0x180012591  mov     r12, rcx
0x180012594  mov     [rsp+708h+var_678], rdx
0x18001259c  mov     [rsp+708h+var_6C4], 0
0x1800125a4  xor     edi, edi
0x1800125a6  mov     [rsp+708h+var_6C0], rdi
0x1800125ab  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x1800125b0  test    rax, rax
0x1800125b3  jnz     short loc_1800125C4
0x1800125b5  lea     rcx, [rsp+708h+var_6C0]
0x1800125ba  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800125bf  jmp     loc_180012C1D
0x1800125c4  mov     rdx, rsi; unsigned __int16 *
0x1800125c7  lea     rcx, [rsp+708h+var_668]; this
0x1800125cf  call    ??0TaskLock@@QEAA@PEBG@Z; TaskLock::TaskLock(ushort const *)
0x1800125d4  nop
0x1800125d5  add     r12, 10h
0x1800125d9  mov     [rsp+708h+var_670], r12
0x1800125e1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800125e4  mov     rcx, [r12]; hHandle
0x1800125e8  call    cs:__imp_WaitForSingleObject
0x1800125ee  nop
0x1800125ef  mov     rcx, rsi; unsigned __int16 *
0x1800125f2  call    ?Exists@SignatureStore@@SAJPEBG@Z; SignatureStore::Exists(ushort const *)
0x1800125f7  mov     [rsp+708h+var_6C4], eax
0x1800125fb  test    eax, eax
0x1800125fd  jns     short loc_18001265F
0x1800125ff  lea     r14, WPP_GLOBAL_Control
0x180012606  mov     rcx, cs:WPP_GLOBAL_Control
0x18001260d  cmp     rcx, r14
0x180012610  jz      short loc_180012637
0x180012612  test    byte ptr [rcx+1Ch], 2
0x180012616  jz      short loc_180012637
0x180012618  cmp     byte ptr [rcx+19h], 2
0x18001261c  jb      short loc_180012637
0x18001261e  mov     edx, 11h
0x180012623  mov     r9d, eax
0x180012626  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x18001262d  mov     rcx, [rcx+10h]
0x180012631  call    WPP_SF_d
0x180012636  nop
0x180012637  mov     rcx, [r12]; hMutex
0x18001263b  call    cs:__imp_ReleaseMutex
0x180012641  nop
0x180012642  lea     rcx, [rsp+708h+var_668]; this
0x18001264a  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x18001264f  nop
0x180012650  lea     rcx, [rsp+708h+var_6C0]
0x180012655  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001265a  jmp     loc_180012C1D
0x18001265f  mov     r13d, 20Ah
0x180012665  mov     r8d, r13d; Size
0x180012668  xor     edx, edx; Val
0x18001266a  lea     rcx, [rsp+708h+FileName]; void *
0x180012672  call    memset_0
0x180012677  mov     r9, rsi; unsigned __int16 *
0x18001267a  mov     r8, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned int
0x180012681  lea     rcx, [rsp+708h+FileName]; this
0x180012689  call    ?SafePathAppend@tsched@@YAJPEAGKPEBG1@Z; tsched::SafePathAppend(ushort *,ulong,ushort const *,ushort const *)
0x18001268e  mov     [rsp+708h+var_6C4], eax
0x180012692  test    eax, eax
0x180012694  jns     short loc_1800126F6
0x180012696  lea     r14, WPP_GLOBAL_Control
0x18001269d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126a4  cmp     rcx, r14
0x1800126a7  jz      short loc_1800126CE
0x1800126a9  test    byte ptr [rcx+1Ch], 2
0x1800126ad  jz      short loc_1800126CE
0x1800126af  cmp     byte ptr [rcx+19h], 2
0x1800126b3  jb      short loc_1800126CE
0x1800126b5  mov     edx, 12h
0x1800126ba  mov     r9d, eax
0x1800126bd  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x1800126c4  mov     rcx, [rcx+10h]
0x1800126c8  call    WPP_SF_d
0x1800126cd  nop
0x1800126ce  mov     rcx, [r12]; hMutex
0x1800126d2  call    cs:__imp_ReleaseMutex
0x1800126d8  nop
0x1800126d9  lea     rcx, [rsp+708h+var_668]; this
0x1800126e1  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x1800126e6  nop
0x1800126e7  lea     rcx, [rsp+708h+var_6C0]
0x1800126ec  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800126f1  jmp     loc_180012C1D
0x1800126f6  mov     [rsp+708h+pSecurityDescriptor], 0
0x1800126ff  lea     rdx, aSesecuritypriv; "SeSecurityPrivilege"
0x180012706  lea     rcx, [rsp+708h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18001270b  call    ??0ImpersonateSelfWithPrivilege@@QEAA@PEBG@Z; ImpersonateSelfWithPrivilege::ImpersonateSelfWithPrivilege(ushort const *)
0x180012710  nop
0x180012711  mov     [rsp+708h+nLengthNeeded], 0
0x180012719  lea     rax, [rsp+708h+nLengthNeeded]
0x18001271e  mov     [rsp+708h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180012723  xor     r9d, r9d; nLength
0x180012726  xor     r8d, r8d; pSecurityDescriptor
0x180012729  lea     r14d, [r9+0Fh]
0x18001272d  mov     edx, r14d; RequestedInformation
0x180012730  lea     rcx, [rsp+708h+FileName]; lpFileName
0x180012738  call    cs:__imp_GetFileSecurityW
0x18001273e  test    eax, eax
0x180012740  jnz     loc_1800127D5
0x180012746  call    cs:__imp_GetLastError
0x18001274c  cmp     eax, 7Ah ; 'z'
0x18001274f  jz      loc_1800127D5
0x180012755  lea     r14, WPP_GLOBAL_Control
0x18001275c  mov     rax, cs:WPP_GLOBAL_Control
0x180012763  cmp     rax, r14
0x180012766  jz      short loc_18001279A
0x180012768  test    byte ptr [rax+1Ch], 2
0x18001276c  jz      short loc_18001279A
0x18001276e  cmp     byte ptr [rax+19h], 2
0x180012772  jb      short loc_18001279A
0x180012774  call    cs:__imp_GetLastError
0x18001277a  mov     edx, 13h
0x18001277f  mov     r9d, eax
0x180012782  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180012789  mov     rcx, cs:WPP_GLOBAL_Control
0x180012790  mov     rcx, [rcx+10h]
0x180012794  call    WPP_SF_d
0x180012799  nop
0x18001279a  lea     rcx, [rsp+708h+DuplicateTokenHandle]; this
0x18001279f  call    ??1ImpersonateSelfWithPrivilege@@QEAA@XZ; ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege(void)
0x1800127a4  nop
0x1800127a5  xor     ecx, ecx; Block
0x1800127a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800127ac  nop
0x1800127ad  mov     rcx, [r12]; hMutex
0x1800127b1  call    cs:__imp_ReleaseMutex
0x1800127b7  nop
0x1800127b8  lea     rcx, [rsp+708h+var_668]; this
0x1800127c0  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x1800127c5  nop
0x1800127c6  lea     rcx, [rsp+708h+var_6C0]
0x1800127cb  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800127d0  jmp     loc_180012C1D
0x1800127d5  mov     ecx, [rsp+708h+nLengthNeeded]; unsigned __int64
0x1800127d9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800127de  mov     rdx, rax
0x1800127e1  lea     rcx, [rsp+708h+pSecurityDescriptor]
0x1800127e6  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x1800127eb  lea     rax, [rsp+708h+nLengthNeeded]
0x1800127f0  mov     [rsp+708h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800127f5  mov     r9d, [rsp+708h+nLengthNeeded]; nLength
0x1800127fa  mov     rbx, [rsp+708h+pSecurityDescriptor]
0x1800127ff  mov     r8, rbx; pSecurityDescriptor
0x180012802  mov     edx, r14d; RequestedInformation
0x180012805  lea     rcx, [rsp+708h+FileName]; lpFileName
0x18001280d  call    cs:__imp_GetFileSecurityW
0x180012813  test    eax, eax
0x180012815  jnz     loc_18001289C
0x18001281b  lea     r14, WPP_GLOBAL_Control
0x180012822  mov     rax, cs:WPP_GLOBAL_Control
0x180012829  cmp     rax, r14
0x18001282c  jz      short loc_180012860
0x18001282e  test    byte ptr [rax+1Ch], 2
0x180012832  jz      short loc_180012860
0x180012834  cmp     byte ptr [rax+19h], 2
0x180012838  jb      short loc_180012860
0x18001283a  call    cs:__imp_GetLastError
0x180012840  mov     edx, 14h
0x180012845  mov     r9d, eax
0x180012848  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x18001284f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012856  mov     rcx, [rcx+10h]
0x18001285a  call    WPP_SF_d
0x18001285f  nop
0x180012860  lea     rcx, [rsp+708h+DuplicateTokenHandle]; this
0x180012865  call    ??1ImpersonateSelfWithPrivilege@@QEAA@XZ; ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege(void)
0x18001286a  nop
0x18001286b  mov     rcx, rbx; Block
0x18001286e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012873  nop
0x180012874  mov     rcx, [r12]; hMutex
0x180012878  call    cs:__imp_ReleaseMutex
0x18001287e  nop
0x18001287f  lea     rcx, [rsp+708h+var_668]; this
0x180012887  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x18001288c  nop
0x18001288d  lea     rcx, [rsp+708h+var_6C0]
0x180012892  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x180012897  jmp     loc_180012C1D
0x18001289c  lea     rcx, [rsp+708h+DuplicateTokenHandle]; this
0x1800128a1  call    ??1ImpersonateSelfWithPrivilege@@QEAA@XZ; ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege(void)
0x1800128a6  mov     [rsp+708h+StringSecurityDescriptor], 0
0x1800128af  mov     [rsp+708h+StringSecurityDescriptorLen], 0
0x1800128b7  lea     rax, [rsp+708h+StringSecurityDescriptorLen]
0x1800128bc  mov     [rsp+708h+lpnLengthNeeded], rax; StringSecurityDescriptorLen
0x1800128c1  lea     r9, [rsp+708h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800128c6  mov     r8d, r14d; SecurityInformation
0x1800128c9  mov     edx, 1; RequestedStringSDRevision
0x1800128ce  mov     rcx, rbx; SecurityDescriptor
0x1800128d1  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800128d7  test    eax, eax
0x1800128d9  jnz     loc_180012960
0x1800128df  lea     r14, WPP_GLOBAL_Control
0x1800128e6  mov     rax, cs:WPP_GLOBAL_Control
0x1800128ed  cmp     rax, r14
0x1800128f0  jz      short loc_180012924
0x1800128f2  test    byte ptr [rax+1Ch], 2
0x1800128f6  jz      short loc_180012924
0x1800128f8  cmp     byte ptr [rax+19h], 2
0x1800128fc  jb      short loc_180012924
0x1800128fe  call    cs:__imp_GetLastError
0x180012904  mov     edx, 15h
0x180012909  mov     r9d, eax
0x18001290c  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180012913  mov     rcx, cs:WPP_GLOBAL_Control
0x18001291a  mov     rcx, [rcx+10h]
0x18001291e  call    WPP_SF_d
0x180012923  nop
0x180012924  lea     rcx, [rsp+708h+StringSecurityDescriptor]
0x180012929  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001292e  nop
0x18001292f  mov     rcx, rbx; Block
0x180012932  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012937  nop
0x180012938  mov     rcx, [r12]; hMutex
0x18001293c  call    cs:__imp_ReleaseMutex
0x180012942  nop
0x180012943  lea     rcx, [rsp+708h+var_668]; this
0x18001294b  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x180012950  nop
0x180012951  lea     rcx, [rsp+708h+var_6C0]
0x180012956  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x18001295b  jmp     loc_180012C1D
0x180012960  mov     qword ptr [rsp+708h+nLengthNeeded], 0
0x180012969  lea     r8, [rsp+708h+nLengthNeeded]
0x18001296e  mov     rdx, [rsp+708h+StringSecurityDescriptor]
0x180012973  call    ?Append_A_FX_SY@CompatibilityAdapter@@AEAAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; CompatibilityAdapter::Append_A_FX_SY(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x180012978  mov     [rsp+708h+var_6C4], eax
0x18001297c  test    eax, eax
0x18001297e  jns     short loc_1800129FF
0x180012980  lea     r14, WPP_GLOBAL_Control
0x180012987  mov     rcx, cs:WPP_GLOBAL_Control
0x18001298e  cmp     rcx, r14
0x180012991  jz      short loc_1800129B8
0x180012993  test    byte ptr [rcx+1Ch], 2
0x180012997  jz      short loc_1800129B8
0x180012999  cmp     byte ptr [rcx+19h], 2
0x18001299d  jb      short loc_1800129B8
0x18001299f  mov     edx, 16h
0x1800129a4  mov     r9d, eax
0x1800129a7  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x1800129ae  mov     rcx, [rcx+10h]
0x1800129b2  call    WPP_SF_d
0x1800129b7  nop
0x1800129b8  mov     rcx, qword ptr [rsp+708h+nLengthNeeded]; Block
0x1800129bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800129c2  nop
0x1800129c3  lea     rcx, [rsp+708h+StringSecurityDescriptor]
0x1800129c8  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800129cd  nop
0x1800129ce  mov     rcx, rbx; Block
0x1800129d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800129d6  nop
0x1800129d7  mov     rcx, [r12]; hMutex
0x1800129db  call    cs:__imp_ReleaseMutex
0x1800129e1  nop
0x1800129e2  lea     rcx, [rsp+708h+var_668]; this
0x1800129ea  call    ??1TaskLock@@QEAA@XZ; TaskLock::~TaskLock(void)
0x1800129ef  nop
0x1800129f0  lea     rcx, [rsp+708h+var_6C0]
0x1800129f5  call    ??1?$AutoLocalPtr@G@tsched@@QEAA@XZ; tsched::AutoLocalPtr<ushort>::~AutoLocalPtr<ushort>(void)
0x1800129fa  jmp     loc_180012C1D
0x1800129ff  mov     r8, r13; Size
0x180012a02  xor     edx, edx; Val
0x180012a04  lea     rcx, [rsp+708h+var_248]; void *
0x180012a0c  call    memset_0
0x180012a11  lea     rdx, [rsp+708h+var_248]; unsigned __int16 *
0x180012a19  mov     rcx, rsi; unsigned __int16 *
0x180012a1c  call    ?FilenameToUri@@YAJPEBGPEAG@Z; FilenameToUri(ushort const *,ushort *)
0x180012a21  mov     [rsp+708h+var_6C4], eax
0x180012a25  test    eax, eax
0x180012a27  jns     short loc_180012AA8
0x180012a29  lea     r14, WPP_GLOBAL_Control
0x180012a30  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a37  cmp     rcx, r14
0x180012a3a  jz      short loc_180012A61
0x180012a3c  test    byte ptr [rcx+1Ch], 2
0x180012a40  jz      short loc_180012A61
0x180012a42  cmp     byte ptr [rcx+19h], 2
0x180012a46  jb      short loc_180012A61
0x180012a48  mov     edx, 17h
0x180012a4d  mov     r9d, eax
0x180012a50  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180012a57  mov     rcx, [rcx+10h]
0x180012a5b  call    WPP_SF_d
0x180012a60  nop
0x180012a61  mov     rcx, qword ptr [rsp+708h+nLengthNeeded]; Block
  ... truncated ...
```
