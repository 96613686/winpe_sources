# CreateMediumIntegritySplWow64(void)

- ea: `0x14004b6c4`
- end: `0x14004b9d1`
- name: `?CreateMediumIntegritySplWow64@@YAKXZ`
- size: `781`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400353d0`

## callees

- `0x1400087c8`
- `0x14000d4d0`
- `0x140010300`
- `0x140010c4c`
- `0x14001748c`
- `0x140018f84`
- `0x14002d0a0`
- `0x14004b6c4`
- `0x14004b9d8`
- `0x14004bbd0`
- `0x14004bf6c`
- `0x140056b58`
- `0x140056bb4`
- `0x140056c3c`
- `0x140056d8c`
- `0x14005e898`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14004b7b2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14004b7b2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14004b931`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14004b96e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14004b931`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14004b96e`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14004b7c7`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14004b7c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14004b88a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14004b88a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14004b796`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14004b796`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14004b8e8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14004b8e8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14004b73b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14004b73b`

## string_xrefs

- `0x14004b6f5`: `CreateMediumIntegritySplWow64`
- `0x14004b89b`: `GetSidAsString failed. Error 0x%x`
- `0x14004b8b7`: `QueryTo IPrintScanBrokerHandler failed. Error 0x%x`
- `0x14004b8d4`: `RoActivateInstance for PrintScanBrokerHandler failed. Error 0x%x`
- `0x14004b78f`: `Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler`

## pseudocode

```c
unsigned int __fastcall CreateMediumIntegritySplWow64(__int64 a1, int a2, int a3)
{
  int AuthenticationIdAndIntegrity; // edi
  HRESULT v4; // r14d
  HRESULT v5; // eax
  int v6; // eax
  int v7; // eax
  int SidAsString; // eax
  unsigned __int16 *v9; // rbx
  __int64 v10; // rsi
  int v11; // eax
  NCoreLibrary::TString *v12; // rcx
  void *v13; // rbx
  void *v14; // rdx
  int LastErrorAsHResult; // eax
  void *v16; // rdx
  int v17; // edx
  unsigned int v19; // [rsp+30h] [rbp-79h] BYREF
  void *v20; // [rsp+38h] [rbp-71h] BYREF
  void *v21; // [rsp+40h] [rbp-69h] BYREF
  HSTRING v22; // [rsp+48h] [rbp-61h] BYREF
  struct _LUID v23; // [rsp+50h] [rbp-59h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-51h] BYREF
  HSTRING string; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v26[56]; // [rsp+80h] [rbp-29h] BYREF
  int v27; // [rsp+B8h] [rbp+Fh]

  NSecurityLibrary::TSidUserContext::TSidUserContext((NSecurityLibrary::TSidUserContext *)v26, a2, a3);
  AuthenticationIdAndIntegrity = v27;
  if ( v27 < 0 )
    goto LABEL_38;
  v19 = 0;
  v23 = 0;
  AuthenticationIdAndIntegrity = NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(
                                   (NSecurityLibrary::TSidUserContext *)v26,
                                   &v23,
                                   &v19);
  if ( AuthenticationIdAndIntegrity < 0 )
    goto LABEL_38;
  if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    v4 = CoInitializeEx(0, 0);
    if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147417850 )
    {
      AuthenticationIdAndIntegrity = v4;
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "CreateMediumIntegritySplWow64",
        L"CoInitializeEx failed. Error 0x%x",
        (unsigned int)v4);
LABEL_38:
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "CreateMediumIntegritySplWow64",
        L"Failed to launch medium IL Splwow64. Error 0x%x",
        (unsigned int)AuthenticationIdAndIntegrity);
      goto LABEL_39;
    }
    v21 = 0;
    string = 0;
    v5 = WindowsCreateStringReference(
           L"Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler",
           0x49u,
           &hstringHeader,
           &string);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      __debugbreak();
    }
    v6 = RoActivateInstance(string, &v21);
    AuthenticationIdAndIntegrity = v6;
    if ( v6 < 0 )
    {
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "CreateMediumIntegritySplWow64",
        L"RoActivateInstance for PrintScanBrokerHandler failed. Error 0x%x",
        (unsigned int)v6);
    }
    else
    {
      v20 = 0;
      v7 = (**(__int64 (__fastcall ***)(void *, GUID *, void **))v21)(
             v21,
             &GUID_42964634_70ff_4d1c_8ea0_520607b4c1c3,
             &v20);
      AuthenticationIdAndIntegrity = v7;
      if ( v7 < 0 )
      {
        SpoolerServiceTelemetry::WriteDbgTraceError(
          "CreateMediumIntegritySplWow64",
          L"QueryTo IPrintScanBrokerHandler failed. Error 0x%x",
          (unsigned int)v7);
      }
      else
      {
        v22 = (HSTRING)&NCoreLibrary::TString::gszNullState;
        SidAsString = NSecurityLibrary::TSidUserContext::GetSidAsString(
                        (NSecurityLibrary::TSidUserContext *)v26,
                        (struct NCoreLibrary::TString *)&v22);
        v9 = (unsigned __int16 *)v22;
        AuthenticationIdAndIntegrity = SidAsString;
        if ( SidAsString < 0 )
        {
          SpoolerServiceTelemetry::WriteDbgTraceError(
            "CreateMediumIntegritySplWow64",
            L"GetSidAsString failed. Error 0x%x",
            (unsigned int)SidAsString);
        }
        else
        {
          v22 = 0;
          v10 = -1;
          do
            ++v10;
          while ( v9[v10] );
          Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v22, v9, v10);
          v11 = (*(__int64 (__fastcall **)(void *, HSTRING, _QWORD, _QWORD, unsigned int))(*(_QWORD *)v20 + 80LL))(
                  v20,
                  v22,
                  v23.LowPart,
                  (unsigned int)v23.HighPart,
                  v19);
          AuthenticationIdAndIntegrity = v11;
          if ( v11 < 0 )
            SpoolerServiceTelemetry::WriteDbgTraceError(
              "CreateMediumIntegritySplWow64",
              L"LaunchSplWOW64 failed. Error 0x%x",
              (unsigned int)v11);
          WindowsDeleteString(v22);
        }
        NCoreLibrary::TString::vFree(v12, v9);
      }
      sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v20);
    }
    if ( v4 >= 0 )
      CoUninitialize();
    sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v21);
  }
  else
  {
    v20 = (void *)-1LL;
    v21 = (void *)-1LL;
    AuthenticationIdAndIntegrity = GetUserTokens(&v20, &v21);
    if ( AuthenticationIdAndIntegrity >= 0 )
    {
      v13 = v21;
      v14 = v21;
      if ( v21 == (void *)-1LL )
        v14 = 0;
      if ( SetThreadToken(0, v14) )
      {
        if ( v13 == (void *)-1LL )
          v13 = 0;
        LastErrorAsHResult = InternalCreateSplWowProcess(v13, &v23, v19);
      }
      else
      {
        LastErrorAsHResult = GetLastErrorAsHResult();
      }
      v16 = v20;
      AuthenticationIdAndIntegrity = LastErrorAsHResult;
      if ( v20 == (void *)-1LL )
        v16 = 0;
      SetThreadToken(0, v16);
    }
    NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&v21);
    NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&v20);
  }
  if ( AuthenticationIdAndIntegrity < 0 )
    goto LABEL_38;
LABEL_39:
  NSecurityLibrary::TSidUserContext::~TSidUserContext((NSecurityLibrary::TSidUserContext *)v26);
  return NCoreLibrary::StatusFromHResult((NCoreLibrary *)(unsigned int)AuthenticationIdAndIntegrity, v17);
}

```

## disassembly

```asm
0x14004b6c4  push    rbp
0x14004b6c6  push    rbx
0x14004b6c7  push    rsi
0x14004b6c8  push    rdi
0x14004b6c9  push    r12
0x14004b6cb  push    r14
0x14004b6cd  push    r15
0x14004b6cf  lea     rbp, [rsp-27h]
0x14004b6d4  sub     rsp, 0D0h
0x14004b6db  mov     rax, cs:__security_cookie
0x14004b6e2  xor     rax, rsp
0x14004b6e5  mov     [rbp+57h+var_40], rax
0x14004b6e9  lea     rcx, [rbp+57h+var_80]; this
0x14004b6ed  call    ??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z; NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)
0x14004b6f2  mov     edi, [rbp+57h+var_48]
0x14004b6f5  lea     r12, aCreatemediumin; "CreateMediumIntegritySplWow64"
0x14004b6fc  xor     r15d, r15d
0x14004b6ff  test    edi, edi
0x14004b701  js      loc_14004B990
0x14004b707  lea     r8, [rbp+57h+var_D0]; unsigned int *
0x14004b70b  mov     [rbp+57h+var_D0], r15d
0x14004b70f  lea     rdx, [rbp+57h+var_B0]; struct _LUID *
0x14004b713  mov     qword ptr [rbp+57h+var_B0.LowPart], r15
0x14004b717  lea     rcx, [rbp+57h+var_80]; this
0x14004b71b  call    ?GetAuthenticationIdAndIntegrity@TSidUserContext@NSecurityLibrary@@QEBAJPEAU_LUID@@PEAK@Z; NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(_LUID *,ulong *)
0x14004b720  mov     edi, eax
0x14004b722  test    eax, eax
0x14004b724  js      loc_14004B990
0x14004b72a  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x14004b72f  test    eax, eax
0x14004b731  jz      loc_14004B902
0x14004b737  xor     edx, edx; dwCoInit
0x14004b739  xor     ecx, ecx; pvReserved
0x14004b73b  call    cs:__imp_CoInitializeEx
0x14004b742  nop     dword ptr [rax+rax+00h]
0x14004b747  mov     r14d, eax
0x14004b74a  mov     eax, 80000000h
0x14004b74f  lea     ecx, [r14+rax]
0x14004b753  test    eax, ecx
0x14004b755  jnz     short loc_14004B77A
0x14004b757  cmp     r14d, 80010106h
0x14004b75e  jz      short loc_14004B77A
0x14004b760  mov     r8d, r14d
0x14004b763  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed. Error 0x%x"
0x14004b76a  mov     rcx, r12; char *
0x14004b76d  mov     edi, r14d
0x14004b770  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004b775  jmp     loc_14004B990
0x14004b77a  lea     r9, [rbp+57h+string]; string
0x14004b77e  mov     [rbp+57h+var_C0], r15
0x14004b782  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14004b786  mov     [rbp+57h+string], r15
0x14004b78a  mov     edx, 49h ; 'I'; length
0x14004b78f  lea     rcx, ?RuntimeClass_Windows_Graphics_Internal_Printing_PrintScanBroker_PrintScanBrokerHandler@@3QBGB; "Windows.Graphics.Internal.Printing.Prin"...
0x14004b796  call    cs:__imp_WindowsCreateStringReference
0x14004b79d  nop     dword ptr [rax+rax+00h]
0x14004b7a2  test    eax, eax
0x14004b7a4  jns     short loc_14004B7BF
0x14004b7a6  xor     r9d, r9d; lpArguments
0x14004b7a9  xor     r8d, r8d; nNumberOfArguments
0x14004b7ac  mov     ecx, eax; dwExceptionCode
0x14004b7ae  lea     edx, [r9+1]; dwExceptionFlags
0x14004b7b2  call    cs:__imp_RaiseException
0x14004b7b9  nop     dword ptr [rax+rax+00h]
0x14004b7be  int     3; Trap to Debugger
0x14004b7bf  mov     rcx, [rbp+57h+string]
0x14004b7c3  lea     rdx, [rbp+57h+var_C0]
0x14004b7c7  call    cs:__imp_RoActivateInstance
0x14004b7ce  nop     dword ptr [rax+rax+00h]
0x14004b7d3  mov     edi, eax
0x14004b7d5  test    eax, eax
0x14004b7d7  js      loc_14004B8D1
0x14004b7dd  mov     rcx, [rbp+57h+var_C0]
0x14004b7e1  lea     r8, [rbp+57h+var_C8]
0x14004b7e5  mov     [rbp+57h+var_C8], r15
0x14004b7e9  lea     rdx, _GUID_42964634_70ff_4d1c_8ea0_520607b4c1c3
0x14004b7f0  mov     rax, [rcx]
0x14004b7f3  mov     rax, [rax]
0x14004b7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b7fb  mov     edi, eax
0x14004b7fd  test    eax, eax
0x14004b7ff  js      loc_14004B8B4
0x14004b805  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x14004b80c  lea     rdx, [rbp+57h+var_B8]; struct NCoreLibrary::TString *
0x14004b810  mov     [rbp+57h+var_B8], rax
0x14004b814  lea     rcx, [rbp+57h+var_80]; this
0x14004b818  call    ?GetSidAsString@TSidUserContext@NSecurityLibrary@@QEBAJAEAVTString@NCoreLibrary@@@Z; NSecurityLibrary::TSidUserContext::GetSidAsString(NCoreLibrary::TString &)
0x14004b81d  mov     rbx, [rbp+57h+var_B8]
0x14004b821  mov     edi, eax
0x14004b823  test    eax, eax
0x14004b825  js      short loc_14004B898
0x14004b827  mov     [rbp+57h+var_B8], r15
0x14004b82b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14004b82f  inc     rsi
0x14004b832  cmp     [rbx+rsi*2], r15w
0x14004b837  jnz     short loc_14004B82F
0x14004b839  mov     r8d, esi; unsigned int
0x14004b83c  lea     rcx, [rbp+57h+var_B8]; this
0x14004b840  mov     rdx, rbx; unsigned __int16 *
0x14004b843  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x14004b848  mov     r10, [rbp+57h+var_C8]
0x14004b84c  mov     ecx, [rbp+57h+var_D0]
0x14004b84f  mov     r9d, [rbp+57h+var_B0.HighPart]
0x14004b853  mov     r8d, [rbp+57h+var_B0.LowPart]
0x14004b857  mov     rax, [r10]
0x14004b85a  mov     rdx, [rbp+57h+var_B8]
0x14004b85e  mov     [rsp+100h+var_E0], ecx
0x14004b862  mov     rcx, r10
0x14004b865  mov     rax, [rax+50h]
0x14004b869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004b86e  mov     edi, eax
0x14004b870  test    eax, eax
0x14004b872  jns     short loc_14004B886
0x14004b874  mov     r8d, eax
0x14004b877  lea     rdx, aLaunchsplwow64; "LaunchSplWOW64 failed. Error 0x%x"
0x14004b87e  mov     rcx, r12; char *
0x14004b881  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004b886  mov     rcx, [rbp+57h+var_B8]; string
0x14004b88a  call    cs:__imp_WindowsDeleteString
0x14004b891  nop     dword ptr [rax+rax+00h]
0x14004b896  jmp     short loc_14004B8AA
0x14004b898  mov     r8d, eax
0x14004b89b  lea     rdx, aGetsidasstring; "GetSidAsString failed. Error 0x%x"
0x14004b8a2  mov     rcx, r12; char *
0x14004b8a5  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004b8aa  mov     rdx, rbx; void *
0x14004b8ad  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x14004b8b2  jmp     short loc_14004B8C6
0x14004b8b4  mov     r8d, eax
0x14004b8b7  lea     rdx, aQuerytoIprints_0; "QueryTo IPrintScanBrokerHandler failed."...
0x14004b8be  mov     rcx, r12; char *
0x14004b8c1  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004b8c6  lea     rcx, [rbp+57h+var_C8]; this
0x14004b8ca  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x14004b8cf  jmp     short loc_14004B8E3
0x14004b8d1  mov     r8d, eax
0x14004b8d4  lea     rdx, aRoactivateinst; "RoActivateInstance for PrintScanBrokerH"...
0x14004b8db  mov     rcx, r12; char *
0x14004b8de  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004b8e3  test    r14d, r14d
0x14004b8e6  js      short loc_14004B8F4
0x14004b8e8  call    cs:__imp_CoUninitialize
0x14004b8ef  nop     dword ptr [rax+rax+00h]
0x14004b8f4  lea     rcx, [rbp+57h+var_C0]; this
0x14004b8f8  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x14004b8fd  jmp     loc_14004B98C
0x14004b902  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14004b906  lea     rdx, [rbp+57h+var_C0]; void **
0x14004b90a  lea     rcx, [rbp+57h+var_C8]; void **
0x14004b90e  mov     [rbp+57h+var_C8], rsi
0x14004b912  mov     [rbp+57h+var_C0], rsi
0x14004b916  call    ?GetUserTokens@@YAJPEAPEAX0@Z; GetUserTokens(void * *,void * *)
0x14004b91b  mov     edi, eax
0x14004b91d  test    eax, eax
0x14004b91f  js      short loc_14004B97A
0x14004b921  mov     rbx, [rbp+57h+var_C0]
0x14004b925  cmp     rbx, rsi
0x14004b928  mov     rdx, rbx
0x14004b92b  cmovz   rdx, r15; Token
0x14004b92f  xor     ecx, ecx; Thread
0x14004b931  call    cs:__imp_SetThreadToken
0x14004b938  nop     dword ptr [rax+rax+00h]
0x14004b93d  test    eax, eax
0x14004b93f  jz      short loc_14004B95A
0x14004b941  mov     r8d, [rbp+57h+var_D0]; unsigned int
0x14004b945  lea     rdx, [rbp+57h+var_B0]; struct _LUID *
0x14004b949  cmp     rbx, rsi
0x14004b94c  cmovz   rbx, r15
0x14004b950  mov     rcx, rbx; hToken
0x14004b953  call    ?InternalCreateSplWowProcess@@YAJPEAXAEAU_LUID@@K@Z; InternalCreateSplWowProcess(void *,_LUID &,ulong)
0x14004b958  jmp     short loc_14004B95F
0x14004b95a  call    GetLastErrorAsHResult
0x14004b95f  mov     rdx, [rbp+57h+var_C8]
0x14004b963  mov     edi, eax
0x14004b965  cmp     rdx, rsi
0x14004b968  cmovz   rdx, r15; Token
0x14004b96c  xor     ecx, ecx; Thread
0x14004b96e  call    cs:__imp_SetThreadToken
0x14004b975  nop     dword ptr [rax+rax+00h]
0x14004b97a  lea     rcx, [rbp+57h+var_C0]
0x14004b97e  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x14004b983  lea     rcx, [rbp+57h+var_C8]
0x14004b987  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x14004b98c  test    edi, edi
0x14004b98e  jns     short loc_14004B9A2
0x14004b990  mov     r8d, edi
0x14004b993  lea     rdx, aFailedToLaunch; "Failed to launch medium IL Splwow64. Er"...
0x14004b99a  mov     rcx, r12; char *
0x14004b99d  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004b9a2  lea     rcx, [rbp+57h+var_80]; this
0x14004b9a6  call    ??1TSidUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TSidUserContext::~TSidUserContext(void)
0x14004b9ab  mov     ecx, edi; this
0x14004b9ad  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x14004b9b2  mov     rcx, [rbp+57h+var_40]
0x14004b9b6  xor     rcx, rsp; StackCookie
0x14004b9b9  call    __security_check_cookie
0x14004b9be  add     rsp, 0D0h
0x14004b9c5  pop     r15
0x14004b9c7  pop     r14
0x14004b9c9  pop     r12
0x14004b9cb  pop     rdi
0x14004b9cc  pop     rsi
0x14004b9cd  pop     rbx
0x14004b9ce  pop     rbp
0x14004b9cf  retn
```
