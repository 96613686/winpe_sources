# FvepIsVolumeEncryptedNoDriverTest

- ea: `0x1800437d4`
- end: `0x1800439d8`
- name: `FvepIsVolumeEncryptedNoDriverTest`
- size: `516`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800425a4`

## callees

- `0x180042c78`
- `0x1800433e4`
- `0x1800436e0`
- `0x1800437d4`
- `0x1800439e0`
- `0x180043b88`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004392a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004392a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043851`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180043851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800438cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043934`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800438cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043934`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800439af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800439af`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800438c1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800438c1`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800439a6`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800439a6`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180043906`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180043906`

## pseudocode

```c
__int64 __fastcall FvepIsVolumeEncryptedNoDriverTest(LPCWSTR lpFileName)
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
  int v14; // [rsp+40h] [rbp-30h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-2Ch] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-28h] BYREF
  __int128 OutBuffer; // [rsp+50h] [rbp-20h] BYREF
  __int64 v18; // [rsp+60h] [rbp-10h]

  v18 = 0;
  OutBuffer = 0;
  BytesReturned = 0;
  NumberOfBytesRead = 0;
  v14 = 0;
  if ( (unsigned int)FvepIsVolumeEncryptedCached(lpFileName, &v14) )
    return v14 == 0;
  FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x20000000u, 0);
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
      || (v7 = (HIDWORD(v18) + 511) & 0xFFFFFE00, v8 = VirtualAlloc(0, v7, 0x3000u, 4u), (v9 = v8) == 0) )
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
    FvepSetVolumeEncryptedCached((__int64)lpFileName, v11);
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
0x1800437d4  mov     [rsp-18h+arg_8], rbx
0x1800437d9  mov     [rsp-18h+arg_10], rsi
0x1800437de  push    rbp
0x1800437df  push    rdi
0x1800437e0  push    r14
0x1800437e2  mov     rbp, rsp
0x1800437e5  sub     rsp, 70h
0x1800437e9  mov     rax, cs:__security_cookie
0x1800437f0  xor     rax, rsp
0x1800437f3  mov     [rbp+var_8], rax
0x1800437f7  xor     eax, eax
0x1800437f9  lea     rdx, [rbp+var_30]
0x1800437fd  xorps   xmm0, xmm0
0x180043800  mov     [rbp+var_10], rax
0x180043804  movups  [rbp+OutBuffer], xmm0
0x180043808  mov     [rbp+BytesReturned], eax
0x18004380b  mov     rsi, rcx
0x18004380e  mov     [rbp+NumberOfBytesRead], eax
0x180043811  mov     [rbp+var_30], eax
0x180043814  call    FvepIsVolumeEncryptedCached
0x180043819  test    eax, eax
0x18004381b  jz      short loc_18004382A
0x18004381d  xor     ebx, ebx
0x18004381f  cmp     [rbp+var_30], ebx
0x180043822  setz    bl
0x180043825  jmp     loc_1800439B5
0x18004382a  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180043833  mov     r8d, 3; dwShareMode
0x180043839  mov     [rsp+70h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x180043841  xor     r9d, r9d; lpSecurityAttributes
0x180043844  mov     edx, 80000000h; dwDesiredAccess
0x180043849  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x18004384e  mov     rcx, rsi; lpFileName
0x180043851  call    cs:__imp_CreateFileW
0x180043857  mov     rdi, rax
0x18004385a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004385e  jnz     short loc_18004387E
0x180043860  call    cs:__imp_GetLastError
0x180043866  mov     ebx, eax
0x180043868  test    eax, eax
0x18004386a  jle     loc_1800439B5
0x180043870  movzx   ebx, ax
0x180043873  or      ebx, 80070000h
0x180043879  jmp     loc_1800439B5
0x18004387e  mov     rcx, rdi; hDevice
0x180043881  call    FvepIsBandBitLockerManaged
0x180043886  mov     ebx, eax
0x180043888  test    eax, eax
0x18004388a  jz      loc_1800439AC
0x180043890  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x180043899  lea     rax, [rbp+BytesReturned]
0x18004389d  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x1800438a2  xor     r9d, r9d; nInBufferSize
0x1800438a5  lea     rax, [rbp+OutBuffer]
0x1800438a9  mov     [rsp+70h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x1800438b1  xor     r8d, r8d; lpInBuffer
0x1800438b4  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpOutBuffer
0x1800438b9  mov     edx, 70000h; dwIoControlCode
0x1800438be  mov     rcx, rdi; hDevice
0x1800438c1  call    cs:__imp_DeviceIoControl
0x1800438c7  test    eax, eax
0x1800438c9  jnz     short loc_1800438E9
0x1800438cb  call    cs:__imp_GetLastError
0x1800438d1  mov     ebx, eax
0x1800438d3  test    eax, eax
0x1800438d5  jle     loc_1800439AC
0x1800438db  movzx   ebx, ax
0x1800438de  or      ebx, 80070000h
0x1800438e4  jmp     loc_1800439AC
0x1800438e9  mov     eax, dword ptr [rbp+var_10+4]
0x1800438ec  xor     ecx, ecx; lpAddress
0x1800438ee  add     eax, 1FFh
0x1800438f3  mov     r8d, 3000h; flAllocationType
0x1800438f9  and     eax, 0FFFFFE00h
0x1800438fe  mov     edx, eax; dwSize
0x180043900  lea     r9d, [rcx+4]; flProtect
0x180043904  mov     ebx, eax
0x180043906  call    cs:__imp_VirtualAlloc
0x18004390c  mov     r14, rax
0x18004390f  test    rax, rax
0x180043912  jz      short loc_1800438CB
0x180043914  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180043918  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180043921  mov     r8d, ebx; nNumberOfBytesToRead
0x180043924  mov     rdx, rax; lpBuffer
0x180043927  mov     rcx, rdi; hFile
0x18004392a  call    cs:__imp_ReadFile
0x180043930  test    eax, eax
0x180043932  jnz     short loc_180043958
0x180043934  call    cs:__imp_GetLastError
0x18004393a  mov     ebx, eax
0x18004393c  test    eax, eax
0x18004393e  jle     short loc_180043949
0x180043940  movzx   ebx, ax
0x180043943  or      ebx, 80070000h
0x180043949  cmp     ebx, 80310000h
0x18004394f  jnz     short loc_18004399B
0x180043951  xor     ebx, ebx
0x180043953  lea     edx, [rbx+1]
0x180043956  jmp     short loc_180043993
0x180043958  mov     edx, [rbp+NumberOfBytesRead]
0x18004395b  xor     r8d, r8d
0x18004395e  mov     rcx, r14
0x180043961  call    FveCheckVolumeTypeEx
0x180043966  lea     ecx, [rax-2]
0x180043969  cmp     ecx, 1
0x18004396c  jbe     short loc_18004398A
0x18004396e  cmp     eax, 1
0x180043971  jnz     short loc_180043983
0x180043973  mov     rcx, rdi; hDevice
0x180043976  call    FvepCheckForVolumeControlFiles
0x18004397b  mov     ebx, eax
0x18004397d  test    eax, eax
0x18004397f  js      short loc_18004399B
0x180043981  jmp     short loc_18004398C
0x180043983  mov     ebx, 1
0x180043988  jmp     short loc_18004398C
0x18004398a  xor     ebx, ebx
0x18004398c  xor     edx, edx
0x18004398e  test    ebx, ebx
0x180043990  setz    dl
0x180043993  mov     rcx, rsi
0x180043996  call    FvepSetVolumeEncryptedCached
0x18004399b  xor     edx, edx; dwSize
0x18004399d  mov     r8d, 8000h; dwFreeType
0x1800439a3  mov     rcx, r14; lpAddress
0x1800439a6  call    cs:__imp_VirtualFree
0x1800439ac  mov     rcx, rdi; hObject
0x1800439af  call    cs:__imp_CloseHandle
0x1800439b5  mov     eax, ebx
0x1800439b7  mov     rcx, [rbp+var_8]
0x1800439bb  xor     rcx, rsp; StackCookie
0x1800439be  call    __security_check_cookie
0x1800439c3  lea     r11, [rsp+70h+var_s0]
0x1800439c8  mov     rbx, [r11+28h]
0x1800439cc  mov     rsi, [r11+30h]
0x1800439d0  mov     rsp, r11
0x1800439d3  pop     r14
0x1800439d5  pop     rdi
0x1800439d6  pop     rbp
0x1800439d7  retn
```
