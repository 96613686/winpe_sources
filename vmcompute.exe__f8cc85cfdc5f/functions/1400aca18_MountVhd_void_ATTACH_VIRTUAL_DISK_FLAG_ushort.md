# MountVhd(void *,_ATTACH_VIRTUAL_DISK_FLAG,ushort)

- ea: `0x1400aca18`
- end: `0x1400acc26`
- name: `?MountVhd@@YAXPEAXW4_ATTACH_VIRTUAL_DISK_FLAG@@G@Z`
- size: `526`
- prototype: `void(void *, enum _ATTACH_VIRTUAL_DISK_FLAG, unsigned __int16)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400ab050`
- `0x1400d526c`

## callees

- `0x140024030`
- `0x140080180`
- `0x140087ef4`
- `0x140088698`
- `0x1400aca18`
- `0x1400c4154`
- `0x1401332f0`
- `0x140233b80`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400acbb3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400acbb3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400acac0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400acac0`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1400acb21`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x1400acb21`
- `VirtDisk!AttachVirtualDisk` at `0x1400acb5f`
- `VirtDisk!AttachVirtualDisk` at `0x1400acb5f`

## string_xrefs

- `0x1400acad7`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x1400acb3b`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x1400acb7d`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x1400acbdd`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall MountVhd(void *a1, ATTACH_VIRTUAL_DISK_FLAG a2, __int16 a3)
{
  const char *v5; // r9
  DWORD VirtualDiskPhysicalPath; // eax
  DWORD v7; // eax
  HANDLE FileW; // rax
  const char *v9; // r9
  unsigned int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  HANDLE v11; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-B8h] BYREF
  ULONG DiskPathSizeInBytes; // [rsp+50h] [rbp-B0h] BYREF
  struct _LUID v14[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h]
  _DWORD InBuffer[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 InBuffer_8; // [rsp+78h] [rbp-88h]
  __int128 v18; // [rsp+80h] [rbp-80h]
  __int128 v19; // [rsp+90h] [rbp-70h]
  __int64 v20; // [rsp+A0h] [rbp-60h]
  WCHAR DiskPath[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  hDevice = a1;
  if ( a3 )
  {
    *(_OWORD *)&v14[0].LowPart = 0;
    v15 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege(v14, 28);
    InBuffer_8 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    InBuffer[0] = 1;
    InBuffer[1] = a2;
    WORD3(v18) = a3;
    if ( !DeviceIoControl(hDevice, 0x2D191Cu, InBuffer, 0x38u, 0, 0, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x12E,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        v5);
    Vml::TemporaryPrivilege::~TemporaryPrivilege(v14);
  }
  else
  {
    v7 = AttachVirtualDisk(a1, 0, a2, 0, 0, 0);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x132,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        (const char *)v7,
        lpOutBuffer);
  }
  if ( (a2 & 0x40) == 0 )
  {
    v14[0] = (struct _LUID)&hDevice;
    LOBYTE(v14[1].LowPart) = 1;
    DiskPathSizeInBytes = 520;
    VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(hDevice, &DiskPathSizeInBytes, DiskPath);
    if ( VirtualDiskPhysicalPath )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        (const char *)VirtualDiskPhysicalPath,
        lpOutBuffer);
    FileW = CreateFileW(DiskPath, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
    v11 = FileW;
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x147,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        v9);
    ForceOnlineHardDisk(FileW);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
  }
}

```

## disassembly

```asm
0x1400aca18  mov     [rsp-8+arg_18], rbx
0x1400aca1d  push    rbp
0x1400aca1e  push    rsi
0x1400aca1f  push    rdi
0x1400aca20  lea     rbp, [rsp-1D0h]
0x1400aca28  sub     rsp, 2D0h
0x1400aca2f  mov     rax, cs:__security_cookie
0x1400aca36  xor     rax, rsp
0x1400aca39  mov     [rbp+1E0h+var_20], rax
0x1400aca40  movzx   edi, r8w
0x1400aca44  mov     ebx, edx
0x1400aca46  mov     [rsp+2E0h+hDevice], rcx
0x1400aca4b  xor     esi, esi
0x1400aca4d  test    r8w, r8w
0x1400aca51  jz      loc_1400ACB4D
0x1400aca57  xorps   xmm0, xmm0
0x1400aca5a  xor     eax, eax
0x1400aca5c  movups  xmmword ptr [rsp+2E0h+var_288.LowPart], xmm0
0x1400aca61  mov     [rsp+2E0h+var_278], rax
0x1400aca66  lea     edx, [rsi+1Ch]; int
0x1400aca69  lea     rcx, [rsp+2E0h+var_288]; this
0x1400aca6e  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1400aca73  nop
0x1400aca74  xorps   xmm0, xmm0
0x1400aca77  xor     eax, eax
0x1400aca79  movups  [rsp+2E0h+InBuffer], xmm0
0x1400aca7e  movups  [rbp+1E0h+var_260], xmm0
0x1400aca82  movups  [rbp+1E0h+var_250], xmm0
0x1400aca86  mov     [rbp+1E0h+var_240], rax
0x1400aca8a  mov     dword ptr [rsp+2E0h+InBuffer], 1
0x1400aca92  mov     dword ptr [rsp+2E0h+InBuffer+4], ebx
0x1400aca96  mov     word ptr [rbp+1E0h+var_260+6], di
0x1400aca9a  mov     [rsp+2E0h+lpOverlapped], rsi; lpOverlapped
0x1400aca9f  mov     [rsp+2E0h+lpBytesReturned], rsi; lpBytesReturned
0x1400acaa4  mov     [rsp+2E0h+nOutBufferSize], esi; nOutBufferSize
0x1400acaa8  mov     [rsp+2E0h+lpOutBuffer], rsi; unsigned int
0x1400acaad  lea     r9d, [rsi+38h]; nInBufferSize
0x1400acab1  lea     r8, [rsp+2E0h+InBuffer]; lpInBuffer
0x1400acab6  mov     edx, 2D191Ch; dwIoControlCode
0x1400acabb  mov     rcx, [rsp+2E0h+hDevice]; hDevice
0x1400acac0  call    cs:__imp_DeviceIoControl
0x1400acac7  nop     dword ptr [rax+rax+00h]
0x1400acacc  mov     rcx, [rbp+1E8h]; this
0x1400acad3  test    eax, eax
0x1400acad5  jnz     short loc_1400ACAE9
0x1400acad7  lea     r8, aOnecoreVmCompu_100; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400acade  mov     edx, 12Eh; void *
0x1400acae3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400acae9  lea     rcx, [rsp+2E0h+var_288]; this
0x1400acaee  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x1400acaf3  test    bl, 40h
0x1400acaf6  jnz     loc_1400ACC03
0x1400acafc  lea     rax, [rsp+2E0h+hDevice]
0x1400acb01  mov     qword ptr [rsp+2E0h+var_288.LowPart], rax
0x1400acb06  mov     byte ptr [rsp+2E0h+var_288.LowPart+8], 1
0x1400acb0b  mov     [rsp+2E0h+DiskPathSizeInBytes], 208h
0x1400acb13  lea     r8, [rbp+1E0h+DiskPath]; DiskPath
0x1400acb17  lea     rdx, [rsp+2E0h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x1400acb1c  mov     rcx, [rsp+2E0h+hDevice]; VirtualDiskHandle
0x1400acb21  call    cs:__imp_GetVirtualDiskPhysicalPath
0x1400acb28  nop     dword ptr [rax+rax+00h]
0x1400acb2d  mov     rcx, [rbp+1E8h]; this
0x1400acb34  test    eax, eax
0x1400acb36  jz      short loc_1400ACB8F
0x1400acb38  mov     r9d, eax; char *
0x1400acb3b  lea     r8, aOnecoreVmCompu_100; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400acb42  mov     edx, 13Ch; void *
0x1400acb47  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400acb4d  mov     qword ptr [rsp+2E0h+nOutBufferSize], rsi; Overlapped
0x1400acb52  mov     [rsp+2E0h+lpOutBuffer], rsi; unsigned int
0x1400acb57  xor     r9d, r9d; ProviderSpecificFlags
0x1400acb5a  mov     r8d, ebx; Flags
0x1400acb5d  xor     edx, edx; SecurityDescriptor
0x1400acb5f  call    cs:__imp_AttachVirtualDisk
0x1400acb66  nop     dword ptr [rax+rax+00h]
0x1400acb6b  mov     rcx, [rbp+1E8h]; this
0x1400acb72  test    eax, eax
0x1400acb74  jz      loc_1400ACAF3
0x1400acb7a  mov     r9d, eax; char *
0x1400acb7d  lea     r8, aOnecoreVmCompu_100; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400acb84  mov     edx, 132h; void *
0x1400acb89  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400acb8f  mov     [rsp+2E0h+lpBytesReturned], rsi; hTemplateFile
0x1400acb94  mov     [rsp+2E0h+nOutBufferSize], 20000080h; dwFlagsAndAttributes
0x1400acb9c  mov     r8d, 3; dwShareMode
0x1400acba2  mov     dword ptr [rsp+2E0h+lpOutBuffer], r8d; dwCreationDisposition
0x1400acba7  xor     r9d, r9d; lpSecurityAttributes
0x1400acbaa  mov     edx, 0C0000000h; dwDesiredAccess
0x1400acbaf  lea     rcx, [rbp+1E0h+DiskPath]; lpFileName
0x1400acbb3  call    cs:__imp_CreateFileW
0x1400acbba  nop     dword ptr [rax+rax+00h]
0x1400acbbf  mov     [rsp+2E0h+var_2A0], rax
0x1400acbc4  lea     rcx, [rax+1]
0x1400acbc8  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1400acbcf  setz    dl
0x1400acbd2  mov     rcx, [rbp+1E8h]; this
0x1400acbd9  test    dl, dl
0x1400acbdb  jz      short loc_1400ACBEF
0x1400acbdd  lea     r8, aOnecoreVmCompu_100; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400acbe4  mov     edx, 147h; void *
0x1400acbe9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400acbef  mov     rcx, rax; void *
0x1400acbf2  call    ?ForceOnlineHardDisk@@YAXPEAX@Z; ForceOnlineHardDisk(void *)
0x1400acbf7  nop
0x1400acbf8  lea     rcx, [rsp+2E0h+var_2A0]; void *
0x1400acbfd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400acc02  nop
0x1400acc03  mov     rcx, [rbp+1E0h+var_20]
0x1400acc0a  xor     rcx, rsp; StackCookie
0x1400acc0d  call    __security_check_cookie
0x1400acc12  mov     rbx, [rsp+2E0h+arg_18]
0x1400acc1a  add     rsp, 2D0h
0x1400acc21  pop     rdi
0x1400acc22  pop     rsi
0x1400acc23  pop     rbp
0x1400acc24  retn
```
