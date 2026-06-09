# TraceMoveClientFileW(x)

- ea: `0x100080a7`
- end: `0x100081d8`
- name: `_TraceMoveClientFileW@4`
- size: `305`
- prototype: `signed int __thiscall(int this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x100081de`

## callees

- `0x100036b5`
- `0x10003c20`
- `0x10004ef5`
- `0x10006fac`
- `0x10007954`
- `0x100080a7`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100081a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100081a4`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x10008191`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x10008191`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x100080d8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x100080d8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1000815e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1000815e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100080e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000819b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100081ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100080e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1000819b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100081ac`

## pseudocode

```c
signed int __thiscall TraceMoveClientFileW(int this)
{
  DWORD FullPathNameW; // eax
  signed int result; // eax
  HANDLE FileW; // eax
  void *v5; // edi
  DWORD IsNotALinkW; // esi
  DWORD LastError; // eax
  size_t v8; // [esp+0h] [ebp-21Ch]
  size_t v9; // [esp+0h] [ebp-21Ch]
  size_t v10; // [esp+0h] [ebp-21Ch]
  const wchar_t *v11; // [esp+4h] [ebp-218h]
  const wchar_t *v12; // [esp+4h] [ebp-218h]
  const wchar_t *v13; // [esp+4h] [ebp-218h]
  char FileInformation; // [esp+Fh] [ebp-20Dh] BYREF
  WCHAR Buffer[260]; // [esp+10h] [ebp-20Ch] BYREF

  FullPathNameW = GetFullPathNameW((LPCWSTR)(this + 514), 0x104u, Buffer, 0);
  if ( !FullPathNameW )
    return GetLastError();
  if ( FullPathNameW >= 0x104 )
    return 161;
  result = StringCchCatW((STRSAFE_LPWSTR)L"\\", v8, v11);
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatW((STRSAFE_LPWSTR)(this + 104), v9, v12);
  if ( result < 0 )
    return (unsigned __int16)result;
  result = StringCchCatW((STRSAFE_LPWSTR)L".LOG", v10, v13);
  if ( result < 0 )
    return (unsigned __int16)result;
  TraceCloseClientFileW(this);
  FileW = CreateFileW(Buffer, 0x10000u, 3u, 0, 3u, 0, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1 )
  {
    LastError = GetLastError();
    IsNotALinkW = 0;
    if ( LastError != 2 )
      IsNotALinkW = LastError;
  }
  else
  {
    IsNotALinkW = TraceVerifyFileIsNotALinkW(FileW);
    if ( !IsNotALinkW )
    {
      FileInformation = 1;
      if ( !SetFileInformationByHandle(v5, FileDispositionInfo, &FileInformation, 1u) )
        IsNotALinkW = GetLastError();
    }
    CloseHandle(v5);
  }
  if ( IsNotALinkW )
    return IsNotALinkW;
  else
    return TraceCreateClientFileW(this);
}

```

## disassembly

```asm
0x100080a7  mov     edi, edi
0x100080a9  push    ebp
0x100080aa  mov     ebp, esp
0x100080ac  sub     esp, 210h
0x100080b2  mov     eax, ___security_cookie
0x100080b7  xor     eax, ebp
0x100080b9  mov     [ebp+var_4], eax
0x100080bc  push    ebx
0x100080bd  push    esi; pszSrc
0x100080be  push    edi; cchDest
0x100080bf  mov     ebx, ecx
0x100080c1  lea     eax, [ebp+Buffer]
0x100080c7  xor     edi, edi
0x100080c9  mov     esi, 104h
0x100080ce  push    edi; lpFilePart
0x100080cf  push    eax; lpBuffer
0x100080d0  push    esi; nBufferLength
0x100080d1  lea     eax, [ebx+202h]
0x100080d7  push    eax; lpFileName
0x100080d8  call    ds:__imp__GetFullPathNameW@16; GetFullPathNameW(x,x,x,x)
0x100080de  test    eax, eax
0x100080e0  jnz     short loc_100080ED
0x100080e2  call    ds:__imp__GetLastError@0; GetLastError()
0x100080e8  jmp     loc_100081C9
0x100080ed  cmp     eax, esi
0x100080ef  jb      short loc_100080FB
0x100080f1  mov     eax, 0A1h
0x100080f6  jmp     loc_100081C9
0x100080fb  push    offset asc_10001298; "\\"
0x10008100  mov     edx, esi
0x10008102  lea     ecx, [ebp+Buffer]
0x10008108  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000810d  test    eax, eax
0x1000810f  jns     short loc_10008119
0x10008111  movzx   eax, ax
0x10008114  jmp     loc_100081C9
0x10008119  lea     eax, [ebx+68h]
0x1000811c  mov     edx, esi
0x1000811e  push    eax; pszDest
0x1000811f  lea     ecx, [ebp+Buffer]
0x10008125  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000812a  test    eax, eax
0x1000812c  js      short loc_10008111
0x1000812e  push    offset aLog; ".LOG"
0x10008133  mov     edx, esi
0x10008135  lea     ecx, [ebp+Buffer]
0x1000813b  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10008140  test    eax, eax
0x10008142  js      short loc_10008111
0x10008144  mov     ecx, ebx
0x10008146  call    _TraceCloseClientFileW@4; TraceCloseClientFileW(x)
0x1000814b  push    edi; hTemplateFile
0x1000814c  push    edi; dwFlagsAndAttributes
0x1000814d  push    3; dwCreationDisposition
0x1000814f  push    edi; lpSecurityAttributes
0x10008150  push    3; dwShareMode
0x10008152  push    10000h; dwDesiredAccess
0x10008157  lea     eax, [ebp+Buffer]
0x1000815d  push    eax; lpFileName
0x1000815e  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x10008164  mov     edi, eax
0x10008166  cmp     edi, 0FFFFFFFFh
0x10008169  jz      short loc_100081AC
0x1000816b  lea     edx, [ebp+Buffer]
0x10008171  mov     ecx, edi; hFile
0x10008173  call    _TraceVerifyFileIsNotALinkW@8; TraceVerifyFileIsNotALinkW(x,x)
0x10008178  mov     esi, eax
0x1000817a  test    esi, esi
0x1000817c  jnz     short loc_100081A3
0x1000817e  push    1; dwBufferSize
0x10008180  lea     eax, [ebp+FileInformation]
0x10008186  mov     [ebp+FileInformation], 1
0x1000818d  push    eax; lpFileInformation
0x1000818e  push    4; FileInformationClass
0x10008190  push    edi; hFile
0x10008191  call    ds:__imp__SetFileInformationByHandle@16; SetFileInformationByHandle(x,x,x,x)
0x10008197  test    eax, eax
0x10008199  jnz     short loc_100081A3
0x1000819b  call    ds:__imp__GetLastError@0; GetLastError()
0x100081a1  mov     esi, eax
0x100081a3  push    edi; hObject
0x100081a4  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100081aa  jmp     short loc_100081BA
0x100081ac  call    ds:__imp__GetLastError@0; GetLastError()
0x100081b2  xor     esi, esi
0x100081b4  cmp     eax, 2
0x100081b7  cmovnz  esi, eax
0x100081ba  test    esi, esi
0x100081bc  jz      short loc_100081C2
0x100081be  mov     eax, esi
0x100081c0  jmp     short loc_100081C9
0x100081c2  mov     ecx, ebx
0x100081c4  call    _TraceCreateClientFileW@4; TraceCreateClientFileW(x)
0x100081c9  mov     ecx, [ebp+var_4]
0x100081cc  pop     edi
0x100081cd  pop     esi
0x100081ce  xor     ecx, ebp; StackCookie
0x100081d0  pop     ebx
0x100081d1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100081d6  leave
0x100081d7  retn
```
