# WsInformVirtualDiskHandlers

- ea: `0x18002ec48`
- end: `0x18002ed83`
- name: `WsInformVirtualDiskHandlers`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18002ee64`

## callees

- `0x18002ec48`

## import_xrefs

- `ntdll!DbgPrint` at `0x18002ed4d`
- `ntdll!DbgPrint` at `0x18002ed4d`
- `ntdll!NtDeviceIoControlFile` at `0x18002ed17`
- `ntdll!NtDeviceIoControlFile` at `0x18002ed17`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ed30`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ed30`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ec6d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ec6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ed5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ed6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ed5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ed6b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ecb0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002ecb0`

## pseudocode

```c
int WsInformVirtualDiskHandlers()
{
  HANDLE EventW; // rax
  void *v1; // rbx
  HANDLE FileW; // rax
  void *v3; // rdi
  NTSTATUS Status; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  __int64 InputBuffer; // [rsp+70h] [rbp+8h] BYREF

  InputBuffer = 0;
  IoStatusBlock = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v1 = EventW;
  if ( EventW )
  {
    FileW = CreateFileW(L"\\\\.\\VDRVROOT", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
    v3 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      InputBuffer = 0x100000001LL;
      Status = NtDeviceIoControlFile(FileW, v1, 0, 0, &IoStatusBlock, 0x2D9938u, &InputBuffer, 8u, 0, 0);
      if ( Status == 259 )
      {
        WaitForSingleObject(v1, 0xFFFFFFFF);
        Status = IoStatusBlock.Status;
      }
      if ( Status < 0 )
        DbgPrint("WKSSVC IOCTL to vdrvroot returned 0x%lx\n", Status);
      CloseHandle(v3);
    }
    LODWORD(EventW) = CloseHandle(v1);
  }
  return (int)EventW;
}

```

## disassembly

```asm
0x18002ec48  mov     [rsp+arg_8], rbx
0x18002ec4d  push    rdi
0x18002ec4e  sub     rsp, 60h
0x18002ec52  xorps   xmm0, xmm0
0x18002ec55  mov     [rsp+68h+InputBuffer], 0
0x18002ec5e  xor     r9d, r9d; lpName
0x18002ec61  xor     r8d, r8d; bInitialState
0x18002ec64  xor     edx, edx; bManualReset
0x18002ec66  xor     ecx, ecx; lpEventAttributes
0x18002ec68  movups  xmmword ptr [rsp+68h+IoStatusBlock], xmm0
0x18002ec6d  call    cs:__imp_CreateEventW
0x18002ec74  nop     dword ptr [rax+rax+00h]
0x18002ec79  mov     rbx, rax
0x18002ec7c  test    rax, rax
0x18002ec7f  jz      loc_18002ED77
0x18002ec85  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18002ec8e  lea     rcx, FileName; "\\\\.\\VDRVROOT"
0x18002ec95  mov     r8d, 3; dwShareMode
0x18002ec9b  mov     [rsp+68h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18002eca3  xor     r9d, r9d; lpSecurityAttributes
0x18002eca6  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002ecab  mov     edx, 0C0000000h; dwDesiredAccess
0x18002ecb0  call    cs:__imp_CreateFileW
0x18002ecb7  nop     dword ptr [rax+rax+00h]
0x18002ecbc  mov     rdi, rax
0x18002ecbf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ecc3  jz      loc_18002ED68
0x18002ecc9  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x18002ecd1  mov     eax, 1
0x18002ecd6  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x18002ecdf  xor     r9d, r9d; ApcContext
0x18002ece2  mov     dword ptr [rsp+68h+InputBuffer], eax
0x18002ece6  xor     r8d, r8d; ApcRoutine
0x18002ece9  mov     dword ptr [rsp+68h+InputBuffer+4], eax
0x18002eced  mov     rdx, rbx; Event
0x18002ecf0  mov     [rsp+68h+InputBufferLength], 8; InputBufferLength
0x18002ecf8  lea     rax, [rsp+68h+InputBuffer]
0x18002ecfd  mov     [rsp+68h+hTemplateFile], rax; InputBuffer
0x18002ed02  mov     rcx, rdi; FileHandle
0x18002ed05  lea     rax, [rsp+68h+IoStatusBlock]
0x18002ed0a  mov     [rsp+68h+dwFlagsAndAttributes], 2D9938h; IoControlCode
0x18002ed12  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; IoStatusBlock
0x18002ed17  call    cs:__imp_NtDeviceIoControlFile
0x18002ed1e  nop     dword ptr [rax+rax+00h]
0x18002ed23  cmp     eax, 103h
0x18002ed28  jnz     short loc_18002ED40
0x18002ed2a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002ed2d  mov     rcx, rbx; hHandle
0x18002ed30  call    cs:__imp_WaitForSingleObject
0x18002ed37  nop     dword ptr [rax+rax+00h]
0x18002ed3c  mov     eax, dword ptr [rsp+68h+IoStatusBlock]
0x18002ed40  test    eax, eax
0x18002ed42  jns     short loc_18002ED59
0x18002ed44  mov     edx, eax
0x18002ed46  lea     rcx, aWkssvcIoctlToV; "WKSSVC IOCTL to vdrvroot returned 0x%lx"...
0x18002ed4d  call    cs:__imp_DbgPrint
0x18002ed54  nop     dword ptr [rax+rax+00h]
0x18002ed59  mov     rcx, rdi; hObject
0x18002ed5c  call    cs:__imp_CloseHandle
0x18002ed63  nop     dword ptr [rax+rax+00h]
0x18002ed68  mov     rcx, rbx; hObject
0x18002ed6b  call    cs:__imp_CloseHandle
0x18002ed72  nop     dword ptr [rax+rax+00h]
0x18002ed77  mov     rbx, [rsp+68h+arg_8]
0x18002ed7c  add     rsp, 60h
0x18002ed80  pop     rdi
0x18002ed81  retn
```
