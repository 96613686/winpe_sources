# GmoMigrationSmb::Initialize(IMemoryManager *,IProcessorManager *,VmMigrationConnection *,MigrationManager *)

- ea: `0x14010ca50`
- end: `0x14010cb90`
- name: `?Initialize@GmoMigrationSmb@@MEAAJPEAUIMemoryManager@@PEAUIProcessorManager@@PEAVVmMigrationConnection@@PEAVMigrationManager@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(GmoMigrationSmb *__hidden this, struct IMemoryManager *, struct IProcessorManager *, struct VmMigrationConnection *, struct MigrationManager *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1400b5998`

## callees

- `0x1400557e0`
- `0x140078628`
- `0x14010ca50`
- `0x14010cec0`
- `0x14011ea40`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14010cabb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14010cabb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14010caed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14010caed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14010ca9b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14010ca9b`

## string_xrefs

- `0x14010ca94`: `wkscli.dll`
- `0x14010cab1`: `NetpWkstaClientGetSmbClientCapabilities`

## pseudocode

```c
__int64 __fastcall GmoMigrationSmb::Initialize(
        GmoMigrationSmb *this,
        struct IMemoryManager *a2,
        struct IProcessorManager *a3,
        struct VmMigrationConnection *a4,
        struct MigrationManager *a5)
{
  HMODULE Library; // rax
  HMODULE v10; // rsi
  BOOL v11; // edi
  FARPROC ProcAddress; // rax
  unsigned int v13; // edi
  int v14; // eax
  const struct Vml::ExceptionTraceParameters *v15; // r8
  int v17; // [rsp+20h] [rbp-58h]
  int v18; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( *((_DWORD *)this + 296) )
  {
    Library = LoadLibraryExW(L"wkscli.dll", 0, 0x800u);
    v10 = Library;
    v11 = 0;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "NetpWkstaClientGetSmbClientCapabilities");
      if ( ProcAddress )
      {
        v18 = 0;
        if ( !((unsigned int (__fastcall *)(_QWORD, int *))ProcAddress)(0, &v18) )
          v11 = (v18 & 1) != 0;
      }
      FreeLibrary(v10);
    }
    *((_DWORD *)this + 296) = v11;
  }
  v13 = 0;
  try
  {
    Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset((char *)this + 1160, a5);
    v14 = GmoMigration::Initialize(this, a2, a3, a4, a5);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecore\\vm\\worker\\migration\\gmomigrationsmb.cpp",
        (const char *)(unsigned int)v14,
        v17);
    (*(void (__fastcall **)(_QWORD, unsigned __int64))(**((_QWORD **)this + 146) + 224LL))(
      *((_QWORD *)this + 146),
      ((unsigned __int64)this + 1104) & -(__int64)(this != 0));
  }
  catch ( ... )
  {
    return (unsigned int)Vml::GetHResultFromThrownExceptionAndTrace(
                           (Vml *)0x41E2,
                           (unsigned __int16)&off_1402E4AB0,
                           v15);
  }
  return v13;
}

```

## disassembly

```asm
0x14010ca50  push    rbx
0x14010ca52  push    rsi
0x14010ca53  push    rdi
0x14010ca54  push    r12
0x14010ca56  push    r13
0x14010ca58  push    r14
0x14010ca5a  push    r15
0x14010ca5c  sub     rsp, 40h
0x14010ca60  mov     rax, cs:__security_cookie
0x14010ca67  xor     rax, rsp
0x14010ca6a  mov     [rsp+78h+var_40], rax
0x14010ca6f  mov     r13, r9
0x14010ca72  mov     r12, r8
0x14010ca75  mov     r15, rdx
0x14010ca78  mov     rbx, rcx
0x14010ca7b  mov     r14, [rsp+78h+arg_20]
0x14010ca83  cmp     dword ptr [rcx+4A0h], 0
0x14010ca8a  jz      short loc_14010CAFF
0x14010ca8c  xor     edx, edx; hFile
0x14010ca8e  mov     r8d, 800h; dwFlags
0x14010ca94  lea     rcx, LibFileName; "wkscli.dll"
0x14010ca9b  call    cs:__imp_LoadLibraryExW
0x14010caa2  nop     dword ptr [rax+rax+00h]
0x14010caa7  mov     rsi, rax
0x14010caaa  xor     edi, edi
0x14010caac  test    rax, rax
0x14010caaf  jz      short loc_14010CAF9
0x14010cab1  lea     rdx, aNetpwkstaclien; "NetpWkstaClientGetSmbClientCapabilities"
0x14010cab8  mov     rcx, rax; hModule
0x14010cabb  call    cs:__imp_GetProcAddress
0x14010cac2  nop     dword ptr [rax+rax+00h]
0x14010cac7  test    rax, rax
0x14010caca  jz      short loc_14010CAEA
0x14010cacc  mov     [rsp+78h+var_48], edi
0x14010cad0  lea     rdx, [rsp+78h+var_48]
0x14010cad5  xor     ecx, ecx
0x14010cad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010cadc  test    eax, eax
0x14010cade  jnz     short loc_14010CAEA
0x14010cae0  lea     eax, [rdi+1]
0x14010cae3  test    byte ptr [rsp+78h+var_48], al
0x14010cae7  cmovnz  edi, eax
0x14010caea  mov     rcx, rsi; hLibModule
0x14010caed  call    cs:__imp_FreeLibrary
0x14010caf4  nop     dword ptr [rax+rax+00h]
0x14010caf9  mov     [rbx+4A0h], edi
0x14010caff  xor     edi, edi
0x14010cb01  lea     rcx, [rbx+488h]
0x14010cb08  mov     rdx, r14
0x14010cb0b  call    ?Reset@?$VmReferencePtr@VWorkerConfiguration@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVWorkerConfiguration@@@Z; Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(WorkerConfiguration *)
0x14010cb10  mov     qword ptr [rsp+78h+var_58], r14; int
0x14010cb15  mov     r9, r13; struct VmMigrationConnection *
0x14010cb18  mov     r8, r12; struct IProcessorManager *
0x14010cb1b  mov     rdx, r15; struct IMemoryManager *
0x14010cb1e  mov     rcx, rbx; this
0x14010cb21  call    ?Initialize@GmoMigration@@MEAAJPEAUIMemoryManager@@PEAUIProcessorManager@@PEAVVmMigrationConnection@@PEAVMigrationManager@@@Z; GmoMigration::Initialize(IMemoryManager *,IProcessorManager *,VmMigrationConnection *,MigrationManager *)
0x14010cb26  mov     rcx, [rsp+78h]; this
0x14010cb2b  test    eax, eax
0x14010cb2d  jns     short loc_14010CB43
0x14010cb2f  mov     r9d, eax; char *
0x14010cb32  lea     r8, aOnecoreVmWorke_74; "onecore\\vm\\worker\\migration\\gmomigr"...
0x14010cb39  mov     edx, 15Bh; void *
0x14010cb3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14010cb43  mov     rcx, [rbx+490h]
0x14010cb4a  mov     r8, [rcx]
0x14010cb4d  lea     rax, [rbx+450h]
0x14010cb54  neg     rbx
0x14010cb57  sbb     rdx, rdx
0x14010cb5a  and     rdx, rax
0x14010cb5d  mov     rax, [r8+0E0h]
0x14010cb64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14010cb69  nop
0x14010cb6a  jmp     short loc_14010CB70
0x14010cb6c  mov     edi, [rsp+78h+var_48]
0x14010cb70  mov     eax, edi
0x14010cb72  mov     rcx, [rsp+78h+var_40]
0x14010cb77  xor     rcx, rsp; StackCookie
0x14010cb7a  call    __security_check_cookie
0x14010cb7f  add     rsp, 40h
0x14010cb83  pop     r15
0x14010cb85  pop     r14
0x14010cb87  pop     r13
0x14010cb89  pop     r12
0x14010cb8b  pop     rdi
0x14010cb8c  pop     rsi
0x14010cb8d  pop     rbx
0x14010cb8e  retn
```
