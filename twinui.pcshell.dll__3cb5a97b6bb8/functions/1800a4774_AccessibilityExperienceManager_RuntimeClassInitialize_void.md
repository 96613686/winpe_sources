# AccessibilityExperienceManager::RuntimeClassInitialize(void)

- ea: `0x1800a4774`
- end: `0x1800a4cad`
- name: `?RuntimeClassInitialize@AccessibilityExperienceManager@@QEAAJXZ`
- size: `1337`
- prototype: `__int64 __fastcall(AccessibilityExperienceManager *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18014cb84`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180024b80`
- `0x180043f00`
- `0x1800a4774`
- `0x1800a5838`
- `0x1800a5c94`
- `0x1800d5610`
- `0x1800d7ecc`
- `0x1800d7f24`
- `0x180195820`
- `0x1801c9a58`
- `0x1801fd8cc`
- `0x1802d71c8`
- `0x1802dd470`
- `0x180356360`
- `0x180356384`
- `0x180356edc`
- `0x180366f6c`
- `0x1804d338c`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4c49`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a4c49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a4954`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a4954`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800a4ab0`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800a4ab0`
- `ntdll!NtQueryWnfStateData` at `0x1806f096e`
- `ntdll!NtQueryWnfStateData` at `0x1806f096e`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800a4888`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800a4888`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a497f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800a497f`
- `USER32!RegisterClassExW` at `0x1800a47d9`
- `USER32!RegisterClassExW` at `0x1800a47d9`
- `USER32!CreateWindowExW` at `0x1800a481d`
- `USER32!CreateWindowExW` at `0x1800a481d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x1800a4835`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x1800a4835`

## string_xrefs

- `0x1800a47ca`: `AccessibilityEMWndClass`
- `0x1800a4811`: `AccessibilityEMWnd`
- `0x1800a48c2`: `pcshell\twinui\accessibilityexperiencemanager\lib\accessibilityexperiencemanager.cpp`
- `0x1800a4b73`: `pcshell\twinui\accessibilityexperiencemanager\lib\accessibilityexperiencemanager.cpp`
- `0x1806f0930`: `pcshell\twinui\accessibilityexperiencemanager\lib\accessibilityexperiencemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AccessibilityExperienceManager::RuntimeClassInitialize(AccessibilityExperienceManager *this)
{
  HWND Window; // rax
  char *v3; // r14
  __int64 v4; // rax
  unsigned int AgileReference; // ebx
  int v6; // eax
  int v8; // eax
  HRESULT v9; // eax
  HSTRING v10; // rbx
  int ActivationFactory; // eax
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, char *, char *); // rdi
  int v14; // eax
  __int64 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  std::_Ref_count_base *v18; // rcx
  WnfHelper *v19; // rcx
  __int64 v20; // rax
  wil::details *v21; // rsi
  void *v22; // rax
  wil::details *v23; // rdi
  __int64 v24; // r8
  int v25; // ebx
  int v26; // ebx
  struct wil::details::wnf_subscription_state_base *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r9
  __int64 v30; // rdx
  unsigned __int64 v31; // r9
  __int64 v32; // rdx
  int X; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v36; // [rsp+70h] [rbp-90h] BYREF
  wil::details *v37; // [rsp+78h] [rbp-88h] BYREF
  char v38[8]; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v39; // [rsp+88h] [rbp-78h]
  char *v40; // [rsp+90h] [rbp-70h] BYREF
  WNDCLASSEXW v41; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING string; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v44[112]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v45; // [rsp+180h] [rbp+80h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  memset_0(&v41, 0, sizeof(v41));
  v41.cbSize = 80;
  v41.lpfnWndProc = (WNDPROC)_AccessibilityEMWndProc;
  v41.lpszClassName = L"AccessibilityEMWndClass";
  RegisterClassExW(&v41);
  Window = CreateWindowExW(0, L"AccessibilityEMWndClass", L"AccessibilityEMWnd", 0, 0, 0, 0, 0, HWND_MESSAGE, 0, 0, 0);
  *((_QWORD *)this + 53) = Window;
  SetWindowLongPtrW(Window, -21, (LONG_PTR)this);
  qword_1808DA1A8 = (__int64)"M\x00i\x00c\x00r\x00o\x00s\x00o\x00f\x00t\x00.\x00E\x00C\x00A\x00p\x00p\x00_\x008\x00w\x00e\x00k\x00y\x00b\x003\x00d\x008\x00b\x00b\x00w\x00e\x00!\x00A\x00p\x00p";
  v3 = (char *)this + 144;
  v40 = (char *)this + 144;
  if ( this != (AccessibilityExperienceManager *)-144LL )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 144);
  v4 = 0;
  v35 = 0;
  AgileReference = 0;
  if ( this != (AccessibilityExperienceManager *)-144LL )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    AgileReference = RoGetAgileReference(0, &GUID_5e575f11_41b8_4e5f_a100_ceaab370f70c, (char *)this + 144, &v35);
    v4 = v35;
  }
  v35 = v4;
  if ( (AgileReference & 0x80000000) != 0 )
  {
    v31 = AgileReference;
    v32 = 103;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"pcshell\\twinui\\accessibilityexperiencemanager\\lib\\accessibilityexperiencemanager.cpp",
      (const char *)v31,
      X);
    goto LABEL_41;
  }
  v6 = CImmersiveShellComponent::RegisterServiceInformation(
         (AccessibilityExperienceManager *)((char *)this + 48),
         (const struct _GUID *)&SID_AccessibilityExperienceManager);
  AgileReference = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"pcshell\\twinui\\accessibilityexperiencemanager\\lib\\accessibilityexperiencemanager.cpp",
      (const char *)(unsigned int)v6,
      X);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    if ( this != (AccessibilityExperienceManager *)-144LL )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))((char *)this + 144);
    return AgileReference;
  }
  v8 = Microsoft::WRL::Details::MakeAndInitialize<CreationThreadDispatcher,CreationThreadDispatcher,>((char *)this + 288);
  AgileReference = v8;
  if ( v8 < 0 )
  {
    v31 = (unsigned int)v8;
    v32 = 107;
    goto LABEL_50;
  }
  v34 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.UI.Internal.Input.EyeControlApp", 0x27u, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    RaiseException(v9, 1u, 0, 0);
    __debugbreak();
  }
  v10 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  ActivationFactory = RoGetActivationFactory(v10, &GUID_fc3ec75f_fb9f_4147_93fc_59b58dbf65be, &v34);
  AgileReference = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v29 = (unsigned int)ActivationFactory;
    v30 = 110;
    goto LABEL_40;
  }
  v12 = v34;
  v13 = *(__int64 (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v34 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 408);
  v14 = v13(v12, (char *)this + 144, (char *)this + 408);
  AgileReference = v14;
  if ( v14 < 0 )
  {
    v29 = (unsigned int)v14;
    v30 = 111;
    goto LABEL_40;
  }
  v15 = (__int64 *)std::make_shared<WnfHelper,>(v38);
  v16 = *v15;
  v17 = v15[1];
  *v15 = 0;
  v15[1] = 0;
  *((_QWORD *)this + 37) = v16;
  v18 = (std::_Ref_count_base *)*((_QWORD *)this + 38);
  *((_QWORD *)this + 38) = v17;
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( v39 )
    std::_Ref_count_base::_Decref(v39);
  v19 = (WnfHelper *)*((_QWORD *)this + 37);
  if ( v19 )
    WnfHelper::Subscribe(
      v19,
      (struct IWnfCallback *)(((unsigned __int64)this + 136)
                            & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
  v20 = lambda_383a1ad20d5032ad96979058c699feb6_::_lambda_383a1ad20d5032ad96979058c699feb6_(v38, &v35);
  wistd::function_void___cdecl_unsigned_long_const____::function_void___cdecl_unsigned_long_const______lambda_383a1ad20d5032ad96979058c699feb6__void_(
    v44,
    v20);
  v36 = 0;
  v21 = 0;
  v22 = operator new(0x88u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v22
    || (v23 = (wil::details *)wil::details::wnf_subscription_state<unsigned long>::wnf_subscription_state<unsigned long>(
                                v22,
                                v44)) == 0 )
  {
    v26 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
      (const char *)0x8007000ELL,
      X);
    goto LABEL_27;
  }
  v24 = v36;
  if ( v36 != -1 )
    goto LABEL_23;
  LODWORD(v37) = 0;
  v26 = NtQueryWnfStateData(&WNF_SHEL_LOCKSCREEN_ACTIVE, 0, 0, &v36) | 0x10000000;
  if ( (int)(v26 + 0x80000000) < 0 || v26 == -805306333 )
  {
    v24 = v36;
LABEL_23:
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)v23 + 8;
    hstringHeader.Reserved.Reserved2[16] = 1;
    X = (int)v23;
    v25 = RtlSubscribeWnfStateChangeNotification(
            &hstringHeader.Reserved.Reserved2[8],
            WNF_SHEL_LOCKSCREEN_ACTIVE,
            v24,
            _lambda_a14e49ce427a1853f087bba834558a2c_::_lambda_invoker_cdecl_);
    if ( hstringHeader.Reserved.Reserved2[16] )
      wil::details::unique_storage<wil::details::resource_policy<_WNF_USER_SUBSCRIPTION *,long (*)(_WNF_USER_SUBSCRIPTION *),&long RtlUnsubscribeWnfStateChangeNotification(_WNF_USER_SUBSCRIPTION *),wistd::integral_constant<unsigned __int64,0>,_WNF_USER_SUBSCRIPTION *,_WNF_USER_SUBSCRIPTION *,0,std::nullptr_t>>::reset(
        hstringHeader.Reserved.Reserved1,
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8]);
    if ( v25 >= 0 )
    {
      v21 = v23;
      v26 = 0;
      goto LABEL_27;
    }
    v26 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x3C7,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
            (const char *)(unsigned int)v25,
            (int)v23);
    goto LABEL_44;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3B8,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil/resource.h",
    (const char *)(unsigned int)v26,
    0);
LABEL_44:
  (**(void (__fastcall ***)(wil::details *, __int64))v23)(v23, 1);
LABEL_27:
  if ( v26 < 0 )
    v21 = 0;
  v37 = v21;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    (char *)this + 312,
    &v37);
  if ( v37 )
    wil::details::delete_wnf_subscription_state(v37, v27);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 24LL))(v45);
  if ( !*((_QWORD *)this + 39) )
  {
    AgileReference = -2147467259;
    v29 = 2147500037LL;
    v30 = 130;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"pcshell\\twinui\\accessibilityexperiencemanager\\lib\\accessibilityexperiencemanager.cpp",
      (const char *)v29,
      X);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
LABEL_41:
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(&v35);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    return AgileReference;
  }
  AccessibilityExperienceManager::EnsureInputDeviceWatcher(this);
  v28 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  if ( this != (AccessibilityExperienceManager *)-144LL )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))((char *)this + 144);
  return 0;
}

```

## disassembly

```asm
0x1800a4774  mov     [rsp-8+arg_8], rbx
0x1800a4779  mov     [rsp-8+arg_10], rsi
0x1800a477e  push    rbp
0x1800a477f  push    rdi
0x1800a4780  push    r12
0x1800a4782  push    r14
0x1800a4784  push    r15
0x1800a4786  lea     rbp, [rsp-90h]
0x1800a478e  sub     rsp, 190h
0x1800a4795  mov     rax, cs:__security_cookie
0x1800a479c  xor     rax, rsp
0x1800a479f  mov     [rbp+0B0h+var_28], rax
0x1800a47a6  mov     r15, rcx
0x1800a47a9  mov     ebx, 50h ; 'P'
0x1800a47ae  mov     r8d, ebx; Size
0x1800a47b1  xor     edx, edx; Val
0x1800a47b3  lea     rcx, [rbp+0B0h+var_110]; void *
0x1800a47b7  call    memset_0
0x1800a47bc  mov     [rbp+0B0h+var_110.cbSize], ebx
0x1800a47bf  lea     rax, ?_AccessibilityEMWndProc@@YA_JPEAUHWND__@@I_K_J@Z; _AccessibilityEMWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800a47c6  mov     [rbp+0B0h+var_110.lpfnWndProc], rax
0x1800a47ca  lea     rbx, aAccessibilitye_0; "AccessibilityEMWndClass"
0x1800a47d1  mov     [rbp+0B0h+var_110.lpszClassName], rbx
0x1800a47d5  lea     rcx, [rbp+0B0h+var_110]; WNDCLASSEXW *
0x1800a47d9  call    cs:__imp_RegisterClassExW
0x1800a47df  xor     r12d, r12d
0x1800a47e2  mov     [rsp+1B0h+lpParam], r12; lpParam
0x1800a47e7  mov     [rsp+1B0h+hInstance], r12; hInstance
0x1800a47ec  mov     [rsp+1B0h+hMenu], r12; hMenu
0x1800a47f1  mov     [rsp+1B0h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x1800a47fa  mov     [rsp+1B0h+nHeight], r12d; nHeight
0x1800a47ff  mov     [rsp+1B0h+nWidth], r12d; nWidth
0x1800a4804  mov     [rsp+1B0h+Y], r12d; Y
0x1800a4809  mov     [rsp+1B0h+X], r12d; int
0x1800a480e  xor     r9d, r9d; dwStyle
0x1800a4811  lea     r8, WindowName; "AccessibilityEMWnd"
0x1800a4818  mov     rdx, rbx; lpClassName
0x1800a481b  xor     ecx, ecx; dwExStyle
0x1800a481d  call    cs:__imp_CreateWindowExW
0x1800a4823  mov     [r15+1A8h], rax
0x1800a482a  mov     r8, r15; dwNewLong
0x1800a482d  lea     edx, [r12-15h]; nIndex
0x1800a4832  mov     rcx, rax; hWnd
0x1800a4835  call    cs:__imp_SetWindowLongPtrW
0x1800a483b  lea     rax, aT6microsoftEca+4; "M\x00i\x00c\x00r\x00o\x00s\x00o\x00f"...
0x1800a4842  mov     cs:qword_1808DA1A8, rax
0x1800a4849  lea     r14, [r15+90h]
0x1800a4850  mov     [rbp+0B0h+var_120], r14
0x1800a4854  test    r14, r14
0x1800a4857  jnz     loc_1800A4C0F
0x1800a485d  mov     rax, r12
0x1800a4860  mov     [rsp+1B0h+var_148], rax
0x1800a4865  mov     ebx, r12d
0x1800a4868  test    r14, r14
0x1800a486b  jz      short loc_1800A4895
0x1800a486d  lea     rcx, [rsp+1B0h+var_148]
0x1800a4872  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4877  lea     r9, [rsp+1B0h+var_148]
0x1800a487c  mov     r8, r14
0x1800a487f  lea     rdx, _GUID_5e575f11_41b8_4e5f_a100_ceaab370f70c
0x1800a4886  xor     ecx, ecx
0x1800a4888  call    cs:__imp_RoGetAgileReference
0x1800a488e  mov     ebx, eax
0x1800a4890  mov     rax, [rsp+1B0h+var_148]
0x1800a4895  mov     [rsp+1B0h+var_148], rax
0x1800a489a  test    ebx, ebx
0x1800a489c  js      loc_1800A4C23
0x1800a48a2  lea     rcx, [r15+30h]; this
0x1800a48a6  lea     rdx, SID_AccessibilityExperienceManager; struct _GUID *
0x1800a48ad  call    ?RegisterServiceInformation@CImmersiveShellComponent@@QEAAJAEBU_GUID@@@Z; CImmersiveShellComponent::RegisterServiceInformation(_GUID const &)
0x1800a48b2  mov     ebx, eax
0x1800a48b4  test    eax, eax
0x1800a48b6  jns     short loc_1800A4921
0x1800a48b8  mov     rcx, [rbp+0B8h]; this
0x1800a48bf  mov     r9d, eax; char *
0x1800a48c2  lea     r8, aPcshellTwinuiA_11; "pcshell\\twinui\\accessibilityexperienc"...
0x1800a48c9  mov     edx, 69h ; 'i'; void *
0x1800a48ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a48d3  nop
0x1800a48d4  lea     rcx, [rsp+1B0h+var_148]
0x1800a48d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a48de  nop
0x1800a48df  test    r14, r14
0x1800a48e2  jz      short loc_1800A48F4
0x1800a48e4  mov     rax, [r14]
0x1800a48e7  mov     rcx, r14
0x1800a48ea  mov     rax, [rax+10h]
0x1800a48ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a48f3  nop
0x1800a48f4  mov     eax, ebx
0x1800a48f6  mov     rcx, [rbp+0B0h+var_28]
0x1800a48fd  xor     rcx, rsp; StackCookie
0x1800a4900  call    __security_check_cookie
0x1800a4905  lea     r11, [rsp+1B0h+var_20]
0x1800a490d  mov     rbx, [r11+38h]
0x1800a4911  mov     rsi, [r11+40h]
0x1800a4915  mov     rsp, r11
0x1800a4918  pop     r15
0x1800a491a  pop     r14
0x1800a491c  pop     r12
0x1800a491e  pop     rdi
0x1800a491f  pop     rbp
0x1800a4920  retn
0x1800a4921  lea     rcx, [r15+120h]
0x1800a4928  call    ??$MakeAndInitialize@VCreationThreadDispatcher@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCreationThreadDispatcher@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CreationThreadDispatcher,CreationThreadDispatcher,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CreationThreadDispatcher>>)
0x1800a492d  mov     ebx, eax
0x1800a492f  test    eax, eax
0x1800a4931  js      loc_1800A4C30
0x1800a4937  mov     [rsp+1B0h+var_150], r12
0x1800a493c  mov     [rbp+0B0h+string], r12
0x1800a4940  lea     r9, [rbp+0B0h+string]; string
0x1800a4944  lea     r8, [rbp+0B0h+hstringHeader]; hstringHeader
0x1800a4948  mov     edx, 27h ; '''; length
0x1800a494d  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Input_EyeControlApp@@3QBGB; "Windows.UI.Internal.Input.EyeControlApp"
0x1800a4954  call    cs:__imp_WindowsCreateStringReference
0x1800a495a  test    eax, eax
0x1800a495c  js      loc_1800A4C3D
0x1800a4962  mov     rbx, [rbp+0B0h+string]
0x1800a4966  lea     rcx, [rsp+1B0h+var_150]
0x1800a496b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4970  lea     r8, [rsp+1B0h+var_150]
0x1800a4975  lea     rdx, _GUID_fc3ec75f_fb9f_4147_93fc_59b58dbf65be
0x1800a497c  mov     rcx, rbx
0x1800a497f  call    cs:__imp_RoGetActivationFactory
0x1800a4985  mov     ebx, eax
0x1800a4987  test    eax, eax
0x1800a4989  js      loc_1800A4C50
0x1800a498f  mov     rsi, [rsp+1B0h+var_150]
0x1800a4994  mov     rax, [rsi]
0x1800a4997  mov     rdi, [rax+30h]
0x1800a499b  lea     rbx, [r15+198h]
0x1800a49a2  mov     rcx, rbx
0x1800a49a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a49aa  mov     r8, rbx
0x1800a49ad  mov     rdx, r14
0x1800a49b0  mov     rcx, rsi
0x1800a49b3  mov     rax, rdi
0x1800a49b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a49bb  mov     ebx, eax
0x1800a49bd  test    eax, eax
0x1800a49bf  js      loc_1800A4C5D
0x1800a49c5  lea     rcx, [rbp+0B0h+var_130]
0x1800a49c9  call    ??$make_shared@VWnfHelper@@$$V@std@@YA?AV?$shared_ptr@VWnfHelper@@@0@XZ; std::make_shared<WnfHelper,>(void)
0x1800a49ce  mov     rcx, [rax]
0x1800a49d1  mov     rdx, [rax+8]
0x1800a49d5  mov     [rax], r12
0x1800a49d8  mov     [rax+8], r12
0x1800a49dc  mov     [r15+128h], rcx
0x1800a49e3  mov     rcx, [r15+130h]; this
0x1800a49ea  mov     [r15+130h], rdx
0x1800a49f1  test    rcx, rcx
0x1800a49f4  jnz     loc_1800A4C6A
0x1800a49fa  mov     rcx, [rbp+0B0h+var_128]; this
0x1800a49fe  test    rcx, rcx
0x1800a4a01  jnz     loc_1800A4C74
0x1800a4a07  mov     rcx, [r15+128h]; this
0x1800a4a0e  test    rcx, rcx
0x1800a4a11  jnz     loc_1800A4C7E
0x1800a4a17  lea     rdx, [rsp+1B0h+var_148]
0x1800a4a1c  lea     rcx, [rbp+0B0h+var_130]
0x1800a4a20  call    _lambda_383a1ad20d5032ad96979058c699feb6____lambda_383a1ad20d5032ad96979058c699feb6_
0x1800a4a25  mov     rdx, rax
0x1800a4a28  lea     rcx, [rbp+0B0h+var_A0]
0x1800a4a2c  call    wistd__function_void___cdecl_unsigned_long_const______function_void___cdecl_unsigned_long_const______lambda_383a1ad20d5032ad96979058c699feb6__void_
0x1800a4a31  mov     [rsp+1B0h+var_140], r12d
0x1800a4a36  mov     rsi, r12
0x1800a4a39  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a4a40  mov     ecx, 88h; unsigned __int64
0x1800a4a45  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a4a4a  test    rax, rax
0x1800a4a4d  jz      loc_1800A4BAB
0x1800a4a53  lea     rdx, [rbp+0B0h+var_A0]
0x1800a4a57  mov     rcx, rax
0x1800a4a5a  call    ??0?$wnf_subscription_state@K@details@wil@@QEAA@$$QEAV?$function@$$A6AXAEBK@Z@wistd@@@Z; wil::details::wnf_subscription_state<ulong>::wnf_subscription_state<ulong>(wistd::function<void (ulong const &)> &&)
0x1800a4a5f  mov     rdi, rax
0x1800a4a62  test    rax, rax
0x1800a4a65  jz      loc_1800A4BAB
0x1800a4a6b  mov     r8d, [rsp+1B0h+var_140]
0x1800a4a70  cmp     r8d, 0FFFFFFFFh
0x1800a4a74  jz      loc_1806F0949
0x1800a4a7a  lea     rax, [rdi+8]
0x1800a4a7e  mov     qword ptr [rbp+0B0h+hstringHeader.Reserved], rax
0x1800a4a82  mov     qword ptr [rbp+0B0h+hstringHeader.Reserved+8], r12
0x1800a4a86  mov     byte ptr [rbp+0B0h+hstringHeader.Reserved+10h], 1
0x1800a4a8a  mov     [rsp+1B0h+nHeight], r12d
0x1800a4a8f  mov     [rsp+1B0h+nWidth], r12d
0x1800a4a94  mov     qword ptr [rsp+1B0h+Y], r12
0x1800a4a99  mov     qword ptr [rsp+1B0h+X], rdi; int
0x1800a4a9e  lea     r9, ?_lambda_invoker_cdecl_@_lambda_a14e49ce427a1853f087bba834558a2c_@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; _lambda_a14e49ce427a1853f087bba834558a2c_::_lambda_invoker_cdecl_(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800a4aa5  mov     rdx, cs:WNF_SHEL_LOCKSCREEN_ACTIVE
0x1800a4aac  lea     rcx, [rbp+0B0h+hstringHeader.Reserved+8]
0x1800a4ab0  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800a4ab6  mov     ebx, eax
0x1800a4ab8  cmp     byte ptr [rbp+0B0h+hstringHeader.Reserved+10h], r12b
0x1800a4abc  jnz     loc_1800A4C9B
0x1800a4ac2  test    ebx, ebx
0x1800a4ac4  js      loc_1800A4BD0
0x1800a4aca  mov     rsi, rdi
0x1800a4acd  mov     ebx, r12d
0x1800a4ad0  test    ebx, ebx
0x1800a4ad2  cmovs   rsi, r12
0x1800a4ad6  mov     [rsp+1B0h+var_138], rsi
0x1800a4adb  lea     rbx, [r15+138h]
0x1800a4ae2  lea     rdx, [rsp+1B0h+var_138]
0x1800a4ae7  mov     rcx, rbx
0x1800a4aea  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x1800a4aef  mov     rcx, [rsp+1B0h+var_138]; this
0x1800a4af4  test    rcx, rcx
0x1800a4af7  jnz     loc_1800A4C05
0x1800a4afd  mov     rcx, [rbp+0B0h+var_30]
0x1800a4b04  test    rcx, rcx
0x1800a4b07  jz      short loc_1800A4B15
0x1800a4b09  mov     rax, [rcx]
0x1800a4b0c  mov     rax, [rax+18h]
0x1800a4b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4b15  cmp     [rbx], r12
0x1800a4b18  jz      short loc_1800A4B66
0x1800a4b1a  mov     rcx, r15; this
0x1800a4b1d  call    ?EnsureInputDeviceWatcher@AccessibilityExperienceManager@@AEAAJXZ; AccessibilityExperienceManager::EnsureInputDeviceWatcher(void)
0x1800a4b22  nop
0x1800a4b23  mov     rcx, [rsp+1B0h+var_150]
0x1800a4b28  test    rcx, rcx
0x1800a4b2b  jz      short loc_1800A4B3F
0x1800a4b2d  mov     [rsp+1B0h+var_150], r12
0x1800a4b32  mov     rax, [rcx]
0x1800a4b35  mov     rax, [rax+10h]
0x1800a4b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4b3e  nop
0x1800a4b3f  lea     rcx, [rsp+1B0h+var_148]
0x1800a4b44  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4b49  nop
0x1800a4b4a  test    r14, r14
0x1800a4b4d  jz      short loc_1800A4B5F
0x1800a4b4f  mov     rax, [r14]
0x1800a4b52  mov     rcx, r14
0x1800a4b55  mov     rax, [rax+10h]
0x1800a4b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4b5e  nop
0x1800a4b5f  xor     eax, eax
0x1800a4b61  jmp     loc_1800A48F6
0x1800a4b66  mov     ebx, 80004005h
0x1800a4b6b  mov     r9d, ebx; char *
0x1800a4b6e  mov     edx, 82h; void *
0x1800a4b73  lea     r8, aPcshellTwinuiA_11; "pcshell\\twinui\\accessibilityexperienc"...
0x1800a4b7a  mov     rcx, [rbp+0B8h]; this
0x1800a4b81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4b86  nop
0x1800a4b87  lea     rcx, [rsp+1B0h+var_150]
0x1800a4b8c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4b91  nop
0x1800a4b92  lea     rcx, [rsp+1B0h+var_148]; void *
0x1800a4b97  call    ??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)
0x1800a4b9c  nop
0x1800a4b9d  lea     rcx, [rbp+0B0h+var_120]
0x1800a4ba1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a4ba6  jmp     loc_1800A48F4
0x1800a4bab  mov     rcx, [rbp+0B8h]; this
0x1800a4bb2  mov     ebx, 8007000Eh
0x1800a4bb7  mov     r9d, ebx; char *
0x1800a4bba  lea     r8, aOnecoreInterna_24; "onecore\\internal\\sdk\\inc\\wil/resour"...
0x1800a4bc1  mov     edx, 3B1h; void *
0x1800a4bc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4bcb  jmp     loc_1800A4AD0
0x1800a4bd0  mov     rcx, [rbp+0B8h]; this
0x1800a4bd7  mov     r9d, ebx; char *
0x1800a4bda  lea     r8, aOnecoreInterna_24; "onecore\\internal\\sdk\\inc\\wil/resour"...
0x1800a4be1  mov     edx, 3C7h; void *
0x1800a4be6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a4beb  mov     ebx, eax
0x1800a4bed  mov     rax, [rdi]
0x1800a4bf0  mov     edx, 1
0x1800a4bf5  mov     rcx, rdi
0x1800a4bf8  mov     rax, [rax]
0x1800a4bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4c00  jmp     loc_1800A4AD0
0x1800a4c05  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x1800a4c0a  jmp     loc_1800A4AFD
0x1800a4c0f  mov     rax, [r14]
0x1800a4c12  mov     rcx, r14
0x1800a4c15  mov     rax, [rax+8]
0x1800a4c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4c1e  jmp     loc_1800A485D
0x1800a4c23  mov     r9d, ebx; char *
0x1800a4c26  mov     edx, 67h ; 'g'; void *
0x1800a4c2b  jmp     loc_1806F0930
0x1800a4c30  mov     r9d, eax
0x1800a4c33  mov     edx, 6Bh ; 'k'
0x1800a4c38  jmp     loc_1806F0930
0x1800a4c3d  xor     r9d, r9d; lpArguments
0x1800a4c40  xor     r8d, r8d; nNumberOfArguments
0x1800a4c43  lea     edx, [r9+1]; dwExceptionFlags
0x1800a4c47  mov     ecx, eax; dwExceptionCode
0x1800a4c49  call    cs:__imp_RaiseException
0x1800a4c4f  int     3; Trap to Debugger
0x1800a4c50  mov     r9d, eax
0x1800a4c53  mov     edx, 6Eh ; 'n'
0x1800a4c58  jmp     loc_1800A4B73
0x1800a4c5d  mov     r9d, eax
0x1800a4c60  mov     edx, 6Fh ; 'o'
0x1800a4c65  jmp     loc_1800A4B73
  ... truncated ...
```
