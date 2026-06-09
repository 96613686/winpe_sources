# CAccentAcrylicBlurBehind::CNoiseSurfaceCache::EnsureNoiseSurfaceBrush(void)

- ea: `0x180099ccc`
- end: `0x18009a0c5`
- name: `?EnsureNoiseSurfaceBrush@CNoiseSurfaceCache@CAccentAcrylicBlurBehind@@AEAAJXZ`
- size: `1017`
- prototype: `__int64 __fastcall(CAccentAcrylicBlurBehind::CNoiseSurfaceCache *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180094b44`

## callees

- `0x1800028f4`
- `0x1800061e4`
- `0x1800068e0`
- `0x18000aa54`
- `0x18001f43c`
- `0x180099ccc`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180099cff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180099cff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180099d24`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180099d24`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180099d3c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180099d3c`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180099d2d`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180099d2d`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180099d15`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180099d15`

## string_xrefs

- `0x180099cf8`: `Windows.UI.Xaml.Controls.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAccentAcrylicBlurBehind::CNoiseSurfaceCache::EnsureNoiseSurfaceBrush(
        CAccentAcrylicBlurBehind::CNoiseSurfaceCache *this)
{
  unsigned int v1; // ebx
  char *v2; // r14
  HMODULE ModuleHandleW; // rdi
  HRSRC ResourceW; // rbx
  HGLOBAL Resource; // rax
  LPVOID v6; // r15
  DWORD v7; // edi
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  __int64 (__fastcall *v12)(__int64, __int64, _QWORD, __int64, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int v18; // eax
  int v19; // eax
  __int64 (__fastcall *v20)(__int64, __int64, __int64, struct IWICBitmapSource **); // rbx
  int v21; // eax
  int CompSurfaceFromWICBitmap; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, struct Windows::UI::Composition::ICompositionSurface *, __int64 *); // rbx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  struct IWICBitmapSource *v29; // [rsp+40h] [rbp-20h] BYREF
  __int64 v30; // [rsp+48h] [rbp-18h] BYREF
  struct Windows::UI::Composition::ICompositionSurface *v31[2]; // [rsp+50h] [rbp-10h] BYREF
  __int64 v32; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v33; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v34; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v35; // [rsp+B8h] [rbp+58h] BYREF

  v1 = 0;
  v2 = (char *)this + 24;
  if ( (unsigned __int8)std::operator==<CWindowBorder::CCachedBorderBrush>((char *)this + 24) )
  {
    ModuleHandleW = GetModuleHandleW(L"Windows.UI.Xaml.Controls.dll");
    ResourceW = FindResourceW(ModuleHandleW, (LPCWSTR)0x7D0, (LPCWSTR)0xA);
    Resource = LoadResource(ModuleHandleW, ResourceW);
    v6 = LockResource(Resource);
    v7 = SizeofResource(ModuleHandleW, ResourceW);
    v8 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 30);
    v32 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 112LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v32);
    v10 = v9(v8, &v32);
    v1 = v10;
    if ( v10 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v10, 0x4D7u, 0);
    }
    else
    {
      v11 = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD))(*(_QWORD *)v32 + 128LL))(v32, v6, v7);
      v1 = v11;
      if ( v11 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v11, 0x4D8u, 0);
      }
      else
      {
        v33 = 0;
        v12 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v8 + 32LL);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
        v13 = v12(v8, v32, 0, 1, &v33);
        v1 = v13;
        if ( v13 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v13, 0x4DBu, 0);
        }
        else
        {
          v35 = 0;
          v14 = v33;
          v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 104LL);
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v35);
          v16 = v15(v14, 0, &v35);
          v1 = v16;
          if ( v16 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v16, 0x4DEu, 0);
          }
          else
          {
            v34 = 0;
            v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 80LL);
            Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v34);
            v18 = v17(v8, &v34);
            v1 = v18;
            if ( v18 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v18, 0x4E1u, 0);
            }
            else
            {
              v19 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)v34 + 64LL))(
                      v34,
                      v35,
                      &GUID_WICPixelFormat32bppPBGRA,
                      0,
                      0,
                      0,
                      1);
              v1 = v19;
              if ( v19 < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v19, 0x4E2u, 0);
              }
              else
              {
                v29 = 0;
                v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64, struct IWICBitmapSource **))(*(_QWORD *)v8 + 144LL);
                Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
                v21 = v20(v8, v34, 2, &v29);
                v1 = v21;
                if ( v21 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v21, 0x4E5u, 0);
                }
                else
                {
                  v31[0] = 0;
                  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v31);
                  CompSurfaceFromWICBitmap = CBitmapSource::CreateCompSurfaceFromWICBitmap(v29, v31);
                  v1 = CompSurfaceFromWICBitmap;
                  if ( CompSurfaceFromWICBitmap < 0 )
                  {
                    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, CompSurfaceFromWICBitmap, 0x4E8u, 0);
                  }
                  else
                  {
                    v30 = 0;
                    v23 = *(_QWORD *)(*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 6) + 40LL);
                    v24 = *(__int64 (__fastcall **)(__int64, struct Windows::UI::Composition::ICompositionSurface *, __int64 *))(*(_QWORD *)v23 + 192LL);
                    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
                    v25 = v24(v23, v31[0], &v30);
                    v1 = v25;
                    if ( v25 < 0 )
                    {
                      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v25, 0x4EDu, 0);
                    }
                    else
                    {
                      v26 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v30 + 88LL))(v30, 0);
                      v1 = v26;
                      if ( v26 < 0 )
                      {
                        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v26, 0x4EEu, 0);
                      }
                      else
                      {
                        v27 = Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionSurfaceBrush>::As<Windows::UI::Composition::ICompositionBrush>(
                                &v30,
                                v2);
                        v1 = v27;
                        if ( v27 < 0 )
                          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v27, 0x4F1u, 0);
                      }
                    }
                    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v30);
                  }
                  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v31);
                }
                Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
              }
            }
            Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v34);
          }
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v35);
        }
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v33);
      }
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v32);
  }
  return v1;
}

```

## disassembly

```asm
0x180099ccc  push    rbp
0x180099cce  push    rbx
0x180099ccf  push    rsi
0x180099cd0  push    rdi
0x180099cd1  push    r12
0x180099cd3  push    r14
0x180099cd5  push    r15
0x180099cd7  mov     rbp, rsp
0x180099cda  sub     rsp, 60h
0x180099cde  xor     r12d, r12d
0x180099ce1  mov     ebx, r12d
0x180099ce4  lea     r14, [rcx+18h]
0x180099ce8  mov     rcx, r14
0x180099ceb  call    ??$?8VCCachedBorderBrush@CWindowBorder@@@std@@YA_NAEBV?$shared_ptr@VCCachedBorderBrush@CWindowBorder@@@0@$$T@Z; std::operator==<CWindowBorder::CCachedBorderBrush>(std::shared_ptr<CWindowBorder::CCachedBorderBrush> const &,std::nullptr_t)
0x180099cf0  test    al, al
0x180099cf2  jz      loc_18009A0B4
0x180099cf8  lea     rcx, aWindowsUiXamlC; "Windows.UI.Xaml.Controls.dll"
0x180099cff  call    cs:__imp_GetModuleHandleW
0x180099d05  mov     rdi, rax
0x180099d08  mov     edx, 7D0h; lpName
0x180099d0d  lea     r8d, [r12+0Ah]; lpType
0x180099d12  mov     rcx, rax; hModule
0x180099d15  call    cs:__imp_FindResourceW
0x180099d1b  mov     rbx, rax
0x180099d1e  mov     rdx, rax; hResInfo
0x180099d21  mov     rcx, rdi; hModule
0x180099d24  call    cs:__imp_LoadResource
0x180099d2a  mov     rcx, rax; hResData
0x180099d2d  call    cs:__imp_LockResource
0x180099d33  mov     r15, rax
0x180099d36  mov     rdx, rbx; hResInfo
0x180099d39  mov     rcx, rdi; hModule
0x180099d3c  call    cs:__imp_SizeofResource
0x180099d42  mov     edi, eax
0x180099d44  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180099d4b  mov     rsi, [rcx+0F0h]
0x180099d52  mov     [rbp+arg_0], r12
0x180099d56  mov     rcx, [rsi]
0x180099d59  mov     rbx, [rcx+70h]
0x180099d5d  lea     rcx, [rbp+arg_0]
0x180099d61  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099d66  lea     rdx, [rbp+arg_0]
0x180099d6a  mov     rcx, rsi
0x180099d6d  mov     rax, rbx
0x180099d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099d75  mov     ebx, eax
0x180099d77  test    eax, eax
0x180099d79  js      loc_18009A08D
0x180099d7f  mov     rcx, [rbp+arg_0]
0x180099d83  mov     rax, [rcx]
0x180099d86  mov     r8d, edi
0x180099d89  mov     rdx, r15
0x180099d8c  mov     rax, [rax+80h]
0x180099d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099d98  mov     ebx, eax
0x180099d9a  test    eax, eax
0x180099d9c  js      loc_18009A07E
0x180099da2  mov     [rbp+arg_8], r12
0x180099da6  mov     rax, [rsi]
0x180099da9  mov     rbx, [rax+20h]
0x180099dad  lea     rcx, [rbp+arg_8]
0x180099db1  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099db6  lea     rax, [rbp+arg_8]
0x180099dba  mov     qword ptr [rsp+60h+var_40], rax
0x180099dbf  lea     r15d, [r12+1]
0x180099dc4  mov     r9d, r15d
0x180099dc7  xor     r8d, r8d
0x180099dca  mov     rdx, [rbp+arg_0]
0x180099dce  mov     rcx, rsi
0x180099dd1  mov     rax, rbx
0x180099dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099dd9  mov     ebx, eax
0x180099ddb  test    eax, eax
0x180099ddd  js      loc_18009A05C
0x180099de3  mov     [rbp+arg_18], r12
0x180099de7  mov     rdi, [rbp+arg_8]
0x180099deb  mov     rax, [rdi]
0x180099dee  mov     rbx, [rax+68h]
0x180099df2  lea     rcx, [rbp+arg_18]
0x180099df6  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099dfb  lea     r8, [rbp+arg_18]
0x180099dff  xor     edx, edx
0x180099e01  mov     rcx, rdi
0x180099e04  mov     rax, rbx
0x180099e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099e0c  mov     ebx, eax
0x180099e0e  test    eax, eax
0x180099e10  js      loc_18009A03A
0x180099e16  mov     [rbp+arg_10], r12
0x180099e1a  mov     rax, [rsi]
0x180099e1d  mov     rbx, [rax+50h]
0x180099e21  lea     rcx, [rbp+arg_10]
0x180099e25  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099e2a  lea     rdx, [rbp+arg_10]
0x180099e2e  mov     rcx, rsi
0x180099e31  mov     rax, rbx
0x180099e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099e39  mov     ebx, eax
0x180099e3b  test    eax, eax
0x180099e3d  js      loc_18009A02B
0x180099e43  mov     rcx, [rbp+arg_10]
0x180099e47  mov     rax, [rcx]
0x180099e4a  mov     [rsp+60h+var_30], r15d
0x180099e4f  xorps   xmm0, xmm0
0x180099e52  movsd   [rsp+60h+var_38], xmm0
0x180099e58  mov     qword ptr [rsp+60h+var_40], r12
0x180099e5d  xor     r9d, r9d
0x180099e60  lea     r8, GUID_WICPixelFormat32bppPBGRA
0x180099e67  mov     rdx, [rbp+arg_18]
0x180099e6b  mov     rax, [rax+40h]
0x180099e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099e74  mov     ebx, eax
0x180099e76  test    eax, eax
0x180099e78  js      loc_18009A009
0x180099e7e  mov     [rbp+var_20], r12
0x180099e82  mov     rax, [rsi]
0x180099e85  mov     rbx, [rax+90h]
0x180099e8c  lea     rcx, [rbp+var_20]
0x180099e90  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099e95  lea     r9, [rbp+var_20]
0x180099e99  lea     r8d, [r12+2]
0x180099e9e  mov     rdx, [rbp+arg_10]
0x180099ea2  mov     rcx, rsi
0x180099ea5  mov     rax, rbx
0x180099ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099ead  mov     ebx, eax
0x180099eaf  test    eax, eax
0x180099eb1  js      loc_180099FE7
0x180099eb7  mov     [rbp+var_10], r12
0x180099ebb  lea     rcx, [rbp+var_10]
0x180099ebf  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099ec4  lea     rdx, [rbp+var_10]; struct Windows::UI::Composition::ICompositionSurface **
0x180099ec8  mov     rcx, [rbp+var_20]; struct IWICBitmapSource *
0x180099ecc  call    ?CreateCompSurfaceFromWICBitmap@CBitmapSource@@SAJPEAUIWICBitmapSource@@PEAPEAUICompositionSurface@Composition@UI@Windows@@@Z; CBitmapSource::CreateCompSurfaceFromWICBitmap(IWICBitmapSource *,Windows::UI::Composition::ICompositionSurface * *)
0x180099ed1  mov     ebx, eax
0x180099ed3  test    eax, eax
0x180099ed5  js      loc_180099FC5
0x180099edb  mov     [rbp+var_18], r12
0x180099edf  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180099ee6  mov     rcx, [rax+30h]
0x180099eea  mov     rdi, [rcx+28h]
0x180099eee  mov     rax, [rdi]
0x180099ef1  mov     rbx, [rax+0C0h]
0x180099ef8  lea     rcx, [rbp+var_18]
0x180099efc  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099f01  lea     r8, [rbp+var_18]
0x180099f05  mov     rdx, [rbp+var_10]
0x180099f09  mov     rcx, rdi
0x180099f0c  mov     rax, rbx
0x180099f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099f14  mov     ebx, eax
0x180099f16  test    eax, eax
0x180099f18  js      loc_180099FB6
0x180099f1e  mov     rcx, [rbp+var_18]
0x180099f22  mov     rax, [rcx]
0x180099f25  xor     edx, edx
0x180099f27  mov     rax, [rax+58h]
0x180099f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099f30  mov     ebx, eax
0x180099f32  test    eax, eax
0x180099f34  js      short loc_180099FA7
0x180099f36  mov     rdx, r14
0x180099f39  lea     rcx, [rbp+var_18]
0x180099f3d  call    ??$As@UICompositionBrush@Composition@UI@Windows@@@?$ComPtr@UICompositionSurfaceBrush@Composition@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICompositionBrush@Composition@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionSurfaceBrush>::As<Windows::UI::Composition::ICompositionBrush>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionBrush>>)
0x180099f42  mov     ebx, eax
0x180099f44  test    eax, eax
0x180099f46  js      short loc_180099F88
0x180099f48  lea     rcx, [rbp+var_18]
0x180099f4c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099f51  nop
0x180099f52  lea     rcx, [rbp+var_10]
0x180099f56  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099f5b  nop
0x180099f5c  lea     rcx, [rbp+var_20]
0x180099f60  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099f65  nop
0x180099f66  lea     rcx, [rbp+arg_10]
0x180099f6a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099f6f  nop
0x180099f70  lea     rcx, [rbp+arg_18]
0x180099f74  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099f79  nop
0x180099f7a  lea     rcx, [rbp+arg_8]
0x180099f7e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180099f83  jmp     loc_18009A0AB
0x180099f88  mov     [rsp+60h+var_38], r12; void *
0x180099f8d  mov     [rsp+60h+var_40], 4F1h; unsigned int
0x180099f95  mov     r9d, eax; int
0x180099f98  xor     r8d, r8d; unsigned int
0x180099f9b  xor     edx, edx; int *
0x180099f9d  lea     ecx, [rdx+14h]; unsigned int
0x180099fa0  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180099fa5  jmp     short loc_180099F48
0x180099fa7  mov     [rsp+60h+var_38], r12
0x180099fac  mov     [rsp+60h+var_40], 4EEh
0x180099fb4  jmp     short loc_180099F95
0x180099fb6  mov     [rsp+60h+var_38], r12
0x180099fbb  mov     [rsp+60h+var_40], 4EDh
0x180099fc3  jmp     short loc_180099F95
0x180099fc5  mov     [rsp+60h+var_38], r12; void *
0x180099fca  mov     [rsp+60h+var_40], 4E8h; unsigned int
0x180099fd2  mov     r9d, eax; int
0x180099fd5  xor     r8d, r8d; unsigned int
0x180099fd8  xor     edx, edx; int *
0x180099fda  lea     ecx, [rdx+14h]; unsigned int
0x180099fdd  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180099fe2  jmp     loc_180099F52
0x180099fe7  mov     [rsp+60h+var_38], r12; void *
0x180099fec  mov     [rsp+60h+var_40], 4E5h; unsigned int
0x180099ff4  mov     r9d, eax; int
0x180099ff7  xor     r8d, r8d; unsigned int
0x180099ffa  xor     edx, edx; int *
0x180099ffc  lea     ecx, [rdx+14h]; unsigned int
0x180099fff  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18009a004  jmp     loc_180099F5C
0x18009a009  mov     [rsp+60h+var_38], r12; void *
0x18009a00e  mov     [rsp+60h+var_40], 4E2h; unsigned int
0x18009a016  mov     r9d, eax; int
0x18009a019  xor     r8d, r8d; unsigned int
0x18009a01c  xor     edx, edx; int *
0x18009a01e  lea     ecx, [rdx+14h]; unsigned int
0x18009a021  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18009a026  jmp     loc_180099F66
0x18009a02b  mov     [rsp+60h+var_38], r12
0x18009a030  mov     [rsp+60h+var_40], 4E1h
0x18009a038  jmp     short loc_18009A016
0x18009a03a  mov     [rsp+60h+var_38], r12; void *
0x18009a03f  mov     [rsp+60h+var_40], 4DEh; unsigned int
0x18009a047  mov     r9d, eax; int
0x18009a04a  xor     r8d, r8d; unsigned int
0x18009a04d  xor     edx, edx; int *
0x18009a04f  lea     ecx, [rdx+14h]; unsigned int
0x18009a052  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18009a057  jmp     loc_180099F70
0x18009a05c  mov     [rsp+60h+var_38], r12; void *
0x18009a061  mov     [rsp+60h+var_40], 4DBh; unsigned int
0x18009a069  mov     r9d, eax; int
0x18009a06c  xor     r8d, r8d; unsigned int
0x18009a06f  xor     edx, edx; int *
0x18009a071  lea     ecx, [rdx+14h]; unsigned int
0x18009a074  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18009a079  jmp     loc_180099F7A
0x18009a07e  mov     [rsp+60h+var_38], r12
0x18009a083  mov     [rsp+60h+var_40], 4D8h
0x18009a08b  jmp     short loc_18009A09A
0x18009a08d  mov     [rsp+60h+var_38], r12; void *
0x18009a092  mov     [rsp+60h+var_40], 4D7h; unsigned int
0x18009a09a  mov     r9d, eax; int
0x18009a09d  xor     r8d, r8d; unsigned int
0x18009a0a0  xor     edx, edx; int *
0x18009a0a2  lea     ecx, [rdx+14h]; unsigned int
0x18009a0a5  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18009a0aa  nop
0x18009a0ab  lea     rcx, [rbp+arg_0]
0x18009a0af  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009a0b4  mov     eax, ebx
0x18009a0b6  add     rsp, 60h
0x18009a0ba  pop     r15
0x18009a0bc  pop     r14
0x18009a0be  pop     r12
0x18009a0c0  pop     rdi
0x18009a0c1  pop     rsi
0x18009a0c2  pop     rbx
0x18009a0c3  pop     rbp
0x18009a0c4  retn
```
