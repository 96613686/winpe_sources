# CJob::SaveP(ushort const *,int,ulong)

- ea: `0x180025ed4`
- end: `0x1800267f3`
- name: `?SaveP@CJob@@QEAAJPEBGHK@Z`
- size: `2335`
- prototype: `__int64 __fastcall(CJob *__hidden this, LPCWSTR lpFileName, int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800267fc`

## callees

- `0x1800040c0`
- `0x180007948`
- `0x180007988`
- `0x180008c66`
- `0x1800254fc`
- `0x180025794`
- `0x180025ed4`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026627`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026092`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026324`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026647`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026092`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026324`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026647`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002633c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002633c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002674e`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002674e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800265bf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002660c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180026720`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800265bf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002660c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180026720`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800265e3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800265e3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180025f85`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180025f85`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026057`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026057`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180025fe4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180025fe4`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18002607b`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18002607b`
- `SspiCli!GetUserNameExW` at `0x1800260db`
- `SspiCli!GetUserNameExW` at `0x1800260db`
- `ext-ms-win-shell-directory-l1-1-0!SHChangeNotify` at `0x180026698`
- `ext-ms-win-shell-directory-l1-1-0!SHChangeNotify` at `0x18002677c`
- `ext-ms-win-shell-directory-l1-1-0!SHChangeNotify` at `0x180026698`
- `ext-ms-win-shell-directory-l1-1-0!SHChangeNotify` at `0x18002677c`

## pseudocode

```c
signed int __fastcall CJob::SaveP(CJob *this, LPCWSTR lpFileName, int a3, DWORD a4)
{
  LPCWSTR *v5; // rsi
  const WCHAR *v6; // r15
  _DWORD *v7; // r14
  const WCHAR *v8; // rcx
  signed int result; // eax
  DWORD dwCreationDisposition; // r13d
  DWORD v11; // ebx
  unsigned int v12; // ebx
  HANDLE FileW; // rax
  HANDLE v14; // r13
  unsigned __int16 *v15; // rax
  int v16; // ecx
  BOOL v17; // eax
  int v18; // ebx
  __int128 v19; // xmm0
  DWORD v20; // r14d
  __int128 v21; // xmm0
  int v22; // r14d
  signed int i; // ecx
  __int64 v24; // r8
  _WORD *v25; // rdx
  __int64 v26; // rax
  WCHAR v27; // ax
  unsigned __int16 v28; // cx
  int v29; // edx
  int v30; // edx
  ULONG v31; // eax
  ULONG v32; // ecx
  DWORD v33; // eax
  char *v34; // rax
  __m256i *v35; // r15
  signed int v36; // ebx
  char *v37; // rbx
  unsigned int v38; // esi
  unsigned int v39; // r13d
  unsigned int v40; // esi
  __int64 v41; // rax
  char *v42; // rbx
  unsigned int v43; // esi
  char *v44; // rbx
  __int64 v45; // rcx
  __int64 *v46; // rdx
  unsigned int v47; // esi
  unsigned int v48; // esi
  char *v49; // rbx
  __int64 v50; // rax
  unsigned int v51; // esi
  char *v52; // rcx
  unsigned __int16 v53; // ax
  unsigned int v54; // r13d
  size_t v55; // rbx
  _WORD *v56; // rsi
  unsigned int v57; // r13d
  _OWORD *v58; // rax
  DWORD v59; // r14d
  signed int LastError; // eax
  const unsigned __int16 *v61; // rbx
  void **v62; // r14
  __int64 v63; // rsi
  __int64 v64; // rcx
  unsigned __int16 *v65; // rax
  ULONG nSize; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  int v68; // [rsp+48h] [rbp-B8h]
  DWORD v69; // [rsp+4Ch] [rbp-B4h]
  int v70; // [rsp+50h] [rbp-B0h]
  __int64 Src; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hFile; // [rsp+60h] [rbp-A0h]
  LPCVOID *v73; // [rsp+68h] [rbp-98h]
  LPCWSTR lpFileNamea; // [rsp+70h] [rbp-90h]
  LPCVOID dwItem1; // [rsp+78h] [rbp-88h]
  __int64 v76; // [rsp+80h] [rbp-80h]
  __m256i v77; // [rsp+90h] [rbp-70h] BYREF
  __int128 v78; // [rsp+B0h] [rbp-50h]
  _BYTE v79[22]; // [rsp+C0h] [rbp-40h]
  _OWORD FileInformation[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v81; // [rsp+100h] [rbp+0h]
  WCHAR v82[12]; // [rsp+108h] [rbp+8h]
  WCHAR NameBuffer[264]; // [rsp+120h] [rbp+20h] BYREF

  NumberOfBytesWritten = a4;
  v68 = a3;
  dwItem1 = lpFileName;
  v5 = (LPCWSTR *)((char *)this + 152);
  if ( lpFileName )
  {
    v6 = lpFileName;
    lpFileNamea = lpFileName;
  }
  else
  {
    v6 = *v5;
    lpFileNamea = v6;
    if ( !v6 )
      return -2147024809;
  }
  v73 = (LPCVOID *)((char *)this + 152);
  if ( !*v6 )
    return -2147024809;
  if ( v6 != *v5 || (v7 = (_DWORD *)((char *)this + 160), !*((_DWORD *)this + 40)) )
  {
    if ( (a4 & 1) != 0 )
    {
      dwCreationDisposition = 1;
      v70 = 1;
      v12 = (*((_DWORD *)this + 22) & 0x200) != 0 ? 0xFFFFFF82 : 0;
      NumberOfBytesWritten = a4 | 2;
      v11 = v12 + 128;
      GenerateUniqueID((struct _GUID *)((char *)this + 44));
      v7 = (_DWORD *)((char *)this + 160);
      goto LABEL_16;
    }
    return -2147024809;
  }
  v8 = *v5;
  v81 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileAttributesExW(v8, GetFileExInfoStandard, FileInformation) )
    goto LABEL_8;
  dwCreationDisposition = 3;
  v70 = 3;
  v11 = FileInformation[0] & 0xFFFFFFFC | 2;
  if ( (*((_DWORD *)this + 22) & 0x200) == 0 )
    v11 = FileInformation[0] & 0xFFFFFFFE;
  if ( v11 != LODWORD(FileInformation[0]) )
    SetFileAttributesW(*v5, v11);
LABEL_16:
  FileW = CreateFileW(v6, 0x40000000u, 5u, 0, dwCreationDisposition, v11 | 0x8000000, 0);
  hFile = FileW;
  v14 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_8:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( GetFileType(FileW) != 1 )
  {
    CloseHandle(v14);
    return -2147024891;
  }
  if ( v68 || lpFileNamea == *v5 )
    *v7 = 1;
  if ( !*((_QWORD *)this + 17) )
  {
    nSize = 257;
    if ( GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
    {
      v15 = (unsigned __int16 *)operator new(saturated_mul(nSize + 1, 2u));
      *((_QWORD *)this + 17) = v15;
      if ( !v15 )
      {
LABEL_54:
        v36 = -2147024882;
        if ( v14 )
          CloseHandle(v14);
        goto LABEL_56;
      }
      StringCchCopyW(v15, nSize + 1, NameBuffer);
    }
  }
  v16 = *((_DWORD *)this + 22);
  v17 = 0;
  if ( (v16 & 4) != 0 )
  {
    if ( *((_DWORD *)this + 21) != 267009 )
      *((_DWORD *)this + 21) = 267010;
  }
  else
  {
    v17 = *((_DWORD *)this + 21) == 267010;
  }
  if ( v16 < 0 )
    v17 = 1;
  if ( (v16 & 0x10000000) != 0 )
  {
    *((_DWORD *)this + 22) = v16 & 0xCFFFFFFF;
LABEL_35:
    CJob::UpdateJobState(this, 0);
    goto LABEL_36;
  }
  if ( v17 )
    goto LABEL_35;
LABEL_36:
  v18 = *((_DWORD *)this + 22);
  if ( (v18 & 0x10000) != 0 )
  {
    GenerateUniqueID((struct _GUID *)((char *)this + 44));
    *((_DWORD *)this + 22) &= ~0x10000u;
    v18 = *((_DWORD *)this + 22);
  }
  if ( (NumberOfBytesWritten & 4) == 0 )
  {
    v18 &= ~0x200000u;
    *((_DWORD *)this + 22) = v18;
  }
  memset_0(&v77, 0, 0x48u);
  v19 = *(_OWORD *)((char *)this + 44);
  v77.m256i_i32[0] = *((_DWORD *)this + 10);
  v77.m256i_i16[10] = 70;
  *(__int32 *)((char *)&v77.m256i_i32[5] + 2) = *((_DWORD *)this + 15);
  v77.m256i_i16[13] = *((_WORD *)this + 32);
  v77.m256i_i16[15] = *((_WORD *)this + 34);
  v77.m256i_i16[14] = *((_WORD *)this + 35);
  v78 = *(_OWORD *)((char *)this + 72);
  *(_WORD *)&v79[20] = *((_WORD *)this + 33);
  *(_DWORD *)v79 = v18 & 0x3FFDFFFF;
  *(_OWORD *)((char *)v77.m256i_i64 + 4) = v19;
  v20 = (NumberOfBytesWritten & 3) != 0 ? 70 : 68;
  v21 = *((_OWORD *)this + 6);
  v69 = NumberOfBytesWritten & 1;
  *(_OWORD *)&v79[4] = v21;
  if ( (NumberOfBytesWritten & 1) == 0 )
  {
    v35 = &v77;
    goto LABEL_104;
  }
  v22 = (NumberOfBytesWritten & 3) != 0 ? 80 : 78;
  for ( i = 0; (unsigned int)i < 5; ++i )
  {
    v24 = i;
    v25 = *(_WORD **)((char *)this + *((int *)CJob::s_StringField + i));
    if ( v25 && *v25 )
    {
      v26 = -1;
      do
        ++v26;
      while ( v25[v26] );
      v27 = v26 + 1;
    }
    else
    {
      v27 = 0;
    }
    v82[v24] = v27;
    v22 += 2 * v27;
  }
  v28 = *((_WORD *)this + 89);
  if ( v28 < 8u )
  {
    *((_WORD *)this + 89) = 8;
    v28 = 8;
  }
  v29 = *((unsigned __int16 *)this + 88);
  nSize = *((unsigned __int16 *)this + 16);
  v30 = v28 + 4 + v22 + v29;
  v31 = 48 * nSize;
  v76 = 48 * nSize;
  *((_WORD *)this + 30) = v30;
  v77.m256i_i16[11] = v30;
  v32 = v30 + v31 + 2;
  v33 = v32 + 68;
  if ( !*((_QWORD *)this + 26) )
    v33 = v32;
  v20 = v33;
  v34 = (char *)operator new(v33);
  v14 = hFile;
  v35 = (__m256i *)v34;
  if ( !v34 )
    goto LABEL_54;
  if ( v20 < 0x46 )
  {
    v36 = -2147418113;
    goto LABEL_90;
  }
  v37 = v34 + 70;
  *(__m256i *)v34 = v77;
  v38 = v20 - 70;
  v39 = 0;
  *((_OWORD *)v34 + 2) = v78;
  *((_OWORD *)v34 + 3) = *(_OWORD *)v79;
  *(_QWORD *)(v34 + 62) = *(_QWORD *)&v79[14];
  while ( v39 < 5 )
  {
    if ( v38 < 2 )
      goto LABEL_66;
    v40 = v38 - 2;
    v41 = v82[v39];
    *(_WORD *)v37 = v41;
    Src = 2 * v41;
    if ( 2 * v41 > (unsigned __int64)v40 )
      goto LABEL_66;
    v42 = v37 + 2;
    memcpy_0(v42, *(const void **)((char *)this + *((int *)CJob::s_StringField + (int)v39)), 2 * v41);
    v37 = &v42[Src];
    v38 = v40 - 2 * v82[v39++];
  }
  if ( v38 < 2 )
    goto LABEL_66;
  v43 = v38 - 2;
  *(_WORD *)v37 = *((_WORD *)this + 88);
  if ( *((unsigned __int16 *)this + 88) > v43 )
    goto LABEL_66;
  v44 = v37 + 2;
  memcpy_0(v44, *((const void **)this + 21), *((unsigned __int16 *)this + 88));
  v45 = *((unsigned __int16 *)this + 88);
  v46 = (__int64 *)*((_QWORD *)this + 23);
  v47 = v43 - v45;
  LODWORD(Src) = *((_DWORD *)this + 48);
  HIDWORD(Src) = *((_DWORD *)this + 23);
  if ( v46 )
  {
    *v46 = Src;
    if ( v47 < 2 )
      goto LABEL_66;
    v48 = v47 - 2;
    *(_WORD *)&v44[v45] = *((_WORD *)this + 89);
    if ( *((unsigned __int16 *)this + 89) > v48 )
      goto LABEL_66;
    v49 = &v44[v45 + 2];
    memcpy_0(v49, *((const void **)this + 23), *((unsigned __int16 *)this + 89));
    v50 = *((unsigned __int16 *)this + 89);
  }
  else
  {
    *((_WORD *)this + 89) = 8;
    if ( v47 < 2 )
      goto LABEL_66;
    *(_WORD *)&v44[v45] = 8;
    v48 = v47 - 2;
    if ( *((unsigned __int16 *)this + 89) > v48 )
      goto LABEL_66;
    v49 = &v44[v45 + 2];
    memcpy_0(v49, &Src, *((unsigned __int16 *)this + 89));
    v50 = *((unsigned __int16 *)this + 89);
    *((_WORD *)this + 89) = 0;
  }
  v51 = v48 - v50;
  v52 = &v49[v50];
  if ( v51 < 2 )
    goto LABEL_66;
  v53 = nSize;
  v54 = v51 - 2;
  *(_WORD *)v52 = nSize;
  v55 = 48LL * v53;
  if ( v55 > v51 - 2 )
    goto LABEL_66;
  v56 = v52 + 2;
  memcpy_0(v52 + 2, *((const void **)this + 3), v55);
  if ( !*((_QWORD *)this + 26) )
    goto LABEL_82;
  v57 = v54 - v76;
  nSize = 65537;
  if ( v57 < 4 || (*(_DWORD *)&v56[v55 / 2] = nSize, v57 - 4 < 0x40) )
  {
LABEL_66:
    v36 = -2147418113;
    goto LABEL_90;
  }
  v58 = (_OWORD *)*((_QWORD *)this + 26);
  *(_OWORD *)&v56[v55 / 2 + 2] = *v58;
  *(_OWORD *)&v56[v55 / 2 + 10] = v58[1];
  *(_OWORD *)&v56[v55 / 2 + 18] = v58[2];
  *(_OWORD *)&v56[v55 / 2 + 26] = v58[3];
LABEL_82:
  v14 = hFile;
  if ( (NumberOfBytesWritten & 2) == 0 )
  {
    NumberOfBytesWritten = 0;
    if ( !WriteFile(hFile, v35, 0x44u, &NumberOfBytesWritten, 0) )
      goto LABEL_88;
    if ( NumberOfBytesWritten != 68 )
      goto LABEL_88;
    if ( SetFilePointer(v14, 2, 0, 1u) == -1 )
      goto LABEL_88;
    v59 = v20 - 70;
    if ( !WriteFile(v14, &v35[2].m256i_u16[3], v59, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != v59 )
      goto LABEL_88;
    goto LABEL_106;
  }
LABEL_104:
  nSize = 0;
  if ( !WriteFile(v14, v35, v20, &nSize, 0) || nSize != v20 )
  {
LABEL_88:
    LastError = GetLastError();
    v36 = LastError;
    if ( LastError > 0 )
      v36 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_90;
  }
LABEL_106:
  v36 = 0;
  if ( v69 )
    SetEndOfFile(v14);
LABEL_90:
  CloseHandle(hFile);
  if ( v35 != &v77 )
    operator delete(v35);
  if ( v36 < 0 )
    goto LABEL_56;
  v61 = (const unsigned __int16 *)dwItem1;
  if ( !NtCurrentPeb()->SessionId )
    goto LABEL_96;
  if ( dwItem1 )
  {
    SHChangeNotify(2, 5u, dwItem1, 0);
LABEL_96:
    v62 = (void **)v73;
    goto LABEL_97;
  }
  v62 = (void **)v73;
  if ( *v73 )
    SHChangeNotify(0x2000, 5u, *v73, 0);
LABEL_97:
  if ( !v68 )
  {
    if ( v61 )
      return 0;
LABEL_113:
    *((_DWORD *)this + 22) &= ~0x40000000u;
    if ( v69 )
      *((_DWORD *)this + 22) &= ~0x80000000;
    return 0;
  }
  if ( !v61 )
    goto LABEL_113;
  operator delete(*v62);
  v63 = -1;
  v64 = -1;
  do
    ++v64;
  while ( v61[v64] );
  v65 = (unsigned __int16 *)operator new(saturated_mul(v64 + 1, 2u));
  *v62 = v65;
  if ( v65 )
  {
    do
      ++v63;
    while ( v61[v63] );
    StringCchCopyW(v65, v63 + 1, v61);
    goto LABEL_113;
  }
  v36 = -2147024882;
LABEL_56:
  if ( v70 == 1 )
    DeleteFileW(lpFileNamea);
  return v36;
}

```

## disassembly

```asm
0x180025ed4  mov     [rsp-8+arg_10], rbx
0x180025ed9  push    rbp
0x180025eda  push    rsi
0x180025edb  push    rdi
0x180025edc  push    r12
0x180025ede  push    r13
0x180025ee0  push    r14
0x180025ee2  push    r15
0x180025ee4  lea     rbp, [rsp-240h]
0x180025eec  sub     rsp, 340h
0x180025ef3  mov     rax, cs:__security_cookie
0x180025efa  xor     rax, rsp
0x180025efd  mov     [rbp+270h+var_40], rax
0x180025f04  xor     ebx, ebx
0x180025f06  mov     [rsp+370h+NumberOfBytesWritten], r9d
0x180025f0b  mov     [rsp+370h+var_328], r8d
0x180025f10  mov     rdi, rcx
0x180025f13  mov     [rsp+370h+dwItem1], rdx
0x180025f18  lea     rsi, [rcx+98h]
0x180025f1f  test    rdx, rdx
0x180025f22  jz      short loc_180025F2E
0x180025f24  mov     r15, rdx
0x180025f27  mov     [rsp+370h+lpFileName], rdx
0x180025f2c  jmp     short loc_180025F3F
0x180025f2e  mov     r15, [rsi]
0x180025f31  mov     [rsp+370h+lpFileName], r15
0x180025f36  test    r15, r15
0x180025f39  jz      loc_1800267C3
0x180025f3f  mov     [rsp+370h+var_308], rsi
0x180025f44  cmp     [r15], bx
0x180025f48  jz      loc_1800267C3
0x180025f4e  mov     eax, 1
0x180025f53  cmp     r15, [rsi]
0x180025f56  jnz     loc_180025FF2
0x180025f5c  lea     r14, [rcx+0A0h]
0x180025f63  cmp     [r14], ebx
0x180025f66  jz      loc_180025FF2
0x180025f6c  mov     rcx, [rsi]; lpFileName
0x180025f6f  lea     r8, [rbp+270h+FileInformation]; lpFileInformation
0x180025f73  xorps   xmm0, xmm0
0x180025f76  xor     eax, eax
0x180025f78  xor     edx, edx; fInfoLevelId
0x180025f7a  mov     [rbp+270h+var_270], eax
0x180025f7d  movups  [rbp+270h+FileInformation], xmm0
0x180025f81  movups  [rbp+270h+var_280], xmm0
0x180025f85  call    cs:__imp_GetFileAttributesExW
0x180025f8c  nop     dword ptr [rax+rax+00h]
0x180025f91  test    eax, eax
0x180025f93  jnz     short loc_180025FB6
0x180025f95  call    cs:__imp_GetLastError
0x180025f9c  nop     dword ptr [rax+rax+00h]
0x180025fa1  test    eax, eax
0x180025fa3  jle     loc_1800267C8
0x180025fa9  movzx   eax, ax
0x180025fac  or      eax, 80070000h
0x180025fb1  jmp     loc_1800267C8
0x180025fb6  mov     ecx, dword ptr [rbp+270h+FileInformation]
0x180025fb9  mov     r13d, 3
0x180025fbf  and     ecx, 0FFFFFFFEh
0x180025fc2  mov     [rsp+370h+var_320], r13d
0x180025fc7  mov     ebx, ecx
0x180025fc9  lea     r12d, [r13-1]
0x180025fcd  or      ebx, r12d
0x180025fd0  test    dword ptr [rdi+58h], 200h
0x180025fd7  cmovz   ebx, ecx
0x180025fda  cmp     ebx, dword ptr [rbp+270h+FileInformation]
0x180025fdd  jz      short loc_180026032
0x180025fdf  mov     rcx, [rsi]; lpFileName
0x180025fe2  mov     edx, ebx; dwFileAttributes
0x180025fe4  call    cs:__imp_SetFileAttributesW
0x180025feb  nop     dword ptr [rax+rax+00h]
0x180025ff0  jmp     short loc_180026032
0x180025ff2  test    al, r9b
0x180025ff5  jz      loc_1800267C3
0x180025ffb  mov     r13d, eax
0x180025ffe  mov     [rsp+370h+var_320], eax
0x180026002  mov     eax, [rcx+58h]
0x180026005  mov     r12d, 2
0x18002600b  and     eax, 200h
0x180026010  neg     eax
0x180026012  sbb     ebx, ebx
0x180026014  or      r9d, r12d
0x180026017  and     ebx, 0FFFFFF82h
0x18002601a  mov     [rsp+370h+NumberOfBytesWritten], r9d
0x18002601f  sub     ebx, 0FFFFFF80h
0x180026022  add     rcx, 2Ch ; ','; struct _GUID *
0x180026026  call    ?GenerateUniqueID@@YAXPEAU_GUID@@@Z; GenerateUniqueID(_GUID *)
0x18002602b  lea     r14, [rdi+0A0h]
0x180026032  xor     r9d, r9d; lpSecurityAttributes
0x180026035  mov     [rsp+370h+hTemplateFile], 0; hTemplateFile
0x18002603e  bts     ebx, 1Bh
0x180026042  mov     edx, 40000000h; dwDesiredAccess
0x180026047  mov     [rsp+370h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18002604b  mov     rcx, r15; lpFileName
0x18002604e  mov     [rsp+370h+dwCreationDisposition], r13d; dwCreationDisposition
0x180026053  lea     r8d, [r9+5]; dwShareMode
0x180026057  call    cs:__imp_CreateFileW
0x18002605e  nop     dword ptr [rax+rax+00h]
0x180026063  or      r15, 0FFFFFFFFFFFFFFFFh
0x180026067  mov     [rsp+370h+hFile], rax
0x18002606c  mov     r13, rax
0x18002606f  cmp     rax, r15
0x180026072  jz      loc_180025F95
0x180026078  mov     rcx, rax; hFile
0x18002607b  call    cs:__imp_GetFileType
0x180026082  nop     dword ptr [rax+rax+00h]
0x180026087  lea     edx, [r15+2]
0x18002608b  cmp     eax, edx
0x18002608d  jz      short loc_1800260A8
0x18002608f  mov     rcx, r13; hObject
0x180026092  call    cs:__imp_CloseHandle
0x180026099  nop     dword ptr [rax+rax+00h]
0x18002609e  mov     eax, 80070005h
0x1800260a3  jmp     loc_1800267C8
0x1800260a8  cmp     [rsp+370h+var_328], 0
0x1800260ad  jnz     short loc_1800260B9
0x1800260af  mov     rax, [rsp+370h+lpFileName]
0x1800260b4  cmp     rax, [rsi]
0x1800260b7  jnz     short loc_1800260BC
0x1800260b9  mov     [r14], edx
0x1800260bc  xor     esi, esi
0x1800260be  cmp     [rdi+88h], rsi
0x1800260c5  jnz     short loc_18002612A
0x1800260c7  lea     r8, [rsp+370h+nSize]; nSize
0x1800260cc  mov     [rsp+370h+nSize], 101h
0x1800260d4  lea     rdx, [rbp+270h+NameBuffer]; lpNameBuffer
0x1800260d8  mov     ecx, r12d; NameFormat
0x1800260db  call    cs:__imp_GetUserNameExW
0x1800260e2  nop     dword ptr [rax+rax+00h]
0x1800260e7  test    al, al
0x1800260e9  jz      short loc_180026125
0x1800260eb  mov     ecx, [rsp+370h+nSize]
0x1800260ef  mov     rax, r12
0x1800260f2  inc     ecx
0x1800260f4  mul     rcx
0x1800260f7  cmovb   rax, r15
0x1800260fb  mov     rcx, rax; Size
0x1800260fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026103  mov     [rdi+88h], rax
0x18002610a  mov     rcx, rax; unsigned __int16 *
0x18002610d  test    rax, rax
0x180026110  jz      loc_180026317
0x180026116  mov     edx, [rsp+370h+nSize]
0x18002611a  lea     r8, [rbp+270h+NameBuffer]; unsigned __int16 *
0x18002611e  inc     edx; unsigned __int64
0x180026120  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026125  mov     edx, 1
0x18002612a  mov     ecx, [rdi+58h]
0x18002612d  mov     eax, esi
0x18002612f  test    cl, 4
0x180026132  jz      short loc_180026146
0x180026134  cmp     dword ptr [rdi+54h], 41301h
0x18002613b  jz      short loc_180026150
0x18002613d  mov     dword ptr [rdi+54h], 41302h
0x180026144  jmp     short loc_180026150
0x180026146  cmp     dword ptr [rdi+54h], 41302h
0x18002614d  cmovz   eax, edx
0x180026150  test    ecx, ecx
0x180026152  cmovs   eax, edx
0x180026155  bt      ecx, 1Ch
0x180026159  jnb     short loc_180026166
0x18002615b  and     ecx, 0CFFFFFFFh
0x180026161  mov     [rdi+58h], ecx
0x180026164  jmp     short loc_18002616A
0x180026166  test    eax, eax
0x180026168  jz      short loc_180026174
0x18002616a  xor     edx, edx; int
0x18002616c  mov     rcx, rdi; this
0x18002616f  call    ?UpdateJobState@CJob@@QEAAJH@Z; CJob::UpdateJobState(int)
0x180026174  mov     ebx, [rdi+58h]
0x180026177  bt      ebx, 10h
0x18002617b  jnb     short loc_18002618E
0x18002617d  lea     rcx, [rdi+2Ch]; struct _GUID *
0x180026181  call    ?GenerateUniqueID@@YAXPEAU_GUID@@@Z; GenerateUniqueID(_GUID *)
0x180026186  btr     dword ptr [rdi+58h], 10h
0x18002618b  mov     ebx, [rdi+58h]
0x18002618e  test    byte ptr [rsp+370h+NumberOfBytesWritten], 4
0x180026193  mov     esi, 2Ch ; ','
0x180026198  mov     r14, rdi
0x18002619b  jnz     short loc_1800261A4
0x18002619d  btr     ebx, 15h
0x1800261a1  mov     [rdi+58h], ebx
0x1800261a4  xor     edx, edx; Val
0x1800261a6  lea     rcx, [rbp+270h+var_2E0]; void *
0x1800261aa  lea     r8d, [rdx+48h]; Size
0x1800261ae  call    memset_0
0x1800261b3  movups  xmm0, xmmword ptr [rsi+r14]
0x1800261b8  movzx   eax, word ptr [rdi+28h]
0x1800261bc  and     ebx, 3FFDFFFFh
0x1800261c2  mov     word ptr [rbp+270h+var_2E0], ax
0x1800261c6  mov     r9d, 1
0x1800261cc  movzx   eax, word ptr [rdi+2Ah]
0x1800261d0  mov     word ptr [rbp+270h+var_2E0+2], ax
0x1800261d4  mov     eax, 46h ; 'F'
0x1800261d9  mov     [rbp+270h+var_2CC], ax
0x1800261dd  movzx   eax, word ptr [rdi+3Ch]
0x1800261e1  mov     [rbp+270h+var_2CA], ax
0x1800261e5  movzx   eax, word ptr [rdi+3Eh]
0x1800261e9  mov     [rbp+270h+var_2C8], ax
0x1800261ed  movzx   eax, word ptr [rdi+40h]
0x1800261f1  mov     [rbp+270h+var_2C6], ax
0x1800261f5  movzx   eax, word ptr [rdi+44h]
0x1800261f9  mov     [rbp+270h+var_2C2], ax
0x1800261fd  movzx   eax, word ptr [rdi+46h]
0x180026201  mov     [rbp+270h+var_2C4], ax
0x180026205  mov     eax, [rdi+48h]
0x180026208  mov     dword ptr [rbp+270h+var_2C0], eax
0x18002620b  mov     eax, [rdi+4Ch]
0x18002620e  mov     dword ptr [rbp+270h+var_2C0+4], eax
0x180026211  mov     eax, [rdi+50h]
0x180026214  mov     dword ptr [rbp+270h+var_2C0+8], eax
0x180026217  mov     eax, [rdi+54h]
0x18002621a  mov     dword ptr [rbp+270h+var_2C0+0Ch], eax
0x18002621d  movzx   eax, word ptr [rdi+42h]
0x180026221  mov     [rbp+270h+var_29C], ax
0x180026225  mov     eax, [rsp+370h+NumberOfBytesWritten]
0x180026229  and     al, 3
0x18002622b  mov     dword ptr [rbp+270h+var_2B0], ebx
0x18002622e  neg     al
0x180026230  mov     eax, [rsp+370h+NumberOfBytesWritten]
0x180026234  sbb     r14d, r14d
0x180026237  and     r14d, r12d
0x18002623a  movdqu  [rbp+270h+var_2E0+4], xmm0
0x18002623f  add     r14d, 44h ; 'D'
0x180026243  movups  xmm0, xmmword ptr [rdi+60h]
0x180026247  and     eax, r9d
0x18002624a  mov     [rsp+370h+var_324], eax
0x18002624e  movdqu  [rbp+270h+var_2B0+4], xmm0
0x180026253  jz      loc_180026703
0x180026259  add     r14d, 0Ah
0x18002625d  lea     r13, ?s_StringField@CJob@@0QBQEQ1@PEAGB; ushort * CJob::* const near * const CJob::s_StringField
0x180026264  xor     esi, esi
0x180026266  mov     ecx, esi
0x180026268  movsxd  r8, ecx
0x18002626b  movsxd  rax, dword ptr [r13+r8*4+0]
0x180026270  mov     rdx, [rax+rdi]
0x180026274  test    rdx, rdx
0x180026277  jz      short loc_18002628F
0x180026279  cmp     [rdx], si
0x18002627c  jz      short loc_18002628F
0x18002627e  mov     rax, r15
0x180026281  inc     rax
0x180026284  cmp     [rdx+rax*2], si
0x180026288  jnz     short loc_180026281
0x18002628a  inc     rax
0x18002628d  jmp     short loc_180026292
0x18002628f  mov     rax, rsi
0x180026292  movzx   eax, ax
0x180026295  add     ecx, r9d
0x180026298  mov     [rbp+r8*2+270h+var_268], ax
0x18002629e  lea     r14d, [r14+rax*2]
0x1800262a2  cmp     ecx, 5
0x1800262a5  jb      short loc_180026268
0x1800262a7  movzx   ecx, word ptr [rdi+0B2h]
0x1800262ae  mov     eax, 8
0x1800262b3  cmp     cx, ax
0x1800262b6  jnb     short loc_1800262C2
0x1800262b8  mov     [rdi+0B2h], ax
0x1800262bf  movzx   ecx, ax
0x1800262c2  movzx   eax, word ptr [rdi+20h]
0x1800262c6  movzx   edx, word ptr [rdi+0B0h]
0x1800262cd  mov     [rsp+370h+nSize], eax
0x1800262d1  add     edx, r14d
0x1800262d4  movzx   ecx, cx
0x1800262d7  add     ecx, 4
0x1800262da  lea     eax, [rax+rax*2]
0x1800262dd  add     edx, ecx
0x1800262df  shl     eax, 4
0x1800262e2  mov     [rbp+270h+var_2F0], rax
0x1800262e6  mov     [rdi+3Ch], dx
0x1800262ea  mov     [rbp+270h+var_2CA], dx
0x1800262ee  lea     ecx, [rax+2]
0x1800262f1  add     ecx, edx
0x1800262f3  cmp     [rdi+0D0h], rsi
0x1800262fa  lea     eax, [rcx+44h]
0x1800262fd  cmovz   eax, ecx
0x180026300  mov     ecx, eax; Size
0x180026302  mov     r14d, eax
0x180026305  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002630a  mov     r13, [rsp+370h+hFile]
0x18002630f  mov     r15, rax
0x180026312  test    rax, rax
0x180026315  jnz     short loc_18002634F
0x180026317  mov     ebx, 8007000Eh
0x18002631c  test    r13, r13
0x18002631f  jz      short loc_180026330
0x180026321  mov     rcx, r13; hObject
0x180026324  call    cs:__imp_CloseHandle
0x18002632b  nop     dword ptr [rax+rax+00h]
0x180026330  cmp     [rsp+370h+var_320], 1
0x180026335  jnz     short loc_180026348
0x180026337  mov     rcx, [rsp+370h+lpFileName]; lpFileName
0x18002633c  call    cs:__imp_DeleteFileW
0x180026343  nop     dword ptr [rax+rax+00h]
0x180026348  mov     eax, ebx
0x18002634a  jmp     loc_1800267C8
0x18002634f  cmp     r14d, 46h ; 'F'
0x180026353  jnb     short loc_18002635F
0x180026355  mov     ebx, 8000FFFFh
0x18002635a  jmp     loc_180026642
  ... truncated ...
```
