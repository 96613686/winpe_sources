# CThumbnailCacheIndex::CheckRecreateFileMapping(int)

- ea: `0x18000e6a0`
- end: `0x18000ec57`
- name: `?CheckRecreateFileMapping@CThumbnailCacheIndex@@QEAAJH@Z`
- size: `1463`
- prototype: `__int64 __fastcall(CThumbnailCacheIndex *__hidden this, int)`
- caller_count: `8`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d498`
- `0x18000f878`
- `0x180010e00`
- `0x18002556c`
- `0x180025a00`
- `0x180028d00`
- `0x180034a74`
- `0x180045b5c`

## callees

- `0x18000bfd8`
- `0x18000e280`
- `0x18000e6a0`
- `0x18000ec60`
- `0x18000ed30`
- `0x18000ed88`
- `0x18000edf0`
- `0x18000f1fc`
- `0x180010ea4`
- `0x180011094`
- `0x18001264c`
- `0x180023e68`
- `0x180027890`
- `0x180027a2c`
- `0x1800328c4`
- `0x180033870`
- `0x180034bb0`
- `0x180035830`
- `0x180045af0`
- `0x180045c88`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000e6ed`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000e6ed`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000ebe6`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000ebe6`

## string_xrefs

- `0x18000e708`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbidx.cpp`
- `0x18000e933`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbidx.cpp`
- `0x18000ea4c`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbidx.cpp`
- `0x18000ea8f`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbidx.cpp`
- `0x18000eb16`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbidx.cpp`
- `0x18000eb74`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbidx.cpp`
- `0x18000eaf3`: `onecoreuap\shell\ext\thumbnailcache\common\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThumbnailCacheIndex::CheckRecreateFileMapping(CThumbnailCacheIndex *this, int a2)
{
  void **v4; // rdi
  void *v5; // rcx
  DWORD FileSize; // eax
  __int64 v7; // r15
  LPCVOID *v9; // rsi
  unsigned __int64 v10; // rax
  char *v11; // r12
  char v12; // cl
  char v13; // al
  _QWORD *v14; // r13
  __int64 v15; // rcx
  _DWORD *v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  int DataFile; // eax
  CFileHandleCache *v20; // rcx
  unsigned int v21; // r15d
  int IndexFileSize; // eax
  unsigned int v23; // ebx
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  char v27; // [rsp+40h] [rbp-C0h]
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  void **v29; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v30[272]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v31[8]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v32[24]; // [rsp+170h] [rbp+70h] BYREF
  int v33; // [rsp+188h] [rbp+88h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  ThumbnailCacheTelemetry::CheckRecreateFileMapping::Start<>((ThumbnailCacheTelemetry::CheckRecreateFileMapping *)&v29);
  v4 = (void **)((char *)this + 80);
  v5 = (void *)*((_QWORD *)this + 10);
  if ( v5 == (void *)-1LL || (FileSize = GetFileSize(v5, 0), v7 = FileSize, FileSize == -1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x168,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbidx.cpp",
      (const char *)0x80004005LL,
      v24);
    v29 = &ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable';
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v29);
    if ( v33 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v32);
    wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v31);
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v30);
    return 2147500037LL;
  }
  LODWORD(hObject) = FileSize;
  v9 = (LPCVOID *)((char *)this + 72);
  v10 = *((_QWORD *)this + 9);
  if ( v10 && (v11 = (char *)this + 88, *((_QWORD *)this + 11) == v7) )
  {
    v27 = 0;
  }
  else
  {
    v12 = 1;
    v27 = 1;
    v11 = (char *)this + 88;
    if ( !v10 )
      goto LABEL_12;
  }
  if ( a2 && !(unsigned int)IsBufferPagedIn(v10, 0x90u) )
  {
    v12 = v27;
    goto LABEL_12;
  }
  v12 = v27;
  if ( !*((_DWORD *)*v9 + 3) )
  {
LABEL_12:
    v13 = 0;
    v14 = v11;
    goto LABEL_13;
  }
  v13 = 1;
  v14 = (_QWORD *)((char *)this + 88);
LABEL_13:
  if ( v12 )
  {
    if ( !v13 )
    {
      if ( *v9 )
      {
        UnmapViewOfFile(*v9);
        *v9 = 0;
      }
      goto LABEL_27;
    }
  }
  else if ( !v13 )
  {
LABEL_15:
    *v14 = (unsigned int)v7;
    if ( !a2 || (unsigned int)IsBufferPagedIn((unsigned __int64)*v9, 0x90u) )
    {
      v15 = 72 * (*((unsigned int *)*v9 + 6) + 2LL);
      hObject = (HANDLE)v15;
      v16 = *v9;
      if ( *((_DWORD *)*v9 + 1) == 1296911689 && v16[2] == 32 && *v14 == v15 && v16[5] < v16[6] )
      {
        if ( *((_DWORD *)*v9 + 3) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x195,
            (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbidx.cpp",
            (const char *)0x8004B204LL,
            v24);
          v29 = &ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable';
          wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v29);
          if ( v33 )
            wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v32);
          wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v31);
          wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v30);
          return 2147791364LL;
        }
        else
        {
          wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)&v29, 0);
          v29 = &ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable';
          wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v29);
          if ( v33 )
            wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v32);
          wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v31);
          wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v30);
          return 0;
        }
      }
      else
      {
        ThumbnailCacheTelemetry::CheckRecreateFileMapping::InvalidIndex<unsigned long &,unsigned long &,__int64 &,__int64 &,unsigned int volatile &,unsigned int volatile &>(
          (unsigned int)&v29,
          *(_DWORD *)v9 + 4,
          *(_DWORD *)v9 + 8,
          (_DWORD)v14,
          (__int64)&hObject,
          (__int64)*v9 + 20,
          (__int64)*v9 + 24);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19A,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbidx.cpp",
          (const char *)0x80041221LL,
          v25);
        v29 = &ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable';
        wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v29);
        if ( v33 )
          wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v32);
        wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v31);
        wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v30);
        return 2147750433LL;
      }
    }
    else
    {
      v29 = &ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable';
      wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v29);
      if ( v33 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v32);
      wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v31);
      wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v30);
      return 2147500035LL;
    }
  }
  CThumbnailCacheIndex::_CloseFileAndMapping(this);
  DataFile = OpenOrCreateDataFile((PCWSTR)this + 50, 1, (_QWORD *)this + 10);
  v21 = DataFile;
  if ( DataFile < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\util.cpp",
      (const char *)(unsigned int)DataFile,
      v24);
    CThumbnailCacheIndex::_CloseFileAndMapping(this);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x176,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbidx.cpp",
      (const char *)v21,
      v26);
    v29 = &ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable';
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v29);
    if ( v33 )
      wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v32);
    wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v31);
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v30);
    return v21;
  }
  CFileHandleCache::SetFileHandle(v20, (const unsigned __int16 *)this + 50, *v4);
  IndexFileSize = CThumbnailCacheIndex::GetIndexFileSize(this, (unsigned int *)&hObject);
  v23 = IndexFileSize;
  if ( IndexFileSize < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x179,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbidx.cpp",
      (const char *)(unsigned int)IndexFileSize,
      v24);
    v29 = &ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable';
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v29);
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v29);
    return v23;
  }
  LODWORD(v7) = (_DWORD)hObject;
LABEL_27:
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(&hObject);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(hObject);
  hObject = (HANDLE)-1LL;
  v17 = MapViewOfEntireFile(*v4, (void **)v9, &hObject);
  v18 = v17;
  if ( v17 >= 0 )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    v14 = v11;
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x183,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbidx.cpp",
    (const char *)(unsigned int)v17,
    v24);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
  v29 = &ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable';
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v29);
  if ( v33 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v32);
  wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v31);
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v30);
  return v18;
}

```

## disassembly

```asm
0x18000e6a0  push    rbp
0x18000e6a2  push    rbx
0x18000e6a3  push    rsi
0x18000e6a4  push    rdi
0x18000e6a5  push    r12
0x18000e6a7  push    r13
0x18000e6a9  push    r14
0x18000e6ab  push    r15
0x18000e6ad  lea     rbp, [rsp-0B8h]
0x18000e6b5  sub     rsp, 1B8h
0x18000e6bc  mov     rax, cs:__security_cookie
0x18000e6c3  xor     rax, rsp
0x18000e6c6  mov     [rbp+0F0h+var_50], rax
0x18000e6cd  mov     r14d, edx
0x18000e6d0  mov     rbx, rcx
0x18000e6d3  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18000e6d8  call    ??$Start@$$V@CheckRecreateFileMapping@ThumbnailCacheTelemetry@@SA?AV01@XZ; ThumbnailCacheTelemetry::CheckRecreateFileMapping::Start<>(void)
0x18000e6dd  nop
0x18000e6de  lea     rdi, [rbx+50h]
0x18000e6e2  mov     rcx, [rdi]; hFile
0x18000e6e5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e6e9  jz      short loc_18000E6FB
0x18000e6eb  xor     edx, edx; lpFileSizeHigh
0x18000e6ed  call    cs:__imp_GetFileSize
0x18000e6f3  mov     r15d, eax
0x18000e6f6  cmp     eax, 0FFFFFFFFh
0x18000e6f9  jnz     short loc_18000E75B
0x18000e6fb  mov     rcx, [rbp+0F8h]; this
0x18000e702  mov     r9d, 80004005h; char *
0x18000e708  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000e70f  mov     edx, 168h; void *
0x18000e714  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e719  nop
0x18000e71a  lea     rax, ??_7CheckRecreateFileMapping@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable'
0x18000e721  mov     [rsp+1F0h+var_1A0], rax
0x18000e726  lea     rcx, [rsp+1F0h+var_1A0]
0x18000e72b  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000e730  nop
0x18000e731  cmp     [rbp+0F0h+var_68], 0
0x18000e738  jnz     loc_18000EC48
0x18000e73e  lea     rcx, [rbp+0F0h+var_88]
0x18000e742  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000e747  lea     rcx, [rsp+1F0h+var_198]
0x18000e74c  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e751  mov     eax, 80004005h
0x18000e756  jmp     loc_18000E869
0x18000e75b  mov     dword ptr [rsp+1F0h+hObject], r15d
0x18000e760  lea     rsi, [rbx+48h]
0x18000e764  mov     rax, [rsi]
0x18000e767  test    rax, rax
0x18000e76a  jz      short loc_18000E77E
0x18000e76c  lea     r12, [rbx+58h]
0x18000e770  cmp     [r12], r15
0x18000e774  jnz     short loc_18000E77E
0x18000e776  xor     cl, cl
0x18000e778  mov     [rsp+1F0h+var_1B0], cl
0x18000e77c  jmp     short loc_18000E78D
0x18000e77e  mov     cl, 1
0x18000e780  mov     [rsp+1F0h+var_1B0], cl
0x18000e784  lea     r12, [rbx+58h]
0x18000e788  test    rax, rax
0x18000e78b  jz      short loc_18000E7A8
0x18000e78d  test    r14d, r14d
0x18000e790  jnz     loc_18000E9DC
0x18000e796  mov     rax, [rsi]
0x18000e799  movzx   ecx, [rsp+1F0h+var_1B0]
0x18000e79e  cmp     dword ptr [rax+0Ch], 0
0x18000e7a2  jnz     loc_18000EBC3
0x18000e7a8  xor     al, al
0x18000e7aa  mov     r13, r12
0x18000e7ad  test    cl, cl
0x18000e7af  jnz     loc_18000E88C
0x18000e7b5  test    al, al
0x18000e7b7  jnz     loc_18000E9FB
0x18000e7bd  mov     eax, r15d
0x18000e7c0  mov     [r13+0], rax
0x18000e7c4  test    r14d, r14d
0x18000e7c7  jnz     loc_18000E986
0x18000e7cd  mov     rax, [rsi]
0x18000e7d0  mov     eax, [rax+18h]
0x18000e7d3  add     rax, 2
0x18000e7d7  lea     rcx, [rax+rax*8]
0x18000e7db  shl     rcx, 3
0x18000e7df  mov     [rsp+1F0h+hObject], rcx
0x18000e7e4  mov     rax, [rsi]
0x18000e7e7  cmp     dword ptr [rax+4], 4D4D4D49h
0x18000e7ee  jnz     loc_18000E8F2
0x18000e7f4  cmp     dword ptr [rax+8], 20h ; ' '
0x18000e7f8  jnz     loc_18000E8F2
0x18000e7fe  cmp     [r13+0], rcx
0x18000e802  jnz     loc_18000E8F2
0x18000e808  mov     ecx, [rax+18h]
0x18000e80b  mov     eax, [rax+14h]
0x18000e80e  cmp     eax, ecx
0x18000e810  jnb     loc_18000E8F2
0x18000e816  mov     rax, [rsi]
0x18000e819  cmp     dword ptr [rax+0Ch], 0
0x18000e81d  jnz     loc_18000EB67
0x18000e823  xor     edx, edx
0x18000e825  lea     rcx, [rsp+1F0h+var_1A0]
0x18000e82a  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000e82f  nop
0x18000e830  lea     rax, ??_7CheckRecreateFileMapping@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable'
0x18000e837  mov     [rsp+1F0h+var_1A0], rax
0x18000e83c  lea     rcx, [rsp+1F0h+var_1A0]
0x18000e841  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000e846  nop
0x18000e847  cmp     [rbp+0F0h+var_68], 0
0x18000e84e  jnz     loc_18000EC2C
0x18000e854  lea     rcx, [rbp+0F0h+var_88]
0x18000e858  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000e85d  lea     rcx, [rsp+1F0h+var_198]
0x18000e862  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e867  xor     eax, eax
0x18000e869  mov     rcx, [rbp+0F0h+var_50]
0x18000e870  xor     rcx, rsp; StackCookie
0x18000e873  call    __security_check_cookie
0x18000e878  add     rsp, 1B8h
0x18000e87f  pop     r15
0x18000e881  pop     r14
0x18000e883  pop     r13
0x18000e885  pop     r12
0x18000e887  pop     rdi
0x18000e888  pop     rsi
0x18000e889  pop     rbx
0x18000e88a  pop     rbp
0x18000e88b  retn
0x18000e88c  test    al, al
0x18000e88e  jnz     loc_18000E9FB
0x18000e894  mov     rcx, [rsi]; lpBaseAddress
0x18000e897  test    rcx, rcx
0x18000e89a  jnz     loc_18000EBE6
0x18000e8a0  lea     rcx, [rsp+1F0h+hObject]
0x18000e8a5  call    ??0?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x18000e8aa  mov     rcx, [rsp+1F0h+hObject]; hObject
0x18000e8af  lea     rax, [rcx-1]
0x18000e8b3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e8b7  jbe     loc_18000EBF8
0x18000e8bd  mov     [rsp+1F0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18000e8c6  lea     r8, [rsp+1F0h+hObject]; void **
0x18000e8cb  mov     rdx, rsi; void **
0x18000e8ce  mov     rcx, [rdi]; void *
0x18000e8d1  call    ?MapViewOfEntireFile@@YAJPEAXPEAPEAX1@Z; MapViewOfEntireFile(void *,void * *,void * *)
0x18000e8d6  mov     ebx, eax
0x18000e8d8  test    eax, eax
0x18000e8da  js      loc_18000EA85
0x18000e8e0  lea     rcx, [rsp+1F0h+hObject]
0x18000e8e5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000e8ea  mov     r13, r12
0x18000e8ed  jmp     loc_18000E7BD
0x18000e8f2  mov     rdx, [rsi]
0x18000e8f5  lea     rax, [rdx+18h]
0x18000e8f9  lea     rcx, [rdx+14h]
0x18000e8fd  lea     r8, [rdx+8]
0x18000e901  add     rdx, 4
0x18000e905  mov     [rsp+1F0h+var_1C0], rax
0x18000e90a  mov     [rsp+1F0h+var_1C8], rcx
0x18000e90f  lea     rax, [rsp+1F0h+hObject]
0x18000e914  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x18000e919  mov     r9, r13
0x18000e91c  lea     rcx, [rsp+1F0h+var_1A0]
0x18000e921  call    ??$InvalidIndex@AEAKAEAKAEA_JAEA_JAECIAECI@CheckRecreateFileMapping@ThumbnailCacheTelemetry@@QEAAXAEAK0AEA_J1AECI2@Z; ThumbnailCacheTelemetry::CheckRecreateFileMapping::InvalidIndex<ulong &,ulong &,__int64 &,__int64 &,uint volatile &,uint volatile &>(ulong &,ulong &,__int64 &,__int64 &,uint volatile &,uint volatile &)
0x18000e926  mov     rcx, [rbp+0F8h]; this
0x18000e92d  mov     r9d, 80041221h; char *
0x18000e933  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000e93a  mov     edx, 19Ah; void *
0x18000e93f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e944  nop
0x18000e945  lea     rax, ??_7CheckRecreateFileMapping@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable'
0x18000e94c  mov     [rsp+1F0h+var_1A0], rax
0x18000e951  lea     rcx, [rsp+1F0h+var_1A0]
0x18000e956  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000e95b  nop
0x18000e95c  cmp     [rbp+0F0h+var_68], 0
0x18000e963  jnz     loc_18000EC3A
0x18000e969  lea     rcx, [rbp+0F0h+var_88]
0x18000e96d  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000e972  lea     rcx, [rsp+1F0h+var_198]
0x18000e977  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e97c  mov     eax, 80041221h
0x18000e981  jmp     loc_18000E869
0x18000e986  mov     edx, 90h; unsigned int
0x18000e98b  mov     rcx, [rsi]; void *
0x18000e98e  call    ?IsBufferPagedIn@@YAHPEBXI@Z; IsBufferPagedIn(void const *,uint)
0x18000e993  test    eax, eax
0x18000e995  jnz     loc_18000E7CD
0x18000e99b  lea     rax, ??_7CheckRecreateFileMapping@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable'
0x18000e9a2  mov     [rsp+1F0h+var_1A0], rax
0x18000e9a7  lea     rcx, [rsp+1F0h+var_1A0]
0x18000e9ac  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000e9b1  nop
0x18000e9b2  cmp     [rbp+0F0h+var_68], 0
0x18000e9b9  jnz     loc_18000EC10
0x18000e9bf  lea     rcx, [rbp+0F0h+var_88]
0x18000e9c3  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000e9c8  lea     rcx, [rsp+1F0h+var_198]
0x18000e9cd  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e9d2  mov     eax, 80004003h
0x18000e9d7  jmp     loc_18000E869
0x18000e9dc  mov     edx, 90h; unsigned int
0x18000e9e1  mov     rcx, rax; void *
0x18000e9e4  call    ?IsBufferPagedIn@@YAHPEBXI@Z; IsBufferPagedIn(void const *,uint)
0x18000e9e9  test    eax, eax
0x18000e9eb  jnz     loc_18000E796
0x18000e9f1  movzx   ecx, [rsp+1F0h+var_1B0]
0x18000e9f6  jmp     loc_18000E7A8
0x18000e9fb  mov     rcx, rbx; this
0x18000e9fe  call    ?_CloseFileAndMapping@CThumbnailCacheIndex@@AEAAXXZ; CThumbnailCacheIndex::_CloseFileAndMapping(void)
0x18000ea03  mov     r8, rdi
0x18000ea06  mov     edx, 1
0x18000ea0b  lea     rcx, [rbx+64h]; pszPath
0x18000ea0f  call    _OpenOrCreateDataFile
0x18000ea14  mov     r15d, eax
0x18000ea17  test    eax, eax
0x18000ea19  js      loc_18000EAE9
0x18000ea1f  mov     r8, [rdi]; void *
0x18000ea22  lea     rdx, [rbx+64h]; unsigned __int16 *
0x18000ea26  call    ?SetFileHandle@CFileHandleCache@@QEAAJPEBGPEAX@Z; CFileHandleCache::SetFileHandle(ushort const *,void *)
0x18000ea2b  lea     rdx, [rsp+1F0h+hObject]; unsigned int *
0x18000ea30  mov     rcx, rbx; this
0x18000ea33  call    ?GetIndexFileSize@CThumbnailCacheIndex@@QEAAJPEAK@Z; CThumbnailCacheIndex::GetIndexFileSize(ulong *)
0x18000ea38  mov     ebx, eax
0x18000ea3a  test    eax, eax
0x18000ea3c  jns     loc_18000EBDC
0x18000ea42  mov     rcx, [rbp+0F8h]; this
0x18000ea49  mov     r9d, eax; char *
0x18000ea4c  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000ea53  mov     edx, 179h; void *
0x18000ea58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea5d  nop
0x18000ea5e  lea     rax, ??_7CheckRecreateFileMapping@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable'
0x18000ea65  mov     [rsp+1F0h+var_1A0], rax
0x18000ea6a  lea     rcx, [rsp+1F0h+var_1A0]
0x18000ea6f  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000ea74  lea     rcx, [rsp+1F0h+var_1A0]
0x18000ea79  call    ??1?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000ea7e  mov     eax, ebx
0x18000ea80  jmp     loc_18000E869
0x18000ea85  mov     rcx, [rbp+0F8h]; this
0x18000ea8c  mov     r9d, ebx; char *
0x18000ea8f  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000ea96  mov     edx, 183h; void *
0x18000ea9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eaa0  lea     rcx, [rsp+1F0h+hObject]
0x18000eaa5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000eaaa  nop
0x18000eaab  lea     rax, ??_7CheckRecreateFileMapping@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable'
0x18000eab2  mov     [rsp+1F0h+var_1A0], rax
0x18000eab7  lea     rcx, [rsp+1F0h+var_1A0]
0x18000eabc  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000eac1  nop
0x18000eac2  cmp     [rbp+0F0h+var_68], 0
0x18000eac9  jnz     loc_18000EC02
0x18000eacf  lea     rcx, [rbp+0F0h+var_88]
0x18000ead3  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000ead8  lea     rcx, [rsp+1F0h+var_198]
0x18000eadd  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000eae2  mov     eax, ebx
0x18000eae4  jmp     loc_18000E869
0x18000eae9  mov     rcx, [rbp+0F8h]; this
0x18000eaf0  mov     r9d, r15d; char *
0x18000eaf3  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000eafa  mov     edx, 0ABh; void *
0x18000eaff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb04  mov     rcx, rbx; this
0x18000eb07  call    ?_CloseFileAndMapping@CThumbnailCacheIndex@@AEAAXXZ; CThumbnailCacheIndex::_CloseFileAndMapping(void)
0x18000eb0c  mov     rcx, [rbp+0F8h]; this
0x18000eb13  mov     r9d, r15d; char *
0x18000eb16  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000eb1d  mov     edx, 176h; void *
0x18000eb22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb27  nop
0x18000eb28  lea     rax, ??_7CheckRecreateFileMapping@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable'
0x18000eb2f  mov     [rsp+1F0h+var_1A0], rax
0x18000eb34  lea     rcx, [rsp+1F0h+var_1A0]
0x18000eb39  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000eb3e  nop
0x18000eb3f  cmp     [rbp+0F0h+var_68], 0
0x18000eb46  jnz     loc_18000EBCE
0x18000eb4c  lea     rcx, [rbp+0F0h+var_88]
0x18000eb50  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000eb55  lea     rcx, [rsp+1F0h+var_198]
0x18000eb5a  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000eb5f  mov     eax, r15d
0x18000eb62  jmp     loc_18000E869
0x18000eb67  mov     rcx, [rbp+0F8h]; this
0x18000eb6e  mov     r9d, 8004B204h; char *
0x18000eb74  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000eb7b  mov     edx, 195h; void *
0x18000eb80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb85  nop
0x18000eb86  lea     rax, ??_7CheckRecreateFileMapping@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::CheckRecreateFileMapping::`vftable'
0x18000eb8d  mov     [rsp+1F0h+var_1A0], rax
0x18000eb92  lea     rcx, [rsp+1F0h+var_1A0]
0x18000eb97  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000eb9c  nop
0x18000eb9d  cmp     [rbp+0F0h+var_68], 0
0x18000eba4  jnz     short loc_18000EC1E
0x18000eba6  lea     rcx, [rbp+0F0h+var_88]
0x18000ebaa  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
  ... truncated ...
```
