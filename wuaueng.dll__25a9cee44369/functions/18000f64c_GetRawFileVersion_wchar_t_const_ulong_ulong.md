# GetRawFileVersion(wchar_t const *,ulong *,ulong *)

- ea: `0x18000f64c`
- end: `0x18000f98a`
- name: `?GetRawFileVersion@@YAJPEB_WPEAK1@Z`
- size: `830`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000f570`

## callees

- `0x180003760`
- `0x180003784`
- `0x18000b198`
- `0x18000b1c8`
- `0x18000f64c`
- `0x18000f990`
- `0x18000fc90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f706`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f955`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f955`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000f750`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000f750`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f6f7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f6f7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18000f7c7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18000f7c7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000f919`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000f919`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000f79d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000f79d`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000f89b`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000f89b`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18000f82c`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18000f82c`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18000f878`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18000f878`

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
0x18000f64c  mov     [rsp-28h+arg_8], rbx
0x18000f651  mov     [rsp-28h+arg_10], rsi
0x18000f656  mov     [rsp-28h+arg_18], rdi
0x18000f65b  push    rbp
0x18000f65c  push    r12
0x18000f65e  push    r13
0x18000f660  push    r14
0x18000f662  push    r15
0x18000f664  mov     rbp, rsp
0x18000f667  sub     rsp, 80h
0x18000f66e  mov     rax, cs:__security_cookie
0x18000f675  xor     rax, rsp
0x18000f678  mov     [rbp+var_8], rax
0x18000f67c  xor     r12d, r12d
0x18000f67f  mov     [rbp+var_38], rdx
0x18000f683  mov     [rbp+var_20], r12d
0x18000f687  mov     rax, r8
0x18000f68a  mov     [rbp+var_30], rax
0x18000f68e  mov     r15, rcx
0x18000f691  mov     [rbp+var_1C], r12d
0x18000f695  mov     edi, r12d
0x18000f698  mov     ebx, r12d
0x18000f69b  test    rcx, rcx
0x18000f69e  jnz     short loc_18000F6A5
0x18000f6a0  lea     edx, [rcx+64h]
0x18000f6a3  jmp     short loc_18000F6B9
0x18000f6a5  test    rdx, rdx
0x18000f6a8  jnz     short loc_18000F6B1
0x18000f6aa  mov     edx, 65h ; 'e'
0x18000f6af  jmp     short loc_18000F6B9
0x18000f6b1  test    rax, rax
0x18000f6b4  jnz     short loc_18000F6D6
0x18000f6b6  lea     edx, [rax+66h]; void *
0x18000f6b9  mov     rcx, [rbp+28h]; this
0x18000f6bd  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f6c4  mov     esi, 80004003h
0x18000f6c9  mov     r9d, esi; char *
0x18000f6cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f6d1  jmp     loc_18000F95B
0x18000f6d6  xor     r9d, r9d; lpSecurityAttributes
0x18000f6d9  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x18000f6de  mov     [rsp+80h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18000f6e3  mov     edx, 80000000h; dwDesiredAccess
0x18000f6e8  mov     [rsp+80h+dwCreationDisposition], 3; int
0x18000f6f0  lea     esi, [r9+1]
0x18000f6f4  mov     r8d, esi; dwShareMode
0x18000f6f7  call    cs:__imp_CreateFileW
0x18000f6fd  mov     r13, rax
0x18000f700  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f704  jnz     short loc_18000F745
0x18000f706  call    cs:__imp_GetLastError
0x18000f70c  movzx   esi, ax
0x18000f70f  or      esi, 80070000h
0x18000f715  test    eax, eax
0x18000f717  cmovle  esi, eax
0x18000f71a  test    esi, esi
0x18000f71c  js      short loc_18000F725
0x18000f71e  mov     esi, 8000FFFFh
0x18000f723  jmp     short loc_18000F73E
0x18000f725  mov     eax, esi
0x18000f727  cmp     esi, 80070002h
0x18000f72d  jz      loc_18000F91F
0x18000f733  cmp     eax, 80070003h
0x18000f738  jz      loc_18000F91F
0x18000f73e  mov     edx, 74h ; 't'
0x18000f743  jmp     short loc_18000F76F
0x18000f745  lea     rdx, [rbp+FileSize]; lpFileSize
0x18000f749  mov     qword ptr [rbp+FileSize], r12
0x18000f74d  mov     rcx, r13; hFile
0x18000f750  call    cs:__imp_GetFileSizeEx
0x18000f756  test    eax, eax
0x18000f758  jnz     short loc_18000F75F
0x18000f75a  lea     edx, [rax+7Ah]
0x18000f75d  jmp     short loc_18000F7DB
0x18000f75f  cmp     dword ptr [rbp+FileSize+4], r12d
0x18000f763  jz      short loc_18000F787
0x18000f765  mov     esi, 8007000Dh
0x18000f76a  mov     edx, 7Ch ; '|'; void *
0x18000f76f  mov     rcx, [rbp+28h]; this
0x18000f773  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f77a  mov     r9d, esi; char *
0x18000f77d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f782  jmp     loc_18000F91F
0x18000f787  xor     r9d, r9d; dwMaximumSizeHigh
0x18000f78a  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpName
0x18000f78f  xor     edx, edx; lpFileMappingAttributes
0x18000f791  mov     [rsp+80h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x18000f796  mov     rcx, r13; hFile
0x18000f799  lea     r8d, [r9+2]; flProtect
0x18000f79d  call    cs:__imp_CreateFileMappingW
0x18000f7a3  mov     rdi, rax
0x18000f7a6  test    rax, rax
0x18000f7a9  jnz     short loc_18000F7B0
0x18000f7ab  lea     edx, [rax+7Fh]
0x18000f7ae  jmp     short loc_18000F7DB
0x18000f7b0  xor     r9d, r9d; dwFileOffsetLow
0x18000f7b3  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpBaseAddress
0x18000f7b8  xor     r8d, r8d; dwFileOffsetHigh
0x18000f7bb  mov     qword ptr [rsp+80h+dwCreationDisposition], r12; int
0x18000f7c0  mov     rcx, rax; hFileMappingObject
0x18000f7c3  lea     edx, [r9+4]; dwDesiredAccess
0x18000f7c7  call    cs:__imp_MapViewOfFileEx
0x18000f7cd  mov     [rbp+lpBaseAddress], rax
0x18000f7d1  test    rax, rax
0x18000f7d4  jnz     short loc_18000F7F2
0x18000f7d6  mov     edx, 82h; void *
0x18000f7db  mov     rcx, [rbp+28h]; this
0x18000f7df  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f7e6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f7eb  mov     esi, eax
0x18000f7ed  jmp     loc_18000F91F
0x18000f7f2  mov     rdx, qword ptr [rbp+FileSize]; unsigned __int64
0x18000f7f6  lea     r9, [rbp+var_1C]; unsigned int *
0x18000f7fa  mov     rcx, rax
0x18000f7fd  lea     r8, [rbp+var_20]; unsigned int *
0x18000f801  or      rcx, rsi; hModule
0x18000f804  call    ?GetRawFileVersionFromModule@@YAJPEAUHINSTANCE__@@_KPEAK2@Z; GetRawFileVersionFromModule(HINSTANCE__ *,unsigned __int64,ulong *,ulong *)
0x18000f809  mov     r14d, eax
0x18000f80c  cmp     eax, 800710DCh
0x18000f811  jnz     loc_18000F8F5
0x18000f817  lea     r8, [rbp+dwHandle]; lpdwHandle
0x18000f81b  mov     [rbp+dwHandle], r12d
0x18000f81f  mov     rdx, r15; lpwstrFilename
0x18000f822  mov     [rbp+lpBuffer], r12
0x18000f826  xor     ecx, ecx; dwFlags
0x18000f828  mov     [rbp+puLen], r12d
0x18000f82c  call    cs:__imp_GetFileVersionInfoSizeExW
0x18000f832  mov     r12d, eax
0x18000f835  test    eax, eax
0x18000f837  jnz     short loc_18000F840
0x18000f839  mov     edx, 95h
0x18000f83e  jmp     short loc_18000F8AA
0x18000f840  mov     rcx, r12; unsigned __int64
0x18000f843  mov     rdx, rsi; unsigned __int64
0x18000f846  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x18000f84b  mov     rbx, rax
0x18000f84e  neg     rax
0x18000f851  sbb     esi, esi
0x18000f853  not     esi
0x18000f855  and     esi, 8007000Eh
0x18000f85b  test    rbx, rbx
0x18000f85e  jnz     short loc_18000F867
0x18000f860  mov     edx, 96h
0x18000f865  jmp     short loc_18000F8CE
0x18000f867  mov     r8d, [rbp+dwHandle]; dwHandle
0x18000f86b  mov     r9d, r12d; dwLen
0x18000f86e  mov     rdx, r15; lpwstrFilename
0x18000f871  mov     qword ptr [rsp+80h+dwCreationDisposition], rbx; int
0x18000f876  xor     ecx, ecx; dwFlags
0x18000f878  call    cs:__imp_GetFileVersionInfoExW
0x18000f87e  test    eax, eax
0x18000f880  jnz     short loc_18000F889
0x18000f882  mov     edx, 9Eh
0x18000f887  jmp     short loc_18000F8C9
0x18000f889  lea     r9, [rbp+puLen]; puLen
0x18000f88d  mov     rcx, rbx; pBlock
0x18000f890  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x18000f894  lea     rdx, SubBlock; "\\"
0x18000f89b  call    cs:__imp_VerQueryValueW
0x18000f8a1  test    eax, eax
0x18000f8a3  jnz     short loc_18000F8BE
0x18000f8a5  mov     edx, 0A1h; void *
0x18000f8aa  mov     rcx, [rbp+28h]; this
0x18000f8ae  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f8b5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f8ba  mov     esi, eax
0x18000f8bc  jmp     short loc_18000F915
0x18000f8be  cmp     [rbp+puLen], 34h ; '4'
0x18000f8c2  jnb     short loc_18000F8E3
0x18000f8c4  mov     edx, 0A2h; void *
0x18000f8c9  mov     esi, 80070714h
0x18000f8ce  mov     rcx, [rbp+28h]; this
0x18000f8d2  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f8d9  mov     r9d, esi; char *
0x18000f8dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f8e1  jmp     short loc_18000F915
0x18000f8e3  mov     rcx, [rbp+lpBuffer]
0x18000f8e7  mov     eax, [rcx+8]
0x18000f8ea  mov     [rbp+var_20], eax
0x18000f8ed  mov     eax, [rcx+0Ch]
0x18000f8f0  mov     [rbp+var_1C], eax
0x18000f8f3  jmp     short loc_18000F8FA
0x18000f8f5  test    r14d, r14d
0x18000f8f8  jns     short loc_18000F912
0x18000f8fa  mov     rcx, [rbp+28h]; this
0x18000f8fe  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000f905  mov     r9d, r14d; char *
0x18000f908  mov     edx, 0A8h; void *
0x18000f90d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f912  mov     esi, r14d
0x18000f915  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x18000f919  call    cs:__imp_UnmapViewOfFile
0x18000f91f  mov     eax, [rbp+var_20]
0x18000f922  mov     rcx, [rbp+var_38]
0x18000f926  mov     [rcx], eax
0x18000f928  mov     rcx, [rbp+var_30]
0x18000f92c  mov     eax, [rbp+var_1C]
0x18000f92f  mov     [rcx], eax
0x18000f931  test    rbx, rbx
0x18000f934  jz      short loc_18000F93E
0x18000f936  mov     rcx, rbx; lpMem
0x18000f939  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18000f93e  test    rdi, rdi
0x18000f941  jz      short loc_18000F94C
0x18000f943  mov     rcx, rdi; hObject
0x18000f946  call    cs:__imp_CloseHandle
0x18000f94c  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18000f950  jz      short loc_18000F95B
0x18000f952  mov     rcx, r13; hObject
0x18000f955  call    cs:__imp_CloseHandle
0x18000f95b  mov     eax, esi
0x18000f95d  mov     rcx, [rbp+var_8]
0x18000f961  xor     rcx, rsp; StackCookie
0x18000f964  call    __security_check_cookie
0x18000f969  lea     r11, [rsp+80h+var_s0]
0x18000f971  mov     rbx, [r11+38h]
0x18000f975  mov     rsi, [r11+40h]
0x18000f979  mov     rdi, [r11+48h]
0x18000f97d  mov     rsp, r11
0x18000f980  pop     r15
0x18000f982  pop     r14
0x18000f984  pop     r13
0x18000f986  pop     r12
0x18000f988  pop     rbp
0x18000f989  retn
```
