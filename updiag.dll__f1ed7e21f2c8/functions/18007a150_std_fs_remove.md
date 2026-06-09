# __std_fs_remove

- ea: `0x18007a150`
- end: `0x18007a3e0`
- name: `__std_fs_remove`
- size: `656`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180039da4`
- `0x1800641c4`

## callees

- `0x180079e3c`
- `0x180079ebc`
- `0x18007a150`
- `0x18008fc40`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a2d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a2d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a38a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a222`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a2e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a222`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a2e9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18007a1ba`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18007a319`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18007a356`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18007a1ba`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18007a319`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18007a356`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18007a2bc`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18007a2bc`

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
0x18007a150  mov     [rsp-8+arg_8], rbx
0x18007a155  mov     [rsp-8+arg_10], rsi
0x18007a15a  mov     [rsp-8+arg_18], rdi
0x18007a15f  push    rbp
0x18007a160  mov     rbp, rsp
0x18007a163  sub     rsp, 70h
0x18007a167  mov     rax, cs:__security_cookie
0x18007a16e  xor     rax, rsp
0x18007a171  mov     [rbp+var_10], rax
0x18007a175  mov     rbx, rcx
0x18007a178  mov     rdx, rcx
0x18007a17b  xor     esi, esi
0x18007a17d  lea     rcx, [rbp+hFile]
0x18007a181  mov     r9d, 2200000h
0x18007a187  mov     r8d, 10180h
0x18007a18d  mov     dil, sil
0x18007a190  call    __std_fs_open_handle
0x18007a195  mov     ecx, eax
0x18007a197  test    eax, eax
0x18007a199  jnz     short loc_18007A1E3
0x18007a19b  mov     dil, 1
0x18007a19e  mov     rbx, [rbp+hFile]
0x18007a1a2  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18007a1a6  mov     r9d, 4; dwBufferSize
0x18007a1ac  mov     [rbp+FileInformation], 13h
0x18007a1b3  mov     rcx, rbx; hFile
0x18007a1b6  lea     edx, [r9+11h]; FileInformationClass
0x18007a1ba  call    cs:__imp_SetFileInformationByHandle
0x18007a1c0  test    eax, eax
0x18007a1c2  jz      loc_18007A256
0x18007a1c8  xor     eax, eax
0x18007a1ca  mov     byte ptr [rbp+var_50], 1
0x18007a1ce  mov     word ptr [rbp+var_50+1], ax
0x18007a1d2  mov     byte ptr [rbp+var_50+3], al
0x18007a1d5  mov     dword ptr [rbp+var_50+4], esi
0x18007a1d8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007a1dc  jz      short loc_18007A230
0x18007a1de  mov     rcx, rbx
0x18007a1e1  jmp     short loc_18007A222
0x18007a1e3  cmp     ecx, 5
0x18007a1e6  jnz     loc_18007A39B
0x18007a1ec  mov     r9d, 2200000h
0x18007a1f2  lea     rcx, [rbp+hFile]
0x18007a1f6  mov     r8d, 10000h
0x18007a1fc  mov     rdx, rbx
0x18007a1ff  call    __std_fs_open_handle
0x18007a204  test    eax, eax
0x18007a206  jz      short loc_18007A19E
0x18007a208  xor     ecx, ecx
0x18007a20a  mov     byte ptr [rbp+var_50], sil
0x18007a20e  mov     word ptr [rbp+var_50+1], cx
0x18007a212  mov     byte ptr [rbp+var_50+3], cl
0x18007a215  mov     dword ptr [rbp+var_50+4], eax
0x18007a218  mov     rcx, [rbp+hFile]; hObject
0x18007a21c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18007a220  jz      short loc_18007A230
0x18007a222  call    cs:__imp_CloseHandle
0x18007a228  test    eax, eax
0x18007a22a  jz      loc_18007A3D4
0x18007a230  mov     rax, [rbp+var_50]
0x18007a234  mov     rcx, [rbp+var_10]
0x18007a238  xor     rcx, rsp; StackCookie
0x18007a23b  call    __security_check_cookie
0x18007a240  lea     r11, [rsp+70h+var_s0]
0x18007a245  mov     rbx, [r11+18h]
0x18007a249  mov     rsi, [r11+20h]
0x18007a24d  mov     rdi, [r11+28h]
0x18007a251  mov     rsp, r11
0x18007a254  pop     rbp
0x18007a255  retn
0x18007a256  call    cs:__imp_GetLastError
0x18007a25c  mov     ecx, eax
0x18007a25e  sub     ecx, 1
0x18007a261  jz      short loc_18007A282
0x18007a263  sub     ecx, 31h ; '1'
0x18007a266  jz      short loc_18007A282
0x18007a268  cmp     ecx, 25h ; '%'
0x18007a26b  jz      short loc_18007A282
0x18007a26d  xor     ecx, ecx
0x18007a26f  mov     byte ptr [rbp+var_50], sil
0x18007a273  mov     word ptr [rbp+var_50+1], cx
0x18007a277  mov     byte ptr [rbp+var_50+3], cl
0x18007a27a  mov     dword ptr [rbp+var_50+4], eax
0x18007a27d  jmp     loc_18007A1D8
0x18007a282  mov     rcx, rbx; hFile
0x18007a285  call    _anonymous_namespace____Set_delete_flag
0x18007a28a  test    eax, eax
0x18007a28c  jz      loc_18007A1C8
0x18007a292  cmp     eax, 5
0x18007a295  jnz     short loc_18007A26D
0x18007a297  test    dil, dil
0x18007a29a  jz      short loc_18007A26D
0x18007a29c  xor     eax, eax
0x18007a29e  lea     r8, [rbp+var_38]; lpFileInformation
0x18007a2a2  xorps   xmm0, xmm0
0x18007a2a5  mov     [rbp+var_18], rax
0x18007a2a9  xor     edx, edx; FileInformationClass
0x18007a2ab  mov     rcx, rbx; hFile
0x18007a2ae  movups  [rbp+var_38], xmm0
0x18007a2b2  lea     edi, [rax+28h]
0x18007a2b5  mov     r9d, edi; dwBufferSize
0x18007a2b8  movups  [rbp+var_28], xmm0
0x18007a2bc  call    cs:__imp_GetFileInformationByHandleEx
0x18007a2c2  test    eax, eax
0x18007a2c4  jnz     short loc_18007A2FC
0x18007a2c6  mov     byte ptr [rbp+var_50], sil
0x18007a2ca  xor     eax, eax
0x18007a2cc  mov     word ptr [rbp+var_50+1], ax
0x18007a2d0  mov     byte ptr [rbp+var_50+3], al
0x18007a2d3  call    cs:__imp_GetLastError
0x18007a2d9  mov     dword ptr [rbp+var_50+4], eax
0x18007a2dc  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007a2e0  jz      loc_18007A230
0x18007a2e6  mov     rcx, rbx; hObject
0x18007a2e9  call    cs:__imp_CloseHandle
0x18007a2ef  test    eax, eax
0x18007a2f1  jz      loc_18007A3DA
0x18007a2f7  jmp     loc_18007A230
0x18007a2fc  mov     eax, dword ptr [rbp+var_18]
0x18007a2ff  test    al, 1
0x18007a301  jz      loc_18007A395
0x18007a307  xor     eax, 1
0x18007a30a  lea     r8, [rbp+var_38]; lpFileInformation
0x18007a30e  mov     r9d, edi; dwBufferSize
0x18007a311  mov     dword ptr [rbp+var_18], eax
0x18007a314  xor     edx, edx; FileInformationClass
0x18007a316  mov     rcx, rbx; hFile
0x18007a319  call    cs:__imp_SetFileInformationByHandle
0x18007a31f  test    eax, eax
0x18007a321  jz      short loc_18007A2C6
0x18007a323  mov     rcx, rbx; hFile
0x18007a326  call    _anonymous_namespace____Set_delete_flag
0x18007a32b  test    eax, eax
0x18007a32d  jnz     short loc_18007A341
0x18007a32f  xor     eax, eax
0x18007a331  mov     byte ptr [rbp+var_50], 1
0x18007a335  mov     word ptr [rbp+var_50+1], ax
0x18007a339  mov     byte ptr [rbp+var_50+3], al
0x18007a33c  mov     dword ptr [rbp+var_50+4], esi
0x18007a33f  jmp     short loc_18007A2DC
0x18007a341  cmp     eax, 5
0x18007a344  jnz     short loc_18007A37D
0x18007a346  or      dword ptr [rbp+var_18], 1
0x18007a34a  lea     r8, [rbp+var_38]; lpFileInformation
0x18007a34e  mov     r9d, edi; dwBufferSize
0x18007a351  xor     edx, edx; FileInformationClass
0x18007a353  mov     rcx, rbx; hFile
0x18007a356  call    cs:__imp_SetFileInformationByHandle
0x18007a35c  mov     byte ptr [rbp+var_50], sil
0x18007a360  test    eax, eax
0x18007a362  jz      loc_18007A2CA
0x18007a368  xor     eax, eax
0x18007a36a  mov     dword ptr [rbp+var_50+4], 5
0x18007a371  mov     word ptr [rbp+var_50+1], ax
0x18007a375  mov     byte ptr [rbp+var_50+3], al
0x18007a378  jmp     loc_18007A2DC
0x18007a37d  xor     eax, eax
0x18007a37f  mov     byte ptr [rbp+var_50], sil
0x18007a383  mov     word ptr [rbp+var_50+1], ax
0x18007a387  mov     byte ptr [rbp+var_50+3], al
0x18007a38a  call    cs:__imp_GetLastError
0x18007a390  jmp     loc_18007A27A
0x18007a395  mov     byte ptr [rbp+var_50], sil
0x18007a399  jmp     short loc_18007A368
0x18007a39b  xor     eax, eax
0x18007a39d  mov     byte ptr [rbp+var_50], sil
0x18007a3a1  mov     word ptr [rbp+var_50+1], ax
0x18007a3a5  mov     byte ptr [rbp+var_50+3], al
0x18007a3a8  mov     eax, ecx
0x18007a3aa  sub     eax, 2
0x18007a3ad  jz      short loc_18007A3CA
0x18007a3af  sub     eax, 1
0x18007a3b2  jz      short loc_18007A3CA
0x18007a3b4  sub     eax, 32h ; '2'
0x18007a3b7  jz      short loc_18007A3CA
0x18007a3b9  sub     eax, 0Bh
0x18007a3bc  jz      short loc_18007A3CA
0x18007a3be  sub     eax, 3Bh ; ';'
0x18007a3c1  jz      short loc_18007A3CA
0x18007a3c3  cmp     eax, 90h
0x18007a3c8  jnz     short loc_18007A3CC
0x18007a3ca  mov     ecx, esi
0x18007a3cc  mov     dword ptr [rbp+var_50+4], ecx
0x18007a3cf  jmp     loc_18007A218
0x18007a3d4  call    abort
0x18007a3da  call    abort
```
