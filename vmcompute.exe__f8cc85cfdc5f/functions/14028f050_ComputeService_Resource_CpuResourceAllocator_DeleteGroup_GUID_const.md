# ComputeService::Resource::CpuResourceAllocator::DeleteGroup(_GUID const &)

- ea: `0x14028f050`
- end: `0x14028f385`
- name: `?DeleteGroup@CpuResourceAllocator@Resource@ComputeService@@AEAA?AUCpuGroupConfig@Processor@Resources@Schema@@AEBU_GUID@@@Z`
- size: `821`
- prototype: `struct Schema::Resources::Processor::CpuGroupConfig __high(const struct _GUID *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14028fc50`

## callees

- `0x1400046c8`
- `0x140017040`
- `0x140020890`
- `0x1400286f0`
- `0x14002f9e8`
- `0x14004249c`
- `0x1400521fc`
- `0x14005bb24`
- `0x14005bdc8`
- `0x14005d900`
- `0x1400602cc`
- `0x14006a5a0`
- `0x1400a01ec`
- `0x1400a023c`
- `0x1400a02f8`
- `0x1400c40e0`
- `0x1401332f0`
- `0x140206834`
- `0x14021d970`
- `0x14028e570`
- `0x14028ea10`
- `0x14028f050`
- `0x140290140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14028f1a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14028f1a2`
- `vid!VidOpenStatisticsHandle` at `0x14028f13f`
- `vid!VidOpenStatisticsHandle` at `0x14028f13f`
- `vid!VidDeleteCpuGroup` at `0x14028f18e`
- `vid!VidDeleteCpuGroup` at `0x14028f18e`

## string_xrefs

- `0x14028f10e`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14028f176`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14028f361`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14028f373`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14028f160`: `Failed to open VID statistics handle`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
Schema::Resources::Processor::CpuGroupConfig *__fastcall ComputeService::Resource::CpuResourceAllocator::DeleteGroup(
        __int64 a1,
        Schema::Resources::Processor::CpuGroupConfig *a2,
        __int64 a3)
{
  __int64 v6; // r8
  __int64 v7; // rax
  const char *v8; // rdx
  Schema::Resources::Processor::CpuGroupConfig *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rbx
  signed int LastError; // eax
  unsigned __int64 v13; // r9
  const struct _tlgProvider_t *v14; // r8
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rax
  __int64 v18; // rax
  int v20; // [rsp+20h] [rbp-89h]
  char *v21; // [rsp+30h] [rbp-79h]
  _OWORD v22[2]; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v23[4]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v24[32]; // [rsp+90h] [rbp-19h] BYREF
  Schema::Resources::Processor::CpuGroupConfig *v25; // [rsp+B0h] [rbp+7h] BYREF
  _QWORD v26[2]; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v23[2] = a2;
  Schema::Resources::Processor::CpuGroupConfig::CpuGroupConfig(a2);
  v26[0] = 0;
  wil::AcquireSRWLockShared(v26, a1 + 16);
  v25 = 0;
  std::_Tree<std::_Tmap_traits<_GUID,Schema::Resources::Processor::CpuGroupConfig,Vml::GuidLess,std::allocator<std::pair<_GUID const,Schema::Resources::Processor::CpuGroupConfig>>,0>>::find(
    a1 + 32,
    &v25,
    a3);
  LOBYTE(v6) = 1;
  v7 = Vml::GuidToString(v22, a3, v6);
  v8 = (const char *)v7;
  if ( *(_QWORD *)(v7 + 24) > 7u )
    v8 = *(const char **)v7;
  v9 = v25;
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x1CA,
    (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
    (const char *)0x80070490LL,
    v25 != *(Schema::Resources::Processor::CpuGroupConfig **)(a1 + 32),
    (bool)"CPU group %ws does not exist.",
    v8);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v22);
  Schema::Resources::Processor::CpuGroupConfig::operator=(a2, (char *)v9 + 48);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v26);
  v11 = VidOpenStatisticsHandle(v10);
  v23[0] = v11;
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x1D2,
    (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
    (const char *)0x8000FFFFLL,
    (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL,
    (bool)"Failed to open VID statistics handle",
    v21);
  if ( !(unsigned int)VidDeleteCpuGroup(v11, *((_QWORD *)a2 + 9)) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    else
      v13 = (unsigned int)LastError;
    if ( LastError != -1070268305 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1DA,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
        (const char *)v13,
        v20);
    if ( *(_BYTE *)(a1 + 52) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
        (const char *)0xC035006FLL,
        v20);
    v14 = ComputeService::Diagnostics::TraceProvider::Provider();
    if ( *(_DWORD *)v14 > 4u && (unsigned __int8)tlgKeywordOn(v14, 4096, v14) )
    {
      *(_QWORD *)&v22[0] = *((_QWORD *)a2 + 9);
      v25 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
        v15,
        (unsigned int)byte_140373A0D,
        v15,
        v16,
        (__int64)&v25,
        (__int64)v22);
    }
  }
  v25 = 0;
  wil::AcquireSRWLockExclusive(&v25, a1 + 16);
  v22[0] = *(_OWORD *)std::_Tree<std::_Tmap_traits<_GUID,Schema::Resources::Processor::CpuGroupConfig,Vml::GuidLess,std::allocator<std::pair<_GUID const,Schema::Resources::Processor::CpuGroupConfig>>,0>>::_Eqrange<_GUID>(
                        a1 + 32,
                        v26,
                        a3);
  std::_Tree<std::_Tmap_traits<_GUID,Schema::Resources::Processor::CpuGroupConfig,Vml::GuidLess,std::allocator<std::pair<_GUID const,Schema::Resources::Processor::CpuGroupConfig>>,0>>::_Erase(
    a1 + 32,
    v22);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v25);
  if ( !*(_DWORD *)(a1 + 48) )
  {
    *(_QWORD *)&v22[0] = 0;
    wil::AcquireSRWLockExclusive(v22, a1 + 24);
    v25 = 0;
    ComputeService::RecoveryStore::OpenVolatileCpuGroupsRegKey(&v25);
    v26[0] = 0;
    ComputeService::RecoveryStore::OpenPersistentCpuGroupsRegKey(v26);
    v17 = Vml::GuidToString(v24, a3, 0);
    if ( *(_QWORD *)(v17 + 24) > 7u )
      v17 = *(_QWORD *)v17;
    Vml::VmRegistryKey::DeleteValue((Vml::VmRegistryKey *)&v25, (const unsigned __int16 *)v17);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v24);
    v18 = Vml::GuidToString(v24, a3, 0);
    if ( *(_QWORD *)(v18 + 24) > 7u )
      v18 = *(_QWORD *)v18;
    Vml::VmRegistryKey::DeleteValue((Vml::VmRegistryKey *)v26, (const unsigned __int16 *)v18);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v24);
    Vml::VmRegistryKey::~VmRegistryKey((Vml::VmRegistryKey *)v26);
    Vml::VmRegistryKey::~VmRegistryKey((Vml::VmRegistryKey *)&v25);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v22);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(v23);
  return a2;
}

```

## disassembly

```asm
0x14028f050  push    rbp
0x14028f052  push    rbx
0x14028f053  push    rsi
0x14028f054  push    rdi
0x14028f055  push    r12
0x14028f057  push    r14
0x14028f059  push    r15
0x14028f05b  lea     rbp, [rsp-27h]
0x14028f060  sub     rsp, 0D0h
0x14028f067  mov     rax, cs:__security_cookie
0x14028f06e  xor     rax, rsp
0x14028f071  mov     [rbp+57h+var_38], rax
0x14028f075  mov     r14, r8
0x14028f078  mov     rdi, rdx
0x14028f07b  mov     rsi, rcx
0x14028f07e  mov     [rbp+57h+var_80], rdx
0x14028f082  mov     [rbp+57h+var_C0], 0
0x14028f089  mov     rcx, rdx; this
0x14028f08c  call    ??0CpuGroupConfig@Processor@Resources@Schema@@QEAA@XZ; Schema::Resources::Processor::CpuGroupConfig::CpuGroupConfig(void)
0x14028f091  mov     [rbp+57h+var_C0], 1
0x14028f098  mov     [rbp+57h+var_48], 0
0x14028f0a0  lea     rdx, [rsi+10h]
0x14028f0a4  lea     rcx, [rbp+57h+var_48]
0x14028f0a8  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x14028f0ad  nop
0x14028f0ae  mov     [rbp+57h+var_50], 0
0x14028f0b6  lea     r15, [rsi+20h]
0x14028f0ba  mov     r8, r14
0x14028f0bd  lea     rdx, [rbp+57h+var_50]
0x14028f0c1  mov     rcx, r15
0x14028f0c4  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,Schema::Resources::Processor::CpuGroupConfig,Vml::GuidLess,std::allocator<std::pair<_GUID const,Schema::Resources::Processor::CpuGroupConfig>>,0>>::find(_GUID const &)
0x14028f0c9  mov     r8b, 1
0x14028f0cc  mov     rdx, r14
0x14028f0cf  lea     rcx, [rbp+57h+var_B0]
0x14028f0d3  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x14028f0d8  mov     rdx, rax
0x14028f0db  cmp     qword ptr [rax+18h], 7
0x14028f0e0  jbe     short loc_14028F0E5
0x14028f0e2  mov     rdx, [rax]
0x14028f0e5  mov     rbx, [rbp+57h+var_50]
0x14028f0e9  cmp     rbx, [r15]
0x14028f0ec  setnz   al
0x14028f0ef  mov     rcx, [rbp+5Fh]; this
0x14028f0f3  mov     [rsp+100h+var_D0], rdx; char *
0x14028f0f8  lea     rdx, aCpuGroupWsDoes; "CPU group %ws does not exist."
0x14028f0ff  mov     qword ptr [rsp+100h+var_D8], rdx; bool
0x14028f104  mov     [rsp+100h+var_E0], al; char
0x14028f108  mov     r9d, 80070490h; char *
0x14028f10e  lea     r8, aOnecoreVmCompu_105; "onecore\\vm\\compute\\management\\resou"...
0x14028f115  mov     edx, 1CAh; void *
0x14028f11a  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x14028f11f  nop
0x14028f120  lea     rcx, [rbp+57h+var_B0]; this
0x14028f124  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14028f129  lea     rdx, [rbx+30h]
0x14028f12d  mov     rcx, rdi
0x14028f130  call    ??4CpuGroupConfig@Processor@Resources@Schema@@QEAAAEAU0123@AEBU0123@@Z; Schema::Resources::Processor::CpuGroupConfig::operator=(Schema::Resources::Processor::CpuGroupConfig const &)
0x14028f135  nop
0x14028f136  lea     rcx, [rbp+57h+var_48]
0x14028f13a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028f13f  call    cs:__imp_VidOpenStatisticsHandle
0x14028f146  nop     dword ptr [rax+rax+00h]
0x14028f14b  mov     rbx, rax
0x14028f14e  mov     [rbp+57h+var_90], rax
0x14028f152  dec     rax
0x14028f155  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14028f159  setbe   al
0x14028f15c  mov     rcx, [rbp+5Fh]; this
0x14028f160  lea     rdx, aFailedToOpenVi; "Failed to open VID statistics handle"
0x14028f167  mov     qword ptr [rsp+100h+var_D8], rdx; bool
0x14028f16c  mov     [rsp+100h+var_E0], al; int
0x14028f170  mov     r9d, 8000FFFFh; char *
0x14028f176  lea     r8, aOnecoreVmCompu_105; "onecore\\vm\\compute\\management\\resou"...
0x14028f17d  mov     edx, 1D2h; void *
0x14028f182  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x14028f187  mov     rdx, [rdi+48h]
0x14028f18b  mov     rcx, rbx
0x14028f18e  call    cs:__imp_VidDeleteCpuGroup
0x14028f195  nop     dword ptr [rax+rax+00h]
0x14028f19a  test    eax, eax
0x14028f19c  jnz     loc_14028F22C
0x14028f1a2  call    cs:__imp_GetLastError
0x14028f1a9  nop     dword ptr [rax+rax+00h]
0x14028f1ae  test    eax, eax
0x14028f1b0  jg      short loc_14028F1B7
0x14028f1b2  mov     r9d, eax
0x14028f1b5  jmp     short loc_14028F1C2
0x14028f1b7  movzx   r9d, ax
0x14028f1bb  or      r9d, 80070000h; char *
0x14028f1c2  mov     rcx, [rbp+5Fh]; this
0x14028f1c6  cmp     eax, 0C035006Fh
0x14028f1cb  jnz     loc_14028F373
0x14028f1d1  mov     rcx, [rbp+5Fh]; this
0x14028f1d5  cmp     byte ptr [rsi+34h], 0
0x14028f1d9  jnz     loc_14028F35B
0x14028f1df  call    ?Provider@TraceProvider@Diagnostics@ComputeService@@SAPEBU_tlgProvider_t@@XZ; ComputeService::Diagnostics::TraceProvider::Provider(void)
0x14028f1e4  mov     r8, rax
0x14028f1e7  mov     eax, [rax]
0x14028f1e9  cmp     eax, 4
0x14028f1ec  jbe     short loc_14028F22C
0x14028f1ee  mov     edx, 1000h
0x14028f1f3  mov     rcx, r8
0x14028f1f6  call    _tlgKeywordOn
0x14028f1fb  test    al, al
0x14028f1fd  jz      short loc_14028F22C
0x14028f1ff  mov     rax, [rdi+48h]
0x14028f203  mov     qword ptr [rbp+57h+var_B0], rax
0x14028f207  mov     [rbp+57h+var_50], rdi
0x14028f20b  lea     rax, [rbp+57h+var_B0]
0x14028f20f  mov     qword ptr [rsp+100h+var_D8], rax
0x14028f214  lea     rax, [rbp+57h+var_50]
0x14028f218  mov     qword ptr [rsp+100h+var_E0], rax
0x14028f21d  lea     rdx, byte_140373A0D
0x14028f224  mov     rcx, r8
0x14028f227  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x14028f22c  mov     [rbp+57h+var_50], 0
0x14028f234  lea     rdx, [rsi+10h]
0x14028f238  lea     rcx, [rbp+57h+var_50]
0x14028f23c  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14028f241  mov     r8, r14
0x14028f244  lea     rdx, [rbp+57h+var_48]
0x14028f248  mov     rcx, r15
0x14028f24b  call    ??$_Eqrange@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@@std@@PEAX@std@@PEAU12@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,Schema::Resources::Processor::CpuGroupConfig,Vml::GuidLess,std::allocator<std::pair<_GUID const,Schema::Resources::Processor::CpuGroupConfig>>,0>>::_Eqrange<_GUID>(_GUID const &)
0x14028f250  movups  xmm0, xmmword ptr [rax]
0x14028f253  movdqu  [rbp+57h+var_B0], xmm0
0x14028f258  lea     rdx, [rbp+57h+var_B0]
0x14028f25c  mov     rcx, r15
0x14028f25f  call    ?_Erase@?$_Tree@V?$_Tmap_traits@U_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@@std@@@std@@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<_GUID,Schema::Resources::Processor::CpuGroupConfig,Vml::GuidLess,std::allocator<std::pair<_GUID const,Schema::Resources::Processor::CpuGroupConfig>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<_GUID const,Schema::Resources::Processor::CpuGroupConfig>,void *> *,std::_Tree_node<std::pair<_GUID const,Schema::Resources::Processor::CpuGroupConfig>,void *> *>)
0x14028f264  lea     rcx, [rbp+57h+var_50]
0x14028f268  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028f26d  cmp     dword ptr [rsi+30h], 0
0x14028f271  jnz     loc_14028F330
0x14028f277  mov     qword ptr [rbp+57h+var_B0], 0
0x14028f27f  lea     rdx, [rsi+18h]
0x14028f283  lea     rcx, [rbp+57h+var_B0]
0x14028f287  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14028f28c  nop
0x14028f28d  mov     [rbp+57h+var_50], 0
0x14028f295  lea     rcx, [rbp+57h+var_50]
0x14028f299  call    ?OpenVolatileCpuGroupsRegKey@RecoveryStore@ComputeService@@YA?AVVmRegistryKey@Vml@@K@Z; ComputeService::RecoveryStore::OpenVolatileCpuGroupsRegKey(ulong)
0x14028f29e  nop
0x14028f29f  mov     [rbp+57h+var_48], 0
0x14028f2a7  lea     rcx, [rbp+57h+var_48]
0x14028f2ab  call    ?OpenPersistentCpuGroupsRegKey@RecoveryStore@ComputeService@@YA?AVVmRegistryKey@Vml@@K@Z; ComputeService::RecoveryStore::OpenPersistentCpuGroupsRegKey(ulong)
0x14028f2b0  nop
0x14028f2b1  xor     r8d, r8d
0x14028f2b4  mov     rdx, r14
0x14028f2b7  lea     rcx, [rbp+57h+var_70]
0x14028f2bb  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x14028f2c0  nop
0x14028f2c1  cmp     qword ptr [rax+18h], 7
0x14028f2c6  jbe     short loc_14028F2CB
0x14028f2c8  mov     rax, [rax]
0x14028f2cb  mov     rdx, rax; unsigned __int16 *
0x14028f2ce  lea     rcx, [rbp+57h+var_50]; this
0x14028f2d2  call    ?DeleteValue@VmRegistryKey@Vml@@QEAAHPEBG@Z; Vml::VmRegistryKey::DeleteValue(ushort const *)
0x14028f2d7  nop
0x14028f2d8  lea     rcx, [rbp+57h+var_70]; this
0x14028f2dc  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14028f2e1  xor     r8d, r8d
0x14028f2e4  mov     rdx, r14
0x14028f2e7  lea     rcx, [rbp+57h+var_70]
0x14028f2eb  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x14028f2f0  nop
0x14028f2f1  cmp     qword ptr [rax+18h], 7
0x14028f2f6  jbe     short loc_14028F2FB
0x14028f2f8  mov     rax, [rax]
0x14028f2fb  mov     rdx, rax; unsigned __int16 *
0x14028f2fe  lea     rcx, [rbp+57h+var_48]; this
0x14028f302  call    ?DeleteValue@VmRegistryKey@Vml@@QEAAHPEBG@Z; Vml::VmRegistryKey::DeleteValue(ushort const *)
0x14028f307  nop
0x14028f308  lea     rcx, [rbp+57h+var_70]; this
0x14028f30c  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14028f311  nop
0x14028f312  lea     rcx, [rbp+57h+var_48]; this
0x14028f316  call    ??1VmRegistryKey@Vml@@QEAA@XZ; Vml::VmRegistryKey::~VmRegistryKey(void)
0x14028f31b  nop
0x14028f31c  lea     rcx, [rbp+57h+var_50]; this
0x14028f320  call    ??1VmRegistryKey@Vml@@QEAA@XZ; Vml::VmRegistryKey::~VmRegistryKey(void)
0x14028f325  nop
0x14028f326  lea     rcx, [rbp+57h+var_B0]
0x14028f32a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028f32f  nop
0x14028f330  lea     rcx, [rbp+57h+var_90]
0x14028f334  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?VidCloseStatisticsHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>(void)
0x14028f339  mov     rax, rdi
0x14028f33c  mov     rcx, [rbp+57h+var_38]
0x14028f340  xor     rcx, rsp; StackCookie
0x14028f343  call    __security_check_cookie
0x14028f348  add     rsp, 0D0h
0x14028f34f  pop     r15
0x14028f351  pop     r14
0x14028f353  pop     r12
0x14028f355  pop     rdi
0x14028f356  pop     rsi
0x14028f357  pop     rbx
0x14028f358  pop     rbp
0x14028f359  retn
0x14028f35b  mov     r9d, 0C035006Fh; char *
0x14028f361  lea     r8, aOnecoreVmCompu_105; "onecore\\vm\\compute\\management\\resou"...
0x14028f368  mov     edx, 1DEh; void *
0x14028f36d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14028f373  lea     r8, aOnecoreVmCompu_105; "onecore\\vm\\compute\\management\\resou"...
0x14028f37a  mov     edx, 1DAh; void *
0x14028f37f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
