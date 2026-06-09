# ComputeService::Vmwp::Details::StartWorkerProcess(_GUID const &,void *,void *,ComputeService::Vmwp::StartWorkerProcessContext const &)

- ea: `0x1400b6a4c`
- end: `0x1400b6f27`
- name: `?StartWorkerProcess@Details@Vmwp@ComputeService@@YA?AUWorkerProcessContext@23@AEBU_GUID@@PEAX1AEBUStartWorkerProcessContext@23@@Z`
- size: `1243`
- prototype: `struct ComputeService::Vmwp::WorkerProcessContext __high(const struct _GUID *, void *, void *, const struct ComputeService::Vmwp::StartWorkerProcessContext *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14007ff94`

## callees

- `0x140017040`
- `0x140018d54`
- `0x14003b540`
- `0x1400427e0`
- `0x1400454c4`
- `0x140057fec`
- `0x140060394`
- `0x140080180`
- `0x1400b1dd0`
- `0x1400b6a4c`
- `0x1400b6f84`
- `0x1400b6fa8`
- `0x1400b7028`
- `0x1400b710c`
- `0x1400b7410`
- `0x1400b7450`
- `0x1400b74d0`
- `0x1400b7604`
- `0x1400c4154`
- `0x1401213d4`
- `0x14012144c`
- `0x1401332f0`
- `0x140134048`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400b6ada`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400b6ada`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1400b6dd2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1400b6dd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400b6bcf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400b6bcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b6e91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400b6e91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400b6ef4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400b6ef4`
- `USERENV!DeleteAppContainerProfile` at `0x1400b6eae`
- `USERENV!DeleteAppContainerProfile` at `0x1400b6eae`

## string_xrefs

- `0x1400b6bf8`: `onecore\vm\common\vml\VmRegistry.h`
- `0x1400b6aa8`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x1400b6de9`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
struct _GUID *__fastcall ComputeService::Vmwp::Details::StartWorkerProcess(
        struct _GUID *a1,
        struct _GUID *a2,
        void *a3,
        __int64 a4,
        __int64 a5)
{
  char *v9; // rbx
  __int128 v10; // xmm0
  DWORD dwCreationFlags; // r15d
  unsigned int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rdx
  unsigned int v15; // edi
  __int64 *AppContainerValue; // rdi
  WCHAR *v17; // r8
  const WCHAR *v18; // rdx
  const char *v19; // r9
  void *v20; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  struct IUnknown **phkResultb; // [rsp+20h] [rbp-E0h]
  char v25[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+64h] [rbp-9Ch] BYREF
  int v27; // [rsp+68h] [rbp-98h]
  struct _GUID *v28; // [rsp+70h] [rbp-90h]
  char *v29; // [rsp+78h] [rbp-88h]
  struct _GUID *v30; // [rsp+80h] [rbp-80h]
  struct _PROCESS_INFORMATION *p_ProcessInformation; // [rsp+88h] [rbp-78h]
  char v32; // [rsp+90h] [rbp-70h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v34[7]; // [rsp+B0h] [rbp-50h] BYREF
  int v35; // [rsp+E8h] [rbp-18h]
  char v36; // [rsp+ECh] [rbp-14h]
  __int16 v37; // [rsp+EDh] [rbp-13h]
  char v38; // [rsp+EFh] [rbp-11h]
  __int64 v39; // [rsp+F0h] [rbp-10h] BYREF
  int v40; // [rsp+F8h] [rbp-8h]
  char v41; // [rsp+FCh] [rbp-4h]
  __int16 v42; // [rsp+FDh] [rbp-3h]
  char v43; // [rsp+FFh] [rbp-1h]
  __int64 v44; // [rsp+100h] [rbp+0h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+110h] [rbp+10h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+130h] [rbp+30h] BYREF
  __int64 v47; // [rsp+198h] [rbp+98h]
  HKEY hKey; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned int v49; // [rsp+1A8h] [rbp+A8h] BYREF
  unsigned int v50; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v51; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v52; // [rsp+1C8h] [rbp+C8h]
  unsigned __int64 v53; // [rsp+1D0h] [rbp+D0h]
  LPWSTR lpCommandLine[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v55; // [rsp+1E8h] [rbp+E8h]
  _BYTE v56[24]; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v57; // [rsp+210h] [rbp+110h]
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  v28 = a1;
  v27 = 0;
  if ( !(unsigned __int8)HviIsAnyHypervisorPresent() )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)0xC0351000LL,
      phkResult);
  *(_QWORD *)&EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)&EventAttributes.bInheritHandle = 1;
  v9 = (char *)CreateEventW(&EventAttributes, 0, 0, 0);
  v29 = v9;
  v10 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  *(double *)&v10 = std::wstring::_Construct_empty(&v51);
  *(_OWORD *)lpCommandLine = v10;
  v55 = 0;
  std::wstring::_Construct_empty(lpCommandLine);
  ComputeService::Vmwp::Details::CreateWorkerProcessCmd(a2, v9, &v51, lpCommandLine);
  dwCreationFlags = 524296;
  v26 = 524296;
  ComputeService::Vmwp::ProcessAttributes::AttributeListOptions::AttributeListOptions(
    (ComputeService::Vmwp::ProcessAttributes::AttributeListOptions *)v34,
    a2);
  v34[5] = v9;
  v34[6] = a4;
  if ( (*(_BYTE *)a5 & 1) != 0 )
  {
    v35 = 2;
    v36 = 1;
    v37 = *(_WORD *)((char *)&hKey + 5);
    v38 = HIBYTE(hKey);
    dwCreationFlags = 786440;
    v26 = 786440;
  }
  hKey = 0;
  v12 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
          0,
          0x20019u,
          &hKey);
  if ( v12 )
  {
    if ( v12 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
        (const char *)v12,
        phkResulta);
    v13 = 1;
  }
  else
  {
    v49 = 0;
    if ( (unsigned int)Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&hKey, L"RelaxWorkerSigning", &v49) && v49 )
    {
      LOBYTE(v14) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_HcsSecurityMitigation>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_HcsSecurityMitigation>::GetImpl'::`2'::impl,
        v14);
      v34[0] = 0x1111031111111305LL;
      v34[1] = 0x10000000000LL;
    }
    v50 = 0;
    v13 = 1;
    if ( (unsigned int)Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&hKey, L"WorkerAppContainer", &v50) )
      v13 = v50;
  }
  v34[2] = 0;
  v34[3] = 0x10000000000LL;
  if ( *(_DWORD *)(a5 + 4) )
    v13 = *(_DWORD *)(a5 + 4);
  v15 = v13 - 2;
  if ( v15 )
  {
    if ( v15 != 1 )
      goto LABEL_22;
    v40 = 1;
    v41 = 1;
    v42 = *(_WORD *)((char *)&hKey + 5);
    v43 = HIBYTE(hKey);
  }
  AppContainerValue = (__int64 *)ComputeService::Vmwp::ProcessAttributes::GetAppContainerValue(&v50, v44);
  if ( &v39 != AppContainerValue )
  {
    wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&long FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::reset(
      &v39,
      *AppContainerValue);
    *AppContainerValue = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&long FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&long FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v50);
LABEL_22:
  ComputeService::Vmwp::ProcessAttributes::AttributeList::AttributeList(
    (ComputeService::Vmwp::ProcessAttributes::AttributeList *)v56,
    (struct ComputeService::Vmwp::ProcessAttributes::AttributeListOptions *)v34);
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 112;
  v47 = v57;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v17 = (WCHAR *)lpCommandLine;
  if ( *((_QWORD *)&v55 + 1) > 7u )
    v17 = lpCommandLine[0];
  if ( v52 )
  {
    v18 = (const WCHAR *)&v51;
    if ( v53 > 7 )
      v18 = (const WCHAR *)v51;
  }
  else
  {
    v18 = 0;
  }
  if ( !CreateProcessAsUserW(a3, v18, v17, 0, 0, 1, dwCreationFlags, 0, 0, &StartupInfo, &ProcessInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      v19);
  ComputeService::Diagnostics::TraceProvider::Vmwp_ProcessCreated<_GUID const &,unsigned long &>(a2, &v26);
  v30 = a2;
  p_ProcessInformation = &ProcessInformation;
  v32 = 1;
  *(_QWORD *)&a1[1].Data1 = 0;
  *(_QWORD *)a1[1].Data4 = 0;
  a1[2].Data1 = -1;
  v27 = 1;
  ComputeService::Vmwp::Details::WaitForWorkerProcessInterface(
    (ComputeService::Vmwp::Details *)a2,
    ProcessInformation.hProcess,
    v9,
    &a1[1],
    phkResultb);
  v25[0] = 1;
  ComputeService::Diagnostics::TraceProvider::Vmwp_RegisteredComInterface<_GUID const &,bool>(a2, v25);
  *a1 = *a2;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a1[1].Data4,
    ProcessInformation.hProcess);
  ProcessInformation.hProcess = 0;
  if ( ProcessInformation.hThread )
    wil::details::CloseHandle((wil::details *)ProcessInformation.hThread, v20);
  std::vector<enum gsl::byte>::_Tidy(v56);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v39 )
    DeleteAppContainerProfile(v44);
  Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&v44);
  wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&long FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&long FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(&v39);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpCommandLine);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&v51);
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  return a1;
}

```

## disassembly

```asm
0x1400b6a4c  push    rbp
0x1400b6a4e  push    rbx
0x1400b6a4f  push    rsi
0x1400b6a50  push    rdi
0x1400b6a51  push    r12
0x1400b6a53  push    r13
0x1400b6a55  push    r14
0x1400b6a57  push    r15
0x1400b6a59  lea     rbp, [rsp-128h]
0x1400b6a61  sub     rsp, 228h
0x1400b6a68  mov     rax, cs:__security_cookie
0x1400b6a6f  xor     rax, rsp
0x1400b6a72  mov     [rbp+160h+var_48], rax
0x1400b6a79  mov     rdi, r9
0x1400b6a7c  mov     r13, r8
0x1400b6a7f  mov     r14, rdx
0x1400b6a82  mov     rsi, rcx
0x1400b6a85  mov     [rsp+260h+var_1F0], rcx
0x1400b6a8a  xor     r15d, r15d
0x1400b6a8d  mov     [rsp+260h+var_1F8], r15d
0x1400b6a92  call    HviIsAnyHypervisorPresent
0x1400b6a97  test    al, al
0x1400b6a99  jnz     short loc_1400B6ABA
0x1400b6a9b  mov     rcx, [rbp+168h]; this
0x1400b6aa2  mov     r9d, 0C0351000h; char *
0x1400b6aa8  lea     r8, aOnecoreVmCompu_62; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x1400b6aaf  mov     edx, 1ABh; void *
0x1400b6ab4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b6aba  mov     qword ptr [rbp+160h+EventAttributes.nLength], 18h
0x1400b6ac2  mov     [rbp+160h+EventAttributes.lpSecurityDescriptor], r15
0x1400b6ac6  mov     qword ptr [rbp+160h+EventAttributes.bInheritHandle], 1
0x1400b6ace  xor     r9d, r9d; lpName
0x1400b6ad1  xor     r8d, r8d; bInitialState
0x1400b6ad4  xor     edx, edx; bManualReset
0x1400b6ad6  lea     rcx, [rbp+160h+EventAttributes]; lpEventAttributes
0x1400b6ada  call    cs:__imp_CreateEventW
0x1400b6ae1  nop     dword ptr [rax+rax+00h]
0x1400b6ae6  mov     rbx, rax
0x1400b6ae9  mov     [rsp+260h+var_1E8], rax
0x1400b6aee  xorps   xmm0, xmm0
0x1400b6af1  movups  [rbp+160h+var_A8], xmm0
0x1400b6af8  mov     [rbp+160h+var_98], r15
0x1400b6aff  mov     [rbp+160h+var_90], r15
0x1400b6b06  lea     rcx, [rbp+160h+var_A8]
0x1400b6b0d  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1400b6b12  nop
0x1400b6b13  movups  xmmword ptr [rbp+160h+lpCommandLine], xmm0
0x1400b6b1a  xorps   xmm1, xmm1
0x1400b6b1d  movdqu  [rbp+160h+var_78], xmm1
0x1400b6b25  lea     rcx, [rbp+160h+lpCommandLine]
0x1400b6b2c  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1400b6b31  nop
0x1400b6b32  lea     r9, [rbp+160h+lpCommandLine]
0x1400b6b39  lea     r8, [rbp+160h+var_A8]
0x1400b6b40  mov     rdx, rbx
0x1400b6b43  mov     rcx, r14
0x1400b6b46  call    ?CreateWorkerProcessCmd@Details@Vmwp@ComputeService@@YAXAEBU_GUID@@PEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; ComputeService::Vmwp::Details::CreateWorkerProcessCmd(_GUID const &,void *,std::wstring &,std::wstring &)
0x1400b6b4b  mov     r15d, 80008h
0x1400b6b51  mov     [rsp+260h+var_1FC], r15d
0x1400b6b56  mov     rdx, r14; struct _GUID *
0x1400b6b59  lea     rcx, [rbp+160h+var_1B0]; this
0x1400b6b5d  call    ??0AttributeListOptions@ProcessAttributes@Vmwp@ComputeService@@QEAA@AEBU_GUID@@@Z; ComputeService::Vmwp::ProcessAttributes::AttributeListOptions::AttributeListOptions(_GUID const &)
0x1400b6b62  nop
0x1400b6b63  mov     [rbp+160h+var_188], rbx
0x1400b6b67  mov     [rbp+160h+var_180], rdi
0x1400b6b6b  mov     r12, [rbp+160h+arg_20]
0x1400b6b72  test    byte ptr [r12], 1
0x1400b6b77  jz      short loc_1400B6BA3
0x1400b6b79  mov     [rbp+160h+var_178], 2
0x1400b6b80  mov     [rbp+160h+var_174], 1
0x1400b6b84  movzx   eax, word ptr [rbp+160h+hKey+5]
0x1400b6b8b  mov     [rbp+160h+var_173], ax
0x1400b6b8f  mov     al, byte ptr [rbp+160h+hKey+7]
0x1400b6b95  mov     [rbp+160h+var_171], al
0x1400b6b98  mov     r15d, 0C0008h
0x1400b6b9e  mov     [rsp+260h+var_1FC], r15d
0x1400b6ba3  xor     edi, edi
0x1400b6ba5  mov     [rbp+0A0h], rdi
0x1400b6bac  lea     rax, [rbp+160h+hKey]
0x1400b6bb3  mov     [rsp+260h+phkResult], rax; unsigned int
0x1400b6bb8  mov     r9d, 20019h; samDesired
0x1400b6bbe  xor     r8d, r8d; ulOptions
0x1400b6bc1  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400b6bc8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400b6bcf  call    cs:__imp_RegOpenKeyExW
0x1400b6bd6  nop     dword ptr [rax+rax+00h]
0x1400b6bdb  mov     rcx, 10000000000h
0x1400b6be5  test    eax, eax
0x1400b6be7  jz      short loc_1400B6C14
0x1400b6be9  cmp     eax, 2
0x1400b6bec  jz      short loc_1400B6C0A
0x1400b6bee  mov     rcx, [rbp+168h]; this
0x1400b6bf5  mov     r9d, eax; char *
0x1400b6bf8  lea     r8, aOnecoreVmCommo_65; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x1400b6bff  mov     edx, 1F9h; void *
0x1400b6c04  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b6c0a  mov     edi, 1
0x1400b6c0f  jmp     loc_1400B6CA2
0x1400b6c14  mov     [rbp+160h+var_B8], edi
0x1400b6c1a  lea     r8, [rbp+160h+var_B8]; unsigned int *
0x1400b6c21  lea     rdx, aRelaxworkersig; "RelaxWorkerSigning"
0x1400b6c28  lea     rcx, [rbp+160h+hKey]; this
0x1400b6c2f  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x1400b6c34  test    eax, eax
0x1400b6c36  jz      short loc_1400B6C6A
0x1400b6c38  cmp     [rbp+160h+var_B8], edi
0x1400b6c3e  jbe     short loc_1400B6C6A
0x1400b6c40  mov     dl, 1
0x1400b6c42  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HcsSecurityMitigation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HcsSecurityMitigation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HcsSecurityMitigation> `wil::Feature<__WilFeatureTraits_Feature_HcsSecurityMitigation>::GetImpl(void)'::`2'::impl
0x1400b6c49  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_HcsSecurityMitigation@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HcsSecurityMitigation>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400b6c4e  mov     rax, 1111031111111305h
0x1400b6c58  mov     [rbp+160h+var_1B0], rax
0x1400b6c5c  mov     rax, 10000000000h
0x1400b6c66  mov     [rbp+160h+var_1A8], rax
0x1400b6c6a  mov     [rbp+160h+var_B0], edi
0x1400b6c70  mov     edi, 1
0x1400b6c75  lea     r8, [rbp+160h+var_B0]; unsigned int *
0x1400b6c7c  lea     rdx, aWorkerappconta; "WorkerAppContainer"
0x1400b6c83  lea     rcx, [rbp+160h+hKey]; this
0x1400b6c8a  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x1400b6c8f  test    eax, eax
0x1400b6c91  cmovnz  edi, [rbp+160h+var_B0]
0x1400b6c98  mov     rcx, 10000000000h
0x1400b6ca2  mov     [rbp+160h+var_1A0], 0
0x1400b6caa  mov     [rbp+160h+var_198], rcx
0x1400b6cae  cmp     dword ptr [r12+4], 0
0x1400b6cb4  cmovnz  edi, [r12+4]
0x1400b6cba  sub     edi, 2
0x1400b6cbd  jz      short loc_1400B6CDF
0x1400b6cbf  cmp     edi, 1
0x1400b6cc2  jnz     short loc_1400B6D1A
0x1400b6cc4  mov     [rbp+160h+var_168], edi
0x1400b6cc7  mov     [rbp+160h+var_164], dil
0x1400b6ccb  movzx   eax, word ptr [rbp+160h+hKey+5]
0x1400b6cd2  mov     [rbp+160h+var_163], ax
0x1400b6cd6  mov     al, byte ptr [rbp+160h+hKey+7]
0x1400b6cdc  mov     [rbp+160h+var_161], al
0x1400b6cdf  mov     rdx, [rbp+160h+var_160]
0x1400b6ce3  lea     rcx, [rbp+160h+var_B0]
0x1400b6cea  call    ?GetAppContainerValue@ProcessAttributes@Vmwp@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@P6AJPEAU1@@Z$1?FreeWorkerProcessCapabilities@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; ComputeService::Vmwp::ProcessAttributes::GetAppContainerValue(ushort const *)
0x1400b6cef  mov     rdi, rax
0x1400b6cf2  lea     rax, [rbp+160h+var_170]
0x1400b6cf6  cmp     rax, rdi
0x1400b6cf9  jz      short loc_1400B6D0E
0x1400b6cfb  mov     rdx, [rdi]
0x1400b6cfe  lea     rcx, [rbp+160h+var_170]
0x1400b6d02  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@P6AJPEAU1@@Z$1?FreeWorkerProcessCapabilities@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SECURITY_CAPABILITIES@@@Z; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::reset(_SECURITY_CAPABILITIES *)
0x1400b6d07  mov     qword ptr [rdi], 0
0x1400b6d0e  lea     rcx, [rbp+160h+var_B0]
0x1400b6d15  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@P6AJPEAU1@@Z$1?FreeWorkerProcessCapabilities@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x1400b6d1a  lea     rdx, [rbp+160h+var_1B0]; struct ComputeService::Vmwp::ProcessAttributes::AttributeListOptions *
0x1400b6d1e  lea     rcx, [rbp+160h+var_68]; this
0x1400b6d25  call    ??0AttributeList@ProcessAttributes@Vmwp@ComputeService@@QEAA@AEAUAttributeListOptions@123@@Z; ComputeService::Vmwp::ProcessAttributes::AttributeList::AttributeList(ComputeService::Vmwp::ProcessAttributes::AttributeListOptions &)
0x1400b6d2a  nop
0x1400b6d2b  xor     edx, edx; Val
0x1400b6d2d  lea     r8d, [rdx+64h]; Size
0x1400b6d31  lea     rcx, [rbp+160h+StartupInfo+4]; void *
0x1400b6d35  call    memset_0
0x1400b6d3a  mov     [rbp+160h+StartupInfo.cb], 70h ; 'p'
0x1400b6d41  mov     rax, [rbp+160h+var_50]
0x1400b6d48  mov     [rbp+160h+var_C8], rax
0x1400b6d4f  xorps   xmm0, xmm0
0x1400b6d52  xor     eax, eax
0x1400b6d54  movups  xmmword ptr [rbp+160h+ProcessInformation.hProcess], xmm0
0x1400b6d58  mov     qword ptr [rbp+160h+ProcessInformation.dwProcessId], rax
0x1400b6d5c  lea     r8, [rbp+160h+lpCommandLine]
0x1400b6d63  cmp     qword ptr [rbp+160h+var_78+8], 7
0x1400b6d6b  cmova   r8, [rbp+160h+lpCommandLine]; lpCommandLine
0x1400b6d73  xor     r12d, r12d
0x1400b6d76  cmp     [rbp+160h+var_98], r12
0x1400b6d7d  jz      short loc_1400B6D98
0x1400b6d7f  lea     rdx, [rbp+160h+var_A8]
0x1400b6d86  cmp     [rbp+160h+var_90], 7
0x1400b6d8e  cmova   rdx, qword ptr [rbp+160h+var_A8]
0x1400b6d96  jmp     short loc_1400B6D9B
0x1400b6d98  mov     rdx, r12; lpApplicationName
0x1400b6d9b  lea     rax, [rbp+160h+ProcessInformation]
0x1400b6d9f  mov     [rsp+260h+lpProcessInformation], rax; lpProcessInformation
0x1400b6da4  lea     rax, [rbp+160h+StartupInfo]
0x1400b6da8  mov     [rsp+260h+lpStartupInfo], rax; lpStartupInfo
0x1400b6dad  mov     [rsp+260h+lpCurrentDirectory], r12; lpCurrentDirectory
0x1400b6db2  mov     [rsp+260h+lpEnvironment], r12; lpEnvironment
0x1400b6db7  mov     [rsp+260h+dwCreationFlags], r15d; dwCreationFlags
0x1400b6dbc  mov     r15d, 1
0x1400b6dc2  mov     [rsp+260h+bInheritHandles], r15d; bInheritHandles
0x1400b6dc7  mov     [rsp+260h+phkResult], r12; struct IUnknown **
0x1400b6dcc  xor     r9d, r9d; lpProcessAttributes
0x1400b6dcf  mov     rcx, r13; hToken
0x1400b6dd2  call    cs:__imp_CreateProcessAsUserW
0x1400b6dd9  nop     dword ptr [rax+rax+00h]
0x1400b6dde  mov     rcx, [rbp+168h]; this
0x1400b6de5  test    eax, eax
0x1400b6de7  jnz     short loc_1400B6DFB
0x1400b6de9  lea     r8, aOnecoreVmCompu_62; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x1400b6df0  mov     edx, 232h; void *
0x1400b6df5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b6dfb  lea     rdx, [rsp+260h+var_1FC]
0x1400b6e00  mov     rcx, r14
0x1400b6e03  call    ??$Vmwp_ProcessCreated@AEBU_GUID@@AEAK@TraceProvider@Diagnostics@ComputeService@@SAXAEBU_GUID@@AEAK@Z; ComputeService::Diagnostics::TraceProvider::Vmwp_ProcessCreated<_GUID const &,ulong &>(_GUID const &,ulong &)
0x1400b6e08  mov     [rbp+160h+var_1E0], r14
0x1400b6e0c  lea     rax, [rbp+160h+ProcessInformation]
0x1400b6e10  mov     [rbp+160h+var_1D8], rax
0x1400b6e14  mov     [rbp+160h+var_1D0], r15b
0x1400b6e18  lea     r9, [rsi+10h]; void *
0x1400b6e1c  mov     [r9], r12
0x1400b6e1f  mov     [rsi+18h], r12
0x1400b6e23  mov     dword ptr [rsi+20h], 0FFFFFFFFh
0x1400b6e2a  mov     [rsp+260h+var_1F8], r15d
0x1400b6e2f  mov     r8, rbx; void *
0x1400b6e32  mov     rdx, [rbp+160h+ProcessInformation.hProcess]; hProcess
0x1400b6e36  mov     rcx, r14; this
0x1400b6e39  call    ?WaitForWorkerProcessInterface@Details@Vmwp@ComputeService@@YAXAEBU_GUID@@PEAX1PEAPEAUIUnknown@@@Z; ComputeService::Vmwp::Details::WaitForWorkerProcessInterface(_GUID const &,void *,void *,IUnknown * *)
0x1400b6e3e  mov     [rsp+260h+var_200], r15b
0x1400b6e43  lea     rdx, [rsp+260h+var_200]
0x1400b6e48  mov     rcx, r14
0x1400b6e4b  call    ??$Vmwp_RegisteredComInterface@AEBU_GUID@@_N@TraceProvider@Diagnostics@ComputeService@@SAXAEBU_GUID@@$$QEA_N@Z; ComputeService::Diagnostics::TraceProvider::Vmwp_RegisteredComInterface<_GUID const &,bool>(_GUID const &,bool &&)
0x1400b6e50  movups  xmm0, xmmword ptr [r14]
0x1400b6e54  movdqu  xmmword ptr [rsi], xmm0
0x1400b6e58  mov     rdx, [rbp+160h+ProcessInformation.hProcess]
0x1400b6e5c  lea     rcx, [rsi+18h]
0x1400b6e60  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400b6e65  mov     [rbp+160h+ProcessInformation.hProcess], r12
0x1400b6e69  mov     rcx, [rbp+160h+ProcessInformation.hThread]; this
0x1400b6e6d  test    rcx, rcx
0x1400b6e70  jz      short loc_1400B6E78
0x1400b6e72  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400b6e77  nop
0x1400b6e78  lea     rcx, [rbp+160h+var_68]
0x1400b6e7f  call    ?_Tidy@?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@AEAAXXZ; std::vector<gsl::byte>::_Tidy(void)
0x1400b6e84  nop
0x1400b6e85  mov     rcx, [rbp+160h+hKey]; hKey
0x1400b6e8c  test    rcx, rcx
0x1400b6e8f  jz      short loc_1400B6EA4
0x1400b6e91  call    cs:__imp_RegCloseKey
0x1400b6e98  nop     dword ptr [rax+rax+00h]
0x1400b6e9d  mov     [rbp+160h+hKey], r12
0x1400b6ea4  cmp     [rbp+160h+var_170], r12
0x1400b6ea8  jz      short loc_1400B6EBA
0x1400b6eaa  mov     rcx, [rbp+160h+var_160]
0x1400b6eae  call    cs:__imp_DeleteAppContainerProfile
0x1400b6eb5  nop     dword ptr [rax+rax+00h]
0x1400b6eba  lea     rcx, [rbp+160h+var_160]
0x1400b6ebe  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400b6ec3  lea     rcx, [rbp+160h+var_170]
0x1400b6ec7  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@P6AJPEAU1@@Z$1?FreeWorkerProcessCapabilities@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,long (*)(_SECURITY_CAPABILITIES *),&FreeWorkerProcessCapabilities(_SECURITY_CAPABILITIES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)
0x1400b6ecc  nop
0x1400b6ecd  lea     rcx, [rbp+160h+lpCommandLine]; this
0x1400b6ed4  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400b6ed9  nop
0x1400b6eda  lea     rcx, [rbp+160h+var_A8]; this
0x1400b6ee1  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400b6ee6  nop
0x1400b6ee7  lea     rcx, [rbx-1]
0x1400b6eeb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1400b6eef  ja      short loc_1400B6F00
0x1400b6ef1  mov     rcx, rbx; hObject
0x1400b6ef4  call    cs:__imp_CloseHandle
0x1400b6efb  nop     dword ptr [rax+rax+00h]
0x1400b6f00  mov     rax, rsi
0x1400b6f03  mov     rcx, [rbp+160h+var_48]
0x1400b6f0a  xor     rcx, rsp; StackCookie
0x1400b6f0d  call    __security_check_cookie
0x1400b6f12  add     rsp, 228h
0x1400b6f19  pop     r15
0x1400b6f1b  pop     r14
0x1400b6f1d  pop     r13
0x1400b6f1f  pop     r12
0x1400b6f21  pop     rdi
0x1400b6f22  pop     rsi
0x1400b6f23  pop     rbx
0x1400b6f24  pop     rbp
0x1400b6f25  retn
```
