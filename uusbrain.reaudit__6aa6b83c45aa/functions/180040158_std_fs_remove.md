# __std_fs_remove

- ea: `0x180040158`
- end: `0x1800403e8`
- name: `__std_fs_remove`
- size: `656`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800250d0`
- `0x1800252e0`

## callees

- `0x18003fe44`
- `0x18003fec4`
- `0x180040158`
- `0x180042640`
- `0x1800427d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004025e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800402db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004025e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800402db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004022a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800402f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004022a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800402f1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800401c2`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180040321`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18004035e`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800401c2`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180040321`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18004035e`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800402c4`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800402c4`

## pseudocode

```c
__int64 __fastcall _std_fs_remove(__int64 a1)
{
  char v2; // di
  int v3; // ecx
  HANDLE v4; // rbx
  HANDLE v5; // rcx
  int v6; // eax
  DWORD LastError; // eax
  int v9; // eax
  __int64 v10; // [rsp+20h] [rbp-50h]
  HANDLE hFile; // [rsp+28h] [rbp-48h] BYREF
  int FileInformation; // [rsp+30h] [rbp-40h] BYREF
  _OWORD v13[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v14; // [rsp+58h] [rbp-18h]

  v2 = 0;
  v3 = _std_fs_open_handle(&hFile, a1, 65920, 35651584);
  if ( !v3 )
  {
    v2 = 1;
    goto LABEL_3;
  }
  if ( v3 != 5 )
  {
    LOBYTE(v10) = 0;
    *(_WORD *)((char *)&v10 + 1) = 0;
    BYTE3(v10) = 0;
    if ( v3 == 2 || v3 == 3 || v3 == 53 || v3 == 64 || v3 == 123 || v3 == 267 )
      v3 = 0;
    HIDWORD(v10) = v3;
LABEL_10:
    v5 = hFile;
    if ( hFile == (HANDLE)-1LL )
      return v10;
LABEL_11:
    if ( !CloseHandle(v5) )
      abort();
    return v10;
  }
  v6 = _std_fs_open_handle(&hFile, a1, 0x10000, 35651584);
  if ( v6 )
  {
    LOBYTE(v10) = 0;
    *(_WORD *)((char *)&v10 + 1) = 0;
    BYTE3(v10) = 0;
    HIDWORD(v10) = v6;
    goto LABEL_10;
  }
LABEL_3:
  v4 = hFile;
  FileInformation = 19;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
  {
LABEL_4:
    v10 = 1;
LABEL_5:
    if ( v4 == (HANDLE)-1LL )
      return v10;
    v5 = v4;
    goto LABEL_11;
  }
  LastError = GetLastError();
  if ( LastError != 1 && LastError != 50 && LastError != 87 )
    goto LABEL_16;
  LastError = anonymous_namespace_::_Set_delete_flag(v4);
  if ( !LastError )
    goto LABEL_4;
  if ( LastError != 5 || !v2 )
  {
LABEL_16:
    LOBYTE(v10) = 0;
    *(_WORD *)((char *)&v10 + 1) = 0;
    BYTE3(v10) = 0;
    goto LABEL_17;
  }
  v14 = 0;
  memset(v13, 0, sizeof(v13));
  if ( GetFileInformationByHandleEx(v4, FileBasicInfo, v13, 0x28u) )
  {
    if ( (v14 & 1) == 0 )
    {
      LOBYTE(v10) = 0;
      goto LABEL_33;
    }
    LODWORD(v14) = v14 ^ 1;
    if ( !SetFileInformationByHandle(v4, FileBasicInfo, v13, 0x28u) )
      goto LABEL_22;
    v9 = anonymous_namespace_::_Set_delete_flag(v4);
    if ( !v9 )
    {
      v10 = 1;
      goto LABEL_24;
    }
    if ( v9 == 5 )
    {
      LODWORD(v14) = v14 | 1;
      LOBYTE(v10) = 0;
      if ( !SetFileInformationByHandle(v4, FileBasicInfo, v13, 0x28u) )
        goto LABEL_23;
LABEL_33:
      HIDWORD(v10) = 5;
      *(_WORD *)((char *)&v10 + 1) = 0;
      BYTE3(v10) = 0;
      goto LABEL_24;
    }
    LOBYTE(v10) = 0;
    *(_WORD *)((char *)&v10 + 1) = 0;
    BYTE3(v10) = 0;
    LastError = GetLastError();
LABEL_17:
    HIDWORD(v10) = LastError;
    goto LABEL_5;
  }
LABEL_22:
  LOBYTE(v10) = 0;
LABEL_23:
  *(_WORD *)((char *)&v10 + 1) = 0;
  BYTE3(v10) = 0;
  HIDWORD(v10) = GetLastError();
LABEL_24:
  if ( v4 != (HANDLE)-1LL && !CloseHandle(v4) )
    abort();
  return v10;
}

```

## disassembly

```asm
0x180040158  mov     [rsp-8+arg_8], rbx
0x18004015d  mov     [rsp-8+arg_10], rsi
0x180040162  mov     [rsp-8+arg_18], rdi
0x180040167  push    rbp
0x180040168  mov     rbp, rsp
0x18004016b  sub     rsp, 70h
0x18004016f  mov     rax, cs:__security_cookie
0x180040176  xor     rax, rsp
0x180040179  mov     [rbp+var_10], rax
0x18004017d  mov     rbx, rcx
0x180040180  mov     rdx, rcx
0x180040183  xor     esi, esi
0x180040185  lea     rcx, [rbp+hFile]
0x180040189  mov     r9d, 2200000h
0x18004018f  mov     r8d, 10180h
0x180040195  mov     dil, sil
0x180040198  call    __std_fs_open_handle
0x18004019d  mov     ecx, eax
0x18004019f  test    eax, eax
0x1800401a1  jnz     short loc_1800401EB
0x1800401a3  mov     dil, 1
0x1800401a6  mov     rbx, [rbp+hFile]
0x1800401aa  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1800401ae  mov     r9d, 4; dwBufferSize
0x1800401b4  mov     [rbp+FileInformation], 13h
0x1800401bb  mov     rcx, rbx; hFile
0x1800401be  lea     edx, [r9+11h]; FileInformationClass
0x1800401c2  call    cs:__imp_SetFileInformationByHandle
0x1800401c8  test    eax, eax
0x1800401ca  jz      loc_18004025E
0x1800401d0  xor     eax, eax
0x1800401d2  mov     byte ptr [rbp+var_50], 1
0x1800401d6  mov     word ptr [rbp+var_50+1], ax
0x1800401da  mov     byte ptr [rbp+var_50+3], al
0x1800401dd  mov     dword ptr [rbp+var_50+4], esi
0x1800401e0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800401e4  jz      short loc_180040238
0x1800401e6  mov     rcx, rbx
0x1800401e9  jmp     short loc_18004022A
0x1800401eb  cmp     ecx, 5
0x1800401ee  jnz     loc_1800403A3
0x1800401f4  mov     r9d, 2200000h
0x1800401fa  lea     rcx, [rbp+hFile]
0x1800401fe  mov     r8d, 10000h
0x180040204  mov     rdx, rbx
0x180040207  call    __std_fs_open_handle
0x18004020c  test    eax, eax
0x18004020e  jz      short loc_1800401A6
0x180040210  xor     ecx, ecx
0x180040212  mov     byte ptr [rbp+var_50], sil
0x180040216  mov     word ptr [rbp+var_50+1], cx
0x18004021a  mov     byte ptr [rbp+var_50+3], cl
0x18004021d  mov     dword ptr [rbp+var_50+4], eax
0x180040220  mov     rcx, [rbp+hFile]; hObject
0x180040224  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180040228  jz      short loc_180040238
0x18004022a  call    cs:__imp_CloseHandle
0x180040230  test    eax, eax
0x180040232  jz      loc_1800403DC
0x180040238  mov     rax, [rbp+var_50]
0x18004023c  mov     rcx, [rbp+var_10]
0x180040240  xor     rcx, rsp; StackCookie
0x180040243  call    __security_check_cookie
0x180040248  lea     r11, [rsp+70h+var_s0]
0x18004024d  mov     rbx, [r11+18h]
0x180040251  mov     rsi, [r11+20h]
0x180040255  mov     rdi, [r11+28h]
0x180040259  mov     rsp, r11
0x18004025c  pop     rbp
0x18004025d  retn
0x18004025e  call    cs:__imp_GetLastError
0x180040264  mov     ecx, eax
0x180040266  sub     ecx, 1
0x180040269  jz      short loc_18004028A
0x18004026b  sub     ecx, 31h ; '1'
0x18004026e  jz      short loc_18004028A
0x180040270  cmp     ecx, 25h ; '%'
0x180040273  jz      short loc_18004028A
0x180040275  xor     ecx, ecx
0x180040277  mov     byte ptr [rbp+var_50], sil
0x18004027b  mov     word ptr [rbp+var_50+1], cx
0x18004027f  mov     byte ptr [rbp+var_50+3], cl
0x180040282  mov     dword ptr [rbp+var_50+4], eax
0x180040285  jmp     loc_1800401E0
0x18004028a  mov     rcx, rbx; hFile
0x18004028d  call    _anonymous_namespace____Set_delete_flag
0x180040292  test    eax, eax
0x180040294  jz      loc_1800401D0
0x18004029a  cmp     eax, 5
0x18004029d  jnz     short loc_180040275
0x18004029f  test    dil, dil
0x1800402a2  jz      short loc_180040275
0x1800402a4  xor     eax, eax
0x1800402a6  lea     r8, [rbp+var_38]; lpFileInformation
0x1800402aa  xorps   xmm0, xmm0
0x1800402ad  mov     [rbp+var_18], rax
0x1800402b1  xor     edx, edx; FileInformationClass
0x1800402b3  mov     rcx, rbx; hFile
0x1800402b6  movups  [rbp+var_38], xmm0
0x1800402ba  lea     edi, [rax+28h]
0x1800402bd  mov     r9d, edi; dwBufferSize
0x1800402c0  movups  [rbp+var_28], xmm0
0x1800402c4  call    cs:__imp_GetFileInformationByHandleEx
0x1800402ca  test    eax, eax
0x1800402cc  jnz     short loc_180040304
0x1800402ce  mov     byte ptr [rbp+var_50], sil
0x1800402d2  xor     eax, eax
0x1800402d4  mov     word ptr [rbp+var_50+1], ax
0x1800402d8  mov     byte ptr [rbp+var_50+3], al
0x1800402db  call    cs:__imp_GetLastError
0x1800402e1  mov     dword ptr [rbp+var_50+4], eax
0x1800402e4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800402e8  jz      loc_180040238
0x1800402ee  mov     rcx, rbx; hObject
0x1800402f1  call    cs:__imp_CloseHandle
0x1800402f7  test    eax, eax
0x1800402f9  jz      loc_1800403E2
0x1800402ff  jmp     loc_180040238
0x180040304  mov     eax, dword ptr [rbp+var_18]
0x180040307  test    al, 1
0x180040309  jz      loc_18004039D
0x18004030f  xor     eax, 1
0x180040312  lea     r8, [rbp+var_38]; lpFileInformation
0x180040316  mov     r9d, edi; dwBufferSize
0x180040319  mov     dword ptr [rbp+var_18], eax
0x18004031c  xor     edx, edx; FileInformationClass
0x18004031e  mov     rcx, rbx; hFile
0x180040321  call    cs:__imp_SetFileInformationByHandle
0x180040327  test    eax, eax
0x180040329  jz      short loc_1800402CE
0x18004032b  mov     rcx, rbx; hFile
0x18004032e  call    _anonymous_namespace____Set_delete_flag
0x180040333  test    eax, eax
0x180040335  jnz     short loc_180040349
0x180040337  xor     eax, eax
0x180040339  mov     byte ptr [rbp+var_50], 1
0x18004033d  mov     word ptr [rbp+var_50+1], ax
0x180040341  mov     byte ptr [rbp+var_50+3], al
0x180040344  mov     dword ptr [rbp+var_50+4], esi
0x180040347  jmp     short loc_1800402E4
0x180040349  cmp     eax, 5
0x18004034c  jnz     short loc_180040385
0x18004034e  or      dword ptr [rbp+var_18], 1
0x180040352  lea     r8, [rbp+var_38]; lpFileInformation
0x180040356  mov     r9d, edi; dwBufferSize
0x180040359  xor     edx, edx; FileInformationClass
0x18004035b  mov     rcx, rbx; hFile
0x18004035e  call    cs:__imp_SetFileInformationByHandle
0x180040364  mov     byte ptr [rbp+var_50], sil
0x180040368  test    eax, eax
0x18004036a  jz      loc_1800402D2
0x180040370  xor     eax, eax
0x180040372  mov     dword ptr [rbp+var_50+4], 5
0x180040379  mov     word ptr [rbp+var_50+1], ax
0x18004037d  mov     byte ptr [rbp+var_50+3], al
0x180040380  jmp     loc_1800402E4
0x180040385  xor     eax, eax
0x180040387  mov     byte ptr [rbp+var_50], sil
0x18004038b  mov     word ptr [rbp+var_50+1], ax
0x18004038f  mov     byte ptr [rbp+var_50+3], al
0x180040392  call    cs:__imp_GetLastError
0x180040398  jmp     loc_180040282
0x18004039d  mov     byte ptr [rbp+var_50], sil
0x1800403a1  jmp     short loc_180040370
0x1800403a3  xor     eax, eax
0x1800403a5  mov     byte ptr [rbp+var_50], sil
0x1800403a9  mov     word ptr [rbp+var_50+1], ax
0x1800403ad  mov     byte ptr [rbp+var_50+3], al
0x1800403b0  mov     eax, ecx
0x1800403b2  sub     eax, 2
0x1800403b5  jz      short loc_1800403D2
0x1800403b7  sub     eax, 1
0x1800403ba  jz      short loc_1800403D2
0x1800403bc  sub     eax, 32h ; '2'
0x1800403bf  jz      short loc_1800403D2
0x1800403c1  sub     eax, 0Bh
0x1800403c4  jz      short loc_1800403D2
0x1800403c6  sub     eax, 3Bh ; ';'
0x1800403c9  jz      short loc_1800403D2
0x1800403cb  cmp     eax, 90h
0x1800403d0  jnz     short loc_1800403D4
0x1800403d2  mov     ecx, esi
0x1800403d4  mov     dword ptr [rbp+var_50+4], ecx
0x1800403d7  jmp     loc_180040220
0x1800403dc  call    abort
0x1800403e2  call    abort
```
