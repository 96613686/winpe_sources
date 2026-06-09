# extractIndexedItem

- ea: `0x18002f584`
- end: `0x18002febd`
- name: `extractIndexedItem`
- size: `2361`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, reparse_path`

## callers

- `0x18000fe10`

## callees

- `0x180005464`
- `0x1800054dc`
- `0x1800056f8`
- `0x180007df0`
- `0x180015e80`
- `0x180016900`
- `0x180016d80`
- `0x1800170f0`
- `0x180017600`
- `0x1800177f0`
- `0x180017ba0`
- `0x180018170`
- `0x1800183f0`
- `0x1800184a0`
- `0x1800188b8`
- `0x180018950`
- `0x18001e360`
- `0x1800210f0`
- `0x18002115c`
- `0x180023df4`
- `0x18002555c`
- `0x1800255d8`
- `0x18002b5e4`
- `0x18002f584`
- `0x180036f50`
- `0x18003791c`
- `0x180037958`
- `0x18006aae8`
- `0x18006e9a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002f849`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002f849`
- `SHLWAPI!PathCanonicalizeW` at `0x18002f73d`
- `SHLWAPI!PathCanonicalizeW` at `0x18002f73d`
- `SHLWAPI!PathIsRelativeW` at `0x18002f721`
- `SHLWAPI!PathIsRelativeW` at `0x18002f721`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f99a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f99a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f61e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f61e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f9fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f9fc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f9ed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f9ed`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002f93a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002f93a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002f85f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002f85f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002fbc8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002fd3a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002fbc8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002fd3a`
- `KERNEL32!lstrcmpiW` at `0x18002f759`
- `KERNEL32!lstrcmpiW` at `0x18002f985`
- `KERNEL32!lstrcmpiW` at `0x18002fc3f`
- `KERNEL32!lstrcmpiW` at `0x18002f759`
- `KERNEL32!lstrcmpiW` at `0x18002f985`
- `KERNEL32!lstrcmpiW` at `0x18002fc3f`
- `KERNEL32!lstrlenW` at `0x18002f8d9`
- `KERNEL32!lstrlenW` at `0x18002f8f4`
- `KERNEL32!lstrlenW` at `0x18002f961`
- `KERNEL32!lstrlenW` at `0x18002f970`
- `KERNEL32!lstrlenW` at `0x18002fe2a`
- `KERNEL32!lstrlenW` at `0x18002fe38`
- `KERNEL32!lstrlenW` at `0x18002f8d9`
- `KERNEL32!lstrlenW` at `0x18002f8f4`
- `KERNEL32!lstrlenW` at `0x18002f961`
- `KERNEL32!lstrlenW` at `0x18002f970`
- `KERNEL32!lstrlenW` at `0x18002fe2a`
- `KERNEL32!lstrlenW` at `0x18002fe38`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall extractIndexedItem(__int64 a1)
{
  _QWORD *Value; // rax
  __int64 v3; // rdx
  _QWORD *v4; // rdi
  __int64 result; // rax
  __int64 v6; // rsi
  int v7; // ebx
  wchar_t *v8; // r15
  __int16 *v9; // rax
  __int16 v10; // cx
  const wchar_t *v11; // r8
  int v12; // ebx
  wchar_t *v13; // rax
  wchar_t *v14; // rbx
  wchar_t *v15; // rdx
  wchar_t i; // ax
  int v17; // ebx
  unsigned int v18; // ebx
  DWORD LastError; // eax
  unsigned int v20; // ecx
  HANDLE FileW; // rax
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  int v29; // r13d
  int v30; // edx
  unsigned int v31; // r9d
  int v32; // ecx
  __int64 v33; // rdx
  int MVFromHDName; // eax
  __int64 v35; // rdx
  __int64 v36; // rax
  int v37; // eax
  void *v38; // rcx
  void *v39; // rcx
  __int64 v40; // rax
  wchar_t *v41; // r10
  wchar_t *v42; // r8
  size_t v43; // rdx
  unsigned int v44; // r11d
  int v45; // r8d
  int Member; // eax
  void *v47; // rcx
  void *v48; // rcx
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v50[260]; // [rsp+60h] [rbp-A0h] BYREF
  int v51; // [rsp+268h] [rbp+168h]
  int v52; // [rsp+26Ch] [rbp+16Ch]
  int v53; // [rsp+270h] [rbp+170h]
  wchar_t v54[262]; // [rsp+274h] [rbp+174h] BYREF
  _BYTE v55[102]; // [rsp+480h] [rbp+380h] BYREF
  __int16 v56; // [rsp+4E6h] [rbp+3E6h]
  WCHAR String[264]; // [rsp+1510h] [rbp+1410h] BYREF
  WCHAR pszSrc[264]; // [rsp+1720h] [rbp+1620h] BYREF
  wchar_t pszDest; // [rsp+1930h] [rbp+1830h] BYREF
  _BYTE v60[526]; // [rsp+1932h] [rbp+1832h] BYREF
  wchar_t String2[264]; // [rsp+1B40h] [rbp+1A40h] BYREF
  WCHAR pszBuf[2048]; // [rsp+1D50h] [rbp+1C50h] BYREF

  pszDest = 0;
  memset_0(v60, 0, 0x206u);
  memset_0(v55, 0, 0x1086u);
  memset_0(v50, 0, 0x41Cu);
  NumberOfBytesRead = 0;
  memset_0(pszBuf, 0, sizeof(pszBuf));
  Value = TlsGetValue(dwUnZIPTlsIndex);
  v4 = Value;
  if ( !Value )
    return 4;
  Value[402] = 0;
  if ( !*((_DWORD *)Value + 4) )
  {
    RemoveDoubleQuotes(&pszDest, *(_QWORD *)(a1 + 28));
    if ( !(unsigned int)zip_HasTrailingCharacter(&pszDest) )
      StringCchCatW(&pszDest, 0x104u, L"\\");
  }
  v6 = a1 + 116;
  if ( !*((_DWORD *)v4 + 20) )
  {
    v56 = 0;
    *(_QWORD *)v6 = v55;
    if ( !*((_DWORD *)v4 + 20) )
    {
      if ( (unsigned int)GetIndexedZipInfo(a1, v3) )
      {
        v7 = 47;
        goto LABEL_121;
      }
    }
  }
  v8 = (wchar_t *)(v4 + 271);
  StringCchCopyW((STRSAFE_LPWSTR)v4 + 1084, 0x104u, &pszDest);
  v6 = a1 + 116;
  v9 = (__int16 *)(*(_QWORD *)(a1 + 116) + 102LL);
  v10 = *v9;
  if ( *v9 )
  {
    do
    {
      if ( v10 == 47 )
      {
        *v9 = 92;
      }
      else if ( v10 == 58 && !*(_QWORD *)(a1 + 36) )
      {
        *v9 = 95;
      }
      v9 = (__int16 *)zip_charnext(v9);
      v10 = *v9;
    }
    while ( *v9 );
    v8 = (wchar_t *)(v4 + 271);
  }
  if ( !PathIsRelativeW((LPCWSTR)(*(_QWORD *)v6 + 102LL))
    || !PathCanonicalizeW(pszBuf, (LPCWSTR)(*(_QWORD *)v6 + 102LL))
    || lstrcmpiW(pszBuf, (LPCWSTR)(*(_QWORD *)v6 + 102LL)) )
  {
    result = 48;
    goto LABEL_127;
  }
  StringCchCopyW(v54, 0x104u, (STRSAFE_LPCWSTR)(*(_QWORD *)v6 + 102LL));
  v11 = *(const wchar_t **)(a1 + 36);
  if ( !v11 )
    v11 = (const wchar_t *)(*(_QWORD *)v6 + 102LL);
  StringCchCatW(v8, 0x104u, v11);
  v51 = *((unsigned __int16 *)v4 + 2213);
  v52 = *((unsigned __int16 *)v4 + 2212);
  v53 = *(_DWORD *)(*(_QWORD *)v6 + 24LL);
  StringCchCopyW(v50, 0x104u, v8);
  if ( !*((_DWORD *)v4 + 4) )
  {
    zip_splitpath(v8, &pszDest, 0x104u, String2, 0x104u, 0, 0, 0, 0);
    zip_makepath(pszSrc);
    StringCchCopyW(String2, 0x104u, pszSrc);
    v12 = 0;
    while ( 1 )
    {
      v13 = wcsrchr(pszSrc, 0x5Cu);
      if ( !v13 )
        break;
      *v13 = 0;
      if ( GetFileAttributesW(pszSrc) != -1 )
      {
        StringCchCopyW(String, 0x104u, pszSrc);
        v12 = 1;
      }
      if ( v12 )
        goto LABEL_31;
    }
    StringCchCopyW(String, 0x104u, pszSrc);
LABEL_31:
    StringCchCatW(String, 0x104u, L"\\");
    StringCchCopyW(pszSrc, 0x104u, String2);
    while ( 1 )
    {
      v17 = lstrlenW(String);
      if ( v17 >= lstrlenW(pszSrc) )
        break;
      v14 = &String[lstrlenW(String)];
      v15 = &pszSrc[lstrlenW(String)];
      for ( i = *v15; *v15; i = *v15 )
      {
        if ( i == 92 )
          break;
        ++v15;
        *v14++ = i;
      }
      *v14 = 0;
      if ( !CreateDirectoryW(String, 0) )
      {
        *(_QWORD *)v6 = 0;
        LastError = GetLastError();
        v20 = 28;
        if ( LastError == 206 )
          return 51;
        return v20;
      }
      StringCchCatW(String, 0x104u, L"\\");
    }
    if ( !lstrcmpiW((LPCWSTR)v4 + 44, v8) )
    {
      v18 = 49;
LABEL_48:
      result = v18;
LABEL_127:
      *(_QWORD *)v6 = 0;
      return result;
    }
    StringCchCopyW((STRSAFE_LPWSTR)v4 + 1344, 0x104u, v8);
    FileW = CreateFileW(v8, 0x80000000, 3u, 0, 3u, 0x80000080, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      CloseHandle(FileW);
      if ( !*((_DWORD *)v4 + 1) )
      {
        v18 = 52;
        goto LABEL_48;
      }
    }
  }
  v22 = initialize((_WORD *)v4 + 44);
  if ( v22 )
  {
    v18 = v22;
    goto LABEL_48;
  }
  if ( !OpenCurrentZIP(v24, v23) )
    return 29;
  v7 = 0;
  if ( !*((_DWORD *)v4 + 20) )
  {
    v26 = Process_End_Directory();
    *((_DWORD *)v4 + 812) = v26;
    v25 = v26;
    if ( v26 )
      v7 = v26;
    if ( *(_DWORD *)(a1 + 24) <= *(_DWORD *)((char *)v4 + 4358) - 1 )
    {
      if ( !v7 )
      {
        if ( !*((_DWORD *)v4 + 1102) )
        {
          v4[404] = 0;
          v27 = Process_Central_Directory();
          v25 = v27;
          *((_DWORD *)v4 + 812) = v27;
        }
        if ( !(_DWORD)v25 )
        {
          v4[404] = *(int *)(a1 + 24);
          v28 = Process_Central_Directory();
          v25 = v28;
          *((_DWORD *)v4 + 812) = v28;
        }
      }
    }
    else
    {
      v7 = 25;
    }
    if ( (int)v25 > v7 )
      v7 = v25;
  }
  *((_DWORD *)v4 + 1201) = 0;
  if ( (*((_BYTE *)v4 + 4420) & 1) != 0 )
    *((_DWORD *)v4 + 1201) = 1;
  if ( *((_WORD *)v4 + 2211) > 0x13u )
  {
    v7 = 42;
    goto LABEL_120;
  }
  if ( v7 )
    goto LABEL_120;
  v29 = 1;
  while ( *((_DWORD *)v4 + 1199) && *((unsigned __int16 *)v4 + 2223) != *((_DWORD *)v4 + 1200) )
  {
    CloseCurrentZIP(v25);
    v30 = *(_DWORD *)((char *)v4 + 4342);
    v31 = *((unsigned __int16 *)v4 + 2223) + 1;
    v32 = *((_DWORD *)v4 + 3);
    if ( v30 == -1 )
    {
      v33 = 0;
      if ( !v32 )
      {
        MVFromHDName = MsgCB(*(_QWORD *)(a1 + 124), 0, 1, v31, 0);
        goto LABEL_77;
      }
LABEL_75:
      MVFromHDName = duzMakeMVFromHDName(v31, v33, v4);
      goto LABEL_77;
    }
    v33 = (unsigned int)(v30 + 1);
    if ( v32 )
      goto LABEL_75;
    MVFromHDName = MsgCB(*(_QWORD *)(a1 + 124), 1, 1, v31, v33);
LABEL_77:
    if ( MVFromHDName != 1 )
    {
      v7 = 48;
LABEL_101:
      CloseCurrentZIP(v25);
      goto LABEL_121;
    }
    if ( *((_DWORD *)v4 + 3) )
      v29 = 0;
    if ( !(unsigned int)CheckCurrentZIP()
      && OpenCurrentZIP(v25, v35)
      && (v36 = duzLLGetLDOffset(v4),
          DZSetFilePointer(v4[405], v36, 0),
          ReadFile((HANDLE)v4[405], v4 + 494, 0x1Eu, &NumberOfBytesRead, 0))
      && NumberOfBytesRead == 30
      && *((_DWORD *)v4 + 988) == 67324752 )
    {
      if ( (unsigned int)GetCDirFilename((HGLOBAL)v4[597], (HGLOBAL)v4[595], *(_DWORD *)(a1 + 24)) )
      {
        StringCchCopyW(String2, 0x104u, (STRSAFE_LPCWSTR)v4 + 35828);
        if ( (unsigned int)get_filename_and_ldir_extra(v4) )
        {
          if ( !lstrcmpiW((LPCWSTR)v4 + 35828, String2) )
          {
            v29 = 0;
            *((_DWORD *)v4 + 1200) = *((unsigned __int16 *)v4 + 2223);
            v7 = 0;
          }
        }
        else
        {
          v7 = 3;
        }
      }
      else
      {
        v7 = 3;
      }
    }
    else
    {
      v7 = 29;
    }
    if ( !v29 )
      goto LABEL_93;
  }
  v40 = duzLLGetLDOffset(v4);
  DZSetFilePointer(v4[405], v40, 0);
  if ( !ReadFile((HANDLE)v4[405], v4 + 494, 0x1Eu, &NumberOfBytesRead, 0) || !NumberOfBytesRead )
    v7 = 3;
  if ( *((_DWORD *)v4 + 988) != 67324752 )
  {
    v7 = 3;
    CloseCurrentZIP(v25);
    goto LABEL_121;
  }
  if ( !v7 && !(unsigned int)get_filename_and_ldir_extra(v4) )
  {
    v7 = 3;
    goto LABEL_101;
  }
LABEL_93:
  CloseCurrentZIP(v25);
  if ( v7 )
    goto LABEL_121;
  v37 = OpenArchive((LPCWSTR)v4 + 44);
  *((_DWORD *)v4 + 812) = v37;
  if ( v37 )
  {
    *(_QWORD *)v6 = 0;
    v38 = (void *)v4[8807];
    if ( v38 )
    {
      free(v38);
      v4[8807] = 0;
    }
    v39 = (void *)v4[8954];
    if ( v39 )
    {
      v4[8956] = 0;
      free(v39);
      v4[8954] = 0;
    }
    return *((unsigned int *)v4 + 812);
  }
  v41 = (wchar_t *)(v4 + 408);
  v42 = v8;
  if ( *((_DWORD *)v4 + 4) )
  {
    v43 = 260;
  }
  else
  {
    StringCchCopyW(v50, 0x104u, v8);
    v42 = v50;
    v43 = v44;
  }
  StringCchCopyW(v41, v43, v42);
  *((_DWORD *)v4 + 802) = *(_DWORD *)(*(_QWORD *)v6 + 24LL) & 0x27;
  if ( (unsigned int)zip_HasTrailingCharacter(v8) )
  {
    *((_DWORD *)v4 + 802) = v45 | 0x10;
    if ( lstrlenW(v8) > 1 )
    {
      *((_WORD *)v4 + lstrlenW(v8) + 1083) = 0;
      set_file_time_and_close();
    }
  }
  else
  {
    Member = ExtractMember((LPCWSTR)v4 + 1344, (_DWORD *)(a1 + 132));
    *((_DWORD *)v4 + 812) = Member;
    v7 = Member;
    if ( Member > 0 && *((_DWORD *)v4 + 1201) && Member == 44 )
    {
      *(_QWORD *)v6 = 0;
      v7 = 49;
    }
  }
LABEL_120:
  CloseArchive();
LABEL_121:
  *(_QWORD *)v6 = 0;
  v47 = (void *)v4[8807];
  if ( v47 )
  {
    free(v47);
    v4[8807] = 0;
  }
  v48 = (void *)v4[8954];
  if ( v48 )
  {
    v4[8956] = 0;
    free(v48);
    v4[8954] = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002f584  push    rbp
0x18002f586  push    rbx
0x18002f587  push    rsi
0x18002f588  push    rdi
0x18002f589  push    r12
0x18002f58b  push    r13
0x18002f58d  push    r14
0x18002f58f  push    r15
0x18002f591  lea     rbp, [rsp-2C68h]
0x18002f599  mov     eax, 2D68h
0x18002f59e  call    _alloca_probe
0x18002f5a3  sub     rsp, rax
0x18002f5a6  mov     rax, cs:__security_cookie
0x18002f5ad  xor     rax, rsp
0x18002f5b0  mov     [rbp+2CA0h+var_50], rax
0x18002f5b7  mov     r14, rcx
0x18002f5ba  xor     r12d, r12d
0x18002f5bd  lea     rcx, [rbp+2CA0h+var_146E]; void *
0x18002f5c4  mov     [rbp+2CA0h+pszDest], r12w
0x18002f5cc  xor     edx, edx; Val
0x18002f5ce  mov     r8d, 206h; Size
0x18002f5d4  call    memset_0
0x18002f5d9  xor     edx, edx; Val
0x18002f5db  lea     rcx, [rbp+2CA0h+var_2920]; void *
0x18002f5e2  mov     r8d, 1086h; Size
0x18002f5e8  call    memset_0
0x18002f5ed  xor     edx, edx; Val
0x18002f5ef  lea     rcx, [rsp+2DA0h+var_2D40]; void *
0x18002f5f4  mov     r8d, 41Ch; Size
0x18002f5fa  call    memset_0
0x18002f5ff  xor     edx, edx; Val
0x18002f601  mov     [rsp+2DA0h+NumberOfBytesRead], r12d
0x18002f606  mov     r8d, 1000h; Size
0x18002f60c  lea     rcx, [rbp+2CA0h+pszBuf]; void *
0x18002f613  call    memset_0
0x18002f618  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x18002f61e  call    cs:__imp_TlsGetValue
0x18002f624  mov     rdi, rax
0x18002f627  test    rax, rax
0x18002f62a  jnz     short loc_18002F634
0x18002f62c  lea     eax, [rdi+4]
0x18002f62f  jmp     loc_18002FE9A
0x18002f634  mov     r13d, 104h
0x18002f63a  mov     [rax+0C90h], r12
0x18002f641  cmp     [rax+10h], r12d
0x18002f645  jnz     short loc_18002F67D
0x18002f647  mov     rdx, [r14+1Ch]
0x18002f64b  lea     rcx, [rbp+2CA0h+pszDest]
0x18002f652  call    RemoveDoubleQuotes
0x18002f657  lea     rcx, [rbp+2CA0h+pszDest]
0x18002f65e  call    zip_HasTrailingCharacter
0x18002f663  test    eax, eax
0x18002f665  jnz     short loc_18002F67D
0x18002f667  lea     r8, asc_180078AAC; "\\"
0x18002f66e  mov     edx, r13d; cchDest
0x18002f671  lea     rcx, [rbp+2CA0h+pszDest]; pszDest
0x18002f678  call    StringCchCatW
0x18002f67d  lea     rsi, [r14+74h]
0x18002f681  cmp     [rdi+50h], r12d
0x18002f685  jnz     short loc_18002F6B5
0x18002f687  lea     rax, [rbp+2CA0h+var_2920]
0x18002f68e  mov     [rbp+2CA0h+var_28BA], r12w
0x18002f696  mov     [rsi], rax
0x18002f699  cmp     [rdi+50h], r12d
0x18002f69d  jnz     short loc_18002F6B5
0x18002f69f  mov     rcx, r14
0x18002f6a2  call    GetIndexedZipInfo
0x18002f6a7  test    eax, eax
0x18002f6a9  jz      short loc_18002F6B5
0x18002f6ab  mov     ebx, 2Fh ; '/'
0x18002f6b0  jmp     loc_18002FE54
0x18002f6b5  lea     r15, [rdi+878h]
0x18002f6bc  mov     rdx, r13; cchDest
0x18002f6bf  mov     rcx, r15; pszDest
0x18002f6c2  lea     r8, [rbp+2CA0h+pszDest]; pszSrc
0x18002f6c9  call    StringCchCopyW
0x18002f6ce  lea     rsi, [r14+74h]
0x18002f6d2  mov     rax, [rsi]
0x18002f6d5  add     rax, 66h ; 'f'
0x18002f6d9  movzx   ecx, word ptr [rax]
0x18002f6dc  test    cx, cx
0x18002f6df  jz      short loc_18002F71A
0x18002f6e1  mov     ebx, 2Fh ; '/'
0x18002f6e6  cmp     cx, bx
0x18002f6e9  jnz     short loc_18002F6F2
0x18002f6eb  mov     word ptr [rax], 5Ch ; '\'
0x18002f6f0  jmp     short loc_18002F703
0x18002f6f2  cmp     cx, 3Ah ; ':'
0x18002f6f6  jnz     short loc_18002F703
0x18002f6f8  cmp     [r14+24h], r12
0x18002f6fc  jnz     short loc_18002F703
0x18002f6fe  mov     word ptr [rax], 5Fh ; '_'
0x18002f703  mov     rcx, rax
0x18002f706  call    zip_charnext
0x18002f70b  movzx   ecx, word ptr [rax]
0x18002f70e  test    cx, cx
0x18002f711  jnz     short loc_18002F6E6
0x18002f713  lea     r15, [rdi+878h]
0x18002f71a  mov     rcx, [rsi]
0x18002f71d  add     rcx, 66h ; 'f'; pszPath
0x18002f721  call    cs:__imp_PathIsRelativeW
0x18002f727  test    eax, eax
0x18002f729  jz      loc_18002FE92
0x18002f72f  mov     rdx, [rsi]
0x18002f732  lea     rcx, [rbp+2CA0h+pszBuf]; pszBuf
0x18002f739  add     rdx, 66h ; 'f'; pszPath
0x18002f73d  call    cs:__imp_PathCanonicalizeW
0x18002f743  test    eax, eax
0x18002f745  jz      loc_18002FE92
0x18002f74b  mov     rdx, [rsi]
0x18002f74e  lea     rcx, [rbp+2CA0h+pszBuf]; lpString1
0x18002f755  add     rdx, 66h ; 'f'; lpString2
0x18002f759  call    cs:__imp_lstrcmpiW
0x18002f75f  test    eax, eax
0x18002f761  jnz     loc_18002FE92
0x18002f767  mov     r8, [rsi]
0x18002f76a  lea     rcx, [rbp+2CA0h+var_2B2C]; pszDest
0x18002f771  add     r8, 66h ; 'f'; pszSrc
0x18002f775  mov     rdx, r13; cchDest
0x18002f778  call    StringCchCopyW
0x18002f77d  mov     r8, [r14+24h]
0x18002f781  test    r8, r8
0x18002f784  jnz     short loc_18002F78D
0x18002f786  mov     r8, [rsi]
0x18002f789  add     r8, 66h ; 'f'; pszSrc
0x18002f78d  mov     rdx, r13; cchDest
0x18002f790  mov     rcx, r15; pszDest
0x18002f793  call    StringCchCatW
0x18002f798  movzx   eax, word ptr [rdi+114Ah]
0x18002f79f  mov     r8, r15; pszSrc
0x18002f7a2  mov     [rbp+2CA0h+var_2B38], eax
0x18002f7a8  mov     rdx, r13; cchDest
0x18002f7ab  movzx   eax, word ptr [rdi+1148h]
0x18002f7b2  mov     [rbp+2CA0h+var_2B34], eax
0x18002f7b8  mov     rax, [rsi]
0x18002f7bb  mov     ecx, [rax+18h]
0x18002f7be  mov     [rbp+2CA0h+var_2B30], ecx
0x18002f7c4  lea     rcx, [rsp+2DA0h+var_2D40]; pszDest
0x18002f7c9  call    StringCchCopyW
0x18002f7ce  cmp     [rdi+10h], r12d
0x18002f7d2  jnz     loc_18002FA0F
0x18002f7d8  mov     [rsp+2DA0h+var_2D60], r12d; int
0x18002f7dd  lea     r9, [rbp+2CA0h+String2]
0x18002f7e4  mov     [rsp+2DA0h+var_2D68], r12; __int64
0x18002f7e9  lea     rdx, [rbp+2CA0h+pszDest]
0x18002f7f0  mov     dword ptr [rsp+2DA0h+hTemplateFile], r12d; int
0x18002f7f5  mov     r8d, r13d
0x18002f7f8  mov     qword ptr [rsp+2DA0h+dwFlagsAndAttributes], r12; __int64
0x18002f7fd  mov     rcx, r15; Str
0x18002f800  mov     [rsp+2DA0h+dwCreationDisposition], r13d; int
0x18002f805  call    zip_splitpath
0x18002f80a  lea     r9, [rbp+2CA0h+String2]
0x18002f811  lea     r8, [rbp+2CA0h+pszDest]
0x18002f818  lea     rcx, [rbp+2CA0h+pszSrc]; pszDest
0x18002f81f  call    zip_makepath
0x18002f824  lea     r8, [rbp+2CA0h+pszSrc]; pszSrc
0x18002f82b  mov     rdx, r13; cchDest
0x18002f82e  lea     rcx, [rbp+2CA0h+String2]; pszDest
0x18002f835  call    StringCchCopyW
0x18002f83a  mov     ebx, r12d
0x18002f83d  mov     edx, 5Ch ; '\'; Ch
0x18002f842  lea     rcx, [rbp+2CA0h+pszSrc]; Str
0x18002f849  call    cs:__imp_wcsrchr
0x18002f84f  test    rax, rax
0x18002f852  jz      short loc_18002F88B
0x18002f854  lea     rcx, [rbp+2CA0h+pszSrc]; lpFileName
0x18002f85b  mov     [rax], r12w
0x18002f85f  call    cs:__imp_GetFileAttributesW
0x18002f865  cmp     eax, 0FFFFFFFFh
0x18002f868  jz      short loc_18002F885
0x18002f86a  lea     r8, [rbp+2CA0h+pszSrc]; pszSrc
0x18002f871  mov     rdx, r13; cchDest
0x18002f874  lea     rcx, [rbp+2CA0h+String]; pszDest
0x18002f87b  call    StringCchCopyW
0x18002f880  mov     ebx, 1
0x18002f885  test    ebx, ebx
0x18002f887  jz      short loc_18002F83D
0x18002f889  jmp     short loc_18002F8A1
0x18002f88b  lea     r8, [rbp+2CA0h+pszSrc]; pszSrc
0x18002f892  mov     rdx, r13; cchDest
0x18002f895  lea     rcx, [rbp+2CA0h+String]; pszDest
0x18002f89c  call    StringCchCopyW
0x18002f8a1  lea     r8, asc_180078AAC; "\\"
0x18002f8a8  mov     rdx, r13; cchDest
0x18002f8ab  lea     rcx, [rbp+2CA0h+String]; pszDest
0x18002f8b2  call    StringCchCatW
0x18002f8b7  lea     r8, [rbp+2CA0h+String2]; pszSrc
0x18002f8be  mov     rdx, r13; cchDest
0x18002f8c1  lea     rcx, [rbp+2CA0h+pszSrc]; pszDest
0x18002f8c8  call    StringCchCopyW
0x18002f8cd  jmp     loc_18002F95A
0x18002f8d2  lea     rcx, [rbp+2CA0h+String]; lpString
0x18002f8d9  call    cs:__imp_lstrlenW
0x18002f8df  movsxd  rcx, eax
0x18002f8e2  lea     rbx, [rbp+2CA0h+String]
0x18002f8e9  lea     rbx, [rbx+rcx*2]
0x18002f8ed  lea     rcx, [rbp+2CA0h+String]; lpString
0x18002f8f4  call    cs:__imp_lstrlenW
0x18002f8fa  movsxd  rcx, eax
0x18002f8fd  lea     rdx, [rbp+2CA0h+pszSrc]
0x18002f904  lea     rdx, [rdx+rcx*2]
0x18002f908  movzx   eax, word ptr [rdx]
0x18002f90b  test    ax, ax
0x18002f90e  jz      short loc_18002F92D
0x18002f910  mov     ecx, 5Ch ; '\'
0x18002f915  cmp     ax, cx
0x18002f918  jz      short loc_18002F92D
0x18002f91a  add     rdx, 2
0x18002f91e  mov     [rbx], ax
0x18002f921  add     rbx, 2
0x18002f925  movzx   eax, word ptr [rdx]
0x18002f928  test    ax, ax
0x18002f92b  jnz     short loc_18002F915
0x18002f92d  xor     edx, edx; lpSecurityAttributes
0x18002f92f  mov     [rbx], r12w
0x18002f933  lea     rcx, [rbp+2CA0h+String]; lpPathName
0x18002f93a  call    cs:__imp_CreateDirectoryW
0x18002f940  test    eax, eax
0x18002f942  jz      short loc_18002F997
0x18002f944  lea     r8, asc_180078AAC; "\\"
0x18002f94b  mov     rdx, r13; cchDest
0x18002f94e  lea     rcx, [rbp+2CA0h+String]; pszDest
0x18002f955  call    StringCchCatW
0x18002f95a  lea     rcx, [rbp+2CA0h+String]; lpString
0x18002f961  call    cs:__imp_lstrlenW
0x18002f967  lea     rcx, [rbp+2CA0h+pszSrc]; lpString
0x18002f96e  mov     ebx, eax
0x18002f970  call    cs:__imp_lstrlenW
0x18002f976  cmp     ebx, eax
0x18002f978  jl      loc_18002F8D2
0x18002f97e  lea     rcx, [rdi+58h]; lpString1
0x18002f982  mov     rdx, r15; lpString2
0x18002f985  call    cs:__imp_lstrcmpiW
0x18002f98b  test    eax, eax
0x18002f98d  jnz     short loc_18002F9B7
0x18002f98f  lea     ebx, [rax+31h]
0x18002f992  jmp     loc_18002FA1E
0x18002f997  mov     [rsi], r12
0x18002f99a  call    cs:__imp_GetLastError
0x18002f9a0  mov     ecx, 1Ch
0x18002f9a5  cmp     eax, 0CEh
0x18002f9aa  lea     edx, [rcx+17h]
0x18002f9ad  cmovz   ecx, edx
0x18002f9b0  mov     eax, ecx
0x18002f9b2  jmp     loc_18002FE9A
0x18002f9b7  lea     rcx, [rdi+0A80h]; pszDest
0x18002f9be  mov     r8, r15; pszSrc
0x18002f9c1  mov     rdx, r13; cchDest
0x18002f9c4  call    StringCchCopyW
0x18002f9c9  mov     ebx, 3
0x18002f9ce  mov     [rsp+2DA0h+hTemplateFile], r12; hTemplateFile
0x18002f9d3  mov     r8d, ebx; dwShareMode
0x18002f9d6  mov     [rsp+2DA0h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x18002f9de  xor     r9d, r9d; lpSecurityAttributes
0x18002f9e1  mov     [rsp+2DA0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18002f9e5  mov     edx, 80000000h; dwDesiredAccess
0x18002f9ea  mov     rcx, r15; lpFileName
0x18002f9ed  call    cs:__imp_CreateFileW
0x18002f9f3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002f9f7  jz      short loc_18002FA0F
0x18002f9f9  mov     rcx, rax; hObject
0x18002f9fc  call    cs:__imp_CloseHandle
0x18002fa02  cmp     [rdi+4], r12d
0x18002fa06  jnz     short loc_18002FA0F
0x18002fa08  mov     ebx, 34h ; '4'
0x18002fa0d  jmp     short loc_18002FA1E
0x18002fa0f  lea     rcx, [rdi+58h]
0x18002fa13  call    initialize
0x18002fa18  test    eax, eax
0x18002fa1a  jz      short loc_18002FA25
0x18002fa1c  mov     ebx, eax
0x18002fa1e  mov     eax, ebx
0x18002fa20  jmp     loc_18002FE97
0x18002fa25  call    OpenCurrentZIP
0x18002fa2a  test    rax, rax
0x18002fa2d  jnz     short loc_18002FA39
0x18002fa2f  mov     eax, 1Dh
0x18002fa34  jmp     loc_18002FE9A
0x18002fa39  mov     ebx, r12d
0x18002fa3c  cmp     [rdi+50h], r12d
0x18002fa40  jnz     short loc_18002FAAB
0x18002fa42  call    Process_End_Directory
0x18002fa47  test    eax, eax
0x18002fa49  mov     [rdi+0CB0h], eax
0x18002fa4f  mov     ecx, eax
0x18002fa51  cmovnz  ebx, eax
0x18002fa54  mov     eax, [rdi+1106h]
0x18002fa5a  dec     eax
0x18002fa5c  cmp     [r14+18h], eax
0x18002fa60  jle     short loc_18002FA69
0x18002fa62  mov     ebx, 19h
0x18002fa67  jmp     short loc_18002FAA6
0x18002fa69  test    ebx, ebx
0x18002fa6b  jnz     short loc_18002FAA6
0x18002fa6d  cmp     [rdi+1138h], r12d
0x18002fa74  jnz     short loc_18002FA8A
0x18002fa76  mov     [rdi+0CA0h], r12
0x18002fa7d  call    Process_Central_Directory
0x18002fa82  mov     ecx, eax
0x18002fa84  mov     [rdi+0CB0h], eax
  ... truncated ...
```
