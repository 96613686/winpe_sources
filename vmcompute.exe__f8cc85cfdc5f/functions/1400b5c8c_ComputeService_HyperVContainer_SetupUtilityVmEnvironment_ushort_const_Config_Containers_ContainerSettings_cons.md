# ComputeService::HyperVContainer::SetupUtilityVmEnvironment(ushort const *,Config::Containers::ContainerSettings const &,Schema::Registry::RegistryChanges const &,ushort const *,ushort const *,unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&,bool,ComputeService::UtilityVm::UtilityVmType,bool,IVmHandleBrokerManager *,_GUID const &)

- ea: `0x1400b5c8c`
- end: `0x1400b60f8`
- name: `?SetupUtilityVmEnvironment@HyperVContainer@ComputeService@@YA?AV?$unique_ptr@UUtilityVmEnvironment@HyperVContainer@ComputeService@@U?$default_delete@UUtilityVmEnvironment@HyperVContainer@ComputeService@@@std@@@std@@PEBGAEBUContainerSettings@Containers@Config@@AEBURegistryChanges@Registry@Schema@@00_K$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@_NW4UtilityVmType@UtilityVm@2@5PEAUIVmHandleBrokerManager@@AEBU_GUID@@@Z`
- size: `1132`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14009dad0`
- `0x14018b1d0`

## callees

- `0x140017040`
- `0x14001d490`
- `0x140024030`
- `0x14002fa20`
- `0x1400421f0`
- `0x140044974`
- `0x140057fec`
- `0x140080180`
- `0x14008526c`
- `0x1400979d8`
- `0x1400aaa9c`
- `0x1400ad53c`
- `0x1400b1dd0`
- `0x1400b45f4`
- `0x1400b5024`
- `0x1400b5c8c`
- `0x1400b6100`
- `0x1400b61e0`
- `0x1400b65c4`
- `0x1400b66e0`
- `0x1400b7c50`
- `0x1400b7cac`
- `0x1400c40e0`
- `0x1401332f0`
- `0x140133314`
- `0x14019cf34`
- `0x14019d128`
- `0x14021797c`
- `0x1402179ec`
- `0x140217df0`
- `0x140217e88`
- `0x140217eb0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1400b60a0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1400b60a0`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1400b6011`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1400b6011`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1400b5f36`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1400b5f36`

## string_xrefs

- `0x1400b5f72`: `onecore\vm\compute\management\orchestration\hypervcontainer\utilityvm.cpp`
- `0x1400b6028`: `onecore\vm\compute\management\orchestration\hypervcontainer\utilityvm.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
ComputeService::HyperVContainer::Details **__fastcall ComputeService::HyperVContainer::SetupUtilityVmEnvironment(
        ComputeService::HyperVContainer::Details **a1,
        ComputeService::HyperVContainer::Details *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        char a9,
        unsigned int a10,
        char a11,
        __int64 a12,
        _OWORD *a13)
{
  WCHAR *v16; // rbx
  ComputeService::HyperVContainer::Details *v17; // r8
  unsigned __int64 v18; // rcx
  struct ComputeService::HyperVContainer::UtilityVmEnvironment *v19; // rdx
  __int64 v20; // rax
  struct ComputeService::HyperVContainer::UtilityVmEnvironment *v21; // r8
  struct ComputeService::HyperVContainer::UtilityVmEnvironment *v22; // r9
  ComputeService::HyperVContainer::Details *v23; // rdx
  __int64 WorkerProcessSiloJobName; // rax
  __int64 NamedWorkerProcessSiloJobObject; // rax
  void *v26; // r8
  ComputeService::HyperVContainer::Details *v27; // rbx
  HANDLE JobObjectW; // rax
  ComputeService::JobUtilities *v29; // rcx
  const WCHAR *v30; // rsi
  __int64 UtilityVmDataRoot; // rax
  HRESULT v32; // eax
  __int64 UtilityVmBugcheckSavedStateFilename; // rax
  const WCHAR *v34; // rcx
  const struct _GUID *v35; // r8
  const WCHAR *v36; // rcx
  _QWORD v38[2]; // [rsp+48h] [rbp-A9h] BYREF
  WCHAR pszPathOut[16]; // [rsp+58h] [rbp-99h] BYREF
  ComputeService::HyperVContainer::Details **v40; // [rsp+78h] [rbp-79h]
  ComputeService::HyperVContainer::Details **v41; // [rsp+80h] [rbp-71h]
  ComputeService::HyperVContainer::Details **v42; // [rsp+88h] [rbp-69h]
  char v43; // [rsp+90h] [rbp-61h]
  _BYTE v44[32]; // [rsp+98h] [rbp-59h] BYREF
  ComputeService::HyperVContainer::Details *v45; // [rsp+B8h] [rbp-39h] BYREF
  PWSTR ppszPathOut; // [rsp+C0h] [rbp-31h] BYREF
  WCHAR v47[16]; // [rsp+C8h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+47h]

  v40 = a1;
  v45 = a2;
  v38[0] = a5;
  v38[1] = a12;
  *a1 = 0;
  v16 = (WCHAR *)operator new(0x408u);
  ppszPathOut = v16;
  ComputeService::UtilityVm::Environment::Environment((ComputeService::UtilityVm::Environment *)v16);
  *((_BYTE *)v16 + 992) = 0;
  std::wstring::wstring(v16 + 500);
  *a1 = (ComputeService::HyperVContainer::Details *)v16;
  *(_OWORD *)v16 = *(_OWORD *)(a3 + 248);
  v17 = *a1;
  v18 = *(_QWORD *)*a1;
  if ( !v18 )
    v18 = *((_QWORD *)v17 + 1) - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( !v18 )
    *(_OWORD *)v17 = *a13;
  v41 = &v45;
  v42 = a1;
  v43 = 1;
  *((_BYTE *)*a1 + 304) = a9;
  std::wstring::operator=((char *)*a1 + 16, a8);
  if ( a10 == 2 )
    ComputeService::HyperVContainer::Details::SetupRuntimeStateFile(*a1, v19);
  ComputeService::HyperVContainer::Details::UpdateUtilityVmSettings(v45, a3, a10, *a1);
  if ( *(_BYTE *)(a3 + 840) )
  {
    if ( *(_QWORD *)(a3 + 768) )
      v20 = ComputeService::JobUtilities::OpenMemoryPartition(&ppszPathOut);
    else
      v20 = ComputeService::JobUtilities::CreateMemoryPartition(&ppszPathOut);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      (char *)*a1 + 576,
      v20);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ppszPathOut);
  }
  ComputeService::HyperVContainer::Details::SetupStorage(v47, a10, (unsigned __int16 *)*a1, a11);
  if ( *((_QWORD *)*a1 + 26) )
    ComputeService::HyperVContainer::Details::SetupDebugNetworking(
      (ComputeService::HyperVContainer::Details *)a3,
      *a1,
      v21);
  if ( *(_BYTE *)(a3 + 465) && *(_BYTE *)(a3 + 404) )
    ComputeService::HyperVContainer::Details::SetupVmSharedMemory(v45, (const unsigned __int16 *)a3, *a1, v22);
  ComputeService::HyperVContainer::Details::CreateConfiguration(v45, a3, a4, v38[0]);
  if ( a10 != 2 )
  {
    if ( *(_BYTE *)(a3 + 465) )
    {
      std::wstring::wstring(v44, v45);
      WorkerProcessSiloJobName = ComputeService::JobUtilities::GetWorkerProcessSiloJobName(pszPathOut, v44);
      NamedWorkerProcessSiloJobObject = ComputeService::JobUtilities::CreateNamedWorkerProcessSiloJobObject(
                                          v38,
                                          WorkerProcessSiloJobName);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        (char *)*a1 + 512,
        NamedWorkerProcessSiloJobObject);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v38);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pszPathOut);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v44);
      ComputeService::JobUtilities::CreateSiloForIsolatedWorkerProcess(*((ComputeService::JobUtilities **)*a1 + 64));
    }
    else
    {
      v27 = *a1;
      JobObjectW = CreateJobObjectW(0, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)v27 + 512,
        JobObjectW);
    }
    v23 = *a1;
    v29 = (ComputeService::JobUtilities *)*((_QWORD *)*a1 + 64);
    if ( (((unsigned __int64)v29 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3CF,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\utilityvm.cpp",
        (const char *)retaddr);
    if ( *(_BYTE *)(a3 + 840) )
      ComputeService::JobUtilities::SetMemoryPartitionForJob(v29, *((void **)v23 + 72), v26);
  }
  *((_DWORD *)*a1 + 78) = 1;
  if ( ComputeService::HyperVContainer::Details::EnableSaveVmOnBugcheck(
         (ComputeService::HyperVContainer::Details *)a3,
         v23) )
  {
    *((_BYTE *)*a1 + 992) = 1;
    if ( *(_QWORD *)(a3 + 504) )
    {
      ppszPathOut = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &ppszPathOut,
        0);
      v30 = (const WCHAR *)(a3 + 488);
      if ( *((_QWORD *)v30 + 3) > 7u )
        v30 = *(const WCHAR **)v30;
      UtilityVmDataRoot = ComputeService::HyperVContainer::GetUtilityVmDataRoot(pszPathOut);
      if ( *(_QWORD *)(UtilityVmDataRoot + 24) > 7u )
        UtilityVmDataRoot = *(_QWORD *)UtilityVmDataRoot;
      v32 = PathAllocCombine((PCWSTR)UtilityVmDataRoot, v30, 0, &ppszPathOut);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3EC,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\hypervcontainer\\utilityvm.cpp",
          (const char *)(unsigned int)v32,
          a7);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pszPathOut);
      std::wstring::assign((char *)*a1 + 1000, ppszPathOut);
      Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(&ppszPathOut);
    }
    else
    {
      UtilityVmBugcheckSavedStateFilename = ComputeService::HyperVContainer::GetUtilityVmBugcheckSavedStateFilename(pszPathOut);
      std::wstring::operator=((char *)*a1 + 1000, UtilityVmBugcheckSavedStateFilename);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pszPathOut);
    }
    v34 = (const WCHAR *)((char *)*a1 + 1000);
    if ( *((_QWORD *)*a1 + 128) > 7u )
      v34 = *(const WCHAR **)v34;
    if ( PathFileExistsW(v34) )
    {
      v36 = (const WCHAR *)((char *)*a1 + 1000);
      if ( *((_QWORD *)*a1 + 128) > 7u )
        v36 = *(const WCHAR **)v36;
      ComputeService::Vmwp::GrantVmAccess(v36, (DWORD *)*a1, v35);
    }
  }
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v47);
  return a1;
}

```

## disassembly

```asm
0x1400b5c8c  push    rbp
0x1400b5c8e  push    rbx
0x1400b5c8f  push    rsi
0x1400b5c90  push    rdi
0x1400b5c91  push    r12
0x1400b5c93  push    r13
0x1400b5c95  push    r14
0x1400b5c97  push    r15
0x1400b5c99  lea     rbp, [rsp-7]
0x1400b5c9e  sub     rsp, 0F8h
0x1400b5ca5  mov     rax, cs:__security_cookie
0x1400b5cac  xor     rax, rsp
0x1400b5caf  mov     [rbp+3Fh+var_48], rax
0x1400b5cb3  mov     r13, r9
0x1400b5cb6  mov     rsi, r8
0x1400b5cb9  mov     rdi, rcx
0x1400b5cbc  mov     [rbp+3Fh+var_B8], rcx
0x1400b5cc0  mov     [rbp+3Fh+var_78], rdx
0x1400b5cc4  mov     rax, [rbp+3Fh+arg_20]
0x1400b5cc8  mov     [rsp+130h+var_E8], rax
0x1400b5ccd  mov     r12, [rbp+3Fh+arg_28]
0x1400b5cd1  mov     r15, [rbp+3Fh+arg_38]
0x1400b5cd8  mov     r14d, [rbp+3Fh+arg_48]
0x1400b5cdf  mov     rax, [rbp+3Fh+arg_58]
0x1400b5ce6  mov     [rsp+130h+var_E0], rax
0x1400b5ceb  mov     [rsp+130h+var_F0], 0
0x1400b5cf3  xor     eax, eax
0x1400b5cf5  mov     [rcx], rax
0x1400b5cf8  mov     ecx, 408h; Size
0x1400b5cfd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400b5d02  mov     rbx, rax
0x1400b5d05  mov     [rbp+3Fh+ppszPathOut], rax
0x1400b5d09  mov     rcx, rax; this
0x1400b5d0c  call    ??0Environment@UtilityVm@ComputeService@@QEAA@XZ; ComputeService::UtilityVm::Environment::Environment(void)
0x1400b5d11  mov     byte ptr [rbx+3E0h], 0
0x1400b5d18  lea     rcx, [rbx+3E8h]; void *
0x1400b5d1f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400b5d24  nop
0x1400b5d25  mov     [rdi], rbx
0x1400b5d28  mov     [rsp+130h+var_F0], 1
0x1400b5d30  movups  xmm0, xmmword ptr [rsi+0F8h]
0x1400b5d37  movdqu  xmmword ptr [rbx], xmm0
0x1400b5d3b  xorps   xmm1, xmm1
0x1400b5d3e  mov     r8, [rdi]
0x1400b5d41  mov     rcx, [r8]
0x1400b5d44  movq    rax, xmm1
0x1400b5d49  sub     rcx, rax
0x1400b5d4c  jnz     short loc_1400B5D5F
0x1400b5d4e  mov     rcx, [r8+8]
0x1400b5d52  psrldq  xmm1, 8
0x1400b5d57  movq    rax, xmm1
0x1400b5d5c  sub     rcx, rax
0x1400b5d5f  xor     ebx, ebx
0x1400b5d61  test    rcx, rcx
0x1400b5d64  jnz     short loc_1400B5D75
0x1400b5d66  mov     rax, [rbp+3Fh+arg_60]
0x1400b5d6d  movups  xmm0, xmmword ptr [rax]
0x1400b5d70  movdqu  xmmword ptr [r8], xmm0
0x1400b5d75  lea     rax, [rbp+3Fh+var_78]
0x1400b5d79  mov     [rbp+3Fh+var_B0], rax
0x1400b5d7d  mov     [rbp+3Fh+var_A8], rdi
0x1400b5d81  mov     [rbp+3Fh+var_A0], 1
0x1400b5d85  mov     rcx, [rdi]
0x1400b5d88  mov     al, [rbp+3Fh+arg_40]
0x1400b5d8e  mov     [rcx+130h], al
0x1400b5d94  mov     rcx, [rdi]
0x1400b5d97  add     rcx, 10h
0x1400b5d9b  mov     rdx, r15
0x1400b5d9e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400b5da3  cmp     r14d, 2
0x1400b5da7  jnz     short loc_1400B5DB1
0x1400b5da9  mov     rcx, [rdi]; this
0x1400b5dac  call    ?SetupRuntimeStateFile@Details@HyperVContainer@ComputeService@@YAXPEAUUtilityVmEnvironment@23@@Z; ComputeService::HyperVContainer::Details::SetupRuntimeStateFile(ComputeService::HyperVContainer::UtilityVmEnvironment *)
0x1400b5db1  mov     r9, [rdi]
0x1400b5db4  mov     r8d, r14d
0x1400b5db7  mov     rdx, rsi
0x1400b5dba  mov     rcx, [rbp+3Fh+var_78]
0x1400b5dbe  call    ?UpdateUtilityVmSettings@Details@HyperVContainer@ComputeService@@YAXPEBGAEAUContainerSettings@Containers@Config@@W4UtilityVmType@UtilityVm@3@PEAUUtilityVmEnvironment@23@@Z; ComputeService::HyperVContainer::Details::UpdateUtilityVmSettings(ushort const *,Config::Containers::ContainerSettings &,ComputeService::UtilityVm::UtilityVmType,ComputeService::HyperVContainer::UtilityVmEnvironment *)
0x1400b5dc3  cmp     [rsi+348h], bl
0x1400b5dc9  jz      short loc_1400B5E1B
0x1400b5dcb  lea     rdx, [rsi+2F0h]
0x1400b5dd2  mov     al, [rdx+58h]
0x1400b5dd5  mov     ecx, 5
0x1400b5dda  test    al, al
0x1400b5ddc  jnz     short loc_1400B5DE0
0x1400b5dde  int     29h; Win8: RtlFailFast(ecx)
0x1400b5de0  cmp     [rdx+10h], rbx
0x1400b5de4  jnz     short loc_1400B5DF1
0x1400b5de6  lea     rcx, [rbp+3Fh+ppszPathOut]
0x1400b5dea  call    ?CreateMemoryPartition@JobUtilities@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ComputeService::JobUtilities::CreateMemoryPartition(void)
0x1400b5def  jmp     short loc_1400B5E00
0x1400b5df1  test    al, al
0x1400b5df3  jnz     short loc_1400B5DF7
0x1400b5df5  int     29h; Win8: RtlFailFast(ecx)
0x1400b5df7  lea     rcx, [rbp+3Fh+ppszPathOut]
0x1400b5dfb  call    ?OpenMemoryPartition@JobUtilities@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::JobUtilities::OpenMemoryPartition(std::wstring const &)
0x1400b5e00  mov     rcx, [rdi]
0x1400b5e03  mov     rdx, rax
0x1400b5e06  add     rcx, 240h
0x1400b5e0d  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400b5e12  lea     rcx, [rbp+3Fh+ppszPathOut]; void *
0x1400b5e16  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400b5e1b  mov     al, [rbp+3Fh+arg_50]
0x1400b5e21  mov     byte ptr [rsp+130h+var_100], al
0x1400b5e25  mov     rax, [rdi]
0x1400b5e28  mov     [rsp+130h+var_108], rax
0x1400b5e2d  mov     [rsp+130h+var_110], r14d
0x1400b5e32  mov     r9, r12
0x1400b5e35  mov     r8, rsi
0x1400b5e38  mov     rdx, [rbp+3Fh+var_78]
0x1400b5e3c  lea     rcx, [rbp+3Fh+var_68]
0x1400b5e40  call    ?SetupStorage@Details@HyperVContainer@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEBUContainerSettings@Containers@Config@@0W4UtilityVmType@UtilityVm@3@PEAUUtilityVmEnvironment@23@_N@Z; ComputeService::HyperVContainer::Details::SetupStorage(ushort const *,Config::Containers::ContainerSettings const &,ushort const *,ComputeService::UtilityVm::UtilityVmType,ComputeService::HyperVContainer::UtilityVmEnvironment *,bool)
0x1400b5e45  nop
0x1400b5e46  mov     rdx, [rdi]; struct Config::Containers::ContainerSettings *
0x1400b5e49  cmp     [rdx+0D0h], rbx
0x1400b5e50  jz      short loc_1400B5E5A
0x1400b5e52  mov     rcx, rsi; this
0x1400b5e55  call    ?SetupDebugNetworking@Details@HyperVContainer@ComputeService@@YAXAEAUContainerSettings@Containers@Config@@PEAUUtilityVmEnvironment@23@@Z; ComputeService::HyperVContainer::Details::SetupDebugNetworking(Config::Containers::ContainerSettings &,ComputeService::HyperVContainer::UtilityVmEnvironment *)
0x1400b5e5a  cmp     [rsi+1D1h], bl
0x1400b5e60  jz      short loc_1400B5E79
0x1400b5e62  cmp     [rsi+194h], bl
0x1400b5e68  jz      short loc_1400B5E79
0x1400b5e6a  mov     r8, [rdi]; struct Config::Containers::ContainerSettings *
0x1400b5e6d  mov     rdx, rsi; unsigned __int16 *
0x1400b5e70  mov     rcx, [rbp+3Fh+var_78]; this
0x1400b5e74  call    ?SetupVmSharedMemory@Details@HyperVContainer@ComputeService@@YAXPEBGAEBUContainerSettings@Containers@Config@@PEAUUtilityVmEnvironment@23@@Z; ComputeService::HyperVContainer::Details::SetupVmSharedMemory(ushort const *,Config::Containers::ContainerSettings const &,ComputeService::HyperVContainer::UtilityVmEnvironment *)
0x1400b5e79  mov     rax, [rsp+130h+var_E0]
0x1400b5e7e  mov     [rsp+130h+var_F8], rax
0x1400b5e83  mov     rax, [rdi]
0x1400b5e86  mov     [rsp+130h+var_100], rax
0x1400b5e8b  mov     dword ptr [rsp+130h+var_108], r14d
0x1400b5e90  mov     rax, qword ptr [rbp+3Fh+arg_30]
0x1400b5e94  mov     qword ptr [rsp+130h+var_110], rax; int
0x1400b5e99  mov     r9, [rsp+130h+var_E8]
0x1400b5e9e  mov     r8, r13
0x1400b5ea1  mov     rdx, rsi
0x1400b5ea4  mov     rcx, [rbp+3Fh+var_78]
0x1400b5ea8  call    ?CreateConfiguration@Details@HyperVContainer@ComputeService@@YAXPEBGAEBUContainerSettings@Containers@Config@@AEBURegistryChanges@Registry@Schema@@0_KW4UtilityVmType@UtilityVm@3@PEAUUtilityVmEnvironment@23@PEAUIVmHandleBrokerManager@@@Z; ComputeService::HyperVContainer::Details::CreateConfiguration(ushort const *,Config::Containers::ContainerSettings const &,Schema::Registry::RegistryChanges const &,ushort const *,unsigned __int64,ComputeService::UtilityVm::UtilityVmType,ComputeService::HyperVContainer::UtilityVmEnvironment *,IVmHandleBrokerManager *)
0x1400b5ead  cmp     r14d, 2
0x1400b5eb1  jz      loc_1400B5F9B
0x1400b5eb7  cmp     [rsi+1D1h], bl
0x1400b5ebd  jz      short loc_1400B5F2F
0x1400b5ebf  mov     rdx, [rbp+3Fh+var_78]
0x1400b5ec3  lea     rcx, [rbp+3Fh+var_98]
0x1400b5ec7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400b5ecc  nop
0x1400b5ecd  lea     rdx, [rbp+3Fh+var_98]
0x1400b5ed1  lea     rcx, [rsp+130h+pszPathOut]
0x1400b5ed6  call    ?GetWorkerProcessSiloJobName@JobUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; ComputeService::JobUtilities::GetWorkerProcessSiloJobName(std::wstring const &)
0x1400b5edb  nop
0x1400b5edc  mov     rdx, rax
0x1400b5edf  lea     rcx, [rsp+130h+var_E8]
0x1400b5ee4  call    ?CreateNamedWorkerProcessSiloJobObject@JobUtilities@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::JobUtilities::CreateNamedWorkerProcessSiloJobObject(std::wstring const &)
0x1400b5ee9  mov     rcx, [rdi]
0x1400b5eec  add     rcx, 200h
0x1400b5ef3  mov     rdx, rax
0x1400b5ef6  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400b5efb  lea     rcx, [rsp+130h+var_E8]; void *
0x1400b5f00  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400b5f05  nop
0x1400b5f06  lea     rcx, [rsp+130h+pszPathOut]; this
0x1400b5f0b  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400b5f10  nop
0x1400b5f11  lea     rcx, [rbp+3Fh+var_98]; this
0x1400b5f15  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400b5f1a  mov     rcx, [rdi]
0x1400b5f1d  lea     rdx, [rbp+3Fh+var_68]
0x1400b5f21  mov     rcx, [rcx+200h]; this
0x1400b5f28  call    ?CreateSiloForIsolatedWorkerProcess@JobUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::JobUtilities::CreateSiloForIsolatedWorkerProcess(void *,std::wstring const &)
0x1400b5f2d  jmp     short loc_1400B5F53
0x1400b5f2f  mov     rbx, [rdi]
0x1400b5f32  xor     edx, edx; lpName
0x1400b5f34  xor     ecx, ecx; lpJobAttributes
0x1400b5f36  call    cs:__imp_CreateJobObjectW
0x1400b5f3d  nop     dword ptr [rax+rax+00h]
0x1400b5f42  mov     rdx, rax
0x1400b5f45  lea     rcx, [rbx+200h]
0x1400b5f4c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400b5f51  xor     ebx, ebx
0x1400b5f53  mov     rdx, [rdi]
0x1400b5f56  mov     rcx, [rdx+200h]; this
0x1400b5f5d  lea     rax, [rcx+1]
0x1400b5f61  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400b5f67  setz    al
0x1400b5f6a  mov     r9, [rbp+47h]; char *
0x1400b5f6e  test    al, al
0x1400b5f70  jz      short loc_1400B5F87
0x1400b5f72  lea     r8, aOnecoreVmCompu_151; "onecore\\vm\\compute\\management\\orche"...
0x1400b5f79  mov     edx, 3CFh; void *
0x1400b5f7e  mov     rcx, r9; this
0x1400b5f81  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b5f87  cmp     [rsi+348h], bl
0x1400b5f8d  jz      short loc_1400B5F9B
0x1400b5f8f  mov     rdx, [rdx+240h]; void *
0x1400b5f96  call    ?SetMemoryPartitionForJob@JobUtilities@ComputeService@@YAXPEAX0@Z; ComputeService::JobUtilities::SetMemoryPartitionForJob(void *,void *)
0x1400b5f9b  mov     rax, [rdi]
0x1400b5f9e  mov     dword ptr [rax+138h], 1
0x1400b5fa8  mov     rcx, rsi; this
0x1400b5fab  call    ?EnableSaveVmOnBugcheck@Details@HyperVContainer@ComputeService@@YA_NAEBUContainerSettings@Containers@Config@@@Z; ComputeService::HyperVContainer::Details::EnableSaveVmOnBugcheck(Config::Containers::ContainerSettings const &)
0x1400b5fb0  test    al, al
0x1400b5fb2  jz      loc_1400B60CA
0x1400b5fb8  mov     rax, [rdi]
0x1400b5fbb  mov     byte ptr [rax+3E0h], 1
0x1400b5fc2  cmp     [rsi+1F8h], rbx
0x1400b5fc9  jz      loc_1400B6063
0x1400b5fcf  mov     [rbp+3Fh+ppszPathOut], rbx
0x1400b5fd3  xor     edx, edx
0x1400b5fd5  lea     rcx, [rbp+3Fh+ppszPathOut]
0x1400b5fd9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1400b5fde  add     rsi, 1E8h
0x1400b5fe5  cmp     qword ptr [rsi+18h], 7
0x1400b5fea  jbe     short loc_1400B5FEF
0x1400b5fec  mov     rsi, [rsi]
0x1400b5fef  lea     rcx, [rsp+130h+pszPathOut]; pszPathOut
0x1400b5ff4  call    ?GetUtilityVmDataRoot@HyperVContainer@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ComputeService::HyperVContainer::GetUtilityVmDataRoot(void)
0x1400b5ff9  nop
0x1400b5ffa  cmp     qword ptr [rax+18h], 7
0x1400b5fff  jbe     short loc_1400B6004
0x1400b6001  mov     rax, [rax]
0x1400b6004  lea     r9, [rbp+3Fh+ppszPathOut]; ppszPathOut
0x1400b6008  xor     r8d, r8d; dwFlags
0x1400b600b  mov     rdx, rsi; pszMore
0x1400b600e  mov     rcx, rax; pszPathIn
0x1400b6011  call    cs:__imp_PathAllocCombine
0x1400b6018  nop     dword ptr [rax+rax+00h]
0x1400b601d  mov     rcx, [rbp+47h]; this
0x1400b6021  test    eax, eax
0x1400b6023  jns     short loc_1400B603A
0x1400b6025  mov     r9d, eax; char *
0x1400b6028  lea     r8, aOnecoreVmCompu_151; "onecore\\vm\\compute\\management\\orche"...
0x1400b602f  mov     edx, 3ECh; void *
0x1400b6034  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400b603a  lea     rcx, [rsp+130h+pszPathOut]; this
0x1400b603f  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400b6044  mov     rcx, [rdi]
0x1400b6047  add     rcx, 3E8h
0x1400b604e  mov     rdx, [rbp+3Fh+ppszPathOut]
0x1400b6052  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1400b6057  nop
0x1400b6058  lea     rcx, [rbp+3Fh+ppszPathOut]
0x1400b605c  call    ??1?$VmLocalPtr@U_TOKEN_PRIMARY_GROUP@@@Vml@@QEAA@XZ; Vml::VmLocalPtr<_TOKEN_PRIMARY_GROUP>::~VmLocalPtr<_TOKEN_PRIMARY_GROUP>(void)
0x1400b6061  jmp     short loc_1400B608C
0x1400b6063  mov     rdx, [rdi]
0x1400b6066  lea     rcx, [rsp+130h+pszPathOut]; pszPathOut
0x1400b606b  call    ?GetUtilityVmBugcheckSavedStateFilename@HyperVContainer@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; ComputeService::HyperVContainer::GetUtilityVmBugcheckSavedStateFilename(_GUID const &)
0x1400b6070  mov     rcx, [rdi]
0x1400b6073  add     rcx, 3E8h
0x1400b607a  mov     rdx, rax
0x1400b607d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400b6082  lea     rcx, [rsp+130h+pszPathOut]; this
0x1400b6087  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400b608c  mov     rcx, [rdi]
0x1400b608f  add     rcx, 3E8h
0x1400b6096  cmp     qword ptr [rcx+18h], 7
0x1400b609b  jbe     short loc_1400B60A0
0x1400b609d  mov     rcx, [rcx]; pszPath
0x1400b60a0  call    cs:__imp_PathFileExistsW
0x1400b60a7  nop     dword ptr [rax+rax+00h]
0x1400b60ac  test    eax, eax
0x1400b60ae  jz      short loc_1400B60CA
0x1400b60b0  mov     rdx, [rdi]; unsigned __int16 *
0x1400b60b3  lea     rcx, [rdx+3E8h]
0x1400b60ba  cmp     qword ptr [rcx+18h], 7
0x1400b60bf  jbe     short loc_1400B60C4
0x1400b60c1  mov     rcx, [rcx]; lpFileName
0x1400b60c4  call    ?GrantVmAccess@Vmwp@ComputeService@@YAXPEBGAEBU_GUID@@@Z; ComputeService::Vmwp::GrantVmAccess(ushort const *,_GUID const &)
0x1400b60c9  nop
0x1400b60ca  lea     rcx, [rbp+3Fh+var_68]; this
0x1400b60ce  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400b60d3  nop
0x1400b60d4  mov     rax, rdi
0x1400b60d7  mov     rcx, [rbp+3Fh+var_48]
0x1400b60db  xor     rcx, rsp; StackCookie
0x1400b60de  call    __security_check_cookie
0x1400b60e3  add     rsp, 0F8h
0x1400b60ea  pop     r15
0x1400b60ec  pop     r14
0x1400b60ee  pop     r13
0x1400b60f0  pop     r12
0x1400b60f2  pop     rdi
0x1400b60f3  pop     rsi
0x1400b60f4  pop     rbx
0x1400b60f5  pop     rbp
0x1400b60f6  retn
```
