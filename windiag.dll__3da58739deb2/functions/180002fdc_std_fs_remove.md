# __std_fs_remove

- ea: `0x180002fdc`
- end: `0x18000331e`
- name: `__std_fs_remove`
- size: `834`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800673c8`
- `0x180069e7c`
- `0x18008dd60`

## callees

- `0x180002934`
- `0x180002f80`
- `0x180002fdc`
- `0x180004510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000323b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800032e3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000323b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800032e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000317f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000317f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003258`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000305e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003231`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000326e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003289`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000305e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800031e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003231`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000326e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003289`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032d9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180003045`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800031c1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180003215`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180003045`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800031c1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180003215`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180003168`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180003168`

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
0x180002fdc  mov     [rsp-18h+arg_8], rbx
0x180002fe1  mov     [rsp-18h+arg_10], rsi
0x180002fe6  push    rbp
0x180002fe7  push    rdi
0x180002fe8  push    r15
0x180002fea  mov     rbp, rsp
0x180002fed  sub     rsp, 60h
0x180002ff1  mov     rax, cs:__security_cookie
0x180002ff8  xor     rax, rsp
0x180002ffb  mov     [rbp+var_8], rax
0x180002fff  mov     rdi, rcx
0x180003002  mov     rdx, rcx
0x180003005  lea     rcx, [rbp+hFile]
0x180003009  mov     r9d, 2200000h
0x18000300f  mov     r8d, 10180h
0x180003015  call    __std_fs_open_handle
0x18000301a  mov     ebx, eax
0x18000301c  mov     r15d, 5
0x180003022  test    eax, eax
0x180003024  jnz     short loc_18000307D
0x180003026  mov     sil, 1
0x180003029  mov     rbx, [rbp+hFile]
0x18000302d  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180003031  mov     r9d, 4; dwBufferSize
0x180003037  mov     dword ptr [rbp+FileInformation], 13h
0x18000303e  mov     rcx, rbx; hFile
0x180003041  lea     edx, [r9+11h]; FileInformationClass
0x180003045  call    cs:__imp_SetFileInformationByHandle
0x18000304b  test    eax, eax
0x18000304d  jz      loc_1800030DC
0x180003053  xor     edi, edi
0x180003055  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180003059  jz      short loc_18000306C
0x18000305b  mov     rcx, rbx; hObject
0x18000305e  call    cs:__imp_CloseHandle
0x180003064  test    eax, eax
0x180003066  jz      loc_1800032E3
0x18000306c  mov     byte ptr [rbp+FileInformation], 1
0x180003070  mov     word ptr [rbp+FileInformation+1], di
0x180003074  mov     byte ptr [rbp+FileInformation+3], dil
0x180003078  mov     dword ptr [rbp+FileInformation+4], edi
0x18000307b  jmp     short loc_1800030D3
0x18000307d  cmp     eax, r15d
0x180003080  jnz     loc_1800032A5
0x180003086  mov     r9d, 2200000h
0x18000308c  lea     rcx, [rbp+hFile]
0x180003090  mov     r8d, 10000h
0x180003096  mov     rdx, rdi
0x180003099  xor     sil, sil
0x18000309c  call    __std_fs_open_handle
0x1800030a1  mov     ebx, eax
0x1800030a3  test    eax, eax
0x1800030a5  jz      short loc_180003029
0x1800030a7  mov     rcx, [rbp+hFile]; hObject
0x1800030ab  xor     dil, dil
0x1800030ae  xor     esi, esi
0x1800030b0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800030b4  jz      short loc_1800030C4
0x1800030b6  call    cs:__imp_CloseHandle
0x1800030bc  test    eax, eax
0x1800030be  jz      loc_1800032E3
0x1800030c4  mov     byte ptr [rbp+FileInformation], dil
0x1800030c8  mov     word ptr [rbp+FileInformation+1], si
0x1800030cc  mov     byte ptr [rbp+FileInformation+3], sil
0x1800030d0  mov     dword ptr [rbp+FileInformation+4], ebx
0x1800030d3  mov     rax, [rbp+FileInformation]
0x1800030d7  jmp     loc_1800032FD
0x1800030dc  call    cs:__imp_GetLastError
0x1800030e2  mov     ecx, eax
0x1800030e4  mov     edi, eax
0x1800030e6  sub     ecx, 1
0x1800030e9  jz      short loc_180003124
0x1800030eb  sub     ecx, 31h ; '1'
0x1800030ee  jz      short loc_180003124
0x1800030f0  cmp     ecx, 25h ; '%'
0x1800030f3  jz      short loc_180003124
0x1800030f5  xor     sil, sil
0x1800030f8  xor     r15d, r15d
0x1800030fb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800030ff  jz      short loc_180003112
0x180003101  mov     rcx, rbx; hObject
0x180003104  call    cs:__imp_CloseHandle
0x18000310a  test    eax, eax
0x18000310c  jz      loc_1800032E3
0x180003112  mov     byte ptr [rbp+FileInformation], sil
0x180003116  mov     word ptr [rbp+FileInformation+1], r15w
0x18000311b  mov     byte ptr [rbp+FileInformation+3], r15b
0x18000311f  jmp     loc_180003078
0x180003124  mov     rcx, rbx; hFile
0x180003127  call    _anonymous_namespace____Set_delete_flag
0x18000312c  mov     edi, eax
0x18000312e  test    eax, eax
0x180003130  jz      loc_180003053
0x180003136  cmp     eax, r15d
0x180003139  jnz     loc_18000327A
0x18000313f  test    sil, sil
0x180003142  jz      loc_18000327A
0x180003148  xor     eax, eax
0x18000314a  lea     r8, [rbp+var_30]; lpFileInformation
0x18000314e  xorps   xmm0, xmm0
0x180003151  mov     [rbp+var_10], rax
0x180003155  xor     edx, edx; FileInformationClass
0x180003157  mov     rcx, rbx; hFile
0x18000315a  movups  [rbp+var_30], xmm0
0x18000315e  lea     edi, [rax+28h]
0x180003161  mov     r9d, edi; dwBufferSize
0x180003164  movups  [rbp+var_20], xmm0
0x180003168  call    cs:__imp_GetFileInformationByHandleEx
0x18000316e  test    eax, eax
0x180003170  jnz     short loc_1800031A8
0x180003172  xor     eax, eax
0x180003174  mov     byte ptr [rbp+hFile], 0
0x180003178  mov     word ptr [rbp+hFile+1], ax
0x18000317c  mov     byte ptr [rbp+hFile+3], al
0x18000317f  call    cs:__imp_GetLastError
0x180003185  mov     dword ptr [rbp+hFile+4], eax
0x180003188  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000318c  jz      loc_1800032F9
0x180003192  mov     rcx, rbx; hObject
0x180003195  call    cs:__imp_CloseHandle
0x18000319b  test    eax, eax
0x18000319d  jz      loc_18000323B
0x1800031a3  jmp     loc_1800032F9
0x1800031a8  mov     eax, dword ptr [rbp+var_10]
0x1800031ab  test    al, 1
0x1800031ad  jz      short loc_180003223
0x1800031af  xor     eax, 1
0x1800031b2  lea     r8, [rbp+var_30]; lpFileInformation
0x1800031b6  mov     r9d, edi; dwBufferSize
0x1800031b9  mov     dword ptr [rbp+var_10], eax
0x1800031bc  xor     edx, edx; FileInformationClass
0x1800031be  mov     rcx, rbx; hFile
0x1800031c1  call    cs:__imp_SetFileInformationByHandle
0x1800031c7  test    eax, eax
0x1800031c9  jz      short loc_180003172
0x1800031cb  mov     rcx, rbx; hFile
0x1800031ce  call    _anonymous_namespace____Set_delete_flag
0x1800031d3  test    eax, eax
0x1800031d5  jnz     short loc_180003200
0x1800031d7  xor     edi, edi
0x1800031d9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800031dd  jz      short loc_1800031EC
0x1800031df  mov     rcx, rbx; hObject
0x1800031e2  call    cs:__imp_CloseHandle
0x1800031e8  test    eax, eax
0x1800031ea  jz      short loc_18000323B
0x1800031ec  mov     byte ptr [rbp+hFile], 1
0x1800031f0  mov     word ptr [rbp+hFile+1], di
0x1800031f4  mov     byte ptr [rbp+hFile+3], dil
0x1800031f8  mov     dword ptr [rbp+hFile+4], edi
0x1800031fb  jmp     loc_1800032F9
0x180003200  cmp     eax, r15d
0x180003203  jnz     short loc_18000324B
0x180003205  or      dword ptr [rbp+var_10], 1
0x180003209  lea     r8, [rbp+var_30]; lpFileInformation
0x18000320d  mov     r9d, edi; dwBufferSize
0x180003210  xor     edx, edx; FileInformationClass
0x180003212  mov     rcx, rbx; hFile
0x180003215  call    cs:__imp_SetFileInformationByHandle
0x18000321b  test    eax, eax
0x18000321d  jz      loc_180003172
0x180003223  xor     dil, dil
0x180003226  xor     esi, esi
0x180003228  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000322c  jz      short loc_180003242
0x18000322e  mov     rcx, rbx; hObject
0x180003231  call    cs:__imp_CloseHandle
0x180003237  test    eax, eax
0x180003239  jnz     short loc_180003242
0x18000323b  call    cs:__imp_abort
0x180003242  mov     dword ptr [rbp+hFile+4], r15d
0x180003246  jmp     loc_1800032ED
0x18000324b  xor     eax, eax
0x18000324d  mov     byte ptr [rbp+hFile], 0
0x180003251  mov     word ptr [rbp+hFile+1], ax
0x180003255  mov     byte ptr [rbp+hFile+3], al
0x180003258  call    cs:__imp_GetLastError
0x18000325e  mov     dword ptr [rbp+hFile+4], eax
0x180003261  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180003265  jz      loc_1800032F9
0x18000326b  mov     rcx, rbx; hObject
0x18000326e  call    cs:__imp_CloseHandle
0x180003274  test    eax, eax
0x180003276  jz      short loc_1800032E3
0x180003278  jmp     short loc_1800032F9
0x18000327a  xor     sil, sil
0x18000327d  xor     r15d, r15d
0x180003280  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180003284  jz      short loc_180003293
0x180003286  mov     rcx, rbx; hObject
0x180003289  call    cs:__imp_CloseHandle
0x18000328f  test    eax, eax
0x180003291  jz      short loc_1800032E3
0x180003293  mov     byte ptr [rbp+hFile], sil
0x180003297  mov     word ptr [rbp+hFile+1], r15w
0x18000329c  mov     byte ptr [rbp+hFile+3], r15b
0x1800032a0  jmp     loc_1800031F8
0x1800032a5  xor     dil, dil
0x1800032a8  xor     esi, esi
0x1800032aa  sub     eax, 2
0x1800032ad  jz      short loc_1800032CD
0x1800032af  sub     eax, 1
0x1800032b2  jz      short loc_1800032CD
0x1800032b4  sub     eax, 32h ; '2'
0x1800032b7  jz      short loc_1800032CD
0x1800032b9  sub     eax, 0Bh
0x1800032bc  jz      short loc_1800032CD
0x1800032be  sub     eax, 3Bh ; ';'
0x1800032c1  jz      short loc_1800032CD
0x1800032c3  sub     eax, 26h ; '&'
0x1800032c6  jz      short loc_1800032CD
0x1800032c8  cmp     eax, 6Ah ; 'j'
0x1800032cb  jnz     short loc_1800032CF
0x1800032cd  xor     ebx, ebx
0x1800032cf  mov     rcx, [rbp+hFile]; hObject
0x1800032d3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800032d7  jz      short loc_1800032EA
0x1800032d9  call    cs:__imp_CloseHandle
0x1800032df  test    eax, eax
0x1800032e1  jnz     short loc_1800032EA
0x1800032e3  call    cs:__imp_abort
0x1800032ea  mov     dword ptr [rbp+hFile+4], ebx
0x1800032ed  mov     byte ptr [rbp+hFile], dil
0x1800032f1  mov     word ptr [rbp+hFile+1], si
0x1800032f5  mov     byte ptr [rbp+hFile+3], sil
0x1800032f9  mov     rax, [rbp+hFile]
0x1800032fd  mov     rcx, [rbp+var_8]
0x180003301  xor     rcx, rsp; StackCookie
0x180003304  call    __security_check_cookie
0x180003309  lea     r11, [rsp+60h+var_s0]
0x18000330e  mov     rbx, [r11+28h]
0x180003312  mov     rsi, [r11+30h]
0x180003316  mov     rsp, r11
0x180003319  pop     r15
0x18000331b  pop     rdi
0x18000331c  pop     rbp
0x18000331d  retn
```
