# CDataFormat::s_CopyBitmapToMedium(Windows::Storage::Streams::IRandomAccessStream *,tagSTGMEDIUM *)

- ea: `0x18005d9f8`
- end: `0x18005db81`
- name: `?s_CopyBitmapToMedium@CDataFormat@@KAJPEAUIRandomAccessStream@Streams@Storage@Windows@@PEAUtagSTGMEDIUM@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(struct Windows::Storage::Streams::IRandomAccessStream *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180053520`

## callees

- `0x180008b68`
- `0x180022d34`
- `0x180022e30`
- `0x18003a624`
- `0x18005d9f8`
- `0x180081010`

## import_xrefs

- `SHCORE!CreateStreamOverRandomAccessStream` at `0x18005da74`
- `SHCORE!CreateStreamOverRandomAccessStream` at `0x18005da74`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005db4d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18005db4d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005db3b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005db3b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005da46`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005da46`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x18005db1b`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x18005db1b`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x18005daaf`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x18005daaf`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18005daa1`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18005daa1`

## pseudocode

```c
__int64 __fastcall CDataFormat::s_CopyBitmapToMedium(
        struct Windows::Storage::Streams::IRandomAccessStream *a1,
        struct tagSTGMEDIUM *a2)
{
  HRESULT Instance; // ebx
  LPVOID *ppv; // rax
  __int64 v6; // rax
  __int64 v7; // r8
  HDC DC; // rbx
  enum WICBitmapDitherType v9; // r9d
  union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *p_hBitmap; // r8
  HRESULT v11; // eax
  struct IWICBitmapSource *v12; // rcx
  __int64 v13; // rcx
  unsigned int StringW; // eax
  struct IWICImagingFactory *v15; // rcx
  struct IWICImagingFactory *v17; // [rsp+58h] [rbp+28h] BYREF
  struct IWICBitmapSource *Buffer; // [rsp+60h] [rbp+30h] BYREF
  __int64 v19; // [rsp+68h] [rbp+38h] BYREF

  if ( a2->tymed == 16 )
  {
    v17 = 0;
    ppv = (LPVOID *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v17);
    Instance = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, ppv);
    if ( Instance < 0 )
      goto LABEL_15;
    v19 = 0;
    v6 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v19);
    Instance = CreateStreamOverRandomAccessStream(a1, &GUID_0000000c_0000_0000_c000_000000000046, v6);
    if ( Instance >= 0 )
    {
      Buffer = 0;
      Instance = LoadImageWithWIC(v17, v19, v7, &Buffer);
      if ( Instance >= 0 )
      {
        DC = GetDC(0);
        ReleaseDC(0, DC);
        p_hBitmap = (union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *)&a2->hBitmap;
        if ( DC == (HDC)-589410304LL )
          v11 = ConvertWICBitmapToHBITMAP(v17, Buffer, &p_hBitmap->hBitmap, v9);
        else
          v11 = ConvertWICBitmapToDDB(v17, Buffer, &p_hBitmap->hBitmap, v9);
        Instance = v11;
      }
      v12 = Buffer;
      if ( Buffer )
      {
        Buffer = 0;
        ((void (__fastcall *)(struct IWICBitmapSource *))v12->lpVtbl->Release)(v12);
      }
    }
    v13 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    if ( Instance < 0 )
    {
LABEL_15:
      ReleaseStgMedium(a2);
      Buffer = 0;
      StringW = LoadStringW(&_ImageBase, 0xBu, (LPWSTR)&Buffer, 0);
      if ( StringW )
        RoOriginateErrorW((unsigned int)Instance, StringW, Buffer);
    }
    v15 = v17;
    if ( v17 )
    {
      v17 = 0;
      ((void (__fastcall *)(struct IWICImagingFactory *))v15->lpVtbl->Release)(v15);
    }
  }
  else
  {
    return (unsigned int)-2147221399;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18005d9f8  mov     [rsp-18h+arg_0], rbx
0x18005d9fd  push    rbp
0x18005d9fe  push    rsi
0x18005d9ff  push    rdi
0x18005da00  mov     rbp, rsp
0x18005da03  sub     rsp, 30h
0x18005da07  mov     rdi, rdx
0x18005da0a  mov     rsi, rcx
0x18005da0d  cmp     dword ptr [rdx], 10h
0x18005da10  jz      short loc_18005DA1C
0x18005da12  mov     ebx, 80040069h
0x18005da17  jmp     loc_18005DB72
0x18005da1c  mov     [rbp+arg_8], 0
0x18005da24  lea     rcx, [rbp+arg_8]
0x18005da28  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18005da2d  mov     [rsp+30h+ppv], rax; ppv
0x18005da32  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18005da39  xor     edx, edx; pUnkOuter
0x18005da3b  lea     r8d, [rdx+1]; dwClsContext
0x18005da3f  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18005da46  call    cs:__imp_CoCreateInstance
0x18005da4c  mov     ebx, eax
0x18005da4e  test    eax, eax
0x18005da50  js      loc_18005DB18
0x18005da56  mov     [rbp+arg_18], 0
0x18005da5e  lea     rcx, [rbp+arg_18]
0x18005da62  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18005da67  mov     r8, rax
0x18005da6a  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18005da71  mov     rcx, rsi
0x18005da74  call    cs:__imp_CreateStreamOverRandomAccessStream
0x18005da7a  mov     ebx, eax
0x18005da7c  test    eax, eax
0x18005da7e  js      short loc_18005DAF6
0x18005da80  mov     [rbp+Buffer], 0
0x18005da88  lea     r9, [rbp+Buffer]
0x18005da8c  mov     rdx, [rbp+arg_18]
0x18005da90  mov     rcx, [rbp+arg_8]
0x18005da94  call    ?LoadImageWithWIC@@YAJPEAUIWICImagingFactory@@PEAUIStream@@W4LOAD_IMAGE_WITH_WIC_OPTION@@PEAPEAUIWICBitmapSource@@PEAPEAUIWICBitmapFrameDecode@@PEAU_GUID@@@Z; LoadImageWithWIC(IWICImagingFactory *,IStream *,LOAD_IMAGE_WITH_WIC_OPTION,IWICBitmapSource * *,IWICBitmapFrameDecode * *,_GUID *)
0x18005da99  mov     ebx, eax
0x18005da9b  test    eax, eax
0x18005da9d  js      short loc_18005DAD8
0x18005da9f  xor     ecx, ecx; hWnd
0x18005daa1  call    cs:__imp_GetDC
0x18005daa7  mov     rbx, rax
0x18005daaa  mov     rdx, rax; hDC
0x18005daad  xor     ecx, ecx; hWnd
0x18005daaf  call    cs:__imp_ReleaseDC
0x18005dab5  lea     r8, [rdi+8]; HBITMAP *
0x18005dab9  mov     rdx, [rbp+Buffer]; struct IWICBitmapSource *
0x18005dabd  mov     rcx, [rbp+arg_8]; struct IWICImagingFactory *
0x18005dac1  cmp     rbx, 0FFFFFFFFDCDE5000h
0x18005dac8  jnz     short loc_18005DAD1
0x18005daca  call    ?ConvertWICBitmapToHBITMAP@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; ConvertWICBitmapToHBITMAP(IWICImagingFactory *,IWICBitmapSource *,HBITMAP__ * *)
0x18005dacf  jmp     short loc_18005DAD6
0x18005dad1  call    ?ConvertWICBitmapToDDB@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z; ConvertWICBitmapToDDB(IWICImagingFactory *,IWICBitmapSource *,HBITMAP__ * *)
0x18005dad6  mov     ebx, eax
0x18005dad8  mov     rcx, [rbp+Buffer]
0x18005dadc  test    rcx, rcx
0x18005dadf  jz      short loc_18005DAF6
0x18005dae1  mov     [rbp+Buffer], 0
0x18005dae9  mov     rax, [rcx]
0x18005daec  mov     rax, [rax+10h]
0x18005daf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005daf5  nop
0x18005daf6  mov     rcx, [rbp+arg_18]
0x18005dafa  test    rcx, rcx
0x18005dafd  jz      short loc_18005DB14
0x18005daff  mov     [rbp+arg_18], 0
0x18005db07  mov     rax, [rcx]
0x18005db0a  mov     rax, [rax+10h]
0x18005db0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db13  nop
0x18005db14  test    ebx, ebx
0x18005db16  jns     short loc_18005DB54
0x18005db18  mov     rcx, rdi; LPSTGMEDIUM
0x18005db1b  call    cs:__imp_ReleaseStgMedium
0x18005db21  mov     [rbp+Buffer], 0
0x18005db29  xor     r9d, r9d; cchBufferMax
0x18005db2c  lea     r8, [rbp+Buffer]; lpBuffer
0x18005db30  lea     edx, [r9+0Bh]; uID
0x18005db34  lea     rcx, __ImageBase; hInstance
0x18005db3b  call    cs:__imp_LoadStringW
0x18005db41  test    eax, eax
0x18005db43  jz      short loc_18005DB54
0x18005db45  mov     r8, [rbp+Buffer]
0x18005db49  mov     edx, eax
0x18005db4b  mov     ecx, ebx
0x18005db4d  call    cs:__imp_RoOriginateErrorW
0x18005db53  nop
0x18005db54  mov     rcx, [rbp+arg_8]
0x18005db58  test    rcx, rcx
0x18005db5b  jz      short loc_18005DB72
0x18005db5d  mov     [rbp+arg_8], 0
0x18005db65  mov     rax, [rcx]
0x18005db68  mov     rax, [rax+10h]
0x18005db6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db71  nop
0x18005db72  mov     eax, ebx
0x18005db74  mov     rbx, [rsp+30h+arg_0]
0x18005db79  add     rsp, 30h
0x18005db7d  pop     rdi
0x18005db7e  pop     rsi
0x18005db7f  pop     rbp
0x18005db80  retn
```
