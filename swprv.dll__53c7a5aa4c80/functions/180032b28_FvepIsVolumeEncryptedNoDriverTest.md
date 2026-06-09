# FvepIsVolumeEncryptedNoDriverTest

- ea: `0x180032b28`
- end: `0x180032d2c`
- name: `FvepIsVolumeEncryptedNoDriverTest`
- size: `516`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18003195c`

## callees

- `0x180001580`
- `0x1800320fc`
- `0x18003273c`
- `0x180032a34`
- `0x180032b28`
- `0x180032d34`
- `0x180041608`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032d03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032d03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032c88`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032ba5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180032ba5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032c7e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032c7e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180032c15`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180032c15`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180032cfa`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180032cfa`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180032c5a`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180032c5a`

## pseudocode

```c
__int64 __fastcall FvepIsVolumeEncryptedNoDriverTest(STRSAFE_PCNZWCH pszSrc)
{
  unsigned int IsBandBitLockerManaged; // ebx
  HANDLE FileW; // rax
  void *v4; // rdi
  signed int v5; // eax
  signed int LastError; // eax
  DWORD v7; // ebx
  void *v8; // rax
  void *v9; // r14
  signed int v10; // eax
  BOOL v11; // edx
  int v12; // eax
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-2Ch] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-28h] BYREF
  __int128 OutBuffer; // [rsp+50h] [rbp-20h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]

  v17 = 0;
  OutBuffer = 0;
  BytesReturned = 0;
  NumberOfBytesRead = 0;
  if ( (unsigned int)FvepIsVolumeEncryptedCached(pszSrc) )
    return 1;
  FileW = CreateFileW(pszSrc, 0x80000000, 3u, 0, 3u, 0x20000000u, 0);
  v4 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    IsBandBitLockerManaged = FvepIsBandBitLockerManaged(FileW);
    if ( !IsBandBitLockerManaged )
    {
LABEL_25:
      CloseHandle(v4);
      return IsBandBitLockerManaged;
    }
    if ( !DeviceIoControl(v4, 0x70000u, 0, 0, &OutBuffer, 0x18u, &BytesReturned, 0)
      || (v7 = (HIDWORD(v17) + 511) & 0xFFFFFE00, v8 = VirtualAlloc(0, v7, 0x3000u, 4u), (v9 = v8) == 0) )
    {
      LastError = GetLastError();
      IsBandBitLockerManaged = LastError;
      if ( LastError > 0 )
        IsBandBitLockerManaged = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_25;
    }
    if ( ReadFile(v4, v8, v7, &NumberOfBytesRead, 0) )
    {
      v12 = FveCheckVolumeTypeEx(v9, NumberOfBytesRead, 0);
      if ( (unsigned int)(v12 - 2) <= 1 )
      {
        IsBandBitLockerManaged = 0;
      }
      else if ( v12 == 1 )
      {
        IsBandBitLockerManaged = FvepCheckForVolumeControlFiles(v4);
        if ( (IsBandBitLockerManaged & 0x80000000) != 0 )
        {
LABEL_24:
          VirtualFree(v9, 0, 0x8000u);
          goto LABEL_25;
        }
      }
      else
      {
        IsBandBitLockerManaged = 1;
      }
      v11 = IsBandBitLockerManaged == 0;
    }
    else
    {
      v10 = GetLastError();
      IsBandBitLockerManaged = v10;
      if ( v10 > 0 )
        IsBandBitLockerManaged = (unsigned __int16)v10 | 0x80070000;
      if ( IsBandBitLockerManaged != -2144272384 )
        goto LABEL_24;
      IsBandBitLockerManaged = 0;
      v11 = 1;
    }
    FvepSetVolumeEncryptedCached(pszSrc, v11);
    goto LABEL_24;
  }
  v5 = GetLastError();
  IsBandBitLockerManaged = v5;
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return IsBandBitLockerManaged;
}

```

## disassembly

```asm
0x180032b28  mov     [rsp-18h+arg_8], rbx
0x180032b2d  mov     [rsp-18h+arg_10], rsi
0x180032b32  push    rbp
0x180032b33  push    rdi
0x180032b34  push    r14
0x180032b36  mov     rbp, rsp
0x180032b39  sub     rsp, 70h
0x180032b3d  mov     rax, cs:__security_cookie
0x180032b44  xor     rax, rsp
0x180032b47  mov     [rbp+var_8], rax
0x180032b4b  xor     eax, eax
0x180032b4d  lea     rdx, [rbp+var_30]
0x180032b51  xorps   xmm0, xmm0
0x180032b54  mov     [rbp+var_10], rax
0x180032b58  movups  [rbp+OutBuffer], xmm0
0x180032b5c  mov     [rbp+BytesReturned], eax
0x180032b5f  mov     rsi, rcx
0x180032b62  mov     [rbp+NumberOfBytesRead], eax
0x180032b65  mov     [rbp+var_30], eax
0x180032b68  call    FvepIsVolumeEncryptedCached
0x180032b6d  test    eax, eax
0x180032b6f  jz      short loc_180032B7E
0x180032b71  xor     ebx, ebx
0x180032b73  cmp     [rbp+var_30], ebx
0x180032b76  setz    bl
0x180032b79  jmp     loc_180032D09
0x180032b7e  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180032b87  mov     r8d, 3; dwShareMode
0x180032b8d  mov     [rsp+70h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x180032b95  xor     r9d, r9d; lpSecurityAttributes
0x180032b98  mov     edx, 80000000h; dwDesiredAccess
0x180032b9d  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x180032ba2  mov     rcx, rsi; lpFileName
0x180032ba5  call    cs:__imp_CreateFileW
0x180032bab  mov     rdi, rax
0x180032bae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032bb2  jnz     short loc_180032BD2
0x180032bb4  call    cs:__imp_GetLastError
0x180032bba  mov     ebx, eax
0x180032bbc  test    eax, eax
0x180032bbe  jle     loc_180032D09
0x180032bc4  movzx   ebx, ax
0x180032bc7  or      ebx, 80070000h
0x180032bcd  jmp     loc_180032D09
0x180032bd2  mov     rcx, rdi; hDevice
0x180032bd5  call    FvepIsBandBitLockerManaged
0x180032bda  mov     ebx, eax
0x180032bdc  test    eax, eax
0x180032bde  jz      loc_180032D00
0x180032be4  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x180032bed  lea     rax, [rbp+BytesReturned]
0x180032bf1  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x180032bf6  xor     r9d, r9d; nInBufferSize
0x180032bf9  lea     rax, [rbp+OutBuffer]
0x180032bfd  mov     [rsp+70h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x180032c05  xor     r8d, r8d; lpInBuffer
0x180032c08  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpOutBuffer
0x180032c0d  mov     edx, 70000h; dwIoControlCode
0x180032c12  mov     rcx, rdi; hDevice
0x180032c15  call    cs:__imp_DeviceIoControl
0x180032c1b  test    eax, eax
0x180032c1d  jnz     short loc_180032C3D
0x180032c1f  call    cs:__imp_GetLastError
0x180032c25  mov     ebx, eax
0x180032c27  test    eax, eax
0x180032c29  jle     loc_180032D00
0x180032c2f  movzx   ebx, ax
0x180032c32  or      ebx, 80070000h
0x180032c38  jmp     loc_180032D00
0x180032c3d  mov     eax, dword ptr [rbp+var_10+4]
0x180032c40  xor     ecx, ecx; lpAddress
0x180032c42  add     eax, 1FFh
0x180032c47  mov     r8d, 3000h; flAllocationType
0x180032c4d  and     eax, 0FFFFFE00h
0x180032c52  mov     edx, eax; dwSize
0x180032c54  lea     r9d, [rcx+4]; flProtect
0x180032c58  mov     ebx, eax
0x180032c5a  call    cs:__imp_VirtualAlloc
0x180032c60  mov     r14, rax
0x180032c63  test    rax, rax
0x180032c66  jz      short loc_180032C1F
0x180032c68  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180032c6c  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180032c75  mov     r8d, ebx; nNumberOfBytesToRead
0x180032c78  mov     rdx, rax; lpBuffer
0x180032c7b  mov     rcx, rdi; hFile
0x180032c7e  call    cs:__imp_ReadFile
0x180032c84  test    eax, eax
0x180032c86  jnz     short loc_180032CAC
0x180032c88  call    cs:__imp_GetLastError
0x180032c8e  mov     ebx, eax
0x180032c90  test    eax, eax
0x180032c92  jle     short loc_180032C9D
0x180032c94  movzx   ebx, ax
0x180032c97  or      ebx, 80070000h
0x180032c9d  cmp     ebx, 80310000h
0x180032ca3  jnz     short loc_180032CEF
0x180032ca5  xor     ebx, ebx
0x180032ca7  lea     edx, [rbx+1]
0x180032caa  jmp     short loc_180032CE7
0x180032cac  mov     edx, [rbp+NumberOfBytesRead]
0x180032caf  xor     r8d, r8d
0x180032cb2  mov     rcx, r14
0x180032cb5  call    FveCheckVolumeTypeEx
0x180032cba  lea     ecx, [rax-2]
0x180032cbd  cmp     ecx, 1
0x180032cc0  jbe     short loc_180032CDE
0x180032cc2  cmp     eax, 1
0x180032cc5  jnz     short loc_180032CD7
0x180032cc7  mov     rcx, rdi; hDevice
0x180032cca  call    FvepCheckForVolumeControlFiles
0x180032ccf  mov     ebx, eax
0x180032cd1  test    eax, eax
0x180032cd3  js      short loc_180032CEF
0x180032cd5  jmp     short loc_180032CE0
0x180032cd7  mov     ebx, 1
0x180032cdc  jmp     short loc_180032CE0
0x180032cde  xor     ebx, ebx
0x180032ce0  xor     edx, edx
0x180032ce2  test    ebx, ebx
0x180032ce4  setz    dl
0x180032ce7  mov     rcx, rsi; pszSrc
0x180032cea  call    FvepSetVolumeEncryptedCached
0x180032cef  xor     edx, edx; dwSize
0x180032cf1  mov     r8d, 8000h; dwFreeType
0x180032cf7  mov     rcx, r14; lpAddress
0x180032cfa  call    cs:__imp_VirtualFree
0x180032d00  mov     rcx, rdi; hObject
0x180032d03  call    cs:__imp_CloseHandle
0x180032d09  mov     eax, ebx
0x180032d0b  mov     rcx, [rbp+var_8]
0x180032d0f  xor     rcx, rsp; StackCookie
0x180032d12  call    __security_check_cookie
0x180032d17  lea     r11, [rsp+70h+var_s0]
0x180032d1c  mov     rbx, [r11+28h]
0x180032d20  mov     rsi, [r11+30h]
0x180032d24  mov     rsp, r11
0x180032d27  pop     r14
0x180032d29  pop     rdi
0x180032d2a  pop     rbp
0x180032d2b  retn
```
