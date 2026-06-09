# CreateDiffVhd(ushort const *,ushort const *,ulong)

- ea: `0x1402331f8`
- end: `0x1402333ec`
- name: `?CreateDiffVhd@@YAXPEBG0K@Z`
- size: `500`
- prototype: `void __fastcall(PCWSTR Path, PCWSTR, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400bcc70`

## callees

- `0x140024030`
- `0x140024f6c`
- `0x1400c4154`
- `0x1401332f0`
- `0x140134048`
- `0x1402331f8`

## import_xrefs

- `VirtDisk!OpenVirtualDisk` at `0x140233288`
- `VirtDisk!OpenVirtualDisk` at `0x140233288`
- `VirtDisk!GetVirtualDiskInformation` at `0x1402332d8`
- `VirtDisk!GetVirtualDiskInformation` at `0x1402332d8`
- `VirtDisk!CreateVirtualDisk` at `0x14023338f`
- `VirtDisk!CreateVirtualDisk` at `0x14023338f`

## string_xrefs

- `0x1402332a2`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x1402332f2`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x1402333a9`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CreateDiffVhd(PCWSTR Path, PCWSTR a2)
{
  DWORD v4; // eax
  DWORD VirtualDiskInformation; // eax
  ULONG BlockSize; // ebx
  DWORD v7; // eax
  unsigned int Parameters; // [rsp+20h] [rbp-E0h]
  unsigned int Parametersa; // [rsp+20h] [rbp-E0h]
  struct _CREATE_VIRTUAL_DISK_PARAMETERS v10; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+110h] [rbp+10h] BYREF
  ULONG VirtualDiskInfoSize; // [rsp+118h] [rbp+18h] BYREF
  void *v13; // [rsp+120h] [rbp+20h] BYREF
  _GET_VIRTUAL_DISK_INFO VirtualDiskInfo; // [rsp+128h] [rbp+28h] BYREF
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+148h] [rbp+48h] BYREF
  struct _VIRTUAL_STORAGE_TYPE v16; // [rsp+160h] [rbp+60h] BYREF
  struct _OPEN_VIRTUAL_DISK_PARAMETERS v17; // [rsp+178h] [rbp+78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  memset(&VirtualStorageType, 0, sizeof(VirtualStorageType));
  v17.Version = OPEN_VIRTUAL_DISK_VERSION_2;
  memset(&v17.Version1, 0, 40);
  VirtualDiskHandle = (HANDLE)-1LL;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &VirtualDiskHandle,
    -1);
  v4 = OpenVirtualDisk(
         &VirtualStorageType,
         a2,
         VIRTUAL_DISK_ACCESS_NONE,
         OPEN_VIRTUAL_DISK_FLAG_NO_PARENTS,
         &v17,
         &VirtualDiskHandle);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      (const char *)v4,
      Parameters);
  memset(&VirtualDiskInfo, 0, sizeof(VirtualDiskInfo));
  VirtualDiskInfo.Version = GET_VIRTUAL_DISK_INFO_SIZE;
  VirtualDiskInfoSize = 32;
  VirtualDiskInformation = GetVirtualDiskInformation(VirtualDiskHandle, &VirtualDiskInfoSize, &VirtualDiskInfo, 0);
  if ( VirtualDiskInformation )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      (const char *)VirtualDiskInformation,
      Parameters);
  BlockSize = VirtualDiskInfo.Size.BlockSize;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&VirtualDiskHandle);
  *(_QWORD *)&v10.Version = 2;
  memset_0(&v10.Version1, 0, 0xB0u);
  v10.Version1.SourcePath = a2;
  v10.Version1.BlockSizeInBytes = BlockSize;
  v10.Version2.OpenFlags = OPEN_VIRTUAL_DISK_FLAG_CACHED_IO;
  memset(&v16, 0, sizeof(v16));
  v13 = (void *)-1LL;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v13,
    -1);
  v7 = CreateVirtualDisk(&v16, Path, VIRTUAL_DISK_ACCESS_NONE, 0, CREATE_VIRTUAL_DISK_FLAG_NONE, 0, &v10, 0, &v13);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      (const char *)v7,
      Parametersa);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
}

```

## disassembly

```asm
0x1402331f8  mov     [rsp-8+arg_10], rbx
0x1402331fd  mov     [rsp-8+arg_18], rsi
0x140233202  push    rbp
0x140233203  push    rdi
0x140233204  push    r15
0x140233206  lea     rbp, [rsp-0B0h]
0x14023320e  sub     rsp, 1B0h
0x140233215  mov     rax, cs:__security_cookie
0x14023321c  xor     rax, rsp
0x14023321f  mov     [rbp+0C0h+var_18], rax
0x140233226  mov     rdi, rdx
0x140233229  mov     rsi, rcx
0x14023322c  xorps   xmm0, xmm0
0x14023322f  xor     eax, eax
0x140233231  movups  xmmword ptr [rbp+0C0h+VirtualStorageType.DeviceId], xmm0
0x140233235  mov     dword ptr [rbp+0C0h+VirtualStorageType.VendorId.Data4+4], eax
0x140233238  mov     [rbp+0C0h+var_48.Version], 2
0x14023323f  movups  xmmword ptr [rbp+0C0h+var_48.4], xmm0
0x140233243  movups  xmmword ptr [rbp+0C0h+var_48.4+10h], xmm0
0x14023324a  mov     qword ptr [rbp+0C0h+var_48.4+20h], rax
0x140233251  or      r15, 0FFFFFFFFFFFFFFFFh
0x140233255  mov     [rbp+0C0h+VirtualDiskHandle], r15
0x140233259  mov     rdx, r15
0x14023325c  lea     rcx, [rbp+0C0h+VirtualDiskHandle]
0x140233260  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140233265  lea     rax, [rbp+0C0h+VirtualDiskHandle]
0x140233269  mov     [rsp+1C0h+Handle], rax; Handle
0x14023326e  lea     rax, [rbp+0C0h+var_48]
0x140233272  mov     [rsp+1C0h+Parameters], rax; unsigned int
0x140233277  lea     ebx, [r15+2]
0x14023327b  mov     r9d, ebx; Flags
0x14023327e  xor     r8d, r8d; VirtualDiskAccessMask
0x140233281  mov     rdx, rdi; Path
0x140233284  lea     rcx, [rbp+0C0h+VirtualStorageType]; VirtualStorageType
0x140233288  call    cs:__imp_OpenVirtualDisk
0x14023328f  nop     dword ptr [rax+rax+00h]
0x140233294  mov     rcx, [rbp+0C8h]; this
0x14023329b  test    eax, eax
0x14023329d  jz      short loc_1402332B4
0x14023329f  mov     r9d, eax; char *
0x1402332a2  lea     r8, aOnecoreVmCompu_100; "onecore\\vm\\compute\\shared\\storage\\"...
0x1402332a9  mov     edx, 0C4h; void *
0x1402332ae  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1402332b4  xorps   xmm0, xmm0
0x1402332b7  movups  xmmword ptr [rbp+0C0h+VirtualDiskInfo.Version], xmm0
0x1402332bb  movups  xmmword ptr [rbp+0C0h+VirtualDiskInfo.8+8], xmm0
0x1402332bf  mov     [rbp+0C0h+VirtualDiskInfo.Version], ebx
0x1402332c2  mov     [rbp+0C0h+VirtualDiskInfoSize], 20h ; ' '
0x1402332c9  xor     r9d, r9d; SizeUsed
0x1402332cc  lea     r8, [rbp+0C0h+VirtualDiskInfo]; VirtualDiskInfo
0x1402332d0  lea     rdx, [rbp+0C0h+VirtualDiskInfoSize]; VirtualDiskInfoSize
0x1402332d4  mov     rcx, [rbp+0C0h+VirtualDiskHandle]; VirtualDiskHandle
0x1402332d8  call    cs:__imp_GetVirtualDiskInformation
0x1402332df  nop     dword ptr [rax+rax+00h]
0x1402332e4  mov     rcx, [rbp+0C8h]; this
0x1402332eb  test    eax, eax
0x1402332ed  jz      short loc_140233304
0x1402332ef  mov     r9d, eax; char *
0x1402332f2  lea     r8, aOnecoreVmCompu_100; "onecore\\vm\\compute\\shared\\storage\\"...
0x1402332f9  mov     edx, 0CEh; void *
0x1402332fe  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140233304  mov     ebx, dword ptr [rbp+0C0h+VirtualDiskInfo.8+10h]
0x140233307  lea     rcx, [rbp+0C0h+VirtualDiskHandle]; void *
0x14023330b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140233310  mov     qword ptr [rsp+1C0h+var_170.Version], 2
0x140233319  xor     edx, edx; Val
0x14023331b  mov     r8d, 0B0h; Size
0x140233321  lea     rcx, [rsp+1C0h+var_170.8]; void *
0x140233326  call    memset_0
0x14023332b  mov     qword ptr [rbp+0C0h+var_170.8+28h], rdi
0x14023332f  mov     dword ptr [rsp+1C0h+var_170.8+18h], ebx
0x140233333  mov     dword ptr [rbp+0C0h+var_170.8+38h], 8
0x14023333a  xorps   xmm0, xmm0
0x14023333d  xor     eax, eax
0x14023333f  movups  xmmword ptr [rbp+0C0h+var_60.DeviceId], xmm0
0x140233343  mov     dword ptr [rbp+0C0h+var_60.VendorId.Data4+4], eax
0x140233346  mov     [rbp+0C0h+var_A0], r15
0x14023334a  mov     rdx, r15
0x14023334d  lea     rcx, [rbp+0C0h+var_A0]
0x140233351  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140233356  lea     rax, [rbp+0C0h+var_A0]
0x14023335a  mov     [rsp+1C0h+var_180], rax; Handle
0x14023335f  mov     [rsp+1C0h+Overlapped], 0; Overlapped
0x140233368  lea     rax, [rsp+1C0h+var_170]
0x14023336d  mov     [rsp+1C0h+var_190], rax; Parameters
0x140233372  mov     dword ptr [rsp+1C0h+Handle], 0; ProviderSpecificFlags
0x14023337a  mov     dword ptr [rsp+1C0h+Parameters], 0; unsigned int
0x140233382  xor     r9d, r9d; SecurityDescriptor
0x140233385  xor     r8d, r8d; VirtualDiskAccessMask
0x140233388  mov     rdx, rsi; Path
0x14023338b  lea     rcx, [rbp+0C0h+var_60]; VirtualStorageType
0x14023338f  call    cs:__imp_CreateVirtualDisk
0x140233396  nop     dword ptr [rax+rax+00h]
0x14023339b  mov     rcx, [rbp+0C8h]; this
0x1402333a2  test    eax, eax
0x1402333a4  jz      short loc_1402333BB
0x1402333a6  mov     r9d, eax; char *
0x1402333a9  lea     r8, aOnecoreVmCompu_100; "onecore\\vm\\compute\\shared\\storage\\"...
0x1402333b0  mov     edx, 0E3h; void *
0x1402333b5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1402333bb  lea     rcx, [rbp+0C0h+var_A0]; void *
0x1402333bf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1402333c4  mov     rcx, [rbp+0C0h+var_18]
0x1402333cb  xor     rcx, rsp; StackCookie
0x1402333ce  call    __security_check_cookie
0x1402333d3  lea     r11, [rsp+1C0h+var_10]
0x1402333db  mov     rbx, [r11+30h]
0x1402333df  mov     rsi, [r11+38h]
0x1402333e3  mov     rsp, r11
0x1402333e6  pop     r15
0x1402333e8  pop     rdi
0x1402333e9  pop     rbp
0x1402333ea  retn
```
