# CThumbnailCache::_ResetCacheFiles(RESETTHUMBNAILCACHEFILES_RECREATEFLAG)

- ea: `0x180028518`
- end: `0x180028715`
- name: `?_ResetCacheFiles@CThumbnailCache@@AEAAJW4RESETTHUMBNAILCACHEFILES_RECREATEFLAG@@@Z`
- size: `509`
- prototype: `int __high(enum RESETTHUMBNAILCACHEFILES_RECREATEFLAG)`
- caller_count: `5`
- callee_count: `18`
- tags: `file_ops, registry_config`

## callers

- `0x18000bffc`
- `0x1800152b0`
- `0x180015868`
- `0x180041270`
- `0x180041360`

## callees

- `0x18000bfd8`
- `0x18000e280`
- `0x18000e4b0`
- `0x18000ed30`
- `0x18000ed88`
- `0x18000edf0`
- `0x18000f234`
- `0x1800112c8`
- `0x18001264c`
- `0x180028518`
- `0x18002871c`
- `0x1800287c4`
- `0x180028a34`
- `0x180028b90`
- `0x180028c8c`
- `0x180033f48`
- `0x180034168`
- `0x180035830`

## import_xrefs

- `SHCORE!__imp_SHCreateDirectoryExW` at `0x18002859e`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x18002859e`

## string_xrefs

- `0x1800285d6`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x1800286dd`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x1800286c2`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbfile.cpp`
- `0x180028550`: `ResetCacheFiles`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThumbnailCache::_ResetCacheFiles(__int64 a1, unsigned int a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int FileW; // eax
  int i; // ebx
  __int64 v12; // rdi
  __int64 v13; // rax
  CFileHandleCache *v14; // rcx
  unsigned int v15; // r14d
  int v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  void **v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[272]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v19[8]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v20[48]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  *(_BYTE *)(a1 + 758) = 1;
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v17,
    "ResetCacheFiles");
  v17 = &ThumbnailCacheTelemetry::ResetCacheFiles::`vftable';
  ThumbnailCacheTelemetry::ResetCacheFiles::StartActivity((ThumbnailCacheTelemetry::ResetCacheFiles *)&v17, a2);
  v4 = CThumbnailCache::_MoveCachesFileToTempDirectoryAndDelete((CThumbnailCacheIndex **)a1);
  v5 = v4;
  if ( v4 < 0 )
  {
    v7 = (unsigned int)v4;
    v8 = 1753;
    goto LABEL_9;
  }
  if ( a2 != 1 )
    goto LABEL_19;
  v6 = SHCreateDirectoryExW(0, (LPCWSTR)(a1 + 72), 0);
  v5 = v6;
  if ( v6 > 0 )
    v5 = (unsigned __int16)v6 | 0x80070000;
  if ( (v5 & 0x80000000) == 0 || v5 == -2147024713 || v5 == -2147024816 )
  {
    FileW = CThumbnailCacheIndex::CreateFileW(*(CThumbnailCacheIndex **)(a1 + 48));
    v5 = FileW;
    if ( FileW < 0 )
    {
      v7 = (unsigned int)FileW;
      v8 = 1765;
      goto LABEL_9;
    }
    for ( i = 0; i < 14; ++i )
    {
      v12 = *(_QWORD *)ATL::CSimpleArray<CThumbnailCacheDataFile *,ATL::CSimpleArrayEqualHelper<CThumbnailCacheDataFile *>>::operator[](
                         a1 + 56,
                         (unsigned int)i);
      CThumbnailCacheDataFile::_CloseFileAndMapping((CThumbnailCacheDataFile *)v12);
      v13 = wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(
              v16,
              v12);
      v15 = lambda_a3819191aa42c9b12893e59208468e90_::operator()(v13);
      if ( (v15 & 0x80000000) != 0 )
      {
        CThumbnailCacheDataFile::_CloseFileAndMapping((CThumbnailCacheDataFile *)v12);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x228,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbfile.cpp",
          (const char *)v15,
          v16[0]);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6E9,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
          (const char *)v15,
          v16[0]);
        ThumbnailCacheTelemetry::ResetCacheFiles::~ResetCacheFiles((ThumbnailCacheTelemetry::ResetCacheFiles *)&v17);
        return v15;
      }
      CFileHandleCache::SetFileHandle(v14, (const unsigned __int16 *)(v12 + 428), *(void **)(v12 + 416));
    }
LABEL_19:
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)&v17, 0);
    v5 = 0;
    goto LABEL_10;
  }
  v7 = v5;
  v8 = 1763;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
    (const char *)v7,
    v16[0]);
LABEL_10:
  v17 = &ThumbnailCacheTelemetry::ResetCacheFiles::`vftable';
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v17);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v20);
  wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v19);
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v18);
  return v5;
}

```

## disassembly

```asm
0x180028518  mov     [rsp-8+arg_10], rbx
0x18002851d  push    rbp
0x18002851e  push    rsi
0x18002851f  push    rdi
0x180028520  push    r14
0x180028522  push    r15
0x180028524  lea     rbp, [rsp-90h]
0x18002852c  sub     rsp, 190h
0x180028533  mov     rax, cs:__security_cookie
0x18002853a  xor     rax, rsp
0x18002853d  mov     [rbp+0B0h+var_30], rax
0x180028544  mov     edi, edx
0x180028546  mov     rsi, rcx
0x180028549  mov     byte ptr [rcx+2F6h], 1
0x180028550  lea     rdx, aResetcachefile_2; "ResetCacheFiles"
0x180028557  lea     rcx, [rsp+1B0h+var_180]
0x18002855c  call    ??0?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180028561  lea     r15, ??_7ResetCacheFiles@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::ResetCacheFiles::`vftable'
0x180028568  mov     [rsp+1B0h+var_180], r15
0x18002856d  mov     edx, edi; unsigned int
0x18002856f  lea     rcx, [rsp+1B0h+var_180]; this
0x180028574  call    ?StartActivity@ResetCacheFiles@ThumbnailCacheTelemetry@@QEAAXK@Z; ThumbnailCacheTelemetry::ResetCacheFiles::StartActivity(ulong)
0x180028579  nop
0x18002857a  mov     rcx, rsi; this
0x18002857d  call    ?_MoveCachesFileToTempDirectoryAndDelete@CThumbnailCache@@AEAAJXZ; CThumbnailCache::_MoveCachesFileToTempDirectoryAndDelete(void)
0x180028582  mov     ebx, eax
0x180028584  test    eax, eax
0x180028586  js      loc_18002864F
0x18002858c  cmp     edi, 1
0x18002858f  jnz     loc_180028701
0x180028595  lea     rdx, [rsi+48h]; pszPath
0x180028599  xor     r8d, r8d; psa
0x18002859c  xor     ecx, ecx; hwnd
0x18002859e  call    cs:__imp_SHCreateDirectoryExW
0x1800285a4  mov     ebx, eax
0x1800285a6  test    eax, eax
0x1800285a8  jle     short loc_1800285B3
0x1800285aa  movzx   ebx, ax
0x1800285ad  or      ebx, 80070000h
0x1800285b3  test    ebx, ebx
0x1800285b5  jns     short loc_180028636
0x1800285b7  cmp     ebx, 800700B7h
0x1800285bd  jz      short loc_180028636
0x1800285bf  cmp     ebx, 80070050h
0x1800285c5  jz      short loc_180028636
0x1800285c7  mov     r9d, ebx; char *
0x1800285ca  mov     edx, 6E3h; void *
0x1800285cf  mov     rcx, [rbp+0B8h]; this
0x1800285d6  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800285dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800285e2  nop
0x1800285e3  mov     [rsp+1B0h+var_180], r15
0x1800285e8  lea     rcx, [rsp+1B0h+var_180]
0x1800285ed  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800285f2  lea     rcx, [rbp+0B0h+var_60]; this
0x1800285f6  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800285fb  lea     rcx, [rbp+0B0h+var_68]
0x1800285ff  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180028604  lea     rcx, [rsp+1B0h+var_178]
0x180028609  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002860e  mov     eax, ebx
0x180028610  mov     rcx, [rbp+0B0h+var_30]
0x180028617  xor     rcx, rsp; StackCookie
0x18002861a  call    __security_check_cookie
0x18002861f  mov     rbx, [rsp+1B0h+arg_10]
0x180028627  add     rsp, 190h
0x18002862e  pop     r15
0x180028630  pop     r14
0x180028632  pop     rdi
0x180028633  pop     rsi
0x180028634  pop     rbp
0x180028635  retn
0x180028636  mov     rcx, [rsi+30h]; this
0x18002863a  call    ?CreateFileW@CThumbnailCacheIndex@@QEAAJXZ; CThumbnailCacheIndex::CreateFileW(void)
0x18002863f  mov     ebx, eax
0x180028641  test    eax, eax
0x180028643  jns     short loc_18002865C
0x180028645  mov     r9d, eax
0x180028648  mov     edx, 6E5h
0x18002864d  jmp     short loc_1800285CF
0x18002864f  mov     r9d, eax
0x180028652  mov     edx, 6D9h
0x180028657  jmp     loc_1800285CF
0x18002865c  xor     ebx, ebx
0x18002865e  cmp     ebx, 0Eh
0x180028661  jge     loc_180028701
0x180028667  lea     rcx, [rsi+38h]
0x18002866b  mov     edx, ebx
0x18002866d  call    ??A?$CSimpleArray@PEAVCThumbnailCacheDataFile@@V?$CSimpleArrayEqualHelper@PEAVCThumbnailCacheDataFile@@@ATL@@@ATL@@QEAAAEAPEAVCThumbnailCacheDataFile@@H@Z; ATL::CSimpleArray<CThumbnailCacheDataFile *,ATL::CSimpleArrayEqualHelper<CThumbnailCacheDataFile *>>::operator[](int)
0x180028672  mov     rdi, [rax]
0x180028675  mov     rcx, rdi; this
0x180028678  call    ?_CloseFileAndMapping@CThumbnailCacheDataFile@@AEAAXXZ; CThumbnailCacheDataFile::_CloseFileAndMapping(void)
0x18002867d  mov     rdx, rdi
0x180028680  lea     rcx, [rsp+1B0h+var_190]
0x180028685  call    ??0?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@PEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(_RTL_SRWLOCK *)
0x18002868a  mov     rcx, rax
0x18002868d  call    _lambda_a3819191aa42c9b12893e59208468e90___operator__
0x180028692  mov     r14d, eax
0x180028695  test    eax, eax
0x180028697  js      short loc_1800286B0
0x180028699  lea     rdx, [rdi+1ACh]; unsigned __int16 *
0x1800286a0  mov     r8, [rdi+1A0h]; void *
0x1800286a7  call    ?SetFileHandle@CFileHandleCache@@QEAAJPEBGPEAX@Z; CFileHandleCache::SetFileHandle(ushort const *,void *)
0x1800286ac  inc     ebx
0x1800286ae  jmp     short loc_18002865E
0x1800286b0  mov     rcx, rdi; this
0x1800286b3  call    ?_CloseFileAndMapping@CThumbnailCacheDataFile@@AEAAXXZ; CThumbnailCacheDataFile::_CloseFileAndMapping(void)
0x1800286b8  mov     rcx, [rbp+0B8h]; this
0x1800286bf  mov     r9d, r14d; char *
0x1800286c2  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800286c9  mov     edx, 228h; void *
0x1800286ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800286d3  mov     rcx, [rbp+0B8h]; this
0x1800286da  mov     r9d, r14d; char *
0x1800286dd  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800286e4  mov     edx, 6E9h; void *
0x1800286e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800286ee  nop
0x1800286ef  lea     rcx, [rsp+1B0h+var_180]; this
0x1800286f4  call    ??1ResetCacheFiles@ThumbnailCacheTelemetry@@QEAA@XZ; ThumbnailCacheTelemetry::ResetCacheFiles::~ResetCacheFiles(void)
0x1800286f9  mov     eax, r14d
0x1800286fc  jmp     loc_180028610
0x180028701  xor     edx, edx
0x180028703  lea     rcx, [rsp+1B0h+var_180]
0x180028708  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002870d  xor     ebx, ebx
0x18002870f  jmp     loc_1800285E3
```
