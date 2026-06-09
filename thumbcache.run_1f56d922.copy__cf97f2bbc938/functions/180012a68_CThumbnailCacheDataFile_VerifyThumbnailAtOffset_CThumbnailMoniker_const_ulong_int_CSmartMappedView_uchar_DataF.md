# CThumbnailCacheDataFile::_VerifyThumbnailAtOffset(CThumbnailMoniker const &,ulong,int,CSmartMappedView<uchar> &,DataFileEntryHeaderAligned const * *)

- ea: `0x180012a68`
- end: `0x180012e54`
- name: `?_VerifyThumbnailAtOffset@CThumbnailCacheDataFile@@AEAAJAEBVCThumbnailMoniker@@KHAEAV?$CSmartMappedView@E@@PEAPEFBUDataFileEntryHeaderAligned@@@Z`
- size: `1004`
- prototype: `__int64 __usercall@<rax>(CThumbnailCacheDataFile *this@<rcx>, __int64, CFileHandleCache *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f0e8`
- `0x180044ff4`

## callees

- `0x18000b3c0`
- `0x18000bfd8`
- `0x18000cac0`
- `0x180011300`
- `0x18001290c`
- `0x180012a68`
- `0x180012f3c`
- `0x180013008`
- `0x180014a38`
- `0x180023e68`
- `0x180025ac4`
- `0x180033f48`
- `0x18003470c`
- `0x180047a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012bb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180012bb3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180012b46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180012b46`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180012ae3`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180012c2f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180012c94`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180012ca5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180012ae3`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180012c2f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180012c94`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180012ca5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180012c7d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180012c7d`

## string_xrefs

- `0x180012d4d`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbfile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThumbnailCacheDataFile::_VerifyThumbnailAtOffset(
        CThumbnailCacheDataFile *this,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        CFileHandleCache *a6)
{
  CFileHandleCache *v8; // rcx
  HANDLE *v9; // r15
  __int64 v10; // r12
  unsigned int FileHandle; // edi
  RTL_SRWLOCK *v12; // r14
  unsigned int v13; // r15d
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rsi
  unsigned int v17; // edi
  unsigned int v18; // r8d
  __int64 v19; // rcx
  __int64 v20; // rdx
  unsigned int Ptr; // ecx
  unsigned int v22; // r9d
  __int64 v23; // rbx
  bool v24; // zf
  __int64 v25; // rbx
  CThumbnailCacheDataFile *v27; // rbx
  HANDLE v28; // rdi
  HANDLE FileMappingW; // rax
  DWORD FileSize; // eax
  int Error; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 *v34; // rdx
  int dwMaximumSizeLow; // [rsp+20h] [rbp-40h]
  int v36; // [rsp+30h] [rbp-30h]
  _OWORD v37[2]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned __int64 v39; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v40; // [rsp+B0h] [rbp+50h]
  int v41; // [rsp+B8h] [rbp+58h]

  v41 = a4;
  v40 = a3;
  v8 = a6;
  *(_QWORD *)a6 = 0;
  v9 = (HANDLE *)((char *)this + 416);
  v10 = -1;
  if ( *((_QWORD *)this + 52) == -1 )
  {
    FileHandle = -2147019890;
    if ( !a4 )
      return FileHandle;
    FileHandle = CFileHandleCache::GetFileHandle(v8, (const unsigned __int16 *)this + 214, (void **)this + 52);
    if ( (FileHandle & 0x80000000) != 0 )
      return FileHandle;
  }
  v12 = (RTL_SRWLOCK *)((char *)this + 72);
  if ( !*((_QWORD *)this + 9) || *((_QWORD *)this + 120) != GetFileSize(*v9, 0) )
  {
    if ( *((_QWORD *)this + 120) > (__int64)GetFileSize(*v9, 0) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    CThumbnailCacheDataFile::_CloseMapping(this);
    v27 = *(CThumbnailCacheDataFile **)wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(
                                         &v39,
                                         this);
    *(_QWORD *)&v37[0] = v27;
    BYTE8(v37[0]) = 1;
    v28 = *v9;
    FileMappingW = CreateFileMappingW(*v9, 0, 4u, 0, 0, 0);
    if ( FileMappingW )
    {
      v12->Ptr = FileMappingW;
      *((_QWORD *)this + 10) = GetFileSize(v28, 0);
    }
    else
    {
      Error = ResultFromKnownLastError();
      FileHandle = Error;
      if ( Error < 0 )
      {
        v32 = 633;
        goto LABEL_38;
      }
    }
    FileSize = GetFileSize(*v9, 0);
    *((_QWORD *)this + 120) = FileSize;
    Error = CThumbnailCacheIndex::SetDataFileSize(*((_QWORD *)this + 4), *((unsigned int *)this + 106), FileSize);
    FileHandle = Error;
    if ( Error < 0 )
    {
      v32 = 636;
    }
    else
    {
      Error = CSmartMappedView<DataFileHeader>::MapPartialViewAtOffset((char *)this + 40, (char *)this + 72);
      FileHandle = Error;
      if ( Error >= 0 )
        goto LABEL_6;
      v32 = 638;
    }
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbfile.cpp",
      (const char *)(unsigned int)Error,
      dwMaximumSizeLow);
    CThumbnailCacheDataFile::_CloseMapping(v27);
    return FileHandle;
  }
LABEL_6:
  v13 = 56;
  if ( (*(_BYTE *)(a2 + 12) & 2) != 0 )
  {
    v14 = *(_QWORD *)(a2 + 16);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
    }
    else
    {
      LODWORD(v15) = 0;
    }
    v13 = 2 * v15 + 56;
  }
  v16 = a5;
  *(_DWORD *)(a5 + 24) = 0;
  v36 = -2147467259;
  *(_QWORD *)v16 = 0;
  v17 = 0;
  LODWORD(v39) = 0;
  AcquireSRWLockShared(v12 + 42);
  v18 = 0;
  v19 = 1;
  while ( v18 < 0xA )
  {
    v20 = 4LL * v18;
    if ( v12[v20 + 3].Ptr )
    {
      Ptr = (unsigned int)v12[v20 + 4].Ptr;
      v22 = v40;
      if ( v40 >= Ptr && v13 + v40 < HIDWORD(v12[v20 + 4].Ptr) + Ptr )
      {
        v36 = 0;
        v19 = 1;
        _InterlockedAdd((volatile signed __int32 *)&v12[v20 + 2], 1u);
        *(RTL_SRWLOCK *)v16 = v12[v20 + 3];
        v17 = v22 - LODWORD(v12[v20 + 4].Ptr);
        LODWORD(v39) = v17;
        break;
      }
      v19 = 1;
    }
    ++v18;
  }
  if ( v12 != (RTL_SRWLOCK *)-336LL )
  {
    ReleaseSRWLockShared(v12 + 42);
    v19 = 1;
  }
  if ( v36 >= 0 )
    goto LABEL_20;
  memset(v37, 0, sizeof(v37));
  FileHandle = CMappingManager::_CreateView(
                 (CMappingManager *)v12,
                 0,
                 v40,
                 v13,
                 (unsigned int *)&v39,
                 (struct MAPPED_VIEW *)v37);
  if ( (FileHandle & 0x80000000) == 0 )
  {
    *(_QWORD *)v16 = *((_QWORD *)&v37[0] + 1);
    v19 = (unsigned int)CMappingManager::_CacheView((CMappingManager *)v12, (struct MAPPED_VIEW *)v37);
    v17 = v39;
LABEL_20:
    *(_DWORD *)(v16 + 24) = v19;
    *(_QWORD *)(v16 + 16) = v12;
    v23 = v17;
    FileHandle = 0;
    v24 = *(_QWORD *)v16 + v23 == 0;
    v25 = *(_QWORD *)v16 + v23;
    *(_QWORD *)(v16 + 8) = v25;
    if ( v24 || v41 && !(unsigned int)IsBufferPagedIn((const void *)v25, v13) )
    {
      return (unsigned int)-2147467259;
    }
    else
    {
      if ( *(_DWORD *)v25 != 1296911683 )
        return (unsigned int)-2147287038;
      v39 = 0;
      CThumbnailCacheDataFile::_ComputeHeaderDataChecksum(
        (CThumbnailCacheDataFile *)v19,
        (const struct DataFileEntryHeaderAligned *)v25,
        &v39);
      if ( *(_QWORD *)(v25 + 48) != v39 || *(_QWORD *)a2 != *(_QWORD *)(v25 + 8) )
        return (unsigned int)-2147287038;
      if ( (*(_BYTE *)(a2 + 12) & 2) == 0 )
        goto LABEL_52;
      v33 = *(_QWORD *)(a2 + 16);
      if ( v33 )
      {
        do
          ++v10;
        while ( *(_WORD *)(v33 + 2 * v10) );
      }
      else
      {
        LODWORD(v10) = 0;
      }
      if ( *(_DWORD *)(v25 + 16) != 2 * (_DWORD)v10 )
        return (unsigned int)-2147287038;
      v34 = &qword_1800509F8;
      if ( v33 )
        v34 = *(__int64 **)(a2 + 16);
      if ( !memcmp_0((const void *)(v25 + 56), v34, *(unsigned int *)(v25 + 16)) )
LABEL_52:
        *(_QWORD *)a6 = v25;
      else
        return (unsigned int)-2147287038;
    }
    return FileHandle;
  }
  if ( FileHandle == -2147024891 )
    return (unsigned int)-2147287038;
  return FileHandle;
}

```

## disassembly

```asm
0x180012a68  mov     [rsp-38h+arg_8], rbx
0x180012a6d  mov     [rsp-38h+arg_18], r9d
0x180012a72  mov     [rsp-38h+arg_10], r8d
0x180012a77  push    rbp
0x180012a78  push    rsi
0x180012a79  push    rdi
0x180012a7a  push    r12
0x180012a7c  push    r13
0x180012a7e  push    r14
0x180012a80  push    r15
0x180012a82  mov     rbp, rsp
0x180012a85  sub     rsp, 60h
0x180012a89  mov     eax, r9d
0x180012a8c  mov     r13, rdx
0x180012a8f  mov     rsi, rcx
0x180012a92  xor     ebx, ebx
0x180012a94  mov     rcx, [rbp+arg_28]; this
0x180012a98  mov     [rcx], rbx
0x180012a9b  lea     r15, [rsi+1A0h]
0x180012aa2  or      r12, 0FFFFFFFFFFFFFFFFh
0x180012aa6  cmp     [r15], r12
0x180012aa9  jnz     short loc_180012AD1
0x180012aab  mov     edi, 8007138Eh
0x180012ab0  test    eax, eax
0x180012ab2  jz      loc_180012C10
0x180012ab8  lea     rdx, [rsi+1ACh]; unsigned __int16 *
0x180012abf  mov     r8, r15; void **
0x180012ac2  call    ?GetFileHandle@CFileHandleCache@@QEAAJPEBGPEAPEAX@Z; CFileHandleCache::GetFileHandle(ushort const *,void * *)
0x180012ac7  mov     edi, eax
0x180012ac9  test    eax, eax
0x180012acb  js      loc_180012C10
0x180012ad1  lea     r14, [rsi+48h]
0x180012ad5  cmp     [r14], rbx
0x180012ad8  jz      loc_180012C2A
0x180012ade  xor     edx, edx; lpFileSizeHigh
0x180012ae0  mov     rcx, [r15]; hFile
0x180012ae3  call    cs:__imp_GetFileSize
0x180012ae9  mov     eax, eax
0x180012aeb  cmp     [rsi+3C0h], rax
0x180012af2  jnz     loc_180012C2A
0x180012af8  mov     r15d, 38h ; '8'
0x180012afe  test    byte ptr [r13+0Ch], 2
0x180012b03  jz      short loc_180012B26
0x180012b05  mov     rcx, [r13+10h]
0x180012b09  test    rcx, rcx
0x180012b0c  jz      loc_180012E45
0x180012b12  mov     rax, r12
0x180012b15  inc     rax
0x180012b18  cmp     [rcx+rax*2], bx
0x180012b1c  jnz     short loc_180012B15
0x180012b1e  lea     r15d, ds:38h[rax*2]
0x180012b26  mov     rsi, [rbp+arg_20]
0x180012b2a  mov     [rsi+18h], ebx
0x180012b2d  mov     [rbp+var_30], 80004005h
0x180012b34  mov     [rsi], rbx
0x180012b37  mov     edi, ebx
0x180012b39  mov     dword ptr [rbp+arg_0], ebx
0x180012b3c  lea     rbx, [r14+150h]
0x180012b43  mov     rcx, rbx; SRWLock
0x180012b46  call    cs:__imp_AcquireSRWLockShared
0x180012b4c  xor     r10d, r10d
0x180012b4f  mov     r8d, r10d
0x180012b52  lea     ecx, [r10+1]
0x180012b56  cmp     r8d, 0Ah
0x180012b5a  jnb     short loc_180012BAB
0x180012b5c  mov     edx, r8d
0x180012b5f  shl     rdx, 5
0x180012b63  cmp     [rdx+r14+18h], r10
0x180012b68  jz      loc_180012BEE
0x180012b6e  mov     ecx, [rdx+r14+20h]
0x180012b73  mov     r9d, [rbp+arg_10]
0x180012b77  cmp     r9d, ecx
0x180012b7a  jb      short loc_180012BE9
0x180012b7c  add     ecx, [rdx+r14+24h]
0x180012b81  lea     eax, [r15+r9]
0x180012b85  cmp     eax, ecx
0x180012b87  jnb     short loc_180012BE9
0x180012b89  mov     [rbp+var_30], r10d
0x180012b8d  mov     ecx, 1
0x180012b92  lock add [rdx+r14+10h], ecx
0x180012b98  mov     rax, [rdx+r14+18h]
0x180012b9d  mov     [rsi], rax
0x180012ba0  mov     edi, r9d
0x180012ba3  sub     edi, [rdx+r14+20h]
0x180012ba8  mov     dword ptr [rbp+arg_0], edi
0x180012bab  test    rbx, rbx
0x180012bae  jz      short loc_180012BC1
0x180012bb0  mov     rcx, rbx; SRWLock
0x180012bb3  call    cs:__imp_ReleaseSRWLockShared
0x180012bb9  mov     ecx, 1; this
0x180012bbe  xor     r10d, r10d
0x180012bc1  cmp     [rbp+var_30], r10d
0x180012bc5  jl      loc_180012CE9
0x180012bcb  lea     rax, [rsi+18h]
0x180012bcf  mov     [rax], ecx
0x180012bd1  mov     [rsi+10h], r14
0x180012bd5  mov     ebx, edi
0x180012bd7  xor     edi, edi
0x180012bd9  add     rbx, [rsi]
0x180012bdc  mov     [rsi+8], rbx
0x180012be0  jnz     short loc_180012BF6
0x180012be2  mov     edi, 80004005h
0x180012be7  jmp     short loc_180012C10
0x180012be9  mov     ecx, 1
0x180012bee  add     r8d, ecx
0x180012bf1  jmp     loc_180012B56
0x180012bf6  cmp     [rbp+arg_18], edi
0x180012bf9  jnz     loc_180012D7A
0x180012bff  cmp     dword ptr [rbx], 4D4D4D43h
0x180012c05  jz      loc_180012DFA
0x180012c0b  mov     edi, 80030002h
0x180012c10  mov     eax, edi
0x180012c12  mov     rbx, [rsp+60h+arg_8]
0x180012c1a  add     rsp, 60h
0x180012c1e  pop     r15
0x180012c20  pop     r14
0x180012c22  pop     r13
0x180012c24  pop     r12
0x180012c26  pop     rdi
0x180012c27  pop     rsi
0x180012c28  pop     rbp
0x180012c29  retn
0x180012c2a  xor     edx, edx; lpFileSizeHigh
0x180012c2c  mov     rcx, [r15]; hFile
0x180012c2f  call    cs:__imp_GetFileSize
0x180012c35  mov     ecx, eax
0x180012c37  cmp     [rsi+3C0h], rcx
0x180012c3e  jg      loc_180012E31
0x180012c44  mov     rcx, rsi; this
0x180012c47  call    ?_CloseMapping@CThumbnailCacheDataFile@@AEAAXXZ; CThumbnailCacheDataFile::_CloseMapping(void)
0x180012c4c  mov     rdx, rsi
0x180012c4f  lea     rcx, [rbp+arg_0]
0x180012c53  call    ??0?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@PEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(_RTL_SRWLOCK *)
0x180012c58  mov     rbx, [rax]
0x180012c5b  mov     qword ptr [rbp+var_28], rbx
0x180012c5f  mov     byte ptr [rbp+var_28+8], 1
0x180012c63  mov     rdi, [r15]
0x180012c66  xor     eax, eax
0x180012c68  mov     [rsp+60h+lpName], rax; lpName
0x180012c6d  mov     [rsp+60h+dwMaximumSizeLow], eax; int
0x180012c71  xor     r9d, r9d; dwMaximumSizeHigh
0x180012c74  xor     edx, edx; lpFileMappingAttributes
0x180012c76  lea     r8d, [rax+4]; flProtect
0x180012c7a  mov     rcx, rdi; hFile
0x180012c7d  call    cs:__imp_CreateFileMappingW
0x180012c83  test    rax, rax
0x180012c86  jz      loc_180012E1D
0x180012c8c  mov     [r14], rax
0x180012c8f  xor     edx, edx; lpFileSizeHigh
0x180012c91  mov     rcx, rdi; hFile
0x180012c94  call    cs:__imp_GetFileSize
0x180012c9a  mov     eax, eax
0x180012c9c  mov     [r14+8], rax
0x180012ca0  xor     edx, edx; lpFileSizeHigh
0x180012ca2  mov     rcx, [r15]; hFile
0x180012ca5  call    cs:__imp_GetFileSize
0x180012cab  mov     eax, eax
0x180012cad  mov     [rsi+3C0h], rax
0x180012cb4  mov     r8d, eax
0x180012cb7  mov     edx, [rsi+1A8h]
0x180012cbd  mov     rcx, [rsi+20h]
0x180012cc1  call    ?SetDataFileSize@CThumbnailCacheIndex@@QEAAJW4THUMBSIZE@@K@Z; CThumbnailCacheIndex::SetDataFileSize(THUMBSIZE,ulong)
0x180012cc6  mov     edi, eax
0x180012cc8  test    eax, eax
0x180012cca  js      short loc_180012D3A
0x180012ccc  lea     rcx, [rsi+28h]
0x180012cd0  mov     rdx, r14
0x180012cd3  call    ?MapPartialViewAtOffset@?$CSmartMappedView@UDataFileHeader@@@@QEAAJPEAVCMappingManager@@HKK@Z; CSmartMappedView<DataFileHeader>::MapPartialViewAtOffset(CMappingManager *,int,ulong,ulong)
0x180012cd8  mov     edi, eax
0x180012cda  test    eax, eax
0x180012cdc  js      loc_180012E3B
0x180012ce2  xor     ebx, ebx
0x180012ce4  jmp     loc_180012AF8
0x180012ce9  xorps   xmm0, xmm0
0x180012cec  movups  [rbp+var_28], xmm0
0x180012cf0  movups  [rbp+var_18], xmm0
0x180012cf4  lea     rax, [rbp+var_28]
0x180012cf8  mov     [rsp+60h+lpName], rax; struct MAPPED_VIEW *
0x180012cfd  lea     rax, [rbp+arg_0]
0x180012d01  mov     qword ptr [rsp+60h+dwMaximumSizeLow], rax; unsigned int *
0x180012d06  mov     r9d, r15d; unsigned int
0x180012d09  mov     r8d, [rbp+arg_10]; unsigned int
0x180012d0d  xor     edx, edx; int
0x180012d0f  mov     rcx, r14; this
0x180012d12  call    ?_CreateView@CMappingManager@@AEAAJHKKPEAKPEAUMAPPED_VIEW@@@Z; CMappingManager::_CreateView(int,ulong,ulong,ulong *,MAPPED_VIEW *)
0x180012d17  mov     edi, eax
0x180012d19  test    eax, eax
0x180012d1b  js      short loc_180012D67
0x180012d1d  mov     rax, qword ptr [rbp+var_28+8]
0x180012d21  mov     [rsi], rax
0x180012d24  lea     rdx, [rbp+var_28]; struct MAPPED_VIEW *
0x180012d28  mov     rcx, r14; this
0x180012d2b  call    ?_CacheView@CMappingManager@@AEAAHPEAUMAPPED_VIEW@@@Z; CMappingManager::_CacheView(MAPPED_VIEW *)
0x180012d30  mov     ecx, eax
0x180012d32  mov     edi, dword ptr [rbp+arg_0]
0x180012d35  jmp     loc_180012BCB
0x180012d3a  mov     edx, 27Ch
0x180012d3f  jmp     short loc_180012D46
0x180012d41  mov     edx, 279h; void *
0x180012d46  mov     rcx, [rbp+38h]; this
0x180012d4a  mov     r9d, eax; char *
0x180012d4d  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180012d54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d59  nop
0x180012d5a  mov     rcx, rbx; this
0x180012d5d  call    ?_CloseMapping@CThumbnailCacheDataFile@@AEAAXXZ; CThumbnailCacheDataFile::_CloseMapping(void)
0x180012d62  jmp     loc_180012C10
0x180012d67  mov     eax, 80030002h
0x180012d6c  cmp     edi, 80070005h
0x180012d72  cmovz   edi, eax
0x180012d75  jmp     loc_180012C10
0x180012d7a  mov     edx, r15d; unsigned int
0x180012d7d  mov     rcx, rbx; void *
0x180012d80  call    ?IsBufferPagedIn@@YAHPEBXI@Z; IsBufferPagedIn(void const *,uint)
0x180012d85  test    eax, eax
0x180012d87  jnz     loc_180012BFF
0x180012d8d  jmp     loc_180012BE2
0x180012d92  mov     rax, [rbx+8]
0x180012d96  cmp     [r13+0], rax
0x180012d9a  jnz     loc_180012C0B
0x180012da0  test    byte ptr [r13+0Ch], 2
0x180012da5  jz      short loc_180012DEE
0x180012da7  mov     rcx, [r13+10h]
0x180012dab  test    rcx, rcx
0x180012dae  jz      loc_180012E4C
0x180012db4  inc     r12
0x180012db7  cmp     [rcx+r12*2], di
0x180012dbc  jnz     short loc_180012DB4
0x180012dbe  lea     eax, [r12+r12]
0x180012dc2  cmp     [rbx+10h], eax
0x180012dc5  jnz     loc_180012C0B
0x180012dcb  lea     rdx, qword_1800509F8
0x180012dd2  test    rcx, rcx
0x180012dd5  cmovnz  rdx, rcx; Buf2
0x180012dd9  mov     r8d, [rbx+10h]; Size
0x180012ddd  lea     rcx, [rbx+38h]; Buf1
0x180012de1  call    memcmp_0
0x180012de6  test    eax, eax
0x180012de8  jnz     loc_180012C0B
0x180012dee  mov     rax, [rbp+arg_28]
0x180012df2  mov     [rax], rbx
0x180012df5  jmp     loc_180012C10
0x180012dfa  mov     [rbp+arg_0], rdi
0x180012dfe  lea     r8, [rbp+arg_0]; unsigned __int64 *
0x180012e02  mov     rdx, rbx; struct DataFileEntryHeaderAligned *
0x180012e05  call    ?_ComputeHeaderDataChecksum@CThumbnailCacheDataFile@@AEAAXPEFBUDataFileEntryHeaderAligned@@PEA_K@Z; CThumbnailCacheDataFile::_ComputeHeaderDataChecksum(DataFileEntryHeaderAligned const *,unsigned __int64 *)
0x180012e0a  mov     r8, [rbp+arg_0]
0x180012e0e  cmp     [rbx+30h], r8
0x180012e12  jnz     loc_180012C0B
0x180012e18  jmp     loc_180012D92
0x180012e1d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180012e22  mov     edi, eax
0x180012e24  test    eax, eax
0x180012e26  jns     loc_180012CA0
0x180012e2c  jmp     loc_180012D41
0x180012e31  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "_cbLastKnownFileSize <= _GetFileSize()")
0x180012e36  jmp     loc_180012C44
0x180012e3b  mov     edx, 27Eh
0x180012e40  jmp     loc_180012D46
0x180012e45  mov     eax, ebx
0x180012e47  jmp     loc_180012B1E
0x180012e4c  mov     r12d, edi
0x180012e4f  jmp     loc_180012DBE
```
