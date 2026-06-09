# GetRawFileVersion(wchar_t const *,ulong *,ulong *)

- ea: `0x140014cac`
- end: `0x140014fea`
- name: `?GetRawFileVersion@@YAJPEB_WPEAK1@Z`
- size: `830`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140014bd0`

## callees

- `0x140002ac0`
- `0x140003e74`
- `0x14000d4cc`
- `0x14000d538`
- `0x140014cac`
- `0x140014ff0`
- `0x14001aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014d66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014fa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014fb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014fa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014fb5`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x140014db0`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x140014db0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140014d57`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140014d57`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140014f79`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140014f79`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140014dfd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140014dfd`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x140014e27`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x140014e27`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x140014e8c`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x140014e8c`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x140014ed8`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x140014ed8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x140014efb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x140014efb`

## pseudocode

```c
__int64 __fastcall GetRawFileVersion(LPCWSTR lpwstrFilename, unsigned int *a2, unsigned int *a3)
{
  void *v4; // rdi
  void *v5; // rbx
  __int64 v6; // rdx
  unsigned int v7; // esi
  HANDLE FileW; // rax
  void *v9; // r13
  signed int LastError; // eax
  __int64 v11; // rdx
  const char *v12; // r9
  __int64 v13; // rdx
  HANDLE FileMappingW; // rax
  unsigned __int64 v15; // rax
  int RawFileVersionFromModule; // r14d
  DWORD FileVersionInfoSize; // eax
  const char *v18; // r9
  DWORD v19; // r12d
  __int64 v20; // rdx
  __int64 v21; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-60h]
  LPCVOID lpBaseAddress; // [rsp+40h] [rbp-40h]
  LPVOID lpBuffer; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v30; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v31; // [rsp+64h] [rbp-1Ch] BYREF
  unsigned int puLen; // [rsp+68h] [rbp-18h] BYREF
  DWORD dwHandle; // [rsp+6Ch] [rbp-14h] BYREF
  LARGE_INTEGER FileSize; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v30 = 0;
  v31 = 0;
  v4 = 0;
  v5 = 0;
  if ( !lpwstrFilename )
  {
    v6 = 100;
LABEL_7:
    v7 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileVersion.cpp",
      (const char *)0x80004003LL,
      dwCreationDisposition);
    return v7;
  }
  if ( !a2 )
  {
    v6 = 101;
    goto LABEL_7;
  }
  if ( !a3 )
  {
    v6 = 102;
    goto LABEL_7;
  }
  FileW = CreateFileW(lpwstrFilename, 0x80000000, 1u, 0, 3u, 0, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v7 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v7 = LastError;
    if ( (v7 & 0x80000000) != 0 )
    {
      if ( v7 == -2147024894 || v7 == -2147024893 )
        goto LABEL_45;
    }
    else
    {
      v7 = -2147418113;
    }
    v11 = 116;
    goto LABEL_20;
  }
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    v13 = 122;
LABEL_25:
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v13,
           (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileVersion.cpp",
           v12);
    goto LABEL_45;
  }
  if ( !FileSize.HighPart )
  {
    FileMappingW = CreateFileMappingW(v9, 0, 2u, 0, 0, 0);
    v4 = FileMappingW;
    if ( !FileMappingW )
    {
      v13 = 127;
      goto LABEL_25;
    }
    v15 = (unsigned __int64)MapViewOfFileEx(FileMappingW, 4u, 0, 0, 0, 0);
    lpBaseAddress = (LPCVOID)v15;
    if ( !v15 )
    {
      v13 = 130;
      goto LABEL_25;
    }
    RawFileVersionFromModule = GetRawFileVersionFromModule((HINSTANCE)(v15 | 1), FileSize.QuadPart, &v30, &v31);
    if ( RawFileVersionFromModule == -2147020580 )
    {
      dwHandle = 0;
      lpBuffer = 0;
      puLen = 0;
      FileVersionInfoSize = GetFileVersionInfoSizeExW(0, lpwstrFilename, &dwHandle);
      v19 = FileVersionInfoSize;
      if ( !FileVersionInfoSize )
      {
        v20 = 149;
LABEL_35:
        v7 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v20,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileVersion.cpp",
               v18);
LABEL_44:
        UnmapViewOfFile(lpBaseAddress);
        goto LABEL_45;
      }
      v5 = SafeSusAllocArray(FileVersionInfoSize, 1u);
      v7 = v5 == 0 ? 0x8007000E : 0;
      if ( !v5 )
      {
        v21 = 150;
LABEL_39:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileVersion.cpp",
          (const char *)v7,
          dwCreationDispositionb);
        goto LABEL_44;
      }
      if ( !GetFileVersionInfoExW(0, lpwstrFilename, dwHandle, v19, v5) )
      {
        v21 = 158;
LABEL_38:
        v7 = -2147023084;
        goto LABEL_39;
      }
      if ( !VerQueryValueW(v5, L"\\", &lpBuffer, &puLen) )
      {
        v20 = 161;
        goto LABEL_35;
      }
      if ( puLen < 0x34 )
      {
        v21 = 162;
        goto LABEL_38;
      }
      v30 = *((_DWORD *)lpBuffer + 2);
      v31 = *((_DWORD *)lpBuffer + 3);
    }
    else if ( RawFileVersionFromModule >= 0 )
    {
LABEL_43:
      v7 = RawFileVersionFromModule;
      goto LABEL_44;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileVersion.cpp",
      (const char *)(unsigned int)RawFileVersionFromModule,
      dwCreationDispositionb);
    goto LABEL_43;
  }
  v7 = -2147024883;
  v11 = 124;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\FileVersion.cpp",
    (const char *)v7,
    dwCreationDispositiona);
LABEL_45:
  *a2 = v30;
  *a3 = v31;
  if ( v5 )
    SusFree(v5);
  if ( v4 )
    CloseHandle(v4);
  if ( v9 != (void *)-1LL )
    CloseHandle(v9);
  return v7;
}

```

## disassembly

```asm
0x140014cac  mov     [rsp-28h+arg_8], rbx
0x140014cb1  mov     [rsp-28h+arg_10], rsi
0x140014cb6  mov     [rsp-28h+arg_18], rdi
0x140014cbb  push    rbp
0x140014cbc  push    r12
0x140014cbe  push    r13
0x140014cc0  push    r14
0x140014cc2  push    r15
0x140014cc4  mov     rbp, rsp
0x140014cc7  sub     rsp, 80h
0x140014cce  mov     rax, cs:__security_cookie
0x140014cd5  xor     rax, rsp
0x140014cd8  mov     [rbp+var_8], rax
0x140014cdc  xor     r12d, r12d
0x140014cdf  mov     [rbp+var_38], rdx
0x140014ce3  mov     [rbp+var_20], r12d
0x140014ce7  mov     rax, r8
0x140014cea  mov     [rbp+var_30], rax
0x140014cee  mov     r15, rcx
0x140014cf1  mov     [rbp+var_1C], r12d
0x140014cf5  mov     edi, r12d
0x140014cf8  mov     ebx, r12d
0x140014cfb  test    rcx, rcx
0x140014cfe  jnz     short loc_140014D05
0x140014d00  lea     edx, [rcx+64h]
0x140014d03  jmp     short loc_140014D19
0x140014d05  test    rdx, rdx
0x140014d08  jnz     short loc_140014D11
0x140014d0a  mov     edx, 65h ; 'e'
0x140014d0f  jmp     short loc_140014D19
0x140014d11  test    rax, rax
0x140014d14  jnz     short loc_140014D36
0x140014d16  lea     edx, [rax+66h]; void *
0x140014d19  mov     rcx, [rbp+28h]; this
0x140014d1d  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140014d24  mov     esi, 80004003h
0x140014d29  mov     r9d, esi; char *
0x140014d2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014d31  jmp     loc_140014FBB
0x140014d36  xor     r9d, r9d; lpSecurityAttributes
0x140014d39  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x140014d3e  mov     [rsp+80h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x140014d43  mov     edx, 80000000h; dwDesiredAccess
0x140014d48  mov     [rsp+80h+dwCreationDisposition], 3; int
0x140014d50  lea     esi, [r9+1]
0x140014d54  mov     r8d, esi; dwShareMode
0x140014d57  call    cs:__imp_CreateFileW
0x140014d5d  mov     r13, rax
0x140014d60  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140014d64  jnz     short loc_140014DA5
0x140014d66  call    cs:__imp_GetLastError
0x140014d6c  movzx   esi, ax
0x140014d6f  or      esi, 80070000h
0x140014d75  test    eax, eax
0x140014d77  cmovle  esi, eax
0x140014d7a  test    esi, esi
0x140014d7c  js      short loc_140014D85
0x140014d7e  mov     esi, 8000FFFFh
0x140014d83  jmp     short loc_140014D9E
0x140014d85  mov     eax, esi
0x140014d87  cmp     esi, 80070002h
0x140014d8d  jz      loc_140014F7F
0x140014d93  cmp     eax, 80070003h
0x140014d98  jz      loc_140014F7F
0x140014d9e  mov     edx, 74h ; 't'
0x140014da3  jmp     short loc_140014DCF
0x140014da5  lea     rdx, [rbp+FileSize]; lpFileSize
0x140014da9  mov     qword ptr [rbp+FileSize], r12
0x140014dad  mov     rcx, r13; hFile
0x140014db0  call    cs:__imp_GetFileSizeEx
0x140014db6  test    eax, eax
0x140014db8  jnz     short loc_140014DBF
0x140014dba  lea     edx, [rax+7Ah]
0x140014dbd  jmp     short loc_140014E3B
0x140014dbf  cmp     dword ptr [rbp+FileSize+4], r12d
0x140014dc3  jz      short loc_140014DE7
0x140014dc5  mov     esi, 8007000Dh
0x140014dca  mov     edx, 7Ch ; '|'; void *
0x140014dcf  mov     rcx, [rbp+28h]; this
0x140014dd3  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140014dda  mov     r9d, esi; char *
0x140014ddd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014de2  jmp     loc_140014F7F
0x140014de7  xor     r9d, r9d; dwMaximumSizeHigh
0x140014dea  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpName
0x140014def  xor     edx, edx; lpFileMappingAttributes
0x140014df1  mov     [rsp+80h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x140014df6  mov     rcx, r13; hFile
0x140014df9  lea     r8d, [r9+2]; flProtect
0x140014dfd  call    cs:__imp_CreateFileMappingW
0x140014e03  mov     rdi, rax
0x140014e06  test    rax, rax
0x140014e09  jnz     short loc_140014E10
0x140014e0b  lea     edx, [rax+7Fh]
0x140014e0e  jmp     short loc_140014E3B
0x140014e10  xor     r9d, r9d; dwFileOffsetLow
0x140014e13  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpBaseAddress
0x140014e18  xor     r8d, r8d; dwFileOffsetHigh
0x140014e1b  mov     qword ptr [rsp+80h+dwCreationDisposition], r12; int
0x140014e20  mov     rcx, rax; hFileMappingObject
0x140014e23  lea     edx, [r9+4]; dwDesiredAccess
0x140014e27  call    cs:__imp_MapViewOfFileEx
0x140014e2d  mov     [rbp+lpBaseAddress], rax
0x140014e31  test    rax, rax
0x140014e34  jnz     short loc_140014E52
0x140014e36  mov     edx, 82h; void *
0x140014e3b  mov     rcx, [rbp+28h]; this
0x140014e3f  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140014e46  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140014e4b  mov     esi, eax
0x140014e4d  jmp     loc_140014F7F
0x140014e52  mov     rdx, qword ptr [rbp+FileSize]; unsigned __int64
0x140014e56  lea     r9, [rbp+var_1C]; unsigned int *
0x140014e5a  mov     rcx, rax
0x140014e5d  lea     r8, [rbp+var_20]; unsigned int *
0x140014e61  or      rcx, rsi; hModule
0x140014e64  call    ?GetRawFileVersionFromModule@@YAJPEAUHINSTANCE__@@_KPEAK2@Z; GetRawFileVersionFromModule(HINSTANCE__ *,unsigned __int64,ulong *,ulong *)
0x140014e69  mov     r14d, eax
0x140014e6c  cmp     eax, 800710DCh
0x140014e71  jnz     loc_140014F55
0x140014e77  lea     r8, [rbp+dwHandle]; lpdwHandle
0x140014e7b  mov     [rbp+dwHandle], r12d
0x140014e7f  mov     rdx, r15; lpwstrFilename
0x140014e82  mov     [rbp+lpBuffer], r12
0x140014e86  xor     ecx, ecx; dwFlags
0x140014e88  mov     [rbp+puLen], r12d
0x140014e8c  call    cs:__imp_GetFileVersionInfoSizeExW
0x140014e92  mov     r12d, eax
0x140014e95  test    eax, eax
0x140014e97  jnz     short loc_140014EA0
0x140014e99  mov     edx, 95h
0x140014e9e  jmp     short loc_140014F0A
0x140014ea0  mov     rcx, r12; unsigned __int64
0x140014ea3  mov     rdx, rsi; unsigned __int64
0x140014ea6  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x140014eab  mov     rbx, rax
0x140014eae  neg     rax
0x140014eb1  sbb     esi, esi
0x140014eb3  not     esi
0x140014eb5  and     esi, 8007000Eh
0x140014ebb  test    rbx, rbx
0x140014ebe  jnz     short loc_140014EC7
0x140014ec0  mov     edx, 96h
0x140014ec5  jmp     short loc_140014F2E
0x140014ec7  mov     r8d, [rbp+dwHandle]; dwHandle
0x140014ecb  mov     r9d, r12d; dwLen
0x140014ece  mov     rdx, r15; lpwstrFilename
0x140014ed1  mov     qword ptr [rsp+80h+dwCreationDisposition], rbx; int
0x140014ed6  xor     ecx, ecx; dwFlags
0x140014ed8  call    cs:__imp_GetFileVersionInfoExW
0x140014ede  test    eax, eax
0x140014ee0  jnz     short loc_140014EE9
0x140014ee2  mov     edx, 9Eh
0x140014ee7  jmp     short loc_140014F29
0x140014ee9  lea     r9, [rbp+puLen]; puLen
0x140014eed  mov     rcx, rbx; pBlock
0x140014ef0  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x140014ef4  lea     rdx, SubBlock; "\\"
0x140014efb  call    cs:__imp_VerQueryValueW
0x140014f01  test    eax, eax
0x140014f03  jnz     short loc_140014F1E
0x140014f05  mov     edx, 0A1h; void *
0x140014f0a  mov     rcx, [rbp+28h]; this
0x140014f0e  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140014f15  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140014f1a  mov     esi, eax
0x140014f1c  jmp     short loc_140014F75
0x140014f1e  cmp     [rbp+puLen], 34h ; '4'
0x140014f22  jnb     short loc_140014F43
0x140014f24  mov     edx, 0A2h; void *
0x140014f29  mov     esi, 80070714h
0x140014f2e  mov     rcx, [rbp+28h]; this
0x140014f32  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140014f39  mov     r9d, esi; char *
0x140014f3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014f41  jmp     short loc_140014F75
0x140014f43  mov     rcx, [rbp+lpBuffer]
0x140014f47  mov     eax, [rcx+8]
0x140014f4a  mov     [rbp+var_20], eax
0x140014f4d  mov     eax, [rcx+0Ch]
0x140014f50  mov     [rbp+var_1C], eax
0x140014f53  jmp     short loc_140014F5A
0x140014f55  test    r14d, r14d
0x140014f58  jns     short loc_140014F72
0x140014f5a  mov     rcx, [rbp+28h]; this
0x140014f5e  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140014f65  mov     r9d, r14d; char *
0x140014f68  mov     edx, 0A8h; void *
0x140014f6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014f72  mov     esi, r14d
0x140014f75  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x140014f79  call    cs:__imp_UnmapViewOfFile
0x140014f7f  mov     eax, [rbp+var_20]
0x140014f82  mov     rcx, [rbp+var_38]
0x140014f86  mov     [rcx], eax
0x140014f88  mov     rcx, [rbp+var_30]
0x140014f8c  mov     eax, [rbp+var_1C]
0x140014f8f  mov     [rcx], eax
0x140014f91  test    rbx, rbx
0x140014f94  jz      short loc_140014F9E
0x140014f96  mov     rcx, rbx; lpMem
0x140014f99  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140014f9e  test    rdi, rdi
0x140014fa1  jz      short loc_140014FAC
0x140014fa3  mov     rcx, rdi; hObject
0x140014fa6  call    cs:__imp_CloseHandle
0x140014fac  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x140014fb0  jz      short loc_140014FBB
0x140014fb2  mov     rcx, r13; hObject
0x140014fb5  call    cs:__imp_CloseHandle
0x140014fbb  mov     eax, esi
0x140014fbd  mov     rcx, [rbp+var_8]
0x140014fc1  xor     rcx, rsp; StackCookie
0x140014fc4  call    __security_check_cookie
0x140014fc9  lea     r11, [rsp+80h+var_s0]
0x140014fd1  mov     rbx, [r11+38h]
0x140014fd5  mov     rsi, [r11+40h]
0x140014fd9  mov     rdi, [r11+48h]
0x140014fdd  mov     rsp, r11
0x140014fe0  pop     r15
0x140014fe2  pop     r14
0x140014fe4  pop     r13
0x140014fe6  pop     r12
0x140014fe8  pop     rbp
0x140014fe9  retn
```
