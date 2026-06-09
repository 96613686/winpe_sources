# Windows::UI::ViewManagement::AccessibilitySettings::add_HighContrastChanged(Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *> *,EventRegistrationToken *)

- ea: `0x180015400`
- end: `0x1800156fd`
- name: `?add_HighContrastChanged@AccessibilitySettings@ViewManagement@UI@Windows@@UEAAJPEAU?$ITypedEventHandler@PEAVAccessibilitySettings@ViewManagement@UI@Windows@@PEAUIInspectable@@@Foundation@4@PEAUEventRegistrationToken@@@Z`
- size: `765`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180004dd4`
- `0x180014e44`
- `0x1800151a4`
- `0x180015400`
- `0x180015704`
- `0x180015a44`
- `0x180016064`
- `0x180021ee0`
- `0x18004028c`
- `0x180043ae8`
- `0x180044420`
- `0x1800585d0`
- `0x18005f1a4`
- `0x180061740`
- `0x1800a4574`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015695`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015695`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x180015553`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x180015553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800154a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800154a2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800154cb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800154cb`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18001546f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18001546f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::ViewManagement::AccessibilitySettings::add_HighContrastChanged(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v6; // rdx
  HSTRING v7; // rbx
  int ActivationFactory; // ebx
  _QWORD *v9; // rdi
  void (__fastcall *v10)(_QWORD *, __int64 *); // rbx
  __int64 v11; // rdi
  __int64 v13; // rax
  void *v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rbx
  _QWORD *v18; // rcx
  _QWORD *v19; // [rsp+20h] [rbp-60h] BYREF
  __int64 v20; // [rsp+28h] [rbp-58h] BYREF
  _QWORD *v21; // [rsp+30h] [rbp-50h] BYREF
  _QWORD *v22; // [rsp+38h] [rbp-48h] BYREF
  __int128 pvParam; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF

  if ( !(unsigned __int8)IsSystemParametersInfoWPresent() )
    return 2147500033LL;
  if ( Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(
         a1 + 80,
         v6) )
  {
    goto LABEL_34;
  }
  pvParam = 0;
  LODWORD(pvParam) = 16;
  if ( SystemParametersInfoW(0x42u, 0, &pvParam, 0) )
  {
    if ( *((_QWORD *)&pvParam + 1) )
      Windows::Internal::String::_InitializeHelper(
        (Windows::Internal::String *)(a1 + 104),
        *((const unsigned __int16 **)&pvParam + 1));
    *(_BYTE *)(a1 + 112) = BYTE4(pvParam) & 1;
  }
  if ( *(_QWORD *)(a1 + 64) )
    goto LABEL_34;
  v21 = 0;
  if ( WindowsCreateStringReference(L"Windows.UI.Core.CoreWindow", 0x1Au, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = string;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
  ActivationFactory = RoGetActivationFactory(v7, &GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1, &v21);
  if ( ActivationFactory >= 0 )
  {
    v20 = 0;
    v9 = v21;
    v10 = *(void (__fastcall **)(_QWORD *, __int64 *))(*v21 + 48LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v20);
    v10(v9, &v20);
    v11 = 0;
    if ( v20 )
    {
      ActivationFactory = Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow>(
                            &v20,
                            a1 + 64);
      if ( ActivationFactory >= 0 )
      {
        v22 = 0;
        v19 = &v22;
        v13 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v19);
        Microsoft::WRL::AsWeak<Windows::UI::ViewManagement::AccessibilitySettings>(a1, v13);
        v19 = v22;
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v19);
        v14 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        if ( v14 )
          v11 = Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::UI::Core::CoreWindow___Windows::UI::Core::ICoreWindow____Windows::Foundation::Internal::AggregateType_Windows::UI::Core::CoreWindowEventArgs___Windows::UI::Core::ICoreWindowEventArgs_____::___Windows::UI::Core::ICoreWindow___Windows::UI::Core::ICoreWindowEventArgs____::DelegateInvokeHelper_Windows::Foundation::ITypedEventHandler_Windows::UI::Core::CoreWindow___Windows::UI::Core::CoreWindowEventArgs_____lambda_e8c9ecf17d3e450269b49e5f313ecbf2___1_Windows::UI::Core::ICoreWindow___Windows::UI::Core::ICoreWindowEventArgs___::DelegateInvokeHelper_Windows::Foundation::ITypedEventHandler_Windows::UI::Core::CoreWindow___Windows::UI::Core::CoreWindowEventArgs_____lambda_e8c9ecf17d3e450269b49e5f313ecbf2___1_Windows::UI::Core::ICoreWindow___Windows::UI::Core::ICoreWindowEventArgs___(
                  v14,
                  &v19);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v19);
        if ( v11 )
        {
          ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(a1 + 64) + 136LL))(
                                *(_QWORD *)(a1 + 64),
                                v11,
                                a1 + 72);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
        else
        {
          ActivationFactory = -2147024882;
        }
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v22);
      }
    }
    else
    {
      ActivationFactory = -2147023728;
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v20);
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v21);
  if ( ActivationFactory >= 0 )
  {
LABEL_34:
    if ( (unsigned int)QuirkIsEnabled(589842) )
    {
      v21 = a2;
      Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::UISettings *,IInspectable *>>::InternalAddRef(&v21);
      v22 = a2;
      Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::UISettings *,IInspectable *>>::InternalAddRef(&v22);
      v15 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::UI::ViewManagement::AccessibilitySettings___Windows::UI::ViewManagement::IAccessibilitySettings____IInspectable___::___Windows::UI::ViewManagement::IAccessibilitySettings___IInspectable____::DelegateInvokeHelper_Windows::Foundation::ITypedEventHandler_Windows::UI::ViewManagement::AccessibilitySettings___IInspectable_____lambda_f8bd2f9a7a48da5ae4835c80e5a7ff7c___1_Windows::UI::ViewManagement::IAccessibilitySettings___IInspectable_____lambda_f8bd2f9a7a48da5ae4835c80e5a7ff7c___(
                         &v19,
                         &v22);
      v17 = *v15;
      v20 = *v15;
      *v15 = 0;
      v18 = v19;
      if ( v19 )
      {
        v19 = 0;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler>::Release(
          v18,
          v16);
      }
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v22);
      if ( v17 )
        ActivationFactory = Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(
                              a1 + 80,
                              v17,
                              a3);
      else
        ActivationFactory = -2147024882;
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v20);
      Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(&v21);
    }
    else
    {
      return (unsigned int)Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(
                             a1 + 80,
                             a2,
                             a3);
    }
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180015400  mov     [rsp-38h+arg_18], rbx
0x180015405  push    rbp
0x180015406  push    rsi
0x180015407  push    rdi
0x180015408  push    r12
0x18001540a  push    r13
0x18001540c  push    r14
0x18001540e  push    r15
0x180015410  mov     rbp, rsp
0x180015413  sub     rsp, 80h
0x18001541a  mov     rax, cs:__security_cookie
0x180015421  xor     rax, rsp
0x180015424  mov     [rbp+var_10], rax
0x180015428  mov     r13, r8
0x18001542b  mov     r12, rdx
0x18001542e  mov     rsi, rcx
0x180015431  call    IsSystemParametersInfoWPresent
0x180015436  xor     edi, edi
0x180015438  test    al, al
0x18001543a  jz      loc_180015652
0x180015440  lea     r15, [rsi+50h]
0x180015444  mov     rcx, r15
0x180015447  call    ?GetSize@?$EventSource@U?$ITypedEventHandler@PEAVAccessibilitySettings@ViewManagement@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEBA_KXZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(void)
0x18001544c  test    rax, rax
0x18001544f  jnz     loc_18001554E
0x180015455  xorps   xmm0, xmm0
0x180015458  movups  [rbp+pvParam], xmm0
0x18001545c  mov     dword ptr [rbp+pvParam], 10h
0x180015463  xor     r9d, r9d; fWinIni
0x180015466  lea     r8, [rbp+pvParam]; pvParam
0x18001546a  xor     edx, edx; uiParam
0x18001546c  lea     ecx, [rdi+42h]; uiAction
0x18001546f  call    cs:__imp_SystemParametersInfoW
0x180015475  test    eax, eax
0x180015477  jnz     loc_180015573
0x18001547d  lea     r14, [rsi+40h]
0x180015481  cmp     [r14], rdi
0x180015484  jnz     loc_18001554E
0x18001548a  mov     [rbp+var_50], rdi
0x18001548e  lea     r9, [rbp+string]; string
0x180015492  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180015496  mov     edx, 1Ah; length
0x18001549b  lea     rcx, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x1800154a2  call    cs:__imp_WindowsCreateStringReference
0x1800154a8  test    eax, eax
0x1800154aa  js      loc_180015686
0x1800154b0  mov     rbx, [rbp+string]
0x1800154b4  lea     rcx, [rbp+var_50]
0x1800154b8  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800154bd  lea     r8, [rbp+var_50]
0x1800154c1  lea     rdx, _GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1
0x1800154c8  mov     rcx, rbx
0x1800154cb  call    cs:__imp_RoGetActivationFactory
0x1800154d1  mov     ebx, eax
0x1800154d3  test    eax, eax
0x1800154d5  js      short loc_180015518
0x1800154d7  mov     [rbp+var_58], rdi
0x1800154db  mov     rdi, [rbp+var_50]
0x1800154df  mov     rax, [rdi]
0x1800154e2  mov     rbx, [rax+30h]
0x1800154e6  lea     rcx, [rbp+var_58]
0x1800154ea  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800154ef  lea     rdx, [rbp+var_58]
0x1800154f3  mov     rcx, rdi
0x1800154f6  mov     rax, rbx
0x1800154f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154fe  xor     edi, edi
0x180015500  cmp     [rbp+var_58], rdi
0x180015504  jnz     loc_180015592
0x18001550a  mov     ebx, 80070490h
0x18001550f  lea     rcx, [rbp+var_58]
0x180015513  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180015518  lea     rcx, [rbp+var_50]
0x18001551c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180015521  test    ebx, ebx
0x180015523  jns     short loc_18001554E
0x180015525  mov     eax, ebx
0x180015527  mov     rcx, [rbp+var_10]
0x18001552b  xor     rcx, rsp; StackCookie
0x18001552e  call    __security_check_cookie
0x180015533  mov     rbx, [rsp+80h+arg_18]
0x18001553b  add     rsp, 80h
0x180015542  pop     r15
0x180015544  pop     r14
0x180015546  pop     r13
0x180015548  pop     r12
0x18001554a  pop     rdi
0x18001554b  pop     rsi
0x18001554c  pop     rbp
0x18001554d  retn
0x18001554e  mov     ecx, 90012h
0x180015553  call    cs:__imp_QuirkIsEnabled
0x180015559  test    eax, eax
0x18001555b  jnz     loc_1800156A0
0x180015561  mov     r8, r13
0x180015564  mov     rdx, r12
0x180015567  mov     rcx, r15
0x18001556a  call    ?Add@?$AgileEventSource@U?$ITypedEventHandler@PEAVAccessibilitySettings@ViewManagement@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAU?$ITypedEventHandler@PEAVAccessibilitySettings@ViewManagement@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z; Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *> *,EventRegistrationToken *)
0x18001556f  mov     ebx, eax
0x180015571  jmp     short loc_180015525
0x180015573  mov     rdx, qword ptr [rbp+pvParam+8]; unsigned __int16 *
0x180015577  test    rdx, rdx
0x18001557a  jz      short loc_180015585
0x18001557c  lea     rcx, [rsi+68h]; this
0x180015580  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180015585  mov     eax, dword ptr [rbp+pvParam+4]
0x180015588  and     al, 1
0x18001558a  mov     [rsi+70h], al
0x18001558d  jmp     loc_18001547D
0x180015592  mov     rdx, r14
0x180015595  lea     rcx, [rbp+var_58]
0x180015599  call    ??$As@UIInternalCoreWindow@Core@UI@Windows@@@?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInternalCoreWindow@Core@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::IInternalCoreWindow>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoreWindow>>)
0x18001559e  mov     ebx, eax
0x1800155a0  test    eax, eax
0x1800155a2  js      loc_18001550F
0x1800155a8  mov     [rbp+var_48], rdi
0x1800155ac  lea     rax, [rbp+var_48]
0x1800155b0  mov     [rbp+var_60], rax
0x1800155b4  lea     rcx, [rbp+var_60]
0x1800155b8  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x1800155bd  mov     rdx, rax
0x1800155c0  mov     rcx, rsi
0x1800155c3  call    ??$AsWeak@VAccessibilitySettings@ViewManagement@UI@Windows@@@WRL@Microsoft@@YAJPEAVAccessibilitySettings@ViewManagement@UI@Windows@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<Windows::UI::ViewManagement::AccessibilitySettings>(Windows::UI::ViewManagement::AccessibilitySettings *,Microsoft::WRL::WeakRef *)
0x1800155c8  nop
0x1800155c9  mov     rax, [rbp+var_48]
0x1800155cd  mov     [rbp+var_60], rax
0x1800155d1  lea     rcx, [rbp+var_60]
0x1800155d5  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800155da  nop
0x1800155db  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800155e2  mov     ecx, 18h; unsigned __int64
0x1800155e7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800155ec  test    rax, rax
0x1800155ef  jz      short loc_180015600
0x1800155f1  lea     rdx, [rbp+var_60]
0x1800155f5  mov     rcx, rax
0x1800155f8  call    Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__UI__Core__CoreWindow___Windows__UI__Core__ICoreWindow____Windows__Foundation__Internal__AggregateType_Windows__UI__Core__CoreWindowEventArgs___Windows__UI__Core__ICoreWindowEventArgs__________Windows__UI__Core__ICoreWindow___Windows__UI__Core__ICoreWindowEventArgs______DelegateInvokeHelper_Windows__Foundation__ITypedEventHandler_Windows__UI__Core__CoreWindow___Windows__UI__Core__CoreWindowEventArgs_____lambda_e8c9ecf17d3e450269b49e5f313ecbf2___1_Windows__UI__Core__ICoreWindow___Windows__UI__Core__ICoreWindowEventArgs_____DelegateInvokeHelper_Windows__Foundation__ITypedEventHandler_Windows__UI__Core__CoreWindow___Windows__UI__Core__CoreWindowEventArgs_____lambda_e8c9ecf17d3e450269b49e5f313ecbf2___1_Windows__UI__Core__ICoreWindow___Windows__UI__Core__ICoreWindowEventArgs___
0x1800155fd  mov     rdi, rax
0x180015600  lea     rcx, [rbp+var_60]
0x180015604  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180015609  nop
0x18001560a  test    rdi, rdi
0x18001560d  jz      short loc_18001564B
0x18001560f  mov     rcx, [r14]
0x180015612  mov     rax, [rcx]
0x180015615  lea     r8, [rsi+48h]
0x180015619  mov     rdx, rdi
0x18001561c  mov     rax, [rax+88h]
0x180015623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015628  mov     ebx, eax
0x18001562a  mov     rax, [rdi]
0x18001562d  mov     rcx, rdi
0x180015630  mov     rax, [rax+10h]
0x180015634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015639  nop
0x18001563a  lea     rcx, [rbp+var_48]
0x18001563e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180015643  nop
0x180015644  xor     edi, edi
0x180015646  jmp     loc_18001550F
0x18001564b  mov     ebx, 8007000Eh
0x180015650  jmp     short loc_18001563A
0x180015652  mov     eax, 80004001h
0x180015657  jmp     loc_180015527
0x18001565c  lea     rcx, [rbp+var_48]
0x180015660  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x180015665  test    rbx, rbx
0x180015668  jnz     short loc_1800156E8
0x18001566a  mov     ebx, 8007000Eh
0x18001566f  lea     rcx, [rbp+var_58]
0x180015673  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x180015678  lea     rcx, [rbp+var_50]
0x18001567c  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x180015681  jmp     loc_180015525
0x180015686  xor     r9d, r9d; lpArguments
0x180015689  xor     r8d, r8d; nNumberOfArguments
0x18001568c  lea     edx, [r9+1]; dwExceptionFlags
0x180015690  mov     ecx, 0C000000Dh; dwExceptionCode
0x180015695  call    cs:__imp_RaiseException
0x18001569b  jmp     loc_1800154B0
0x1800156a0  mov     [rbp+var_50], r12
0x1800156a4  lea     rcx, [rbp+var_50]
0x1800156a8  call    ?InternalAddRef@?$ComPtr@U?$ITypedEventHandler@PEAVUISettings@ViewManagement@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::UISettings *,IInspectable *>>::InternalAddRef(void)
0x1800156ad  mov     [rbp+var_48], r12
0x1800156b1  lea     rcx, [rbp+var_48]
0x1800156b5  call    ?InternalAddRef@?$ComPtr@U?$ITypedEventHandler@PEAVUISettings@ViewManagement@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::UISettings *,IInspectable *>>::InternalAddRef(void)
0x1800156ba  lea     rdx, [rbp+var_48]
0x1800156be  lea     rcx, [rbp+var_60]
0x1800156c2  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__UI__ViewManagement__AccessibilitySettings___Windows__UI__ViewManagement__IAccessibilitySettings____IInspectable________Windows__UI__ViewManagement__IAccessibilitySettings___IInspectable______DelegateInvokeHelper_Windows__Foundation__ITypedEventHandler_Windows__UI__ViewManagement__AccessibilitySettings___IInspectable_____lambda_f8bd2f9a7a48da5ae4835c80e5a7ff7c___1_Windows__UI__ViewManagement__IAccessibilitySettings___IInspectable_____lambda_f8bd2f9a7a48da5ae4835c80e5a7ff7c___
0x1800156c7  mov     rbx, [rax]
0x1800156ca  mov     [rbp+var_58], rbx
0x1800156ce  mov     [rax], rdi
0x1800156d1  mov     rcx, [rbp+var_60]
0x1800156d5  test    rcx, rcx
0x1800156d8  jz      short loc_18001565C
0x1800156da  mov     [rbp+var_60], rdi
0x1800156de  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncActionCompletedHandler@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler>::Release(void)
0x1800156e3  jmp     loc_18001565C
0x1800156e8  mov     r8, r13
0x1800156eb  mov     rdx, rbx
0x1800156ee  mov     rcx, r15
0x1800156f1  call    ?Add@?$AgileEventSource@U?$ITypedEventHandler@PEAVAccessibilitySettings@ViewManagement@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAU?$ITypedEventHandler@PEAVAccessibilitySettings@ViewManagement@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z; Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(Windows::Foundation::ITypedEventHandler<Windows::UI::ViewManagement::AccessibilitySettings *,IInspectable *> *,EventRegistrationToken *)
0x1800156f6  mov     ebx, eax
0x1800156f8  jmp     loc_18001566F
```
