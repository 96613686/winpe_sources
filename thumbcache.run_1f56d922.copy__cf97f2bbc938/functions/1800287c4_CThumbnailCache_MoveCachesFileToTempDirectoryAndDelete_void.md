# CThumbnailCache::_MoveCachesFileToTempDirectoryAndDelete(void)

- ea: `0x1800287c4`
- end: `0x180028a2c`
- name: `?_MoveCachesFileToTempDirectoryAndDelete@CThumbnailCache@@AEAAJXZ`
- size: `616`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x180028518`

## callees

- `0x18000b3c0`
- `0x18000bfd8`
- `0x18000e280`
- `0x18000e4b0`
- `0x18000ed30`
- `0x18000ed88`
- `0x18000edf0`
- `0x18000f234`
- `0x18001680c`
- `0x1800177e0`
- `0x1800287c4`
- `0x180028a34`
- `0x180028a6c`
- `0x180028e1c`
- `0x18002e1ec`
- `0x18002ed0c`
- `0x180035830`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002899f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002899f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800288d2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002898b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800288d2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002898b`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180028910`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180028910`

## string_xrefs

- `0x180028837`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x180028a09`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x1800287f0`: `MoveCachesFileToTempDirectoryAndDelete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThumbnailCache::_MoveCachesFileToTempDirectoryAndDelete(CThumbnailCacheIndex **this)
{
  unsigned int v2; // r8d
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // r14d
  int i; // edi
  int DataFilePath; // eax
  const WCHAR *v9; // rdx
  CThumbnailCacheDataFile **v10; // rax
  __int64 v11; // rdx
  int v12; // [rsp+20h] [rbp-E0h]
  void **v13; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v14[272]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v15[8]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v16[48]; // [rsp+150h] [rbp+50h] BYREF
  WCHAR PathName[264]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR FileName[264]; // [rsp+390h] [rbp+290h] BYREF
  WCHAR TempFileName[264]; // [rsp+5A0h] [rbp+4A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7F8h] [rbp+6F8h]

  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v13,
    "MoveCachesFileToTempDirectoryAndDelete");
  v13 = &ThumbnailCacheTelemetry::MoveCachesFileToTempDirectoryAndDelete::`vftable';
  ThumbnailCacheTelemetry::MoveCachesFileToTempDirectoryAndDelete::StartActivity((ThumbnailCacheTelemetry::MoveCachesFileToTempDirectoryAndDelete *)&v13);
  v3 = CThumbnailCache::_GetToBeDeletedDirectory((CThumbnailCache *)this, PathName, v2);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x699,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)(unsigned int)v3,
      v12);
LABEL_3:
    v13 = &ThumbnailCacheTelemetry::MoveCachesFileToTempDirectoryAndDelete::`vftable';
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v13);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v16);
    wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v15);
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v14);
    return v4;
  }
  v6 = 0;
  for ( i = 14; ; --i )
  {
    if ( i < 0 )
    {
      wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v13, 0);
      v4 = 0;
      goto LABEL_3;
    }
    if ( i != 14 )
      break;
    DataFilePath = CThumbnailCache::_GetDataFilePath((__int64)this, 1, -1, FileName);
    v4 = DataFilePath;
    if ( DataFilePath < 0 )
    {
      v11 = 1701;
      goto LABEL_31;
    }
LABEL_9:
    if ( GetFileAttributesW(FileName) != -1 )
    {
      if ( !v6 )
      {
        if ( GetFileAttributesW(PathName) == -1 && !CreateDirectoryW(PathName, 0) )
        {
          DataFilePath = ResultFromKnownLastError();
          v4 = DataFilePath;
          if ( DataFilePath < 0 )
          {
            v11 = 1715;
            goto LABEL_31;
          }
        }
        v6 = 1;
      }
      v9 = L"icn";
      if ( ((_BYTE)this[96] & 2) == 0 )
        v9 = L"thm";
      if ( GetTempFileNameW(PathName, v9, 0, TempFileName) )
      {
        if ( i == 14 )
        {
          DataFilePath = CThumbnailCacheIndex::MoveFileToTempDirectoryAndDelete(this[6], TempFileName);
          v4 = DataFilePath;
          if ( DataFilePath < 0 )
          {
            v11 = 1726;
            goto LABEL_31;
          }
        }
        else
        {
          v10 = (CThumbnailCacheDataFile **)ATL::CSimpleArray<CThumbnailCacheDataFile *,ATL::CSimpleArrayEqualHelper<CThumbnailCacheDataFile *>>::operator[](
                                              this + 7,
                                              (unsigned int)i);
          DataFilePath = CThumbnailCacheDataFile::MoveFileToTempDirectoryAndDelete(*v10, TempFileName);
          v4 = DataFilePath;
          if ( DataFilePath < 0 )
          {
            v11 = 1730;
            goto LABEL_31;
          }
        }
      }
      else
      {
        DataFilePath = ResultFromKnownLastError();
        v4 = DataFilePath;
        if ( DataFilePath < 0 )
        {
          v11 = 1735;
          goto LABEL_31;
        }
      }
    }
  }
  DataFilePath = CThumbnailCache::_GetDataFilePath((__int64)this, 0, i, FileName);
  v4 = DataFilePath;
  if ( DataFilePath >= 0 )
    goto LABEL_9;
  v11 = 1706;
LABEL_31:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
    (const char *)(unsigned int)DataFilePath,
    v12);
  ThumbnailCacheTelemetry::MoveCachesFileToTempDirectoryAndDelete::~MoveCachesFileToTempDirectoryAndDelete((ThumbnailCacheTelemetry::MoveCachesFileToTempDirectoryAndDelete *)&v13);
  return v4;
}

```

## disassembly

```asm
0x1800287c4  push    rbp
0x1800287c6  push    rbx
0x1800287c7  push    rsi
0x1800287c8  push    rdi
0x1800287c9  push    r13
0x1800287cb  push    r14
0x1800287cd  lea     rbp, [rsp-6C8h]
0x1800287d5  sub     rsp, 7C8h
0x1800287dc  mov     rax, cs:__security_cookie
0x1800287e3  xor     rax, rsp
0x1800287e6  mov     [rbp+6F0h+var_40], rax
0x1800287ed  mov     rsi, rcx
0x1800287f0  lea     rdx, aMovecachesfile; "MoveCachesFileToTempDirectoryAndDelete"
0x1800287f7  lea     rcx, [rsp+7F0h+var_7C0]
0x1800287fc  call    ??0?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180028801  lea     r13, ??_7MoveCachesFileToTempDirectoryAndDelete@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::MoveCachesFileToTempDirectoryAndDelete::`vftable'
0x180028808  mov     [rsp+7F0h+var_7C0], r13
0x18002880d  lea     rcx, [rsp+7F0h+var_7C0]; this
0x180028812  call    ?StartActivity@MoveCachesFileToTempDirectoryAndDelete@ThumbnailCacheTelemetry@@QEAAXXZ; ThumbnailCacheTelemetry::MoveCachesFileToTempDirectoryAndDelete::StartActivity(void)
0x180028817  nop
0x180028818  lea     rdx, [rbp+6F0h+PathName]; unsigned __int16 *
0x18002881f  mov     rcx, rsi; this
0x180028822  call    ?_GetToBeDeletedDirectory@CThumbnailCache@@AEAAJPEAGI@Z; CThumbnailCache::_GetToBeDeletedDirectory(ushort *,uint)
0x180028827  mov     ebx, eax
0x180028829  test    eax, eax
0x18002882b  jns     short loc_180028895
0x18002882d  mov     rcx, [rbp+6F8h]; this
0x180028834  mov     r9d, eax; char *
0x180028837  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18002883e  mov     edx, 699h; void *
0x180028843  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028848  nop
0x180028849  mov     [rsp+7F0h+var_7C0], r13
0x18002884e  lea     rcx, [rsp+7F0h+var_7C0]
0x180028853  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180028858  lea     rcx, [rbp+6F0h+var_6A0]; this
0x18002885c  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180028861  lea     rcx, [rbp+6F0h+var_6A8]
0x180028865  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18002886a  lea     rcx, [rsp+7F0h+var_7B8]
0x18002886f  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180028874  mov     eax, ebx
0x180028876  mov     rcx, [rbp+6F0h+var_40]
0x18002887d  xor     rcx, rsp; StackCookie
0x180028880  call    __security_check_cookie
0x180028885  add     rsp, 7C8h
0x18002888c  pop     r14
0x18002888e  pop     r13
0x180028890  pop     rdi
0x180028891  pop     rsi
0x180028892  pop     rbx
0x180028893  pop     rbp
0x180028894  retn
0x180028895  xor     r14d, r14d
0x180028898  lea     edi, [r14+0Eh]
0x18002889c  test    edi, edi
0x18002889e  js      loc_1800289B4
0x1800288a4  lea     r9, [rbp+6F0h+FileName]
0x1800288ab  mov     rcx, rsi
0x1800288ae  cmp     edi, 0Eh
0x1800288b1  jz      loc_18002894E
0x1800288b7  mov     r8d, edi
0x1800288ba  xor     edx, edx
0x1800288bc  call    ?_GetDataFilePath@CThumbnailCache@@AEAAJHW4THUMBSIZE@@PEAGI@Z; CThumbnailCache::_GetDataFilePath(int,THUMBSIZE,ushort *,uint)
0x1800288c1  mov     ebx, eax
0x1800288c3  test    eax, eax
0x1800288c5  js      loc_180028A01
0x1800288cb  lea     rcx, [rbp+6F0h+FileName]; lpFileName
0x1800288d2  call    cs:__imp_GetFileAttributesW
0x1800288d8  cmp     eax, 0FFFFFFFFh
0x1800288db  jz      short loc_180028947
0x1800288dd  test    r14d, r14d
0x1800288e0  jz      loc_180028984
0x1800288e6  test    byte ptr [rsi+300h], 2
0x1800288ed  lea     rax, PrefixString; "thm"
0x1800288f4  lea     rdx, aIcn_0; "icn"
0x1800288fb  cmovz   rdx, rax; lpPrefixString
0x1800288ff  lea     r9, [rbp+6F0h+TempFileName]; lpTempFileName
0x180028906  xor     r8d, r8d; uUnique
0x180028909  lea     rcx, [rbp+6F0h+PathName]; lpPathName
0x180028910  call    cs:__imp_GetTempFileNameW
0x180028916  test    eax, eax
0x180028918  jz      short loc_18002896F
0x18002891a  cmp     edi, 0Eh
0x18002891d  jz      loc_1800289D9
0x180028923  lea     rcx, [rsi+38h]
0x180028927  mov     edx, edi
0x180028929  call    ??A?$CSimpleArray@PEAVCThumbnailCacheDataFile@@V?$CSimpleArrayEqualHelper@PEAVCThumbnailCacheDataFile@@@ATL@@@ATL@@QEAAAEAPEAVCThumbnailCacheDataFile@@H@Z; ATL::CSimpleArray<CThumbnailCacheDataFile *,ATL::CSimpleArrayEqualHelper<CThumbnailCacheDataFile *>>::operator[](int)
0x18002892e  lea     rdx, [rbp+6F0h+TempFileName]; unsigned __int16 *
0x180028935  mov     rcx, [rax]; this
0x180028938  call    ?MoveFileToTempDirectoryAndDelete@CThumbnailCacheDataFile@@QEAAJPEBG@Z; CThumbnailCacheDataFile::MoveFileToTempDirectoryAndDelete(ushort const *)
0x18002893d  mov     ebx, eax
0x18002893f  test    eax, eax
0x180028941  js      loc_1800289FA
0x180028947  dec     edi
0x180028949  jmp     loc_18002889C
0x18002894e  or      r8d, 0FFFFFFFFh
0x180028952  lea     edx, [r8+2]
0x180028956  call    ?_GetDataFilePath@CThumbnailCache@@AEAAJHW4THUMBSIZE@@PEAGI@Z; CThumbnailCache::_GetDataFilePath(int,THUMBSIZE,ushort *,uint)
0x18002895b  mov     ebx, eax
0x18002895d  test    eax, eax
0x18002895f  jns     loc_1800288CB
0x180028965  mov     edx, 6A5h
0x18002896a  jmp     loc_180028A06
0x18002896f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180028974  mov     ebx, eax
0x180028976  test    eax, eax
0x180028978  jns     short loc_180028947
0x18002897a  mov     edx, 6C7h
0x18002897f  jmp     loc_180028A06
0x180028984  lea     rcx, [rbp+6F0h+PathName]; lpFileName
0x18002898b  call    cs:__imp_GetFileAttributesW
0x180028991  cmp     eax, 0FFFFFFFFh
0x180028994  jnz     short loc_1800289A9
0x180028996  xor     edx, edx; lpSecurityAttributes
0x180028998  lea     rcx, [rbp+6F0h+PathName]; lpPathName
0x18002899f  call    cs:__imp_CreateDirectoryW
0x1800289a5  test    eax, eax
0x1800289a7  jz      short loc_1800289C7
0x1800289a9  mov     r14d, 1
0x1800289af  jmp     loc_1800288E6
0x1800289b4  xor     edx, edx
0x1800289b6  lea     rcx, [rsp+7F0h+var_7C0]
0x1800289bb  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800289c0  xor     ebx, ebx
0x1800289c2  jmp     loc_180028849
0x1800289c7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800289cc  mov     ebx, eax
0x1800289ce  test    eax, eax
0x1800289d0  jns     short loc_1800289A9
0x1800289d2  mov     edx, 6B3h
0x1800289d7  jmp     short loc_180028A06
0x1800289d9  lea     rdx, [rbp+6F0h+TempFileName]; lpFileName
0x1800289e0  mov     rcx, [rsi+30h]; this
0x1800289e4  call    ?MoveFileToTempDirectoryAndDelete@CThumbnailCacheIndex@@QEAAJPEBG@Z; CThumbnailCacheIndex::MoveFileToTempDirectoryAndDelete(ushort const *)
0x1800289e9  mov     ebx, eax
0x1800289eb  test    eax, eax
0x1800289ed  jns     loc_180028947
0x1800289f3  mov     edx, 6BEh
0x1800289f8  jmp     short loc_180028A06
0x1800289fa  mov     edx, 6C2h
0x1800289ff  jmp     short loc_180028A06
0x180028a01  mov     edx, 6AAh; void *
0x180028a06  mov     r9d, eax; char *
0x180028a09  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180028a10  mov     rcx, [rbp+6F8h]; this
0x180028a17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a1c  nop
0x180028a1d  lea     rcx, [rsp+7F0h+var_7C0]; this
0x180028a22  call    ??1MoveCachesFileToTempDirectoryAndDelete@ThumbnailCacheTelemetry@@QEAA@XZ; ThumbnailCacheTelemetry::MoveCachesFileToTempDirectoryAndDelete::~MoveCachesFileToTempDirectoryAndDelete(void)
0x180028a27  jmp     loc_180028874
```
