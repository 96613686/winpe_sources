# HDRConverter::Convert(IWICComponentFactory *,IWICBitmapSource *,_GUID const &,_GUID const &,IWICBitmapSource * *,IWICBitmapSourceTransform * *)

- ea: `0x18003b7b0`
- end: `0x18003bac3`
- name: `?Convert@HDRConverter@@QEAAJPEAUIWICComponentFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@2PEAPEAU3@PEAPEAUIWICBitmapSourceTransform@@@Z`
- size: `787`
- prototype: `__int64 __usercall@<rax>(HDRConverter *__hidden this@<rcx>, struct IWICComponentFactory *@<rdx>, struct IWICBitmapSource *@<r8>, const struct _GUID *@<r9>, const struct _GUID *, struct IWICBitmapSource **, struct IWICBitmapSourceTransform **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800314f0`

## callees

- `0x18003653c`
- `0x18003b7b0`
- `0x18003bad0`
- `0x18003be30`
- `0x18003d420`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18003b91c`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18003b91c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall HDRConverter::Convert(
        struct ID2D1ColorContext **this,
        struct IWICComponentFactory *a2,
        struct IWICBitmapSource *a3,
        const struct _GUID *a4,
        const struct _GUID *a5,
        struct IWICBitmapSource **a6,
        struct IWICBitmapSourceTransform **ppunkMarshal)
{
  struct IWICBitmapSource **v11; // r13
  struct IWICBitmapSourceTransform **v12; // r12
  HRESULT D2DBitmaps; // esi
  const struct _GUID *v14; // r9
  struct ID2D1ColorContext *v15; // rcx
  struct ID2D1ColorContext *v16; // rcx
  struct ID2D1ColorContext *v17; // rcx
  struct ID2D1ColorContext *v18; // rcx
  struct ID2D1ColorContext *v19; // rcx
  struct IWICBitmapSource **v20; // rsi
  _QWORD *v21; // rax
  _QWORD *v22; // rdi
  struct IWICBitmapSourceTransform **v23; // rbx
  struct IWICBitmapSourceTransformVtbl *lpVtbl; // rbp
  __int64 v25; // rcx
  struct IWICBitmapSourceTransform **v26; // rcx
  struct IWICBitmapSource **v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  struct IWICBitmapSource **v30; // rax
  struct IWICBitmapSource **v31; // rcx

  v11 = a6;
  *a6 = 0;
  v12 = ppunkMarshal;
  *ppunkMarshal = 0;
  a6 = 0;
  D2DBitmaps = D2DImageConverterBase::EnsureInitialized((D2DImageConverterBase *)this, a2);
  if ( D2DBitmaps >= 0 )
  {
    D2DBitmaps = HDRConverter::CreateD2DBitmaps((HDRConverter *)this, a3, a4, v14);
    if ( D2DBitmaps >= 0 )
      D2DBitmaps = HDRConverter::ConvertToFloatingPointPixels(
                     (HDRConverter *)this,
                     this[5],
                     this[7],
                     this[1],
                     a5,
                     (struct IWICBitmapSource **)&a6);
  }
  v15 = this[5];
  if ( v15 )
    (*(void (__fastcall **)(struct ID2D1ColorContext *, _QWORD))(*(_QWORD *)v15 + 592LL))(v15, 0);
  v16 = this[7];
  if ( v16 )
  {
    this[7] = 0;
    (*(void (__fastcall **)(struct ID2D1ColorContext *))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = this[1];
  if ( v17 )
  {
    this[1] = 0;
    (*(void (__fastcall **)(struct ID2D1ColorContext *))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = this[8];
  if ( v18 )
  {
    this[8] = 0;
    (*(void (__fastcall **)(struct ID2D1ColorContext *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = this[9];
  if ( v19 )
  {
    this[9] = 0;
    (*(void (__fastcall **)(struct ID2D1ColorContext *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  if ( D2DBitmaps >= 0 )
  {
    v20 = a6;
    *v12 = 0;
    v21 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v22 = v21;
    if ( v21 )
    {
      v21[1] = &Microsoft::WRL::FtmBase::`vftable';
      v21[4] = 0;
      ppunkMarshal = 0;
      if ( CoCreateFreeThreadedMarshaler(0, (LPUNKNOWN *)&ppunkMarshal) >= 0 )
      {
        v23 = ppunkMarshal;
        lpVtbl = (*ppunkMarshal)->lpVtbl;
        v25 = v22[4];
        if ( v25 )
        {
          v22[4] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
        ((void (__fastcall *)(struct IWICBitmapSourceTransform **, GUID *, _QWORD *))lpVtbl)(
          v23,
          &GUID_00000003_0000_0000_c000_000000000046,
          v22 + 4);
      }
      v26 = ppunkMarshal;
      if ( ppunkMarshal )
      {
        ppunkMarshal = 0;
        ((void (__fastcall *)(struct IWICBitmapSourceTransform **))(*v26)[2].lpVtbl)(v26);
      }
      *((_DWORD *)v22 + 11) = 1;
      *v22 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWICBitmapSourceTransform,Microsoft::WRL::FtmBase>::`vftable'{for `IWICBitmapSourceTransform'};
      v22[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWICBitmapSourceTransform,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *v22 = &CBitmapSourceTransformOnBitmapSource::`vftable'{for `IWICBitmapSourceTransform'};
      v22[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWICBitmapSourceTransform,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      v22[6] = 0;
      v22[7] = 0;
      v27 = 0;
      if ( a2 )
      {
        ((void (__fastcall *)(struct IWICComponentFactory *))a2->lpVtbl->AddRef)(a2);
        v27 = (struct IWICBitmapSource **)v22[6];
        v28 = v22[7];
        v22[7] = a2;
        if ( v28 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          v27 = (struct IWICBitmapSource **)v22[6];
        }
      }
      if ( v27 != v20 )
      {
        if ( v20 )
          ((void (__fastcall *)(struct IWICBitmapSource **))(*v20)[1].lpVtbl)(v20);
        v29 = v22[6];
        v22[6] = v20;
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      D2DBitmaps = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IWICBitmapSourceTransform **))*v22)(
                     v22,
                     &GUID_3b16811b_6a43_4ec9_b713_3d5a0c13b940,
                     v12);
      (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
      if ( D2DBitmaps >= 0 )
      {
        v30 = a6;
        a6 = 0;
        *v11 = (struct IWICBitmapSource *)v30;
      }
    }
    else
    {
      D2DBitmaps = -2147024882;
    }
  }
  v31 = a6;
  if ( a6 )
  {
    a6 = 0;
    ((void (__fastcall *)(struct IWICBitmapSource **))(*v31)[2].lpVtbl)(v31);
  }
  return (unsigned int)D2DBitmaps;
}

```

## disassembly

```asm
0x18003b7b0  push    rbx
0x18003b7b2  push    rbp
0x18003b7b3  push    rsi
0x18003b7b4  push    rdi
0x18003b7b5  push    r12
0x18003b7b7  push    r13
0x18003b7b9  push    r14
0x18003b7bb  push    r15
0x18003b7bd  sub     rsp, 38h
0x18003b7c1  mov     rdi, r9
0x18003b7c4  mov     rbp, r8
0x18003b7c7  mov     r15, rdx
0x18003b7ca  mov     rbx, rcx
0x18003b7cd  xor     r14d, r14d
0x18003b7d0  mov     r13, [rsp+78h+arg_28]
0x18003b7d8  mov     [r13+0], r14
0x18003b7dc  mov     r12, [rsp+78h+ppunkMarshal]
0x18003b7e4  mov     [r12], r14
0x18003b7e8  mov     [rsp+78h+arg_28], r14
0x18003b7f0  call    ?EnsureInitialized@D2DImageConverterBase@@IEAAJPEAUIWICComponentFactory@@@Z; D2DImageConverterBase::EnsureInitialized(IWICComponentFactory *)
0x18003b7f5  mov     esi, eax
0x18003b7f7  test    eax, eax
0x18003b7f9  js      short loc_18003B83F
0x18003b7fb  mov     r8, rdi; struct _GUID *
0x18003b7fe  mov     rdx, rbp; struct IWICBitmapSource *
0x18003b801  mov     rcx, rbx; this
0x18003b804  call    ?CreateD2DBitmaps@HDRConverter@@AEAAJPEAUIWICBitmapSource@@AEBU_GUID@@1@Z; HDRConverter::CreateD2DBitmaps(IWICBitmapSource *,_GUID const &,_GUID const &)
0x18003b809  mov     esi, eax
0x18003b80b  test    eax, eax
0x18003b80d  js      short loc_18003B83F
0x18003b80f  lea     rax, [rsp+78h+arg_28]
0x18003b817  mov     [rsp+78h+var_50], rax; struct IWICBitmapSource **
0x18003b81c  mov     rax, [rsp+78h+arg_20]
0x18003b824  mov     [rsp+78h+var_58], rax; struct _GUID *
0x18003b829  mov     r9, [rbx+8]; struct ID2D1ColorContext *
0x18003b82d  mov     r8, [rbx+38h]; struct ID2D1Image *
0x18003b831  mov     rdx, [rbx+28h]; struct ID2D1DeviceContext5 *
0x18003b835  mov     rcx, rbx; this
0x18003b838  call    ?ConvertToFloatingPointPixels@HDRConverter@@AEAAJPEAUID2D1DeviceContext5@@PEAUID2D1Image@@PEAUID2D1ColorContext@@AEBU_GUID@@PEAPEAUIWICBitmapSource@@@Z; HDRConverter::ConvertToFloatingPointPixels(ID2D1DeviceContext5 *,ID2D1Image *,ID2D1ColorContext *,_GUID const &,IWICBitmapSource * *)
0x18003b83d  mov     esi, eax
0x18003b83f  mov     rcx, [rbx+28h]
0x18003b843  test    rcx, rcx
0x18003b846  jz      short loc_18003B85A
0x18003b848  mov     rax, [rcx]
0x18003b84b  xor     edx, edx
0x18003b84d  mov     rax, [rax+250h]
0x18003b854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b859  nop
0x18003b85a  mov     rcx, [rbx+38h]
0x18003b85e  test    rcx, rcx
0x18003b861  jz      short loc_18003B874
0x18003b863  mov     [rbx+38h], r14
0x18003b867  mov     rax, [rcx]
0x18003b86a  mov     rax, [rax+10h]
0x18003b86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b873  nop
0x18003b874  mov     rcx, [rbx+8]
0x18003b878  test    rcx, rcx
0x18003b87b  jz      short loc_18003B88E
0x18003b87d  mov     [rbx+8], r14
0x18003b881  mov     rax, [rcx]
0x18003b884  mov     rax, [rax+10h]
0x18003b888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b88d  nop
0x18003b88e  mov     rcx, [rbx+40h]
0x18003b892  test    rcx, rcx
0x18003b895  jz      short loc_18003B8A8
0x18003b897  mov     [rbx+40h], r14
0x18003b89b  mov     rax, [rcx]
0x18003b89e  mov     rax, [rax+10h]
0x18003b8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8a7  nop
0x18003b8a8  mov     rcx, [rbx+48h]
0x18003b8ac  test    rcx, rcx
0x18003b8af  jz      short loc_18003B8C2
0x18003b8b1  mov     [rbx+48h], r14
0x18003b8b5  mov     rax, [rcx]
0x18003b8b8  mov     rax, [rax+10h]
0x18003b8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8c1  nop
0x18003b8c2  test    esi, esi
0x18003b8c4  js      loc_18003BA8E
0x18003b8ca  mov     rsi, [rsp+78h+arg_28]
0x18003b8d2  mov     [r12], r14
0x18003b8d6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003b8dd  mov     ecx, 40h ; '@'; unsigned __int64
0x18003b8e2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003b8e7  mov     rdi, rax
0x18003b8ea  test    rax, rax
0x18003b8ed  jnz     short loc_18003B8F9
0x18003b8ef  mov     esi, 8007000Eh
0x18003b8f4  jmp     loc_18003BA8E
0x18003b8f9  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18003b900  mov     [rdi+8], rax
0x18003b904  xor     eax, eax
0x18003b906  mov     [rdi+20h], rax
0x18003b90a  mov     [rsp+78h+ppunkMarshal], rax
0x18003b912  lea     rdx, [rsp+78h+ppunkMarshal]; ppunkMarshal
0x18003b91a  xor     ecx, ecx; punkOuter
0x18003b91c  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18003b922  test    eax, eax
0x18003b924  js      short loc_18003B969
0x18003b926  mov     rbx, [rsp+78h+ppunkMarshal]
0x18003b92e  mov     rax, [rbx]
0x18003b931  mov     rbp, [rax]
0x18003b934  mov     rcx, [rdi+20h]
0x18003b938  test    rcx, rcx
0x18003b93b  jz      short loc_18003B952
0x18003b93d  mov     qword ptr [rdi+20h], 0
0x18003b945  mov     rdx, [rcx]
0x18003b948  mov     rax, [rdx+10h]
0x18003b94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b951  nop
0x18003b952  lea     r8, [rdi+20h]
0x18003b956  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18003b95d  mov     rcx, rbx
0x18003b960  mov     rax, rbp
0x18003b963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b968  nop
0x18003b969  mov     rcx, [rsp+78h+ppunkMarshal]
0x18003b971  xor     r14d, r14d
0x18003b974  test    rcx, rcx
0x18003b977  jz      short loc_18003B98E
0x18003b979  mov     [rsp+78h+ppunkMarshal], r14
0x18003b981  mov     rax, [rcx]
0x18003b984  mov     rax, [rax+10h]
0x18003b988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b98d  nop
0x18003b98e  mov     dword ptr [rdi+2Ch], 1
0x18003b995  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWICBitmapSourceTransform@@VFtmBase@23@@WRL@Microsoft@@6BIWICBitmapSourceTransform@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWICBitmapSourceTransform,Microsoft::WRL::FtmBase>::`vftable'{for `IWICBitmapSourceTransform'}
0x18003b99c  mov     [rdi], rax
0x18003b99f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWICBitmapSourceTransform@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWICBitmapSourceTransform,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003b9a6  mov     [rdi+8], rax
0x18003b9aa  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18003b9b1  test    rcx, rcx
0x18003b9b4  jz      short loc_18003B9C3
0x18003b9b6  mov     rax, [rcx]
0x18003b9b9  mov     rax, [rax+8]
0x18003b9bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9c2  nop
0x18003b9c3  lea     rax, ??_7CBitmapSourceTransformOnBitmapSource@@6BIWICBitmapSourceTransform@@@; const CBitmapSourceTransformOnBitmapSource::`vftable'{for `IWICBitmapSourceTransform'}
0x18003b9ca  mov     [rdi], rax
0x18003b9cd  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWICBitmapSourceTransform@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWICBitmapSourceTransform,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003b9d4  mov     [rdi+8], rax
0x18003b9d8  mov     [rdi+30h], r14
0x18003b9dc  mov     [rdi+38h], r14
0x18003b9e0  mov     rax, r14
0x18003b9e3  test    r15, r15
0x18003b9e6  jz      short loc_18003BA18
0x18003b9e8  mov     rax, [r15]
0x18003b9eb  mov     rcx, r15
0x18003b9ee  mov     rax, [rax+8]
0x18003b9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9f7  mov     rax, [rdi+30h]
0x18003b9fb  mov     rcx, [rdi+38h]
0x18003b9ff  mov     [rdi+38h], r15
0x18003ba03  test    rcx, rcx
0x18003ba06  jz      short loc_18003BA18
0x18003ba08  mov     rax, [rcx]
0x18003ba0b  mov     rax, [rax+10h]
0x18003ba0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba14  mov     rax, [rdi+30h]
0x18003ba18  cmp     rax, rsi
0x18003ba1b  jz      short loc_18003BA4C
0x18003ba1d  test    rsi, rsi
0x18003ba20  jz      short loc_18003BA32
0x18003ba22  mov     rax, [rsi]
0x18003ba25  mov     rcx, rsi
0x18003ba28  mov     rax, [rax+8]
0x18003ba2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba31  nop
0x18003ba32  mov     rcx, [rdi+30h]
0x18003ba36  mov     [rdi+30h], rsi
0x18003ba3a  test    rcx, rcx
0x18003ba3d  jz      short loc_18003BA4C
0x18003ba3f  mov     rax, [rcx]
0x18003ba42  mov     rax, [rax+10h]
0x18003ba46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba4b  nop
0x18003ba4c  mov     rax, [rdi]
0x18003ba4f  mov     r8, r12
0x18003ba52  lea     rdx, _GUID_3b16811b_6a43_4ec9_b713_3d5a0c13b940
0x18003ba59  mov     rcx, rdi
0x18003ba5c  mov     rax, [rax]
0x18003ba5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba64  mov     esi, eax
0x18003ba66  mov     rax, [rdi]
0x18003ba69  mov     rcx, rdi
0x18003ba6c  mov     rax, [rax+10h]
0x18003ba70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba75  nop
0x18003ba76  test    esi, esi
0x18003ba78  js      short loc_18003BA8E
0x18003ba7a  mov     rax, [rsp+78h+arg_28]
0x18003ba82  mov     [rsp+78h+arg_28], r14
0x18003ba8a  mov     [r13+0], rax
0x18003ba8e  mov     rcx, [rsp+78h+arg_28]
0x18003ba96  test    rcx, rcx
0x18003ba99  jz      short loc_18003BAB0
0x18003ba9b  mov     [rsp+78h+arg_28], r14
0x18003baa3  mov     rdx, [rcx]
0x18003baa6  mov     rax, [rdx+10h]
0x18003baaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003baaf  nop
0x18003bab0  mov     eax, esi
0x18003bab2  add     rsp, 38h
0x18003bab6  pop     r15
0x18003bab8  pop     r14
0x18003baba  pop     r13
0x18003babc  pop     r12
0x18003babe  pop     rdi
0x18003babf  pop     rsi
0x18003bac0  pop     rbp
0x18003bac1  pop     rbx
0x18003bac2  retn
```
