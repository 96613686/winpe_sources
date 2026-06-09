# CreateWicImageTile(ushort const *,uint,DirectUI::Element * *)

- ea: `0x1800df110`
- end: `0x1800df3f1`
- name: `?CreateWicImageTile@@YAJPEBGIPEAPEAVElement@DirectUI@@@Z`
- size: `737`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct DirectUI::Element **)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800de0ec`
- `0x1800de430`

## callees

- `0x180013f14`
- `0x180015fc0`
- `0x180024630`
- `0x180026c70`
- `0x180054130`
- `0x18007eb98`
- `0x180091d00`
- `0x1800d8338`
- `0x1800df110`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800df1f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800df1f4`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x1800df160`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x1800df160`
- `DUI70!?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800df198`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x1800df180`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x1800df180`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800df3bc`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800df3bc`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800df39b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800df39b`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800df1ad`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800df1ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CreateWicImageTile(const unsigned __int16 *a1, unsigned int a2, struct DirectUI::Element **a3)
{
  HRESULT Instance; // ebx
  struct DirectUI::Value *String; // rax
  DirectUI::Value *v8; // rsi
  bool v9; // cl
  unsigned int v10; // r9d
  struct IWICBitmapSource *v11; // rbx
  __int64 v12; // r8
  HBITMAP v14; // [rsp+30h] [rbp-D0h] BYREF
  struct IWICBitmapSource *v15; // [rsp+38h] [rbp-C8h] BYREF
  struct IWICImagingFactory *ppv; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+4Ch] [rbp-B4h] BYREF
  struct IWICBitmapSource *v19; // [rsp+50h] [rbp-B0h] BYREF
  struct DirectUI::Element *v20; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v21[264]; // [rsp+60h] [rbp-A0h] BYREF

  *a3 = 0;
  v20 = 0;
  Instance = DirectUI::Element::Create(0, 0, 0, &v20);
  if ( Instance >= 0 )
  {
    Instance = -2147024882;
    String = DirectUI::Value::CreateString(a1, 0);
    v8 = String;
    if ( !String )
      goto LABEL_22;
    Instance = DirectUI::Element::SetValue(
                 v20,
                 (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::CustomProp,
                 1,
                 String);
    if ( Instance < 0 )
    {
LABEL_20:
      DirectUI::Value::Release(v8);
      if ( Instance >= 0 )
      {
        *a3 = v20;
        return (unsigned int)Instance;
      }
LABEL_22:
      DirectUI::Element::Destroy(v20, 0);
      return (unsigned int)Instance;
    }
    ppv = 0;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
    Instance = CoCreateInstance(
                 &CLSID_WICImagingFactory2,
                 0,
                 1u,
                 &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
    {
LABEL_19:
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
      goto LABEL_20;
    }
    v15 = 0;
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v15);
    if ( (int)LoadImageWithWIC(ppv, a1, 0, &v15, 0) < 0
      && ((Instance = _GetDefaultUserPicturePathBySize(v9, a2, v21, v10), Instance < 0)
       || (Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v15),
           Instance = LoadImageWithWIC(ppv, v21, 0, &v15, 0),
           Instance < 0))
      || (v17 = 0,
          v18 = 0,
          Instance = ((__int64 (__fastcall *)(struct IWICBitmapSource *, int *, int *))v15->lpVtbl->GetSize)(
                       v15,
                       &v17,
                       &v18),
          Instance < 0) )
    {
LABEL_18:
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v15);
      goto LABEL_19;
    }
    v11 = 0;
    v19 = 0;
    if ( v17 == a2 && v18 == a2 )
    {
      if ( v15 )
      {
        v14 = (HBITMAP)v15;
        v11 = v15;
        Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(&v14);
        v14 = 0;
        v19 = v11;
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v14);
      }
    }
    else
    {
      LODWORD(v14) = a2;
      HIDWORD(v14) = a2;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v19);
      Instance = ScaleImageWithWIC(ppv, v15, (struct tagSIZE)v14, 1, &v19);
      if ( Instance < 0 )
      {
LABEL_17:
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v19);
        goto LABEL_18;
      }
      v11 = v19;
    }
    v14 = 0;
    Instance = ConvertWICBitmapToHBITMAP(ppv, v11, &v14);
    if ( Instance >= 0 )
    {
      LOBYTE(v12) = 1;
      Instance = DUI_SetElementBitmap(v20, v14, v12);
    }
    goto LABEL_17;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800df110  mov     [rsp-8+arg_18], rbx
0x1800df115  push    rbp
0x1800df116  push    rsi
0x1800df117  push    rdi
0x1800df118  push    r14
0x1800df11a  push    r15
0x1800df11c  lea     rbp, [rsp-180h]
0x1800df124  sub     rsp, 280h
0x1800df12b  mov     rax, cs:__security_cookie
0x1800df132  xor     rax, rsp
0x1800df135  mov     [rbp+1A0h+var_30], rax
0x1800df13c  mov     r15, r8
0x1800df13f  mov     qword ptr [r8], 0
0x1800df146  mov     edi, edx
0x1800df148  mov     [rsp+2A0h+var_248], 0
0x1800df151  mov     r14, rcx
0x1800df154  lea     r9, [rsp+2A0h+var_248]
0x1800df159  xor     r8d, r8d
0x1800df15c  xor     edx, edx
0x1800df15e  xor     ecx, ecx
0x1800df160  call    cs:__imp_?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z; DirectUI::Element::Create(uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800df167  nop     dword ptr [rax+rax+00h]
0x1800df16c  mov     ebx, eax
0x1800df16e  test    eax, eax
0x1800df170  js      loc_1800DF3C8
0x1800df176  xor     edx, edx
0x1800df178  mov     rcx, r14
0x1800df17b  mov     ebx, 8007000Eh
0x1800df180  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x1800df187  nop     dword ptr [rax+rax+00h]
0x1800df18c  mov     rsi, rax
0x1800df18f  test    rax, rax
0x1800df192  jz      loc_1800DF3B5
0x1800df198  mov     rdx, cs:__imp_?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::CustomProp(void)
0x1800df19f  mov     r9, rax
0x1800df1a2  mov     rcx, [rsp+2A0h+var_248]
0x1800df1a7  mov     r8d, 1
0x1800df1ad  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800df1b4  nop     dword ptr [rax+rax+00h]
0x1800df1b9  mov     ebx, eax
0x1800df1bb  test    eax, eax
0x1800df1bd  js      loc_1800DF398
0x1800df1c3  lea     rcx, [rsp+2A0h+var_260]
0x1800df1c8  mov     [rsp+2A0h+var_260], 0
0x1800df1d1  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800df1d6  xor     edx, edx; pUnkOuter
0x1800df1d8  lea     rax, [rsp+2A0h+var_260]
0x1800df1dd  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x1800df1e4  mov     [rsp+2A0h+ppv], rax; ppv
0x1800df1e9  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x1800df1f0  lea     r8d, [rdx+1]; dwClsContext
0x1800df1f4  call    cs:__imp_CoCreateInstance
0x1800df1fb  nop     dword ptr [rax+rax+00h]
0x1800df200  mov     ebx, eax
0x1800df202  test    eax, eax
0x1800df204  js      loc_1800DF38E
0x1800df20a  lea     rcx, [rsp+2A0h+var_268]
0x1800df20f  mov     [rsp+2A0h+var_268], 0
0x1800df218  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800df21d  mov     rcx, [rsp+2A0h+var_260]
0x1800df222  lea     r9, [rsp+2A0h+var_268]
0x1800df227  xor     r8d, r8d
0x1800df22a  mov     [rsp+2A0h+ppv], 0
0x1800df233  mov     rdx, r14
0x1800df236  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEBGW4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAU_GUID@@PEAPEAUIWICBitmapFrameDecode@@@Z; LoadImageWithWIC(IWICImagingFactory *,ushort const *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,_GUID *,IWICBitmapFrameDecode * *)
0x1800df23b  test    eax, eax
0x1800df23d  jns     short loc_1800DF289
0x1800df23f  lea     r8, [rsp+2A0h+var_240]; unsigned __int16 *
0x1800df244  mov     edx, edi; unsigned int
0x1800df246  call    ?_GetDefaultUserPicturePathBySize@@YAJ_NIPEAGK@Z; _GetDefaultUserPicturePathBySize(bool,uint,ushort *,ulong)
0x1800df24b  mov     ebx, eax
0x1800df24d  test    eax, eax
0x1800df24f  js      loc_1800DF384
0x1800df255  lea     rcx, [rsp+2A0h+var_268]
0x1800df25a  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800df25f  mov     rcx, [rsp+2A0h+var_260]
0x1800df264  lea     r9, [rsp+2A0h+var_268]
0x1800df269  xor     r8d, r8d
0x1800df26c  mov     [rsp+2A0h+ppv], 0
0x1800df275  lea     rdx, [rsp+2A0h+var_240]
0x1800df27a  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEBGW4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAU_GUID@@PEAPEAUIWICBitmapFrameDecode@@@Z; LoadImageWithWIC(IWICImagingFactory *,ushort const *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,_GUID *,IWICBitmapFrameDecode * *)
0x1800df27f  mov     ebx, eax
0x1800df281  test    eax, eax
0x1800df283  js      loc_1800DF384
0x1800df289  mov     rcx, [rsp+2A0h+var_268]
0x1800df28e  lea     r8, [rsp+2A0h+var_254]
0x1800df293  mov     [rsp+2A0h+var_258], 0
0x1800df29b  lea     rdx, [rsp+2A0h+var_258]
0x1800df2a0  mov     [rsp+2A0h+var_254], 0
0x1800df2a8  mov     rax, [rcx]
0x1800df2ab  mov     rax, [rax+18h]
0x1800df2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df2b4  mov     ebx, eax
0x1800df2b6  test    eax, eax
0x1800df2b8  js      loc_1800DF384
0x1800df2be  xor     ebx, ebx
0x1800df2c0  mov     [rsp+2A0h+var_250], rbx
0x1800df2c5  cmp     [rsp+2A0h+var_258], edi
0x1800df2c9  jnz     short loc_1800DF307
0x1800df2cb  cmp     [rsp+2A0h+var_254], edi
0x1800df2cf  jnz     short loc_1800DF307
0x1800df2d1  mov     rax, [rsp+2A0h+var_268]
0x1800df2d6  test    rax, rax
0x1800df2d9  jz      short loc_1800DF345
0x1800df2db  lea     rcx, [rsp+2A0h+var_270]
0x1800df2e0  mov     [rsp+2A0h+var_270], rax
0x1800df2e5  mov     rbx, rax
0x1800df2e8  call    ?InternalAddRef@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(void)
0x1800df2ed  lea     rcx, [rsp+2A0h+var_270]
0x1800df2f2  mov     [rsp+2A0h+var_270], 0
0x1800df2fb  mov     [rsp+2A0h+var_250], rbx
0x1800df300  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800df305  jmp     short loc_1800DF345
0x1800df307  lea     rcx, [rsp+2A0h+var_250]
0x1800df30c  mov     dword ptr [rsp+2A0h+var_270], edi
0x1800df310  mov     dword ptr [rsp+2A0h+var_270+4], edi
0x1800df314  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800df319  mov     r8, [rsp+2A0h+var_270]; struct tagSIZE
0x1800df31e  lea     rax, [rsp+2A0h+var_250]
0x1800df323  mov     rdx, [rsp+2A0h+var_268]; struct IWICBitmapSource *
0x1800df328  mov     r9b, 1; bool
0x1800df32b  mov     rcx, [rsp+2A0h+var_260]; struct IWICImagingFactory *
0x1800df330  mov     [rsp+2A0h+ppv], rax; struct IWICBitmapSource **
0x1800df335  call    ?ScaleImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@UtagSIZE@@_NPEAPEAU2@@Z; ScaleImageWithWIC(IWICImagingFactory *,IWICBitmapSource *,tagSIZE,bool,IWICBitmapSource * *)
0x1800df33a  mov     ebx, eax
0x1800df33c  test    eax, eax
0x1800df33e  js      short loc_1800DF37A
0x1800df340  mov     rbx, [rsp+2A0h+var_250]
0x1800df345  mov     rcx, [rsp+2A0h+var_260]; struct IWICImagingFactory *
0x1800df34a  lea     r8, [rsp+2A0h+var_270]; HBITMAP *
0x1800df34f  mov     rdx, rbx; struct IWICBitmapSource *
0x1800df352  mov     [rsp+2A0h+var_270], 0
0x1800df35b  call    ?ConvertWICBitmapToHBITMAP@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; ConvertWICBitmapToHBITMAP(IWICImagingFactory *,IWICBitmapSource *,HBITMAP__ * *)
0x1800df360  mov     ebx, eax
0x1800df362  test    eax, eax
0x1800df364  js      short loc_1800DF37A
0x1800df366  mov     rdx, [rsp+2A0h+var_270]
0x1800df36b  mov     r8b, 1
0x1800df36e  mov     rcx, [rsp+2A0h+var_248]
0x1800df373  call    ?DUI_SetElementBitmap@@YAJPEAVElement@DirectUI@@PEAUHBITMAP__@@EIW4ImageRtlMode@@_N@Z; DUI_SetElementBitmap(DirectUI::Element *,HBITMAP__ *,uchar,uint,ImageRtlMode,bool)
0x1800df378  mov     ebx, eax
0x1800df37a  lea     rcx, [rsp+2A0h+var_250]
0x1800df37f  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800df384  lea     rcx, [rsp+2A0h+var_268]
0x1800df389  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800df38e  lea     rcx, [rsp+2A0h+var_260]
0x1800df393  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800df398  mov     rcx, rsi
0x1800df39b  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800df3a2  nop     dword ptr [rax+rax+00h]
0x1800df3a7  test    ebx, ebx
0x1800df3a9  js      short loc_1800DF3B5
0x1800df3ab  mov     rax, [rsp+2A0h+var_248]
0x1800df3b0  mov     [r15], rax
0x1800df3b3  jmp     short loc_1800DF3C8
0x1800df3b5  mov     rcx, [rsp+2A0h+var_248]
0x1800df3ba  xor     edx, edx
0x1800df3bc  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800df3c3  nop     dword ptr [rax+rax+00h]
0x1800df3c8  mov     eax, ebx
0x1800df3ca  mov     rcx, [rbp+1A0h+var_30]
0x1800df3d1  xor     rcx, rsp; StackCookie
0x1800df3d4  call    __security_check_cookie
0x1800df3d9  mov     rbx, [rsp+2A0h+arg_18]
0x1800df3e1  add     rsp, 280h
0x1800df3e8  pop     r15
0x1800df3ea  pop     r14
0x1800df3ec  pop     rdi
0x1800df3ed  pop     rsi
0x1800df3ee  pop     rbp
0x1800df3ef  retn
```
