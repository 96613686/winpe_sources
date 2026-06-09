# CDVRFileCollection::CDVRFileCollection(CDVRFileCollection::CClientInfo const *,ushort const *,int,ulong *,long *)

- ea: `0x180071424`
- end: `0x180071ca9`
- name: `??0CDVRFileCollection@@QEAA@PEBUCClientInfo@0@PEBGHPEAKPEAJ@Z`
- size: `2181`
- prototype: `CDVRFileCollection *__usercall@<rax>(CDVRFileCollection *__hidden this@<rcx>, const struct CDVRFileCollection::CClientInfo *@<rdx>, const unsigned __int16 *@<r8>, int@<r9d>, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180063528`

## callees

- `0x1800017ec`
- `0x180001c00`
- `0x18000256c`
- `0x18000262c`
- `0x180071424`
- `0x180073368`
- `0x180073bd8`
- `0x180073ebc`
- `0x180074ec4`
- `0x180076948`
- `0x18007721c`
- `0x1800b33ed`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180071669`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180071669`
- `KERNEL32!CloseHandle` at `0x180071b5d`
- `KERNEL32!CloseHandle` at `0x180071c2d`
- `KERNEL32!CloseHandle` at `0x1800b4c74`
- `KERNEL32!CloseHandle` at `0x180071b5d`
- `KERNEL32!CloseHandle` at `0x180071c2d`
- `KERNEL32!CloseHandle` at `0x1800b4c74`
- `KERNEL32!InitializeCriticalSection` at `0x180071507`
- `KERNEL32!InitializeCriticalSection` at `0x180071507`
- `KERNEL32!GetLastError` at `0x18007156a`
- `KERNEL32!GetLastError` at `0x1800715ec`
- `KERNEL32!GetLastError` at `0x1800716b4`
- `KERNEL32!GetLastError` at `0x180071884`
- `KERNEL32!GetLastError` at `0x1800719d8`
- `KERNEL32!GetLastError` at `0x180071adf`
- `KERNEL32!GetLastError` at `0x180071be5`
- `KERNEL32!GetLastError` at `0x18007156a`
- `KERNEL32!GetLastError` at `0x1800715ec`
- `KERNEL32!GetLastError` at `0x1800716b4`
- `KERNEL32!GetLastError` at `0x180071884`
- `KERNEL32!GetLastError` at `0x1800719d8`
- `KERNEL32!GetLastError` at `0x180071adf`
- `KERNEL32!GetLastError` at `0x180071be5`
- `KERNEL32!GetFileInformationByHandle` at `0x180071714`
- `KERNEL32!GetFileInformationByHandle` at `0x180071ad5`
- `KERNEL32!GetFileInformationByHandle` at `0x180071714`
- `KERNEL32!GetFileInformationByHandle` at `0x180071ad5`
- `KERNEL32!OpenFileMappingW` at `0x18007184c`
- `KERNEL32!OpenFileMappingW` at `0x18007184c`
- `KERNEL32!Sleep` at `0x180071763`
- `KERNEL32!Sleep` at `0x180071933`
- `KERNEL32!Sleep` at `0x180071763`
- `KERNEL32!Sleep` at `0x180071933`
- `KERNEL32!OpenMutexW` at `0x1800719c9`
- `KERNEL32!OpenMutexW` at `0x1800719c9`
- `KERNEL32!MapViewOfFile` at `0x1800718df`
- `KERNEL32!MapViewOfFile` at `0x1800718df`
- `KERNEL32!CreateFileMappingW` at `0x18007187a`
- `KERNEL32!CreateFileMappingW` at `0x18007187a`
- `KERNEL32!GetFullPathNameW` at `0x18007155e`
- `KERNEL32!GetFullPathNameW` at `0x1800715df`
- `KERNEL32!GetFullPathNameW` at `0x18007155e`
- `KERNEL32!GetFullPathNameW` at `0x1800715df`
- `KERNEL32!CreateFileW` at `0x1800716a1`
- `KERNEL32!CreateFileW` at `0x1800716a1`

## pseudocode

```c
CDVRFileCollection *__fastcall CDVRFileCollection::CDVRFileCollection(
        CDVRFileCollection *this,
        const struct CDVRFileCollection::CClientInfo *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int *a5,
        int *a6)
{
  int *v9; // rsi
  int v10; // r12d
  HANDLE FileW; // r14
  __int64 v12; // rdx
  signed int SectionName; // ebx
  signed int v14; // esi
  DWORD FullPathNameW; // eax
  DWORD v16; // ebx
  signed int LastError; // eax
  DWORD v18; // r12d
  WCHAR *v19; // rax
  DWORD v20; // eax
  signed int v21; // eax
  __int64 v22; // rbx
  void *v23; // rax
  signed int v24; // eax
  int v25; // ebx
  enum _ACCESS_MODE v26; // r8d
  ULONG v27; // ecx
  signed int v28; // eax
  bool v29; // cc
  struct _SECURITY_ATTRIBUTES *p_FileMappingAttributes; // rbx
  HANDLE v31; // rax
  BOOL v32; // ebx
  void *v33; // rcx
  _DWORD *v34; // rax
  _DWORD *v35; // rcx
  int v36; // ebx
  __int64 v37; // rax
  int v38; // esi
  HANDLE v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rcx
  _QWORD *v43; // rcx
  signed int v44; // eax
  unsigned __int64 v45; // rbx
  CDVRFileCollection *v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rax
  enum _ACCESS_MODE dwCreationDisposition; // [rsp+20h] [rbp-1E8h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-1E8h]
  unsigned int dwFlagsAndAttributes; // [rsp+28h] [rbp-1E0h]
  unsigned int v53; // [rsp+54h] [rbp-1B4h] BYREF
  HANDLE v54; // [rsp+58h] [rbp-1B0h]
  CDVRFileCollection *v55; // [rsp+60h] [rbp-1A8h]
  void *v56[2]; // [rsp+68h] [rbp-1A0h] BYREF
  unsigned int *v57; // [rsp+78h] [rbp-190h]
  unsigned int *v58; // [rsp+80h] [rbp-188h]
  LPWSTR FilePart; // [rsp+88h] [rbp-180h] BYREF
  struct _ACL *v60; // [rsp+90h] [rbp-178h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+98h] [rbp-170h] BYREF
  WCHAR Buffer; // [rsp+B0h] [rbp-158h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+B8h] [rbp-150h] BYREF
  wchar_t v64[40]; // [rsp+F0h] [rbp-118h] BYREF
  WCHAR Name[64]; // [rsp+140h] [rbp-C8h] BYREF

  v55 = this;
  v57 = a5;
  v58 = a5;
  v9 = a6;
  v56[1] = a6;
  *(_QWORD *)this = &CDVRFileCollection::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = -1;
  *((_DWORD *)this + 34) = 1;
  *(_QWORD *)((char *)this + 140) = 1;
  *(_QWORD *)((char *)this + 148) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = a4;
  *((_DWORD *)this + 43) = 4;
  v53 = 0;
  v10 = 0;
  FileW = 0;
  v54 = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  memset_0((char *)this + 176, 0, 0x100u);
  _InterlockedIncrement((volatile signed __int32 *)this + 36);
  if ( !a3 )
  {
    SectionName = -2147024809;
    goto LABEL_105;
  }
  v14 = 0;
  Buffer = 0;
  FilePart = 0;
  FullPathNameW = GetFullPathNameW(a3, 0, &Buffer, 0);
  v16 = FullPathNameW;
  if ( !FullPathNameW )
  {
    LastError = GetLastError();
    LODWORD(a3) = 0;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    SectionName = -2147467259;
    if ( LastError < 0 )
      SectionName = LastError;
    goto LABEL_104;
  }
  v18 = FullPathNameW + 1;
  v19 = (WCHAR *)operator new[](saturated_mul(FullPathNameW + 1, 2u));
  *((_QWORD *)this + 14) = v19;
  if ( !v19 )
    goto LABEL_10;
  v20 = GetFullPathNameW(a3, v18, v19, &FilePart);
  LODWORD(a3) = 0;
  if ( !v20 )
  {
    v21 = GetLastError();
    if ( v21 > 0 )
      v21 = (unsigned __int16)v21 | 0x80070000;
    SectionName = -2147467259;
    if ( v21 < 0 )
      SectionName = v21;
    goto LABEL_103;
  }
  if ( v20 > v16 )
  {
    SectionName = -2147467259;
    goto LABEL_103;
  }
  v22 = ((__int64)FilePart - *((_QWORD *)this + 14)) >> 1;
  v23 = operator new[](saturated_mul((unsigned int)(v22 + 1), 2u));
  *((_QWORD *)this + 15) = v23;
  if ( !v23 )
  {
LABEL_10:
    SectionName = -2147024882;
    LODWORD(a3) = 0;
LABEL_103:
    v10 = 0;
    goto LABEL_104;
  }
  _o_wcsncpy_s(v23, (unsigned int)(v22 + 1), *((_QWORD *)this + 14), (unsigned int)v22);
  LODWORD(a3) = 0;
  *(_WORD *)(*((_QWORD *)this + 15) + 2LL * (unsigned int)v22) = 0;
  FileW = CreateFileW(*((LPCWSTR *)this + 14), 0xC0000000, 7u, 0, 3u, 0x80u, 0);
  v54 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v24 = GetLastError();
    SectionName = v24;
    if ( v24 > 0 )
      SectionName = (unsigned __int16)v24 | 0x80070000;
    FileW = 0;
    v54 = 0;
    goto LABEL_103;
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  v25 = 0;
  v10 = 1;
  while ( 1 )
  {
    if ( !GetFileInformationByHandle(FileW, &FileInformation) )
      goto LABEL_99;
    if ( FileInformation.nFileSizeHigh || FileInformation.nFileSizeLow >= 0x2380308 )
      goto LABEL_51;
    if ( FileInformation.nFileSizeLow >= 0x778 )
      break;
    if ( ++v25 == 5 )
      goto LABEL_51;
    Sleep(0x64u);
  }
  SectionName = CDVRFileCollection::CreateSectionName(
                  this,
                  FileInformation.dwVolumeSerialNumber,
                  FileInformation.nFileIndexHigh,
                  FileInformation.nFileIndexLow,
                  *((_DWORD *)this + 35),
                  dwFlagsAndAttributes,
                  Name);
  if ( SectionName < 0 )
    goto LABEL_103;
  v60 = 0;
  v56[0] = 0;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  v27 = *((_DWORD *)a2 + 4);
  if ( v27 )
  {
    v28 = CreateACL(v27, *((void ***)a2 + 3), v26, 0xF0007u, dwCreationDisposition, 7u, &v60, v56);
    SectionName = v28;
    v29 = v28 <= 0;
    if ( v28 )
    {
LABEL_100:
      if ( v29 )
        goto LABEL_103;
      SectionName = (unsigned __int16)v28;
LABEL_102:
      SectionName |= 0x80070000;
      goto LABEL_103;
    }
    FileMappingAttributes.nLength = 24;
    FileMappingAttributes.lpSecurityDescriptor = v56[0];
    FileMappingAttributes.bInheritHandle = 0;
    p_FileMappingAttributes = &FileMappingAttributes;
  }
  else
  {
    p_FileMappingAttributes = 0;
  }
  v31 = OpenFileMappingW(6u, 0, Name);
  *((_QWORD *)this + 6) = v31;
  if ( v31 )
  {
    v32 = 1;
  }
  else
  {
    *((_QWORD *)this + 6) = CreateFileMappingW(FileW, p_FileMappingAttributes, 4u, 0, 0, Name);
    v14 = GetLastError();
    v32 = v14 == 183;
  }
  if ( *((_DWORD *)a2 + 4) )
    FreeSecurityDescriptors(&v60, v56);
  v33 = (void *)*((_QWORD *)this + 6);
  if ( !v33 )
  {
    if ( v14 <= 0 )
    {
      SectionName = v14;
      goto LABEL_103;
    }
    SectionName = (unsigned __int16)v14;
    goto LABEL_102;
  }
  v34 = MapViewOfFile(v33, 6u, 0, 0, 0);
  v35 = v34;
  if ( !v34 )
  {
LABEL_99:
    v28 = GetLastError();
    v29 = v28 <= 0;
    SectionName = v28;
    goto LABEL_100;
  }
  *((_QWORD *)this + 4) = v34;
  *((_DWORD *)this + 43) |= 1u;
  if ( v32 )
  {
    v36 = 0;
    while ( 1 )
    {
      v35 = (_DWORD *)*((_QWORD *)this + 4);
      if ( v35[20] )
        break;
      if ( ++v36 == 5 )
        goto LABEL_50;
      Sleep(0x64u);
    }
  }
  else if ( !v34[20] )
  {
LABEL_50:
    *((_DWORD *)this + 35) = 0;
LABEL_51:
    SectionName = -2147024883;
    goto LABEL_103;
  }
  v37 = *(_QWORD *)v35 - *(_QWORD *)&CDVRFileCollection::m_guidV11.Data1;
  if ( *(_QWORD *)v35 == *(_QWORD *)&CDVRFileCollection::m_guidV11.Data1 )
    v37 = *((_QWORD *)v35 + 1) - *(_QWORD *)CDVRFileCollection::m_guidV11.Data4;
  if ( v37 )
  {
    SectionName = memcmp_0(v35, &CDVRFileCollection::m_guidV1, 0x10u) != 0 ? -2147024883 : -2147220924;
    goto LABEL_103;
  }
  *((_QWORD *)this + 5) = v35 + 478;
  v38 = v35[15];
  if ( v38 )
  {
    dwCreationDispositiona[0] = v35[15];
    swprintf_s(v64, 0x28u, L"%ls%d", L"Global\\_MS_TSDVR_MUTEX_", *(_QWORD *)dwCreationDispositiona);
    v39 = OpenMutexW(0x100000u, 0, v64);
    *((_QWORD *)this + 12) = v39;
    if ( !v39 )
    {
      SectionName = GetLastError();
      if ( SectionName != 2 || (v40 = *((_QWORD *)this + 4), *(_DWORD *)(v40 + 16)) || *(_DWORD *)(v40 + 20) )
      {
        if ( SectionName <= 0 )
          goto LABEL_103;
        SectionName = (unsigned __int16)SectionName;
        goto LABEL_102;
      }
      *((_DWORD *)this + 43) |= 8u;
    }
  }
  SectionName = CDVRFileCollection::Lock(this, a2, &v53, 1, 0);
  if ( SectionName < 0 )
    goto LABEL_104;
  v41 = *((_QWORD *)this + 4);
  v42 = *(_QWORD *)v41 - *(_QWORD *)&CDVRFileCollection::m_guidV11.Data1;
  if ( *(_QWORD *)v41 == *(_QWORD *)&CDVRFileCollection::m_guidV11.Data1 )
    v42 = *(_QWORD *)(v41 + 8) - *(_QWORD *)CDVRFileCollection::m_guidV11.Data4;
  if ( v42 )
  {
    v43 = (_QWORD *)*((_QWORD *)this + 4);
LABEL_72:
    SectionName = memcmp_0(v43, &CDVRFileCollection::m_guidV1, 0x10u) != 0 ? -2147024883 : -2147220924;
    goto LABEL_104;
  }
  if ( v38 )
  {
    if ( (*(_DWORD *)(v41 + 16) || *(_DWORD *)(v41 + 20)) && !*(_DWORD *)(v41 + 56) )
    {
      SectionName = -2147467259;
      goto LABEL_104;
    }
  }
  else if ( *(_DWORD *)(v41 + 68)
         || !*(_DWORD *)(v41 + 72)
         || *(_DWORD *)(v41 + 16)
         || *(_DWORD *)(v41 + 20)
         || *(_DWORD *)(v41 + 60) )
  {
LABEL_79:
    SectionName = -2147024883;
    goto LABEL_104;
  }
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
  {
    v44 = GetLastError();
    SectionName = v44;
    if ( v44 > 0 )
      SectionName = (unsigned __int16)v44 | 0x80070000;
    goto LABEL_104;
  }
  if ( FileInformation.nFileSizeHigh )
    goto LABEL_79;
  if ( FileInformation.nFileSizeLow <= 0x778 )
    goto LABEL_79;
  v12 = (((unsigned __int64)FileInformation.nFileSizeLow - 1912) * (unsigned __int128)0xCD85689039B0AD13uLL) >> 64;
  v45 = (v12 + (((unsigned __int64)FileInformation.nFileSizeLow - 1912 - v12) >> 1)) >> 9;
  if ( FileInformation.nFileSizeLow - 1912LL != 568 * v45 || (unsigned int)v45 > 0xFFFE )
    goto LABEL_79;
  *((_DWORD *)this + 2) = v45;
  CloseHandle(FileW);
  FileW = 0;
  v54 = 0;
  SectionName = CDVRFileCollection::ValidateSharedMemory(
                  v46,
                  *((struct CDVRFileCollection::CSharedData **)this + 4),
                  *((struct CDVRFileCollection::CSharedData::CFileInfo **)this + 5),
                  v45);
  if ( SectionName < 0 )
    goto LABEL_104;
  if ( !v38 && *(_DWORD *)(*((_QWORD *)this + 4) + 60LL) )
    goto LABEL_79;
  v43 = (_QWORD *)*((_QWORD *)this + 4);
  if ( *((_DWORD *)v43 + 16) )
    goto LABEL_79;
  v47 = *v43 - *(_QWORD *)&CDVRFileCollection::m_guidV11.Data1;
  if ( *v43 == *(_QWORD *)&CDVRFileCollection::m_guidV11.Data1 )
    v47 = v43[1] - *(_QWORD *)CDVRFileCollection::m_guidV11.Data4;
  if ( v47 )
    goto LABEL_72;
  *((_DWORD *)this + 43) |= 0x100u;
  *((_DWORD *)this + 43) |= 0x80u;
  SectionName = 0;
LABEL_104:
  v9 = a6;
LABEL_105:
  if ( v10 )
    CDVRFileCollection::Unlock(this, v12, v53, 1, (_DWORD)a3);
  if ( FileW )
    CloseHandle(FileW);
  if ( SectionName < 0 )
  {
    v48 = *((_QWORD *)this + 4);
    if ( v48 && (*((_BYTE *)this + 172) & 1) == 0 )
      *(_DWORD *)(v48 + 72) = 1;
  }
  else if ( v57 )
  {
    *v57 = *(_DWORD *)(*((_QWORD *)this + 4) + 76LL);
  }
  if ( v9 )
    *v9 = SectionName;
  return this;
}

```

## disassembly

```asm
0x180071424  push    rbx
0x180071426  push    rsi
0x180071427  push    rdi
0x180071428  push    r12
0x18007142a  push    r13
0x18007142c  push    r14
0x18007142e  push    r15
0x180071430  sub     rsp, 1D0h
0x180071437  mov     rax, cs:__security_cookie
0x18007143e  xor     rax, rsp
0x180071441  mov     [rsp+208h+var_48], rax
0x180071449  mov     r15, r8
0x18007144c  mov     r13, rdx
0x18007144f  mov     rdi, rcx
0x180071452  mov     [rsp+208h+var_1A8], rcx
0x180071457  mov     rax, [rsp+208h+arg_20]
0x18007145f  mov     [rsp+208h+var_190], rax
0x180071464  mov     [rsp+208h+var_188], rax
0x18007146c  mov     rsi, [rsp+208h+arg_28]
0x180071474  mov     [rsp+208h+var_1C0], rsi
0x180071479  mov     [rsp+208h+var_198], rsi
0x18007147e  lea     rax, ??_7CDVRFileCollection@@6B@; const CDVRFileCollection::`vftable'
0x180071485  mov     [rcx], rax
0x180071488  xor     ebx, ebx
0x18007148a  mov     [rcx+8], rbx
0x18007148e  mov     [rcx+10h], rbx
0x180071492  mov     [rcx+18h], rbx
0x180071496  mov     [rcx+20h], rbx
0x18007149a  mov     [rcx+28h], rbx
0x18007149e  mov     [rcx+30h], rbx
0x1800714a2  mov     [rcx+60h], rbx
0x1800714a6  mov     [rcx+68h], rbx
0x1800714aa  mov     [rcx+70h], rbx
0x1800714ae  mov     [rcx+78h], rbx
0x1800714b2  mov     qword ptr [rcx+80h], 0FFFFFFFFFFFFFFFFh
0x1800714bd  lea     eax, [rbx+1]
0x1800714c0  mov     [rcx+88h], eax
0x1800714c6  mov     [rcx+8Ch], rax
0x1800714cd  mov     [rcx+94h], rbx
0x1800714d4  mov     [rcx+0A0h], rbx
0x1800714db  mov     [rcx+0A8h], r9d
0x1800714e2  mov     dword ptr [rcx+0ACh], 4
0x1800714ec  mov     [rsp+208h+var_1C8], ebx
0x1800714f0  mov     [rsp+208h+var_1B4], ebx
0x1800714f4  mov     r12d, ebx
0x1800714f7  mov     [rsp+208h+var_1C4], ebx
0x1800714fb  mov     r14d, ebx
0x1800714fe  mov     [rsp+208h+var_1B0], rbx
0x180071503  add     rcx, 38h ; '8'; lpCriticalSection
0x180071507  call    cs:__imp_InitializeCriticalSection
0x18007150d  lea     rcx, [rdi+0B0h]; void *
0x180071514  xor     edx, edx; Val
0x180071516  mov     r8d, 100h; Size
0x18007151c  call    memset_0
0x180071521  nop
0x180071522  lock inc dword ptr [rdi+90h]
0x180071529  test    r15, r15
0x18007152c  jnz     short loc_18007153C
0x18007152e  mov     ebx, 80070057h
0x180071533  mov     [rsp+208h+var_1C8], ebx
0x180071537  jmp     loc_180071C08
0x18007153c  mov     esi, ebx
0x18007153e  mov     [rsp+208h+Buffer], bx
0x180071546  mov     [rsp+208h+FilePart], rbx
0x18007154e  xor     r9d, r9d; lpFilePart
0x180071551  lea     r8, [rsp+208h+Buffer]; lpBuffer
0x180071559  xor     edx, edx; nBufferLength
0x18007155b  mov     rcx, r15; lpFileName
0x18007155e  call    cs:__imp_GetFullPathNameW
0x180071564  mov     ebx, eax
0x180071566  test    eax, eax
0x180071568  jnz     short loc_180071596
0x18007156a  call    cs:__imp_GetLastError
0x180071570  xor     r15d, r15d
0x180071573  test    eax, eax
0x180071575  jle     short loc_18007157F
0x180071577  movzx   eax, ax
0x18007157a  or      eax, 80070000h
0x18007157f  mov     [rsp+208h+var_1C8], eax
0x180071583  mov     ebx, 80004005h
0x180071588  test    eax, eax
0x18007158a  cmovs   ebx, eax
0x18007158d  mov     [rsp+208h+var_1C8], ebx
0x180071591  jmp     loc_180071C03
0x180071596  lea     r12d, [rax+1]
0x18007159a  mov     ecx, r12d
0x18007159d  mov     eax, 2
0x1800715a2  mul     rcx
0x1800715a5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800715ac  cmovb   rax, rcx
0x1800715b0  mov     rcx, rax; unsigned __int64
0x1800715b3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800715b8  mov     [rdi+70h], rax
0x1800715bc  test    rax, rax
0x1800715bf  jnz     short loc_1800715CE
0x1800715c1  mov     ebx, 8007000Eh
0x1800715c6  xor     r15d, r15d
0x1800715c9  jmp     loc_180071BFA
0x1800715ce  lea     r9, [rsp+208h+FilePart]; lpFilePart
0x1800715d6  mov     r8, rax; lpBuffer
0x1800715d9  mov     edx, r12d; nBufferLength
0x1800715dc  mov     rcx, r15; lpFileName
0x1800715df  call    cs:__imp_GetFullPathNameW
0x1800715e5  xor     r15d, r15d
0x1800715e8  test    eax, eax
0x1800715ea  jnz     short loc_180071611
0x1800715ec  call    cs:__imp_GetLastError
0x1800715f2  test    eax, eax
0x1800715f4  jle     short loc_1800715FE
0x1800715f6  movzx   eax, ax
0x1800715f9  or      eax, 80070000h
0x1800715fe  mov     [rsp+208h+var_1C8], eax
0x180071602  mov     ebx, 80004005h
0x180071607  test    eax, eax
0x180071609  cmovs   ebx, eax
0x18007160c  jmp     loc_180071BFA
0x180071611  cmp     eax, ebx
0x180071613  jbe     short loc_18007161F
0x180071615  mov     ebx, 80004005h
0x18007161a  jmp     loc_180071BFA
0x18007161f  mov     rbx, [rsp+208h+FilePart]
0x180071627  sub     rbx, [rdi+70h]
0x18007162b  sar     rbx, 1
0x18007162e  lea     r15d, [rbx+1]
0x180071632  mov     eax, 2
0x180071637  mul     r15
0x18007163a  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180071641  cmovb   rax, r12
0x180071645  mov     rcx, rax; unsigned __int64
0x180071648  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007164d  mov     [rdi+78h], rax
0x180071651  test    rax, rax
0x180071654  jz      loc_1800715C1
0x18007165a  mov     ebx, ebx
0x18007165c  mov     r9d, ebx
0x18007165f  mov     r8, [rdi+70h]
0x180071663  mov     edx, r15d
0x180071666  mov     rcx, rax
0x180071669  call    cs:__imp__o_wcsncpy_s
0x18007166f  mov     rcx, [rdi+78h]
0x180071673  xor     r15d, r15d
0x180071676  mov     [rcx+rbx*2], r15w
0x18007167b  mov     [rsp+208h+hTemplateFile], r15; hTemplateFile
0x180071680  mov     [rsp+208h+dwFlagsAndAttributes], 80h; unsigned int
0x180071688  mov     [rsp+208h+dwCreationDisposition], 3; dwCreationDisposition
0x180071690  xor     r9d, r9d; lpSecurityAttributes
0x180071693  mov     edx, 0C0000000h; dwDesiredAccess
0x180071698  lea     r8d, [r12+8]; dwShareMode
0x18007169d  mov     rcx, [rdi+70h]; lpFileName
0x1800716a1  call    cs:__imp_CreateFileW
0x1800716a7  mov     r14, rax
0x1800716aa  mov     [rsp+208h+var_1B0], rax
0x1800716af  cmp     rax, r12
0x1800716b2  jnz     short loc_1800716DA
0x1800716b4  call    cs:__imp_GetLastError
0x1800716ba  mov     ebx, eax
0x1800716bc  test    eax, eax
0x1800716be  jle     short loc_1800716C9
0x1800716c0  movzx   ebx, ax
0x1800716c3  or      ebx, 80070000h
0x1800716c9  mov     [rsp+208h+var_1C8], ebx
0x1800716cd  mov     r14, r15
0x1800716d0  mov     [rsp+208h+var_1B0], r15
0x1800716d5  jmp     loc_180071BFE
0x1800716da  xorps   xmm0, xmm0
0x1800716dd  xor     eax, eax
0x1800716df  movups  xmmword ptr [rsp+208h+FileInformation.dwFileAttributes], xmm0
0x1800716e7  movups  xmmword ptr [rsp+208h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800716ef  movups  xmmword ptr [rsp+208h+FileInformation.nFileSizeHigh], xmm0
0x1800716f7  mov     [rsp+208h+FileInformation.nFileIndexLow], eax
0x1800716fe  mov     ebx, r15d
0x180071701  mov     [rsp+208h+var_1B8], ebx
0x180071705  lea     r12d, [rax+1]
0x180071709  lea     rdx, [rsp+208h+FileInformation]; lpFileInformation
0x180071711  mov     rcx, r14; hFile
0x180071714  call    cs:__imp_GetFileInformationByHandle
0x18007171a  test    eax, eax
0x18007171c  jz      loc_180071BE5
0x180071722  cmp     [rsp+208h+FileInformation.nFileSizeHigh], r15d
0x18007172a  ja      loc_180071924
0x180071730  cmp     [rsp+208h+FileInformation.nFileSizeLow], 2380308h
0x18007173b  jnb     loc_180071924
0x180071741  cmp     [rsp+208h+FileInformation.nFileSizeLow], 778h
0x18007174c  jnb     short loc_18007176B
0x18007174e  add     ebx, r12d
0x180071751  mov     [rsp+208h+var_1B8], ebx
0x180071755  cmp     ebx, 5
0x180071758  jz      loc_180071924
0x18007175e  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180071763  call    cs:__imp_Sleep
0x180071769  jmp     short loc_180071709
0x18007176b  lea     rax, [rsp+208h+Name]
0x180071773  mov     [rsp+208h+hTemplateFile], rax; Buffer
0x180071778  mov     eax, [rdi+8Ch]
0x18007177e  mov     [rsp+208h+dwCreationDisposition], eax; enum _ACCESS_MODE
0x180071782  mov     r9d, [rsp+208h+FileInformation.nFileIndexLow]; unsigned int
0x18007178a  mov     r8d, [rsp+208h+FileInformation.nFileIndexHigh]; unsigned int
0x180071792  mov     edx, [rsp+208h+FileInformation.dwVolumeSerialNumber]; unsigned int
0x180071799  mov     rcx, rdi; this
0x18007179c  call    ?CreateSectionName@CDVRFileCollection@@AEAAJKKKKKPEAG@Z; CDVRFileCollection::CreateSectionName(ulong,ulong,ulong,ulong,ulong,ushort *)
0x1800717a1  mov     ebx, eax
0x1800717a3  test    eax, eax
0x1800717a5  jns     short loc_1800717B0
0x1800717a7  mov     [rsp+208h+var_1C8], eax
0x1800717ab  jmp     loc_180071BFE
0x1800717b0  mov     [rsp+208h+var_178], r15
0x1800717b8  mov     [rsp+208h+var_1A0], r15
0x1800717bd  xorps   xmm0, xmm0
0x1800717c0  xor     eax, eax
0x1800717c2  movups  xmmword ptr [rsp+208h+FileMappingAttributes.nLength], xmm0
0x1800717ca  mov     qword ptr [rsp+208h+FileMappingAttributes.bInheritHandle], rax
0x1800717d2  mov     ecx, [r13+10h]; cCountOfExplicitEntries
0x1800717d6  test    ecx, ecx
0x1800717d8  jz      short loc_18007183C
0x1800717da  lea     rax, [rsp+208h+var_1A0]
0x1800717df  mov     [rsp+208h+var_1D0], rax; void **
0x1800717e4  lea     rax, [rsp+208h+var_178]
0x1800717ec  mov     [rsp+208h+hTemplateFile], rax; struct _ACL **
0x1800717f1  mov     [rsp+208h+dwFlagsAndAttributes], 7; unsigned int
0x1800717f9  mov     r9d, 0F0007h; unsigned int
0x1800717ff  mov     rdx, [r13+18h]; void **
0x180071803  call    ?CreateACL@@YAKKPEAPEAXW4_ACCESS_MODE@@K1KAEAPEAU_ACL@@AEAPEAX@Z; CreateACL(ulong,void * *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * &,void * &)
0x180071808  mov     ebx, eax
0x18007180a  test    eax, eax
0x18007180c  jnz     loc_180071BEF
0x180071812  mov     [rsp+208h+FileMappingAttributes.nLength], 18h
0x18007181d  mov     rax, [rsp+208h+var_1A0]
0x180071822  mov     [rsp+208h+FileMappingAttributes.lpSecurityDescriptor], rax
0x18007182a  mov     [rsp+208h+FileMappingAttributes.bInheritHandle], r15d
0x180071832  lea     rbx, [rsp+208h+FileMappingAttributes]
0x18007183a  jmp     short loc_18007183F
0x18007183c  mov     rbx, r15
0x18007183f  lea     r8, [rsp+208h+Name]; lpName
0x180071847  xor     edx, edx; bInheritHandle
0x180071849  lea     ecx, [rdx+6]; dwDesiredAccess
0x18007184c  call    cs:__imp_OpenFileMappingW
0x180071852  mov     [rdi+30h], rax
0x180071856  test    rax, rax
0x180071859  jnz     short loc_180071899
0x18007185b  lea     rax, [rsp+208h+Name]
0x180071863  mov     qword ptr [rsp+208h+dwFlagsAndAttributes], rax; lpName
0x180071868  mov     [rsp+208h+dwCreationDisposition], r15d; dwMaximumSizeLow
0x18007186d  xor     r9d, r9d; dwMaximumSizeHigh
0x180071870  lea     r8d, [r9+4]; flProtect
0x180071874  mov     rdx, rbx; lpFileMappingAttributes
0x180071877  mov     rcx, r14; hFile
0x18007187a  call    cs:__imp_CreateFileMappingW
0x180071880  mov     [rdi+30h], rax
0x180071884  call    cs:__imp_GetLastError
0x18007188a  mov     esi, eax
0x18007188c  mov     ebx, r15d
0x18007188f  cmp     eax, 0B7h
0x180071894  setz    bl
0x180071897  jmp     short loc_18007189C
0x180071899  mov     ebx, r12d
0x18007189c  cmp     [r13+10h], r15d
0x1800718a0  jbe     short loc_1800718B4
0x1800718a2  lea     rdx, [rsp+208h+var_1A0]; void **
0x1800718a7  lea     rcx, [rsp+208h+var_178]; struct _ACL **
0x1800718af  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x1800718b4  mov     rcx, [rdi+30h]; hFileMappingObject
0x1800718b8  test    rcx, rcx
0x1800718bb  jnz     short loc_1800718D0
0x1800718bd  test    esi, esi
0x1800718bf  jg      short loc_1800718C8
0x1800718c1  mov     ebx, esi
0x1800718c3  jmp     loc_180071BFA
0x1800718c8  movzx   ebx, si
0x1800718cb  jmp     loc_180071BF4
0x1800718d0  mov     qword ptr [rsp+208h+dwCreationDisposition], r15; dwNumberOfBytesToMap
0x1800718d5  xor     r9d, r9d; dwFileOffsetLow
0x1800718d8  xor     r8d, r8d; dwFileOffsetHigh
0x1800718db  lea     edx, [r9+6]; dwDesiredAccess
0x1800718df  call    cs:__imp_MapViewOfFile
0x1800718e5  mov     rcx, rax; Buf1
0x1800718e8  test    rax, rax
0x1800718eb  jz      loc_180071BE5
0x1800718f1  mov     [rdi+20h], rax
0x1800718f5  or      [rdi+0ACh], r12d
0x1800718fc  test    ebx, ebx
0x1800718fe  jz      short loc_18007193B
0x180071900  mov     ebx, r15d
0x180071903  mov     [rsp+208h+var_1B8], ebx
0x180071907  mov     rcx, [rdi+20h]
0x18007190b  cmp     [rcx+50h], r15d
0x18007190f  jnz     short loc_180071941
0x180071911  add     ebx, r12d
0x180071914  mov     [rsp+208h+var_1B8], ebx
0x180071918  cmp     ebx, 5
0x18007191b  jnz     short loc_18007192E
0x18007191d  mov     [rdi+8Ch], r15d
0x180071924  mov     ebx, 8007000Dh
0x180071929  jmp     loc_180071BFA
0x18007192e  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180071933  call    cs:__imp_Sleep
0x180071939  jmp     short loc_180071907
0x18007193b  cmp     [rax+50h], r15d
0x18007193f  jz      short loc_18007191D
0x180071941  mov     rax, [rcx]
0x180071944  sub     rax, qword ptr cs:?m_guidV11@CDVRFileCollection@@2U_GUID@@B.Data1; _GUID const CDVRFileCollection::m_guidV11 ...
  ... truncated ...
```
