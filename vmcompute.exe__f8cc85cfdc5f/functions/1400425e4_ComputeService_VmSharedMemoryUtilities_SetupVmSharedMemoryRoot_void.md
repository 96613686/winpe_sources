# ComputeService::VmSharedMemoryUtilities::SetupVmSharedMemoryRoot(void)

- ea: `0x1400425e4`
- end: `0x1400427da`
- name: `?SetupVmSharedMemoryRoot@VmSharedMemoryUtilities@ComputeService@@YAXXZ`
- size: `502`
- prototype: `void __fastcall(ComputeService::VmSharedMemoryUtilities *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140041ad8`

## callees

- `0x1400425e4`
- `0x140080180`
- `0x1400ffd74`
- `0x1401332f0`
- `0x140142dac`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14004261c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14004261c`
- `ntdll!NtCreateDirectoryObject` at `0x14004268c`
- `ntdll!NtCreateDirectoryObject` at `0x140042710`
- `ntdll!NtCreateDirectoryObject` at `0x14004268c`
- `ntdll!NtCreateDirectoryObject` at `0x140042710`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004273e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004273e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400427c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400427c8`

## string_xrefs

- `0x14004277a`: `onecore\vm\compute\management\orchestration\shared\vmsharedmemory\vmsharedmemoryutilities.cpp`
- `0x14004279a`: `onecore\vm\compute\management\orchestration\shared\vmsharedmemory\vmsharedmemoryutilities.cpp`
- `0x1400427ac`: `onecore\vm\compute\management\orchestration\shared\vmsharedmemory\vmsharedmemoryutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ComputeService::VmSharedMemoryUtilities::SetupVmSharedMemoryRoot(
        ComputeService::VmSharedMemoryUtilities *this)
{
  const char *v1; // r9
  unsigned int v2; // eax
  unsigned int v3; // eax
  __int64 v4; // [rsp+20h] [rbp-60h] BYREF
  const wchar_t *v5; // [rsp+28h] [rbp-58h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-50h] BYREF
  void *DirectoryHandle; // [rsp+60h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:S-1-5-80-3867325368-3464583989-2985581467-4189893692-1030155791D:(A;CINP;GA;;;S-1-5-80-3867325368-3464583989"
           "-2985581467-4189893692-1030155791)(A;;GR;;;WD)",
          1u,
          &SecurityDescriptor,
          0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmsharedmemory\\vmsharedmemoryutilities.cpp",
      v1);
  v4 = 2097182;
  v5 = L"\\VmSharedMemory";
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 80;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v4;
  ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  ObjectAttributes.SecurityQualityOfService = 0;
  DirectoryHandle = 0;
  v2 = NtCreateDirectoryObject(&DirectoryHandle, 0xF000Fu, &ObjectAttributes);
  if ( (int)(v2 + 0x80000000) >= 0 && v2 != -1073741771 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmsharedmemory\\vmsharedmemoryutilities.cpp",
      (const char *)v2,
      v4);
  v4 = 2752552;
  v5 = L"\\VmSharedMemory\\Host";
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 80;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v4;
  ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  ObjectAttributes.SecurityQualityOfService = 0;
  if ( (char *)DirectoryHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(DirectoryHandle);
  DirectoryHandle = 0;
  v3 = NtCreateDirectoryObject(&DirectoryHandle, 0xF000Fu, &ObjectAttributes);
  if ( ((v3 + 0x80000000) & 0x80000000) == 0 && v3 != -1073741771 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\shared\\vmsharedmemory\\vmsharedmemoryutilities.cpp",
      (const char *)v3,
      v4);
  if ( (char *)DirectoryHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(DirectoryHandle);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
}

```

## disassembly

```asm
0x1400425e4  mov     [rsp-8+arg_0], rsi
0x1400425e9  push    rbp
0x1400425ea  mov     rbp, rsp
0x1400425ed  sub     rsp, 80h
0x1400425f4  mov     rax, cs:__security_cookie
0x1400425fb  xor     rax, rsp
0x1400425fe  mov     [rbp+var_10], rax
0x140042602  mov     [rbp+SecurityDescriptor], 0
0x14004260a  xor     r9d, r9d; SecurityDescriptorSize
0x14004260d  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140042611  lea     edx, [r9+1]; StringSDRevision
0x140042615  lea     rcx, StringSecurityDescriptor; "O:S-1-5-80-3867325368-3464583989-298558"...
0x14004261c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140042623  nop     dword ptr [rax+rax+00h]
0x140042628  mov     rcx, [rbp+8]; this
0x14004262c  test    eax, eax
0x14004262e  jz      loc_1400427AC
0x140042634  mov     [rbp+var_60], 20001Eh
0x14004263c  lea     rax, aVmsharedmemory; "\\VmSharedMemory"
0x140042643  mov     [rbp+var_58], rax
0x140042647  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14004264f  mov     qword ptr [rbp+ObjectAttributes.Attributes], 50h ; 'P'
0x140042657  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14004265f  lea     rax, [rbp+var_60]
0x140042663  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140042667  mov     rax, [rbp+SecurityDescriptor]
0x14004266b  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x14004266f  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x140042677  mov     [rbp+DirectoryHandle], 0
0x14004267f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140042683  mov     edx, 0F000Fh; DesiredAccess
0x140042688  lea     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x14004268c  call    cs:__imp_NtCreateDirectoryObject
0x140042693  nop     dword ptr [rax+rax+00h]
0x140042698  mov     esi, 80000000h
0x14004269d  lea     ecx, [rax+rsi]
0x1400426a0  test    esi, ecx
0x1400426a2  jz      loc_140042768
0x1400426a8  mov     [rbp+var_60], 2A0028h
0x1400426b0  lea     rax, aVmsharedmemory_0; "\\VmSharedMemory\\Host"
0x1400426b7  mov     [rbp+var_58], rax
0x1400426bb  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400426c2  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400426ca  mov     [rbp+ObjectAttributes.Attributes], 50h ; 'P'
0x1400426d1  lea     rax, [rbp+var_60]
0x1400426d5  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400426d9  mov     rax, [rbp+SecurityDescriptor]
0x1400426dd  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x1400426e1  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x1400426e9  mov     rcx, [rbp+DirectoryHandle]; hObject
0x1400426ed  lea     rax, [rcx-1]
0x1400426f1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400426f5  jbe     loc_1400427BE
0x1400426fb  mov     [rbp+DirectoryHandle], 0
0x140042703  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140042707  mov     edx, 0F000Fh; DesiredAccess
0x14004270c  lea     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x140042710  call    cs:__imp_NtCreateDirectoryObject
0x140042717  nop     dword ptr [rax+rax+00h]
0x14004271c  lea     ecx, [rax+rsi]
0x14004271f  test    esi, ecx
0x140042721  jz      short loc_14004278C
0x140042723  mov     rcx, [rbp+DirectoryHandle]; hObject
0x140042727  lea     rax, [rcx-1]
0x14004272b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14004272f  jbe     loc_1400427C8
0x140042735  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x140042739  test    rcx, rcx
0x14004273c  jz      short loc_14004274A
0x14004273e  call    cs:__imp_LocalFree
0x140042745  nop     dword ptr [rax+rax+00h]
0x14004274a  mov     rcx, [rbp+var_10]
0x14004274e  xor     rcx, rsp; StackCookie
0x140042751  call    __security_check_cookie
0x140042756  mov     rsi, [rsp+80h+arg_0]
0x14004275e  add     rsp, 80h
0x140042765  pop     rbp
0x140042766  retn
0x140042768  cmp     eax, 0C0000035h
0x14004276d  jz      loc_1400426A8
0x140042773  mov     rcx, [rbp+8]; this
0x140042777  mov     r9d, eax; char *
0x14004277a  lea     r8, aOnecoreVmCompu_124; "onecore\\vm\\compute\\management\\orche"...
0x140042781  mov     edx, 43h ; 'C'; void *
0x140042786  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x14004278c  cmp     eax, 0C0000035h
0x140042791  jz      short loc_140042723
0x140042793  mov     rcx, [rbp+8]; this
0x140042797  mov     r9d, eax; char *
0x14004279a  lea     r8, aOnecoreVmCompu_124; "onecore\\vm\\compute\\management\\orche"...
0x1400427a1  mov     edx, 53h ; 'S'; void *
0x1400427a6  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1400427ac  lea     r8, aOnecoreVmCompu_124; "onecore\\vm\\compute\\management\\orche"...
0x1400427b3  mov     edx, 31h ; '1'; void *
0x1400427b8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400427be  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x1400427c3  jmp     loc_1400426FB
0x1400427c8  call    cs:__imp_CloseHandle
0x1400427cf  nop     dword ptr [rax+rax+00h]
0x1400427d4  jmp     loc_140042735
```
