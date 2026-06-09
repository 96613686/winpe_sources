# ComputeService::Management::VmHostedContainer::OfflineVolume(ushort const *)

- ea: `0x1400af194`
- end: `0x1400af28e`
- name: `?OfflineVolume@VmHostedContainer@Management@ComputeService@@YAXPEBG@Z`
- size: `250`
- prototype: `void __fastcall(ComputeService::Management::VmHostedContainer *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14009b370`
- `0x1400a1224`
- `0x1400a13a8`

## callees

- `0x140005360`
- `0x14000ddac`
- `0x140041564`
- `0x1400af194`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400af261`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400af261`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400af1cd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400af1cd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400af245`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400af245`

## string_xrefs

- `0x1400af1fa`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerstorage.cpp`
- `0x1400af27b`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostedcontainerstorage.cpp`
- `0x1400af1ea`: `Failed to open scratch volume`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeService::Management::VmHostedContainer::OfflineVolume(
        const WCHAR *this,
        const unsigned __int16 *a2)
{
  char *FileW; // rax
  char *v3; // rbx
  const char *v4; // r9
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-40h]
  DWORD BytesReturned; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  FileW = (char *)CreateFileW(this, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  try
  {
    v3 = FileW;
    wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
      retaddr,
      (void *)0x127,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerstorage.cpp",
      (const char *)((unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL),
      (bool)"Failed to open scratch volume",
      dwFlagsAndAttributes);
    BytesReturned = 0;
    if ( !DeviceIoControl(v3, 0x90020u, 0, 0, 0, 0, &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x132,
        (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerstorage.cpp",
        v4);
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v3);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x134,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostedcontainerstorage.cpp",
      v4);
  }
}

```

## disassembly

```asm
0x1400af194  push    rbx
0x1400af196  sub     rsp, 60h
0x1400af19a  mov     rax, cs:__security_cookie
0x1400af1a1  xor     rax, rsp
0x1400af1a4  mov     [rsp+68h+var_18], rax
0x1400af1a9  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1400af1b2  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 80h; char *
0x1400af1ba  mov     r8d, 3; dwShareMode
0x1400af1c0  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400af1c5  xor     r9d, r9d; lpSecurityAttributes
0x1400af1c8  mov     edx, 0C0000000h; dwDesiredAccess
0x1400af1cd  call    cs:__imp_CreateFileW
0x1400af1d3  mov     rbx, rax
0x1400af1d6  mov     [rsp+68h+var_28], rax
0x1400af1db  dec     rax
0x1400af1de  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400af1e2  setbe   al
0x1400af1e5  mov     rcx, [rsp+68h]; this
0x1400af1ea  lea     rdx, aFailedToOpenSc; "Failed to open scratch volume"
0x1400af1f1  mov     qword ptr [rsp+68h+dwCreationDisposition], rdx; bool
0x1400af1f6  movzx   r9d, al; char *
0x1400af1fa  lea     r8, aOnecoreVmCompu_53; "onecore\\vm\\compute\\management\\orche"...
0x1400af201  mov     edx, 127h; void *
0x1400af206  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x1400af20b  mov     [rsp+68h+BytesReturned], 0
0x1400af213  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1400af21c  lea     rax, [rsp+68h+BytesReturned]
0x1400af221  mov     [rsp+68h+hTemplateFile], rax; lpBytesReturned
0x1400af226  mov     dword ptr [rsp+68h+dwFlagsAndAttributes], 0; nOutBufferSize
0x1400af22e  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOutBuffer
0x1400af237  xor     r9d, r9d; nInBufferSize
0x1400af23a  xor     r8d, r8d; lpInBuffer
0x1400af23d  mov     edx, 90020h; dwIoControlCode
0x1400af242  mov     rcx, rbx; hDevice
0x1400af245  call    cs:__imp_DeviceIoControl
0x1400af24b  mov     rcx, [rsp+68h]; this
0x1400af250  test    eax, eax
0x1400af252  jz      short loc_1400AF27B
0x1400af254  lea     rax, [rbx-1]
0x1400af258  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400af25c  ja      short loc_1400AF268
0x1400af25e  mov     rcx, rbx; hObject
0x1400af261  call    cs:__imp_CloseHandle
0x1400af267  nop
0x1400af268  mov     rcx, [rsp+68h+var_18]
0x1400af26d  xor     rcx, rsp; StackCookie
0x1400af270  call    __security_check_cookie
0x1400af275  add     rsp, 60h
0x1400af279  pop     rbx
0x1400af27a  retn
0x1400af27b  lea     r8, aOnecoreVmCompu_53; "onecore\\vm\\compute\\management\\orche"...
0x1400af282  mov     edx, 132h; void *
0x1400af287  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
