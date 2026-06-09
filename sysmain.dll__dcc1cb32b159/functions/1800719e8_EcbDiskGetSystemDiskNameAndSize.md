# EcbDiskGetSystemDiskNameAndSize

- ea: `0x1800719e8`
- end: `0x180071b06`
- name: `EcbDiskGetSystemDiskNameAndSize`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180062740`

## callees

- `0x180020ee8`
- `0x180021e0c`
- `0x1800719e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071a67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071ac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071a67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071ac0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071aee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180071aee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180071a58`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180071a58`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180071ab6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180071ab6`

## string_xrefs

- `0x180071a70`: `ERROR: Failed to open a disk %ws.\n`

## pseudocode

```c
__int64 __fastcall EcbDiskGetSystemDiskNameAndSize(unsigned int a1, __int64 a2, _QWORD *LastError)
{
  const WCHAR *v3; // rsi
  HRESULT v5; // eax
  HANDLE FileW; // rdi
  DWORD BytesReturned; // [rsp+58h] [rbp+10h] BYREF
  __int64 OutBuffer; // [rsp+68h] [rbp+20h] BYREF

  v3 = (const WCHAR *)(a2 + 32);
  BytesReturned = 0;
  OutBuffer = 0;
  v5 = StringCchPrintfW((STRSAFE_LPWSTR)(a2 + 32), 0x104u, L"\\\\.\\PhysicalDrive%d", a1);
  if ( v5 >= 0 )
  {
    FileW = CreateFileW(v3, 0x80000000, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LODWORD(LastError) = GetLastError();
      EcbUtilsOut(1, "ERROR: Failed to open a disk %ws.\n", v3);
    }
    else
    {
      if ( DeviceIoControl(FileW, 0x7405Cu, 0, 0, &OutBuffer, 8u, &BytesReturned, 0) )
      {
        *LastError = OutBuffer;
        LODWORD(LastError) = 0;
      }
      else
      {
        LastError = (_QWORD *)GetLastError();
        EcbUtilsOut(1, "ERROR: Get length info failed for drive %ws with %d\n", v3, LastError);
      }
      CloseHandle(FileW);
    }
  }
  else
  {
    LODWORD(LastError) = (unsigned __int16)v5;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800719e8  mov     rax, rsp
0x1800719eb  mov     [rax+8], rbx
0x1800719ef  mov     [rax+18h], rsi
0x1800719f3  push    rdi
0x1800719f4  sub     rsp, 40h
0x1800719f8  lea     rsi, [rdx+20h]
0x1800719fc  mov     dword ptr [rax+10h], 0
0x180071a03  mov     rbx, r8
0x180071a06  mov     qword ptr [rax+20h], 0
0x180071a0e  mov     r9d, ecx
0x180071a11  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x180071a18  mov     rcx, rsi; pszDest
0x180071a1b  mov     edx, 104h; cchDest
0x180071a20  call    StringCchPrintfW
0x180071a25  test    eax, eax
0x180071a27  jns     short loc_180071A31
0x180071a29  movzx   ebx, ax
0x180071a2c  jmp     loc_180071AF4
0x180071a31  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180071a3a  mov     r8d, 3; dwShareMode
0x180071a40  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180071a48  xor     r9d, r9d; lpSecurityAttributes
0x180071a4b  mov     edx, 80000000h; dwDesiredAccess
0x180071a50  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180071a55  mov     rcx, rsi; lpFileName
0x180071a58  call    cs:__imp_CreateFileW
0x180071a5e  mov     rdi, rax
0x180071a61  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180071a65  jnz     short loc_180071A83
0x180071a67  call    cs:__imp_GetLastError
0x180071a6d  mov     r8, rsi
0x180071a70  lea     rdx, aErrorFailedToO_0; "ERROR: Failed to open a disk %ws.\n"
0x180071a77  lea     ecx, [rdi+2]
0x180071a7a  mov     ebx, eax
0x180071a7c  call    EcbUtilsOut
0x180071a81  jmp     short loc_180071AF4
0x180071a83  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180071a8c  lea     rax, [rsp+48h+BytesReturned]
0x180071a91  mov     [rsp+48h+hTemplateFile], rax; lpBytesReturned
0x180071a96  xor     r9d, r9d; nInBufferSize
0x180071a99  lea     rax, [rsp+48h+OutBuffer]
0x180071a9e  mov     [rsp+48h+dwFlagsAndAttributes], 8; nOutBufferSize
0x180071aa6  xor     r8d, r8d; lpInBuffer
0x180071aa9  mov     qword ptr [rsp+48h+dwCreationDisposition], rax; lpOutBuffer
0x180071aae  mov     edx, 7405Ch; dwIoControlCode
0x180071ab3  mov     rcx, rdi; hDevice
0x180071ab6  call    cs:__imp_DeviceIoControl
0x180071abc  test    eax, eax
0x180071abe  jnz     short loc_180071AE1
0x180071ac0  call    cs:__imp_GetLastError
0x180071ac6  mov     r8, rsi
0x180071ac9  lea     rdx, aErrorGetLength; "ERROR: Get length info failed for drive"...
0x180071ad0  mov     r9d, eax
0x180071ad3  mov     ecx, 1
0x180071ad8  mov     ebx, eax
0x180071ada  call    EcbUtilsOut
0x180071adf  jmp     short loc_180071AEB
0x180071ae1  mov     rax, [rsp+48h+OutBuffer]
0x180071ae6  mov     [rbx], rax
0x180071ae9  xor     ebx, ebx
0x180071aeb  mov     rcx, rdi; hObject
0x180071aee  call    cs:__imp_CloseHandle
0x180071af4  mov     rsi, [rsp+48h+arg_10]
0x180071af9  mov     eax, ebx
0x180071afb  mov     rbx, [rsp+48h+arg_0]
0x180071b00  add     rsp, 40h
0x180071b04  pop     rdi
0x180071b05  retn
```
