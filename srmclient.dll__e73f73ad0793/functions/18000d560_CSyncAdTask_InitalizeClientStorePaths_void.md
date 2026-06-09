# CSyncAdTask::InitalizeClientStorePaths(void)

- ea: `0x18000d560`
- end: `0x18000d8cc`
- name: `?InitalizeClientStorePaths@CSyncAdTask@@SAXXZ`
- size: `876`
- prototype: `void(void)`
- caller_count: `4`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e290`
- `0x180064d70`
- `0x180066910`
- `0x180068230`

## callees

- `0x180001350`
- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000d560`
- `0x18000ebd4`
- `0x18000ed14`
- `0x18000ff90`
- `0x180010930`
- `0x18001c1f0`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073f54`
- `0x18007791c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d656`
- `KERNEL32!GetLastError` at `0x18000d661`
- `KERNEL32!GetLastError` at `0x18000d656`
- `KERNEL32!GetLastError` at `0x18000d661`
- `KERNEL32!LocalFree` at `0x18000d798`
- `KERNEL32!LocalFree` at `0x18000d798`
- `KERNEL32!GetFileAttributesW` at `0x18000d647`
- `KERNEL32!GetFileAttributesW` at `0x18000d647`
- `KERNEL32!CreateDirectoryW` at `0x18000d720`
- `KERNEL32!CreateDirectoryW` at `0x18000d720`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000d6e9`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000d6e9`

## string_xrefs

- `0x18000d586`: `base\fs\fsrm\service\globalstore\taskhandler.cpp`
- `0x18000d592`: `CSyncAdTask::InitalizeClientStorePaths`
- `0x18000d683`: `Creating global store directory %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
void CSyncAdTask::InitalizeClientStorePaths(void)
{
  const WCHAR *v0; // rcx
  DWORD FileAttributesW; // eax
  const unsigned __int16 *v2; // rcx
  LPCWSTR *v3; // rax
  PSECURITY_DESCRIPTOR v4; // rdi
  const WCHAR *v5; // rcx
  unsigned int i; // ebx
  unsigned int v7; // edx
  const unsigned __int16 *v8; // rcx
  int v9; // eax
  char v10; // al
  char v11; // al
  int LastFailureAsHRESULT; // eax
  char Hr; // al
  int v14; // eax
  char v15; // al
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+38h] [rbp-C8h] BYREF
  void **v18; // [rsp+50h] [rbp-B0h]
  PSECURITY_DESCRIPTOR v19; // [rsp+58h] [rbp-A8h]
  void *v20[3]; // [rsp+60h] [rbp-A0h]
  _QWORD v21[3]; // [rsp+78h] [rbp-88h] BYREF
  int v22; // [rsp+90h] [rbp-70h]
  int v23; // [rsp+94h] [rbp-6Ch]
  int v24; // [rsp+98h] [rbp-68h]
  _BYTE v25[96]; // [rsp+A0h] [rbp-60h] BYREF
  int v26; // [rsp+100h] [rbp+0h]
  LPCWSTR lpFileName[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v28; // [rsp+118h] [rbp+18h]
  unsigned __int64 v29; // [rsp+120h] [rbp+20h]
  void *Block[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v31; // [rsp+148h] [rbp+48h]
  void **v32; // [rsp+160h] [rbp+60h] BYREF
  int v33; // [rsp+168h] [rbp+68h]

  v21[0] = L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp";
  v21[1] = L"CSyncAdTask::InitalizeClientStorePaths";
  v21[2] = L"TSKNDLRC";
  v22 = 361;
  v23 = 30;
  v24 = 255;
  v26 = 0x1000000;
  memset_0(v25, 0, sizeof(v25));
  CSrmFunctionTracer::CSrmFunctionTracer(&v32, v21, 0);
  v29 = 7;
  v28 = 0;
  LOWORD(lpFileName[0]) = 0;
  std::wstring::assign(lpFileName);
  v20[0] = L"Properties";
  v20[1] = (void *)L"Modules";
  v20[2] = L"StoreVersions";
  v0 = (const WCHAR *)lpFileName;
  if ( v29 >= 8 )
    v0 = lpFileName[0];
  FileAttributesW = GetFileAttributesW(v0);
  if ( FileAttributesW == -1 )
  {
    if ( GetLastError() != 2 && GetLastError() != 3 )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v32, LastFailureAsHRESULT);
      Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v32, 0x19Au, Hr, 0);
    }
    v3 = lpFileName;
    if ( v29 >= 8 )
      v3 = (LPCWSTR *)lpFileName[0];
    CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v32, 0x8Cu, 0x17Eu, L"Creating global store directory %s", v3);
    v19 = 0;
    v18 = &CSrmAuto<void *,CSrmAutoLocalPtr_Storage<void *>>::`vftable';
    SecurityDescriptor = 0;
    memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
    SecurityAttributes.nLength = 24;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;OICI;GR;;;AU)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      v14 = GetLastFailureAsHRESULT();
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v32, v14);
      v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v32, 0x188u, v15, 0);
    }
    v33 = 0;
    v4 = SecurityDescriptor;
    v19 = SecurityDescriptor;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    v5 = (const WCHAR *)lpFileName;
    if ( v29 >= 8 )
      v5 = lpFileName[0];
    if ( !CreateDirectoryW(v5, &SecurityAttributes) )
    {
      v9 = GetLastFailureAsHRESULT();
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v32, v9);
      v10 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v32, 0x18Cu, v10, 0);
    }
    v33 = 0;
    for ( i = 0; i < 3; ++i )
    {
      v31 = 7;
      Block[2] = 0;
      LOWORD(Block[0]) = 0;
      std::wstring::assign(Block);
      std::wstring::append(Block, v20[i]);
      CSrmFileSafe::CreateDirectoryInternal((LPCWSTR)Block);
      if ( v31 >= 8 )
        operator delete(Block[0]);
    }
    if ( v4 )
      LocalFree(v4);
  }
  else if ( (FileAttributesW & 0x10) == 0 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v32, -2147200234);
    v11 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v32);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v32, 0x19Fu, v11, 0);
  }
  v33 = 0;
  if ( !CGlobalStoreManager::GetStorePathVersion(v2) )
  {
    SaveInBoxModuleDefinitions(0, 1);
    CGlobalStoreManager::SetStorePathVersion(v8, v7);
  }
  if ( v29 >= 8 )
    operator delete((void *)lpFileName[0]);
  v29 = 7;
  v28 = 0;
  LOWORD(lpFileName[0]) = 0;
  v32 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v32);
}

```

## disassembly

```asm
0x18000d560  push    rbp
0x18000d562  push    rbx
0x18000d563  push    rdi
0x18000d564  push    r15
0x18000d566  lea     rbp, [rsp-128h]
0x18000d56e  sub     rsp, 228h
0x18000d575  mov     rax, cs:__security_cookie
0x18000d57c  xor     rax, rsp
0x18000d57f  mov     [rbp+140h+var_30], rax
0x18000d586  lea     rax, aBaseFsFsrmServ_39; "base\\fs\\fsrm\\service\\globalstore\\t"...
0x18000d58d  mov     [rsp+240h+var_1C8], rax
0x18000d592  lea     rax, aCsyncadtaskIni_0; "CSyncAdTask::InitalizeClientStorePaths"
0x18000d599  mov     [rbp+140h+var_1C0], rax
0x18000d59d  lea     rax, aTskndlrc; "TSKNDLRC"
0x18000d5a4  mov     [rbp+140h+var_1B8], rax
0x18000d5a8  mov     [rbp+140h+var_1B0], 169h
0x18000d5af  mov     [rbp+140h+var_1AC], 1Eh
0x18000d5b6  mov     [rbp+140h+var_1A8], 0FFh
0x18000d5bd  mov     [rbp+140h+var_140], 1000000h
0x18000d5c4  xor     edx, edx; Val
0x18000d5c6  lea     r8d, [rdx+60h]; Size
0x18000d5ca  lea     rcx, [rbp+140h+var_1A0]; void *
0x18000d5ce  call    memset_0
0x18000d5d3  xor     r8d, r8d
0x18000d5d6  lea     rdx, [rsp+240h+var_1C8]
0x18000d5db  lea     rcx, [rbp+140h+var_E0]
0x18000d5df  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000d5e4  nop
0x18000d5e5  mov     r15d, 7
0x18000d5eb  mov     [rbp+140h+var_120], r15
0x18000d5ef  mov     [rbp+140h+var_128], 0
0x18000d5f7  xor     eax, eax
0x18000d5f9  mov     word ptr [rbp+140h+lpFileName], ax
0x18000d5fd  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000d601  xor     r8d, r8d
0x18000d604  lea     rdx, ?s_strStoreRootPath@CGlobalStoreManager@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring CGlobalStoreManager::s_strStoreRootPath
0x18000d60b  lea     rcx, [rbp+140h+lpFileName]; void *
0x18000d60f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000d614  nop
0x18000d615  lea     rax, aProperties_0; "Properties"
0x18000d61c  mov     [rsp+240h+var_1E0], rax
0x18000d621  lea     rax, aModules_0; "Modules"
0x18000d628  mov     [rsp+240h+var_1D8], rax
0x18000d62d  lea     rax, aStoreversions; "StoreVersions"
0x18000d634  mov     [rsp+240h+var_1D0], rax
0x18000d639  lea     rcx, [rbp+140h+lpFileName]
0x18000d63d  cmp     [rbp+140h+var_120], 8
0x18000d642  cmovnb  rcx, [rbp+140h+lpFileName]; lpFileName
0x18000d647  call    cs:__imp_GetFileAttributesW
0x18000d64d  cmp     eax, 0FFFFFFFFh
0x18000d650  jnz     loc_18000D810
0x18000d656  call    cs:__imp_GetLastError
0x18000d65c  cmp     eax, 2
0x18000d65f  jz      short loc_18000D670
0x18000d661  call    cs:__imp_GetLastError
0x18000d667  cmp     eax, 3
0x18000d66a  jnz     loc_18000D870
0x18000d670  lea     rax, [rbp+140h+lpFileName]
0x18000d674  cmp     [rbp+140h+var_120], 8
0x18000d679  cmovnb  rax, [rbp+140h+lpFileName]
0x18000d67e  mov     [rsp+240h+var_220], rax
0x18000d683  lea     r9, aCreatingGlobal; "Creating global store directory %s"
0x18000d68a  mov     edx, 8Ch; unsigned int
0x18000d68f  mov     r8d, 17Eh; unsigned int
0x18000d695  lea     rcx, [rbp+140h+var_E0]; this
0x18000d699  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18000d69e  mov     [rsp+240h+var_1E8], 0
0x18000d6a7  lea     rax, ??_7?$CSrmAuto@PEAXV?$CSrmAutoLocalPtr_Storage@PEAX@@@@6B@; const CSrmAuto<void *,CSrmAutoLocalPtr_Storage<void *>>::`vftable'
0x18000d6ae  mov     [rsp+240h+var_1F0], rax
0x18000d6b3  mov     [rsp+240h+SecurityDescriptor], 0
0x18000d6bc  xorps   xmm0, xmm0
0x18000d6bf  xor     eax, eax
0x18000d6c1  movups  xmmword ptr [rsp+240h+SecurityAttributes.nLength], xmm0
0x18000d6c6  mov     qword ptr [rsp+240h+SecurityAttributes.bInheritHandle], rax
0x18000d6cb  mov     [rsp+240h+SecurityAttributes.nLength], 18h
0x18000d6d3  mov     [rsp+240h+SecurityAttributes.bInheritHandle], eax
0x18000d6d7  xor     r9d, r9d; SecurityDescriptorSize
0x18000d6da  lea     r8, [rsp+240h+SecurityDescriptor]; SecurityDescriptor
0x18000d6df  lea     edx, [rax+1]; StringSDRevision
0x18000d6e2  lea     rcx, StringSecurityDescriptor; "D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;O"...
0x18000d6e9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000d6ef  test    eax, eax
0x18000d6f1  jz      loc_18000D89E
0x18000d6f7  mov     [rbp+140h+var_D8], 0
0x18000d6fe  mov     rdi, [rsp+240h+SecurityDescriptor]
0x18000d703  mov     [rsp+240h+var_1E8], rdi
0x18000d708  mov     [rsp+240h+SecurityAttributes.lpSecurityDescriptor], rdi
0x18000d70d  lea     rcx, [rbp+140h+lpFileName]
0x18000d711  cmp     [rbp+140h+var_120], 8
0x18000d716  cmovnb  rcx, [rbp+140h+lpFileName]; lpPathName
0x18000d71b  lea     rdx, [rsp+240h+SecurityAttributes]; lpSecurityAttributes
0x18000d720  call    cs:__imp_CreateDirectoryW
0x18000d726  test    eax, eax
0x18000d728  jz      loc_18000D816
0x18000d72e  mov     [rbp+140h+var_D8], 0
0x18000d735  xor     ebx, ebx
0x18000d737  mov     [rbp+140h+var_F8], r15
0x18000d73b  mov     [rbp+140h+var_100], 0
0x18000d743  xor     eax, eax
0x18000d745  mov     word ptr [rbp+140h+Block], ax
0x18000d749  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000d74d  xor     r8d, r8d
0x18000d750  lea     rdx, [rbp+140h+lpFileName]
0x18000d754  lea     rcx, [rbp+140h+Block]; void *
0x18000d758  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000d75d  nop
0x18000d75e  movsxd  rdx, ebx
0x18000d761  mov     rdx, [rsp+rdx*8+240h+var_1E0]; void *
0x18000d766  lea     rcx, [rbp+140h+Block]; Src
0x18000d76a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000d76f  lea     rcx, [rbp+140h+Block]; lpPathName
0x18000d773  call    ?CreateDirectoryInternal@CSrmFileSafe@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CSrmFileSafe::CreateDirectoryInternal(std::wstring const &)
0x18000d778  nop
0x18000d779  cmp     [rbp+140h+var_F8], 8
0x18000d77e  jb      short loc_18000D789
0x18000d780  mov     rcx, [rbp+140h+Block]; Block
0x18000d784  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d789  inc     ebx
0x18000d78b  cmp     ebx, 3
0x18000d78e  jb      short loc_18000D737
0x18000d790  test    rdi, rdi
0x18000d793  jz      short loc_18000D79E
0x18000d795  mov     rcx, rdi; hMem
0x18000d798  call    cs:__imp_LocalFree
0x18000d79e  mov     [rbp+140h+var_D8], 0
0x18000d7a5  call    ?GetStorePathVersion@CGlobalStoreManager@@SAKPEBG@Z; CGlobalStoreManager::GetStorePathVersion(ushort const *)
0x18000d7aa  test    eax, eax
0x18000d7ac  jnz     short loc_18000D7BE
0x18000d7ae  lea     edx, [rax+1]; int
0x18000d7b1  xor     ecx, ecx; unsigned int
0x18000d7b3  call    ?SaveInBoxModuleDefinitions@@YAXKH@Z; SaveInBoxModuleDefinitions(ulong,int)
0x18000d7b8  call    ?SetStorePathVersion@CGlobalStoreManager@@SAXPEBGK@Z; CGlobalStoreManager::SetStorePathVersion(ushort const *,ulong)
0x18000d7bd  nop
0x18000d7be  cmp     [rbp+140h+var_120], 8
0x18000d7c3  jb      short loc_18000D7CE
0x18000d7c5  mov     rcx, [rbp+140h+lpFileName]; Block
0x18000d7c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d7ce  mov     [rbp+140h+var_120], r15
0x18000d7d2  mov     [rbp+140h+var_128], 0
0x18000d7da  xor     eax, eax
0x18000d7dc  mov     word ptr [rbp+140h+lpFileName], ax
0x18000d7e0  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000d7e7  mov     [rbp+140h+var_E0], rax
0x18000d7eb  lea     rcx, [rbp+140h+var_E0]; this
0x18000d7ef  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000d7f4  mov     rcx, [rbp+140h+var_30]
0x18000d7fb  xor     rcx, rsp; StackCookie
0x18000d7fe  call    __security_check_cookie
0x18000d803  add     rsp, 228h
0x18000d80a  pop     r15
0x18000d80c  pop     rdi
0x18000d80d  pop     rbx
0x18000d80e  pop     rbp
0x18000d80f  retn
0x18000d810  test    al, 10h
0x18000d812  jz      short loc_18000D844
0x18000d814  jmp     short loc_18000D79E
0x18000d816  call    GetLastFailureAsHRESULT
0x18000d81b  mov     edx, eax; int
0x18000d81d  lea     rcx, [rbp+140h+var_E0]; this
0x18000d821  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000d826  lea     rcx, [rbp+140h+var_E0]; this
0x18000d82a  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000d82f  mov     r8d, eax; char
0x18000d832  xor     r9d, r9d; unsigned __int16 *
0x18000d835  mov     edx, 18Ch; unsigned int
0x18000d83a  lea     rcx, [rbp+140h+var_E0]; this
0x18000d83e  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000d844  mov     edx, 80045316h; int
0x18000d849  lea     rcx, [rbp+140h+var_E0]; this
0x18000d84d  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000d852  lea     rcx, [rbp+140h+var_E0]; this
0x18000d856  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000d85b  mov     r8d, eax; char
0x18000d85e  xor     r9d, r9d; unsigned __int16 *
0x18000d861  mov     edx, 19Fh; unsigned int
0x18000d866  lea     rcx, [rbp+140h+var_E0]; this
0x18000d86a  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000d870  call    GetLastFailureAsHRESULT
0x18000d875  mov     edx, eax; int
0x18000d877  lea     rcx, [rbp+140h+var_E0]; this
0x18000d87b  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000d880  lea     rcx, [rbp+140h+var_E0]; this
0x18000d884  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000d889  mov     r8d, eax; char
0x18000d88c  xor     r9d, r9d; unsigned __int16 *
0x18000d88f  mov     edx, 19Ah; unsigned int
0x18000d894  lea     rcx, [rbp+140h+var_E0]; this
0x18000d898  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000d89e  call    GetLastFailureAsHRESULT
0x18000d8a3  mov     edx, eax; int
0x18000d8a5  lea     rcx, [rbp+140h+var_E0]; this
0x18000d8a9  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000d8ae  lea     rcx, [rbp+140h+var_E0]; this
0x18000d8b2  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000d8b7  mov     r8d, eax; char
0x18000d8ba  xor     r9d, r9d; unsigned __int16 *
0x18000d8bd  mov     edx, 188h; unsigned int
0x18000d8c2  lea     rcx, [rbp+140h+var_E0]; this
0x18000d8c6  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
