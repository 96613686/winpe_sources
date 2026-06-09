# __std_fs_remove

- ea: `0x180276f2c`
- end: `0x18027726e`
- name: `__std_fs_remove`
- size: `834`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1803b8044`

## callees

- `0x18015cb00`
- `0x18027689c`
- `0x180276ed0`
- `0x180276f2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18027718b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180277233`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18027718b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180277233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027702c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802770cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802771a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027702c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802770cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802771a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180276fae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180277006`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180277054`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802770e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180277132`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180277181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802771be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802771d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180277229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180276fae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180277006`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180277054`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802770e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180277132`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180277181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802771be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802771d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180277229`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180276f95`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180277111`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180277165`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180276f95`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180277111`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180277165`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1802770b8`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1802770b8`

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
0x180276f2c  mov     [rsp-18h+arg_8], rbx
0x180276f31  mov     [rsp-18h+arg_10], rsi
0x180276f36  push    rbp
0x180276f37  push    rdi
0x180276f38  push    r15
0x180276f3a  mov     rbp, rsp
0x180276f3d  sub     rsp, 60h
0x180276f41  mov     rax, cs:__security_cookie
0x180276f48  xor     rax, rsp
0x180276f4b  mov     [rbp+var_8], rax
0x180276f4f  mov     rdi, rcx
0x180276f52  mov     rdx, rcx
0x180276f55  lea     rcx, [rbp+hFile]
0x180276f59  mov     r9d, 2200000h
0x180276f5f  mov     r8d, 10180h
0x180276f65  call    __std_fs_open_handle
0x180276f6a  mov     ebx, eax
0x180276f6c  mov     r15d, 5
0x180276f72  test    eax, eax
0x180276f74  jnz     short loc_180276FCD
0x180276f76  mov     sil, 1
0x180276f79  mov     rbx, [rbp+hFile]
0x180276f7d  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180276f81  mov     r9d, 4; dwBufferSize
0x180276f87  mov     dword ptr [rbp+FileInformation], 13h
0x180276f8e  mov     rcx, rbx; hFile
0x180276f91  lea     edx, [r9+11h]; FileInformationClass
0x180276f95  call    cs:__imp_SetFileInformationByHandle
0x180276f9b  test    eax, eax
0x180276f9d  jz      loc_18027702C
0x180276fa3  xor     edi, edi
0x180276fa5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180276fa9  jz      short loc_180276FBC
0x180276fab  mov     rcx, rbx; hObject
0x180276fae  call    cs:__imp_CloseHandle
0x180276fb4  test    eax, eax
0x180276fb6  jz      loc_180277233
0x180276fbc  mov     byte ptr [rbp+FileInformation], 1
0x180276fc0  mov     word ptr [rbp+FileInformation+1], di
0x180276fc4  mov     byte ptr [rbp+FileInformation+3], dil
0x180276fc8  mov     dword ptr [rbp+FileInformation+4], edi
0x180276fcb  jmp     short loc_180277023
0x180276fcd  cmp     eax, r15d
0x180276fd0  jnz     loc_1802771F5
0x180276fd6  mov     r9d, 2200000h
0x180276fdc  lea     rcx, [rbp+hFile]
0x180276fe0  mov     r8d, 10000h
0x180276fe6  mov     rdx, rdi
0x180276fe9  xor     sil, sil
0x180276fec  call    __std_fs_open_handle
0x180276ff1  mov     ebx, eax
0x180276ff3  test    eax, eax
0x180276ff5  jz      short loc_180276F79
0x180276ff7  mov     rcx, [rbp+hFile]; hObject
0x180276ffb  xor     dil, dil
0x180276ffe  xor     esi, esi
0x180277000  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180277004  jz      short loc_180277014
0x180277006  call    cs:__imp_CloseHandle
0x18027700c  test    eax, eax
0x18027700e  jz      loc_180277233
0x180277014  mov     byte ptr [rbp+FileInformation], dil
0x180277018  mov     word ptr [rbp+FileInformation+1], si
0x18027701c  mov     byte ptr [rbp+FileInformation+3], sil
0x180277020  mov     dword ptr [rbp+FileInformation+4], ebx
0x180277023  mov     rax, [rbp+FileInformation]
0x180277027  jmp     loc_18027724D
0x18027702c  call    cs:__imp_GetLastError
0x180277032  mov     ecx, eax
0x180277034  mov     edi, eax
0x180277036  sub     ecx, 1
0x180277039  jz      short loc_180277074
0x18027703b  sub     ecx, 31h ; '1'
0x18027703e  jz      short loc_180277074
0x180277040  cmp     ecx, 25h ; '%'
0x180277043  jz      short loc_180277074
0x180277045  xor     sil, sil
0x180277048  xor     r15d, r15d
0x18027704b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18027704f  jz      short loc_180277062
0x180277051  mov     rcx, rbx; hObject
0x180277054  call    cs:__imp_CloseHandle
0x18027705a  test    eax, eax
0x18027705c  jz      loc_180277233
0x180277062  mov     byte ptr [rbp+FileInformation], sil
0x180277066  mov     word ptr [rbp+FileInformation+1], r15w
0x18027706b  mov     byte ptr [rbp+FileInformation+3], r15b
0x18027706f  jmp     loc_180276FC8
0x180277074  mov     rcx, rbx; hFile
0x180277077  call    _anonymous_namespace____Set_delete_flag
0x18027707c  mov     edi, eax
0x18027707e  test    eax, eax
0x180277080  jz      loc_180276FA3
0x180277086  cmp     eax, r15d
0x180277089  jnz     loc_1802771CA
0x18027708f  test    sil, sil
0x180277092  jz      loc_1802771CA
0x180277098  xor     eax, eax
0x18027709a  lea     r8, [rbp+var_30]; lpFileInformation
0x18027709e  xorps   xmm0, xmm0
0x1802770a1  mov     [rbp+var_10], rax
0x1802770a5  xor     edx, edx; FileInformationClass
0x1802770a7  mov     rcx, rbx; hFile
0x1802770aa  movups  [rbp+var_30], xmm0
0x1802770ae  lea     edi, [rax+28h]
0x1802770b1  mov     r9d, edi; dwBufferSize
0x1802770b4  movups  [rbp+var_20], xmm0
0x1802770b8  call    cs:__imp_GetFileInformationByHandleEx
0x1802770be  test    eax, eax
0x1802770c0  jnz     short loc_1802770F8
0x1802770c2  xor     eax, eax
0x1802770c4  mov     byte ptr [rbp+hFile], 0
0x1802770c8  mov     word ptr [rbp+hFile+1], ax
0x1802770cc  mov     byte ptr [rbp+hFile+3], al
0x1802770cf  call    cs:__imp_GetLastError
0x1802770d5  mov     dword ptr [rbp+hFile+4], eax
0x1802770d8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1802770dc  jz      loc_180277249
0x1802770e2  mov     rcx, rbx; hObject
0x1802770e5  call    cs:__imp_CloseHandle
0x1802770eb  test    eax, eax
0x1802770ed  jz      loc_18027718B
0x1802770f3  jmp     loc_180277249
0x1802770f8  mov     eax, dword ptr [rbp+var_10]
0x1802770fb  test    al, 1
0x1802770fd  jz      short loc_180277173
0x1802770ff  xor     eax, 1
0x180277102  lea     r8, [rbp+var_30]; lpFileInformation
0x180277106  mov     r9d, edi; dwBufferSize
0x180277109  mov     dword ptr [rbp+var_10], eax
0x18027710c  xor     edx, edx; FileInformationClass
0x18027710e  mov     rcx, rbx; hFile
0x180277111  call    cs:__imp_SetFileInformationByHandle
0x180277117  test    eax, eax
0x180277119  jz      short loc_1802770C2
0x18027711b  mov     rcx, rbx; hFile
0x18027711e  call    _anonymous_namespace____Set_delete_flag
0x180277123  test    eax, eax
0x180277125  jnz     short loc_180277150
0x180277127  xor     edi, edi
0x180277129  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18027712d  jz      short loc_18027713C
0x18027712f  mov     rcx, rbx; hObject
0x180277132  call    cs:__imp_CloseHandle
0x180277138  test    eax, eax
0x18027713a  jz      short loc_18027718B
0x18027713c  mov     byte ptr [rbp+hFile], 1
0x180277140  mov     word ptr [rbp+hFile+1], di
0x180277144  mov     byte ptr [rbp+hFile+3], dil
0x180277148  mov     dword ptr [rbp+hFile+4], edi
0x18027714b  jmp     loc_180277249
0x180277150  cmp     eax, r15d
0x180277153  jnz     short loc_18027719B
0x180277155  or      dword ptr [rbp+var_10], 1
0x180277159  lea     r8, [rbp+var_30]; lpFileInformation
0x18027715d  mov     r9d, edi; dwBufferSize
0x180277160  xor     edx, edx; FileInformationClass
0x180277162  mov     rcx, rbx; hFile
0x180277165  call    cs:__imp_SetFileInformationByHandle
0x18027716b  test    eax, eax
0x18027716d  jz      loc_1802770C2
0x180277173  xor     dil, dil
0x180277176  xor     esi, esi
0x180277178  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18027717c  jz      short loc_180277192
0x18027717e  mov     rcx, rbx; hObject
0x180277181  call    cs:__imp_CloseHandle
0x180277187  test    eax, eax
0x180277189  jnz     short loc_180277192
0x18027718b  call    cs:__imp_abort
0x180277192  mov     dword ptr [rbp+hFile+4], r15d
0x180277196  jmp     loc_18027723D
0x18027719b  xor     eax, eax
0x18027719d  mov     byte ptr [rbp+hFile], 0
0x1802771a1  mov     word ptr [rbp+hFile+1], ax
0x1802771a5  mov     byte ptr [rbp+hFile+3], al
0x1802771a8  call    cs:__imp_GetLastError
0x1802771ae  mov     dword ptr [rbp+hFile+4], eax
0x1802771b1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1802771b5  jz      loc_180277249
0x1802771bb  mov     rcx, rbx; hObject
0x1802771be  call    cs:__imp_CloseHandle
0x1802771c4  test    eax, eax
0x1802771c6  jz      short loc_180277233
0x1802771c8  jmp     short loc_180277249
0x1802771ca  xor     sil, sil
0x1802771cd  xor     r15d, r15d
0x1802771d0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1802771d4  jz      short loc_1802771E3
0x1802771d6  mov     rcx, rbx; hObject
0x1802771d9  call    cs:__imp_CloseHandle
0x1802771df  test    eax, eax
0x1802771e1  jz      short loc_180277233
0x1802771e3  mov     byte ptr [rbp+hFile], sil
0x1802771e7  mov     word ptr [rbp+hFile+1], r15w
0x1802771ec  mov     byte ptr [rbp+hFile+3], r15b
0x1802771f0  jmp     loc_180277148
0x1802771f5  xor     dil, dil
0x1802771f8  xor     esi, esi
0x1802771fa  sub     eax, 2
0x1802771fd  jz      short loc_18027721D
0x1802771ff  sub     eax, 1
0x180277202  jz      short loc_18027721D
0x180277204  sub     eax, 32h ; '2'
0x180277207  jz      short loc_18027721D
0x180277209  sub     eax, 0Bh
0x18027720c  jz      short loc_18027721D
0x18027720e  sub     eax, 3Bh ; ';'
0x180277211  jz      short loc_18027721D
0x180277213  sub     eax, 26h ; '&'
0x180277216  jz      short loc_18027721D
0x180277218  cmp     eax, 6Ah ; 'j'
0x18027721b  jnz     short loc_18027721F
0x18027721d  xor     ebx, ebx
0x18027721f  mov     rcx, [rbp+hFile]; hObject
0x180277223  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180277227  jz      short loc_18027723A
0x180277229  call    cs:__imp_CloseHandle
0x18027722f  test    eax, eax
0x180277231  jnz     short loc_18027723A
0x180277233  call    cs:__imp_abort
0x18027723a  mov     dword ptr [rbp+hFile+4], ebx
0x18027723d  mov     byte ptr [rbp+hFile], dil
0x180277241  mov     word ptr [rbp+hFile+1], si
0x180277245  mov     byte ptr [rbp+hFile+3], sil
0x180277249  mov     rax, [rbp+hFile]
0x18027724d  mov     rcx, [rbp+var_8]
0x180277251  xor     rcx, rsp; StackCookie
0x180277254  call    __security_check_cookie
0x180277259  lea     r11, [rsp+60h+var_s0]
0x18027725e  mov     rbx, [r11+28h]
0x180277262  mov     rsi, [r11+30h]
0x180277266  mov     rsp, r11
0x180277269  pop     r15
0x18027726b  pop     rdi
0x18027726c  pop     rbp
0x18027726d  retn
```
