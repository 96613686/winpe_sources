# GetRawFileVersion(wchar_t const *,ulong *,ulong *)

- ea: `0x18000e488`
- end: `0x18000e7c6`
- name: `?GetRawFileVersion@@YAJPEB_WPEAK1@Z`
- size: `830`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000e3ac`

## callees

- `0x1800061b0`
- `0x180006858`
- `0x18000a150`
- `0x18000a180`
- `0x18000e488`
- `0x18000e7cc`
- `0x18000ed40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e542`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e782`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e791`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e782`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e791`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000e755`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000e755`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18000e603`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18000e603`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000e5d9`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000e5d9`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000e6d7`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000e6d7`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18000e6b4`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18000e6b4`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18000e668`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18000e668`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e533`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e533`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000e58c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000e58c`

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
0x18000e488  mov     [rsp-28h+arg_8], rbx
0x18000e48d  mov     [rsp-28h+arg_10], rsi
0x18000e492  mov     [rsp-28h+arg_18], rdi
0x18000e497  push    rbp
0x18000e498  push    r12
0x18000e49a  push    r13
0x18000e49c  push    r14
0x18000e49e  push    r15
0x18000e4a0  mov     rbp, rsp
0x18000e4a3  sub     rsp, 80h
0x18000e4aa  mov     rax, cs:__security_cookie
0x18000e4b1  xor     rax, rsp
0x18000e4b4  mov     [rbp+var_8], rax
0x18000e4b8  xor     r12d, r12d
0x18000e4bb  mov     [rbp+var_38], rdx
0x18000e4bf  mov     [rbp+var_20], r12d
0x18000e4c3  mov     rax, r8
0x18000e4c6  mov     [rbp+var_30], rax
0x18000e4ca  mov     r15, rcx
0x18000e4cd  mov     [rbp+var_1C], r12d
0x18000e4d1  mov     edi, r12d
0x18000e4d4  mov     ebx, r12d
0x18000e4d7  test    rcx, rcx
0x18000e4da  jnz     short loc_18000E4E1
0x18000e4dc  lea     edx, [rcx+64h]
0x18000e4df  jmp     short loc_18000E4F5
0x18000e4e1  test    rdx, rdx
0x18000e4e4  jnz     short loc_18000E4ED
0x18000e4e6  mov     edx, 65h ; 'e'
0x18000e4eb  jmp     short loc_18000E4F5
0x18000e4ed  test    rax, rax
0x18000e4f0  jnz     short loc_18000E512
0x18000e4f2  lea     edx, [rax+66h]; void *
0x18000e4f5  mov     rcx, [rbp+28h]; this
0x18000e4f9  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e500  mov     esi, 80004003h
0x18000e505  mov     r9d, esi; char *
0x18000e508  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e50d  jmp     loc_18000E797
0x18000e512  xor     r9d, r9d; lpSecurityAttributes
0x18000e515  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x18000e51a  mov     [rsp+80h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18000e51f  mov     edx, 80000000h; dwDesiredAccess
0x18000e524  mov     [rsp+80h+dwCreationDisposition], 3; int
0x18000e52c  lea     esi, [r9+1]
0x18000e530  mov     r8d, esi; dwShareMode
0x18000e533  call    cs:__imp_CreateFileW
0x18000e539  mov     r13, rax
0x18000e53c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e540  jnz     short loc_18000E581
0x18000e542  call    cs:__imp_GetLastError
0x18000e548  movzx   esi, ax
0x18000e54b  or      esi, 80070000h
0x18000e551  test    eax, eax
0x18000e553  cmovle  esi, eax
0x18000e556  test    esi, esi
0x18000e558  js      short loc_18000E561
0x18000e55a  mov     esi, 8000FFFFh
0x18000e55f  jmp     short loc_18000E57A
0x18000e561  mov     eax, esi
0x18000e563  cmp     esi, 80070002h
0x18000e569  jz      loc_18000E75B
0x18000e56f  cmp     eax, 80070003h
0x18000e574  jz      loc_18000E75B
0x18000e57a  mov     edx, 74h ; 't'
0x18000e57f  jmp     short loc_18000E5AB
0x18000e581  lea     rdx, [rbp+FileSize]; lpFileSize
0x18000e585  mov     qword ptr [rbp+FileSize], r12
0x18000e589  mov     rcx, r13; hFile
0x18000e58c  call    cs:__imp_GetFileSizeEx
0x18000e592  test    eax, eax
0x18000e594  jnz     short loc_18000E59B
0x18000e596  lea     edx, [rax+7Ah]
0x18000e599  jmp     short loc_18000E617
0x18000e59b  cmp     dword ptr [rbp+FileSize+4], r12d
0x18000e59f  jz      short loc_18000E5C3
0x18000e5a1  mov     esi, 8007000Dh
0x18000e5a6  mov     edx, 7Ch ; '|'; void *
0x18000e5ab  mov     rcx, [rbp+28h]; this
0x18000e5af  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e5b6  mov     r9d, esi; char *
0x18000e5b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e5be  jmp     loc_18000E75B
0x18000e5c3  xor     r9d, r9d; dwMaximumSizeHigh
0x18000e5c6  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpName
0x18000e5cb  xor     edx, edx; lpFileMappingAttributes
0x18000e5cd  mov     [rsp+80h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x18000e5d2  mov     rcx, r13; hFile
0x18000e5d5  lea     r8d, [r9+2]; flProtect
0x18000e5d9  call    cs:__imp_CreateFileMappingW
0x18000e5df  mov     rdi, rax
0x18000e5e2  test    rax, rax
0x18000e5e5  jnz     short loc_18000E5EC
0x18000e5e7  lea     edx, [rax+7Fh]
0x18000e5ea  jmp     short loc_18000E617
0x18000e5ec  xor     r9d, r9d; dwFileOffsetLow
0x18000e5ef  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpBaseAddress
0x18000e5f4  xor     r8d, r8d; dwFileOffsetHigh
0x18000e5f7  mov     qword ptr [rsp+80h+dwCreationDisposition], r12; int
0x18000e5fc  mov     rcx, rax; hFileMappingObject
0x18000e5ff  lea     edx, [r9+4]; dwDesiredAccess
0x18000e603  call    cs:__imp_MapViewOfFileEx
0x18000e609  mov     [rbp+lpBaseAddress], rax
0x18000e60d  test    rax, rax
0x18000e610  jnz     short loc_18000E62E
0x18000e612  mov     edx, 82h; void *
0x18000e617  mov     rcx, [rbp+28h]; this
0x18000e61b  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e622  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e627  mov     esi, eax
0x18000e629  jmp     loc_18000E75B
0x18000e62e  mov     rdx, qword ptr [rbp+FileSize]; unsigned __int64
0x18000e632  lea     r9, [rbp+var_1C]; unsigned int *
0x18000e636  mov     rcx, rax
0x18000e639  lea     r8, [rbp+var_20]; unsigned int *
0x18000e63d  or      rcx, rsi; hModule
0x18000e640  call    ?GetRawFileVersionFromModule@@YAJPEAUHINSTANCE__@@_KPEAK2@Z; GetRawFileVersionFromModule(HINSTANCE__ *,unsigned __int64,ulong *,ulong *)
0x18000e645  mov     r14d, eax
0x18000e648  cmp     eax, 800710DCh
0x18000e64d  jnz     loc_18000E731
0x18000e653  lea     r8, [rbp+dwHandle]; lpdwHandle
0x18000e657  mov     [rbp+dwHandle], r12d
0x18000e65b  mov     rdx, r15; lpwstrFilename
0x18000e65e  mov     [rbp+lpBuffer], r12
0x18000e662  xor     ecx, ecx; dwFlags
0x18000e664  mov     [rbp+puLen], r12d
0x18000e668  call    cs:__imp_GetFileVersionInfoSizeExW
0x18000e66e  mov     r12d, eax
0x18000e671  test    eax, eax
0x18000e673  jnz     short loc_18000E67C
0x18000e675  mov     edx, 95h
0x18000e67a  jmp     short loc_18000E6E6
0x18000e67c  mov     rcx, r12; unsigned __int64
0x18000e67f  mov     rdx, rsi; unsigned __int64
0x18000e682  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18000e687  mov     rbx, rax
0x18000e68a  neg     rax
0x18000e68d  sbb     esi, esi
0x18000e68f  not     esi
0x18000e691  and     esi, 8007000Eh
0x18000e697  test    rbx, rbx
0x18000e69a  jnz     short loc_18000E6A3
0x18000e69c  mov     edx, 96h
0x18000e6a1  jmp     short loc_18000E70A
0x18000e6a3  mov     r8d, [rbp+dwHandle]; dwHandle
0x18000e6a7  mov     r9d, r12d; dwLen
0x18000e6aa  mov     rdx, r15; lpwstrFilename
0x18000e6ad  mov     qword ptr [rsp+80h+dwCreationDisposition], rbx; int
0x18000e6b2  xor     ecx, ecx; dwFlags
0x18000e6b4  call    cs:__imp_GetFileVersionInfoExW
0x18000e6ba  test    eax, eax
0x18000e6bc  jnz     short loc_18000E6C5
0x18000e6be  mov     edx, 9Eh
0x18000e6c3  jmp     short loc_18000E705
0x18000e6c5  lea     r9, [rbp+puLen]; puLen
0x18000e6c9  mov     rcx, rbx; pBlock
0x18000e6cc  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x18000e6d0  lea     rdx, SubBlock; "\\"
0x18000e6d7  call    cs:__imp_VerQueryValueW
0x18000e6dd  test    eax, eax
0x18000e6df  jnz     short loc_18000E6FA
0x18000e6e1  mov     edx, 0A1h; void *
0x18000e6e6  mov     rcx, [rbp+28h]; this
0x18000e6ea  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e6f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e6f6  mov     esi, eax
0x18000e6f8  jmp     short loc_18000E751
0x18000e6fa  cmp     [rbp+puLen], 34h ; '4'
0x18000e6fe  jnb     short loc_18000E71F
0x18000e700  mov     edx, 0A2h; void *
0x18000e705  mov     esi, 80070714h
0x18000e70a  mov     rcx, [rbp+28h]; this
0x18000e70e  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e715  mov     r9d, esi; char *
0x18000e718  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e71d  jmp     short loc_18000E751
0x18000e71f  mov     rcx, [rbp+lpBuffer]
0x18000e723  mov     eax, [rcx+8]
0x18000e726  mov     [rbp+var_20], eax
0x18000e729  mov     eax, [rcx+0Ch]
0x18000e72c  mov     [rbp+var_1C], eax
0x18000e72f  jmp     short loc_18000E736
0x18000e731  test    r14d, r14d
0x18000e734  jns     short loc_18000E74E
0x18000e736  mov     rcx, [rbp+28h]; this
0x18000e73a  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000e741  mov     r9d, r14d; char *
0x18000e744  mov     edx, 0A8h; void *
0x18000e749  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e74e  mov     esi, r14d
0x18000e751  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x18000e755  call    cs:__imp_UnmapViewOfFile
0x18000e75b  mov     eax, [rbp+var_20]
0x18000e75e  mov     rcx, [rbp+var_38]
0x18000e762  mov     [rcx], eax
0x18000e764  mov     rcx, [rbp+var_30]
0x18000e768  mov     eax, [rbp+var_1C]
0x18000e76b  mov     [rcx], eax
0x18000e76d  test    rbx, rbx
0x18000e770  jz      short loc_18000E77A
0x18000e772  mov     rcx, rbx; lpMem
0x18000e775  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000e77a  test    rdi, rdi
0x18000e77d  jz      short loc_18000E788
0x18000e77f  mov     rcx, rdi; hObject
0x18000e782  call    cs:__imp_CloseHandle
0x18000e788  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18000e78c  jz      short loc_18000E797
0x18000e78e  mov     rcx, r13; hObject
0x18000e791  call    cs:__imp_CloseHandle
0x18000e797  mov     eax, esi
0x18000e799  mov     rcx, [rbp+var_8]
0x18000e79d  xor     rcx, rsp; StackCookie
0x18000e7a0  call    __security_check_cookie
0x18000e7a5  lea     r11, [rsp+80h+var_s0]
0x18000e7ad  mov     rbx, [r11+38h]
0x18000e7b1  mov     rsi, [r11+40h]
0x18000e7b5  mov     rdi, [r11+48h]
0x18000e7b9  mov     rsp, r11
0x18000e7bc  pop     r15
0x18000e7be  pop     r14
0x18000e7c0  pop     r13
0x18000e7c2  pop     r12
0x18000e7c4  pop     rbp
0x18000e7c5  retn
```
