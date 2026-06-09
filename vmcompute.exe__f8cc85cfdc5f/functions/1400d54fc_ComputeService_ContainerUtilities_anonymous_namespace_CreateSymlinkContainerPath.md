# ComputeService::ContainerUtilities::_anonymous_namespace_::CreateSymlinkContainerPath

- ea: `0x1400d54fc`
- end: `0x1400d5951`
- name: `ComputeService::ContainerUtilities::_anonymous_namespace_::CreateSymlinkContainerPath`
- size: `1109`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d5370`

## callees

- `0x140017040`
- `0x140017840`
- `0x140018d70`
- `0x14001d490`
- `0x140024030`
- `0x14002d7f0`
- `0x1400421f0`
- `0x140042468`
- `0x14004249c`
- `0x140044974`
- `0x1400d54fc`
- `0x1400d5958`
- `0x1400d5bb8`
- `0x1400d630c`
- `0x14010b3f4`
- `0x1401182b4`
- `0x1401332f0`
- `0x140142dac`
- `0x14017386c`

## import_xrefs

- `ntdll!NtSetInformationSymbolicLink` at `0x1400d581b`
- `ntdll!NtSetInformationSymbolicLink` at `0x1400d5865`
- `ntdll!NtSetInformationSymbolicLink` at `0x1400d581b`
- `ntdll!NtSetInformationSymbolicLink` at `0x1400d5865`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1400d57c3`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1400d57c3`
- `ntdll!NtMakePermanentObject` at `0x1400d58cd`
- `ntdll!NtMakePermanentObject` at `0x1400d58cd`
- `RPCRT4!UuidCreate` at `0x1400d56cb`
- `RPCRT4!UuidCreate` at `0x1400d56cb`

## string_xrefs

- `0x1400d565f`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400d57dd`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400d5835`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400d587f`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400d58e7`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400d564d`: `Cannot map a host path to the container's C: drive`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ComputeService::ContainerUtilities::_anonymous_namespace_::CreateSymlinkContainerPath(
        __int64 a1,
        ComputeService::Storage *a2,
        char *a3,
        ComputeService::Storage *a4,
        char a5,
        char a6,
        char a7)
{
  ComputeService::Storage *v7; // rbx
  char *v8; // rdi
  ComputeService::Storage *v11; // rcx
  bool IsDriveLetter; // r15
  __int64 v13; // rax
  void *ContainerNamespacePath; // rax
  char v15; // di
  ComputeService::Storage *v16; // r9
  _QWORD *v17; // r8
  __int64 v18; // rax
  Schema::Responses::System::CrashReportProcessDump *v19; // rcx
  __int64 v20; // rax
  unsigned __int16 **v21; // r9
  _QWORD *v22; // r8
  __int64 v23; // rax
  __int64 v24; // rax
  void **v25; // rax
  NTSTATUS v26; // eax
  const unsigned __int16 *v27; // r9
  int v28; // eax
  int v29; // eax
  const unsigned __int16 *v30; // r8
  NTSTATUS PermanentObject; // eax
  void *v32; // [rsp+20h] [rbp-E0h]
  const char *v33; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v34[8]; // [rsp+30h] [rbp-D0h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v36[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v37[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v38[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v39[32]; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  int v41; // [rsp+100h] [rbp+0h] BYREF
  HANDLE Object; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 *v43[3]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v44; // [rsp+128h] [rbp+28h]
  _QWORD v45[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v46; // [rsp+148h] [rbp+48h]
  _BYTE v47[32]; // [rsp+150h] [rbp+50h] BYREF
  UUID v48; // [rsp+170h] [rbp+70h] BYREF
  struct _UNICODE_STRING Name; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v50[32]; // [rsp+190h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v7 = a4;
  v8 = a3;
  v41 = 0;
  LOBYTE(v34[0]) = 0;
  if ( *((_QWORD *)a4 + 3) <= 7u )
    v11 = a4;
  else
    v11 = *(ComputeService::Storage **)a4;
  IsDriveLetter = ComputeService::Storage::IsDriveLetter(v11, v34, a3);
  std::wstring::wstring(v50);
  if ( *((_QWORD *)v8 + 3) > 7u )
    v8 = *(char **)v8;
  ComputeService::Storage::GetFinalDirectoryPaths((PCWSTR)v8);
  v13 = std::wstring::operator std::basic_string_view<unsigned short>(v50, v36);
  *(_DWORD *)&Uuid.Data2 = 0;
  *(_QWORD *)Uuid.Data4 = *(_QWORD *)v13;
  LOWORD(Uuid.Data1) = 2 * *(_WORD *)(v13 + 8);
  *(unsigned int *)((char *)&Uuid.Data1 + 2) = LOWORD(Uuid.Data1);
  Name = (struct _UNICODE_STRING)Uuid;
  std::wstring::wstring(v43);
  std::wstring::wstring(v47);
  if ( a7 )
  {
    ContainerNamespacePath = (void *)std::wstring::wstring(v39, &szPassword);
    v15 = 1;
  }
  else
  {
    ContainerNamespacePath = (void *)ComputeService::ContainerUtilities::QueryContainerNamespacePath(v38, a1);
    v15 = 2;
  }
  std::wstring::wstring(v45, ContainerNamespacePath);
  if ( (v15 & 2) != 0 )
  {
    v15 &= ~2u;
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v38);
  }
  if ( (v15 & 1) != 0 )
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v39);
  if ( IsDriveLetter )
  {
    if ( LOBYTE(v34[0]) == 67 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)0xD,
        (unsigned int)"Cannot map a host path to the container's C: drive",
        v33);
    if ( *((_QWORD *)v7 + 3) <= 7u )
      v16 = v7;
    else
      v16 = *(ComputeService::Storage **)v7;
    v17 = v45;
    if ( v46 > 7 )
      v17 = (_QWORD *)v45[0];
    v18 = Vml::FormatString(v36, L"%s\\GLOBAL??\\%s", v17, v16);
    std::wstring::operator=(v47, v18);
    v19 = (Schema::Responses::System::CrashReportProcessDump *)v36;
  }
  else
  {
    ComputeService::ContainerUtilities::_anonymous_namespace_::CreateMappedDirectoryRoot(v45);
    Uuid = 0;
    UuidCreate(&Uuid);
    v36[0] = Uuid;
    v20 = Vml::GuidToString(v37, v36, 0);
    std::wstring::operator=(v43, v20);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v37);
    v21 = v43;
    if ( v44 > 7 )
      v21 = (unsigned __int16 **)v43[0];
    v22 = v45;
    if ( v46 > 7 )
      v22 = (_QWORD *)v45[0];
    v23 = Vml::FormatString(v37, L"%s\\ContainerMappedDirectories\\%s", v22, v21);
    std::wstring::operator=(v47, v23);
    v19 = (Schema::Responses::System::CrashReportProcessDump *)v37;
  }
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(v19);
  v24 = std::wstring::operator std::basic_string_view<unsigned short>(v47, v36);
  *(_DWORD *)&Uuid.Data2 = 0;
  *(_QWORD *)Uuid.Data4 = *(_QWORD *)v24;
  LOWORD(Uuid.Data1) = 2 * *(_WORD *)(v24 + 8);
  *(unsigned int *)((char *)&Uuid.Data1 + 2) = LOWORD(Uuid.Data1);
  v48 = Uuid;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.Attributes, 0, 24);
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v48;
  Object = 0;
  v25 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&Object);
  v26 = NtCreateSymbolicLinkObject(v25, 0xFFFFFu, &ObjectAttributes, &Name);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
      (const char *)(unsigned int)v26,
      (int)v32);
  if ( a1 )
  {
    if ( a5 )
    {
      v41 = 1179817;
      v28 = NtSetInformationSymbolicLink(Object, 2, &v41, 4);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
          (const char *)(unsigned int)v28,
          (int)v32);
    }
    if ( a6 )
    {
      v41 = 1;
      v29 = NtSetInformationSymbolicLink(Object, 1, &v41, 4);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_NtStatus(
          retaddr,
          (void *)0xF6,
          (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
          (const char *)(unsigned int)v29,
          (int)v32);
    }
  }
  if ( v43[2] )
  {
    v30 = (const unsigned __int16 *)v43;
    if ( v44 > 7 )
      v30 = v43[0];
    if ( *((_QWORD *)v7 + 3) > 7u )
      v7 = *(ComputeService::Storage **)v7;
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(ComputeService::Storage **)a2;
    LOBYTE(v32) = a7;
    ComputeService::Storage::CreateMappedDirectoryLink(a2, (const unsigned __int16 *)v7, v30, v27, v32, (bool)v33);
  }
  PermanentObject = NtMakePermanentObject(Object);
  if ( PermanentObject < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
      (const char *)(unsigned int)PermanentObject,
      (int)v32);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Object);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v45);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v47);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v43);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v50);
}

```

## disassembly

```asm
0x1400d54fc  push    rbp
0x1400d54fe  push    rbx
0x1400d54ff  push    rsi
0x1400d5500  push    rdi
0x1400d5501  push    r12
0x1400d5503  push    r13
0x1400d5505  push    r14
0x1400d5507  push    r15
0x1400d5509  lea     rbp, [rsp-0C8h]
0x1400d5511  sub     rsp, 1C8h
0x1400d5518  mov     rax, cs:__security_cookie
0x1400d551f  xor     rax, rsp
0x1400d5522  mov     [rbp+100h+var_50], rax
0x1400d5529  mov     rbx, r9
0x1400d552c  mov     rdi, r8
0x1400d552f  mov     rsi, rdx
0x1400d5532  mov     r14, rcx
0x1400d5535  xor     r13d, r13d
0x1400d5538  mov     [rbp+100h+var_100], r13d
0x1400d553c  mov     byte ptr [rsp+200h+var_1D0], r13b
0x1400d5541  cmp     qword ptr [r9+18h], 7
0x1400d5546  jbe     short loc_1400D554D
0x1400d5548  mov     rcx, [r9]
0x1400d554b  jmp     short loc_1400D5550
0x1400d554d  mov     rcx, rbx; this
0x1400d5550  lea     rdx, [rsp+200h+var_1D0]; unsigned __int16 *
0x1400d5555  call    ?IsDriveLetter@Storage@ComputeService@@YA_NPEBGPEAD@Z; ComputeService::Storage::IsDriveLetter(ushort const *,char *)
0x1400d555a  mov     r15b, al
0x1400d555d  lea     rcx, [rbp+100h+var_70]; void *
0x1400d5564  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400d5569  nop
0x1400d556a  cmp     qword ptr [rdi+18h], 7
0x1400d556f  jbe     short loc_1400D5574
0x1400d5571  mov     rdi, [rdi]
0x1400d5574  xor     r8d, r8d
0x1400d5577  lea     rdx, [rbp+100h+var_70]
0x1400d557e  mov     rcx, rdi; pszPathIn
0x1400d5581  call    ?GetFinalDirectoryPaths@Storage@ComputeService@@YAXPEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; ComputeService::Storage::GetFinalDirectoryPaths(ushort const *,std::wstring *,std::wstring *)
0x1400d5586  lea     rdx, [rsp+200h+var_1B0]
0x1400d558b  lea     rcx, [rbp+100h+var_70]
0x1400d5592  call    ??B?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@1@XZ; std::wstring::operator std::basic_string_view<ushort>(void)
0x1400d5597  mov     dword ptr [rsp+200h+Uuid.Data2], r13d
0x1400d559c  mov     rcx, [rax]
0x1400d559f  mov     qword ptr [rsp+200h+Uuid.Data4], rcx
0x1400d55a4  movzx   ecx, word ptr [rax+8]
0x1400d55a8  add     cx, cx
0x1400d55ab  mov     word ptr [rsp+200h+Uuid.Data1], cx
0x1400d55b0  mov     word ptr [rsp+200h+Uuid.Data1+2], cx
0x1400d55b5  movaps  xmm0, xmmword ptr [rsp+200h+Uuid.Data1]
0x1400d55ba  movdqa  xmmword ptr [rbp+100h+Name.Length], xmm0
0x1400d55c2  lea     rcx, [rbp+100h+var_F0]; void *
0x1400d55c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400d55cb  nop
0x1400d55cc  lea     rcx, [rbp+100h+var_B0]; void *
0x1400d55d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400d55d5  nop
0x1400d55d6  mov     r12b, byte ptr [rbp+100h+arg_30]
0x1400d55dd  test    r12b, r12b
0x1400d55e0  jz      short loc_1400D55FA
0x1400d55e2  lea     rdx, szPassword
0x1400d55e9  lea     rcx, [rbp+100h+var_150]
0x1400d55ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400d55f2  nop
0x1400d55f3  mov     edi, 1
0x1400d55f8  jmp     short loc_1400D560B
0x1400d55fa  mov     rdx, r14
0x1400d55fd  lea     rcx, [rbp+100h+var_170]
0x1400d5601  call    ?QueryContainerNamespacePath@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; ComputeService::ContainerUtilities::QueryContainerNamespacePath(void *)
0x1400d5606  mov     edi, 2
0x1400d560b  mov     rdx, rax; void *
0x1400d560e  lea     rcx, [rbp+100h+var_D0]; void *
0x1400d5612  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1400d5617  nop
0x1400d5618  test    dil, 2
0x1400d561c  jz      short loc_1400D562B
0x1400d561e  and     edi, 0FFFFFFFDh
0x1400d5621  lea     rcx, [rbp+100h+var_170]; this
0x1400d5625  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d562a  nop
0x1400d562b  test    dil, 1
0x1400d562f  jz      short loc_1400D563A
0x1400d5631  lea     rcx, [rbp+100h+var_150]; this
0x1400d5635  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d563a  test    r15b, r15b
0x1400d563d  jz      short loc_1400D56B5
0x1400d563f  cmp     byte ptr [rsp+200h+var_1D0], 43h ; 'C'
0x1400d5644  jnz     short loc_1400D5671
0x1400d5646  mov     rcx, [rbp+108h]; this
0x1400d564d  lea     rax, aCannotMapAHost; "Cannot map a host path to the container"...
0x1400d5654  mov     [rsp+200h+var_1E0], rax; unsigned int
0x1400d5659  mov     r9d, 0Dh; char *
0x1400d565f  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400d5666  mov     edx, 0C9h; void *
0x1400d566b  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1400d5671  cmp     qword ptr [rbx+18h], 7
0x1400d5676  jbe     short loc_1400D567D
0x1400d5678  mov     r9, [rbx]
0x1400d567b  jmp     short loc_1400D5680
0x1400d567d  mov     r9, rbx
0x1400d5680  lea     r8, [rbp+100h+var_D0]
0x1400d5684  cmp     [rbp+100h+var_B8], 7
0x1400d5689  cmova   r8, [rbp+100h+var_D0]
0x1400d568e  lea     rdx, aSGlobalS; "%s\\GLOBAL??\\%s"
0x1400d5695  lea     rcx, [rsp+200h+var_1B0]
0x1400d569a  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400d569f  mov     rdx, rax
0x1400d56a2  lea     rcx, [rbp+100h+var_B0]
0x1400d56a6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400d56ab  lea     rcx, [rsp+200h+var_1B0]
0x1400d56b0  jmp     loc_1400D5748
0x1400d56b5  lea     rcx, [rbp+100h+var_D0]
0x1400d56b9  call    ComputeService__ContainerUtilities___anonymous_namespace___CreateMappedDirectoryRoot
0x1400d56be  xorps   xmm0, xmm0
0x1400d56c1  movups  xmmword ptr [rsp+200h+Uuid.Data1], xmm0
0x1400d56c6  lea     rcx, [rsp+200h+Uuid]; Uuid
0x1400d56cb  call    cs:__imp_UuidCreate
0x1400d56d2  nop     dword ptr [rax+rax+00h]
0x1400d56d7  movaps  xmm0, xmmword ptr [rsp+200h+Uuid.Data1]
0x1400d56dc  movdqa  [rsp+200h+var_1B0], xmm0
0x1400d56e2  xor     r8d, r8d
0x1400d56e5  lea     rdx, [rsp+200h+var_1B0]
0x1400d56ea  lea     rcx, [rsp+200h+var_190]
0x1400d56ef  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400d56f4  mov     rdx, rax
0x1400d56f7  lea     rcx, [rbp+100h+var_F0]
0x1400d56fb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400d5700  lea     rcx, [rsp+200h+var_190]; this
0x1400d5705  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d570a  lea     r9, [rbp+100h+var_F0]
0x1400d570e  cmp     [rbp+100h+var_D8], 7
0x1400d5713  cmova   r9, [rbp+100h+var_F0]
0x1400d5718  lea     r8, [rbp+100h+var_D0]
0x1400d571c  cmp     [rbp+100h+var_B8], 7
0x1400d5721  cmova   r8, [rbp+100h+var_D0]
0x1400d5726  lea     rdx, aSContainermapp_0; "%s\\ContainerMappedDirectories\\%s"
0x1400d572d  lea     rcx, [rsp+200h+var_190]
0x1400d5732  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400d5737  mov     rdx, rax
0x1400d573a  lea     rcx, [rbp+100h+var_B0]
0x1400d573e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400d5743  lea     rcx, [rsp+200h+var_190]; this
0x1400d5748  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d574d  lea     rdx, [rsp+200h+var_1B0]
0x1400d5752  lea     rcx, [rbp+100h+var_B0]
0x1400d5756  call    ??B?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@1@XZ; std::wstring::operator std::basic_string_view<ushort>(void)
0x1400d575b  mov     dword ptr [rsp+200h+Uuid.Data2], r13d
0x1400d5760  mov     rcx, [rax]
0x1400d5763  mov     qword ptr [rsp+200h+Uuid.Data4], rcx
0x1400d5768  movzx   ecx, word ptr [rax+8]
0x1400d576c  add     cx, cx
0x1400d576f  mov     word ptr [rsp+200h+Uuid.Data1], cx
0x1400d5774  mov     word ptr [rsp+200h+Uuid.Data1+2], cx
0x1400d5779  movaps  xmm0, xmmword ptr [rsp+200h+Uuid.Data1]
0x1400d577e  movdqa  [rbp+100h+var_90], xmm0
0x1400d5783  mov     qword ptr [rbp+100h+ObjectAttributes.Length], 30h ; '0'
0x1400d578b  mov     qword ptr [rbp+100h+ObjectAttributes.Attributes], r13
0x1400d578f  mov     [rbp+100h+ObjectAttributes.RootDirectory], r13
0x1400d5793  lea     rax, [rbp+100h+var_90]
0x1400d5797  mov     [rbp+100h+ObjectAttributes.ObjectName], rax
0x1400d579b  xorps   xmm0, xmm0
0x1400d579e  movdqu  xmmword ptr [rbp+100h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d57a3  mov     [rbp+100h+Object], r13
0x1400d57a7  lea     rcx, [rbp+100h+Object]
0x1400d57ab  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1400d57b0  lea     r9, [rbp+100h+Name]; Name
0x1400d57b7  lea     r8, [rbp+100h+ObjectAttributes]; ObjectAttributes
0x1400d57bb  mov     edx, 0FFFFFh; DesiredAccess
0x1400d57c0  mov     rcx, rax; SymbolicLinkHandle
0x1400d57c3  call    cs:__imp_NtCreateSymbolicLinkObject
0x1400d57ca  nop     dword ptr [rax+rax+00h]
0x1400d57cf  mov     rcx, [rbp+108h]; this
0x1400d57d6  test    eax, eax
0x1400d57d8  jns     short loc_1400D57EF
0x1400d57da  mov     r9d, eax; char *
0x1400d57dd  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400d57e4  mov     edx, 0E2h; void *
0x1400d57e9  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1400d57ef  test    r14, r14
0x1400d57f2  jz      loc_1400D5891
0x1400d57f8  mov     edi, 4
0x1400d57fd  cmp     [rbp+100h+arg_20], r13b
0x1400d5804  jz      short loc_1400D5847
0x1400d5806  mov     [rbp+100h+var_100], 1200A9h
0x1400d580d  mov     r9d, edi
0x1400d5810  lea     r8, [rbp+100h+var_100]
0x1400d5814  lea     edx, [rdi-2]
0x1400d5817  mov     rcx, [rbp+100h+Object]
0x1400d581b  call    cs:__imp_NtSetInformationSymbolicLink
0x1400d5822  nop     dword ptr [rax+rax+00h]
0x1400d5827  mov     rcx, [rbp+108h]; this
0x1400d582e  test    eax, eax
0x1400d5830  jns     short loc_1400D5847
0x1400d5832  mov     r9d, eax; char *
0x1400d5835  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400d583c  mov     edx, 0EEh; void *
0x1400d5841  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1400d5847  cmp     [rbp+100h+arg_28], r13b
0x1400d584e  jz      short loc_1400D5891
0x1400d5850  mov     eax, 1
0x1400d5855  mov     [rbp+100h+var_100], eax
0x1400d5858  mov     r9d, edi
0x1400d585b  lea     r8, [rbp+100h+var_100]
0x1400d585f  mov     edx, eax
0x1400d5861  mov     rcx, [rbp+100h+Object]
0x1400d5865  call    cs:__imp_NtSetInformationSymbolicLink
0x1400d586c  nop     dword ptr [rax+rax+00h]
0x1400d5871  mov     rcx, [rbp+108h]; this
0x1400d5878  test    eax, eax
0x1400d587a  jns     short loc_1400D5891
0x1400d587c  mov     r9d, eax; char *
0x1400d587f  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400d5886  mov     edx, 0F6h; void *
0x1400d588b  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1400d5891  cmp     [rbp+100h+var_E0], r13
0x1400d5895  jz      short loc_1400D58C9
0x1400d5897  lea     r8, [rbp+100h+var_F0]
0x1400d589b  cmp     [rbp+100h+var_D8], 7
0x1400d58a0  cmova   r8, [rbp+100h+var_F0]; unsigned __int16 *
0x1400d58a5  cmp     qword ptr [rbx+18h], 7
0x1400d58aa  jbe     short loc_1400D58AF
0x1400d58ac  mov     rbx, [rbx]
0x1400d58af  cmp     qword ptr [rsi+18h], 7
0x1400d58b4  jbe     short loc_1400D58B9
0x1400d58b6  mov     rsi, [rsi]
0x1400d58b9  mov     byte ptr [rsp+200h+var_1E0], r12b; int
0x1400d58be  mov     rdx, rbx; unsigned __int16 *
0x1400d58c1  mov     rcx, rsi; this
0x1400d58c4  call    ?CreateMappedDirectoryLink@Storage@ComputeService@@YAXPEBG00PEAX_N@Z; ComputeService::Storage::CreateMappedDirectoryLink(ushort const *,ushort const *,ushort const *,void *,bool)
0x1400d58c9  mov     rcx, [rbp+100h+Object]; Object
0x1400d58cd  call    cs:__imp_NtMakePermanentObject
0x1400d58d4  nop     dword ptr [rax+rax+00h]
0x1400d58d9  mov     rcx, [rbp+108h]; this
0x1400d58e0  test    eax, eax
0x1400d58e2  jns     short loc_1400D58F9
0x1400d58e4  mov     r9d, eax; char *
0x1400d58e7  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400d58ee  mov     edx, 107h; void *
0x1400d58f3  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1400d58f9  lea     rcx, [rbp+100h+Object]; void *
0x1400d58fd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400d5902  nop
0x1400d5903  lea     rcx, [rbp+100h+var_D0]; this
0x1400d5907  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d590c  nop
0x1400d590d  lea     rcx, [rbp+100h+var_B0]; this
0x1400d5911  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d5916  nop
0x1400d5917  lea     rcx, [rbp+100h+var_F0]; this
0x1400d591b  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d5920  nop
0x1400d5921  lea     rcx, [rbp+100h+var_70]; this
0x1400d5928  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d592d  mov     rcx, [rbp+100h+var_50]
0x1400d5934  xor     rcx, rsp; StackCookie
0x1400d5937  call    __security_check_cookie
0x1400d593c  add     rsp, 1C8h
0x1400d5943  pop     r15
0x1400d5945  pop     r14
0x1400d5947  pop     r13
0x1400d5949  pop     r12
0x1400d594b  pop     rdi
0x1400d594c  pop     rsi
0x1400d594d  pop     rbx
0x1400d594e  pop     rbp
0x1400d594f  retn
```
