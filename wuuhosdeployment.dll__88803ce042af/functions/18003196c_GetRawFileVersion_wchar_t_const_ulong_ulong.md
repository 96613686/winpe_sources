# GetRawFileVersion(wchar_t const *,ulong *,ulong *)

- ea: `0x18003196c`
- end: `0x180031caa`
- name: `?GetRawFileVersion@@YAJPEB_WPEAK1@Z`
- size: `830`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180031890`

## callees

- `0x180003950`
- `0x180003974`
- `0x180005f64`
- `0x18000a6d0`
- `0x18003196c`
- `0x180031cb0`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031c66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031c75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031c66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031c75`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180031abd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180031abd`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180031ae7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180031ae7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180031c39`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180031c39`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180031bbb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180031bbb`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180031b4c`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180031b4c`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180031b98`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180031b98`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180031a70`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180031a70`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031a17`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031a17`

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
    CSusBaseAllocTag<942762101>::operator delete(v5);
  if ( v4 )
    CloseHandle(v4);
  if ( v9 != (void *)-1LL )
    CloseHandle(v9);
  return v7;
}

```

## disassembly

```asm
0x18003196c  mov     [rsp-28h+arg_8], rbx
0x180031971  mov     [rsp-28h+arg_10], rsi
0x180031976  mov     [rsp-28h+arg_18], rdi
0x18003197b  push    rbp
0x18003197c  push    r12
0x18003197e  push    r13
0x180031980  push    r14
0x180031982  push    r15
0x180031984  mov     rbp, rsp
0x180031987  sub     rsp, 80h
0x18003198e  mov     rax, cs:__security_cookie
0x180031995  xor     rax, rsp
0x180031998  mov     [rbp+var_8], rax
0x18003199c  xor     r12d, r12d
0x18003199f  mov     [rbp+var_38], rdx
0x1800319a3  mov     [rbp+var_20], r12d
0x1800319a7  mov     rax, r8
0x1800319aa  mov     [rbp+var_30], rax
0x1800319ae  mov     r15, rcx
0x1800319b1  mov     [rbp+var_1C], r12d
0x1800319b5  mov     edi, r12d
0x1800319b8  mov     ebx, r12d
0x1800319bb  test    rcx, rcx
0x1800319be  jnz     short loc_1800319C5
0x1800319c0  lea     edx, [rcx+64h]
0x1800319c3  jmp     short loc_1800319D9
0x1800319c5  test    rdx, rdx
0x1800319c8  jnz     short loc_1800319D1
0x1800319ca  mov     edx, 65h ; 'e'
0x1800319cf  jmp     short loc_1800319D9
0x1800319d1  test    rax, rax
0x1800319d4  jnz     short loc_1800319F6
0x1800319d6  lea     edx, [rax+66h]; void *
0x1800319d9  mov     rcx, [rbp+28h]; this
0x1800319dd  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800319e4  mov     esi, 80004003h
0x1800319e9  mov     r9d, esi; char *
0x1800319ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800319f1  jmp     loc_180031C7B
0x1800319f6  xor     r9d, r9d; lpSecurityAttributes
0x1800319f9  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x1800319fe  mov     [rsp+80h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180031a03  mov     edx, 80000000h; dwDesiredAccess
0x180031a08  mov     [rsp+80h+dwCreationDisposition], 3; int
0x180031a10  lea     esi, [r9+1]
0x180031a14  mov     r8d, esi; dwShareMode
0x180031a17  call    cs:__imp_CreateFileW
0x180031a1d  mov     r13, rax
0x180031a20  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031a24  jnz     short loc_180031A65
0x180031a26  call    cs:__imp_GetLastError
0x180031a2c  movzx   esi, ax
0x180031a2f  or      esi, 80070000h
0x180031a35  test    eax, eax
0x180031a37  cmovle  esi, eax
0x180031a3a  test    esi, esi
0x180031a3c  js      short loc_180031A45
0x180031a3e  mov     esi, 8000FFFFh
0x180031a43  jmp     short loc_180031A5E
0x180031a45  mov     eax, esi
0x180031a47  cmp     esi, 80070002h
0x180031a4d  jz      loc_180031C3F
0x180031a53  cmp     eax, 80070003h
0x180031a58  jz      loc_180031C3F
0x180031a5e  mov     edx, 74h ; 't'
0x180031a63  jmp     short loc_180031A8F
0x180031a65  lea     rdx, [rbp+FileSize]; lpFileSize
0x180031a69  mov     qword ptr [rbp+FileSize], r12
0x180031a6d  mov     rcx, r13; hFile
0x180031a70  call    cs:__imp_GetFileSizeEx
0x180031a76  test    eax, eax
0x180031a78  jnz     short loc_180031A7F
0x180031a7a  lea     edx, [rax+7Ah]
0x180031a7d  jmp     short loc_180031AFB
0x180031a7f  cmp     dword ptr [rbp+FileSize+4], r12d
0x180031a83  jz      short loc_180031AA7
0x180031a85  mov     esi, 8007000Dh
0x180031a8a  mov     edx, 7Ch ; '|'; void *
0x180031a8f  mov     rcx, [rbp+28h]; this
0x180031a93  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180031a9a  mov     r9d, esi; char *
0x180031a9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031aa2  jmp     loc_180031C3F
0x180031aa7  xor     r9d, r9d; dwMaximumSizeHigh
0x180031aaa  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpName
0x180031aaf  xor     edx, edx; lpFileMappingAttributes
0x180031ab1  mov     [rsp+80h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x180031ab6  mov     rcx, r13; hFile
0x180031ab9  lea     r8d, [r9+2]; flProtect
0x180031abd  call    cs:__imp_CreateFileMappingW
0x180031ac3  mov     rdi, rax
0x180031ac6  test    rax, rax
0x180031ac9  jnz     short loc_180031AD0
0x180031acb  lea     edx, [rax+7Fh]
0x180031ace  jmp     short loc_180031AFB
0x180031ad0  xor     r9d, r9d; dwFileOffsetLow
0x180031ad3  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpBaseAddress
0x180031ad8  xor     r8d, r8d; dwFileOffsetHigh
0x180031adb  mov     qword ptr [rsp+80h+dwCreationDisposition], r12; int
0x180031ae0  mov     rcx, rax; hFileMappingObject
0x180031ae3  lea     edx, [r9+4]; dwDesiredAccess
0x180031ae7  call    cs:__imp_MapViewOfFileEx
0x180031aed  mov     [rbp+lpBaseAddress], rax
0x180031af1  test    rax, rax
0x180031af4  jnz     short loc_180031B12
0x180031af6  mov     edx, 82h; void *
0x180031afb  mov     rcx, [rbp+28h]; this
0x180031aff  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180031b06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031b0b  mov     esi, eax
0x180031b0d  jmp     loc_180031C3F
0x180031b12  mov     rdx, qword ptr [rbp+FileSize]; unsigned __int64
0x180031b16  lea     r9, [rbp+var_1C]; unsigned int *
0x180031b1a  mov     rcx, rax
0x180031b1d  lea     r8, [rbp+var_20]; unsigned int *
0x180031b21  or      rcx, rsi; hModule
0x180031b24  call    ?GetRawFileVersionFromModule@@YAJPEAUHINSTANCE__@@_KPEAK2@Z; GetRawFileVersionFromModule(HINSTANCE__ *,unsigned __int64,ulong *,ulong *)
0x180031b29  mov     r14d, eax
0x180031b2c  cmp     eax, 800710DCh
0x180031b31  jnz     loc_180031C15
0x180031b37  lea     r8, [rbp+dwHandle]; lpdwHandle
0x180031b3b  mov     [rbp+dwHandle], r12d
0x180031b3f  mov     rdx, r15; lpwstrFilename
0x180031b42  mov     [rbp+lpBuffer], r12
0x180031b46  xor     ecx, ecx; dwFlags
0x180031b48  mov     [rbp+puLen], r12d
0x180031b4c  call    cs:__imp_GetFileVersionInfoSizeExW
0x180031b52  mov     r12d, eax
0x180031b55  test    eax, eax
0x180031b57  jnz     short loc_180031B60
0x180031b59  mov     edx, 95h
0x180031b5e  jmp     short loc_180031BCA
0x180031b60  mov     rcx, r12; unsigned __int64
0x180031b63  mov     rdx, rsi; unsigned __int64
0x180031b66  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180031b6b  mov     rbx, rax
0x180031b6e  neg     rax
0x180031b71  sbb     esi, esi
0x180031b73  not     esi
0x180031b75  and     esi, 8007000Eh
0x180031b7b  test    rbx, rbx
0x180031b7e  jnz     short loc_180031B87
0x180031b80  mov     edx, 96h
0x180031b85  jmp     short loc_180031BEE
0x180031b87  mov     r8d, [rbp+dwHandle]; dwHandle
0x180031b8b  mov     r9d, r12d; dwLen
0x180031b8e  mov     rdx, r15; lpwstrFilename
0x180031b91  mov     qword ptr [rsp+80h+dwCreationDisposition], rbx; int
0x180031b96  xor     ecx, ecx; dwFlags
0x180031b98  call    cs:__imp_GetFileVersionInfoExW
0x180031b9e  test    eax, eax
0x180031ba0  jnz     short loc_180031BA9
0x180031ba2  mov     edx, 9Eh
0x180031ba7  jmp     short loc_180031BE9
0x180031ba9  lea     r9, [rbp+puLen]; puLen
0x180031bad  mov     rcx, rbx; pBlock
0x180031bb0  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x180031bb4  lea     rdx, SubBlock; "\\"
0x180031bbb  call    cs:__imp_VerQueryValueW
0x180031bc1  test    eax, eax
0x180031bc3  jnz     short loc_180031BDE
0x180031bc5  mov     edx, 0A1h; void *
0x180031bca  mov     rcx, [rbp+28h]; this
0x180031bce  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180031bd5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031bda  mov     esi, eax
0x180031bdc  jmp     short loc_180031C35
0x180031bde  cmp     [rbp+puLen], 34h ; '4'
0x180031be2  jnb     short loc_180031C03
0x180031be4  mov     edx, 0A2h; void *
0x180031be9  mov     esi, 80070714h
0x180031bee  mov     rcx, [rbp+28h]; this
0x180031bf2  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180031bf9  mov     r9d, esi; char *
0x180031bfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031c01  jmp     short loc_180031C35
0x180031c03  mov     rcx, [rbp+lpBuffer]
0x180031c07  mov     eax, [rcx+8]
0x180031c0a  mov     [rbp+var_20], eax
0x180031c0d  mov     eax, [rcx+0Ch]
0x180031c10  mov     [rbp+var_1C], eax
0x180031c13  jmp     short loc_180031C1A
0x180031c15  test    r14d, r14d
0x180031c18  jns     short loc_180031C32
0x180031c1a  mov     rcx, [rbp+28h]; this
0x180031c1e  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180031c25  mov     r9d, r14d; char *
0x180031c28  mov     edx, 0A8h; void *
0x180031c2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031c32  mov     esi, r14d
0x180031c35  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x180031c39  call    cs:__imp_UnmapViewOfFile
0x180031c3f  mov     eax, [rbp+var_20]
0x180031c42  mov     rcx, [rbp+var_38]
0x180031c46  mov     [rcx], eax
0x180031c48  mov     rcx, [rbp+var_30]
0x180031c4c  mov     eax, [rbp+var_1C]
0x180031c4f  mov     [rcx], eax
0x180031c51  test    rbx, rbx
0x180031c54  jz      short loc_180031C5E
0x180031c56  mov     rcx, rbx; lpMem
0x180031c59  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180031c5e  test    rdi, rdi
0x180031c61  jz      short loc_180031C6C
0x180031c63  mov     rcx, rdi; hObject
0x180031c66  call    cs:__imp_CloseHandle
0x180031c6c  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180031c70  jz      short loc_180031C7B
0x180031c72  mov     rcx, r13; hObject
0x180031c75  call    cs:__imp_CloseHandle
0x180031c7b  mov     eax, esi
0x180031c7d  mov     rcx, [rbp+var_8]
0x180031c81  xor     rcx, rsp; StackCookie
0x180031c84  call    __security_check_cookie
0x180031c89  lea     r11, [rsp+80h+var_s0]
0x180031c91  mov     rbx, [r11+38h]
0x180031c95  mov     rsi, [r11+40h]
0x180031c99  mov     rdi, [r11+48h]
0x180031c9d  mov     rsp, r11
0x180031ca0  pop     r15
0x180031ca2  pop     r14
0x180031ca4  pop     r13
0x180031ca6  pop     r12
0x180031ca8  pop     rbp
0x180031ca9  retn
```
