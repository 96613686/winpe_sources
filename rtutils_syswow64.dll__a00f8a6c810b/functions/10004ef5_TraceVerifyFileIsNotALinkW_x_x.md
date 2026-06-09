# TraceVerifyFileIsNotALinkW(x,x)

- ea: `0x10004ef5`
- end: `0x10004fe0`
- name: `_TraceVerifyFileIsNotALinkW@8`
- size: `235`
- prototype: `DWORD __fastcall(HANDLE hFile, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x10007954`
- `0x100080a7`

## callees

- `0x10003c20`
- `0x10004ef5`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x10004fb3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x10004fb3`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x10004f27`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x10004f27`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x10004f5e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x10004f5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10004fd6`

## pseudocode

```c
DWORD __fastcall TraceVerifyFileIsNotALinkW(HANDLE hFile, int a2)
{
  int v2; // ebx
  int v3; // esi
  DWORD FinalPathNameByHandleW; // eax
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [esp+14h] [ebp-240h] BYREF
  WCHAR szFilePath[260]; // [esp+48h] [ebp-20Ch] BYREF

  v2 = 0;
  v3 = 0;
  if ( !GetFileInformationByHandle(hFile, &FileInformation)
    || (FileInformation.dwFileAttributes & 0x400) != 0
    || FileInformation.nNumberOfLinks > 1 )
  {
    return 161;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, szFilePath, 0x104u, 0);
  if ( !FinalPathNameByHandleW || FinalPathNameByHandleW > 0x104 )
    return GetLastError();
  if ( FinalPathNameByHandleW >= 4 )
  {
    if ( szFilePath[0] == 92 && szFilePath[1] == 92 && szFilePath[2] == 63 && szFilePath[3] == 92 )
      v2 = 4;
    else
      v2 = 0;
  }
  if ( __o__wcsnicmp(a2, &szFilePath[v2], 260 - v2) )
    return 161;
  return v3;
}

```

## disassembly

```asm
0x10004ef5  mov     edi, edi
0x10004ef7  push    ebp
0x10004ef8  mov     ebp, esp
0x10004efa  sub     esp, 248h
0x10004f00  mov     eax, ___security_cookie
0x10004f05  xor     eax, ebp
0x10004f07  mov     [ebp+var_4], eax
0x10004f0a  push    ebx
0x10004f0b  push    esi
0x10004f0c  mov     eax, ecx
0x10004f0e  mov     [ebp+var_248], edx
0x10004f14  push    edi
0x10004f15  lea     ecx, [ebp+FileInformation]
0x10004f1b  mov     [ebp+hFile], eax
0x10004f21  push    ecx; lpFileInformation
0x10004f22  push    eax; hFile
0x10004f23  xor     ebx, ebx
0x10004f25  xor     esi, esi
0x10004f27  call    ds:__imp__GetFileInformationByHandle@8; GetFileInformationByHandle(x,x)
0x10004f2d  test    eax, eax
0x10004f2f  jz      loc_10004FC0
0x10004f35  test    [ebp+FileInformation.dwFileAttributes], 400h
0x10004f3f  jnz     short loc_10004FC0
0x10004f41  cmp     [ebp+FileInformation.nNumberOfLinks], 1
0x10004f48  ja      short loc_10004FC0
0x10004f4a  push    esi; dwFlags
0x10004f4b  mov     edi, 104h
0x10004f50  lea     eax, [ebp+szFilePath]
0x10004f56  push    edi; cchFilePath
0x10004f57  push    eax; lpszFilePath
0x10004f58  push    [ebp+hFile]; hFile
0x10004f5e  call    ds:__imp__GetFinalPathNameByHandleW@16; GetFinalPathNameByHandleW(x,x,x,x)
0x10004f64  test    eax, eax
0x10004f66  jz      short loc_10004FD6
0x10004f68  cmp     eax, edi
0x10004f6a  ja      short loc_10004FD6
0x10004f6c  cmp     eax, 4
0x10004f6f  jb      short loc_10004FA0
0x10004f71  push    5Ch ; '\'
0x10004f73  pop     eax
0x10004f74  cmp     [ebp+szFilePath], ax
0x10004f7b  jnz     short loc_10004F9E
0x10004f7d  cmp     [ebp+var_20A], ax
0x10004f84  jnz     short loc_10004F9E
0x10004f86  cmp     [ebp+var_208], 3Fh ; '?'
0x10004f8e  jnz     short loc_10004F9E
0x10004f90  cmp     [ebp+var_206], ax
0x10004f97  jnz     short loc_10004F9E
0x10004f99  push    4
0x10004f9b  pop     ebx
0x10004f9c  jmp     short loc_10004FA0
0x10004f9e  xor     ebx, ebx
0x10004fa0  sub     edi, ebx
0x10004fa2  lea     eax, [ebp+szFilePath]
0x10004fa8  push    edi
0x10004fa9  lea     eax, [eax+ebx*2]
0x10004fac  push    eax
0x10004fad  push    [ebp+var_248]
0x10004fb3  call    ds:__imp___o__wcsnicmp
0x10004fb9  add     esp, 0Ch
0x10004fbc  test    eax, eax
0x10004fbe  jz      short loc_10004FC5
0x10004fc0  mov     esi, 0A1h
0x10004fc5  mov     ecx, [ebp+var_4]
0x10004fc8  mov     eax, esi
0x10004fca  pop     edi
0x10004fcb  pop     esi
0x10004fcc  xor     ecx, ebp; StackCookie
0x10004fce  pop     ebx
0x10004fcf  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10004fd4  leave
0x10004fd5  retn
0x10004fd6  call    ds:__imp__GetLastError@0; GetLastError()
0x10004fdc  mov     esi, eax
0x10004fde  jmp     short loc_10004FC5
```
