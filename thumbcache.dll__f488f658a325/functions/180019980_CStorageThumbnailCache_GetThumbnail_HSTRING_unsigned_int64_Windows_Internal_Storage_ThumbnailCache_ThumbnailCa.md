# CStorageThumbnailCache::GetThumbnail(HSTRING__ *,unsigned __int64,Windows::Internal::Storage::ThumbnailCache::ThumbnailCacheOptions,Windows::Foundation::Size,Windows::Internal::Storage::ThumbnailCache::IThumbnailResult * *)

- ea: `0x180019980`
- end: `0x180019ff9`
- name: `?GetThumbnail@CStorageThumbnailCache@@UEAAJPEAUHSTRING__@@_KW4ThumbnailCacheOptions@ThumbnailCache@Storage@Internal@Windows@@USize@Foundation@7@PEAPEAUIThumbnailResult@4567@@Z`
- size: `1657`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x18000c67c`
- `0x18000e280`
- `0x18000e4b0`
- `0x18000ed30`
- `0x18000ed88`
- `0x18000edf0`
- `0x18000f234`
- `0x180010388`
- `0x180019980`
- `0x18001a000`
- `0x18001a0e8`
- `0x18001a5c0`
- `0x18001a694`
- `0x18001a7dc`
- `0x18001a96c`
- `0x18001aa44`
- `0x18001aac4`
- `0x18001aaf0`
- `0x180025890`
- `0x180035830`
- `0x180035860`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019b02`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019e26`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019e72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019b02`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019e26`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019e72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019a89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019d9c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019a89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800199ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800199ed`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180019d51`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180019d51`

## string_xrefs

- `0x180019cb5`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x180019cdc`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x180019ebe`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x180019f50`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x180019f70`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x180019f90`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x180019fb8`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x180019fd8`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CStorageThumbnailCache::GetThumbnail(
        CStorageThumbnailCache *a1,
        HSTRING a2,
        unsigned __int64 a3,
        char a4,
        __int64 a5,
        _QWORD *a6)
{
  unsigned int v10; // r14d
  const struct _GUID *v11; // rdx
  int ThumbnailCache; // eax
  void *v13; // rbx
  float v14; // xmm6_4
  RTL_SRWLOCK *v15; // rdi
  void *v16; // rsi
  const WCHAR *v17; // r15
  __int64 v18; // rcx
  const struct _GUID *v19; // rdx
  int v20; // eax
  __m128 v21; // xmm6
  __m128 v22; // xmm7
  void *v23; // rdi
  CStorageThumbnailResult *v24; // rax
  CStorageThumbnailResult *v25; // rbx
  int v26; // edi
  void *v27; // rcx
  struct IStream *v28; // rcx
  void *v29; // rcx
  __int64 v31; // rdx
  HRESULT v32; // eax
  __int64 (__fastcall *v33)(void *, GUID *, __int64 *); // rsi
  int v34; // eax
  __int64 v35; // rbx
  unsigned int (__fastcall *v36)(__int64, PCWSTR, _QWORD, _QWORD); // rsi
  struct IStream *v37; // rcx
  int v38; // ecx
  __int64 v39; // rcx
  PCWSTR v40; // rcx
  void *v41; // rcx
  int v42; // [rsp+28h] [rbp-E0h]
  int v43; // [rsp+28h] [rbp-E0h]
  RTL_SRWLOCK *v44; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v45[2]; // [rsp+68h] [rbp-A0h] BYREF
  struct IStream *v46; // [rsp+78h] [rbp-90h] BYREF
  void *v47; // [rsp+80h] [rbp-88h] BYREF
  PCWSTR pszPath; // [rsp+88h] [rbp-80h] BYREF
  __int64 v49; // [rsp+90h] [rbp-78h] BYREF
  void *v50; // [rsp+98h] [rbp-70h] BYREF
  __int128 v51; // [rsp+A0h] [rbp-68h]
  __int128 v52; // [rsp+B0h] [rbp-58h]
  void **v53; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v54[272]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v55[8]; // [rsp+1E0h] [rbp+D8h] BYREF
  _BYTE v56[48]; // [rsp+1E8h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  *a6 = 0;
  if ( !a3 )
  {
    LODWORD(v13) = -2147024809;
    v31 = 997;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v13,
      v42);
    return (unsigned int)v13;
  }
  if ( !IsCallerAllowed((bool)a1) )
  {
    LODWORD(v13) = -2147024891;
    v31 = 998;
    goto LABEL_27;
  }
  pszPath = WindowsGetStringRawBuffer(a2, 0);
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v53,
    "OptimizedGetThumbnail");
  v53 = &ThumbnailCacheTelemetry::OptimizedGetThumbnail::`vftable';
  ThumbnailCacheTelemetry::OptimizedGetThumbnail::StartActivity(
    (ThumbnailCacheTelemetry::OptimizedGetThumbnail *)&v53,
    1,
    a3);
  v10 = ((a4 & 1) + 0x2000) | 0x40;
  if ( (a4 & 2) == 0 )
    v10 = (a4 & 1) + 0x2000;
  v47 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
  ThumbnailCache = CStorageThumbnailCache::GetThumbnailCache(a1, v11, &v47);
  LODWORD(v13) = ThumbnailCache;
  if ( ThumbnailCache < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F1,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)ThumbnailCache,
      v42);
    v41 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
    }
    goto LABEL_24;
  }
  v14 = fmaxf(*(float *)&a5, *((float *)&a5 + 1));
  v46 = 0;
  v51 = 0;
  v52 = 0;
  v15 = (RTL_SRWLOCK *)((char *)a1 + 64);
  AcquireSRWLockExclusive(v15);
  v44 = v15;
  v16 = v47;
  v13 = *(void **)(*(_QWORD *)v47 + 104LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  v45[0] = a3;
  v45[1] = 0;
  v43 = v10;
  v17 = pszPath;
  LODWORD(v13) = ((__int64 (__fastcall *)(void *, PCWSTR, _QWORD *, _QWORD))v13)(
                   v16,
                   pszPath,
                   v45,
                   (unsigned int)(int)v14);
  if ( v15 )
    ReleaseSRWLockExclusive(v15);
  if ( (int)v13 >= 0 && (v51 & 1) != 0 && (a4 & 4) == 0 )
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  if ( (v10 & 1) == 0 && ((int)v13 >= 0 && (v51 & 1) != 0 || (unsigned int)((_DWORD)v13 + 2147287038) <= 1) )
  {
    pszPath = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pszPath);
    v32 = SHCreateItemFromParsingName(v17, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, (void **)&pszPath);
    LODWORD(v13) = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40C,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)(unsigned int)v32,
        v10);
    }
    else
    {
      v49 = 0;
      v13 = v47;
      v33 = **(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v47;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
      v34 = v33(v13, &GUID_2d3e7f31_91d1_4fb8_a7ea_fa4011bdbcda, &v49);
      LODWORD(v13) = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40F,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
          (const char *)(unsigned int)v34,
          v10);
      }
      else
      {
        AcquireSRWLockExclusive(v15);
        v44 = v15;
        v35 = v49;
        v36 = *(unsigned int (__fastcall **)(__int64, PCWSTR, _QWORD, _QWORD))(*(_QWORD *)v49 + 88LL);
        v37 = v46;
        if ( v46 )
        {
          v46 = 0;
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v37 + 16LL))(v37);
        }
        v43 = 0;
        v13 = (void *)v36(v35, pszPath, (unsigned int)(int)v14, v10);
        if ( (unsigned __int8)ShouldSuppressWilErrorTelemetry(v13) )
        {
          if ( (int)v13 >= 0 )
            goto LABEL_39;
        }
        else
        {
          if ( v38 >= 0 )
          {
LABEL_39:
            if ( v15 )
              ReleaseSRWLockExclusive(v15);
            v39 = v49;
            if ( v49 )
            {
              v49 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
            }
            v40 = pszPath;
            if ( pszPath )
            {
              pszPath = 0;
              (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)v40 + 16LL))(v40);
            }
            goto LABEL_10;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x41B,
            (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
            (const char *)(unsigned int)v13,
            0);
        }
        if ( v15 )
          ReleaseSRWLockExclusive(v15);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pszPath);
    goto LABEL_30;
  }
LABEL_10:
  if ( !IsExpectedThumbnailError((int)v13) )
  {
    if ( (unsigned __int8)ShouldSuppressWilErrorTelemetry(v18) )
    {
      if ( (int)v13 < 0 )
        goto LABEL_30;
    }
    else if ( (int)v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42A,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)(unsigned int)v13,
        v43);
      goto LABEL_30;
    }
  }
  v50 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
  v20 = CreateRandomAccessStreamOverReadOnlySharedMemoryStream(v46, v19, &v50);
  LODWORD(v13) = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42E,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v20,
      v43);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    goto LABEL_30;
  }
  v21 = (__m128)COERCE_UNSIGNED_INT((float)SDWORD1(v52));
  v22 = (__m128)COERCE_UNSIGNED_INT((float)SDWORD2(v52));
  v23 = v50;
  *a6 = 0;
  v24 = (CStorageThumbnailResult *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v24 )
  {
    v26 = -2147024882;
    goto LABEL_29;
  }
  v25 = CStorageThumbnailResult::CStorageThumbnailResult(v24);
  v45[0] = v25;
  v44 = 0;
  v26 = CStorageThumbnailResult::RuntimeClassInitialize(v25, _mm_unpacklo_ps(v21, v22).m128_u64[0], v23);
  if ( v26 < 0 )
  {
    if ( v25 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::ThumbnailCache::IThumbnailResult,Microsoft::WRL::FtmBase>::Release(v25);
    Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CStorageThumbnailResult,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<CStorageThumbnailResult,0>>(&v44);
    goto LABEL_29;
  }
  v26 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Storage::ThumbnailCache::IThumbnailResult,Microsoft::WRL::FtmBase>>(
          v25,
          &GUID_277f0b63_2e83_43bd_8a09_02098e3da243,
          a6);
  if ( v25 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::ThumbnailCache::IThumbnailResult,Microsoft::WRL::FtmBase>::Release(v25);
  if ( v26 < 0 )
  {
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x431,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v26,
      v43);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50);
    LODWORD(v13) = v26;
LABEL_30:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    ThumbnailCacheTelemetry::OptimizedGetThumbnail::~OptimizedGetThumbnail((ThumbnailCacheTelemetry::OptimizedGetThumbnail *)&v53);
    return (unsigned int)v13;
  }
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v53, 0);
  v27 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v29 + 16LL))(v29);
  }
  LODWORD(v13) = 0;
LABEL_24:
  v53 = &ThumbnailCacheTelemetry::OptimizedGetThumbnail::`vftable';
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v53);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v56);
  wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v55);
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v54);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180019980  mov     rax, rsp
0x180019983  mov     [rax+20h], rbx
0x180019987  push    rbp
0x180019988  push    rsi
0x180019989  push    rdi
0x18001998a  push    r12
0x18001998c  push    r13
0x18001998e  push    r14
0x180019990  push    r15
0x180019992  lea     rbp, [rax-178h]
0x180019999  sub     rsp, 240h
0x1800199a0  movaps  xmmword ptr [rax-48h], xmm6
0x1800199a4  movaps  xmmword ptr [rax-58h], xmm7
0x1800199a8  mov     rax, cs:__security_cookie
0x1800199af  xor     rax, rsp
0x1800199b2  mov     [rbp+170h+var_60], rax
0x1800199b9  mov     r12d, r9d
0x1800199bc  mov     r15, r8
0x1800199bf  mov     rbx, rdx
0x1800199c2  mov     rdi, rcx
0x1800199c5  mov     r13, [rbp+170h+arg_28]
0x1800199cc  xor     esi, esi
0x1800199ce  mov     [r13+0], rsi
0x1800199d2  test    r8, r8
0x1800199d5  jz      loc_180019CAB
0x1800199db  call    ?IsCallerAllowed@@YA_N_N@Z; IsCallerAllowed(bool)
0x1800199e0  test    al, al
0x1800199e2  jz      loc_180019F28
0x1800199e8  xor     edx, edx; length
0x1800199ea  mov     rcx, rbx; string
0x1800199ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800199f3  mov     [rbp+170h+pszPath], rax
0x1800199f7  lea     rdx, aOptimizedgetth; "OptimizedGetThumbnail"
0x1800199fe  lea     rcx, [rbp+170h+var_1B0]
0x180019a02  call    ??0?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180019a07  lea     rax, ??_7OptimizedGetThumbnail@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::OptimizedGetThumbnail::`vftable'
0x180019a0e  mov     [rbp+170h+var_1B0], rax
0x180019a12  mov     r8, r15; unsigned __int64
0x180019a15  mov     dl, 1; bool
0x180019a17  lea     rcx, [rbp+170h+var_1B0]; this
0x180019a1b  call    ?StartActivity@OptimizedGetThumbnail@ThumbnailCacheTelemetry@@QEAAX_N_K@Z; ThumbnailCacheTelemetry::OptimizedGetThumbnail::StartActivity(bool,unsigned __int64)
0x180019a20  nop
0x180019a21  mov     ecx, r12d
0x180019a24  and     ecx, 1
0x180019a27  add     ecx, 2000h
0x180019a2d  mov     r14d, ecx
0x180019a30  or      r14d, 40h
0x180019a34  test    r12b, 2
0x180019a38  cmovz   r14d, ecx
0x180019a3c  mov     [rsp+270h+var_1F8], rsi
0x180019a41  lea     rcx, [rsp+270h+var_1F8]
0x180019a46  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019a4b  lea     r8, [rsp+270h+var_1F8]; void **
0x180019a50  mov     rcx, rdi; this
0x180019a53  call    ?GetThumbnailCache@CStorageThumbnailCache@@AEAAJAEBU_GUID@@PEAPEAX@Z; CStorageThumbnailCache::GetThumbnailCache(_GUID const &,void * *)
0x180019a58  mov     ebx, eax
0x180019a5a  test    eax, eax
0x180019a5c  js      loc_180019EB4
0x180019a62  movss   xmm6, [rbp+170h+arg_20]
0x180019a6a  maxss   xmm6, [rbp+170h+arg_24]
0x180019a72  mov     [rsp+270h+var_200], rsi
0x180019a77  xorps   xmm0, xmm0
0x180019a7a  movups  [rbp+170h+var_1D8], xmm0
0x180019a7e  movups  [rbp+170h+var_1C8], xmm0
0x180019a82  add     rdi, 40h ; '@'
0x180019a86  mov     rcx, rdi; SRWLock
0x180019a89  call    cs:__imp_AcquireSRWLockExclusive
0x180019a8f  mov     [rsp+270h+var_220], rdi
0x180019a94  mov     rsi, [rsp+270h+var_1F8]
0x180019a99  mov     rax, [rsi]
0x180019a9c  mov     rbx, [rax+68h]
0x180019aa0  lea     rcx, [rsp+270h+var_200]
0x180019aa5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019aaa  mov     [rsp+270h+var_210], r15
0x180019aaf  mov     [rsp+270h+var_208], 0
0x180019ab8  cvttss2si r9, xmm6
0x180019abd  lea     rcx, [rsp+270h+var_200]
0x180019ac2  mov     [rsp+270h+var_238], rcx
0x180019ac7  lea     rcx, _GUID_0000000c_0000_0000_c000_000000000046
0x180019ace  mov     [rsp+270h+var_240], rcx
0x180019ad3  lea     rcx, [rbp+170h+var_1D8]
0x180019ad7  mov     [rsp+270h+var_248], rcx
0x180019adc  mov     [rsp+270h+var_250], r14d; int
0x180019ae1  lea     r8, [rsp+270h+var_210]
0x180019ae6  mov     r15, [rbp+170h+pszPath]
0x180019aea  mov     rdx, r15
0x180019aed  mov     rcx, rsi
0x180019af0  mov     rax, rbx
0x180019af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019af8  mov     ebx, eax
0x180019afa  test    rdi, rdi
0x180019afd  jz      short loc_180019B08
0x180019aff  mov     rcx, rdi; SRWLock
0x180019b02  call    cs:__imp_ReleaseSRWLockExclusive
0x180019b08  test    ebx, ebx
0x180019b0a  jns     loc_180019E91
0x180019b10  xor     r12d, r12d
0x180019b13  test    r14b, 1
0x180019b17  jz      loc_180019D1D
0x180019b1d  mov     ecx, ebx; int
0x180019b1f  call    ?IsExpectedThumbnailError@@YA_NJ@Z; IsExpectedThumbnailError(long)
0x180019b24  test    al, al
0x180019b26  jz      loc_180019EF1
0x180019b2c  mov     [rbp+170h+var_1E0], r12
0x180019b30  lea     rcx, [rbp+170h+var_1E0]
0x180019b34  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019b39  lea     r8, [rbp+170h+var_1E0]; void **
0x180019b3d  mov     rcx, [rsp+270h+var_200]; struct IStream *
0x180019b42  call    ?CreateRandomAccessStreamOverReadOnlySharedMemoryStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; CreateRandomAccessStreamOverReadOnlySharedMemoryStream(IStream *,_GUID const &,void * *)
0x180019b47  mov     ebx, eax
0x180019b49  test    eax, eax
0x180019b4b  js      loc_180019FCE
0x180019b51  movd    xmm6, dword ptr [rbp+170h+var_1C8+4]
0x180019b56  cvtdq2ps xmm6, xmm6
0x180019b59  movd    xmm7, dword ptr [rbp+170h+var_1C8+8]
0x180019b5e  cvtdq2ps xmm7, xmm7
0x180019b61  mov     rdi, [rbp+170h+var_1E0]
0x180019b65  mov     [r13+0], r12
0x180019b69  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019b70  mov     ecx, 50h ; 'P'; unsigned __int64
0x180019b75  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180019b7a  test    rax, rax
0x180019b7d  jz      loc_180019CCD
0x180019b83  mov     rcx, rax; this
0x180019b86  call    ??0CStorageThumbnailResult@@QEAA@XZ; CStorageThumbnailResult::CStorageThumbnailResult(void)
0x180019b8b  mov     rbx, rax
0x180019b8e  mov     [rsp+270h+var_210], rax
0x180019b93  mov     [rsp+270h+var_220], r12
0x180019b98  mov     r8, rdi
0x180019b9b  unpcklps xmm6, xmm7
0x180019b9e  movq    rdx, xmm6
0x180019ba3  mov     rcx, rax
0x180019ba6  call    ?RuntimeClassInitialize@CStorageThumbnailResult@@QEAAJUSize@Foundation@Windows@@PEAUIRandomAccessStream@Streams@Storage@4@@Z; CStorageThumbnailResult::RuntimeClassInitialize(Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStream *)
0x180019bab  mov     edi, eax
0x180019bad  test    eax, eax
0x180019baf  js      loc_180019F0B
0x180019bb5  mov     r8, r13
0x180019bb8  lea     rdx, _GUID_277f0b63_2e83_43bd_8a09_02098e3da243
0x180019bbf  mov     rcx, rbx
0x180019bc2  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIThumbnailResult@ThumbnailCache@Storage@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIThumbnailResult@ThumbnailCache@Storage@Internal@Windows@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Storage::ThumbnailCache::IThumbnailResult,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Storage::ThumbnailCache::IThumbnailResult,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180019bc7  mov     edi, eax
0x180019bc9  test    rbx, rbx
0x180019bcc  jz      short loc_180019BD7
0x180019bce  mov     rcx, rbx
0x180019bd1  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIThumbnailResult@ThumbnailCache@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::ThumbnailCache::IThumbnailResult,Microsoft::WRL::FtmBase>::Release(void)
0x180019bd6  nop
0x180019bd7  test    edi, edi
0x180019bd9  js      loc_180019CD2
0x180019bdf  xor     edx, edx
0x180019be1  lea     rcx, [rbp+170h+var_1B0]
0x180019be5  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180019bea  nop
0x180019beb  mov     rcx, [rbp+170h+var_1E0]
0x180019bef  test    rcx, rcx
0x180019bf2  jz      short loc_180019C05
0x180019bf4  mov     [rbp+170h+var_1E0], r12
0x180019bf8  mov     rax, [rcx]
0x180019bfb  mov     rax, [rax+10h]
0x180019bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c04  nop
0x180019c05  mov     rcx, [rsp+270h+var_200]
0x180019c0a  test    rcx, rcx
0x180019c0d  jz      short loc_180019C21
0x180019c0f  mov     [rsp+270h+var_200], r12
0x180019c14  mov     rax, [rcx]
0x180019c17  mov     rax, [rax+10h]
0x180019c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c20  nop
0x180019c21  mov     rcx, [rsp+270h+var_1F8]
0x180019c26  test    rcx, rcx
0x180019c29  jz      short loc_180019C3D
0x180019c2b  mov     [rsp+270h+var_1F8], r12
0x180019c30  mov     rax, [rcx]
0x180019c33  mov     rax, [rax+10h]
0x180019c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c3c  nop
0x180019c3d  mov     ebx, r12d
0x180019c40  lea     rax, ??_7OptimizedGetThumbnail@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::OptimizedGetThumbnail::`vftable'
0x180019c47  mov     [rbp+170h+var_1B0], rax
0x180019c4b  lea     rcx, [rbp+170h+var_1B0]
0x180019c4f  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180019c54  lea     rcx, [rbp+170h+var_90]; this
0x180019c5b  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180019c60  lea     rcx, [rbp+170h+var_98]
0x180019c67  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x180019c6c  lea     rcx, [rbp+170h+var_1A8]
0x180019c70  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x180019c75  mov     eax, ebx
0x180019c77  mov     rcx, [rbp+170h+var_60]
0x180019c7e  xor     rcx, rsp; StackCookie
0x180019c81  call    __security_check_cookie
0x180019c86  lea     r11, [rsp+270h+var_30]
0x180019c8e  mov     rbx, [r11+58h]
0x180019c92  movaps  xmm6, xmmword ptr [r11-10h]
0x180019c97  movaps  xmm7, xmmword ptr [r11-20h]
0x180019c9c  mov     rsp, r11
0x180019c9f  pop     r15
0x180019ca1  pop     r14
0x180019ca3  pop     r13
0x180019ca5  pop     r12
0x180019ca7  pop     rdi
0x180019ca8  pop     rsi
0x180019ca9  pop     rbp
0x180019caa  retn
0x180019cab  mov     ebx, 80070057h
0x180019cb0  mov     edx, 3E5h; void *
0x180019cb5  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180019cbc  mov     r9d, ebx; char *
0x180019cbf  mov     rcx, [rbp+178h]; this
0x180019cc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ccb  jmp     short loc_180019C75
0x180019ccd  mov     edi, 8007000Eh
0x180019cd2  mov     rcx, [rbp+178h]; this
0x180019cd9  mov     r9d, edi; char *
0x180019cdc  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180019ce3  mov     edx, 431h; void *
0x180019ce8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ced  nop
0x180019cee  lea     rcx, [rbp+170h+var_1E0]
0x180019cf2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019cf7  mov     ebx, edi
0x180019cf9  lea     rcx, [rsp+270h+var_200]
0x180019cfe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019d03  nop
0x180019d04  lea     rcx, [rsp+270h+var_1F8]
0x180019d09  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019d0e  nop
0x180019d0f  lea     rcx, [rbp+170h+var_1B0]; this
0x180019d13  call    ??1OptimizedGetThumbnail@ThumbnailCacheTelemetry@@QEAA@XZ; ThumbnailCacheTelemetry::OptimizedGetThumbnail::~OptimizedGetThumbnail(void)
0x180019d18  jmp     loc_180019C75
0x180019d1d  test    ebx, ebx
0x180019d1f  jns     loc_180019F37
0x180019d25  lea     eax, [rbx+7FFCFFFEh]
0x180019d2b  cmp     eax, 1
0x180019d2e  ja      loc_180019B1D
0x180019d34  mov     [rbp+170h+pszPath], r12
0x180019d38  lea     rcx, [rbp+170h+pszPath]
0x180019d3c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019d41  lea     r9, [rbp+170h+pszPath]; ppv
0x180019d45  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180019d4c  xor     edx, edx; pbc
0x180019d4e  mov     rcx, r15; pszPath
0x180019d51  call    cs:__imp_SHCreateItemFromParsingName
0x180019d57  mov     ebx, eax
0x180019d59  test    eax, eax
0x180019d5b  js      loc_180019F46
0x180019d61  mov     [rbp+170h+var_1E8], r12
0x180019d65  mov     rbx, [rsp+270h+var_1F8]
0x180019d6a  mov     rax, [rbx]
0x180019d6d  mov     rsi, [rax]
0x180019d70  lea     rcx, [rbp+170h+var_1E8]
0x180019d74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019d79  lea     r8, [rbp+170h+var_1E8]
0x180019d7d  lea     rdx, _GUID_2d3e7f31_91d1_4fb8_a7ea_fa4011bdbcda
0x180019d84  mov     rcx, rbx
0x180019d87  mov     rax, rsi
0x180019d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d8f  mov     ebx, eax
0x180019d91  test    eax, eax
0x180019d93  js      loc_180019F66
0x180019d99  mov     rcx, rdi; SRWLock
0x180019d9c  call    cs:__imp_AcquireSRWLockExclusive
0x180019da2  mov     [rsp+270h+var_220], rdi
0x180019da7  mov     rbx, [rbp+170h+var_1E8]
0x180019dab  mov     rax, [rbx]
0x180019dae  mov     rsi, [rax+58h]
0x180019db2  mov     rcx, [rsp+270h+var_200]
0x180019db7  test    rcx, rcx
0x180019dba  jz      short loc_180019DCE
0x180019dbc  mov     [rsp+270h+var_200], r12
0x180019dc1  mov     rax, [rcx]
0x180019dc4  mov     rax, [rax+10h]
0x180019dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dcd  nop
0x180019dce  lea     rax, [rsp+270h+var_200]
0x180019dd3  mov     [rsp+270h+var_238], rax
0x180019dd8  lea     rax, _GUID_0000000c_0000_0000_c000_000000000046
0x180019ddf  mov     [rsp+270h+var_240], rax
0x180019de4  lea     rax, [rbp+170h+var_1D8]
0x180019de8  mov     [rsp+270h+var_248], rax
0x180019ded  mov     qword ptr [rsp+270h+var_250], r12; int
0x180019df2  mov     r9d, r14d
0x180019df5  cvttss2si r8, xmm6
0x180019dfa  mov     rdx, [rbp+170h+pszPath]
0x180019dfe  mov     rcx, rbx
0x180019e01  mov     rax, rsi
0x180019e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e09  mov     ebx, eax
0x180019e0b  mov     ecx, eax
0x180019e0d  call    ShouldSuppressWilErrorTelemetry
0x180019e12  test    al, al
0x180019e14  jnz     short loc_180019E66
0x180019e16  test    ecx, ecx
0x180019e18  js      loc_180019F86
0x180019e1e  test    rdi, rdi
0x180019e21  jz      short loc_180019E2D
0x180019e23  mov     rcx, rdi; SRWLock
0x180019e26  call    cs:__imp_ReleaseSRWLockExclusive
0x180019e2c  nop
0x180019e2d  mov     rcx, [rbp+170h+var_1E8]
  ... truncated ...
```
