# GmoMigrationSmb::Initialize(IMemoryManager *,IProcessorManager *,VmMigrationConnection *,MigrationManager *)

- ea: `0x1400c5f00`
- end: `0x1400c6040`
- name: `?Initialize@GmoMigrationSmb@@MEAAJPEAUIMemoryManager@@PEAUIProcessorManager@@PEAVVmMigrationConnection@@PEAVMigrationManager@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(GmoMigrationSmb *__hidden this, struct IMemoryManager *, struct IProcessorManager *, struct VmMigrationConnection *, struct MigrationManager *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1400c3918`

## callees

- `0x140055a90`
- `0x14006af58`
- `0x1400c5f00`
- `0x1400c6050`
- `0x140132960`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400c5f4b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400c5f4b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400c5f9d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400c5f9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400c5f6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400c5f6b`

## string_xrefs

- `0x1400c5f61`: `NetpWkstaClientGetSmbClientCapabilities`
- `0x1400c5f44`: `wkscli.dll`

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

  if ( *((_DWORD *)this + 252) )
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
    *((_DWORD *)this + 252) = v11;
  }
  v13 = 0;
  try
  {
    Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset((char *)this + 984, a5);
    v14 = GmoMigration::Initialize(this, a2, a3, a4, a5);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecore\\vm\\worker\\migration\\gmomigrationsmb.cpp",
        (const char *)(unsigned int)v14,
        v17);
    (*(void (__fastcall **)(_QWORD, unsigned __int64))(**((_QWORD **)this + 124) + 224LL))(
      *((_QWORD *)this + 124),
      ((unsigned __int64)this + 928) & -(__int64)(this != 0));
  }
  catch ( ... )
  {
    return (unsigned int)Vml::GetHResultFromThrownExceptionAndTrace(
                           (Vml *)0x41E2,
                           (unsigned __int16)&off_1402DB588,
                           v15);
  }
  return v13;
}

```

## disassembly

```asm
0x1400c5f00  push    rbx
0x1400c5f02  push    rsi
0x1400c5f03  push    rdi
0x1400c5f04  push    r12
0x1400c5f06  push    r13
0x1400c5f08  push    r14
0x1400c5f0a  push    r15
0x1400c5f0c  sub     rsp, 40h
0x1400c5f10  mov     rax, cs:__security_cookie
0x1400c5f17  xor     rax, rsp
0x1400c5f1a  mov     [rsp+78h+var_40], rax
0x1400c5f1f  mov     r13, r9
0x1400c5f22  mov     r12, r8
0x1400c5f25  mov     r15, rdx
0x1400c5f28  mov     rbx, rcx
0x1400c5f2b  mov     r14, [rsp+78h+arg_20]
0x1400c5f33  cmp     dword ptr [rcx+3F0h], 0
0x1400c5f3a  jz      short loc_1400C5FAF
0x1400c5f3c  xor     edx, edx; hFile
0x1400c5f3e  mov     r8d, 800h; dwFlags
0x1400c5f44  lea     rcx, LibFileName; "wkscli.dll"
0x1400c5f4b  call    cs:__imp_LoadLibraryExW
0x1400c5f52  nop     dword ptr [rax+rax+00h]
0x1400c5f57  mov     rsi, rax
0x1400c5f5a  xor     edi, edi
0x1400c5f5c  test    rax, rax
0x1400c5f5f  jz      short loc_1400C5FA9
0x1400c5f61  lea     rdx, aNetpwkstaclien; "NetpWkstaClientGetSmbClientCapabilities"
0x1400c5f68  mov     rcx, rax; hModule
0x1400c5f6b  call    cs:__imp_GetProcAddress
0x1400c5f72  nop     dword ptr [rax+rax+00h]
0x1400c5f77  test    rax, rax
0x1400c5f7a  jz      short loc_1400C5F9A
0x1400c5f7c  mov     [rsp+78h+var_48], edi
0x1400c5f80  lea     rdx, [rsp+78h+var_48]
0x1400c5f85  xor     ecx, ecx
0x1400c5f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c5f8c  test    eax, eax
0x1400c5f8e  jnz     short loc_1400C5F9A
0x1400c5f90  lea     eax, [rdi+1]
0x1400c5f93  test    byte ptr [rsp+78h+var_48], al
0x1400c5f97  cmovnz  edi, eax
0x1400c5f9a  mov     rcx, rsi; hLibModule
0x1400c5f9d  call    cs:__imp_FreeLibrary
0x1400c5fa4  nop     dword ptr [rax+rax+00h]
0x1400c5fa9  mov     [rbx+3F0h], edi
0x1400c5faf  xor     edi, edi
0x1400c5fb1  lea     rcx, [rbx+3D8h]
0x1400c5fb8  mov     rdx, r14
0x1400c5fbb  call    ?Reset@?$VmReferencePtr@VWorkerConfiguration@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVWorkerConfiguration@@@Z; Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(WorkerConfiguration *)
0x1400c5fc0  mov     qword ptr [rsp+78h+var_58], r14; int
0x1400c5fc5  mov     r9, r13; struct VmMigrationConnection *
0x1400c5fc8  mov     r8, r12; struct IProcessorManager *
0x1400c5fcb  mov     rdx, r15; struct IMemoryManager *
0x1400c5fce  mov     rcx, rbx; this
0x1400c5fd1  call    ?Initialize@GmoMigration@@MEAAJPEAUIMemoryManager@@PEAUIProcessorManager@@PEAVVmMigrationConnection@@PEAVMigrationManager@@@Z; GmoMigration::Initialize(IMemoryManager *,IProcessorManager *,VmMigrationConnection *,MigrationManager *)
0x1400c5fd6  mov     rcx, [rsp+78h]; this
0x1400c5fdb  test    eax, eax
0x1400c5fdd  jns     short loc_1400C5FF3
0x1400c5fdf  mov     r9d, eax; char *
0x1400c5fe2  lea     r8, aOnecoreVmWorke_74; "onecore\\vm\\worker\\migration\\gmomigr"...
0x1400c5fe9  mov     edx, 15Bh; void *
0x1400c5fee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400c5ff3  mov     rcx, [rbx+3E0h]
0x1400c5ffa  mov     r8, [rcx]
0x1400c5ffd  lea     rax, [rbx+3A0h]
0x1400c6004  neg     rbx
0x1400c6007  sbb     rdx, rdx
0x1400c600a  and     rdx, rax
0x1400c600d  mov     rax, [r8+0E0h]
0x1400c6014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c6019  nop
0x1400c601a  jmp     short loc_1400C6020
0x1400c601c  mov     edi, [rsp+78h+var_48]
0x1400c6020  mov     eax, edi
0x1400c6022  mov     rcx, [rsp+78h+var_40]
0x1400c6027  xor     rcx, rsp; StackCookie
0x1400c602a  call    __security_check_cookie
0x1400c602f  add     rsp, 40h
0x1400c6033  pop     r15
0x1400c6035  pop     r14
0x1400c6037  pop     r13
0x1400c6039  pop     r12
0x1400c603b  pop     rdi
0x1400c603c  pop     rsi
0x1400c603d  pop     rbx
0x1400c603e  retn
```
