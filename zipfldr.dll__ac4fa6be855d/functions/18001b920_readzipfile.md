# readzipfile

- ea: `0x18001b920`
- end: `0x18001c828`
- name: `readzipfile`
- size: `3848`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18001a6cc`

## callees

- `0x180005464`
- `0x180015950`
- `0x180019af4`
- `0x18001a4c8`
- `0x18001b920`
- `0x18001d80c`
- `0x18001e070`
- `0x1800242c4`
- `0x180036f50`
- `0x18003791c`
- `0x180037928`
- `0x180037934`
- `0x180037958`
- `0x1800390f1`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001beeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c6c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001beeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c6c9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001bad3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001bedd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001bf53`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001c5b2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001c6bc`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001bad3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001bedd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001bf53`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001c5b2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001c6bc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001ba3f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001bb81`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001be63`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001bfc1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c07d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c138`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c47f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c530`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c63e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001ba3f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001bb81`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001be63`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001bfc1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c07d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c138`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c47f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c530`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001c63e`
- `KERNEL32!lstrlenA` at `0x18001bddd`
- `KERNEL32!lstrlenA` at `0x18001bddd`
- `USER32!OemToCharBuffA` at `0x18001bdd0`
- `USER32!OemToCharBuffA` at `0x18001c32f`
- `USER32!OemToCharBuffA` at `0x18001bdd0`
- `USER32!OemToCharBuffA` at `0x18001c32f`

## pseudocode

```c
__int64 __fastcall readzipfile(__int64 a1)
{
  __int64 v1; // rdx
  _QWORD *v2; // r14
  int v4; // eax
  __int64 v5; // rdi
  __int64 result; // rax
  _BYTE *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rsi
  void *v10; // rcx
  int SomeBytes; // eax
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  int v15; // r10d
  unsigned __int64 v16; // rcx
  void *v17; // rcx
  DWORD v18; // eax
  __int64 v19; // rdi
  _QWORD *v20; // r13
  char *v21; // rax
  char *v22; // rdi
  void *v23; // rcx
  __int16 v24; // cx
  __int16 v25; // ax
  unsigned __int16 v26; // cx
  unsigned __int64 v27; // r14
  __int64 v28; // r15
  DWORD v29; // eax
  _BYTE *v30; // rax
  _BYTE *v31; // r13
  size_t v32; // rcx
  void *v33; // rax
  const CHAR *v34; // r13
  char *v35; // rax
  __int64 v36; // rax
  __int64 v37; // r10
  unsigned __int64 v38; // rax
  void *v39; // rcx
  void *v40; // rcx
  DWORD v41; // eax
  __int64 v42; // r14
  DWORD v43; // eax
  __int64 v44; // r15
  __int64 v45; // r14
  bool v46; // zf
  void *v47; // rcx
  void *v48; // rcx
  __int64 v49; // rdi
  void *v50; // rcx
  size_t v51; // r12
  CHAR *v52; // r14
  size_t v53; // r14
  void *v54; // rax
  int v55; // eax
  CHAR *v56; // rcx
  size_t v57; // r8
  void *v58; // r14
  void *v59; // rax
  void *v60; // rcx
  int v61; // ecx
  void *v62; // rcx
  void *v63; // rcx
  DWORD v64; // eax
  __int64 v65; // rdi
  void *v66; // rcx
  void *v67; // rcx
  DWORD v68; // eax
  __int64 v69; // rdi
  __int64 v70; // rcx
  _QWORD *v71; // rax
  _QWORD *v72; // rcx
  __int64 i; // rax
  __int64 v74; // [rsp+40h] [rbp-39h] BYREF
  size_t cchDest; // [rsp+48h] [rbp-31h]
  _QWORD *v76; // [rsp+50h] [rbp-29h]
  _BYTE Buffer[4]; // [rsp+58h] [rbp-21h] BYREF
  DWORD NumberOfBytesRead; // [rsp+5Ch] [rbp-1Dh] BYREF
  DWORD v79[2]; // [rsp+60h] [rbp-19h] BYREF
  __int16 v80; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int16 v81; // [rsp+6Ah] [rbp-Fh]
  unsigned __int16 v82; // [rsp+6Ch] [rbp-Dh]
  __int16 v83; // [rsp+6Eh] [rbp-Bh]
  unsigned __int16 v84; // [rsp+70h] [rbp-9h]
  unsigned __int16 v85; // [rsp+72h] [rbp-7h]
  unsigned __int16 v86; // [rsp+74h] [rbp-5h]
  unsigned __int16 v87; // [rsp+76h] [rbp-3h]
  unsigned __int16 v88; // [rsp+78h] [rbp-1h]
  unsigned __int16 v89; // [rsp+7Ah] [rbp+1h]
  unsigned __int16 v90; // [rsp+7Ch] [rbp+3h]
  unsigned __int16 v91; // [rsp+7Eh] [rbp+5h]
  unsigned __int16 v92; // [rsp+80h] [rbp+7h]
  unsigned __int16 v93; // [rsp+82h] [rbp+9h]
  unsigned __int16 v94; // [rsp+84h] [rbp+Bh]
  unsigned __int16 v95; // [rsp+86h] [rbp+Dh]
  __int16 v96; // [rsp+88h] [rbp+Fh]
  unsigned __int8 v97; // [rsp+8Ah] [rbp+11h]
  unsigned __int8 v98; // [rsp+8Bh] [rbp+12h]
  unsigned __int16 v99; // [rsp+8Ch] [rbp+13h]
  unsigned __int8 v100; // [rsp+8Eh] [rbp+15h]
  unsigned __int8 v101; // [rsp+8Fh] [rbp+16h]
  unsigned __int16 v102; // [rsp+90h] [rbp+17h]

  v1 = *(_QWORD *)(a1 + 5056);
  v2 = (_QWORD *)(a1 + 5080);
  *(_QWORD *)(a1 + 5064) = 0;
  v79[0] = 0;
  Buffer[0] = 0;
  *(_QWORD *)(a1 + 5080) = 0;
  v74 = 0;
  v4 = filetime(0, v1, v79, &v74, a1);
  v5 = v74;
  if ( !v4 || v74 )
  {
    result = ValidZIPTestUTF8(*(_QWORD *)(a1 + 5056), a1);
    if ( (_DWORD)result )
      return result;
  }
  result = MakeZipFileDirUTF8(*(_QWORD *)(a1 + 5056));
  if ( (_DWORD)result )
    return result;
  v7 = *(_BYTE **)(a1 + 5056);
  if ( !v7 )
    return 0;
  if ( !*v7 )
    return 0;
  v8 = *(_QWORD *)(a1 + 21528);
  if ( v8 == -1 || !v5 )
    return 0;
  if ( DZSetFilePointer(v8, 0, 0) == -1 )
    return 11;
  v9 = 0;
  *(_QWORD *)(a1 + 5088) = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v10 = *(void **)(a1 + 21528);
      NumberOfBytesRead = 0;
      if ( !ReadFile(v10, Buffer, 1u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 1 || Buffer[0] == 80 )
        break;
      ++v9;
    }
    LOBYTE(v80) = Buffer[0];
    SomeBytes = GetSomeBytes(*(HANDLE *)(a1 + 21528));
    v12 = HIBYTE(v81);
    v13 = (unsigned __int8)v81;
    v14 = HIBYTE(v80);
    v15 = (unsigned __int8)v80;
    if ( !SomeBytes )
      break;
    v16 = (unsigned __int8)v80
        | ((HIBYTE(v80) | (((unsigned __int8)v81 | ((unsigned __int64)HIBYTE(v81) << 8)) << 8)) << 8);
    if ( v16 == 67324752 || v16 == 101010256 )
      break;
    v17 = *(void **)(a1 + 21528);
    NumberOfBytesRead = -1;
    v18 = SetFilePointer(v17, -3, (PLONG)&NumberOfBytesRead, 1u);
    v19 = v18;
    if ( v18 == -1 && GetLastError() || v19 + ((__int64)(int)NumberOfBytesRead << 32) == -1 )
      return 11;
    ++v9;
  }
  *(_QWORD *)(a1 + 5064) = v9;
  v20 = v2;
  if ( (v15 | (v14 << 8) | ((v13 | (v12 << 8)) << 16)) == 0x4034B50 )
  {
    while ( 1 )
    {
      v21 = (char *)o_malloc_0(0xA0u);
      v22 = v21;
      if ( !v21 )
        return 4;
      memset_0(v21, 0, 0xA0u);
      v23 = *(void **)(a1 + 21528);
      NumberOfBytesRead = 0;
      if ( !ReadFile(v23, &v80, 0x1Au, &NumberOfBytesRead, 0) || NumberOfBytesRead != 26 )
        return 11;
      v24 = HIBYTE(v80);
      v25 = (unsigned __int8)v80;
      *(_WORD *)v22 = 20;
      *((_WORD *)v22 + 1) = v25 | (v24 << 8);
      v26 = v81;
      *((_WORD *)v22 + 35) = v81;
      *((_WORD *)v22 + 2) = v26;
      LOWORD(NumberOfBytesRead) = v26;
      *((_WORD *)v22 + 3) = v82;
      *((_DWORD *)v22 + 2) = (unsigned __int8)v83 | (HIBYTE(v83) << 8) | (v84 << 16);
      *((_DWORD *)v22 + 3) = (unsigned __int8)v85 | (HIBYTE(v85) << 8) | (v86 << 16);
      v27 = (unsigned __int8)v87 | ((HIBYTE(v87) | ((unsigned __int64)v88 << 8)) << 8);
      *((_QWORD *)v22 + 2) = v27;
      *((_QWORD *)v22 + 3) = (unsigned __int8)v89 | ((HIBYTE(v89) | ((unsigned __int64)v90 << 8)) << 8);
      v28 = v91;
      *((_QWORD *)v22 + 4) = v91;
      v29 = v79[0];
      *((_QWORD *)v22 + 5) = v92;
      *((_DWORD *)v22 + 18) = v29;
      *((_QWORD *)v22 + 7) = 0;
      *((_DWORD *)v22 + 16) = 0;
      *((_WORD *)v22 + 34) = 0;
      *((_WORD *)v22 + 64) = 0;
      *v20 = v22;
      v76 = v22 + 152;
      *((_QWORD *)v22 + 19) = 0;
      if ( !v28 )
        return 3;
      v30 = o_malloc_0(v28 + 1);
      *((_QWORD *)v22 + 15) = v30;
      v31 = v30;
      if ( !v30 )
        return 4;
      v32 = *((_QWORD *)v22 + 5);
      if ( v32 )
      {
        v33 = o_malloc_0(v32);
        *((_QWORD *)v22 + 12) = v33;
        if ( !v33 )
          return 4;
      }
      *v31 = 0;
      if ( !(unsigned int)GetSomeBytes(*(HANDLE *)(a1 + 21528)) )
        return 11;
      *(_BYTE *)(v28 + *((_QWORD *)v22 + 15)) = 0;
      if ( *((_QWORD *)v22 + 5) )
      {
        if ( !(unsigned int)GetSomeBytes(*(HANDLE *)(a1 + 21528)) )
          return 11;
      }
      v74 = 0;
      *((_QWORD *)v22 + 17) = 0;
      if ( (unsigned int)ParseExtra64(
                           *((char **)v22 + 12),
                           (_QWORD *)v22 + 5,
                           (_QWORD *)v22 + 3,
                           (_QWORD *)v22 + 2,
                           0,
                           0,
                           &v74) )
      {
        v27 = *((_QWORD *)v22 + 2);
        *((_QWORD *)v22 + 17) = v74;
      }
      if ( v27 && DZSetFilePointer(*(_QWORD *)(a1 + 21528), v27, 1) == -1 )
        return 2;
      if ( (*((_WORD *)v22 + 2) & 0x800) == 0 )
        OemToCharBuffA(*((LPCSTR *)v22 + 15), *((LPSTR *)v22 + 15), v28);
      v34 = (const CHAR *)*((_QWORD *)v22 + 15);
      cchDest = (unsigned int)(lstrlenA(v34) + 1);
      v35 = (char *)o_malloc_0(cchDest);
      if ( !v35 )
      {
        *((_QWORD *)v22 + 11) = 0;
        return 4;
      }
      StringCchCopyA(v35, cchDest, v34);
      v36 = v28 + v74;
      *((_QWORD *)v22 + 10) = v9;
      *((_QWORD *)v22 + 11) = v37;
      v38 = *((_QWORD *)v22 + 5) + v27 + v36;
      ++*(_QWORD *)(a1 + 5088);
      v9 += v38 + 30;
      if ( (NumberOfBytesRead & 8) != 0 )
      {
        if ( v27 )
        {
          if ( DZSetFilePointer(*(_QWORD *)(a1 + 21528), v9, 0) == -1 )
            return 11;
          v47 = *(void **)(a1 + 21528);
          NumberOfBytesRead = 0;
          if ( !ReadFile(v47, &v80, 0x10u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 16 )
            return 11;
          v46 = ((unsigned __int8)v80 | (HIBYTE(v80) << 8) | (v81 << 16)) == 134695760;
        }
        else
        {
          while ( 1 )
          {
            do
            {
              v39 = *(void **)(a1 + 21528);
              NumberOfBytesRead = 0;
            }
            while ( ReadFile(v39, Buffer, 1u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 1 && Buffer[0] != 80 );
            LOBYTE(v80) = Buffer[0];
            if ( !(unsigned int)GetSomeBytes(*(HANDLE *)(a1 + 21528))
              || ((unsigned __int8)v80 | (HIBYTE(v80) << 8) | (v81 << 16)) == 0x8074B50 )
            {
              break;
            }
            v40 = *(void **)(a1 + 21528);
            NumberOfBytesRead = -1;
            v41 = SetFilePointer(v40, -15, (PLONG)&NumberOfBytesRead, 1u);
            v42 = v41;
            if ( v41 == -1 && GetLastError() || v42 + ((__int64)(int)NumberOfBytesRead << 32) == -1 )
              return 2;
          }
          NumberOfBytesRead = 0;
          v9 += (unsigned __int8)v84 | ((HIBYTE(v84) | ((unsigned __int64)v85 << 8)) << 8);
          v43 = SetFilePointer(*(HANDLE *)(a1 + 21528), 0, (PLONG)&NumberOfBytesRead, 1u);
          v44 = v43;
          if ( v43 != -1 || (v45 = -1, !GetLastError()) )
            v45 = v44 + ((__int64)(int)NumberOfBytesRead << 32);
          v46 = v45 == v9 + 16;
        }
        if ( !v46 )
          return 3;
        v9 += 16;
        *((_WORD *)v22 + 5) = v82;
        *((_WORD *)v22 + 6) = v83;
        *((_WORD *)v22 + 7) = v84;
        *((_WORD *)v22 + 8) = v85;
        *((_WORD *)v22 + 9) = v86;
        *((_WORD *)v22 + 10) = v87;
      }
      v48 = *(void **)(a1 + 21528);
      NumberOfBytesRead = 0;
      if ( !ReadFile(v48, &v80, 4u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 4 )
        return 11;
      LOBYTE(v12) = HIBYTE(v81);
      LOBYTE(v13) = v81;
      LOBYTE(v14) = HIBYTE(v80);
      LOBYTE(v15) = v80;
      if ( ((unsigned __int8)v80 | (HIBYTE(v80) << 8) | (v81 << 16)) != 0x4034B50 )
      {
        v2 = (_QWORD *)(a1 + 5080);
        break;
      }
      v20 = v76;
    }
  }
  v49 = *v2;
  if ( ((unsigned __int8)v15 | ((unsigned __int8)v14 << 8)
                             | (((unsigned __int8)v13 | ((unsigned __int8)v12 << 8)) << 16)) == 0x2014B50 )
  {
    while ( v49 )
    {
      v50 = *(void **)(a1 + 21528);
      v79[0] = 0;
      if ( !ReadFile(v50, &v80, 0x2Au, v79, 0) || v79[0] != 42 )
        return 11;
      *(_WORD *)v49 = v80;
      *(_WORD *)(v49 + 2) = v81;
      *(_WORD *)(v49 + 4) = v82;
      *(_WORD *)(v49 + 70) = v82;
      *(_WORD *)(v49 + 6) = v83;
      *(_DWORD *)(v49 + 8) = (unsigned __int8)v84 | (HIBYTE(v84) << 8) | (v85 << 16);
      *(_DWORD *)(v49 + 12) = (unsigned __int8)v86 | (HIBYTE(v86) << 8) | (v87 << 16);
      *(_QWORD *)(v49 + 16) = (unsigned __int8)v88 | ((HIBYTE(v88) | ((unsigned __int64)v89 << 8)) << 8);
      *(_QWORD *)(v49 + 24) = (unsigned __int8)v90 | ((HIBYTE(v90) | ((unsigned __int64)v91 << 8)) << 8);
      v51 = v92;
      *(_QWORD *)(v49 + 32) = v92;
      *(_QWORD *)(v49 + 48) = v93;
      *(_QWORD *)(v49 + 56) = v94;
      *(_DWORD *)(v49 + 64) = v95;
      *(_WORD *)(v49 + 68) = v96;
      *(_DWORD *)(v49 + 72) = v97 | (v98 << 8) | (v99 << 16);
      *(_QWORD *)v79 = v100 | ((v101 | ((unsigned __int64)v102 << 8)) << 8);
      v52 = (CHAR *)o_malloc_0(v51);
      if ( !v52 )
        return 4;
      if ( !(unsigned int)GetSomeBytes(*(HANDLE *)(a1 + 21528)) )
      {
        v56 = v52;
LABEL_108:
        free(v56);
        return 11;
      }
      if ( (*(_WORD *)(v49 + 4) & 0x800) == 0 )
        OemToCharBuffA(v52, v52, *(_DWORD *)(v49 + 32));
      if ( memcmp_0(v52, *(const void **)(v49 + 120), *(_QWORD *)(v49 + 32)) )
      {
        free(v52);
        return 3;
      }
      free(v52);
      v53 = *(_QWORD *)(v49 + 48);
      v74 = 0;
      *(_QWORD *)(v49 + 144) = 0;
      if ( v53 )
      {
        v54 = o_malloc_0(v53);
        *(_QWORD *)(v49 + 104) = v54;
        if ( !v54 )
          return 4;
        v55 = GetSomeBytes(*(HANDLE *)(a1 + 21528));
        v56 = *(CHAR **)(v49 + 104);
        if ( !v55 )
          goto LABEL_108;
        if ( (unsigned int)ParseExtra64(
                             v56,
                             (_QWORD *)(v49 + 48),
                             (_QWORD *)(v49 + 24),
                             (_QWORD *)(v49 + 16),
                             v79,
                             (_DWORD *)(v49 + 64),
                             &v74) )
          *(_QWORD *)(v49 + 144) = v74;
        v57 = *(_QWORD *)(v49 + 40);
        if ( v57 == *(_QWORD *)(v49 + 48) )
        {
          v58 = *(void **)(v49 + 104);
          if ( !memcmp_0(*(const void **)(v49 + 96), v58, v57) )
          {
            free(v58);
            *(_QWORD *)(v49 + 104) = *(_QWORD *)(v49 + 96);
          }
        }
      }
      if ( *(_QWORD *)(v49 + 56) )
      {
        v59 = o_malloc_0(*(_QWORD *)(v49 + 56));
        *(_QWORD *)(v49 + 112) = v59;
        if ( !v59 )
          return 4;
        if ( !(unsigned int)GetSomeBytes(*(HANDLE *)(a1 + 21528)) )
        {
          free(*(void **)(v49 + 112));
          return 11;
        }
      }
      if ( *(_QWORD *)(v49 + 80) != *(_QWORD *)v79 )
        return 3;
      *(_WORD *)(v49 + 128) = 0;
      v60 = *(void **)(a1 + 21528);
      v49 = *(_QWORD *)(v49 + 152);
      v79[0] = 0;
      if ( !ReadFile(v60, &v80, 4u, v79, 0) || v79[0] != 4 )
        return 11;
      LOBYTE(v12) = HIBYTE(v81);
      LOBYTE(v13) = v81;
      LOBYTE(v14) = HIBYTE(v80);
      LOBYTE(v15) = v80;
      if ( ((unsigned __int8)v80 | (HIBYTE(v80) << 8) | (v81 << 16)) != 0x2014B50 )
      {
        v2 = (_QWORD *)(a1 + 5080);
        goto LABEL_92;
      }
    }
    return 3;
  }
LABEL_92:
  if ( v49 )
    return 3;
  v61 = (unsigned __int8)v15
      | ((unsigned __int8)v14 << 8)
      | (((unsigned __int8)v13 | ((unsigned __int8)v12 << 8)) << 16);
  if ( v61 == 101010256 )
  {
    if ( (unsigned int)GetSomeBytes(*(HANDLE *)(a1 + 21528)) )
    {
      if ( *(_QWORD *)(a1 + 5088) != v82
        || ((unsigned __int8)v86 | ((HIBYTE(v86) | ((unsigned __int64)v87 << 8)) << 8)) != v9 )
      {
        return 3;
      }
LABEL_124:
      v70 = *(_QWORD *)(a1 + 5088);
      *(_QWORD *)(a1 + 5072) = v9;
      if ( v70 )
      {
        v71 = o_malloc_0(8 * v70);
        *(_QWORD *)(a1 + 5096) = v71;
        v72 = v71;
        if ( !v71 )
          return 4;
        for ( i = *v2; i; i = *(_QWORD *)(i + 152) )
          *v72++ = i;
        qsort(*(void **)(a1 + 5096), *(_QWORD *)(a1 + 5088), 8u, zqcmp);
      }
      return 0;
    }
    return 11;
  }
  if ( v61 != 101075792 )
    return 3;
  while ( 1 )
  {
    do
    {
      v62 = *(void **)(a1 + 21528);
      v79[0] = 0;
    }
    while ( ReadFile(v62, Buffer, 1u, v79, 0) && v79[0] == 1 && Buffer[0] != 80 );
    LOBYTE(v80) = Buffer[0];
    if ( !(unsigned int)GetSomeBytes(*(HANDLE *)(a1 + 21528)) )
      return 2;
    if ( ((unsigned __int8)v80 | (HIBYTE(v80) << 8) | (v81 << 16)) == 0x7064B50 )
    {
      while ( 1 )
      {
        do
        {
          v66 = *(void **)(a1 + 21528);
          v79[0] = 0;
        }
        while ( ReadFile(v66, Buffer, 1u, v79, 0) && v79[0] == 1 && Buffer[0] != 80 );
        LOBYTE(v80) = Buffer[0];
        if ( !(unsigned int)GetSomeBytes(*(HANDLE *)(a1 + 21528)) )
          return 2;
        v67 = *(void **)(a1 + 21528);
        if ( ((unsigned __int8)v80 | (HIBYTE(v80) << 8) | (v81 << 16)) == 0x6054B50 )
        {
          if ( !(unsigned int)GetSomeBytes(v67) )
            return 11;
          goto LABEL_124;
        }
        v79[0] = -1;
        v68 = SetFilePointer(v67, -3, (PLONG)v79, 1u);
        v69 = v68;
        if ( v68 == -1 && GetLastError() )
          return 2;
        if ( v69 + ((__int64)(int)v79[0] << 32) == -1 )
          return 2;
      }
    }
    v63 = *(void **)(a1 + 21528);
    v79[0] = -1;
    v64 = SetFilePointer(v63, -3, (PLONG)v79, 1u);
    v65 = v64;
    if ( v64 == -1 && GetLastError() )
      return 2;
    if ( v65 + ((__int64)(int)v79[0] << 32) == -1 )
      return 2;
  }
}

```

## disassembly

```asm
0x18001b920  push    rbp
0x18001b922  push    rbx
0x18001b923  push    rdi
0x18001b924  push    r12
0x18001b926  push    r14
0x18001b928  lea     rbp, [rsp-37h]
0x18001b92d  sub     rsp, 0B0h
0x18001b934  mov     rax, cs:__security_cookie
0x18001b93b  xor     rax, rsp
0x18001b93e  mov     [rbp+57h+var_30], rax
0x18001b942  mov     rdx, [rcx+13C0h]
0x18001b949  lea     r14, [rcx+13D8h]
0x18001b950  xor     r12d, r12d
0x18001b953  mov     [rsp+0D0h+lpOverlapped], rcx
0x18001b958  mov     [rcx+13C8h], r12
0x18001b95f  lea     r9, [rbp+57h+var_90]
0x18001b963  mov     rbx, rcx
0x18001b966  mov     [rbp+57h+var_70], r12d
0x18001b96a  xor     ecx, ecx
0x18001b96c  mov     [rbp+57h+Buffer], r12b
0x18001b970  lea     r8, [rbp+57h+var_70]
0x18001b974  mov     [r14], r12
0x18001b977  mov     [rbp+57h+var_90], r12
0x18001b97b  call    filetime
0x18001b980  mov     rdi, [rbp+57h+var_90]
0x18001b984  test    eax, eax
0x18001b986  jz      short loc_18001B98D
0x18001b988  test    rdi, rdi
0x18001b98b  jz      short loc_18001B9A4
0x18001b98d  mov     rcx, [rbx+13C0h]
0x18001b994  mov     rdx, rbx
0x18001b997  call    ValidZIPTestUTF8
0x18001b99c  test    eax, eax
0x18001b99e  jnz     loc_18001C80D
0x18001b9a4  mov     rcx, [rbx+13C0h]
0x18001b9ab  call    MakeZipFileDirUTF8
0x18001b9b0  test    eax, eax
0x18001b9b2  jnz     loc_18001C80D
0x18001b9b8  mov     rax, [rbx+13C0h]
0x18001b9bf  mov     [rsp+0D0h+arg_8], rsi
0x18001b9c7  mov     [rsp+0D0h+arg_10], r13
0x18001b9cf  mov     [rsp+0D0h+arg_18], r15
0x18001b9d7  test    rax, rax
0x18001b9da  jz      loc_18001C7F3
0x18001b9e0  cmp     [rax], r12b
0x18001b9e3  jz      loc_18001C7F3
0x18001b9e9  mov     rcx, [rbx+5418h]
0x18001b9f0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001b9f4  jz      loc_18001C7F3
0x18001b9fa  test    rdi, rdi
0x18001b9fd  jz      loc_18001C7F3
0x18001ba03  xor     r8d, r8d
0x18001ba06  xor     edx, edx
0x18001ba08  call    DZSetFilePointer
0x18001ba0d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ba11  jz      loc_18001C616
0x18001ba17  mov     rsi, r12
0x18001ba1a  mov     [rbx+13E0h], r12
0x18001ba21  mov     rcx, [rbx+5418h]; hFile
0x18001ba28  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001ba2c  mov     r8d, 1; nNumberOfBytesToRead
0x18001ba32  mov     [rbp+57h+NumberOfBytesRead], r12d
0x18001ba36  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18001ba3a  mov     [rsp+0D0h+lpOverlapped], r12; lpOverlapped
0x18001ba3f  call    cs:__imp_ReadFile
0x18001ba45  movzx   ecx, [rbp+57h+Buffer]
0x18001ba49  test    eax, eax
0x18001ba4b  jz      short loc_18001BA5D
0x18001ba4d  cmp     [rbp+57h+NumberOfBytesRead], 1
0x18001ba51  jnz     short loc_18001BA5D
0x18001ba53  cmp     cl, 50h ; 'P'
0x18001ba56  jz      short loc_18001BA5D
0x18001ba58  inc     rsi
0x18001ba5b  jmp     short loc_18001BA21
0x18001ba5d  mov     byte ptr [rbp+57h+var_68], cl
0x18001ba60  lea     rdx, [rbp+57h+var_68+1]
0x18001ba64  mov     rcx, [rbx+5418h]; hFile
0x18001ba6b  mov     r8d, 3
0x18001ba71  call    GetSomeBytes
0x18001ba76  movzx   edx, byte ptr [rbp+57h+var_66+1]
0x18001ba7a  movzx   r8d, byte ptr [rbp+57h+var_66]
0x18001ba7f  movzx   r9d, byte ptr [rbp+57h+var_68+1]
0x18001ba84  movzx   r10d, byte ptr [rbp+57h+var_68]
0x18001ba89  test    eax, eax
0x18001ba8b  jz      short loc_18001BB0B
0x18001ba8d  mov     ecx, edx
0x18001ba8f  shl     rcx, 8
0x18001ba93  or      rcx, r8
0x18001ba96  shl     rcx, 8
0x18001ba9a  or      rcx, r9
0x18001ba9d  shl     rcx, 8
0x18001baa1  or      rcx, r10
0x18001baa4  cmp     rcx, 4034B50h
0x18001baab  jz      short loc_18001BB0B
0x18001baad  cmp     rcx, 6054B50h
0x18001bab4  jz      short loc_18001BB0B
0x18001bab6  mov     rcx, [rbx+5418h]; hFile
0x18001babd  lea     r8, [rbp+57h+NumberOfBytesRead]; lpDistanceToMoveHigh
0x18001bac1  mov     r9d, 1; dwMoveMethod
0x18001bac7  mov     [rbp+57h+NumberOfBytesRead], 0FFFFFFFFh
0x18001bace  mov     edx, 0FFFFFFFDh; lDistanceToMove
0x18001bad3  call    cs:__imp_SetFilePointer
0x18001bad9  mov     edi, eax
0x18001badb  cmp     eax, 0FFFFFFFFh
0x18001bade  jnz     short loc_18001BAEE
0x18001bae0  call    cs:__imp_GetLastError
0x18001bae6  test    eax, eax
0x18001bae8  jnz     loc_18001C616
0x18001baee  movsxd  rcx, [rbp+57h+NumberOfBytesRead]
0x18001baf2  shl     rcx, 20h
0x18001baf6  add     rcx, rdi
0x18001baf9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001bafd  jz      loc_18001C616
0x18001bb03  inc     rsi
0x18001bb06  jmp     loc_18001BA21
0x18001bb0b  mov     ecx, edx
0x18001bb0d  mov     [rbx+13C8h], rsi
0x18001bb14  shl     ecx, 8
0x18001bb17  mov     eax, r9d
0x18001bb1a  or      ecx, r8d
0x18001bb1d  shl     eax, 8
0x18001bb20  shl     ecx, 10h
0x18001bb23  mov     r13, r14
0x18001bb26  or      ecx, eax
0x18001bb28  or      ecx, r10d
0x18001bb2b  cmp     ecx, 4034B50h
0x18001bb31  jnz     loc_18001C0E4
0x18001bb37  mov     ecx, 0A0h; Size
0x18001bb3c  mov     r14d, 14h
0x18001bb42  call    _o_malloc_0
0x18001bb47  mov     rdi, rax
0x18001bb4a  test    rax, rax
0x18001bb4d  jz      loc_18001C7A6
0x18001bb53  xor     edx, edx; Val
0x18001bb55  mov     r8d, 0A0h; Size
0x18001bb5b  mov     rcx, rax; void *
0x18001bb5e  call    memset_0
0x18001bb63  mov     rcx, [rbx+5418h]; hFile
0x18001bb6a  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001bb6e  mov     r8d, 1Ah; nNumberOfBytesToRead
0x18001bb74  mov     [rbp+57h+NumberOfBytesRead], r12d
0x18001bb78  lea     rdx, [rbp+57h+var_68]; lpBuffer
0x18001bb7c  mov     [rsp+0D0h+lpOverlapped], r12; lpOverlapped
0x18001bb81  call    cs:__imp_ReadFile
0x18001bb87  test    eax, eax
0x18001bb89  jz      loc_18001C616
0x18001bb8f  cmp     [rbp+57h+NumberOfBytesRead], 1Ah
0x18001bb93  jnz     loc_18001C616
0x18001bb99  movzx   ecx, byte ptr [rbp+57h+var_68+1]
0x18001bb9d  movzx   eax, byte ptr [rbp+57h+var_68]
0x18001bba1  mov     [rdi], r14w
0x18001bba5  shl     cx, 8
0x18001bba9  or      cx, ax
0x18001bbac  mov     [rdi+2], cx
0x18001bbb0  movzx   ecx, byte ptr [rbp+57h+var_66+1]
0x18001bbb4  movzx   eax, byte ptr [rbp+57h+var_66]
0x18001bbb8  shl     cx, 8
0x18001bbbc  or      cx, ax
0x18001bbbf  mov     [rdi+46h], cx
0x18001bbc3  mov     [rdi+4], cx
0x18001bbc7  movzx   eax, byte ptr [rbp+57h+var_64]
0x18001bbcb  mov     word ptr [rbp+57h+NumberOfBytesRead], cx
0x18001bbcf  movzx   ecx, byte ptr [rbp+57h+var_64+1]
0x18001bbd3  shl     cx, 8
0x18001bbd7  or      cx, ax
0x18001bbda  mov     [rdi+6], cx
0x18001bbde  movzx   eax, byte ptr [rbp+57h+var_60]
0x18001bbe2  movzx   ecx, byte ptr [rbp+57h+var_60+1]
0x18001bbe6  shl     ecx, 8
0x18001bbe9  or      ecx, eax
0x18001bbeb  movzx   eax, byte ptr [rbp+57h+var_62+1]
0x18001bbef  shl     ecx, 10h
0x18001bbf2  shl     eax, 8
0x18001bbf5  or      ecx, eax
0x18001bbf7  movzx   eax, byte ptr [rbp+57h+var_62]
0x18001bbfb  or      ecx, eax
0x18001bbfd  mov     [rdi+8], ecx
0x18001bc00  movzx   eax, byte ptr [rbp+57h+var_5C]
0x18001bc04  movzx   ecx, byte ptr [rbp+57h+var_5C+1]
0x18001bc08  shl     ecx, 8
0x18001bc0b  or      ecx, eax
0x18001bc0d  movzx   eax, byte ptr [rbp+57h+var_5E+1]
0x18001bc11  shl     eax, 8
0x18001bc14  shl     ecx, 10h
0x18001bc17  or      ecx, eax
0x18001bc19  movzx   eax, byte ptr [rbp+57h+var_5E]
0x18001bc1d  or      ecx, eax
0x18001bc1f  mov     [rdi+0Ch], ecx
0x18001bc22  movzx   eax, byte ptr [rbp+57h+var_58]
0x18001bc26  movzx   r14d, byte ptr [rbp+57h+var_58+1]
0x18001bc2b  shl     r14, 8
0x18001bc2f  or      r14, rax
0x18001bc32  movzx   eax, byte ptr [rbp+57h+var_5A+1]
0x18001bc36  shl     r14, 8
0x18001bc3a  or      r14, rax
0x18001bc3d  movzx   eax, byte ptr [rbp+57h+var_5A]
0x18001bc41  shl     r14, 8
0x18001bc45  or      r14, rax
0x18001bc48  mov     [rdi+10h], r14
0x18001bc4c  movzx   eax, byte ptr [rbp+57h+var_54]
0x18001bc50  movzx   ecx, byte ptr [rbp+57h+var_54+1]
0x18001bc54  shl     rcx, 8
0x18001bc58  or      rcx, rax
0x18001bc5b  movzx   eax, byte ptr [rbp+57h+var_56+1]
0x18001bc5f  shl     rcx, 8
0x18001bc63  or      rcx, rax
0x18001bc66  movzx   eax, byte ptr [rbp+57h+var_56]
0x18001bc6a  shl     rcx, 8
0x18001bc6e  or      rcx, rax
0x18001bc71  mov     [rdi+18h], rcx
0x18001bc75  movzx   eax, byte ptr [rbp+57h+var_52]
0x18001bc79  movzx   r15d, byte ptr [rbp+57h+var_52+1]
0x18001bc7e  shl     r15, 8
0x18001bc82  or      r15, rax
0x18001bc85  mov     [rdi+20h], r15
0x18001bc89  movzx   eax, byte ptr [rbp+57h+var_50]
0x18001bc8d  movzx   ecx, byte ptr [rbp+57h+var_50+1]
0x18001bc91  shl     rcx, 8
0x18001bc95  or      rcx, rax
0x18001bc98  mov     eax, [rbp+57h+var_70]
0x18001bc9b  mov     [rdi+28h], rcx
0x18001bc9f  xor     ecx, ecx
0x18001bca1  mov     [rdi+48h], eax
0x18001bca4  lea     rax, [rdi+98h]
0x18001bcab  mov     [rdi+38h], rcx
0x18001bcaf  mov     [rdi+40h], ecx
0x18001bcb2  mov     [rdi+44h], cx
0x18001bcb6  mov     [rdi+80h], cx
0x18001bcbd  mov     [r13+0], rdi
0x18001bcc1  mov     [rbp+57h+var_80], rax
0x18001bcc5  mov     [rax], rcx
0x18001bcc8  test    r15, r15
0x18001bccb  jz      loc_18001C604
0x18001bcd1  lea     rcx, [r15+1]; Size
0x18001bcd5  call    _o_malloc_0
0x18001bcda  mov     [rdi+78h], rax
0x18001bcde  mov     r13, rax
0x18001bce1  test    rax, rax
0x18001bce4  jz      loc_18001C7A6
0x18001bcea  mov     rcx, [rdi+28h]; Size
0x18001bcee  test    rcx, rcx
0x18001bcf1  jz      short loc_18001BD05
0x18001bcf3  call    _o_malloc_0
0x18001bcf8  mov     [rdi+60h], rax
0x18001bcfc  test    rax, rax
0x18001bcff  jz      loc_18001C7A6
0x18001bd05  mov     byte ptr [r13+0], 0
0x18001bd0a  mov     r8, r15
0x18001bd0d  mov     rdx, [rdi+78h]
0x18001bd11  mov     rcx, [rbx+5418h]; hFile
0x18001bd18  call    GetSomeBytes
0x18001bd1d  test    eax, eax
0x18001bd1f  jz      loc_18001C616
0x18001bd25  mov     rax, [rdi+78h]
0x18001bd29  mov     byte ptr [r15+rax], 0
0x18001bd2e  mov     r8, [rdi+28h]
0x18001bd32  test    r8, r8
0x18001bd35  jz      short loc_18001BD4F
0x18001bd37  mov     rdx, [rdi+60h]
0x18001bd3b  mov     rcx, [rbx+5418h]; hFile
0x18001bd42  call    GetSomeBytes
0x18001bd47  test    eax, eax
0x18001bd49  jz      loc_18001C616
0x18001bd4f  xor     ecx, ecx
0x18001bd51  lea     rax, [rbp+57h+var_90]
0x18001bd55  mov     [rsp+0D0h+var_A0], rax; __int64
0x18001bd5a  lea     r9, [rdi+10h]
0x18001bd5e  mov     [rsp+0D0h+var_A8], rcx; __int64
0x18001bd63  lea     r8, [rdi+18h]
0x18001bd67  mov     [rsp+0D0h+lpOverlapped], rcx; __int64
0x18001bd6c  lea     rdx, [rdi+28h]
0x18001bd70  mov     [rbp+57h+var_90], rcx
0x18001bd74  mov     [rdi+88h], rcx
0x18001bd7b  mov     rcx, [rdi+60h]; Src
0x18001bd7f  call    ParseExtra64
0x18001bd84  test    eax, eax
0x18001bd86  jz      short loc_18001BD97
0x18001bd88  mov     rax, [rbp+57h+var_90]
0x18001bd8c  mov     r14, [rdi+10h]
0x18001bd90  mov     [rdi+88h], rax
0x18001bd97  test    r14, r14
0x18001bd9a  jz      short loc_18001BDBB
0x18001bd9c  mov     rcx, [rbx+5418h]
0x18001bda3  mov     r8d, 1
0x18001bda9  mov     rdx, r14
0x18001bdac  call    DZSetFilePointer
0x18001bdb1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bdb5  jz      loc_18001BF0A
0x18001bdbb  mov     eax, 800h
0x18001bdc0  test    [rdi+4], ax
0x18001bdc4  jnz     short loc_18001BDD6
0x18001bdc6  mov     rcx, [rdi+78h]; lpszSrc
0x18001bdca  mov     r8d, r15d; cchDstLength
0x18001bdcd  mov     rdx, rcx; lpszDst
0x18001bdd0  call    cs:__imp_OemToCharBuffA
0x18001bdd6  mov     r13, [rdi+78h]
0x18001bdda  mov     rcx, r13; lpString
0x18001bddd  call    cs:__imp_lstrlenA
0x18001bde3  inc     eax
0x18001bde5  mov     ecx, eax; Size
  ... truncated ...
```
