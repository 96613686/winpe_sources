# GetParentDriveOfVirtualDrive

- ea: `0x180030ae0`
- end: `0x180030ee6`
- name: `GetParentDriveOfVirtualDrive`
- size: `1030`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x1800308c0`

## callees

- `0x1800150e0`
- `0x180030ae0`
- `0x1800a2718`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180030df8`
- `msvcrt!wcscat_s` at `0x180030df8`
- `msvcrt!free` at `0x180030ecd`
- `msvcrt!free` at `0x180030ecd`
- `msvcrt!wcscpy_s` at `0x180030de6`
- `msvcrt!wcscpy_s` at `0x180030de6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180030b52`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180030b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030e78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030e78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030d32`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030d32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030edb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030edb`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180030ba4`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180030ba4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030c1a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030c1a`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180030bc3`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180030bc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030b2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030eb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030b2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030eb8`

## pseudocode

```c
__int64 __fastcall GetParentDriveOfVirtualDrive(LPCWSTR lpszFileName, _DWORD *a2, wchar_t **a3)
{
  _DWORD *v3; // r15
  wchar_t *v5; // rcx
  __int64 (__fastcall *v7)(HANDLE, __int64, __int64, _DWORD *, SIZE_T *); // r13
  unsigned __int64 v8; // rax
  __int64 v9; // rax
  HANDLE FileW; // rsi
  signed int LastError; // edi
  unsigned __int64 v13; // rcx
  size_t v14; // rdi
  _DWORD *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  wchar_t *v18; // rax
  wchar_t *v19; // rcx
  signed __int64 v20; // rdx
  int v21; // ecx
  int v22; // eax
  rsize_t v23; // r13
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // [rsp-20h] [rbp-A0h] BYREF
  int v27[4]; // [rsp+20h] [rbp-60h] BYREF
  _DWORD v28[4]; // [rsp+30h] [rbp-50h] BYREF
  SIZE_T uBytes; // [rsp+80h] [rbp+0h] BYREF
  rsize_t SizeInWords; // [rsp+88h] [rbp+8h]
  _DWORD *v31; // [rsp+90h] [rbp+10h]
  WCHAR szVolumeName[264]; // [rsp+A0h] [rbp+20h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+2B0h] [rbp+230h] BYREF

  v3 = 0;
  v31 = a2;
  *a2 = 0;
  v5 = *a3;
  LODWORD(uBytes) = 0;
  *a3 = 0;
  if ( v5 )
    CoTaskMemFree(v5);
  if ( !lpszFileName )
  {
    LOWORD(LastError) = 87;
    return (unsigned __int16)LastError | 0x80070000;
  }
  if ( !InitOnceExecuteOnce(&g_InitOnceGetStorageDependencyInformation, InitGetStorageDependencyInformation, 0, 0)
    || (v7 = (__int64 (__fastcall *)(HANDLE, __int64, __int64, _DWORD *, SIZE_T *))qword_18015E7A8) == 0 )
  {
    LOWORD(LastError) = 1157;
    return (unsigned __int16)LastError | 0x80070000;
  }
  v8 = -1;
  do
    ++v8;
  while ( lpszFileName[v8] );
  if ( v8 < 2 )
  {
    LOWORD(LastError) = 1;
    return (unsigned __int16)LastError | 0x80070000;
  }
  if ( !GetVolumePathNameW(lpszFileName, szVolumePathName, 0x104u)
    || !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    LastError = GetLastError();
    goto LABEL_24;
  }
  v9 = -1;
  do
    ++v9;
  while ( szVolumeName[v9] );
  if ( v9 && szVolumeName[v9 - 1] == 92 )
  {
    v13 = 2 * v9 - 2;
    if ( v13 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v13) = 0;
  }
  FileW = CreateFileW(szVolumeName, 0x20000u, 7u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    goto LABEL_24;
  }
  if ( &v26 == (__int64 *)-64LL || (v27[0] = 52428, !v28) )
  {
    LOWORD(LastError) = 8;
    CloseHandle(FileW);
    return (unsigned __int16)LastError | 0x80070000;
  }
  v28[0] = 2;
  LODWORD(uBytes) = 0;
  LastError = v7(FileW, 1, 72, v28, &uBytes);
  if ( LastError != 122 )
  {
    SizeInWords = (rsize_t)v28;
    goto LABEL_19;
  }
  v14 = (unsigned int)uBytes;
  v15 = LocalAlloc(0, (unsigned int)uBytes);
  v3 = v15;
  if ( v15 )
  {
    SizeInWords = (rsize_t)v15;
    memset_0(v15, 0, v14);
    *v3 = 2;
    LODWORD(uBytes) = 0;
    LastError = v7(FileW, 1, (unsigned int)v14, v3, &uBytes);
LABEL_19:
    if ( !LastError )
    {
      v23 = SizeInWords;
      if ( *(_DWORD *)(SizeInWords + 4)
        && SizeInWords != -8
        && (v24 = *(_QWORD *)(SizeInWords + 48)) != 0
        && (v25 = *(_QWORD *)(SizeInWords + 64)) != 0 )
      {
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(v24 + 2 * v16) );
        v17 = -1;
        do
          ++v17;
        while ( *(_WORD *)(v25 + 2 * v17) );
        SizeInWords = v16 + 1 + v17;
        v18 = (wchar_t *)operator new(saturated_mul(SizeInWords, 2u));
        v19 = *a3;
        *a3 = v18;
        if ( v19 )
          CoTaskMemFree(v19);
        wcscpy_s(*a3, SizeInWords, *(const wchar_t **)(v23 + 48));
        wcscat_s(*a3, SizeInWords, *(const wchar_t **)(v23 + 64));
        v20 = (char *)*a3 - (char *)lpszFileName;
        do
        {
          v21 = *(LPCWSTR)((char *)lpszFileName + v20);
          v22 = *lpszFileName - v21;
          if ( v22 )
            break;
          ++lpszFileName;
        }
        while ( v21 );
        if ( v22 )
          *v31 = 1;
      }
      else
      {
        LastError = -1069940715;
      }
    }
    goto LABEL_20;
  }
  LastError = 8;
LABEL_20:
  CloseHandle(FileW);
  if ( v27[0] == 56797 )
    free(v27);
  if ( v3 )
    LocalFree(v3);
LABEL_24:
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180030ae0  push    rbp
0x180030ae2  push    rsi
0x180030ae3  push    rdi
0x180030ae4  push    r12
0x180030ae6  push    r13
0x180030ae8  push    r14
0x180030aea  push    r15
0x180030aec  sub     rsp, 490h
0x180030af3  lea     rbp, [rsp+40h]
0x180030af8  mov     [rbp+480h+arg_18], rbx
0x180030aff  mov     rax, cs:__security_cookie
0x180030b06  xor     rax, rbp
0x180030b09  mov     [rbp+480h+var_40], rax
0x180030b10  xor     r15d, r15d
0x180030b13  mov     [rbp+480h+var_470], rdx
0x180030b17  mov     [rdx], r15d
0x180030b1a  mov     rbx, rcx
0x180030b1d  mov     rcx, [r8]; pv
0x180030b20  mov     r12, r8
0x180030b23  mov     dword ptr [rbp+480h+uBytes], r15d
0x180030b27  mov     [r8], r15
0x180030b2a  test    rcx, rcx
0x180030b2d  jz      short loc_180030B35
0x180030b2f  call    cs:__imp_CoTaskMemFree
0x180030b35  test    rbx, rbx
0x180030b38  jz      loc_180030E2F
0x180030b3e  xor     r9d, r9d; Context
0x180030b41  lea     rdx, ?InitGetStorageDependencyInformation@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180030b48  xor     r8d, r8d; Parameter
0x180030b4b  lea     rcx, ?g_InitOnceGetStorageDependencyInformation@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180030b52  call    cs:__imp_InitOnceExecuteOnce
0x180030b58  test    eax, eax
0x180030b5a  jz      loc_180030CF8
0x180030b60  mov     r13, cs:qword_18015E7A8
0x180030b67  test    r13, r13
0x180030b6a  jz      loc_180030CF8
0x180030b70  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180030b77  mov     rax, rdi
0x180030b7a  nop     word ptr [rax+rax+00h]
0x180030b80  inc     rax
0x180030b83  cmp     [rbx+rax*2], r15w
0x180030b88  jnz     short loc_180030B80
0x180030b8a  cmp     rax, 2
0x180030b8e  jb      loc_180030E39
0x180030b94  mov     r8d, 104h; cchBufferLength
0x180030b9a  lea     rdx, [rbp+480h+szVolumePathName]; lpszVolumePathName
0x180030ba1  mov     rcx, rbx; lpszFileName
0x180030ba4  call    cs:__imp_GetVolumePathNameW
0x180030baa  test    eax, eax
0x180030bac  jz      loc_180030E43
0x180030bb2  mov     r8d, 104h; cchBufferLength
0x180030bb8  lea     rdx, [rbp+480h+szVolumeName]; lpszVolumeName
0x180030bbc  lea     rcx, [rbp+480h+szVolumePathName]; lpszVolumeMountPoint
0x180030bc3  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180030bc9  test    eax, eax
0x180030bcb  jz      loc_180030E50
0x180030bd1  lea     rcx, [rbp+480h+szVolumeName]
0x180030bd5  mov     rax, rdi
0x180030bd8  nop     dword ptr [rax+rax+00000000h]
0x180030be0  inc     rax
0x180030be3  cmp     [rcx+rax*2], r15w
0x180030be8  jnz     short loc_180030BE0
0x180030bea  test    rax, rax
0x180030bed  jnz     loc_180030CFF
0x180030bf3  mov     [rsp+4C0h+hTemplateFile], r15; hTemplateFile
0x180030bf8  lea     rcx, [rbp+480h+szVolumeName]; lpFileName
0x180030bfc  mov     [rsp+4C0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180030c04  xor     r9d, r9d; lpSecurityAttributes
0x180030c07  mov     edx, 20000h; dwDesiredAccess
0x180030c0c  mov     [rsp+4C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180030c14  mov     r8d, 7; dwShareMode
0x180030c1a  call    cs:__imp_CreateFileW
0x180030c20  mov     rsi, rax
0x180030c23  cmp     rax, rdi
0x180030c26  jz      loc_180030E63
0x180030c2c  mov     eax, [rsp+4C0h+var_4C0]
0x180030c2f  sub     rsp, 60h
0x180030c33  lea     r14, [rsp+520h+var_4E0]
0x180030c38  mov     eax, [r14]
0x180030c3b  test    r14, r14
0x180030c3e  jz      loc_180030E70
0x180030c44  mov     dword ptr [r14], 0CCCCh
0x180030c4b  add     r14, 10h
0x180030c4f  test    r14, r14
0x180030c52  jz      loc_180030E70
0x180030c58  lea     rax, [rbp+480h+uBytes]
0x180030c5c  mov     dword ptr [r14], 2
0x180030c63  mov     [rsp+520h+var_500], rax
0x180030c68  mov     r9, r14
0x180030c6b  mov     rax, r13
0x180030c6e  mov     dword ptr [rbp+480h+uBytes], r15d
0x180030c72  mov     edx, 1
0x180030c77  mov     r8d, 48h ; 'H'
0x180030c7d  mov     rcx, rsi
0x180030c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c85  mov     edi, eax
0x180030c87  cmp     eax, 7Ah ; 'z'
0x180030c8a  jz      loc_180030D2B
0x180030c90  mov     [rbp+480h+SizeInWords], r14
0x180030c94  test    edi, edi
0x180030c96  jz      loc_180030E83
0x180030c9c  mov     rcx, rsi; hObject
0x180030c9f  call    cs:__imp_CloseHandle
0x180030ca5  cmp     dword ptr [r14-10h], 0DDDDh
0x180030cad  lea     rcx, [r14-10h]; Block
0x180030cb1  jz      loc_180030ECD
0x180030cb7  test    r15, r15
0x180030cba  jnz     loc_180030ED8
0x180030cc0  test    edi, edi
0x180030cc2  jle     short loc_180030CCD
0x180030cc4  movzx   edi, di
0x180030cc7  or      edi, 80070000h
0x180030ccd  mov     eax, edi
0x180030ccf  mov     rcx, [rbp+480h+var_40]
0x180030cd6  xor     rcx, rbp; StackCookie
0x180030cd9  call    __security_check_cookie
0x180030cde  mov     rbx, [rbp+480h+arg_18]
0x180030ce5  lea     rsp, [rbp+450h]
0x180030cec  pop     r15
0x180030cee  pop     r14
0x180030cf0  pop     r13
0x180030cf2  pop     r12
0x180030cf4  pop     rdi
0x180030cf5  pop     rsi
0x180030cf6  pop     rbp
0x180030cf7  retn
0x180030cf8  mov     edi, 485h
0x180030cfd  jmp     short loc_180030CC4
0x180030cff  cmp     [rbp+rax*2+480h+var_462], 5Ch ; '\'
0x180030d05  jnz     loc_180030BF3
0x180030d0b  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180030d13  cmp     rcx, 208h
0x180030d1a  jnb     loc_180030E5D
0x180030d20  mov     [rbp+rcx+480h+szVolumeName], r15w
0x180030d26  jmp     loc_180030BF3
0x180030d2b  mov     edi, dword ptr [rbp+480h+uBytes]
0x180030d2e  xor     ecx, ecx; uFlags
0x180030d30  mov     edx, edi; uBytes
0x180030d32  call    cs:__imp_LocalAlloc
0x180030d38  mov     r15, rax
0x180030d3b  test    rax, rax
0x180030d3e  jnz     short loc_180030D4A
0x180030d40  mov     edi, 8
0x180030d45  jmp     loc_180030C9C
0x180030d4a  mov     r8, rdi; Size
0x180030d4d  mov     [rbp+480h+SizeInWords], r15
0x180030d51  xor     edx, edx; Val
0x180030d53  mov     rcx, r15; void *
0x180030d56  call    memset_0
0x180030d5b  lea     rax, [rbp+480h+uBytes]
0x180030d5f  mov     dword ptr [r15], 2
0x180030d66  mov     [rsp+520h+var_500], rax
0x180030d6b  mov     r9, r15
0x180030d6e  mov     rax, r13
0x180030d71  mov     dword ptr [rbp+480h+uBytes], 0
0x180030d78  mov     r8d, edi
0x180030d7b  mov     edx, 1
0x180030d80  mov     rcx, rsi
0x180030d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d88  mov     edi, eax
0x180030d8a  jmp     loc_180030C94
0x180030d90  inc     rdx
0x180030d93  cmp     word ptr [rax+rdx*2], 0
0x180030d98  jnz     short loc_180030D90
0x180030d9a  mov     rcx, r9
0x180030d9d  nop     dword ptr [rax]
0x180030da0  inc     rcx
0x180030da3  cmp     word ptr [r8+rcx*2], 0
0x180030da9  jnz     short loc_180030DA0
0x180030dab  inc     rdx
0x180030dae  mov     eax, 2
0x180030db3  add     rcx, rdx
0x180030db6  mul     rcx
0x180030db9  mov     [rbp+480h+SizeInWords], rcx
0x180030dbd  cmovb   rax, r9
0x180030dc1  mov     rcx, rax; Size
0x180030dc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030dc9  mov     rcx, [r12]; pv
0x180030dcd  mov     [r12], rax
0x180030dd1  test    rcx, rcx
0x180030dd4  jnz     loc_180030EB8
0x180030dda  mov     r8, [r13+30h]; Source
0x180030dde  mov     rdx, [rbp+480h+SizeInWords]; SizeInWords
0x180030de2  mov     rcx, [r12]; Destination
0x180030de6  call    cs:__imp_wcscpy_s
0x180030dec  mov     r8, [r13+40h]; Source
0x180030df0  mov     rdx, [rbp+480h+SizeInWords]; SizeInWords
0x180030df4  mov     rcx, [r12]; Destination
0x180030df8  call    cs:__imp_wcscat_s
0x180030dfe  mov     rdx, [r12]
0x180030e02  sub     rdx, rbx
0x180030e05  movzx   eax, word ptr [rbx]
0x180030e08  movzx   ecx, word ptr [rbx+rdx]
0x180030e0c  sub     eax, ecx
0x180030e0e  jnz     short loc_180030E18
0x180030e10  add     rbx, 2
0x180030e14  test    ecx, ecx
0x180030e16  jnz     short loc_180030E05
0x180030e18  test    eax, eax
0x180030e1a  jz      loc_180030C9C
0x180030e20  mov     rax, [rbp+480h+var_470]
0x180030e24  mov     dword ptr [rax], 1
0x180030e2a  jmp     loc_180030C9C
0x180030e2f  mov     edi, 57h ; 'W'
0x180030e34  jmp     loc_180030CC4
0x180030e39  mov     edi, 1
0x180030e3e  jmp     loc_180030CC4
0x180030e43  call    cs:__imp_GetLastError
0x180030e49  mov     edi, eax
0x180030e4b  jmp     loc_180030CC0
0x180030e50  call    cs:__imp_GetLastError
0x180030e56  mov     edi, eax
0x180030e58  jmp     loc_180030CC0
0x180030e5d  call    __report_rangecheckfailure
0x180030e63  call    cs:__imp_GetLastError
0x180030e69  mov     edi, eax
0x180030e6b  jmp     loc_180030CC0
0x180030e70  mov     rcx, rsi; hObject
0x180030e73  mov     edi, 8
0x180030e78  call    cs:__imp_CloseHandle
0x180030e7e  jmp     loc_180030CC4
0x180030e83  mov     r13, [rbp+480h+SizeInWords]
0x180030e87  cmp     dword ptr [r13+4], 0
0x180030e8c  jz      short loc_180030EC3
0x180030e8e  lea     rax, [r13+8]
0x180030e92  test    rax, rax
0x180030e95  jz      short loc_180030EC3
0x180030e97  mov     rax, [r13+30h]
0x180030e9b  test    rax, rax
0x180030e9e  jz      short loc_180030EC3
0x180030ea0  mov     r8, [r13+40h]
0x180030ea4  test    r8, r8
0x180030ea7  jz      short loc_180030EC3
0x180030ea9  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180030eb0  mov     rdx, r9
0x180030eb3  jmp     loc_180030D90
0x180030eb8  call    cs:__imp_CoTaskMemFree
0x180030ebe  jmp     loc_180030DDA
0x180030ec3  mov     edi, 0C03A0015h
0x180030ec8  jmp     loc_180030C9C
0x180030ecd  call    cs:__imp_free
0x180030ed3  jmp     loc_180030CB7
0x180030ed8  mov     rcx, r15; hMem
0x180030edb  call    cs:__imp_LocalFree
0x180030ee1  jmp     loc_180030CC0
```
