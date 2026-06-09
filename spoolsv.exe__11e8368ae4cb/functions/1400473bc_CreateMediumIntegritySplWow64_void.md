# CreateMediumIntegritySplWow64(void)

- ea: `0x1400473bc`
- end: `0x140047695`
- name: `?CreateMediumIntegritySplWow64@@YAKXZ`
- size: `729`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140032a70`

## callees

- `0x140007bdc`
- `0x14000c880`
- `0x14000f5f0`
- `0x14000fa4c`
- `0x1400160a0`
- `0x140017ae0`
- `0x14002abc0`
- `0x1400473bc`
- `0x14004769c`
- `0x14004785c`
- `0x140047b98`
- `0x140051bd4`
- `0x140051c2c`
- `0x140051cac`
- `0x140051de4`
- `0x1400590f0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14004749e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14004749e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140047602`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140047639`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140047602`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140047639`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1400474ad`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1400474ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14004756a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14004756a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140047488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140047488`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400475c2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400475c2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140047433`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140047433`

## string_xrefs

- `0x1400473ed`: `CreateMediumIntegritySplWow64`
- `0x140047575`: `GetSidAsString failed. Error 0x%x`
- `0x140047591`: `QueryTo IPrintScanBrokerHandler failed. Error 0x%x`
- `0x1400475ae`: `RoActivateInstance for PrintScanBrokerHandler failed. Error 0x%x`
- `0x140047481`: `Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler`

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
0x1400473bc  push    rbp
0x1400473be  push    rbx
0x1400473bf  push    rsi
0x1400473c0  push    rdi
0x1400473c1  push    r12
0x1400473c3  push    r14
0x1400473c5  push    r15
0x1400473c7  lea     rbp, [rsp-27h]
0x1400473cc  sub     rsp, 0D0h
0x1400473d3  mov     rax, cs:__security_cookie
0x1400473da  xor     rax, rsp
0x1400473dd  mov     [rbp+57h+var_40], rax
0x1400473e1  lea     rcx, [rbp+57h+var_80]; this
0x1400473e5  call    ??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z; NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)
0x1400473ea  mov     edi, [rbp+57h+var_48]
0x1400473ed  lea     r12, aCreatemediumin; "CreateMediumIntegritySplWow64"
0x1400473f4  xor     r15d, r15d
0x1400473f7  test    edi, edi
0x1400473f9  js      loc_140047655
0x1400473ff  lea     r8, [rbp+57h+var_D0]; unsigned int *
0x140047403  mov     [rbp+57h+var_D0], r15d
0x140047407  lea     rdx, [rbp+57h+var_B0]; struct _LUID *
0x14004740b  mov     qword ptr [rbp+57h+var_B0.LowPart], r15
0x14004740f  lea     rcx, [rbp+57h+var_80]; this
0x140047413  call    ?GetAuthenticationIdAndIntegrity@TSidUserContext@NSecurityLibrary@@QEBAJPEAU_LUID@@PEAK@Z; NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(_LUID *,ulong *)
0x140047418  mov     edi, eax
0x14004741a  test    eax, eax
0x14004741c  js      loc_140047655
0x140047422  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140047427  test    eax, eax
0x140047429  jz      loc_1400475D3
0x14004742f  xor     edx, edx; dwCoInit
0x140047431  xor     ecx, ecx; pvReserved
0x140047433  call    cs:__imp_CoInitializeEx
0x140047439  mov     r14d, eax
0x14004743c  mov     eax, 80000000h
0x140047441  lea     ecx, [r14+rax]
0x140047445  test    eax, ecx
0x140047447  jnz     short loc_14004746C
0x140047449  cmp     r14d, 80010106h
0x140047450  jz      short loc_14004746C
0x140047452  mov     r8d, r14d
0x140047455  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed. Error 0x%x"
0x14004745c  mov     rcx, r12; char *
0x14004745f  mov     edi, r14d
0x140047462  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140047467  jmp     loc_140047655
0x14004746c  lea     r9, [rbp+57h+string]; string
0x140047470  mov     [rbp+57h+var_C0], r15
0x140047474  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x140047478  mov     [rbp+57h+string], r15
0x14004747c  mov     edx, 49h ; 'I'; length
0x140047481  lea     rcx, ?RuntimeClass_Windows_Graphics_Internal_Printing_PrintScanBroker_PrintScanBrokerHandler@@3QBGB; "Windows.Graphics.Internal.Printing.Prin"...
0x140047488  call    cs:__imp_WindowsCreateStringReference
0x14004748e  test    eax, eax
0x140047490  jns     short loc_1400474A5
0x140047492  xor     r9d, r9d; lpArguments
0x140047495  xor     r8d, r8d; nNumberOfArguments
0x140047498  mov     ecx, eax; dwExceptionCode
0x14004749a  lea     edx, [r9+1]; dwExceptionFlags
0x14004749e  call    cs:__imp_RaiseException
0x1400474a4  int     3; Trap to Debugger
0x1400474a5  mov     rcx, [rbp+57h+string]
0x1400474a9  lea     rdx, [rbp+57h+var_C0]
0x1400474ad  call    cs:__imp_RoActivateInstance
0x1400474b3  mov     edi, eax
0x1400474b5  test    eax, eax
0x1400474b7  js      loc_1400475AB
0x1400474bd  mov     rcx, [rbp+57h+var_C0]
0x1400474c1  lea     r8, [rbp+57h+var_C8]
0x1400474c5  mov     [rbp+57h+var_C8], r15
0x1400474c9  lea     rdx, _GUID_42964634_70ff_4d1c_8ea0_520607b4c1c3
0x1400474d0  mov     rax, [rcx]
0x1400474d3  mov     rax, [rax]
0x1400474d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400474db  mov     edi, eax
0x1400474dd  test    eax, eax
0x1400474df  js      loc_14004758E
0x1400474e5  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x1400474ec  lea     rdx, [rbp+57h+var_B8]; struct NCoreLibrary::TString *
0x1400474f0  mov     [rbp+57h+var_B8], rax
0x1400474f4  lea     rcx, [rbp+57h+var_80]; this
0x1400474f8  call    ?GetSidAsString@TSidUserContext@NSecurityLibrary@@QEBAJAEAVTString@NCoreLibrary@@@Z; NSecurityLibrary::TSidUserContext::GetSidAsString(NCoreLibrary::TString &)
0x1400474fd  mov     rbx, [rbp+57h+var_B8]
0x140047501  mov     edi, eax
0x140047503  test    eax, eax
0x140047505  js      short loc_140047572
0x140047507  mov     [rbp+57h+var_B8], r15
0x14004750b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14004750f  inc     rsi
0x140047512  cmp     [rbx+rsi*2], r15w
0x140047517  jnz     short loc_14004750F
0x140047519  mov     r8d, esi; unsigned int
0x14004751c  lea     rcx, [rbp+57h+var_B8]; this
0x140047520  mov     rdx, rbx; unsigned __int16 *
0x140047523  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x140047528  mov     r10, [rbp+57h+var_C8]
0x14004752c  mov     ecx, [rbp+57h+var_D0]
0x14004752f  mov     r9d, [rbp+57h+var_B0.HighPart]
0x140047533  mov     r8d, [rbp+57h+var_B0.LowPart]
0x140047537  mov     rax, [r10]
0x14004753a  mov     rdx, [rbp+57h+var_B8]
0x14004753e  mov     [rsp+100h+var_E0], ecx
0x140047542  mov     rcx, r10
0x140047545  mov     rax, [rax+50h]
0x140047549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004754e  mov     edi, eax
0x140047550  test    eax, eax
0x140047552  jns     short loc_140047566
0x140047554  mov     r8d, eax
0x140047557  lea     rdx, aLaunchsplwow64; "LaunchSplWOW64 failed. Error 0x%x"
0x14004755e  mov     rcx, r12; char *
0x140047561  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140047566  mov     rcx, [rbp+57h+var_B8]; string
0x14004756a  call    cs:__imp_WindowsDeleteString
0x140047570  jmp     short loc_140047584
0x140047572  mov     r8d, eax
0x140047575  lea     rdx, aGetsidasstring; "GetSidAsString failed. Error 0x%x"
0x14004757c  mov     rcx, r12; char *
0x14004757f  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140047584  mov     rdx, rbx; void *
0x140047587  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x14004758c  jmp     short loc_1400475A0
0x14004758e  mov     r8d, eax
0x140047591  lea     rdx, aQuerytoIprints_0; "QueryTo IPrintScanBrokerHandler failed."...
0x140047598  mov     rcx, r12; char *
0x14004759b  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400475a0  lea     rcx, [rbp+57h+var_C8]; this
0x1400475a4  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x1400475a9  jmp     short loc_1400475BD
0x1400475ab  mov     r8d, eax
0x1400475ae  lea     rdx, aRoactivateinst; "RoActivateInstance for PrintScanBrokerH"...
0x1400475b5  mov     rcx, r12; char *
0x1400475b8  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400475bd  test    r14d, r14d
0x1400475c0  js      short loc_1400475C8
0x1400475c2  call    cs:__imp_CoUninitialize
0x1400475c8  lea     rcx, [rbp+57h+var_C0]; this
0x1400475cc  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x1400475d1  jmp     short loc_140047651
0x1400475d3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400475d7  lea     rdx, [rbp+57h+var_C0]; void **
0x1400475db  lea     rcx, [rbp+57h+var_C8]; void **
0x1400475df  mov     [rbp+57h+var_C8], rsi
0x1400475e3  mov     [rbp+57h+var_C0], rsi
0x1400475e7  call    ?GetUserTokens@@YAJPEAPEAX0@Z; GetUserTokens(void * *,void * *)
0x1400475ec  mov     edi, eax
0x1400475ee  test    eax, eax
0x1400475f0  js      short loc_14004763F
0x1400475f2  mov     rbx, [rbp+57h+var_C0]
0x1400475f6  cmp     rbx, rsi
0x1400475f9  mov     rdx, rbx
0x1400475fc  cmovz   rdx, r15; Token
0x140047600  xor     ecx, ecx; Thread
0x140047602  call    cs:__imp_SetThreadToken
0x140047608  test    eax, eax
0x14004760a  jz      short loc_140047625
0x14004760c  mov     r8d, [rbp+57h+var_D0]; unsigned int
0x140047610  lea     rdx, [rbp+57h+var_B0]; struct _LUID *
0x140047614  cmp     rbx, rsi
0x140047617  cmovz   rbx, r15
0x14004761b  mov     rcx, rbx; hToken
0x14004761e  call    ?InternalCreateSplWowProcess@@YAJPEAXAEAU_LUID@@K@Z; InternalCreateSplWowProcess(void *,_LUID &,ulong)
0x140047623  jmp     short loc_14004762A
0x140047625  call    GetLastErrorAsHResult
0x14004762a  mov     rdx, [rbp+57h+var_C8]
0x14004762e  mov     edi, eax
0x140047630  cmp     rdx, rsi
0x140047633  cmovz   rdx, r15; Token
0x140047637  xor     ecx, ecx; Thread
0x140047639  call    cs:__imp_SetThreadToken
0x14004763f  lea     rcx, [rbp+57h+var_C0]
0x140047643  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x140047648  lea     rcx, [rbp+57h+var_C8]
0x14004764c  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleNT@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(void)
0x140047651  test    edi, edi
0x140047653  jns     short loc_140047667
0x140047655  mov     r8d, edi
0x140047658  lea     rdx, aFailedToLaunch; "Failed to launch medium IL Splwow64. Er"...
0x14004765f  mov     rcx, r12; char *
0x140047662  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140047667  lea     rcx, [rbp+57h+var_80]; this
0x14004766b  call    ??1TSidUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TSidUserContext::~TSidUserContext(void)
0x140047670  mov     ecx, edi; this
0x140047672  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x140047677  mov     rcx, [rbp+57h+var_40]
0x14004767b  xor     rcx, rsp; StackCookie
0x14004767e  call    __security_check_cookie
0x140047683  add     rsp, 0D0h
0x14004768a  pop     r15
0x14004768c  pop     r14
0x14004768e  pop     r12
0x140047690  pop     rdi
0x140047691  pop     rsi
0x140047692  pop     rbx
0x140047693  pop     rbp
0x140047694  retn
```
