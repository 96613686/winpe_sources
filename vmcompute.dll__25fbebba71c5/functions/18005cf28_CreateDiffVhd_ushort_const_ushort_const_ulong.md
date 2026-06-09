# CreateDiffVhd(ushort const *,ushort const *,ulong)

- ea: `0x18005cf28`
- end: `0x18005d140`
- name: `?CreateDiffVhd@@YAXPEBG0K@Z`
- size: `536`
- prototype: `void __fastcall(PCWSTR Path, PCWSTR, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800355f0`
- `0x1800369c0`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x180022d10`
- `0x18002ee18`
- `0x18005cf28`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d025`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d0d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d025`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d0d2`
- `VirtDisk!OpenVirtualDisk` at `0x18005cfba`
- `VirtDisk!OpenVirtualDisk` at `0x18005cfba`
- `VirtDisk!GetVirtualDiskInformation` at `0x18005cff9`
- `VirtDisk!GetVirtualDiskInformation` at `0x18005cff9`
- `VirtDisk!CreateVirtualDisk` at `0x18005d0ad`
- `VirtDisk!CreateVirtualDisk` at `0x18005d0ad`

## string_xrefs

- `0x18005d104`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x18005d119`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x18005d12e`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CreateDiffVhd(PCWSTR Path, PCWSTR a2, int a3)
{
  ULONG BlockSize; // ebx
  void **Handle; // rax
  DWORD v7; // eax
  DWORD VirtualDiskInformation; // eax
  void **v9; // rax
  DWORD v10; // eax
  unsigned int Parameters; // [rsp+20h] [rbp-E0h]
  unsigned int Parametersa; // [rsp+20h] [rbp-E0h]
  struct _CREATE_VIRTUAL_DISK_PARAMETERS v13; // [rsp+50h] [rbp-B0h] BYREF
  ULONG VirtualDiskInfoSize; // [rsp+110h] [rbp+10h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+118h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+120h] [rbp+20h] BYREF
  struct _GET_VIRTUAL_DISK_INFO VirtualDiskInfo; // [rsp+128h] [rbp+28h] BYREF
  struct _VIRTUAL_STORAGE_TYPE VirtualStorageType; // [rsp+148h] [rbp+48h] BYREF
  struct _VIRTUAL_STORAGE_TYPE v19; // [rsp+160h] [rbp+60h] BYREF
  struct _OPEN_VIRTUAL_DISK_PARAMETERS v20; // [rsp+178h] [rbp+78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  BlockSize = a3 << 20;
  if ( !(a3 << 20) )
  {
    memset(&VirtualStorageType, 0, sizeof(VirtualStorageType));
    v20.Version = OPEN_VIRTUAL_DISK_VERSION_2;
    memset(&v20.Version1, 0, 40);
    VirtualDiskHandle = (HANDLE)-1LL;
    Handle = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&VirtualDiskHandle);
    v7 = OpenVirtualDisk(
           &VirtualStorageType,
           a2,
           VIRTUAL_DISK_ACCESS_NONE,
           OPEN_VIRTUAL_DISK_FLAG_NO_PARENTS,
           &v20,
           Handle);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        (const char *)v7,
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
    if ( (char *)VirtualDiskHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(VirtualDiskHandle);
  }
  *(_QWORD *)&v13.Version = 2;
  memset_0(&v13.Version1, 0, 0xB0u);
  v13.Version1.SourcePath = a2;
  v13.Version1.BlockSizeInBytes = BlockSize;
  v13.Version2.OpenFlags = OPEN_VIRTUAL_DISK_FLAG_CACHED_IO;
  memset(&v19, 0, sizeof(v19));
  hObject = (HANDLE)-1LL;
  v9 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
  v10 = CreateVirtualDisk(&v19, Path, VIRTUAL_DISK_ACCESS_NONE, 0, CREATE_VIRTUAL_DISK_FLAG_NONE, 0, &v13, 0, v9);
  if ( v10 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      (const char *)v10,
      Parametersa);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x18005cf28  mov     [rsp-8+arg_18], rbx
0x18005cf2d  push    rbp
0x18005cf2e  push    rsi
0x18005cf2f  push    rdi
0x18005cf30  lea     rbp, [rsp-0B0h]
0x18005cf38  sub     rsp, 1B0h
0x18005cf3f  mov     rax, cs:__security_cookie
0x18005cf46  xor     rax, rsp
0x18005cf49  mov     [rbp+0C0h+var_18], rax
0x18005cf50  mov     ebx, r8d
0x18005cf53  mov     rdi, rdx
0x18005cf56  mov     rsi, rcx
0x18005cf59  shl     ebx, 14h
0x18005cf5c  test    ebx, ebx
0x18005cf5e  jnz     loc_18005D031
0x18005cf64  xorps   xmm0, xmm0
0x18005cf67  xor     eax, eax
0x18005cf69  movups  xmmword ptr [rbp+0C0h+VirtualStorageType.DeviceId], xmm0
0x18005cf6d  mov     dword ptr [rbp+0C0h+VirtualStorageType.VendorId.Data4+4], eax
0x18005cf70  mov     [rbp+0C0h+var_48.Version], 2
0x18005cf77  movups  xmmword ptr [rbp+0C0h+var_48.4], xmm0
0x18005cf7b  movups  xmmword ptr [rbp+0C0h+var_48.4+10h], xmm0
0x18005cf82  mov     qword ptr [rbp+0C0h+var_48.4+20h], rax
0x18005cf89  mov     [rbp+0C0h+VirtualDiskHandle], 0FFFFFFFFFFFFFFFFh
0x18005cf91  lea     rcx, [rbp+0C0h+VirtualDiskHandle]
0x18005cf95  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18005cf9a  mov     [rsp+1C0h+Handle], rax; Handle
0x18005cf9f  lea     rax, [rbp+0C0h+var_48]
0x18005cfa3  mov     [rsp+1C0h+Parameters], rax; unsigned int
0x18005cfa8  mov     ebx, 1
0x18005cfad  mov     r9d, ebx; Flags
0x18005cfb0  xor     r8d, r8d; VirtualDiskAccessMask
0x18005cfb3  mov     rdx, rdi; Path
0x18005cfb6  lea     rcx, [rbp+0C0h+VirtualStorageType]; VirtualStorageType
0x18005cfba  call    cs:__imp_OpenVirtualDisk
0x18005cfc1  nop     dword ptr [rax+rax+00h]
0x18005cfc6  mov     rcx, [rbp+0C8h]; this
0x18005cfcd  test    eax, eax
0x18005cfcf  jnz     loc_18005D116
0x18005cfd5  xorps   xmm0, xmm0
0x18005cfd8  movups  xmmword ptr [rbp+0C0h+VirtualDiskInfo.Version], xmm0
0x18005cfdc  movups  xmmword ptr [rbp+0C0h+VirtualDiskInfo.8+8], xmm0
0x18005cfe0  mov     [rbp+0C0h+VirtualDiskInfo.Version], ebx
0x18005cfe3  mov     [rbp+0C0h+VirtualDiskInfoSize], 20h ; ' '
0x18005cfea  xor     r9d, r9d; SizeUsed
0x18005cfed  lea     r8, [rbp+0C0h+VirtualDiskInfo]; VirtualDiskInfo
0x18005cff1  lea     rdx, [rbp+0C0h+VirtualDiskInfoSize]; VirtualDiskInfoSize
0x18005cff5  mov     rcx, [rbp+0C0h+VirtualDiskHandle]; VirtualDiskHandle
0x18005cff9  call    cs:__imp_GetVirtualDiskInformation
0x18005d000  nop     dword ptr [rax+rax+00h]
0x18005d005  mov     rcx, [rbp+0C8h]; this
0x18005d00c  test    eax, eax
0x18005d00e  jnz     loc_18005D12B
0x18005d014  mov     ebx, dword ptr [rbp+0C0h+VirtualDiskInfo.8+10h]
0x18005d017  mov     rcx, [rbp+0C0h+VirtualDiskHandle]; hObject
0x18005d01b  lea     rax, [rcx-1]
0x18005d01f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005d023  ja      short loc_18005D031
0x18005d025  call    cs:__imp_CloseHandle
0x18005d02c  nop     dword ptr [rax+rax+00h]
0x18005d031  mov     qword ptr [rsp+1C0h+var_170.Version], 2
0x18005d03a  xor     edx, edx; Val
0x18005d03c  mov     r8d, 0B0h; Size
0x18005d042  lea     rcx, [rsp+1C0h+var_170.8]; void *
0x18005d047  call    memset_0
0x18005d04c  mov     qword ptr [rbp+0C0h+var_170.8+28h], rdi
0x18005d050  mov     dword ptr [rsp+1C0h+var_170.8+18h], ebx
0x18005d054  mov     dword ptr [rbp+0C0h+var_170.8+38h], 8
0x18005d05b  xorps   xmm0, xmm0
0x18005d05e  xor     eax, eax
0x18005d060  movups  xmmword ptr [rbp+0C0h+var_60.DeviceId], xmm0
0x18005d064  mov     dword ptr [rbp+0C0h+var_60.VendorId.Data4+4], eax
0x18005d067  mov     [rbp+0C0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18005d06f  lea     rcx, [rbp+0C0h+hObject]
0x18005d073  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18005d078  mov     [rsp+1C0h+var_180], rax; Handle
0x18005d07d  mov     [rsp+1C0h+Overlapped], 0; Overlapped
0x18005d086  lea     rax, [rsp+1C0h+var_170]
0x18005d08b  mov     [rsp+1C0h+var_190], rax; Parameters
0x18005d090  mov     dword ptr [rsp+1C0h+Handle], 0; ProviderSpecificFlags
0x18005d098  mov     dword ptr [rsp+1C0h+Parameters], 0; unsigned int
0x18005d0a0  xor     r9d, r9d; SecurityDescriptor
0x18005d0a3  xor     r8d, r8d; VirtualDiskAccessMask
0x18005d0a6  mov     rdx, rsi; Path
0x18005d0a9  lea     rcx, [rbp+0C0h+var_60]; VirtualStorageType
0x18005d0ad  call    cs:__imp_CreateVirtualDisk
0x18005d0b4  nop     dword ptr [rax+rax+00h]
0x18005d0b9  mov     rcx, [rbp+0C8h]; this
0x18005d0c0  test    eax, eax
0x18005d0c2  jnz     short loc_18005D101
0x18005d0c4  mov     rcx, [rbp+0C0h+hObject]; hObject
0x18005d0c8  lea     rax, [rcx-1]
0x18005d0cc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005d0d0  ja      short loc_18005D0DE
0x18005d0d2  call    cs:__imp_CloseHandle
0x18005d0d9  nop     dword ptr [rax+rax+00h]
0x18005d0de  mov     rcx, [rbp+0C0h+var_18]
0x18005d0e5  xor     rcx, rsp; StackCookie
0x18005d0e8  call    __security_check_cookie
0x18005d0ed  mov     rbx, [rsp+1C0h+arg_18]
0x18005d0f5  add     rsp, 1B0h
0x18005d0fc  pop     rdi
0x18005d0fd  pop     rsi
0x18005d0fe  pop     rbp
0x18005d0ff  retn
0x18005d101  mov     r9d, eax; char *
0x18005d104  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005d10b  mov     edx, 0E3h; void *
0x18005d110  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005d116  mov     r9d, eax; char *
0x18005d119  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005d120  mov     edx, 0C4h; void *
0x18005d125  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005d12b  mov     r9d, eax; char *
0x18005d12e  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005d135  mov     edx, 0CEh; void *
0x18005d13a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
