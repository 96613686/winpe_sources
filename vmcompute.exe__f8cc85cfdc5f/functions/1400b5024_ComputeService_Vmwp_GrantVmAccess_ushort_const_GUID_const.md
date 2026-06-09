# ComputeService::Vmwp::GrantVmAccess(ushort const *,_GUID const &)

- ea: `0x1400b5024`
- end: `0x1400b5281`
- name: `?GrantVmAccess@Vmwp@ComputeService@@YAXPEBGAEBU_GUID@@@Z`
- size: `605`
- prototype: `void __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `5`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400aaa9c`
- `0x1400b4084`
- `0x1400b45f4`
- `0x1400b4cec`
- `0x1400b5c8c`

## callees

- `0x140024030`
- `0x140064c5c`
- `0x140080180`
- `0x1400b5024`
- `0x1400bd968`
- `0x1400bda34`
- `0x1400bdc70`
- `0x1400bdcd0`
- `0x1400be4dc`
- `0x1400c4154`
- `0x1400e91a8`
- `0x1401332f0`
- `0x140134048`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400b5227`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400b523e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400b5227`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400b523e`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1400b51e9`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1400b51e9`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1400b5116`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1400b5116`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400b509a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400b509a`

## string_xrefs

- `0x1400b50c0`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x1400b512d`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x1400b5200`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ComputeService::Vmwp::GrantVmAccess(LPCWSTR lpFileName, DWORD *a2, const struct _GUID *a3)
{
  const struct _GUID *v5; // rdx
  void *VirtualMachineSid; // rax
  char *FileW; // rbx
  const char *v8; // r9
  DWORD SecurityInfo; // eax
  const struct _ACL *Dacl; // rax
  DWORD v11; // eax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  char *v14; // [rsp+40h] [rbp-C0h] BYREF
  PACL pDacl[2]; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR hMem[3]; // [rsp+58h] [rbp-A8h] BYREF
  void *v17[10]; // [rsp+70h] [rbp-90h] BYREF
  void *v18[10]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  memset_0(v18, 0, sizeof(v18));
  VirtualMachineSid = WpSecurity::AllocateVirtualMachineSid(a2, v5);
  Vml::VmSid::VmSid((Vml::VmSid *)v18, VirtualMachineSid);
  FileW = (char *)CreateFileW(lpFileName, 0x60000u, 3u, 0, 3u, 0x80u, 0);
  v14 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x756,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      v8);
  *(_OWORD *)hMem = 0;
  SecurityInfo = GetSecurityInfo(FileW, SE_FILE_OBJECT, 4u, 0, 0, 0, 0, hMem);
  if ( SecurityInfo )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x75D,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)SecurityInfo,
      dwCreationDisposition);
  *(_OWORD *)pDacl = 0;
  Dacl = Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)hMem);
  Vml::VmDacl::VmDacl((Vml::VmDacl *)pDacl, Dacl);
  memset_0(v17, 0, sizeof(v17));
  Vml::VmSid::VmSid(
    (Vml::VmSid *)v17,
    L"S-1-15-3-1024-2268835264-3721307629-241982045-173645152-1490879176-104643441-2915960892-1612460704");
  Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, v18[0], 0x1F01FFu, 0, GRANT_ACCESS);
  Vml::VmAcl::UpdateAccess((Vml::VmAcl *)pDacl, v17[0], 0x1F01FFu, 0, GRANT_ACCESS);
  v11 = SetSecurityInfo(FileW, SE_FILE_OBJECT, 4u, 0, 0, pDacl[0], 0);
  if ( v11 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x769,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)v11,
      dwCreationDispositiona);
  Vml::VmSid::~VmSid((Vml::VmSid *)v17);
  if ( pDacl[0] )
    LocalFree(pDacl[0]);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
  Vml::VmSid::~VmSid((Vml::VmSid *)v18);
}

```

## disassembly

```asm
0x1400b5024  mov     [rsp-8+arg_10], rbx
0x1400b5029  mov     [rsp-8+arg_18], rdi
0x1400b502e  push    rbp
0x1400b502f  lea     rbp, [rsp-20h]
0x1400b5034  sub     rsp, 120h
0x1400b503b  mov     rax, cs:__security_cookie
0x1400b5042  xor     rax, rsp
0x1400b5045  mov     [rbp+20h+var_10], rax
0x1400b5049  mov     rbx, rdx
0x1400b504c  mov     rdi, rcx
0x1400b504f  xor     edx, edx; Val
0x1400b5051  lea     r8d, [rdx+50h]; Size
0x1400b5055  lea     rcx, [rbp+20h+var_60]; void *
0x1400b5059  call    memset_0
0x1400b505e  mov     rcx, rbx; this
0x1400b5061  call    ?AllocateVirtualMachineSid@WpSecurity@@YAPEAXAEBU_GUID@@@Z; WpSecurity::AllocateVirtualMachineSid(_GUID const &)
0x1400b5066  mov     rdx, rax; pSourceSid
0x1400b5069  lea     rcx, [rbp+20h+var_60]; this
0x1400b506d  call    ??0VmSid@Vml@@QEAA@PEAX@Z; Vml::VmSid::VmSid(void *)
0x1400b5072  nop
0x1400b5073  mov     [rsp+120h+hTemplateFile], 0; hTemplateFile
0x1400b507c  mov     [rsp+120h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400b5084  mov     r8d, 3; dwShareMode
0x1400b508a  mov     [rsp+120h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400b508f  xor     r9d, r9d; lpSecurityAttributes
0x1400b5092  mov     edx, 60000h; dwDesiredAccess
0x1400b5097  mov     rcx, rdi; lpFileName
0x1400b509a  call    cs:__imp_CreateFileW
0x1400b50a1  nop     dword ptr [rax+rax+00h]
0x1400b50a6  mov     rbx, rax
0x1400b50a9  mov     [rsp+120h+var_E0], rax
0x1400b50ae  dec     rax
0x1400b50b1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400b50b5  setbe   al
0x1400b50b8  mov     rcx, [rbp+28h]; this
0x1400b50bc  test    al, al
0x1400b50be  jnz     short loc_1400B50D2
0x1400b50c0  lea     r8, aOnecoreVmCompu_62; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x1400b50c7  mov     edx, 756h; void *
0x1400b50cc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400b50d2  xorps   xmm0, xmm0
0x1400b50d5  movups  xmmword ptr [rsp+120h+hMem], xmm0
0x1400b50da  mov     [rsp+120h+hMem], 0
0x1400b50e3  lea     rax, [rsp+120h+hMem]
0x1400b50e8  mov     [rsp+120h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1400b50ed  mov     [rsp+120h+hTemplateFile], 0; ppSacl
0x1400b50f6  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], 0; ppDacl
0x1400b50ff  mov     qword ptr [rsp+120h+dwCreationDisposition], 0; unsigned int
0x1400b5108  xor     r9d, r9d; ppsidOwner
0x1400b510b  lea     edx, [r9+1]; ObjectType
0x1400b510f  lea     r8d, [r9+4]; SecurityInfo
0x1400b5113  mov     rcx, rbx; handle
0x1400b5116  call    cs:__imp_GetSecurityInfo
0x1400b511d  nop     dword ptr [rax+rax+00h]
0x1400b5122  mov     rcx, [rbp+28h]; this
0x1400b5126  test    eax, eax
0x1400b5128  jz      short loc_1400B513F
0x1400b512a  mov     r9d, eax; char *
0x1400b512d  lea     r8, aOnecoreVmCompu_62; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x1400b5134  mov     edx, 75Dh; void *
0x1400b5139  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b513f  xorps   xmm0, xmm0
0x1400b5142  movups  xmmword ptr [rsp+120h+pDacl], xmm0
0x1400b5147  lea     rcx, [rsp+120h+hMem]; this
0x1400b514c  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x1400b5151  mov     rdx, rax; struct _ACL *
0x1400b5154  lea     rcx, [rsp+120h+pDacl]; this
0x1400b5159  call    ??0VmDacl@Vml@@QEAA@PEBU_ACL@@@Z; Vml::VmDacl::VmDacl(_ACL const *)
0x1400b515e  nop
0x1400b515f  xor     edx, edx; Val
0x1400b5161  lea     r8d, [rdx+50h]; Size
0x1400b5165  lea     rcx, [rsp+120h+var_B0]; void *
0x1400b516a  call    memset_0
0x1400b516f  lea     rdx, StringSid; "S-1-15-3-1024-2268835264-3721307629-241"...
0x1400b5176  lea     rcx, [rsp+120h+var_B0]; this
0x1400b517b  call    ??0VmSid@Vml@@QEAA@PEBG@Z; Vml::VmSid::VmSid(ushort const *)
0x1400b5180  nop
0x1400b5181  mov     [rsp+120h+dwCreationDisposition], 1; enum _ACCESS_MODE
0x1400b5189  xor     r9d, r9d; unsigned int
0x1400b518c  mov     edi, 1F01FFh
0x1400b5191  mov     r8d, edi; unsigned int
0x1400b5194  mov     rdx, [rbp+20h+var_60]; void *
0x1400b5198  lea     rcx, [rsp+120h+pDacl]; this
0x1400b519d  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x1400b51a2  mov     [rsp+120h+dwCreationDisposition], 1; enum _ACCESS_MODE
0x1400b51aa  xor     r9d, r9d; unsigned int
0x1400b51ad  mov     r8d, edi; unsigned int
0x1400b51b0  mov     rdx, [rsp+120h+var_B0]; void *
0x1400b51b5  lea     rcx, [rsp+120h+pDacl]; this
0x1400b51ba  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x1400b51bf  mov     rax, [rsp+120h+pDacl]
0x1400b51c4  mov     [rsp+120h+hTemplateFile], 0; pSacl
0x1400b51cd  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rax; pDacl
0x1400b51d2  mov     qword ptr [rsp+120h+dwCreationDisposition], 0; unsigned int
0x1400b51db  xor     r9d, r9d; psidOwner
0x1400b51de  lea     edx, [r9+1]; ObjectType
0x1400b51e2  lea     r8d, [r9+4]; SecurityInfo
0x1400b51e6  mov     rcx, rbx; handle
0x1400b51e9  call    cs:__imp_SetSecurityInfo
0x1400b51f0  nop     dword ptr [rax+rax+00h]
0x1400b51f5  mov     rcx, [rbp+28h]; this
0x1400b51f9  test    eax, eax
0x1400b51fb  jz      short loc_1400B5212
0x1400b51fd  mov     r9d, eax; char *
0x1400b5200  lea     r8, aOnecoreVmCompu_62; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x1400b5207  mov     edx, 769h; void *
0x1400b520c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400b5212  lea     rcx, [rsp+120h+var_B0]; this
0x1400b5217  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x1400b521c  nop
0x1400b521d  mov     rcx, [rsp+120h+pDacl]; hMem
0x1400b5222  test    rcx, rcx
0x1400b5225  jz      short loc_1400B5234
0x1400b5227  call    cs:__imp_LocalFree
0x1400b522e  nop     dword ptr [rax+rax+00h]
0x1400b5233  nop
0x1400b5234  mov     rcx, [rsp+120h+hMem]; hMem
0x1400b5239  test    rcx, rcx
0x1400b523c  jz      short loc_1400B524B
0x1400b523e  call    cs:__imp_LocalFree
0x1400b5245  nop     dword ptr [rax+rax+00h]
0x1400b524a  nop
0x1400b524b  lea     rcx, [rsp+120h+var_E0]; void *
0x1400b5250  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400b5255  nop
0x1400b5256  lea     rcx, [rbp+20h+var_60]; this
0x1400b525a  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x1400b525f  mov     rcx, [rbp+20h+var_10]
0x1400b5263  xor     rcx, rsp; StackCookie
0x1400b5266  call    __security_check_cookie
0x1400b526b  lea     r11, [rsp+120h+var_s0]
0x1400b5273  mov     rbx, [r11+20h]
0x1400b5277  mov     rdi, [r11+28h]
0x1400b527b  mov     rsp, r11
0x1400b527e  pop     rbp
0x1400b527f  retn
```
