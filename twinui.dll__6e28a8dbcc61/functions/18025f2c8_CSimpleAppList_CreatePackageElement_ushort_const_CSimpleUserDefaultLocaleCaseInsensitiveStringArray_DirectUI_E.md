# CSimpleAppList::_CreatePackageElement(ushort const *,CSimpleUserDefaultLocaleCaseInsensitiveStringArray *,DirectUI::Element * *)

- ea: `0x18025f2c8`
- end: `0x18025f594`
- name: `?_CreatePackageElement@CSimpleAppList@@AEAAJPEBGPEAVCSimpleUserDefaultLocaleCaseInsensitiveStringArray@@PEAPEAVElement@DirectUI@@@Z`
- size: `716`
- prototype: `__int64 __fastcall(CSimpleAppList *__hidden this, const unsigned __int16 *, struct CSimpleUserDefaultLocaleCaseInsensitiveStringArray *, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18025ee58`

## callees

- `0x180008acc`
- `0x1800a57c8`
- `0x1801078a8`
- `0x18013f43c`
- `0x18013f4a4`
- `0x18025c2c0`
- `0x18025e874`
- `0x18025f2c8`
- `0x1803596d8`
- `0x18035a278`
- `0x18035a2d0`
- `0x1803a3010`

## import_xrefs

- `GDI32!DeleteObject` at `0x18025f496`
- `GDI32!DeleteObject` at `0x18025f496`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18025f3e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18025f3e5`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18025f51e`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18025f326`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18025f508`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18025f326`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18025f508`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18025f540`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18025f540`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18025f33d`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18025f33d`
- `SHCORE!__imp_SHCreateStreamOnModuleResourceW` at `0x18025f427`
- `SHCORE!__imp_SHCreateStreamOnModuleResourceW` at `0x18025f427`

## pseudocode

```c
__int64 __fastcall CSimpleAppList::_CreatePackageElement(
        CSimpleAppList *this,
        const unsigned __int16 *a2,
        struct CSimpleUserDefaultLocaleCaseInsensitiveStringArray *a3,
        struct DirectUI::Element **a4)
{
  DirectUI::DUIXmlParser *ParserForThread; // rax
  HRESULT Instance; // ebx
  __int64 v9; // rdi
  struct IWICImagingFactory *v10; // rsi
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdi
  DirectUI::DUIXmlParser *v14; // rax
  struct IWICImagingFactory *ppv; // [rsp+30h] [rbp-10h] BYREF
  struct IWICBitmapSource *v17; // [rsp+38h] [rbp-8h] BYREF
  struct DirectUI::Element *v18; // [rsp+70h] [rbp+30h] BYREF
  HGDIOBJ ho; // [rsp+88h] [rbp+48h] BYREF

  *a4 = 0;
  v18 = 0;
  ParserForThread = CDUIResourceManager::GetParserForThread((CDUIResourceManager *)g_resmgrLockScreenFlyoutDUI);
  Instance = DirectUI::DUIXmlParser::CreateElement(ParserForThread, L"LockScreenPackage", 0, 0, 0, &v18);
  if ( Instance >= 0 )
  {
    Instance = DirectUI::Element::SetAccName(v18, a2);
    if ( Instance >= 0 )
    {
      if ( dword_1804B71A8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                       + 4LL) )
      {
        Init_thread_header(&dword_1804B71A8);
        if ( dword_1804B71A8 == -1 )
        {
          dword_1804B71AC = CLauncherSettings::GetScaleFactorForPart();
          Init_thread_footer(&dword_1804B71A8);
        }
      }
      v9 = 10410;
      if ( dword_1804B71AC == 140 )
      {
        v9 = 10411;
      }
      else if ( dword_1804B71AC == 180 )
      {
        v9 = 10412;
      }
      ppv = 0;
      Instance = CoCreateInstance(
                   &CLSID_WICImagingFactory2,
                   0,
                   1u,
                   &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                   (LPVOID *)&ppv);
      if ( Instance >= 0 )
      {
        v10 = ppv;
        v17 = 0;
        ho = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ho);
        Instance = SHCreateStreamOnModuleResourceW(&_ImageBase, v9, L"Image", &ho);
        if ( Instance >= 0 )
          Instance = LoadImageWithWIC(v10, ho, v11, &v17);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ho);
        if ( Instance >= 0 )
        {
          ho = 0;
          Instance = ConvertWICBitmapToHBITMAP(ppv, v17, (HBITMAP *)&ho);
          if ( Instance >= 0 )
          {
            LOBYTE(v12) = 2;
            Instance = DUI_SetDescendentElementBitmap(v18, L"LockScreenPackageImage", ho, v12, -1);
            DeleteObject(ho);
          }
          ((void (__fastcall *)(struct IWICBitmapSource *))v17->lpVtbl->Release)(v17);
        }
        ((void (__fastcall *)(struct IWICImagingFactory *))ppv->lpVtbl->Release)(ppv);
        if ( Instance >= 0 )
        {
          v13 = 0;
          while ( (unsigned __int64)(unsigned int)v13 < *((_QWORD *)a3 + 1) )
          {
            ho = 0;
            v14 = CDUIResourceManager::GetParserForThread((CDUIResourceManager *)g_resmgrLockScreenFlyoutDUI);
            Instance = DirectUI::DUIXmlParser::CreateElement(
                         v14,
                         L"LockScreenPackageApp",
                         0,
                         0,
                         0,
                         (struct DirectUI::Element **)&ho);
            if ( Instance >= 0 )
            {
              Instance = DUI_SetElementStringProperty(
                           (struct DirectUI::Element *)ho,
                           DirectUI::Element::ContentProp,
                           *(const unsigned __int16 **)(*(_QWORD *)a3 + 8 * v13),
                           (HINSTANCE)&_ImageBase);
              if ( Instance >= 0 )
              {
                Instance = DirectUI::Element::Add(v18, (struct DirectUI::Element *)ho);
                if ( Instance >= 0 )
                  ho = 0;
              }
              DUI_SafeDestroyElement((struct DirectUI::Element **)&ho);
            }
            v13 = (unsigned int)(v13 + 1);
            if ( Instance < 0 )
              goto LABEL_28;
          }
          *a4 = v18;
          v18 = 0;
        }
      }
    }
LABEL_28:
    DUI_SafeDestroyElement(&v18);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18025f2c8  mov     [rsp-28h+arg_8], rbx
0x18025f2cd  mov     [rsp-28h+arg_0], rcx
0x18025f2d2  push    rbp
0x18025f2d3  push    rsi
0x18025f2d4  push    rdi
0x18025f2d5  push    r14
0x18025f2d7  push    r15
0x18025f2d9  mov     rbp, rsp
0x18025f2dc  sub     rsp, 40h
0x18025f2e0  lea     rcx, ?g_resmgrLockScreenFlyoutDUI@@3VCDUIResourceManager@@A; this
0x18025f2e7  mov     qword ptr [r9], 0
0x18025f2ee  mov     r14, r9
0x18025f2f1  mov     [rbp+arg_0], 0
0x18025f2f9  mov     r15, r8
0x18025f2fc  mov     rdi, rdx
0x18025f2ff  call    ?GetParserForThread@CDUIResourceManager@@QEBAPEAVDUIXmlParser@DirectUI@@XZ; CDUIResourceManager::GetParserForThread(void)
0x18025f304  lea     rcx, [rbp+arg_0]
0x18025f308  xor     r9d, r9d
0x18025f30b  mov     [rsp+40h+var_18], rcx
0x18025f310  lea     rdx, aLockscreenpack_0; "LockScreenPackage"
0x18025f317  mov     rcx, rax
0x18025f31a  mov     [rsp+40h+ppv], 0
0x18025f323  xor     r8d, r8d
0x18025f326  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18025f32c  mov     ebx, eax
0x18025f32e  test    eax, eax
0x18025f330  js      loc_18025F581
0x18025f336  mov     rcx, [rbp+arg_0]
0x18025f33a  mov     rdx, rdi
0x18025f33d  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18025f343  mov     ebx, eax
0x18025f345  test    eax, eax
0x18025f347  js      loc_18025F578
0x18025f34d  mov     ecx, cs:_tls_index
0x18025f353  mov     rax, gs:58h
0x18025f35c  mov     edx, 4
0x18025f361  mov     rax, [rax+rcx*8]
0x18025f365  mov     eax, [rdx+rax]
0x18025f368  cmp     cs:dword_1804B71A8, eax
0x18025f36e  jle     short loc_18025F39C
0x18025f370  lea     rcx, dword_1804B71A8
0x18025f377  call    _Init_thread_header
0x18025f37c  cmp     cs:dword_1804B71A8, 0FFFFFFFFh
0x18025f383  jnz     short loc_18025F39C
0x18025f385  call    ?GetScaleFactorForPart@CLauncherSettings@@QEAA?AW4DEVICE_SCALE_FACTOR@@W4ScalablePart@@@Z; CLauncherSettings::GetScaleFactorForPart(ScalablePart)
0x18025f38a  lea     rcx, dword_1804B71A8
0x18025f391  mov     cs:dword_1804B71AC, eax
0x18025f397  call    _Init_thread_footer
0x18025f39c  mov     ecx, cs:dword_1804B71AC
0x18025f3a2  mov     edi, 28AAh
0x18025f3a7  sub     ecx, 8Ch
0x18025f3ad  jz      short loc_18025F3BB
0x18025f3af  cmp     ecx, 28h ; '('
0x18025f3b2  jnz     short loc_18025F3C0
0x18025f3b4  mov     edi, 28ACh
0x18025f3b9  jmp     short loc_18025F3C0
0x18025f3bb  mov     edi, 28ABh
0x18025f3c0  xor     edx, edx; pUnkOuter
0x18025f3c2  mov     [rbp+var_10], 0
0x18025f3ca  lea     rax, [rbp+var_10]
0x18025f3ce  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18025f3d5  mov     [rsp+40h+ppv], rax; ppv
0x18025f3da  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18025f3e1  lea     r8d, [rdx+1]; dwClsContext
0x18025f3e5  call    cs:__imp_CoCreateInstance
0x18025f3eb  mov     ebx, eax
0x18025f3ed  test    eax, eax
0x18025f3ef  js      loc_18025F578
0x18025f3f5  mov     rsi, [rbp+var_10]
0x18025f3f9  lea     rcx, [rbp+ho]
0x18025f3fd  mov     [rbp+var_8], 0
0x18025f405  mov     [rbp+ho], 0
0x18025f40d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025f412  lea     r9, [rbp+ho]
0x18025f416  mov     rdx, rdi
0x18025f419  lea     r8, aImage_0; "Image"
0x18025f420  lea     rcx, __ImageBase
0x18025f427  call    cs:__imp_SHCreateStreamOnModuleResourceW
0x18025f42d  mov     ebx, eax
0x18025f42f  test    eax, eax
0x18025f431  js      short loc_18025F445
0x18025f433  mov     rdx, [rbp+ho]
0x18025f437  lea     r9, [rbp+var_8]
0x18025f43b  mov     rcx, rsi
0x18025f43e  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIStream@@W4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAPEAUIWICBitmapFrameDecode@@PEAU_GUID@@@Z; LoadImageWithWIC(IWICImagingFactory *,IStream *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,IWICBitmapFrameDecode * *,_GUID *)
0x18025f443  mov     ebx, eax
0x18025f445  lea     rcx, [rbp+ho]
0x18025f449  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18025f44e  test    ebx, ebx
0x18025f450  js      short loc_18025F4AC
0x18025f452  mov     rdx, [rbp+var_8]; struct IWICBitmapSource *
0x18025f456  lea     r8, [rbp+ho]; HBITMAP *
0x18025f45a  mov     rcx, [rbp+var_10]; struct IWICImagingFactory *
0x18025f45e  mov     [rbp+ho], 0
0x18025f466  call    ?ConvertWICBitmapToHBITMAP@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; ConvertWICBitmapToHBITMAP(IWICImagingFactory *,IWICBitmapSource *,HBITMAP__ * *)
0x18025f46b  mov     ebx, eax
0x18025f46d  test    eax, eax
0x18025f46f  js      short loc_18025F49C
0x18025f471  mov     r8, [rbp+ho]
0x18025f475  lea     rdx, aLockscreenpack; "LockScreenPackageImage"
0x18025f47c  mov     rcx, [rbp+arg_0]
0x18025f480  mov     r9b, 2
0x18025f483  mov     dword ptr [rsp+40h+ppv], 0FFFFFFFFh
0x18025f48b  call    ?DUI_SetDescendentElementBitmap@@YAJPEAVElement@DirectUI@@PEBGPEAUHBITMAP__@@EIW4ImageRtlMode@@@Z; DUI_SetDescendentElementBitmap(DirectUI::Element *,ushort const *,HBITMAP__ *,uchar,uint,ImageRtlMode)
0x18025f490  mov     rcx, [rbp+ho]; ho
0x18025f494  mov     ebx, eax
0x18025f496  call    cs:__imp_DeleteObject
0x18025f49c  mov     rcx, [rbp+var_8]
0x18025f4a0  mov     rax, [rcx]
0x18025f4a3  mov     rax, [rax+10h]
0x18025f4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025f4ac  mov     rcx, [rbp+var_10]
0x18025f4b0  mov     rax, [rcx]
0x18025f4b3  mov     rax, [rax+10h]
0x18025f4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025f4bc  test    ebx, ebx
0x18025f4be  js      loc_18025F578
0x18025f4c4  xor     edi, edi
0x18025f4c6  mov     esi, edi
0x18025f4c8  cmp     rsi, [r15+8]
0x18025f4cc  jnb     loc_18025F569
0x18025f4d2  lea     rcx, ?g_resmgrLockScreenFlyoutDUI@@3VCDUIResourceManager@@A; this
0x18025f4d9  mov     [rbp+ho], 0
0x18025f4e1  call    ?GetParserForThread@CDUIResourceManager@@QEBAPEAVDUIXmlParser@DirectUI@@XZ; CDUIResourceManager::GetParserForThread(void)
0x18025f4e6  lea     rcx, [rbp+ho]
0x18025f4ea  xor     r9d, r9d
0x18025f4ed  mov     [rsp+40h+var_18], rcx
0x18025f4f2  lea     rdx, aLockscreenpack_1; "LockScreenPackageApp"
0x18025f4f9  mov     rcx, rax
0x18025f4fc  mov     [rsp+40h+ppv], 0
0x18025f505  xor     r8d, r8d
0x18025f508  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18025f50e  mov     ebx, eax
0x18025f510  test    eax, eax
0x18025f512  js      short loc_18025F55D
0x18025f514  mov     r8, [r15]
0x18025f517  lea     r9, __ImageBase; HINSTANCE
0x18025f51e  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; const struct DirectUI::PropertyInfo *(*)(void)
0x18025f525  mov     rcx, [rbp+ho]; struct DirectUI::Element *
0x18025f529  mov     r8, [r8+rdi*8]; unsigned __int16 *
0x18025f52d  call    ?DUI_SetElementStringProperty@@YAJPEAVElement@DirectUI@@P6APEBUPropertyInfo@2@XZPEBGPEAUHINSTANCE__@@@Z; DUI_SetElementStringProperty(DirectUI::Element *,DirectUI::PropertyInfo const * (*)(void),ushort const *,HINSTANCE__ *)
0x18025f532  mov     ebx, eax
0x18025f534  test    eax, eax
0x18025f536  js      short loc_18025F554
0x18025f538  mov     rdx, [rbp+ho]
0x18025f53c  mov     rcx, [rbp+arg_0]
0x18025f540  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18025f546  mov     ebx, eax
0x18025f548  test    eax, eax
0x18025f54a  js      short loc_18025F554
0x18025f54c  mov     [rbp+ho], 0
0x18025f554  lea     rcx, [rbp+ho]; struct DirectUI::Element **
0x18025f558  call    ?DUI_SafeDestroyElement@@YAXPEAPEAVElement@DirectUI@@@Z; DUI_SafeDestroyElement(DirectUI::Element * *)
0x18025f55d  inc     edi
0x18025f55f  test    ebx, ebx
0x18025f561  jns     loc_18025F4C6
0x18025f567  jmp     short loc_18025F578
0x18025f569  mov     rax, [rbp+arg_0]
0x18025f56d  mov     [r14], rax
0x18025f570  mov     [rbp+arg_0], 0
0x18025f578  lea     rcx, [rbp+arg_0]; struct DirectUI::Element **
0x18025f57c  call    ?DUI_SafeDestroyElement@@YAXPEAPEAVElement@DirectUI@@@Z; DUI_SafeDestroyElement(DirectUI::Element * *)
0x18025f581  mov     eax, ebx
0x18025f583  mov     rbx, [rsp+40h+arg_8]
0x18025f588  add     rsp, 40h
0x18025f58c  pop     r15
0x18025f58e  pop     r14
0x18025f590  pop     rdi
0x18025f591  pop     rsi
0x18025f592  pop     rbp
0x18025f593  retn
```
