# Windows::Internal::Thumbnails::CBitmapResult::_GetResultAs(BITMAP_RESULT_TYPE,_GUID const &,_GUID const &,void * *)

- ea: `0x1800078c4`
- end: `0x180007ca8`
- name: `?_GetResultAs@CBitmapResult@Thumbnails@Internal@Windows@@AEAAJW4BITMAP_RESULT_TYPE@@AEBU_GUID@@1PEAPEAX@Z`
- size: `996`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006230`
- `0x1800298e0`

## callees

- `0x180003624`
- `0x180005bd8`
- `0x180005d38`
- `0x180006274`
- `0x1800063cc`
- `0x180006588`
- `0x18000701c`
- `0x1800078c4`
- `0x180007cb0`
- `0x180008014`
- `0x180035830`
- `0x180047a40`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800079bd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800079bd`
- `GDI32!DeleteObject` at `0x180007a24`
- `GDI32!DeleteObject` at `0x180007a24`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Internal::Thumbnails::CBitmapResult::_GetResultAs(
        __int64 a1,
        int a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        void **a5)
{
  HRESULT WicBitmapSource; // ebx
  int v10; // r14d
  int v11; // r14d
  struct IStream *v12; // rcx
  struct IWICImagingFactory *v13; // rcx
  struct IWICBitmapSource *v14; // rcx
  __int64 v16; // rax
  GUID v17; // xmm6
  __int64 v18; // rdx
  __int64 v19; // r8
  struct IStream *v20; // rcx
  struct IWICImagingFactory *v21; // rcx
  __int64 v22; // rax
  const struct _GUID *v23; // rdx
  Windows::Internal::Thumbnails::CBitmapResult *v24; // rcx
  struct IStream *v25; // rcx
  __int64 v26; // rax
  struct IWICImagingFactory *v27; // [rsp+38h] [rbp-41h] BYREF
  struct IWICBitmapSource *v28; // [rsp+40h] [rbp-39h] BYREF
  GUID v29; // [rsp+48h] [rbp-31h] BYREF
  struct IStream *ppv[2]; // [rsp+58h] [rbp-21h] BYREF
  HGDIOBJ ho[2]; // [rsp+68h] [rbp-11h] BYREF

  if ( *(_DWORD *)(a1 + 68) != a2 )
    goto LABEL_2;
  if ( *(_DWORD *)(a1 + 68) != 3 )
    return (unsigned int)(***(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))(a1 + 80))(
                           *(_QWORD *)(a1 + 80),
                           a4,
                           a5);
  v22 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v22 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( !v22 )
    goto LABEL_44;
  v26 = *(_QWORD *)(a1 + 52) - *(_QWORD *)&a3->Data1;
  if ( !v26 )
    v26 = *(_QWORD *)(a1 + 60) - *(_QWORD *)a3->Data4;
  if ( v26 )
  {
LABEL_2:
    *(_OWORD *)ho = 0;
    v28 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    WicBitmapSource = Windows::Internal::Thumbnails::CBitmapResult::_GetWicBitmapSource(
                        (Windows::Internal::Thumbnails::CBitmapResult *)a1,
                        &v28,
                        (struct _GUID *)ho);
    if ( WicBitmapSource >= 0 )
    {
      v10 = a2 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 == 1 )
          {
            WicBitmapSource = Windows::Internal::Thumbnails::CBitmapResult::TryGetStream(
                                (Windows::Internal::Thumbnails::CBitmapResult *)a1,
                                a3,
                                a4,
                                a5);
            if ( WicBitmapSource < 0 )
            {
              v27 = 0;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
              WicBitmapSource = Windows::Internal::Thumbnails::CBitmapResult::_GetImagingFactory(
                                  (Windows::Internal::Thumbnails::CBitmapResult *)a1,
                                  &v27);
              if ( WicBitmapSource >= 0 )
              {
                v16 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_NULL.Data1;
                if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
                  v16 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_NULL.Data4;
                if ( v16 )
                  *(struct _GUID *)ho = *a3;
                if ( !memcmp_0(ho, &GUID_ContainerFormatJpeg, 0x10u) )
                  v17 = GUID_WICPixelFormat24bppRGB;
                else
                  v17 = GUID_WICPixelFormat32bppBGRA;
                ppv[0] = 0;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppv);
                v29 = v17;
                WicBitmapSource = GetStreamOfWICBitmapSourceWithOptions(v27, v28, ho, &v29, 3, ppv);
                if ( WicBitmapSource >= 0 )
                {
                  *(struct _GUID *)(a1 + 104) = *a3;
                  WicBitmapSource = AgileGitPtr::Initialize(a1 + 120, v18, v19, ppv[0]);
                  if ( WicBitmapSource >= 0 )
                    WicBitmapSource = Windows::Internal::Thumbnails::CBitmapResult::TryGetStream(
                                        (Windows::Internal::Thumbnails::CBitmapResult *)a1,
                                        a3,
                                        a4,
                                        a5);
                }
                v20 = ppv[0];
                if ( ppv[0] )
                {
                  ppv[0] = 0;
                  (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v20 + 16LL))(v20);
                }
              }
              v21 = v27;
              if ( v27 )
              {
                v27 = 0;
                ((void (__fastcall *)(struct IWICImagingFactory *))v21->lpVtbl->Release)(v21);
              }
            }
          }
        }
        else
        {
          v27 = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
          WicBitmapSource = Windows::Internal::Thumbnails::CBitmapResult::_GetImagingFactory(
                              (Windows::Internal::Thumbnails::CBitmapResult *)a1,
                              &v27);
          if ( WicBitmapSource >= 0 )
          {
            ho[0] = 0;
            WicBitmapSource = ConvertIWICBitmapSourceTo32bppHBITMAP(v28, v27, (HBITMAP *)ho);
            if ( WicBitmapSource >= 0 )
            {
              ppv[0] = 0;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppv);
              WicBitmapSource = CoCreateInstance(
                                  &CLSID_SharedBitmap,
                                  0,
                                  1u,
                                  &GUID_091162a4_bc96_411f_aae8_c5122cd03363,
                                  (LPVOID *)ppv);
              if ( WicBitmapSource >= 0 )
              {
                WicBitmapSource = (*(__int64 (__fastcall **)(struct IStream *, HGDIOBJ, _QWORD))(*(_QWORD *)ppv[0] + 48LL))(
                                    ppv[0],
                                    ho[0],
                                    0);
                if ( WicBitmapSource >= 0 )
                {
                  ho[0] = 0;
                  WicBitmapSource = (**(__int64 (__fastcall ***)(struct IStream *, const struct _GUID *, void **))ppv[0])(
                                      ppv[0],
                                      a4,
                                      a5);
                }
              }
              v12 = ppv[0];
              if ( ppv[0] )
              {
                ppv[0] = 0;
                (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v12 + 16LL))(v12);
              }
            }
            if ( ho[0] )
              DeleteObject(ho[0]);
          }
          v13 = v27;
          if ( v27 )
          {
            v27 = 0;
            ((void (__fastcall *)(struct IWICImagingFactory *))v13->lpVtbl->Release)(v13);
          }
        }
      }
      else
      {
        WicBitmapSource = ((__int64 (__fastcall *)(struct IWICBitmapSource *, const struct _GUID *, void **))v28->lpVtbl->QueryInterface)(
                            v28,
                            a4,
                            a5);
      }
    }
    v14 = v28;
    if ( v28 )
    {
      v28 = 0;
      ((void (__fastcall *)(struct IWICBitmapSource *))v14->lpVtbl->Release)(v14);
    }
  }
  else
  {
LABEL_44:
    ppv[0] = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppv);
    WicBitmapSource = AgileGitPtr::CopyLocal((AgileGitPtr *)(a1 + 88), v23, (void **)ppv);
    if ( WicBitmapSource >= 0 )
      WicBitmapSource = Windows::Internal::Thumbnails::CBitmapResult::CloneStream(v24, ppv[0], a4, a5);
    v25 = ppv[0];
    if ( ppv[0] )
    {
      ppv[0] = 0;
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v25 + 16LL))(v25);
    }
  }
  return (unsigned int)WicBitmapSource;
}

```

## disassembly

```asm
0x1800078c4  mov     rax, rsp
0x1800078c7  mov     [rax+10h], rbx
0x1800078cb  push    rbp
0x1800078cc  push    rsi
0x1800078cd  push    rdi
0x1800078ce  push    r12
0x1800078d0  push    r13
0x1800078d2  push    r14
0x1800078d4  push    r15
0x1800078d6  lea     rbp, [rax-57h]
0x1800078da  sub     rsp, 90h
0x1800078e1  movaps  xmmword ptr [rax-48h], xmm6
0x1800078e5  mov     rax, cs:__security_cookie
0x1800078ec  xor     rax, rsp
0x1800078ef  mov     [rbp+4Fh+var_50], rax
0x1800078f3  mov     r15, r9
0x1800078f6  mov     rsi, r8
0x1800078f9  mov     r14d, edx
0x1800078fc  mov     rdi, rcx
0x1800078ff  mov     r12, [rbp+4Fh+arg_20]
0x180007903  xor     r13d, r13d
0x180007906  cmp     [rcx+44h], edx
0x180007909  jz      loc_180007A8D
0x18000790f  xorps   xmm0, xmm0
0x180007912  movups  xmmword ptr [rbp+4Fh+ho], xmm0
0x180007916  mov     [rbp+4Fh+var_88], r13
0x18000791a  lea     rcx, [rbp+4Fh+var_88]
0x18000791e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007923  lea     r8, [rbp+4Fh+ho]; struct _GUID *
0x180007927  lea     rdx, [rbp+4Fh+var_88]; struct IWICBitmapSource **
0x18000792b  mov     rcx, rdi; this
0x18000792e  call    ?_GetWicBitmapSource@CBitmapResult@Thumbnails@Internal@Windows@@AEAAJPEAPEAUIWICBitmapSource@@PEAU_GUID@@@Z; Windows::Internal::Thumbnails::CBitmapResult::_GetWicBitmapSource(IWICBitmapSource * *,_GUID *)
0x180007933  mov     ebx, eax
0x180007935  test    eax, eax
0x180007937  js      loc_180007A45
0x18000793d  sub     r14d, 1
0x180007941  jz      loc_180007AB0
0x180007947  sub     r14d, 1
0x18000794b  jnz     loc_180007ACC
0x180007951  mov     [rbp+4Fh+var_90], r13
0x180007955  lea     rcx, [rbp+4Fh+var_90]
0x180007959  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000795e  lea     rdx, [rbp+4Fh+var_90]; struct IWICImagingFactory **
0x180007962  mov     rcx, rdi; this
0x180007965  call    ?_GetImagingFactory@CBitmapResult@Thumbnails@Internal@Windows@@AEAAJPEAPEAUIWICImagingFactory@@@Z; Windows::Internal::Thumbnails::CBitmapResult::_GetImagingFactory(IWICImagingFactory * *)
0x18000796a  mov     ebx, eax
0x18000796c  test    eax, eax
0x18000796e  js      loc_180007A2B
0x180007974  mov     [rbp+4Fh+ho], r13
0x180007978  lea     r8, [rbp+4Fh+ho]; HBITMAP *
0x18000797c  mov     rdx, [rbp+4Fh+var_90]; struct IWICImagingFactory *
0x180007980  mov     rcx, [rbp+4Fh+var_88]; struct IWICBitmapSource *
0x180007984  call    ?ConvertIWICBitmapSourceTo32bppHBITMAP@@YAJPEAUIWICBitmapSource@@PEAUIWICImagingFactory@@PEAPEAUHBITMAP__@@@Z; ConvertIWICBitmapSourceTo32bppHBITMAP(IWICBitmapSource *,IWICImagingFactory *,HBITMAP__ * *)
0x180007989  mov     ebx, eax
0x18000798b  test    eax, eax
0x18000798d  js      loc_180007A1B
0x180007993  mov     [rbp+4Fh+var_70], r13
0x180007997  lea     rcx, [rbp+4Fh+var_70]
0x18000799b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800079a0  lea     rax, [rbp+4Fh+var_70]
0x1800079a4  mov     [rsp+0C0h+ppv], rax; ppv
0x1800079a9  lea     r9, _GUID_091162a4_bc96_411f_aae8_c5122cd03363; riid
0x1800079b0  xor     edx, edx; pUnkOuter
0x1800079b2  lea     r8d, [r14+1]; dwClsContext
0x1800079b6  lea     rcx, CLSID_SharedBitmap; rclsid
0x1800079bd  call    cs:__imp_CoCreateInstance
0x1800079c3  mov     ebx, eax
0x1800079c5  test    eax, eax
0x1800079c7  js      short loc_180007A01
0x1800079c9  mov     rcx, [rbp+4Fh+var_70]
0x1800079cd  mov     rax, [rcx]
0x1800079d0  xor     r8d, r8d
0x1800079d3  mov     rdx, [rbp+4Fh+ho]
0x1800079d7  mov     rax, [rax+30h]
0x1800079db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e0  mov     ebx, eax
0x1800079e2  test    eax, eax
0x1800079e4  js      short loc_180007A01
0x1800079e6  mov     [rbp+4Fh+ho], r13
0x1800079ea  mov     rcx, [rbp+4Fh+var_70]
0x1800079ee  mov     rax, [rcx]
0x1800079f1  mov     r8, r12
0x1800079f4  mov     rdx, r15
0x1800079f7  mov     rax, [rax]
0x1800079fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079ff  mov     ebx, eax
0x180007a01  mov     rcx, [rbp+4Fh+var_70]
0x180007a05  test    rcx, rcx
0x180007a08  jz      short loc_180007A1B
0x180007a0a  mov     [rbp+4Fh+var_70], r13
0x180007a0e  mov     rax, [rcx]
0x180007a11  mov     rax, [rax+10h]
0x180007a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a1a  nop
0x180007a1b  mov     rcx, [rbp+4Fh+ho]; ho
0x180007a1f  test    rcx, rcx
0x180007a22  jz      short loc_180007A2B
0x180007a24  call    cs:__imp_DeleteObject
0x180007a2a  nop
0x180007a2b  mov     rcx, [rbp+4Fh+var_90]
0x180007a2f  test    rcx, rcx
0x180007a32  jz      short loc_180007A45
0x180007a34  mov     [rbp+4Fh+var_90], r13
0x180007a38  mov     rax, [rcx]
0x180007a3b  mov     rax, [rax+10h]
0x180007a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a44  nop
0x180007a45  mov     rcx, [rbp+4Fh+var_88]
0x180007a49  test    rcx, rcx
0x180007a4c  jz      short loc_180007A5F
0x180007a4e  mov     [rbp+4Fh+var_88], r13
0x180007a52  mov     rax, [rcx]
0x180007a55  mov     rax, [rax+10h]
0x180007a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a5e  nop
0x180007a5f  mov     eax, ebx
0x180007a61  mov     rcx, [rbp+4Fh+var_50]
0x180007a65  xor     rcx, rsp; StackCookie
0x180007a68  call    __security_check_cookie
0x180007a6d  lea     r11, [rsp+0C0h+var_30]
0x180007a75  mov     rbx, [r11+48h]
0x180007a79  movaps  xmm6, xmmword ptr [r11-10h]
0x180007a7e  mov     rsp, r11
0x180007a81  pop     r15
0x180007a83  pop     r14
0x180007a85  pop     r13
0x180007a87  pop     r12
0x180007a89  pop     rdi
0x180007a8a  pop     rsi
0x180007a8b  pop     rbp
0x180007a8c  retn
0x180007a8d  cmp     dword ptr [rcx+44h], 3
0x180007a91  jz      loc_180007C20
0x180007a97  mov     rcx, [rcx+50h]
0x180007a9b  mov     rax, [rcx]
0x180007a9e  mov     r8, r12
0x180007aa1  mov     rdx, r15
0x180007aa4  mov     rax, [rax]
0x180007aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aac  mov     ebx, eax
0x180007aae  jmp     short loc_180007A5F
0x180007ab0  mov     rcx, [rbp+4Fh+var_88]
0x180007ab4  mov     rax, [rcx]
0x180007ab7  mov     r8, r12
0x180007aba  mov     rdx, r15
0x180007abd  mov     rax, [rax]
0x180007ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ac5  mov     ebx, eax
0x180007ac7  jmp     loc_180007A45
0x180007acc  cmp     r14d, 1
0x180007ad0  jnz     loc_180007A45
0x180007ad6  mov     r9, r12; void **
0x180007ad9  mov     r8, r15; struct _GUID *
0x180007adc  mov     rdx, rsi; struct _GUID *
0x180007adf  mov     rcx, rdi; this
0x180007ae2  call    ?TryGetStream@CBitmapResult@Thumbnails@Internal@Windows@@AEAAJAEBU_GUID@@0PEAPEAX@Z; Windows::Internal::Thumbnails::CBitmapResult::TryGetStream(_GUID const &,_GUID const &,void * *)
0x180007ae7  mov     ebx, eax
0x180007ae9  test    eax, eax
0x180007aeb  jns     loc_180007A45
0x180007af1  mov     [rbp+4Fh+var_90], r13
0x180007af5  lea     rcx, [rbp+4Fh+var_90]
0x180007af9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007afe  lea     rdx, [rbp+4Fh+var_90]; struct IWICImagingFactory **
0x180007b02  mov     rcx, rdi; this
0x180007b05  call    ?_GetImagingFactory@CBitmapResult@Thumbnails@Internal@Windows@@AEAAJPEAPEAUIWICImagingFactory@@@Z; Windows::Internal::Thumbnails::CBitmapResult::_GetImagingFactory(IWICImagingFactory * *)
0x180007b0a  mov     ebx, eax
0x180007b0c  test    eax, eax
0x180007b0e  js      loc_180007BE7
0x180007b14  mov     rax, [rsi]
0x180007b17  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180007b1e  jnz     short loc_180007B2B
0x180007b20  mov     rax, [rsi+8]
0x180007b24  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180007b2b  test    rax, rax
0x180007b2e  jz      loc_180007C06
0x180007b34  movups  xmm0, xmmword ptr [rsi]
0x180007b37  movdqu  xmmword ptr [rbp+4Fh+ho], xmm0
0x180007b3c  mov     r8d, 10h; Size
0x180007b42  lea     rdx, GUID_ContainerFormatJpeg; Buf2
0x180007b49  lea     rcx, [rbp+4Fh+ho]; Buf1
0x180007b4d  call    memcmp_0
0x180007b52  test    eax, eax
0x180007b54  jnz     loc_180007C14
0x180007b5a  movups  xmm6, xmmword ptr cs:GUID_WICPixelFormat24bppRGB.Data1
0x180007b61  mov     [rbp+4Fh+var_70], r13
0x180007b65  lea     rcx, [rbp+4Fh+var_70]
0x180007b69  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007b6e  movdqa  [rbp+4Fh+var_80], xmm6
0x180007b73  lea     rax, [rbp+4Fh+var_70]
0x180007b77  mov     [rsp+0C0h+var_98], rax
0x180007b7c  mov     dword ptr [rsp+0C0h+ppv], 3
0x180007b84  lea     r9, [rbp+4Fh+var_80]
0x180007b88  lea     r8, [rbp+4Fh+ho]
0x180007b8c  mov     rdx, [rbp+4Fh+var_88]
0x180007b90  mov     rcx, [rbp+4Fh+var_90]
0x180007b94  call    ?GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U3@W4EncodingOptions@@PEAPEAUIStream@@@Z; GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)
0x180007b99  mov     ebx, eax
0x180007b9b  test    eax, eax
0x180007b9d  js      short loc_180007BCD
0x180007b9f  movups  xmm0, xmmword ptr [rsi]
0x180007ba2  movdqu  xmmword ptr [rdi+68h], xmm0
0x180007ba7  lea     rcx, [rdi+78h]
0x180007bab  mov     r9, [rbp+4Fh+var_70]
0x180007baf  call    ?Initialize@AgileGitPtr@@QEAAJW4AgileReferenceOptions@@AEBU_GUID@@PEAUIUnknown@@@Z; AgileGitPtr::Initialize(AgileReferenceOptions,_GUID const &,IUnknown *)
0x180007bb4  mov     ebx, eax
0x180007bb6  test    eax, eax
0x180007bb8  js      short loc_180007BCD
0x180007bba  mov     r9, r12; void **
0x180007bbd  mov     r8, r15; struct _GUID *
0x180007bc0  mov     rdx, rsi; struct _GUID *
0x180007bc3  mov     rcx, rdi; this
0x180007bc6  call    ?TryGetStream@CBitmapResult@Thumbnails@Internal@Windows@@AEAAJAEBU_GUID@@0PEAPEAX@Z; Windows::Internal::Thumbnails::CBitmapResult::TryGetStream(_GUID const &,_GUID const &,void * *)
0x180007bcb  mov     ebx, eax
0x180007bcd  mov     rcx, [rbp+4Fh+var_70]
0x180007bd1  test    rcx, rcx
0x180007bd4  jz      short loc_180007BE7
0x180007bd6  mov     [rbp+4Fh+var_70], r13
0x180007bda  mov     rax, [rcx]
0x180007bdd  mov     rax, [rax+10h]
0x180007be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007be6  nop
0x180007be7  mov     rcx, [rbp+4Fh+var_90]
0x180007beb  test    rcx, rcx
0x180007bee  jz      short loc_180007C01
0x180007bf0  mov     [rbp+4Fh+var_90], r13
0x180007bf4  mov     rax, [rcx]
0x180007bf7  mov     rax, [rax+10h]
0x180007bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c00  nop
0x180007c01  jmp     loc_180007A45
0x180007c06  movaps  xmm0, xmmword ptr [rbp+4Fh+ho]
0x180007c0a  movdqa  xmmword ptr [rbp+4Fh+ho], xmm0
0x180007c0f  jmp     loc_180007B3C
0x180007c14  movups  xmm6, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x180007c1b  jmp     loc_180007B61
0x180007c20  mov     rax, [r8]
0x180007c23  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180007c2a  jnz     short loc_180007C37
0x180007c2c  mov     rax, [r8+8]
0x180007c30  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180007c37  test    rax, rax
0x180007c3a  jnz     short loc_180007C8C
0x180007c3c  mov     [rbp+4Fh+var_70], r13
0x180007c40  lea     rcx, [rbp+4Fh+var_70]
0x180007c44  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007c49  lea     rcx, [rdi+58h]; this
0x180007c4d  lea     r8, [rbp+4Fh+var_70]; void **
0x180007c51  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x180007c56  mov     ebx, eax
0x180007c58  test    eax, eax
0x180007c5a  js      short loc_180007C6D
0x180007c5c  mov     r9, r12; void **
0x180007c5f  mov     r8, r15; struct _GUID *
0x180007c62  mov     rdx, [rbp+4Fh+var_70]; struct IStream *
0x180007c66  call    ?CloneStream@CBitmapResult@Thumbnails@Internal@Windows@@AEAAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::Thumbnails::CBitmapResult::CloneStream(IStream *,_GUID const &,void * *)
0x180007c6b  mov     ebx, eax
0x180007c6d  mov     rcx, [rbp+4Fh+var_70]
0x180007c71  test    rcx, rcx
0x180007c74  jz      short loc_180007C87
0x180007c76  mov     [rbp+4Fh+var_70], r13
0x180007c7a  mov     rax, [rcx]
0x180007c7d  mov     rax, [rax+10h]
0x180007c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c86  nop
0x180007c87  jmp     loc_180007A5F
0x180007c8c  mov     rax, [rcx+34h]
0x180007c90  sub     rax, [r8]
0x180007c93  jnz     short loc_180007C9D
0x180007c95  mov     rax, [rcx+3Ch]
0x180007c99  sub     rax, [r8+8]
0x180007c9d  test    rax, rax
0x180007ca0  jnz     loc_18000790F
0x180007ca6  jmp     short loc_180007C3C
```
