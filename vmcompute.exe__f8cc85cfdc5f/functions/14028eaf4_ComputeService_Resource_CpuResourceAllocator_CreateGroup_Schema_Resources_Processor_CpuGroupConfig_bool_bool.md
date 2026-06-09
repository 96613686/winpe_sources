# ComputeService::Resource::CpuResourceAllocator::CreateGroup(Schema::Resources::Processor::CpuGroupConfig &,bool,bool)

- ea: `0x14028eaf4`
- end: `0x14028f04a`
- name: `?CreateGroup@CpuResourceAllocator@Resource@ComputeService@@AEAAXAEAUCpuGroupConfig@Processor@Resources@Schema@@_N1@Z`
- size: `1366`
- prototype: `void __fastcall(ComputeService::Resource::CpuResourceAllocator *__hidden this, struct Schema::Resources::Processor::CpuGroupConfig *, bool, bool)`
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14028f478`
- `0x14028fc50`

## callees

- `0x140008d84`
- `0x140017040`
- `0x140020890`
- `0x1400286f0`
- `0x14002d888`
- `0x14002f9e8`
- `0x1400421f0`
- `0x14004249c`
- `0x140044974`
- `0x1400521fc`
- `0x14005bb24`
- `0x14005bdc8`
- `0x14005d900`
- `0x1400602cc`
- `0x14006a5a0`
- `0x140080180`
- `0x1400a0164`
- `0x1400a019c`
- `0x1400a023c`
- `0x1400a02f8`
- `0x1401332f0`
- `0x1401d0be4`
- `0x140206834`
- `0x14028dbcc`
- `0x14028e7fc`
- `0x14028eaf4`
- `0x1402c4010`

## import_xrefs

- `vid!VidOpenStatisticsHandle` at `0x14028ebd8`
- `vid!VidOpenStatisticsHandle` at `0x14028ebd8`
- `vid!VidGetCpuGroupProperty` at `0x14028ec67`
- `vid!VidGetCpuGroupProperty` at `0x14028ecc4`
- `vid!VidGetCpuGroupProperty` at `0x14028ed21`
- `vid!VidGetCpuGroupProperty` at `0x14028ed7e`
- `vid!VidGetCpuGroupProperty` at `0x14028ec67`
- `vid!VidGetCpuGroupProperty` at `0x14028ecc4`
- `vid!VidGetCpuGroupProperty` at `0x14028ed21`
- `vid!VidGetCpuGroupProperty` at `0x14028ed7e`
- `vid!VidCreateCpuGroup` at `0x14028ec2f`
- `vid!VidCreateCpuGroup` at `0x14028ec2f`

## string_xrefs

- `0x14028eba9`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14028ec0f`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14028eff0`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14028f002`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14028f014`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14028f026`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14028f038`: `onecore\vm\compute\management\resources\processor\cpuresourceallocator.cpp`
- `0x14028ebf9`: `Failed to open VID statistics handle`
- `0x14028eb93`: `CPU group %ws already exists.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall ComputeService::Resource::CpuResourceAllocator::CreateGroup(
        ComputeService::Resource::CpuResourceAllocator *this,
        struct Schema::Resources::Processor::CpuGroupConfig *a2,
        unsigned __int8 a3,
        char a4)
{
  int v5; // r15d
  __int64 v8; // r8
  __int64 v9; // rax
  const char *v10; // rbx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rbx
  const char *v14; // r9
  __int64 v15; // rdx
  const char *v16; // r9
  _OWORD *v17; // rdx
  const char *v18; // r9
  _OWORD *v19; // rdx
  const char *v20; // r9
  _OWORD *v21; // rdx
  const char *v22; // r9
  _OWORD *v23; // rdx
  __int64 v24; // rax
  unsigned __int8 v25; // cl
  int v26; // ebx
  __int64 v27; // rax
  const unsigned __int16 *v28; // rbx
  __int64 v29; // rax
  const struct _tlgProvider_t *v30; // rax
  int v31; // r8d
  _QWORD *v32; // rax
  char *v33; // [rsp+30h] [rbp-69h]
  __int64 v34[2]; // [rsp+40h] [rbp-59h] BYREF
  __int64 v35; // [rsp+50h] [rbp-49h] BYREF
  __int64 v36; // [rsp+58h] [rbp-41h] BYREF
  __int64 v37; // [rsp+60h] [rbp-39h] BYREF
  __int64 v38; // [rsp+68h] [rbp-31h] BYREF
  __int64 v39; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v40[4]; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int16 *v41[4]; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v5 = a3;
  v39 = 0;
  v37 = 0;
  std::wstring::wstring(v41);
  v36 = 0;
  wil::AcquireSRWLockShared(&v36, (char *)this + 16);
  LOBYTE(v8) = 1;
  v9 = Vml::GuidToString(v40, a2, v8);
  v10 = (const char *)v9;
  if ( *(_QWORD *)(v9 + 24) > 7u )
    v10 = *(const char **)v9;
  v11 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,Schema::Resources::Processor::CpuGroupConfig,Vml::GuidLess,std::allocator<std::pair<_GUID const,Schema::Resources::Processor::CpuGroupConfig>>,0>>::find(
                    (char *)this + 32,
                    v34,
                    a2);
  wil::details::in1diag3::Throw_HrIfFalseMsg(
    retaddr,
    (void *)0x156,
    (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
    (const char *)0x80070490LL,
    *v11 == *((_QWORD *)this + 4),
    (bool)"CPU group %ws already exists.",
    v10);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v40);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v36);
  if ( (_BYTE)v5 == 1 )
  {
    v13 = VidOpenStatisticsHandle(v12);
    v35 = v13;
    wil::details::in1diag3::Throw_HrIfFalseMsg(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
      (const char *)0x8000FFFFLL,
      (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL,
      (bool)"Failed to open VID statistics handle",
      v33);
    if ( !(unsigned int)VidCreateCpuGroup(v13, *((_QWORD *)a2 + 3), *((unsigned int *)a2 + 4), &v39) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
        v14);
    v15 = v39;
    *((_QWORD *)a2 + 9) = v39;
    if ( a4 )
    {
      if ( !(unsigned int)VidGetCpuGroupProperty(v13, v15, 0x10000, &v37) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x168,
          (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
          v16);
      LODWORD(v34[0]) = 0x10000;
      v34[1] = v37;
      v17 = (_OWORD *)*((_QWORD *)a2 + 7);
      if ( v17 == *((_OWORD **)a2 + 8) )
      {
        std::vector<Schema::Resources::Processor::CpuGroupProperty>::_Emplace_reallocate<Schema::Resources::Processor::CpuGroupProperty const &>(
          (char *)a2 + 48,
          v17,
          v34);
      }
      else
      {
        *v17 = *(_OWORD *)v34;
        *((_QWORD *)a2 + 7) += 16LL;
      }
      if ( !(unsigned int)VidGetCpuGroupProperty(v13, v39, 0x20000, &v37) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x170,
          (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
          v18);
      LODWORD(v34[0]) = 0x20000;
      v34[1] = v37;
      v19 = (_OWORD *)*((_QWORD *)a2 + 7);
      if ( v19 == *((_OWORD **)a2 + 8) )
      {
        std::vector<Schema::Resources::Processor::CpuGroupProperty>::_Emplace_reallocate<Schema::Resources::Processor::CpuGroupProperty const &>(
          (char *)a2 + 48,
          v19,
          v34);
      }
      else
      {
        *v19 = *(_OWORD *)v34;
        *((_QWORD *)a2 + 7) += 16LL;
      }
      if ( !(unsigned int)VidGetCpuGroupProperty(v13, v39, 196608, &v37) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x177,
          (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
          v20);
      LODWORD(v34[0]) = 196608;
      v34[1] = v37;
      v21 = (_OWORD *)*((_QWORD *)a2 + 7);
      if ( v21 == *((_OWORD **)a2 + 8) )
      {
        std::vector<Schema::Resources::Processor::CpuGroupProperty>::_Emplace_reallocate<Schema::Resources::Processor::CpuGroupProperty const &>(
          (char *)a2 + 48,
          v21,
          v34);
      }
      else
      {
        *v21 = *(_OWORD *)v34;
        *((_QWORD *)a2 + 7) += 16LL;
      }
      if ( !(unsigned int)VidGetCpuGroupProperty(v13, v39, 0x40000, &v37) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x17E,
          (unsigned int)"onecore\\vm\\compute\\management\\resources\\processor\\cpuresourceallocator.cpp",
          v22);
      LODWORD(v34[0]) = 0x40000;
      v34[1] = v37;
      v23 = (_OWORD *)*((_QWORD *)a2 + 7);
      if ( v23 == *((_OWORD **)a2 + 8) )
      {
        std::vector<Schema::Resources::Processor::CpuGroupProperty>::_Emplace_reallocate<Schema::Resources::Processor::CpuGroupProperty const &>(
          (char *)a2 + 48,
          v23,
          v34);
      }
      else
      {
        *v23 = *(_OWORD *)v34;
        *((_QWORD *)a2 + 7) += 16LL;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(&v35);
  }
  v36 = 0;
  wil::AcquireSRWLockExclusive(&v36, (char *)this + 16);
  std::_Tree<std::_Tmap_traits<_GUID,Schema::Resources::Processor::CpuGroupConfig,Vml::GuidLess,std::allocator<std::pair<_GUID const,Schema::Resources::Processor::CpuGroupConfig>>,0>>::emplace<_GUID &,Schema::Resources::Processor::CpuGroupConfig &>(
    (char *)this + 32,
    v34,
    a2,
    a2);
  v24 = Marshal::ToJson<Schema::Resources::Processor::CpuGroupConfig &,>(v40, v34[0] + 48);
  std::wstring::operator=(v41, v24);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v40);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v36);
  if ( !*((_DWORD *)this + 12) )
  {
    v35 = 0;
    wil::AcquireSRWLockExclusive(&v35, (char *)this + 24);
    v36 = 0;
    ComputeService::RecoveryStore::OpenVolatileCpuGroupsRegKey(&v36);
    v26 = *((_DWORD *)a2 + 18);
    v27 = Vml::GuidToString(v40, a2, 0);
    if ( *(_QWORD *)(v27 + 24) > 7u )
      v27 = *(_QWORD *)v27;
    LODWORD(v38) = v26;
    Vml::VmRegistryKey::SetValue((Vml::VmRegistryKey *)&v36, (const unsigned __int16 *)v27, 4u, &v38, 4u);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v40);
    if ( (_BYTE)v5 == 1 )
    {
      v38 = 0;
      ComputeService::RecoveryStore::OpenPersistentCpuGroupsRegKey(&v38);
      v28 = (const unsigned __int16 *)v41;
      if ( v41[3] > (unsigned __int16 *)7 )
        v28 = v41[0];
      v29 = Vml::GuidToString(v40, a2, 0);
      if ( *(_QWORD *)(v29 + 24) > 7u )
        v29 = *(_QWORD *)v29;
      Vml::VmRegistryKey::SetValue((Vml::VmRegistryKey *)&v38, (const unsigned __int16 *)v29, v28);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v40);
      Vml::VmRegistryKey::~VmRegistryKey((Vml::VmRegistryKey *)&v38);
    }
    Vml::VmRegistryKey::~VmRegistryKey((Vml::VmRegistryKey *)&v36);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v35);
  }
  if ( ComputeService::Diagnostics::TraceProvider::IsEnabled(v25, 0x1000u) )
  {
    std::wstring::wstring(v40);
    (*(void (__fastcall **)(char *, struct Schema::Resources::Processor::CpuGroupConfig *, _QWORD *))(*((_QWORD *)this + 1) + 8LL))(
      (char *)this + 8,
      a2,
      v40);
    v30 = ComputeService::Diagnostics::TraceProvider::Provider();
    if ( *(_DWORD *)v30 > 4u && (unsigned __int8)tlgKeywordOn(v30, 4096, v30) )
    {
      LODWORD(v38) = v5;
      v32 = v40;
      if ( v40[3] > 7u )
        v32 = (_QWORD *)v40[0];
      v35 = (__int64)v32;
      v36 = *((_QWORD *)a2 + 9);
      v34[0] = (__int64)a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v31,
        (__int64)v34,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v38);
    }
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v40);
  }
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v41);
}

```

## disassembly

```asm
0x14028eaf4  mov     [rsp-8+arg_10], rbx
0x14028eaf9  push    rbp
0x14028eafa  push    rsi
0x14028eafb  push    rdi
0x14028eafc  push    r12
0x14028eafe  push    r13
0x14028eb00  push    r14
0x14028eb02  push    r15
0x14028eb04  lea     rbp, [rsp-27h]
0x14028eb09  sub     rsp, 0C0h
0x14028eb10  mov     rax, cs:__security_cookie
0x14028eb17  xor     rax, rsp
0x14028eb1a  mov     [rbp+57h+var_38], rax
0x14028eb1e  mov     dil, r9b
0x14028eb21  movzx   r15d, r8b
0x14028eb25  mov     rsi, rdx
0x14028eb28  mov     r14, rcx
0x14028eb2b  xor     ebx, ebx
0x14028eb2d  mov     [rbp+57h+var_80], rbx
0x14028eb31  mov     [rbp+57h+var_90], rbx
0x14028eb35  lea     rcx, [rbp+57h+var_58]; void *
0x14028eb39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14028eb3e  nop
0x14028eb3f  mov     [rbp+57h+var_98], rbx
0x14028eb43  lea     rdx, [r14+10h]
0x14028eb47  lea     rcx, [rbp+57h+var_98]
0x14028eb4b  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x14028eb50  nop
0x14028eb51  mov     r8b, 1
0x14028eb54  mov     rdx, rsi
0x14028eb57  lea     rcx, [rbp+57h+var_78]
0x14028eb5b  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x14028eb60  mov     rbx, rax
0x14028eb63  cmp     qword ptr [rax+18h], 7
0x14028eb68  jbe     short loc_14028EB6D
0x14028eb6a  mov     rbx, [rax]
0x14028eb6d  lea     r12, [r14+20h]
0x14028eb71  mov     r8, rsi
0x14028eb74  lea     rdx, [rbp+57h+var_B0]
0x14028eb78  mov     rcx, r12
0x14028eb7b  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,Schema::Resources::Processor::CpuGroupConfig,Vml::GuidLess,std::allocator<std::pair<_GUID const,Schema::Resources::Processor::CpuGroupConfig>>,0>>::find(_GUID const &)
0x14028eb80  mov     rcx, [r12]
0x14028eb84  cmp     [rax], rcx
0x14028eb87  setz    al
0x14028eb8a  mov     rcx, [rbp+5Fh]; this
0x14028eb8e  mov     [rsp+0F0h+var_C0], rbx; char *
0x14028eb93  lea     rdx, aCpuGroupWsAlre; "CPU group %ws already exists."
0x14028eb9a  mov     qword ptr [rsp+0F0h+var_C8], rdx; bool
0x14028eb9f  mov     [rsp+0F0h+var_D0], al; char
0x14028eba3  mov     r9d, 80070490h; char *
0x14028eba9  lea     r8, aOnecoreVmCompu_105; "onecore\\vm\\compute\\management\\resou"...
0x14028ebb0  mov     edx, 156h; void *
0x14028ebb5  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x14028ebba  nop
0x14028ebbb  lea     rcx, [rbp+57h+var_78]; this
0x14028ebbf  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14028ebc4  nop
0x14028ebc5  lea     rcx, [rbp+57h+var_98]
0x14028ebc9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028ebce  cmp     r15b, 1
0x14028ebd2  jnz     loc_14028EDD4
0x14028ebd8  call    cs:__imp_VidOpenStatisticsHandle
0x14028ebdf  nop     dword ptr [rax+rax+00h]
0x14028ebe4  mov     rbx, rax
0x14028ebe7  mov     [rbp+57h+var_A0], rax
0x14028ebeb  dec     rax
0x14028ebee  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14028ebf2  setbe   al
0x14028ebf5  mov     rcx, [rbp+5Fh]; this
0x14028ebf9  lea     rdx, aFailedToOpenVi; "Failed to open VID statistics handle"
0x14028ec00  mov     qword ptr [rsp+0F0h+var_C8], rdx; bool
0x14028ec05  mov     [rsp+0F0h+var_D0], al; char
0x14028ec09  mov     r9d, 8000FFFFh; char *
0x14028ec0f  lea     r8, aOnecoreVmCompu_105; "onecore\\vm\\compute\\management\\resou"...
0x14028ec16  mov     edx, 15Eh; void *
0x14028ec1b  call    ?Throw_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x14028ec20  lea     r9, [rbp+57h+var_80]
0x14028ec24  mov     r8d, [rsi+10h]
0x14028ec28  mov     rdx, [rsi+18h]
0x14028ec2c  mov     rcx, rbx
0x14028ec2f  call    cs:__imp_VidCreateCpuGroup
0x14028ec36  nop     dword ptr [rax+rax+00h]
0x14028ec3b  mov     rcx, [rbp+5Fh]; this
0x14028ec3f  test    eax, eax
0x14028ec41  jz      loc_14028F002
0x14028ec47  mov     rdx, [rbp+57h+var_80]
0x14028ec4b  mov     [rsi+48h], rdx
0x14028ec4f  test    dil, dil
0x14028ec52  jz      loc_14028EDCB
0x14028ec58  lea     r9, [rbp+57h+var_90]
0x14028ec5c  mov     edi, 10000h
0x14028ec61  mov     r8d, edi
0x14028ec64  mov     rcx, rbx
0x14028ec67  call    cs:__imp_VidGetCpuGroupProperty
0x14028ec6e  nop     dword ptr [rax+rax+00h]
0x14028ec73  mov     rcx, [rbp+5Fh]; this
0x14028ec77  test    eax, eax
0x14028ec79  jz      loc_14028F014
0x14028ec7f  mov     dword ptr [rbp+57h+var_B0], edi
0x14028ec82  mov     rax, [rbp+57h+var_90]
0x14028ec86  mov     [rbp+57h+var_B0+8], rax
0x14028ec8a  lea     rdi, [rsi+30h]
0x14028ec8e  mov     rdx, [rdi+8]
0x14028ec92  cmp     rdx, [rdi+10h]
0x14028ec96  jz      short loc_14028ECA7
0x14028ec98  movups  xmm0, xmmword ptr [rbp+57h+var_B0]
0x14028ec9c  movdqu  xmmword ptr [rdx], xmm0
0x14028eca0  add     qword ptr [rdi+8], 10h
0x14028eca5  jmp     short loc_14028ECB3
0x14028eca7  lea     r8, [rbp+57h+var_B0]
0x14028ecab  mov     rcx, rdi
0x14028ecae  call    ??$_Emplace_reallocate@AEBUCpuGroupProperty@Processor@Resources@Schema@@@?$vector@UCpuGroupProperty@Processor@Resources@Schema@@V?$allocator@UCpuGroupProperty@Processor@Resources@Schema@@@std@@@std@@AEAAPEAUCpuGroupProperty@Processor@Resources@Schema@@QEAU2345@AEBU2345@@Z; std::vector<Schema::Resources::Processor::CpuGroupProperty>::_Emplace_reallocate<Schema::Resources::Processor::CpuGroupProperty const &>(Schema::Resources::Processor::CpuGroupProperty * const,Schema::Resources::Processor::CpuGroupProperty const &)
0x14028ecb3  lea     r9, [rbp+57h+var_90]
0x14028ecb7  mov     r8d, 20000h
0x14028ecbd  mov     rdx, [rbp+57h+var_80]
0x14028ecc1  mov     rcx, rbx
0x14028ecc4  call    cs:__imp_VidGetCpuGroupProperty
0x14028eccb  nop     dword ptr [rax+rax+00h]
0x14028ecd0  mov     rcx, [rbp+5Fh]; this
0x14028ecd4  test    eax, eax
0x14028ecd6  jz      loc_14028F026
0x14028ecdc  mov     dword ptr [rbp+57h+var_B0], 20000h
0x14028ece3  mov     rax, [rbp+57h+var_90]
0x14028ece7  mov     [rbp+57h+var_B0+8], rax
0x14028eceb  mov     rdx, [rdi+8]
0x14028ecef  cmp     rdx, [rdi+10h]
0x14028ecf3  jz      short loc_14028ED04
0x14028ecf5  movups  xmm0, xmmword ptr [rbp+57h+var_B0]
0x14028ecf9  movdqu  xmmword ptr [rdx], xmm0
0x14028ecfd  add     qword ptr [rdi+8], 10h
0x14028ed02  jmp     short loc_14028ED10
0x14028ed04  lea     r8, [rbp+57h+var_B0]
0x14028ed08  mov     rcx, rdi
0x14028ed0b  call    ??$_Emplace_reallocate@AEBUCpuGroupProperty@Processor@Resources@Schema@@@?$vector@UCpuGroupProperty@Processor@Resources@Schema@@V?$allocator@UCpuGroupProperty@Processor@Resources@Schema@@@std@@@std@@AEAAPEAUCpuGroupProperty@Processor@Resources@Schema@@QEAU2345@AEBU2345@@Z; std::vector<Schema::Resources::Processor::CpuGroupProperty>::_Emplace_reallocate<Schema::Resources::Processor::CpuGroupProperty const &>(Schema::Resources::Processor::CpuGroupProperty * const,Schema::Resources::Processor::CpuGroupProperty const &)
0x14028ed10  lea     r9, [rbp+57h+var_90]
0x14028ed14  mov     r8d, 30000h
0x14028ed1a  mov     rdx, [rbp+57h+var_80]
0x14028ed1e  mov     rcx, rbx
0x14028ed21  call    cs:__imp_VidGetCpuGroupProperty
0x14028ed28  nop     dword ptr [rax+rax+00h]
0x14028ed2d  mov     rcx, [rbp+5Fh]; this
0x14028ed31  test    eax, eax
0x14028ed33  jz      loc_14028F038
0x14028ed39  mov     dword ptr [rbp+57h+var_B0], 30000h
0x14028ed40  mov     rax, [rbp+57h+var_90]
0x14028ed44  mov     [rbp+57h+var_B0+8], rax
0x14028ed48  mov     rdx, [rdi+8]
0x14028ed4c  cmp     rdx, [rdi+10h]
0x14028ed50  jz      short loc_14028ED61
0x14028ed52  movups  xmm0, xmmword ptr [rbp+57h+var_B0]
0x14028ed56  movdqu  xmmword ptr [rdx], xmm0
0x14028ed5a  add     qword ptr [rdi+8], 10h
0x14028ed5f  jmp     short loc_14028ED6D
0x14028ed61  lea     r8, [rbp+57h+var_B0]
0x14028ed65  mov     rcx, rdi
0x14028ed68  call    ??$_Emplace_reallocate@AEBUCpuGroupProperty@Processor@Resources@Schema@@@?$vector@UCpuGroupProperty@Processor@Resources@Schema@@V?$allocator@UCpuGroupProperty@Processor@Resources@Schema@@@std@@@std@@AEAAPEAUCpuGroupProperty@Processor@Resources@Schema@@QEAU2345@AEBU2345@@Z; std::vector<Schema::Resources::Processor::CpuGroupProperty>::_Emplace_reallocate<Schema::Resources::Processor::CpuGroupProperty const &>(Schema::Resources::Processor::CpuGroupProperty * const,Schema::Resources::Processor::CpuGroupProperty const &)
0x14028ed6d  lea     r9, [rbp+57h+var_90]
0x14028ed71  mov     r8d, 40000h
0x14028ed77  mov     rdx, [rbp+57h+var_80]
0x14028ed7b  mov     rcx, rbx
0x14028ed7e  call    cs:__imp_VidGetCpuGroupProperty
0x14028ed85  nop     dword ptr [rax+rax+00h]
0x14028ed8a  mov     rcx, [rbp+5Fh]; this
0x14028ed8e  test    eax, eax
0x14028ed90  jz      loc_14028EFF0
0x14028ed96  mov     dword ptr [rbp+57h+var_B0], 40000h
0x14028ed9d  mov     rax, [rbp+57h+var_90]
0x14028eda1  mov     [rbp+57h+var_B0+8], rax
0x14028eda5  mov     rdx, [rdi+8]
0x14028eda9  cmp     rdx, [rdi+10h]
0x14028edad  jz      short loc_14028EDBE
0x14028edaf  movups  xmm0, xmmword ptr [rbp+57h+var_B0]
0x14028edb3  movdqu  xmmword ptr [rdx], xmm0
0x14028edb7  add     qword ptr [rdi+8], 10h
0x14028edbc  jmp     short loc_14028EDCB
0x14028edbe  lea     r8, [rbp+57h+var_B0]
0x14028edc2  mov     rcx, rdi
0x14028edc5  call    ??$_Emplace_reallocate@AEBUCpuGroupProperty@Processor@Resources@Schema@@@?$vector@UCpuGroupProperty@Processor@Resources@Schema@@V?$allocator@UCpuGroupProperty@Processor@Resources@Schema@@@std@@@std@@AEAAPEAUCpuGroupProperty@Processor@Resources@Schema@@QEAU2345@AEBU2345@@Z; std::vector<Schema::Resources::Processor::CpuGroupProperty>::_Emplace_reallocate<Schema::Resources::Processor::CpuGroupProperty const &>(Schema::Resources::Processor::CpuGroupProperty * const,Schema::Resources::Processor::CpuGroupProperty const &)
0x14028edca  nop
0x14028edcb  lea     rcx, [rbp+57h+var_A0]
0x14028edcf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?VidCloseStatisticsHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>(void)
0x14028edd4  xor     edi, edi
0x14028edd6  mov     [rbp+57h+var_98], rdi
0x14028edda  lea     rdx, [r14+10h]
0x14028edde  lea     rcx, [rbp+57h+var_98]
0x14028ede2  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14028ede7  nop
0x14028ede8  mov     r9, rsi
0x14028edeb  mov     r8, rsi
0x14028edee  lea     rdx, [rbp+57h+var_B0]
0x14028edf2  mov     rcx, r12
0x14028edf5  call    ??$emplace@AEAU_GUID@@AEAUCpuGroupConfig@Processor@Resources@Schema@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UCpuGroupConfig@Processor@Resources@Schema@@@std@@@std@@@std@@@std@@_N@1@AEAU_GUID@@AEAUCpuGroupConfig@Processor@Resources@Schema@@@Z; std::_Tree<std::_Tmap_traits<_GUID,Schema::Resources::Processor::CpuGroupConfig,Vml::GuidLess,std::allocator<std::pair<_GUID const,Schema::Resources::Processor::CpuGroupConfig>>,0>>::emplace<_GUID &,Schema::Resources::Processor::CpuGroupConfig &>(_GUID &,Schema::Resources::Processor::CpuGroupConfig &)
0x14028edfa  mov     rdx, [rbp+57h+var_B0]
0x14028edfe  add     rdx, 30h ; '0'
0x14028ee02  lea     rcx, [rbp+57h+var_78]
0x14028ee06  call    ??$ToJson@AEAUCpuGroupConfig@Processor@Resources@Schema@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUCpuGroupConfig@Processor@Resources@Schema@@W4MarshalFlags@0@@Z; Marshal::ToJson<Schema::Resources::Processor::CpuGroupConfig &,>(Schema::Resources::Processor::CpuGroupConfig &,Marshal::MarshalFlags)
0x14028ee0b  mov     rdx, rax
0x14028ee0e  lea     rcx, [rbp+57h+var_58]
0x14028ee12  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14028ee17  lea     rcx, [rbp+57h+var_78]; this
0x14028ee1b  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14028ee20  nop
0x14028ee21  lea     rcx, [rbp+57h+var_98]
0x14028ee25  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028ee2a  lea     r12d, [rdi+4]
0x14028ee2e  cmp     [r14+30h], edi
0x14028ee32  jnz     loc_14028EF0D
0x14028ee38  mov     [rbp+57h+var_A0], rdi
0x14028ee3c  lea     rdx, [r14+18h]
0x14028ee40  lea     rcx, [rbp+57h+var_A0]
0x14028ee44  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14028ee49  nop
0x14028ee4a  mov     [rbp+57h+var_98], rdi
0x14028ee4e  lea     rcx, [rbp+57h+var_98]
0x14028ee52  call    ?OpenVolatileCpuGroupsRegKey@RecoveryStore@ComputeService@@YA?AVVmRegistryKey@Vml@@K@Z; ComputeService::RecoveryStore::OpenVolatileCpuGroupsRegKey(ulong)
0x14028ee57  nop
0x14028ee58  mov     ebx, [rsi+48h]
0x14028ee5b  xor     r8d, r8d
0x14028ee5e  mov     rdx, rsi
0x14028ee61  lea     rcx, [rbp+57h+var_78]
0x14028ee65  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x14028ee6a  nop
0x14028ee6b  cmp     qword ptr [rax+18h], 7
0x14028ee70  jbe     short loc_14028EE75
0x14028ee72  mov     rax, [rax]
0x14028ee75  mov     dword ptr [rbp+57h+var_88], ebx
0x14028ee78  mov     dword ptr [rsp+0F0h+var_D0], r12d; unsigned int
0x14028ee7d  lea     r9, [rbp+57h+var_88]; void *
0x14028ee81  mov     r8d, r12d; unsigned int
0x14028ee84  mov     rdx, rax; unsigned __int16 *
0x14028ee87  lea     rcx, [rbp+57h+var_98]; this
0x14028ee8b  call    ?SetValue@VmRegistryKey@Vml@@QEAAXPEBGKPEBXK@Z; Vml::VmRegistryKey::SetValue(ushort const *,ulong,void const *,ulong)
0x14028ee90  nop
0x14028ee91  lea     rcx, [rbp+57h+var_78]; this
0x14028ee95  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14028ee9a  cmp     r15b, 1
0x14028ee9e  jnz     short loc_14028EEFA
0x14028eea0  mov     [rbp+57h+var_88], rdi
0x14028eea4  lea     rcx, [rbp+57h+var_88]
0x14028eea8  call    ?OpenPersistentCpuGroupsRegKey@RecoveryStore@ComputeService@@YA?AVVmRegistryKey@Vml@@K@Z; ComputeService::RecoveryStore::OpenPersistentCpuGroupsRegKey(ulong)
0x14028eead  nop
0x14028eeae  lea     rbx, [rbp+57h+var_58]
0x14028eeb2  cmp     [rbp+57h+var_40], 7
0x14028eeb7  cmova   rbx, [rbp+57h+var_58]
0x14028eebc  xor     r8d, r8d
0x14028eebf  mov     rdx, rsi
0x14028eec2  lea     rcx, [rbp+57h+var_78]
0x14028eec6  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x14028eecb  nop
0x14028eecc  cmp     qword ptr [rax+18h], 7
0x14028eed1  jbe     short loc_14028EED6
0x14028eed3  mov     rax, [rax]
0x14028eed6  mov     r8, rbx; unsigned __int16 *
0x14028eed9  mov     rdx, rax; unsigned __int16 *
0x14028eedc  lea     rcx, [rbp+57h+var_88]; this
0x14028eee0  call    ?SetValue@VmRegistryKey@Vml@@QEAAXPEBG0@Z; Vml::VmRegistryKey::SetValue(ushort const *,ushort const *)
0x14028eee5  nop
0x14028eee6  lea     rcx, [rbp+57h+var_78]; this
0x14028eeea  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14028eeef  nop
0x14028eef0  lea     rcx, [rbp+57h+var_88]; this
0x14028eef4  call    ??1VmRegistryKey@Vml@@QEAA@XZ; Vml::VmRegistryKey::~VmRegistryKey(void)
0x14028eef9  nop
0x14028eefa  lea     rcx, [rbp+57h+var_98]; this
0x14028eefe  call    ??1VmRegistryKey@Vml@@QEAA@XZ; Vml::VmRegistryKey::~VmRegistryKey(void)
0x14028ef03  nop
0x14028ef04  lea     rcx, [rbp+57h+var_A0]
0x14028ef08  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028ef0d  mov     ebx, 1000h
0x14028ef12  mov     edx, ebx; unsigned __int64
0x14028ef14  call    ?IsEnabled@TraceProvider@Diagnostics@ComputeService@@SA_NE_K@Z; ComputeService::Diagnostics::TraceProvider::IsEnabled(uchar,unsigned __int64)
0x14028ef19  test    al, al
0x14028ef1b  jz      loc_14028EFBF
0x14028ef21  lea     rcx, [rbp+57h+var_78]; void *
0x14028ef25  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14028ef2a  nop
0x14028ef2b  lea     rcx, [r14+8]
0x14028ef2f  mov     rax, [rcx]
0x14028ef32  lea     r8, [rbp+57h+var_78]
0x14028ef36  mov     rdx, rsi
0x14028ef39  mov     rax, [rax+8]
0x14028ef3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14028ef42  call    ?Provider@TraceProvider@Diagnostics@ComputeService@@SAPEBU_tlgProvider_t@@XZ; ComputeService::Diagnostics::TraceProvider::Provider(void)
0x14028ef47  mov     r8, rax
0x14028ef4a  mov     ecx, [rax]
0x14028ef4c  cmp     ecx, r12d
0x14028ef4f  jbe     short loc_14028EFB5
0x14028ef51  mov     edx, ebx
0x14028ef53  mov     rcx, rax
0x14028ef56  call    _tlgKeywordOn
0x14028ef5b  test    al, al
0x14028ef5d  jz      short loc_14028EFB5
0x14028ef5f  mov     dword ptr [rbp+57h+var_88], r15d
0x14028ef63  lea     rax, [rbp+57h+var_78]
0x14028ef67  cmp     [rbp+57h+var_60], 7
0x14028ef6c  cmova   rax, [rbp+57h+var_78]
0x14028ef71  mov     [rbp+57h+var_A0], rax
0x14028ef75  mov     rax, [rsi+48h]
0x14028ef79  mov     [rbp+57h+var_98], rax
0x14028ef7d  mov     [rbp+57h+var_B0], rsi
  ... truncated ...
```
