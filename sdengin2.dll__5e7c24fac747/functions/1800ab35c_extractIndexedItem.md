# extractIndexedItem

- ea: `0x1800ab35c`
- end: `0x1800abd7e`
- name: `extractIndexedItem`
- size: `2594`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops`

## callers

- `0x1800aa6d0`

## callees

- `0x18009b270`
- `0x18009b2f0`
- `0x1800a3608`
- `0x1800a6cb0`
- `0x1800a6d70`
- `0x1800a6dc4`
- `0x1800a7310`
- `0x1800a73e8`
- `0x1800a7cf4`
- `0x1800a7fa8`
- `0x1800a95e8`
- `0x1800a9660`
- `0x1800a96dc`
- `0x1800a9748`
- `0x1800a9a0c`
- `0x1800aa214`
- `0x1800ab320`
- `0x1800ab35c`
- `0x1800abdec`
- `0x1800abed4`
- `0x1800ac004`
- `0x1800ac3ac`
- `0x1800ac44c`
- `0x1800ac578`
- `0x1800ac800`
- `0x1800ad8d8`
- `0x1800c97da`
- `0x1800c9830`
- `0x1800c98f0`
- `0x1800cb010`

## import_xrefs

- `msvcrt!free` at `0x1800abbe4`
- `msvcrt!free` at `0x1800abc04`
- `msvcrt!free` at `0x1800abd2c`
- `msvcrt!free` at `0x1800abd4c`
- `msvcrt!free` at `0x1800abbe4`
- `msvcrt!free` at `0x1800abc04`
- `msvcrt!free` at `0x1800abd2c`
- `msvcrt!free` at `0x1800abd4c`
- `KERNEL32!lstrcmpiA` at `0x1800ab814`
- `KERNEL32!lstrcmpiA` at `0x1800abab1`
- `KERNEL32!lstrcmpiA` at `0x1800ab814`
- `KERNEL32!lstrcmpiA` at `0x1800abab1`
- `KERNEL32!ReadFile` at `0x1800aba3f`
- `KERNEL32!ReadFile` at `0x1800abb5e`
- `KERNEL32!ReadFile` at `0x1800aba3f`
- `KERNEL32!ReadFile` at `0x1800abb5e`
- `KERNEL32!GetLastError` at `0x1800ab7e6`
- `KERNEL32!GetLastError` at `0x1800ab7e6`
- `KERNEL32!CloseHandle` at `0x1800ab862`
- `KERNEL32!CloseHandle` at `0x1800ab862`
- `USER32!CharNextA` at `0x1800ab4c4`
- `USER32!CharNextA` at `0x1800ab79b`
- `USER32!CharNextA` at `0x1800ab4c4`
- `USER32!CharNextA` at `0x1800ab79b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800ab3e1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800ab3e1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x1800ab7b6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x1800ab7b6`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800ab854`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800ab854`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800ab6bb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800ab6bb`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1800ab786`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x1800ab786`

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
0x1800ab35c  push    rbp
0x1800ab35e  push    rbx
0x1800ab35f  push    rsi
0x1800ab360  push    rdi
0x1800ab361  push    r12
0x1800ab363  push    r13
0x1800ab365  push    r14
0x1800ab367  push    r15
0x1800ab369  lea     rbp, [rsp-0F58h]
0x1800ab371  mov     eax, 1058h
0x1800ab376  call    _alloca_probe
0x1800ab37b  sub     rsp, rax
0x1800ab37e  mov     rax, cs:__security_cookie
0x1800ab385  xor     rax, rsp
0x1800ab388  mov     [rbp+0F90h+var_50], rax
0x1800ab38f  mov     r14, rcx
0x1800ab392  xor     r13d, r13d
0x1800ab395  lea     rcx, [rbp+0F90h+var_37F]; void *
0x1800ab39c  mov     [rbp+0F90h+pszDest], r13b
0x1800ab3a3  xor     edx, edx; Val
0x1800ab3a5  mov     r8d, 103h; Size
0x1800ab3ab  call    memset_0
0x1800ab3b0  xor     edx, edx; Val
0x1800ab3b2  lea     rcx, [rbp+0F90h+var_E10]; void *
0x1800ab3b9  mov     r8d, 866h; Size
0x1800ab3bf  call    memset_0
0x1800ab3c4  xor     edx, edx; Val
0x1800ab3c6  lea     rcx, [rsp+1090h+var_1030]; void *
0x1800ab3cb  mov     r8d, 214h; Size
0x1800ab3d1  call    memset_0
0x1800ab3d6  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800ab3dc  mov     [rsp+1090h+NumberOfBytesRead], r13d
0x1800ab3e1  call    cs:__imp_TlsGetValue
0x1800ab3e7  mov     rdi, rax
0x1800ab3ea  test    rax, rax
0x1800ab3ed  jnz     short loc_1800AB3F7
0x1800ab3ef  lea     eax, [rdi+4]
0x1800ab3f2  jmp     loc_1800ABD5B
0x1800ab3f7  mov     [rax+11C0h], r13
0x1800ab3fe  mov     ebx, 104h
0x1800ab403  cmp     [r14+38h], r13d
0x1800ab407  jnz     short loc_1800AB44A
0x1800ab409  cmp     [rax+28h], r13d
0x1800ab40d  jnz     short loc_1800AB44A
0x1800ab40f  cmp     [rax+30h], r13d
0x1800ab413  jnz     short loc_1800AB44A
0x1800ab415  mov     rdx, [r14+24h]
0x1800ab419  lea     rcx, [rbp+0F90h+pszDest]
0x1800ab420  call    RemoveDoubleQuotes
0x1800ab425  lea     rcx, [rbp+0F90h+pszDest]
0x1800ab42c  call    DBCS_IsLastBackSlash
0x1800ab431  test    eax, eax
0x1800ab433  jnz     short loc_1800AB44A
0x1800ab435  lea     r8, asc_1800E8550; "\\"
0x1800ab43c  mov     edx, ebx; cchDest
0x1800ab43e  lea     rcx, [rbp+0F90h+pszDest]; pszDest
0x1800ab445  call    StringCchCatA
0x1800ab44a  lea     r15, [r14+0BEh]
0x1800ab451  cmp     [rdi+84h], r13d
0x1800ab458  jnz     short loc_1800AB487
0x1800ab45a  lea     rax, [rbp+0F90h+var_E10]
0x1800ab461  mov     [r14+10h], r13
0x1800ab465  mov     [r15], rax
0x1800ab468  cmp     [rdi+84h], r13d
0x1800ab46f  jnz     short loc_1800AB487
0x1800ab471  mov     rcx, r14
0x1800ab474  call    GetIndexedZipInfo
0x1800ab479  test    eax, eax
0x1800ab47b  jz      short loc_1800AB487
0x1800ab47d  mov     esi, 2Fh ; '/'
0x1800ab482  jmp     loc_1800ABD19
0x1800ab487  lea     rsi, [rdi+0FB4h]
0x1800ab48e  mov     rdx, rbx; cchDest
0x1800ab491  mov     rcx, rsi; pszDest
0x1800ab494  lea     r8, [rbp+0F90h+pszDest]; pszSrc
0x1800ab49b  call    StringCchCopyA
0x1800ab4a0  lea     r15, [r14+0BEh]
0x1800ab4a7  mov     rax, [r15]
0x1800ab4aa  add     rax, 46h ; 'F'
0x1800ab4ae  mov     cl, [rax]
0x1800ab4b0  test    cl, cl
0x1800ab4b2  jz      short loc_1800AB4D7
0x1800ab4b4  mov     esi, 2Fh ; '/'
0x1800ab4b9  cmp     cl, sil
0x1800ab4bc  jnz     short loc_1800AB4C1
0x1800ab4be  mov     byte ptr [rax], 5Ch ; '\'
0x1800ab4c1  mov     rcx, rax; lpsz
0x1800ab4c4  call    cs:__imp_CharNextA
0x1800ab4ca  mov     cl, [rax]
0x1800ab4cc  test    cl, cl
0x1800ab4ce  jnz     short loc_1800AB4B9
0x1800ab4d0  lea     rsi, [rdi+0FB4h]
0x1800ab4d7  mov     r8, [r14+10h]
0x1800ab4db  test    r8, r8
0x1800ab4de  jz      short loc_1800AB4E6
0x1800ab4e0  add     r8, 26h ; '&'
0x1800ab4e4  jmp     short loc_1800AB4ED
0x1800ab4e6  mov     r8, [r15]
0x1800ab4e9  add     r8, 46h ; 'F'; pszSrc
0x1800ab4ed  mov     rdx, rbx; cchDest
0x1800ab4f0  lea     rcx, [rbp+0F90h+var_F20]; pszDest
0x1800ab4f4  call    StringCchCopyA
0x1800ab4f9  mov     r8, [r14+10h]
0x1800ab4fd  mov     eax, [r14+3Ch]
0x1800ab501  test    r8, r8
0x1800ab504  jz      short loc_1800AB53D
0x1800ab506  test    eax, eax
0x1800ab508  jz      short loc_1800AB533
0x1800ab50a  add     r8, 26h ; '&'
0x1800ab50e  lea     rcx, [rbp+0F90h+pszSrc]; pszDest
0x1800ab515  mov     edx, ebx; cchDest
0x1800ab517  call    ExtractFilename
0x1800ab51c  mov     rcx, [r14+10h]
0x1800ab520  lea     r8, [rbp+0F90h+pszSrc]; pszSrc
0x1800ab527  add     rcx, 26h ; '&'; pszDest
0x1800ab52b  mov     rdx, rbx; cchDest
0x1800ab52e  call    StringCchCopyA
0x1800ab533  mov     r8, [r14+10h]
0x1800ab537  add     r8, 26h ; '&'
0x1800ab53b  jmp     short loc_1800AB575
0x1800ab53d  test    eax, eax
0x1800ab53f  jz      short loc_1800AB56E
0x1800ab541  mov     r8, [r15]
0x1800ab544  lea     rcx, [rbp+0F90h+pszSrc]; pszDest
0x1800ab54b  add     r8, 46h ; 'F'
0x1800ab54f  mov     edx, ebx; cchDest
0x1800ab551  call    ExtractFilename
0x1800ab556  mov     rcx, [r15]
0x1800ab559  lea     r8, [rbp+0F90h+pszSrc]; pszSrc
0x1800ab560  add     rcx, 46h ; 'F'; pszDest
0x1800ab564  mov     edx, 800h; cchDest
0x1800ab569  call    StringCchCopyA
0x1800ab56e  mov     r8, [r15]
0x1800ab571  add     r8, 46h ; 'F'; pszSrc
0x1800ab575  mov     rdx, rbx; cchDest
0x1800ab578  mov     rcx, rsi; pszDest
0x1800ab57b  call    StringCchCatA
0x1800ab580  movzx   eax, word ptr [rdi+157Eh]
0x1800ab587  mov     [rbp+0F90h+var_F2C], eax
0x1800ab58a  movzx   eax, word ptr [rdi+157Ch]
0x1800ab591  mov     [rbp+0F90h+var_F28], eax
0x1800ab594  mov     rax, [r14+10h]
0x1800ab598  test    rax, rax
0x1800ab59b  jz      short loc_1800AB5A8
0x1800ab59d  mov     eax, [rax+12Ah]
0x1800ab5a3  mov     [rbp+0F90h+var_F24], eax
0x1800ab5a6  jmp     short loc_1800AB5B1
0x1800ab5a8  mov     rax, [r15]
0x1800ab5ab  mov     ecx, [rax+18h]
0x1800ab5ae  mov     [rbp+0F90h+var_F24], ecx
0x1800ab5b1  mov     r8, rsi; pszSrc
0x1800ab5b4  lea     rcx, [rsp+1090h+var_1030]; pszDest
0x1800ab5b9  mov     rdx, rbx; cchDest
0x1800ab5bc  call    StringCchCopyA
0x1800ab5c1  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800ab5c5  cmp     [r14+38h], r13d
0x1800ab5c9  jnz     loc_1800AB875
0x1800ab5cf  cmp     [rdi+28h], r13d
0x1800ab5d3  jnz     loc_1800AB875
0x1800ab5d9  cmp     [rdi+30h], r13d
0x1800ab5dd  jnz     loc_1800AB875
0x1800ab5e3  mov     rax, [rdi+1338h]
0x1800ab5ea  test    rax, rax
0x1800ab5ed  jz      short loc_1800AB62D
0x1800ab5ef  mov     rdx, [rdi+1340h]
0x1800ab5f6  lea     rcx, [rsp+1090h+var_1030]
0x1800ab5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab600  lea     r8, [rsp+1090h+var_1030]; pszSrc
0x1800ab605  mov     rdx, rbx; cchDest
0x1800ab608  mov     rcx, rsi; pszDest
0x1800ab60b  call    StringCchCopyA
0x1800ab610  mov     rax, [r14+10h]
0x1800ab614  mov     r10d, [rbp+0F90h+var_F24]
0x1800ab618  test    rax, rax
0x1800ab61b  jz      short loc_1800AB626
0x1800ab61d  mov     [rax+12Ah], r10d
0x1800ab624  jmp     short loc_1800AB62D
0x1800ab626  mov     rax, [r15]
0x1800ab629  mov     [rax+18h], r10d
0x1800ab62d  mov     [rsp+1090h+var_1050], r13d
0x1800ab632  lea     r9, [rbp+0F90h+String2]
0x1800ab639  mov     [rsp+1090h+var_1058], r13
0x1800ab63e  lea     rdx, [rbp+0F90h+pszSrc]
0x1800ab645  mov     dword ptr [rsp+1090h+hTemplateFile], r13d
0x1800ab64a  mov     r8d, ebx
0x1800ab64d  mov     qword ptr [rsp+1090h+dwFlagsAndAttributes], r13
0x1800ab652  mov     rcx, rsi
0x1800ab655  mov     [rsp+1090h+dwCreationDisposition], ebx
0x1800ab659  call    DBCS_splitpath
0x1800ab65e  lea     r9, [rbp+0F90h+String2]
0x1800ab665  mov     qword ptr [rsp+1090h+dwFlagsAndAttributes], r13; STRSAFE_LPCSTR
0x1800ab66a  lea     r8, [rbp+0F90h+pszSrc]
0x1800ab671  mov     qword ptr [rsp+1090h+dwCreationDisposition], r13; pszSrc
0x1800ab676  lea     rcx, [rbp+0F90h+FileName]; pszDest
0x1800ab67d  call    DBCS_makepath
0x1800ab682  lea     r8, [rbp+0F90h+FileName]; pszSrc
0x1800ab689  mov     rdx, rbx; cchDest
0x1800ab68c  lea     rcx, [rbp+0F90h+String2]; pszDest
0x1800ab693  call    StringCchCopyA
0x1800ab698  mov     ebx, r13d
0x1800ab69b  mov     edx, 5Ch ; '\'
0x1800ab6a0  lea     rcx, [rbp+0F90h+FileName]
0x1800ab6a7  call    DBCS_strrchr
0x1800ab6ac  test    rax, rax
0x1800ab6af  jz      short loc_1800AB6EE
0x1800ab6b1  lea     rcx, [rbp+0F90h+FileName]; lpFileName
0x1800ab6b8  mov     [rax], r13b
0x1800ab6bb  call    cs:__imp_GetFileAttributesA
0x1800ab6c1  cmp     eax, 0FFFFFFFFh
0x1800ab6c4  jz      short loc_1800AB6E3
0x1800ab6c6  lea     r8, [rbp+0F90h+FileName]; pszSrc
0x1800ab6cd  mov     edx, 104h; cchDest
0x1800ab6d2  lea     rcx, [rbp+0F90h+PathName]; pszDest
0x1800ab6d9  call    StringCchCopyA
0x1800ab6de  mov     ebx, 1
0x1800ab6e3  test    ebx, ebx
0x1800ab6e5  jz      short loc_1800AB69B
0x1800ab6e7  mov     ebx, 104h
0x1800ab6ec  jmp     short loc_1800AB708
0x1800ab6ee  mov     ebx, 104h
0x1800ab6f3  lea     r8, [rbp+0F90h+FileName]; pszSrc
0x1800ab6fa  mov     edx, ebx; cchDest
0x1800ab6fc  lea     rcx, [rbp+0F90h+PathName]; pszDest
0x1800ab703  call    StringCchCopyA
0x1800ab708  lea     r8, asc_1800E8550; "\\"
0x1800ab70f  mov     rdx, rbx; cchDest
0x1800ab712  lea     rcx, [rbp+0F90h+PathName]; pszDest
0x1800ab719  call    StringCchCatA
0x1800ab71e  lea     r8, [rbp+0F90h+String2]; pszSrc
0x1800ab725  mov     rdx, rbx; cchDest
0x1800ab728  lea     rcx, [rbp+0F90h+FileName]; pszDest
0x1800ab72f  call    StringCchCopyA
0x1800ab734  lea     rax, [rbp+0F90h+FileName]
0x1800ab73b  mov     rcx, r12
0x1800ab73e  inc     rcx
0x1800ab741  cmp     [rax+rcx], r13b
0x1800ab745  jnz     short loc_1800AB73E
0x1800ab747  lea     rdx, [rbp+0F90h+PathName]
0x1800ab74e  mov     rax, r12
0x1800ab751  inc     rax
0x1800ab754  cmp     [rdx+rax], r13b
0x1800ab758  jnz     short loc_1800AB751
0x1800ab75a  cmp     rax, rcx
0x1800ab75d  jnb     loc_1800AB803
0x1800ab763  lea     rbx, [rbp+0F90h+PathName]
0x1800ab76a  add     rbx, rax
0x1800ab76d  lea     rsi, [rbp+0F90h+FileName]
0x1800ab774  add     rsi, rax
0x1800ab777  mov     al, [rsi]
0x1800ab779  jmp     short loc_1800AB7A6
0x1800ab77b  cmp     al, 5Ch ; '\'
0x1800ab77d  jz      short loc_1800AB7AA
0x1800ab77f  mov     [rbx], al
0x1800ab781  inc     rbx
0x1800ab784  mov     cl, [rsi]; TestChar
0x1800ab786  call    cs:__imp_IsDBCSLeadByte
0x1800ab78c  test    eax, eax
0x1800ab78e  jz      short loc_1800AB798
0x1800ab790  mov     al, [rsi+1]
0x1800ab793  mov     [rbx], al
0x1800ab795  inc     rbx
0x1800ab798  mov     rcx, rsi; lpsz
0x1800ab79b  call    cs:__imp_CharNextA
0x1800ab7a1  mov     rsi, rax
0x1800ab7a4  mov     al, [rax]
0x1800ab7a6  test    al, al
0x1800ab7a8  jnz     short loc_1800AB77B
0x1800ab7aa  xor     edx, edx; lpSecurityAttributes
0x1800ab7ac  mov     [rbx], r13b
0x1800ab7af  lea     rcx, [rbp+0F90h+PathName]; lpPathName
0x1800ab7b6  call    cs:__imp_CreateDirectoryA
0x1800ab7bc  test    eax, eax
0x1800ab7be  jz      short loc_1800AB7DF
0x1800ab7c0  mov     ebx, 104h
0x1800ab7c5  lea     r8, asc_1800E8550; "\\"
0x1800ab7cc  mov     edx, ebx; cchDest
0x1800ab7ce  lea     rcx, [rbp+0F90h+PathName]; pszDest
0x1800ab7d5  call    StringCchCatA
0x1800ab7da  jmp     loc_1800AB734
0x1800ab7df  mov     [r14+10h], r13
0x1800ab7e3  mov     [r15], r13
0x1800ab7e6  call    cs:__imp_GetLastError
0x1800ab7ec  mov     ecx, 1Ch
0x1800ab7f1  cmp     eax, 0CEh
0x1800ab7f6  lea     edx, [rcx+17h]
0x1800ab7f9  cmovz   ecx, edx
0x1800ab7fc  mov     eax, ecx
0x1800ab7fe  jmp     loc_1800ABD5B
0x1800ab803  lea     rsi, [rdi+0FB4h]
0x1800ab80a  mov     rdx, rsi; lpString2
0x1800ab80d  lea     rcx, [rdi+208h]; lpString1
0x1800ab814  call    cs:__imp_lstrcmpiA
0x1800ab81a  test    eax, eax
0x1800ab81c  jz      short loc_1800AB86E
0x1800ab81e  lea     rcx, [rdi+10B8h]; pszDest
0x1800ab825  mov     r8, rsi; pszSrc
0x1800ab828  mov     rdx, rbx; cchDest
0x1800ab82b  call    StringCchCopyA
0x1800ab830  mov     eax, 3
0x1800ab835  mov     [rsp+1090h+hTemplateFile], r13; hTemplateFile
  ... truncated ...
```
