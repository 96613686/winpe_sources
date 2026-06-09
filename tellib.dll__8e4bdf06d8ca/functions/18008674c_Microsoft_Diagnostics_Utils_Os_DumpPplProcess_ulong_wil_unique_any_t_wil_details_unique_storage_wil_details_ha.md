# Microsoft::Diagnostics::Utils::Os::DumpPplProcess(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ulong,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,unsigned __int64)

- ea: `0x18008674c`
- end: `0x180086c35`
- name: `?DumpPplProcess@Os@Utils@Diagnostics@Microsoft@@SAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_K@Z`
- size: `1257`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e7680`

## callees

- `0x18001d160`
- `0x180026ecc`
- `0x180032718`
- `0x180034d94`
- `0x180035698`
- `0x180048ff4`
- `0x1800495cc`
- `0x180054ca4`
- `0x180058f54`
- `0x18005a614`
- `0x18005b050`
- `0x18007fae8`
- `0x18008674c`
- `0x180086c3c`
- `0x180086e5c`
- `0x180086e78`
- `0x180086f40`
- `0x180087044`
- `0x180089080`
- `0x1800890b4`
- `0x18008bd1c`
- `0x180112c8c`
- `0x18012de40`
- `0x18012eb08`
- `0x1801b2804`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x180086a35`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x180086a56`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x180086a35`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x180086a56`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x1800869f3`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x180086a14`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x1800869f3`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x180086a14`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180086b7b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180086b7b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180086ae4`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180086ae4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180086911`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180086911`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800867ef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800867ef`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1800868f3`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1800868f3`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18008689b`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18008689b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::DumpPplProcess(
        unsigned int a1,
        _QWORD *a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned int a5)
{
  __int64 v9; // rax
  HANDLE v10; // rbx
  const char *v11; // r9
  DWORD LastError; // ebx
  wil::details *v13; // rdi
  const char *v14; // r9
  __int64 v15; // rdx
  WCHAR *v16; // rcx
  UINT SystemWow64Directory2W; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  LPWSTR *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  BOOL v30; // ebx
  const char *v31; // r9
  HANDLE hProcess; // rbx
  void *v33; // rdx
  DWORD v34; // eax
  const char *v35; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  _WORD v39[2]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD ExitCode[3]; // [rsp+54h] [rbp-ACh] BYREF
  __int128 v41; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v42[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h]
  wil::details *v44; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v45[2]; // [rsp+88h] [rbp-78h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+98h] [rbp-68h] BYREF
  HANDLE v47; // [rsp+B0h] [rbp-50h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v49[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v51; // [rsp+148h] [rbp+48h]
  _BYTE v52[16]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v53[240]; // [rsp+160h] [rbp+60h] BYREF
  LPWSTR lpBuffer[2]; // [rsp+250h] [rbp+150h] BYREF
  UINT uSize[2]; // [rsp+260h] [rbp+160h]
  unsigned __int64 v56; // [rsp+268h] [rbp+168h]
  _BYTE v57[32]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
  v44 = 0;
  _try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAA_NW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &v44,
    0,
    0,
    &SecurityAttributes,
    0);
  v9 = std::wstring::wstring((__int64)v57, a4);
  if ( *(_QWORD *)(v9 + 24) > 7u )
    v9 = *(_QWORD *)v9;
  v10 = CreateFileW((LPCWSTR)v9, 0x40000000u, 0, &SecurityAttributes, 1u, 0, 0);
  v47 = v10;
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
  if ( (((unsigned __int64)v10 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v13 = v44;
    v49[0] = v44;
    v49[1] = v10;
    *(_QWORD *)&v41 = v49;
    v41 = *(_OWORD *)gsl::span<void * const,-1>::span<void * const,-1>(v45, &v41);
    Microsoft::Diagnostics::Utils::Os::BuildInheritHandleAttributeList(v42, &v41);
    v39[0] = 0;
    std::wstring::wstring(lpBuffer, 260, 0);
    if ( !(unsigned int)IsWow64Process2(*a2, v39, 0) )
    {
      v15 = 1112;
LABEL_7:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v15,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                    v14);
LABEL_37:
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpBuffer);
      Microsoft::Diagnostics::Utils::Os::AttributeListAndMemory::~AttributeListAndMemory((Microsoft::Diagnostics::Utils::Os::AttributeListAndMemory *)v42);
      goto LABEL_38;
    }
    v16 = (WCHAR *)lpBuffer;
    if ( v39[0] )
    {
      if ( v56 > 7 )
        v16 = lpBuffer[0];
      SystemWow64Directory2W = GetSystemWow64Directory2W(v16, uSize[0]);
    }
    else
    {
      if ( v56 > 7 )
        v16 = lpBuffer[0];
      SystemWow64Directory2W = GetSystemDirectoryW(v16, uSize[0]);
    }
    if ( !SystemWow64Directory2W )
    {
      v15 = 1123;
      goto LABEL_7;
    }
    v18 = SystemWow64Directory2W;
    if ( (unsigned __int64)SystemWow64Directory2W >= *(_QWORD *)uSize )
    {
      LastError = -2147024774;
      v19 = 1124;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
        (const char *)LastError,
        dwCreationDisposition);
      goto LABEL_37;
    }
    v20 = lpBuffer;
    if ( v56 > 7 )
      v20 = (LPWSTR *)lpBuffer[0];
    if ( !*(_WORD *)v20 )
    {
      LastError = -2147024735;
      v19 = 1125;
      goto LABEL_19;
    }
    std::wstring::resize(lpBuffer, v18);
    *(_QWORD *)&v41 = L"werfaultsecure.exe";
    *((_QWORD *)&v41 + 1) = 18;
    Microsoft::Diagnostics::Utils::String::AppendPath((PWSTR)lpBuffer);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpBuffer);
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v52);
    v21 = std::operator<<<wchar_t>(v53, lpBuffer);
    v22 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v21, L" /h /s /pid ");
    v23 = std::wostream::operator<<(v22, a1);
    v24 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v23, L" /type ");
    v25 = std::wostream::operator<<(v24, a3);
    v26 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v25, L" /encfile ");
    v27 = std::wostream::operator<<(v26, v10);
    v28 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v27, L" /cancel ");
    std::wostream::operator<<(v28, v13);
    *(&StartupInfo.cb + 1) = 0;
    memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    StartupInfo.cb = 112;
    v51 = v43;
    v29 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v52, v57);
    if ( *(_QWORD *)(v29 + 24) > 7u )
      v29 = *(_QWORD *)v29;
    v30 = CreateProcessW(0, (LPWSTR)v29, 0, 0, 1, 0xC0000u, 0, 0, &StartupInfo, &ProcessInformation);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
    if ( !v30 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x47F,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                    v31);
LABEL_36:
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v52);
      goto LABEL_37;
    }
    hProcess = ProcessInformation.hProcess;
    *(_QWORD *)&v41 = ProcessInformation.hProcess;
    v45[0] = ProcessInformation.hThread;
    if ( Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(ProcessInformation.hProcess, a5) )
    {
      ExitCode[0] = 0;
      if ( GetExitCodeProcess(hProcess, ExitCode) )
      {
        LastError = ExitCode[0];
        if ( (ExitCode[0] & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x491,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
            (const char *)ExitCode[0],
            dwCreationDispositiona);
        goto LABEL_35;
      }
      v34 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x490,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              v35);
    }
    else
    {
      wil::details::SetEvent(v13, v33);
      v34 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x48B,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              (const char *)0x5B4,
              dwCreationDispositiona);
    }
    LastError = v34;
LABEL_35:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v45);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v41);
    goto LABEL_36;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x446,
                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                v11);
LABEL_38:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v47);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v44);
  return LastError;
}

```

## disassembly

```asm
0x18008674c  push    rbp
0x18008674e  push    rbx
0x18008674f  push    rsi
0x180086750  push    rdi
0x180086751  push    r12
0x180086753  push    r14
0x180086755  push    r15
0x180086757  lea     rbp, [rsp-1A0h]
0x18008675f  sub     rsp, 2A0h
0x180086766  mov     rax, cs:__security_cookie
0x18008676d  xor     rax, rsp
0x180086770  mov     [rbp+1D0h+var_40], rax
0x180086777  mov     rbx, r9
0x18008677a  mov     r15d, r8d
0x18008677d  mov     rsi, rdx
0x180086780  mov     r14d, ecx
0x180086783  mov     qword ptr [rbp+1D0h+SecurityAttributes.nLength], 18h
0x18008678b  xor     r12d, r12d
0x18008678e  mov     [rbp+1D0h+SecurityAttributes.lpSecurityDescriptor], r12
0x180086792  mov     qword ptr [rbp+1D0h+SecurityAttributes.bInheritHandle], 1
0x18008679a  mov     [rbp+1D0h+var_250], r12
0x18008679e  mov     qword ptr [rsp+2D0h+dwCreationDisposition], r12
0x1800867a3  lea     r9, [rbp+1D0h+SecurityAttributes]
0x1800867a7  xor     r8d, r8d
0x1800867aa  xor     edx, edx
0x1800867ac  lea     rcx, [rbp+1D0h+var_250]
0x1800867b0  call    ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA_NW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800867b5  mov     rdx, rbx
0x1800867b8  lea     rcx, [rbp+1D0h+var_60]
0x1800867bf  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1800867c4  cmp     qword ptr [rax+18h], 7
0x1800867c9  jbe     short loc_1800867CE
0x1800867cb  mov     rax, [rax]
0x1800867ce  mov     [rsp+2D0h+hTemplateFile], r12; hTemplateFile
0x1800867d3  mov     [rsp+2D0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800867d8  mov     [rsp+2D0h+dwCreationDisposition], 1; int
0x1800867e0  lea     r9, [rbp+1D0h+SecurityAttributes]; lpSecurityAttributes
0x1800867e4  xor     r8d, r8d; dwShareMode
0x1800867e7  mov     edx, 40000000h; dwDesiredAccess
0x1800867ec  mov     rcx, rax; lpFileName
0x1800867ef  call    cs:__imp_CreateFileW
0x1800867f6  nop     dword ptr [rax+rax+00h]
0x1800867fb  mov     rbx, rax
0x1800867fe  mov     [rbp+1D0h+var_220], rax
0x180086802  lea     rcx, [rbp+1D0h+var_60]; this
0x180086809  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008680e  lea     rax, [rbx+1]
0x180086812  test    rax, 0FFFFFFFFFFFFFFFEh
0x180086818  jnz     short loc_180086839
0x18008681a  mov     rcx, [rbp+1D8h]; this
0x180086821  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x180086828  mov     edx, 446h; void *
0x18008682d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180086832  mov     ebx, eax
0x180086834  jmp     loc_180086BFE
0x180086839  mov     rdi, [rbp+1D0h+var_250]
0x18008683d  mov     [rbp+1D0h+var_200], rdi
0x180086841  mov     [rbp+1D0h+var_1F8], rbx
0x180086845  lea     rax, [rbp+1D0h+var_200]
0x180086849  mov     qword ptr [rsp+2D0h+var_270], rax
0x18008684e  lea     rdx, [rsp+2D0h+var_270]
0x180086853  lea     rcx, [rbp+1D0h+var_248]
0x180086857  call    ??$?0QEAX$01$0?0$0A@@?$span@QEAX$0?0@gsl@@QEAA@AEBV?$span@QEAX$01@1@@Z; gsl::span<void * const,-1>::span<void * const,-1>(gsl::span<void * const,2> const &)
0x18008685c  movups  xmm0, xmmword ptr [rax]
0x18008685f  movdqu  [rsp+2D0h+var_270], xmm0
0x180086865  lea     rdx, [rsp+2D0h+var_270]
0x18008686a  lea     rcx, [rsp+2D0h+var_260]
0x18008686f  call    ?BuildInheritHandleAttributeList@Os@Utils@Diagnostics@Microsoft@@CA?AUAttributeListAndMemory@1234@V?$span@QEAX$0?0@gsl@@@Z; Microsoft::Diagnostics::Utils::Os::BuildInheritHandleAttributeList(gsl::span<void * const,-1>)
0x180086874  nop
0x180086875  mov     [rsp+2D0h+var_280], r12w
0x18008687b  xor     r8d, r8d
0x18008687e  mov     edx, 104h
0x180086883  lea     rcx, [rbp+1D0h+lpBuffer]
0x18008688a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x18008688f  nop
0x180086890  xor     r8d, r8d
0x180086893  lea     rdx, [rsp+2D0h+var_280]
0x180086898  mov     rcx, [rsi]
0x18008689b  call    cs:__imp_IsWow64Process2
0x1800868a2  nop     dword ptr [rax+rax+00h]
0x1800868a7  test    eax, eax
0x1800868a9  jnz     short loc_1800868CA
0x1800868ab  mov     edx, 458h; void *
0x1800868b0  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x1800868b7  mov     rcx, [rbp+1D8h]; this
0x1800868be  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800868c3  mov     ebx, eax
0x1800868c5  jmp     loc_180086BE6
0x1800868ca  movzx   r8d, [rsp+2D0h+var_280]
0x1800868d0  lea     rcx, [rbp+1D0h+lpBuffer]
0x1800868d7  mov     edx, [rbp+1D0h+uSize]; uSize
0x1800868dd  test    r8w, r8w
0x1800868e1  jz      short loc_180086901
0x1800868e3  cmp     [rbp+1D0h+var_68], 7
0x1800868eb  cmova   rcx, [rbp+1D0h+lpBuffer]
0x1800868f3  call    cs:__imp_GetSystemWow64Directory2W
0x1800868fa  nop     dword ptr [rax+rax+00h]
0x1800868ff  jmp     short loc_18008691D
0x180086901  cmp     [rbp+1D0h+var_68], 7
0x180086909  cmova   rcx, [rbp+1D0h+lpBuffer]; lpBuffer
0x180086911  call    cs:__imp_GetSystemDirectoryW
0x180086918  nop     dword ptr [rax+rax+00h]
0x18008691d  test    eax, eax
0x18008691f  jnz     short loc_180086928
0x180086921  mov     edx, 463h
0x180086926  jmp     short loc_1800868B0
0x180086928  mov     edx, eax
0x18008692a  cmp     rdx, qword ptr [rbp+1D0h+uSize]
0x180086931  jb      short loc_180086958
0x180086933  mov     ebx, 8007007Ah
0x180086938  mov     edx, 464h; void *
0x18008693d  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x180086944  mov     r9d, ebx; char *
0x180086947  mov     rcx, [rbp+1D8h]; this
0x18008694e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086953  jmp     loc_180086BE6
0x180086958  lea     rax, [rbp+1D0h+lpBuffer]
0x18008695f  cmp     [rbp+1D0h+var_68], 7
0x180086967  cmova   rax, [rbp+1D0h+lpBuffer]
0x18008696f  cmp     [rax], r12w
0x180086973  jnz     short loc_180086981
0x180086975  mov     ebx, 800700A1h
0x18008697a  mov     edx, 465h
0x18008697f  jmp     short loc_18008693D
0x180086981  lea     rcx, [rbp+1D0h+lpBuffer]
0x180086988  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18008698d  lea     rax, aWerfaultsecure; "werfaultsecure.exe"
0x180086994  mov     qword ptr [rsp+2D0h+var_270], rax
0x180086999  mov     qword ptr [rsp+2D0h+var_270+8], 12h
0x1800869a2  lea     rdx, [rsp+2D0h+var_270]
0x1800869a7  lea     rcx, [rbp+1D0h+lpBuffer]; pszPath
0x1800869ae  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x1800869b3  xor     r8d, r8d
0x1800869b6  mov     dl, 1
0x1800869b8  lea     rcx, [rbp+1D0h+lpBuffer]; lpSrc
0x1800869bf  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1800869c4  lea     rcx, [rbp+1D0h+var_180]
0x1800869c8  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x1800869cd  nop
0x1800869ce  lea     rdx, [rbp+1D0h+lpBuffer]
0x1800869d5  lea     rcx, [rbp+1D0h+var_170]
0x1800869d9  call    ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x1800869de  mov     rcx, rax
0x1800869e1  lea     rdx, aHSPid; " /h /s /pid "
0x1800869e8  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1800869ed  mov     edx, r14d
0x1800869f0  mov     rcx, rax
0x1800869f3  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z; std::wostream::operator<<(ulong)
0x1800869fa  nop     dword ptr [rax+rax+00h]
0x1800869ff  mov     rcx, rax
0x180086a02  lea     rdx, aType_5; " /type "
0x180086a09  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180086a0e  mov     edx, r15d
0x180086a11  mov     rcx, rax
0x180086a14  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z; std::wostream::operator<<(ulong)
0x180086a1b  nop     dword ptr [rax+rax+00h]
0x180086a20  mov     rcx, rax
0x180086a23  lea     rdx, aEncfile; " /encfile "
0x180086a2a  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180086a2f  mov     rdx, rbx
0x180086a32  mov     rcx, rax
0x180086a35  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z; std::wostream::operator<<(unsigned __int64)
0x180086a3c  nop     dword ptr [rax+rax+00h]
0x180086a41  mov     rcx, rax
0x180086a44  lea     rdx, aCancel_1; " /cancel "
0x180086a4b  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180086a50  mov     rdx, rdi
0x180086a53  mov     rcx, rax
0x180086a56  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z; std::wostream::operator<<(unsigned __int64)
0x180086a5d  nop     dword ptr [rax+rax+00h]
0x180086a62  xor     eax, eax
0x180086a64  mov     dword ptr [rbp+1D0h+StartupInfo+4], eax
0x180086a67  xor     edx, edx; Val
0x180086a69  lea     r8d, [rax+68h]; Size
0x180086a6d  lea     rcx, [rbp+1D0h+StartupInfo.lpReserved]; void *
0x180086a71  call    memset_0
0x180086a76  xorps   xmm0, xmm0
0x180086a79  xor     eax, eax
0x180086a7b  movups  xmmword ptr [rbp+1D0h+ProcessInformation.hProcess], xmm0
0x180086a7f  mov     qword ptr [rbp+1D0h+ProcessInformation.dwProcessId], rax
0x180086a83  mov     [rbp+1D0h+StartupInfo.cb], 70h ; 'p'
0x180086a8a  mov     rax, [rsp+2D0h+var_258]
0x180086a8f  mov     [rbp+1D0h+var_188], rax
0x180086a93  lea     rdx, [rbp+1D0h+var_60]
0x180086a9a  lea     rcx, [rbp+1D0h+var_180]
0x180086a9e  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x180086aa3  cmp     qword ptr [rax+18h], 7
0x180086aa8  jbe     short loc_180086AAD
0x180086aaa  mov     rax, [rax]
0x180086aad  lea     rcx, [rbp+1D0h+ProcessInformation]
0x180086ab1  mov     [rsp+2D0h+lpProcessInformation], rcx; lpProcessInformation
0x180086ab6  lea     rcx, [rbp+1D0h+StartupInfo]
0x180086aba  mov     [rsp+2D0h+lpStartupInfo], rcx; lpStartupInfo
0x180086abf  mov     [rsp+2D0h+lpCurrentDirectory], r12; lpCurrentDirectory
0x180086ac4  mov     [rsp+2D0h+hTemplateFile], r12; lpEnvironment
0x180086ac9  mov     [rsp+2D0h+dwFlagsAndAttributes], 0C0000h; dwCreationFlags
0x180086ad1  mov     [rsp+2D0h+dwCreationDisposition], 1; int
0x180086ad9  xor     r9d, r9d; lpThreadAttributes
0x180086adc  xor     r8d, r8d; lpProcessAttributes
0x180086adf  mov     rdx, rax; lpCommandLine
0x180086ae2  xor     ecx, ecx; lpApplicationName
0x180086ae4  call    cs:__imp_CreateProcessW
0x180086aeb  nop     dword ptr [rax+rax+00h]
0x180086af0  mov     ebx, eax
0x180086af2  lea     rcx, [rbp+1D0h+var_60]; this
0x180086af9  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180086afe  test    ebx, ebx
0x180086b00  jnz     short loc_180086B21
0x180086b02  mov     rcx, [rbp+1D8h]; this
0x180086b09  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x180086b10  mov     edx, 47Fh; void *
0x180086b15  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180086b1a  mov     ebx, eax
0x180086b1c  jmp     loc_180086BDC
0x180086b21  mov     rbx, [rbp+1D0h+ProcessInformation.hProcess]
0x180086b25  mov     qword ptr [rsp+2D0h+var_270], rbx
0x180086b2a  mov     rax, [rbp+1D0h+ProcessInformation.hThread]
0x180086b2e  mov     [rbp+1D0h+var_248], rax
0x180086b32  mov     edx, [rbp+1D0h+arg_20]; unsigned int
0x180086b38  mov     rcx, rbx; void *
0x180086b3b  call    ?WaitOrTimeout@Os@Utils@Diagnostics@Microsoft@@SA_NPEAXK@Z; Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(void *,ulong)
0x180086b40  test    al, al
0x180086b42  jnz     short loc_180086B6E
0x180086b44  mov     rcx, rdi; this
0x180086b47  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180086b4c  mov     rcx, [rbp+1D8h]; this
0x180086b53  mov     r9d, 5B4h; char *
0x180086b59  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x180086b60  mov     edx, 48Bh; void *
0x180086b65  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180086b6a  mov     ebx, eax
0x180086b6c  jmp     short loc_180086BC8
0x180086b6e  mov     [rsp+2D0h+ExitCode], r12d
0x180086b73  lea     rdx, [rsp+2D0h+ExitCode]; lpExitCode
0x180086b78  mov     rcx, rbx; hProcess
0x180086b7b  call    cs:__imp_GetExitCodeProcess
0x180086b82  nop     dword ptr [rax+rax+00h]
0x180086b87  test    eax, eax
0x180086b89  jnz     short loc_180086BA5
0x180086b8b  mov     rcx, [rbp+1D8h]; this
0x180086b92  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x180086b99  mov     edx, 490h; void *
0x180086b9e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180086ba3  jmp     short loc_180086B6A
0x180086ba5  mov     ebx, [rsp+2D0h+ExitCode]
0x180086ba9  test    ebx, ebx
0x180086bab  jns     short loc_180086BC8
0x180086bad  mov     rcx, [rbp+1D8h]; this
0x180086bb4  mov     r9d, ebx; char *
0x180086bb7  lea     r8, aOnecoreBaseTel_242; "onecore\\base\\telemetry\\utc\\include"...
0x180086bbe  mov     edx, 491h; void *
0x180086bc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086bc8  lea     rcx, [rbp+1D0h+var_248]
0x180086bcc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180086bd1  lea     rcx, [rsp+2D0h+var_270]
0x180086bd6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180086bdb  nop
0x180086bdc  lea     rcx, [rbp+1D0h+var_180]
0x180086be0  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(void)
0x180086be5  nop
0x180086be6  lea     rcx, [rbp+1D0h+lpBuffer]; this
0x180086bed  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180086bf2  nop
0x180086bf3  lea     rcx, [rsp+2D0h+var_260]; this
0x180086bf8  call    ??1AttributeListAndMemory@Os@Utils@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::Utils::Os::AttributeListAndMemory::~AttributeListAndMemory(void)
0x180086bfd  nop
0x180086bfe  lea     rcx, [rbp+1D0h+var_220]
0x180086c02  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180086c07  nop
0x180086c08  lea     rcx, [rbp+1D0h+var_250]
0x180086c0c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180086c11  mov     eax, ebx
0x180086c13  mov     rcx, [rbp+1D0h+var_40]
0x180086c1a  xor     rcx, rsp; StackCookie
0x180086c1d  call    __security_check_cookie
0x180086c22  add     rsp, 2A0h
0x180086c29  pop     r15
0x180086c2b  pop     r14
0x180086c2d  pop     r12
0x180086c2f  pop     rdi
0x180086c30  pop     rsi
0x180086c31  pop     rbx
0x180086c32  pop     rbp
0x180086c33  retn
```
