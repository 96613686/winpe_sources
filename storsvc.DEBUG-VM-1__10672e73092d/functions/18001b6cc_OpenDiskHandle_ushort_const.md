# OpenDiskHandle(ushort const *)

- ea: `0x18001b6cc`
- end: `0x18001b7ce`
- name: `?OpenDiskHandle@@YAPEAXPEBG@Z`
- size: `258`
- prototype: `void *__fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001b164`
- `0x18001b5cc`
- `0x18001bb98`
- `0x18001bd98`
- `0x180020a8c`

## callees

- `0x18000d030`
- `0x180012ce0`
- `0x18001b6cc`
- `0x18001b7d4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b7a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b7a4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001b748`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001b748`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b798`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b798`

## pseudocode

```c
__int64 __fastcall OpenDiskHandle(const unsigned __int16 *a1)
{
  __int64 FileW; // rbx
  HANDLE v2; // rdi
  DWORD BytesReturned; // [rsp+40h] [rbp-258h] BYREF
  _OWORD OutBuffer[2]; // [rsp+48h] [rbp-250h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-228h] BYREF

  BytesReturned = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  FileW = -1;
  v2 = OpenVolumeHandle(a1);
  if ( v2 != (HANDLE)-1LL )
  {
    if ( DeviceIoControl(v2, 0x560000u, 0, 0, OutBuffer, 0x20u, &BytesReturned, 0)
      && StringCchPrintfW(FileName, 0x104u, L"\\\\.\\PhysicalDrive%d", DWORD2(OutBuffer[0])) >= 0 )
    {
      FileW = (__int64)CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
    }
    CloseHandle(v2);
  }
  return FileW;
}

```

## disassembly

```asm
0x18001b6cc  mov     [rsp+arg_8], rbx
0x18001b6d1  push    rdi
0x18001b6d2  sub     rsp, 290h
0x18001b6d9  mov     rax, cs:__security_cookie
0x18001b6e0  xor     rax, rsp
0x18001b6e3  mov     [rsp+298h+var_18], rax
0x18001b6eb  xorps   xmm0, xmm0
0x18001b6ee  mov     [rsp+298h+BytesReturned], 0
0x18001b6f6  movups  [rsp+298h+OutBuffer], xmm0
0x18001b6fb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001b6ff  movups  [rsp+298h+var_240], xmm0
0x18001b704  call    ?OpenVolumeHandle@@YAPEAXPEBG@Z; OpenVolumeHandle(ushort const *)
0x18001b709  mov     rdi, rax
0x18001b70c  cmp     rax, rbx
0x18001b70f  jz      loc_18001B7AA
0x18001b715  mov     [rsp+298h+lpOverlapped], 0; lpOverlapped
0x18001b71e  lea     rax, [rsp+298h+BytesReturned]
0x18001b723  mov     [rsp+298h+lpBytesReturned], rax; lpBytesReturned
0x18001b728  xor     r9d, r9d; nInBufferSize
0x18001b72b  lea     rax, [rsp+298h+OutBuffer]
0x18001b730  mov     [rsp+298h+nOutBufferSize], 20h ; ' '; nOutBufferSize
0x18001b738  xor     r8d, r8d; lpInBuffer
0x18001b73b  mov     [rsp+298h+lpOutBuffer], rax; lpOutBuffer
0x18001b740  mov     edx, 560000h; dwIoControlCode
0x18001b745  mov     rcx, rdi; hDevice
0x18001b748  call    cs:__imp_DeviceIoControl
0x18001b74e  test    eax, eax
0x18001b750  jz      short loc_18001B7A1
0x18001b752  mov     r9d, dword ptr [rsp+298h+OutBuffer+8]
0x18001b757  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x18001b75e  mov     edx, 104h; unsigned __int64
0x18001b763  lea     rcx, [rsp+298h+FileName]; unsigned __int16 *
0x18001b768  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b76d  test    eax, eax
0x18001b76f  js      short loc_18001B7A1
0x18001b771  mov     [rsp+298h+lpBytesReturned], 0; hTemplateFile
0x18001b77a  lea     r8d, [rbx+4]; dwShareMode
0x18001b77e  mov     [rsp+298h+nOutBufferSize], 80h; dwFlagsAndAttributes
0x18001b786  lea     rcx, [rsp+298h+FileName]; lpFileName
0x18001b78b  xor     r9d, r9d; lpSecurityAttributes
0x18001b78e  mov     dword ptr [rsp+298h+lpOutBuffer], r8d; dwCreationDisposition
0x18001b793  mov     edx, 0C0000000h; dwDesiredAccess
0x18001b798  call    cs:__imp_CreateFileW
0x18001b79e  mov     rbx, rax
0x18001b7a1  mov     rcx, rdi; hObject
0x18001b7a4  call    cs:__imp_CloseHandle
0x18001b7aa  mov     rax, rbx
0x18001b7ad  mov     rcx, [rsp+298h+var_18]
0x18001b7b5  xor     rcx, rsp; StackCookie
0x18001b7b8  call    __security_check_cookie
0x18001b7bd  mov     rbx, [rsp+298h+arg_8]
0x18001b7c5  add     rsp, 290h
0x18001b7cc  pop     rdi
0x18001b7cd  retn
```
