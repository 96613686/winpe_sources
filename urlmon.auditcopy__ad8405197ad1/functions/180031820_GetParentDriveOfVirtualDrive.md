# GetParentDriveOfVirtualDrive

- ea: `0x180031820`
- end: `0x180031c7c`
- name: `GetParentDriveOfVirtualDrive`
- size: `1116`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName, _DWORD *, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x180031600`

## callees

- `0x18001db50`
- `0x180031820`
- `0x1800a9538`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180031b5e`
- `msvcrt!wcscat_s` at `0x180031b5e`
- `msvcrt!free` at `0x180031c57`
- `msvcrt!free` at `0x180031c57`
- `msvcrt!wcscpy_s` at `0x180031b46`
- `msvcrt!wcscpy_s` at `0x180031b46`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180031898`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180031898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800319f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031bf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800319f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031bf6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031a8f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031a8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031c6b`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800318ea`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800318ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003196a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003196a`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18003190f`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18003190f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003186f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031c3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003186f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031c3c`

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
  if ( !InitOnceExecuteOnce(
          &g_InitOnceGetStorageDependencyInformation,
          (PINIT_ONCE_FN)InitGetStorageDependencyInformation,
          0,
          0)
    || (v7 = (__int64 (__fastcall *)(HANDLE, __int64, __int64, _DWORD *, SIZE_T *))qword_18016B8A0) == 0 )
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
0x180031820  push    rbp
0x180031822  push    rsi
0x180031823  push    rdi
0x180031824  push    r12
0x180031826  push    r13
0x180031828  push    r14
0x18003182a  push    r15
0x18003182c  sub     rsp, 490h
0x180031833  lea     rbp, [rsp+40h]
0x180031838  mov     [rbp+480h+arg_18], rbx
0x18003183f  mov     rax, cs:__security_cookie
0x180031846  xor     rax, rbp
0x180031849  mov     [rbp+480h+var_40], rax
0x180031850  xor     r15d, r15d
0x180031853  mov     [rbp+480h+var_470], rdx
0x180031857  mov     [rdx], r15d
0x18003185a  mov     rbx, rcx
0x18003185d  mov     rcx, [r8]; pv
0x180031860  mov     r12, r8
0x180031863  mov     dword ptr [rbp+480h+uBytes], r15d
0x180031867  mov     [r8], r15
0x18003186a  test    rcx, rcx
0x18003186d  jz      short loc_18003187B
0x18003186f  call    cs:__imp_CoTaskMemFree
0x180031876  nop     dword ptr [rax+rax+00h]
0x18003187b  test    rbx, rbx
0x18003187e  jz      loc_180031B9B
0x180031884  xor     r9d, r9d; Context
0x180031887  lea     rdx, ?InitGetStorageDependencyInformation@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18003188e  xor     r8d, r8d; Parameter
0x180031891  lea     rcx, ?g_InitOnceGetStorageDependencyInformation@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180031898  call    cs:__imp_InitOnceExecuteOnce
0x18003189f  nop     dword ptr [rax+rax+00h]
0x1800318a4  test    eax, eax
0x1800318a6  jz      loc_180031A55
0x1800318ac  mov     r13, cs:qword_18016B8A0
0x1800318b3  test    r13, r13
0x1800318b6  jz      loc_180031A55
0x1800318bc  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800318c3  mov     rax, rdi
0x1800318c6  inc     rax
0x1800318c9  cmp     [rbx+rax*2], r15w
0x1800318ce  jnz     short loc_1800318C6
0x1800318d0  cmp     rax, 2
0x1800318d4  jb      loc_180031BA5
0x1800318da  mov     r8d, 104h; cchBufferLength
0x1800318e0  lea     rdx, [rbp+480h+szVolumePathName]; lpszVolumePathName
0x1800318e7  mov     rcx, rbx; lpszFileName
0x1800318ea  call    cs:__imp_GetVolumePathNameW
0x1800318f1  nop     dword ptr [rax+rax+00h]
0x1800318f6  test    eax, eax
0x1800318f8  jz      loc_180031BAF
0x1800318fe  mov     r8d, 104h; cchBufferLength
0x180031904  lea     rdx, [rbp+480h+szVolumeName]; lpszVolumeName
0x180031908  lea     rcx, [rbp+480h+szVolumePathName]; lpszVolumeMountPoint
0x18003190f  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180031916  nop     dword ptr [rax+rax+00h]
0x18003191b  test    eax, eax
0x18003191d  jz      loc_180031BC2
0x180031923  lea     rcx, [rbp+480h+szVolumeName]
0x180031927  mov     rax, rdi
0x18003192a  nop     word ptr [rax+rax+00h]
0x180031930  inc     rax
0x180031933  cmp     [rcx+rax*2], r15w
0x180031938  jnz     short loc_180031930
0x18003193a  test    rax, rax
0x18003193d  jnz     loc_180031A5C
0x180031943  mov     [rsp+4C0h+hTemplateFile], r15; hTemplateFile
0x180031948  lea     rcx, [rbp+480h+szVolumeName]; lpFileName
0x18003194c  mov     [rsp+4C0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180031954  xor     r9d, r9d; lpSecurityAttributes
0x180031957  mov     edx, 20000h; dwDesiredAccess
0x18003195c  mov     [rsp+4C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180031964  mov     r8d, 7; dwShareMode
0x18003196a  call    cs:__imp_CreateFileW
0x180031971  nop     dword ptr [rax+rax+00h]
0x180031976  mov     rsi, rax
0x180031979  cmp     rax, rdi
0x18003197c  jz      loc_180031BDB
0x180031982  mov     eax, [rsp+4C0h+var_4C0]
0x180031985  sub     rsp, 60h
0x180031989  lea     r14, [rsp+520h+var_4E0]
0x18003198e  mov     eax, [r14]
0x180031991  test    r14, r14
0x180031994  jz      loc_180031BEE
0x18003199a  mov     dword ptr [r14], 0CCCCh
0x1800319a1  add     r14, 10h
0x1800319a5  test    r14, r14
0x1800319a8  jz      loc_180031BEE
0x1800319ae  lea     rax, [rbp+480h+uBytes]
0x1800319b2  mov     dword ptr [r14], 2
0x1800319b9  mov     [rsp+520h+var_500], rax
0x1800319be  mov     r9, r14
0x1800319c1  mov     rax, r13
0x1800319c4  mov     dword ptr [rbp+480h+uBytes], r15d
0x1800319c8  mov     edx, 1
0x1800319cd  mov     r8d, 48h ; 'H'
0x1800319d3  mov     rcx, rsi
0x1800319d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319db  mov     edi, eax
0x1800319dd  cmp     eax, 7Ah ; 'z'
0x1800319e0  jz      loc_180031A88
0x1800319e6  mov     [rbp+480h+SizeInWords], r14
0x1800319ea  test    edi, edi
0x1800319ec  jz      loc_180031C07
0x1800319f2  mov     rcx, rsi; hObject
0x1800319f5  call    cs:__imp_CloseHandle
0x1800319fc  nop     dword ptr [rax+rax+00h]
0x180031a01  cmp     dword ptr [r14-10h], 0DDDDh
0x180031a09  lea     rcx, [r14-10h]; Block
0x180031a0d  jz      loc_180031C57
0x180031a13  test    r15, r15
0x180031a16  jnz     loc_180031C68
0x180031a1c  test    edi, edi
0x180031a1e  jle     short loc_180031A29
0x180031a20  movzx   edi, di
0x180031a23  or      edi, 80070000h
0x180031a29  mov     eax, edi
0x180031a2b  mov     rcx, [rbp+480h+var_40]
0x180031a32  xor     rcx, rbp; StackCookie
0x180031a35  call    __security_check_cookie
0x180031a3a  mov     rbx, [rbp+480h+arg_18]
0x180031a41  lea     rsp, [rbp+450h]
0x180031a48  pop     r15
0x180031a4a  pop     r14
0x180031a4c  pop     r13
0x180031a4e  pop     r12
0x180031a50  pop     rdi
0x180031a51  pop     rsi
0x180031a52  pop     rbp
0x180031a53  retn
0x180031a55  mov     edi, 485h
0x180031a5a  jmp     short loc_180031A20
0x180031a5c  cmp     [rbp+rax*2+480h+var_462], 5Ch ; '\'
0x180031a62  jnz     loc_180031943
0x180031a68  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180031a70  cmp     rcx, 208h
0x180031a77  jnb     loc_180031BD5
0x180031a7d  mov     [rbp+rcx+480h+szVolumeName], r15w
0x180031a83  jmp     loc_180031943
0x180031a88  mov     edi, dword ptr [rbp+480h+uBytes]
0x180031a8b  xor     ecx, ecx; uFlags
0x180031a8d  mov     edx, edi; uBytes
0x180031a8f  call    cs:__imp_LocalAlloc
0x180031a96  nop     dword ptr [rax+rax+00h]
0x180031a9b  mov     r15, rax
0x180031a9e  test    rax, rax
0x180031aa1  jnz     short loc_180031AAD
0x180031aa3  mov     edi, 8
0x180031aa8  jmp     loc_1800319F2
0x180031aad  mov     r8, rdi; Size
0x180031ab0  mov     [rbp+480h+SizeInWords], r15
0x180031ab4  xor     edx, edx; Val
0x180031ab6  mov     rcx, r15; void *
0x180031ab9  call    memset_0
0x180031abe  lea     rax, [rbp+480h+uBytes]
0x180031ac2  mov     dword ptr [r15], 2
0x180031ac9  mov     [rsp+520h+var_500], rax
0x180031ace  mov     r9, r15
0x180031ad1  mov     rax, r13
0x180031ad4  mov     dword ptr [rbp+480h+uBytes], 0
0x180031adb  mov     r8d, edi
0x180031ade  mov     edx, 1
0x180031ae3  mov     rcx, rsi
0x180031ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031aeb  mov     edi, eax
0x180031aed  jmp     loc_1800319EA
0x180031af2  inc     rdx
0x180031af5  cmp     word ptr [rax+rdx*2], 0
0x180031afa  jnz     short loc_180031AF2
0x180031afc  mov     rcx, r9
0x180031aff  nop
0x180031b00  inc     rcx
0x180031b03  cmp     word ptr [r8+rcx*2], 0
0x180031b09  jnz     short loc_180031B00
0x180031b0b  inc     rdx
0x180031b0e  mov     eax, 2
0x180031b13  add     rcx, rdx
0x180031b16  mul     rcx
0x180031b19  mov     [rbp+480h+SizeInWords], rcx
0x180031b1d  cmovb   rax, r9
0x180031b21  mov     rcx, rax; Size
0x180031b24  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031b29  mov     rcx, [r12]; pv
0x180031b2d  mov     [r12], rax
0x180031b31  test    rcx, rcx
0x180031b34  jnz     loc_180031C3C
0x180031b3a  mov     r8, [r13+30h]; Source
0x180031b3e  mov     rdx, [rbp+480h+SizeInWords]; SizeInWords
0x180031b42  mov     rcx, [r12]; Destination
0x180031b46  call    cs:__imp_wcscpy_s
0x180031b4d  nop     dword ptr [rax+rax+00h]
0x180031b52  mov     r8, [r13+40h]; Source
0x180031b56  mov     rdx, [rbp+480h+SizeInWords]; SizeInWords
0x180031b5a  mov     rcx, [r12]; Destination
0x180031b5e  call    cs:__imp_wcscat_s
0x180031b65  nop     dword ptr [rax+rax+00h]
0x180031b6a  mov     rdx, [r12]
0x180031b6e  sub     rdx, rbx
0x180031b71  movzx   eax, word ptr [rbx]
0x180031b74  movzx   ecx, word ptr [rbx+rdx]
0x180031b78  sub     eax, ecx
0x180031b7a  jnz     short loc_180031B84
0x180031b7c  add     rbx, 2
0x180031b80  test    ecx, ecx
0x180031b82  jnz     short loc_180031B71
0x180031b84  test    eax, eax
0x180031b86  jz      loc_1800319F2
0x180031b8c  mov     rax, [rbp+480h+var_470]
0x180031b90  mov     dword ptr [rax], 1
0x180031b96  jmp     loc_1800319F2
0x180031b9b  mov     edi, 57h ; 'W'
0x180031ba0  jmp     loc_180031A20
0x180031ba5  mov     edi, 1
0x180031baa  jmp     loc_180031A20
0x180031baf  call    cs:__imp_GetLastError
0x180031bb6  nop     dword ptr [rax+rax+00h]
0x180031bbb  mov     edi, eax
0x180031bbd  jmp     loc_180031A1C
0x180031bc2  call    cs:__imp_GetLastError
0x180031bc9  nop     dword ptr [rax+rax+00h]
0x180031bce  mov     edi, eax
0x180031bd0  jmp     loc_180031A1C
0x180031bd5  call    __report_rangecheckfailure
0x180031bdb  call    cs:__imp_GetLastError
0x180031be2  nop     dword ptr [rax+rax+00h]
0x180031be7  mov     edi, eax
0x180031be9  jmp     loc_180031A1C
0x180031bee  mov     rcx, rsi; hObject
0x180031bf1  mov     edi, 8
0x180031bf6  call    cs:__imp_CloseHandle
0x180031bfd  nop     dword ptr [rax+rax+00h]
0x180031c02  jmp     loc_180031A20
0x180031c07  mov     r13, [rbp+480h+SizeInWords]
0x180031c0b  cmp     dword ptr [r13+4], 0
0x180031c10  jz      short loc_180031C4D
0x180031c12  lea     rax, [r13+8]
0x180031c16  test    rax, rax
0x180031c19  jz      short loc_180031C4D
0x180031c1b  mov     rax, [r13+30h]
0x180031c1f  test    rax, rax
0x180031c22  jz      short loc_180031C4D
0x180031c24  mov     r8, [r13+40h]
0x180031c28  test    r8, r8
0x180031c2b  jz      short loc_180031C4D
0x180031c2d  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180031c34  mov     rdx, r9
0x180031c37  jmp     loc_180031AF2
0x180031c3c  call    cs:__imp_CoTaskMemFree
0x180031c43  nop     dword ptr [rax+rax+00h]
0x180031c48  jmp     loc_180031B3A
0x180031c4d  mov     edi, 0C03A0015h
0x180031c52  jmp     loc_1800319F2
0x180031c57  call    cs:__imp_free
0x180031c5e  nop     dword ptr [rax+rax+00h]
0x180031c63  jmp     loc_180031A13
0x180031c68  mov     rcx, r15; hMem
0x180031c6b  call    cs:__imp_LocalFree
0x180031c72  nop     dword ptr [rax+rax+00h]
0x180031c77  jmp     loc_180031A1C
```
