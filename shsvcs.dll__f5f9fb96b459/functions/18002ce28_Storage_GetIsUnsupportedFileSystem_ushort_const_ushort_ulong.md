# Storage::_GetIsUnsupportedFileSystem(ushort const *,ushort *,ulong)

- ea: `0x18002ce28`
- end: `0x18002cf88`
- name: `?_GetIsUnsupportedFileSystem@Storage@@YAJPEBGPEAGK@Z`
- size: `352`
- prototype: `__int64 __fastcall(Storage *this, LPWSTR lpWideCharStr, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18002d4d8`

## callees

- `0x1800140f0`
- `0x18001951c`
- `0x18001afa8`
- `0x18002ce28`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cf54`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002cf36`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002cf36`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002cf16`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002cf16`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002cec4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002cec4`

## pseudocode

```c
__int64 __fastcall Storage::_GetIsUnsupportedFileSystem(Storage *this, LPWSTR lpWideCharStr, unsigned __int16 *a3)
{
  int Error; // ebx
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  HANDLE FileW; // rdi
  DWORD BytesReturned; // [rsp+40h] [rbp-C8h] BYREF
  __int64 OutBuffer; // [rsp+48h] [rbp-C0h] BYREF
  char v11; // [rsp+50h] [rbp-B8h]
  WCHAR FileName[64]; // [rsp+60h] [rbp-A8h] BYREF

  Error = StringCchCopyW(FileName, 0x40u, (const unsigned __int16 *)this);
  if ( Error >= 0 )
  {
    v5 = -1;
    do
      ++v5;
    while ( FileName[v5] );
    if ( v5 && FileName[v5 - 1] == 92 )
    {
      v6 = 2 * v5 - 2;
      if ( v6 >= 0x80 )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)FileName + v6) = 0;
    }
    FileW = CreateFileW(FileName, 0x1000A0u, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      return (unsigned int)ResultFromKnownLastError();
    }
    else
    {
      OutBuffer = 0;
      v11 = 0;
      BytesReturned = 0;
      if ( DeviceIoControl(FileW, 0x9024Cu, 0, 0, &OutBuffer, 9u, &BytesReturned, 0)
        && MultiByteToWideChar(0, 1u, (LPCCH)&OutBuffer, 9, lpWideCharStr, 9) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
      }
      CloseHandle(FileW);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002ce28  mov     [rsp+arg_10], rbx
0x18002ce2d  push    rbp
0x18002ce2e  push    rsi
0x18002ce2f  push    rdi
0x18002ce30  sub     rsp, 0F0h
0x18002ce37  mov     rax, cs:__security_cookie
0x18002ce3e  xor     rax, rsp
0x18002ce41  mov     [rsp+108h+var_28], rax
0x18002ce49  mov     rsi, rdx
0x18002ce4c  mov     r8, rcx; unsigned __int16 *
0x18002ce4f  mov     edx, 40h ; '@'; unsigned __int64
0x18002ce54  lea     rcx, [rsp+108h+FileName]; unsigned __int16 *
0x18002ce59  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ce5e  xor     ebp, ebp
0x18002ce60  mov     ebx, eax
0x18002ce62  test    eax, eax
0x18002ce64  js      loc_18002CF63
0x18002ce6a  lea     rcx, [rsp+108h+FileName]
0x18002ce6f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ce73  inc     rax
0x18002ce76  cmp     [rcx+rax*2], bp
0x18002ce7a  jnz     short loc_18002CE73
0x18002ce7c  test    rax, rax
0x18002ce7f  jz      short loc_18002CEA3
0x18002ce81  cmp     [rsp+rax*2+108h+var_AA], 5Ch ; '\'
0x18002ce87  jnz     short loc_18002CEA3
0x18002ce89  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18002ce91  cmp     rcx, 80h
0x18002ce98  jnb     loc_18002CF44
0x18002ce9e  mov     [rsp+rcx+108h+FileName], bp
0x18002cea3  mov     [rsp+108h+hTemplateFile], rbp; hTemplateFile
0x18002cea8  lea     rcx, [rsp+108h+FileName]; lpFileName
0x18002cead  mov     r8d, 3; dwShareMode
0x18002ceb3  mov     [rsp+108h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x18002ceb7  xor     r9d, r9d; lpSecurityAttributes
0x18002ceba  mov     [rsp+108h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002cebf  mov     edx, 1000A0h; dwDesiredAccess
0x18002cec4  call    cs:__imp_CreateFileW
0x18002ceca  mov     rdi, rax
0x18002cecd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ced1  jz      loc_18002CF5C
0x18002ced7  xor     eax, eax
0x18002ced9  mov     [rsp+108h+lpOverlapped], rbp; lpOverlapped
0x18002cede  mov     [rsp+108h+OutBuffer], rax
0x18002cee3  mov     ebx, 9
0x18002cee8  mov     [rsp+108h+var_B8], al
0x18002ceec  xor     r9d, r9d; nInBufferSize
0x18002ceef  lea     rax, [rsp+108h+BytesReturned]
0x18002cef4  mov     [rsp+108h+BytesReturned], ebp
0x18002cef8  mov     [rsp+108h+hTemplateFile], rax; lpBytesReturned
0x18002cefd  xor     r8d, r8d; lpInBuffer
0x18002cf00  lea     rax, [rsp+108h+OutBuffer]
0x18002cf05  mov     [rsp+108h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x18002cf09  mov     edx, 9024Ch; dwIoControlCode
0x18002cf0e  mov     qword ptr [rsp+108h+dwCreationDisposition], rax; lpOutBuffer
0x18002cf13  mov     rcx, rdi; hDevice
0x18002cf16  call    cs:__imp_DeviceIoControl
0x18002cf1c  test    eax, eax
0x18002cf1e  jz      short loc_18002CF4A
0x18002cf20  mov     [rsp+108h+dwFlagsAndAttributes], ebx; cchWideChar
0x18002cf24  lea     r8, [rsp+108h+OutBuffer]; lpMultiByteStr
0x18002cf29  mov     r9d, ebx; cbMultiByte
0x18002cf2c  mov     qword ptr [rsp+108h+dwCreationDisposition], rsi; lpWideCharStr
0x18002cf31  lea     edx, [rbx-8]; dwFlags
0x18002cf34  xor     ecx, ecx; CodePage
0x18002cf36  call    cs:__imp_MultiByteToWideChar
0x18002cf3c  test    eax, eax
0x18002cf3e  jz      short loc_18002CF4A
0x18002cf40  mov     ebx, ebp
0x18002cf42  jmp     short loc_18002CF51
0x18002cf44  call    __report_rangecheckfailure
0x18002cf4a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002cf4f  mov     ebx, eax
0x18002cf51  mov     rcx, rdi; hObject
0x18002cf54  call    cs:__imp_CloseHandle
0x18002cf5a  jmp     short loc_18002CF63
0x18002cf5c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002cf61  mov     ebx, eax
0x18002cf63  mov     eax, ebx
0x18002cf65  mov     rcx, [rsp+108h+var_28]
0x18002cf6d  xor     rcx, rsp; StackCookie
0x18002cf70  call    __security_check_cookie
0x18002cf75  mov     rbx, [rsp+108h+arg_10]
0x18002cf7d  add     rsp, 0F0h
0x18002cf84  pop     rdi
0x18002cf85  pop     rsi
0x18002cf86  pop     rbp
0x18002cf87  retn
```
