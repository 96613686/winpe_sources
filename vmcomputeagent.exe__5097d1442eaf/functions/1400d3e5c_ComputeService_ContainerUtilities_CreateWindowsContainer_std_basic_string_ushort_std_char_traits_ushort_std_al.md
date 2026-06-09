# ComputeService::ContainerUtilities::CreateWindowsContainer(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Schema::Containers::Definition::Container &,ComputeService::ContainerUtilities::WindowsContainerFlags,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::optional<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>)

- ea: `0x1400d3e5c`
- end: `0x1400d435c`
- name: `?CreateWindowsContainer@ContainerUtilities@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUContainer@Definition@Containers@Schema@@W4WindowsContainerFlags@12@0V?$optional@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@6@@Z`
- size: `1280`
- prototype: `__int64 __usercall@<rax>(PHANDLE JobHandle@<rcx>, RPC_WSTR StringUuid@<rdx>, void *@<r8>, __int64, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140087d00`
- `0x14009a630`

## callees

- `0x140005360`
- `0x140008760`
- `0x14000ea60`
- `0x14002c0a8`
- `0x140041b14`
- `0x140041d9c`
- `0x14004283c`
- `0x140044adc`
- `0x14008853c`
- `0x1400bfb14`
- `0x1400d14c8`
- `0x1400d337c`
- `0x1400d33c0`
- `0x1400d3e5c`
- `0x1400d4d44`
- `0x1400d6908`
- `0x1400dbe7c`
- `0x1400f4ea0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d4008`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d40bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d4165`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d4008`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d40bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d4165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d40ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d4152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d40ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d4152`
- `ntdll!NtSetInformationJobObject` at `0x1400d41e3`
- `ntdll!NtSetInformationJobObject` at `0x1400d41e3`
- `ntdll!NtCreateJobObject` at `0x1400d417f`
- `ntdll!NtCreateJobObject` at `0x1400d417f`
- `ntdll!RtlInitUnicodeString` at `0x1400d4075`
- `ntdll!RtlInitUnicodeString` at `0x1400d4118`
- `ntdll!RtlInitUnicodeString` at `0x1400d4075`
- `ntdll!RtlInitUnicodeString` at `0x1400d4118`
- `ntdll!NtOpenJobObject` at `0x1400d40d9`
- `ntdll!NtOpenJobObject` at `0x1400d40d9`
- `ntdll!NtQueryObject` at `0x1400d3f87`
- `ntdll!NtQueryObject` at `0x1400d3f87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d4000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d40b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d415d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d42a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d4000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d40b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d415d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d42a8`
- `container!WcSetRegistryFlushState` at `0x1400d4235`
- `container!WcSetRegistryFlushState` at `0x1400d4235`

## string_xrefs

- `0x1400d42db`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d42f0`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d4308`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d4320`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d4335`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d434a`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
PHANDLE __fastcall ComputeService::ContainerUtilities::CreateWindowsContainer(
        PHANDLE JobHandle,
        unsigned __int16 *StringUuid,
        void *a3,
        char a4,
        __int64 a5,
        __int64 a6)
{
  void *v7; // r12
  const wchar_t **v10; // rbx
  NTSTATUS Object; // eax
  unsigned int v12; // r8d
  size_t v13; // r8
  const wchar_t *v14; // rdx
  bool v15; // zf
  char v16; // al
  HANDLE v17; // r12
  void *v18; // r14
  DWORD LastError; // ebx
  const struct _GUID *v20; // r9
  const WCHAR *v21; // rdx
  void *v22; // r14
  DWORD v23; // ebx
  NTSTATUS v24; // eax
  const WCHAR *v25; // rdx
  void *v26; // r14
  DWORD v27; // ebx
  NTSTATUS v28; // eax
  NTSTATUS v29; // eax
  const struct Schema::Containers::Definition::Container *v30; // r8
  bool v31; // r9
  int v32; // eax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  struct _OBJECT_ATTRIBUTES ObjectInformation; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h]
  char v37; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String2[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v41; // [rsp+A8h] [rbp-58h]
  __int128 v42; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v43; // [rsp+C0h] [rbp-40h]
  __int128 v44; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v45; // [rsp+D8h] [rbp-28h]
  __int128 v46; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v47; // [rsp+F0h] [rbp-10h]
  __int128 v48; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v49; // [rsp+108h] [rbp+8h]
  struct _UNICODE_STRING JobInformation; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v7 = a3;
  *(_QWORD *)&DestinationString.Length = a3;
  v36 = a6;
  *JobHandle = 0;
  v37 = 0;
  v48 = 0;
  v49 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v48, 8);
  v46 = 0;
  v47 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v46, 9);
  v44 = 0;
  v45 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v44, 17);
  v42 = 0;
  v43 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v42, 18);
  ComputeService::ContainerUtilities::GetWindowsContainerJobName(String2, StringUuid);
  if ( *(_BYTE *)(a6 + 8) )
  {
    memset(&ObjectInformation, 0, 24);
    std::vector<unsigned char>::vector<unsigned char>(&ObjectInformation, 2 * v40 + 18);
    v10 = *(const wchar_t ***)&ObjectInformation.Length;
    Object = NtQueryObject(
               *(HANDLE *)a6,
               ObjectNameInformation,
               *(PVOID *)&ObjectInformation.Length,
               LODWORD(ObjectInformation.RootDirectory) - ObjectInformation.Length,
               0);
    if ( Object >= 0 )
    {
      v13 = *(unsigned __int16 *)v10;
      if ( v13 == 2 * v40 )
      {
        v14 = (const wchar_t *)String2;
        if ( v41 > 7 )
          v14 = String2[0];
        v15 = wcsncmp_0(v10[1], v14, v13) == 0;
        v16 = 0;
        if ( v15 )
          goto LABEL_9;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0x261,
        v12,
        (const char *)(unsigned int)Object,
        ReturnLength);
    }
    v16 = 1;
LABEL_9:
    if ( v16 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x261,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)0x80070057LL,
        ReturnLength);
    if ( JobHandle != (PHANDLE)a6 )
    {
      v17 = *(HANDLE *)a6;
      v18 = *JobHandle;
      if ( (char *)*JobHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v18);
        SetLastError(LastError);
      }
      *JobHandle = v17;
      *(_QWORD *)a6 = 0;
      v7 = *(void **)&DestinationString.Length;
    }
    std::vector<unsigned char>::~vector<unsigned char>(&ObjectInformation);
    goto LABEL_29;
  }
  if ( *(_QWORD *)(a5 + 16) )
  {
    if ( (unsigned __int8)std::operator!=<unsigned short>(String2, a5) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x268,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)0x80070057LL,
        ReturnLength);
    memset(&ObjectInformation, 0, sizeof(ObjectInformation));
    DestinationString = 0;
    v21 = (const WCHAR *)String2;
    if ( v41 > 7 )
      v21 = String2[0];
    RtlInitUnicodeString(&DestinationString, v21);
    ObjectInformation.Length = 48;
    ObjectInformation.RootDirectory = 0;
    ObjectInformation.Attributes = 0;
    ObjectInformation.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectInformation.SecurityDescriptor = 0;
    v22 = *JobHandle;
    if ( (char *)*JobHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v23 = GetLastError();
      CloseHandle(v22);
      SetLastError(v23);
    }
    *JobHandle = 0;
    v24 = NtOpenJobObject(JobHandle, 0x1F003Fu, &ObjectInformation);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x270,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)(unsigned int)v24,
        ReturnLength);
  }
  else
  {
    memset(&ObjectInformation, 0, sizeof(ObjectInformation));
    DestinationString = 0;
    v25 = (const WCHAR *)String2;
    if ( v41 > 7 )
      v25 = String2[0];
    RtlInitUnicodeString(&DestinationString, v25);
    ObjectInformation.Length = 48;
    ObjectInformation.RootDirectory = 0;
    ObjectInformation.Attributes = 16;
    ObjectInformation.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectInformation.SecurityDescriptor = 0;
    v26 = *JobHandle;
    if ( (char *)*JobHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v27 = GetLastError();
      CloseHandle(v26);
      SetLastError(v27);
    }
    *JobHandle = 0;
    v28 = NtCreateJobObject(JobHandle, 0x1F003Fu, &ObjectInformation);
    if ( v28 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x27A,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)(unsigned int)v28,
        ReturnLength);
    v37 = 1;
  }
LABEL_29:
  *(_QWORD *)&ObjectInformation.Length = &v37;
  ObjectInformation.RootDirectory = JobHandle;
  LOWORD(ObjectInformation.ObjectName) = 257;
  if ( *((_QWORD *)StringUuid + 3) > 7u )
    StringUuid = *(unsigned __int16 **)StringUuid;
  ComputeService::Management::ConvertIdToGuid(
    (UUID *)&DestinationString,
    StringUuid,
    &`ComputeService::Management::GetComputeSystemGuid'::`2'::c_ComputeSystemSeedId,
    v20);
  JobInformation = DestinationString;
  v29 = NtSetInformationJobObject(*JobHandle, MaxJobObjectInfoClass|0x20, &JobInformation, 0x10u);
  if ( v29 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x28F,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
      (const char *)(unsigned int)v29,
      ReturnLength);
  ComputeService::ContainerDefinition::ResolveRuntimeAliases(v7, *JobHandle, String2);
  LOBYTE(v30) = !(a4 & 1);
  ComputeService::JobUtilities::ConvertJobObjectToContainer((ComputeService::JobUtilities *)*JobHandle, v7, v30, v31);
  if ( (a4 & 2) != 0 && (a4 & 1) == 0 )
  {
    *(_QWORD *)&DestinationString.Length = JobHandle;
    LOWORD(DestinationString.Buffer) = 257;
    v32 = WcSetRegistryFlushState(*JobHandle, 0);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A1,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)(unsigned int)v32,
        ReturnLength);
    BYTE1(DestinationString.Buffer) = a4 & 1;
    wil::details::ScopeExitFnGuard__lambda_db21ce235646f5ac0b140d27d935719e___::operator()(&DestinationString);
  }
  BYTE1(ObjectInformation.ObjectName) = 0;
  wil::details::ScopeExitFnGuard__lambda_f12084f5d33c28d2c6b46bb0592d2f62___::operator()(&ObjectInformation);
  std::wstring::~wstring(String2);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v42);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v44);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v46);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v48);
  if ( *(_BYTE *)(a6 + 8) && (unsigned __int64)(*(_QWORD *)a6 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(*(HANDLE *)a6);
  return JobHandle;
}

```

## disassembly

```asm
0x1400d3e5c  mov     [rsp-8+arg_18], rbx
0x1400d3e61  push    rbp
0x1400d3e62  push    rsi
0x1400d3e63  push    rdi
0x1400d3e64  push    r12
0x1400d3e66  push    r13
0x1400d3e68  push    r14
0x1400d3e6a  push    r15
0x1400d3e6c  lea     rbp, [rsp-30h]
0x1400d3e71  sub     rsp, 130h
0x1400d3e78  mov     rax, cs:__security_cookie
0x1400d3e7f  xor     rax, rsp
0x1400d3e82  mov     [rbp+60h+var_40], rax
0x1400d3e86  mov     r13d, r9d
0x1400d3e89  mov     r12, r8
0x1400d3e8c  mov     qword ptr [rbp+60h+DestinationString.Length], r8
0x1400d3e90  mov     r15, rdx
0x1400d3e93  mov     rdi, rcx
0x1400d3e96  mov     rbx, [rbp+60h+arg_20]
0x1400d3e9d  mov     [rsp+160h+var_128], rcx
0x1400d3ea2  mov     rsi, [rbp+60h+arg_28]
0x1400d3ea9  mov     [rsp+160h+var_F0], rsi
0x1400d3eae  xor     r14d, r14d
0x1400d3eb1  mov     [rsp+160h+var_130], r14d
0x1400d3eb6  mov     [rcx], r14
0x1400d3eb9  mov     [rsp+160h+var_130], 1
0x1400d3ec1  mov     [rsp+160h+var_E8], r14b
0x1400d3ec6  xorps   xmm0, xmm0
0x1400d3ec9  xor     eax, eax
0x1400d3ecb  movups  [rbp+60h+var_68], xmm0
0x1400d3ecf  mov     [rbp+60h+var_58], rax
0x1400d3ed3  lea     edx, [rax+8]; int
0x1400d3ed6  lea     rcx, [rbp+60h+var_68]; this
0x1400d3eda  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1400d3edf  nop
0x1400d3ee0  xorps   xmm0, xmm0
0x1400d3ee3  xor     eax, eax
0x1400d3ee5  movups  [rbp+60h+var_80], xmm0
0x1400d3ee9  mov     [rbp+60h+var_70], rax
0x1400d3eed  lea     edx, [rax+9]; int
0x1400d3ef0  lea     rcx, [rbp+60h+var_80]; this
0x1400d3ef4  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1400d3ef9  nop
0x1400d3efa  xorps   xmm0, xmm0
0x1400d3efd  xor     eax, eax
0x1400d3eff  movups  [rbp+60h+var_98], xmm0
0x1400d3f03  mov     [rbp+60h+var_88], rax
0x1400d3f07  lea     edx, [rax+11h]; int
0x1400d3f0a  lea     rcx, [rbp+60h+var_98]; this
0x1400d3f0e  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1400d3f13  nop
0x1400d3f14  xorps   xmm0, xmm0
0x1400d3f17  xor     eax, eax
0x1400d3f19  movups  [rbp+60h+var_B0], xmm0
0x1400d3f1d  mov     [rbp+60h+var_A0], rax
0x1400d3f21  lea     edx, [rax+12h]; int
0x1400d3f24  lea     rcx, [rbp+60h+var_B0]; this
0x1400d3f28  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1400d3f2d  nop
0x1400d3f2e  mov     rdx, r15
0x1400d3f31  lea     rcx, [rbp+60h+String2]
0x1400d3f35  call    ?GetWindowsContainerJobName@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; ComputeService::ContainerUtilities::GetWindowsContainerJobName(std::wstring const &)
0x1400d3f3a  nop
0x1400d3f3b  cmp     [rsi+8], r14b
0x1400d3f3f  jz      loc_1400D402B
0x1400d3f45  xorps   xmm0, xmm0
0x1400d3f48  xor     eax, eax
0x1400d3f4a  movups  xmmword ptr [rsp+160h+ObjectInformation], xmm0
0x1400d3f4f  mov     qword ptr [rsp+160h+var_110], rax
0x1400d3f54  mov     rdx, [rbp+60h+var_C0]
0x1400d3f58  lea     rdx, ds:12h[rdx*2]
0x1400d3f60  lea     rcx, [rsp+160h+ObjectInformation]
0x1400d3f65  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1400d3f6a  nop
0x1400d3f6b  mov     rbx, [rsp+160h+ObjectInformation]
0x1400d3f70  mov     r9d, dword ptr [rsp+160h+ObjectInformation+8]
0x1400d3f75  sub     r9d, ebx; ObjectInformationLength
0x1400d3f78  mov     qword ptr [rsp+160h+ReturnLength], r14; int
0x1400d3f7d  mov     r8, rbx; ObjectInformation
0x1400d3f80  lea     edx, [r14+1]; ObjectInformationClass
0x1400d3f84  mov     rcx, [rsi]; Handle
0x1400d3f87  call    cs:__imp_NtQueryObject
0x1400d3f8d  mov     rcx, [rbp+68h]; this
0x1400d3f91  test    eax, eax
0x1400d3f93  jns     short loc_1400D3FA4
0x1400d3f95  mov     r9d, eax; char *
0x1400d3f98  mov     edx, 261h; void *
0x1400d3f9d  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1400d3fa2  jmp     short loc_1400D3FD2
0x1400d3fa4  movzx   r8d, word ptr [rbx]; MaxCount
0x1400d3fa8  mov     rax, [rbp+60h+var_C0]
0x1400d3fac  add     rax, rax
0x1400d3faf  cmp     r8, rax
0x1400d3fb2  jnz     short loc_1400D3FD2
0x1400d3fb4  lea     rdx, [rbp+60h+String2]
0x1400d3fb8  cmp     [rbp+60h+var_B8], 7
0x1400d3fbd  cmova   rdx, [rbp+60h+String2]; String2
0x1400d3fc2  mov     rcx, [rbx+8]; String1
0x1400d3fc6  call    wcsncmp_0
0x1400d3fcb  test    eax, eax
0x1400d3fcd  mov     al, r14b
0x1400d3fd0  jz      short loc_1400D3FD4
0x1400d3fd2  mov     al, 1
0x1400d3fd4  mov     rcx, [rbp+68h]; this
0x1400d3fd8  test    al, al
0x1400d3fda  jnz     loc_1400D4302
0x1400d3fe0  cmp     rdi, rsi
0x1400d3fe3  jz      short loc_1400D401C
0x1400d3fe5  mov     r12, [rsi]
0x1400d3fe8  mov     r14, [rdi]
0x1400d3feb  lea     rax, [r14-1]
0x1400d3fef  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d3ff3  ja      short loc_1400D400E
0x1400d3ff5  call    cs:__imp_GetLastError
0x1400d3ffb  mov     ebx, eax
0x1400d3ffd  mov     rcx, r14; hObject
0x1400d4000  call    cs:__imp_CloseHandle
0x1400d4006  mov     ecx, ebx; dwErrCode
0x1400d4008  call    cs:__imp_SetLastError
0x1400d400e  mov     [rdi], r12
0x1400d4011  mov     qword ptr [rsi], 0
0x1400d4018  mov     r12, qword ptr [rbp+60h+DestinationString.Length]
0x1400d401c  lea     rcx, [rsp+160h+ObjectInformation]
0x1400d4021  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1400d4026  jmp     loc_1400D4196
0x1400d402b  cmp     [rbx+10h], r14
0x1400d402f  jz      loc_1400D40F0
0x1400d4035  mov     rdx, rbx
0x1400d4038  lea     rcx, [rbp+60h+String2]
0x1400d403c  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x1400d4041  mov     rcx, [rbp+68h]; this
0x1400d4045  test    al, al
0x1400d4047  jnz     loc_1400D431A
0x1400d404d  xorps   xmm0, xmm0
0x1400d4050  movups  xmmword ptr [rsp+160h+ObjectInformation], xmm0
0x1400d4055  movups  [rsp+160h+var_110], xmm0
0x1400d405a  movups  [rsp+160h+var_100], xmm0
0x1400d405f  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x1400d4063  lea     rdx, [rbp+60h+String2]
0x1400d4067  cmp     [rbp+60h+var_B8], 7
0x1400d406c  cmova   rdx, [rbp+60h+String2]; SourceString
0x1400d4071  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x1400d4075  call    cs:__imp_RtlInitUnicodeString
0x1400d407b  mov     dword ptr [rsp+160h+ObjectInformation], 30h ; '0'
0x1400d4083  mov     [rsp+160h+ObjectInformation+8], r14
0x1400d4088  mov     dword ptr [rsp+160h+var_110+8], r14d
0x1400d408d  lea     rax, [rbp+60h+DestinationString]
0x1400d4091  mov     qword ptr [rsp+160h+var_110], rax
0x1400d4096  xorps   xmm0, xmm0
0x1400d4099  movdqu  [rsp+160h+var_100], xmm0
0x1400d409f  mov     r14, [rdi]
0x1400d40a2  lea     rax, [r14-1]
0x1400d40a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d40aa  ja      short loc_1400D40C5
0x1400d40ac  call    cs:__imp_GetLastError
0x1400d40b2  mov     ebx, eax
0x1400d40b4  mov     rcx, r14; hObject
0x1400d40b7  call    cs:__imp_CloseHandle
0x1400d40bd  mov     ecx, ebx; dwErrCode
0x1400d40bf  call    cs:__imp_SetLastError
0x1400d40c5  mov     qword ptr [rdi], 0
0x1400d40cc  lea     r8, [rsp+160h+ObjectInformation]; ObjectAttributes
0x1400d40d1  mov     edx, 1F003Fh; DesiredAccess
0x1400d40d6  mov     rcx, rdi; JobHandle
0x1400d40d9  call    cs:__imp_NtOpenJobObject
0x1400d40df  mov     rcx, [rbp+68h]; this
0x1400d40e3  test    eax, eax
0x1400d40e5  js      loc_1400D42ED
0x1400d40eb  jmp     loc_1400D4196
0x1400d40f0  xorps   xmm0, xmm0
0x1400d40f3  movups  xmmword ptr [rsp+160h+ObjectInformation], xmm0
0x1400d40f8  movups  [rsp+160h+var_110], xmm0
0x1400d40fd  movups  [rsp+160h+var_100], xmm0
0x1400d4102  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x1400d4106  lea     rdx, [rbp+60h+String2]
0x1400d410a  cmp     [rbp+60h+var_B8], 7
0x1400d410f  cmova   rdx, [rbp+60h+String2]; SourceString
0x1400d4114  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x1400d4118  call    cs:__imp_RtlInitUnicodeString
0x1400d411e  mov     dword ptr [rsp+160h+ObjectInformation], 30h ; '0'
0x1400d4126  mov     [rsp+160h+ObjectInformation+8], r14
0x1400d412b  mov     dword ptr [rsp+160h+var_110+8], 10h
0x1400d4133  lea     rax, [rbp+60h+DestinationString]
0x1400d4137  mov     qword ptr [rsp+160h+var_110], rax
0x1400d413c  xorps   xmm0, xmm0
0x1400d413f  movdqu  [rsp+160h+var_100], xmm0
0x1400d4145  mov     r14, [rdi]
0x1400d4148  lea     rax, [r14-1]
0x1400d414c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d4150  ja      short loc_1400D416B
0x1400d4152  call    cs:__imp_GetLastError
0x1400d4158  mov     ebx, eax
0x1400d415a  mov     rcx, r14; hObject
0x1400d415d  call    cs:__imp_CloseHandle
0x1400d4163  mov     ecx, ebx; dwErrCode
0x1400d4165  call    cs:__imp_SetLastError
0x1400d416b  mov     qword ptr [rdi], 0
0x1400d4172  lea     r8, [rsp+160h+ObjectInformation]; ObjectAttributes
0x1400d4177  mov     edx, 1F003Fh; DesiredAccess
0x1400d417c  mov     rcx, rdi; JobHandle
0x1400d417f  call    cs:__imp_NtCreateJobObject
0x1400d4185  mov     rcx, [rbp+68h]; this
0x1400d4189  test    eax, eax
0x1400d418b  js      loc_1400D4332
0x1400d4191  mov     [rsp+160h+var_E8], 1
0x1400d4196  lea     rax, [rsp+160h+var_E8]
0x1400d419b  mov     [rsp+160h+ObjectInformation], rax
0x1400d41a0  mov     [rsp+160h+ObjectInformation+8], rdi
0x1400d41a5  mov     word ptr [rsp+160h+var_110], 101h
0x1400d41ac  cmp     qword ptr [r15+18h], 7
0x1400d41b1  jbe     short loc_1400D41B6
0x1400d41b3  mov     r15, [r15]
0x1400d41b6  lea     r8, ?c_ComputeSystemSeedId@?1??GetComputeSystemGuid@Management@ComputeService@@YA?AU_GUID@@PEBG@Z@4U4@B; retstr
0x1400d41bd  mov     rdx, r15; StringUuid
0x1400d41c0  lea     rcx, [rbp+60h+DestinationString]; Uuid
0x1400d41c4  call    ?ConvertIdToGuid@Management@ComputeService@@YA?AU_GUID@@PEBGAEBU3@@Z; ComputeService::Management::ConvertIdToGuid(ushort const *,_GUID const &)
0x1400d41c9  movaps  xmm0, xmmword ptr [rbp+60h+DestinationString.Length]
0x1400d41cd  movdqa  [rbp+60h+JobInformation], xmm0
0x1400d41d2  mov     r9d, 10h; JobInformationLength
0x1400d41d8  lea     r8, [rbp+60h+JobInformation]; JobInformation
0x1400d41dc  lea     edx, [r9+1Ch]; JobInformationClass
0x1400d41e0  mov     rcx, [rdi]; JobHandle
0x1400d41e3  call    cs:__imp_NtSetInformationJobObject
0x1400d41e9  mov     rcx, [rbp+68h]; this
0x1400d41ed  test    eax, eax
0x1400d41ef  js      loc_1400D4347
0x1400d41f5  mov     bl, r13b
0x1400d41f8  and     bl, 1
0x1400d41fb  lea     r8, [rbp+60h+String2]
0x1400d41ff  mov     rdx, [rdi]
0x1400d4202  mov     rcx, r12
0x1400d4205  call    ?ResolveRuntimeAliases@ContainerDefinition@ComputeService@@YAXAEAUContainer@Definition@Containers@Schema@@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::ContainerDefinition::ResolveRuntimeAliases(Schema::Containers::Definition::Container &,void *,std::wstring const &)
0x1400d420a  mov     r8b, bl
0x1400d420d  xor     r8b, 1; struct Schema::Containers::Definition::Container *
0x1400d4211  mov     rdx, r12; void *
0x1400d4214  mov     rcx, [rdi]; this
0x1400d4217  call    ?ConvertJobObjectToContainer@JobUtilities@ComputeService@@YAXPEAXAEBUContainer@Definition@Containers@Schema@@_N@Z; ComputeService::JobUtilities::ConvertJobObjectToContainer(void *,Schema::Containers::Definition::Container const &,bool)
0x1400d421c  test    r13b, 2
0x1400d4220  jz      short loc_1400D4253
0x1400d4222  test    bl, bl
0x1400d4224  jnz     short loc_1400D4253
0x1400d4226  mov     qword ptr [rbp+60h+DestinationString.Length], rdi
0x1400d422a  mov     word ptr [rbp+60h+DestinationString.Buffer], 101h
0x1400d4230  xor     edx, edx
0x1400d4232  mov     rcx, [rdi]
0x1400d4235  call    cs:__imp_WcSetRegistryFlushState
0x1400d423b  mov     rcx, [rbp+68h]; this
0x1400d423f  test    eax, eax
0x1400d4241  js      loc_1400D42D8
0x1400d4247  mov     byte ptr [rbp+60h+DestinationString.Buffer+1], bl
0x1400d424a  lea     rcx, [rbp+60h+DestinationString]
0x1400d424e  call    wil__details__ScopeExitFnGuard__lambda_db21ce235646f5ac0b140d27d935719e_____operator__
0x1400d4253  mov     byte ptr [rsp+160h+var_110+1], 0
0x1400d4258  lea     rcx, [rsp+160h+ObjectInformation]
0x1400d425d  call    wil__details__ScopeExitFnGuard__lambda_f12084f5d33c28d2c6b46bb0592d2f62_____operator__
0x1400d4262  nop
0x1400d4263  lea     rcx, [rbp+60h+String2]; void *
0x1400d4267  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d426c  nop
0x1400d426d  lea     rcx, [rbp+60h+var_B0]; this
0x1400d4271  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x1400d4276  nop
0x1400d4277  lea     rcx, [rbp+60h+var_98]; this
0x1400d427b  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x1400d4280  nop
0x1400d4281  lea     rcx, [rbp+60h+var_80]; this
0x1400d4285  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x1400d428a  nop
0x1400d428b  lea     rcx, [rbp+60h+var_68]; this
0x1400d428f  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x1400d4294  nop
0x1400d4295  cmp     byte ptr [rsi+8], 0
0x1400d4299  jz      short loc_1400D42AE
0x1400d429b  mov     rcx, [rsi]; hObject
0x1400d429e  lea     rdx, [rcx-1]
0x1400d42a2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1400d42a6  ja      short loc_1400D42AE
0x1400d42a8  call    cs:__imp_CloseHandle
0x1400d42ae  mov     rax, rdi
0x1400d42b1  mov     rcx, [rbp+60h+var_40]
0x1400d42b5  xor     rcx, rsp; StackCookie
0x1400d42b8  call    __security_check_cookie
0x1400d42bd  mov     rbx, [rsp+160h+arg_18]
0x1400d42c5  add     rsp, 130h
0x1400d42cc  pop     r15
0x1400d42ce  pop     r14
0x1400d42d0  pop     r13
0x1400d42d2  pop     r12
0x1400d42d4  pop     rdi
0x1400d42d5  pop     rsi
0x1400d42d6  pop     rbp
0x1400d42d7  retn
0x1400d42d8  mov     r9d, eax; char *
0x1400d42db  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d42e2  mov     edx, 2A1h; void *
0x1400d42e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400d42ed  mov     r9d, eax; char *
0x1400d42f0  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d42f7  mov     edx, 270h; void *
0x1400d42fc  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
  ... truncated ...
```
