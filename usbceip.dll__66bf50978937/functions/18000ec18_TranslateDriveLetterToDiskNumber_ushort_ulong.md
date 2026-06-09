# TranslateDriveLetterToDiskNumber(ushort,ulong *)

- ea: `0x18000ec18`
- end: `0x18000ede5`
- name: `?TranslateDriveLetterToDiskNumber@@YAKGPEAK@Z`
- size: `461`
- prototype: `__int64 __fastcall(unsigned __int16, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800074fc`
- `0x18000edec`

## callees

- `0x180002410`
- `0x180002e6e`
- `0x180003a80`
- `0x18000ec18`
- `0x18000f32c`
- `0x18000f370`
- `0x18000fe30`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000edb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000edb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed45`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ecbc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ecbc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ed3b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ed3b`

## pseudocode

```c
__int64 __fastcall TranslateDriveLetterToDiskNumber(unsigned __int16 a1, unsigned int *a2)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rdi
  DWORD LastError; // ebx
  __int64 v6; // r8
  __int64 v7; // r8
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-2238h] BYREF
  _DWORD OutBuffer[2048]; // [rsp+50h] [rbp-2228h] BYREF
  WCHAR FileName[264]; // [rsp+2050h] [rbp-228h] BYREF

  v3 = a1;
  memset_0(OutBuffer, 0, sizeof(OutBuffer));
  BytesReturned[0] = 0;
  memset_0(FileName, 0, 0x208u);
  StringCchPrintfW(FileName, 0x104u, L"\\\\.\\%c:", v3);
  FileW = CreateFileW(FileName, 0, 3u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v6, LastError);
  }
  else
  {
    if ( DeviceIoControl(FileW, 0x560000u, 0, 0, OutBuffer, 0x2000u, BytesReturned, 0) )
    {
      if ( OutBuffer[0] == 1 )
      {
        LastError = 0;
        *a2 = OutBuffer[2];
      }
      else
      {
        LastError = 87;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2));
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v7, LastError);
    }
    CloseHandle(FileW);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000ec18  mov     [rsp+arg_10], rbx
0x18000ec1d  mov     [rsp+arg_18], rsi
0x18000ec22  push    rdi
0x18000ec23  mov     eax, 2270h
0x18000ec28  call    _alloca_probe
0x18000ec2d  sub     rsp, rax
0x18000ec30  mov     rax, cs:__security_cookie
0x18000ec37  xor     rax, rsp
0x18000ec3a  mov     [rsp+2278h+var_18], rax
0x18000ec42  mov     rsi, rdx
0x18000ec45  movzx   ebx, cx
0x18000ec48  xor     edx, edx; Val
0x18000ec4a  lea     rcx, [rsp+2278h+OutBuffer]; void *
0x18000ec4f  mov     r8d, 2000h; Size
0x18000ec55  call    memset_0
0x18000ec5a  xor     edx, edx; Val
0x18000ec5c  mov     [rsp+2278h+BytesReturned], 0
0x18000ec64  mov     r8d, 208h; Size
0x18000ec6a  lea     rcx, [rsp+2278h+FileName]; void *
0x18000ec72  call    memset_0
0x18000ec77  mov     r9d, ebx
0x18000ec7a  lea     r8, aC; "\\\\.\\%c:"
0x18000ec81  mov     edx, 104h; unsigned __int64
0x18000ec86  lea     rcx, [rsp+2278h+FileName]; unsigned __int16 *
0x18000ec8e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ec93  mov     r8d, 3; dwShareMode
0x18000ec99  mov     [rsp+2278h+hTemplateFile], 0; hTemplateFile
0x18000eca2  mov     [rsp+2278h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000ecaa  lea     rcx, [rsp+2278h+FileName]; lpFileName
0x18000ecb2  xor     r9d, r9d; lpSecurityAttributes
0x18000ecb5  mov     [rsp+2278h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000ecba  xor     edx, edx; dwDesiredAccess
0x18000ecbc  call    cs:__imp_CreateFileW
0x18000ecc2  mov     rdi, rax
0x18000ecc5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ecc9  jnz     short loc_18000ED08
0x18000eccb  call    cs:__imp_GetLastError
0x18000ecd1  mov     ebx, eax
0x18000ecd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecda  lea     rax, WPP_GLOBAL_Control
0x18000ece1  cmp     rcx, rax
0x18000ece4  jz      loc_18000EDBE
0x18000ecea  test    byte ptr [rcx+1Ch], 1
0x18000ecee  jz      loc_18000EDBE
0x18000ecf4  mov     rcx, [rcx+10h]
0x18000ecf8  lea     edx, [rdi+0Bh]
0x18000ecfb  mov     r9d, ebx
0x18000ecfe  call    WPP_SF_D
0x18000ed03  jmp     loc_18000EDBE
0x18000ed08  mov     [rsp+2278h+lpOverlapped], 0; lpOverlapped
0x18000ed11  lea     rax, [rsp+2278h+BytesReturned]
0x18000ed16  mov     [rsp+2278h+hTemplateFile], rax; lpBytesReturned
0x18000ed1b  xor     r9d, r9d; nInBufferSize
0x18000ed1e  lea     rax, [rsp+2278h+OutBuffer]
0x18000ed23  mov     [rsp+2278h+dwFlagsAndAttributes], 2000h; nOutBufferSize
0x18000ed2b  xor     r8d, r8d; lpInBuffer
0x18000ed2e  mov     qword ptr [rsp+2278h+dwCreationDisposition], rax; lpOutBuffer
0x18000ed33  mov     edx, 560000h; dwIoControlCode
0x18000ed38  mov     rcx, rdi; hDevice
0x18000ed3b  call    cs:__imp_DeviceIoControl
0x18000ed41  test    eax, eax
0x18000ed43  jnz     short loc_18000ED79
0x18000ed45  call    cs:__imp_GetLastError
0x18000ed4b  mov     ebx, eax
0x18000ed4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed54  lea     rax, WPP_GLOBAL_Control
0x18000ed5b  cmp     rcx, rax
0x18000ed5e  jz      short loc_18000EDB5
0x18000ed60  test    byte ptr [rcx+1Ch], 1
0x18000ed64  jz      short loc_18000EDB5
0x18000ed66  mov     rcx, [rcx+10h]
0x18000ed6a  mov     edx, 0Bh
0x18000ed6f  mov     r9d, ebx
0x18000ed72  call    WPP_SF_D
0x18000ed77  jmp     short loc_18000EDB5
0x18000ed79  mov     r9d, [rsp+2278h+OutBuffer]
0x18000ed7e  cmp     r9d, 1
0x18000ed82  jnz     short loc_18000ED8E
0x18000ed84  mov     eax, [rsp+2278h+var_2220]
0x18000ed88  xor     ebx, ebx
0x18000ed8a  mov     [rsi], eax
0x18000ed8c  jmp     short loc_18000EDB5
0x18000ed8e  mov     ebx, 57h ; 'W'
0x18000ed93  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed9a  lea     rax, WPP_GLOBAL_Control
0x18000eda1  cmp     rcx, rax
0x18000eda4  jz      short loc_18000EDB5
0x18000eda6  test    byte ptr [rcx+1Ch], 1
0x18000edaa  jz      short loc_18000EDB5
0x18000edac  mov     rcx, [rcx+10h]
0x18000edb0  call    WPP_SF_DD
0x18000edb5  mov     rcx, rdi; hObject
0x18000edb8  call    cs:__imp_CloseHandle
0x18000edbe  mov     eax, ebx
0x18000edc0  mov     rcx, [rsp+2278h+var_18]
0x18000edc8  xor     rcx, rsp; StackCookie
0x18000edcb  call    __security_check_cookie
0x18000edd0  lea     r11, [rsp+2278h+var_8]
0x18000edd8  mov     rbx, [r11+20h]
0x18000eddc  mov     rsi, [r11+28h]
0x18000ede0  mov     rsp, r11
0x18000ede3  pop     rdi
0x18000ede4  retn
```
