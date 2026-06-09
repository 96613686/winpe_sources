# CThumbnailCache::_TryAdjustRequestSizeFromStream(IShellItem *,WTS_FLAGS,uint *)

- ea: `0x180003650`
- end: `0x1800039a0`
- name: `?_TryAdjustRequestSizeFromStream@CThumbnailCache@@AEAAJPEAUIShellItem@@W4WTS_FLAGS@@PEAI@Z`
- size: `848`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this, struct IShellItem *, enum WTS_FLAGS, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008a70`
- `0x18002d090`

## callees

- `0x180003624`
- `0x180003650`
- `0x180004bdc`
- `0x180004c60`
- `0x180005078`
- `0x180013440`
- `0x1800137b4`
- `0x180035830`
- `0x180042d38`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800036de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800036de`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180003701`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180003701`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CThumbnailCache::_TryAdjustRequestSizeFromStream(
        CThumbnailCache *this,
        struct IShellItem *a2,
        enum WTS_FLAGS a3,
        unsigned int *a4)
{
  HRESULT Instance; // ebx
  unsigned int v9; // edx
  HRESULT (__stdcall *BindToHandler)(IShellItem *, IBindCtx *, const GUID *const, const IID *const, void **); // rbx
  struct IWICImagingFactory *v11; // rdi
  HRESULT (__stdcall *CreateDecoderFromStream)(IWICImagingFactory *, IStream *, const GUID *, WICDecodeOptions, IWICBitmapDecoder **); // rbx
  struct IWICBitmapDecoder *v13; // rdi
  HRESULT (__stdcall *GetFrame)(IWICBitmapDecoder *, UINT, IWICBitmapFrameDecode **); // rbx
  struct IWICBitmapSource *v15; // rcx
  struct IWICBitmapFrameDecode *v16; // rcx
  struct IWICBitmapDecoder *v17; // rcx
  __int64 v18; // rcx
  struct IWICImagingFactory *v19; // rcx
  __int64 v20; // rcx
  unsigned int ThumbPixelSize; // eax
  unsigned int v23; // r9d
  int v24; // r10d
  struct IWICBitmapSource *v25; // [rsp+30h] [rbp-50h] BYREF
  struct IWICBitmapDecoder *v26; // [rsp+38h] [rbp-48h] BYREF
  LPBC ppbc; // [rsp+40h] [rbp-40h] BYREF
  struct IWICImagingFactory *ppv; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v29; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v30; // [rsp+54h] [rbp-2Ch] BYREF
  struct IWICBitmapFrameDecode *v31; // [rsp+58h] [rbp-28h] BYREF
  __int64 v32; // [rsp+60h] [rbp-20h] BYREF
  __int64 v33; // [rsp+68h] [rbp-18h] BYREF

  Instance = 0;
  if ( _ItemHasStream(a2) )
  {
    v33 = 0;
    Instance = Microsoft::WRL::Details::MakeAndInitialize<CThumbnailStreamBindCtx,CThumbnailStreamBindCtx,>(&v33);
    if ( Instance >= 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
      Instance = CoCreateInstance(
                   &CLSID_WICImagingFactory2,
                   0,
                   1u,
                   &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                   (LPVOID *)&ppv);
      if ( Instance < 0 )
        goto LABEL_28;
      ppbc = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppbc);
      CreateBindCtx(0, &ppbc);
      Instance = wil::ShellBindContextHelper::SetMode((wil::ShellBindContextHelper *)&ppbc, v9);
      if ( Instance >= 0 )
      {
        if ( ppbc )
        {
          Instance = ((__int64 (__fastcall *)(LPBC, const wchar_t *, __int64))ppbc->lpVtbl->RegisterObjectParam)(
                       ppbc,
                       L"BindToThumbnailStream",
                       v33);
          if ( Instance >= 0 )
          {
            v32 = 0;
            BindToHandler = a2->lpVtbl->BindToHandler;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
            Instance = ((__int64 (__fastcall *)(struct IShellItem *, LPBC, const GUID *, GUID *, __int64 *))BindToHandler)(
                         a2,
                         ppbc,
                         &BHID_Stream,
                         &GUID_0000000c_0000_0000_c000_000000000046,
                         &v32);
            if ( Instance >= 0 )
            {
              v26 = 0;
              v11 = ppv;
              CreateDecoderFromStream = ppv->lpVtbl->CreateDecoderFromStream;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
              Instance = ((__int64 (__fastcall *)(struct IWICImagingFactory *, __int64, GUID *, _QWORD, struct IWICBitmapDecoder **))CreateDecoderFromStream)(
                           v11,
                           v32,
                           &GUID_VendorMicrosoft,
                           0,
                           &v26);
              if ( Instance >= 0 )
              {
                v31 = 0;
                v13 = v26;
                GetFrame = v26->lpVtbl->GetFrame;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
                Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, _QWORD, struct IWICBitmapFrameDecode **))GetFrame)(
                             v13,
                             0,
                             &v31);
                if ( Instance >= 0 )
                {
                  v25 = 0;
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
                  Instance = WICOrientateFrame(ppv, v26, v31, 0, &v25);
                  if ( Instance >= 0 )
                  {
                    v30 = 0;
                    v29 = 0;
                    Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))v25->lpVtbl->GetSize)(
                                 v25,
                                 &v30,
                                 &v29);
                    if ( Instance >= 0 )
                      Instance = CThumbnailCache::_CalculateIdealLengthForCropping(this, v30, v29, a3, a4);
                  }
                  v15 = v25;
                  if ( v25 )
                  {
                    v25 = 0;
                    ((void (__fastcall *)(struct IWICBitmapSource *))v15->lpVtbl->Release)(v15);
                  }
                }
                v16 = v31;
                if ( v31 )
                {
                  v31 = 0;
                  ((void (__fastcall *)(struct IWICBitmapFrameDecode *))v16->lpVtbl->Release)(v16);
                }
              }
              v17 = v26;
              if ( v26 )
              {
                v26 = 0;
                ((void (__fastcall *)(struct IWICBitmapDecoder *))v17->lpVtbl->Release)(v17);
              }
            }
            v18 = v32;
            if ( v32 )
            {
              v32 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            }
          }
        }
        else
        {
          Instance = -2147024882;
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppbc);
      if ( Instance < 0 )
      {
LABEL_28:
        if ( (*(_BYTE *)(v33 + 16) & 8) == 0 )
        {
          ThumbPixelSize = CThumbnailCache::_GetThumbPixelSize((__int64)this, 1, 8);
          if ( v23 <= ThumbPixelSize )
            v23 = CThumbnailCache::_GetThumbPixelSize((__int64)this, v24 - 7, v24);
          *a4 = v23;
        }
      }
      v19 = ppv;
      if ( ppv )
      {
        ppv = 0;
        ((void (__fastcall *)(struct IWICImagingFactory *))v19->lpVtbl->Release)(v19);
      }
    }
    v20 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180003650  mov     [rsp-28h+arg_0], rbx
0x180003655  mov     [rsp-28h+arg_10], rsi
0x18000365a  push    rbp
0x18000365b  push    rdi
0x18000365c  push    r12
0x18000365e  push    r14
0x180003660  push    r15
0x180003662  mov     rbp, rsp
0x180003665  sub     rsp, 80h
0x18000366c  mov     rax, cs:__security_cookie
0x180003673  xor     rax, rsp
0x180003676  mov     [rbp+var_10], rax
0x18000367a  mov     rsi, r9
0x18000367d  mov     r15d, r8d
0x180003680  mov     rdi, rdx
0x180003683  mov     r14, rcx
0x180003686  xor     r12d, r12d
0x180003689  mov     ebx, r12d
0x18000368c  mov     rcx, rdx; struct IShellItem *
0x18000368f  call    ?_ItemHasStream@@YA_NPEAUIShellItem@@@Z; _ItemHasStream(IShellItem *)
0x180003694  test    al, al
0x180003696  jz      loc_1800038E1
0x18000369c  mov     [rbp+var_18], r12
0x1800036a0  lea     rcx, [rbp+var_18]
0x1800036a4  call    ??$MakeAndInitialize@VCThumbnailStreamBindCtx@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCThumbnailStreamBindCtx@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CThumbnailStreamBindCtx,CThumbnailStreamBindCtx,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CThumbnailStreamBindCtx>>)
0x1800036a9  mov     ebx, eax
0x1800036ab  test    eax, eax
0x1800036ad  js      loc_1800038C7
0x1800036b3  mov     [rbp+var_38], r12
0x1800036b7  lea     rcx, [rbp+var_38]
0x1800036bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800036c0  lea     rax, [rbp+var_38]
0x1800036c4  mov     [rsp+80h+ppv], rax; ppv
0x1800036c9  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x1800036d0  xor     edx, edx; pUnkOuter
0x1800036d2  lea     r8d, [r12+1]; dwClsContext
0x1800036d7  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x1800036de  call    cs:__imp_CoCreateInstance
0x1800036e4  mov     ebx, eax
0x1800036e6  test    eax, eax
0x1800036e8  js      loc_18000395A
0x1800036ee  mov     [rbp+ppbc], r12
0x1800036f2  lea     rcx, [rbp+ppbc]
0x1800036f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800036fb  lea     rdx, [rbp+ppbc]; ppbc
0x1800036ff  xor     ecx, ecx; reserved
0x180003701  call    cs:__imp_CreateBindCtx
0x180003707  nop
0x180003708  lea     rcx, [rbp+ppbc]; this
0x18000370c  call    ?SetMode@ShellBindContextHelper@wil@@QEAAJK@Z; wil::ShellBindContextHelper::SetMode(ulong)
0x180003711  mov     ebx, eax
0x180003713  test    eax, eax
0x180003715  js      loc_18000389C
0x18000371b  mov     rcx, [rbp+ppbc]
0x18000371f  test    rcx, rcx
0x180003722  jz      loc_18000390B
0x180003728  mov     rax, [rcx]
0x18000372b  mov     r8, [rbp+var_18]
0x18000372f  lea     rdx, aBindtothumbnai; "BindToThumbnailStream"
0x180003736  mov     rax, [rax+48h]
0x18000373a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000373f  mov     ebx, eax
0x180003741  test    eax, eax
0x180003743  js      loc_18000389C
0x180003749  mov     [rbp+var_20], r12
0x18000374d  mov     rax, [rdi]
0x180003750  mov     rbx, [rax+18h]
0x180003754  lea     rcx, [rbp+var_20]
0x180003758  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000375d  lea     rax, [rbp+var_20]
0x180003761  mov     [rsp+80h+ppv], rax
0x180003766  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046
0x18000376d  lea     r8, BHID_Stream
0x180003774  mov     rdx, [rbp+ppbc]
0x180003778  mov     rcx, rdi
0x18000377b  mov     rax, rbx
0x18000377e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003783  mov     ebx, eax
0x180003785  test    eax, eax
0x180003787  js      loc_180003882
0x18000378d  mov     [rbp+var_48], r12
0x180003791  mov     rdi, [rbp+var_38]
0x180003795  mov     rax, [rdi]
0x180003798  mov     rbx, [rax+20h]
0x18000379c  lea     rcx, [rbp+var_48]
0x1800037a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800037a5  lea     rax, [rbp+var_48]
0x1800037a9  mov     [rsp+80h+ppv], rax
0x1800037ae  xor     r9d, r9d
0x1800037b1  lea     r8, GUID_VendorMicrosoft
0x1800037b8  mov     rdx, [rbp+var_20]
0x1800037bc  mov     rcx, rdi
0x1800037bf  mov     rax, rbx
0x1800037c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c7  mov     ebx, eax
0x1800037c9  test    eax, eax
0x1800037cb  js      loc_180003868
0x1800037d1  mov     [rbp+var_28], r12
0x1800037d5  mov     rdi, [rbp+var_48]
0x1800037d9  mov     rax, [rdi]
0x1800037dc  mov     rbx, [rax+68h]
0x1800037e0  lea     rcx, [rbp+var_28]
0x1800037e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800037e9  lea     r8, [rbp+var_28]
0x1800037ed  xor     edx, edx
0x1800037ef  mov     rcx, rdi
0x1800037f2  mov     rax, rbx
0x1800037f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037fa  mov     ebx, eax
0x1800037fc  test    eax, eax
0x1800037fe  js      short loc_18000384E
0x180003800  mov     [rbp+var_50], r12
0x180003804  lea     rcx, [rbp+var_50]
0x180003808  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000380d  lea     rax, [rbp+var_50]
0x180003811  mov     [rsp+80h+ppv], rax; struct IWICBitmapSource **
0x180003816  xor     r9d, r9d; bool
0x180003819  mov     r8, [rbp+var_28]; struct IWICBitmapFrameDecode *
0x18000381d  mov     rdx, [rbp+var_48]; struct IWICBitmapDecoder *
0x180003821  mov     rcx, [rbp+var_38]; struct IWICImagingFactory *
0x180003825  call    ?WICOrientateFrame@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapDecoder@@PEAUIWICBitmapFrameDecode@@_NPEAPEAUIWICBitmapSource@@@Z; WICOrientateFrame(IWICImagingFactory *,IWICBitmapDecoder *,IWICBitmapFrameDecode *,bool,IWICBitmapSource * *)
0x18000382a  mov     ebx, eax
0x18000382c  test    eax, eax
0x18000382e  jns     loc_180003912
0x180003834  mov     rcx, [rbp+var_50]
0x180003838  test    rcx, rcx
0x18000383b  jz      short loc_18000384E
0x18000383d  mov     [rbp+var_50], r12
0x180003841  mov     rax, [rcx]
0x180003844  mov     rax, [rax+10h]
0x180003848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000384d  nop
0x18000384e  mov     rcx, [rbp+var_28]
0x180003852  test    rcx, rcx
0x180003855  jz      short loc_180003868
0x180003857  mov     [rbp+var_28], r12
0x18000385b  mov     rax, [rcx]
0x18000385e  mov     rax, [rax+10h]
0x180003862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003867  nop
0x180003868  mov     rcx, [rbp+var_48]
0x18000386c  test    rcx, rcx
0x18000386f  jz      short loc_180003882
0x180003871  mov     [rbp+var_48], r12
0x180003875  mov     rax, [rcx]
0x180003878  mov     rax, [rax+10h]
0x18000387c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003881  nop
0x180003882  mov     rcx, [rbp+var_20]
0x180003886  test    rcx, rcx
0x180003889  jz      short loc_18000389C
0x18000388b  mov     [rbp+var_20], r12
0x18000388f  mov     rax, [rcx]
0x180003892  mov     rax, [rax+10h]
0x180003896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000389b  nop
0x18000389c  lea     rcx, [rbp+ppbc]
0x1800038a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800038a5  test    ebx, ebx
0x1800038a7  js      loc_18000395A
0x1800038ad  mov     rcx, [rbp+var_38]
0x1800038b1  test    rcx, rcx
0x1800038b4  jz      short loc_1800038C7
0x1800038b6  mov     [rbp+var_38], r12
0x1800038ba  mov     rax, [rcx]
0x1800038bd  mov     rax, [rax+10h]
0x1800038c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038c6  nop
0x1800038c7  mov     rcx, [rbp+var_18]
0x1800038cb  test    rcx, rcx
0x1800038ce  jz      short loc_1800038E1
0x1800038d0  mov     [rbp+var_18], r12
0x1800038d4  mov     rax, [rcx]
0x1800038d7  mov     rax, [rax+10h]
0x1800038db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038e0  nop
0x1800038e1  mov     eax, ebx
0x1800038e3  mov     rcx, [rbp+var_10]
0x1800038e7  xor     rcx, rsp; StackCookie
0x1800038ea  call    __security_check_cookie
0x1800038ef  lea     r11, [rsp+80h+var_s0]
0x1800038f7  mov     rbx, [r11+30h]
0x1800038fb  mov     rsi, [r11+40h]
0x1800038ff  mov     rsp, r11
0x180003902  pop     r15
0x180003904  pop     r14
0x180003906  pop     r12
0x180003908  pop     rdi
0x180003909  pop     rbp
0x18000390a  retn
0x18000390b  mov     ebx, 8007000Eh
0x180003910  jmp     short loc_18000389C
0x180003912  mov     [rbp+var_2C], r12d
0x180003916  mov     [rbp+var_30], r12d
0x18000391a  mov     rcx, [rbp+var_50]
0x18000391e  mov     rax, [rcx]
0x180003921  lea     r8, [rbp+var_30]
0x180003925  lea     rdx, [rbp+var_2C]
0x180003929  mov     rax, [rax+18h]
0x18000392d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003932  mov     ebx, eax
0x180003934  test    eax, eax
0x180003936  js      loc_180003834
0x18000393c  mov     [rsp+80h+ppv], rsi; unsigned int *
0x180003941  mov     r9d, r15d; enum WTS_FLAGS
0x180003944  mov     r8d, [rbp+var_30]; unsigned int
0x180003948  mov     edx, [rbp+var_2C]; unsigned int
0x18000394b  mov     rcx, r14; this
0x18000394e  call    ?_CalculateIdealLengthForCropping@CThumbnailCache@@AEAAJIIW4WTS_FLAGS@@PEAI@Z; CThumbnailCache::_CalculateIdealLengthForCropping(uint,uint,WTS_FLAGS,uint *)
0x180003953  mov     ebx, eax
0x180003955  jmp     loc_180003834
0x18000395a  mov     rax, [rbp+var_18]
0x18000395e  mov     r10d, 8
0x180003964  test    [rax+10h], r10b
0x180003968  jnz     loc_1800038AD
0x18000396e  mov     r9d, [rsi]
0x180003971  mov     r8d, r10d
0x180003974  lea     edx, [r10-7]
0x180003978  mov     rcx, r14
0x18000397b  call    ?_GetThumbPixelSize@CThumbnailCache@@AEAAIHW4THUMBSIZE@@@Z; CThumbnailCache::_GetThumbPixelSize(int,THUMBSIZE)
0x180003980  cmp     r9d, eax
0x180003983  ja      short loc_180003997
0x180003985  mov     r8d, r10d
0x180003988  lea     edx, [r10-7]
0x18000398c  mov     rcx, r14
0x18000398f  call    ?_GetThumbPixelSize@CThumbnailCache@@AEAAIHW4THUMBSIZE@@@Z; CThumbnailCache::_GetThumbPixelSize(int,THUMBSIZE)
0x180003994  mov     r9d, eax
0x180003997  mov     [rsi], r9d
0x18000399a  jmp     loc_1800038AD
```
