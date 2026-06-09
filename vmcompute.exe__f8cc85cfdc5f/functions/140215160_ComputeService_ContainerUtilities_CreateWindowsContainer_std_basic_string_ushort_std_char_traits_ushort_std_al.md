# ComputeService::ContainerUtilities::CreateWindowsContainer(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Schema::Containers::Definition::Container &,ComputeService::ContainerUtilities::WindowsContainerFlags,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::optional<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>)

- ea: `0x140215160`
- end: `0x1402155e4`
- name: `?CreateWindowsContainer@ContainerUtilities@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUContainer@Definition@Containers@Schema@@W4WindowsContainerFlags@12@0V?$optional@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@6@@Z`
- size: `1156`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400a99f0`
- `0x140170930`

## callees

- `0x140017040`
- `0x140042468`
- `0x1400451a0`
- `0x1400862a4`
- `0x140087ef4`
- `0x140088698`
- `0x1400951f8`
- `0x1400a1dcc`
- `0x1400a864c`
- `0x1400ad53c`
- `0x1400c40e0`
- `0x1400d46bc`
- `0x140117910`
- `0x1401332f0`
- `0x140142dac`
- `0x14016f814`
- `0x140214c2c`
- `0x140214c80`
- `0x140215160`
- `0x1402160b8`
- `0x1402a0e50`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140215344`
- `ntdll!RtlInitUnicodeString` at `0x1402153d5`
- `ntdll!RtlInitUnicodeString` at `0x140215344`
- `ntdll!RtlInitUnicodeString` at `0x1402153d5`
- `ntdll!NtOpenJobObject` at `0x140215390`
- `ntdll!NtOpenJobObject` at `0x140215390`
- `ntdll!NtSetInformationJobObject` at `0x140215479`
- `ntdll!NtSetInformationJobObject` at `0x140215479`
- `ntdll!NtCreateJobObject` at `0x140215421`
- `ntdll!NtCreateJobObject` at `0x140215421`
- `ntdll!NtQueryObject` at `0x140215281`
- `ntdll!NtQueryObject` at `0x140215281`
- `container!WcSetRegistryFlushState` at `0x1402154d3`
- `container!WcSetRegistryFlushState` at `0x1402154d3`

## string_xrefs

- `0x140215563`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x140215578`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x140215590`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1402155a8`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1402155bd`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1402155d2`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall ComputeService::ContainerUtilities::CreateWindowsContainer(
        _QWORD *a1,
        __int64 a2,
        void *a3,
        char a4,
        __int64 a5,
        __int64 a6)
{
  const wchar_t **v10; // rdi
  NTSTATUS Object; // eax
  unsigned int v12; // r8d
  int v13; // eax
  const wchar_t *v14; // rdx
  const WCHAR *v15; // rdx
  void **v16; // rax
  NTSTATUS v17; // eax
  const WCHAR *v18; // rdx
  void **v19; // rax
  NTSTATUS v20; // eax
  NTSTATUS v21; // eax
  const struct Schema::Containers::Definition::Container *v22; // r8
  bool v23; // r9
  int v24; // eax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+70h] [rbp-90h]
  char v29; // [rsp+78h] [rbp-88h] BYREF
  PVOID ObjectInformation[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h]
  wchar_t *String2[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v34; // [rsp+B0h] [rbp-50h]
  struct _LUID v35[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-38h]
  struct _LUID v37[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v38; // [rsp+E0h] [rbp-20h]
  struct _LUID v39[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v40; // [rsp+F8h] [rbp-8h]
  struct _LUID v41[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v42; // [rsp+110h] [rbp+10h]
  __int128 JobInformation; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v28 = a6;
  *a1 = 0;
  v29 = 0;
  *(_OWORD *)&v41[0].LowPart = 0;
  v42 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege(v41, 8);
  *(_OWORD *)&v39[0].LowPart = 0;
  v40 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege(v39, 9);
  *(_OWORD *)&v37[0].LowPart = 0;
  v38 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege(v37, 17);
  *(_OWORD *)&v35[0].LowPart = 0;
  v36 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege(v35, 18);
  ComputeService::ContainerUtilities::GetWindowsContainerJobName(String2);
  if ( *(_BYTE *)(a6 + 8) )
  {
    *(_OWORD *)ObjectInformation = 0;
    v31 = 0;
    std::vector<unsigned char>::vector<unsigned char>(ObjectInformation, 2 * v33 + 18);
    v10 = (const wchar_t **)ObjectInformation[0];
    Object = NtQueryObject(
               *(HANDLE *)a6,
               ObjectNameInformation,
               ObjectInformation[0],
               LODWORD(ObjectInformation[1]) - LODWORD(ObjectInformation[0]),
               0);
    if ( Object >= 0 )
    {
      if ( *(unsigned __int16 *)v10 == 2 * v33 )
      {
        v14 = (const wchar_t *)String2;
        if ( v34 > 7 )
          v14 = String2[0];
        v13 = wcsncmp_0(v10[1], v14, *(unsigned __int16 *)v10);
        if ( !v13 )
          goto LABEL_5;
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
    LOBYTE(v13) = 1;
LABEL_5:
    if ( (_BYTE)v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x261,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)0x80070057LL,
        ReturnLength);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      a1,
      a6);
    std::vector<unsigned char>::_Tidy(ObjectInformation);
    goto LABEL_22;
  }
  if ( *(_QWORD *)(a5 + 16) )
  {
    if ( (unsigned __int8)std::operator!=<unsigned short>(String2) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x268,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)0x80070057LL,
        ReturnLength);
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    *(_OWORD *)ObjectInformation = 0;
    v15 = (const WCHAR *)String2;
    if ( v34 > 7 )
      v15 = String2[0];
    RtlInitUnicodeString((PUNICODE_STRING)ObjectInformation, v15);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)ObjectInformation;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v16 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(a1);
    v17 = NtOpenJobObject(v16, 0x1F003Fu, &ObjectAttributes);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x270,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)(unsigned int)v17,
        ReturnLength);
  }
  else
  {
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    *(_OWORD *)ObjectInformation = 0;
    v18 = (const WCHAR *)String2;
    if ( v34 > 7 )
      v18 = String2[0];
    RtlInitUnicodeString((PUNICODE_STRING)ObjectInformation, v18);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 16;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)ObjectInformation;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v19 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(a1);
    v20 = NtCreateJobObject(v19, 0x1F003Fu, &ObjectAttributes);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x27A,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)(unsigned int)v20,
        ReturnLength);
    v29 = 1;
  }
LABEL_22:
  *(_QWORD *)&ObjectAttributes.Length = &v29;
  ObjectAttributes.RootDirectory = a1;
  LOWORD(ObjectAttributes.ObjectName) = 257;
  JobInformation = *(_OWORD *)ComputeService::Management::GetComputeSystemGuid(ObjectInformation, a2);
  v21 = NtSetInformationJobObject((HANDLE)*a1, MaxJobObjectInfoClass|0x20, &JobInformation, 0x10u);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x28F,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
      (const char *)(unsigned int)v21,
      ReturnLength);
  ComputeService::ContainerDefinition::ResolveRuntimeAliases(a3, *a1, String2);
  LOBYTE(v22) = !(a4 & 1);
  ComputeService::JobUtilities::ConvertJobObjectToContainer((ComputeService::JobUtilities *)*a1, a3, v22, v23);
  if ( (a4 & 2) != 0 && (a4 & 1) == 0 )
  {
    ObjectInformation[0] = a1;
    LOWORD(ObjectInformation[1]) = 257;
    v24 = WcSetRegistryFlushState(*a1, 0);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A1,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)(unsigned int)v24,
        ReturnLength);
    BYTE1(ObjectInformation[1]) = a4 & 1;
    wil::details::ScopeExitFnGuard__lambda_db21ce235646f5ac0b140d27d935719e___::operator()(ObjectInformation);
  }
  BYTE1(ObjectAttributes.ObjectName) = 0;
  wil::details::ScopeExitFnGuard__lambda_f12084f5d33c28d2c6b46bb0592d2f62___::operator()(&ObjectAttributes);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)String2);
  Vml::TemporaryPrivilege::~TemporaryPrivilege(v35);
  Vml::TemporaryPrivilege::~TemporaryPrivilege(v37);
  Vml::TemporaryPrivilege::~TemporaryPrivilege(v39);
  Vml::TemporaryPrivilege::~TemporaryPrivilege(v41);
  std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,0>::~_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,0>(a6);
  return a1;
}

```

## disassembly

```asm
0x140215160  push    rbp
0x140215162  push    rbx
0x140215163  push    rsi
0x140215164  push    rdi
0x140215165  push    r12
0x140215167  push    r14
0x140215169  push    r15
0x14021516b  lea     rbp, [rsp-30h]
0x140215170  sub     rsp, 130h
0x140215177  mov     rax, cs:__security_cookie
0x14021517e  xor     rax, rsp
0x140215181  mov     [rbp+60h+var_38], rax
0x140215185  mov     r14d, r9d
0x140215188  mov     r15, r8
0x14021518b  mov     r12, rdx
0x14021518e  mov     rbx, rcx
0x140215191  mov     rdi, [rbp+60h+arg_20]
0x140215198  mov     [rsp+160h+var_128], rcx
0x14021519d  mov     rsi, [rbp+60h+arg_28]
0x1402151a4  mov     [rsp+160h+var_F0], rsi
0x1402151a9  mov     [rsp+160h+var_130], 0
0x1402151b1  xor     eax, eax
0x1402151b3  mov     [rcx], rax
0x1402151b6  mov     [rsp+160h+var_130], 1
0x1402151be  mov     [rsp+160h+var_E8], al
0x1402151c2  xorps   xmm0, xmm0
0x1402151c5  movups  xmmword ptr [rbp+60h+var_60.LowPart], xmm0
0x1402151c9  mov     [rbp+60h+var_50], rax
0x1402151cd  lea     edx, [rax+8]; int
0x1402151d0  lea     rcx, [rbp+60h+var_60]; this
0x1402151d4  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1402151d9  nop
0x1402151da  xorps   xmm0, xmm0
0x1402151dd  xor     eax, eax
0x1402151df  movups  xmmword ptr [rbp+60h+var_78.LowPart], xmm0
0x1402151e3  mov     [rbp+60h+var_68], rax
0x1402151e7  lea     edx, [rax+9]; int
0x1402151ea  lea     rcx, [rbp+60h+var_78]; this
0x1402151ee  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1402151f3  nop
0x1402151f4  xorps   xmm0, xmm0
0x1402151f7  xor     eax, eax
0x1402151f9  movups  xmmword ptr [rbp+60h+var_90.LowPart], xmm0
0x1402151fd  mov     [rbp+60h+var_80], rax
0x140215201  lea     edx, [rax+11h]; int
0x140215204  lea     rcx, [rbp+60h+var_90]; this
0x140215208  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x14021520d  nop
0x14021520e  xorps   xmm0, xmm0
0x140215211  xor     eax, eax
0x140215213  movups  xmmword ptr [rbp+60h+var_A8.LowPart], xmm0
0x140215217  mov     [rbp+60h+var_98], rax
0x14021521b  lea     edx, [rax+12h]; int
0x14021521e  lea     rcx, [rbp+60h+var_A8]; this
0x140215222  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x140215227  nop
0x140215228  mov     rdx, r12
0x14021522b  lea     rcx, [rbp+60h+String2]; void *
0x14021522f  call    ?GetWindowsContainerJobName@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; ComputeService::ContainerUtilities::GetWindowsContainerJobName(std::wstring const &)
0x140215234  nop
0x140215235  cmp     byte ptr [rsi+8], 0
0x140215239  jz      loc_1402152F9
0x14021523f  xorps   xmm0, xmm0
0x140215242  xor     eax, eax
0x140215244  movups  xmmword ptr [rbp+60h+ObjectInformation], xmm0
0x140215248  mov     [rbp+60h+var_D0], rax
0x14021524c  mov     rdx, [rbp+60h+var_B8]
0x140215250  lea     rdx, ds:12h[rdx*2]
0x140215258  lea     rcx, [rbp+60h+ObjectInformation]
0x14021525c  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140215261  nop
0x140215262  mov     rdi, [rbp+60h+ObjectInformation]
0x140215266  mov     r9d, dword ptr [rbp+60h+ObjectInformation+8]
0x14021526a  sub     r9d, edi; ObjectInformationLength
0x14021526d  mov     qword ptr [rsp+160h+ReturnLength], 0; int
0x140215276  mov     r8, rdi; ObjectInformation
0x140215279  mov     edx, 1; ObjectInformationClass
0x14021527e  mov     rcx, [rsi]; Handle
0x140215281  call    cs:__imp_NtQueryObject
0x140215288  nop     dword ptr [rax+rax+00h]
0x14021528d  mov     rcx, [rbp+68h]; this
0x140215291  test    eax, eax
0x140215293  jns     short loc_1402152CA
0x140215295  mov     r9d, eax; char *
0x140215298  mov     edx, 261h; void *
0x14021529d  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x1402152a2  mov     al, 1
0x1402152a4  mov     rcx, [rbp+68h]; this
0x1402152a8  test    al, al
0x1402152aa  jnz     loc_14021558A
0x1402152b0  mov     rdx, rsi
0x1402152b3  mov     rcx, rbx
0x1402152b6  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1402152bb  nop
0x1402152bc  lea     rcx, [rbp+60h+ObjectInformation]
0x1402152c0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1402152c5  jmp     loc_14021543E
0x1402152ca  movzx   ecx, word ptr [rdi]
0x1402152cd  mov     rax, [rbp+60h+var_B8]
0x1402152d1  add     rax, rax
0x1402152d4  cmp     rcx, rax
0x1402152d7  jnz     short loc_1402152A2
0x1402152d9  lea     rdx, [rbp+60h+String2]
0x1402152dd  cmp     [rbp+60h+var_B0], 7
0x1402152e2  cmova   rdx, [rbp+60h+String2]; String2
0x1402152e7  mov     r8d, ecx; MaxCount
0x1402152ea  mov     rcx, [rdi+8]; String1
0x1402152ee  call    wcsncmp_0
0x1402152f3  test    eax, eax
0x1402152f5  jnz     short loc_1402152A2
0x1402152f7  jmp     short loc_1402152A4
0x1402152f9  cmp     qword ptr [rdi+10h], 0
0x1402152fe  jz      loc_1402153AD
0x140215304  mov     rdx, rdi
0x140215307  lea     rcx, [rbp+60h+String2]
0x14021530b  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x140215310  mov     rcx, [rbp+68h]; this
0x140215314  test    al, al
0x140215316  jnz     loc_1402155A2
0x14021531c  xorps   xmm0, xmm0
0x14021531f  movups  xmmword ptr [rsp+160h+ObjectAttributes.Length], xmm0
0x140215324  movups  xmmword ptr [rsp+160h+ObjectAttributes.ObjectName], xmm0
0x140215329  movups  xmmword ptr [rsp+160h+ObjectAttributes.SecurityDescriptor], xmm0
0x14021532e  movups  xmmword ptr [rbp+60h+ObjectInformation], xmm0
0x140215332  lea     rdx, [rbp+60h+String2]
0x140215336  cmp     [rbp+60h+var_B0], 7
0x14021533b  cmova   rdx, [rbp+60h+String2]; SourceString
0x140215340  lea     rcx, [rbp+60h+ObjectInformation]; DestinationString
0x140215344  call    cs:__imp_RtlInitUnicodeString
0x14021534b  nop     dword ptr [rax+rax+00h]
0x140215350  mov     [rsp+160h+ObjectAttributes.Length], 30h ; '0'
0x140215358  mov     [rsp+160h+ObjectAttributes.RootDirectory], 0
0x140215361  mov     [rsp+160h+ObjectAttributes.Attributes], 0
0x140215369  lea     rax, [rbp+60h+ObjectInformation]
0x14021536d  mov     [rsp+160h+ObjectAttributes.ObjectName], rax
0x140215372  xorps   xmm0, xmm0
0x140215375  movdqu  xmmword ptr [rsp+160h+ObjectAttributes.SecurityDescriptor], xmm0
0x14021537b  mov     rcx, rbx
0x14021537e  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x140215383  lea     r8, [rsp+160h+ObjectAttributes]; ObjectAttributes
0x140215388  mov     edx, 1F003Fh; DesiredAccess
0x14021538d  mov     rcx, rax; JobHandle
0x140215390  call    cs:__imp_NtOpenJobObject
0x140215397  nop     dword ptr [rax+rax+00h]
0x14021539c  mov     rcx, [rbp+68h]; this
0x1402153a0  test    eax, eax
0x1402153a2  js      loc_140215575
0x1402153a8  jmp     loc_14021543E
0x1402153ad  xorps   xmm0, xmm0
0x1402153b0  movups  xmmword ptr [rsp+160h+ObjectAttributes.Length], xmm0
0x1402153b5  movups  xmmword ptr [rsp+160h+ObjectAttributes.ObjectName], xmm0
0x1402153ba  movups  xmmword ptr [rsp+160h+ObjectAttributes.SecurityDescriptor], xmm0
0x1402153bf  movups  xmmword ptr [rbp+60h+ObjectInformation], xmm0
0x1402153c3  lea     rdx, [rbp+60h+String2]
0x1402153c7  cmp     [rbp+60h+var_B0], 7
0x1402153cc  cmova   rdx, [rbp+60h+String2]; SourceString
0x1402153d1  lea     rcx, [rbp+60h+ObjectInformation]; DestinationString
0x1402153d5  call    cs:__imp_RtlInitUnicodeString
0x1402153dc  nop     dword ptr [rax+rax+00h]
0x1402153e1  mov     [rsp+160h+ObjectAttributes.Length], 30h ; '0'
0x1402153e9  mov     [rsp+160h+ObjectAttributes.RootDirectory], 0
0x1402153f2  mov     [rsp+160h+ObjectAttributes.Attributes], 10h
0x1402153fa  lea     rax, [rbp+60h+ObjectInformation]
0x1402153fe  mov     [rsp+160h+ObjectAttributes.ObjectName], rax
0x140215403  xorps   xmm0, xmm0
0x140215406  movdqu  xmmword ptr [rsp+160h+ObjectAttributes.SecurityDescriptor], xmm0
0x14021540c  mov     rcx, rbx
0x14021540f  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x140215414  lea     r8, [rsp+160h+ObjectAttributes]; ObjectAttributes
0x140215419  mov     edx, 1F003Fh; DesiredAccess
0x14021541e  mov     rcx, rax; JobHandle
0x140215421  call    cs:__imp_NtCreateJobObject
0x140215428  nop     dword ptr [rax+rax+00h]
0x14021542d  mov     rcx, [rbp+68h]; this
0x140215431  test    eax, eax
0x140215433  js      loc_1402155BA
0x140215439  mov     [rsp+160h+var_E8], 1
0x14021543e  lea     rax, [rsp+160h+var_E8]
0x140215443  mov     qword ptr [rsp+160h+ObjectAttributes.Length], rax
0x140215448  mov     [rsp+160h+ObjectAttributes.RootDirectory], rbx
0x14021544d  mov     word ptr [rsp+160h+ObjectAttributes.ObjectName], 101h
0x140215454  mov     rdx, r12
0x140215457  lea     rcx, [rbp+60h+ObjectInformation]
0x14021545b  call    ?GetComputeSystemGuid@Management@ComputeService@@YA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::Management::GetComputeSystemGuid(std::wstring const &)
0x140215460  movups  xmm0, xmmword ptr [rax]
0x140215463  movdqu  [rbp+60h+JobInformation], xmm0
0x140215468  mov     r9d, 10h; JobInformationLength
0x14021546e  lea     r8, [rbp+60h+JobInformation]; JobInformation
0x140215472  lea     edx, [r9+1Ch]; JobInformationClass
0x140215476  mov     rcx, [rbx]; JobHandle
0x140215479  call    cs:__imp_NtSetInformationJobObject
0x140215480  nop     dword ptr [rax+rax+00h]
0x140215485  mov     rcx, [rbp+68h]; this
0x140215489  test    eax, eax
0x14021548b  js      loc_1402155CF
0x140215491  mov     dil, r14b
0x140215494  and     dil, 1
0x140215498  lea     r8, [rbp+60h+String2]
0x14021549c  mov     rdx, [rbx]
0x14021549f  mov     rcx, r15
0x1402154a2  call    ?ResolveRuntimeAliases@ContainerDefinition@ComputeService@@YAXAEAUContainer@Definition@Containers@Schema@@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ComputeService::ContainerDefinition::ResolveRuntimeAliases(Schema::Containers::Definition::Container &,void *,std::wstring const &)
0x1402154a7  mov     r8b, dil
0x1402154aa  xor     r8b, 1; struct Schema::Containers::Definition::Container *
0x1402154ae  mov     rdx, r15; void *
0x1402154b1  mov     rcx, [rbx]; this
0x1402154b4  call    ?ConvertJobObjectToContainer@JobUtilities@ComputeService@@YAXPEAXAEBUContainer@Definition@Containers@Schema@@_N@Z; ComputeService::JobUtilities::ConvertJobObjectToContainer(void *,Schema::Containers::Definition::Container const &,bool)
0x1402154b9  test    r14b, 2
0x1402154bd  jz      short loc_1402154F4
0x1402154bf  test    dil, dil
0x1402154c2  jnz     short loc_1402154F4
0x1402154c4  mov     [rbp+60h+ObjectInformation], rbx
0x1402154c8  mov     word ptr [rbp+60h+ObjectInformation+8], 101h
0x1402154ce  xor     edx, edx
0x1402154d0  mov     rcx, [rbx]
0x1402154d3  call    cs:__imp_WcSetRegistryFlushState
0x1402154da  nop     dword ptr [rax+rax+00h]
0x1402154df  mov     rcx, [rbp+68h]; this
0x1402154e3  test    eax, eax
0x1402154e5  js      short loc_140215560
0x1402154e7  mov     byte ptr [rbp+60h+ObjectInformation+9], dil
0x1402154eb  lea     rcx, [rbp+60h+ObjectInformation]
0x1402154ef  call    wil__details__ScopeExitFnGuard__lambda_db21ce235646f5ac0b140d27d935719e_____operator__
0x1402154f4  mov     byte ptr [rsp+160h+ObjectAttributes.ObjectName+1], 0
0x1402154f9  lea     rcx, [rsp+160h+ObjectAttributes]
0x1402154fe  call    wil__details__ScopeExitFnGuard__lambda_f12084f5d33c28d2c6b46bb0592d2f62_____operator__
0x140215503  nop
0x140215504  lea     rcx, [rbp+60h+String2]; this
0x140215508  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14021550d  nop
0x14021550e  lea     rcx, [rbp+60h+var_A8]; this
0x140215512  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x140215517  nop
0x140215518  lea     rcx, [rbp+60h+var_90]; this
0x14021551c  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x140215521  nop
0x140215522  lea     rcx, [rbp+60h+var_78]; this
0x140215526  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x14021552b  nop
0x14021552c  lea     rcx, [rbp+60h+var_60]; this
0x140215530  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x140215535  nop
0x140215536  mov     rcx, rsi
0x140215539  call    ??1?$_Optional_destruct_base@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,0>::~_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,0>(void)
0x14021553e  mov     rax, rbx
0x140215541  mov     rcx, [rbp+60h+var_38]
0x140215545  xor     rcx, rsp; StackCookie
0x140215548  call    __security_check_cookie
0x14021554d  add     rsp, 130h
0x140215554  pop     r15
0x140215556  pop     r14
0x140215558  pop     r12
0x14021555a  pop     rdi
0x14021555b  pop     rsi
0x14021555c  pop     rbx
0x14021555d  pop     rbp
0x14021555e  retn
0x140215560  mov     r9d, eax; char *
0x140215563  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x14021556a  mov     edx, 2A1h; void *
0x14021556f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140215575  mov     r9d, eax; char *
0x140215578  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x14021557f  mov     edx, 270h; void *
0x140215584  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x14021558a  mov     r9d, 80070057h; char *
0x140215590  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x140215597  mov     edx, 261h; void *
0x14021559c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402155a2  mov     r9d, 80070057h; char *
0x1402155a8  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x1402155af  mov     edx, 268h; void *
0x1402155b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402155ba  mov     r9d, eax; char *
0x1402155bd  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x1402155c4  mov     edx, 27Ah; void *
0x1402155c9  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1402155cf  mov     r9d, eax; char *
0x1402155d2  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x1402155d9  mov     edx, 28Fh; void *
0x1402155de  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
