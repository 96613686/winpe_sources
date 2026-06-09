# ComputeService::ContainerUtilities::_anonymous_namespace_::CreateSymlinkContainerPath

- ea: `0x1400d9ce8`
- end: `0x1400da172`
- name: `ComputeService::ContainerUtilities::_anonymous_namespace_::CreateSymlinkContainerPath`
- size: `1162`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d90a0`

## callees

- `0x140005360`
- `0x140008760`
- `0x14001e4f4`
- `0x14002dd18`
- `0x140042e04`
- `0x14004346c`
- `0x140043544`
- `0x1400438dc`
- `0x140044adc`
- `0x14008ae64`
- `0x14008f640`
- `0x1400d4de0`
- `0x1400d9af4`
- `0x1400d9ce8`

## import_xrefs

- `ntdll!NtSetInformationSymbolicLink` at `0x1400d9fff`
- `ntdll!NtSetInformationSymbolicLink` at `0x1400da032`
- `ntdll!NtSetInformationSymbolicLink` at `0x1400d9fff`
- `ntdll!NtSetInformationSymbolicLink` at `0x1400da032`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1400d9fc2`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1400d9fc2`
- `ntdll!NtMakePermanentObject` at `0x1400da083`
- `ntdll!NtMakePermanentObject` at `0x1400da083`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400da0a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400da0a2`
- `RPCRT4!UuidCreate` at `0x1400d9edb`
- `RPCRT4!UuidCreate` at `0x1400d9edb`

## string_xrefs

- `0x1400da0f6`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400da121`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400da136`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400da14b`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400da160`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400da10f`: `Cannot map a host path to the container's C: drive`

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
  __int128 *v13; // rax
  _OWORD *ContainerNamespacePath; // rcx
  char v15; // di
  __int64 v16; // rax
  _BYTE *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int128 *v20; // rax
  NTSTATUS v21; // eax
  const unsigned __int16 *v22; // r9
  int v23; // eax
  int v24; // eax
  const unsigned __int16 *v25; // r8
  NTSTATUS PermanentObject; // eax
  void *v27; // [rsp+20h] [rbp-E0h]
  const char *v28; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v29[8]; // [rsp+30h] [rbp-D0h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD Src[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v32[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v33[32]; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  int v35; // [rsp+E0h] [rbp-20h] BYREF
  void *SymbolicLinkHandle; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v37[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v38; // [rsp+100h] [rbp+0h]
  unsigned __int64 v39; // [rsp+108h] [rbp+8h]
  __int128 v40; // [rsp+110h] [rbp+10h] BYREF
  __int128 v41; // [rsp+120h] [rbp+20h]
  __int128 v42; // [rsp+130h] [rbp+30h] BYREF
  __int64 v43; // [rsp+140h] [rbp+40h]
  unsigned __int64 v44; // [rsp+148h] [rbp+48h]
  __int128 v45; // [rsp+150h] [rbp+50h] BYREF
  __int64 v46; // [rsp+160h] [rbp+60h]
  unsigned __int64 v47; // [rsp+168h] [rbp+68h]
  UUID v48; // [rsp+170h] [rbp+70h] BYREF
  struct _UNICODE_STRING Name; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v7 = a4;
  v8 = a3;
  v35 = 0;
  LOBYTE(v29[0]) = 0;
  if ( *((_QWORD *)a4 + 3) <= 7u )
    v11 = a4;
  else
    v11 = *(ComputeService::Storage **)a4;
  IsDriveLetter = ComputeService::Storage::IsDriveLetter(v11, v29, a3);
  v45 = 0;
  v46 = 0;
  v47 = 7;
  LOWORD(v45) = 0;
  if ( *((_QWORD *)v8 + 3) > 7u )
    v8 = *(char **)v8;
  ComputeService::Storage::GetFinalDirectoryPaths((PCWSTR)v8);
  v13 = &v45;
  if ( v47 > 7 )
    v13 = (__int128 *)v45;
  Uuid.Data3 = 0;
  *(_QWORD *)Uuid.Data4 = v13;
  LOWORD(Uuid.Data1) = 2 * v46;
  *(unsigned int *)((char *)&Uuid.Data1 + 2) = (unsigned __int16)(2 * v46);
  Name = (struct _UNICODE_STRING)Uuid;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  v39 = 7;
  LOWORD(v37[0]) = 0;
  v42 = 0;
  v43 = 0;
  v44 = 7;
  LOWORD(v42) = 0;
  if ( a7 )
  {
    memset(Src, 0, sizeof(Src));
    std::wstring::_Construct<1,unsigned short const *>((__int64)Src, &szPassword, 0);
    ContainerNamespacePath = Src;
    v15 = 1;
  }
  else
  {
    ContainerNamespacePath = (_OWORD *)ComputeService::ContainerUtilities::QueryContainerNamespacePath(v33);
    v15 = 2;
  }
  v40 = 0;
  v41 = 0;
  v40 = *ContainerNamespacePath;
  v41 = ContainerNamespacePath[1];
  *((_QWORD *)ContainerNamespacePath + 2) = 0;
  *((_QWORD *)ContainerNamespacePath + 3) = 7;
  *(_WORD *)ContainerNamespacePath = 0;
  if ( (v15 & 2) != 0 )
  {
    v15 &= ~2u;
    std::wstring::~wstring(v33);
  }
  if ( (v15 & 1) != 0 )
    std::wstring::~wstring(Src);
  if ( IsDriveLetter )
  {
    if ( LOBYTE(v29[0]) == 67 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)0xD,
        (unsigned int)"Cannot map a host path to the container's C: drive",
        v28);
    v16 = Vml::FormatString(Src, (wchar_t *)L"%s\\GLOBAL??\\%s");
    std::wstring::operator=(&v42, v16);
    v17 = Src;
  }
  else
  {
    ComputeService::ContainerUtilities::_anonymous_namespace_::CreateMappedDirectoryRoot(&v40);
    Uuid = 0;
    UuidCreate(&Uuid);
    Src[0] = Uuid;
    v18 = Vml::GuidToString(v32, Src, 0);
    std::wstring::operator=(v37, v18);
    std::wstring::~wstring(v32);
    v19 = Vml::FormatString(v32, (wchar_t *)L"%s\\ContainerMappedDirectories\\%s");
    std::wstring::operator=(&v42, v19);
    v17 = v32;
  }
  std::wstring::~wstring(v17);
  v20 = &v42;
  if ( v44 > 7 )
    v20 = (__int128 *)v42;
  Uuid.Data3 = 0;
  *(_QWORD *)Uuid.Data4 = v20;
  LOWORD(Uuid.Data1) = 2 * v43;
  *(unsigned int *)((char *)&Uuid.Data1 + 2) = (unsigned __int16)(2 * v43);
  v48 = Uuid;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.Attributes, 0, 24);
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v48;
  SymbolicLinkHandle = 0;
  v21 = NtCreateSymbolicLinkObject(&SymbolicLinkHandle, 0xFFFFFu, &ObjectAttributes, &Name);
  if ( v21 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
      (const char *)(unsigned int)v21,
      (int)v27);
  if ( a1 )
  {
    if ( a5 )
    {
      v35 = 1179817;
      v23 = NtSetInformationSymbolicLink(SymbolicLinkHandle, 2, &v35, 4);
      if ( v23 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
          (const char *)(unsigned int)v23,
          (int)v27);
    }
    if ( a6 )
    {
      v35 = 1;
      v24 = NtSetInformationSymbolicLink(SymbolicLinkHandle, 1, &v35, 4);
      if ( v24 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0xF6,
          (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
          (const char *)(unsigned int)v24,
          (int)v27);
    }
  }
  if ( v38 )
  {
    v25 = (const unsigned __int16 *)v37;
    if ( v39 > 7 )
      v25 = v37[0];
    if ( *((_QWORD *)v7 + 3) > 7u )
      v7 = *(ComputeService::Storage **)v7;
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(ComputeService::Storage **)a2;
    LOBYTE(v27) = a7;
    ComputeService::Storage::CreateMappedDirectoryLink(a2, (const unsigned __int16 *)v7, v25, v22, v27, (bool)v28);
  }
  PermanentObject = NtMakePermanentObject(SymbolicLinkHandle);
  if ( PermanentObject < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
      (const char *)(unsigned int)PermanentObject,
      (int)v27);
  if ( (char *)SymbolicLinkHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(SymbolicLinkHandle);
  std::wstring::~wstring(&v40);
  std::wstring::~wstring(&v42);
  std::wstring::~wstring(v37);
  std::wstring::~wstring(&v45);
}

```

## disassembly

```asm
0x1400d9ce8  push    rbp
0x1400d9cea  push    rbx
0x1400d9ceb  push    rsi
0x1400d9cec  push    rdi
0x1400d9ced  push    r12
0x1400d9cef  push    r13
0x1400d9cf1  push    r14
0x1400d9cf3  push    r15
0x1400d9cf5  lea     rbp, [rsp-0A8h]
0x1400d9cfd  sub     rsp, 1A8h
0x1400d9d04  mov     rax, cs:__security_cookie
0x1400d9d0b  xor     rax, rsp
0x1400d9d0e  mov     [rbp+0E0h+var_50], rax
0x1400d9d15  mov     rbx, r9
0x1400d9d18  mov     rdi, r8
0x1400d9d1b  mov     rsi, rdx
0x1400d9d1e  mov     r14, rcx
0x1400d9d21  xor     r13d, r13d
0x1400d9d24  mov     [rbp+0E0h+var_100], r13d
0x1400d9d28  mov     byte ptr [rsp+1E0h+var_1B0], r13b
0x1400d9d2d  lea     r12d, [r13+7]
0x1400d9d31  cmp     [r9+18h], r12
0x1400d9d35  jbe     short loc_1400D9D3C
0x1400d9d37  mov     rcx, [r9]
0x1400d9d3a  jmp     short loc_1400D9D3F
0x1400d9d3c  mov     rcx, rbx; this
0x1400d9d3f  lea     rdx, [rsp+1E0h+var_1B0]; unsigned __int16 *
0x1400d9d44  call    ?IsDriveLetter@Storage@ComputeService@@YA_NPEBGPEAD@Z; ComputeService::Storage::IsDriveLetter(ushort const *,char *)
0x1400d9d49  mov     r15b, al
0x1400d9d4c  xorps   xmm0, xmm0
0x1400d9d4f  movups  [rbp+0E0h+var_90], xmm0
0x1400d9d53  mov     [rbp+0E0h+var_80], r13
0x1400d9d57  mov     [rbp+0E0h+var_78], r12
0x1400d9d5b  mov     word ptr [rbp+0E0h+var_90], r13w
0x1400d9d60  cmp     [rdi+18h], r12
0x1400d9d64  jbe     short loc_1400D9D69
0x1400d9d66  mov     rdi, [rdi]
0x1400d9d69  xor     r8d, r8d
0x1400d9d6c  lea     rdx, [rbp+0E0h+var_90]
0x1400d9d70  mov     rcx, rdi; pszPathIn
0x1400d9d73  call    ?GetFinalDirectoryPaths@Storage@ComputeService@@YAXPEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; ComputeService::Storage::GetFinalDirectoryPaths(ushort const *,std::wstring *,std::wstring *)
0x1400d9d78  lea     rax, [rbp+0E0h+var_90]
0x1400d9d7c  cmp     [rbp+0E0h+var_78], r12
0x1400d9d80  cmova   rax, qword ptr [rbp+0E0h+var_90]
0x1400d9d85  mov     rcx, [rbp+0E0h+var_80]
0x1400d9d89  mov     dword ptr [rsp+1E0h+Uuid.Data2], r13d
0x1400d9d8e  mov     qword ptr [rsp+1E0h+Uuid.Data4], rax
0x1400d9d93  add     cx, cx
0x1400d9d96  mov     word ptr [rsp+1E0h+Uuid.Data1], cx
0x1400d9d9b  mov     word ptr [rsp+1E0h+Uuid.Data1+2], cx
0x1400d9da0  movaps  xmm0, xmmword ptr [rsp+1E0h+Uuid.Data1]
0x1400d9da5  movdqa  xmmword ptr [rbp+0E0h+Name.Length], xmm0
0x1400d9dad  xorps   xmm1, xmm1
0x1400d9db0  movups  xmmword ptr [rbp+0E0h+var_F0], xmm1
0x1400d9db4  mov     [rbp+0E0h+var_E0], r13
0x1400d9db8  mov     [rbp+0E0h+var_D8], r12
0x1400d9dbc  mov     word ptr [rbp+0E0h+var_F0], r13w
0x1400d9dc1  xorps   xmm0, xmm0
0x1400d9dc4  movups  [rbp+0E0h+var_B0], xmm0
0x1400d9dc8  mov     [rbp+0E0h+var_A0], r13
0x1400d9dcc  mov     [rbp+0E0h+var_98], r12
0x1400d9dd0  mov     word ptr [rbp+0E0h+var_B0], r13w
0x1400d9dd5  mov     r12b, byte ptr [rbp+0E0h+arg_30]
0x1400d9ddc  test    r12b, r12b
0x1400d9ddf  jz      short loc_1400D9E0C
0x1400d9de1  movups  [rsp+1E0h+Src], xmm0
0x1400d9de6  movdqu  [rsp+1E0h+var_180], xmm1
0x1400d9dec  xor     r8d, r8d
0x1400d9def  lea     rdx, szPassword
0x1400d9df6  lea     rcx, [rsp+1E0h+Src]
0x1400d9dfb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400d9e00  lea     rcx, [rsp+1E0h+Src]
0x1400d9e05  mov     edi, 1
0x1400d9e0a  jmp     short loc_1400D9E20
0x1400d9e0c  mov     rdx, r14
0x1400d9e0f  lea     rcx, [rbp+0E0h+var_150]; Src
0x1400d9e13  call    ?QueryContainerNamespacePath@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; ComputeService::ContainerUtilities::QueryContainerNamespacePath(void *)
0x1400d9e18  mov     rcx, rax
0x1400d9e1b  mov     edi, 2
0x1400d9e20  xorps   xmm0, xmm0
0x1400d9e23  movups  [rbp+0E0h+var_D0], xmm0
0x1400d9e27  xorps   xmm1, xmm1
0x1400d9e2a  movdqu  [rbp+0E0h+var_C0], xmm1
0x1400d9e2f  movups  xmm0, xmmword ptr [rcx]
0x1400d9e32  movups  [rbp+0E0h+var_D0], xmm0
0x1400d9e36  movups  xmm1, xmmword ptr [rcx+10h]
0x1400d9e3a  movups  [rbp+0E0h+var_C0], xmm1
0x1400d9e3e  mov     [rcx+10h], r13
0x1400d9e42  mov     qword ptr [rcx+18h], 7
0x1400d9e4a  mov     [rcx], r13w
0x1400d9e4e  test    dil, 2
0x1400d9e52  jz      short loc_1400D9E61
0x1400d9e54  and     edi, 0FFFFFFFDh
0x1400d9e57  lea     rcx, [rbp+0E0h+var_150]; void *
0x1400d9e5b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d9e60  nop
0x1400d9e61  test    dil, 1
0x1400d9e65  jz      short loc_1400D9E71
0x1400d9e67  lea     rcx, [rsp+1E0h+Src]; void *
0x1400d9e6c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d9e71  test    r15b, r15b
0x1400d9e74  jz      short loc_1400D9EC5
0x1400d9e76  cmp     byte ptr [rsp+1E0h+var_1B0], 43h ; 'C'
0x1400d9e7b  jz      loc_1400DA108
0x1400d9e81  cmp     qword ptr [rbx+18h], 7
0x1400d9e86  jbe     short loc_1400D9E8D
0x1400d9e88  mov     r9, [rbx]
0x1400d9e8b  jmp     short loc_1400D9E90
0x1400d9e8d  mov     r9, rbx
0x1400d9e90  lea     r8, [rbp+0E0h+var_D0]
0x1400d9e94  cmp     qword ptr [rbp+0E0h+var_C0+8], 7
0x1400d9e99  cmova   r8, qword ptr [rbp+0E0h+var_D0]
0x1400d9e9e  lea     rdx, aSGlobalS; "%s\\GLOBAL??\\%s"
0x1400d9ea5  lea     rcx, [rsp+1E0h+Src]; Src
0x1400d9eaa  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400d9eaf  mov     rdx, rax
0x1400d9eb2  lea     rcx, [rbp+0E0h+var_B0]
0x1400d9eb6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400d9ebb  lea     rcx, [rsp+1E0h+Src]
0x1400d9ec0  jmp     loc_1400D9F52
0x1400d9ec5  lea     rcx, [rbp+0E0h+var_D0]
0x1400d9ec9  call    ComputeService__ContainerUtilities___anonymous_namespace___CreateMappedDirectoryRoot
0x1400d9ece  xorps   xmm0, xmm0
0x1400d9ed1  movups  xmmword ptr [rsp+1E0h+Uuid.Data1], xmm0
0x1400d9ed6  lea     rcx, [rsp+1E0h+Uuid]; Uuid
0x1400d9edb  call    cs:__imp_UuidCreate
0x1400d9ee1  movaps  xmm0, xmmword ptr [rsp+1E0h+Uuid.Data1]
0x1400d9ee6  movdqa  [rsp+1E0h+Src], xmm0
0x1400d9eec  xor     r8d, r8d
0x1400d9eef  lea     rdx, [rsp+1E0h+Src]
0x1400d9ef4  lea     rcx, [rsp+1E0h+var_170]
0x1400d9ef9  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400d9efe  mov     rdx, rax
0x1400d9f01  lea     rcx, [rbp+0E0h+var_F0]
0x1400d9f05  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400d9f0a  lea     rcx, [rsp+1E0h+var_170]; void *
0x1400d9f0f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d9f14  lea     r9, [rbp+0E0h+var_F0]
0x1400d9f18  cmp     [rbp+0E0h+var_D8], 7
0x1400d9f1d  cmova   r9, [rbp+0E0h+var_F0]
0x1400d9f22  lea     r8, [rbp+0E0h+var_D0]
0x1400d9f26  cmp     qword ptr [rbp+0E0h+var_C0+8], 7
0x1400d9f2b  cmova   r8, qword ptr [rbp+0E0h+var_D0]
0x1400d9f30  lea     rdx, aSContainermapp_0; "%s\\ContainerMappedDirectories\\%s"
0x1400d9f37  lea     rcx, [rsp+1E0h+var_170]; Src
0x1400d9f3c  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400d9f41  mov     rdx, rax
0x1400d9f44  lea     rcx, [rbp+0E0h+var_B0]
0x1400d9f48  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400d9f4d  lea     rcx, [rsp+1E0h+var_170]; void *
0x1400d9f52  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d9f57  lea     rax, [rbp+0E0h+var_B0]
0x1400d9f5b  cmp     [rbp+0E0h+var_98], 7
0x1400d9f60  cmova   rax, qword ptr [rbp+0E0h+var_B0]
0x1400d9f65  mov     rcx, [rbp+0E0h+var_A0]
0x1400d9f69  mov     dword ptr [rsp+1E0h+Uuid.Data2], r13d
0x1400d9f6e  mov     qword ptr [rsp+1E0h+Uuid.Data4], rax
0x1400d9f73  add     cx, cx
0x1400d9f76  mov     word ptr [rsp+1E0h+Uuid.Data1], cx
0x1400d9f7b  mov     word ptr [rsp+1E0h+Uuid.Data1+2], cx
0x1400d9f80  movaps  xmm0, xmmword ptr [rsp+1E0h+Uuid.Data1]
0x1400d9f85  movdqa  [rbp+0E0h+var_70], xmm0
0x1400d9f8a  mov     qword ptr [rbp+0E0h+ObjectAttributes.Length], 30h ; '0'
0x1400d9f92  mov     qword ptr [rbp+0E0h+ObjectAttributes.Attributes], r13
0x1400d9f96  mov     [rbp+0E0h+ObjectAttributes.RootDirectory], r13
0x1400d9f9a  lea     rax, [rbp+0E0h+var_70]
0x1400d9f9e  mov     [rbp+0E0h+ObjectAttributes.ObjectName], rax
0x1400d9fa2  xorps   xmm0, xmm0
0x1400d9fa5  movdqu  xmmword ptr [rbp+0E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d9faa  mov     [rbp+0E0h+SymbolicLinkHandle], r13
0x1400d9fae  lea     r9, [rbp+0E0h+Name]; Name
0x1400d9fb5  lea     r8, [rbp+0E0h+ObjectAttributes]; ObjectAttributes
0x1400d9fb9  mov     edx, 0FFFFFh; DesiredAccess
0x1400d9fbe  lea     rcx, [rbp+0E0h+SymbolicLinkHandle]; SymbolicLinkHandle
0x1400d9fc2  call    cs:__imp_NtCreateSymbolicLinkObject
0x1400d9fc8  mov     rcx, [rbp+0E8h]; this
0x1400d9fcf  test    eax, eax
0x1400d9fd1  js      loc_1400DA133
0x1400d9fd7  test    r14, r14
0x1400d9fda  jz      short loc_1400DA047
0x1400d9fdc  mov     edi, 4
0x1400d9fe1  cmp     [rbp+0E0h+arg_20], r13b
0x1400d9fe8  jz      short loc_1400DA014
0x1400d9fea  mov     [rbp+0E0h+var_100], 1200A9h
0x1400d9ff1  mov     r9d, edi
0x1400d9ff4  lea     r8, [rbp+0E0h+var_100]
0x1400d9ff8  lea     edx, [rdi-2]
0x1400d9ffb  mov     rcx, [rbp+0E0h+SymbolicLinkHandle]
0x1400d9fff  call    cs:__imp_NtSetInformationSymbolicLink
0x1400da005  mov     rcx, [rbp+0E8h]; this
0x1400da00c  test    eax, eax
0x1400da00e  js      loc_1400DA148
0x1400da014  cmp     [rbp+0E0h+arg_28], r13b
0x1400da01b  jz      short loc_1400DA047
0x1400da01d  mov     eax, 1
0x1400da022  mov     [rbp+0E0h+var_100], eax
0x1400da025  mov     r9d, edi
0x1400da028  lea     r8, [rbp+0E0h+var_100]
0x1400da02c  mov     edx, eax
0x1400da02e  mov     rcx, [rbp+0E0h+SymbolicLinkHandle]
0x1400da032  call    cs:__imp_NtSetInformationSymbolicLink
0x1400da038  mov     rcx, [rbp+0E8h]; this
0x1400da03f  test    eax, eax
0x1400da041  js      loc_1400DA15D
0x1400da047  cmp     [rbp+0E0h+var_E0], r13
0x1400da04b  jz      short loc_1400DA07F
0x1400da04d  lea     r8, [rbp+0E0h+var_F0]
0x1400da051  cmp     [rbp+0E0h+var_D8], 7
0x1400da056  cmova   r8, [rbp+0E0h+var_F0]; unsigned __int16 *
0x1400da05b  cmp     qword ptr [rbx+18h], 7
0x1400da060  jbe     short loc_1400DA065
0x1400da062  mov     rbx, [rbx]
0x1400da065  cmp     qword ptr [rsi+18h], 7
0x1400da06a  jbe     short loc_1400DA06F
0x1400da06c  mov     rsi, [rsi]
0x1400da06f  mov     byte ptr [rsp+1E0h+var_1C0], r12b; int
0x1400da074  mov     rdx, rbx; unsigned __int16 *
0x1400da077  mov     rcx, rsi; this
0x1400da07a  call    ?CreateMappedDirectoryLink@Storage@ComputeService@@YAXPEBG00PEAX_N@Z; ComputeService::Storage::CreateMappedDirectoryLink(ushort const *,ushort const *,ushort const *,void *,bool)
0x1400da07f  mov     rcx, [rbp+0E0h+SymbolicLinkHandle]; Object
0x1400da083  call    cs:__imp_NtMakePermanentObject
0x1400da089  mov     rcx, [rbp+0E8h]; this
0x1400da090  test    eax, eax
0x1400da092  js      short loc_1400DA0F3
0x1400da094  mov     rcx, [rbp+0E0h+SymbolicLinkHandle]; hObject
0x1400da098  lea     rax, [rcx-1]
0x1400da09c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400da0a0  ja      short loc_1400DA0A9
0x1400da0a2  call    cs:__imp_CloseHandle
0x1400da0a8  nop
0x1400da0a9  lea     rcx, [rbp+0E0h+var_D0]; void *
0x1400da0ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400da0b2  nop
0x1400da0b3  lea     rcx, [rbp+0E0h+var_B0]; void *
0x1400da0b7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400da0bc  nop
0x1400da0bd  lea     rcx, [rbp+0E0h+var_F0]; void *
0x1400da0c1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400da0c6  nop
0x1400da0c7  lea     rcx, [rbp+0E0h+var_90]; void *
0x1400da0cb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400da0d0  mov     rcx, [rbp+0E0h+var_50]
0x1400da0d7  xor     rcx, rsp; StackCookie
0x1400da0da  call    __security_check_cookie
0x1400da0df  add     rsp, 1A8h
0x1400da0e6  pop     r15
0x1400da0e8  pop     r14
0x1400da0ea  pop     r13
0x1400da0ec  pop     r12
0x1400da0ee  pop     rdi
0x1400da0ef  pop     rsi
0x1400da0f0  pop     rbx
0x1400da0f1  pop     rbp
0x1400da0f2  retn
0x1400da0f3  mov     r9d, eax; char *
0x1400da0f6  lea     r8, aOnecoreVmCompu_40; "onecore\\vm\\compute\\management\\share"...
0x1400da0fd  mov     edx, 107h; void *
0x1400da102  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400da108  mov     rcx, [rbp+0E8h]; this
0x1400da10f  lea     rax, aCannotMapAHost; "Cannot map a host path to the container"...
0x1400da116  mov     [rsp+1E0h+var_1C0], rax; unsigned int
0x1400da11b  mov     r9d, 0Dh; char *
0x1400da121  lea     r8, aOnecoreVmCompu_40; "onecore\\vm\\compute\\management\\share"...
0x1400da128  mov     edx, 0C9h; void *
0x1400da12d  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1400da133  mov     r9d, eax; char *
0x1400da136  lea     r8, aOnecoreVmCompu_40; "onecore\\vm\\compute\\management\\share"...
0x1400da13d  mov     edx, 0E2h; void *
0x1400da142  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400da148  mov     r9d, eax; char *
0x1400da14b  lea     r8, aOnecoreVmCompu_40; "onecore\\vm\\compute\\management\\share"...
0x1400da152  mov     edx, 0EEh; void *
0x1400da157  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400da15d  mov     r9d, eax; char *
0x1400da160  lea     r8, aOnecoreVmCompu_40; "onecore\\vm\\compute\\management\\share"...
0x1400da167  mov     edx, 0F6h; void *
0x1400da16c  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
