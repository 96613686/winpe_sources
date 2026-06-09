# TraceMoveClientFileA(x)

- ea: `0x100075de`
- end: `0x1000770f`
- name: `_TraceMoveClientFileA@4`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x100077c0`

## callees

- `0x10002c90`
- `0x10003c20`
- `0x10004ab6`
- `0x10006fac`
- `0x10006fd6`
- `0x100075de`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100076db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100076db`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1000760f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1000760f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x100076c8`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x100076c8`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x10007695`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x10007695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10007619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100076d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100076e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10007619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100076d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100076e3`

## pseudocode

```c
HRESULT __thiscall TraceMoveClientFileA(int this)
{
  DWORD FullPathNameA; // eax
  HRESULT result; // eax
  HANDLE FileA; // eax
  void *v5; // edi
  DWORD IsNotALinkA; // esi
  DWORD LastError; // eax
  size_t v8; // [esp+0h] [ebp-118h]
  size_t v9; // [esp+0h] [ebp-118h]
  size_t v10; // [esp+0h] [ebp-118h]
  const char *v11; // [esp+4h] [ebp-114h]
  const char *v12; // [esp+4h] [ebp-114h]
  const char *v13; // [esp+4h] [ebp-114h]
  char FileInformation; // [esp+Fh] [ebp-109h] BYREF
  CHAR Buffer[260]; // [esp+10h] [ebp-108h] BYREF

  FullPathNameA = GetFullPathNameA((LPCSTR)(this + 252), 0x104u, Buffer, 0);
  if ( !FullPathNameA )
    return GetLastError();
  if ( FullPathNameA >= 0x104 )
    return 161;
  result = StringCchCatA((STRSAFE_LPSTR)"\\", v8, v11);
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatA((STRSAFE_LPSTR)(this + 40), v9, v12);
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatA((STRSAFE_LPSTR)".LOG", v10, v13);
  if ( result < 0 )
    return (unsigned __int16)result;
  TraceCloseClientFileW(this);
  FileA = CreateFileA(Buffer, 0x10000u, 3u, 0, 3u, 0, 0);
  v5 = FileA;
  if ( FileA == (HANDLE)-1 )
  {
    LastError = GetLastError();
    IsNotALinkA = 0;
    if ( LastError != 2 )
      IsNotALinkA = LastError;
  }
  else
  {
    IsNotALinkA = TraceVerifyFileIsNotALinkA(FileA);
    if ( !IsNotALinkA )
    {
      FileInformation = 1;
      if ( !SetFileInformationByHandle(v5, FileDispositionInfo, &FileInformation, 1u) )
        IsNotALinkA = GetLastError();
    }
    CloseHandle(v5);
  }
  if ( IsNotALinkA )
    return IsNotALinkA;
  else
    return TraceCreateClientFileA(this);
}

```

## disassembly

```asm
0x100075de  mov     edi, edi
0x100075e0  push    ebp
0x100075e1  mov     ebp, esp
0x100075e3  sub     esp, 10Ch
0x100075e9  mov     eax, ___security_cookie
0x100075ee  xor     eax, ebp
0x100075f0  mov     [ebp+var_4], eax
0x100075f3  push    ebx
0x100075f4  push    esi; pszSrc
0x100075f5  push    edi; cchDest
0x100075f6  mov     ebx, ecx
0x100075f8  lea     eax, [ebp+Buffer]
0x100075fe  xor     edi, edi
0x10007600  mov     esi, 104h
0x10007605  push    edi; lpFilePart
0x10007606  push    eax; lpBuffer
0x10007607  push    esi; nBufferLength
0x10007608  lea     eax, [ebx+0FCh]
0x1000760e  push    eax; lpFileName
0x1000760f  call    ds:__imp__GetFullPathNameA@16; GetFullPathNameA(x,x,x,x)
0x10007615  test    eax, eax
0x10007617  jnz     short loc_10007624
0x10007619  call    ds:__imp__GetLastError@0; GetLastError()
0x1000761f  jmp     loc_10007700
0x10007624  cmp     eax, esi
0x10007626  jb      short loc_10007632
0x10007628  mov     eax, 0A1h
0x1000762d  jmp     loc_10007700
0x10007632  push    offset asc_10001294; "\\"
0x10007637  mov     edx, esi
0x10007639  lea     ecx, [ebp+Buffer]
0x1000763f  call    _StringCchCatA@12; StringCchCatA(x,x,x)
0x10007644  test    eax, eax
0x10007646  jns     short loc_10007650
0x10007648  movzx   eax, ax
0x1000764b  jmp     loc_10007700
0x10007650  lea     eax, [ebx+28h]
0x10007653  mov     edx, esi
0x10007655  push    eax; pszDest
0x10007656  lea     ecx, [ebp+Buffer]
0x1000765c  call    _StringCchCatA@12; StringCchCatA(x,x,x)
0x10007661  test    eax, eax
0x10007663  js      short loc_10007648
0x10007665  push    offset aLog_0; ".LOG"
0x1000766a  mov     edx, esi
0x1000766c  lea     ecx, [ebp+Buffer]
0x10007672  call    _StringCchCatA@12; StringCchCatA(x,x,x)
0x10007677  test    eax, eax
0x10007679  js      short loc_10007648
0x1000767b  mov     ecx, ebx
0x1000767d  call    _TraceCloseClientFileW@4; TraceCloseClientFileW(x)
0x10007682  push    edi; hTemplateFile
0x10007683  push    edi; dwFlagsAndAttributes
0x10007684  push    3; dwCreationDisposition
0x10007686  push    edi; lpSecurityAttributes
0x10007687  push    3; dwShareMode
0x10007689  push    10000h; dwDesiredAccess
0x1000768e  lea     eax, [ebp+Buffer]
0x10007694  push    eax; lpFileName
0x10007695  call    ds:__imp__CreateFileA@28; CreateFileA(x,x,x,x,x,x,x)
0x1000769b  mov     edi, eax
0x1000769d  cmp     edi, 0FFFFFFFFh
0x100076a0  jz      short loc_100076E3
0x100076a2  lea     edx, [ebp+Buffer]
0x100076a8  mov     ecx, edi; hFile
0x100076aa  call    _TraceVerifyFileIsNotALinkA@8; TraceVerifyFileIsNotALinkA(x,x)
0x100076af  mov     esi, eax
0x100076b1  test    esi, esi
0x100076b3  jnz     short loc_100076DA
0x100076b5  push    1; dwBufferSize
0x100076b7  lea     eax, [ebp+FileInformation]
0x100076bd  mov     [ebp+FileInformation], 1
0x100076c4  push    eax; lpFileInformation
0x100076c5  push    4; FileInformationClass
0x100076c7  push    edi; hFile
0x100076c8  call    ds:__imp__SetFileInformationByHandle@16; SetFileInformationByHandle(x,x,x,x)
0x100076ce  test    eax, eax
0x100076d0  jnz     short loc_100076DA
0x100076d2  call    ds:__imp__GetLastError@0; GetLastError()
0x100076d8  mov     esi, eax
0x100076da  push    edi; hObject
0x100076db  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100076e1  jmp     short loc_100076F1
0x100076e3  call    ds:__imp__GetLastError@0; GetLastError()
0x100076e9  xor     esi, esi
0x100076eb  cmp     eax, 2
0x100076ee  cmovnz  esi, eax
0x100076f1  test    esi, esi
0x100076f3  jz      short loc_100076F9
0x100076f5  mov     eax, esi
0x100076f7  jmp     short loc_10007700
0x100076f9  mov     ecx, ebx
0x100076fb  call    _TraceCreateClientFileA@4; TraceCreateClientFileA(x)
0x10007700  mov     ecx, [ebp+var_4]
0x10007703  pop     edi
0x10007704  pop     esi
0x10007705  xor     ecx, ebp; StackCookie
0x10007707  pop     ebx
0x10007708  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000770d  leave
0x1000770e  retn
```
