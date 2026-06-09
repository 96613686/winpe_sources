# UsbHelper_GetDeviceSpeedInformation(ushort *,ushort,_USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS *)

- ea: `0x18000fbf8`
- end: `0x18000fcde`
- name: `?UsbHelper_GetDeviceSpeedInformation@@YAKPEAGGPEAT_USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16, union _USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000f74c`

## callees

- `0x180002410`
- `0x18000fbf8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fcc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fcc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000fc46`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000fc46`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000fca2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000fca2`

## pseudocode

```c
__int64 __fastcall UsbHelper_GetDeviceSpeedInformation(
        unsigned __int16 *a1,
        unsigned __int16 a2,
        union _USB_NODE_CONNECTION_INFORMATION_EX_V2_FLAGS *a3)
{
  unsigned int v4; // esi
  HANDLE FileW; // rdi
  DWORD LastError; // ebx
  DWORD BytesReturned; // [rsp+40h] [rbp-38h] BYREF
  __int128 OutBuffer; // [rsp+48h] [rbp-30h] BYREF

  v4 = a2;
  BytesReturned = 0;
  OutBuffer = 0;
  FileW = CreateFileW(a1, 0, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    DWORD2(OutBuffer) |= 7u;
    *(_QWORD *)&OutBuffer = v4 | 0x1000000000LL;
    if ( DeviceIoControl(FileW, 0x22045Cu, &OutBuffer, 0x10u, &OutBuffer, 0x10u, &BytesReturned, 0) )
    {
      *(_DWORD *)a3 = HIDWORD(OutBuffer);
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
    CloseHandle(FileW);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000fbf8  push    rbx
0x18000fbfa  push    rsi
0x18000fbfb  push    rdi
0x18000fbfc  sub     rsp, 60h
0x18000fc00  mov     rax, cs:__security_cookie
0x18000fc07  xor     rax, rsp
0x18000fc0a  mov     [rsp+78h+var_20], rax
0x18000fc0f  mov     rbx, r8
0x18000fc12  movzx   esi, dx
0x18000fc15  mov     r8d, 3; dwShareMode
0x18000fc1b  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18000fc24  xorps   xmm0, xmm0
0x18000fc27  mov     [rsp+78h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000fc2f  xor     r9d, r9d; lpSecurityAttributes
0x18000fc32  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000fc37  xor     edx, edx; dwDesiredAccess
0x18000fc39  mov     [rsp+78h+BytesReturned], 0
0x18000fc41  movups  [rsp+78h+OutBuffer], xmm0
0x18000fc46  call    cs:__imp_CreateFileW
0x18000fc4c  mov     rdi, rax
0x18000fc4f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fc53  jnz     short loc_18000FC5F
0x18000fc55  call    cs:__imp_GetLastError
0x18000fc5b  mov     ebx, eax
0x18000fc5d  jmp     short loc_18000FCC7
0x18000fc5f  or      dword ptr [rsp+78h+OutBuffer+8], 7
0x18000fc64  lea     rax, [rsp+78h+BytesReturned]
0x18000fc69  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18000fc72  lea     r8, [rsp+78h+OutBuffer]; lpInBuffer
0x18000fc77  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18000fc7c  mov     r9d, 10h; nInBufferSize
0x18000fc82  lea     rax, [rsp+78h+OutBuffer]
0x18000fc87  mov     [rsp+78h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x18000fc8c  mov     edx, 22045Ch; dwIoControlCode
0x18000fc91  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpOutBuffer
0x18000fc96  mov     rcx, rdi; hDevice
0x18000fc99  mov     dword ptr [rsp+78h+OutBuffer+4], r9d
0x18000fc9e  mov     dword ptr [rsp+78h+OutBuffer], esi
0x18000fca2  call    cs:__imp_DeviceIoControl
0x18000fca8  test    eax, eax
0x18000fcaa  jnz     short loc_18000FCB6
0x18000fcac  call    cs:__imp_GetLastError
0x18000fcb2  mov     ebx, eax
0x18000fcb4  jmp     short loc_18000FCBE
0x18000fcb6  mov     eax, dword ptr [rsp+78h+OutBuffer+0Ch]
0x18000fcba  mov     [rbx], eax
0x18000fcbc  xor     ebx, ebx
0x18000fcbe  mov     rcx, rdi; hObject
0x18000fcc1  call    cs:__imp_CloseHandle
0x18000fcc7  mov     eax, ebx
0x18000fcc9  mov     rcx, [rsp+78h+var_20]
0x18000fcce  xor     rcx, rsp; StackCookie
0x18000fcd1  call    __security_check_cookie
0x18000fcd6  add     rsp, 60h
0x18000fcda  pop     rdi
0x18000fcdb  pop     rsi
0x18000fcdc  pop     rbx
0x18000fcdd  retn
```
