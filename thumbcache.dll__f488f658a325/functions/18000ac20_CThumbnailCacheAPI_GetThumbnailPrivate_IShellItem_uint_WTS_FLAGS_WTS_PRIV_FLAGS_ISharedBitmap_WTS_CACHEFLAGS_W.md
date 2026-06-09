# CThumbnailCacheAPI::GetThumbnailPrivate(IShellItem *,uint,WTS_FLAGS,WTS_PRIV_FLAGS,ISharedBitmap * *,WTS_CACHEFLAGS *,WTS_THUMBNAILID *)

- ea: `0x18000ac20`
- end: `0x18000af1b`
- name: `?GetThumbnailPrivate@CThumbnailCacheAPI@@UEAAJPEAUIShellItem@@IW4WTS_FLAGS@@W4WTS_PRIV_FLAGS@@PEAPEAUISharedBitmap@@PEAW4WTS_CACHEFLAGS@@PEAUWTS_THUMBNAILID@@@Z`
- size: `763`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180003624`
- `0x18000ac20`
- `0x18000bfd8`
- `0x18000c67c`
- `0x180017be0`
- `0x180019248`
- `0x180019338`
- `0x180035830`
- `0x180035860`
- `0x180049010`

## string_xrefs

- `0x18000ae52`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18000ae74`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18000ae98`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18000aeb4`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18000af04`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CThumbnailCacheAPI::GetThumbnailPrivate(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        _QWORD *a6,
        _DWORD *a7,
        _OWORD *a8)
{
  _QWORD *v12; // r13
  bool IsGraphicsDeviceInterfacePresent; // al
  int v14; // edx
  unsigned int v15; // esi
  void *v16; // rax
  __int64 (__fastcall ***v17)(_QWORD, GUID *, _QWORD *); // rax
  int v18; // eax
  __int64 v19; // rbx
  int v20; // ecx
  __int64 v21; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // [rsp+20h] [rbp-98h]
  int v26; // [rsp+20h] [rbp-98h]
  int v27; // [rsp+20h] [rbp-98h]
  unsigned int v28; // [rsp+50h] [rbp-68h]
  __int64 (__fastcall ***v29)(_QWORD, GUID *, _QWORD *); // [rsp+50h] [rbp-68h]
  __int64 v30; // [rsp+60h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  v30 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  v30 = 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS>::__private_IsEnabledPreCheck(&`wil::Feature<__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS>::GetImpl'::`2'::impl);
  v30 = 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS>::__private_IsEnabledPreCheck(&`wil::Feature<__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS>::GetImpl'::`2'::impl);
  v12 = (_QWORD *)(a1 + 600);
  if ( !*(_QWORD *)(a1 + 600) )
  {
    IsGraphicsDeviceInterfacePresent = CThumbnailCacheAPI::IsGraphicsDeviceInterfacePresent((CThumbnailCacheAPI *)a1);
    v14 = *(_DWORD *)(a1 + 44);
    if ( !IsGraphicsDeviceInterfacePresent )
      v14 = *(_DWORD *)(a1 + 44) | 4;
    v28 = v14;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 600);
    *v12 = 0;
    v15 = -2147024882;
    v16 = operator new(0x320u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v16
      || (v17 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))CThumbnailCache::CThumbnailCache(v16, v28),
          (v29 = v17) == 0)
      || (v15 = (**v17)(v17, &GUID_f676c15d_596a_4ce2_8234_33996f445db1, v12),
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v29)[2])(v29),
          (v15 & 0x80000000) != 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x252,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)v15,
        v25);
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x265,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)v15,
        v26);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x130,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)v15,
        v27);
      v24 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      return v15;
    }
  }
  v18 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v12)(
          *v12,
          &GUID_2d3e7f31_91d1_4fb8_a7ea_fa4011bdbcda,
          &v30);
  v15 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x254,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v18,
      v25);
    goto LABEL_25;
  }
  v19 = (*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v30 + 104LL))(v30, a2, a3, a4);
  if ( (unsigned __int8)ShouldSuppressWilErrorTelemetry(v19) )
  {
    if ( v20 < 0 )
    {
LABEL_16:
      v21 = v30;
      if ( v30 )
      {
        v30 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      return (unsigned int)v19;
    }
  }
  else if ( (int)v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v19,
      a5);
    goto LABEL_16;
  }
  v23 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ac20  push    rbx
0x18000ac22  push    rbp
0x18000ac23  push    rsi
0x18000ac24  push    rdi
0x18000ac25  push    r12
0x18000ac27  push    r13
0x18000ac29  push    r14
0x18000ac2b  push    r15
0x18000ac2d  sub     rsp, 78h
0x18000ac31  mov     rax, cs:__security_cookie
0x18000ac38  xor     rax, rsp
0x18000ac3b  mov     [rsp+0B8h+var_50], rax
0x18000ac40  mov     r12d, r9d
0x18000ac43  mov     r15d, r8d
0x18000ac46  mov     r14, rdx
0x18000ac49  mov     rsi, rcx
0x18000ac4c  mov     rbx, [rsp+0B8h+arg_28]
0x18000ac54  mov     rdi, [rsp+0B8h+arg_30]
0x18000ac5c  mov     rbp, [rsp+0B8h+arg_38]
0x18000ac64  test    rbx, rbx
0x18000ac67  jz      short loc_18000AC70
0x18000ac69  mov     qword ptr [rbx], 0
0x18000ac70  test    rdi, rdi
0x18000ac73  jz      short loc_18000AC7B
0x18000ac75  mov     dword ptr [rdi], 0
0x18000ac7b  test    rbp, rbp
0x18000ac7e  jnz     loc_18000AEED
0x18000ac84  mov     [rsp+0B8h+var_58], 0
0x18000ac8d  lea     rcx, [rsp+0B8h+var_58]
0x18000ac92  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ac97  mov     [rsp+0B8h+var_58], 0
0x18000aca0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS> `wil::Feature<__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS>::GetImpl(void)'::`2'::impl
0x18000aca7  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18000acac  mov     [rsp+0B8h+var_58], 0
0x18000acb5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS> `wil::Feature<__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS>::GetImpl(void)'::`2'::impl
0x18000acbc  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerUserThumbnailCache_WCOS>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18000acc1  lea     r13, [rsi+258h]
0x18000acc8  cmp     qword ptr [r13+0], 0
0x18000accd  jnz     loc_18000AD73
0x18000acd3  mov     rcx, rsi; this
0x18000acd6  call    ?IsGraphicsDeviceInterfacePresent@CThumbnailCacheAPI@@AEAA_NXZ; CThumbnailCacheAPI::IsGraphicsDeviceInterfacePresent(void)
0x18000acdb  mov     edx, [rsi+2Ch]
0x18000acde  mov     ecx, edx
0x18000ace0  or      ecx, 4
0x18000ace3  test    al, al
0x18000ace5  cmovz   edx, ecx
0x18000ace8  mov     dword ptr [rsp+0B8h+var_68], edx
0x18000acec  mov     rcx, r13
0x18000acef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000acf4  mov     qword ptr [r13+0], 0
0x18000acfc  mov     esi, 8007000Eh
0x18000ad01  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ad08  mov     ecx, 320h; unsigned __int64
0x18000ad0d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ad12  mov     [rsp+0B8h+var_60], rax
0x18000ad17  test    rax, rax
0x18000ad1a  jz      loc_18000AE69
0x18000ad20  mov     edx, dword ptr [rsp+0B8h+var_68]
0x18000ad24  mov     rcx, rax
0x18000ad27  call    ??0CThumbnailCache@@AEAA@W4THUMBNAILCACHECREATEFLAGS@@@Z; CThumbnailCache::CThumbnailCache(THUMBNAILCACHECREATEFLAGS)
0x18000ad2c  mov     r9, rax
0x18000ad2f  mov     [rsp+0B8h+var_68], rax
0x18000ad34  test    rax, rax
0x18000ad37  jz      loc_18000AE69
0x18000ad3d  mov     rcx, [rax]
0x18000ad40  mov     rax, [rcx]
0x18000ad43  mov     r8, r13
0x18000ad46  lea     rdx, _GUID_f676c15d_596a_4ce2_8234_33996f445db1
0x18000ad4d  mov     rcx, r9
0x18000ad50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad55  mov     esi, eax
0x18000ad57  mov     rdx, [rsp+0B8h+var_68]
0x18000ad5c  mov     rcx, [rdx]
0x18000ad5f  mov     rax, [rcx+10h]
0x18000ad63  mov     rcx, rdx
0x18000ad66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad6b  test    esi, esi
0x18000ad6d  js      loc_18000AE69
0x18000ad73  mov     rcx, [r13+0]
0x18000ad77  mov     rax, [rcx]
0x18000ad7a  lea     r8, [rsp+0B8h+var_58]
0x18000ad7f  lea     rdx, _GUID_2d3e7f31_91d1_4fb8_a7ea_fa4011bdbcda
0x18000ad86  mov     rax, [rax]
0x18000ad89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad8e  mov     esi, eax
0x18000ad90  test    eax, eax
0x18000ad92  js      loc_18000AEF9
0x18000ad98  mov     rcx, [rsp+0B8h+var_58]
0x18000ad9d  mov     rax, [rcx]
0x18000ada0  mov     [rsp+0B8h+var_80], rbp
0x18000ada5  mov     [rsp+0B8h+var_88], rdi
0x18000adaa  mov     [rsp+0B8h+var_90], rbx
0x18000adaf  mov     r10d, [rsp+0B8h+arg_20]
0x18000adb7  mov     [rsp+0B8h+var_98], r10d; int
0x18000adbc  mov     r9d, r12d
0x18000adbf  mov     r8d, r15d
0x18000adc2  mov     rdx, r14
0x18000adc5  mov     rax, [rax+68h]
0x18000adc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adce  mov     ebx, eax
0x18000add0  mov     ecx, eax
0x18000add2  call    ShouldSuppressWilErrorTelemetry
0x18000add7  test    al, al
0x18000add9  jz      short loc_18000AE1F
0x18000addb  test    ecx, ecx
0x18000addd  jns     short loc_18000AE23
0x18000addf  mov     rcx, [rsp+0B8h+var_58]
0x18000ade4  test    rcx, rcx
0x18000ade7  jz      short loc_18000ADFF
0x18000ade9  mov     [rsp+0B8h+var_58], 0
0x18000adf2  mov     rax, [rcx]
0x18000adf5  mov     rax, [rax+10h]
0x18000adf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adfe  nop
0x18000adff  mov     eax, ebx
0x18000ae01  mov     rcx, [rsp+0B8h+var_50]
0x18000ae06  xor     rcx, rsp; StackCookie
0x18000ae09  call    __security_check_cookie
0x18000ae0e  add     rsp, 78h
0x18000ae12  pop     r15
0x18000ae14  pop     r14
0x18000ae16  pop     r13
0x18000ae18  pop     r12
0x18000ae1a  pop     rdi
0x18000ae1b  pop     rsi
0x18000ae1c  pop     rbp
0x18000ae1d  pop     rbx
0x18000ae1e  retn
0x18000ae1f  test    ebx, ebx
0x18000ae21  js      short loc_18000AE47
0x18000ae23  mov     rcx, [rsp+0B8h+var_58]
0x18000ae28  test    rcx, rcx
0x18000ae2b  jz      short loc_18000AE43
0x18000ae2d  mov     [rsp+0B8h+var_58], 0
0x18000ae36  mov     rax, [rcx]
0x18000ae39  mov     rax, [rax+10h]
0x18000ae3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae42  nop
0x18000ae43  xor     eax, eax
0x18000ae45  jmp     short loc_18000AE01
0x18000ae47  mov     rcx, [rsp+0B8h]; this
0x18000ae4f  mov     r9d, ebx; char *
0x18000ae52  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000ae59  mov     edx, 133h; void *
0x18000ae5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae63  nop
0x18000ae64  jmp     loc_18000ADDF
0x18000ae69  mov     rcx, [rsp+0B8h]; this
0x18000ae71  mov     r9d, esi; char *
0x18000ae74  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000ae7b  mov     edx, 252h; void *
0x18000ae80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae85  test    esi, esi
0x18000ae87  jns     loc_18000AD98
0x18000ae8d  mov     rcx, [rsp+0B8h]; this
0x18000ae95  mov     r9d, esi; char *
0x18000ae98  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000ae9f  mov     edx, 265h; void *
0x18000aea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aea9  mov     rcx, [rsp+0B8h]; this
0x18000aeb1  mov     r9d, esi; char *
0x18000aeb4  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000aebb  mov     edx, 130h; void *
0x18000aec0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aec5  nop
0x18000aec6  mov     rcx, [rsp+0B8h+var_58]
0x18000aecb  test    rcx, rcx
0x18000aece  jz      short loc_18000AEE6
0x18000aed0  mov     [rsp+0B8h+var_58], 0
0x18000aed9  mov     rdx, [rcx]
0x18000aedc  mov     rax, [rdx+10h]
0x18000aee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee5  nop
0x18000aee6  mov     eax, esi
0x18000aee8  jmp     loc_18000AE01
0x18000aeed  xorps   xmm0, xmm0
0x18000aef0  movups  xmmword ptr [rbp+0], xmm0
0x18000aef4  jmp     loc_18000AC84
0x18000aef9  mov     rcx, [rsp+0B8h]; this
0x18000af01  mov     r9d, eax; char *
0x18000af04  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000af0b  mov     edx, 254h; void *
0x18000af10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000af15  jmp     loc_18000AE8D
```
