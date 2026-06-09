# WusaSandBoxClean(ushort const *)

- ea: `0x140012b00`
- end: `0x14001301a`
- name: `?WusaSandBoxClean@@YAJPEBG@Z`
- size: `1306`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14000f674`
- `0x140012b00`

## callees

- `0x140001258`
- `0x140001264`
- `0x140001a63`
- `0x1400044e0`
- `0x14000e280`
- `0x140012b00`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140012ff1`
- `KERNEL32!LocalFree` at `0x140012ff1`
- `KERNEL32!FindFirstFileW` at `0x140012c63`
- `KERNEL32!FindFirstFileW` at `0x140012c63`
- `KERNEL32!FindClose` at `0x140012e56`
- `KERNEL32!FindClose` at `0x140012f43`
- `KERNEL32!FindClose` at `0x140012e56`
- `KERNEL32!FindClose` at `0x140012f43`
- `KERNEL32!lstrcmpW` at `0x140012cae`
- `KERNEL32!lstrcmpW` at `0x140012cc8`
- `KERNEL32!lstrcmpW` at `0x140012cae`
- `KERNEL32!lstrcmpW` at `0x140012cc8`
- `KERNEL32!DeleteFileW` at `0x140012d3a`
- `KERNEL32!DeleteFileW` at `0x140012d3a`
- `KERNEL32!MoveFileExW` at `0x140012d98`
- `KERNEL32!MoveFileExW` at `0x140012ef0`
- `KERNEL32!MoveFileExW` at `0x140012d98`
- `KERNEL32!MoveFileExW` at `0x140012ef0`
- `KERNEL32!RemoveDirectoryW` at `0x140012e92`
- `KERNEL32!RemoveDirectoryW` at `0x140012e92`
- `KERNEL32!GetLastError` at `0x140012c72`
- `KERNEL32!GetLastError` at `0x140012d48`
- `KERNEL32!GetLastError` at `0x140012da4`
- `KERNEL32!GetLastError` at `0x140012dec`
- `KERNEL32!GetLastError` at `0x140012e60`
- `KERNEL32!GetLastError` at `0x140012ea0`
- `KERNEL32!GetLastError` at `0x140012efc`
- `KERNEL32!GetLastError` at `0x140012f4d`
- `KERNEL32!GetLastError` at `0x140012c72`
- `KERNEL32!GetLastError` at `0x140012d48`
- `KERNEL32!GetLastError` at `0x140012da4`
- `KERNEL32!GetLastError` at `0x140012dec`
- `KERNEL32!GetLastError` at `0x140012e60`
- `KERNEL32!GetLastError` at `0x140012ea0`
- `KERNEL32!GetLastError` at `0x140012efc`
- `KERNEL32!GetLastError` at `0x140012f4d`
- `KERNEL32!FindNextFileW` at `0x140012dde`
- `KERNEL32!FindNextFileW` at `0x140012dde`

## string_xrefs

- `0x140012c3e`: `Failed to build a wildcard file name under the directory %S`
- `0x140012f98`: `Failed to get input parameter wszPath's length`
- `0x140012b8d`: `Error: RECURSIVE DELETE FROM ROOT?! %s`
- `0x140012d51`: `Warning: Failed to delete file %S, error code %u`
- `0x140012d77`: `Warning: Delaying delete until reboot`
- `0x140012ecf`: `Warning: Delaying delete until reboot`
- `0x140012dbb`: `Failed to delay delete the file %S`
- `0x140012f13`: `Failed to delay delete the file %S`
- `0x140012ea9`: `Warning: Failed to remove directory %S, error code: %u`

## pseudocode

```c
__int64 __fastcall WusaSandBoxClean(const unsigned __int16 *a1)
{
  const unsigned __int16 *v2; // rax
  __int64 v3; // rcx
  signed int v4; // edi
  unsigned int v5; // edx
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // r12
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // r15
  const unsigned __int16 *v10; // r9
  const char *v11; // r8
  __int64 v12; // rdx
  __int64 FirstFileW; // r13
  signed int LastError; // eax
  const char *v15; // r8
  __int64 v16; // rdx
  DWORD v17; // ebx
  signed int v18; // eax
  signed int v19; // eax
  DWORD v20; // eax
  DWORD v21; // ebx
  signed int v22; // eax
  DWORD v23; // eax
  HLOCAL v24; // rbx
  HLOCAL hMem; // [rsp+30h] [rbp-2A8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-298h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
  {
    v5 = -2147024809;
LABEL_63:
    v4 = v5;
    WusaLogDebugEventA(L"WusaSandBoxClean", 527, "Failed to get input parameter wszPath's length");
LABEL_64:
    hMem = 0;
    WusaGetErrorMessage(v4, (unsigned __int16 **)&hMem);
    v24 = hMem;
    WusaLogDebugEventA(L"WusaSandBoxClean", 649, "Exit with error code 0X%x (%ls)", v4, (const wchar_t *)hMem);
    if ( v24 )
      LocalFree(v24);
    return (unsigned int)v4;
  }
  v2 = a1;
  v3 = 0x7FFFFFFF;
  do
  {
    if ( !*v2 )
      break;
    ++v2;
    --v3;
  }
  while ( v3 );
  v4 = -2147024809;
  v5 = v3 == 0 ? 0x80070057 : 0;
  if ( !v3 )
    goto LABEL_63;
  if ( ((0x7FFFFFFF - v3) & (unsigned __int64)-(__int64)(v3 != 0)) <= 3 )
  {
    WusaLogDebugEventA(L"WusaSandBoxClean", 532, "Error: RECURSIVE DELETE FROM ROOT?! %s", a1);
    goto LABEL_64;
  }
  v6 = (unsigned __int16 *)operator new(0x208u);
  v7 = v6;
  if ( !v6 )
  {
    WusaLogDebugEventA(L"WusaSandBoxClean", 540, "Failed to allocate memory for file searching string");
    v4 = -2147024882;
    goto LABEL_64;
  }
  memset_0(v6, 0, 0x208u);
  v8 = (unsigned __int16 *)operator new(0x208u);
  v9 = v8;
  if ( !v8 )
  {
    WusaLogDebugEventA(L"WusaSandBoxClean", 544, "Failed to allocate memory for deletion target file string");
    v4 = -2147024882;
    goto LABEL_58;
  }
  memset_0(v8, 0, 0x208u);
  v4 = StringCchPrintfW(v7, 0x104u, L"%s\\*.*", a1);
  if ( v4 < 0 )
  {
    v10 = a1;
    v11 = "Failed to build a wildcard file name under the directory %S";
    v12 = 548;
LABEL_14:
    WusaLogDebugEventA(L"WusaSandBoxClean", v12, v11, v10);
    goto LABEL_58;
  }
  FirstFileW = (__int64)FindFirstFileW(v7, &FindFileData);
  if ( FirstFileW == -1 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v11 = "Failed: FindFirstFile() for %S";
    v10 = v7;
    if ( v4 >= 0 )
      v4 = -2147467259;
    v12 = 551;
    goto LABEL_14;
  }
  do
  {
    if ( lstrcmpW(FindFileData.cFileName, L".") && lstrcmpW(FindFileData.cFileName, L"..") )
    {
      v4 = StringCchPrintfW(v9, 0x104u, L"%s\\%s", a1, FindFileData.cFileName);
      if ( v4 < 0 )
      {
        WusaLogDebugEventA(L"WusaSandBoxClean", 566, "Failed to build a file name %S\\%S", a1, FindFileData.cFileName);
        goto LABEL_56;
      }
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      {
        v4 = WusaSandBoxClean(v9);
        if ( v4 < 0 )
        {
          v15 = "Failed to recursively call SandBoxClean for %S";
          v16 = 573;
          goto LABEL_27;
        }
      }
      else if ( !DeleteFileW(v9) )
      {
        v17 = GetLastError();
        WusaLogDebugEventA(L"WusaSandBoxClean", 580, "Warning: Failed to delete file %S, error code %u", v9, v17);
        if ( v17 - 2 > 1 )
        {
          WusaLogDebugEventA(L"WusaSandBoxClean", 583, "Warning: Delaying delete until reboot");
          if ( !MoveFileExW(v9, 0, 4u) )
          {
            v18 = GetLastError();
            v4 = v18;
            if ( v18 > 0 )
              v4 = (unsigned __int16)v18 | 0x80070000;
            v15 = "Failed to delay delete the file %S";
            v16 = 585;
            if ( v4 >= 0 )
              v4 = -2147467259;
LABEL_27:
            WusaLogDebugEventA(L"WusaSandBoxClean", v16, v15, v9);
LABEL_56:
            if ( !FindClose((HANDLE)FirstFileW) )
            {
              v23 = GetLastError();
              WusaLogDebugEventA(L"WusaSandBoxClean", 642, "Failed: %s, error code %u", "FindClose", v23);
            }
            goto LABEL_58;
          }
        }
      }
    }
  }
  while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
  v19 = GetLastError();
  if ( v19 != 18 )
  {
    v4 = v19 > 0 ? (unsigned __int16)v19 | 0x80070000 : v19;
    if ( v4 < 0 )
    {
      WusaLogDebugEventA(L"WusaSandBoxClean", 595, "Failed: FindNextFile()");
      goto LABEL_56;
    }
  }
  if ( FindClose((HANDLE)FirstFileW) )
  {
    FirstFileW = -1;
  }
  else
  {
    v20 = GetLastError();
    WusaLogDebugEventA(L"WusaSandBoxClean", 607, "Failed: %s, error code %u", "FindClose", v20);
  }
  if ( !RemoveDirectoryW(a1) )
  {
    v21 = GetLastError();
    WusaLogDebugEventA(L"WusaSandBoxClean", 625, "Warning: Failed to remove directory %S, error code: %u", a1, v21);
    if ( v21 - 2 > 1 )
    {
      WusaLogDebugEventA(L"WusaSandBoxClean", 629, "Warning: Delaying delete until reboot");
      if ( !MoveFileExW(a1, 0, 4u) )
      {
        v22 = GetLastError();
        v4 = v22;
        if ( v22 > 0 )
          v4 = (unsigned __int16)v22 | 0x80070000;
        if ( v4 >= 0 )
          v4 = -2147467259;
        WusaLogDebugEventA(L"WusaSandBoxClean", 631, "Failed to delay delete the file %S", a1);
      }
    }
  }
  if ( FirstFileW != -1 )
    goto LABEL_56;
LABEL_58:
  operator delete(v7);
  if ( v9 )
    operator delete(v9);
  if ( v4 < 0 )
    goto LABEL_64;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140012b00  push    rbx
0x140012b02  push    rbp
0x140012b03  push    rdi
0x140012b04  push    r12
0x140012b06  push    r13
0x140012b08  push    r15
0x140012b0a  sub     rsp, 2A8h
0x140012b11  mov     rax, cs:__security_cookie
0x140012b18  xor     rax, rsp
0x140012b1b  mov     [rsp+2D8h+var_48], rax
0x140012b23  mov     rbp, rcx
0x140012b26  xor     edx, edx; Val
0x140012b28  lea     rcx, [rsp+2D8h+FindFileData]; void *
0x140012b2d  mov     r8d, 250h; Size
0x140012b33  call    memset_0
0x140012b38  xor     ebx, ebx
0x140012b3a  test    rbp, rbp
0x140012b3d  jz      loc_140012F91
0x140012b43  mov     r8d, 7FFFFFFFh
0x140012b49  mov     rax, rbp
0x140012b4c  mov     ecx, r8d
0x140012b4f  cmp     [rax], bx
0x140012b52  jz      short loc_140012B5E
0x140012b54  add     rax, 2
0x140012b58  sub     rcx, 1
0x140012b5c  jnz     short loc_140012B4F
0x140012b5e  mov     rax, rcx
0x140012b61  mov     edi, 80070057h
0x140012b66  neg     rax
0x140012b69  mov     rax, rcx
0x140012b6c  sbb     edx, edx
0x140012b6e  sub     r8, rcx
0x140012b71  not     edx
0x140012b73  and     edx, edi
0x140012b75  neg     rax
0x140012b78  sbb     r9, r9
0x140012b7b  and     r9, r8
0x140012b7e  test    rcx, rcx
0x140012b81  jz      loc_140012F96
0x140012b87  cmp     r9, 3
0x140012b8b  ja      short loc_140012B9E
0x140012b8d  lea     r8, aErrorRecursive; "Error: RECURSIVE DELETE FROM ROOT?! %s"
0x140012b94  mov     edx, 214h
0x140012b99  jmp     loc_140012FA4
0x140012b9e  mov     edi, 208h
0x140012ba3  mov     ecx, edi; Size
0x140012ba5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012baa  mov     r12, rax
0x140012bad  test    rax, rax
0x140012bb0  jnz     short loc_140012BD2
0x140012bb2  lea     r8, aFailedToAlloca_15; "Failed to allocate memory for file sear"...
0x140012bb9  lea     edx, [rdi+14h]
0x140012bbc  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012bc3  call    WusaLogDebugEventA
0x140012bc8  mov     edi, 8007000Eh
0x140012bcd  jmp     loc_140012FB3
0x140012bd2  mov     r8, rdi; Size
0x140012bd5  xor     edx, edx; Val
0x140012bd7  mov     rcx, r12; void *
0x140012bda  call    memset_0
0x140012bdf  mov     rcx, rdi; Size
0x140012be2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012be7  mov     r15, rax
0x140012bea  test    rax, rax
0x140012bed  jnz     short loc_140012C11
0x140012bef  lea     r8, aFailedToAlloca_7; "Failed to allocate memory for deletion "...
0x140012bf6  mov     edx, 220h
0x140012bfb  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012c02  call    WusaLogDebugEventA
0x140012c07  mov     edi, 8007000Eh
0x140012c0c  jmp     loc_140012F76
0x140012c11  mov     r8, rdi; Size
0x140012c14  xor     edx, edx; Val
0x140012c16  mov     rcx, r15; void *
0x140012c19  call    memset_0
0x140012c1e  mov     r9, rbp
0x140012c21  lea     r8, aS; "%s\\*.*"
0x140012c28  mov     edx, 104h; unsigned __int64
0x140012c2d  mov     rcx, r12; unsigned __int16 *
0x140012c30  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140012c35  mov     edi, eax
0x140012c37  test    eax, eax
0x140012c39  jns     short loc_140012C5B
0x140012c3b  mov     r9, rbp
0x140012c3e  lea     r8, aFailedToBuildA_0; "Failed to build a wildcard file name un"...
0x140012c45  mov     edx, 224h
0x140012c4a  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012c51  call    WusaLogDebugEventA
0x140012c56  jmp     loc_140012F76
0x140012c5b  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x140012c60  mov     rcx, r12; lpFileName
0x140012c63  call    cs:__imp_FindFirstFileW
0x140012c69  mov     r13, rax
0x140012c6c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140012c70  jnz     short loc_140012CA2
0x140012c72  call    cs:__imp_GetLastError
0x140012c78  mov     edi, eax
0x140012c7a  test    eax, eax
0x140012c7c  jle     short loc_140012C87
0x140012c7e  movzx   edi, ax
0x140012c81  or      edi, 80070000h
0x140012c87  test    edi, edi
0x140012c89  lea     r8, aFailedFindfirs; "Failed: FindFirstFile() for %S"
0x140012c90  mov     eax, 80004005h
0x140012c95  mov     r9, r12
0x140012c98  cmovns  edi, eax
0x140012c9b  mov     edx, 227h
0x140012ca0  jmp     short loc_140012C4A
0x140012ca2  lea     rdx, asc_14001C378; "."
0x140012ca9  lea     rcx, [rsp+2D8h+FindFileData.cFileName]; lpString1
0x140012cae  call    cs:__imp_lstrcmpW
0x140012cb4  test    eax, eax
0x140012cb6  jz      loc_140012DD6
0x140012cbc  lea     rdx, asc_14001C37C; ".."
0x140012cc3  lea     rcx, [rsp+2D8h+FindFileData.cFileName]; lpString1
0x140012cc8  call    cs:__imp_lstrcmpW
0x140012cce  test    eax, eax
0x140012cd0  jz      loc_140012DD6
0x140012cd6  lea     rax, [rsp+2D8h+FindFileData.cFileName]
0x140012cdb  mov     r9, rbp
0x140012cde  lea     r8, aSS; "%s\\%s"
0x140012ce5  mov     [rsp+2D8h+var_2B8], rax
0x140012cea  mov     edx, 104h; unsigned __int64
0x140012cef  mov     rcx, r15; unsigned __int16 *
0x140012cf2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140012cf7  mov     edi, eax
0x140012cf9  test    eax, eax
0x140012cfb  js      loc_140012DFF
0x140012d01  test    byte ptr [rsp+2D8h+FindFileData.dwFileAttributes], 10h
0x140012d06  mov     rcx, r15; unsigned __int16 *
0x140012d09  jz      short loc_140012D3A
0x140012d0b  call    ?WusaSandBoxClean@@YAJPEBG@Z; WusaSandBoxClean(ushort const *)
0x140012d10  mov     edi, eax
0x140012d12  test    eax, eax
0x140012d14  jns     loc_140012DD6
0x140012d1a  lea     r8, aFailedToRecurs_0; "Failed to recursively call SandBoxClean"...
0x140012d21  mov     edx, 23Dh
0x140012d26  mov     r9, r15
0x140012d29  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012d30  call    WusaLogDebugEventA
0x140012d35  jmp     loc_140012F40
0x140012d3a  call    cs:__imp_DeleteFileW
0x140012d40  test    eax, eax
0x140012d42  jnz     loc_140012DD6
0x140012d48  call    cs:__imp_GetLastError
0x140012d4e  mov     r9, r15
0x140012d51  lea     r8, aWarningFailedT_0; "Warning: Failed to delete file %S, erro"...
0x140012d58  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012d5f  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x140012d63  mov     edx, 244h
0x140012d68  mov     ebx, eax
0x140012d6a  call    WusaLogDebugEventA
0x140012d6f  lea     eax, [rbx-2]
0x140012d72  cmp     eax, 1
0x140012d75  jbe     short loc_140012DD4
0x140012d77  lea     r8, aWarningDelayin; "Warning: Delaying delete until reboot"
0x140012d7e  mov     edx, 247h
0x140012d83  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012d8a  call    WusaLogDebugEventA
0x140012d8f  xor     edx, edx; lpNewFileName
0x140012d91  mov     rcx, r15; lpExistingFileName
0x140012d94  lea     r8d, [rdx+4]; dwFlags
0x140012d98  call    cs:__imp_MoveFileExW
0x140012d9e  xor     ebx, ebx
0x140012da0  test    eax, eax
0x140012da2  jnz     short loc_140012DD6
0x140012da4  call    cs:__imp_GetLastError
0x140012daa  mov     edi, eax
0x140012dac  test    eax, eax
0x140012dae  jle     short loc_140012DB9
0x140012db0  movzx   edi, ax
0x140012db3  or      edi, 80070000h
0x140012db9  test    edi, edi
0x140012dbb  lea     r8, aFailedToDelayD; "Failed to delay delete the file %S"
0x140012dc2  mov     eax, 80004005h
0x140012dc7  mov     edx, 249h
0x140012dcc  cmovns  edi, eax
0x140012dcf  jmp     loc_140012D26
0x140012dd4  xor     ebx, ebx
0x140012dd6  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x140012ddb  mov     rcx, r13; hFindFile
0x140012dde  call    cs:__imp_FindNextFileW
0x140012de4  test    eax, eax
0x140012de6  jnz     loc_140012CA2
0x140012dec  call    cs:__imp_GetLastError
0x140012df2  cmp     eax, 12h
0x140012df5  jz      short loc_140012E53
0x140012df7  test    eax, eax
0x140012df9  jg      short loc_140012E29
0x140012dfb  mov     edi, eax
0x140012dfd  jmp     short loc_140012E32
0x140012dff  lea     rax, [rsp+2D8h+FindFileData.cFileName]
0x140012e04  mov     r9, rbp
0x140012e07  lea     r8, aFailedToBuildA_1; "Failed to build a file name %S\\%S"
0x140012e0e  mov     [rsp+2D8h+var_2B8], rax
0x140012e13  mov     edx, 236h
0x140012e18  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012e1f  call    WusaLogDebugEventA
0x140012e24  jmp     loc_140012F40
0x140012e29  movzx   edi, ax
0x140012e2c  or      edi, 80070000h
0x140012e32  test    edi, edi
0x140012e34  jns     short loc_140012E53
0x140012e36  lea     r8, aFailedFindnext; "Failed: FindNextFile()"
0x140012e3d  mov     edx, 253h
0x140012e42  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012e49  call    WusaLogDebugEventA
0x140012e4e  jmp     loc_140012F40
0x140012e53  mov     rcx, r13; hFindFile
0x140012e56  call    cs:__imp_FindClose
0x140012e5c  test    eax, eax
0x140012e5e  jnz     short loc_140012E8B
0x140012e60  call    cs:__imp_GetLastError
0x140012e66  lea     r9, aFindclose; "FindClose"
0x140012e6d  mov     edx, 25Fh
0x140012e72  lea     r8, aFailedSErrorCo; "Failed: %s, error code %u"
0x140012e79  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x140012e7d  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012e84  call    WusaLogDebugEventA
0x140012e89  jmp     short loc_140012E8F
0x140012e8b  or      r13, 0FFFFFFFFFFFFFFFFh
0x140012e8f  mov     rcx, rbp; lpPathName
0x140012e92  call    cs:__imp_RemoveDirectoryW
0x140012e98  test    eax, eax
0x140012e9a  jnz     loc_140012F3A
0x140012ea0  call    cs:__imp_GetLastError
0x140012ea6  mov     r9, rbp
0x140012ea9  lea     r8, aWarningFailedT; "Warning: Failed to remove directory %S,"...
0x140012eb0  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012eb7  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x140012ebb  mov     edx, 271h
0x140012ec0  mov     ebx, eax
0x140012ec2  call    WusaLogDebugEventA
0x140012ec7  lea     eax, [rbx-2]
0x140012eca  cmp     eax, 1
0x140012ecd  jbe     short loc_140012F38
0x140012ecf  lea     r8, aWarningDelayin; "Warning: Delaying delete until reboot"
0x140012ed6  mov     edx, 275h
0x140012edb  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012ee2  call    WusaLogDebugEventA
0x140012ee7  xor     edx, edx; lpNewFileName
0x140012ee9  mov     rcx, rbp; lpExistingFileName
0x140012eec  lea     r8d, [rdx+4]; dwFlags
0x140012ef0  call    cs:__imp_MoveFileExW
0x140012ef6  xor     ebx, ebx
0x140012ef8  test    eax, eax
0x140012efa  jnz     short loc_140012F3A
0x140012efc  call    cs:__imp_GetLastError
0x140012f02  mov     edi, eax
0x140012f04  test    eax, eax
0x140012f06  jle     short loc_140012F11
0x140012f08  movzx   edi, ax
0x140012f0b  or      edi, 80070000h
0x140012f11  test    edi, edi
0x140012f13  lea     r8, aFailedToDelayD; "Failed to delay delete the file %S"
0x140012f1a  mov     eax, 80004005h
0x140012f1f  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012f26  mov     r9, rbp
0x140012f29  mov     edx, 277h
0x140012f2e  cmovns  edi, eax
0x140012f31  call    WusaLogDebugEventA
0x140012f36  jmp     short loc_140012F3A
0x140012f38  xor     ebx, ebx
0x140012f3a  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x140012f3e  jz      short loc_140012F76
0x140012f40  mov     rcx, r13; hFindFile
0x140012f43  call    cs:__imp_FindClose
0x140012f49  test    eax, eax
0x140012f4b  jnz     short loc_140012F76
0x140012f4d  call    cs:__imp_GetLastError
0x140012f53  lea     r9, aFindclose; "FindClose"
0x140012f5a  mov     edx, 282h
0x140012f5f  lea     r8, aFailedSErrorCo; "Failed: %s, error code %u"
0x140012f66  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x140012f6a  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012f71  call    WusaLogDebugEventA
0x140012f76  mov     rcx, r12; Block
0x140012f79  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140012f7e  test    r15, r15
0x140012f81  jz      short loc_140012F8B
0x140012f83  mov     rcx, r15; Block
0x140012f86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140012f8b  test    edi, edi
0x140012f8d  jns     short loc_140012FF7
0x140012f8f  jmp     short loc_140012FB3
0x140012f91  mov     edx, 80070057h
0x140012f96  mov     edi, edx
0x140012f98  lea     r8, aFailedToGetInp; "Failed to get input parameter wszPath's"...
0x140012f9f  mov     edx, 20Fh
0x140012fa4  mov     r9, rbp
0x140012fa7  lea     rcx, aWusasandboxcle; "WusaSandBoxClean"
0x140012fae  call    WusaLogDebugEventA
0x140012fb3  lea     rdx, [rsp+2D8h+hMem]; unsigned __int16 **
0x140012fb8  mov     [rsp+2D8h+hMem], rbx
0x140012fbd  mov     ecx, edi; dwMessageId
0x140012fbf  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x140012fc4  mov     rbx, [rsp+2D8h+hMem]
0x140012fc9  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140012fd0  mov     r9d, edi
0x140012fd3  mov     [rsp+2D8h+var_2B8], rbx
  ... truncated ...
```
