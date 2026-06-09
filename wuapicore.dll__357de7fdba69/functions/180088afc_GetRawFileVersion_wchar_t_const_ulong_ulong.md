# GetRawFileVersion(wchar_t const *,ulong *,ulong *)

- ea: `0x180088afc`
- end: `0x180088e3a`
- name: `?GetRawFileVersion@@YAJPEB_WPEAK1@Z`
- size: `830`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180089054`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x180081a38`
- `0x180081adc`
- `0x180088afc`
- `0x180088e40`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088bb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088df6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088e05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088df6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180088e05`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180088c77`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180088c77`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180088dc9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180088dc9`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180088c4d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180088c4d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180088c00`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180088c00`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180088ba7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180088ba7`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180088d28`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180088d28`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180088cdc`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180088cdc`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180088d4b`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180088d4b`

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
  _LARGE_INTEGER FileSize; // [rsp+70h] [rbp-10h] BYREF
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
0x180088afc  mov     [rsp-28h+arg_8], rbx
0x180088b01  mov     [rsp-28h+arg_10], rsi
0x180088b06  mov     [rsp-28h+arg_18], rdi
0x180088b0b  push    rbp
0x180088b0c  push    r12
0x180088b0e  push    r13
0x180088b10  push    r14
0x180088b12  push    r15
0x180088b14  mov     rbp, rsp
0x180088b17  sub     rsp, 80h
0x180088b1e  mov     rax, cs:__security_cookie
0x180088b25  xor     rax, rsp
0x180088b28  mov     [rbp+var_8], rax
0x180088b2c  xor     r12d, r12d
0x180088b2f  mov     [rbp+var_38], rdx
0x180088b33  mov     [rbp+var_20], r12d
0x180088b37  mov     rax, r8
0x180088b3a  mov     [rbp+var_30], rax
0x180088b3e  mov     r15, rcx
0x180088b41  mov     [rbp+var_1C], r12d
0x180088b45  mov     edi, r12d
0x180088b48  mov     ebx, r12d
0x180088b4b  test    rcx, rcx
0x180088b4e  jnz     short loc_180088B55
0x180088b50  lea     edx, [rcx+64h]
0x180088b53  jmp     short loc_180088B69
0x180088b55  test    rdx, rdx
0x180088b58  jnz     short loc_180088B61
0x180088b5a  mov     edx, 65h ; 'e'
0x180088b5f  jmp     short loc_180088B69
0x180088b61  test    rax, rax
0x180088b64  jnz     short loc_180088B86
0x180088b66  lea     edx, [rax+66h]; void *
0x180088b69  mov     rcx, [rbp+28h]; this
0x180088b6d  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180088b74  mov     esi, 80004003h
0x180088b79  mov     r9d, esi; char *
0x180088b7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088b81  jmp     loc_180088E0B
0x180088b86  xor     r9d, r9d; lpSecurityAttributes
0x180088b89  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x180088b8e  mov     [rsp+80h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180088b93  mov     edx, 80000000h; dwDesiredAccess
0x180088b98  mov     [rsp+80h+dwCreationDisposition], 3; int
0x180088ba0  lea     esi, [r9+1]
0x180088ba4  mov     r8d, esi; dwShareMode
0x180088ba7  call    cs:__imp_CreateFileW
0x180088bad  mov     r13, rax
0x180088bb0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180088bb4  jnz     short loc_180088BF5
0x180088bb6  call    cs:__imp_GetLastError
0x180088bbc  movzx   esi, ax
0x180088bbf  or      esi, 80070000h
0x180088bc5  test    eax, eax
0x180088bc7  cmovle  esi, eax
0x180088bca  test    esi, esi
0x180088bcc  js      short loc_180088BD5
0x180088bce  mov     esi, 8000FFFFh
0x180088bd3  jmp     short loc_180088BEE
0x180088bd5  mov     eax, esi
0x180088bd7  cmp     esi, 80070002h
0x180088bdd  jz      loc_180088DCF
0x180088be3  cmp     eax, 80070003h
0x180088be8  jz      loc_180088DCF
0x180088bee  mov     edx, 74h ; 't'
0x180088bf3  jmp     short loc_180088C1F
0x180088bf5  lea     rdx, [rbp+FileSize]; lpFileSize
0x180088bf9  mov     qword ptr [rbp+FileSize], r12
0x180088bfd  mov     rcx, r13; hFile
0x180088c00  call    cs:__imp_GetFileSizeEx
0x180088c06  test    eax, eax
0x180088c08  jnz     short loc_180088C0F
0x180088c0a  lea     edx, [rax+7Ah]
0x180088c0d  jmp     short loc_180088C8B
0x180088c0f  cmp     dword ptr [rbp+FileSize+4], r12d
0x180088c13  jz      short loc_180088C37
0x180088c15  mov     esi, 8007000Dh
0x180088c1a  mov     edx, 7Ch ; '|'; void *
0x180088c1f  mov     rcx, [rbp+28h]; this
0x180088c23  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180088c2a  mov     r9d, esi; char *
0x180088c2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088c32  jmp     loc_180088DCF
0x180088c37  xor     r9d, r9d; dwMaximumSizeHigh
0x180088c3a  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpName
0x180088c3f  xor     edx, edx; lpFileMappingAttributes
0x180088c41  mov     [rsp+80h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x180088c46  mov     rcx, r13; hFile
0x180088c49  lea     r8d, [r9+2]; flProtect
0x180088c4d  call    cs:__imp_CreateFileMappingW
0x180088c53  mov     rdi, rax
0x180088c56  test    rax, rax
0x180088c59  jnz     short loc_180088C60
0x180088c5b  lea     edx, [rax+7Fh]
0x180088c5e  jmp     short loc_180088C8B
0x180088c60  xor     r9d, r9d; dwFileOffsetLow
0x180088c63  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r12; lpBaseAddress
0x180088c68  xor     r8d, r8d; dwFileOffsetHigh
0x180088c6b  mov     qword ptr [rsp+80h+dwCreationDisposition], r12; int
0x180088c70  mov     rcx, rax; hFileMappingObject
0x180088c73  lea     edx, [r9+4]; dwDesiredAccess
0x180088c77  call    cs:__imp_MapViewOfFileEx
0x180088c7d  mov     [rbp+lpBaseAddress], rax
0x180088c81  test    rax, rax
0x180088c84  jnz     short loc_180088CA2
0x180088c86  mov     edx, 82h; void *
0x180088c8b  mov     rcx, [rbp+28h]; this
0x180088c8f  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180088c96  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180088c9b  mov     esi, eax
0x180088c9d  jmp     loc_180088DCF
0x180088ca2  mov     rdx, qword ptr [rbp+FileSize]; unsigned __int64
0x180088ca6  lea     r9, [rbp+var_1C]; unsigned int *
0x180088caa  mov     rcx, rax
0x180088cad  lea     r8, [rbp+var_20]; unsigned int *
0x180088cb1  or      rcx, rsi; hModule
0x180088cb4  call    ?GetRawFileVersionFromModule@@YAJPEAUHINSTANCE__@@_KPEAK2@Z; GetRawFileVersionFromModule(HINSTANCE__ *,unsigned __int64,ulong *,ulong *)
0x180088cb9  mov     r14d, eax
0x180088cbc  cmp     eax, 800710DCh
0x180088cc1  jnz     loc_180088DA5
0x180088cc7  lea     r8, [rbp+dwHandle]; lpdwHandle
0x180088ccb  mov     [rbp+dwHandle], r12d
0x180088ccf  mov     rdx, r15; lpwstrFilename
0x180088cd2  mov     [rbp+lpBuffer], r12
0x180088cd6  xor     ecx, ecx; dwFlags
0x180088cd8  mov     [rbp+puLen], r12d
0x180088cdc  call    cs:__imp_GetFileVersionInfoSizeExW
0x180088ce2  mov     r12d, eax
0x180088ce5  test    eax, eax
0x180088ce7  jnz     short loc_180088CF0
0x180088ce9  mov     edx, 95h
0x180088cee  jmp     short loc_180088D5A
0x180088cf0  mov     rcx, r12; unsigned __int64
0x180088cf3  mov     rdx, rsi; unsigned __int64
0x180088cf6  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180088cfb  mov     rbx, rax
0x180088cfe  neg     rax
0x180088d01  sbb     esi, esi
0x180088d03  not     esi
0x180088d05  and     esi, 8007000Eh
0x180088d0b  test    rbx, rbx
0x180088d0e  jnz     short loc_180088D17
0x180088d10  mov     edx, 96h
0x180088d15  jmp     short loc_180088D7E
0x180088d17  mov     r8d, [rbp+dwHandle]; dwHandle
0x180088d1b  mov     r9d, r12d; dwLen
0x180088d1e  mov     rdx, r15; lpwstrFilename
0x180088d21  mov     qword ptr [rsp+80h+dwCreationDisposition], rbx; int
0x180088d26  xor     ecx, ecx; dwFlags
0x180088d28  call    cs:__imp_GetFileVersionInfoExW
0x180088d2e  test    eax, eax
0x180088d30  jnz     short loc_180088D39
0x180088d32  mov     edx, 9Eh
0x180088d37  jmp     short loc_180088D79
0x180088d39  lea     r9, [rbp+puLen]; puLen
0x180088d3d  mov     rcx, rbx; pBlock
0x180088d40  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x180088d44  lea     rdx, SubBlock; "\\"
0x180088d4b  call    cs:__imp_VerQueryValueW
0x180088d51  test    eax, eax
0x180088d53  jnz     short loc_180088D6E
0x180088d55  mov     edx, 0A1h; void *
0x180088d5a  mov     rcx, [rbp+28h]; this
0x180088d5e  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180088d65  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180088d6a  mov     esi, eax
0x180088d6c  jmp     short loc_180088DC5
0x180088d6e  cmp     [rbp+puLen], 34h ; '4'
0x180088d72  jnb     short loc_180088D93
0x180088d74  mov     edx, 0A2h; void *
0x180088d79  mov     esi, 80070714h
0x180088d7e  mov     rcx, [rbp+28h]; this
0x180088d82  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180088d89  mov     r9d, esi; char *
0x180088d8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088d91  jmp     short loc_180088DC5
0x180088d93  mov     rcx, [rbp+lpBuffer]
0x180088d97  mov     eax, [rcx+8]
0x180088d9a  mov     [rbp+var_20], eax
0x180088d9d  mov     eax, [rcx+0Ch]
0x180088da0  mov     [rbp+var_1C], eax
0x180088da3  jmp     short loc_180088DAA
0x180088da5  test    r14d, r14d
0x180088da8  jns     short loc_180088DC2
0x180088daa  mov     rcx, [rbp+28h]; this
0x180088dae  lea     r8, aCW1SSrcClientL; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180088db5  mov     r9d, r14d; char *
0x180088db8  mov     edx, 0A8h; void *
0x180088dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180088dc2  mov     esi, r14d
0x180088dc5  mov     rcx, [rbp+lpBaseAddress]; lpBaseAddress
0x180088dc9  call    cs:__imp_UnmapViewOfFile
0x180088dcf  mov     eax, [rbp+var_20]
0x180088dd2  mov     rcx, [rbp+var_38]
0x180088dd6  mov     [rcx], eax
0x180088dd8  mov     rcx, [rbp+var_30]
0x180088ddc  mov     eax, [rbp+var_1C]
0x180088ddf  mov     [rcx], eax
0x180088de1  test    rbx, rbx
0x180088de4  jz      short loc_180088DEE
0x180088de6  mov     rcx, rbx; lpMem
0x180088de9  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180088dee  test    rdi, rdi
0x180088df1  jz      short loc_180088DFC
0x180088df3  mov     rcx, rdi; hObject
0x180088df6  call    cs:__imp_CloseHandle
0x180088dfc  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180088e00  jz      short loc_180088E0B
0x180088e02  mov     rcx, r13; hObject
0x180088e05  call    cs:__imp_CloseHandle
0x180088e0b  mov     eax, esi
0x180088e0d  mov     rcx, [rbp+var_8]
0x180088e11  xor     rcx, rsp; StackCookie
0x180088e14  call    __security_check_cookie
0x180088e19  lea     r11, [rsp+80h+var_s0]
0x180088e21  mov     rbx, [r11+38h]
0x180088e25  mov     rsi, [r11+40h]
0x180088e29  mov     rdi, [r11+48h]
0x180088e2d  mov     rsp, r11
0x180088e30  pop     r15
0x180088e32  pop     r14
0x180088e34  pop     r13
0x180088e36  pop     r12
0x180088e38  pop     rbp
0x180088e39  retn
```
