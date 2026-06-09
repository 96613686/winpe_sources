# _lambda_83e7bbb7b373b13c1f2bf36d3decc3d7_::operator()

- ea: `0x18002ee84`
- end: `0x18002f0bb`
- name: `_lambda_83e7bbb7b373b13c1f2bf36d3decc3d7_::operator()`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030f70`

## callees

- `0x180002f50`
- `0x180006660`
- `0x18000d0ec`
- `0x180018bd4`
- `0x180022d10`
- `0x18002ee84`
- `0x180030498`
- `0x18005d664`
- `0x18005dab8`
- `0x18005db40`
- `0x18005f6d8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f032`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f04e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f032`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f04e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002efae`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002efae`
- `VirtDisk!GetVirtualDiskInformation` at `0x18002ef3d`
- `VirtDisk!GetVirtualDiskInformation` at `0x18002ef3d`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x18002eff2`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x18002eff2`

## string_xrefs

- `0x18002f082`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x18002f097`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x18002f0a9`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall lambda_83e7bbb7b373b13c1f2bf36d3decc3d7_::operator()(__int64 a1)
{
  __int64 v2; // rax
  ULONGLONG v3; // rbx
  HANDLE v4; // rdi
  DWORD VirtualDiskInformation; // eax
  const char *v6; // r9
  DWORD VirtualDiskPhysicalPath; // eax
  int result; // eax
  unsigned int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+48h] [rbp-B8h] BYREF
  ULONG VirtualDiskInfoSize[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD InBuffer[2]; // [rsp+58h] [rbp-A8h] BYREF
  _GET_VIRTUAL_DISK_INFO VirtualDiskInfo; // [rsp+68h] [rbp-98h] BYREF
  WCHAR DiskPath[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v2 = anonymous_namespace_::LayerDiskPath(&VirtualDiskInfo);
  std::wstring::operator=(*(_QWORD *)a1, v2);
  std::wstring::~wstring(&VirtualDiskInfo);
  VirtualDiskHandle = 0;
  OpenVhd(&VirtualDiskHandle);
  v3 = **(_QWORD **)(a1 + 24);
  v4 = VirtualDiskHandle;
  memset(&VirtualDiskInfo, 0, sizeof(VirtualDiskInfo));
  VirtualDiskInfoSize[0] = 32;
  VirtualDiskInfo.Version = GET_VIRTUAL_DISK_INFO_SIZE;
  VirtualDiskInformation = GetVirtualDiskInformation(VirtualDiskHandle, VirtualDiskInfoSize, &VirtualDiskInfo, 0);
  if ( VirtualDiskInformation )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2D4,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      (const char *)VirtualDiskInformation,
      lpOutBuffer);
  if ( VirtualDiskInfo.Size.VirtualSize < v3 )
  {
    InBuffer[1] = 1;
    InBuffer[0] = v3;
    BytesReturned = 0;
    if ( !DeviceIoControl(v4, 0x2D1950u, InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2EC,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        v6);
  }
  MountVhd(
    VirtualDiskHandle,
    ATTACH_VIRTUAL_DISK_FLAG_BYPASS_DEFAULT_ENCRYPTION_POLICY|ATTACH_VIRTUAL_DISK_FLAG_NO_DRIVE_LETTER,
    4);
  BytesReturned = 520;
  VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(VirtualDiskHandle, &BytesReturned, DiskPath);
  if ( VirtualDiskPhysicalPath )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2A8,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
      (const char *)VirtualDiskPhysicalPath,
      lpOutBuffer);
  OpenDisk(VirtualDiskInfoSize, DiskPath);
  ExpandPartition(*(HANDLE *)VirtualDiskInfoSize);
  if ( (unsigned __int64)(*(_QWORD *)VirtualDiskInfoSize - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(*(HANDLE *)VirtualDiskInfoSize);
  result = (_DWORD)VirtualDiskHandle - 1;
  if ( (char *)VirtualDiskHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    return CloseHandle(VirtualDiskHandle);
  return result;
}

```

## disassembly

```asm
0x18002ee84  mov     [rsp-8+arg_8], rbx
0x18002ee89  mov     [rsp-8+arg_10], rdi
0x18002ee8e  push    rbp
0x18002ee8f  lea     rbp, [rsp-1B0h]
0x18002ee97  sub     rsp, 2B0h
0x18002ee9e  mov     rax, cs:__security_cookie
0x18002eea5  xor     rax, rsp
0x18002eea8  mov     [rbp+1B0h+var_10], rax
0x18002eeaf  mov     rbx, rcx
0x18002eeb2  mov     r8, [rcx+10h]
0x18002eeb6  mov     rax, [rcx+8]
0x18002eeba  mov     rdx, [rax]
0x18002eebd  mov     r8, [r8]
0x18002eec0  mov     rdx, [rdx+8]
0x18002eec4  lea     rcx, [rsp+2B0h+VirtualDiskInfo]; Src
0x18002eec9  call    _anonymous_namespace___LayerDiskPath
0x18002eece  mov     rdx, rax
0x18002eed1  mov     rcx, [rbx]
0x18002eed4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002eed9  lea     rcx, [rsp+2B0h+VirtualDiskInfo]
0x18002eede  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002eee3  mov     [rsp+2B0h+VirtualDiskHandle], 0
0x18002eeec  mov     rdx, [rbx]
0x18002eeef  cmp     qword ptr [rdx+18h], 7
0x18002eef4  jbe     short loc_18002EEF9
0x18002eef6  mov     rdx, [rdx]
0x18002eef9  lea     rcx, [rsp+2B0h+VirtualDiskHandle]
0x18002eefe  call    ?OpenVhd@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBG_N@Z; OpenVhd(ushort const *,bool)
0x18002ef03  nop
0x18002ef04  mov     rax, [rbx+18h]
0x18002ef08  mov     rbx, [rax]
0x18002ef0b  mov     rdi, [rsp+2B0h+VirtualDiskHandle]
0x18002ef10  xorps   xmm0, xmm0
0x18002ef13  movups  xmmword ptr [rsp+2B0h+VirtualDiskInfo.Version], xmm0
0x18002ef18  movups  xmmword ptr [rsp+2B0h+VirtualDiskInfo.8+8], xmm0
0x18002ef1d  mov     [rsp+2B0h+VirtualDiskInfoSize], 20h ; ' '
0x18002ef25  mov     [rsp+2B0h+VirtualDiskInfo.Version], 1
0x18002ef2d  xor     r9d, r9d; SizeUsed
0x18002ef30  lea     r8, [rsp+2B0h+VirtualDiskInfo]; VirtualDiskInfo
0x18002ef35  lea     rdx, [rsp+2B0h+VirtualDiskInfoSize]; VirtualDiskInfoSize
0x18002ef3a  mov     rcx, rdi; VirtualDiskHandle
0x18002ef3d  call    cs:__imp_GetVirtualDiskInformation
0x18002ef44  nop     dword ptr [rax+rax+00h]
0x18002ef49  mov     rcx, [rbp+1B8h]; this
0x18002ef50  test    eax, eax
0x18002ef52  jnz     loc_18002F094
0x18002ef58  cmp     qword ptr [rsp+2B0h+VirtualDiskInfo.8], rbx
0x18002ef5d  jnb     short loc_18002EFC9
0x18002ef5f  xorps   xmm0, xmm0
0x18002ef62  movups  [rsp+2B0h+InBuffer], xmm0
0x18002ef67  mov     qword ptr [rsp+2B0h+InBuffer], rbx
0x18002ef6c  mov     word ptr [rsp+2B0h+InBuffer+8], 1
0x18002ef73  mov     [rsp+2B0h+BytesReturned], eax
0x18002ef77  mov     [rsp+2B0h+lpOverlapped], 0; lpOverlapped
0x18002ef80  lea     rax, [rsp+2B0h+BytesReturned]
0x18002ef85  mov     [rsp+2B0h+lpBytesReturned], rax; lpBytesReturned
0x18002ef8a  mov     [rsp+2B0h+nOutBufferSize], 0; nOutBufferSize
0x18002ef92  mov     [rsp+2B0h+lpOutBuffer], 0; unsigned int
0x18002ef9b  mov     r9d, 10h; nInBufferSize
0x18002efa1  lea     r8, [rsp+2B0h+InBuffer]; lpInBuffer
0x18002efa6  mov     edx, 2D1950h; dwIoControlCode
0x18002efab  mov     rcx, rdi; hDevice
0x18002efae  call    cs:__imp_DeviceIoControl
0x18002efb5  nop     dword ptr [rax+rax+00h]
0x18002efba  mov     rcx, [rbp+1B8h]; this
0x18002efc1  test    eax, eax
0x18002efc3  jz      loc_18002F0A9
0x18002efc9  mov     edx, 22h ; '"'; enum _ATTACH_VIRTUAL_DISK_FLAG
0x18002efce  lea     r8d, [rdx-1Eh]; unsigned __int16
0x18002efd2  mov     rcx, [rsp+2B0h+VirtualDiskHandle]; void *
0x18002efd7  call    ?MountVhd@@YAXPEAXW4_ATTACH_VIRTUAL_DISK_FLAG@@G@Z; MountVhd(void *,_ATTACH_VIRTUAL_DISK_FLAG,ushort)
0x18002efdc  mov     [rsp+2B0h+BytesReturned], 208h
0x18002efe4  lea     r8, [rbp+1B0h+DiskPath]; DiskPath
0x18002efe8  lea     rdx, [rsp+2B0h+BytesReturned]; DiskPathSizeInBytes
0x18002efed  mov     rcx, [rsp+2B0h+VirtualDiskHandle]; VirtualDiskHandle
0x18002eff2  call    cs:__imp_GetVirtualDiskPhysicalPath
0x18002eff9  nop     dword ptr [rax+rax+00h]
0x18002effe  mov     rcx, [rbp+1B8h]; this
0x18002f005  test    eax, eax
0x18002f007  jnz     short loc_18002F07F
0x18002f009  lea     rdx, [rbp+1B0h+DiskPath]
0x18002f00d  lea     rcx, [rsp+2B0h+VirtualDiskInfoSize]
0x18002f012  call    ?OpenDisk@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGK@Z; OpenDisk(ushort const *,ulong)
0x18002f017  nop
0x18002f018  mov     rcx, qword ptr [rsp+2B0h+VirtualDiskInfoSize]; hDevice
0x18002f01d  call    ?ExpandPartition@@YA_JPEAX@Z; ExpandPartition(void *)
0x18002f022  nop
0x18002f023  mov     rcx, qword ptr [rsp+2B0h+VirtualDiskInfoSize]; hObject
0x18002f028  lea     rax, [rcx-1]
0x18002f02c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f030  ja      short loc_18002F03F
0x18002f032  call    cs:__imp_CloseHandle
0x18002f039  nop     dword ptr [rax+rax+00h]
0x18002f03e  nop
0x18002f03f  mov     rcx, [rsp+2B0h+VirtualDiskHandle]; hObject
0x18002f044  lea     rax, [rcx-1]
0x18002f048  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f04c  ja      short loc_18002F05A
0x18002f04e  call    cs:__imp_CloseHandle
0x18002f055  nop     dword ptr [rax+rax+00h]
0x18002f05a  mov     rcx, [rbp+1B0h+var_10]
0x18002f061  xor     rcx, rsp; StackCookie
0x18002f064  call    __security_check_cookie
0x18002f069  lea     r11, [rsp+2B0h+var_s0]
0x18002f071  mov     rbx, [r11+18h]
0x18002f075  mov     rdi, [r11+20h]
0x18002f079  mov     rsp, r11
0x18002f07c  pop     rbp
0x18002f07d  retn
0x18002f07f  mov     r9d, eax; char *
0x18002f082  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002f089  mov     edx, 2A8h; void *
0x18002f08e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002f094  mov     r9d, eax; char *
0x18002f097  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002f09e  mov     edx, 2D4h; void *
0x18002f0a3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002f0a9  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002f0b0  mov     edx, 2ECh; void *
0x18002f0b5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
