# ComputeService::Management::UtilityVmTemplateOrchestrator::Recover(std::shared_ptr<ComputeService::Management::ComputeSystem> const &)

- ea: `0x14008b9a0`
- end: `0x14008bbea`
- name: `?Recover@UtilityVmTemplateOrchestrator@Management@ComputeService@@UEAA_NAEBV?$shared_ptr@VComputeSystem@Management@ComputeService@@@std@@@Z`
- size: `586`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x140017040`
- `0x140021de0`
- `0x140021ea4`
- `0x1400286f0`
- `0x1400421f0`
- `0x1400429e4`
- `0x14005b868`
- `0x14008b9a0`
- `0x14008bbf0`
- `0x14008bcb0`
- `0x14008c800`
- `0x1401332f0`
- `0x140134048`
- `0x14023740c`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x14008ba96`
- `RPCRT4!UuidFromStringW` at `0x14008ba96`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14008baee`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14008bb2d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14008bb6c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14008baee`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14008bb2d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14008bb6c`

## string_xrefs

- `0x14008b9f3`: `UtilityVmTemplate_Recover`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall ComputeService::Management::UtilityVmTemplateOrchestrator::Recover(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rcx
  _QWORD *v4; // rdx
  unsigned __int16 *v5; // rcx
  const struct _GUID *v6; // rdx
  const WCHAR *v7; // rcx
  const WCHAR *v8; // rcx
  const unsigned __int16 *v9; // rdx
  const WCHAR *v10; // rcx
  ComputeService::RecoveryStore *v11; // rcx
  _QWORD *v13; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v17; // [rsp+48h] [rbp-B8h]
  UUID Uuid; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 StringUuid[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v20; // [rsp+78h] [rbp-88h]
  _QWORD v21[42]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v21, 0, sizeof(v21));
  v3 = (_QWORD *)(**(_QWORD **)a2 + 8LL);
  if ( *(_QWORD *)(**(_QWORD **)a2 + 32LL) > 7u )
    v3 = (_QWORD *)*v3;
  v13 = v3;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v21,
    "UtilityVmTemplate_Recover");
  v21[0] = &ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Recover::`vftable';
  ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Recover::StartActivity<unsigned short const *>(
    v21,
    &v13);
  v14 = 0;
  v4 = (_QWORD *)(**(_QWORD **)a2 + 8LL);
  if ( *(_QWORD *)(**(_QWORD **)a2 + 32LL) > 7u )
    v4 = (_QWORD *)*v4;
  ComputeService::RecoveryStore::OpenSystemRegKey(&v14, v4, 131097);
  std::wstring::wstring(StringUuid);
  Uuid = 0;
  if ( (unsigned int)Vml::VmRegistryKey::QueryValue(&v14, L"VmId", StringUuid) )
  {
    if ( v20 <= 7 )
    {
      v5 = StringUuid;
    }
    else
    {
      v5 = *(unsigned __int16 **)StringUuid;
      if ( !*(_QWORD *)StringUuid )
        goto LABEL_12;
    }
    if ( !UuidFromStringW(v5, &Uuid) )
      ComputeService::Vmwp::TerminateWorkerProcess((ComputeService::Vmwp *)&Uuid, v6);
  }
LABEL_12:
  std::wstring::wstring(lpFileName);
  if ( (unsigned int)Vml::VmRegistryKey::QueryValue(&v14, L"ScratchBaseVhd", lpFileName) && v16 )
  {
    v7 = (const WCHAR *)lpFileName;
    if ( v17 > 7 )
      v7 = lpFileName[0];
    DeleteFileW(v7);
  }
  if ( (unsigned int)Vml::VmRegistryKey::QueryValue(&v14, L"ScratchDiffVhd", lpFileName) && v16 )
  {
    v8 = (const WCHAR *)lpFileName;
    if ( v17 > 7 )
      v8 = lpFileName[0];
    DeleteFileW(v8);
  }
  if ( (unsigned int)Vml::VmRegistryKey::QueryValue(&v14, L"RuntimeStateFile", lpFileName) && v16 )
  {
    v10 = (const WCHAR *)lpFileName;
    if ( v17 > 7 )
      v10 = lpFileName[0];
    DeleteFileW(v10);
  }
  v11 = (ComputeService::RecoveryStore *)(**(_QWORD **)a2 + 8LL);
  if ( *(_QWORD *)(**(_QWORD **)a2 + 32LL) > 7u )
    v11 = *(ComputeService::RecoveryStore **)v11;
  ComputeService::RecoveryStore::RemoveSystem(v11, v9);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v21,
    0);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpFileName);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)StringUuid);
  Vml::VmRegistryKey::~VmRegistryKey((Vml::VmRegistryKey *)&v14);
  ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Recover::~UtilityVmTemplate_Recover((ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Recover *)v21);
  return 0;
}

```

## disassembly

```asm
0x14008b9a0  mov     [rsp-8+arg_0], rbx
0x14008b9a5  push    rbp
0x14008b9a6  lea     rbp, [rsp-0E0h]
0x14008b9ae  sub     rsp, 1E0h
0x14008b9b5  mov     rax, cs:__security_cookie
0x14008b9bc  xor     rax, rsp
0x14008b9bf  mov     [rbp+0E0h+var_10], rax
0x14008b9c6  mov     rbx, rdx
0x14008b9c9  xor     edx, edx; Val
0x14008b9cb  mov     r8d, 150h; Size
0x14008b9d1  lea     rcx, [rbp+0E0h+var_160]; void *
0x14008b9d5  call    memset_0
0x14008b9da  mov     rax, [rbx]
0x14008b9dd  mov     rcx, [rax]
0x14008b9e0  add     rcx, 8
0x14008b9e4  cmp     qword ptr [rcx+18h], 7
0x14008b9e9  jbe     short loc_14008B9EE
0x14008b9eb  mov     rcx, [rcx]
0x14008b9ee  mov     [rsp+1E0h+var_1C0], rcx
0x14008b9f3  lea     rdx, aUtilityvmtempl_1; "UtilityVmTemplate_Recover"
0x14008b9fa  lea     rcx, [rbp+0E0h+var_160]
0x14008b9fe  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14008ba03  lea     rax, ??_7UtilityVmTemplate_Recover@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Recover::`vftable'
0x14008ba0a  mov     [rbp+0E0h+var_160], rax
0x14008ba0e  lea     rdx, [rsp+1E0h+var_1C0]
0x14008ba13  lea     rcx, [rbp+0E0h+var_160]
0x14008ba17  call    ??$StartActivity@PEBG@UtilityVmTemplate_Recover@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEBG@Z; ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Recover::StartActivity<ushort const *>(ushort const * &&)
0x14008ba1c  nop
0x14008ba1d  mov     [rsp+1E0h+var_1B8], 0
0x14008ba26  mov     rax, [rbx]
0x14008ba29  mov     rdx, [rax]
0x14008ba2c  add     rdx, 8
0x14008ba30  cmp     qword ptr [rdx+18h], 7
0x14008ba35  jbe     short loc_14008BA3A
0x14008ba37  mov     rdx, [rdx]
0x14008ba3a  mov     r8d, 20019h
0x14008ba40  lea     rcx, [rsp+1E0h+var_1B8]
0x14008ba45  call    ?OpenSystemRegKey@RecoveryStore@ComputeService@@YA?AVVmRegistryKey@Vml@@PEBGK@Z; ComputeService::RecoveryStore::OpenSystemRegKey(ushort const *,ulong)
0x14008ba4a  nop
0x14008ba4b  lea     rcx, [rsp+1E0h+StringUuid]; void *
0x14008ba50  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14008ba55  nop
0x14008ba56  xorps   xmm0, xmm0
0x14008ba59  movups  xmmword ptr [rsp+1E0h+Uuid.Data1], xmm0
0x14008ba5e  lea     r8, [rsp+1E0h+StringUuid]
0x14008ba63  lea     rdx, aVmid; "VmId"
0x14008ba6a  lea     rcx, [rsp+1E0h+var_1B8]
0x14008ba6f  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Vml::VmRegistryKey::QueryValue(ushort const *,std::wstring &,bool)
0x14008ba74  test    eax, eax
0x14008ba76  jz      short loc_14008BAB0
0x14008ba78  cmp     [rsp+1E0h+var_168], 7
0x14008ba7e  jbe     short loc_14008BA8C
0x14008ba80  mov     rcx, qword ptr [rsp+1E0h+StringUuid]
0x14008ba85  test    rcx, rcx
0x14008ba88  jz      short loc_14008BAB0
0x14008ba8a  jmp     short loc_14008BA91
0x14008ba8c  lea     rcx, [rsp+1E0h+StringUuid]; StringUuid
0x14008ba91  lea     rdx, [rsp+1E0h+Uuid]; Uuid
0x14008ba96  call    cs:__imp_UuidFromStringW
0x14008ba9d  nop     dword ptr [rax+rax+00h]
0x14008baa2  test    eax, eax
0x14008baa4  jnz     short loc_14008BAB0
0x14008baa6  lea     rcx, [rsp+1E0h+Uuid]; this
0x14008baab  call    ?TerminateWorkerProcess@Vmwp@ComputeService@@YAXAEBU_GUID@@@Z; ComputeService::Vmwp::TerminateWorkerProcess(_GUID const &)
0x14008bab0  lea     rcx, [rsp+1E0h+lpFileName]; void *
0x14008bab5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14008baba  nop
0x14008babb  lea     r8, [rsp+1E0h+lpFileName]
0x14008bac0  lea     rdx, aScratchbasevhd; "ScratchBaseVhd"
0x14008bac7  lea     rcx, [rsp+1E0h+var_1B8]
0x14008bacc  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Vml::VmRegistryKey::QueryValue(ushort const *,std::wstring &,bool)
0x14008bad1  test    eax, eax
0x14008bad3  jz      short loc_14008BAFA
0x14008bad5  cmp     [rsp+1E0h+var_1A0], 0
0x14008badb  jz      short loc_14008BAFA
0x14008badd  lea     rcx, [rsp+1E0h+lpFileName]
0x14008bae2  cmp     [rsp+1E0h+var_198], 7
0x14008bae8  cmova   rcx, [rsp+1E0h+lpFileName]; lpFileName
0x14008baee  call    cs:__imp_DeleteFileW
0x14008baf5  nop     dword ptr [rax+rax+00h]
0x14008bafa  lea     r8, [rsp+1E0h+lpFileName]
0x14008baff  lea     rdx, aScratchdiffvhd; "ScratchDiffVhd"
0x14008bb06  lea     rcx, [rsp+1E0h+var_1B8]
0x14008bb0b  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Vml::VmRegistryKey::QueryValue(ushort const *,std::wstring &,bool)
0x14008bb10  test    eax, eax
0x14008bb12  jz      short loc_14008BB39
0x14008bb14  cmp     [rsp+1E0h+var_1A0], 0
0x14008bb1a  jz      short loc_14008BB39
0x14008bb1c  lea     rcx, [rsp+1E0h+lpFileName]
0x14008bb21  cmp     [rsp+1E0h+var_198], 7
0x14008bb27  cmova   rcx, [rsp+1E0h+lpFileName]; lpFileName
0x14008bb2d  call    cs:__imp_DeleteFileW
0x14008bb34  nop     dword ptr [rax+rax+00h]
0x14008bb39  lea     r8, [rsp+1E0h+lpFileName]
0x14008bb3e  lea     rdx, aRuntimestatefi; "RuntimeStateFile"
0x14008bb45  lea     rcx, [rsp+1E0h+var_1B8]
0x14008bb4a  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Vml::VmRegistryKey::QueryValue(ushort const *,std::wstring &,bool)
0x14008bb4f  test    eax, eax
0x14008bb51  jz      short loc_14008BB78
0x14008bb53  cmp     [rsp+1E0h+var_1A0], 0
0x14008bb59  jz      short loc_14008BB78
0x14008bb5b  lea     rcx, [rsp+1E0h+lpFileName]
0x14008bb60  cmp     [rsp+1E0h+var_198], 7
0x14008bb66  cmova   rcx, [rsp+1E0h+lpFileName]; lpFileName
0x14008bb6c  call    cs:__imp_DeleteFileW
0x14008bb73  nop     dword ptr [rax+rax+00h]
0x14008bb78  mov     rax, [rbx]
0x14008bb7b  mov     rcx, [rax]
0x14008bb7e  add     rcx, 8
0x14008bb82  cmp     qword ptr [rcx+18h], 7
0x14008bb87  jbe     short loc_14008BB8C
0x14008bb89  mov     rcx, [rcx]; this
0x14008bb8c  call    ?RemoveSystem@RecoveryStore@ComputeService@@YAXPEBG@Z; ComputeService::RecoveryStore::RemoveSystem(ushort const *)
0x14008bb91  xor     edx, edx
0x14008bb93  lea     rcx, [rbp+0E0h+var_160]
0x14008bb97  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$07$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,8,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14008bb9c  nop
0x14008bb9d  lea     rcx, [rsp+1E0h+lpFileName]; this
0x14008bba2  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14008bba7  nop
0x14008bba8  lea     rcx, [rsp+1E0h+StringUuid]; this
0x14008bbad  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14008bbb2  nop
0x14008bbb3  lea     rcx, [rsp+1E0h+var_1B8]; this
0x14008bbb8  call    ??1VmRegistryKey@Vml@@QEAA@XZ; Vml::VmRegistryKey::~VmRegistryKey(void)
0x14008bbbd  nop
0x14008bbbe  lea     rcx, [rbp+0E0h+var_160]; this
0x14008bbc2  call    ??1UtilityVmTemplate_Recover@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ; ComputeService::Diagnostics::TraceProvider::UtilityVmTemplate_Recover::~UtilityVmTemplate_Recover(void)
0x14008bbc7  xor     al, al
0x14008bbc9  mov     rcx, [rbp+0E0h+var_10]
0x14008bbd0  xor     rcx, rsp; StackCookie
0x14008bbd3  call    __security_check_cookie
0x14008bbd8  mov     rbx, [rsp+1E0h+arg_0]
0x14008bbe0  add     rsp, 1E0h
0x14008bbe7  pop     rbp
0x14008bbe8  retn
```
