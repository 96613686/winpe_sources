# CJob::SaveP(ushort const *,int,ulong)

- ea: `0x1800247dc`
- end: `0x18002508a`
- name: `?SaveP@CJob@@QEAAJPEBGHK@Z`
- size: `2222`
- prototype: `signed int __fastcall(CJob *this, LPCWSTR lpFileName, int, DWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180025090`

## callees

- `0x180003ef0`
- `0x180007488`
- `0x1800074c8`
- `0x1800087a6`
- `0x180023e5c`
- `0x1800240e4`
- `0x1800247dc`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024978`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024bfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024efd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024978`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024bfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024efd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180024c10`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180024c10`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180024ff2`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180024ff2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180024e8d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180024ece`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180024fca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180024e8d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180024ece`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180024fca`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180024eab`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180024eab`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180024889`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180024889`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024949`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024949`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800248dc`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800248dc`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180024967`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180024967`
- `SspiCli!GetUserNameExW` at `0x1800249bb`
- `SspiCli!GetUserNameExW` at `0x1800249bb`
- `ext-ms-win-shell-directory-l1-1-0!SHChangeNotify` at `0x180024f48`
- `ext-ms-win-shell-directory-l1-1-0!SHChangeNotify` at `0x18002501a`
- `ext-ms-win-shell-directory-l1-1-0!SHChangeNotify` at `0x180024f48`
- `ext-ms-win-shell-directory-l1-1-0!SHChangeNotify` at `0x18002501a`

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
0x1800247dc  mov     [rsp-8+arg_10], rbx
0x1800247e1  push    rbp
0x1800247e2  push    rsi
0x1800247e3  push    rdi
0x1800247e4  push    r12
0x1800247e6  push    r13
0x1800247e8  push    r14
0x1800247ea  push    r15
0x1800247ec  lea     rbp, [rsp-240h]
0x1800247f4  sub     rsp, 340h
0x1800247fb  mov     rax, cs:__security_cookie
0x180024802  xor     rax, rsp
0x180024805  mov     [rbp+270h+var_40], rax
0x18002480c  xor     ebx, ebx
0x18002480e  mov     [rsp+370h+NumberOfBytesWritten], r9d
0x180024813  mov     [rsp+370h+var_328], r8d
0x180024818  mov     rdi, rcx
0x18002481b  mov     [rsp+370h+dwItem1], rdx
0x180024820  lea     rsi, [rcx+98h]
0x180024827  test    rdx, rdx
0x18002482a  jz      short loc_180024836
0x18002482c  mov     r15, rdx
0x18002482f  mov     [rsp+370h+lpFileName], rdx
0x180024834  jmp     short loc_180024847
0x180024836  mov     r15, [rsi]
0x180024839  mov     [rsp+370h+lpFileName], r15
0x18002483e  test    r15, r15
0x180024841  jz      loc_18002505B
0x180024847  mov     [rsp+370h+var_308], rsi
0x18002484c  cmp     [r15], bx
0x180024850  jz      loc_18002505B
0x180024856  mov     eax, 1
0x18002485b  cmp     r15, [rsi]
0x18002485e  jnz     loc_1800248E4
0x180024864  lea     r14, [rcx+0A0h]
0x18002486b  cmp     [r14], ebx
0x18002486e  jz      short loc_1800248E4
0x180024870  mov     rcx, [rsi]; lpFileName
0x180024873  lea     r8, [rbp+270h+FileInformation]; lpFileInformation
0x180024877  xorps   xmm0, xmm0
0x18002487a  xor     eax, eax
0x18002487c  xor     edx, edx; fInfoLevelId
0x18002487e  mov     [rbp+270h+var_270], eax
0x180024881  movups  [rbp+270h+FileInformation], xmm0
0x180024885  movups  [rbp+270h+var_280], xmm0
0x180024889  call    cs:__imp_GetFileAttributesExW
0x18002488f  test    eax, eax
0x180024891  jnz     short loc_1800248AE
0x180024893  call    cs:__imp_GetLastError
0x180024899  test    eax, eax
0x18002489b  jle     loc_180025060
0x1800248a1  movzx   eax, ax
0x1800248a4  or      eax, 80070000h
0x1800248a9  jmp     loc_180025060
0x1800248ae  mov     ecx, dword ptr [rbp+270h+FileInformation]
0x1800248b1  mov     r13d, 3
0x1800248b7  and     ecx, 0FFFFFFFEh
0x1800248ba  mov     [rsp+370h+var_320], r13d
0x1800248bf  mov     ebx, ecx
0x1800248c1  lea     r12d, [r13-1]
0x1800248c5  or      ebx, r12d
0x1800248c8  test    dword ptr [rdi+58h], 200h
0x1800248cf  cmovz   ebx, ecx
0x1800248d2  cmp     ebx, dword ptr [rbp+270h+FileInformation]
0x1800248d5  jz      short loc_180024924
0x1800248d7  mov     rcx, [rsi]; lpFileName
0x1800248da  mov     edx, ebx; dwFileAttributes
0x1800248dc  call    cs:__imp_SetFileAttributesW
0x1800248e2  jmp     short loc_180024924
0x1800248e4  test    al, r9b
0x1800248e7  jz      loc_18002505B
0x1800248ed  mov     r13d, eax
0x1800248f0  mov     [rsp+370h+var_320], eax
0x1800248f4  mov     eax, [rcx+58h]
0x1800248f7  mov     r12d, 2
0x1800248fd  and     eax, 200h
0x180024902  neg     eax
0x180024904  sbb     ebx, ebx
0x180024906  or      r9d, r12d
0x180024909  and     ebx, 0FFFFFF82h
0x18002490c  mov     [rsp+370h+NumberOfBytesWritten], r9d
0x180024911  sub     ebx, 0FFFFFF80h
0x180024914  add     rcx, 2Ch ; ','; struct _GUID *
0x180024918  call    ?GenerateUniqueID@@YAXPEAU_GUID@@@Z; GenerateUniqueID(_GUID *)
0x18002491d  lea     r14, [rdi+0A0h]
0x180024924  xor     r9d, r9d; lpSecurityAttributes
0x180024927  mov     [rsp+370h+hTemplateFile], 0; hTemplateFile
0x180024930  bts     ebx, 1Bh
0x180024934  mov     edx, 40000000h; dwDesiredAccess
0x180024939  mov     [rsp+370h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18002493d  mov     rcx, r15; lpFileName
0x180024940  mov     [rsp+370h+dwCreationDisposition], r13d; dwCreationDisposition
0x180024945  lea     r8d, [r9+5]; dwShareMode
0x180024949  call    cs:__imp_CreateFileW
0x18002494f  or      r15, 0FFFFFFFFFFFFFFFFh
0x180024953  mov     [rsp+370h+hFile], rax
0x180024958  mov     r13, rax
0x18002495b  cmp     rax, r15
0x18002495e  jz      loc_180024893
0x180024964  mov     rcx, rax; hFile
0x180024967  call    cs:__imp_GetFileType
0x18002496d  lea     edx, [r15+2]
0x180024971  cmp     eax, edx
0x180024973  jz      short loc_180024988
0x180024975  mov     rcx, r13; hObject
0x180024978  call    cs:__imp_CloseHandle
0x18002497e  mov     eax, 80070005h
0x180024983  jmp     loc_180025060
0x180024988  cmp     [rsp+370h+var_328], 0
0x18002498d  jnz     short loc_180024999
0x18002498f  mov     rax, [rsp+370h+lpFileName]
0x180024994  cmp     rax, [rsi]
0x180024997  jnz     short loc_18002499C
0x180024999  mov     [r14], edx
0x18002499c  xor     esi, esi
0x18002499e  cmp     [rdi+88h], rsi
0x1800249a5  jnz     short loc_180024A04
0x1800249a7  lea     r8, [rsp+370h+nSize]; nSize
0x1800249ac  mov     [rsp+370h+nSize], 101h
0x1800249b4  lea     rdx, [rbp+270h+NameBuffer]; lpNameBuffer
0x1800249b8  mov     ecx, r12d; NameFormat
0x1800249bb  call    cs:__imp_GetUserNameExW
0x1800249c1  test    al, al
0x1800249c3  jz      short loc_1800249FF
0x1800249c5  mov     ecx, [rsp+370h+nSize]
0x1800249c9  mov     rax, r12
0x1800249cc  inc     ecx
0x1800249ce  mul     rcx
0x1800249d1  cmovb   rax, r15
0x1800249d5  mov     rcx, rax; Size
0x1800249d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800249dd  mov     [rdi+88h], rax
0x1800249e4  mov     rcx, rax; unsigned __int16 *
0x1800249e7  test    rax, rax
0x1800249ea  jz      loc_180024BF1
0x1800249f0  mov     edx, [rsp+370h+nSize]
0x1800249f4  lea     r8, [rbp+270h+NameBuffer]; unsigned __int16 *
0x1800249f8  inc     edx; unsigned __int64
0x1800249fa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800249ff  mov     edx, 1
0x180024a04  mov     ecx, [rdi+58h]
0x180024a07  mov     eax, esi
0x180024a09  test    cl, 4
0x180024a0c  jz      short loc_180024A20
0x180024a0e  cmp     dword ptr [rdi+54h], 41301h
0x180024a15  jz      short loc_180024A2A
0x180024a17  mov     dword ptr [rdi+54h], 41302h
0x180024a1e  jmp     short loc_180024A2A
0x180024a20  cmp     dword ptr [rdi+54h], 41302h
0x180024a27  cmovz   eax, edx
0x180024a2a  test    ecx, ecx
0x180024a2c  cmovs   eax, edx
0x180024a2f  bt      ecx, 1Ch
0x180024a33  jnb     short loc_180024A40
0x180024a35  and     ecx, 0CFFFFFFFh
0x180024a3b  mov     [rdi+58h], ecx
0x180024a3e  jmp     short loc_180024A44
0x180024a40  test    eax, eax
0x180024a42  jz      short loc_180024A4E
0x180024a44  xor     edx, edx; int
0x180024a46  mov     rcx, rdi; this
0x180024a49  call    ?UpdateJobState@CJob@@QEAAJH@Z; CJob::UpdateJobState(int)
0x180024a4e  mov     ebx, [rdi+58h]
0x180024a51  bt      ebx, 10h
0x180024a55  jnb     short loc_180024A68
0x180024a57  lea     rcx, [rdi+2Ch]; struct _GUID *
0x180024a5b  call    ?GenerateUniqueID@@YAXPEAU_GUID@@@Z; GenerateUniqueID(_GUID *)
0x180024a60  btr     dword ptr [rdi+58h], 10h
0x180024a65  mov     ebx, [rdi+58h]
0x180024a68  test    byte ptr [rsp+370h+NumberOfBytesWritten], 4
0x180024a6d  mov     esi, 2Ch ; ','
0x180024a72  mov     r14, rdi
0x180024a75  jnz     short loc_180024A7E
0x180024a77  btr     ebx, 15h
0x180024a7b  mov     [rdi+58h], ebx
0x180024a7e  xor     edx, edx; Val
0x180024a80  lea     rcx, [rbp+270h+var_2E0]; void *
0x180024a84  lea     r8d, [rdx+48h]; Size
0x180024a88  call    memset_0
0x180024a8d  movups  xmm0, xmmword ptr [rsi+r14]
0x180024a92  movzx   eax, word ptr [rdi+28h]
0x180024a96  and     ebx, 3FFDFFFFh
0x180024a9c  mov     word ptr [rbp+270h+var_2E0], ax
0x180024aa0  mov     r9d, 1
0x180024aa6  movzx   eax, word ptr [rdi+2Ah]
0x180024aaa  mov     word ptr [rbp+270h+var_2E0+2], ax
0x180024aae  mov     eax, 46h ; 'F'
0x180024ab3  mov     [rbp+270h+var_2CC], ax
0x180024ab7  movzx   eax, word ptr [rdi+3Ch]
0x180024abb  mov     [rbp+270h+var_2CA], ax
0x180024abf  movzx   eax, word ptr [rdi+3Eh]
0x180024ac3  mov     [rbp+270h+var_2C8], ax
0x180024ac7  movzx   eax, word ptr [rdi+40h]
0x180024acb  mov     [rbp+270h+var_2C6], ax
0x180024acf  movzx   eax, word ptr [rdi+44h]
0x180024ad3  mov     [rbp+270h+var_2C2], ax
0x180024ad7  movzx   eax, word ptr [rdi+46h]
0x180024adb  mov     [rbp+270h+var_2C4], ax
0x180024adf  mov     eax, [rdi+48h]
0x180024ae2  mov     dword ptr [rbp+270h+var_2C0], eax
0x180024ae5  mov     eax, [rdi+4Ch]
0x180024ae8  mov     dword ptr [rbp+270h+var_2C0+4], eax
0x180024aeb  mov     eax, [rdi+50h]
0x180024aee  mov     dword ptr [rbp+270h+var_2C0+8], eax
0x180024af1  mov     eax, [rdi+54h]
0x180024af4  mov     dword ptr [rbp+270h+var_2C0+0Ch], eax
0x180024af7  movzx   eax, word ptr [rdi+42h]
0x180024afb  mov     [rbp+270h+var_29C], ax
0x180024aff  mov     eax, [rsp+370h+NumberOfBytesWritten]
0x180024b03  and     al, 3
0x180024b05  mov     dword ptr [rbp+270h+var_2B0], ebx
0x180024b08  neg     al
0x180024b0a  mov     eax, [rsp+370h+NumberOfBytesWritten]
0x180024b0e  sbb     r14d, r14d
0x180024b11  and     r14d, r12d
0x180024b14  movdqu  [rbp+270h+var_2E0+4], xmm0
0x180024b19  add     r14d, 44h ; 'D'
0x180024b1d  movups  xmm0, xmmword ptr [rdi+60h]
0x180024b21  and     eax, r9d
0x180024b24  mov     [rsp+370h+var_324], eax
0x180024b28  movdqu  [rbp+270h+var_2B0+4], xmm0
0x180024b2d  jz      loc_180024FAD
0x180024b33  add     r14d, 0Ah
0x180024b37  lea     r13, ?s_StringField@CJob@@0QBQEQ1@PEAGB; ushort * CJob::* const near * const CJob::s_StringField
0x180024b3e  xor     esi, esi
0x180024b40  mov     ecx, esi
0x180024b42  movsxd  r8, ecx
0x180024b45  movsxd  rax, dword ptr [r13+r8*4+0]
0x180024b4a  mov     rdx, [rax+rdi]
0x180024b4e  test    rdx, rdx
0x180024b51  jz      short loc_180024B69
0x180024b53  cmp     [rdx], si
0x180024b56  jz      short loc_180024B69
0x180024b58  mov     rax, r15
0x180024b5b  inc     rax
0x180024b5e  cmp     [rdx+rax*2], si
0x180024b62  jnz     short loc_180024B5B
0x180024b64  inc     rax
0x180024b67  jmp     short loc_180024B6C
0x180024b69  mov     rax, rsi
0x180024b6c  movzx   eax, ax
0x180024b6f  add     ecx, r9d
0x180024b72  mov     [rbp+r8*2+270h+var_268], ax
0x180024b78  lea     r14d, [r14+rax*2]
0x180024b7c  cmp     ecx, 5
0x180024b7f  jb      short loc_180024B42
0x180024b81  movzx   ecx, word ptr [rdi+0B2h]
0x180024b88  mov     eax, 8
0x180024b8d  cmp     cx, ax
0x180024b90  jnb     short loc_180024B9C
0x180024b92  mov     [rdi+0B2h], ax
0x180024b99  movzx   ecx, ax
0x180024b9c  movzx   eax, word ptr [rdi+20h]
0x180024ba0  movzx   edx, word ptr [rdi+0B0h]
0x180024ba7  mov     [rsp+370h+nSize], eax
0x180024bab  add     edx, r14d
0x180024bae  movzx   ecx, cx
0x180024bb1  add     ecx, 4
0x180024bb4  lea     eax, [rax+rax*2]
0x180024bb7  add     edx, ecx
0x180024bb9  shl     eax, 4
0x180024bbc  mov     [rbp+270h+var_2F0], rax
0x180024bc0  mov     [rdi+3Ch], dx
0x180024bc4  mov     [rbp+270h+var_2CA], dx
0x180024bc8  lea     ecx, [rax+2]
0x180024bcb  add     ecx, edx
0x180024bcd  cmp     [rdi+0D0h], rsi
0x180024bd4  lea     eax, [rcx+44h]
0x180024bd7  cmovz   eax, ecx
0x180024bda  mov     ecx, eax; Size
0x180024bdc  mov     r14d, eax
0x180024bdf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024be4  mov     r13, [rsp+370h+hFile]
0x180024be9  mov     r15, rax
0x180024bec  test    rax, rax
0x180024bef  jnz     short loc_180024C1D
0x180024bf1  mov     ebx, 8007000Eh
0x180024bf6  test    r13, r13
0x180024bf9  jz      short loc_180024C04
0x180024bfb  mov     rcx, r13; hObject
0x180024bfe  call    cs:__imp_CloseHandle
0x180024c04  cmp     [rsp+370h+var_320], 1
0x180024c09  jnz     short loc_180024C16
0x180024c0b  mov     rcx, [rsp+370h+lpFileName]; lpFileName
0x180024c10  call    cs:__imp_DeleteFileW
0x180024c16  mov     eax, ebx
0x180024c18  jmp     loc_180025060
0x180024c1d  cmp     r14d, 46h ; 'F'
0x180024c21  jnb     short loc_180024C2D
0x180024c23  mov     ebx, 8000FFFFh
0x180024c28  jmp     loc_180024EF8
0x180024c2d  movaps  xmm0, [rbp+270h+var_2E0]
0x180024c31  lea     rbx, [rax+46h]
0x180024c35  movups  xmmword ptr [rax], xmm0
0x180024c38  lea     esi, [r14-46h]
0x180024c3c  xor     r13d, r13d
0x180024c3f  movaps  xmm1, xmmword ptr [rbp-60h]
0x180024c43  movups  xmmword ptr [rax+10h], xmm1
0x180024c47  movaps  xmm0, [rbp+270h+var_2C0]
0x180024c4b  movups  xmmword ptr [rax+20h], xmm0
  ... truncated ...
```
