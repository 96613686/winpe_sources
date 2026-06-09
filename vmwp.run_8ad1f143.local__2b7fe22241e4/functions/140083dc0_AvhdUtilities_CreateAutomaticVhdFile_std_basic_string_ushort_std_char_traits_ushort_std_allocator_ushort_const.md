# AvhdUtilities::CreateAutomaticVhdFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,AvhdUtilities::CreateAutomaticVhdFileFlags)

- ea: `0x140083dc0`
- end: `0x140083fc2`
- name: `?CreateAutomaticVhdFile@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4CreateAutomaticVhdFileFlags@1@@Z`
- size: `514`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14010694c`

## callees

- `0x14005145c`
- `0x14006af58`
- `0x140083dc0`
- `0x140084204`
- `0x14009d7cc`
- `0x1400c3d00`
- `0x140132960`
- `0x14013361c`
- `0x1401bbdac`
- `0x1401ee320`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x140083e54`
- `RPCRT4!UuidCreate` at `0x140083e54`
- `VirtDisk!CreateVirtualDisk` at `0x140083f30`
- `VirtDisk!CreateVirtualDisk` at `0x140083f30`

## string_xrefs

- `0x140083dfa`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x140083e72`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x140083f4b`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x140083f84`: `onecore\vm\common\avhd\avhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall AvhdUtilities::CreateAutomaticVhdFile(unsigned __int16 *a1, __int64 a2)
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
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v4 = a1;
  else
    v4 = *(const unsigned __int16 **)a1;
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
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v5 = (const WCHAR *)a2;
  else
    v5 = *(const WCHAR **)a2;
  Parameters.Version1.SourcePath = v5;
  Handle = (void *)-1LL;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(&Handle);
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v6 = a1;
  else
    v6 = *(const WCHAR **)a1;
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
  v8 = AvhdUtilities::CopyFileAcl(a1, (LPCWSTR)a2);
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
0x140083dc0  mov     [rsp+arg_10], rbx
0x140083dc5  push    rdi
0x140083dc6  sub     rsp, 150h
0x140083dcd  mov     rax, cs:__security_cookie
0x140083dd4  xor     rax, rsp
0x140083dd7  mov     [rsp+158h+var_18], rax
0x140083ddf  mov     rdi, rdx
0x140083de2  mov     rbx, rcx
0x140083de5  call    ?IsAutomaticVhd@AvhdUtilities@@SAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AvhdUtilities::IsAutomaticVhd(std::wstring const &)
0x140083dea  test    eax, eax
0x140083dec  jnz     short loc_140083E0B
0x140083dee  mov     rcx, [rsp+158h]; this
0x140083df6  lea     r9d, [rax+57h]; char *
0x140083dfa  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x140083e01  mov     edx, 100h; void *
0x140083e06  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140083e0b  mov     [rsp+158h+VirtualStorageType.DeviceId], 0
0x140083e16  movups  xmm0, xmmword ptr cs:VIRTUAL_STORAGE_TYPE_VENDOR_MICROSOFT.Data1
0x140083e1d  movdqu  xmmword ptr [rsp+158h+VirtualStorageType.VendorId.Data1], xmm0
0x140083e26  cmp     qword ptr [rbx+18h], 7
0x140083e2b  jbe     short loc_140083E32
0x140083e2d  mov     rcx, [rbx]
0x140083e30  jmp     short loc_140083E35
0x140083e32  mov     rcx, rbx; unsigned __int16 *
0x140083e35  call    ?GetVhdDeviceIDFromExtension@@YAKPEBG@Z; GetVhdDeviceIDFromExtension(ushort const *)
0x140083e3a  mov     [rsp+158h+VirtualStorageType.DeviceId], eax
0x140083e41  xorps   xmm0, xmm0
0x140083e44  movups  xmmword ptr [rsp+158h+Uuid.Data1], xmm0
0x140083e4c  lea     rcx, [rsp+158h+Uuid]; Uuid
0x140083e54  call    cs:__imp_UuidCreate
0x140083e5b  nop     dword ptr [rax+rax+00h]
0x140083e60  test    eax, eax
0x140083e62  jz      short loc_140083E83
0x140083e64  mov     rcx, [rsp+158h]; this
0x140083e6c  mov     r9d, 8007000Eh; char *
0x140083e72  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x140083e79  mov     edx, 11Eh; void *
0x140083e7e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140083e83  xor     edx, edx; Val
0x140083e85  mov     r8d, 0B8h; Size
0x140083e8b  lea     rcx, [rsp+158h+var_108]; void *
0x140083e90  call    memset_0
0x140083e95  mov     [rsp+158h+var_108.Version], 2
0x140083e9d  movups  xmm0, xmmword ptr [rsp+158h+Uuid.Data1]
0x140083ea5  movdqu  xmmword ptr [rsp+158h+var_108.8], xmm0
0x140083eab  mov     dword ptr [rsp+158h+var_108.8+18h], 0
0x140083eb3  cmp     qword ptr [rdi+18h], 7
0x140083eb8  jbe     short loc_140083EBF
0x140083eba  mov     rax, [rdi]
0x140083ebd  jmp     short loc_140083EC2
0x140083ebf  mov     rax, rdi
0x140083ec2  mov     qword ptr [rsp+158h+var_108.8+28h], rax
0x140083eca  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140083ece  mov     [rsp+158h+var_48], rdx
0x140083ed6  lea     rcx, [rsp+158h+var_48]
0x140083ede  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140083ee3  cmp     qword ptr [rbx+18h], 7
0x140083ee8  jbe     short loc_140083EEF
0x140083eea  mov     rdx, [rbx]
0x140083eed  jmp     short loc_140083EF2
0x140083eef  mov     rdx, rbx; Path
0x140083ef2  lea     rax, [rsp+158h+var_48]
0x140083efa  mov     [rsp+158h+Handle], rax; Handle
0x140083eff  mov     [rsp+158h+Overlapped], 0; Overlapped
0x140083f08  lea     rax, [rsp+158h+var_108]
0x140083f0d  mov     [rsp+158h+Parameters], rax; Parameters
0x140083f12  mov     [rsp+158h+ProviderSpecificFlags], 0; ProviderSpecificFlags
0x140083f1a  mov     [rsp+158h+Flags], 0; int
0x140083f22  xor     r9d, r9d; SecurityDescriptor
0x140083f25  xor     r8d, r8d; VirtualDiskAccessMask
0x140083f28  lea     rcx, [rsp+158h+VirtualStorageType]; VirtualStorageType
0x140083f30  call    cs:__imp_CreateVirtualDisk
0x140083f37  nop     dword ptr [rax+rax+00h]
0x140083f3c  mov     rcx, [rsp+158h]; this
0x140083f44  test    eax, eax
0x140083f46  jz      short loc_140083F5D
0x140083f48  mov     r9d, eax; char *
0x140083f4b  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x140083f52  mov     edx, 136h; void *
0x140083f57  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140083f5d  lea     rcx, [rsp+158h+var_48]
0x140083f65  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140083f6a  mov     rdx, rdi; LPCWSTR
0x140083f6d  mov     rcx, rbx; pObjectName
0x140083f70  call    ?CopyFileAcl@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; AvhdUtilities::CopyFileAcl(std::wstring const &,std::wstring const &)
0x140083f75  mov     rcx, [rsp+158h]; this
0x140083f7d  test    eax, eax
0x140083f7f  jns     short loc_140083F95
0x140083f81  mov     r9d, eax; char *
0x140083f84  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x140083f8b  mov     edx, 14Eh; void *
0x140083f90  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140083f95  xor     eax, eax
0x140083f97  jmp     short loc_140083FA0
0x140083f99  mov     eax, dword ptr [rsp+158h+var_48]
0x140083fa0  mov     rcx, [rsp+158h+var_18]
0x140083fa8  xor     rcx, rsp; StackCookie
0x140083fab  call    __security_check_cookie
0x140083fb0  mov     rbx, [rsp+158h+arg_10]
0x140083fb8  add     rsp, 150h
0x140083fbf  pop     rdi
0x140083fc0  retn
```
