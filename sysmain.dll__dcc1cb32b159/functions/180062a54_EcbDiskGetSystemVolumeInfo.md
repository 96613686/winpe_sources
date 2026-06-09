# EcbDiskGetSystemVolumeInfo

- ea: `0x180062a54`
- end: `0x180062bd7`
- name: `EcbDiskGetSystemVolumeInfo`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180062740`

## callees

- `0x180021e0c`
- `0x180062a54`
- `0x1800b2308`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062b61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062b61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062ba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062ba9`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180062aae`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180062aae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180062b15`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180062b15`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180062b57`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180062b57`

## pseudocode

```c
__int64 __fastcall EcbDiskGetSystemVolumeInfo(_DWORD *a1, _QWORD *a2, _DWORD *a3)
{
  DWORD VolumeIds; // ebx
  HRESULT v7; // eax
  HANDLE FileW; // rdi
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h]
  _DWORD OutBuffer[8]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[24]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  BytesReturned = 0;
  memset(OutBuffer, 0, 28);
  v11 = 0;
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    return GetLastError();
  v7 = StringCchPrintfW(pszDest, 0x14u, L"\\\\.\\%wc:", Buffer[0]);
  if ( v7 < 0 )
    return (unsigned __int16)v7;
  FileW = CreateFileW(pszDest, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    if ( DeviceIoControl(FileW, 0x560000u, 0, 0, OutBuffer, 0x20u, &BytesReturned, 0) )
    {
      if ( OutBuffer[0] == 1 )
      {
        VolumeIds = EcbDiskGetVolumeIds(FileW);
        if ( !VolumeIds )
        {
          *a3 = OutBuffer[2];
          *a1 = 0;
          *a2 = v11;
        }
      }
      else
      {
        VolumeIds = 50;
      }
    }
    else
    {
      VolumeIds = GetLastError();
    }
    CloseHandle(FileW);
  }
  return VolumeIds;
}

```

## disassembly

```asm
0x180062a54  mov     [rsp-8+arg_18], rbx
0x180062a59  push    rbp
0x180062a5a  push    rsi
0x180062a5b  push    rdi
0x180062a5c  push    r14
0x180062a5e  push    r15
0x180062a60  lea     rbp, [rsp-1C0h]
0x180062a68  sub     rsp, 2C0h
0x180062a6f  mov     rax, cs:__security_cookie
0x180062a76  xor     rax, rsp
0x180062a79  mov     [rbp+1E0h+var_30], rax
0x180062a80  xor     eax, eax
0x180062a82  xorps   xmm0, xmm0
0x180062a85  mov     r14, rdx
0x180062a88  mov     [rsp+2E0h+BytesReturned], eax
0x180062a8c  mov     rsi, rcx
0x180062a8f  mov     [rsp+2E0h+var_2A0], eax
0x180062a93  movups  xmmword ptr [rsp+2E0h+OutBuffer], xmm0
0x180062a98  mov     edx, 104h; uSize
0x180062a9d  mov     [rsp+2E0h+var_298], rax
0x180062aa2  lea     rcx, [rbp+1E0h+Buffer]; lpBuffer
0x180062aa6  mov     r15, r8
0x180062aa9  movups  xmmword ptr [rsp+2E0h+OutBuffer+0Ch], xmm0
0x180062aae  call    cs:__imp_GetWindowsDirectoryW
0x180062ab4  test    eax, eax
0x180062ab6  jnz     short loc_180062AC5
0x180062ab8  call    cs:__imp_GetLastError
0x180062abe  mov     ebx, eax
0x180062ac0  jmp     loc_180062BAF
0x180062ac5  movzx   r9d, [rbp+1E0h+Buffer]
0x180062aca  lea     r8, aWc; "\\\\.\\%wc:"
0x180062ad1  mov     edx, 14h; cchDest
0x180062ad6  lea     rcx, [rsp+2E0h+pszDest]; pszDest
0x180062adb  call    StringCchPrintfW
0x180062ae0  test    eax, eax
0x180062ae2  jns     short loc_180062AEC
0x180062ae4  movzx   ebx, ax
0x180062ae7  jmp     loc_180062BAF
0x180062aec  mov     [rsp+2E0h+hTemplateFile], 0; hTemplateFile
0x180062af5  lea     rcx, [rsp+2E0h+pszDest]; lpFileName
0x180062afa  mov     r8d, 3; dwShareMode
0x180062b00  mov     [rsp+2E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180062b08  xor     r9d, r9d; lpSecurityAttributes
0x180062b0b  mov     [rsp+2E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180062b10  mov     edx, 80000000h; dwDesiredAccess
0x180062b15  call    cs:__imp_CreateFileW
0x180062b1b  mov     rdi, rax
0x180062b1e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180062b22  jz      short loc_180062AB8
0x180062b24  mov     [rsp+2E0h+lpOverlapped], 0; lpOverlapped
0x180062b2d  lea     rax, [rsp+2E0h+BytesReturned]
0x180062b32  mov     [rsp+2E0h+hTemplateFile], rax; lpBytesReturned
0x180062b37  xor     r9d, r9d; nInBufferSize
0x180062b3a  lea     rax, [rsp+2E0h+OutBuffer]
0x180062b3f  mov     [rsp+2E0h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x180062b47  xor     r8d, r8d; lpInBuffer
0x180062b4a  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax; lpOutBuffer
0x180062b4f  mov     edx, 560000h; dwIoControlCode
0x180062b54  mov     rcx, rdi; hDevice
0x180062b57  call    cs:__imp_DeviceIoControl
0x180062b5d  test    eax, eax
0x180062b5f  jnz     short loc_180062B6B
0x180062b61  call    cs:__imp_GetLastError
0x180062b67  mov     ebx, eax
0x180062b69  jmp     short loc_180062BA6
0x180062b6b  cmp     [rsp+2E0h+OutBuffer], 1
0x180062b70  jz      short loc_180062B79
0x180062b72  mov     ebx, 32h ; '2'
0x180062b77  jmp     short loc_180062BA6
0x180062b79  lea     r8, [rsp+2E0h+var_298]
0x180062b7e  mov     rcx, rdi; FileHandle
0x180062b81  lea     rdx, [rsp+2E0h+var_2A0]
0x180062b86  call    EcbDiskGetVolumeIds
0x180062b8b  mov     ebx, eax
0x180062b8d  test    eax, eax
0x180062b8f  jnz     short loc_180062BA6
0x180062b91  mov     eax, [rsp+2E0h+OutBuffer+8]
0x180062b95  mov     [r15], eax
0x180062b98  mov     eax, [rsp+2E0h+var_2A0]
0x180062b9c  mov     [rsi], eax
0x180062b9e  mov     rax, [rsp+2E0h+var_298]
0x180062ba3  mov     [r14], rax
0x180062ba6  mov     rcx, rdi; hObject
0x180062ba9  call    cs:__imp_CloseHandle
0x180062baf  mov     eax, ebx
0x180062bb1  mov     rcx, [rbp+1E0h+var_30]
0x180062bb8  xor     rcx, rsp; StackCookie
0x180062bbb  call    __security_check_cookie
0x180062bc0  mov     rbx, [rsp+2E0h+arg_18]
0x180062bc8  add     rsp, 2C0h
0x180062bcf  pop     r15
0x180062bd1  pop     r14
0x180062bd3  pop     rdi
0x180062bd4  pop     rsi
0x180062bd5  pop     rbp
0x180062bd6  retn
```
