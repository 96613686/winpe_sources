# ComputeService::Management::Details::PrepareJobForWorkerProcess(std::shared_ptr<ComputeService::Management::ComputeSystem> const &,Schema::ComputeSystem const &,_GUID const &,ComputeService::Management::ActiveStateOperation &,void *)

- ea: `0x1401d2cec`
- end: `0x1401d30e8`
- name: `?PrepareJobForWorkerProcess@Details@Management@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@AEBUComputeSystem@Schema@@AEBU_GUID@@AEAVActiveStateOperation@23@PEAX@Z`
- size: `1020`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1401cdb60`

## callees

- `0x1400142a0`
- `0x140017040`
- `0x140024030`
- `0x1400421f0`
- `0x140042468`
- `0x14004249c`
- `0x140057fec`
- `0x140080180`
- `0x14008a83c`
- `0x1400ad53c`
- `0x1400b2a44`
- `0x1400c40e0`
- `0x140106acc`
- `0x1401332f0`
- `0x140142dac`
- `0x14016f814`
- `0x140171f6c`
- `0x1401bc7f8`
- `0x1401d2cec`
- `0x1402179ec`
- `0x140217ad4`
- `0x140217e88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401d2d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401d2d9f`
- `ntdll!RtlInitUnicodeString` at `0x1401d2e1d`
- `ntdll!RtlInitUnicodeString` at `0x1401d2e1d`
- `ntdll!NtOpenJobObject` at `0x1401d2e60`
- `ntdll!NtOpenJobObject` at `0x1401d2e60`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1401d2eb3`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1401d2eb3`
- `vid!VidQueryResourcePartitionComponent` at `0x1401d2d8b`
- `vid!VidQueryResourcePartitionComponent` at `0x1401d2d8b`

## string_xrefs

- `0x1401d3053`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x1401d3068`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x1401d307a`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x1401d3092`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x1401d30a4`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x1401d30d6`: `onecore\vm\compute\management\orchestration\virtualmachine\virtualmachineorchestrator.cpp`
- `0x1401d3047`: `Worker Job object cannot be configured if a resource partition worker job is also present.`
- `0x1401d30ca`: `Worker Job object cannot be configured if a resource partition worker job is also present.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
ComputeService::JobUtilities **__fastcall ComputeService::Management::Details::PrepareJobForWorkerProcess(
        ComputeService::JobUtilities **a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  const char *v10; // r9
  unsigned __int64 v11; // rax
  __int64 *v12; // rdx
  const WCHAR *v13; // rdx
  void **v14; // rax
  NTSTATUS v15; // eax
  HANDLE JobObjectW; // rax
  const char *v17; // r9
  __int64 v18; // rax
  __int64 v19; // rax
  const struct Schema::VirtualMachines::SiloSettings *v20; // r8
  char v21; // al
  void *v22; // rax
  int v23; // r8d
  int v24; // r9d
  unsigned int v26; // eax
  unsigned int v27; // eax
  int v28; // [rsp+20h] [rbp-B9h]
  char *v29; // [rsp+28h] [rbp-B1h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-89h] BYREF
  __int64 v31; // [rsp+80h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v33[16]; // [rsp+A8h] [rbp-31h] BYREF
  _BYTE v34[32]; // [rsp+B8h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+4Fh]

  *a1 = 0;
  v31 = 0;
  if ( !*(_BYTE *)(a3 + 4144) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37E,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
      (const char *)0x8000FFFFLL,
      v28);
  if ( a6 != -1 )
  {
    *(_DWORD *)&DestinationString.Length = 5;
    LODWORD(v29) = 8;
    v28 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v31);
    if ( !(unsigned int)VidQueryResourcePartitionComponent(a6, 1, &DestinationString) && GetLastError() != 1168 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x390,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        v10);
  }
  ComputeService::Management::ActiveStateOperation::RetrieveJobResource(a5, v33, L"hcs:/VirtualMachine/WorkerJob");
  v11 = v31 - 1;
  if ( v33[8] )
  {
    if ( v11 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v27 = wil::verify_BOOL<int>(2147942487LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x399,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)v27,
        (int)"Worker Job object cannot be configured if a resource partition worker job is also present.",
        v29);
    }
    v12 = (__int64 *)v33;
    goto LABEL_16;
  }
  if ( *(_QWORD *)(a3 + 4176) )
  {
    if ( v11 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v26 = wil::verify_BOOL<int>(2147942487LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x3A3,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)v26,
        (int)"Worker Job object cannot be configured if a resource partition worker job is also present.",
        v29);
    }
    DestinationString = 0;
    v13 = (const WCHAR *)(a3 + 4160);
    if ( *(_QWORD *)(a3 + 4184) > 7u )
      v13 = *(const WCHAR **)v13;
    RtlInitUnicodeString(&DestinationString, v13);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.Attributes, 0, 24);
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    v14 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(a1);
    v15 = NtOpenJobObject(v14, 0x1F003Fu, &ObjectAttributes);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x3B5,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
        (const char *)(unsigned int)v15,
        v28);
  }
  else
  {
    if ( v11 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v12 = &v31;
LABEL_16:
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        a1,
        v12);
      goto LABEL_35;
    }
    if ( !*(_BYTE *)(a3 + 4144) )
      __fastfail(5u);
    if ( *(_BYTE *)(a3 + 3328) )
    {
      v18 = Vml::GuidToString(&ObjectAttributes, a4, 0);
      ComputeService::JobUtilities::GetWorkerProcessSiloJobName(v34, v18);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&ObjectAttributes);
      v19 = ComputeService::JobUtilities::CreateNamedWorkerProcessSiloJobObject(&DestinationString, v34);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        a1,
        v19);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&DestinationString);
      if ( !*(_BYTE *)(a3 + 4144) )
        __fastfail(5u);
      v21 = *(_BYTE *)(a3 + 3328);
      if ( !v21 )
        __fastfail(5u);
      if ( *(_QWORD *)(a3 + 3256) )
      {
        ComputeService::JobUtilities::CreateSiloForIsolatedWorkerProcess(*a1, (void *)(a3 + 3240), v20);
        v21 = *(_BYTE *)(a3 + 3328);
      }
      if ( !*(_BYTE *)(a3 + 4144) )
        __fastfail(5u);
      if ( !v21 )
        __fastfail(5u);
      if ( *(_BYTE *)(a3 + 3272) )
      {
        std::wstring::wstring(&DestinationString);
        std::wstring::operator=(&DestinationString, v34);
        v22 = (void *)Marshal::ToJson<Compute::System::SiloJobCreatedNotification &,>(
                        &ObjectAttributes,
                        &DestinationString);
        ComputeService::ComputeSystemUtilities::NotifyComputeSystem(*a2, 10, v23, v24, 0, v22);
        Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&ObjectAttributes);
        Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)&DestinationString);
      }
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v34);
    }
    else
    {
      JobObjectW = CreateJobObjectW(0, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        a1,
        JobObjectW);
      if ( (((unsigned __int64)*a1 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x3C1,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\virtualmachine\\virtualmachineorchestrator.cpp",
          v17);
    }
  }
LABEL_35:
  std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,0>::~_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,0>(v33);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v31);
  return a1;
}

```

## disassembly

```asm
0x1401d2cec  push    rbp
0x1401d2cee  push    rbx
0x1401d2cef  push    rsi
0x1401d2cf0  push    rdi
0x1401d2cf1  push    r12
0x1401d2cf3  push    r13
0x1401d2cf5  push    r14
0x1401d2cf7  push    r15
0x1401d2cf9  lea     rbp, [rsp-0Fh]
0x1401d2cfe  sub     rsp, 0E8h
0x1401d2d05  mov     rax, cs:__security_cookie
0x1401d2d0c  xor     rax, rsp
0x1401d2d0f  mov     [rbp+47h+var_48], rax
0x1401d2d13  mov     r15, r9
0x1401d2d16  mov     rbx, r8
0x1401d2d19  mov     r12, rdx
0x1401d2d1c  mov     rdi, rcx
0x1401d2d1f  mov     [rsp+120h+var_D8], rcx
0x1401d2d24  mov     r14, [rbp+47h+arg_20]
0x1401d2d28  mov     rsi, [rbp+47h+arg_28]
0x1401d2d2c  xor     r13d, r13d
0x1401d2d2f  mov     [rsp+120h+var_E0], r13d
0x1401d2d34  mov     [rcx], r13
0x1401d2d37  mov     [rsp+120h+var_E0], 1
0x1401d2d3f  mov     [rbp+47h+var_A0], r13
0x1401d2d43  mov     rcx, [rbp+4Fh]; this
0x1401d2d47  cmp     [r8+1030h], r13b
0x1401d2d4e  jz      loc_1401D308C
0x1401d2d54  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1401d2d58  jz      short loc_1401D2DB6
0x1401d2d5a  mov     dword ptr [rbp+47h+DestinationString.Length], 5
0x1401d2d61  lea     rcx, [rbp+47h+var_A0]
0x1401d2d65  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1401d2d6a  mov     [rsp+120h+var_F0], r13
0x1401d2d6f  mov     dword ptr [rsp+120h+var_F8], 8; char *
0x1401d2d77  mov     qword ptr [rsp+120h+var_100], rax; int
0x1401d2d7c  lea     r9d, [r13+4]
0x1401d2d80  lea     r8, [rbp+47h+DestinationString]
0x1401d2d84  lea     edx, [r13+1]
0x1401d2d88  mov     rcx, rsi
0x1401d2d8b  call    cs:__imp_VidQueryResourcePartitionComponent
0x1401d2d92  nop     dword ptr [rax+rax+00h]
0x1401d2d97  test    eax, eax
0x1401d2d99  jnz     short loc_1401D2DB6
0x1401d2d9b  mov     rsi, [rbp+4Fh]
0x1401d2d9f  call    cs:__imp_GetLastError
0x1401d2da6  nop     dword ptr [rax+rax+00h]
0x1401d2dab  cmp     eax, 490h
0x1401d2db0  jnz     loc_1401D30A4
0x1401d2db6  lea     r8, aHcsVirtualmach_1; "hcs:/VirtualMachine/WorkerJob"
0x1401d2dbd  lea     rdx, [rbp+47h+var_78]
0x1401d2dc1  mov     rcx, r14
0x1401d2dc4  call    ?RetrieveJobResource@ActiveStateOperation@Management@ComputeService@@QEAA?AV?$optional@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@PEBG@Z; ComputeService::Management::ActiveStateOperation::RetrieveJobResource(ushort const *)
0x1401d2dc9  nop
0x1401d2dca  mov     rax, [rbp+47h+var_A0]
0x1401d2dce  dec     rax
0x1401d2dd1  cmp     [rbp+47h+var_70], r13b
0x1401d2dd5  jz      short loc_1401D2DEA
0x1401d2dd7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401d2ddb  jbe     loc_1401D30B9
0x1401d2de1  lea     rdx, [rbp+47h+var_78]
0x1401d2de5  jmp     loc_1401D2E87
0x1401d2dea  cmp     [rbx+1050h], r13
0x1401d2df1  jz      loc_1401D2E7D
0x1401d2df7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401d2dfb  jbe     loc_1401D3036
0x1401d2e01  xorps   xmm0, xmm0
0x1401d2e04  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x1401d2e08  lea     rdx, [rbx+1040h]
0x1401d2e0f  cmp     qword ptr [rdx+18h], 7
0x1401d2e14  jbe     short loc_1401D2E19
0x1401d2e16  mov     rdx, [rdx]; SourceString
0x1401d2e19  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x1401d2e1d  call    cs:__imp_RtlInitUnicodeString
0x1401d2e24  nop     dword ptr [rax+rax+00h]
0x1401d2e29  mov     qword ptr [rsp+120h+ObjectAttributes.Length], 30h ; '0'
0x1401d2e32  mov     qword ptr [rbp+47h+ObjectAttributes.Attributes], r13
0x1401d2e36  mov     [rsp+120h+ObjectAttributes.RootDirectory], r13
0x1401d2e3b  lea     rax, [rbp+47h+DestinationString]
0x1401d2e3f  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x1401d2e43  xorps   xmm0, xmm0
0x1401d2e46  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401d2e4b  mov     rcx, rdi
0x1401d2e4e  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1401d2e53  lea     r8, [rsp+120h+ObjectAttributes]; ObjectAttributes
0x1401d2e58  mov     edx, 1F003Fh; DesiredAccess
0x1401d2e5d  mov     rcx, rax; JobHandle
0x1401d2e60  call    cs:__imp_NtOpenJobObject
0x1401d2e67  nop     dword ptr [rax+rax+00h]
0x1401d2e6c  mov     rcx, [rbp+4Fh]; this
0x1401d2e70  test    eax, eax
0x1401d2e72  js      loc_1401D3065
0x1401d2e78  jmp     loc_1401D2FFF
0x1401d2e7d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401d2e81  ja      short loc_1401D2E94
0x1401d2e83  lea     rdx, [rbp+47h+var_A0]
0x1401d2e87  mov     rcx, rdi
0x1401d2e8a  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1401d2e8f  jmp     loc_1401D2FFF
0x1401d2e94  mov     esi, 5
0x1401d2e99  cmp     [rbx+1030h], r13b
0x1401d2ea0  jnz     short loc_1401D2EA6
0x1401d2ea2  mov     ecx, esi
0x1401d2ea4  int     29h; Win8: RtlFailFast(ecx)
0x1401d2ea6  cmp     [rbx+0D00h], r13b
0x1401d2ead  jnz     short loc_1401D2EEA
0x1401d2eaf  xor     edx, edx; lpName
0x1401d2eb1  xor     ecx, ecx; lpJobAttributes
0x1401d2eb3  call    cs:__imp_CreateJobObjectW
0x1401d2eba  nop     dword ptr [rax+rax+00h]
0x1401d2ebf  mov     rdx, rax
0x1401d2ec2  mov     rcx, rdi
0x1401d2ec5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1401d2eca  mov     rax, [rdi]
0x1401d2ecd  inc     rax
0x1401d2ed0  test    rax, 0FFFFFFFFFFFFFFFEh
0x1401d2ed6  setz    al
0x1401d2ed9  mov     rcx, [rbp+4Fh]; this
0x1401d2edd  test    al, al
0x1401d2edf  jnz     loc_1401D307A
0x1401d2ee5  jmp     loc_1401D2FFF
0x1401d2eea  xor     r8d, r8d
0x1401d2eed  mov     rdx, r15
0x1401d2ef0  lea     rcx, [rsp+120h+ObjectAttributes]
0x1401d2ef5  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1401d2efa  nop
0x1401d2efb  mov     rdx, rax
0x1401d2efe  lea     rcx, [rbp+47h+var_68]
0x1401d2f02  call    ?GetWorkerProcessSiloJobName@JobUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; ComputeService::JobUtilities::GetWorkerProcessSiloJobName(std::wstring const &)
0x1401d2f07  nop
0x1401d2f08  lea     rcx, [rsp+120h+ObjectAttributes]; this
0x1401d2f0d  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1401d2f12  lea     rdx, [rbp+47h+var_68]
0x1401d2f16  lea     rcx, [rbp+47h+DestinationString]
0x1401d2f1a  call    ?CreateNamedWorkerProcessSiloJobObject@JobUtilities@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::JobUtilities::CreateNamedWorkerProcessSiloJobObject(std::wstring const &)
0x1401d2f1f  mov     rdx, rax
0x1401d2f22  mov     rcx, rdi
0x1401d2f25  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1401d2f2a  lea     rcx, [rbp+47h+DestinationString]; void *
0x1401d2f2e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1401d2f33  mov     dl, [rbx+1030h]
0x1401d2f39  test    dl, dl
0x1401d2f3b  jnz     short loc_1401D2F42
0x1401d2f3d  mov     rcx, rsi
0x1401d2f40  int     29h; Win8: RtlFailFast(ecx)
0x1401d2f42  mov     al, [rbx+0D00h]
0x1401d2f48  test    al, al
0x1401d2f4a  jnz     short loc_1401D2F51
0x1401d2f4c  mov     rcx, rsi
0x1401d2f4f  int     29h; Win8: RtlFailFast(ecx)
0x1401d2f51  cmp     [rbx+0CB8h], r13
0x1401d2f58  jz      short loc_1401D2F81
0x1401d2f5a  test    dl, dl
0x1401d2f5c  jnz     short loc_1401D2F63
0x1401d2f5e  mov     rcx, rsi
0x1401d2f61  int     29h; Win8: RtlFailFast(ecx)
0x1401d2f63  lea     rdx, [rbx+0CA8h]; void *
0x1401d2f6a  test    al, al
0x1401d2f6c  jnz     short loc_1401D2F73
0x1401d2f6e  mov     rcx, rsi
0x1401d2f71  int     29h; Win8: RtlFailFast(ecx)
0x1401d2f73  mov     rcx, [rdi]; this
0x1401d2f76  call    ?CreateSiloForIsolatedWorkerProcess@JobUtilities@ComputeService@@YAXPEAXAEBUSiloSettings@VirtualMachines@Schema@@@Z; ComputeService::JobUtilities::CreateSiloForIsolatedWorkerProcess(void *,Schema::VirtualMachines::SiloSettings const &)
0x1401d2f7b  mov     al, [rbx+0D00h]
0x1401d2f81  cmp     [rbx+1030h], r13b
0x1401d2f88  jnz     short loc_1401D2F8F
0x1401d2f8a  mov     rcx, rsi
0x1401d2f8d  int     29h; Win8: RtlFailFast(ecx)
0x1401d2f8f  test    al, al
0x1401d2f91  jnz     short loc_1401D2F98
0x1401d2f93  mov     rcx, rsi
0x1401d2f96  int     29h; Win8: RtlFailFast(ecx)
0x1401d2f98  cmp     [rbx+0CC8h], r13b
0x1401d2f9f  jz      short loc_1401D2FF5
0x1401d2fa1  lea     rcx, [rbp+47h+DestinationString]; void *
0x1401d2fa5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1401d2faa  nop
0x1401d2fab  lea     rdx, [rbp+47h+var_68]
0x1401d2faf  lea     rcx, [rbp+47h+DestinationString]
0x1401d2fb3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1401d2fb8  lea     rdx, [rbp+47h+DestinationString]
0x1401d2fbc  lea     rcx, [rsp+120h+ObjectAttributes]
0x1401d2fc1  call    ??$ToJson@AEAUSiloJobCreatedNotification@System@Compute@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUSiloJobCreatedNotification@System@Compute@@W4MarshalFlags@0@@Z; Marshal::ToJson<Compute::System::SiloJobCreatedNotification &,>(Compute::System::SiloJobCreatedNotification &,Marshal::MarshalFlags)
0x1401d2fc6  nop
0x1401d2fc7  mov     [rsp+120h+var_F8], rax; void *
0x1401d2fcc  mov     [rsp+120h+var_100], r13d; int
0x1401d2fd1  mov     edx, 0Ah; int
0x1401d2fd6  mov     rcx, [r12]; int
0x1401d2fda  call    ?NotifyComputeSystem@ComputeSystemUtilities@ComputeService@@YAXPEAVComputeSystem@Management@2@W4NotificationType@System@Compute@@W4ActiveOperation@67@_KJ$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::ComputeSystemUtilities::NotifyComputeSystem(ComputeService::Management::ComputeSystem *,Compute::System::NotificationType,Compute::System::ActiveOperation,unsigned __int64,long,std::wstring &&)
0x1401d2fdf  nop
0x1401d2fe0  lea     rcx, [rsp+120h+ObjectAttributes]; this
0x1401d2fe5  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1401d2fea  nop
0x1401d2feb  lea     rcx, [rbp+47h+DestinationString]; this
0x1401d2fef  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1401d2ff4  nop
0x1401d2ff5  lea     rcx, [rbp+47h+var_68]; this
0x1401d2ff9  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1401d2ffe  nop
0x1401d2fff  lea     rcx, [rbp+47h+var_78]
0x1401d3003  call    ??1?$_Optional_destruct_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,0>::~_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,0>(void)
0x1401d3008  nop
0x1401d3009  lea     rcx, [rbp+47h+var_A0]; void *
0x1401d300d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1401d3012  mov     rax, rdi
0x1401d3015  mov     rcx, [rbp+47h+var_48]
0x1401d3019  xor     rcx, rsp; StackCookie
0x1401d301c  call    __security_check_cookie
0x1401d3021  add     rsp, 0E8h
0x1401d3028  pop     r15
0x1401d302a  pop     r14
0x1401d302c  pop     r13
0x1401d302e  pop     r12
0x1401d3030  pop     rdi
0x1401d3031  pop     rsi
0x1401d3032  pop     rbx
0x1401d3033  pop     rbp
0x1401d3034  retn
0x1401d3036  mov     ecx, 80070057h
0x1401d303b  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x1401d3040  mov     r9d, eax; char *
0x1401d3043  mov     rcx, [rbp+4Fh]; this
0x1401d3047  lea     rax, aWorkerJobObjec; "Worker Job object cannot be configured "...
0x1401d304e  mov     qword ptr [rsp+120h+var_100], rax; int
0x1401d3053  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x1401d305a  mov     edx, 3A3h; void *
0x1401d305f  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1401d3065  mov     r9d, eax; char *
0x1401d3068  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x1401d306f  mov     edx, 3B5h; void *
0x1401d3074  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1401d307a  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x1401d3081  mov     edx, 3C1h; void *
0x1401d3086  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401d308c  mov     r9d, 8000FFFFh; char *
0x1401d3092  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x1401d3099  mov     edx, 37Eh; void *
0x1401d309e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401d30a4  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x1401d30ab  mov     edx, 390h; void *
0x1401d30b0  mov     rcx, rsi; this
0x1401d30b3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1401d30b9  mov     ecx, 80070057h
0x1401d30be  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x1401d30c3  mov     r9d, eax; char *
0x1401d30c6  mov     rcx, [rbp+4Fh]; this
0x1401d30ca  lea     rax, aWorkerJobObjec; "Worker Job object cannot be configured "...
0x1401d30d1  mov     qword ptr [rsp+120h+var_100], rax; int
0x1401d30d6  lea     r8, aOnecoreVmCompu_36; "onecore\\vm\\compute\\management\\orche"...
0x1401d30dd  mov     edx, 399h; void *
0x1401d30e2  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
