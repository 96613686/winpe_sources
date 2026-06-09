# CClientCallRecorder::CreateUpdateDeploymentSessionCFHost(tagDSDeploymentOperation,_GUID const &,ulong,tagMatchingUpdate const * const,tagDeploymentOperationPriority,wchar_t const *,_GUID *)

- ea: `0x18004f840`
- end: `0x18004fd79`
- name: `?CreateUpdateDeploymentSessionCFHost@CClientCallRecorder@@QEAAJW4tagDSDeploymentOperation@@AEBU_GUID@@KQEBUtagMatchingUpdate@@W4tagDeploymentOperationPriority@@PEB_WPEAU3@@Z`
- size: `1337`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64, int, __int64, _OWORD *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180041250`
- `0x180041d00`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x180016034`
- `0x1800160d0`
- `0x18004f840`
- `0x180110914`
- `0x18011098c`
- `0x180111e18`
- `0x1801120ac`
- `0x180113ae8`
- `0x18012b618`
- `0x1801bd7e8`
- `0x1801bdec0`
- `0x180238984`
- `0x180239110`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004fd56`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004fd56`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004fa89`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004fa89`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fa10`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fa6f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004faa3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fa10`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004fa6f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004faa3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f980`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f980`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fd19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fd2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fd19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fd2a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004f9d6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004f9d6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004fbd8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004fbd8`

## string_xrefs

- `0x18004f87c`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004f8b3`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004f94e`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004fab3`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004fc6b`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004fceb`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004fcff`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004f920`: `LoadHighestUpdateDeploymentProvider method failed`
- `0x18004f93b`: `CClientCallRecorder::CreateUpdateDeploymentSessionCFHost`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CClientCallRecorder::CreateUpdateDeploymentSessionCFHost(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        _OWORD *a8)
{
  __int64 v9; // rdx
  int HighestUpdateDeploymentProvider; // esi
  char *v12; // r14
  __int64 v13; // r8
  unsigned int v14; // esi
  __int64 v15; // r15
  bool v16; // r15
  DWORD v17; // eax
  const char *v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r15
  DWORD v21; // eax
  DWORD v22; // eax
  __int64 v23; // rdx
  char *v24; // rax
  void *v25; // rcx
  __int64 v26; // rdx
  int v27; // eax
  unsigned __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // r9
  __int64 v32; // rcx
  int lpString2; // [rsp+20h] [rbp-69h]
  int lpString2a; // [rsp+20h] [rbp-69h]
  char v35; // [rsp+50h] [rbp-39h]
  _QWORD v36[2]; // [rsp+58h] [rbp-31h] BYREF
  HMODULE hLibModule; // [rsp+68h] [rbp-21h] BYREF
  char *v38; // [rsp+70h] [rbp-19h]
  _OWORD *v39; // [rsp+78h] [rbp-11h]
  __int64 v40; // [rsp+80h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+3Fh]

  v39 = a8;
  if ( !a4 )
  {
    v9 = 8202;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)0x80070057LL,
      lpString2);
    return 2147942487LL;
  }
  if ( !a5 )
  {
    v9 = 8203;
    goto LABEL_3;
  }
  if ( a8 )
  {
    hLibModule = 0;
    v36[1] = 0;
    LODWORD(v36[0]) = 0;
    v12 = 0;
    HighestUpdateDeploymentProvider = LoadHighestUpdateDeploymentProvider(
                                        (int)a1 + 672,
                                        (unsigned int)&hLibModule,
                                        a4,
                                        a5);
    if ( HighestUpdateDeploymentProvider < 0 )
    {
      WUTrace(
        "CClientCallRecorder::CreateUpdateDeploymentSessionCFHost",
        8224,
        1,
        1,
        HighestUpdateDeploymentProvider,
        L"LoadHighestUpdateDeploymentProvider method failed");
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2021,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
        (const char *)(unsigned int)HighestUpdateDeploymentProvider,
        lpString2a);
LABEL_76:
      if ( hLibModule )
        FreeLibrary(hLibModule);
      return (unsigned int)HighestUpdateDeploymentProvider;
    }
    v35 = LODWORD(v36[0]) != 1;
    v40 = a1 + 600;
    if ( a1 != -600 )
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 608));
    v14 = *(_DWORD *)(a1 + 668);
    v15 = 0;
    if ( v14 )
    {
      while ( 1 )
      {
        v12 = *(char **)(*(_QWORD *)(a1 + 656) + 8 * v15);
        v13 = *(_QWORD *)v12;
        if ( !*(_QWORD *)v12 && v12[8] == v35 )
          break;
        v15 = (unsigned int)(v15 + 1);
        if ( (unsigned int)v15 >= *(_DWORD *)(a1 + 668) )
          goto LABEL_16;
      }
      v14 = v15;
    }
LABEL_16:
    v16 = v14 == *(_DWORD *)(a1 + 668);
    if ( v14 == *(_DWORD *)(a1 + 668) )
      goto LABEL_35;
    v17 = WaitForSingleObject(*((HANDLE *)v12 + 5), 0);
    if ( v17 == -1 )
    {
      v19 = 8267;
LABEL_30:
      HighestUpdateDeploymentProvider = wil::details::in1diag3::Return_GetLastError(
                                          retaddr,
                                          (void *)v19,
                                          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
                                          v18);
      goto LABEL_71;
    }
    if ( v17 != 258 )
    {
      v20 = a1 + 648;
      if ( v14 < *(_DWORD *)(a1 + 668) )
        CSusArrayList<tagUpdateDeploymentSessionHostInfo *,CSusArrayListItemOpDelete<tagUpdateDeploymentSessionHostInfo *>>::RemoveArraySection(
          a1 + 648,
          v14,
          v14,
          1);
      goto LABEL_37;
    }
    v21 = WaitForSingleObject(*((HANDLE *)v12 + 6), 0xEA60u);
    if ( v21 == -1 )
    {
      v19 = 8281;
      goto LABEL_30;
    }
    if ( !v21 )
    {
LABEL_35:
      if ( !v16 )
      {
        if ( !v12 )
        {
          HighestUpdateDeploymentProvider = -2147467261;
          v30 = 8162;
          v31 = 2147500035LL;
LABEL_69:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v30,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
            (const char *)v31,
            lpString2);
          v23 = 8334;
          goto LABEL_70;
        }
LABEL_54:
        v29 = 1;
        if ( a6 )
        {
          if ( a6 == 1 )
            v29 = 2;
        }
        else
        {
          v29 = 3;
        }
        v32 = *((_QWORD *)v12 + 5);
        if ( v12[8] )
        {
          HighestUpdateDeploymentProvider = ChangeProcessPriorityState(v32, v29);
          v31 = (unsigned int)HighestUpdateDeploymentProvider;
          if ( HighestUpdateDeploymentProvider < 0 )
          {
            v30 = 8182;
            goto LABEL_69;
          }
        }
        else
        {
          LOBYTE(v13) = 1;
          HighestUpdateDeploymentProvider = ChangeThreadPriorityState(v32, v29, v13);
          v31 = (unsigned int)HighestUpdateDeploymentProvider;
          if ( HighestUpdateDeploymentProvider < 0 )
          {
            v30 = 8188;
            goto LABEL_69;
          }
        }
        if ( a1 != -600 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 608));
        *v39 = *(_OWORD *)(v12 + 24);
        HighestUpdateDeploymentProvider = 0;
        goto LABEL_76;
      }
    }
    else
    {
      if ( !SetEvent(*((HANDLE *)v12 + 7)) )
      {
        v19 = 8290;
        goto LABEL_30;
      }
      v22 = WaitForSingleObject(*((HANDLE *)v12 + 5), 0xEA60u);
      if ( v22 == -1 )
      {
        v19 = 8293;
        goto LABEL_30;
      }
      if ( v22 == 258 )
      {
        HighestUpdateDeploymentProvider = -2147024638;
        v23 = 8294;
LABEL_70:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
          (const char *)(unsigned int)HighestUpdateDeploymentProvider,
          lpString2);
LABEL_71:
        if ( a1 != -600 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 608));
        goto LABEL_76;
      }
      if ( v14 < *(_DWORD *)(a1 + 668) )
        CSusArrayList<tagUpdateDeploymentSessionHostInfo *,CSusArrayListItemOpDelete<tagUpdateDeploymentSessionHostInfo *>>::RemoveArraySection(
          a1 + 648,
          v14,
          v14,
          1);
    }
    v20 = a1 + 648;
LABEL_37:
    v24 = (char *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v24;
    v38 = v24;
    if ( !v24 )
    {
      v12 = 0;
      HighestUpdateDeploymentProvider = -2147024882;
      v26 = 8307;
      goto LABEL_58;
    }
    memset(v24, 0, 0x48u);
    *(_QWORD *)v12 = 0;
    *((_QWORD *)v12 + 2) = 0;
    *((_QWORD *)v12 + 5) = 0;
    *((_QWORD *)v12 + 6) = 0;
    *((_QWORD *)v12 + 7) = 0;
    *((_QWORD *)v12 + 8) = 0;
    v38 = v12;
    v12[8] = v35;
    v25 = (void *)*((_QWORD *)v12 + 2);
    if ( v25 )
    {
      SusFree(v25);
      *((_QWORD *)v12 + 2) = 0;
    }
    HighestUpdateDeploymentProvider = DuplicateString<wchar_t const *,wchar_t *>(L"1.0.0.0", v12 + 16);
    if ( HighestUpdateDeploymentProvider < 0 )
    {
      v26 = 8313;
LABEL_58:
      v28 = (unsigned int)HighestUpdateDeploymentProvider;
LABEL_59:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
        (const char *)v28,
        lpString2);
      if ( v12 )
      {
        tagUpdateDeploymentSessionHostInfo::~tagUpdateDeploymentSessionHostInfo((tagUpdateDeploymentSessionHostInfo *)v12);
        operator delete(v12, (const struct std::nothrow_t *)0x48);
      }
      goto LABEL_71;
    }
    if ( *(_QWORD *)v12 )
    {
      SusFree(*(void **)v12);
      *(_QWORD *)v12 = 0;
    }
    HighestUpdateDeploymentProvider = DuplicateString<wchar_t *,wchar_t *>(0, v12);
    if ( HighestUpdateDeploymentProvider < 0 )
    {
      v26 = 8316;
      goto LABEL_58;
    }
    if ( v35 )
    {
      HighestUpdateDeploymentProvider = CoCreateGuid((GUID *)(v12 + 24));
      if ( HighestUpdateDeploymentProvider < 0 )
      {
        v26 = 8320;
        goto LABEL_58;
      }
    }
    else
    {
      *(GUID *)(v12 + 24) = CLSID_UpdateDeploymentSession;
    }
    HighestUpdateDeploymentProvider = CreateUpdateDeploymentSessionCF(a1 + 672, v12);
    if ( HighestUpdateDeploymentProvider < 0 )
    {
      v26 = 8327;
      goto LABEL_58;
    }
    v36[0] = v12;
    v27 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)(a1 + 648) + 8LL))(v20, v36, 0);
    HighestUpdateDeploymentProvider = v27;
    if ( v27 < 0 )
    {
      v28 = (unsigned int)v27;
      v26 = 8329;
      goto LABEL_59;
    }
    goto LABEL_54;
  }
  HighestUpdateDeploymentProvider = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x200C,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
    (const char *)0x80004003LL,
    lpString2);
  return (unsigned int)HighestUpdateDeploymentProvider;
}

```

## disassembly

```asm
0x18004f840  mov     [rsp-8+arg_8], rbx
0x18004f845  push    rbp
0x18004f846  push    rsi
0x18004f847  push    rdi
0x18004f848  push    r12
0x18004f84a  push    r13
0x18004f84c  push    r14
0x18004f84e  push    r15
0x18004f850  lea     rbp, [rsp-7]
0x18004f855  sub     rsp, 90h
0x18004f85c  mov     eax, r9d
0x18004f85f  mov     r13, rcx
0x18004f862  mov     r9, [rbp+37h+arg_20]
0x18004f866  mov     rcx, [rbp+37h+arg_38]
0x18004f86a  mov     [rbp+37h+var_48], rcx
0x18004f86e  test    eax, eax
0x18004f870  jnz     short loc_18004F896
0x18004f872  mov     edx, 200Ah; void *
0x18004f877  mov     ebx, 80070057h
0x18004f87c  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18004f883  mov     r9d, ebx; char *
0x18004f886  mov     rcx, [rbp+3Fh]; this
0x18004f88a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f88f  mov     eax, ebx
0x18004f891  jmp     loc_18004FD5E
0x18004f896  test    r9, r9
0x18004f899  jnz     short loc_18004F8A2
0x18004f89b  mov     edx, 200Bh
0x18004f8a0  jmp     short loc_18004F877
0x18004f8a2  test    rcx, rcx
0x18004f8a5  jnz     short loc_18004F8C9
0x18004f8a7  mov     rcx, [rbp+3Fh]; this
0x18004f8ab  mov     esi, 80004003h
0x18004f8b0  mov     r9d, esi; char *
0x18004f8b3  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18004f8ba  mov     edx, 200Ch; void *
0x18004f8bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f8c4  jmp     loc_18004FD5C
0x18004f8c9  mov     [rbp+37h+hLibModule], 0
0x18004f8d1  mov     [rbp+37h+var_60], 0
0x18004f8d9  mov     dword ptr [rbp+37h+var_68], 0
0x18004f8e0  xor     r14d, r14d
0x18004f8e3  lea     rcx, [r13+2A0h]
0x18004f8ea  lea     rdx, [rbp+37h+var_68]
0x18004f8ee  mov     [rsp+0C0h+var_80], rdx
0x18004f8f3  lea     rdx, [rbp+37h+var_60]
0x18004f8f7  mov     [rsp+0C0h+var_88], rdx
0x18004f8fc  lea     rdx, [rbp+37h+hLibModule]
0x18004f900  mov     [rsp+0C0h+var_90], rdx
0x18004f905  mov     qword ptr [rsp+0C0h+cchCount2], rcx
0x18004f90a  mov     r8d, eax
0x18004f90d  call    ?LoadHighestUpdateDeploymentProvider@@YAJW4tagDSDeploymentOperation@@U_GUID@@KQEBUtagMatchingUpdate@@PEB_WAEAV?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@wistd@@@wistd@@PEAPEAUHINSTANCE__@@PEAPEA_WPEAW4DeploymentModuleType@@@Z; LoadHighestUpdateDeploymentProvider(tagDSDeploymentOperation,_GUID,ulong,tagMatchingUpdate const * const,wchar_t const *,wistd::unique_ptr<uus::Session,wistd::default_delete<uus::Session>> &,HINSTANCE__ * *,wchar_t * *,DeploymentModuleType *)
0x18004f912  mov     esi, eax
0x18004f914  mov     rdi, [rbp+37h+var_60]
0x18004f918  lea     r12d, [r14+1]
0x18004f91c  test    eax, eax
0x18004f91e  jns     short loc_18004F964
0x18004f920  lea     rax, aLoadhighestupd; "LoadHighestUpdateDeploymentProvider met"...
0x18004f927  mov     qword ptr [rsp+0C0h+cchCount2], rax
0x18004f92c  mov     dword ptr [rsp+0C0h+lpString2], esi; int
0x18004f930  mov     r9d, r12d
0x18004f933  mov     r8d, r12d
0x18004f936  mov     edx, 2020h
0x18004f93b  lea     rcx, aCclientcallrec_8; "CClientCallRecorder::CreateUpdateDeploy"...
0x18004f942  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18004f947  mov     rcx, [rbp+3Fh]; this
0x18004f94b  mov     r9d, esi; char *
0x18004f94e  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18004f955  mov     edx, 2021h; void *
0x18004f95a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f95f  jmp     loc_18004FD3F
0x18004f964  cmp     dword ptr [rbp+37h+var_68], r12d
0x18004f968  setnz   [rbp+37h+var_70]
0x18004f96c  lea     rbx, [r13+258h]
0x18004f973  mov     [rbp+37h+var_40], rbx
0x18004f977  test    rbx, rbx
0x18004f97a  jz      short loc_18004F987
0x18004f97c  lea     rcx, [rbx+8]; lpCriticalSection
0x18004f980  call    cs:__imp_EnterCriticalSection
0x18004f986  nop
0x18004f987  mov     esi, [r13+29Ch]
0x18004f98e  xor     r15d, r15d
0x18004f991  test    esi, esi
0x18004f993  jz      short loc_18004F9F9
0x18004f995  mov     eax, esi
0x18004f997  cmp     r15d, eax
0x18004f99a  jnb     loc_18004FA2A
0x18004f9a0  mov     rax, [r13+290h]
0x18004f9a7  mov     r14, [rax+r15*8]
0x18004f9ab  mov     r8, [r14]; lpString1
0x18004f9ae  cmp     r8, rdi
0x18004f9b1  jz      short loc_18004F9E1
0x18004f9b3  test    r8, r8
0x18004f9b6  jz      short loc_18004F9EA
0x18004f9b8  test    rdi, rdi
0x18004f9bb  jz      short loc_18004F9EA
0x18004f9bd  mov     [rsp+0C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18004f9c5  mov     [rsp+0C0h+lpString2], rdi; int
0x18004f9ca  or      r9d, 0FFFFFFFFh; cchCount1
0x18004f9ce  mov     edx, r12d; dwCmpFlags
0x18004f9d1  mov     ecx, 7Fh; Locale
0x18004f9d6  call    cs:__imp_CompareStringW
0x18004f9dc  cmp     eax, 2
0x18004f9df  jnz     short loc_18004F9EA
0x18004f9e1  mov     al, [rbp+37h+var_70]
0x18004f9e4  cmp     [r14+8], al
0x18004f9e8  jz      short loc_18004FA25
0x18004f9ea  add     r15d, r12d
0x18004f9ed  mov     eax, [r13+29Ch]
0x18004f9f4  cmp     r15d, eax
0x18004f9f7  jb      short loc_18004F9A0
0x18004f9f9  cmp     esi, [r13+29Ch]
0x18004fa00  setz    r15b
0x18004fa04  jz      loc_18004FAFB
0x18004fa0a  xor     edx, edx; dwMilliseconds
0x18004fa0c  mov     rcx, [r14+28h]; hHandle
0x18004fa10  call    cs:__imp_WaitForSingleObject
0x18004fa16  cmp     eax, 0FFFFFFFFh
0x18004fa19  jnz     short loc_18004FA39
0x18004fa1b  mov     edx, 204Bh
0x18004fa20  jmp     loc_18004FAB3
0x18004fa25  mov     esi, r15d
0x18004fa28  jmp     short loc_18004F9F9
0x18004fa2a  mov     esi, 80240007h
0x18004fa2f  mov     edx, 2032h
0x18004fa34  jmp     loc_18004FCFC
0x18004fa39  cmp     eax, 102h
0x18004fa3e  jz      short loc_18004FA66
0x18004fa40  lea     r15, [r13+288h]
0x18004fa47  cmp     esi, [r15+14h]
0x18004fa4b  jnb     loc_18004FB0B
0x18004fa51  mov     r9d, r12d
0x18004fa54  mov     r8d, esi
0x18004fa57  mov     edx, esi
0x18004fa59  mov     rcx, r15
0x18004fa5c  call    ?RemoveArraySection@?$CSusArrayList@PEAUtagUpdateDeploymentSessionHostInfo@@V?$CSusArrayListItemOpDelete@PEAUtagUpdateDeploymentSessionHostInfo@@@@@@IEAAXKKH@Z; CSusArrayList<tagUpdateDeploymentSessionHostInfo *,CSusArrayListItemOpDelete<tagUpdateDeploymentSessionHostInfo *>>::RemoveArraySection(ulong,ulong,int)
0x18004fa61  jmp     loc_18004FB0B
0x18004fa66  mov     edx, 0EA60h; dwMilliseconds
0x18004fa6b  mov     rcx, [r14+30h]; hHandle
0x18004fa6f  call    cs:__imp_WaitForSingleObject
0x18004fa75  cmp     eax, 0FFFFFFFFh
0x18004fa78  jnz     short loc_18004FA81
0x18004fa7a  mov     edx, 2059h
0x18004fa7f  jmp     short loc_18004FAB3
0x18004fa81  test    eax, eax
0x18004fa83  jz      short loc_18004FAFB
0x18004fa85  mov     rcx, [r14+38h]; hEvent
0x18004fa89  call    cs:__imp_SetEvent
0x18004fa8f  test    eax, eax
0x18004fa91  jnz     short loc_18004FA9A
0x18004fa93  mov     edx, 2062h
0x18004fa98  jmp     short loc_18004FAB3
0x18004fa9a  mov     edx, 0EA60h; dwMilliseconds
0x18004fa9f  mov     rcx, [r14+28h]; hHandle
0x18004faa3  call    cs:__imp_WaitForSingleObject
0x18004faa9  cmp     eax, 0FFFFFFFFh
0x18004faac  jnz     short loc_18004FACA
0x18004faae  mov     edx, 2065h; void *
0x18004fab3  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18004faba  mov     rcx, [rbp+3Fh]; this
0x18004fabe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004fac3  mov     esi, eax
0x18004fac5  jmp     loc_18004FD10
0x18004faca  cmp     eax, 102h
0x18004facf  jnz     short loc_18004FAE0
0x18004fad1  mov     esi, 80070102h
0x18004fad6  mov     edx, 2066h
0x18004fadb  jmp     loc_18004FCFC
0x18004fae0  lea     rcx, [r13+288h]
0x18004fae7  cmp     esi, [rcx+14h]
0x18004faea  jnb     short loc_18004FB04
0x18004faec  mov     r9d, r12d
0x18004faef  mov     r8d, esi
0x18004faf2  mov     edx, esi
0x18004faf4  call    ?RemoveArraySection@?$CSusArrayList@PEAUtagUpdateDeploymentSessionHostInfo@@V?$CSusArrayListItemOpDelete@PEAUtagUpdateDeploymentSessionHostInfo@@@@@@IEAAXKKH@Z; CSusArrayList<tagUpdateDeploymentSessionHostInfo *,CSusArrayListItemOpDelete<tagUpdateDeploymentSessionHostInfo *>>::RemoveArraySection(ulong,ulong,int)
0x18004faf9  jmp     short loc_18004FB04
0x18004fafb  test    r15b, r15b
0x18004fafe  jz      loc_18004FC98
0x18004fb04  lea     r15, [r13+288h]
0x18004fb0b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004fb12  mov     esi, 48h ; 'H'
0x18004fb17  mov     ecx, esi; unsigned __int64
0x18004fb19  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004fb1e  mov     r14, rax
0x18004fb21  mov     [rbp+37h+var_50], rax
0x18004fb25  test    rax, rax
0x18004fb28  jz      loc_18004FC57
0x18004fb2e  mov     r8d, esi; Size
0x18004fb31  xor     edx, edx; Val
0x18004fb33  mov     rcx, rax; void *
0x18004fb36  call    memset
0x18004fb3b  xor     edx, edx
0x18004fb3d  mov     [r14], rdx
0x18004fb40  mov     [r14+10h], rdx
0x18004fb44  mov     [r14+28h], rdx
0x18004fb48  mov     [r14+30h], rdx
0x18004fb4c  mov     [r14+38h], rdx
0x18004fb50  mov     [r14+40h], rdx
0x18004fb54  mov     [rbp+37h+var_50], r14
0x18004fb58  test    r14, r14
0x18004fb5b  jz      loc_18004FC5A
0x18004fb61  mov     al, [rbp+37h+var_70]
0x18004fb64  mov     [r14+8], al
0x18004fb68  lea     rsi, [r14+10h]
0x18004fb6c  mov     rcx, [rsi]; lpMem
0x18004fb6f  test    rcx, rcx
0x18004fb72  jz      short loc_18004FB80
0x18004fb74  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18004fb79  mov     qword ptr [rsi], 0
0x18004fb80  mov     rdx, rsi
0x18004fb83  lea     rcx, a1000; "1.0.0.0"
0x18004fb8a  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18004fb8f  mov     esi, eax
0x18004fb91  test    eax, eax
0x18004fb93  jns     short loc_18004FB9F
0x18004fb95  mov     edx, 2079h
0x18004fb9a  jmp     loc_18004FC64
0x18004fb9f  mov     rcx, [r14]; lpMem
0x18004fba2  test    rcx, rcx
0x18004fba5  jz      short loc_18004FBB3
0x18004fba7  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18004fbac  mov     qword ptr [r14], 0
0x18004fbb3  mov     rdx, r14
0x18004fbb6  mov     rcx, rdi
0x18004fbb9  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18004fbbe  mov     esi, eax
0x18004fbc0  test    eax, eax
0x18004fbc2  jns     short loc_18004FBCE
0x18004fbc4  mov     edx, 207Ch
0x18004fbc9  jmp     loc_18004FC64
0x18004fbce  cmp     [rbp+37h+var_70], 0
0x18004fbd2  jz      short loc_18004FBEB
0x18004fbd4  lea     rcx, [r14+18h]; pguid
0x18004fbd8  call    cs:__imp_CoCreateGuid
0x18004fbde  mov     esi, eax
0x18004fbe0  test    eax, eax
0x18004fbe2  jns     short loc_18004FBF8
0x18004fbe4  mov     edx, 2080h
0x18004fbe9  jmp     short loc_18004FC64
0x18004fbeb  movups  xmm0, xmmword ptr cs:CLSID_UpdateDeploymentSession.Data1
0x18004fbf2  movdqu  xmmword ptr [r14+18h], xmm0
0x18004fbf8  mov     rdx, r14
0x18004fbfb  lea     rcx, [r13+2A0h]
0x18004fc02  call    ?CreateUpdateDeploymentSessionCF@@YAJAEAV?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@wistd@@@wistd@@PEAUtagUpdateDeploymentSessionHostInfo@@@Z; CreateUpdateDeploymentSessionCF(wistd::unique_ptr<uus::Session,wistd::default_delete<uus::Session>> &,tagUpdateDeploymentSessionHostInfo *)
0x18004fc07  mov     esi, eax
0x18004fc09  test    eax, eax
0x18004fc0b  jns     short loc_18004FC14
0x18004fc0d  mov     edx, 2087h
0x18004fc12  jmp     short loc_18004FC64
0x18004fc14  mov     [rbp+37h+var_68], r14
0x18004fc18  mov     rax, [r13+288h]
0x18004fc1f  xor     r8d, r8d
0x18004fc22  lea     rdx, [rbp+37h+var_68]
0x18004fc26  mov     rcx, r15
0x18004fc29  mov     rax, [rax+8]
0x18004fc2d  call    _guard_dispatch_icall
0x18004fc32  mov     esi, eax
0x18004fc34  test    eax, eax
0x18004fc36  jns     short loc_18004FC42
0x18004fc38  mov     r9d, eax
0x18004fc3b  mov     edx, 2089h
0x18004fc40  jmp     short loc_18004FC67
0x18004fc42  mov     edx, r12d
0x18004fc45  mov     ecx, [rbp+37h+arg_28]
0x18004fc48  test    ecx, ecx
0x18004fc4a  jz      short loc_18004FCAC
0x18004fc4c  cmp     ecx, edx
0x18004fc4e  jnz     short loc_18004FCB1
0x18004fc50  mov     edx, 2
0x18004fc55  jmp     short loc_18004FCB1
0x18004fc57  xor     r14d, r14d
0x18004fc5a  mov     esi, 8007000Eh
0x18004fc5f  mov     edx, 2073h; void *
0x18004fc64  mov     r9d, esi; char *
0x18004fc67  mov     rcx, [rbp+3Fh]; this
0x18004fc6b  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18004fc72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fc77  nop
0x18004fc78  test    r14, r14
0x18004fc7b  jz      loc_18004FD10
0x18004fc81  mov     rcx, r14; this
0x18004fc84  call    ??1tagUpdateDeploymentSessionHostInfo@@QEAA@XZ; tagUpdateDeploymentSessionHostInfo::~tagUpdateDeploymentSessionHostInfo(void)
0x18004fc89  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x18004fc8e  mov     rcx, r14; void *
0x18004fc91  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004fc96  jmp     short loc_18004FD10
0x18004fc98  test    r14, r14
0x18004fc9b  jnz     short loc_18004FC42
0x18004fc9d  mov     esi, 80004003h
0x18004fca2  mov     edx, 1FE2h
0x18004fca7  mov     r9d, esi
0x18004fcaa  jmp     short loc_18004FCE7
0x18004fcac  mov     edx, 3
0x18004fcb1  mov     rcx, [r14+28h]
0x18004fcb5  cmp     byte ptr [r14+8], 0
0x18004fcba  jz      short loc_18004FCD1
0x18004fcbc  call    ?ChangeProcessPriorityState@@YAJPEAXW4ThreadPriorityLevel@@_N@Z; ChangeProcessPriorityState(void *,ThreadPriorityLevel,bool)
0x18004fcc1  mov     esi, eax
0x18004fcc3  mov     r9d, eax
0x18004fcc6  test    eax, eax
  ... truncated ...
```
