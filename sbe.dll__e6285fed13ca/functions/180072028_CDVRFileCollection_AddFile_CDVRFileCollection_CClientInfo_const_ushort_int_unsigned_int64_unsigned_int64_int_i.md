# CDVRFileCollection::AddFile(CDVRFileCollection::CClientInfo const *,ushort * *,int,unsigned __int64,unsigned __int64,int,int,__int64,ulong *)

- ea: `0x180072028`
- end: `0x180072c94`
- name: `?AddFile@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@PEAPEAGH_K2HH_JPEAK@Z`
- size: `3180`
- prototype: `__int64 __usercall@<rax>(CDVRFileCollection *__hidden this@<rcx>, const struct CDVRFileCollection::CClientInfo *@<rdx>, unsigned __int16 **@<r8>, int@<r9d>, unsigned __int64, unsigned __int64, int, int, __int64, unsigned int *)`
- caller_count: `5`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x180063fbc`
- `0x180069bb8`
- `0x180069ee0`
- `0x18006b020`
- `0x18006f8c8`

## callees

- `0x1800017e0`
- `0x1800017ec`
- `0x180001c00`
- `0x180072028`
- `0x180073504`
- `0x180073c20`
- `0x180074ca8`
- `0x180074d6c`
- `0x180074ec4`
- `0x180076948`
- `0x180076bec`
- `0x1800b33f9`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180072258`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180072258`
- `KERNEL32!CloseHandle` at `0x1800725a8`
- `KERNEL32!CloseHandle` at `0x1800725a8`
- `KERNEL32!GetLastError` at `0x180072117`
- `KERNEL32!GetLastError` at `0x1800721df`
- `KERNEL32!GetLastError` at `0x180072299`
- `KERNEL32!GetLastError` at `0x180072518`
- `KERNEL32!GetLastError` at `0x180072117`
- `KERNEL32!GetLastError` at `0x1800721df`
- `KERNEL32!GetLastError` at `0x180072299`
- `KERNEL32!GetLastError` at `0x180072518`
- `KERNEL32!GetTempFileNameW` at `0x1800721d5`
- `KERNEL32!GetTempFileNameW` at `0x1800721d5`
- `KERNEL32!FlushViewOfFile` at `0x18007250e`
- `KERNEL32!FlushViewOfFile` at `0x18007250e`
- `KERNEL32!UnmapViewOfFile` at `0x1800726bb`
- `KERNEL32!UnmapViewOfFile` at `0x1800726bb`
- `KERNEL32!SetFileAttributesW` at `0x18007220c`
- `KERNEL32!SetFileAttributesW` at `0x18007220c`
- `KERNEL32!DeleteFileW` at `0x180072302`
- `KERNEL32!DeleteFileW` at `0x180072b2b`
- `KERNEL32!DeleteFileW` at `0x1800b4e76`
- `KERNEL32!DeleteFileW` at `0x1800b4f62`
- `KERNEL32!DeleteFileW` at `0x180072302`
- `KERNEL32!DeleteFileW` at `0x180072b2b`
- `KERNEL32!DeleteFileW` at `0x1800b4e76`
- `KERNEL32!DeleteFileW` at `0x1800b4f62`
- `KERNEL32!GetFullPathNameW` at `0x18007210d`
- `KERNEL32!GetFullPathNameW` at `0x18007228f`
- `KERNEL32!GetFullPathNameW` at `0x18007210d`
- `KERNEL32!GetFullPathNameW` at `0x18007228f`

## pseudocode

```c
__int64 __fastcall CDVRFileCollection::AddFile(
        CDVRFileCollection *this,
        const struct CDVRFileCollection::CClientInfo *a2,
        LPCWSTR *a3,
        unsigned int a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        int a7,
        int a8,
        __int64 a9,
        unsigned int *a10)
{
  void **v10; // r13
  unsigned int v12; // ebx
  signed int LastError; // r12d
  int v14; // edi
  DWORD FullPathNameW; // eax
  bool v16; // zf
  int v18; // r15d
  unsigned __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // r13
  const WCHAR *v22; // rax
  __int64 v23; // r9
  const WCHAR *v24; // r15
  int v25; // eax
  __int64 v26; // rdx
  unsigned __int16 *v27; // rcx
  unsigned __int16 *v28; // rbx
  int v29; // r15d
  struct _SHARED_LIST_ENTRY *v30; // r13
  __int64 v31; // r9
  struct _SHARED_LIST_ENTRY *v32; // r11
  __int64 v33; // r10
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rax
  __int64 v36; // r9
  int v37; // r8d
  unsigned int v38; // ecx
  int v39; // ecx
  int v40; // eax
  struct CDVRFileCollection::CSharedData *v41; // rdx
  unsigned int v42; // r9d
  unsigned int v43; // r11d
  unsigned int v44; // r10d
  __int64 v45; // rbx
  __int16 v46; // ax
  volatile __int32 *v47; // rdi
  unsigned int v48; // edx
  const void *v49; // rbx
  struct CDVRFileCollection::CSharedData *v50; // rcx
  __int64 v51; // r10
  __int64 v52; // rax
  void *v53; // rax
  void *v54; // rbx
  unsigned __int64 v55; // rdx
  char *v56; // rcx
  unsigned int v57; // edx
  unsigned int v58; // r8d
  unsigned int i; // r9d
  _WORD *v60; // r10
  __int64 v61; // r11
  __int64 v62; // rbx
  __int16 v63; // dx
  __int64 v64; // r9
  __int64 v65; // rdx
  __int64 v66; // r8
  int v67; // ecx
  WCHAR *v68; // rdx
  int v69; // eax
  __int64 v70; // rdx
  __int64 v71; // rcx
  unsigned __int16 v72; // ax
  unsigned int *v73; // r8
  unsigned __int64 v74; // rdx
  void **v75; // r13
  unsigned __int64 v76; // rdx
  void **v77; // r13
  __int64 v78; // r8
  _WORD *v79; // rdx
  __int64 v80; // r10
  __int64 v81; // r9
  _WORD *v82; // r8
  __int64 v83; // rcx
  unsigned __int16 v84; // ax
  unsigned int v85; // [rsp+68h] [rbp-2F0h]
  unsigned int v86; // [rsp+6Ch] [rbp-2ECh] BYREF
  int v87; // [rsp+70h] [rbp-2E8h]
  int v88; // [rsp+74h] [rbp-2E4h]
  unsigned __int16 *v89; // [rsp+78h] [rbp-2E0h]
  int v90; // [rsp+80h] [rbp-2D8h]
  int v91; // [rsp+84h] [rbp-2D4h]
  void *v92; // [rsp+88h] [rbp-2D0h] BYREF
  unsigned int v93; // [rsp+90h] [rbp-2C8h] BYREF
  unsigned int Size; // [rsp+94h] [rbp-2C4h]
  int Size_4; // [rsp+98h] [rbp-2C0h]
  void **v96; // [rsp+A0h] [rbp-2B8h]
  unsigned __int16 *v97; // [rsp+A8h] [rbp-2B0h]
  struct _SHARED_LIST_ENTRY *v98; // [rsp+B0h] [rbp-2A8h]
  CDVRFileCollection *v99; // [rsp+B8h] [rbp-2A0h]
  LPCWSTR *v100; // [rsp+C0h] [rbp-298h]
  int v101; // [rsp+C8h] [rbp-290h]
  unsigned int v102; // [rsp+CCh] [rbp-28Ch]
  unsigned int v103; // [rsp+D0h] [rbp-288h]
  int v104; // [rsp+D4h] [rbp-284h]
  struct CDVRFileCollection::CClientInfo *v105; // [rsp+D8h] [rbp-280h]
  struct CDVRFileCollection::CSharedData *v106; // [rsp+E0h] [rbp-278h] BYREF
  unsigned int *v107; // [rsp+E8h] [rbp-270h]
  LPWSTR FilePart[2]; // [rsp+F0h] [rbp-268h] BYREF
  WCHAR Buffer[256]; // [rsp+100h] [rbp-258h] BYREF

  v10 = (void **)a3;
  v96 = (void **)a3;
  v105 = a2;
  v99 = this;
  v92 = a2;
  v100 = a3;
  v107 = a10;
  if ( !a3 || !a10 || __PAIR128__(a6, a5) < __PAIR128__(a5, -1) )
    return 2147942487LL;
  v12 = 0;
  LastError = 0;
  FilePart[0] = 0;
  v88 = 0;
  v87 = 0;
  if ( *a3 )
  {
    v14 = 0;
    v91 = 0;
    FullPathNameW = GetFullPathNameW(*a3, 0x104u, Buffer, FilePart);
    if ( FullPathNameW )
    {
      if ( FullPathNameW >= 0x104 )
        v12 = -2147024882;
    }
    else
    {
      LastError = GetLastError();
    }
    if ( v12 || LastError )
    {
      if ( LastError )
      {
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        else
          v12 = LastError;
      }
      v14 = 1;
      v91 = 1;
    }
    v16 = v14 == 0;
  }
  else
  {
    v18 = 0;
    if ( GetTempFileNameW(*((LPCWSTR *)this + 13), L"SBE", 0, Buffer) )
    {
      v88 = 1;
      SetFileAttributesW(Buffer, 0x2006u);
      v20 = -1;
      do
        ++v20;
      while ( Buffer[v20] );
      v21 = v20 + 1;
      v22 = (const WCHAR *)operator new[](saturated_mul(v20 + 1, 2u));
      v24 = v22;
      if ( v22 )
      {
        _o_wcscpy_s(v22, v21, Buffer, v23);
        v10 = v96;
        *v96 = (void *)v24;
        v87 = 1;
        if ( a4 && !GetFullPathNameW(v24, 0x104u, Buffer, FilePart) )
          LastError = GetLastError();
      }
      else
      {
        v12 = -2147024882;
        v10 = v96;
      }
      v18 = 0;
    }
    else
    {
      LastError = GetLastError();
    }
    if ( v12 || LastError )
    {
      if ( LastError )
      {
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        else
          v12 = LastError;
      }
      if ( v87 )
      {
        operator delete(*v10, v19);
        *v10 = 0;
      }
      if ( v88 )
        DeleteFileW(Buffer);
      v18 = 1;
      v104 = 1;
    }
    v16 = v18 == 0;
  }
  if ( !v16 )
    return v12;
  v86 = 0;
  v25 = CDVRFileCollection::Lock(this, v105, &v86, 5, 0);
  v27 = 0;
  v89 = 0;
  v28 = 0;
  v97 = 0;
  v90 = 0;
  v92 = 0;
  v29 = -2147467259;
  if ( v25 < 0 )
  {
    v29 = v25;
    goto LABEL_119;
  }
  if ( (*((_BYTE *)this + 172) & 4) != 0 )
  {
    v29 = -2147024809;
    goto LABEL_119;
  }
  Size_4 = 0;
  v30 = (struct _SHARED_LIST_ENTRY *)(*((_QWORD *)this + 4) + 1896LL);
  v98 = v30;
  while ( 1 )
  {
    if ( *(_WORD *)v30 == 0xFFFF || !(unsigned int)IsSharedListPointerValid(v30) )
    {
      v31 = *((_QWORD *)this + 4);
      v26 = v31 + 1896;
    }
    else
    {
      v26 = 568LL * *(unsigned __int16 *)v30 + *((_QWORD *)this + 5) + 562LL;
    }
    v32 = (struct _SHARED_LIST_ENTRY *)(v31 + 1896);
    if ( v26 == v31 + 1896 )
      break;
    if ( *(_WORD *)v30 == 0xFFFF || !(unsigned int)IsSharedListPointerValid(v30) )
      v30 = v32;
    else
      v30 = (struct _SHARED_LIST_ENTRY *)(568 * v33 + *((_QWORD *)this + 5) + 562LL);
    v98 = v30;
    v34 = *(_QWORD *)((char *)v30 - 562);
    v35 = *(_QWORD *)((char *)v30 - 554);
    if ( v35 != v34 || v35 == -1 )
    {
      if ( a6 <= v34 )
      {
        Size_4 = 1;
        break;
      }
      if ( a5 < v35 )
        goto LABEL_92;
    }
  }
  v36 = *((_QWORD *)this + 4);
  if ( *(_WORD *)(v36 + 1902) != 0xFFFF || *(_WORD *)(v36 + 1904) != 0xFFFF )
    goto LABEL_81;
  v37 = *((_DWORD *)this + 3);
  if ( !v37 || (v26 = *((unsigned int *)this + 2), (_DWORD)v26 == 65534) )
  {
LABEL_91:
    v29 = -2147024882;
    goto LABEL_92;
  }
  if ( (unsigned int)(v26 + v37) <= 0xFFFE )
    v38 = *((_DWORD *)this + 3);
  else
    v38 = 65534 - v26;
  v85 = v38;
  Size = 568 * v26 + 1912;
  v39 = 568 * v38;
  v101 = v39;
  if ( (*((_BYTE *)this + 172) & 1) == 0 )
  {
    v53 = operator new[]((unsigned int)(568 * v26 + 1912 + v39));
    v92 = v53;
    if ( v53 )
    {
      memcpy_0(v53, *((const void **)this + 4), Size);
      v54 = (void *)*((_QWORD *)this + 4);
      operator delete(v54, v55);
      v56 = (char *)v92;
      *((_QWORD *)this + 4) = v92;
      *((_QWORD *)this + 5) = v56 + 1912;
      v30 = (struct _SHARED_LIST_ENTRY *)&v56[v30 - (struct _SHARED_LIST_ENTRY *)v54];
      v98 = v30;
      v57 = 0;
      v58 = 0;
      for ( i = 0; ; i = v57 )
      {
        v103 = v57;
        if ( v58 >= v85 )
          break;
        *(_WORD *)(568LL * (i + *((_DWORD *)this + 2)) + *((_QWORD *)this + 5) + 566) = *((_WORD *)this + 4) + v57;
        v60 = (_WORD *)*((_QWORD *)this + 4);
        v61 = (unsigned __int16)v60[952];
        *(_WORD *)(568LL * (i + *((_DWORD *)this + 2)) + *((_QWORD *)this + 5) + 562) = v60[953];
        *(_WORD *)(568LL * (i + *((_DWORD *)this + 2)) + *((_QWORD *)this + 5) + 564) = v61;
        v62 = *((_QWORD *)this + 5);
        v63 = *(_WORD *)(568LL * (i + *((_DWORD *)this + 2)) + v62 + 566);
        if ( (_WORD)v61 == 0xFFFF )
          v60[951] = v63;
        else
          *(_WORD *)(568 * v61 + v62 + 562) = v63;
        v60[952] = *(_WORD *)(568LL * (i + *((_DWORD *)this + 2)) + *((_QWORD *)this + 5) + 566);
        v57 = v58 + 1;
        v58 = v57;
      }
      *((_DWORD *)this + 2) += v85;
      goto LABEL_81;
    }
    goto LABEL_91;
  }
  v106 = 0;
  v93 = *(_DWORD *)(v36 + 80);
  if ( !FlushViewOfFile((LPCVOID)v36, 0) )
  {
    LastError = GetLastError();
LABEL_92:
    v27 = 0;
    goto LABEL_119;
  }
  v40 = CDVRFileCollection::CreateMemoryMap(
          this,
          v105,
          Size,
          *((unsigned __int8 **)this + 4),
          Size + v101,
          &v93,
          3u,
          0x80u,
          &v106,
          &v92,
          0);
  if ( v40 < 0 )
  {
    v29 = v40;
    goto LABEL_92;
  }
  CloseHandle(*((HANDLE *)this + 6));
  *((_QWORD *)this + 6) = v92;
  v41 = v106;
  LOWORD(v42) = 0;
  v102 = 0;
  v43 = 0;
  v44 = 0;
  while ( v43 < v85 )
  {
    *((_WORD *)v41 + 284 * v44 + 284 * *((_DWORD *)this + 2) + 1239) = *((_WORD *)this + 4) + v42;
    v45 = *((unsigned __int16 *)v41 + 952);
    *((_WORD *)v41 + 284 * v44 + 284 * *((_DWORD *)this + 2) + 1237) = *((_WORD *)v41 + 953);
    *((_WORD *)v41 + 284 * v44 + 284 * *((_DWORD *)this + 2) + 1238) = v45;
    v46 = *((_WORD *)v41 + 284 * v44 + 284 * *((_DWORD *)this + 2) + 1239);
    if ( (_WORD)v45 == 0xFFFF )
      *((_WORD *)v41 + 951) = v46;
    else
      *((_WORD *)v41 + 284 * v45 + 1237) = v46;
    *((_WORD *)v41 + 952) = *((_WORD *)v41 + 284 * v44 + 284 * *((_DWORD *)this + 2) + 1239);
    v42 = v43 + 1;
    v102 = v42;
    ++v43;
    v44 = v42;
  }
  v47 = (volatile __int32 *)((char *)v41 + 80);
  v48 = v93;
  _InterlockedExchange(v47, v93);
  _InterlockedExchange((volatile __int32 *)(*((_QWORD *)this + 4) + 80LL), v48);
  v49 = (const void *)*((_QWORD *)this + 4);
  UnmapViewOfFile(v49);
  v50 = v106;
  *((_QWORD *)this + 4) = v106;
  *((_QWORD *)this + 5) = (char *)v50 + 1912;
  v30 = (struct _SHARED_LIST_ENTRY *)((char *)v30 + v50 - (struct CDVRFileCollection::CSharedData *)v49);
  v98 = v30;
  *((_DWORD *)this + 2) += v85;
  *((_DWORD *)this + 35) = *v47;
LABEL_81:
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 64LL));
  v90 = 1;
  v51 = *((_QWORD *)this + 4);
  v52 = *(unsigned __int16 *)(v51 + 1902);
  if ( (_WORD)v52 == 0xFFFF )
  {
    v28 = 0;
  }
  else
  {
    v64 = *((_QWORD *)this + 5);
    v28 = (unsigned __int16 *)(568 * v52 + v64 + 562);
    v65 = *v28;
    v66 = *(unsigned __int16 *)(568 * v52 + v64 + 564);
    if ( (_WORD)v66 == 0xFFFF )
      *(_WORD *)(v51 + 1902) = v65;
    else
      *(_WORD *)(568 * v66 + v64 + 562) = v65;
    if ( (_WORD)v65 == 0xFFFF )
      *(_WORD *)(v51 + 1904) = v66;
    else
      *(_WORD *)(568 * v65 + v64 + 564) = v66;
  }
  v97 = v28;
  v89 = v28 - 281;
  v67 = 0;
  if ( !a7 )
    v67 = a8;
  v68 = Buffer;
  if ( a4 )
    v68 = FilePart[0];
  v69 = CDVRFileCollection::CSharedData::CFileInfo::Initialize(
          v28 - 281,
          v68,
          a4,
          a5,
          a6,
          a9,
          a7,
          v67,
          *((_DWORD *)this + 34));
  ++*((_DWORD *)this + 34);
  if ( v69 >= 0 )
  {
    if ( !Size_4 )
    {
      if ( *(_WORD *)v30 == 0xFFFF || !(unsigned int)IsSharedListPointerValid(v30) )
        v30 = (struct _SHARED_LIST_ENTRY *)(*((_QWORD *)this + 4) + 1896LL);
      else
        v30 = (struct _SHARED_LIST_ENTRY *)(568LL * *(unsigned __int16 *)v30 + *((_QWORD *)this + 5) + 562LL);
      v98 = v30;
    }
    v70 = *((_QWORD *)this + 4);
    v71 = *((unsigned __int16 *)v30 + 1);
    *v28 = *((_WORD *)v30 + 2);
    v28[1] = v71;
    v72 = v28[2];
    if ( (_WORD)v71 == 0xFFFF )
      *(_WORD *)(v70 + 1896) = v72;
    else
      *(_WORD *)(568 * v71 + *((_QWORD *)this + 5) + 562) = v72;
    *((_WORD *)v30 + 1) = v28[2];
    CDVRFileCollection::UpdateTimeExtent(this, 1);
    _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 64LL));
    v90 = 0;
    if ( !*((_DWORD *)v89 + 8) )
    {
      v29 = CDVRFileCollection::DeleteUnusedInvalidFileNodes(this, 0, v73);
      if ( !v29 )
        v29 = 1;
      v27 = 0;
      v89 = 0;
      v28 = 0;
      v97 = 0;
      goto LABEL_119;
    }
    v29 = CDVRFileCollection::DeleteUnusedInvalidFileNodes(this, 0, v73);
  }
  v27 = v89;
LABEL_119:
  if ( v29 < 0 || LastError )
  {
    CDVRFileCollection::Unlock(this, v26, v86, 5, 0);
    if ( v88 )
      DeleteFileW(Buffer);
    if ( v87 )
    {
      v77 = v96;
      operator delete(*v96, v76);
      *v77 = 0;
    }
    if ( v28 )
    {
      v78 = *v28;
      if ( (_WORD)v78 != 0xFFFF || (v79 = v28 + 1, v28[1] != 0xFFFF) )
      {
        v80 = *((_QWORD *)this + 4);
        v79 = v28 + 1;
        v81 = v28[1];
        if ( (_WORD)v81 == 0xFFFF )
          *(_WORD *)(v80 + 1896) = v78;
        else
          *(_WORD *)(568 * v81 + *((_QWORD *)this + 5) + 562) = v78;
        if ( (_WORD)v78 == 0xFFFF )
          *(_WORD *)(v80 + 1898) = v81;
        else
          *(_WORD *)(568 * v78 + *((_QWORD *)this + 5) + 564) = v81;
      }
      v82 = (_WORD *)*((_QWORD *)this + 4);
      v83 = (unsigned __int16)v82[952];
      *v28 = v82[953];
      *v79 = v83;
      v84 = v28[2];
      if ( (_WORD)v83 == 0xFFFF )
        v82[951] = v84;
      else
        *(_WORD *)(568 * v83 + *((_QWORD *)this + 5) + 562) = v84;
      v82[952] = v28[2];
      v89[20] = 0;
      v89 = 0;
      v97 = 0;
    }
    if ( v90 )
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 4) + 64LL));
    if ( LastError )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      else
        return (unsigned int)LastError;
    }
  }
  else if ( v29 == 1 )
  {
    CDVRFileCollection::Unlock(this, v26, v86, 5, 0);
    if ( v87 )
    {
      v75 = v96;
      operator delete(*v96, v74);
      *v75 = 0;
    }
  }
  else
  {
    *v107 = *((_DWORD *)v27 + 6);
    CDVRFileCollection::Unlock(this, v26, v86, 5, 0);
  }
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x180072028  mov     [rsp+arg_18], r9d
0x18007202d  push    rbx
0x18007202e  push    rsi
0x18007202f  push    rdi
0x180072030  push    r12
0x180072032  push    r13
0x180072034  push    r14
0x180072036  push    r15
0x180072038  sub     rsp, 320h
0x18007203f  mov     rax, cs:__security_cookie
0x180072046  xor     rax, rsp
0x180072049  mov     [rsp+358h+var_48], rax
0x180072051  mov     r13, r8
0x180072054  mov     [rsp+358h+var_2B8], r8
0x18007205c  mov     [rsp+358h+var_280], rdx
0x180072064  mov     r14, rcx
0x180072067  mov     [rsp+358h+var_2A0], rcx
0x18007206f  mov     [rsp+358h+var_2D0], rdx
0x180072077  mov     [rsp+358h+var_298], r8
0x18007207f  mov     r15, [rsp+358h+arg_48]
0x180072087  mov     [rsp+358h+var_270], r15
0x18007208f  xor     esi, esi
0x180072091  test    r8, r8
0x180072094  jz      loc_180072C6C
0x18007209a  test    r15, r15
0x18007209d  jz      loc_180072C6C
0x1800720a3  mov     rax, [rsp+358h+arg_20]
0x1800720ab  cmp     rax, [rsp+358h+arg_28]
0x1800720b3  ja      loc_180072C6C
0x1800720b9  jnz     short loc_1800720C5
0x1800720bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800720bf  jnz     loc_180072C6C
0x1800720c5  mov     ebx, esi
0x1800720c7  mov     [rsp+358h+var_2F8], ebx
0x1800720cb  mov     r12d, esi
0x1800720ce  mov     [rsp+358h+var_2F4], esi
0x1800720d2  mov     [rsp+358h+FilePart], rsi
0x1800720da  mov     [rsp+358h+var_2E4], esi
0x1800720de  mov     [rsp+358h+var_2E8], esi
0x1800720e2  cmp     [r8], rsi
0x1800720e5  jz      loc_1800721B8
0x1800720eb  mov     edi, esi
0x1800720ed  mov     [rsp+358h+var_2D4], esi
0x1800720f4  lea     r9, [rsp+358h+FilePart]; lpFilePart
0x1800720fc  lea     r8, [rsp+358h+Buffer]; lpBuffer
0x180072104  mov     edx, 104h; nBufferLength
0x180072109  mov     rcx, [r13+0]; lpFileName
0x18007210d  call    cs:__imp_GetFullPathNameW
0x180072113  test    eax, eax
0x180072115  jnz     short loc_180072126
0x180072117  call    cs:__imp_GetLastError
0x18007211d  mov     r12d, eax
0x180072120  mov     [rsp+358h+var_2F4], eax
0x180072124  jmp     short loc_180072139
0x180072126  mov     r13d, 8007000Eh
0x18007212c  cmp     eax, 104h
0x180072131  cmovnb  ebx, r13d
0x180072135  mov     [rsp+358h+var_2F8], ebx
0x180072139  test    ebx, ebx
0x18007213b  jnz     short loc_180072142
0x18007213d  test    r12d, r12d
0x180072140  jz      short loc_180072168
0x180072142  test    r12d, r12d
0x180072145  jz      short loc_18007215C
0x180072147  jg      short loc_18007214E
0x180072149  mov     ebx, r12d
0x18007214c  jmp     short loc_180072158
0x18007214e  movzx   ebx, r12w
0x180072152  or      ebx, 80070000h
0x180072158  mov     [rsp+358h+var_2F8], ebx
0x18007215c  mov     edi, 1
0x180072161  mov     [rsp+358h+var_2D4], edi
0x180072168  jmp     short loc_1800721A9
0x18007216a  mov     ebx, 0C0000005h
0x18007216f  mov     [rsp+358h+var_2F8], ebx
0x180072173  xor     esi, esi
0x180072175  mov     r12d, [rsp+358h+var_2F4]
0x18007217a  mov     edi, [rsp+358h+var_2D4]
0x180072181  mov     r14, [rsp+358h+var_2A0]
0x180072189  mov     rax, [rsp+358h+var_2D0]
0x180072191  mov     [rsp+358h+var_280], rax
0x180072199  mov     rax, [rsp+358h+var_298]
0x1800721a1  mov     [rsp+358h+var_2B8], rax
0x1800721a9  test    edi, edi
0x1800721ab  jz      loc_18007231A
0x1800721b1  mov     eax, ebx
0x1800721b3  jmp     loc_180072C71
0x1800721b8  mov     r15d, esi
0x1800721bb  mov     [rsp+358h+var_2F0], esi
0x1800721bf  lea     r9, [rsp+358h+Buffer]; lpTempFileName
0x1800721c7  xor     r8d, r8d; uUnique
0x1800721ca  lea     rdx, PrefixString; "SBE"
0x1800721d1  mov     rcx, [rcx+68h]; lpPathName
0x1800721d5  call    cs:__imp_GetTempFileNameW
0x1800721db  test    eax, eax
0x1800721dd  jnz     short loc_1800721F6
0x1800721df  call    cs:__imp_GetLastError
0x1800721e5  mov     r12d, eax
0x1800721e8  mov     [rsp+358h+var_2F4], eax
0x1800721ec  mov     edi, 1
0x1800721f1  jmp     loc_1800722BE
0x1800721f6  mov     edi, 1
0x1800721fb  mov     [rsp+358h+var_2E4], edi
0x1800721ff  mov     edx, 2006h; dwFileAttributes
0x180072204  lea     rcx, [rsp+358h+Buffer]; lpFileName
0x18007220c  call    cs:__imp_SetFileAttributesW
0x180072212  lea     rdx, [rsp+358h+Buffer]
0x18007221a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007221e  mov     rax, rcx
0x180072221  inc     rax
0x180072224  cmp     [rdx+rax*2], si
0x180072228  jnz     short loc_180072221
0x18007222a  lea     r13, [rax+1]
0x18007222e  mov     eax, 2
0x180072233  mul     r13
0x180072236  cmovb   rax, rcx
0x18007223a  mov     rcx, rax; unsigned __int64
0x18007223d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180072242  mov     r15, rax
0x180072245  test    rax, rax
0x180072248  jz      short loc_1800722A8
0x18007224a  lea     r8, [rsp+358h+Buffer]
0x180072252  mov     rdx, r13
0x180072255  mov     rcx, rax
0x180072258  call    cs:__imp__o_wcscpy_s
0x18007225e  mov     r13, [rsp+358h+var_2B8]
0x180072266  mov     [r13+0], r15
0x18007226a  mov     [rsp+358h+var_2E8], edi
0x18007226e  cmp     [rsp+358h+arg_18], esi
0x180072275  jz      short loc_1800722B9
0x180072277  lea     r9, [rsp+358h+FilePart]; lpFilePart
0x18007227f  lea     r8, [rsp+358h+Buffer]; lpBuffer
0x180072287  mov     edx, 104h; nBufferLength
0x18007228c  mov     rcx, r15; lpFileName
0x18007228f  call    cs:__imp_GetFullPathNameW
0x180072295  test    eax, eax
0x180072297  jnz     short loc_1800722B9
0x180072299  call    cs:__imp_GetLastError
0x18007229f  mov     r12d, eax
0x1800722a2  mov     [rsp+358h+var_2F4], eax
0x1800722a6  jmp     short loc_1800722B9
0x1800722a8  mov     ebx, 8007000Eh
0x1800722ad  mov     [rsp+358h+var_2F8], ebx
0x1800722b1  mov     r13, [rsp+358h+var_2B8]
0x1800722b9  mov     r15d, [rsp+358h+var_2F0]
0x1800722be  test    ebx, ebx
0x1800722c0  jnz     short loc_1800722C7
0x1800722c2  test    r12d, r12d
0x1800722c5  jz      short loc_180072312
0x1800722c7  test    r12d, r12d
0x1800722ca  jz      short loc_1800722E1
0x1800722cc  jg      short loc_1800722D3
0x1800722ce  mov     ebx, r12d
0x1800722d1  jmp     short loc_1800722DD
0x1800722d3  movzx   ebx, r12w
0x1800722d7  or      ebx, 80070000h
0x1800722dd  mov     [rsp+358h+var_2F8], ebx
0x1800722e1  cmp     [rsp+358h+var_2E8], esi
0x1800722e5  jz      short loc_1800722F4
0x1800722e7  mov     rcx, [r13+0]; void *
0x1800722eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800722f0  mov     [r13+0], rsi
0x1800722f4  cmp     [rsp+358h+var_2E4], esi
0x1800722f8  jz      short loc_180072308
0x1800722fa  lea     rcx, [rsp+358h+Buffer]; lpFileName
0x180072302  call    cs:__imp_DeleteFileW
0x180072308  mov     r15d, edi
0x18007230b  mov     [rsp+358h+var_284], edi
0x180072312  test    r15d, r15d
0x180072315  jmp     loc_1800721AB
0x18007231a  mov     [rsp+358h+var_2EC], esi
0x18007231e  mov     [rsp+358h+var_338], esi
0x180072322  mov     r9d, 5
0x180072328  lea     r8, [rsp+358h+var_2EC]
0x18007232d  mov     rdx, [rsp+358h+var_280]
0x180072335  mov     rcx, r14
0x180072338  call    ?Lock@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@AEAHW4DVRFILECOLLECTIONCALLER@@H@Z; CDVRFileCollection::Lock(CDVRFileCollection::CClientInfo const *,int &,DVRFILECOLLECTIONCALLER,int)
0x18007233d  mov     rcx, rsi
0x180072340  mov     [rsp+358h+var_2E0], rcx
0x180072345  mov     rbx, rsi
0x180072348  mov     [rsp+358h+var_2B0], rbx
0x180072350  mov     [rsp+358h+var_2D8], esi
0x180072357  mov     [rsp+358h+var_2D0], rsi
0x18007235f  mov     r15d, 80004005h
0x180072365  mov     [rsp+358h+var_2F8], r15d
0x18007236a  mov     edi, 0FFFFh
0x18007236f  test    eax, eax
0x180072371  jns     short loc_180072385
0x180072373  mov     r15d, eax
0x180072376  mov     [rsp+358h+var_2F8], eax
0x18007237a  mov     r8d, 1
0x180072380  jmp     loc_180072A9E
0x180072385  test    byte ptr [r14+0ACh], 4
0x18007238d  jz      short loc_18007239C
0x18007238f  mov     r15d, 80070057h
0x180072395  mov     [rsp+358h+var_2F8], r15d
0x18007239a  jmp     short loc_18007237A
0x18007239c  mov     dword ptr [rsp+358h+Size+4], esi
0x1800723a3  mov     r9, [r14+20h]
0x1800723a7  lea     r13, [r9+768h]
0x1800723ae  mov     [rsp+358h+var_2A8], r13
0x1800723b6  cmp     [r13+0], di
0x1800723bb  jz      short loc_1800723E5
0x1800723bd  mov     rcx, r13; struct _SHARED_LIST_ENTRY *
0x1800723c0  call    ?IsSharedListPointerValid@@YAHPEAU_SHARED_LIST_ENTRY@@@Z; IsSharedListPointerValid(_SHARED_LIST_ENTRY *)
0x1800723c5  test    eax, eax
0x1800723c7  jz      short loc_1800723E5
0x1800723c9  movzx   r10d, word ptr [r13+0]
0x1800723ce  imul    rcx, r10, 238h
0x1800723d5  mov     rdx, [r14+28h]
0x1800723d9  add     rdx, 232h
0x1800723e0  add     rdx, rcx
0x1800723e3  jmp     short loc_1800723F5
0x1800723e5  mov     r9, [r14+20h]
0x1800723e9  lea     rdx, [r9+768h]
0x1800723f0  movzx   r10d, word ptr [r13+0]
0x1800723f5  lea     r11, [r9+768h]
0x1800723fc  cmp     rdx, r11
0x1800723ff  jz      short loc_180072469
0x180072401  cmp     [r13+0], di
0x180072406  jz      short loc_18007242B
0x180072408  mov     rcx, r13; struct _SHARED_LIST_ENTRY *
0x18007240b  call    ?IsSharedListPointerValid@@YAHPEAU_SHARED_LIST_ENTRY@@@Z; IsSharedListPointerValid(_SHARED_LIST_ENTRY *)
0x180072410  test    eax, eax
0x180072412  jz      short loc_18007242B
0x180072414  imul    rcx, r10, 238h
0x18007241b  mov     r13, [r14+28h]
0x18007241f  add     r13, 232h
0x180072426  add     r13, rcx
0x180072429  jmp     short loc_18007242E
0x18007242b  mov     r13, r11
0x18007242e  mov     [rsp+358h+var_2A8], r13
0x180072436  mov     rcx, [r13-232h]
0x18007243d  mov     rax, [r13-22Ah]
0x180072444  cmp     rax, rcx
0x180072447  jnz     short loc_180072454
0x180072449  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007244d  jz      short loc_180072454
0x18007244f  jmp     loc_1800723B6
0x180072454  cmp     [rsp+358h+arg_28], rcx
0x18007245c  ja      short loc_1800724B3
0x18007245e  mov     dword ptr [rsp+358h+Size+4], 1
0x180072469  mov     r9, [r14+20h]
0x18007246d  cmp     [r9+76Eh], di
0x180072475  jnz     loc_1800726FC
0x18007247b  cmp     [r9+770h], di
0x180072483  jnz     loc_1800726FC
0x180072489  mov     r8d, [r14+0Ch]
0x18007248d  test    r8d, r8d
0x180072490  jz      loc_180072880
0x180072496  mov     edx, [r14+8]
0x18007249a  mov     ecx, 0FFFEh
0x18007249f  cmp     edx, ecx
0x1800724a1  jz      loc_180072880
0x1800724a7  lea     eax, [rdx+r8]
0x1800724ab  cmp     eax, ecx
0x1800724ad  jbe     short loc_1800724C2
0x1800724af  sub     ecx, edx
0x1800724b1  jmp     short loc_1800724C5
0x1800724b3  cmp     [rsp+358h+arg_20], rax
0x1800724bb  jnb     short loc_18007244F
0x1800724bd  jmp     loc_18007288B
0x1800724c2  mov     ecx, r8d
0x1800724c5  mov     [rsp+358h+var_2F0], ecx
0x1800724c9  imul    eax, edx, 238h
0x1800724cf  add     eax, 778h
0x1800724d4  mov     dword ptr [rsp+358h+Size], eax
0x1800724db  imul    ecx, 238h
0x1800724e1  mov     [rsp+358h+var_290], ecx
0x1800724e8  test    byte ptr [r14+0ACh], 1
0x1800724f0  jz      loc_18007272C
0x1800724f6  mov     [rsp+358h+var_278], rsi
0x1800724fe  mov     eax, [r9+50h]
0x180072502  mov     [rsp+358h+var_2C8], eax
0x180072509  xor     edx, edx; dwNumberOfBytesToFlush
0x18007250b  mov     rcx, r9; lpBaseAddress
0x18007250e  call    cs:__imp_FlushViewOfFile
0x180072514  test    eax, eax
0x180072516  jnz     short loc_18007252A
0x180072518  call    cs:__imp_GetLastError
0x18007251e  mov     r12d, eax
0x180072521  mov     [rsp+358h+var_2F4], eax
0x180072525  jmp     loc_18007288B
0x18007252a  mov     eax, [rsp+358h+var_290]
0x180072531  add     eax, dword ptr [rsp+358h+Size]
0x180072538  mov     [rsp+358h+var_308], rsi; void **
0x18007253d  lea     rdx, [rsp+358h+var_2D0]
0x180072545  mov     [rsp+358h+var_310], rdx; void **
0x18007254a  lea     rdx, [rsp+358h+var_278]
0x180072552  mov     [rsp+358h+var_318], rdx; struct CDVRFileCollection::CSharedData **
0x180072557  mov     [rsp+358h+var_320], 80h; unsigned int
0x18007255f  mov     [rsp+358h+var_328], 3; unsigned int
0x180072567  lea     rdx, [rsp+358h+var_2C8]
0x18007256f  mov     [rsp+358h+var_330], rdx; unsigned int *
0x180072574  mov     [rsp+358h+var_338], eax; unsigned int
0x180072578  mov     r9, [r14+20h]; unsigned __int8 *
0x18007257c  mov     r8d, dword ptr [rsp+358h+Size]; unsigned int
0x180072584  mov     rdx, [rsp+358h+var_280]; struct CDVRFileCollection::CClientInfo *
0x18007258c  mov     rcx, r14; this
0x18007258f  call    ?CreateMemoryMap@CDVRFileCollection@@IEAAJPEBUCClientInfo@1@KPEAEKAEAKKKAEAPEAUCSharedData@1@PEAPEAX4@Z; CDVRFileCollection::CreateMemoryMap(CDVRFileCollection::CClientInfo const *,ulong,uchar *,ulong,ulong &,ulong,ulong,CDVRFileCollection::CSharedData * &,void * *,void * *)
  ... truncated ...
```
