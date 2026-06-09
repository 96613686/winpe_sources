# extractIndexedItem

- ea: `0x1800b09b8`
- end: `0x1800b1441`
- name: `extractIndexedItem`
- size: `2697`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops`

## callers

- `0x1800afce8`

## callees

- `0x18009f9c8`
- `0x18009fa48`
- `0x1800a8544`
- `0x1800abe84`
- `0x1800abf58`
- `0x1800abfb8`
- `0x1800ac62c`
- `0x1800ac708`
- `0x1800ad0d8`
- `0x1800ad3c0`
- `0x1800aeb3c`
- `0x1800aebb8`
- `0x1800aec40`
- `0x1800aecb8`
- `0x1800aef84`
- `0x1800af7e0`
- `0x1800b0978`
- `0x1800b09b8`
- `0x1800b14c0`
- `0x1800b15c4`
- `0x1800b1708`
- `0x1800b1ad8`
- `0x1800b1b78`
- `0x1800b1ca8`
- `0x1800b1f48`
- `0x1800b30b0`
- `0x1800cf56a`
- `0x1800cf5c0`
- `0x1800cf680`
- `0x1800d1010`

## import_xrefs

- `msvcrt!free` at `0x1800b128e`
- `msvcrt!free` at `0x1800b12b4`
- `msvcrt!free` at `0x1800b13e2`
- `msvcrt!free` at `0x1800b1408`
- `msvcrt!free` at `0x1800b128e`
- `msvcrt!free` at `0x1800b12b4`
- `msvcrt!free` at `0x1800b13e2`
- `msvcrt!free` at `0x1800b1408`
- `KERNEL32!lstrcmpiA` at `0x1800b0e9a`
- `KERNEL32!lstrcmpiA` at `0x1800b114f`
- `KERNEL32!lstrcmpiA` at `0x1800b0e9a`
- `KERNEL32!lstrcmpiA` at `0x1800b114f`
- `KERNEL32!ReadFile` at `0x1800b10d7`
- `KERNEL32!ReadFile` at `0x1800b1202`
- `KERNEL32!ReadFile` at `0x1800b10d7`
- `KERNEL32!ReadFile` at `0x1800b1202`
- `KERNEL32!GetLastError` at `0x1800b0e66`
- `KERNEL32!GetLastError` at `0x1800b0e66`
- `KERNEL32!CloseHandle` at `0x1800b0ef4`
- `KERNEL32!CloseHandle` at `0x1800b0ef4`
- `USER32!CharNextA` at `0x1800b0b26`
- `USER32!CharNextA` at `0x1800b0e0f`
- `USER32!CharNextA` at `0x1800b0b26`
- `USER32!CharNextA` at `0x1800b0e0f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b0a3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800b0a3d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x1800b0e30`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x1800b0e30`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800b0ee0`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800b0ee0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800b0d23`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800b0d23`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1800b0df4`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1800b0df4`

## pseudocode

```c
__int64 __fastcall extractIndexedItem(__int64 a1)
{
  _QWORD *Value; // rax
  _QWORD *v3; // rdi
  __int64 v5; // r15
  unsigned int v6; // esi
  char *v7; // rsi
  LPSTR v8; // rax
  CHAR v9; // cl
  __int64 v10; // r8
  const char *v11; // r8
  int v12; // eax
  const char *v13; // r8
  __int64 v14; // rax
  void (__fastcall *v15)(char *, _QWORD); // rax
  __int64 v16; // rax
  int v17; // ebx
  _BYTE *v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  CHAR *v21; // rbx
  BYTE *v22; // rsi
  CHAR i; // al
  DWORD LastError; // eax
  unsigned int v25; // ecx
  HANDLE FileA; // rax
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // rcx
  unsigned int v30; // eax
  bool v31; // zf
  int v32; // r12d
  unsigned __int16 *v33; // r13
  int v34; // eax
  int v35; // edx
  int v36; // eax
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rax
  int v40; // eax
  void *v41; // rcx
  void *v42; // rcx
  char *v43; // r10
  char *v44; // rbx
  size_t v45; // rdx
  char *v46; // r8
  unsigned int v47; // r11d
  __int64 v48; // rax
  int v49; // eax
  int Member; // eax
  unsigned __int64 v51; // rax
  void *v52; // rcx
  void *v53; // rcx
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-B0h] BYREF
  char v55[260]; // [rsp+60h] [rbp-A0h] BYREF
  int v56; // [rsp+164h] [rbp+64h]
  int v57; // [rsp+168h] [rbp+68h]
  int v58; // [rsp+16Ch] [rbp+6Ch]
  char v59[272]; // [rsp+170h] [rbp+70h] BYREF
  CHAR v60[2160]; // [rsp+280h] [rbp+180h] BYREF
  CHAR FileName[272]; // [rsp+AF0h] [rbp+9F0h] BYREF
  CHAR PathName[272]; // [rsp+C00h] [rbp+B00h] BYREF
  char pszDest; // [rsp+D10h] [rbp+C10h] BYREF
  char v64[271]; // [rsp+D11h] [rbp+C11h] BYREF
  CHAR String2[272]; // [rsp+E20h] [rbp+D20h] BYREF
  char pszSrc[272]; // [rsp+F30h] [rbp+E30h] BYREF

  pszDest = 0;
  memset_0(v64, 0, 0x103u);
  memset_0(v60, 0, 0x866u);
  memset_0(v55, 0, 0x214u);
  NumberOfBytesRead = 0;
  Value = TlsGetValue(dwUnZIPTlsIndex);
  v3 = Value;
  if ( !Value )
    return 4;
  Value[568] = 0;
  if ( !*(_DWORD *)(a1 + 56) && !*((_DWORD *)Value + 10) && !*((_DWORD *)Value + 12) )
  {
    RemoveDoubleQuotes(&pszDest, *(_QWORD *)(a1 + 36));
    if ( !(unsigned int)DBCS_IsLastBackSlash(&pszDest) )
      StringCchCatA(&pszDest, 0x104u, "\\");
  }
  v5 = a1 + 190;
  if ( !*((_DWORD *)v3 + 33) )
  {
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)v5 = v60;
    if ( !*((_DWORD *)v3 + 33) )
    {
      if ( (unsigned int)GetIndexedZipInfo(a1) )
      {
        v6 = 47;
LABEL_145:
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)v5 = 0;
        v52 = (void *)v3[8904];
        if ( v52 )
        {
          free(v52);
          v3[8904] = 0;
        }
        v53 = *(void **)((char *)v3 + 71886);
        if ( v53 )
        {
          *(_QWORD *)((char *)v3 + 71902) = 0;
          free(v53);
          *(_QWORD *)((char *)v3 + 71886) = 0;
        }
        return v6;
      }
    }
  }
  v7 = (char *)v3 + 4020;
  StringCchCopyA((STRSAFE_LPSTR)v3 + 4020, 0x104u, &pszDest);
  v5 = a1 + 190;
  v8 = (LPSTR)(*(_QWORD *)(a1 + 190) + 70LL);
  v9 = *v8;
  if ( *v8 )
  {
    do
    {
      if ( v9 == 47 )
        *v8 = 92;
      v8 = CharNextA(v8);
      v9 = *v8;
    }
    while ( *v8 );
    v7 = (char *)v3 + 4020;
  }
  v10 = *(_QWORD *)(a1 + 16);
  if ( v10 )
    v11 = (const char *)(v10 + 38);
  else
    v11 = (const char *)(*(_QWORD *)v5 + 70LL);
  StringCchCopyA(v59, 0x104u, v11);
  v12 = *(_DWORD *)(a1 + 60);
  if ( *(_QWORD *)(a1 + 16) )
  {
    if ( v12 )
    {
      ExtractFilename(pszSrc, 0x104u);
      StringCchCopyA((STRSAFE_LPSTR)(*(_QWORD *)(a1 + 16) + 38LL), 0x104u, pszSrc);
    }
    v13 = (const char *)(*(_QWORD *)(a1 + 16) + 38LL);
  }
  else
  {
    if ( v12 )
    {
      ExtractFilename(pszSrc, 0x104u);
      StringCchCopyA((STRSAFE_LPSTR)(*(_QWORD *)v5 + 70LL), 0x800u, pszSrc);
    }
    v13 = (const char *)(*(_QWORD *)v5 + 70LL);
  }
  StringCchCatA(v7, 0x104u, v13);
  v56 = *((unsigned __int16 *)v3 + 2751);
  v57 = *((unsigned __int16 *)v3 + 2750);
  v14 = *(_QWORD *)(a1 + 16);
  if ( v14 )
    v58 = *(_DWORD *)(v14 + 298);
  else
    v58 = *(_DWORD *)(*(_QWORD *)v5 + 24LL);
  StringCchCopyA(v55, 0x104u, v7);
  if ( !*(_DWORD *)(a1 + 56) && !*((_DWORD *)v3 + 10) && !*((_DWORD *)v3 + 12) )
  {
    v15 = (void (__fastcall *)(char *, _QWORD))v3[615];
    if ( v15 )
    {
      v15(v55, v3[616]);
      StringCchCopyA(v7, 0x104u, v55);
      v16 = *(_QWORD *)(a1 + 16);
      if ( v16 )
        *(_DWORD *)(v16 + 298) = v58;
      else
        *(_DWORD *)(*(_QWORD *)v5 + 24LL) = v58;
    }
    DBCS_splitpath((_DWORD)v7, (unsigned int)pszSrc, 260, (unsigned int)String2, 260, 0, 0, 0, 0);
    DBCS_makepath(FileName, 0, 0);
    StringCchCopyA(String2, 0x104u, FileName);
    v17 = 0;
    while ( 1 )
    {
      v18 = (_BYTE *)DBCS_strrchr(FileName, 92);
      if ( !v18 )
        break;
      *v18 = 0;
      if ( GetFileAttributesA(FileName) != -1 )
      {
        StringCchCopyA(PathName, 0x104u, FileName);
        v17 = 1;
      }
      if ( v17 )
        goto LABEL_44;
    }
    StringCchCopyA(PathName, 0x104u, FileName);
LABEL_44:
    StringCchCatA(PathName, 0x104u, "\\");
    StringCchCopyA(FileName, 0x104u, String2);
    while ( 1 )
    {
      v19 = -1;
      do
        ++v19;
      while ( FileName[v19] );
      v20 = -1;
      do
        ++v20;
      while ( PathName[v20] );
      if ( v20 >= v19 )
        break;
      v21 = &PathName[v20];
      v22 = (BYTE *)&FileName[v20];
      for ( i = FileName[v20]; i && i != 92; i = *v22 )
      {
        *v21++ = i;
        if ( IsDBCSLeadByte(*v22) )
          *v21++ = v22[1];
        v22 = (BYTE *)CharNextA((LPCSTR)v22);
      }
      *v21 = 0;
      if ( !CreateDirectoryA(PathName, 0) )
      {
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)v5 = 0;
        LastError = GetLastError();
        v25 = 28;
        if ( LastError == 206 )
          return 51;
        return v25;
      }
      StringCchCatA(PathName, 0x104u, "\\");
    }
    if ( !lstrcmpiA((LPCSTR)v3 + 520, (LPCSTR)v3 + 4020)
      || (StringCchCopyA((STRSAFE_LPSTR)v3 + 4280, 0x104u, (STRSAFE_LPCSTR)v3 + 4020),
          FileA = CreateFileA((LPCSTR)v3 + 4020, 0x80000000, 3u, 0, 3u, 0x80000080, 0),
          FileA != (HANDLE)-1LL)
      && (CloseHandle(FileA), !*((_DWORD *)v3 + 2)) )
    {
      v6 = 49;
      goto LABEL_67;
    }
  }
  v27 = initialize((STRSAFE_LPCSTR)v3 + 520);
  if ( v27 )
  {
    v6 = v27;
LABEL_67:
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)v5 = 0;
    return v6;
  }
  *((_DWORD *)v3 + 1151) = *(_DWORD *)(a1 + 56);
  if ( !OpenCurrentZIP() )
    return 29;
  v6 = 0;
  if ( !*((_DWORD *)v3 + 33) )
  {
    v28 = Process_End_Directory();
    *((_DWORD *)v3 + 1146) = v28;
    v29 = v28;
    if ( v28 )
      v6 = v28;
    if ( *(_DWORD *)(a1 + 32) <= *((_DWORD *)v3 + 1359) - 1 )
    {
      if ( !v6 )
      {
        if ( !*((_DWORD *)v3 + 1371) )
        {
          v3[570] = 0;
          v30 = Process_Central_Directory(v28);
          v29 = v30;
          *((_DWORD *)v3 + 1146) = v30;
        }
        if ( !(_DWORD)v29 )
        {
          v3[570] = *(int *)(a1 + 32);
          LODWORD(v29) = Process_Central_Directory(v29);
          *((_DWORD *)v3 + 1146) = v29;
        }
      }
    }
    else
    {
      v6 = 25;
    }
    if ( (int)v29 > (int)v6 )
      v6 = v29;
  }
  v31 = (v3[687] & 1) == 0;
  *(_DWORD *)((char *)v3 + 5610) = 0;
  if ( !v31 )
    *(_DWORD *)((char *)v3 + 5610) = 1;
  if ( *((_WORD *)v3 + 2749) > 0x13u )
  {
    v6 = 42;
LABEL_144:
    CloseArchive();
    goto LABEL_145;
  }
  if ( v6 )
    goto LABEL_144;
  v32 = 1;
  while ( *(_DWORD *)((char *)v3 + 5602) )
  {
    v33 = (unsigned __int16 *)v3 + 2761;
    if ( *((unsigned __int16 *)v3 + 2761) == *(_DWORD *)((char *)v3 + 5606) )
      break;
    CloseCurrentZIP();
    if ( *((_DWORD *)v3 + 8)
      || ((v34 = *((_DWORD *)v3 + 1355), v34 != -1) ? (v35 = 1, v36 = v34 + 1) : (v35 = 0, v36 = 0),
          (unsigned int)MsgCB(*(_QWORD *)(a1 + 198), v35, 1, (unsigned int)*v33 + 1, v36) != 1) )
    {
      v6 = 48;
      CloseCurrentZIP();
      goto LABEL_145;
    }
    if ( *((_DWORD *)v3 + 8) )
      v32 = 0;
    if ( !(unsigned int)CheckCurrentZIP()
      && OpenCurrentZIP()
      && (v37 = duzLLGetLDOffset(v3),
          DZSetFilePointer(v3[571], v37, 0),
          ReadFile((HANDLE)v3[571], (char *)v3 + 5044, 0x1Eu, &NumberOfBytesRead, 0))
      && NumberOfBytesRead == 30
      && *((_DWORD *)v3 + 1261) == 67324752 )
    {
      if ( (unsigned int)GetCDirFilename(*(HGLOBAL *)((char *)v3 + 5582), *(HGLOBAL *)((char *)v3 + 5566)) )
      {
        StringCchCopyA(String2, 0x104u, (STRSAFE_LPCSTR)v3 + 71910);
        get_filename(*((unsigned __int16 *)v3 + 2535));
        if ( !lstrcmpiA((LPCSTR)v3 + 71910, String2) )
        {
          v38 = *((unsigned __int16 *)v3 + 2536);
          *(_DWORD *)((char *)v3 + 5606) = *v33;
          if ( (unsigned int)get_zip64_extra_ldir(v3, v38) )
          {
            v6 = 0;
            CloseCurrentZIP();
            goto LABEL_120;
          }
          v32 = 0;
          v6 = 3;
        }
      }
      else
      {
        v6 = 3;
      }
    }
    else
    {
      v6 = 29;
    }
    if ( !v32 )
      goto LABEL_119;
  }
  v39 = duzLLGetLDOffset(v3);
  DZSetFilePointer(v3[571], v39, 0);
  if ( !ReadFile((HANDLE)v3[571], (char *)v3 + 5044, 0x1Eu, &NumberOfBytesRead, 0) || !NumberOfBytesRead )
    v6 = 3;
  if ( *((_DWORD *)v3 + 1261) != 67324752
    || !v6
    && (get_filename(*((unsigned __int16 *)v3 + 2535)),
        !(unsigned int)get_zip64_extra_ldir(v3, *((unsigned __int16 *)v3 + 2536))) )
  {
    v6 = 3;
    CloseCurrentZIP();
    goto LABEL_145;
  }
LABEL_119:
  CloseCurrentZIP();
  if ( v6 )
    goto LABEL_145;
LABEL_120:
  v40 = OpenArchive((LPCSTR)v3 + 520);
  *((_DWORD *)v3 + 1146) = v40;
  if ( !v40 )
  {
    v43 = (char *)v3 + 4628;
    if ( *((_DWORD *)v3 + 1151) || !*((_DWORD *)v3 + 10) )
    {
      v44 = (char *)v3 + 4020;
      StringCchCopyA(v55, 0x104u, (STRSAFE_LPCSTR)v3 + 4020);
      v46 = v55;
      v45 = v47;
    }
    else
    {
      v44 = (char *)v3 + 4020;
      v45 = 260;
      v46 = (char *)v3 + 4020;
    }
    StringCchCopyA(v43, v45, v46);
    v48 = *(_QWORD *)(a1 + 16);
    if ( v48 )
      v49 = *(_DWORD *)(v48 + 298);
    else
      v49 = *(_DWORD *)(*(_QWORD *)v5 + 24LL);
    *((_DWORD *)v3 + 1135) = v49 & 0x27;
    if ( v3[615] )
    {
      *((_WORD *)v3 + 2528) = v56;
      *((_WORD *)v3 + 2527) = v57;
    }
    if ( (unsigned int)DBCS_IsLastBackSlash(v44) )
    {
      *((_DWORD *)v3 + 1135) |= 0x10u;
      v51 = -1;
      do
        ++v51;
      while ( v44[v51] );
      if ( v51 > 1 )
      {
        *((_BYTE *)v3 + v51 + 4019) = 0;
        set_file_time_and_close();
      }
    }
    else
    {
      Member = ExtractMember((LPCSTR)v3 + 4280);
      *((_DWORD *)v3 + 1146) = Member;
      v6 = Member;
      if ( Member > 0 && *(_DWORD *)((char *)v3 + 5610) && Member == 44 )
      {
        *(_QWORD *)(a1 + 16) = 0;
        v6 = 49;
        *(_QWORD *)v5 = 0;
      }
    }
    goto LABEL_144;
  }
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)v5 = 0;
  v41 = (void *)v3[8904];
  if ( v41 )
  {
    free(v41);
    v3[8904] = 0;
  }
  v42 = *(void **)((char *)v3 + 71886);
  if ( v42 )
  {
    *(_QWORD *)((char *)v3 + 71902) = 0;
    free(v42);
    *(_QWORD *)((char *)v3 + 71886) = 0;
  }
  return *((unsigned int *)v3 + 1146);
}

```

## disassembly

```asm
0x1800b09b8  push    rbp
0x1800b09ba  push    rbx
0x1800b09bb  push    rsi
0x1800b09bc  push    rdi
0x1800b09bd  push    r12
0x1800b09bf  push    r13
0x1800b09c1  push    r14
0x1800b09c3  push    r15
0x1800b09c5  lea     rbp, [rsp-0F58h]
0x1800b09cd  mov     eax, 1058h
0x1800b09d2  call    _alloca_probe
0x1800b09d7  sub     rsp, rax
0x1800b09da  mov     rax, cs:__security_cookie
0x1800b09e1  xor     rax, rsp
0x1800b09e4  mov     [rbp+0F90h+var_50], rax
0x1800b09eb  mov     r14, rcx
0x1800b09ee  xor     r13d, r13d
0x1800b09f1  lea     rcx, [rbp+0F90h+var_37F]; void *
0x1800b09f8  mov     [rbp+0F90h+pszDest], r13b
0x1800b09ff  xor     edx, edx; Val
0x1800b0a01  mov     r8d, 103h; Size
0x1800b0a07  call    memset_0
0x1800b0a0c  xor     edx, edx; Val
0x1800b0a0e  lea     rcx, [rbp+0F90h+var_E10]; void *
0x1800b0a15  mov     r8d, 866h; Size
0x1800b0a1b  call    memset_0
0x1800b0a20  xor     edx, edx; Val
0x1800b0a22  lea     rcx, [rsp+1090h+var_1030]; void *
0x1800b0a27  mov     r8d, 214h; Size
0x1800b0a2d  call    memset_0
0x1800b0a32  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800b0a38  mov     [rsp+1090h+NumberOfBytesRead], r13d
0x1800b0a3d  call    cs:__imp_TlsGetValue
0x1800b0a44  nop     dword ptr [rax+rax+00h]
0x1800b0a49  mov     rdi, rax
0x1800b0a4c  test    rax, rax
0x1800b0a4f  jnz     short loc_1800B0A59
0x1800b0a51  lea     eax, [rdi+4]
0x1800b0a54  jmp     loc_1800B141D
0x1800b0a59  mov     [rax+11C0h], r13
0x1800b0a60  mov     ebx, 104h
0x1800b0a65  cmp     [r14+38h], r13d
0x1800b0a69  jnz     short loc_1800B0AAC
0x1800b0a6b  cmp     [rax+28h], r13d
0x1800b0a6f  jnz     short loc_1800B0AAC
0x1800b0a71  cmp     [rax+30h], r13d
0x1800b0a75  jnz     short loc_1800B0AAC
0x1800b0a77  mov     rdx, [r14+24h]
0x1800b0a7b  lea     rcx, [rbp+0F90h+pszDest]
0x1800b0a82  call    RemoveDoubleQuotes
0x1800b0a87  lea     rcx, [rbp+0F90h+pszDest]
0x1800b0a8e  call    DBCS_IsLastBackSlash
0x1800b0a93  test    eax, eax
0x1800b0a95  jnz     short loc_1800B0AAC
0x1800b0a97  lea     r8, asc_1800EE530; "\\"
0x1800b0a9e  mov     edx, ebx; cchDest
0x1800b0aa0  lea     rcx, [rbp+0F90h+pszDest]; pszDest
0x1800b0aa7  call    StringCchCatA
0x1800b0aac  lea     r15, [r14+0BEh]
0x1800b0ab3  cmp     [rdi+84h], r13d
0x1800b0aba  jnz     short loc_1800B0AE9
0x1800b0abc  lea     rax, [rbp+0F90h+var_E10]
0x1800b0ac3  mov     [r14+10h], r13
0x1800b0ac7  mov     [r15], rax
0x1800b0aca  cmp     [rdi+84h], r13d
0x1800b0ad1  jnz     short loc_1800B0AE9
0x1800b0ad3  mov     rcx, r14
0x1800b0ad6  call    GetIndexedZipInfo
0x1800b0adb  test    eax, eax
0x1800b0add  jz      short loc_1800B0AE9
0x1800b0adf  mov     esi, 2Fh ; '/'
0x1800b0ae4  jmp     loc_1800B13CF
0x1800b0ae9  lea     rsi, [rdi+0FB4h]
0x1800b0af0  mov     rdx, rbx; cchDest
0x1800b0af3  mov     rcx, rsi; pszDest
0x1800b0af6  lea     r8, [rbp+0F90h+pszDest]; pszSrc
0x1800b0afd  call    StringCchCopyA
0x1800b0b02  lea     r15, [r14+0BEh]
0x1800b0b09  mov     rax, [r15]
0x1800b0b0c  add     rax, 46h ; 'F'
0x1800b0b10  mov     cl, [rax]
0x1800b0b12  test    cl, cl
0x1800b0b14  jz      short loc_1800B0B3F
0x1800b0b16  mov     esi, 2Fh ; '/'
0x1800b0b1b  cmp     cl, sil
0x1800b0b1e  jnz     short loc_1800B0B23
0x1800b0b20  mov     byte ptr [rax], 5Ch ; '\'
0x1800b0b23  mov     rcx, rax; lpsz
0x1800b0b26  call    cs:__imp_CharNextA
0x1800b0b2d  nop     dword ptr [rax+rax+00h]
0x1800b0b32  mov     cl, [rax]
0x1800b0b34  test    cl, cl
0x1800b0b36  jnz     short loc_1800B0B1B
0x1800b0b38  lea     rsi, [rdi+0FB4h]
0x1800b0b3f  mov     r8, [r14+10h]
0x1800b0b43  test    r8, r8
0x1800b0b46  jz      short loc_1800B0B4E
0x1800b0b48  add     r8, 26h ; '&'
0x1800b0b4c  jmp     short loc_1800B0B55
0x1800b0b4e  mov     r8, [r15]
0x1800b0b51  add     r8, 46h ; 'F'; pszSrc
0x1800b0b55  mov     rdx, rbx; cchDest
0x1800b0b58  lea     rcx, [rbp+0F90h+var_F20]; pszDest
0x1800b0b5c  call    StringCchCopyA
0x1800b0b61  mov     r8, [r14+10h]
0x1800b0b65  mov     eax, [r14+3Ch]
0x1800b0b69  test    r8, r8
0x1800b0b6c  jz      short loc_1800B0BA5
0x1800b0b6e  test    eax, eax
0x1800b0b70  jz      short loc_1800B0B9B
0x1800b0b72  add     r8, 26h ; '&'
0x1800b0b76  lea     rcx, [rbp+0F90h+pszSrc]; pszDest
0x1800b0b7d  mov     edx, ebx; cchDest
0x1800b0b7f  call    ExtractFilename
0x1800b0b84  mov     rcx, [r14+10h]
0x1800b0b88  lea     r8, [rbp+0F90h+pszSrc]; pszSrc
0x1800b0b8f  add     rcx, 26h ; '&'; pszDest
0x1800b0b93  mov     rdx, rbx; cchDest
0x1800b0b96  call    StringCchCopyA
0x1800b0b9b  mov     r8, [r14+10h]
0x1800b0b9f  add     r8, 26h ; '&'
0x1800b0ba3  jmp     short loc_1800B0BDD
0x1800b0ba5  test    eax, eax
0x1800b0ba7  jz      short loc_1800B0BD6
0x1800b0ba9  mov     r8, [r15]
0x1800b0bac  lea     rcx, [rbp+0F90h+pszSrc]; pszDest
0x1800b0bb3  add     r8, 46h ; 'F'
0x1800b0bb7  mov     edx, ebx; cchDest
0x1800b0bb9  call    ExtractFilename
0x1800b0bbe  mov     rcx, [r15]
0x1800b0bc1  lea     r8, [rbp+0F90h+pszSrc]; pszSrc
0x1800b0bc8  add     rcx, 46h ; 'F'; pszDest
0x1800b0bcc  mov     edx, 800h; cchDest
0x1800b0bd1  call    StringCchCopyA
0x1800b0bd6  mov     r8, [r15]
0x1800b0bd9  add     r8, 46h ; 'F'; pszSrc
0x1800b0bdd  mov     rdx, rbx; cchDest
0x1800b0be0  mov     rcx, rsi; pszDest
0x1800b0be3  call    StringCchCatA
0x1800b0be8  movzx   eax, word ptr [rdi+157Eh]
0x1800b0bef  mov     [rbp+0F90h+var_F2C], eax
0x1800b0bf2  movzx   eax, word ptr [rdi+157Ch]
0x1800b0bf9  mov     [rbp+0F90h+var_F28], eax
0x1800b0bfc  mov     rax, [r14+10h]
0x1800b0c00  test    rax, rax
0x1800b0c03  jz      short loc_1800B0C10
0x1800b0c05  mov     eax, [rax+12Ah]
0x1800b0c0b  mov     [rbp+0F90h+var_F24], eax
0x1800b0c0e  jmp     short loc_1800B0C19
0x1800b0c10  mov     rax, [r15]
0x1800b0c13  mov     ecx, [rax+18h]
0x1800b0c16  mov     [rbp+0F90h+var_F24], ecx
0x1800b0c19  mov     r8, rsi; pszSrc
0x1800b0c1c  lea     rcx, [rsp+1090h+var_1030]; pszDest
0x1800b0c21  mov     rdx, rbx; cchDest
0x1800b0c24  call    StringCchCopyA
0x1800b0c29  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800b0c2d  cmp     [r14+38h], r13d
0x1800b0c31  jnz     loc_1800B0F0D
0x1800b0c37  cmp     [rdi+28h], r13d
0x1800b0c3b  jnz     loc_1800B0F0D
0x1800b0c41  cmp     [rdi+30h], r13d
0x1800b0c45  jnz     loc_1800B0F0D
0x1800b0c4b  mov     rax, [rdi+1338h]
0x1800b0c52  test    rax, rax
0x1800b0c55  jz      short loc_1800B0C95
0x1800b0c57  mov     rdx, [rdi+1340h]
0x1800b0c5e  lea     rcx, [rsp+1090h+var_1030]
0x1800b0c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0c68  lea     r8, [rsp+1090h+var_1030]; pszSrc
0x1800b0c6d  mov     rdx, rbx; cchDest
0x1800b0c70  mov     rcx, rsi; pszDest
0x1800b0c73  call    StringCchCopyA
0x1800b0c78  mov     rax, [r14+10h]
0x1800b0c7c  mov     r10d, [rbp+0F90h+var_F24]
0x1800b0c80  test    rax, rax
0x1800b0c83  jz      short loc_1800B0C8E
0x1800b0c85  mov     [rax+12Ah], r10d
0x1800b0c8c  jmp     short loc_1800B0C95
0x1800b0c8e  mov     rax, [r15]
0x1800b0c91  mov     [rax+18h], r10d
0x1800b0c95  mov     [rsp+1090h+var_1050], r13d
0x1800b0c9a  lea     r9, [rbp+0F90h+String2]
0x1800b0ca1  mov     [rsp+1090h+var_1058], r13
0x1800b0ca6  lea     rdx, [rbp+0F90h+pszSrc]
0x1800b0cad  mov     dword ptr [rsp+1090h+hTemplateFile], r13d
0x1800b0cb2  mov     r8d, ebx
0x1800b0cb5  mov     qword ptr [rsp+1090h+dwFlagsAndAttributes], r13
0x1800b0cba  mov     rcx, rsi
0x1800b0cbd  mov     [rsp+1090h+dwCreationDisposition], ebx
0x1800b0cc1  call    DBCS_splitpath
0x1800b0cc6  lea     r9, [rbp+0F90h+String2]
0x1800b0ccd  mov     qword ptr [rsp+1090h+dwFlagsAndAttributes], r13; STRSAFE_LPCSTR
0x1800b0cd2  lea     r8, [rbp+0F90h+pszSrc]
0x1800b0cd9  mov     qword ptr [rsp+1090h+dwCreationDisposition], r13; pszSrc
0x1800b0cde  lea     rcx, [rbp+0F90h+FileName]; pszDest
0x1800b0ce5  call    DBCS_makepath
0x1800b0cea  lea     r8, [rbp+0F90h+FileName]; pszSrc
0x1800b0cf1  mov     rdx, rbx; cchDest
0x1800b0cf4  lea     rcx, [rbp+0F90h+String2]; pszDest
0x1800b0cfb  call    StringCchCopyA
0x1800b0d00  mov     ebx, r13d
0x1800b0d03  mov     edx, 5Ch ; '\'
0x1800b0d08  lea     rcx, [rbp+0F90h+FileName]
0x1800b0d0f  call    DBCS_strrchr
0x1800b0d14  test    rax, rax
0x1800b0d17  jz      short loc_1800B0D5C
0x1800b0d19  lea     rcx, [rbp+0F90h+FileName]; lpFileName
0x1800b0d20  mov     [rax], r13b
0x1800b0d23  call    cs:__imp_GetFileAttributesA
0x1800b0d2a  nop     dword ptr [rax+rax+00h]
0x1800b0d2f  cmp     eax, 0FFFFFFFFh
0x1800b0d32  jz      short loc_1800B0D51
0x1800b0d34  lea     r8, [rbp+0F90h+FileName]; pszSrc
0x1800b0d3b  mov     edx, 104h; cchDest
0x1800b0d40  lea     rcx, [rbp+0F90h+PathName]; pszDest
0x1800b0d47  call    StringCchCopyA
0x1800b0d4c  mov     ebx, 1
0x1800b0d51  test    ebx, ebx
0x1800b0d53  jz      short loc_1800B0D03
0x1800b0d55  mov     ebx, 104h
0x1800b0d5a  jmp     short loc_1800B0D76
0x1800b0d5c  mov     ebx, 104h
0x1800b0d61  lea     r8, [rbp+0F90h+FileName]; pszSrc
0x1800b0d68  mov     edx, ebx; cchDest
0x1800b0d6a  lea     rcx, [rbp+0F90h+PathName]; pszDest
0x1800b0d71  call    StringCchCopyA
0x1800b0d76  lea     r8, asc_1800EE530; "\\"
0x1800b0d7d  mov     rdx, rbx; cchDest
0x1800b0d80  lea     rcx, [rbp+0F90h+PathName]; pszDest
0x1800b0d87  call    StringCchCatA
0x1800b0d8c  lea     r8, [rbp+0F90h+String2]; pszSrc
0x1800b0d93  mov     rdx, rbx; cchDest
0x1800b0d96  lea     rcx, [rbp+0F90h+FileName]; pszDest
0x1800b0d9d  call    StringCchCopyA
0x1800b0da2  lea     rax, [rbp+0F90h+FileName]
0x1800b0da9  mov     rcx, r12
0x1800b0dac  inc     rcx
0x1800b0daf  cmp     [rax+rcx], r13b
0x1800b0db3  jnz     short loc_1800B0DAC
0x1800b0db5  lea     rdx, [rbp+0F90h+PathName]
0x1800b0dbc  mov     rax, r12
0x1800b0dbf  inc     rax
0x1800b0dc2  cmp     [rdx+rax], r13b
0x1800b0dc6  jnz     short loc_1800B0DBF
0x1800b0dc8  cmp     rax, rcx
0x1800b0dcb  jnb     loc_1800B0E89
0x1800b0dd1  lea     rbx, [rbp+0F90h+PathName]
0x1800b0dd8  add     rbx, rax
0x1800b0ddb  lea     rsi, [rbp+0F90h+FileName]
0x1800b0de2  add     rsi, rax
0x1800b0de5  mov     al, [rsi]
0x1800b0de7  jmp     short loc_1800B0E20
0x1800b0de9  cmp     al, 5Ch ; '\'
0x1800b0deb  jz      short loc_1800B0E24
0x1800b0ded  mov     [rbx], al
0x1800b0def  inc     rbx
0x1800b0df2  mov     cl, [rsi]; TestChar
0x1800b0df4  call    cs:__imp_IsDBCSLeadByte
0x1800b0dfb  nop     dword ptr [rax+rax+00h]
0x1800b0e00  test    eax, eax
0x1800b0e02  jz      short loc_1800B0E0C
0x1800b0e04  mov     al, [rsi+1]
0x1800b0e07  mov     [rbx], al
0x1800b0e09  inc     rbx
0x1800b0e0c  mov     rcx, rsi; lpsz
0x1800b0e0f  call    cs:__imp_CharNextA
0x1800b0e16  nop     dword ptr [rax+rax+00h]
0x1800b0e1b  mov     rsi, rax
0x1800b0e1e  mov     al, [rax]
0x1800b0e20  test    al, al
0x1800b0e22  jnz     short loc_1800B0DE9
0x1800b0e24  xor     edx, edx; lpSecurityAttributes
0x1800b0e26  mov     [rbx], r13b
0x1800b0e29  lea     rcx, [rbp+0F90h+PathName]; lpPathName
0x1800b0e30  call    cs:__imp_CreateDirectoryA
0x1800b0e37  nop     dword ptr [rax+rax+00h]
0x1800b0e3c  test    eax, eax
0x1800b0e3e  jz      short loc_1800B0E5F
0x1800b0e40  mov     ebx, 104h
0x1800b0e45  lea     r8, asc_1800EE530; "\\"
0x1800b0e4c  mov     edx, ebx; cchDest
0x1800b0e4e  lea     rcx, [rbp+0F90h+PathName]; pszDest
0x1800b0e55  call    StringCchCatA
0x1800b0e5a  jmp     loc_1800B0DA2
0x1800b0e5f  mov     [r14+10h], r13
0x1800b0e63  mov     [r15], r13
0x1800b0e66  call    cs:__imp_GetLastError
0x1800b0e6d  nop     dword ptr [rax+rax+00h]
0x1800b0e72  mov     ecx, 1Ch
0x1800b0e77  cmp     eax, 0CEh
0x1800b0e7c  lea     edx, [rcx+17h]
0x1800b0e7f  cmovz   ecx, edx
0x1800b0e82  mov     eax, ecx
0x1800b0e84  jmp     loc_1800B141D
0x1800b0e89  lea     rsi, [rdi+0FB4h]
0x1800b0e90  mov     rdx, rsi; lpString2
0x1800b0e93  lea     rcx, [rdi+208h]; lpString1
0x1800b0e9a  call    cs:__imp_lstrcmpiA
0x1800b0ea1  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
