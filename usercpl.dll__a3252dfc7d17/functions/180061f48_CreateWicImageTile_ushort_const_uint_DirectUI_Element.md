# CreateWicImageTile(ushort const *,uint,DirectUI::Element * *)

- ea: `0x180061f48`
- end: `0x180062201`
- name: `?CreateWicImageTile@@YAJPEBGIPEAPEAVElement@DirectUI@@@Z`
- size: `697`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct DirectUI::Element **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006088c`
- `0x180060bc4`

## callees

- `0x180024cf4`
- `0x180058324`
- `0x180061e50`
- `0x180061f48`
- `0x180062208`
- `0x180062360`
- `0x1800705e8`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180062015`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180062015`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180061fd9`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180061fd9`
- `DUI70!?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180061fc4`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x180061f98`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x180061f98`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800621d3`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800621d3`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x180061fb2`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x180061fb2`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800621b8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800621b8`

## pseudocode

```c
__int64 __fastcall CreateWicImageTile(const unsigned __int16 *a1, unsigned int a2, struct DirectUI::Element **a3)
{
  HRESULT Instance; // ebx
  struct DirectUI::Value *String; // rax
  DirectUI::Value *v8; // r14
  __int64 *ppv; // rax
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // r8
  struct IWICBitmapSource *v13; // rcx
  bool v14; // r9
  struct IWICBitmapSource *v15; // rdi
  int v16; // eax
  __int64 v17; // r8
  struct IWICBitmapSource *v18; // rcx
  struct IWICImagingFactory *v19; // rcx
  struct IWICBitmapSource *v21; // [rsp+30h] [rbp-D0h] BYREF
  struct IWICImagingFactory *v22; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+44h] [rbp-BCh] BYREF
  struct DirectUI::Element *v25; // [rsp+48h] [rbp-B8h] BYREF
  HBITMAP v26; // [rsp+50h] [rbp-B0h] BYREF
  struct IWICBitmapSource *v27; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v28[528]; // [rsp+60h] [rbp-A0h] BYREF

  *a3 = 0;
  v25 = 0;
  Instance = DirectUI::Element::Create(0, 0, 0, &v25);
  if ( Instance >= 0 )
  {
    Instance = -2147024882;
    String = DirectUI::Value::CreateString(a1, 0);
    v8 = String;
    if ( !String )
      goto LABEL_26;
    Instance = DirectUI::Element::SetValue(
                 v25,
                 (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::CustomProp,
                 1,
                 String);
    if ( Instance < 0 )
    {
LABEL_24:
      DirectUI::Value::Release(v8);
      if ( Instance >= 0 )
      {
        *a3 = v25;
        return (unsigned int)Instance;
      }
LABEL_26:
      DirectUI::Element::Destroy(v25, 0);
      return (unsigned int)Instance;
    }
    v22 = 0;
    ppv = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWICImagingFactory>>((__int64 *)&v22);
    Instance = CoCreateInstance(
                 &CLSID_WICImagingFactory2,
                 0,
                 1u,
                 &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                 (LPVOID *)ppv);
    if ( Instance < 0 )
    {
LABEL_22:
      v19 = v22;
      if ( v22 )
      {
        v22 = 0;
        ((void (__fastcall *)(struct IWICImagingFactory *))v19->lpVtbl->Release)(v19);
      }
      goto LABEL_24;
    }
    v21 = 0;
    if ( (int)LoadImageWithWIC(v22, a1, v10, &v21) < 0 )
    {
      Instance = SHGetDefaultUserPicturePathBySize(v11, a2, v28);
      if ( Instance < 0 )
        goto LABEL_20;
      v13 = v21;
      if ( v21 )
      {
        v21 = 0;
        ((void (__fastcall *)(struct IWICBitmapSource *))v13->lpVtbl->Release)(v13);
      }
      Instance = LoadImageWithWIC(v22, v28, v12, &v21);
      if ( Instance < 0 )
        goto LABEL_20;
    }
    v23 = 0;
    v24 = 0;
    Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, int *, int *))v21->lpVtbl->GetSize)(v21, &v23, &v24);
    if ( Instance < 0 )
    {
LABEL_20:
      v18 = v21;
      if ( v21 )
      {
        v21 = 0;
        ((void (__fastcall *)(struct IWICBitmapSource *))v18->lpVtbl->Release)(v18);
      }
      goto LABEL_22;
    }
    v15 = 0;
    v27 = 0;
    if ( v23 == a2 && v24 == a2 )
    {
      if ( v21 )
      {
        v15 = v21;
        ((void (__fastcall *)(struct IWICBitmapSource *))v21->lpVtbl->AddRef)(v21);
      }
    }
    else
    {
      LODWORD(v26) = a2;
      HIDWORD(v26) = a2;
      v16 = ScaleImageWithWIC(v22, v21, (struct tagSIZE)v26, v14, &v27);
      v15 = v27;
      Instance = v16;
      if ( v16 < 0 )
      {
LABEL_18:
        if ( v15 )
          ((void (__fastcall *)(struct IWICBitmapSource *))v15->lpVtbl->Release)(v15);
        goto LABEL_20;
      }
    }
    v26 = 0;
    Instance = ConvertWICBitmapToHBITMAP(v22, v15, &v26);
    if ( Instance >= 0 )
    {
      LOBYTE(v17) = 1;
      Instance = DUI_SetElementBitmap(v25, v26, v17);
    }
    goto LABEL_18;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180061f48  mov     [rsp-8+arg_18], rbx
0x180061f4d  push    rbp
0x180061f4e  push    rsi
0x180061f4f  push    rdi
0x180061f50  push    r14
0x180061f52  push    r15
0x180061f54  lea     rbp, [rsp-180h]
0x180061f5c  sub     rsp, 280h
0x180061f63  mov     rax, cs:__security_cookie
0x180061f6a  xor     rax, rsp
0x180061f6d  mov     [rbp+1A0h+var_30], rax
0x180061f74  mov     r15, r8
0x180061f77  mov     qword ptr [r8], 0
0x180061f7e  mov     esi, edx
0x180061f80  mov     [rsp+2A0h+var_258], 0
0x180061f89  mov     rdi, rcx
0x180061f8c  lea     r9, [rsp+2A0h+var_258]
0x180061f91  xor     r8d, r8d
0x180061f94  xor     edx, edx
0x180061f96  xor     ecx, ecx
0x180061f98  call    cs:__imp_?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z; DirectUI::Element::Create(uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180061f9e  mov     ebx, eax
0x180061fa0  test    eax, eax
0x180061fa2  js      loc_1800621D9
0x180061fa8  xor     edx, edx
0x180061faa  mov     rcx, rdi
0x180061fad  mov     ebx, 8007000Eh
0x180061fb2  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x180061fb8  mov     r14, rax
0x180061fbb  test    rax, rax
0x180061fbe  jz      loc_1800621CC
0x180061fc4  mov     rdx, cs:__imp_?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::CustomProp(void)
0x180061fcb  mov     r9, rax
0x180061fce  mov     rcx, [rsp+2A0h+var_258]
0x180061fd3  mov     r8d, 1
0x180061fd9  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180061fdf  mov     ebx, eax
0x180061fe1  test    eax, eax
0x180061fe3  js      loc_1800621B5
0x180061fe9  lea     rcx, [rsp+2A0h+var_268]
0x180061fee  mov     [rsp+2A0h+var_268], 0
0x180061ff7  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIWICImagingFactory@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIWICImagingFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IWICImagingFactory>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWICImagingFactory>>)
0x180061ffc  xor     edx, edx; pUnkOuter
0x180061ffe  mov     [rsp+2A0h+ppv], rax; ppv
0x180062003  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18006200a  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180062011  lea     r8d, [rdx+1]; dwClsContext
0x180062015  call    cs:__imp_CoCreateInstance
0x18006201b  mov     ebx, eax
0x18006201d  test    eax, eax
0x18006201f  js      loc_180062196
0x180062025  mov     rcx, [rsp+2A0h+var_268]
0x18006202a  lea     r9, [rsp+2A0h+var_270]
0x18006202f  mov     rdx, rdi
0x180062032  mov     [rsp+2A0h+var_270], 0
0x18006203b  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEBGW4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAU_GUID@@PEAPEAUIWICBitmapFrameDecode@@@Z; LoadImageWithWIC(IWICImagingFactory *,ushort const *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,_GUID *,IWICBitmapFrameDecode * *)
0x180062040  test    eax, eax
0x180062042  jns     short loc_180062097
0x180062044  lea     r8, [rsp+2A0h+var_240]
0x180062049  mov     edx, esi
0x18006204b  call    SHGetDefaultUserPicturePathBySize
0x180062050  mov     ebx, eax
0x180062052  test    eax, eax
0x180062054  js      loc_180062177
0x18006205a  mov     rcx, [rsp+2A0h+var_270]
0x18006205f  test    rcx, rcx
0x180062062  jz      short loc_180062079
0x180062064  mov     [rsp+2A0h+var_270], 0
0x18006206d  mov     rax, [rcx]
0x180062070  mov     rax, [rax+10h]
0x180062074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062079  mov     rcx, [rsp+2A0h+var_268]
0x18006207e  lea     r9, [rsp+2A0h+var_270]
0x180062083  lea     rdx, [rsp+2A0h+var_240]
0x180062088  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEBGW4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAU_GUID@@PEAPEAUIWICBitmapFrameDecode@@@Z; LoadImageWithWIC(IWICImagingFactory *,ushort const *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,_GUID *,IWICBitmapFrameDecode * *)
0x18006208d  mov     ebx, eax
0x18006208f  test    eax, eax
0x180062091  js      loc_180062177
0x180062097  mov     rcx, [rsp+2A0h+var_270]
0x18006209c  lea     r8, [rsp+2A0h+var_25C]
0x1800620a1  mov     [rsp+2A0h+var_260], 0
0x1800620a9  lea     rdx, [rsp+2A0h+var_260]
0x1800620ae  mov     [rsp+2A0h+var_25C], 0
0x1800620b6  mov     rax, [rcx]
0x1800620b9  mov     rax, [rax+18h]
0x1800620bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620c2  mov     ebx, eax
0x1800620c4  test    eax, eax
0x1800620c6  js      loc_180062177
0x1800620cc  xor     edi, edi
0x1800620ce  mov     [rsp+2A0h+var_248], rdi
0x1800620d3  cmp     [rsp+2A0h+var_260], esi
0x1800620d7  jnz     short loc_1800620FD
0x1800620d9  cmp     [rsp+2A0h+var_25C], esi
0x1800620dd  jnz     short loc_1800620FD
0x1800620df  mov     rax, [rsp+2A0h+var_270]
0x1800620e4  test    rax, rax
0x1800620e7  jz      short loc_18006212E
0x1800620e9  mov     rdi, rax
0x1800620ec  mov     rax, [rax]
0x1800620ef  mov     rcx, rdi
0x1800620f2  mov     rax, [rax+8]
0x1800620f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620fb  jmp     short loc_18006212E
0x1800620fd  mov     rdx, [rsp+2A0h+var_270]; struct IWICBitmapSource *
0x180062102  lea     rax, [rsp+2A0h+var_248]
0x180062107  mov     rcx, [rsp+2A0h+var_268]; struct IWICImagingFactory *
0x18006210c  mov     dword ptr [rsp+2A0h+var_250], esi
0x180062110  mov     dword ptr [rsp+2A0h+var_250+4], esi
0x180062114  mov     r8, [rsp+2A0h+var_250]; struct tagSIZE
0x180062119  mov     [rsp+2A0h+ppv], rax; struct IWICBitmapSource **
0x18006211e  call    ?ScaleImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@UtagSIZE@@_NPEAPEAU2@@Z; ScaleImageWithWIC(IWICImagingFactory *,IWICBitmapSource *,tagSIZE,bool,IWICBitmapSource * *)
0x180062123  mov     rdi, [rsp+2A0h+var_248]
0x180062128  mov     ebx, eax
0x18006212a  test    eax, eax
0x18006212c  js      short loc_180062163
0x18006212e  mov     rcx, [rsp+2A0h+var_268]; struct IWICImagingFactory *
0x180062133  lea     r8, [rsp+2A0h+var_250]; HBITMAP *
0x180062138  mov     rdx, rdi; struct IWICBitmapSource *
0x18006213b  mov     [rsp+2A0h+var_250], 0
0x180062144  call    ?ConvertWICBitmapToHBITMAP@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; ConvertWICBitmapToHBITMAP(IWICImagingFactory *,IWICBitmapSource *,HBITMAP__ * *)
0x180062149  mov     ebx, eax
0x18006214b  test    eax, eax
0x18006214d  js      short loc_180062163
0x18006214f  mov     rdx, [rsp+2A0h+var_250]
0x180062154  mov     r8b, 1
0x180062157  mov     rcx, [rsp+2A0h+var_258]
0x18006215c  call    ?DUI_SetElementBitmap@@YAJPEAVElement@DirectUI@@PEAUHBITMAP__@@EIW4ImageRtlMode@@_N@Z; DUI_SetElementBitmap(DirectUI::Element *,HBITMAP__ *,uchar,uint,ImageRtlMode,bool)
0x180062161  mov     ebx, eax
0x180062163  test    rdi, rdi
0x180062166  jz      short loc_180062177
0x180062168  mov     rax, [rdi]
0x18006216b  mov     rcx, rdi
0x18006216e  mov     rax, [rax+10h]
0x180062172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062177  mov     rcx, [rsp+2A0h+var_270]
0x18006217c  test    rcx, rcx
0x18006217f  jz      short loc_180062196
0x180062181  mov     [rsp+2A0h+var_270], 0
0x18006218a  mov     rax, [rcx]
0x18006218d  mov     rax, [rax+10h]
0x180062191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062196  mov     rcx, [rsp+2A0h+var_268]
0x18006219b  test    rcx, rcx
0x18006219e  jz      short loc_1800621B5
0x1800621a0  mov     [rsp+2A0h+var_268], 0
0x1800621a9  mov     rax, [rcx]
0x1800621ac  mov     rax, [rax+10h]
0x1800621b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800621b5  mov     rcx, r14
0x1800621b8  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800621be  test    ebx, ebx
0x1800621c0  js      short loc_1800621CC
0x1800621c2  mov     rax, [rsp+2A0h+var_258]
0x1800621c7  mov     [r15], rax
0x1800621ca  jmp     short loc_1800621D9
0x1800621cc  mov     rcx, [rsp+2A0h+var_258]
0x1800621d1  xor     edx, edx
0x1800621d3  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800621d9  mov     eax, ebx
0x1800621db  mov     rcx, [rbp+1A0h+var_30]
0x1800621e2  xor     rcx, rsp; StackCookie
0x1800621e5  call    __security_check_cookie
0x1800621ea  mov     rbx, [rsp+2A0h+arg_18]
0x1800621f2  add     rsp, 280h
0x1800621f9  pop     r15
0x1800621fb  pop     r14
0x1800621fd  pop     rdi
0x1800621fe  pop     rsi
0x1800621ff  pop     rbp
0x180062200  retn
```
