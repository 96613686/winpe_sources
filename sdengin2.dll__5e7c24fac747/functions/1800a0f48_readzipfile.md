# readzipfile

- ea: `0x1800a0f48`
- end: `0x1800a1ee9`
- name: `readzipfile`
- size: `4001`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1800a24ac`

## callees

- `0x18009b2f0`
- `0x18009d12c`
- `0x18009da0c`
- `0x18009dadc`
- `0x18009de58`
- `0x18009fa74`
- `0x18009fb38`
- `0x18009fd0c`
- `0x1800a0f48`
- `0x1800a3608`
- `0x1800a3660`
- `0x1800a3cf0`
- `0x1800c97b6`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `msvcrt!free` at `0x1800a1ac0`
- `msvcrt!free` at `0x1800a1b6c`
- `msvcrt!free` at `0x1800a1bf2`
- `msvcrt!free` at `0x1800a1c06`
- `msvcrt!free` at `0x1800a1ac0`
- `msvcrt!free` at `0x1800a1b6c`
- `msvcrt!free` at `0x1800a1bf2`
- `msvcrt!free` at `0x1800a1c06`
- `msvcrt!malloc` at `0x1800a127b`
- `msvcrt!malloc` at `0x1800a140e`
- `msvcrt!malloc` at `0x1800a142e`
- `msvcrt!malloc` at `0x1800a1556`
- `msvcrt!malloc` at `0x1800a1a63`
- `msvcrt!malloc` at `0x1800a1ae2`
- `msvcrt!malloc` at `0x1800a1b8b`
- `msvcrt!malloc` at `0x1800a1e0d`
- `msvcrt!malloc` at `0x1800a1e45`
- `msvcrt!malloc` at `0x1800a127b`
- `msvcrt!malloc` at `0x1800a140e`
- `msvcrt!malloc` at `0x1800a142e`
- `msvcrt!malloc` at `0x1800a1556`
- `msvcrt!malloc` at `0x1800a1a63`
- `msvcrt!malloc` at `0x1800a1ae2`
- `msvcrt!malloc` at `0x1800a1b8b`
- `msvcrt!malloc` at `0x1800a1e0d`
- `msvcrt!malloc` at `0x1800a1e45`
- `msvcrt!qsort` at `0x1800a1ec1`
- `msvcrt!qsort` at `0x1800a1ec1`
- `KERNEL32!lstrlenA` at `0x1800a1548`
- `KERNEL32!lstrlenA` at `0x1800a1548`
- `KERNEL32!CloseHandle` at `0x1800a1df3`
- `KERNEL32!CloseHandle` at `0x1800a1e85`
- `KERNEL32!CloseHandle` at `0x1800a1df3`
- `KERNEL32!CloseHandle` at `0x1800a1e85`
- `USER32!OemToCharBuffA` at `0x1800a1537`
- `USER32!OemToCharBuffA` at `0x1800a1a9f`
- `USER32!OemToCharBuffA` at `0x1800a1537`
- `USER32!OemToCharBuffA` at `0x1800a1a9f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a1176`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a1176`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800a102c`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800a10fb`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800a102c`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800a10fb`

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
0x1800a0f48  push    rbp
0x1800a0f4a  push    rbx
0x1800a0f4b  push    rsi
0x1800a0f4c  push    rdi
0x1800a0f4d  push    r12
0x1800a0f4f  push    r13
0x1800a0f51  push    r14
0x1800a0f53  push    r15
0x1800a0f55  lea     rbp, [rsp-1Fh]
0x1800a0f5a  sub     rsp, 0B8h
0x1800a0f61  mov     rax, cs:__security_cookie
0x1800a0f68  xor     rax, rsp
0x1800a0f6b  mov     [rbp+57h+var_48], rax
0x1800a0f6f  movzx   eax, word ptr [rcx+0E9Ch]
0x1800a0f76  lea     r15, [rcx+0E28h]
0x1800a0f7d  xor     r12d, r12d
0x1800a0f80  mov     rbx, rcx
0x1800a0f83  mov     [rbp+57h+var_A0], r12d
0x1800a0f87  mov     [rbp+57h+var_B0], r12b
0x1800a0f8b  mov     [rbp+57h+var_A8], r12
0x1800a0f8f  mov     [rcx+0E10h], r12
0x1800a0f96  lea     esi, [r12+1]
0x1800a0f9b  mov     [r15], r12
0x1800a0f9e  mov     [rcx+0E38h], r12
0x1800a0fa5  test    ax, ax
0x1800a0fa8  jns     loc_1800A10D3
0x1800a0fae  mov     r14d, 4000h
0x1800a0fb4  mov     [rcx+0EA0h], r12d
0x1800a0fbb  mov     qword ptr [rcx+0EA4h], 0FFFFh
0x1800a0fc6  mov     [rcx+0EB0h], r12d
0x1800a0fcd  mov     [rcx+0EB8h], r12
0x1800a0fd4  mov     [rcx+0EC0h], r12
0x1800a0fdb  mov     qword ptr [rcx+1F0h], 200000h
0x1800a0fe6  test    r14w, ax
0x1800a0fea  jnz     short loc_1800A100A
0x1800a0fec  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], rcx
0x1800a0ff1  or      r9d, 0FFFFFFFFh
0x1800a0ff5  mov     rcx, [rcx+0C60h]
0x1800a0ffc  mov     r8d, esi
0x1800a0fff  xor     edx, edx
0x1800a1001  call    dzMsgCB
0x1800a1006  cmp     eax, esi
0x1800a1008  jnz     short loc_1800A1081
0x1800a100a  mov     rcx, [rbx+0E08h]; pszSrc
0x1800a1011  lea     r8, [rbp+57h+var_A8]
0x1800a1015  mov     r9, rbx
0x1800a1018  lea     rdx, [rbp+57h+var_A0]
0x1800a101c  call    filetime
0x1800a1021  test    eax, eax
0x1800a1023  jz      short loc_1800A103A
0x1800a1025  mov     rcx, [rbx+0E08h]; lpFileName
0x1800a102c  call    cs:__imp_DeleteFileA
0x1800a1032  test    eax, eax
0x1800a1034  jz      loc_1800A1105
0x1800a103a  movzx   esi, word ptr [rbx+0E9Ch]
0x1800a1041  lea     rdi, [rbx+0E0h]
0x1800a1048  mov     rcx, rdi
0x1800a104b  test    r14w, si
0x1800a104f  jnz     short loc_1800A1058
0x1800a1051  mov     rcx, [rbx+0E08h]; lpszStart
0x1800a1058  call    dzDriveFromPath
0x1800a105d  mov     ecx, eax
0x1800a105f  mov     r8, rbx
0x1800a1062  movzx   edx, si
0x1800a1065  call    CleanTargetMedia
0x1800a106a  test    eax, eax
0x1800a106c  jnz     short loc_1800A108B
0x1800a106e  cmp     [rbx+0D0h], r12d
0x1800a1075  jnz     short loc_1800A1081
0x1800a1077  mov     eax, 13h
0x1800a107c  jmp     loc_1800A1EC9
0x1800a1081  mov     eax, 9
0x1800a1086  jmp     loc_1800A1EC9
0x1800a108b  mov     rcx, rdi
0x1800a108e  test    [rbx+0E9Ch], r14w
0x1800a1096  jnz     short loc_1800A109F
0x1800a1098  mov     rcx, [rbx+0E08h]; pszSrc
0x1800a109f  call    MakeZipFileDir
0x1800a10a4  test    eax, eax
0x1800a10a6  jnz     loc_1800A1EC9
0x1800a10ac  test    [rbx+0E9Ch], r14w
0x1800a10b4  jnz     short loc_1800A10BD
0x1800a10b6  mov     rdi, [rbx+0E08h]
0x1800a10bd  mov     rcx, rdi; pszSrc
0x1800a10c0  call    RemainingDiskSpace
0x1800a10c5  mov     [rbx+1F0h], rax
0x1800a10cc  mov     esi, 1
0x1800a10d1  jmp     short loc_1800A113A
0x1800a10d3  mov     rcx, [rcx+0E08h]; pszSrc
0x1800a10da  lea     r8, [rbp+57h+var_A8]
0x1800a10de  mov     r9, rbx
0x1800a10e1  lea     rdx, [rbp+57h+var_A0]
0x1800a10e5  call    filetime
0x1800a10ea  test    eax, eax
0x1800a10ec  jz      short loc_1800A110F
0x1800a10ee  cmp     [rbp+57h+var_A8], r12
0x1800a10f2  jnz     short loc_1800A110F
0x1800a10f4  mov     rcx, [rbx+0E08h]; lpFileName
0x1800a10fb  call    cs:__imp_DeleteFileA
0x1800a1101  test    eax, eax
0x1800a1103  jnz     short loc_1800A1126
0x1800a1105  mov     eax, 3
0x1800a110a  jmp     loc_1800A1EC9
0x1800a110f  mov     rcx, [rbx+0E08h]; lpFileName
0x1800a1116  mov     rdx, rbx
0x1800a1119  call    ValidZIPTest
0x1800a111e  test    eax, eax
0x1800a1120  jnz     loc_1800A1EC9
0x1800a1126  mov     rcx, [rbx+0E08h]; pszSrc
0x1800a112d  call    MakeZipFileDir
0x1800a1132  test    eax, eax
0x1800a1134  jnz     loc_1800A1EC9
0x1800a113a  mov     rcx, [rbx+0E08h]; lpFileName
0x1800a1141  test    rcx, rcx
0x1800a1144  jz      loc_1800A1EC7
0x1800a114a  cmp     [rcx], r12b
0x1800a114d  jz      loc_1800A1EC7
0x1800a1153  mov     [rsp+0F0h+hTemplateFile], r12; hTemplateFile
0x1800a1158  mov     r14d, 3
0x1800a115e  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a1166  xor     r9d, r9d; lpSecurityAttributes
0x1800a1169  xor     r8d, r8d; dwShareMode
0x1800a116c  mov     [rsp+0F0h+dwCreationDisposition], r14d; dwCreationDisposition
0x1800a1171  mov     edx, 80000000h; dwDesiredAccess
0x1800a1176  call    cs:__imp_CreateFileA
0x1800a117c  mov     rdi, rax
0x1800a117f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a1183  jz      loc_1800A1EC7
0x1800a1189  cmp     [rbx+0DD4h], r12d
0x1800a1190  jz      short loc_1800A11A9
0x1800a1192  mov     rcx, [rbx+0E08h]; pszSrc
0x1800a1199  lea     r8, [rbp+57h+var_A8]
0x1800a119d  mov     r9, rbx
0x1800a11a0  lea     rdx, [rbp+57h+var_A0]
0x1800a11a4  call    filetime
0x1800a11a9  mov     r13, r12
0x1800a11ac  mov     [rbx+0E30h], r12
0x1800a11b3  jmp     short loc_1800A11BC
0x1800a11b5  cmp     al, 50h ; 'P'
0x1800a11b7  jz      short loc_1800A11D2
0x1800a11b9  add     r13, rsi
0x1800a11bc  mov     r8, rsi
0x1800a11bf  lea     rdx, [rbp+57h+var_B0]
0x1800a11c3  mov     rcx, rdi; hFile
0x1800a11c6  call    GetSomeBytes
0x1800a11cb  test    eax, eax
0x1800a11cd  mov     al, [rbp+57h+var_B0]
0x1800a11d0  jnz     short loc_1800A11B5
0x1800a11d2  mov     r8, r14
0x1800a11d5  mov     byte ptr [rbp+57h+var_80], al
0x1800a11d8  lea     rdx, [rbp+57h+var_80+1]
0x1800a11dc  mov     rcx, rdi; hFile
0x1800a11df  call    GetSomeBytes
0x1800a11e4  test    eax, eax
0x1800a11e6  jz      short loc_1800A1240
0x1800a11e8  movzx   eax, byte ptr [rbp+57h+var_7E]
0x1800a11ec  movzx   ecx, byte ptr [rbp+57h+var_7E+1]
0x1800a11f0  shl     rcx, 8
0x1800a11f4  or      rcx, rax
0x1800a11f7  movzx   eax, byte ptr [rbp+57h+var_80+1]
0x1800a11fb  shl     rcx, 8
0x1800a11ff  or      rcx, rax
0x1800a1202  movzx   eax, byte ptr [rbp+57h+var_80]
0x1800a1206  shl     rcx, 8
0x1800a120a  or      rcx, rax
0x1800a120d  cmp     rcx, 4034B50h
0x1800a1214  jz      short loc_1800A1240
0x1800a1216  cmp     rcx, 6054B50h
0x1800a121d  jz      short loc_1800A1240
0x1800a121f  mov     r8d, esi
0x1800a1222  mov     rdx, 0FFFFFFFFFFFFFFFDh
0x1800a1229  mov     rcx, rdi
0x1800a122c  call    DZSetFilePointer
0x1800a1231  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a1235  jz      loc_1800A1E7C
0x1800a123b  jmp     loc_1800A11B9
0x1800a1240  mov     [rbp+57h+var_98], r15
0x1800a1244  mov     [rbx+0E10h], r13
0x1800a124b  movzx   eax, byte ptr [rbp+57h+var_7E]
0x1800a124f  movzx   ecx, byte ptr [rbp+57h+var_7E+1]
0x1800a1253  shl     ecx, 8
0x1800a1256  or      ecx, eax
0x1800a1258  movzx   eax, byte ptr [rbp+57h+var_80+1]
0x1800a125c  shl     eax, 8
0x1800a125f  shl     ecx, 10h
0x1800a1262  or      ecx, eax
0x1800a1264  movzx   eax, byte ptr [rbp+57h+var_80]
0x1800a1268  or      ecx, eax
0x1800a126a  cmp     ecx, 4034B50h
0x1800a1270  jnz     loc_1800A1858
0x1800a1276  mov     ecx, 0A0h; Size
0x1800a127b  call    cs:__imp_malloc
0x1800a1281  mov     rsi, rax
0x1800a1284  test    rax, rax
0x1800a1287  jz      loc_1800A1E5E
0x1800a128d  xor     edx, edx; Val
0x1800a128f  mov     r8d, 0A0h; Size
0x1800a1295  mov     rcx, rax; void *
0x1800a1298  call    memset_0
0x1800a129d  mov     r8d, 1Ah
0x1800a12a3  lea     rdx, [rbp+57h+var_80]
0x1800a12a7  mov     rcx, rdi; hFile
0x1800a12aa  call    GetSomeBytes
0x1800a12af  test    eax, eax
0x1800a12b1  jz      loc_1800A1782
0x1800a12b7  movzx   ecx, byte ptr [rbp+57h+var_80+1]
0x1800a12bb  movzx   eax, byte ptr [rbp+57h+var_80]
0x1800a12bf  shl     cx, 8
0x1800a12c3  or      cx, ax
0x1800a12c6  mov     word ptr [rsi], 14h
0x1800a12cb  mov     [rsi+2], cx
0x1800a12cf  movzx   ecx, byte ptr [rbp+57h+var_7E+1]
0x1800a12d3  movzx   eax, byte ptr [rbp+57h+var_7E]
0x1800a12d7  shl     cx, 8
0x1800a12db  or      cx, ax
0x1800a12de  mov     [rsi+46h], cx
0x1800a12e2  mov     [rsi+4], cx
0x1800a12e6  movzx   eax, byte ptr [rbp+57h+var_7C]
0x1800a12ea  mov     [rbp+57h+var_9C], cx
0x1800a12ee  movzx   ecx, byte ptr [rbp+57h+var_7C+1]
0x1800a12f2  shl     cx, 8
0x1800a12f6  or      cx, ax
0x1800a12f9  mov     [rsi+6], cx
0x1800a12fd  movzx   eax, byte ptr [rbp+57h+var_78]
0x1800a1301  movzx   ecx, byte ptr [rbp+57h+var_78+1]
0x1800a1305  shl     ecx, 8
0x1800a1308  or      ecx, eax
0x1800a130a  movzx   eax, byte ptr [rbp+57h+var_7A+1]
0x1800a130e  shl     ecx, 10h
0x1800a1311  shl     eax, 8
0x1800a1314  or      ecx, eax
0x1800a1316  movzx   eax, byte ptr [rbp+57h+var_7A]
0x1800a131a  or      ecx, eax
0x1800a131c  mov     [rsi+8], ecx
0x1800a131f  movzx   eax, byte ptr [rbp+57h+var_74]
0x1800a1323  movzx   ecx, byte ptr [rbp+57h+var_74+1]
0x1800a1327  shl     ecx, 8
0x1800a132a  or      ecx, eax
0x1800a132c  movzx   eax, byte ptr [rbp+57h+var_76+1]
0x1800a1330  shl     ecx, 10h
0x1800a1333  shl     eax, 8
0x1800a1336  or      ecx, eax
0x1800a1338  movzx   eax, byte ptr [rbp+57h+var_76]
0x1800a133c  or      ecx, eax
0x1800a133e  mov     [rsi+0Ch], ecx
0x1800a1341  movzx   eax, byte ptr [rbp+57h+var_70]
0x1800a1345  movzx   r15d, byte ptr [rbp+57h+var_70+1]
0x1800a134a  shl     r15, 8
0x1800a134e  or      r15, rax
0x1800a1351  movzx   eax, byte ptr [rbp+57h+var_72+1]
0x1800a1355  shl     r15, 8
0x1800a1359  or      r15, rax
0x1800a135c  movzx   eax, byte ptr [rbp+57h+var_72]
0x1800a1360  shl     r15, 8
0x1800a1364  or      r15, rax
0x1800a1367  mov     [rsi+10h], r15
0x1800a136b  movzx   eax, byte ptr [rbp+57h+var_6C]
0x1800a136f  movzx   ecx, byte ptr [rbp+57h+var_6C+1]
0x1800a1373  shl     rcx, 8
0x1800a1377  or      rcx, rax
0x1800a137a  movzx   eax, byte ptr [rbp+57h+var_6E+1]
0x1800a137e  shl     rcx, 8
0x1800a1382  or      rcx, rax
0x1800a1385  movzx   eax, byte ptr [rbp+57h+var_6E]
0x1800a1389  shl     rcx, 8
0x1800a138d  or      rcx, rax
0x1800a1390  mov     [rsi+18h], rcx
0x1800a1394  movzx   eax, byte ptr [rbp+57h+var_6A]
0x1800a1398  movzx   r12d, byte ptr [rbp+57h+var_6A+1]
0x1800a139d  shl     r12, 8
0x1800a13a1  or      r12, rax
0x1800a13a4  mov     [rsi+20h], r12
0x1800a13a8  movzx   eax, byte ptr [rbp+57h+var_68]
0x1800a13ac  movzx   ecx, byte ptr [rbp+57h+var_68+1]
0x1800a13b0  shl     rcx, 8
0x1800a13b4  or      rcx, rax
0x1800a13b7  movzx   eax, byte ptr [rbp+57h+var_A0]
0x1800a13bb  mov     [rsi+28h], rcx
0x1800a13bf  xor     ecx, ecx
0x1800a13c1  mov     [rsi+38h], rcx
0x1800a13c5  mov     [rsi+40h], ecx
0x1800a13c8  mov     [rsi+44h], cx
0x1800a13cc  cmp     [rbx+0DD0h], ecx
0x1800a13d2  jnz     short loc_1800A13D7
0x1800a13d4  mov     eax, [rbp+57h+var_A0]
0x1800a13d7  mov     [rsi+48h], eax
0x1800a13da  mov     rax, [rbp+57h+var_98]
0x1800a13de  mov     [rsi+80h], ecx
0x1800a13e4  cmp     dword ptr [rbx+0DD4h], 1
0x1800a13eb  mov     [rax], rsi
0x1800a13ee  cmovg   r15, rcx
0x1800a13f2  lea     rax, [rsi+98h]
0x1800a13f9  mov     [rbp+57h+var_98], rax
0x1800a13fd  mov     [rax], rcx
0x1800a1400  test    r12, r12
0x1800a1403  jz      loc_1800A1E82
0x1800a1409  lea     rcx, [r12+1]; Size
0x1800a140e  call    cs:__imp_malloc
0x1800a1414  mov     [rbp+57h+var_A8], rax
0x1800a1418  mov     [rsi+78h], rax
  ... truncated ...
```
