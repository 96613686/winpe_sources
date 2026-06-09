# CThumbnailCacheInternal::GetThumbnail(HSTRING__ *,unsigned __int64,Windows::Internal::ThumbnailCache::ThumbnailFlags,Windows::Foundation::Size,Windows::Internal::ThumbnailCache::IThumbnailResult * *)

- ea: `0x18003d6b0`
- end: `0x18003db4f`
- name: `?GetThumbnail@CThumbnailCacheInternal@@UEAAJPEAUHSTRING__@@_KW4ThumbnailFlags@ThumbnailCache@Internal@Windows@@USize@Foundation@6@PEAPEAUIThumbnailResult@456@@Z`
- size: `1183`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x18000c67c`
- `0x18000e280`
- `0x18000e4b0`
- `0x180010388`
- `0x180019750`
- `0x18001a0e8`
- `0x18001a5c0`
- `0x18001a694`
- `0x18001aac4`
- `0x18002a508`
- `0x180034cb8`
- `0x180035830`
- `0x18003d6b0`
- `0x18003db94`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d882`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d9d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003da71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d882`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d9d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003da71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d745`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d745`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18003d8cc`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18003d8cc`

## string_xrefs

- `0x18003d714`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003d7a5`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003d8e2`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003d93d`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003da51`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003da8f`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CThumbnailCacheInternal::GetThumbnail(
        CThumbnailCacheInternal *a1,
        HSTRING a2,
        unsigned __int64 a3,
        char a4,
        __int64 a5,
        _QWORD *a6)
{
  bool v10; // bl
  int v11; // ebx
  __int64 v12; // rdx
  const WCHAR *StringRawBuffer; // r12
  const struct _GUID *v14; // rdx
  int ThumbnailCache; // eax
  float v16; // xmm6_4
  unsigned int v17; // r14d
  char *v18; // r13
  void *v19; // rdi
  __int64 (__fastcall *v20)(void *, const WCHAR *, _QWORD *, _QWORD); // rbx
  HRESULT v21; // eax
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, void *, _QWORD, _QWORD); // rbx
  int v25; // ecx
  __int64 v26; // rcx
  const struct _GUID *v27; // rdx
  int v28; // eax
  unsigned __int64 v29; // r9
  __int64 v30; // rdx
  int v31; // eax
  int v33; // [rsp+28h] [rbp-E0h]
  int v34; // [rsp+28h] [rbp-E0h]
  PSRWLOCK SRWLock[2]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v36[2]; // [rsp+68h] [rbp-A0h] BYREF
  struct IStream *v37; // [rsp+78h] [rbp-90h] BYREF
  void *v38; // [rsp+80h] [rbp-88h] BYREF
  void *ppv; // [rsp+88h] [rbp-80h] BYREF
  __int64 v40; // [rsp+90h] [rbp-78h] BYREF
  void *v41; // [rsp+98h] [rbp-70h] BYREF
  __int128 v42; // [rsp+A0h] [rbp-68h]
  __int128 v43; // [rsp+B0h] [rbp-58h]
  _QWORD v44[42]; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a6 = 0;
  v10 = IsCallerAllowed((__int64)a1, (__int64)a2);
  if ( v10 )
  {
    if ( !a3 )
    {
      v11 = -2147024809;
      v12 = 759;
      goto LABEL_3;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v44,
      "OptimizedGetThumbnail");
    v44[0] = &ThumbnailCacheTelemetry::OptimizedGetThumbnail::`vftable';
    ThumbnailCacheTelemetry::OptimizedGetThumbnail::StartActivity(
      (ThumbnailCacheTelemetry::OptimizedGetThumbnail *)v44,
      v10,
      a3);
    v41 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    ThumbnailCache = CThumbnailCacheInternal::GetThumbnailCache(a1, v14, &v41);
    v11 = ThumbnailCache;
    if ( ThumbnailCache < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2FC,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)(unsigned int)ThumbnailCache,
        v33);
LABEL_43:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
      ThumbnailCacheTelemetry::OptimizedGetThumbnail::~OptimizedGetThumbnail((ThumbnailCacheTelemetry::OptimizedGetThumbnail *)v44);
      return (unsigned int)v11;
    }
    v16 = fmaxf(*(float *)&a5, *((float *)&a5 + 1));
    v17 = ((a4 & 1) + 0x2000) | 0x40;
    if ( (a4 & 2) == 0 )
      v17 = (a4 & 1) + 0x2000;
    v37 = 0;
    v42 = 0;
    v43 = 0;
    v38 = 0;
    v18 = (char *)a1 + 64;
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, (char *)a1 + 64);
    v19 = v41;
    v20 = *(__int64 (__fastcall **)(void *, const WCHAR *, _QWORD *, _QWORD))(*(_QWORD *)v41 + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    v36[0] = a3;
    v36[1] = 0;
    v34 = v17;
    v11 = v20(v19, StringRawBuffer, v36, (unsigned int)(int)v16);
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
    if ( (v17 & 1) != 0 || (v11 < 0 || (v42 & 1) == 0) && (unsigned int)(v11 + 2147287038) > 1 )
    {
LABEL_28:
      if ( !IsExpectedThumbnailError(v11) )
      {
        if ( (unsigned __int8)ShouldSuppressWilErrorTelemetry(v26) )
        {
          wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v44, 0);
          if ( v11 < 0 )
            goto LABEL_19;
        }
        else if ( v11 < 0 )
        {
          v29 = (unsigned int)v11;
          v30 = 822;
LABEL_39:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v30,
            (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
            (const char *)v29,
            v34);
          goto LABEL_19;
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      v28 = CreateRandomAccessStreamOverReadOnlySharedMemoryStream(v37, v27, &v38);
      v11 = v28;
      if ( v28 >= 0 )
      {
        *(float *)SRWLock = (float)SDWORD1(v43);
        *((float *)SRWLock + 1) = (float)SDWORD2(v43);
        v36[0] = v38;
        v31 = Microsoft::WRL::Details::MakeAndInitialize<CThumbnailResult,Windows::Internal::ThumbnailCache::IThumbnailResult,Windows::Foundation::Size const &,Windows::Storage::Streams::IRandomAccessStream *>(
                a6,
                SRWLock,
                v36);
        v11 = v31;
        if ( v31 >= 0 )
        {
          wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v44, 0);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
          v11 = 0;
          goto LABEL_43;
        }
        v29 = (unsigned int)v31;
        v30 = 829;
      }
      else
      {
        v29 = (unsigned int)v28;
        v30 = 825;
      }
      goto LABEL_39;
    }
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v21 = SHCreateItemFromParsingName(StringRawBuffer, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
    v11 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x316,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)(unsigned int)v21,
        v17);
LABEL_18:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
LABEL_19:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
      goto LABEL_43;
    }
    v40 = 0;
    v22 = Microsoft::WRL::ComPtr<IThumbnailCachePrivate>::As<IThumbnailCache3>(&v41, &v40);
    v11 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x319,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)(unsigned int)v22,
        v17);
LABEL_22:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
      goto LABEL_18;
    }
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, v18);
    v23 = v40;
    v24 = *(__int64 (__fastcall **)(__int64, void *, _QWORD, _QWORD))(*(_QWORD *)v40 + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    v34 = 0;
    v11 = v24(v23, ppv, (unsigned int)(int)v16, v17);
    if ( (unsigned __int8)ShouldSuppressWilErrorTelemetry((unsigned int)v11) )
    {
      if ( v25 >= 0 )
      {
LABEL_25:
        if ( SRWLock[0] )
          ReleaseSRWLockExclusive(SRWLock[0]);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
        goto LABEL_28;
      }
    }
    else
    {
      if ( v11 >= 0 )
        goto LABEL_25;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x325,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)(unsigned int)v11,
        0);
    }
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
    goto LABEL_22;
  }
  v11 = -2147024891;
  v12 = 758;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
    (const char *)(unsigned int)v11,
    v33);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003d6b0  mov     rax, rsp
0x18003d6b3  mov     [rax+20h], rbx
0x18003d6b7  push    rbp
0x18003d6b8  push    rsi
0x18003d6b9  push    rdi
0x18003d6ba  push    r12
0x18003d6bc  push    r13
0x18003d6be  push    r14
0x18003d6c0  push    r15
0x18003d6c2  lea     rbp, [rax-168h]
0x18003d6c9  sub     rsp, 230h
0x18003d6d0  movaps  xmmword ptr [rax-48h], xmm6
0x18003d6d4  mov     rax, cs:__security_cookie
0x18003d6db  xor     rax, rsp
0x18003d6de  mov     [rbp+160h+var_50], rax
0x18003d6e5  mov     r13d, r9d
0x18003d6e8  mov     rsi, r8
0x18003d6eb  mov     r14, rdx
0x18003d6ee  mov     rdi, rcx
0x18003d6f1  mov     r15, [rbp+160h+arg_28]
0x18003d6f8  mov     qword ptr [r15], 0
0x18003d6ff  call    ?IsCallerAllowed@@YA_N_N@Z; IsCallerAllowed(bool)
0x18003d704  mov     bl, al
0x18003d706  test    al, al
0x18003d708  jnz     short loc_18003D72F
0x18003d70a  mov     ebx, 80070005h
0x18003d70f  mov     edx, 2F6h; void *
0x18003d714  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003d71b  mov     r9d, ebx; char *
0x18003d71e  mov     rcx, [rbp+168h]; this
0x18003d725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d72a  jmp     loc_18003DB1E
0x18003d72f  test    rsi, rsi
0x18003d732  jnz     short loc_18003D740
0x18003d734  mov     ebx, 80070057h
0x18003d739  mov     edx, 2F7h
0x18003d73e  jmp     short loc_18003D714
0x18003d740  xor     edx, edx; length
0x18003d742  mov     rcx, r14; string
0x18003d745  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d74b  mov     r12, rax
0x18003d74e  lea     rdx, aOptimizedgetth; "OptimizedGetThumbnail"
0x18003d755  lea     rcx, [rbp+160h+var_1A0]
0x18003d759  call    ??0?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003d75e  lea     rcx, ??_7OptimizedGetThumbnail@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::OptimizedGetThumbnail::`vftable'
0x18003d765  mov     [rbp+160h+var_1A0], rcx
0x18003d769  mov     r8, rsi; unsigned __int64
0x18003d76c  mov     dl, bl; bool
0x18003d76e  lea     rcx, [rbp+160h+var_1A0]; this
0x18003d772  call    ?StartActivity@OptimizedGetThumbnail@ThumbnailCacheTelemetry@@QEAAX_N_K@Z; ThumbnailCacheTelemetry::OptimizedGetThumbnail::StartActivity(bool,unsigned __int64)
0x18003d777  nop
0x18003d778  mov     [rbp+160h+var_1D0], 0
0x18003d780  lea     rcx, [rbp+160h+var_1D0]
0x18003d784  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d789  lea     r8, [rbp+160h+var_1D0]; void **
0x18003d78d  mov     rcx, rdi; this
0x18003d790  call    ?GetThumbnailCache@CThumbnailCacheInternal@@AEAAJAEBU_GUID@@PEAPEAX@Z; CThumbnailCacheInternal::GetThumbnailCache(_GUID const &,void * *)
0x18003d795  mov     ebx, eax
0x18003d797  test    eax, eax
0x18003d799  jns     short loc_18003D7BB
0x18003d79b  mov     rcx, [rbp+168h]; this
0x18003d7a2  mov     r9d, eax; char *
0x18003d7a5  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003d7ac  mov     edx, 2FCh; void *
0x18003d7b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d7b6  jmp     loc_18003DB0B
0x18003d7bb  movss   xmm6, [rbp+160h+arg_20]
0x18003d7c3  maxss   xmm6, [rbp+160h+arg_24]
0x18003d7cb  mov     eax, r13d
0x18003d7ce  and     eax, 1
0x18003d7d1  add     eax, 2000h
0x18003d7d6  mov     r14d, eax
0x18003d7d9  or      r14d, 40h
0x18003d7dd  test    r13b, 2
0x18003d7e1  cmovz   r14d, eax
0x18003d7e5  mov     [rsp+260h+var_1F0], 0
0x18003d7ee  xorps   xmm0, xmm0
0x18003d7f1  movups  [rbp+160h+var_1C8], xmm0
0x18003d7f5  movups  [rbp+160h+var_1B8], xmm0
0x18003d7f9  mov     [rsp+260h+var_1E8], 0
0x18003d802  lea     r13, [rdi+40h]
0x18003d806  mov     rdx, r13
0x18003d809  lea     rcx, [rsp+260h+SRWLock]
0x18003d80e  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18003d813  nop
0x18003d814  mov     rdi, [rbp+160h+var_1D0]
0x18003d818  mov     rax, [rdi]
0x18003d81b  mov     rbx, [rax+68h]
0x18003d81f  lea     rcx, [rsp+260h+var_1F0]
0x18003d824  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d829  mov     [rsp+260h+var_200], rsi
0x18003d82e  mov     [rsp+260h+var_1F8], 0
0x18003d837  cvttss2si rsi, xmm6
0x18003d83c  lea     rax, [rsp+260h+var_1F0]
0x18003d841  mov     [rsp+260h+var_228], rax
0x18003d846  lea     rax, _GUID_0000000c_0000_0000_c000_000000000046
0x18003d84d  mov     [rsp+260h+var_230], rax
0x18003d852  lea     rax, [rbp+160h+var_1C8]
0x18003d856  mov     [rsp+260h+var_238], rax
0x18003d85b  mov     [rsp+260h+var_240], r14d; int
0x18003d860  mov     r9d, esi
0x18003d863  lea     r8, [rsp+260h+var_200]
0x18003d868  mov     rdx, r12
0x18003d86b  mov     rcx, rdi
0x18003d86e  mov     rax, rbx
0x18003d871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d876  mov     ebx, eax
0x18003d878  mov     rcx, [rsp+260h+SRWLock]; SRWLock
0x18003d87d  test    rcx, rcx
0x18003d880  jz      short loc_18003D888
0x18003d882  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d888  test    r14b, 1
0x18003d88c  jnz     loc_18003D9F3
0x18003d892  test    ebx, ebx
0x18003d894  js      short loc_18003D89C
0x18003d896  test    byte ptr [rbp+160h+var_1C8], 1
0x18003d89a  jnz     short loc_18003D8AB
0x18003d89c  lea     eax, [rbx+7FFCFFFEh]
0x18003d8a2  cmp     eax, 1
0x18003d8a5  ja      loc_18003D9F3
0x18003d8ab  mov     [rbp+160h+ppv], 0
0x18003d8b3  lea     rcx, [rbp+160h+ppv]
0x18003d8b7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d8bc  lea     r9, [rbp+160h+ppv]; ppv
0x18003d8c0  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18003d8c7  xor     edx, edx; pbc
0x18003d8c9  mov     rcx, r12; pszPath
0x18003d8cc  call    cs:__imp_SHCreateItemFromParsingName
0x18003d8d2  mov     ebx, eax
0x18003d8d4  test    eax, eax
0x18003d8d6  jns     short loc_18003D918
0x18003d8d8  mov     rcx, [rbp+168h]; this
0x18003d8df  mov     r9d, eax; char *
0x18003d8e2  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003d8e9  mov     edx, 316h; void *
0x18003d8ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d8f3  nop
0x18003d8f4  lea     rcx, [rbp+160h+ppv]
0x18003d8f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d8fd  nop
0x18003d8fe  lea     rcx, [rsp+260h+var_1E8]
0x18003d903  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d908  nop
0x18003d909  lea     rcx, [rsp+260h+var_1F0]
0x18003d90e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d913  jmp     loc_18003DB0B
0x18003d918  mov     [rbp+160h+var_1D8], 0
0x18003d920  lea     rdx, [rbp+160h+var_1D8]
0x18003d924  lea     rcx, [rbp+160h+var_1D0]
0x18003d928  call    ??$As@UIThumbnailCache3@@@?$ComPtr@UIThumbnailCachePrivate@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIThumbnailCache3@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IThumbnailCachePrivate>::As<IThumbnailCache3>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IThumbnailCache3>>)
0x18003d92d  mov     ebx, eax
0x18003d92f  test    eax, eax
0x18003d931  jns     short loc_18003D95A
0x18003d933  mov     rcx, [rbp+168h]; this
0x18003d93a  mov     r9d, eax; char *
0x18003d93d  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003d944  mov     edx, 319h; void *
0x18003d949  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d94e  nop
0x18003d94f  lea     rcx, [rbp+160h+var_1D8]
0x18003d953  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d958  jmp     short loc_18003D8F4
0x18003d95a  mov     rdx, r13
0x18003d95d  lea     rcx, [rsp+260h+SRWLock]
0x18003d962  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18003d967  nop
0x18003d968  mov     rdi, [rbp+160h+var_1D8]
0x18003d96c  mov     rax, [rdi]
0x18003d96f  mov     rbx, [rax+58h]
0x18003d973  lea     rcx, [rsp+260h+var_1F0]
0x18003d978  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d97d  lea     rax, [rsp+260h+var_1F0]
0x18003d982  mov     [rsp+260h+var_228], rax
0x18003d987  lea     rax, _GUID_0000000c_0000_0000_c000_000000000046
0x18003d98e  mov     [rsp+260h+var_230], rax
0x18003d993  lea     rax, [rbp+160h+var_1C8]
0x18003d997  mov     [rsp+260h+var_238], rax
0x18003d99c  mov     qword ptr [rsp+260h+var_240], 0; int
0x18003d9a5  mov     r9d, r14d
0x18003d9a8  mov     r8d, esi
0x18003d9ab  mov     rdx, [rbp+160h+ppv]
0x18003d9af  mov     rcx, rdi
0x18003d9b2  mov     rax, rbx
0x18003d9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9ba  mov     ebx, eax
0x18003d9bc  mov     ecx, eax
0x18003d9be  call    ShouldSuppressWilErrorTelemetry
0x18003d9c3  test    al, al
0x18003d9c5  jz      short loc_18003DA43
0x18003d9c7  test    ecx, ecx
0x18003d9c9  js      loc_18003DA63
0x18003d9cf  mov     rcx, [rsp+260h+SRWLock]; SRWLock
0x18003d9d4  test    rcx, rcx
0x18003d9d7  jz      short loc_18003D9E0
0x18003d9d9  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d9df  nop
0x18003d9e0  lea     rcx, [rbp+160h+var_1D8]
0x18003d9e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d9e9  nop
0x18003d9ea  lea     rcx, [rbp+160h+ppv]
0x18003d9ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d9f3  mov     ecx, ebx; int
0x18003d9f5  call    ?IsExpectedThumbnailError@@YA_NJ@Z; IsExpectedThumbnailError(long)
0x18003d9fa  test    al, al
0x18003d9fc  jnz     short loc_18003DA1A
0x18003d9fe  call    ShouldSuppressWilErrorTelemetry
0x18003da03  test    al, al
0x18003da05  jz      short loc_18003DA7C
0x18003da07  xor     edx, edx
0x18003da09  lea     rcx, [rbp+160h+var_1A0]
0x18003da0d  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003da12  test    ebx, ebx
0x18003da14  js      loc_18003D8FE
0x18003da1a  lea     rcx, [rsp+260h+var_1E8]
0x18003da1f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003da24  lea     r8, [rsp+260h+var_1E8]; void **
0x18003da29  mov     rcx, [rsp+260h+var_1F0]; struct IStream *
0x18003da2e  call    ?CreateRandomAccessStreamOverReadOnlySharedMemoryStream@@YAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; CreateRandomAccessStreamOverReadOnlySharedMemoryStream(IStream *,_GUID const &,void * *)
0x18003da33  mov     ebx, eax
0x18003da35  test    eax, eax
0x18003da37  jns     short loc_18003DAA0
0x18003da39  mov     r9d, eax
0x18003da3c  mov     edx, 339h
0x18003da41  jmp     short loc_18003DA88
0x18003da43  test    ebx, ebx
0x18003da45  jns     short loc_18003D9CF
0x18003da47  mov     rcx, [rbp+168h]; this
0x18003da4e  mov     r9d, ebx; char *
0x18003da51  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003da58  mov     edx, 325h; void *
0x18003da5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003da62  nop
0x18003da63  mov     rcx, [rsp+260h+SRWLock]; SRWLock
0x18003da68  test    rcx, rcx
0x18003da6b  jz      loc_18003D94F
0x18003da71  call    cs:__imp_ReleaseSRWLockExclusive
0x18003da77  jmp     loc_18003D94F
0x18003da7c  test    ebx, ebx
0x18003da7e  jns     short loc_18003DA1A
0x18003da80  mov     r9d, ebx; char *
0x18003da83  mov     edx, 336h; void *
0x18003da88  mov     rcx, [rbp+168h]; this
0x18003da8f  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003da96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003da9b  jmp     loc_18003D8FE
0x18003daa0  movd    xmm0, dword ptr [rbp+160h+var_1B8+4]
0x18003daa5  cvtdq2ps xmm0, xmm0
0x18003daa8  movss   dword ptr [rsp+260h+SRWLock], xmm0
0x18003daae  movd    xmm1, dword ptr [rbp+160h+var_1B8+8]
0x18003dab3  cvtdq2ps xmm1, xmm1
0x18003dab6  movss   dword ptr [rsp+260h+SRWLock+4], xmm1
0x18003dabc  mov     rax, [rsp+260h+var_1E8]
0x18003dac1  mov     [rsp+260h+var_200], rax
0x18003dac6  lea     r8, [rsp+260h+var_200]
0x18003dacb  lea     rdx, [rsp+260h+SRWLock]
0x18003dad0  mov     rcx, r15
0x18003dad3  call    ??$MakeAndInitialize@VCThumbnailResult@@UIThumbnailResult@ThumbnailCache@Internal@Windows@@AEBUSize@Foundation@5@PEAUIRandomAccessStream@Streams@Storage@5@@Details@WRL@Microsoft@@YAJPEAPEAUIThumbnailResult@ThumbnailCache@Internal@Windows@@AEBUSize@Foundation@6@$$QEAPEAUIRandomAccessStream@Streams@Storage@6@@Z; Microsoft::WRL::Details::MakeAndInitialize<CThumbnailResult,Windows::Internal::ThumbnailCache::IThumbnailResult,Windows::Foundation::Size const &,Windows::Storage::Streams::IRandomAccessStream *>(Windows::Internal::ThumbnailCache::IThumbnailResult * *,Windows::Foundation::Size const &,Windows::Storage::Streams::IRandomAccessStream * &&)
0x18003dad8  mov     ebx, eax
0x18003dada  test    eax, eax
0x18003dadc  jns     short loc_18003DAE8
0x18003dade  mov     r9d, eax
0x18003dae1  mov     edx, 33Dh
0x18003dae6  jmp     short loc_18003DA88
0x18003dae8  xor     edx, edx
0x18003daea  lea     rcx, [rbp+160h+var_1A0]
0x18003daee  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003daf3  nop
0x18003daf4  lea     rcx, [rsp+260h+var_1E8]
0x18003daf9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003dafe  nop
0x18003daff  lea     rcx, [rsp+260h+var_1F0]
0x18003db04  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003db09  xor     ebx, ebx
0x18003db0b  lea     rcx, [rbp+160h+var_1D0]
0x18003db0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003db14  nop
0x18003db15  lea     rcx, [rbp+160h+var_1A0]; this
0x18003db19  call    ??1OptimizedGetThumbnail@ThumbnailCacheTelemetry@@QEAA@XZ; ThumbnailCacheTelemetry::OptimizedGetThumbnail::~OptimizedGetThumbnail(void)
0x18003db1e  mov     eax, ebx
0x18003db20  mov     rcx, [rbp+160h+var_50]
0x18003db27  xor     rcx, rsp; StackCookie
0x18003db2a  call    __security_check_cookie
0x18003db2f  lea     r11, [rsp+260h+var_30]
0x18003db37  mov     rbx, [r11+58h]
0x18003db3b  movaps  xmm6, xmmword ptr [r11-10h]
0x18003db40  mov     rsp, r11
0x18003db43  pop     r15
0x18003db45  pop     r14
0x18003db47  pop     r13
0x18003db49  pop     r12
0x18003db4b  pop     rdi
0x18003db4c  pop     rsi
0x18003db4d  pop     rbp
0x18003db4e  retn
```
