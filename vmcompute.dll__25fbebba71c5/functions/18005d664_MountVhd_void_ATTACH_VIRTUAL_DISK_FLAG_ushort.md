# MountVhd(void *,_ATTACH_VIRTUAL_DISK_FLAG,ushort)

- ea: `0x18005d664`
- end: `0x18005d88b`
- name: `?MountVhd@@YAXPEAXW4_ATTACH_VIRTUAL_DISK_FLAG@@G@Z`
- size: `551`
- prototype: `void(void *, enum _ATTACH_VIRTUAL_DISK_FLAG, unsigned __int16)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002ee84`
- `0x180030fb0`
- `0x1800310e0`
- `0x1800369c0`
- `0x18005ca68`

## callees

- `0x180002f50`
- `0x18000d0ec`
- `0x180022d10`
- `0x18002e454`
- `0x18002eb7c`
- `0x18005d664`
- `0x18005fcc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d7df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d7df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005d79e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005d79e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005d70c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005d70c`
- `VirtDisk!AttachVirtualDisk` at `0x18005d821`
- `VirtDisk!AttachVirtualDisk` at `0x18005d821`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x18005d75f`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x18005d75f`

## string_xrefs

- `0x18005d83d`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x18005d852`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x18005d864`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`
- `0x18005d879`: `onecore\vm\compute\shared\storage\vhdutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall MountVhd(void *a1, ATTACH_VIRTUAL_DISK_FLAG a2, __int16 a3)
{
  const char *v5; // r9
  DWORD VirtualDiskPhysicalPath; // eax
  char *FileW; // rbx
  const char *v8; // r9
  DWORD v9; // eax
  unsigned int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  HANDLE hDevice; // [rsp+48h] [rbp-B8h] BYREF
  ULONG DiskPathSizeInBytes; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v13; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v14; // [rsp+68h] [rbp-98h]
  _DWORD InBuffer[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 InBuffer_8; // [rsp+78h] [rbp-88h]
  __int128 v17; // [rsp+80h] [rbp-80h]
  __int128 v18; // [rsp+90h] [rbp-70h]
  __int64 v19; // [rsp+A0h] [rbp-60h]
  WCHAR DiskPath[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  hDevice = a1;
  if ( a3 )
  {
    v13 = 0;
    v14 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v13, 28);
    InBuffer_8 = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    InBuffer[0] = 1;
    InBuffer[1] = a2;
    WORD3(v17) = a3;
    if ( !DeviceIoControl(hDevice, 0x2D191Cu, InBuffer, 0x38u, 0, 0, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x12E,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        v5);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v13);
  }
  else
  {
    v9 = AttachVirtualDisk(a1, 0, a2, 0, 0, 0);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x132,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        (const char *)v9,
        lpOutBuffer);
  }
  if ( (a2 & 0x40) == 0 )
  {
    *(_QWORD *)&v13 = &hDevice;
    BYTE8(v13) = 1;
    DiskPathSizeInBytes = 520;
    VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(hDevice, &DiskPathSizeInBytes, DiskPath);
    if ( VirtualDiskPhysicalPath )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        (const char *)VirtualDiskPhysicalPath,
        lpOutBuffer);
    FileW = (char *)CreateFileW(DiskPath, 0xC0000000, 3u, 0, 3u, 0x20000080u, 0);
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x147,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\vhdutilities.cpp",
        v8);
    ForceOnlineHardDisk(FileW);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
  }
}

```

## disassembly

```asm
0x18005d664  mov     [rsp-8+arg_18], rbx
0x18005d669  push    rbp
0x18005d66a  push    rsi
0x18005d66b  push    rdi
0x18005d66c  lea     rbp, [rsp-1D0h]
0x18005d674  sub     rsp, 2D0h
0x18005d67b  mov     rax, cs:__security_cookie
0x18005d682  xor     rax, rsp
0x18005d685  mov     [rbp+1E0h+var_20], rax
0x18005d68c  movzx   edi, r8w
0x18005d690  mov     ebx, edx
0x18005d692  mov     [rsp+2E0h+hDevice], rcx
0x18005d697  xor     esi, esi
0x18005d699  test    r8w, r8w
0x18005d69d  jz      loc_18005D80F
0x18005d6a3  xorps   xmm0, xmm0
0x18005d6a6  xor     eax, eax
0x18005d6a8  movups  [rsp+2E0h+var_288], xmm0
0x18005d6ad  mov     [rsp+2E0h+var_278], rax
0x18005d6b2  lea     edx, [rsi+1Ch]; int
0x18005d6b5  lea     rcx, [rsp+2E0h+var_288]; this
0x18005d6ba  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18005d6bf  nop
0x18005d6c0  xorps   xmm0, xmm0
0x18005d6c3  xor     eax, eax
0x18005d6c5  movups  [rsp+2E0h+InBuffer], xmm0
0x18005d6ca  movups  [rbp+1E0h+var_260], xmm0
0x18005d6ce  movups  [rbp+1E0h+var_250], xmm0
0x18005d6d2  mov     [rbp+1E0h+var_240], rax
0x18005d6d6  mov     dword ptr [rsp+2E0h+InBuffer], 1
0x18005d6de  mov     dword ptr [rsp+2E0h+InBuffer+4], ebx
0x18005d6e2  mov     word ptr [rbp+1E0h+var_260+6], di
0x18005d6e6  mov     [rsp+2E0h+lpOverlapped], rsi; lpOverlapped
0x18005d6eb  mov     [rsp+2E0h+lpBytesReturned], rsi; lpBytesReturned
0x18005d6f0  mov     [rsp+2E0h+nOutBufferSize], esi; nOutBufferSize
0x18005d6f4  mov     [rsp+2E0h+lpOutBuffer], rsi; unsigned int
0x18005d6f9  lea     r9d, [rsi+38h]; nInBufferSize
0x18005d6fd  lea     r8, [rsp+2E0h+InBuffer]; lpInBuffer
0x18005d702  mov     edx, 2D191Ch; dwIoControlCode
0x18005d707  mov     rcx, [rsp+2E0h+hDevice]; hDevice
0x18005d70c  call    cs:__imp_DeviceIoControl
0x18005d713  nop     dword ptr [rax+rax+00h]
0x18005d718  mov     rcx, [rbp+1E8h]; this
0x18005d71f  test    eax, eax
0x18005d721  jz      loc_18005D864
0x18005d727  lea     rcx, [rsp+2E0h+var_288]; this
0x18005d72c  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18005d731  test    bl, 40h
0x18005d734  jnz     loc_18005D7EC
0x18005d73a  lea     rax, [rsp+2E0h+hDevice]
0x18005d73f  mov     qword ptr [rsp+2E0h+var_288], rax
0x18005d744  mov     byte ptr [rsp+2E0h+var_288+8], 1
0x18005d749  mov     [rsp+2E0h+DiskPathSizeInBytes], 208h
0x18005d751  lea     r8, [rbp+1E0h+DiskPath]; DiskPath
0x18005d755  lea     rdx, [rsp+2E0h+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x18005d75a  mov     rcx, [rsp+2E0h+hDevice]; VirtualDiskHandle
0x18005d75f  call    cs:__imp_GetVirtualDiskPhysicalPath
0x18005d766  nop     dword ptr [rax+rax+00h]
0x18005d76b  mov     rcx, [rbp+1E8h]; this
0x18005d772  test    eax, eax
0x18005d774  jnz     loc_18005D876
0x18005d77a  mov     [rsp+2E0h+lpBytesReturned], rsi; hTemplateFile
0x18005d77f  mov     [rsp+2E0h+nOutBufferSize], 20000080h; dwFlagsAndAttributes
0x18005d787  mov     r8d, 3; dwShareMode
0x18005d78d  mov     dword ptr [rsp+2E0h+lpOutBuffer], r8d; dwCreationDisposition
0x18005d792  xor     r9d, r9d; lpSecurityAttributes
0x18005d795  mov     edx, 0C0000000h; dwDesiredAccess
0x18005d79a  lea     rcx, [rbp+1E0h+DiskPath]; lpFileName
0x18005d79e  call    cs:__imp_CreateFileW
0x18005d7a5  nop     dword ptr [rax+rax+00h]
0x18005d7aa  mov     rbx, rax
0x18005d7ad  mov     [rsp+2E0h+var_2A0], rax
0x18005d7b2  inc     rax
0x18005d7b5  test    rax, 0FFFFFFFFFFFFFFFEh
0x18005d7bb  setz    al
0x18005d7be  mov     rcx, [rbp+1E8h]; this
0x18005d7c5  test    al, al
0x18005d7c7  jnz     short loc_18005D83D
0x18005d7c9  mov     rcx, rbx; void *
0x18005d7cc  call    ?ForceOnlineHardDisk@@YAXPEAX@Z; ForceOnlineHardDisk(void *)
0x18005d7d1  nop
0x18005d7d2  lea     rax, [rbx-1]
0x18005d7d6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005d7da  ja      short loc_18005D7EC
0x18005d7dc  mov     rcx, rbx; hObject
0x18005d7df  call    cs:__imp_CloseHandle
0x18005d7e6  nop     dword ptr [rax+rax+00h]
0x18005d7eb  nop
0x18005d7ec  mov     rcx, [rbp+1E0h+var_20]
0x18005d7f3  xor     rcx, rsp; StackCookie
0x18005d7f6  call    __security_check_cookie
0x18005d7fb  mov     rbx, [rsp+2E0h+arg_18]
0x18005d803  add     rsp, 2D0h
0x18005d80a  pop     rdi
0x18005d80b  pop     rsi
0x18005d80c  pop     rbp
0x18005d80d  retn
0x18005d80f  mov     qword ptr [rsp+2E0h+nOutBufferSize], rsi; Overlapped
0x18005d814  mov     [rsp+2E0h+lpOutBuffer], rsi; unsigned int
0x18005d819  xor     r9d, r9d; ProviderSpecificFlags
0x18005d81c  mov     r8d, ebx; Flags
0x18005d81f  xor     edx, edx; SecurityDescriptor
0x18005d821  call    cs:__imp_AttachVirtualDisk
0x18005d828  nop     dword ptr [rax+rax+00h]
0x18005d82d  mov     rcx, [rbp+1E8h]; this
0x18005d834  test    eax, eax
0x18005d836  jnz     short loc_18005D84F
0x18005d838  jmp     loc_18005D731
0x18005d83d  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005d844  mov     edx, 147h; void *
0x18005d849  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005d84f  mov     r9d, eax; char *
0x18005d852  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005d859  mov     edx, 132h; void *
0x18005d85e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005d864  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005d86b  mov     edx, 12Eh; void *
0x18005d870  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005d876  mov     r9d, eax; char *
0x18005d879  lea     r8, aOnecoreVmCompu_19; "onecore\\vm\\compute\\shared\\storage\\"...
0x18005d880  mov     edx, 13Ch; void *
0x18005d885  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
