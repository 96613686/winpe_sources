# TraceVerifyFileIsNotALinkA(x,x)

- ea: `0x10004ab6`
- end: `0x10004b9c`
- name: `_TraceVerifyFileIsNotALinkA@8`
- size: `230`
- prototype: `int __thiscall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x10006fd6`
- `0x100075de`

## callees

- `0x10003c20`
- `0x10004ab6`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x10004b6f`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x10004b6f`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x10004ae8`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x10004ae8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleA` at `0x10004b1f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleA` at `0x10004b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004b92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004b92`

## pseudocode

```c
DWORD __fastcall TraceVerifyFileIsNotALinkA(HANDLE hFile, const char *a2)
{
  int v2; // ebx
  int v3; // esi
  DWORD FinalPathNameByHandleA; // eax
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [esp+14h] [ebp-13Ch] BYREF
  CHAR szFilePath[260]; // [esp+48h] [ebp-108h] BYREF

  v2 = 0;
  v3 = 0;
  if ( !GetFileInformationByHandle(hFile, &FileInformation)
    || (FileInformation.dwFileAttributes & 0x400) != 0
    || FileInformation.nNumberOfLinks > 1 )
  {
    return 161;
  }
  FinalPathNameByHandleA = GetFinalPathNameByHandleA(hFile, szFilePath, 0x104u, 0);
  if ( !FinalPathNameByHandleA || FinalPathNameByHandleA > 0x104 )
    return GetLastError();
  if ( FinalPathNameByHandleA >= 4 )
  {
    if ( szFilePath[0] == 92 && szFilePath[1] == 92 && szFilePath[2] == 63 && szFilePath[3] == 92 )
      v2 = 4;
    else
      v2 = 0;
  }
  if ( __strnicmp(a2, &szFilePath[v2], 260 - v2) )
    return 161;
  return v3;
}

```

## disassembly

```asm
0x10004ab6  mov     edi, edi
0x10004ab8  push    ebp
0x10004ab9  mov     ebp, esp
0x10004abb  sub     esp, 144h
0x10004ac1  mov     eax, ___security_cookie
0x10004ac6  xor     eax, ebp
0x10004ac8  mov     [ebp+var_4], eax
0x10004acb  push    ebx
0x10004acc  push    esi
0x10004acd  mov     eax, ecx
0x10004acf  mov     [ebp+String1], edx
0x10004ad5  push    edi
0x10004ad6  lea     ecx, [ebp+FileInformation]
0x10004adc  mov     [ebp+hFile], eax
0x10004ae2  push    ecx; lpFileInformation
0x10004ae3  push    eax; hFile
0x10004ae4  xor     ebx, ebx
0x10004ae6  xor     esi, esi
0x10004ae8  call    ds:__imp__GetFileInformationByHandle@8; GetFileInformationByHandle(x,x)
0x10004aee  test    eax, eax
0x10004af0  jz      loc_10004B7C
0x10004af6  test    [ebp+FileInformation.dwFileAttributes], 400h
0x10004b00  jnz     short loc_10004B7C
0x10004b02  cmp     [ebp+FileInformation.nNumberOfLinks], 1
0x10004b09  ja      short loc_10004B7C
0x10004b0b  push    esi; dwFlags
0x10004b0c  mov     edi, 104h
0x10004b11  lea     eax, [ebp+szFilePath]
0x10004b17  push    edi; cchFilePath
0x10004b18  push    eax; lpszFilePath
0x10004b19  push    [ebp+hFile]; hFile
0x10004b1f  call    ds:__imp__GetFinalPathNameByHandleA@16; GetFinalPathNameByHandleA(x,x,x,x)
0x10004b25  test    eax, eax
0x10004b27  jz      short loc_10004B92
0x10004b29  cmp     eax, edi
0x10004b2b  ja      short loc_10004B92
0x10004b2d  cmp     eax, 4
0x10004b30  jb      short loc_10004B5D
0x10004b32  cmp     [ebp+szFilePath], 5Ch ; '\'
0x10004b39  jnz     short loc_10004B5B
0x10004b3b  cmp     [ebp+var_107], 5Ch ; '\'
0x10004b42  jnz     short loc_10004B5B
0x10004b44  cmp     [ebp+var_106], 3Fh ; '?'
0x10004b4b  jnz     short loc_10004B5B
0x10004b4d  cmp     [ebp+var_105], 5Ch ; '\'
0x10004b54  jnz     short loc_10004B5B
0x10004b56  push    4
0x10004b58  pop     ebx
0x10004b59  jmp     short loc_10004B5D
0x10004b5b  xor     ebx, ebx
0x10004b5d  sub     edi, ebx
0x10004b5f  lea     eax, [ebp+szFilePath]
0x10004b65  push    edi; MaxCount
0x10004b66  add     eax, ebx
0x10004b68  push    eax; String2
0x10004b69  push    [ebp+String1]; String1
0x10004b6f  call    ds:__imp___strnicmp
0x10004b75  add     esp, 0Ch
0x10004b78  test    eax, eax
0x10004b7a  jz      short loc_10004B81
0x10004b7c  mov     esi, 0A1h
0x10004b81  mov     ecx, [ebp+var_4]
0x10004b84  mov     eax, esi
0x10004b86  pop     edi
0x10004b87  pop     esi
0x10004b88  xor     ecx, ebp; StackCookie
0x10004b8a  pop     ebx
0x10004b8b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10004b90  leave
0x10004b91  retn
0x10004b92  call    ds:__imp__GetLastError@0; GetLastError()
0x10004b98  mov     esi, eax
0x10004b9a  jmp     short loc_10004B81
```
