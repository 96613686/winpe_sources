# TraceVerifyFileIsNotALinkA

- ea: `0x180006690`
- end: `0x18000678e`
- name: `TraceVerifyFileIsNotALinkA`
- size: `254`
- prototype: `DWORD __fastcall(HANDLE hFile, char *String1)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x180005f70`
- `0x180006514`

## callees

- `0x180003bb0`
- `0x180006690`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x18000674f`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x18000674f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleA` at `0x180006707`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleA` at `0x180006707`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800066d5`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800066d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006762`

## pseudocode

```c
DWORD __fastcall TraceVerifyFileIsNotALinkA(HANDLE hFile, char *String1)
{
  size_t v4; // rbx
  DWORD FinalPathNameByHandleA; // eax
  CHAR *v6; // rdx
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+20h] [rbp-E0h] BYREF
  CHAR szFilePath[4]; // [rsp+60h] [rbp-A0h] BYREF
  char v10; // [rsp+64h] [rbp-9Ch] BYREF

  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(hFile, &FileInformation)
    || (FileInformation.dwFileAttributes & 0x400) != 0
    || FileInformation.nNumberOfLinks > 1 )
  {
    return 161;
  }
  v4 = 260;
  FinalPathNameByHandleA = GetFinalPathNameByHandleA(hFile, szFilePath, 0x104u, 0);
  if ( FinalPathNameByHandleA - 1 > 0x103 )
    return GetLastError();
  if ( FinalPathNameByHandleA >= 4
    && szFilePath[0] == 92
    && szFilePath[1] == 92
    && szFilePath[2] == 63
    && szFilePath[3] == 92 )
  {
    v4 = 256;
    v6 = &v10;
  }
  else
  {
    v6 = szFilePath;
  }
  return _strnicmp(String1, v6, v4) != 0 ? 0xA1 : 0;
}

```

## disassembly

```asm
0x180006690  mov     [rsp-8+arg_10], rbx
0x180006695  push    rbp
0x180006696  push    rsi
0x180006697  push    rdi
0x180006698  lea     rbp, [rsp-80h]
0x18000669d  sub     rsp, 180h
0x1800066a4  mov     rax, cs:__security_cookie
0x1800066ab  xor     rax, rsp
0x1800066ae  mov     [rbp+90h+var_20], rax
0x1800066b2  xorps   xmm0, xmm0
0x1800066b5  mov     rsi, rdx
0x1800066b8  xor     eax, eax
0x1800066ba  lea     rdx, [rsp+190h+FileInformation]; lpFileInformation
0x1800066bf  movups  xmmword ptr [rsp+190h+FileInformation.dwFileAttributes], xmm0
0x1800066c4  mov     [rsp+190h+FileInformation.nFileIndexLow], eax
0x1800066c8  mov     rdi, rcx
0x1800066cb  movups  xmmword ptr [rsp+190h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800066d0  movups  xmmword ptr [rsp+190h+FileInformation.nFileSizeHigh], xmm0
0x1800066d5  call    cs:__imp_GetFileInformationByHandle
0x1800066db  test    eax, eax
0x1800066dd  jz      loc_18000676A
0x1800066e3  test    [rsp+190h+FileInformation.dwFileAttributes], 400h
0x1800066eb  jnz     short loc_18000676A
0x1800066ed  cmp     [rsp+190h+FileInformation.nNumberOfLinks], 1
0x1800066f2  ja      short loc_18000676A
0x1800066f4  mov     ebx, 104h
0x1800066f9  lea     rdx, [rsp+190h+szFilePath]; lpszFilePath
0x1800066fe  mov     r8d, ebx; cchFilePath
0x180006701  xor     r9d, r9d; dwFlags
0x180006704  mov     rcx, rdi; hFile
0x180006707  call    cs:__imp_GetFinalPathNameByHandleA
0x18000670d  lea     ecx, [rax-1]
0x180006710  cmp     ecx, 103h
0x180006716  ja      short loc_180006762
0x180006718  cmp     eax, 4
0x18000671b  jb      short loc_180006744
0x18000671d  mov     al, 5Ch ; '\'
0x18000671f  cmp     [rsp+190h+szFilePath], al
0x180006723  jnz     short loc_180006744
0x180006725  cmp     [rsp+190h+var_12F], al
0x180006729  jnz     short loc_180006744
0x18000672b  cmp     [rsp+190h+var_12E], 3Fh ; '?'
0x180006730  jnz     short loc_180006744
0x180006732  cmp     [rsp+190h+var_12D], al
0x180006736  jnz     short loc_180006744
0x180006738  mov     ebx, 100h
0x18000673d  lea     rdx, [rsp+190h+var_12C]
0x180006742  jmp     short loc_180006749
0x180006744  lea     rdx, [rsp+190h+szFilePath]; String2
0x180006749  mov     r8, rbx; MaxCount
0x18000674c  mov     rcx, rsi; String1
0x18000674f  call    cs:__imp__strnicmp
0x180006755  neg     eax
0x180006757  mov     eax, 0A1h
0x18000675c  sbb     ecx, ecx
0x18000675e  and     eax, ecx
0x180006760  jmp     short loc_18000676F
0x180006762  call    cs:__imp_GetLastError
0x180006768  jmp     short loc_18000676F
0x18000676a  mov     eax, 0A1h
0x18000676f  mov     rcx, [rbp+90h+var_20]
0x180006773  xor     rcx, rsp; StackCookie
0x180006776  call    __security_check_cookie
0x18000677b  mov     rbx, [rsp+190h+arg_10]
0x180006783  add     rsp, 180h
0x18000678a  pop     rdi
0x18000678b  pop     rsi
0x18000678c  pop     rbp
0x18000678d  retn
```
