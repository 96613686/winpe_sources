# HDRConverter::Convert(IWICComponentFactory *,IWICBitmapSource *,_GUID const &,_GUID const &,IWICBitmapSource * *,IWICBitmapSourceTransform * *)

- ea: `0x18003c0a0`
- end: `0x18003c2d1`
- name: `?Convert@HDRConverter@@QEAAJPEAUIWICComponentFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@2PEAPEAU3@PEAPEAUIWICBitmapSourceTransform@@@Z`
- size: `561`
- prototype: `__int64 __usercall@<rax>(HDRConverter *__hidden this@<rcx>, struct IWICComponentFactory *@<rdx>, struct IWICBitmapSource *@<r8>, const struct _GUID *@<r9>, const struct _GUID *, struct IWICBitmapSource **, struct IWICBitmapSourceTransform **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180031850`

## callees

- `0x180036b0c`
- `0x18003be80`
- `0x18003c0a0`
- `0x18003c2e0`
- `0x18003c640`
- `0x18003db90`
- `0x180045010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HDRConverter::Convert(
        struct ID2D1ColorContext **this,
        struct IWICComponentFactory *a2,
        struct IWICBitmapSource *a3,
        const struct _GUID *a4,
        const struct _GUID *a5,
        struct IWICBitmapSource **a6,
        struct IWICBitmapSourceTransform **a7)
{
  struct IWICBitmapSource **v11; // r12
  struct IWICBitmapSourceTransform **v12; // r15
  HRESULT D2DBitmaps; // edi
  const struct _GUID *v14; // r9
  struct ID2D1ColorContext *v15; // rcx
  struct ID2D1ColorContext *v16; // rcx
  struct ID2D1ColorContext *v17; // rcx
  struct ID2D1ColorContext *v18; // rcx
  struct ID2D1ColorContext *v19; // rcx
  struct IWICBitmapSource **v20; // rdi
  CBitmapSourceTransformOnBitmapSource *v21; // rax
  CBitmapSourceTransformOnBitmapSource *v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rcx
  struct IWICBitmapSource **v25; // rax
  struct IWICBitmapSource **v26; // rcx

  v11 = a6;
  *a6 = 0;
  v12 = a7;
  *a7 = 0;
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
    v21 = (CBitmapSourceTransformOnBitmapSource *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v21 )
    {
      v22 = CBitmapSourceTransformOnBitmapSource::CBitmapSourceTransformOnBitmapSource(v21);
      if ( *((struct IWICComponentFactory **)v22 + 7) != a2 )
      {
        if ( a2 )
          ((void (__fastcall *)(struct IWICComponentFactory *))a2->lpVtbl->AddRef)(a2);
        v23 = *((_QWORD *)v22 + 7);
        *((_QWORD *)v22 + 7) = a2;
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      if ( *((struct IWICBitmapSource ***)v22 + 6) != v20 )
      {
        if ( v20 )
          ((void (__fastcall *)(struct IWICBitmapSource **))(*v20)[1].lpVtbl)(v20);
        v24 = *((_QWORD *)v22 + 6);
        *((_QWORD *)v22 + 6) = v20;
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      D2DBitmaps = (**(__int64 (__fastcall ***)(CBitmapSourceTransformOnBitmapSource *, GUID *, struct IWICBitmapSourceTransform **))v22)(
                     v22,
                     &GUID_3b16811b_6a43_4ec9_b713_3d5a0c13b940,
                     v12);
      (*(void (__fastcall **)(CBitmapSourceTransformOnBitmapSource *))(*(_QWORD *)v22 + 16LL))(v22);
      if ( D2DBitmaps >= 0 )
      {
        v25 = a6;
        a6 = 0;
        *v11 = (struct IWICBitmapSource *)v25;
      }
    }
    else
    {
      D2DBitmaps = -2147024882;
    }
  }
  v26 = a6;
  if ( a6 )
  {
    a6 = 0;
    ((void (__fastcall *)(struct IWICBitmapSource **))(*v26)[2].lpVtbl)(v26);
  }
  return (unsigned int)D2DBitmaps;
}

```

## disassembly

```asm
0x18003c0a0  push    rbx
0x18003c0a2  push    rbp
0x18003c0a3  push    rsi
0x18003c0a4  push    rdi
0x18003c0a5  push    r12
0x18003c0a7  push    r13
0x18003c0a9  push    r14
0x18003c0ab  push    r15
0x18003c0ad  sub     rsp, 38h
0x18003c0b1  mov     rbp, r9
0x18003c0b4  mov     r14, r8
0x18003c0b7  mov     rsi, rdx
0x18003c0ba  mov     rbx, rcx
0x18003c0bd  xor     r13d, r13d
0x18003c0c0  mov     r12, [rsp+78h+arg_28]
0x18003c0c8  mov     [r12], r13
0x18003c0cc  mov     r15, [rsp+78h+arg_30]
0x18003c0d4  mov     [r15], r13
0x18003c0d7  mov     [rsp+78h+arg_28], r13
0x18003c0df  call    ?EnsureInitialized@D2DImageConverterBase@@IEAAJPEAUIWICComponentFactory@@@Z; D2DImageConverterBase::EnsureInitialized(IWICComponentFactory *)
0x18003c0e4  mov     edi, eax
0x18003c0e6  test    eax, eax
0x18003c0e8  js      short loc_18003C12E
0x18003c0ea  mov     r8, rbp; struct _GUID *
0x18003c0ed  mov     rdx, r14; struct IWICBitmapSource *
0x18003c0f0  mov     rcx, rbx; this
0x18003c0f3  call    ?CreateD2DBitmaps@HDRConverter@@AEAAJPEAUIWICBitmapSource@@AEBU_GUID@@1@Z; HDRConverter::CreateD2DBitmaps(IWICBitmapSource *,_GUID const &,_GUID const &)
0x18003c0f8  mov     edi, eax
0x18003c0fa  test    eax, eax
0x18003c0fc  js      short loc_18003C12E
0x18003c0fe  lea     rax, [rsp+78h+arg_28]
0x18003c106  mov     [rsp+78h+var_50], rax; struct IWICBitmapSource **
0x18003c10b  mov     rax, [rsp+78h+arg_20]
0x18003c113  mov     [rsp+78h+var_58], rax; struct _GUID *
0x18003c118  mov     r9, [rbx+8]; struct ID2D1ColorContext *
0x18003c11c  mov     r8, [rbx+38h]; struct ID2D1Image *
0x18003c120  mov     rdx, [rbx+28h]; struct ID2D1DeviceContext5 *
0x18003c124  mov     rcx, rbx; this
0x18003c127  call    ?ConvertToFloatingPointPixels@HDRConverter@@AEAAJPEAUID2D1DeviceContext5@@PEAUID2D1Image@@PEAUID2D1ColorContext@@AEBU_GUID@@PEAPEAUIWICBitmapSource@@@Z; HDRConverter::ConvertToFloatingPointPixels(ID2D1DeviceContext5 *,ID2D1Image *,ID2D1ColorContext *,_GUID const &,IWICBitmapSource * *)
0x18003c12c  mov     edi, eax
0x18003c12e  mov     rcx, [rbx+28h]
0x18003c132  test    rcx, rcx
0x18003c135  jz      short loc_18003C149
0x18003c137  mov     rax, [rcx]
0x18003c13a  xor     edx, edx
0x18003c13c  mov     rax, [rax+250h]
0x18003c143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c148  nop
0x18003c149  mov     rcx, [rbx+38h]
0x18003c14d  test    rcx, rcx
0x18003c150  jz      short loc_18003C163
0x18003c152  mov     [rbx+38h], r13
0x18003c156  mov     rax, [rcx]
0x18003c159  mov     rax, [rax+10h]
0x18003c15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c162  nop
0x18003c163  mov     rcx, [rbx+8]
0x18003c167  test    rcx, rcx
0x18003c16a  jz      short loc_18003C17D
0x18003c16c  mov     [rbx+8], r13
0x18003c170  mov     rax, [rcx]
0x18003c173  mov     rax, [rax+10h]
0x18003c177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c17c  nop
0x18003c17d  mov     rcx, [rbx+40h]
0x18003c181  test    rcx, rcx
0x18003c184  jz      short loc_18003C197
0x18003c186  mov     [rbx+40h], r13
0x18003c18a  mov     rax, [rcx]
0x18003c18d  mov     rax, [rax+10h]
0x18003c191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c196  nop
0x18003c197  mov     rcx, [rbx+48h]
0x18003c19b  test    rcx, rcx
0x18003c19e  jz      short loc_18003C1B1
0x18003c1a0  mov     [rbx+48h], r13
0x18003c1a4  mov     rax, [rcx]
0x18003c1a7  mov     rax, [rax+10h]
0x18003c1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1b0  nop
0x18003c1b1  test    edi, edi
0x18003c1b3  js      loc_18003C29B
0x18003c1b9  mov     rdi, [rsp+78h+arg_28]
0x18003c1c1  mov     [r15], r13
0x18003c1c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003c1cb  mov     ecx, 40h ; '@'; unsigned __int64
0x18003c1d0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003c1d5  test    rax, rax
0x18003c1d8  jnz     short loc_18003C1E4
0x18003c1da  mov     edi, 8007000Eh
0x18003c1df  jmp     loc_18003C29B
0x18003c1e4  mov     rcx, rax; this
0x18003c1e7  call    ??0CBitmapSourceTransformOnBitmapSource@@QEAA@XZ; CBitmapSourceTransformOnBitmapSource::CBitmapSourceTransformOnBitmapSource(void)
0x18003c1ec  mov     rbx, rax
0x18003c1ef  cmp     [rax+38h], rsi
0x18003c1f3  jz      short loc_18003C224
0x18003c1f5  test    rsi, rsi
0x18003c1f8  jz      short loc_18003C20A
0x18003c1fa  mov     rcx, [rsi]
0x18003c1fd  mov     rax, [rcx+8]
0x18003c201  mov     rcx, rsi
0x18003c204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c209  nop
0x18003c20a  mov     rcx, [rbx+38h]
0x18003c20e  mov     [rbx+38h], rsi
0x18003c212  test    rcx, rcx
0x18003c215  jz      short loc_18003C224
0x18003c217  mov     rax, [rcx]
0x18003c21a  mov     rax, [rax+10h]
0x18003c21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c223  nop
0x18003c224  cmp     [rbx+30h], rdi
0x18003c228  jz      short loc_18003C259
0x18003c22a  test    rdi, rdi
0x18003c22d  jz      short loc_18003C23F
0x18003c22f  mov     rax, [rdi]
0x18003c232  mov     rcx, rdi
0x18003c235  mov     rax, [rax+8]
0x18003c239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c23e  nop
0x18003c23f  mov     rcx, [rbx+30h]
0x18003c243  mov     [rbx+30h], rdi
0x18003c247  test    rcx, rcx
0x18003c24a  jz      short loc_18003C259
0x18003c24c  mov     rax, [rcx]
0x18003c24f  mov     rax, [rax+10h]
0x18003c253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c258  nop
0x18003c259  mov     rax, [rbx]
0x18003c25c  mov     r8, r15
0x18003c25f  lea     rdx, _GUID_3b16811b_6a43_4ec9_b713_3d5a0c13b940
0x18003c266  mov     rcx, rbx
0x18003c269  mov     rax, [rax]
0x18003c26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c271  mov     edi, eax
0x18003c273  mov     rax, [rbx]
0x18003c276  mov     rcx, rbx
0x18003c279  mov     rax, [rax+10h]
0x18003c27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c282  nop
0x18003c283  test    edi, edi
0x18003c285  js      short loc_18003C29B
0x18003c287  mov     rax, [rsp+78h+arg_28]
0x18003c28f  mov     [rsp+78h+arg_28], r13
0x18003c297  mov     [r12], rax
0x18003c29b  mov     rcx, [rsp+78h+arg_28]
0x18003c2a3  test    rcx, rcx
0x18003c2a6  jz      short loc_18003C2BD
0x18003c2a8  mov     [rsp+78h+arg_28], r13
0x18003c2b0  mov     rdx, [rcx]
0x18003c2b3  mov     rax, [rdx+10h]
0x18003c2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c2bc  nop
0x18003c2bd  mov     eax, edi
0x18003c2bf  add     rsp, 38h
0x18003c2c3  pop     r15
0x18003c2c5  pop     r14
0x18003c2c7  pop     r13
0x18003c2c9  pop     r12
0x18003c2cb  pop     rdi
0x18003c2cc  pop     rsi
0x18003c2cd  pop     rbp
0x18003c2ce  pop     rbx
0x18003c2cf  retn
```
