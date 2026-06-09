# GetRawFileVersion(wchar_t const *,ulong *,ulong *)

- ea: `0x18000f69c`
- end: `0x18000f9da`
- name: `?GetRawFileVersion@@YAJPEB_WPEAK1@Z`
- size: `830`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000f5c0`

## callees

- `0x180003760`
- `0x180003784`
- `0x18000b1ec`
- `0x18000b21c`
- `0x18000f69c`
- `0x18000f9e0`
- `0x18000fce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f756`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f996`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f9a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f996`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f9a5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f747`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f747`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000f7a0`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000f7a0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18000f817`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18000f817`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000f7ed`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000f7ed`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000f969`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000f969`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18000f8c8`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18000f8c8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000f8eb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000f8eb`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18000f87c`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18000f87c`

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
0x18000f69c  mov     [rsp-28h+arg_8], rbx
0x18000f6a1  mov     [rsp-28h+arg_10], rsi
0x18000f6a6  mov     [rsp-28h+arg_18], rdi
0x18000f6ab  push    rbp
0x18000f6ac  push    r12
0x18000f6ae  push    r13
0x18000f6b0  push    r14
0x18000f6b2  push    r15
0x18000f6b4  mov     rbp, rsp
0x18000f6b7  sub     rsp, 80h
0x18000f6be  mov     rax, cs:__security_cookie
0x18000f6c5  xor     rax, rsp
0x18000f6c8  mov     [rbp+var_8], rax
0x18000f6cc  xor     r12d, r12d
0x18000f6cf  mov     [rbp+var_38], rdx
0x18000f6d3  mov     [rbp+var_20], r12d
0x18000f6d7  mov     rax, r8
0x18000f6da  mov     [rbp+var_30], rax
0x18000f6de  mov     r15, rcx
0x18000f6e1  mov     [rbp+var_1C], r12d
0x18000f6e5  mov     edi, r12d
0x18000f6e8  mov     ebx, r12d
0x18000f6eb  test    rcx, rcx
0x18000f6ee  jnz     short loc_18000F6F5
0x18000f6f0  lea     edx, [rcx+64h]
0x18000f6f3  jmp     short loc_18000F709
0x18000f6f5  test    rdx, rdx
0x18000f6f8  jnz     short loc_18000F701
0x18000f6fa  mov     edx, 65h ; 'e'
0x18000f6ff  jmp     short loc_18000F709
0x18000f701  test    rax, rax
0x18000f704  jnz     short loc_18000F726
0x18000f706  lea     edx, [rax+66h]; void *
0x18000f709  mov     rcx, [rbp+28h]; this
0x18000f70d  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f714  mov     esi, 80004003h
0x18000f719  mov     r9d, esi; char *
0x18000f71c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f721  jmp     loc_18000F9AB
0x18000f726  xor     r9d, r9d; lpSecurityAttributes
0x18000f729  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x18000f72e  mov     [rsp+80h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18000f733  mov     edx, 80000000h; dwDesiredAccess
0x18000f738  mov     [rsp+80h+dwCreationDisposition], 3; int
0x18000f740  lea     esi, [r9+1]
0x18000f744  mov     r8d, esi; dwShareMode
0x18000f747  call    cs:__imp_CreateFileW
0x18000f74d  mov     r13, rax
0x18000f750  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f754  jnz     short loc_18000F795
0x18000f756  call    cs:__imp_GetLastError
0x18000f75c  movzx   esi, ax
0x18000f75f  or      esi, 80070000h
0x18000f765  test    eax, eax
0x18000f767  cmovle  esi, eax
0x18000f76a  test    esi, esi
0x18000f76c  js      short loc_18000F775
0x18000f76e  mov     esi, 8000FFFFh
0x18000f773  jmp     short loc_18000F78E
0x18000f775  mov     eax, esi
0x18000f777  cmp     esi, 80070002h
0x18000f77d  jz      loc_18000F96F
0x18000f783  cmp     eax, 80070003h
0x18000f788  jz      loc_18000F96F
0x18000f78e  mov     edx, 74h ; 't'
0x18000f793  jmp     short loc_18000F7BF
0x18000f795  lea     rdx, [rbp+FileSize]; lpFileSize
0x18000f799  mov     qword ptr [rbp+FileSize], r12
0x18000f79d  mov     rcx, r13; hFile
0x18000f7a0  call    cs:__imp_GetFileSizeEx
0x18000f7a6  test    eax, eax
0x18000f7a8  jnz     short loc_18000F7AF
0x18000f7aa  lea     edx, [rax+7Ah]
0x18000f7ad  jmp     short loc_18000F82B
0x18000f7af  cmp     dword ptr [rbp+FileSize+4], r12d
0x18000f7b3  jz      short loc_18000F7D7
0x18000f7b5  mov     esi, 8007000Dh
0x18000f7ba  mov     edx, 7Ch ; '|'; void *
0x18000f7bf  mov     rcx, [rbp+28h]; this
0x18000f7c3  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f7ca  mov     r9d, esi; char *
0x18000f7cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f7d2  jmp     loc_18000F96F
0x18000f7d7  xor     r9d, r9d; dwMaximumSizeHigh
0x18000f7da  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpName
0x18000f7df  xor     edx, edx; lpFileMappingAttributes
0x18000f7e1  mov     [rsp+80h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x18000f7e6  mov     rcx, r13; hFile
0x18000f7e9  lea     r8d, [r9+2]; flProtect
0x18000f7ed  call    cs:__imp_CreateFileMappingW
0x18000f7f3  mov     rdi, rax
0x18000f7f6  test    rax, rax
0x18000f7f9  jnz     short loc_18000F800
0x18000f7fb  lea     edx, [rax+7Fh]
0x18000f7fe  jmp     short loc_18000F82B
0x18000f800  xor     r9d, r9d; dwFileOffsetLow
0x18000f803  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpBaseAddress
0x18000f808  xor     r8d, r8d; dwFileOffsetHigh
0x18000f80b  mov     qword ptr [rsp+80h+dwCreationDisposition], r12; int
0x18000f810  mov     rcx, rax; hFileMappingObject
0x18000f813  lea     edx, [r9+4]; dwDesiredAccess
0x18000f817  call    cs:__imp_MapViewOfFileEx
0x18000f81d  mov     [rbp+lpBaseAddress], rax
0x18000f821  test    rax, rax
0x18000f824  jnz     short loc_18000F842
0x18000f826  mov     edx, 82h; void *
0x18000f82b  mov     rcx, [rbp+28h]; this
0x18000f82f  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f836  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f83b  mov     esi, eax
0x18000f83d  jmp     loc_18000F96F
0x18000f842  mov     rdx, qword ptr [rbp+FileSize]; unsigned __int64
0x18000f846  lea     r9, [rbp+var_1C]; unsigned int *
0x18000f84a  mov     rcx, rax
0x18000f84d  lea     r8, [rbp+var_20]; unsigned int *
0x18000f851  or      rcx, rsi; hModule
0x18000f854  call    ?GetRawFileVersionFromModule@@YAJPEAUHINSTANCE__@@_KPEAK2@Z; GetRawFileVersionFromModule(HINSTANCE__ *,unsigned __int64,ulong *,ulong *)
0x18000f859  mov     r14d, eax
0x18000f85c  cmp     eax, 800710DCh
0x18000f861  jnz     loc_18000F945
0x18000f867  lea     r8, [rbp+dwHandle]; lpdwHandle
0x18000f86b  mov     [rbp+dwHandle], r12d
0x18000f86f  mov     rdx, r15; lpwstrFilename
0x18000f872  mov     [rbp+lpBuffer], r12
0x18000f876  xor     ecx, ecx; dwFlags
0x18000f878  mov     [rbp+puLen], r12d
0x18000f87c  call    cs:__imp_GetFileVersionInfoSizeExW
0x18000f882  mov     r12d, eax
0x18000f885  test    eax, eax
0x18000f887  jnz     short loc_18000F890
0x18000f889  mov     edx, 95h
0x18000f88e  jmp     short loc_18000F8FA
0x18000f890  mov     rcx, r12; unsigned __int64
0x18000f893  mov     rdx, rsi; unsigned __int64
0x18000f896  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18000f89b  mov     rbx, rax
0x18000f89e  neg     rax
0x18000f8a1  sbb     esi, esi
0x18000f8a3  not     esi
0x18000f8a5  and     esi, 8007000Eh
0x18000f8ab  test    rbx, rbx
0x18000f8ae  jnz     short loc_18000F8B7
0x18000f8b0  mov     edx, 96h
0x18000f8b5  jmp     short loc_18000F91E
0x18000f8b7  mov     r8d, [rbp+dwHandle]; dwHandle
0x18000f8bb  mov     r9d, r12d; dwLen
0x18000f8be  mov     rdx, r15; lpwstrFilename
0x18000f8c1  mov     qword ptr [rsp+80h+dwCreationDisposition], rbx; int
0x18000f8c6  xor     ecx, ecx; dwFlags
0x18000f8c8  call    cs:__imp_GetFileVersionInfoExW
0x18000f8ce  test    eax, eax
0x18000f8d0  jnz     short loc_18000F8D9
0x18000f8d2  mov     edx, 9Eh
0x18000f8d7  jmp     short loc_18000F919
0x18000f8d9  lea     r9, [rbp+puLen]; puLen
0x18000f8dd  mov     rcx, rbx; pBlock
0x18000f8e0  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x18000f8e4  lea     rdx, SubBlock; "\\"
0x18000f8eb  call    cs:__imp_VerQueryValueW
0x18000f8f1  test    eax, eax
0x18000f8f3  jnz     short loc_18000F90E
0x18000f8f5  mov     edx, 0A1h; void *
0x18000f8fa  mov     rcx, [rbp+28h]; this
0x18000f8fe  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f905  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f90a  mov     esi, eax
0x18000f90c  jmp     short loc_18000F965
0x18000f90e  cmp     [rbp+puLen], 34h ; '4'
0x18000f912  jnb     short loc_18000F933
0x18000f914  mov     edx, 0A2h; void *
0x18000f919  mov     esi, 80070714h
0x18000f91e  mov     rcx, [rbp+28h]; this
0x18000f922  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f929  mov     r9d, esi; char *
0x18000f92c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f931  jmp     short loc_18000F965
0x18000f933  mov     rcx, [rbp+lpBuffer]
0x18000f937  mov     eax, [rcx+8]
0x18000f93a  mov     [rbp+var_20], eax
0x18000f93d  mov     eax, [rcx+0Ch]
0x18000f940  mov     [rbp+var_1C], eax
0x18000f943  jmp     short loc_18000F94A
0x18000f945  test    r14d, r14d
0x18000f948  jns     short loc_18000F962
0x18000f94a  mov     rcx, [rbp+28h]; this
0x18000f94e  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f955  mov     r9d, r14d; char *
0x18000f958  mov     edx, 0A8h; void *
0x18000f95d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f962  mov     esi, r14d
0x18000f965  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x18000f969  call    cs:__imp_UnmapViewOfFile
0x18000f96f  mov     eax, [rbp+var_20]
0x18000f972  mov     rcx, [rbp+var_38]
0x18000f976  mov     [rcx], eax
0x18000f978  mov     rcx, [rbp+var_30]
0x18000f97c  mov     eax, [rbp+var_1C]
0x18000f97f  mov     [rcx], eax
0x18000f981  test    rbx, rbx
0x18000f984  jz      short loc_18000F98E
0x18000f986  mov     rcx, rbx; lpMem
0x18000f989  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000f98e  test    rdi, rdi
0x18000f991  jz      short loc_18000F99C
0x18000f993  mov     rcx, rdi; hObject
0x18000f996  call    cs:__imp_CloseHandle
0x18000f99c  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18000f9a0  jz      short loc_18000F9AB
0x18000f9a2  mov     rcx, r13; hObject
0x18000f9a5  call    cs:__imp_CloseHandle
0x18000f9ab  mov     eax, esi
0x18000f9ad  mov     rcx, [rbp+var_8]
0x18000f9b1  xor     rcx, rsp; StackCookie
0x18000f9b4  call    __security_check_cookie
0x18000f9b9  lea     r11, [rsp+80h+var_s0]
0x18000f9c1  mov     rbx, [r11+38h]
0x18000f9c5  mov     rsi, [r11+40h]
0x18000f9c9  mov     rdi, [r11+48h]
0x18000f9cd  mov     rsp, r11
0x18000f9d0  pop     r15
0x18000f9d2  pop     r14
0x18000f9d4  pop     r13
0x18000f9d6  pop     r12
0x18000f9d8  pop     rbp
0x18000f9d9  retn
```
