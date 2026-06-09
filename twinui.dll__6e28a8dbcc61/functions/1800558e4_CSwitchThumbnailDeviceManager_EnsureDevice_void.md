# CSwitchThumbnailDeviceManager::_EnsureDevice(void)

- ea: `0x1800558e4`
- end: `0x180055dca`
- name: `?_EnsureDevice@CSwitchThumbnailDeviceManager@@AEAAJXZ`
- size: `1254`
- prototype: `__int64 __fastcall(CSwitchThumbnailDeviceManager *__hidden this)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800554b0`
- `0x180094544`
- `0x1801daea0`

## callees

- `0x180008acc`
- `0x18000b7e8`
- `0x18000c350`
- `0x1800558e4`
- `0x180055dd0`
- `0x180055e28`
- `0x180069ec4`
- `0x1800a2e70`
- `0x180101360`
- `0x180105474`
- `0x18013d330`
- `0x1801db048`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180055d95`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180055d95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055bed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055c21`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055c8d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055bed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055c21`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055c8d`
- `dcomp!DCompositionCreateDevice2` at `0x180055bb9`
- `dcomp!DCompositionCreateDevice2` at `0x180055bb9`
- `d3d11!D3D11CreateDevice` at `0x1800559b5`
- `d3d11!D3D11CreateDevice` at `0x1800559fa`
- `d3d11!D3D11CreateDevice` at `0x1800559b5`
- `d3d11!D3D11CreateDevice` at `0x1800559fa`
- `d2d1!__imp_D2D1CreateFactory` at `0x180055a56`
- `d2d1!__imp_D2D1CreateFactory` at `0x180055a56`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180055940`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180055940`

## string_xrefs

- `0x180055aca`: `Windows.UI.Composition.Compositor`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CSwitchThumbnailDeviceManager::_EnsureDevice(CSwitchThumbnailDeviceManager *this)
{
  HRESULT Device; // ebx
  void *v3; // rbx
  _QWORD *v4; // r15
  __int64 (__fastcall *v5)(void *, __int64, char *); // rdi
  __int64 (__fastcall ***v6)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, _QWORD, GUID *, char *); // rbx
  char *v10; // r12
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, char *); // rbx
  void *v13; // rcx
  __int64 v14; // rcx
  _QWORD *v15; // r14
  __int64 (__fastcall ***v16)(_QWORD, GUID *, void **); // rdi
  __int64 (__fastcall *v17)(_QWORD, GUID *, void **); // rbx
  __int64 pvParam; // [rsp+50h] [rbp-39h] BYREF
  void *ppIFactory; // [rsp+58h] [rbp-31h] BYREF
  __int64 v21; // [rsp+60h] [rbp-29h] BYREF
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-19h] BYREF
  __int64 v24; // [rsp+88h] [rbp-1h]

  Device = 0;
  if ( (int)CSwitchThumbnailDeviceManager::_ValidateDevice(this) < 0 )
    CSwitchThumbnailDeviceManager::_DestroyDevice(this);
  if ( !*((_DWORD *)this + 56) )
  {
    LODWORD(pvParam) = 0;
    SystemParametersInfoW(0x1042u, 0, &pvParam, 0);
    *((_BYTE *)this + 256) = (_DWORD)pvParam != 0;
  }
  if ( !*((_QWORD *)this + 13) )
  {
    if ( (*((_BYTE *)this + 260) & 4) == 0 )
    {
      LODWORD(pvParam) = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 112);
      Device = D3D11CreateDevice(
                 0,
                 D3D_DRIVER_TYPE_HARDWARE,
                 0,
                 0x20u,
                 0,
                 0,
                 7u,
                 (ID3D11Device **)this + 14,
                 (D3D_FEATURE_LEVEL *)&pvParam,
                 0);
      if ( Device == -2005270523 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 112);
        Device = D3D11CreateDevice(
                   0,
                   D3D_DRIVER_TYPE_WARP,
                   0,
                   0x20u,
                   0,
                   0,
                   7u,
                   (ID3D11Device **)this + 14,
                   (D3D_FEATURE_LEVEL *)&pvParam,
                   0);
      }
      if ( Device < 0 )
        goto LABEL_40;
    }
    v21 = 0;
    if ( (*((_BYTE *)this + 260) & 4) == 0 )
    {
      Device = Microsoft::WRL::ComPtr<ID3D11Device>::As<IDXGIDevice>((char *)this + 112, &v21);
      if ( Device < 0 )
      {
LABEL_30:
        v14 = v21;
        if ( v21 )
        {
          v21 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        if ( Device >= 0 )
        {
          v15 = (_QWORD *)((char *)this + 144);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 144);
          Device = CoCreateInstance(
                     &CLSID_UIAnimationTimer,
                     0,
                     1u,
                     &GUID_6b0efad1_a053_41d6_9085_33a689144665,
                     (LPVOID *)this + 18);
          if ( Device >= 0 )
          {
            ppIFactory = 0;
            v16 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 17);
            v17 = **v16;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppIFactory);
            Device = v17(v16, &GUID_195509b7_5d5e_4e3e_b278_ee3759b367ad, &ppIFactory);
            if ( Device >= 0 )
            {
              Device = (*(__int64 (__fastcall **)(_QWORD, void *, __int64))(*(_QWORD *)*v15 + 24LL))(
                         *v15,
                         ppIFactory,
                         1);
              if ( Device >= 0 )
              {
                v21 = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
                Device = Microsoft::WRL::Details::MakeAndInitialize<CDCompThumbnailTimerEventHandler,IUIAnimationTimerEventHandler,>(&v21);
                if ( Device >= 0 )
                  Device = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v15 + 32LL))(*v15, v21);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppIFactory);
          }
        }
LABEL_40:
        *((_BYTE *)this + 258) = (unsigned int)Mirror_IsThreadRTL() != 0;
        if ( Device >= 0 )
        {
          Device = CSwitchThumbnailDeviceManager::_LoadPVLInfo(this);
          if ( Device >= 0 )
          {
            LODWORD(pvParam) = 0;
            LODWORD(ppIFactory) = 4;
            RegGetValueW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\ImmersiveShell\\Switcher",
              L"AllowSlowAnimations",
              0x10u,
              0,
              &pvParam,
              (LPDWORD)&ppIFactory);
            *((_BYTE *)this + 257) = (_DWORD)pvParam != 0;
          }
        }
        return (unsigned int)Device;
      }
    }
    ppIFactory = 0;
    if ( (*((_BYTE *)this + 260) & 4) != 0 )
      goto LABEL_15;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppIFactory);
    Device = D2D1CreateFactory(
               D2D1_FACTORY_TYPE_SINGLE_THREADED,
               &GUID_94f81a73_9212_4376_9c58_b16a3a0d3992,
               0,
               &ppIFactory);
    if ( Device >= 0 )
    {
      v3 = ppIFactory;
      if ( (*((_BYTE *)this + 260) & 4) != 0 )
      {
LABEL_15:
        v4 = (_QWORD *)((char *)this + 120);
LABEL_17:
        if ( (*((_BYTE *)this + 260) & 2) != 0 )
        {
          v22 = 0;
          v24 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &hstringHeader,
            L"Windows.UI.Composition.Compositor",
            0x22u,
            0x21u);
          Device = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(v24, &v22);
          if ( Device >= 0 )
          {
            pvParam = 0;
            v6 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
            v7 = **v22;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pvParam);
            Device = v7(v6, &GUID_22118adf_23f1_4801_bcfa_66cbf48cc51b, &pvParam);
            if ( Device >= 0 )
            {
              v8 = pvParam;
              v9 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *, char *))(*(_QWORD *)pvParam + 48LL);
              v10 = (char *)this + 128;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 128);
              Device = v9(v8, *v4, 0, &GUID_b403ca50_7f8c_4e83_985f_cc45060036d8, (char *)this + 128);
              if ( Device >= 0 )
              {
                v11 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))v10;
                v12 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))v10;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 104);
                Device = v12(v11, &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0, (char *)this + 104);
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pvParam);
          }
          v24 = 0;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
        }
        else
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 104);
          Device = DCompositionCreateDevice2(*v4, &GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0, (char *)this + 104);
        }
        if ( Device >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 136);
          Device = CoCreateInstance(
                     &CLSID_UIAnimationManager2,
                     0,
                     1u,
                     &GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1,
                     (LPVOID *)this + 17);
          if ( Device >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 152);
            Device = CoCreateInstance(
                       &CLSID_UIAnimationTransitionLibrary2,
                       0,
                       1u,
                       &GUID_03cfae53_9580_4ee3_b363_2ece51b4af6a,
                       (LPVOID *)this + 19);
          }
        }
        goto LABEL_28;
      }
      v5 = *(__int64 (__fastcall **)(void *, __int64, char *))(*(_QWORD *)ppIFactory + 136LL);
      v4 = (_QWORD *)((char *)this + 120);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 120);
      Device = v5(v3, v21, (char *)this + 120);
      if ( Device >= 0 )
        goto LABEL_17;
    }
LABEL_28:
    v13 = ppIFactory;
    if ( ppIFactory )
    {
      ppIFactory = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_30;
  }
  return (unsigned int)Device;
}

```

## disassembly

```asm
0x1800558e4  push    rbp
0x1800558e6  push    rbx
0x1800558e7  push    rsi
0x1800558e8  push    rdi
0x1800558e9  push    r12
0x1800558eb  push    r13
0x1800558ed  push    r14
0x1800558ef  push    r15
0x1800558f1  lea     rbp, [rsp-1Fh]
0x1800558f6  sub     rsp, 0A8h
0x1800558fd  mov     rax, cs:__security_cookie
0x180055904  xor     rax, rsp
0x180055907  mov     [rbp+57h+var_50], rax
0x18005590b  mov     rsi, rcx
0x18005590e  xor     r13d, r13d
0x180055911  mov     ebx, r13d
0x180055914  call    ?_ValidateDevice@CSwitchThumbnailDeviceManager@@AEAAJXZ; CSwitchThumbnailDeviceManager::_ValidateDevice(void)
0x180055919  test    eax, eax
0x18005591b  jns     short loc_180055925
0x18005591d  mov     rcx, rsi; this
0x180055920  call    ?_DestroyDevice@CSwitchThumbnailDeviceManager@@AEAAXXZ; CSwitchThumbnailDeviceManager::_DestroyDevice(void)
0x180055925  cmp     [rsi+0E0h], r13d
0x18005592c  jnz     short loc_180055953
0x18005592e  mov     dword ptr [rbp+57h+pvParam], r13d
0x180055932  xor     r9d, r9d; fWinIni
0x180055935  lea     r8, [rbp+57h+pvParam]; pvParam
0x180055939  xor     edx, edx; uiParam
0x18005593b  mov     ecx, 1042h; uiAction
0x180055940  call    cs:__imp_SystemParametersInfoW
0x180055946  cmp     dword ptr [rbp+57h+pvParam], r13d
0x18005594a  setnz   al
0x18005594d  mov     [rsi+100h], al
0x180055953  lea     r14, [rsi+68h]
0x180055957  cmp     [r14], r13
0x18005595a  jnz     loc_180055DA8
0x180055960  lea     rdi, [rsi+70h]
0x180055964  test    byte ptr [rsi+104h], 4
0x18005596b  jnz     loc_180055A0A
0x180055971  mov     dword ptr [rbp+57h+pvParam], r13d
0x180055975  mov     rcx, rdi
0x180055978  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005597d  mov     [rsp+0E0h+ppImmediateContext], r13; ppImmediateContext
0x180055982  lea     rax, [rbp+57h+pvParam]
0x180055986  mov     [rsp+0E0h+pFeatureLevel], rax; pFeatureLevel
0x18005598b  mov     [rsp+0E0h+ppDevice], rdi; ppDevice
0x180055990  mov     r15d, 7
0x180055996  mov     [rsp+0E0h+SDKVersion], r15d; SDKVersion
0x18005599b  mov     [rsp+0E0h+FeatureLevels], r13d; FeatureLevels
0x1800559a0  mov     [rsp+0E0h+pFeatureLevels], r13; pFeatureLevels
0x1800559a5  lea     r12d, [r15+19h]
0x1800559a9  mov     r9d, r12d; Flags
0x1800559ac  xor     r8d, r8d; Software
0x1800559af  lea     edx, [r15-6]; DriverType
0x1800559b3  xor     ecx, ecx; pAdapter
0x1800559b5  call    cs:__imp_D3D11CreateDevice
0x1800559bb  mov     ebx, eax
0x1800559bd  cmp     eax, 887A0005h
0x1800559c2  jnz     short loc_180055A02
0x1800559c4  mov     rcx, rdi
0x1800559c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800559cc  mov     [rsp+0E0h+ppImmediateContext], r13; ppImmediateContext
0x1800559d1  lea     rax, [rbp+57h+pvParam]
0x1800559d5  mov     [rsp+0E0h+pFeatureLevel], rax; pFeatureLevel
0x1800559da  mov     [rsp+0E0h+ppDevice], rdi; ppDevice
0x1800559df  mov     [rsp+0E0h+SDKVersion], r15d; SDKVersion
0x1800559e4  mov     [rsp+0E0h+FeatureLevels], r13d; FeatureLevels
0x1800559e9  mov     [rsp+0E0h+pFeatureLevels], r13; pFeatureLevels
0x1800559ee  mov     r9d, r12d; Flags
0x1800559f1  xor     r8d, r8d; Software
0x1800559f4  lea     edx, [r15-2]; DriverType
0x1800559f8  xor     ecx, ecx; pAdapter
0x1800559fa  call    cs:__imp_D3D11CreateDevice
0x180055a00  mov     ebx, eax
0x180055a02  test    ebx, ebx
0x180055a04  js      loc_180055D36
0x180055a0a  mov     [rbp+57h+var_80], r13
0x180055a0e  test    byte ptr [rsi+104h], 4
0x180055a15  jnz     short loc_180055A2D
0x180055a17  lea     rdx, [rbp+57h+var_80]
0x180055a1b  mov     rcx, rdi
0x180055a1e  call    ??$As@UIDXGIDevice@@@?$ComPtr@UID3D11Device@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDXGIDevice@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Device>::As<IDXGIDevice>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDXGIDevice>>)
0x180055a23  mov     ebx, eax
0x180055a25  test    eax, eax
0x180055a27  js      loc_180055C43
0x180055a2d  mov     rbx, r13
0x180055a30  mov     [rbp+57h+ppIFactory], rbx
0x180055a34  test    byte ptr [rsi+104h], 4
0x180055a3b  jnz     short loc_180055A73
0x180055a3d  lea     rcx, [rbp+57h+ppIFactory]
0x180055a41  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055a46  lea     r9, [rbp+57h+ppIFactory]; ppIFactory
0x180055a4a  xor     r8d, r8d; pFactoryOptions
0x180055a4d  lea     rdx, _GUID_94f81a73_9212_4376_9c58_b16a3a0d3992; riid
0x180055a54  xor     ecx, ecx; factoryType
0x180055a56  call    cs:__imp_D2D1CreateFactory
0x180055a5c  mov     ebx, eax
0x180055a5e  test    eax, eax
0x180055a60  js      loc_180055C29
0x180055a66  mov     rbx, [rbp+57h+ppIFactory]
0x180055a6a  test    byte ptr [rsi+104h], 4
0x180055a71  jz      short loc_180055A79
0x180055a73  lea     r15, [rsi+78h]
0x180055a77  jmp     short loc_180055AAB
0x180055a79  mov     rax, [rbx]
0x180055a7c  mov     rdi, [rax+88h]
0x180055a83  lea     r15, [rsi+78h]
0x180055a87  mov     rcx, r15
0x180055a8a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055a8f  mov     r8, r15
0x180055a92  mov     rdx, [rbp+57h+var_80]
0x180055a96  mov     rcx, rbx
0x180055a99  mov     rax, rdi
0x180055a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055aa1  mov     ebx, eax
0x180055aa3  test    eax, eax
0x180055aa5  js      loc_180055C29
0x180055aab  test    byte ptr [rsi+104h], 2
0x180055ab2  jz      loc_180055BA4
0x180055ab8  mov     [rbp+57h+var_78], r13
0x180055abc  mov     [rbp+57h+var_58], r13
0x180055ac0  mov     r9d, 21h ; '!'; unsigned int
0x180055ac6  lea     r8d, [r9+1]; unsigned int
0x180055aca  lea     rdx, ?RuntimeClass_Windows_UI_Composition_Compositor@@3QBGB; "Windows.UI.Composition.Compositor"
0x180055ad1  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180055ad5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180055ada  nop
0x180055adb  lea     rdx, [rbp+57h+var_78]
0x180055adf  mov     rcx, [rbp+57h+var_58]
0x180055ae3  call    ??$GetActivationFactory@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IActivationFactory>>)
0x180055ae8  mov     ebx, eax
0x180055aea  test    eax, eax
0x180055aec  js      loc_180055B95
0x180055af2  mov     [rbp+57h+pvParam], r13
0x180055af6  mov     rbx, [rbp+57h+var_78]
0x180055afa  mov     rax, [rbx]
0x180055afd  mov     rdi, [rax]
0x180055b00  lea     rcx, [rbp+57h+pvParam]
0x180055b04  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055b09  lea     r8, [rbp+57h+pvParam]
0x180055b0d  lea     rdx, _GUID_22118adf_23f1_4801_bcfa_66cbf48cc51b
0x180055b14  mov     rcx, rbx
0x180055b17  mov     rax, rdi
0x180055b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b1f  mov     ebx, eax
0x180055b21  test    eax, eax
0x180055b23  js      short loc_180055B8B
0x180055b25  mov     rdi, [rbp+57h+pvParam]
0x180055b29  mov     rax, [rdi]
0x180055b2c  mov     rbx, [rax+30h]
0x180055b30  lea     r12, [rsi+80h]
0x180055b37  mov     rcx, r12
0x180055b3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055b3f  mov     [rsp+0E0h+pFeatureLevels], r12
0x180055b44  lea     r9, _GUID_b403ca50_7f8c_4e83_985f_cc45060036d8
0x180055b4b  xor     r8d, r8d
0x180055b4e  mov     rdx, [r15]
0x180055b51  mov     rcx, rdi
0x180055b54  mov     rax, rbx
0x180055b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b5c  mov     ebx, eax
0x180055b5e  test    eax, eax
0x180055b60  js      short loc_180055B8B
0x180055b62  mov     rdi, [r12]
0x180055b66  mov     rax, [rdi]
0x180055b69  mov     rbx, [rax]
0x180055b6c  mov     rcx, r14
0x180055b6f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055b74  mov     r8, r14
0x180055b77  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x180055b7e  mov     rcx, rdi
0x180055b81  mov     rax, rbx
0x180055b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b89  mov     ebx, eax
0x180055b8b  lea     rcx, [rbp+57h+pvParam]
0x180055b8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055b94  nop
0x180055b95  mov     [rbp+57h+var_58], r13
0x180055b99  lea     rcx, [rbp+57h+var_78]
0x180055b9d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180055ba2  jmp     short loc_180055BC1
0x180055ba4  mov     rcx, r14
0x180055ba7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055bac  mov     r8, r14
0x180055baf  lea     rdx, _GUID_d14b6158_c3fa_4bce_9c1f_b61d8665eab0
0x180055bb6  mov     rcx, [r15]
0x180055bb9  call    cs:__imp_DCompositionCreateDevice2
0x180055bbf  mov     ebx, eax
0x180055bc1  test    ebx, ebx
0x180055bc3  js      short loc_180055C29
0x180055bc5  lea     rbx, [rsi+88h]
0x180055bcc  mov     rcx, rbx
0x180055bcf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055bd4  mov     [rsp+0E0h+pFeatureLevels], rbx; ppv
0x180055bd9  lea     r9, _GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1; riid
0x180055be0  xor     edx, edx; pUnkOuter
0x180055be2  lea     r8d, [rdx+1]; dwClsContext
0x180055be6  lea     rcx, CLSID_UIAnimationManager2; rclsid
0x180055bed  call    cs:__imp_CoCreateInstance
0x180055bf3  mov     ebx, eax
0x180055bf5  test    eax, eax
0x180055bf7  js      short loc_180055C29
0x180055bf9  lea     rbx, [rsi+98h]
0x180055c00  mov     rcx, rbx
0x180055c03  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055c08  mov     [rsp+0E0h+pFeatureLevels], rbx; ppv
0x180055c0d  lea     r9, _GUID_03cfae53_9580_4ee3_b363_2ece51b4af6a; riid
0x180055c14  xor     edx, edx; pUnkOuter
0x180055c16  lea     r8d, [rdx+1]; dwClsContext
0x180055c1a  lea     rcx, CLSID_UIAnimationTransitionLibrary2; rclsid
0x180055c21  call    cs:__imp_CoCreateInstance
0x180055c27  mov     ebx, eax
0x180055c29  mov     rcx, [rbp+57h+ppIFactory]
0x180055c2d  test    rcx, rcx
0x180055c30  jz      short loc_180055C43
0x180055c32  mov     [rbp+57h+ppIFactory], r13
0x180055c36  mov     rax, [rcx]
0x180055c39  mov     rax, [rax+10h]
0x180055c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c42  nop
0x180055c43  mov     rcx, [rbp+57h+var_80]
0x180055c47  test    rcx, rcx
0x180055c4a  jz      short loc_180055C5D
0x180055c4c  mov     [rbp+57h+var_80], r13
0x180055c50  mov     rax, [rcx]
0x180055c53  mov     rax, [rax+10h]
0x180055c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c5c  nop
0x180055c5d  test    ebx, ebx
0x180055c5f  js      loc_180055D36
0x180055c65  lea     r14, [rsi+90h]
0x180055c6c  mov     rcx, r14
0x180055c6f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055c74  mov     [rsp+0E0h+pFeatureLevels], r14; ppv
0x180055c79  lea     r9, _GUID_6b0efad1_a053_41d6_9085_33a689144665; riid
0x180055c80  xor     edx, edx; pUnkOuter
0x180055c82  lea     r8d, [rdx+1]; dwClsContext
0x180055c86  lea     rcx, CLSID_UIAnimationTimer; rclsid
0x180055c8d  call    cs:__imp_CoCreateInstance
0x180055c93  mov     ebx, eax
0x180055c95  test    eax, eax
0x180055c97  js      loc_180055D36
0x180055c9d  mov     [rbp+57h+ppIFactory], r13
0x180055ca1  mov     rdi, [rsi+88h]
0x180055ca8  mov     rax, [rdi]
0x180055cab  mov     rbx, [rax]
0x180055cae  lea     rcx, [rbp+57h+ppIFactory]
0x180055cb2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055cb7  lea     r8, [rbp+57h+ppIFactory]
0x180055cbb  lea     rdx, _GUID_195509b7_5d5e_4e3e_b278_ee3759b367ad
0x180055cc2  mov     rcx, rdi
0x180055cc5  mov     rax, rbx
0x180055cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ccd  mov     ebx, eax
0x180055ccf  test    eax, eax
0x180055cd1  js      short loc_180055D2D
0x180055cd3  mov     rcx, [r14]
0x180055cd6  mov     rax, [rcx]
0x180055cd9  mov     r8d, 1
0x180055cdf  mov     rdx, [rbp+57h+ppIFactory]
0x180055ce3  mov     rax, [rax+18h]
0x180055ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055cec  mov     ebx, eax
0x180055cee  test    eax, eax
0x180055cf0  js      short loc_180055D2D
0x180055cf2  mov     [rbp+57h+var_80], r13
0x180055cf6  lea     rcx, [rbp+57h+var_80]
0x180055cfa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055cff  lea     rcx, [rbp+57h+var_80]
0x180055d03  call    ??$MakeAndInitialize@VCDCompThumbnailTimerEventHandler@@UIUIAnimationTimerEventHandler@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUIAnimationTimerEventHandler@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CDCompThumbnailTimerEventHandler,IUIAnimationTimerEventHandler,>(IUIAnimationTimerEventHandler * *)
0x180055d08  mov     ebx, eax
0x180055d0a  test    eax, eax
0x180055d0c  js      short loc_180055D23
0x180055d0e  mov     rcx, [r14]
0x180055d11  mov     rax, [rcx]
0x180055d14  mov     rdx, [rbp+57h+var_80]
0x180055d18  mov     rax, [rax+20h]
0x180055d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d21  mov     ebx, eax
0x180055d23  lea     rcx, [rbp+57h+var_80]
0x180055d27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055d2c  nop
0x180055d2d  lea     rcx, [rbp+57h+ppIFactory]
0x180055d31  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180055d36  call    Mirror_IsThreadRTL
0x180055d3b  test    eax, eax
0x180055d3d  setnz   al
0x180055d40  mov     [rsi+102h], al
0x180055d46  test    ebx, ebx
0x180055d48  js      short loc_180055DA8
0x180055d4a  mov     rcx, rsi; this
0x180055d4d  call    ?_LoadPVLInfo@CSwitchThumbnailDeviceManager@@AEAAJXZ; CSwitchThumbnailDeviceManager::_LoadPVLInfo(void)
0x180055d52  mov     ebx, eax
0x180055d54  test    eax, eax
0x180055d56  js      short loc_180055DA8
0x180055d58  mov     dword ptr [rbp+57h+pvParam], r13d
0x180055d5c  mov     dword ptr [rbp+57h+ppIFactory], 4
0x180055d63  lea     rax, [rbp+57h+ppIFactory]
0x180055d67  mov     qword ptr [rsp+0E0h+SDKVersion], rax; pcbData
0x180055d6c  lea     rax, [rbp+57h+pvParam]
0x180055d70  mov     qword ptr [rsp+0E0h+FeatureLevels], rax; pvData
  ... truncated ...
```
