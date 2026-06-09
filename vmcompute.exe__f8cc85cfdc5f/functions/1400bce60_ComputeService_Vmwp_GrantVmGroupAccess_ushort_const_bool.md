# ComputeService::Vmwp::GrantVmGroupAccess(ushort const *,bool)

- ea: `0x1400bce60`
- end: `0x1400bd0af`
- name: `?GrantVmGroupAccess@Vmwp@ComputeService@@YAXPEBG_N@Z`
- size: `591`
- prototype: `void __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400bcc70`

## callees

- `0x140024030`
- `0x140064c5c`
- `0x140080180`
- `0x1400bce60`
- `0x1400bd968`
- `0x1400bda34`
- `0x1400bdc70`
- `0x1400bdcd0`
- `0x1400be354`
- `0x1400be4dc`
- `0x1400c4154`
- `0x1401332f0`
- `0x140134048`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400bd059`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400bd070`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400bd059`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400bd070`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1400bd01b`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1400bd01b`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1400bcf47`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1400bcf47`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400bcecb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400bcecb`

## string_xrefs

- `0x1400bcef1`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x1400bcf5e`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x1400bd032`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ComputeService::Vmwp::GrantVmGroupAccess(LPCWSTR lpFileName, const unsigned __int16 *a2)
{
  WpSecurity *v3; // rcx
  void *VirtualMachineGroupSid; // rax
  char *FileW; // rbx
  const char *v6; // r9
  DWORD SecurityInfo; // eax
  const struct _ACL *Dacl; // rax
  DWORD v9; // eax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  char *v12; // [rsp+40h] [rbp-C0h] BYREF
  PACL pDacl[2]; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR hMem[3]; // [rsp+58h] [rbp-A8h] BYREF
  void *v15[10]; // [rsp+70h] [rbp-90h] BYREF
  void *v16[10]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  memset_0(v16, 0, sizeof(v16));
  VirtualMachineGroupSid = WpSecurity::AllocateVirtualMachineGroupSid(v3);
  Vml::VmSid::VmSid((Vml::VmSid *)v16, VirtualMachineGroupSid);
  FileW = (char *)CreateFileW(lpFileName, 0x60000u, 3u, 0, 3u, 0x80u, 0);
  v12 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x782,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      v6);
  *(_OWORD *)hMem = 0;
  SecurityInfo = GetSecurityInfo(FileW, SE_FILE_OBJECT, 4u, 0, 0, 0, 0, hMem);
  if ( SecurityInfo )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x789,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)SecurityInfo,
      dwCreationDisposition);
  *(_OWORD *)pDacl = 0;
  Dacl = Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)hMem);
  Vml::VmDacl::VmDacl((Vml::VmDacl *)pDacl, Dacl);
  memset_0(v15, 0, sizeof(v15));
  Vml::VmSid::VmSid(
    (Vml::VmSid *)v15,
    L"S-1-15-3-1024-2268835264-3721307629-241982045-173645152-1490879176-104643441-2915960892-1612460704");
  Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, v16[0], 0x120089u, 0, GRANT_ACCESS);
  Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, v15[0], 0x120089u, 0, GRANT_ACCESS);
  v9 = SetSecurityInfo(FileW, SE_FILE_OBJECT, 4u, 0, 0, pDacl[0], 0);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x79C,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)v9,
      dwCreationDispositiona);
  Vml::VmSid::~VmSid((Vml::VmSid *)v15);
  if ( pDacl[0] )
    LocalFree(pDacl[0]);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v12);
  Vml::VmSid::~VmSid((Vml::VmSid *)v16);
}

```

## disassembly

```asm
0x1400bce60  mov     [rsp-8+arg_8], rbx
0x1400bce65  push    rbp
0x1400bce66  lea     rbp, [rsp-20h]
0x1400bce6b  sub     rsp, 120h
0x1400bce72  mov     rax, cs:__security_cookie
0x1400bce79  xor     rax, rsp
0x1400bce7c  mov     [rbp+20h+var_10], rax
0x1400bce80  mov     rbx, rcx
0x1400bce83  xor     edx, edx; Val
0x1400bce85  lea     r8d, [rdx+50h]; Size
0x1400bce89  lea     rcx, [rbp+20h+var_60]; void *
0x1400bce8d  call    memset_0
0x1400bce92  call    ?AllocateVirtualMachineGroupSid@WpSecurity@@YAPEAXXZ; WpSecurity::AllocateVirtualMachineGroupSid(void)
0x1400bce97  mov     rdx, rax; pSourceSid
0x1400bce9a  lea     rcx, [rbp+20h+var_60]; this
0x1400bce9e  call    ??0VmSid@Vml@@QEAA@PEAX@Z; Vml::VmSid::VmSid(void *)
0x1400bcea3  nop
0x1400bcea4  mov     [rsp+120h+hTemplateFile], 0; hTemplateFile
0x1400bcead  mov     [rsp+120h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400bceb5  mov     r8d, 3; dwShareMode
0x1400bcebb  mov     [rsp+120h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400bcec0  xor     r9d, r9d; lpSecurityAttributes
0x1400bcec3  mov     edx, 60000h; dwDesiredAccess
0x1400bcec8  mov     rcx, rbx; lpFileName
0x1400bcecb  call    cs:__imp_CreateFileW
0x1400bced2  nop     dword ptr [rax+rax+00h]
0x1400bced7  mov     rbx, rax
0x1400bceda  mov     [rsp+120h+var_E0], rax
0x1400bcedf  dec     rax
0x1400bcee2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400bcee6  setbe   al
0x1400bcee9  mov     rcx, [rbp+28h]; this
0x1400bceed  test    al, al
0x1400bceef  jnz     short loc_1400BCF03
0x1400bcef1  lea     r8, aOnecoreVmCompu_62; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x1400bcef8  mov     edx, 782h; void *
0x1400bcefd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400bcf03  xorps   xmm0, xmm0
0x1400bcf06  movups  xmmword ptr [rsp+120h+hMem], xmm0
0x1400bcf0b  mov     [rsp+120h+hMem], 0
0x1400bcf14  lea     rax, [rsp+120h+hMem]
0x1400bcf19  mov     [rsp+120h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1400bcf1e  mov     [rsp+120h+hTemplateFile], 0; ppSacl
0x1400bcf27  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], 0; ppDacl
0x1400bcf30  mov     qword ptr [rsp+120h+dwCreationDisposition], 0; unsigned int
0x1400bcf39  xor     r9d, r9d; ppsidOwner
0x1400bcf3c  lea     edx, [r9+1]; ObjectType
0x1400bcf40  lea     r8d, [r9+4]; SecurityInfo
0x1400bcf44  mov     rcx, rbx; handle
0x1400bcf47  call    cs:__imp_GetSecurityInfo
0x1400bcf4e  nop     dword ptr [rax+rax+00h]
0x1400bcf53  mov     rcx, [rbp+28h]; this
0x1400bcf57  test    eax, eax
0x1400bcf59  jz      short loc_1400BCF70
0x1400bcf5b  mov     r9d, eax; char *
0x1400bcf5e  lea     r8, aOnecoreVmCompu_62; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x1400bcf65  mov     edx, 789h; void *
0x1400bcf6a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400bcf70  xorps   xmm0, xmm0
0x1400bcf73  movups  xmmword ptr [rsp+120h+pDacl], xmm0
0x1400bcf78  lea     rcx, [rsp+120h+hMem]; this
0x1400bcf7d  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x1400bcf82  mov     rdx, rax; struct _ACL *
0x1400bcf85  lea     rcx, [rsp+120h+pDacl]; this
0x1400bcf8a  call    ??0VmDacl@Vml@@QEAA@PEBU_ACL@@@Z; Vml::VmDacl::VmDacl(_ACL const *)
0x1400bcf8f  nop
0x1400bcf90  xor     edx, edx; Val
0x1400bcf92  lea     r8d, [rdx+50h]; Size
0x1400bcf96  lea     rcx, [rsp+120h+var_B0]; void *
0x1400bcf9b  call    memset_0
0x1400bcfa0  lea     rdx, StringSid; "S-1-15-3-1024-2268835264-3721307629-241"...
0x1400bcfa7  lea     rcx, [rsp+120h+var_B0]; this
0x1400bcfac  call    ??0VmSid@Vml@@QEAA@PEBG@Z; Vml::VmSid::VmSid(ushort const *)
0x1400bcfb1  nop
0x1400bcfb2  mov     [rsp+120h+dwCreationDisposition], 1; enum _ACCESS_MODE
0x1400bcfba  xor     r9d, r9d; unsigned int
0x1400bcfbd  mov     r8d, 120089h; unsigned int
0x1400bcfc3  mov     rdx, [rbp+20h+var_60]; void *
0x1400bcfc7  lea     rcx, [rsp+120h+pDacl]; this
0x1400bcfcc  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x1400bcfd1  mov     [rsp+120h+dwCreationDisposition], 1; enum _ACCESS_MODE
0x1400bcfd9  xor     r9d, r9d; unsigned int
0x1400bcfdc  mov     r8d, 120089h; unsigned int
0x1400bcfe2  mov     rdx, [rsp+120h+var_B0]; void *
0x1400bcfe7  lea     rcx, [rsp+120h+pDacl]; this
0x1400bcfec  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x1400bcff1  mov     rax, [rsp+120h+pDacl]
0x1400bcff6  mov     [rsp+120h+hTemplateFile], 0; pSacl
0x1400bcfff  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rax; pDacl
0x1400bd004  mov     qword ptr [rsp+120h+dwCreationDisposition], 0; unsigned int
0x1400bd00d  xor     r9d, r9d; psidOwner
0x1400bd010  lea     edx, [r9+1]; ObjectType
0x1400bd014  lea     r8d, [r9+4]; SecurityInfo
0x1400bd018  mov     rcx, rbx; handle
0x1400bd01b  call    cs:__imp_SetSecurityInfo
0x1400bd022  nop     dword ptr [rax+rax+00h]
0x1400bd027  mov     rcx, [rbp+28h]; this
0x1400bd02b  test    eax, eax
0x1400bd02d  jz      short loc_1400BD044
0x1400bd02f  mov     r9d, eax; char *
0x1400bd032  lea     r8, aOnecoreVmCompu_62; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x1400bd039  mov     edx, 79Ch; void *
0x1400bd03e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400bd044  lea     rcx, [rsp+120h+var_B0]; this
0x1400bd049  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x1400bd04e  nop
0x1400bd04f  mov     rcx, [rsp+120h+pDacl]; hMem
0x1400bd054  test    rcx, rcx
0x1400bd057  jz      short loc_1400BD066
0x1400bd059  call    cs:__imp_LocalFree
0x1400bd060  nop     dword ptr [rax+rax+00h]
0x1400bd065  nop
0x1400bd066  mov     rcx, [rsp+120h+hMem]; hMem
0x1400bd06b  test    rcx, rcx
0x1400bd06e  jz      short loc_1400BD07D
0x1400bd070  call    cs:__imp_LocalFree
0x1400bd077  nop     dword ptr [rax+rax+00h]
0x1400bd07c  nop
0x1400bd07d  lea     rcx, [rsp+120h+var_E0]; void *
0x1400bd082  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400bd087  nop
0x1400bd088  lea     rcx, [rbp+20h+var_60]; this
0x1400bd08c  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x1400bd091  mov     rcx, [rbp+20h+var_10]
0x1400bd095  xor     rcx, rsp; StackCookie
0x1400bd098  call    __security_check_cookie
0x1400bd09d  mov     rbx, [rsp+120h+arg_8]
0x1400bd0a5  add     rsp, 120h
0x1400bd0ac  pop     rbp
0x1400bd0ad  retn
```
