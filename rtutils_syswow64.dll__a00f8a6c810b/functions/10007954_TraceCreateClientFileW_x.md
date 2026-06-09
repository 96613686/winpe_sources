# TraceCreateClientFileW(x)

- ea: `0x10007954`
- end: `0x10007af3`
- name: `_TraceCreateClientFileW@4`
- size: `415`
- prototype: `HRESULT __thiscall(int this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x100037bd`
- `0x100080a7`

## callees

- `0x100036b5`
- `0x10003c20`
- `0x10004ba2`
- `0x10004de8`
- `0x10004ef5`
- `0x10007954`
- `0x10008372`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10007a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10007aa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10007ad6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10007a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10007aa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10007ad6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10007ab9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x10007ab9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x10007aa1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x10007aa1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x10007997`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x10007997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100079a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10007a6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100079a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10007a6c`
- `api-ms-win-core-file-l1-2-5!CreateFile3` at `0x10007a64`
- `api-ms-win-core-file-l1-2-5!CreateFile3` at `0x10007a64`

## pseudocode

```c
HRESULT __thiscall TraceCreateClientFileW(int this)
{
  DWORD FullPathNameW; // eax
  HRESULT result; // eax
  HRESULT v4; // eax
  unsigned __int16 v5; // si
  HRESULT v6; // eax
  void *File3; // esi
  DWORD LastError; // edi
  int IsNotALinkW; // ebx
  size_t v10; // [esp+0h] [ebp-240h]
  size_t v11; // [esp+0h] [ebp-240h]
  size_t v12; // [esp+0h] [ebp-240h]
  const wchar_t *v13; // [esp+4h] [ebp-23Ch]
  const wchar_t *v14; // [esp+4h] [ebp-23Ch]
  const wchar_t *v15; // [esp+4h] [ebp-23Ch]
  char FileInformation; // [esp+Fh] [ebp-231h] BYREF
  HANDLE hObject; // [esp+10h] [ebp-230h] BYREF
  int v18; // [esp+14h] [ebp-22Ch]
  _DWORD v19[6]; // [esp+18h] [ebp-228h] BYREF
  WCHAR Buffer[262]; // [esp+30h] [ebp-210h] BYREF

  v18 = this;
  memset(v19, 0, sizeof(v19));
  FullPathNameW = GetFullPathNameW((LPCWSTR)(this + 514), 0x104u, Buffer, 0);
  if ( !FullPathNameW )
    return GetLastError();
  if ( FullPathNameW >= 0x104 )
    return 161;
  result = TraceVerifyDirectoryPathW(Buffer);
  if ( !result )
  {
    result = StringCchCatW((STRSAFE_LPWSTR)L"\\", v10, v13);
    if ( result >= 0 )
    {
      hObject = (HANDLE)-1;
      result = CreateTracingDirectoryW(Buffer, &hObject);
      if ( !result )
      {
        v4 = StringCchCatW((STRSAFE_LPWSTR)(this + 104), v11, v14);
        v5 = v4;
        if ( v4 < 0 || (v6 = StringCchCatW((STRSAFE_LPWSTR)L".LOG", v12, v15), v5 = v6, v6 < 0) )
        {
          CloseHandle(hObject);
          return v5;
        }
        else
        {
          v19[0] = 24;
          v19[2] = 3211392;
          File3 = (void *)CreateFile3(Buffer, -1073676288, 1, 4, v19);
          LastError = GetLastError();
          if ( File3 != (void *)-1 )
          {
            IsNotALinkW = TraceVerifyFileIsNotALinkW(File3);
            if ( IsNotALinkW )
            {
              if ( LastError != 183 )
              {
                FileInformation = 1;
                SetFileInformationByHandle(File3, FileDispositionInfo, &FileInformation, 1u);
              }
              CloseHandle(File3);
              LastError = IsNotALinkW;
            }
            else
            {
              SetFilePointer(File3, 0, 0, 2u);
              LastError = WriteUnicodeHeader(File3);
              *(_DWORD *)(v18 + 232) = File3;
            }
          }
          CloseHandle(hObject);
          return LastError;
        }
      }
    }
    else
    {
      return (unsigned __int16)result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x10007954  mov     edi, edi
0x10007956  push    ebp
0x10007957  mov     ebp, esp
0x10007959  and     esp, 0FFFFFFF8h
0x1000795c  sub     esp, 234h
0x10007962  mov     eax, ___security_cookie
0x10007967  xor     eax, esp
0x10007969  mov     [esp+234h+var_4], eax
0x10007970  push    ebx
0x10007971  push    esi; pszSrc
0x10007972  push    edi; cchDest
0x10007973  push    6
0x10007975  mov     ebx, ecx
0x10007977  lea     edi, [esp+244h+var_228]
0x1000797b  pop     ecx
0x1000797c  xor     eax, eax
0x1000797e  mov     [esp+240h+var_22C], ebx
0x10007982  push    eax; lpFilePart
0x10007983  rep stosd
0x10007985  lea     eax, [esp+244h+Buffer]
0x10007989  mov     edi, 104h
0x1000798e  push    eax; lpBuffer
0x1000798f  push    edi; nBufferLength
0x10007990  lea     eax, [ebx+202h]
0x10007996  push    eax; lpFileName
0x10007997  call    ds:__imp__GetFullPathNameW@16; GetFullPathNameW(x,x,x,x)
0x1000799d  test    eax, eax
0x1000799f  jnz     short loc_100079AC
0x100079a1  call    ds:__imp__GetLastError@0; GetLastError()
0x100079a7  jmp     loc_10007ADE
0x100079ac  cmp     eax, edi
0x100079ae  jb      short loc_100079BA
0x100079b0  mov     eax, 0A1h
0x100079b5  jmp     loc_10007ADE
0x100079ba  lea     ecx, [esp+240h+Buffer]
0x100079be  call    _TraceVerifyDirectoryPathW@4; TraceVerifyDirectoryPathW(x)
0x100079c3  test    eax, eax
0x100079c5  jnz     loc_10007ADE
0x100079cb  push    offset asc_10001298; "\\"
0x100079d0  mov     edx, edi
0x100079d2  lea     ecx, [esp+244h+Buffer]
0x100079d6  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x100079db  test    eax, eax
0x100079dd  jns     short loc_100079E7
0x100079df  movzx   eax, ax
0x100079e2  jmp     loc_10007ADE
0x100079e7  lea     edx, [esp+240h+hObject]; FileHandle
0x100079eb  mov     [esp+240h+hObject], 0FFFFFFFFh
0x100079f3  lea     ecx, [esp+240h+Buffer]; DosPathName
0x100079f7  call    _CreateTracingDirectoryW@8; CreateTracingDirectoryW(x,x)
0x100079fc  test    eax, eax
0x100079fe  jnz     loc_10007ADE
0x10007a04  lea     eax, [ebx+68h]
0x10007a07  mov     edx, edi
0x10007a09  push    eax; pszDest
0x10007a0a  lea     ecx, [esp+244h+Buffer]
0x10007a0e  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10007a13  mov     esi, eax
0x10007a15  test    esi, esi
0x10007a17  jns     short loc_10007A2B
0x10007a19  push    [esp+240h+hObject]; hObject
0x10007a1d  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10007a23  movzx   eax, si
0x10007a26  jmp     loc_10007ADE
0x10007a2b  push    offset aLog; ".LOG"
0x10007a30  mov     edx, edi
0x10007a32  lea     ecx, [esp+244h+Buffer]
0x10007a36  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10007a3b  mov     esi, eax
0x10007a3d  test    esi, esi
0x10007a3f  js      short loc_10007A19
0x10007a41  lea     eax, [esp+240h+var_228]
0x10007a45  mov     [esp+240h+var_228], 18h
0x10007a4d  push    eax
0x10007a4e  push    4
0x10007a50  push    1
0x10007a52  push    0C0010000h
0x10007a57  lea     eax, [esp+250h+Buffer]
0x10007a5b  mov     [esp+250h+var_220], 310080h
0x10007a63  push    eax
0x10007a64  call    ds:__imp__CreateFile3@20; CreateFile3(x,x,x,x,x)
0x10007a6a  mov     esi, eax
0x10007a6c  call    ds:__imp__GetLastError@0; GetLastError()
0x10007a72  mov     edi, eax
0x10007a74  cmp     esi, 0FFFFFFFFh
0x10007a77  jz      short loc_10007AD2
0x10007a79  lea     edx, [esp+240h+Buffer]
0x10007a7d  mov     ecx, esi; hFile
0x10007a7f  call    _TraceVerifyFileIsNotALinkW@8; TraceVerifyFileIsNotALinkW(x,x)
0x10007a84  mov     ebx, eax
0x10007a86  test    ebx, ebx
0x10007a88  jz      short loc_10007AB2
0x10007a8a  cmp     edi, 0B7h
0x10007a90  jz      short loc_10007AA7
0x10007a92  push    1; dwBufferSize
0x10007a94  lea     eax, [esp+244h+FileInformation]
0x10007a98  mov     [esp+244h+FileInformation], 1
0x10007a9d  push    eax; lpFileInformation
0x10007a9e  push    4; FileInformationClass
0x10007aa0  push    esi; hFile
0x10007aa1  call    ds:__imp__SetFileInformationByHandle@16; SetFileInformationByHandle(x,x,x,x)
0x10007aa7  push    esi; hObject
0x10007aa8  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10007aae  mov     edi, ebx
0x10007ab0  jmp     short loc_10007AD2
0x10007ab2  push    2; dwMoveMethod
0x10007ab4  push    0; lpDistanceToMoveHigh
0x10007ab6  push    0; lDistanceToMove
0x10007ab8  push    esi; hFile
0x10007ab9  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x10007abf  mov     ecx, esi; hFile
0x10007ac1  call    _WriteUnicodeHeader@4; WriteUnicodeHeader(x)
0x10007ac6  mov     ecx, [esp+240h+var_22C]
0x10007aca  mov     edi, eax
0x10007acc  mov     [ecx+0E8h], esi
0x10007ad2  push    [esp+240h+hObject]; hObject
0x10007ad6  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10007adc  mov     eax, edi
0x10007ade  mov     ecx, [esp+240h+var_4]
0x10007ae5  pop     edi
0x10007ae6  pop     esi
0x10007ae7  pop     ebx
0x10007ae8  xor     ecx, esp; StackCookie
0x10007aea  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10007aef  mov     esp, ebp
0x10007af1  pop     ebp
0x10007af2  retn
```
