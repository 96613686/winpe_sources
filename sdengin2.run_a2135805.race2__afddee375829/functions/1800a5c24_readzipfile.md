# readzipfile

- ea: `0x1800a5c24`
- end: `0x1800a6c4a`
- name: `readzipfile`
- size: `4134`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1800a72b0`

## callees

- `0x18009fa48`
- `0x1800a1a1c`
- `0x1800a236c`
- `0x1800a2458`
- `0x1800a2834`
- `0x1800a4640`
- `0x1800a4714`
- `0x1800a48ec`
- `0x1800a5c24`
- `0x1800a8544`
- `0x1800a85ac`
- `0x1800a8d00`
- `0x1800cf546`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!free` at `0x1800a67de`
- `msvcrt!free` at `0x1800a6896`
- `msvcrt!free` at `0x1800a6928`
- `msvcrt!free` at `0x1800a6942`
- `msvcrt!free` at `0x1800a67de`
- `msvcrt!free` at `0x1800a6896`
- `msvcrt!free` at `0x1800a6928`
- `msvcrt!free` at `0x1800a6942`
- `msvcrt!malloc` at `0x1800a5f69`
- `msvcrt!malloc` at `0x1800a6102`
- `msvcrt!malloc` at `0x1800a6128`
- `msvcrt!malloc` at `0x1800a6262`
- `msvcrt!malloc` at `0x1800a6775`
- `msvcrt!malloc` at `0x1800a6806`
- `msvcrt!malloc` at `0x1800a68bb`
- `msvcrt!malloc` at `0x1800a6b55`
- `msvcrt!malloc` at `0x1800a6b93`
- `msvcrt!malloc` at `0x1800a5f69`
- `msvcrt!malloc` at `0x1800a6102`
- `msvcrt!malloc` at `0x1800a6128`
- `msvcrt!malloc` at `0x1800a6262`
- `msvcrt!malloc` at `0x1800a6775`
- `msvcrt!malloc` at `0x1800a6806`
- `msvcrt!malloc` at `0x1800a68bb`
- `msvcrt!malloc` at `0x1800a6b55`
- `msvcrt!malloc` at `0x1800a6b93`
- `msvcrt!qsort` at `0x1800a6c1b`
- `msvcrt!qsort` at `0x1800a6c1b`
- `KERNEL32!lstrlenA` at `0x1800a624e`
- `KERNEL32!lstrlenA` at `0x1800a624e`
- `KERNEL32!CloseHandle` at `0x1800a6b35`
- `KERNEL32!CloseHandle` at `0x1800a6bd9`
- `KERNEL32!CloseHandle` at `0x1800a6b35`
- `KERNEL32!CloseHandle` at `0x1800a6bd9`
- `USER32!OemToCharBuffA` at `0x1800a6237`
- `USER32!OemToCharBuffA` at `0x1800a67b7`
- `USER32!OemToCharBuffA` at `0x1800a6237`
- `USER32!OemToCharBuffA` at `0x1800a67b7`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a5e5e`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a5e5e`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800a5d08`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800a5ddd`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800a5d08`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800a5ddd`

## pseudocode

```c
__int64 __fastcall readzipfile(__int64 a1)
{
  __int16 v1; // ax
  __int64 v2; // r15
  unsigned __int16 v4; // si
  const char *v5; // rdi
  const CHAR *v6; // rcx
  unsigned int v7; // eax
  __int64 result; // rax
  const char *v9; // rcx
  const CHAR *v10; // rcx
  unsigned int v11; // r14d
  HANDLE FileA; // rdi
  __int64 v13; // r13
  unsigned __int64 v14; // rcx
  char *v15; // rax
  char *v16; // rsi
  __int16 v17; // cx
  unsigned __int16 v18; // cx
  unsigned __int64 v19; // r15
  __int64 v20; // r12
  int v21; // eax
  _QWORD *v22; // rax
  _BYTE *v23; // rax
  size_t v24; // rcx
  void *v25; // rax
  _QWORD *v26; // rcx
  char *v27; // rax
  char *v28; // r10
  __int64 v29; // rax
  bool v30; // zf
  int v31; // ecx
  __int64 v32; // rdx
  char *v33; // rcx
  _BYTE *v34; // rsi
  char v35; // al
  __int64 *v36; // r15
  __int64 v37; // rsi
  unsigned __int64 v38; // rcx
  __int64 v39; // rax
  bool v40; // cc
  size_t *v41; // r12
  size_t v42; // rdx
  CHAR *v43; // r15
  void *v44; // rax
  int SomeBytes; // eax
  void *v46; // rcx
  size_t v47; // r8
  void *v48; // rax
  int v49; // ecx
  __int64 v50; // rcx
  _QWORD *v51; // rax
  _QWORD *v52; // rcx
  size_t v53; // rsi
  void *v54; // rax
  __int64 i; // rax
  __int64 v56; // [rsp+48h] [rbp-51h] BYREF
  int v57; // [rsp+50h] [rbp-49h]
  unsigned __int16 v58; // [rsp+54h] [rbp-45h]
  __int64 v59; // [rsp+58h] [rbp-41h] BYREF
  size_t cchDest; // [rsp+60h] [rbp-39h]
  STRSAFE_LPCSTR pszSrc; // [rsp+68h] [rbp-31h]
  __int16 v62; // [rsp+70h] [rbp-29h]
  unsigned __int16 v63; // [rsp+72h] [rbp-27h]
  unsigned __int16 v64; // [rsp+74h] [rbp-25h] BYREF
  unsigned __int16 v65; // [rsp+76h] [rbp-23h]
  unsigned __int16 v66; // [rsp+78h] [rbp-21h]
  unsigned __int16 v67; // [rsp+7Ah] [rbp-1Fh]
  unsigned __int16 v68; // [rsp+7Ch] [rbp-1Dh]
  unsigned __int16 v69; // [rsp+7Eh] [rbp-1Bh]
  unsigned __int16 v70; // [rsp+80h] [rbp-19h]
  unsigned __int16 v71; // [rsp+82h] [rbp-17h]
  unsigned __int16 v72; // [rsp+84h] [rbp-15h]
  unsigned __int16 v73; // [rsp+86h] [rbp-13h]
  unsigned __int16 v74; // [rsp+88h] [rbp-11h]
  unsigned __int16 v75; // [rsp+8Ah] [rbp-Fh]
  unsigned __int16 v76; // [rsp+8Ch] [rbp-Dh]
  unsigned __int16 v77; // [rsp+8Eh] [rbp-Bh]
  __int16 v78; // [rsp+90h] [rbp-9h]
  unsigned __int8 v79; // [rsp+92h] [rbp-7h]
  unsigned __int8 v80; // [rsp+93h] [rbp-6h]
  unsigned __int16 v81; // [rsp+94h] [rbp-5h]
  unsigned __int8 v82; // [rsp+96h] [rbp-3h]
  unsigned __int8 v83; // [rsp+97h] [rbp-2h]
  unsigned __int16 v84; // [rsp+98h] [rbp-1h]

  v1 = *(_WORD *)(a1 + 3740);
  v2 = a1 + 3624;
  v57 = 0;
  v56 = 0;
  *(_QWORD *)(a1 + 3600) = 0;
  *(_QWORD *)(a1 + 3624) = 0;
  *(_QWORD *)(a1 + 3640) = 0;
  if ( v1 >= 0 )
  {
    if ( !(unsigned int)filetime(*(STRSAFE_LPCSTR *)(a1 + 3592)) || v56 )
    {
      result = ValidZIPTest(*(LPCSTR *)(a1 + 3592));
      if ( (_DWORD)result )
        return result;
    }
    else if ( !DeleteFileA(*(LPCSTR *)(a1 + 3592)) )
    {
      return 3;
    }
    result = MakeZipFileDir(*(STRSAFE_LPCSTR *)(a1 + 3592));
    if ( (_DWORD)result )
      return result;
    goto LABEL_24;
  }
  *(_DWORD *)(a1 + 3744) = 0;
  *(_QWORD *)(a1 + 3748) = 0xFFFF;
  *(_DWORD *)(a1 + 3760) = 0;
  *(_QWORD *)(a1 + 3768) = 0;
  *(_QWORD *)(a1 + 3776) = 0;
  *(_QWORD *)(a1 + 496) = 0x200000;
  if ( (v1 & 0x4000) == 0 && (unsigned int)dzMsgCB(*(_QWORD *)(a1 + 3168), 0, 1, -1) != 1 )
    return 9;
  if ( (unsigned int)filetime(*(STRSAFE_LPCSTR *)(a1 + 3592)) && !DeleteFileA(*(LPCSTR *)(a1 + 3592)) )
    return 3;
  v4 = *(_WORD *)(a1 + 3740);
  v5 = (const char *)(a1 + 224);
  v6 = (const CHAR *)(a1 + 224);
  if ( (v4 & 0x4000) == 0 )
    v6 = *(const CHAR **)(a1 + 3592);
  v7 = dzDriveFromPath(v6);
  if ( !(unsigned int)CleanTargetMedia(v7, v4, a1) )
  {
    if ( !*(_DWORD *)(a1 + 208) )
      return 19;
    return 9;
  }
  v9 = (const char *)(a1 + 224);
  if ( (*(_WORD *)(a1 + 3740) & 0x4000) == 0 )
    v9 = *(const char **)(a1 + 3592);
  result = MakeZipFileDir(v9);
  if ( (_DWORD)result )
    return result;
  if ( (*(_WORD *)(a1 + 3740) & 0x4000) == 0 )
    v5 = *(const char **)(a1 + 3592);
  *(_QWORD *)(a1 + 496) = RemainingDiskSpace(v5);
LABEL_24:
  v10 = *(const CHAR **)(a1 + 3592);
  if ( !v10 )
    return 0;
  if ( !*v10 )
    return 0;
  v11 = 3;
  FileA = CreateFileA(v10, 0x80000000, 0, 0, 3u, 0x80u, 0);
  if ( FileA == (HANDLE)-1LL )
    return 0;
  if ( *(_DWORD *)(a1 + 3540) )
    filetime(*(STRSAFE_LPCSTR *)(a1 + 3592));
  v13 = 0;
  *(_QWORD *)(a1 + 3632) = 0;
  while ( 1 )
  {
    if ( (unsigned int)GetSomeBytes(FileA) )
      goto LABEL_30;
    LOBYTE(v62) = 0;
    if ( !(unsigned int)GetSomeBytes(FileA) )
      break;
    v14 = (unsigned __int8)v62 | ((HIBYTE(v62) | ((unsigned __int64)v63 << 8)) << 8);
    if ( v14 == 67324752 || v14 == 101010256 )
      break;
    if ( DZSetFilePointer(FileA, -3, 1) == -1 )
    {
LABEL_155:
      v11 = 11;
      goto LABEL_156;
    }
LABEL_30:
    ++v13;
  }
  v59 = v2;
  *(_QWORD *)(a1 + 3600) = v13;
LABEL_38:
  while ( ((unsigned __int8)v62 | (HIBYTE(v62) << 8) | (v63 << 16)) == 0x4034B50 )
  {
    v15 = (char *)malloc(0xA0u);
    v16 = v15;
    if ( !v15 )
      goto LABEL_153;
    memset_0(v15, 0, 0xA0u);
    if ( !(unsigned int)GetSomeBytes(FileA) )
    {
LABEL_86:
      if ( !*(_DWORD *)(a1 + 3540) )
        goto LABEL_155;
      v36 = (__int64 *)(a1 + 3624);
      v37 = *(_QWORD *)(a1 + 3624);
LABEL_125:
      v40 = *(_DWORD *)(a1 + 3540) <= 0;
      goto LABEL_126;
    }
    v17 = v62;
    *(_WORD *)v16 = 20;
    *((_WORD *)v16 + 1) = v17;
    v18 = v63;
    *((_WORD *)v16 + 35) = v63;
    *((_WORD *)v16 + 2) = v18;
    v58 = v18;
    *((_WORD *)v16 + 3) = v64;
    *((_DWORD *)v16 + 2) = (unsigned __int8)v65 | (HIBYTE(v65) << 8) | (v66 << 16);
    *((_DWORD *)v16 + 3) = (unsigned __int8)v67 | (HIBYTE(v67) << 8) | (v68 << 16);
    v19 = (unsigned __int8)v69 | ((HIBYTE(v69) | ((unsigned __int64)v70 << 8)) << 8);
    *((_QWORD *)v16 + 2) = v19;
    *((_QWORD *)v16 + 3) = (unsigned __int8)v71 | ((HIBYTE(v71) | ((unsigned __int64)v72 << 8)) << 8);
    v20 = v73;
    *((_QWORD *)v16 + 4) = v73;
    v21 = (unsigned __int8)v57;
    *((_QWORD *)v16 + 5) = v74;
    *((_QWORD *)v16 + 7) = 0;
    *((_DWORD *)v16 + 16) = 0;
    *((_WORD *)v16 + 34) = 0;
    if ( !*(_DWORD *)(a1 + 3536) )
      v21 = v57;
    *((_DWORD *)v16 + 18) = v21;
    v22 = (_QWORD *)v59;
    *((_DWORD *)v16 + 32) = 0;
    v40 = *(_DWORD *)(a1 + 3540) <= 1;
    *v22 = v16;
    if ( !v40 )
      v19 = 0;
    v59 = (__int64)(v16 + 152);
    *((_QWORD *)v16 + 19) = 0;
    if ( !v20 )
      goto LABEL_156;
    v23 = malloc(v20 + 1);
    v56 = (__int64)v23;
    *((_QWORD *)v16 + 15) = v23;
    if ( !v23 )
      goto LABEL_153;
    v24 = *((_QWORD *)v16 + 5);
    if ( v24 )
    {
      v25 = malloc(v24);
      *((_QWORD *)v16 + 12) = v25;
      if ( !v25 )
        goto LABEL_153;
      v23 = (_BYTE *)v56;
    }
    *v23 = 0;
    if ( !(unsigned int)GetSomeBytes(FileA) )
      goto LABEL_155;
    v26 = v16 + 40;
    *(_BYTE *)(v20 + *((_QWORD *)v16 + 15)) = 0;
    if ( *((_QWORD *)v16 + 5) )
    {
      if ( !(unsigned int)GetSomeBytes(FileA) )
        goto LABEL_155;
      v26 = v16 + 40;
    }
    if ( *(_DWORD *)(a1 + 3540) )
    {
      *((_QWORD *)v16 + 13) = *((_QWORD *)v16 + 12);
      *((_QWORD *)v16 + 6) = *v26;
    }
    v56 = 0;
    *((_QWORD *)v16 + 17) = 0;
    if ( (unsigned int)ParseExtra64(*((void **)v16 + 12), 0, 0, (__int64)&v56) )
    {
      if ( *(_DWORD *)(a1 + 3540) )
      {
        *((_QWORD *)v16 + 6) = 0;
        *((_QWORD *)v16 + 13) = 0;
      }
      v19 = *((_QWORD *)v16 + 2);
      *((_QWORD *)v16 + 17) = v56;
    }
    if ( v19 && DZSetFilePointer(FileA, v19, 1) == -1 )
      goto LABEL_73;
    if ( !*(_DWORD *)(a1 + 620) )
      OemToCharBuffA(*((LPCSTR *)v16 + 15), *((LPSTR *)v16 + 15), v20);
    pszSrc = (STRSAFE_LPCSTR)*((_QWORD *)v16 + 15);
    cchDest = (unsigned int)(lstrlenA(pszSrc) + 1);
    v27 = (char *)malloc(cchDest);
    v28 = v27;
    if ( v27 )
      StringCchCopyA(v27, cchDest, pszSrc);
    *((_QWORD *)v16 + 11) = v28;
    if ( !v28 )
      goto LABEL_153;
    v29 = *((_QWORD *)v16 + 5) + 30LL;
    *((_QWORD *)v16 + 10) = v13;
    ++*(_QWORD *)(a1 + 3632);
    v13 += v19 + v56 + v20 + v29;
    if ( (v58 & 8) != 0 )
    {
      if ( v19 )
      {
        if ( DZSetFilePointer(FileA, v13, 0) == -1 || !(unsigned int)GetSomeBytes(FileA) )
          goto LABEL_155;
        v30 = ((unsigned __int8)v62 | (HIBYTE(v62) << 8) | (v63 << 16)) == 134695760;
      }
      else
      {
        while ( 1 )
        {
          while ( (unsigned int)GetSomeBytes(FileA) )
            ;
          LOBYTE(v62) = 0;
          if ( !(unsigned int)GetSomeBytes(FileA)
            || ((unsigned __int8)v62 | (HIBYTE(v62) << 8) | (v63 << 16)) == 0x8074B50 )
          {
            break;
          }
          if ( DZSetFilePointer(FileA, -15, 1) == -1 )
            goto LABEL_73;
        }
        v19 = (unsigned __int8)v66 | ((HIBYTE(v66) | ((unsigned __int64)v67 << 8)) << 8);
        v13 += v19;
        v30 = DZSetFilePointer(FileA, 0, 1) == v13 + 16;
      }
      if ( !v30 )
        goto LABEL_156;
      if ( *(_DWORD *)(a1 + 3540) )
      {
        v31 = (unsigned __int8)v64 | (HIBYTE(v64) << 8) | (v65 << 16);
        *((_QWORD *)v16 + 2) = v19;
        *((_DWORD *)v16 + 3) = v31;
        *((_QWORD *)v16 + 3) = (unsigned __int8)v68 | ((HIBYTE(v68) | ((unsigned __int64)v69 << 8)) << 8);
      }
      else
      {
        v32 = 12;
        v33 = (char *)&v64;
        v34 = v16 + 10;
        do
        {
          v35 = *v33++;
          *v34++ = v35;
          --v32;
        }
        while ( v32 );
      }
      v13 += 16;
    }
    else if ( *(int *)(a1 + 3540) > 1 )
    {
      while ( 1 )
      {
        if ( !(unsigned int)GetSomeBytes(FileA) )
        {
          LOBYTE(v62) = 0;
          if ( !(unsigned int)GetSomeBytes(FileA)
            || (v38 = (unsigned __int8)v62 | ((HIBYTE(v62) | ((unsigned __int64)v63 << 8)) << 8), v38 == 67324752)
            || v38 == 33639248 )
          {
            v39 = v13 - *((_QWORD *)v16 + 10) - *((_QWORD *)v16 + 5) - v20 - v56 - 30;
            if ( v39 != *((_QWORD *)v16 + 2) )
              *((_QWORD *)v16 + 2) = v39;
            goto LABEL_38;
          }
          if ( DZSetFilePointer(FileA, -3, 1) == -1 )
            goto LABEL_155;
        }
        ++v13;
      }
    }
    if ( !(unsigned int)GetSomeBytes(FileA) )
      goto LABEL_86;
  }
  v36 = (__int64 *)(a1 + 3624);
  v37 = *(_QWORD *)(a1 + 3624);
  v40 = *(_DWORD *)(a1 + 3540) <= 0;
  if ( !*(_DWORD *)(a1 + 3540) )
  {
    while ( 1 )
    {
      if ( ((unsigned __int8)v62 | (HIBYTE(v62) << 8) | (v63 << 16)) != 0x2014B50 )
      {
        v36 = (__int64 *)(a1 + 3624);
        goto LABEL_125;
      }
      if ( !v37 )
        goto LABEL_156;
      if ( !(unsigned int)GetSomeBytes(FileA) )
        goto LABEL_155;
      v41 = (size_t *)(v37 + 48);
      *(_WORD *)v37 = v62;
      *(_WORD *)(v37 + 2) = v63;
      *(_WORD *)(v37 + 4) = v64;
      *(_WORD *)(v37 + 70) = v64;
      *(_WORD *)(v37 + 6) = v65;
      *(_DWORD *)(v37 + 8) = (unsigned __int8)v66 | (HIBYTE(v66) << 8) | (v67 << 16);
      *(_DWORD *)(v37 + 12) = (unsigned __int8)v68 | (HIBYTE(v68) << 8) | (v69 << 16);
      *(_QWORD *)(v37 + 16) = (unsigned __int8)v70 | ((HIBYTE(v70) | ((unsigned __int64)v71 << 8)) << 8);
      *(_QWORD *)(v37 + 24) = (unsigned __int8)v72 | ((HIBYTE(v72) | ((unsigned __int64)v73 << 8)) << 8);
      v42 = v74;
      *(_QWORD *)(v37 + 32) = v74;
      cchDest = v42;
      *(_QWORD *)(v37 + 48) = v75;
      *(_QWORD *)(v37 + 56) = v76;
      *(_DWORD *)(v37 + 64) = v77;
      *(_WORD *)(v37 + 68) = v78;
      *(_DWORD *)(v37 + 72) = v79 | (v80 << 8) | (v81 << 16);
      v59 = v82 | ((v83 | ((unsigned __int64)v84 << 8)) << 8);
      v43 = (CHAR *)malloc(v42);
      if ( !v43 )
        goto LABEL_153;
      if ( !(unsigned int)GetSomeBytes(FileA) )
        break;
      if ( !*(_DWORD *)(a1 + 620) )
        OemToCharBuffA(v43, v43, *(_DWORD *)(v37 + 32));
      if ( memcmp_0(v43, *(const void **)(v37 + 120), *(_QWORD *)(v37 + 32)) )
        goto LABEL_123;
      free(v43);
      v56 = 0;
      *(_QWORD *)(v37 + 144) = 0;
      if ( *v41 )
      {
        v44 = malloc(*v41);
        *(_QWORD *)(v37 + 104) = v44;
        if ( !v44 )
          goto LABEL_153;
        SomeBytes = GetSomeBytes(FileA);
        v46 = *(void **)(v37 + 104);
        if ( !SomeBytes )
          goto LABEL_121;
        if ( (unsigned int)ParseExtra64(v46, (__int64)&v59, v37 + 64, (__int64)&v56) )
          *(_QWORD *)(v37 + 144) = v56;
        v47 = *(_QWORD *)(v37 + 40);
        if ( v47 == *v41 && !memcmp_0(*(const void **)(v37 + 96), *(const void **)(v37 + 104), v47) )
        {
          free(*(void **)(v37 + 104));
          *(_QWORD *)(v37 + 104) = *(_QWORD *)(v37 + 96);
        }
      }
      if ( *(_QWORD *)(v37 + 56) )
      {
        v48 = malloc(*(_QWORD *)(v37 + 56));
        *(_QWORD *)(v37 + 112) = v48;
        if ( !v48 )
          goto LABEL_153;
        if ( !(unsigned int)GetSomeBytes(FileA) )
        {
          v46 = *(void **)(v37 + 112);
LABEL_121:
          free(v46);
          goto LABEL_155;
        }
      }
      if ( *(_QWORD *)(v37 + 80) != v59 )
        goto LABEL_156;
      *(_DWORD *)(v37 + 128) = 0;
      v37 = *(_QWORD *)(v37 + 152);
      if ( !(unsigned int)GetSomeBytes(FileA) )
        goto LABEL_155;
    }
    v11 = 11;
LABEL_123:
    free(v43);
    goto LABEL_156;
  }
LABEL_126:
  if ( !v40 )
    goto LABEL_145;
  if ( v37 )
    goto LABEL_156;
  v49 = (unsigned __int8)v62 | (HIBYTE(v62) << 8) | (v63 << 16);
  if ( v49 != 101010256 )
  {
    if ( v49 == 101075792 )
    {
      do
      {
        while ( (unsigned int)GetSomeBytes(FileA) )
          ;
        LOBYTE(v62) = 0;
        if ( !(unsigned int)GetSomeBytes(FileA) )
          break;
        if ( ((unsigned __int8)v62 | (HIBYTE(v62) << 8) | (v63 << 16)) == 0x7064B50 )
        {
          while ( 1 )
          {
            while ( (unsigned int)GetSomeBytes(FileA) )
              ;
            LOBYTE(v62) = 0;
            if ( !(unsigned int)GetSomeBytes(FileA) )
              goto LABEL_73;
            if ( ((unsigned __int8)v62 | (HIBYTE(v62) << 8) | (v63 << 16)) == 0x6054B50 )
            {
              if ( !(unsigned int)GetSomeBytes(FileA) )
                goto LABEL_155;
              goto LABEL_145;
            }
            if ( DZSetFilePointer(FileA, -3, 1) == -1 )
              goto LABEL_73;
          }
        }
      }
      while ( DZSetFilePointer(FileA, -3, 1) != -1 );
LABEL_73:
      v11 = 2;
      goto LABEL_156;
    }
    goto LABEL_156;
  }
  if ( !(unsigned int)GetSomeBytes(FileA) )
    goto LABEL_155;
  if ( *(_QWORD *)(a1 + 3632) == v64
    && ((unsigned __int8)v68 | ((HIBYTE(v68) | ((unsigned __int64)v69 << 8)) << 8)) == v13 )
  {
LABEL_145:
    *(_QWORD *)(a1 + 3608) = v13;
    if ( *(_DWORD *)(a1 + 3540) )
    {
      *(_QWORD *)(a1 + 3640) = 0;
    }
    else
    {
      v53 = v70;
      v30 = v70 == 0;
      *(_QWORD *)(a1 + 3640) = v70;
      if ( !v30 )
      {
        v54 = malloc(v53);
        *(_QWORD *)(a1 + 3648) = v54;
        if ( !v54 )
        {
          *(_QWORD *)(a1 + 3640) = 0;
LABEL_153:
          v11 = 4;
          goto LABEL_156;
        }
        if ( !(unsigned int)GetSomeBytes(FileA) )
          goto LABEL_155;
      }
    }
    CloseHandle(FileA);
    v50 = *(_QWORD *)(a1 + 3632);
    if ( !v50 )
      return 0;
    v51 = malloc(8 * v50);
    *(_QWORD *)(a1 + 3656) = v51;
    v52 = v51;
    if ( !v51 )
      return 4;
    for ( i = *v36; i; i = *(_QWORD *)(i + 152) )
      *v52++ = i;
    qsort(*(void **)(a1 + 3656), *(_QWORD *)(a1 + 3632), 8u, zqcmp);
    return 0;
  }
  else
  {
LABEL_156:
    CloseHandle(FileA);
    return v11;
  }
}

```

## disassembly

```asm
0x1800a5c24  push    rbp
0x1800a5c26  push    rbx
0x1800a5c27  push    rsi
0x1800a5c28  push    rdi
0x1800a5c29  push    r12
0x1800a5c2b  push    r13
0x1800a5c2d  push    r14
0x1800a5c2f  push    r15
0x1800a5c31  lea     rbp, [rsp-1Fh]
0x1800a5c36  sub     rsp, 0B8h
0x1800a5c3d  mov     rax, cs:__security_cookie
0x1800a5c44  xor     rax, rsp
0x1800a5c47  mov     [rbp+57h+var_48], rax
0x1800a5c4b  movzx   eax, word ptr [rcx+0E9Ch]
0x1800a5c52  lea     r15, [rcx+0E28h]
0x1800a5c59  xor     r12d, r12d
0x1800a5c5c  mov     rbx, rcx
0x1800a5c5f  mov     [rbp+57h+var_A0], r12d
0x1800a5c63  mov     [rbp+57h+var_B0], r12b
0x1800a5c67  mov     [rbp+57h+var_A8], r12
0x1800a5c6b  mov     [rcx+0E10h], r12
0x1800a5c72  lea     esi, [r12+1]
0x1800a5c77  mov     [r15], r12
0x1800a5c7a  mov     [rcx+0E38h], r12
0x1800a5c81  test    ax, ax
0x1800a5c84  jns     loc_1800A5DB5
0x1800a5c8a  mov     r14d, 4000h
0x1800a5c90  mov     [rcx+0EA0h], r12d
0x1800a5c97  mov     qword ptr [rcx+0EA4h], 0FFFFh
0x1800a5ca2  mov     [rcx+0EB0h], r12d
0x1800a5ca9  mov     [rcx+0EB8h], r12
0x1800a5cb0  mov     [rcx+0EC0h], r12
0x1800a5cb7  mov     qword ptr [rcx+1F0h], 200000h
0x1800a5cc2  test    r14w, ax
0x1800a5cc6  jnz     short loc_1800A5CE6
0x1800a5cc8  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rcx
0x1800a5ccd  or      r9d, 0FFFFFFFFh
0x1800a5cd1  mov     rcx, [rcx+0C60h]
0x1800a5cd8  mov     r8d, esi
0x1800a5cdb  xor     edx, edx
0x1800a5cdd  call    dzMsgCB
0x1800a5ce2  cmp     eax, esi
0x1800a5ce4  jnz     short loc_1800A5D63
0x1800a5ce6  mov     rcx, [rbx+0E08h]; pszSrc
0x1800a5ced  lea     r8, [rbp+57h+var_A8]
0x1800a5cf1  mov     r9, rbx
0x1800a5cf4  lea     rdx, [rbp+57h+var_A0]
0x1800a5cf8  call    filetime
0x1800a5cfd  test    eax, eax
0x1800a5cff  jz      short loc_1800A5D1C
0x1800a5d01  mov     rcx, [rbx+0E08h]; lpFileName
0x1800a5d08  call    cs:__imp_DeleteFileA
0x1800a5d0f  nop     dword ptr [rax+rax+00h]
0x1800a5d14  test    eax, eax
0x1800a5d16  jz      loc_1800A5DED
0x1800a5d1c  movzx   esi, word ptr [rbx+0E9Ch]
0x1800a5d23  lea     rdi, [rbx+0E0h]
0x1800a5d2a  mov     rcx, rdi
0x1800a5d2d  test    r14w, si
0x1800a5d31  jnz     short loc_1800A5D3A
0x1800a5d33  mov     rcx, [rbx+0E08h]; lpszStart
0x1800a5d3a  call    dzDriveFromPath
0x1800a5d3f  mov     ecx, eax
0x1800a5d41  mov     r8, rbx
0x1800a5d44  movzx   edx, si
0x1800a5d47  call    CleanTargetMedia
0x1800a5d4c  test    eax, eax
0x1800a5d4e  jnz     short loc_1800A5D6D
0x1800a5d50  cmp     [rbx+0D0h], r12d
0x1800a5d57  jnz     short loc_1800A5D63
0x1800a5d59  mov     eax, 13h
0x1800a5d5e  jmp     loc_1800A6C29
0x1800a5d63  mov     eax, 9
0x1800a5d68  jmp     loc_1800A6C29
0x1800a5d6d  mov     rcx, rdi
0x1800a5d70  test    [rbx+0E9Ch], r14w
0x1800a5d78  jnz     short loc_1800A5D81
0x1800a5d7a  mov     rcx, [rbx+0E08h]; pszSrc
0x1800a5d81  call    MakeZipFileDir
0x1800a5d86  test    eax, eax
0x1800a5d88  jnz     loc_1800A6C29
0x1800a5d8e  test    [rbx+0E9Ch], r14w
0x1800a5d96  jnz     short loc_1800A5D9F
0x1800a5d98  mov     rdi, [rbx+0E08h]
0x1800a5d9f  mov     rcx, rdi; pszSrc
0x1800a5da2  call    RemainingDiskSpace
0x1800a5da7  mov     [rbx+1F0h], rax
0x1800a5dae  mov     esi, 1
0x1800a5db3  jmp     short loc_1800A5E22
0x1800a5db5  mov     rcx, [rcx+0E08h]; pszSrc
0x1800a5dbc  lea     r8, [rbp+57h+var_A8]
0x1800a5dc0  mov     r9, rbx
0x1800a5dc3  lea     rdx, [rbp+57h+var_A0]
0x1800a5dc7  call    filetime
0x1800a5dcc  test    eax, eax
0x1800a5dce  jz      short loc_1800A5DF7
0x1800a5dd0  cmp     [rbp+57h+var_A8], r12
0x1800a5dd4  jnz     short loc_1800A5DF7
0x1800a5dd6  mov     rcx, [rbx+0E08h]; lpFileName
0x1800a5ddd  call    cs:__imp_DeleteFileA
0x1800a5de4  nop     dword ptr [rax+rax+00h]
0x1800a5de9  test    eax, eax
0x1800a5deb  jnz     short loc_1800A5E0E
0x1800a5ded  mov     eax, 3
0x1800a5df2  jmp     loc_1800A6C29
0x1800a5df7  mov     rcx, [rbx+0E08h]; lpFileName
0x1800a5dfe  mov     rdx, rbx
0x1800a5e01  call    ValidZIPTest
0x1800a5e06  test    eax, eax
0x1800a5e08  jnz     loc_1800A6C29
0x1800a5e0e  mov     rcx, [rbx+0E08h]; pszSrc
0x1800a5e15  call    MakeZipFileDir
0x1800a5e1a  test    eax, eax
0x1800a5e1c  jnz     loc_1800A6C29
0x1800a5e22  mov     rcx, [rbx+0E08h]; lpFileName
0x1800a5e29  test    rcx, rcx
0x1800a5e2c  jz      loc_1800A6C27
0x1800a5e32  cmp     [rcx], r12b
0x1800a5e35  jz      loc_1800A6C27
0x1800a5e3b  mov     [rsp+0F0h+hTemplateFile], r12; hTemplateFile
0x1800a5e40  mov     r14d, 3
0x1800a5e46  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a5e4e  xor     r9d, r9d; lpSecurityAttributes
0x1800a5e51  xor     r8d, r8d; dwShareMode
0x1800a5e54  mov     [rsp+0F0h+dwCreationDisposition], r14d; dwCreationDisposition
0x1800a5e59  mov     edx, 80000000h; dwDesiredAccess
0x1800a5e5e  call    cs:__imp_CreateFileA
0x1800a5e65  nop     dword ptr [rax+rax+00h]
0x1800a5e6a  mov     rdi, rax
0x1800a5e6d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a5e71  jz      loc_1800A6C27
0x1800a5e77  cmp     [rbx+0DD4h], r12d
0x1800a5e7e  jz      short loc_1800A5E97
0x1800a5e80  mov     rcx, [rbx+0E08h]; pszSrc
0x1800a5e87  lea     r8, [rbp+57h+var_A8]
0x1800a5e8b  mov     r9, rbx
0x1800a5e8e  lea     rdx, [rbp+57h+var_A0]
0x1800a5e92  call    filetime
0x1800a5e97  mov     r13, r12
0x1800a5e9a  mov     [rbx+0E30h], r12
0x1800a5ea1  jmp     short loc_1800A5EAA
0x1800a5ea3  cmp     al, 50h ; 'P'
0x1800a5ea5  jz      short loc_1800A5EC0
0x1800a5ea7  add     r13, rsi
0x1800a5eaa  mov     r8, rsi
0x1800a5ead  lea     rdx, [rbp+57h+var_B0]
0x1800a5eb1  mov     rcx, rdi; hFile
0x1800a5eb4  call    GetSomeBytes
0x1800a5eb9  test    eax, eax
0x1800a5ebb  mov     al, [rbp+57h+var_B0]
0x1800a5ebe  jnz     short loc_1800A5EA3
0x1800a5ec0  mov     r8, r14
0x1800a5ec3  mov     byte ptr [rbp+57h+var_80], al
0x1800a5ec6  lea     rdx, [rbp+57h+var_80+1]
0x1800a5eca  mov     rcx, rdi; hFile
0x1800a5ecd  call    GetSomeBytes
0x1800a5ed2  test    eax, eax
0x1800a5ed4  jz      short loc_1800A5F2E
0x1800a5ed6  movzx   eax, byte ptr [rbp+57h+var_7E]
0x1800a5eda  movzx   ecx, byte ptr [rbp+57h+var_7E+1]
0x1800a5ede  shl     rcx, 8
0x1800a5ee2  or      rcx, rax
0x1800a5ee5  movzx   eax, byte ptr [rbp+57h+var_80+1]
0x1800a5ee9  shl     rcx, 8
0x1800a5eed  or      rcx, rax
0x1800a5ef0  movzx   eax, byte ptr [rbp+57h+var_80]
0x1800a5ef4  shl     rcx, 8
0x1800a5ef8  or      rcx, rax
0x1800a5efb  cmp     rcx, 4034B50h
0x1800a5f02  jz      short loc_1800A5F2E
0x1800a5f04  cmp     rcx, 6054B50h
0x1800a5f0b  jz      short loc_1800A5F2E
0x1800a5f0d  mov     r8d, esi
0x1800a5f10  mov     rdx, 0FFFFFFFFFFFFFFFDh
0x1800a5f17  mov     rcx, rdi
0x1800a5f1a  call    DZSetFilePointer
0x1800a5f1f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a5f23  jz      loc_1800A6BD0
0x1800a5f29  jmp     loc_1800A5EA7
0x1800a5f2e  mov     [rbp+57h+var_98], r15
0x1800a5f32  mov     [rbx+0E10h], r13
0x1800a5f39  movzx   eax, byte ptr [rbp+57h+var_7E]
0x1800a5f3d  movzx   ecx, byte ptr [rbp+57h+var_7E+1]
0x1800a5f41  shl     ecx, 8
0x1800a5f44  or      ecx, eax
0x1800a5f46  movzx   eax, byte ptr [rbp+57h+var_80+1]
0x1800a5f4a  shl     eax, 8
0x1800a5f4d  shl     ecx, 10h
0x1800a5f50  or      ecx, eax
0x1800a5f52  movzx   eax, byte ptr [rbp+57h+var_80]
0x1800a5f56  or      ecx, eax
0x1800a5f58  cmp     ecx, 4034B50h
0x1800a5f5e  jnz     loc_1800A656A
0x1800a5f64  mov     ecx, 0A0h; Size
0x1800a5f69  call    cs:__imp_malloc
0x1800a5f70  nop     dword ptr [rax+rax+00h]
0x1800a5f75  mov     rsi, rax
0x1800a5f78  test    rax, rax
0x1800a5f7b  jz      loc_1800A6BB2
0x1800a5f81  xor     edx, edx; Val
0x1800a5f83  mov     r8d, 0A0h; Size
0x1800a5f89  mov     rcx, rax; void *
0x1800a5f8c  call    memset_0
0x1800a5f91  mov     r8d, 1Ah
0x1800a5f97  lea     rdx, [rbp+57h+var_80]
0x1800a5f9b  mov     rcx, rdi; hFile
0x1800a5f9e  call    GetSomeBytes
0x1800a5fa3  test    eax, eax
0x1800a5fa5  jz      loc_1800A6494
0x1800a5fab  movzx   ecx, byte ptr [rbp+57h+var_80+1]
0x1800a5faf  movzx   eax, byte ptr [rbp+57h+var_80]
0x1800a5fb3  shl     cx, 8
0x1800a5fb7  or      cx, ax
0x1800a5fba  mov     word ptr [rsi], 14h
0x1800a5fbf  mov     [rsi+2], cx
0x1800a5fc3  movzx   ecx, byte ptr [rbp+57h+var_7E+1]
0x1800a5fc7  movzx   eax, byte ptr [rbp+57h+var_7E]
0x1800a5fcb  shl     cx, 8
0x1800a5fcf  or      cx, ax
0x1800a5fd2  mov     [rsi+46h], cx
0x1800a5fd6  mov     [rsi+4], cx
0x1800a5fda  movzx   eax, byte ptr [rbp+57h+var_7C]
0x1800a5fde  mov     [rbp+57h+var_9C], cx
0x1800a5fe2  movzx   ecx, byte ptr [rbp+57h+var_7C+1]
0x1800a5fe6  shl     cx, 8
0x1800a5fea  or      cx, ax
0x1800a5fed  mov     [rsi+6], cx
0x1800a5ff1  movzx   eax, byte ptr [rbp+57h+var_78]
0x1800a5ff5  movzx   ecx, byte ptr [rbp+57h+var_78+1]
0x1800a5ff9  shl     ecx, 8
0x1800a5ffc  or      ecx, eax
0x1800a5ffe  movzx   eax, byte ptr [rbp+57h+var_7A+1]
0x1800a6002  shl     ecx, 10h
0x1800a6005  shl     eax, 8
0x1800a6008  or      ecx, eax
0x1800a600a  movzx   eax, byte ptr [rbp+57h+var_7A]
0x1800a600e  or      ecx, eax
0x1800a6010  mov     [rsi+8], ecx
0x1800a6013  movzx   eax, byte ptr [rbp+57h+var_74]
0x1800a6017  movzx   ecx, byte ptr [rbp+57h+var_74+1]
0x1800a601b  shl     ecx, 8
0x1800a601e  or      ecx, eax
0x1800a6020  movzx   eax, byte ptr [rbp+57h+var_76+1]
0x1800a6024  shl     ecx, 10h
0x1800a6027  shl     eax, 8
0x1800a602a  or      ecx, eax
0x1800a602c  movzx   eax, byte ptr [rbp+57h+var_76]
0x1800a6030  or      ecx, eax
0x1800a6032  mov     [rsi+0Ch], ecx
0x1800a6035  movzx   eax, byte ptr [rbp+57h+var_70]
0x1800a6039  movzx   r15d, byte ptr [rbp+57h+var_70+1]
0x1800a603e  shl     r15, 8
0x1800a6042  or      r15, rax
0x1800a6045  movzx   eax, byte ptr [rbp+57h+var_72+1]
0x1800a6049  shl     r15, 8
0x1800a604d  or      r15, rax
0x1800a6050  movzx   eax, byte ptr [rbp+57h+var_72]
0x1800a6054  shl     r15, 8
0x1800a6058  or      r15, rax
0x1800a605b  mov     [rsi+10h], r15
0x1800a605f  movzx   eax, byte ptr [rbp+57h+var_6C]
0x1800a6063  movzx   ecx, byte ptr [rbp+57h+var_6C+1]
0x1800a6067  shl     rcx, 8
0x1800a606b  or      rcx, rax
0x1800a606e  movzx   eax, byte ptr [rbp+57h+var_6E+1]
0x1800a6072  shl     rcx, 8
0x1800a6076  or      rcx, rax
0x1800a6079  movzx   eax, byte ptr [rbp+57h+var_6E]
0x1800a607d  shl     rcx, 8
0x1800a6081  or      rcx, rax
0x1800a6084  mov     [rsi+18h], rcx
0x1800a6088  movzx   eax, byte ptr [rbp+57h+var_6A]
0x1800a608c  movzx   r12d, byte ptr [rbp+57h+var_6A+1]
0x1800a6091  shl     r12, 8
0x1800a6095  or      r12, rax
0x1800a6098  mov     [rsi+20h], r12
0x1800a609c  movzx   eax, byte ptr [rbp+57h+var_68]
0x1800a60a0  movzx   ecx, byte ptr [rbp+57h+var_68+1]
0x1800a60a4  shl     rcx, 8
0x1800a60a8  or      rcx, rax
0x1800a60ab  movzx   eax, byte ptr [rbp+57h+var_A0]
0x1800a60af  mov     [rsi+28h], rcx
0x1800a60b3  xor     ecx, ecx
0x1800a60b5  mov     [rsi+38h], rcx
0x1800a60b9  mov     [rsi+40h], ecx
0x1800a60bc  mov     [rsi+44h], cx
0x1800a60c0  cmp     [rbx+0DD0h], ecx
0x1800a60c6  jnz     short loc_1800A60CB
0x1800a60c8  mov     eax, [rbp+57h+var_A0]
0x1800a60cb  mov     [rsi+48h], eax
0x1800a60ce  mov     rax, [rbp+57h+var_98]
0x1800a60d2  mov     [rsi+80h], ecx
0x1800a60d8  cmp     dword ptr [rbx+0DD4h], 1
0x1800a60df  mov     [rax], rsi
0x1800a60e2  cmovg   r15, rcx
0x1800a60e6  lea     rax, [rsi+98h]
0x1800a60ed  mov     [rbp+57h+var_98], rax
0x1800a60f1  mov     [rax], rcx
0x1800a60f4  test    r12, r12
0x1800a60f7  jz      loc_1800A6BD6
  ... truncated ...
```
