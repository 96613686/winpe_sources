# CThumbnailStreamCache::SetThumbnailStream(ushort const *,unsigned __int64,tagSIZE,IStream *)

- ea: `0x18001b1a0`
- end: `0x18001b5e5`
- name: `?SetThumbnailStream@CThumbnailStreamCache@@UEAAJPEBG_KUtagSIZE@@PEAUIStream@@@Z`
- size: `1093`
- prototype: `__int64 __fastcall(CThumbnailStreamCache *this, const unsigned __int16 *, unsigned __int64, struct tagSIZE, struct IStream *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x18000e280`
- `0x18000e4b0`
- `0x18000ed30`
- `0x18000ed88`
- `0x18000edf0`
- `0x18000f234`
- `0x18001b1a0`
- `0x18001b5ec`
- `0x18001ba34`
- `0x1800341c0`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b373`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b5de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b373`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b5de`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x18001b32e`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOverStream` at `0x18001b32e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b2c7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001b2c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b392`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b392`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18001b243`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18001b243`

## string_xrefs

- `0x18001b3d4`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18001b4d8`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18001b515`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18001b57f`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18001b59c`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CThumbnailStreamCache::SetThumbnailStream(
        CThumbnailStreamCache *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3,
        struct tagSIZE a4,
        struct IStream *a5)
{
  LONG cx; // ebx
  LONG cy; // r15d
  HRESULT v10; // eax
  int v11; // edi
  int v12; // eax
  void *v13; // rcx
  __m128 v14; // xmm6
  __m128 v15; // xmm7
  int RandomAccessStreamOverStream; // eax
  __int64 *v17; // rbx
  __int64 v18; // r15
  unsigned __int64 v19; // rdx
  int v20; // edi
  HRESULT v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  void *v27; // rcx
  int v28; // [rsp+28h] [rbp-E0h]
  int v29; // [rsp+28h] [rbp-E0h]
  PROPERTYKEY v30; // [rsp+38h] [rbp-D0h] BYREF
  int v31[2]; // [rsp+58h] [rbp-B0h] BYREF
  void *ppv; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+68h] [rbp-A0h] BYREF
  HSTRING_HEADER pvar; // [rsp+70h] [rbp-98h] BYREF
  HSTRING string; // [rsp+88h] [rbp-80h] BYREF
  void **v36; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v37[272]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v38[8]; // [rsp+1B0h] [rbp+A8h] BYREF
  _BYTE v39[48]; // [rsp+1B8h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+260h] [rbp+158h]

  cx = a4.cx;
  cy = a4.cy;
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v36,
    "SetThumbnailStream");
  v36 = &ThumbnailCacheTelemetry::SetThumbnailStream::`vftable';
  ThumbnailCacheTelemetry::SetThumbnailStream::StartActivity((ThumbnailCacheTelemetry::SetThumbnailStream *)&v36, a3);
  if ( a3 )
    goto LABEL_10;
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v10 = SHCreateItemFromParsingName(a2, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D3,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v10,
      v28);
LABEL_36:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    ThumbnailCacheTelemetry::SetThumbnailStream::~SetThumbnailStream((ThumbnailCacheTelemetry::SetThumbnailStream *)&v36);
    return (unsigned int)v11;
  }
  v33 = 0;
  v12 = wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v33, ppv);
  v11 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D5,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v12,
      v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    v27 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    goto LABEL_20;
  }
  LOWORD(pvar.Reserved.Reserved1) = 0;
  v30 = PKEY_ThumbnailCacheId;
  v11 = (*(__int64 (__fastcall **)(__int64, PROPERTYKEY *, HSTRING_HEADER *))(*(_QWORD *)v33 + 40LL))(v33, &v30, &pvar);
  if ( v11 >= 0 )
  {
    if ( LOWORD(pvar.Reserved.Reserved1) )
    {
      if ( LOWORD(pvar.Reserved.Reserved1) == 21 )
        a3 = *(_QWORD *)&pvar.Reserved.Reserved2[8];
      else
        v11 = -2147352571;
    }
    else
    {
      v11 = -2147023728;
    }
  }
  PropVariantClear(&pvar.Reserved.Reserved1);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D6,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v11,
      v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    goto LABEL_36;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  v13 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
  }
LABEL_10:
  v14 = (__m128)COERCE_UNSIGNED_INT((float)cx);
  v15 = (__m128)COERCE_UNSIGNED_INT((float)cy);
  *(_QWORD *)v31 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v31);
  RandomAccessStreamOverStream = CreateRandomAccessStreamOverStream(
                                   a5,
                                   0,
                                   &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
                                   v31);
  v11 = RandomAccessStreamOverStream;
  if ( RandomAccessStreamOverStream < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4DB,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)RandomAccessStreamOverStream,
      v28);
    v26 = *(_QWORD *)v31;
    if ( *(_QWORD *)v31 )
    {
      *(_QWORD *)v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    goto LABEL_20;
  }
  v17 = (__int64 *)*((_QWORD *)this + 6);
  v18 = *v17;
  string = 0;
  v19 = -1;
  do
    ++v19;
  while ( a2[v19] );
  if ( v19 > 0xFFFFFFFF || (int)v19 + 1 < (unsigned int)v19 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v20 = v31[0];
  v21 = WindowsCreateStringReference(a2, v19, &pvar, &string);
  if ( v21 < 0 )
  {
    RaiseException(v21, 1u, 0, 0);
    JUMPOUT(0x18001B5E4LL);
  }
  v29 = v20;
  v22 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, unsigned __int64, unsigned __int64))(v18 + 56))(
          v17,
          string,
          a3,
          _mm_unpacklo_ps(v14, v15).m128_u64[0]);
  v11 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4DC,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v22,
      v29);
    v23 = *(_QWORD *)v31;
    if ( *(_QWORD *)v31 )
    {
      *(_QWORD *)v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
LABEL_20:
    v36 = &ThumbnailCacheTelemetry::SetThumbnailStream::`vftable';
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v36);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v39);
    wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v38);
    wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v37);
    return (unsigned int)v11;
  }
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v36, 0);
  v25 = *(_QWORD *)v31;
  if ( *(_QWORD *)v31 )
  {
    *(_QWORD *)v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v36 = &ThumbnailCacheTelemetry::SetThumbnailStream::`vftable';
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v36);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v39);
  wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v38);
  wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v37);
  return 0;
}

```

## disassembly

```asm
0x18001b1a0  mov     rax, rsp
0x18001b1a3  push    rbp
0x18001b1a4  push    rbx
0x18001b1a5  push    rsi
0x18001b1a6  push    rdi
0x18001b1a7  push    r12
0x18001b1a9  push    r13
0x18001b1ab  push    r14
0x18001b1ad  push    r15
0x18001b1af  lea     rbp, [rax-158h]
0x18001b1b6  sub     rsp, 218h
0x18001b1bd  movaps  xmmword ptr [rax-58h], xmm6
0x18001b1c1  movaps  xmmword ptr [rax-68h], xmm7
0x18001b1c5  mov     rax, cs:__security_cookie
0x18001b1cc  xor     rax, rsp
0x18001b1cf  mov     [rbp+150h+var_70], rax
0x18001b1d6  mov     rbx, r9
0x18001b1d9  mov     rsi, r8
0x18001b1dc  mov     r14, rdx
0x18001b1df  mov     r13, rcx
0x18001b1e2  mov     r15, r9
0x18001b1e5  shr     r15, 20h
0x18001b1e9  mov     r12, [rbp+150h+arg_20]
0x18001b1f0  lea     rdx, aSetthumbnailst; "SetThumbnailStream"
0x18001b1f7  lea     rcx, [rbp+150h+var_1C0]
0x18001b1fb  call    ??0?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001b200  lea     rax, ??_7SetThumbnailStream@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::SetThumbnailStream::`vftable'
0x18001b207  mov     [rbp+150h+var_1C0], rax
0x18001b20b  mov     rdx, rsi; unsigned __int64
0x18001b20e  lea     rcx, [rbp+150h+var_1C0]; this
0x18001b212  call    ?StartActivity@SetThumbnailStream@ThumbnailCacheTelemetry@@QEAAX_K@Z; ThumbnailCacheTelemetry::SetThumbnailStream::StartActivity(unsigned __int64)
0x18001b217  nop
0x18001b218  xor     eax, eax
0x18001b21a  test    rsi, rsi
0x18001b21d  jnz     loc_18001B2FF
0x18001b223  mov     [rsp+250h+ppv], rsi
0x18001b228  lea     rcx, [rsp+250h+ppv]
0x18001b22d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b232  lea     r9, [rsp+250h+ppv]; ppv
0x18001b237  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18001b23e  xor     edx, edx; pbc
0x18001b240  mov     rcx, r14; pszPath
0x18001b243  call    cs:__imp_SHCreateItemFromParsingName
0x18001b249  mov     edi, eax
0x18001b24b  test    eax, eax
0x18001b24d  js      loc_18001B575
0x18001b253  mov     [rsp+250h+var_1F0], rsi
0x18001b258  mov     rdx, [rsp+250h+ppv]
0x18001b25d  lea     rcx, [rsp+250h+var_1F0]
0x18001b262  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x18001b267  mov     edi, eax
0x18001b269  test    eax, eax
0x18001b26b  js      loc_18001B50B
0x18001b271  movups  xmm0, xmmword ptr cs:PKEY_ThumbnailCacheId.fmtid.Data1
0x18001b278  mov     ecx, cs:PKEY_ThumbnailCacheId.pid
0x18001b27e  xor     eax, eax
0x18001b280  mov     word ptr [rsp+250h+pvar], ax
0x18001b285  movaps  xmmword ptr [rsp+250h+var_228+8], xmm0
0x18001b28a  mov     [rsp+250h+var_210], ecx
0x18001b28e  mov     rcx, [rsp+250h+var_1F0]
0x18001b293  mov     rax, [rcx]
0x18001b296  lea     r8, [rsp+250h+pvar]
0x18001b29b  lea     rdx, [rsp+250h+var_228+8]
0x18001b2a0  mov     rax, [rax+28h]
0x18001b2a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2a9  mov     edi, eax
0x18001b2ab  movzx   eax, word ptr [rsp+250h+pvar]
0x18001b2b0  test    edi, edi
0x18001b2b2  js      short loc_18001B2C2
0x18001b2b4  test    ax, ax
0x18001b2b7  jnz     loc_18001B553
0x18001b2bd  mov     edi, 80070490h
0x18001b2c2  lea     rcx, [rsp+250h+pvar]; pvar
0x18001b2c7  call    cs:__imp_PropVariantClear
0x18001b2cd  test    edi, edi
0x18001b2cf  js      loc_18001B592
0x18001b2d5  lea     rcx, [rsp+250h+var_1F0]
0x18001b2da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b2df  nop
0x18001b2e0  mov     rcx, [rsp+250h+ppv]
0x18001b2e5  xor     eax, eax
0x18001b2e7  test    rcx, rcx
0x18001b2ea  jz      short loc_18001B2FF
0x18001b2ec  mov     [rsp+250h+ppv], rax
0x18001b2f1  mov     rax, [rcx]
0x18001b2f4  mov     rax, [rax+10h]
0x18001b2f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2fd  xor     eax, eax
0x18001b2ff  movd    xmm6, ebx
0x18001b303  cvtdq2ps xmm6, xmm6
0x18001b306  movd    xmm7, r15d
0x18001b30b  cvtdq2ps xmm7, xmm7
0x18001b30e  mov     qword ptr [rsp+250h+var_200], rax
0x18001b313  lea     rcx, [rsp+250h+var_200]
0x18001b318  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b31d  lea     r9, [rsp+250h+var_200]
0x18001b322  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x18001b329  xor     edx, edx
0x18001b32b  mov     rcx, r12
0x18001b32e  call    cs:__imp_CreateRandomAccessStreamOverStream
0x18001b334  mov     edi, eax
0x18001b336  xor     r12d, r12d
0x18001b339  test    eax, eax
0x18001b33b  js      loc_18001B4CE
0x18001b341  mov     rbx, [r13+30h]
0x18001b345  mov     r15, [rbx]
0x18001b348  mov     [rbp+150h+string], r12
0x18001b34c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001b350  inc     rdx; length
0x18001b353  cmp     [r14+rdx*2], r12w
0x18001b358  jnz     short loc_18001B350
0x18001b35a  mov     eax, 0FFFFFFFFh
0x18001b35f  cmp     rdx, rax
0x18001b362  jbe     short loc_18001B37A
0x18001b364  xor     r9d, r9d; lpArguments
0x18001b367  xor     r8d, r8d; nNumberOfArguments
0x18001b36a  lea     edx, [r9+1]; dwExceptionFlags
0x18001b36e  mov     ecx, 80070216h; dwExceptionCode
0x18001b373  call    cs:__imp_RaiseException
0x18001b379  int     3; Trap to Debugger
0x18001b37a  lea     eax, [rdx+1]
0x18001b37d  cmp     eax, edx
0x18001b37f  jb      short loc_18001B364
0x18001b381  mov     rdi, qword ptr [rsp+250h+var_200]
0x18001b386  lea     r9, [rbp+150h+string]; string
0x18001b38a  lea     r8, [rsp+250h+pvar]; hstringHeader
0x18001b38f  mov     rcx, r14; sourceString
0x18001b392  call    cs:__imp_WindowsCreateStringReference
0x18001b398  test    eax, eax
0x18001b39a  js      loc_18001B5D2
0x18001b3a0  mov     qword ptr [rsp+250h+var_230], rdi; int
0x18001b3a5  unpcklps xmm6, xmm7
0x18001b3a8  movq    r9, xmm6
0x18001b3ad  mov     r8, rsi
0x18001b3b0  mov     rdx, [rbp+150h+string]
0x18001b3b4  mov     rcx, rbx
0x18001b3b7  mov     rax, [r15+38h]
0x18001b3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3c0  mov     edi, eax
0x18001b3c2  test    eax, eax
0x18001b3c4  jns     loc_18001B46A
0x18001b3ca  mov     rcx, [rbp+158h]; this
0x18001b3d1  mov     r9d, eax; char *
0x18001b3d4  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001b3db  mov     edx, 4DCh; void *
0x18001b3e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b3e5  nop
0x18001b3e6  mov     rcx, qword ptr [rsp+250h+var_200]
0x18001b3eb  test    rcx, rcx
0x18001b3ee  jz      short loc_18001B402
0x18001b3f0  mov     qword ptr [rsp+250h+var_200], r12
0x18001b3f5  mov     rax, [rcx]
0x18001b3f8  mov     rax, [rax+10h]
0x18001b3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b401  nop
0x18001b402  lea     rax, ??_7SetThumbnailStream@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::SetThumbnailStream::`vftable'
0x18001b409  mov     [rbp+150h+var_1C0], rax
0x18001b40d  lea     rcx, [rbp+150h+var_1C0]
0x18001b411  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001b416  lea     rcx, [rbp+150h+var_A0]; this
0x18001b41d  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001b422  lea     rcx, [rbp+150h+var_A8]
0x18001b429  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001b42e  lea     rcx, [rbp+150h+var_1B8]
0x18001b432  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001b437  mov     eax, edi
0x18001b439  mov     rcx, [rbp+150h+var_70]
0x18001b440  xor     rcx, rsp; StackCookie
0x18001b443  call    __security_check_cookie
0x18001b448  lea     r11, [rsp+250h+var_38]
0x18001b450  movaps  xmm6, xmmword ptr [r11-18h]
0x18001b455  movaps  xmm7, xmmword ptr [r11-28h]
0x18001b45a  mov     rsp, r11
0x18001b45d  pop     r15
0x18001b45f  pop     r14
0x18001b461  pop     r13
0x18001b463  pop     r12
0x18001b465  pop     rdi
0x18001b466  pop     rsi
0x18001b467  pop     rbx
0x18001b468  pop     rbp
0x18001b469  retn
0x18001b46a  xor     edx, edx
0x18001b46c  lea     rcx, [rbp+150h+var_1C0]
0x18001b470  call    ?Stop@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001b475  nop
0x18001b476  mov     rcx, qword ptr [rsp+250h+var_200]
0x18001b47b  test    rcx, rcx
0x18001b47e  jz      short loc_18001B492
0x18001b480  mov     qword ptr [rsp+250h+var_200], r12
0x18001b485  mov     rax, [rcx]
0x18001b488  mov     rax, [rax+10h]
0x18001b48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b491  nop
0x18001b492  lea     rax, ??_7SetThumbnailStream@ThumbnailCacheTelemetry@@6B@; const ThumbnailCacheTelemetry::SetThumbnailStream::`vftable'
0x18001b499  mov     [rbp+150h+var_1C0], rax
0x18001b49d  lea     rcx, [rbp+150h+var_1C0]
0x18001b4a1  call    ?Destroy@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001b4a6  lea     rcx, [rbp+150h+var_A0]; this
0x18001b4ad  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18001b4b2  lea     rcx, [rbp+150h+var_A8]
0x18001b4b9  call    ?reset@?$shared_object@V?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001b4be  lea     rcx, [rbp+150h+var_1B8]
0x18001b4c2  call    ??1?$ActivityData@VThumbnailCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VThumbnailCacheLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ThumbnailCacheLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ThumbnailCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001b4c7  xor     eax, eax
0x18001b4c9  jmp     loc_18001B439
0x18001b4ce  mov     rcx, [rbp+158h]; this
0x18001b4d5  mov     r9d, eax; char *
0x18001b4d8  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001b4df  mov     edx, 4DBh; void *
0x18001b4e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b4e9  nop
0x18001b4ea  mov     rcx, qword ptr [rsp+250h+var_200]
0x18001b4ef  test    rcx, rcx
0x18001b4f2  jz      short loc_18001B506
0x18001b4f4  mov     qword ptr [rsp+250h+var_200], r12
0x18001b4f9  mov     rax, [rcx]
0x18001b4fc  mov     rax, [rax+10h]
0x18001b500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b505  nop
0x18001b506  jmp     loc_18001B402
0x18001b50b  mov     rcx, [rbp+158h]; this
0x18001b512  mov     r9d, eax; char *
0x18001b515  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001b51c  mov     edx, 4D5h; void *
0x18001b521  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b526  nop
0x18001b527  lea     rcx, [rsp+250h+var_1F0]
0x18001b52c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b531  nop
0x18001b532  mov     rcx, [rsp+250h+ppv]
0x18001b537  test    rcx, rcx
0x18001b53a  jz      short loc_18001B54E
0x18001b53c  mov     [rsp+250h+ppv], rsi
0x18001b541  mov     rax, [rcx]
0x18001b544  mov     rax, [rax+10h]
0x18001b548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b54d  nop
0x18001b54e  jmp     loc_18001B402
0x18001b553  test    edi, edi
0x18001b555  js      loc_18001B2C2
0x18001b55b  cmp     ax, 15h
0x18001b55f  jnz     short loc_18001B56B
0x18001b561  mov     rsi, [rsp+250h+var_1E0]
0x18001b566  jmp     loc_18001B2C2
0x18001b56b  mov     edi, 80020005h
0x18001b570  jmp     loc_18001B2C2
0x18001b575  mov     rcx, [rbp+158h]; this
0x18001b57c  mov     r9d, eax; char *
0x18001b57f  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001b586  mov     edx, 4D3h; void *
0x18001b58b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b590  jmp     short loc_18001B5B9
0x18001b592  mov     rcx, [rbp+158h]; this
0x18001b599  mov     r9d, edi; char *
0x18001b59c  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001b5a3  mov     edx, 4D6h; void *
0x18001b5a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b5ad  nop
0x18001b5ae  lea     rcx, [rsp+250h+var_1F0]
0x18001b5b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b5b8  nop
0x18001b5b9  lea     rcx, [rsp+250h+ppv]
0x18001b5be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b5c3  nop
0x18001b5c4  lea     rcx, [rbp+150h+var_1C0]; this
0x18001b5c8  call    ??1SetThumbnailStream@ThumbnailCacheTelemetry@@QEAA@XZ; ThumbnailCacheTelemetry::SetThumbnailStream::~SetThumbnailStream(void)
0x18001b5cd  jmp     loc_18001B437
0x18001b5d2  xor     r9d, r9d; lpArguments
0x18001b5d5  xor     r8d, r8d; nNumberOfArguments
0x18001b5d8  lea     edx, [r9+1]; dwExceptionFlags
0x18001b5dc  mov     ecx, eax; dwExceptionCode
0x18001b5de  call    cs:__imp_RaiseException
```
