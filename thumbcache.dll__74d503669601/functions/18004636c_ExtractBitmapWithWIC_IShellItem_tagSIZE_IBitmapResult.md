# ExtractBitmapWithWIC(IShellItem *,tagSIZE,IBitmapResult * *)

- ea: `0x18004636c`
- end: `0x18004658b`
- name: `?ExtractBitmapWithWIC@@YAJPEAUIShellItem@@UtagSIZE@@PEAPEAUIBitmapResult@@@Z`
- size: `543`
- prototype: `int(struct IShellItem *, struct tagSIZE, struct IBitmapResult **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180046758`

## callees

- `0x180003624`
- `0x1800045e4`
- `0x180004bdc`
- `0x180004e90`
- `0x1800060a4`
- `0x180006f4c`
- `0x180035830`
- `0x18004636c`
- `0x180046e90`
- `0x180047a40`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004642b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004642b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ExtractBitmapWithWIC(struct IShellItem *a1, struct tagSIZE a2, const struct _GUID *a3)
{
  unsigned int v6; // edx
  int Instance; // edi
  HRESULT (__stdcall *BindToHandler)(IShellItem *, IBindCtx *, const GUID *const, const IID *const, void **); // rdi
  bool v9; // r9
  const struct _GUID *v10; // r8
  const struct tagSIZE *v11; // r9
  enum WICBitmapInterpolationMode v12; // r8d
  LPVOID *ppv; // [rsp+20h] [rbp-50h]
  bool ppva; // [rsp+20h] [rbp-50h]
  LPVOID *ppvb; // [rsp+20h] [rbp-50h]
  struct IWICBitmapSource *v17; // [rsp+30h] [rbp-40h] BYREF
  struct IWICImagingFactory *v18; // [rsp+38h] [rbp-38h] BYREF
  struct IWICBitmapSource *v19; // [rsp+40h] [rbp-30h] BYREF
  __int64 v20; // [rsp+48h] [rbp-28h] BYREF
  LPBC ppbc; // [rsp+50h] [rbp-20h] BYREF
  GUID Buf1; // [rsp+58h] [rbp-18h] BYREF

  *(_QWORD *)&a3->Data1 = 0;
  wil::ShellBindContextHelper::ShellBindContextHelper(&ppbc, *(struct IBindCtx **)&a2);
  Instance = wil::ShellBindContextHelper::SetMode((wil::ShellBindContextHelper *)&ppbc, v6);
  if ( Instance >= 0 )
  {
    v20 = 0;
    BindToHandler = a1->lpVtbl->BindToHandler;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    Instance = ((__int64 (__fastcall *)(struct IShellItem *, LPBC, const GUID *, GUID *, __int64 *))BindToHandler)(
                 a1,
                 ppbc,
                 &BHID_Stream,
                 &GUID_0000000c_0000_0000_c000_000000000046,
                 &v20);
    if ( Instance < 0 )
    {
LABEL_15:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
      goto LABEL_16;
    }
    v18 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    Instance = CoCreateInstance(
                 &CLSID_WICImagingFactory2,
                 0,
                 1u,
                 &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                 (LPVOID *)&v18);
    if ( Instance < 0 )
    {
LABEL_14:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
      goto LABEL_15;
    }
    Buf1 = 0;
    v19 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    Instance = LoadImageWithWIC(v18, v20, 2, &v19, (__int64)ppv, &Buf1);
    if ( Instance < 0 )
    {
LABEL_13:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      goto LABEL_14;
    }
    v17 = 0;
    if ( !memcmp_0(&Buf1, &GUID_ContainerFormatBmp, 0x10u)
      || !memcmp_0(&Buf1, &GUID_ContainerFormatJpeg, 0x10u)
      || !memcmp_0(&Buf1, &GUID_ContainerFormatPng, 0x10u) )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
      Instance = ScaleWICBitmapSource(v18, v19, v12, a2, ppva, &v17);
      if ( Instance >= 0 )
        goto LABEL_11;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
      Instance = ScaleImageWithWIC(v18, v19, a2, v9, &v17);
      if ( Instance >= 0 )
      {
        Buf1 = GUID_ContainerFormatBmp;
LABEL_11:
        Instance = Windows::Internal::Thumbnails::CreateBitmapResult(
                     (Windows::Internal::Thumbnails *)v17,
                     (struct IWICBitmapSource *)&Buf1,
                     v10,
                     v11,
                     (const int *)ppvb,
                     a3,
                     (void **)&v17->lpVtbl);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
    goto LABEL_13;
  }
LABEL_16:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppbc);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18004636c  push    rbp
0x18004636e  push    rbx
0x18004636f  push    rsi
0x180046370  push    rdi
0x180046371  push    r14
0x180046373  mov     rbp, rsp
0x180046376  sub     rsp, 70h
0x18004637a  mov     rax, cs:__security_cookie
0x180046381  xor     rax, rsp
0x180046384  mov     [rbp+var_8], rax
0x180046388  mov     rsi, r8
0x18004638b  mov     rbx, rdx
0x18004638e  mov     r14, rcx
0x180046391  mov     qword ptr [r8], 0
0x180046398  lea     rcx, [rbp+ppbc]; ppbc
0x18004639c  call    ??0ShellBindContextHelper@wil@@QEAA@PEAUIBindCtx@@@Z; wil::ShellBindContextHelper::ShellBindContextHelper(IBindCtx *)
0x1800463a1  nop
0x1800463a2  lea     rcx, [rbp+ppbc]; this
0x1800463a6  call    ?SetMode@ShellBindContextHelper@wil@@QEAAJK@Z; wil::ShellBindContextHelper::SetMode(ulong)
0x1800463ab  mov     edi, eax
0x1800463ad  test    eax, eax
0x1800463af  js      loc_180046569
0x1800463b5  mov     [rbp+var_28], 0
0x1800463bd  mov     rax, [r14]
0x1800463c0  mov     rdi, [rax+18h]
0x1800463c4  lea     rcx, [rbp+var_28]
0x1800463c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800463cd  lea     rax, [rbp+var_28]
0x1800463d1  mov     [rsp+70h+ppv], rax
0x1800463d6  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046
0x1800463dd  lea     r8, BHID_Stream
0x1800463e4  mov     rdx, [rbp+ppbc]
0x1800463e8  mov     rcx, r14
0x1800463eb  mov     rax, rdi
0x1800463ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463f3  mov     edi, eax
0x1800463f5  test    eax, eax
0x1800463f7  js      loc_18004655F
0x1800463fd  mov     [rbp+var_38], 0
0x180046405  lea     rcx, [rbp+var_38]
0x180046409  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004640e  lea     rax, [rbp+var_38]
0x180046412  mov     [rsp+70h+ppv], rax; int *
0x180046417  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18004641e  xor     edx, edx; pUnkOuter
0x180046420  lea     r8d, [rdx+1]; dwClsContext
0x180046424  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18004642b  call    cs:__imp_CoCreateInstance
0x180046431  mov     edi, eax
0x180046433  test    eax, eax
0x180046435  js      loc_180046555
0x18004643b  xorps   xmm0, xmm0
0x18004643e  movups  [rbp+Buf1], xmm0
0x180046442  mov     [rbp+var_30], 0
0x18004644a  lea     rcx, [rbp+var_30]
0x18004644e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046453  lea     rax, [rbp+Buf1]
0x180046457  mov     [rsp+70h+var_48], rax
0x18004645c  lea     r9, [rbp+var_30]
0x180046460  mov     r8d, 2
0x180046466  mov     rdx, [rbp+var_28]
0x18004646a  mov     rcx, [rbp+var_38]
0x18004646e  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIStream@@W4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAPEAUIWICBitmapFrameDecode@@PEAU_GUID@@@Z; LoadImageWithWIC(IWICImagingFactory *,IStream *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,IWICBitmapFrameDecode * *,_GUID *)
0x180046473  mov     edi, eax
0x180046475  test    eax, eax
0x180046477  js      loc_18004654B
0x18004647d  mov     [rbp+var_40], 0
0x180046485  mov     edi, 10h
0x18004648a  mov     r8d, edi; Size
0x18004648d  lea     rdx, GUID_ContainerFormatBmp; Buf2
0x180046494  lea     rcx, [rbp+Buf1]; Buf1
0x180046498  call    memcmp_0
0x18004649d  test    eax, eax
0x18004649f  jz      short loc_180046505
0x1800464a1  mov     r8d, edi; Size
0x1800464a4  lea     rdx, GUID_ContainerFormatJpeg; Buf2
0x1800464ab  lea     rcx, [rbp+Buf1]; Buf1
0x1800464af  call    memcmp_0
0x1800464b4  test    eax, eax
0x1800464b6  jz      short loc_180046505
0x1800464b8  mov     r8d, edi; Size
0x1800464bb  lea     rdx, GUID_ContainerFormatPng; Buf2
0x1800464c2  lea     rcx, [rbp+Buf1]; Buf1
0x1800464c6  call    memcmp_0
0x1800464cb  test    eax, eax
0x1800464cd  jz      short loc_180046505
0x1800464cf  lea     rcx, [rbp+var_40]
0x1800464d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800464d8  lea     rax, [rbp+var_40]
0x1800464dc  mov     [rsp+70h+ppv], rax; struct IWICBitmapSource **
0x1800464e1  mov     r8, rbx; struct tagSIZE
0x1800464e4  mov     rdx, [rbp+var_30]; struct IWICBitmapSource *
0x1800464e8  mov     rcx, [rbp+var_38]; struct IWICImagingFactory *
0x1800464ec  call    ?ScaleImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@UtagSIZE@@_NPEAPEAU2@@Z; ScaleImageWithWIC(IWICImagingFactory *,IWICBitmapSource *,tagSIZE,bool,IWICBitmapSource * *)
0x1800464f1  mov     edi, eax
0x1800464f3  test    eax, eax
0x1800464f5  js      short loc_180046541
0x1800464f7  movups  xmm0, xmmword ptr cs:GUID_ContainerFormatBmp.Data1
0x1800464fe  movdqu  [rbp+Buf1], xmm0
0x180046503  jmp     short loc_18004652D
0x180046505  lea     rcx, [rbp+var_40]
0x180046509  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004650e  lea     rax, [rbp+var_40]
0x180046512  mov     [rsp+70h+var_48], rax; struct IWICBitmapSource **
0x180046517  mov     r9, rbx; struct tagSIZE
0x18004651a  mov     rdx, [rbp+var_30]; struct IWICBitmapSource *
0x18004651e  mov     rcx, [rbp+var_38]; struct IWICImagingFactory *
0x180046522  call    ?ScaleWICBitmapSource@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@W4WICBitmapInterpolationMode@@UtagSIZE@@_NPEAPEAU2@@Z; ScaleWICBitmapSource(IWICImagingFactory *,IWICBitmapSource *,WICBitmapInterpolationMode,tagSIZE,bool,IWICBitmapSource * *)
0x180046527  mov     edi, eax
0x180046529  test    eax, eax
0x18004652b  js      short loc_180046541
0x18004652d  mov     [rsp+70h+var_48], rsi; struct _GUID *
0x180046532  lea     rdx, [rbp+Buf1]; struct IWICBitmapSource *
0x180046536  mov     rcx, [rbp+var_40]; this
0x18004653a  call    ?CreateBitmapResult@Thumbnails@Internal@Windows@@YAJPEAUIWICBitmapSource@@AEBU_GUID@@PEBUtagSIZE@@PEBH1PEAPEAX@Z; Windows::Internal::Thumbnails::CreateBitmapResult(IWICBitmapSource *,_GUID const &,tagSIZE const *,int const *,_GUID const &,void * *)
0x18004653f  mov     edi, eax
0x180046541  lea     rcx, [rbp+var_40]
0x180046545  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004654a  nop
0x18004654b  lea     rcx, [rbp+var_30]
0x18004654f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046554  nop
0x180046555  lea     rcx, [rbp+var_38]
0x180046559  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004655e  nop
0x18004655f  lea     rcx, [rbp+var_28]
0x180046563  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046568  nop
0x180046569  lea     rcx, [rbp+ppbc]
0x18004656d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046572  mov     eax, edi
0x180046574  mov     rcx, [rbp+var_8]
0x180046578  xor     rcx, rsp; StackCookie
0x18004657b  call    __security_check_cookie
0x180046580  add     rsp, 70h
0x180046584  pop     r14
0x180046586  pop     rdi
0x180046587  pop     rsi
0x180046588  pop     rbx
0x180046589  pop     rbp
0x18004658a  retn
```
