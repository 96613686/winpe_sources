# __std_fs_remove

- ea: `0x180004f54`
- end: `0x180005296`
- name: `__std_fs_remove`
- size: `834`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18003f030`

## callees

- `0x180003110`
- `0x180004994`
- `0x180004ef8`
- `0x180004f54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800051b3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000525b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800051b3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000525b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004fd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000502e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000507c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000510d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000515a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005201`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005251`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004fd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000502e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000507c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000510d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000515a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800051e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005201`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005251`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180004fbd`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180005139`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000518d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180004fbd`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180005139`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000518d`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800050e0`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800050e0`

## pseudocode

```c
HANDLE __fastcall _std_fs_remove(__int64 a1)
{
  int v2; // eax
  int v3; // ebx
  char v4; // si
  HANDLE v5; // rbx
  DWORD LastError; // edi
  int v7; // ebx
  int v9; // eax
  int v10; // edi
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  HANDLE hFile; // [rsp+20h] [rbp-40h] BYREF
  __int64 FileInformation; // [rsp+28h] [rbp-38h] BYREF
  _OWORD v20[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h]

  v2 = _std_fs_open_handle(&hFile, a1, 65920, 35651584);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 != 5 )
    {
      v12 = v2 - 2;
      if ( !v12
        || (v13 = v12 - 1) == 0
        || (v14 = v13 - 50) == 0
        || (v15 = v14 - 11) == 0
        || (v16 = v15 - 59) == 0
        || (v17 = v16 - 38) == 0
        || v17 == 106 )
      {
        v3 = 0;
      }
      if ( hFile != (HANDLE)-1LL && !CloseHandle(hFile) )
        goto LABEL_56;
      HIDWORD(hFile) = v3;
LABEL_58:
      LOBYTE(hFile) = 0;
      *(_WORD *)((char *)&hFile + 1) = 0;
      BYTE3(hFile) = 0;
      return hFile;
    }
    v4 = 0;
    v7 = _std_fs_open_handle(&hFile, a1, 0x10000, 35651584);
    if ( v7 )
    {
      if ( hFile == (HANDLE)-1LL || CloseHandle(hFile) )
      {
        LOBYTE(FileInformation) = 0;
        *(_WORD *)((char *)&FileInformation + 1) = 0;
        BYTE3(FileInformation) = 0;
        HIDWORD(FileInformation) = v7;
        return (HANDLE)FileInformation;
      }
      goto LABEL_56;
    }
  }
  else
  {
    v4 = 1;
  }
  v5 = hFile;
  LODWORD(FileInformation) = 19;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
    goto LABEL_4;
  LastError = GetLastError();
  if ( LastError != 1 && LastError != 50 && LastError != 87 )
  {
    if ( v5 == (HANDLE)-1LL || CloseHandle(v5) )
    {
      LOBYTE(FileInformation) = 0;
      *(_WORD *)((char *)&FileInformation + 1) = 0;
      BYTE3(FileInformation) = 0;
      goto LABEL_7;
    }
LABEL_56:
    abort();
  }
  v9 = anonymous_namespace_::_Set_delete_flag(v5);
  v10 = v9;
  if ( !v9 )
  {
LABEL_4:
    LastError = 0;
    if ( v5 == (HANDLE)-1LL || CloseHandle(v5) )
    {
      LOBYTE(FileInformation) = 1;
      *(_WORD *)((char *)&FileInformation + 1) = 0;
      BYTE3(FileInformation) = 0;
LABEL_7:
      HIDWORD(FileInformation) = LastError;
      return (HANDLE)FileInformation;
    }
    goto LABEL_56;
  }
  if ( v9 != 5 || !v4 )
  {
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_56;
    LOBYTE(hFile) = 0;
    *(_WORD *)((char *)&hFile + 1) = 0;
    BYTE3(hFile) = 0;
LABEL_33:
    HIDWORD(hFile) = v10;
    return hFile;
  }
  v21 = 0;
  memset(v20, 0, sizeof(v20));
  if ( !GetFileInformationByHandleEx(v5, FileBasicInfo, v20, 0x28u) )
  {
LABEL_24:
    LOBYTE(hFile) = 0;
    *(_WORD *)((char *)&hFile + 1) = 0;
    BYTE3(hFile) = 0;
    HIDWORD(hFile) = GetLastError();
    if ( v5 == (HANDLE)-1LL || CloseHandle(v5) )
      return hFile;
LABEL_38:
    abort();
  }
  if ( (v21 & 1) == 0 )
  {
LABEL_36:
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_38;
    HIDWORD(hFile) = 5;
    goto LABEL_58;
  }
  LODWORD(v21) = v21 ^ 1;
  if ( !SetFileInformationByHandle(v5, FileBasicInfo, v20, 0x28u) )
    goto LABEL_24;
  v11 = anonymous_namespace_::_Set_delete_flag(v5);
  if ( !v11 )
  {
    v10 = 0;
    if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
      goto LABEL_38;
    LOBYTE(hFile) = 1;
    *(_WORD *)((char *)&hFile + 1) = 0;
    BYTE3(hFile) = 0;
    goto LABEL_33;
  }
  if ( v11 == 5 )
  {
    LODWORD(v21) = v21 | 1;
    if ( !SetFileInformationByHandle(v5, FileBasicInfo, v20, 0x28u) )
      goto LABEL_24;
    goto LABEL_36;
  }
  LOBYTE(hFile) = 0;
  *(_WORD *)((char *)&hFile + 1) = 0;
  BYTE3(hFile) = 0;
  HIDWORD(hFile) = GetLastError();
  if ( v5 != (HANDLE)-1LL && !CloseHandle(v5) )
    goto LABEL_56;
  return hFile;
}

```

## disassembly

```asm
0x180004f54  mov     [rsp-18h+arg_8], rbx
0x180004f59  mov     [rsp-18h+arg_10], rsi
0x180004f5e  push    rbp
0x180004f5f  push    rdi
0x180004f60  push    r15
0x180004f62  mov     rbp, rsp
0x180004f65  sub     rsp, 60h
0x180004f69  mov     rax, cs:__security_cookie
0x180004f70  xor     rax, rsp
0x180004f73  mov     [rbp+var_8], rax
0x180004f77  mov     rdi, rcx
0x180004f7a  mov     rdx, rcx
0x180004f7d  lea     rcx, [rbp+hFile]
0x180004f81  mov     r9d, 2200000h
0x180004f87  mov     r8d, 10180h
0x180004f8d  call    __std_fs_open_handle
0x180004f92  mov     ebx, eax
0x180004f94  mov     r15d, 5
0x180004f9a  test    eax, eax
0x180004f9c  jnz     short loc_180004FF5
0x180004f9e  mov     sil, 1
0x180004fa1  mov     rbx, [rbp+hFile]
0x180004fa5  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180004fa9  mov     r9d, 4; dwBufferSize
0x180004faf  mov     dword ptr [rbp+FileInformation], 13h
0x180004fb6  mov     rcx, rbx; hFile
0x180004fb9  lea     edx, [r9+11h]; FileInformationClass
0x180004fbd  call    cs:__imp_SetFileInformationByHandle
0x180004fc3  test    eax, eax
0x180004fc5  jz      loc_180005054
0x180004fcb  xor     edi, edi
0x180004fcd  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180004fd1  jz      short loc_180004FE4
0x180004fd3  mov     rcx, rbx; hObject
0x180004fd6  call    cs:__imp_CloseHandle
0x180004fdc  test    eax, eax
0x180004fde  jz      loc_18000525B
0x180004fe4  mov     byte ptr [rbp+FileInformation], 1
0x180004fe8  mov     word ptr [rbp+FileInformation+1], di
0x180004fec  mov     byte ptr [rbp+FileInformation+3], dil
0x180004ff0  mov     dword ptr [rbp+FileInformation+4], edi
0x180004ff3  jmp     short loc_18000504B
0x180004ff5  cmp     eax, r15d
0x180004ff8  jnz     loc_18000521D
0x180004ffe  mov     r9d, 2200000h
0x180005004  lea     rcx, [rbp+hFile]
0x180005008  mov     r8d, 10000h
0x18000500e  mov     rdx, rdi
0x180005011  xor     sil, sil
0x180005014  call    __std_fs_open_handle
0x180005019  mov     ebx, eax
0x18000501b  test    eax, eax
0x18000501d  jz      short loc_180004FA1
0x18000501f  mov     rcx, [rbp+hFile]; hObject
0x180005023  xor     dil, dil
0x180005026  xor     esi, esi
0x180005028  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000502c  jz      short loc_18000503C
0x18000502e  call    cs:__imp_CloseHandle
0x180005034  test    eax, eax
0x180005036  jz      loc_18000525B
0x18000503c  mov     byte ptr [rbp+FileInformation], dil
0x180005040  mov     word ptr [rbp+FileInformation+1], si
0x180005044  mov     byte ptr [rbp+FileInformation+3], sil
0x180005048  mov     dword ptr [rbp+FileInformation+4], ebx
0x18000504b  mov     rax, [rbp+FileInformation]
0x18000504f  jmp     loc_180005275
0x180005054  call    cs:__imp_GetLastError
0x18000505a  mov     ecx, eax
0x18000505c  mov     edi, eax
0x18000505e  sub     ecx, 1
0x180005061  jz      short loc_18000509C
0x180005063  sub     ecx, 31h ; '1'
0x180005066  jz      short loc_18000509C
0x180005068  cmp     ecx, 25h ; '%'
0x18000506b  jz      short loc_18000509C
0x18000506d  xor     sil, sil
0x180005070  xor     r15d, r15d
0x180005073  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180005077  jz      short loc_18000508A
0x180005079  mov     rcx, rbx; hObject
0x18000507c  call    cs:__imp_CloseHandle
0x180005082  test    eax, eax
0x180005084  jz      loc_18000525B
0x18000508a  mov     byte ptr [rbp+FileInformation], sil
0x18000508e  mov     word ptr [rbp+FileInformation+1], r15w
0x180005093  mov     byte ptr [rbp+FileInformation+3], r15b
0x180005097  jmp     loc_180004FF0
0x18000509c  mov     rcx, rbx; hFile
0x18000509f  call    _anonymous_namespace____Set_delete_flag
0x1800050a4  mov     edi, eax
0x1800050a6  test    eax, eax
0x1800050a8  jz      loc_180004FCB
0x1800050ae  cmp     eax, r15d
0x1800050b1  jnz     loc_1800051F2
0x1800050b7  test    sil, sil
0x1800050ba  jz      loc_1800051F2
0x1800050c0  xor     eax, eax
0x1800050c2  lea     r8, [rbp+var_30]; lpFileInformation
0x1800050c6  xorps   xmm0, xmm0
0x1800050c9  mov     [rbp+var_10], rax
0x1800050cd  xor     edx, edx; FileInformationClass
0x1800050cf  mov     rcx, rbx; hFile
0x1800050d2  movups  [rbp+var_30], xmm0
0x1800050d6  lea     edi, [rax+28h]
0x1800050d9  mov     r9d, edi; dwBufferSize
0x1800050dc  movups  [rbp+var_20], xmm0
0x1800050e0  call    cs:__imp_GetFileInformationByHandleEx
0x1800050e6  test    eax, eax
0x1800050e8  jnz     short loc_180005120
0x1800050ea  xor     eax, eax
0x1800050ec  mov     byte ptr [rbp+hFile], 0
0x1800050f0  mov     word ptr [rbp+hFile+1], ax
0x1800050f4  mov     byte ptr [rbp+hFile+3], al
0x1800050f7  call    cs:__imp_GetLastError
0x1800050fd  mov     dword ptr [rbp+hFile+4], eax
0x180005100  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180005104  jz      loc_180005271
0x18000510a  mov     rcx, rbx; hObject
0x18000510d  call    cs:__imp_CloseHandle
0x180005113  test    eax, eax
0x180005115  jz      loc_1800051B3
0x18000511b  jmp     loc_180005271
0x180005120  mov     eax, dword ptr [rbp+var_10]
0x180005123  test    al, 1
0x180005125  jz      short loc_18000519B
0x180005127  xor     eax, 1
0x18000512a  lea     r8, [rbp+var_30]; lpFileInformation
0x18000512e  mov     r9d, edi; dwBufferSize
0x180005131  mov     dword ptr [rbp+var_10], eax
0x180005134  xor     edx, edx; FileInformationClass
0x180005136  mov     rcx, rbx; hFile
0x180005139  call    cs:__imp_SetFileInformationByHandle
0x18000513f  test    eax, eax
0x180005141  jz      short loc_1800050EA
0x180005143  mov     rcx, rbx; hFile
0x180005146  call    _anonymous_namespace____Set_delete_flag
0x18000514b  test    eax, eax
0x18000514d  jnz     short loc_180005178
0x18000514f  xor     edi, edi
0x180005151  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180005155  jz      short loc_180005164
0x180005157  mov     rcx, rbx; hObject
0x18000515a  call    cs:__imp_CloseHandle
0x180005160  test    eax, eax
0x180005162  jz      short loc_1800051B3
0x180005164  mov     byte ptr [rbp+hFile], 1
0x180005168  mov     word ptr [rbp+hFile+1], di
0x18000516c  mov     byte ptr [rbp+hFile+3], dil
0x180005170  mov     dword ptr [rbp+hFile+4], edi
0x180005173  jmp     loc_180005271
0x180005178  cmp     eax, r15d
0x18000517b  jnz     short loc_1800051C3
0x18000517d  or      dword ptr [rbp+var_10], 1
0x180005181  lea     r8, [rbp+var_30]; lpFileInformation
0x180005185  mov     r9d, edi; dwBufferSize
0x180005188  xor     edx, edx; FileInformationClass
0x18000518a  mov     rcx, rbx; hFile
0x18000518d  call    cs:__imp_SetFileInformationByHandle
0x180005193  test    eax, eax
0x180005195  jz      loc_1800050EA
0x18000519b  xor     dil, dil
0x18000519e  xor     esi, esi
0x1800051a0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800051a4  jz      short loc_1800051BA
0x1800051a6  mov     rcx, rbx; hObject
0x1800051a9  call    cs:__imp_CloseHandle
0x1800051af  test    eax, eax
0x1800051b1  jnz     short loc_1800051BA
0x1800051b3  call    cs:__imp_abort
0x1800051ba  mov     dword ptr [rbp+hFile+4], r15d
0x1800051be  jmp     loc_180005265
0x1800051c3  xor     eax, eax
0x1800051c5  mov     byte ptr [rbp+hFile], 0
0x1800051c9  mov     word ptr [rbp+hFile+1], ax
0x1800051cd  mov     byte ptr [rbp+hFile+3], al
0x1800051d0  call    cs:__imp_GetLastError
0x1800051d6  mov     dword ptr [rbp+hFile+4], eax
0x1800051d9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800051dd  jz      loc_180005271
0x1800051e3  mov     rcx, rbx; hObject
0x1800051e6  call    cs:__imp_CloseHandle
0x1800051ec  test    eax, eax
0x1800051ee  jz      short loc_18000525B
0x1800051f0  jmp     short loc_180005271
0x1800051f2  xor     sil, sil
0x1800051f5  xor     r15d, r15d
0x1800051f8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800051fc  jz      short loc_18000520B
0x1800051fe  mov     rcx, rbx; hObject
0x180005201  call    cs:__imp_CloseHandle
0x180005207  test    eax, eax
0x180005209  jz      short loc_18000525B
0x18000520b  mov     byte ptr [rbp+hFile], sil
0x18000520f  mov     word ptr [rbp+hFile+1], r15w
0x180005214  mov     byte ptr [rbp+hFile+3], r15b
0x180005218  jmp     loc_180005170
0x18000521d  xor     dil, dil
0x180005220  xor     esi, esi
0x180005222  sub     eax, 2
0x180005225  jz      short loc_180005245
0x180005227  sub     eax, 1
0x18000522a  jz      short loc_180005245
0x18000522c  sub     eax, 32h ; '2'
0x18000522f  jz      short loc_180005245
0x180005231  sub     eax, 0Bh
0x180005234  jz      short loc_180005245
0x180005236  sub     eax, 3Bh ; ';'
0x180005239  jz      short loc_180005245
0x18000523b  sub     eax, 26h ; '&'
0x18000523e  jz      short loc_180005245
0x180005240  cmp     eax, 6Ah ; 'j'
0x180005243  jnz     short loc_180005247
0x180005245  xor     ebx, ebx
0x180005247  mov     rcx, [rbp+hFile]; hObject
0x18000524b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000524f  jz      short loc_180005262
0x180005251  call    cs:__imp_CloseHandle
0x180005257  test    eax, eax
0x180005259  jnz     short loc_180005262
0x18000525b  call    cs:__imp_abort
0x180005262  mov     dword ptr [rbp+hFile+4], ebx
0x180005265  mov     byte ptr [rbp+hFile], dil
0x180005269  mov     word ptr [rbp+hFile+1], si
0x18000526d  mov     byte ptr [rbp+hFile+3], sil
0x180005271  mov     rax, [rbp+hFile]
0x180005275  mov     rcx, [rbp+var_8]
0x180005279  xor     rcx, rsp; StackCookie
0x18000527c  call    __security_check_cookie
0x180005281  lea     r11, [rsp+60h+var_s0]
0x180005286  mov     rbx, [r11+28h]
0x18000528a  mov     rsi, [r11+30h]
0x18000528e  mov     rsp, r11
0x180005291  pop     r15
0x180005293  pop     rdi
0x180005294  pop     rbp
0x180005295  retn
```
