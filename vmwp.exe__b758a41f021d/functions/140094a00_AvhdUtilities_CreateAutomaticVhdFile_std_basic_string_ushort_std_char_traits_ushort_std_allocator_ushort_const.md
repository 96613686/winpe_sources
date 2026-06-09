# AvhdUtilities::CreateAutomaticVhdFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,AvhdUtilities::CreateAutomaticVhdFileFlags)

- ea: `0x140094a00`
- end: `0x140094c02`
- name: `?CreateAutomaticVhdFile@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4CreateAutomaticVhdFileFlags@1@@Z`
- size: `514`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, LPCWSTR)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400f66ac`

## callees

- `0x14004f6dc`
- `0x14006596c`
- `0x140078628`
- `0x140085634`
- `0x140094a00`
- `0x1400ba144`
- `0x14011ea40`
- `0x14011f6fc`
- `0x1401aae8c`
- `0x1401ddec0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x140094a94`
- `RPCRT4!UuidCreate` at `0x140094a94`
- `VirtDisk!CreateVirtualDisk` at `0x140094b70`
- `VirtDisk!CreateVirtualDisk` at `0x140094b70`

## string_xrefs

- `0x140094a3a`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x140094ab2`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x140094b8b`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x140094bc4`: `onecore\vm\common\avhd\avhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall AvhdUtilities::CreateAutomaticVhdFile(unsigned __int16 *pObjectName, const WCHAR *a2)
{
  const unsigned __int16 *v4; // rcx
  const WCHAR *v5; // rax
  const WCHAR *v6; // rdx
  DWORD v7; // eax
  int v8; // eax
  CREATE_VIRTUAL_DISK_FLAG Flags; // [rsp+20h] [rbp-138h]
  CREATE_VIRTUAL_DISK_FLAG Flagsa; // [rsp+20h] [rbp-138h]
  struct _CREATE_VIRTUAL_DISK_PARAMETERS Parameters; // [rsp+50h] [rbp-108h] BYREF
  void *Handle; // [rsp+110h] [rbp-48h] BYREF
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+118h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+130h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  if ( !(unsigned int)AvhdUtilities::IsAutomaticVhd() )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
      (const char *)0x57,
      Flags);
  VirtualStorageType.DeviceId = 0;
  VirtualStorageType.VendorId = VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT;
  if ( *((_QWORD *)pObjectName + 3) <= 7u )
    v4 = pObjectName;
  else
    v4 = *(const unsigned __int16 **)pObjectName;
  VirtualStorageType.DeviceId = GetVhdDeviceIDFromExtension(v4);
  Uuid = 0;
  if ( UuidCreate(&Uuid) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
      (const char *)0x8007000ELL,
      Flags);
  memset_0(&Parameters, 0, sizeof(Parameters));
  Parameters.Version = CREATE_VIRTUAL_DISK_VERSION_2;
  Parameters.Version1.UniqueId = Uuid;
  Parameters.Version1.BlockSizeInBytes = 0;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v5 = a2;
  else
    v5 = *(const WCHAR **)a2;
  Parameters.Version1.SourcePath = v5;
  Handle = (void *)-1LL;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(&Handle);
  if ( *((_QWORD *)pObjectName + 3) <= 7u )
    v6 = pObjectName;
  else
    v6 = *(const WCHAR **)pObjectName;
  v7 = CreateVirtualDisk(
         &VirtualStorageType,
         v6,
         VIRTUAL_DISK_ACCESS_NONE,
         0,
         CREATE_VIRTUAL_DISK_FLAG_NONE,
         0,
         &Parameters,
         0,
         &Handle);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
      (const char *)v7,
      Flagsa);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Handle);
  v8 = AvhdUtilities::CopyFileAcl(pObjectName, a2);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
      (const char *)(unsigned int)v8,
      Flagsa);
  return 0;
}

```

## disassembly

```asm
0x140094a00  mov     [rsp+arg_10], rbx
0x140094a05  push    rdi
0x140094a06  sub     rsp, 150h
0x140094a0d  mov     rax, cs:__security_cookie
0x140094a14  xor     rax, rsp
0x140094a17  mov     [rsp+158h+var_18], rax
0x140094a1f  mov     rdi, rdx
0x140094a22  mov     rbx, rcx
0x140094a25  call    ?IsAutomaticVhd@AvhdUtilities@@SAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AvhdUtilities::IsAutomaticVhd(std::wstring const &)
0x140094a2a  test    eax, eax
0x140094a2c  jnz     short loc_140094A4B
0x140094a2e  mov     rcx, [rsp+158h]; this
0x140094a36  lea     r9d, [rax+57h]; char *
0x140094a3a  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x140094a41  mov     edx, 100h; void *
0x140094a46  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140094a4b  mov     [rsp+158h+VirtualStorageType.DeviceId], 0
0x140094a56  movups  xmm0, xmmword ptr cs:VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT.Data1
0x140094a5d  movdqu  xmmword ptr [rsp+158h+VirtualStorageType.VendorId.Data1], xmm0
0x140094a66  cmp     qword ptr [rbx+18h], 7
0x140094a6b  jbe     short loc_140094A72
0x140094a6d  mov     rcx, [rbx]
0x140094a70  jmp     short loc_140094A75
0x140094a72  mov     rcx, rbx; unsigned __int16 *
0x140094a75  call    ?GetVhdDeviceIDFromExtension@@YAKPEBG@Z; GetVhdDeviceIDFromExtension(ushort const *)
0x140094a7a  mov     [rsp+158h+VirtualStorageType.DeviceId], eax
0x140094a81  xorps   xmm0, xmm0
0x140094a84  movups  xmmword ptr [rsp+158h+Uuid.Data1], xmm0
0x140094a8c  lea     rcx, [rsp+158h+Uuid]; Uuid
0x140094a94  call    cs:__imp_UuidCreate
0x140094a9b  nop     dword ptr [rax+rax+00h]
0x140094aa0  test    eax, eax
0x140094aa2  jz      short loc_140094AC3
0x140094aa4  mov     rcx, [rsp+158h]; this
0x140094aac  mov     r9d, 8007000Eh; char *
0x140094ab2  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x140094ab9  mov     edx, 11Eh; void *
0x140094abe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140094ac3  xor     edx, edx; Val
0x140094ac5  mov     r8d, 0B8h; Size
0x140094acb  lea     rcx, [rsp+158h+var_108]; void *
0x140094ad0  call    memset_0
0x140094ad5  mov     [rsp+158h+var_108.Version], 2
0x140094add  movups  xmm0, xmmword ptr [rsp+158h+Uuid.Data1]
0x140094ae5  movdqu  xmmword ptr [rsp+158h+var_108.8], xmm0
0x140094aeb  mov     dword ptr [rsp+158h+var_108.8+18h], 0
0x140094af3  cmp     qword ptr [rdi+18h], 7
0x140094af8  jbe     short loc_140094AFF
0x140094afa  mov     rax, [rdi]
0x140094afd  jmp     short loc_140094B02
0x140094aff  mov     rax, rdi
0x140094b02  mov     qword ptr [rsp+158h+var_108.8+28h], rax
0x140094b0a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140094b0e  mov     [rsp+158h+var_48], rdx
0x140094b16  lea     rcx, [rsp+158h+var_48]
0x140094b1e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140094b23  cmp     qword ptr [rbx+18h], 7
0x140094b28  jbe     short loc_140094B2F
0x140094b2a  mov     rdx, [rbx]
0x140094b2d  jmp     short loc_140094B32
0x140094b2f  mov     rdx, rbx; Path
0x140094b32  lea     rax, [rsp+158h+var_48]
0x140094b3a  mov     [rsp+158h+Handle], rax; Handle
0x140094b3f  mov     [rsp+158h+Overlapped], 0; Overlapped
0x140094b48  lea     rax, [rsp+158h+var_108]
0x140094b4d  mov     [rsp+158h+Parameters], rax; Parameters
0x140094b52  mov     [rsp+158h+ProviderSpecificFlags], 0; ProviderSpecificFlags
0x140094b5a  mov     [rsp+158h+Flags], 0; int
0x140094b62  xor     r9d, r9d; SecurityDescriptor
0x140094b65  xor     r8d, r8d; VirtualDiskAccessMask
0x140094b68  lea     rcx, [rsp+158h+VirtualStorageType]; VirtualStorageType
0x140094b70  call    cs:__imp_CreateVirtualDisk
0x140094b77  nop     dword ptr [rax+rax+00h]
0x140094b7c  mov     rcx, [rsp+158h]; this
0x140094b84  test    eax, eax
0x140094b86  jz      short loc_140094B9D
0x140094b88  mov     r9d, eax; char *
0x140094b8b  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x140094b92  mov     edx, 136h; void *
0x140094b97  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140094b9d  lea     rcx, [rsp+158h+var_48]
0x140094ba5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140094baa  mov     rdx, rdi; LPCWSTR
0x140094bad  mov     rcx, rbx; pObjectName
0x140094bb0  call    ?CopyFileAcl@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; AvhdUtilities::CopyFileAcl(std::wstring const &,std::wstring const &)
0x140094bb5  mov     rcx, [rsp+158h]; this
0x140094bbd  test    eax, eax
0x140094bbf  jns     short loc_140094BD5
0x140094bc1  mov     r9d, eax; char *
0x140094bc4  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x140094bcb  mov     edx, 14Eh; void *
0x140094bd0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140094bd5  xor     eax, eax
0x140094bd7  jmp     short loc_140094BE0
0x140094bd9  mov     eax, dword ptr [rsp+158h+var_48]
0x140094be0  mov     rcx, [rsp+158h+var_18]
0x140094be8  xor     rcx, rsp; StackCookie
0x140094beb  call    __security_check_cookie
0x140094bf0  mov     rbx, [rsp+158h+arg_10]
0x140094bf8  add     rsp, 150h
0x140094bff  pop     rdi
0x140094c00  retn
```
