# ComputeService::Management::VmHostedContainer::Details::OpenDiskByLun(uint)

- ea: `0x1400af294`
- end: `0x1400af50a`
- name: `?OpenDiskByLun@Details@VmHostedContainer@Management@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@I@Z`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400af510`

## callees

- `0x140005360`
- `0x1400056c4`
- `0x14000ddac`
- `0x14000ea60`
- `0x140040e24`
- `0x140040ff8`
- `0x1400af010`
- `0x1400af294`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400af430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400af430`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400af3e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400af3e1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400af3bc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400af3bc`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400af31c`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400af31c`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400af422`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400af422`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1400af49a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1400af49a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1400af2d4`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1400af2d4`

## string_xrefs

- `0x1400af4bf`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerstorage.cpp`
- `0x1400af4d1`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerstorage.cpp`
- `0x1400af4e3`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerstorage.cpp`
- `0x1400af4f5`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerstorage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HANDLE *__fastcall ComputeService::Management::VmHostedContainer::Details::OpenDiskByLun(HANDLE *a1, int a2)
{
  char *DeviceInfoList; // rbx
  const char *v5; // r9
  const char *v6; // r9
  unsigned int v7; // esi
  __int64 i; // r9
  unsigned __int64 v9; // rdx
  const char *v10; // r9
  signed int LastError; // eax
  unsigned __int64 v12; // r9
  unsigned __int64 v13; // rdx
  bool v14; // cc
  HANDLE hDevice; // [rsp+40h] [rbp-39h] BYREF
  void *v17[3]; // [rsp+48h] [rbp-31h] BYREF
  DWORD BytesReturned[2]; // [rsp+60h] [rbp-19h] BYREF
  HANDLE *OutBuffer; // [rsp+68h] [rbp-11h] BYREF
  int v20[4]; // [rsp+70h] [rbp-9h] BYREF
  __int128 v21; // [rsp+80h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  OutBuffer = a1;
  DeviceInfoList = (char *)DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v17[2] = DeviceInfoList;
  if ( (unsigned __int64)(DeviceInfoList - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerstorage.cpp",
      v5);
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_DISK, 0, 18, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerstorage.cpp",
      v6);
  v7 = 0;
  for ( i = 0; ; i = v7 )
  {
    *(_OWORD *)v20 = 0;
    v21 = 0;
    v20[0] = 32;
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(DeviceInfoList, 0, &GUID_DEVINTERFACE_DISK, i) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      else
        v12 = (unsigned int)LastError;
      if ( LastError != 259 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerstorage.cpp",
          (const char *)v12,
          (int)v20);
      *a1 = (HANDLE)-1LL;
      v14 = (unsigned __int64)(DeviceInfoList - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
      goto LABEL_20;
    }
    *(_QWORD *)BytesReturned = 0;
    v17[0] = 0;
    ComputeService::Management::VmHostedContainer::Details::GetInterfaceDetailData(
      v17,
      DeviceInfoList,
      v20,
      BytesReturned);
    hDevice = 0;
    GetDiskHandle(&hDevice, *(_QWORD *)BytesReturned + 4LL);
    OutBuffer = 0;
    BytesReturned[0] = 0;
    if ( !DeviceIoControl(hDevice, 0x41018u, 0, 0, &OutBuffer, 8u, BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerstorage.cpp",
        v10);
    if ( HIBYTE(OutBuffer) == a2 )
      break;
    if ( (char *)hDevice - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hDevice);
    if ( v17[0] )
      operator delete(v17[0], v9);
    ++v7;
  }
  ForceOnlineHardDisk(hDevice);
  *a1 = hDevice;
  hDevice = (HANDLE)-1LL;
  if ( v17[0] )
    operator delete(v17[0], v13);
  v14 = (unsigned __int64)(DeviceInfoList - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_20:
  if ( v14 )
    DevObjDestroyDeviceInfoList(DeviceInfoList);
  return a1;
}

```

## disassembly

```asm
0x1400af294  push    rbp
0x1400af296  push    rbx
0x1400af297  push    rsi
0x1400af298  push    rdi
0x1400af299  push    r14
0x1400af29b  push    r15
0x1400af29d  lea     rbp, [rsp-2Fh]
0x1400af2a2  sub     rsp, 0A8h
0x1400af2a9  mov     rax, cs:__security_cookie
0x1400af2b0  xor     rax, rsp
0x1400af2b3  mov     [rbp+57h+var_40], rax
0x1400af2b7  mov     r15d, edx
0x1400af2ba  mov     rdi, rcx
0x1400af2bd  mov     [rbp+57h+OutBuffer], rcx
0x1400af2c1  mov     [rsp+0D0h+lpOutBuffer], 0
0x1400af2ca  xor     r9d, r9d
0x1400af2cd  xor     r8d, r8d
0x1400af2d0  xor     edx, edx
0x1400af2d2  xor     ecx, ecx
0x1400af2d4  call    cs:__imp_DevObjCreateDeviceInfoList
0x1400af2da  mov     rbx, rax
0x1400af2dd  mov     [rbp+57h+var_78], rax
0x1400af2e1  dec     rax
0x1400af2e4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400af2e8  setbe   al
0x1400af2eb  mov     rcx, [rbp+5Fh]; this
0x1400af2ef  test    al, al
0x1400af2f1  jz      loc_1400AF4D1
0x1400af2f7  mov     qword ptr [rsp+0D0h+nOutBufferSize], 0
0x1400af300  mov     [rsp+0D0h+lpOutBuffer], 0
0x1400af309  mov     r9d, 12h
0x1400af30f  xor     r8d, r8d
0x1400af312  lea     rdx, GUID_DEVINTERFACE_DISK
0x1400af319  mov     rcx, rbx
0x1400af31c  call    cs:__imp_DevObjGetClassDevs
0x1400af322  mov     rcx, [rbp+5Fh]; this
0x1400af326  test    eax, eax
0x1400af328  jz      loc_1400AF4E3
0x1400af32e  xor     esi, esi
0x1400af330  xor     r9d, r9d
0x1400af333  jmp     loc_1400AF3FB
0x1400af338  mov     qword ptr [rbp+57h+BytesReturned], 0
0x1400af340  mov     [rbp+57h+var_88], 0
0x1400af348  lea     r9, [rbp+57h+BytesReturned]
0x1400af34c  lea     r8, [rbp+57h+var_60]
0x1400af350  mov     rdx, rbx
0x1400af353  lea     rcx, [rbp+57h+var_88]
0x1400af357  call    ?GetInterfaceDetailData@Details@VmHostedContainer@Management@ComputeService@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@PEAXPEAU_DO_DEVICE_INTERFACE_DATA@@PEAPEAU_DO_DEVICE_INTERFACE_DETAIL_DATA@@PEAU_DO_DEVINFO_DATA@@@Z; ComputeService::Management::VmHostedContainer::Details::GetInterfaceDetailData(void *,_DO_DEVICE_INTERFACE_DATA *,_DO_DEVICE_INTERFACE_DETAIL_DATA * *,_DO_DEVINFO_DATA *)
0x1400af35c  nop
0x1400af35d  mov     [rbp+57h+hDevice], 0
0x1400af365  mov     rdx, qword ptr [rbp+57h+BytesReturned]
0x1400af369  add     rdx, 4
0x1400af36d  lea     rcx, [rbp+57h+hDevice]
0x1400af371  call    ?GetDiskHandle@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBG@Z; GetDiskHandle(ushort const *)
0x1400af376  nop
0x1400af377  mov     [rbp+57h+OutBuffer], 0
0x1400af37f  mov     [rbp+57h+BytesReturned], 0
0x1400af386  mov     r14, [rbp+5Fh]
0x1400af38a  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x1400af393  lea     rax, [rbp+57h+BytesReturned]
0x1400af397  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x1400af39c  mov     [rsp+0D0h+nOutBufferSize], 8; nOutBufferSize
0x1400af3a4  lea     rax, [rbp+57h+OutBuffer]
0x1400af3a8  mov     [rsp+0D0h+lpOutBuffer], rax; lpOutBuffer
0x1400af3ad  xor     r9d, r9d; nInBufferSize
0x1400af3b0  xor     r8d, r8d; lpInBuffer
0x1400af3b3  mov     edx, 41018h; dwIoControlCode
0x1400af3b8  mov     rcx, [rbp+57h+hDevice]; hDevice
0x1400af3bc  call    cs:__imp_DeviceIoControl
0x1400af3c2  test    eax, eax
0x1400af3c4  jz      loc_1400AF4F5
0x1400af3ca  movzx   eax, byte ptr [rbp+57h+OutBuffer+7]
0x1400af3ce  cmp     eax, r15d
0x1400af3d1  jz      short loc_1400AF43F
0x1400af3d3  mov     rcx, [rbp+57h+hDevice]; hObject
0x1400af3d7  lea     rax, [rcx-1]
0x1400af3db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400af3df  ja      short loc_1400AF3E8
0x1400af3e1  call    cs:__imp_CloseHandle
0x1400af3e7  nop
0x1400af3e8  mov     rcx, [rbp+57h+var_88]; void *
0x1400af3ec  test    rcx, rcx
0x1400af3ef  jz      short loc_1400AF3F6
0x1400af3f1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400af3f6  inc     esi
0x1400af3f8  mov     r9d, esi
0x1400af3fb  xorps   xmm0, xmm0
0x1400af3fe  lea     rax, [rbp+57h+var_60]
0x1400af402  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1400af406  mov     [rsp+0D0h+lpOutBuffer], rax; int
0x1400af40b  movups  [rbp+57h+var_50], xmm0
0x1400af40f  mov     [rbp+57h+var_60], 20h ; ' '
0x1400af416  lea     r8, GUID_DEVINTERFACE_DISK
0x1400af41d  xor     edx, edx
0x1400af41f  mov     rcx, rbx
0x1400af422  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1400af428  test    eax, eax
0x1400af42a  jnz     loc_1400AF338
0x1400af430  call    cs:__imp_GetLastError
0x1400af436  test    eax, eax
0x1400af438  jg      short loc_1400AF470
0x1400af43a  mov     r9d, eax
0x1400af43d  jmp     short loc_1400AF47B
0x1400af43f  mov     rcx, [rbp+57h+hDevice]; void *
0x1400af443  call    ?ForceOnlineHardDisk@@YAXPEAX@Z; ForceOnlineHardDisk(void *)
0x1400af448  mov     rax, [rbp+57h+hDevice]
0x1400af44c  mov     [rdi], rax
0x1400af44f  mov     [rbp+57h+hDevice], 0FFFFFFFFFFFFFFFFh
0x1400af457  mov     rcx, [rbp+57h+var_88]; void *
0x1400af45b  test    rcx, rcx
0x1400af45e  jz      short loc_1400AF466
0x1400af460  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400af465  nop
0x1400af466  lea     rax, [rbx-1]
0x1400af46a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400af46e  jmp     short loc_1400AF495
0x1400af470  movzx   r9d, ax
0x1400af474  or      r9d, 80070000h; char *
0x1400af47b  mov     rcx, [rbp+5Fh]; this
0x1400af47f  cmp     eax, 103h
0x1400af484  jnz     short loc_1400AF4BF
0x1400af486  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1400af48d  lea     rcx, [rbx-1]
0x1400af491  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1400af495  ja      short loc_1400AF4A0
0x1400af497  mov     rcx, rbx
0x1400af49a  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1400af4a0  mov     rax, rdi
0x1400af4a3  mov     rcx, [rbp+57h+var_40]
0x1400af4a7  xor     rcx, rsp; StackCookie
0x1400af4aa  call    __security_check_cookie
0x1400af4af  add     rsp, 0A8h
0x1400af4b6  pop     r15
0x1400af4b8  pop     r14
0x1400af4ba  pop     rdi
0x1400af4bb  pop     rsi
0x1400af4bc  pop     rbx
0x1400af4bd  pop     rbp
0x1400af4be  retn
0x1400af4bf  lea     r8, aOnecoreVmCompu_53; "onecore\\vm\\compute\\management\\orche"...
0x1400af4c6  mov     edx, 0A9h; void *
0x1400af4cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400af4d1  lea     r8, aOnecoreVmCompu_53; "onecore\\vm\\compute\\management\\orche"...
0x1400af4d8  mov     edx, 90h; void *
0x1400af4dd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400af4e3  lea     r8, aOnecoreVmCompu_53; "onecore\\vm\\compute\\management\\orche"...
0x1400af4ea  mov     edx, 98h; void *
0x1400af4ef  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400af4f5  lea     r8, aOnecoreVmCompu_53; "onecore\\vm\\compute\\management\\orche"...
0x1400af4fc  mov     edx, 79h ; 'y'; void *
0x1400af501  mov     rcx, r14; this
0x1400af504  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
