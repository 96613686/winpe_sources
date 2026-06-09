# CThumbnailCache::AttemptInitialize(WTS_FLAGS,int)

- ea: `0x180015868`
- end: `0x180015bce`
- name: `?AttemptInitialize@CThumbnailCache@@AEAAJW4WTS_FLAGS@@H@Z`
- size: `870`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this, enum WTS_FLAGS, int)`
- caller_count: `3`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a300`
- `0x18000c6f4`
- `0x180013a70`

## callees

- `0x18000bfd8`
- `0x18000e280`
- `0x18000e4b0`
- `0x18000ed30`
- `0x18000ed88`
- `0x18000edf0`
- `0x18000f234`
- `0x180010890`
- `0x180010db0`
- `0x180015868`
- `0x180015bd4`
- `0x180015c74`
- `0x180015d40`
- `0x180016660`
- `0x180016924`
- `0x1800175a4`
- `0x180028518`
- `0x18002b11c`
- `0x18002d440`
- `0x18002e834`
- `0x1800308dc`
- `0x180035830`
- `0x18004092c`
- `0x180040ad4`
- `0x180049010`

## string_xrefs

- `0x180015a4f`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x180015a80`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x180015b52`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x180015b6f`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x1800158ac`: `InitializeCache`
- `0x180015aa3`: `ResetCacheFilesForUninitializedCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CThumbnailCache::AttemptInitialize(CThumbnailCache *this, enum WTS_FLAGS a2, __int64 a3)
{
  HRESULT v4; // eax
  int v5; // edi
  int CacheFileObjects; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rdx
  unsigned int v10; // r8d
  bool v11; // si
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  int v18; // r9d
  int v19; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  _BYTE v21[24]; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  enum WTS_FLAGS v23[4]; // [rsp+50h] [rbp-B0h] BYREF
  void **v24; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[272]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v26[8]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v27[48]; // [rsp+180h] [rbp+80h] BYREF
  void **v28; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v29[272]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v30[8]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v31[48]; // [rsp+2D0h] [rbp+1D0h] BYREF
  CThumbnailCache *v32; // [rsp+300h] [rbp+200h] BYREF
  int v33; // [rsp+308h] [rbp+208h]
  bool v34; // [rsp+30Ch] [rbp+20Ch]
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v23[0] = a2;
  v22 = a3;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(this, Thumbnails_Initialize_Start, a3, 1, &v32);
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v28,
    "InitializeCache");
  v28 = &ThumbnailCacheTelemetry::InitializeCache::`vftable';
  ThumbnailCacheTelemetry::InitializeCache::StartActivity((ThumbnailCacheTelemetry::InitializeCache *)&v28);
  *((_BYTE *)this + 756) = 1;
  v4 = CThumbnailCache::_ComputeCacheDirectory(this);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74E,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)(unsigned int)v4,
      v20);
  }
  else
  {
    CacheFileObjects = CThumbnailCache::_CreateCacheFileObjects(this);
    v5 = CacheFileObjects;
    if ( CacheFileObjects < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x751,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
        (const char *)(unsigned int)CacheFileObjects,
        v20);
      goto LABEL_25;
    }
    if ( (*((_BYTE *)this + 768) & 1) != 0 )
    {
LABEL_13:
      *(_WORD *)((char *)this + 757) = 1;
      if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(v7, Thumbnails_Initialize_Stop, v8, 1, &v32);
      wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)&v28, 0);
      v5 = 0;
      goto LABEL_16;
    }
    v32 = this;
    (*(void (__fastcall **)(CThumbnailCache *))(*(_QWORD *)this + 8LL))(this);
    v5 = 0;
    v33 = 0;
    v11 = 0;
    v34 = 0;
    if ( !*((_BYTE *)this + 744) )
    {
      v5 = CThumbnailCache::_AcquireInitializationMutex(this);
      v33 = v5;
      v11 = v5 >= 0;
      v34 = v5 >= 0;
    }
    if ( v5 >= 0 )
    {
      CThumbnailCache::_CleanupToBeDeletedCacheFiles(this, v9, v10);
      CThumbnailCache::_ReadSettingsFromRegistry(this);
      v12 = lambda_76dcf64d840e02a191d95e56191500e0_::_lambda_76dcf64d840e02a191d95e56191500e0_(v21, this, v23, &v22);
      v13 = lambda_76dcf64d840e02a191d95e56191500e0_::operator()(v12);
      v16 = (unsigned int)v13;
      if ( v13 >= 0 || v13 == -2147024864 )
        goto LABEL_10;
      wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
        &v24,
        "ResetCacheFilesForUninitializedCache");
      v24 = &ThumbnailCacheTelemetry::ResetCacheFilesForUninitializedCache::`vftable';
      ThumbnailCacheTelemetry::ResetCacheFilesForUninitializedCache::StartActivity(
        (ThumbnailCacheTelemetry::ResetCacheFilesForUninitializedCache *)&v24,
        v18);
      v19 = CThumbnailCache::_ResetCacheFiles((__int64)this, 1u);
      v5 = v19;
      if ( v19 >= 0 )
      {
        wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop((__int64)&v24, 0);
        v24 = &ThumbnailCacheTelemetry::ResetCacheFilesForUninitializedCache::`vftable';
        wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v24);
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v27);
        wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v26);
        wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v25);
LABEL_10:
        if ( v11 )
          CNamedMutex::Release((CThumbnailCache *)((char *)this + 736));
        (*(void (__fastcall **)(CThumbnailCache *, __int64, __int64, __int64))(*(_QWORD *)this + 16LL))(
          this,
          v14,
          v15,
          v16);
        goto LABEL_13;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x772,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
        (const char *)(unsigned int)v19,
        v20);
      ThumbnailCacheTelemetry::ResetCacheFilesForUninitializedCache::~ResetCacheFilesForUninitializedCache((ThumbnailCacheTelemetry::ResetCacheFilesForUninitializedCache *)&v24);
      CThumbnailCache::CAcquireInitializationMutex::~CAcquireInitializationMutex((CThumbnailCache::CAcquireInitializationMutex *)&v32);
LABEL_25:
      ThumbnailCacheTelemetry::InitializeCache::~InitializeCache((ThumbnailCacheTelemetry::InitializeCache *)&v28);
      return (unsigned int)v5;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x757,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)(unsigned int)v5,
      v20);
    (*(void (__fastcall **)(CThumbnailCache *))(*(_QWORD *)this + 16LL))(this);
  }
LABEL_16:
  v28 = &ThumbnailCacheTelemetry::InitializeCache::`vftable';
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v28);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v31);
  wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v30);
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v29);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180015868  push    rbp
0x18001586a  push    rbx
0x18001586b  push    rsi
0x18001586c  push    rdi
0x18001586d  push    r12
0x18001586f  push    r13
0x180015871  push    r14
0x180015873  lea     rbp, [rsp-220h]
0x18001587b  sub     rsp, 320h
0x180015882  mov     rax, cs:__security_cookie
0x180015889  xor     rax, rsp
0x18001588c  mov     [rbp+250h+var_40], rax
0x180015893  mov     rbx, rcx
0x180015896  mov     [rsp+350h+var_300], edx
0x18001589a  mov     [rsp+350h+var_308], r8d
0x18001589f  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800158a6  jnz     loc_180015B25
0x1800158ac  lea     rdx, aInitializecach; "InitializeCache"
0x1800158b3  lea     rcx, [rbp+250h+var_1A0]
0x1800158ba  call    ??0?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800158bf  lea     r13, ??_7InitializeCache@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::InitializeCache::`vftable'
0x1800158c6  mov     [rbp+250h+var_1A0], r13
0x1800158cd  lea     rcx, [rbp+250h+var_1A0]; this
0x1800158d4  call    ?StartActivity@InitializeCache@ThumbnailCacheTelemetry@@QEAAXXZ; ThumbnailCacheTelemetry::InitializeCache::StartActivity(void)
0x1800158d9  nop
0x1800158da  mov     byte ptr [rbx+2F4h], 1
0x1800158e1  mov     rcx, rbx; this
0x1800158e4  call    ?_ComputeCacheDirectory@CThumbnailCache@@AEAAJXZ; CThumbnailCache::_ComputeCacheDirectory(void)
0x1800158e9  mov     edi, eax
0x1800158eb  test    eax, eax
0x1800158ed  js      loc_180015A76
0x1800158f3  mov     rcx, rbx; this
0x1800158f6  call    ?_CreateCacheFileObjects@CThumbnailCache@@AEAAJXZ; CThumbnailCache::_CreateCacheFileObjects(void)
0x1800158fb  mov     edi, eax
0x1800158fd  test    eax, eax
0x1800158ff  js      loc_180015B48
0x180015905  test    byte ptr [rbx+300h], 1
0x18001590c  jnz     loc_1800159C5
0x180015912  mov     [rbp+250h+var_50], rbx
0x180015919  mov     rax, [rbx]
0x18001591c  mov     rcx, rbx
0x18001591f  mov     rax, [rax+8]
0x180015923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015928  nop
0x180015929  xor     edi, edi
0x18001592b  mov     [rbp+250h+var_48], edi
0x180015931  xor     sil, sil
0x180015934  mov     [rbp+250h+var_44], sil
0x18001593b  lea     r14, [rbx+2E0h]
0x180015942  cmp     [r14+8], sil
0x180015946  jnz     short loc_180015965
0x180015948  mov     rcx, rbx; this
0x18001594b  call    ?_AcquireInitializationMutex@CThumbnailCache@@AEAAJXZ; CThumbnailCache::_AcquireInitializationMutex(void)
0x180015950  mov     edi, eax
0x180015952  mov     [rbp+250h+var_48], eax
0x180015958  test    eax, eax
0x18001595a  setns   sil
0x18001595e  mov     [rbp+250h+var_44], sil
0x180015965  test    edi, edi
0x180015967  js      loc_180015A45
0x18001596d  mov     rcx, rbx; this
0x180015970  call    ?_CleanupToBeDeletedCacheFiles@CThumbnailCache@@AEAAJXZ; CThumbnailCache::_CleanupToBeDeletedCacheFiles(void)
0x180015975  mov     rcx, rbx; this
0x180015978  call    ?_ReadSettingsFromRegistry@CThumbnailCache@@AEAAXXZ; CThumbnailCache::_ReadSettingsFromRegistry(void)
0x18001597d  lea     r9, [rsp+350h+var_308]
0x180015982  lea     r8, [rsp+350h+var_300]
0x180015987  mov     rdx, rbx
0x18001598a  lea     rcx, [rsp+350h+var_320]
0x18001598f  call    _lambda_76dcf64d840e02a191d95e56191500e0____lambda_76dcf64d840e02a191d95e56191500e0_
0x180015994  mov     rcx, rax
0x180015997  call    _lambda_76dcf64d840e02a191d95e56191500e0___operator__
0x18001599c  mov     r9d, eax
0x18001599f  test    eax, eax
0x1800159a1  js      loc_180015A96
0x1800159a7  test    sil, sil
0x1800159aa  jz      short loc_1800159B5
0x1800159ac  mov     rcx, r14; this
0x1800159af  call    ?Release@CNamedMutex@@QEAAJXZ; CNamedMutex::Release(void)
0x1800159b4  nop
0x1800159b5  mov     rax, [rbx]
0x1800159b8  mov     rcx, rbx
0x1800159bb  mov     rax, [rax+10h]
0x1800159bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159c4  nop
0x1800159c5  mov     word ptr [rbx+2F5h], 1
0x1800159ce  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800159d5  jnz     loc_180015BAA
0x1800159db  xor     edx, edx
0x1800159dd  lea     rcx, [rbp+250h+var_1A0]
0x1800159e4  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800159e9  xor     edi, edi
0x1800159eb  mov     [rbp+250h+var_1A0], r13
0x1800159f2  lea     rcx, [rbp+250h+var_1A0]
0x1800159f9  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800159fe  lea     rcx, [rbp+250h+var_80]; this
0x180015a05  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180015a0a  lea     rcx, [rbp+250h+var_88]
0x180015a11  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180015a16  lea     rcx, [rbp+250h+var_198]
0x180015a1d  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180015a22  mov     eax, edi
0x180015a24  mov     rcx, [rbp+250h+var_40]
0x180015a2b  xor     rcx, rsp; StackCookie
0x180015a2e  call    __security_check_cookie
0x180015a33  add     rsp, 320h
0x180015a3a  pop     r14
0x180015a3c  pop     r13
0x180015a3e  pop     r12
0x180015a40  pop     rdi
0x180015a41  pop     rsi
0x180015a42  pop     rbx
0x180015a43  pop     rbp
0x180015a44  retn
0x180015a45  mov     rcx, [rbp+258h]; this
0x180015a4c  mov     r9d, edi; char *
0x180015a4f  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180015a56  mov     edx, 757h; void *
0x180015a5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015a60  nop
0x180015a61  mov     rax, [rbx]
0x180015a64  mov     rcx, rbx
0x180015a67  mov     rax, [rax+10h]
0x180015a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a70  nop
0x180015a71  jmp     loc_1800159EB
0x180015a76  mov     rcx, [rbp+258h]; this
0x180015a7d  mov     r9d, eax; char *
0x180015a80  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180015a87  mov     edx, 74Eh; void *
0x180015a8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015a91  jmp     loc_1800159EB
0x180015a96  cmp     r9d, 80070020h
0x180015a9d  jz      loc_1800159A7
0x180015aa3  lea     rdx, aResetcachefile_1; "ResetCacheFilesForUninitializedCache"
0x180015aaa  lea     rcx, [rsp+350h+var_2F0]
0x180015aaf  call    ??0?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180015ab4  lea     r12, ??_7ResetCacheFilesForUninitializedCache@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::ResetCacheFilesForUninitializedCache::`vftable'
0x180015abb  mov     [rsp+350h+var_2F0], r12
0x180015ac0  mov     edx, r9d; int
0x180015ac3  lea     rcx, [rsp+350h+var_2F0]; this
0x180015ac8  call    ?StartActivity@ResetCacheFilesForUninitializedCache@ThumbnailCacheTelemetry@@QEAAXJ@Z; ThumbnailCacheTelemetry::ResetCacheFilesForUninitializedCache::StartActivity(long)
0x180015acd  nop
0x180015ace  mov     edx, 1
0x180015ad3  mov     rcx, rbx
0x180015ad6  call    ?_ResetCacheFiles@CThumbnailCache@@AEAAJW4RESETTHUMBNAILCACHEFILES_RECREATEFLAG@@@Z; CThumbnailCache::_ResetCacheFiles(RESETTHUMBNAILCACHEFILES_RECREATEFLAG)
0x180015adb  mov     edi, eax
0x180015add  test    eax, eax
0x180015adf  js      loc_180015B65
0x180015ae5  xor     edx, edx
0x180015ae7  lea     rcx, [rsp+350h+var_2F0]
0x180015aec  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180015af1  nop
0x180015af2  mov     [rsp+350h+var_2F0], r12
0x180015af7  lea     rcx, [rsp+350h+var_2F0]
0x180015afc  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180015b01  lea     rcx, [rbp+250h+var_1D0]; this
0x180015b08  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180015b0d  lea     rcx, [rbp+250h+var_1D8]
0x180015b11  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180015b16  lea     rcx, [rsp+350h+var_2E8]
0x180015b1b  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180015b20  jmp     loc_1800159A7
0x180015b25  lea     rax, [rbp+250h+var_50]
0x180015b2c  mov     qword ptr [rsp+350h+var_330], rax
0x180015b31  mov     r9d, 1
0x180015b37  lea     rdx, Thumbnails_Initialize_Start
0x180015b3e  call    McGenEventWrite_EventWriteTransfer
0x180015b43  jmp     loc_1800158AC
0x180015b48  mov     rcx, [rbp+258h]; this
0x180015b4f  mov     r9d, eax; char *
0x180015b52  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180015b59  mov     edx, 751h; void *
0x180015b5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b63  jmp     short loc_180015B99
0x180015b65  mov     rcx, [rbp+258h]; this
0x180015b6c  mov     r9d, eax; char *
0x180015b6f  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180015b76  mov     edx, 772h; void *
0x180015b7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015b80  nop
0x180015b81  lea     rcx, [rsp+350h+var_2F0]; this
0x180015b86  call    ??1ResetCacheFilesForUninitializedCache@ThumbnailCacheTelemetry@@QEAA@XZ; ThumbnailCacheTelemetry::ResetCacheFilesForUninitializedCache::~ResetCacheFilesForUninitializedCache(void)
0x180015b8b  nop
0x180015b8c  lea     rcx, [rbp+250h+var_50]; this
0x180015b93  call    ??1CAcquireInitializationMutex@CThumbnailCache@@QEAA@XZ; CThumbnailCache::CAcquireInitializationMutex::~CAcquireInitializationMutex(void)
0x180015b98  nop
0x180015b99  lea     rcx, [rbp+250h+var_1A0]; this
0x180015ba0  call    ??1InitializeCache@ThumbnailCacheTelemetry@@QEAA@XZ; ThumbnailCacheTelemetry::InitializeCache::~InitializeCache(void)
0x180015ba5  jmp     loc_180015A22
0x180015baa  lea     rax, [rbp+250h+var_50]
0x180015bb1  mov     qword ptr [rsp+350h+var_330], rax
0x180015bb6  mov     r9d, 1
0x180015bbc  lea     rdx, Thumbnails_Initialize_Stop
0x180015bc3  call    McGenEventWrite_EventWriteTransfer
0x180015bc8  jmp     loc_1800159DB
```
