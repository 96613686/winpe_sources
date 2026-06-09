# __std_fs_remove

- ea: `0x180043090`
- end: `0x180043320`
- name: `__std_fs_remove`
- size: `656`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18002bc94`
- `0x18002bea4`
- `0x18002f120`
- `0x18002f63c`
- `0x180066e90`

## callees

- `0x180042ec4`
- `0x180042f44`
- `0x180043090`
- `0x1800dd768`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043229`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800430fa`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180043259`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180043296`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800430fa`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180043259`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180043296`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800431fc`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800431fc`

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
0x180043090  mov     [rsp-8+arg_8], rbx
0x180043095  mov     [rsp-8+arg_10], rsi
0x18004309a  mov     [rsp-8+arg_18], rdi
0x18004309f  push    rbp
0x1800430a0  mov     rbp, rsp
0x1800430a3  sub     rsp, 70h
0x1800430a7  mov     rax, cs:__security_cookie
0x1800430ae  xor     rax, rsp
0x1800430b1  mov     [rbp+var_10], rax
0x1800430b5  mov     rbx, rcx
0x1800430b8  mov     rdx, rcx
0x1800430bb  xor     esi, esi
0x1800430bd  lea     rcx, [rbp+hFile]
0x1800430c1  mov     r9d, 2200000h
0x1800430c7  mov     r8d, 10180h
0x1800430cd  mov     dil, sil
0x1800430d0  call    __std_fs_open_handle
0x1800430d5  mov     ecx, eax
0x1800430d7  test    eax, eax
0x1800430d9  jnz     short loc_180043123
0x1800430db  mov     dil, 1
0x1800430de  mov     rbx, [rbp+hFile]
0x1800430e2  lea     r8, [rbp+FileInformation]; lpFileInformation
0x1800430e6  mov     r9d, 4; dwBufferSize
0x1800430ec  mov     [rbp+FileInformation], 13h
0x1800430f3  mov     rcx, rbx; hFile
0x1800430f6  lea     edx, [r9+11h]; FileInformationClass
0x1800430fa  call    cs:__imp_SetFileInformationByHandle
0x180043100  test    eax, eax
0x180043102  jz      loc_180043196
0x180043108  xor     eax, eax
0x18004310a  mov     byte ptr [rbp+var_50], 1
0x18004310e  mov     word ptr [rbp+var_50+1], ax
0x180043112  mov     byte ptr [rbp+var_50+3], al
0x180043115  mov     dword ptr [rbp+var_50+4], esi
0x180043118  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18004311c  jz      short loc_180043170
0x18004311e  mov     rcx, rbx
0x180043121  jmp     short loc_180043162
0x180043123  cmp     ecx, 5
0x180043126  jnz     loc_1800432DB
0x18004312c  mov     r9d, 2200000h
0x180043132  lea     rcx, [rbp+hFile]
0x180043136  mov     r8d, 10000h
0x18004313c  mov     rdx, rbx
0x18004313f  call    __std_fs_open_handle
0x180043144  test    eax, eax
0x180043146  jz      short loc_1800430DE
0x180043148  xor     ecx, ecx
0x18004314a  mov     byte ptr [rbp+var_50], sil
0x18004314e  mov     word ptr [rbp+var_50+1], cx
0x180043152  mov     byte ptr [rbp+var_50+3], cl
0x180043155  mov     dword ptr [rbp+var_50+4], eax
0x180043158  mov     rcx, [rbp+hFile]; hObject
0x18004315c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180043160  jz      short loc_180043170
0x180043162  call    cs:__imp_CloseHandle
0x180043168  test    eax, eax
0x18004316a  jz      loc_180043314
0x180043170  mov     rax, [rbp+var_50]
0x180043174  mov     rcx, [rbp+var_10]
0x180043178  xor     rcx, rsp; StackCookie
0x18004317b  call    __security_check_cookie
0x180043180  lea     r11, [rsp+70h+var_s0]
0x180043185  mov     rbx, [r11+18h]
0x180043189  mov     rsi, [r11+20h]
0x18004318d  mov     rdi, [r11+28h]
0x180043191  mov     rsp, r11
0x180043194  pop     rbp
0x180043195  retn
0x180043196  call    cs:__imp_GetLastError
0x18004319c  mov     ecx, eax
0x18004319e  sub     ecx, 1
0x1800431a1  jz      short loc_1800431C2
0x1800431a3  sub     ecx, 31h ; '1'
0x1800431a6  jz      short loc_1800431C2
0x1800431a8  cmp     ecx, 25h ; '%'
0x1800431ab  jz      short loc_1800431C2
0x1800431ad  xor     ecx, ecx
0x1800431af  mov     byte ptr [rbp+var_50], sil
0x1800431b3  mov     word ptr [rbp+var_50+1], cx
0x1800431b7  mov     byte ptr [rbp+var_50+3], cl
0x1800431ba  mov     dword ptr [rbp+var_50+4], eax
0x1800431bd  jmp     loc_180043118
0x1800431c2  mov     rcx, rbx; hFile
0x1800431c5  call    _anonymous_namespace____Set_delete_flag
0x1800431ca  test    eax, eax
0x1800431cc  jz      loc_180043108
0x1800431d2  cmp     eax, 5
0x1800431d5  jnz     short loc_1800431AD
0x1800431d7  test    dil, dil
0x1800431da  jz      short loc_1800431AD
0x1800431dc  xor     eax, eax
0x1800431de  lea     r8, [rbp+var_38]; lpFileInformation
0x1800431e2  xorps   xmm0, xmm0
0x1800431e5  mov     [rbp+var_18], rax
0x1800431e9  xor     edx, edx; FileInformationClass
0x1800431eb  mov     rcx, rbx; hFile
0x1800431ee  movups  [rbp+var_38], xmm0
0x1800431f2  lea     edi, [rax+28h]
0x1800431f5  mov     r9d, edi; dwBufferSize
0x1800431f8  movups  [rbp+var_28], xmm0
0x1800431fc  call    cs:__imp_GetFileInformationByHandleEx
0x180043202  test    eax, eax
0x180043204  jnz     short loc_18004323C
0x180043206  mov     byte ptr [rbp+var_50], sil
0x18004320a  xor     eax, eax
0x18004320c  mov     word ptr [rbp+var_50+1], ax
0x180043210  mov     byte ptr [rbp+var_50+3], al
0x180043213  call    cs:__imp_GetLastError
0x180043219  mov     dword ptr [rbp+var_50+4], eax
0x18004321c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180043220  jz      loc_180043170
0x180043226  mov     rcx, rbx; hObject
0x180043229  call    cs:__imp_CloseHandle
0x18004322f  test    eax, eax
0x180043231  jz      loc_18004331A
0x180043237  jmp     loc_180043170
0x18004323c  mov     eax, dword ptr [rbp+var_18]
0x18004323f  test    al, 1
0x180043241  jz      loc_1800432D5
0x180043247  xor     eax, 1
0x18004324a  lea     r8, [rbp+var_38]; lpFileInformation
0x18004324e  mov     r9d, edi; dwBufferSize
0x180043251  mov     dword ptr [rbp+var_18], eax
0x180043254  xor     edx, edx; FileInformationClass
0x180043256  mov     rcx, rbx; hFile
0x180043259  call    cs:__imp_SetFileInformationByHandle
0x18004325f  test    eax, eax
0x180043261  jz      short loc_180043206
0x180043263  mov     rcx, rbx; hFile
0x180043266  call    _anonymous_namespace____Set_delete_flag
0x18004326b  test    eax, eax
0x18004326d  jnz     short loc_180043281
0x18004326f  xor     eax, eax
0x180043271  mov     byte ptr [rbp+var_50], 1
0x180043275  mov     word ptr [rbp+var_50+1], ax
0x180043279  mov     byte ptr [rbp+var_50+3], al
0x18004327c  mov     dword ptr [rbp+var_50+4], esi
0x18004327f  jmp     short loc_18004321C
0x180043281  cmp     eax, 5
0x180043284  jnz     short loc_1800432BD
0x180043286  or      dword ptr [rbp+var_18], 1
0x18004328a  lea     r8, [rbp+var_38]; lpFileInformation
0x18004328e  mov     r9d, edi; dwBufferSize
0x180043291  xor     edx, edx; FileInformationClass
0x180043293  mov     rcx, rbx; hFile
0x180043296  call    cs:__imp_SetFileInformationByHandle
0x18004329c  mov     byte ptr [rbp+var_50], sil
0x1800432a0  test    eax, eax
0x1800432a2  jz      loc_18004320A
0x1800432a8  xor     eax, eax
0x1800432aa  mov     dword ptr [rbp+var_50+4], 5
0x1800432b1  mov     word ptr [rbp+var_50+1], ax
0x1800432b5  mov     byte ptr [rbp+var_50+3], al
0x1800432b8  jmp     loc_18004321C
0x1800432bd  xor     eax, eax
0x1800432bf  mov     byte ptr [rbp+var_50], sil
0x1800432c3  mov     word ptr [rbp+var_50+1], ax
0x1800432c7  mov     byte ptr [rbp+var_50+3], al
0x1800432ca  call    cs:__imp_GetLastError
0x1800432d0  jmp     loc_1800431BA
0x1800432d5  mov     byte ptr [rbp+var_50], sil
0x1800432d9  jmp     short loc_1800432A8
0x1800432db  xor     eax, eax
0x1800432dd  mov     byte ptr [rbp+var_50], sil
0x1800432e1  mov     word ptr [rbp+var_50+1], ax
0x1800432e5  mov     byte ptr [rbp+var_50+3], al
0x1800432e8  mov     eax, ecx
0x1800432ea  sub     eax, 2
0x1800432ed  jz      short loc_18004330A
0x1800432ef  sub     eax, 1
0x1800432f2  jz      short loc_18004330A
0x1800432f4  sub     eax, 32h ; '2'
0x1800432f7  jz      short loc_18004330A
0x1800432f9  sub     eax, 0Bh
0x1800432fc  jz      short loc_18004330A
0x1800432fe  sub     eax, 3Bh ; ';'
0x180043301  jz      short loc_18004330A
0x180043303  cmp     eax, 90h
0x180043308  jnz     short loc_18004330C
0x18004330a  mov     ecx, esi
0x18004330c  mov     dword ptr [rbp+var_50+4], ecx
0x18004330f  jmp     loc_180043158
0x180043314  call    abort
0x18004331a  call    abort
```
