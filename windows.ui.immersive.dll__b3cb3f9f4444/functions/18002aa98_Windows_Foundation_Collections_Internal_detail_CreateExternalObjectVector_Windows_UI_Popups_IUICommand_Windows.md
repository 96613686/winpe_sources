# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Popups::IUICommand,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Popups::IUICommand *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Popups::IUICommand *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Popups::IUICommand *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Popups::IUICommand *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::UI::Popups::IUICommand *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Popups::IUICommand *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Popups::IUICommand *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Popups::IUICommand *>> * *)

- ea: `0x18002aa98`
- end: `0x18002acfa`
- name: `??$CreateExternalObjectVector@UIUICommand@Popups@UI@Windows@@V?$Vector@PEAUIUICommand@Popups@UI@Windows@@U?$DefaultEqualityPredicate@PEAUIUICommand@Popups@UI@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIUICommand@Popups@UI@Windows@@@6784@U?$DefaultVectorOptions@PEAUIUICommand@Popups@UI@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIUICommand@Popups@UI@Windows@@U?$DefaultEqualityPredicate@PEAUIUICommand@Popups@UI@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIUICommand@Popups@UI@Windows@@@6784@U?$DefaultVectorOptions@PEAUIUICommand@Popups@UI@Windows@@@6784@@1234@@Z`
- size: `610`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a9e0`
- `0x18004bbe4`

## callees

- `0x180013f14`
- `0x18002aa98`
- `0x180049800`
- `0x180049824`
- `0x180054130`
- `0x180075698`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002aaeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ab2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ab71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ac13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002aaeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ab2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ab71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ac13`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002ac3b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002ac3b`

## string_xrefs

- `0x18002ab64`: `Windows.Foundation.Collections.IIterator`1<Windows.UI.Popups.IUICommand>`
- `0x18002aade`: `Windows.Foundation.Collections.IVector`1<Windows.UI.Popups.IUICommand>`
- `0x18002ab21`: `Windows.Foundation.Collections.IVectorView`1<Windows.UI.Popups.IUICommand>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Popups::IUICommand,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Popups::IUICommand *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Popups::IUICommand *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Popups::IUICommand *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Popups::IUICommand *>>>(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v3; // eax
  UINT32 v4; // edx
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  unsigned int v8; // eax
  UINT32 v9; // edx
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  unsigned int v13; // eax
  UINT32 v14; // edx
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  int ActivationFactory; // ebx
  __int64 v22; // rcx
  __int64 v24; // rbx
  __int64 v25; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v27[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v28; // [rsp+48h] [rbp-B8h]
  GUID v29; // [rsp+58h] [rbp-A8h]
  GUID v30; // [rsp+68h] [rbp-98h]
  GUID v31; // [rsp+78h] [rbp-88h]
  GUID v32; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v35; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v36; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v37; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v38; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v39; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v40; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x46u);
  v4 = v3 - 1;
  if ( v3 > 0x46 )
    v4 = 70;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.UI.Popups.IUICommand>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    __debugbreak();
  }
  v36 = 0;
  v8 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Au);
  v9 = v8 - 1;
  if ( v8 > 0x4A )
    v9 = 74;
  v10 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IVectorView`1<Windows.UI.Popups.IUICommand>",
          v9,
          &v35,
          &v36);
  if ( v10 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
    __debugbreak();
  }
  v38 = 0;
  v13 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x48u);
  v14 = v13 - 1;
  if ( v13 > 0x48 )
    v14 = 72;
  v15 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.UI.Popups.IUICommand>",
          v14,
          &v37,
          &v38);
  if ( v15 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
    __debugbreak();
  }
  v27[0] = string;
  v28 = GUID_4ff93a75_4145_47ff_ac7f_dff1c1fa5b0f;
  v27[1] = v36;
  v29 = GUID_105139a1_dcb8_5f65_97ef_cb1bf0b75f9d;
  v27[2] = v38;
  v25 = 0;
  v30 = GUID_ed1165e6_f377_5b00_8172_93c1bd04deb4;
  v31 = GUID_e63de42b_53c3_5e07_90d3_98172d545412;
  v32 = GUID_f45db3d3_7299_57ce_a73e_297cf0af3083;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v25);
  v40 = 0;
  v18 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v39, &v40);
  if ( v18 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v40, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v25);
  if ( ActivationFactory < 0 )
  {
    v22 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return (unsigned int)ActivationFactory;
  }
  v24 = v25;
  v26 = 0;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v26);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v24, v27, &v26);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v25);
    return (unsigned int)ActivationFactory;
  }
  *a2 = v26;
  v26 = 0;
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v25);
  return 0;
}

```

## disassembly

```asm
0x18002aa98  mov     [rsp-8+arg_0], rbx
0x18002aa9d  mov     [rsp-8+arg_10], rdi
0x18002aaa2  push    rbp
0x18002aaa3  lea     rbp, [rsp-30h]
0x18002aaa8  sub     rsp, 130h
0x18002aaaf  mov     rax, cs:__security_cookie
0x18002aab6  xor     rax, rsp
0x18002aab9  mov     [rbp+30h+var_10], rax
0x18002aabd  mov     ebx, 46h ; 'F'
0x18002aac2  mov     [rbp+30h+string], 0
0x18002aaca  mov     ecx, ebx; unsigned int
0x18002aacc  mov     rdi, rdx
0x18002aacf  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002aad4  cmp     eax, ebx
0x18002aad6  lea     r9, [rbp+30h+string]; string
0x18002aada  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18002aade  lea     rcx, aWindowsFoundat_4; "Windows.Foundation.Collections.IVector`"...
0x18002aae5  lea     edx, [rax-1]
0x18002aae8  cmova   edx, ebx; length
0x18002aaeb  call    cs:__imp_WindowsCreateStringReference
0x18002aaf2  nop     dword ptr [rax+rax+00h]
0x18002aaf7  test    eax, eax
0x18002aaf9  jns     short loc_18002AB03
0x18002aafb  mov     ecx, eax; this
0x18002aafd  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002ab02  int     3; Trap to Debugger
0x18002ab03  mov     ebx, 4Ah ; 'J'
0x18002ab08  mov     [rbp+30h+var_58], 0
0x18002ab10  mov     ecx, ebx; unsigned int
0x18002ab12  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002ab17  cmp     eax, ebx
0x18002ab19  lea     r9, [rbp+30h+var_58]; string
0x18002ab1d  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002ab21  lea     rcx, aWindowsFoundat_11; "Windows.Foundation.Collections.IVectorV"...
0x18002ab28  lea     edx, [rax-1]
0x18002ab2b  cmova   edx, ebx; length
0x18002ab2e  call    cs:__imp_WindowsCreateStringReference
0x18002ab35  nop     dword ptr [rax+rax+00h]
0x18002ab3a  test    eax, eax
0x18002ab3c  jns     short loc_18002AB46
0x18002ab3e  mov     ecx, eax; this
0x18002ab40  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002ab45  int     3; Trap to Debugger
0x18002ab46  mov     ebx, 48h ; 'H'
0x18002ab4b  mov     [rbp+30h+var_38], 0
0x18002ab53  mov     ecx, ebx; unsigned int
0x18002ab55  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002ab5a  cmp     eax, ebx
0x18002ab5c  lea     r9, [rbp+30h+var_38]; string
0x18002ab60  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18002ab64  lea     rcx, aWindowsFoundat; "Windows.Foundation.Collections.IIterato"...
0x18002ab6b  lea     edx, [rax-1]
0x18002ab6e  cmova   edx, ebx; length
0x18002ab71  call    cs:__imp_WindowsCreateStringReference
0x18002ab78  nop     dword ptr [rax+rax+00h]
0x18002ab7d  test    eax, eax
0x18002ab7f  jns     short loc_18002AB89
0x18002ab81  mov     ecx, eax; this
0x18002ab83  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002ab88  int     3; Trap to Debugger
0x18002ab89  movups  xmm0, xmmword ptr cs:_GUID_4ff93a75_4145_47ff_ac7f_dff1c1fa5b0f.Data1
0x18002ab90  mov     rax, [rbp+30h+string]
0x18002ab94  lea     rcx, [rsp+130h+var_110]
0x18002ab99  movups  xmm1, xmmword ptr cs:_GUID_105139a1_dcb8_5f65_97ef_cb1bf0b75f9d.Data1
0x18002aba0  mov     [rsp+130h+var_100], rax
0x18002aba5  mov     rax, [rbp+30h+var_58]
0x18002aba9  movdqu  [rsp+130h+var_E8], xmm0
0x18002abaf  mov     [rsp+130h+var_F8], rax
0x18002abb4  movups  xmm0, xmmword ptr cs:_GUID_ed1165e6_f377_5b00_8172_93c1bd04deb4.Data1
0x18002abbb  mov     rax, [rbp+30h+var_38]
0x18002abbf  movdqu  [rsp+130h+var_D8], xmm1
0x18002abc5  mov     [rsp+130h+var_F0], rax
0x18002abca  movups  xmm1, xmmword ptr cs:_GUID_e63de42b_53c3_5e07_90d3_98172d545412.Data1
0x18002abd1  mov     [rsp+130h+var_110], 0
0x18002abda  movdqu  [rsp+130h+var_C8], xmm0
0x18002abe0  movups  xmm0, xmmword ptr cs:_GUID_f45db3d3_7299_57ce_a73e_297cf0af3083.Data1
0x18002abe7  movdqu  [rsp+130h+var_B8], xmm1
0x18002abed  movdqu  [rbp+30h+var_A8], xmm0
0x18002abf2  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18002abf7  lea     r9, [rbp+30h+var_18]; string
0x18002abfb  mov     [rbp+30h+var_18], 0
0x18002ac03  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18002ac07  mov     edx, 2Ch ; ','; length
0x18002ac0c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002ac13  call    cs:__imp_WindowsCreateStringReference
0x18002ac1a  nop     dword ptr [rax+rax+00h]
0x18002ac1f  test    eax, eax
0x18002ac21  jns     short loc_18002AC2B
0x18002ac23  mov     ecx, eax; this
0x18002ac25  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002ac2a  int     3; Trap to Debugger
0x18002ac2b  mov     rcx, [rbp+30h+var_18]
0x18002ac2f  lea     r8, [rsp+130h+var_110]
0x18002ac34  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002ac3b  call    cs:__imp_RoGetActivationFactory
0x18002ac42  nop     dword ptr [rax+rax+00h]
0x18002ac47  mov     ebx, eax
0x18002ac49  test    eax, eax
0x18002ac4b  jns     short loc_18002AC70
0x18002ac4d  mov     rcx, [rsp+130h+var_110]
0x18002ac52  test    rcx, rcx
0x18002ac55  jz      short loc_18002AC6C
0x18002ac57  mov     [rsp+130h+var_110], 0
0x18002ac60  mov     rdx, [rcx]
0x18002ac63  mov     rax, [rdx+10h]
0x18002ac67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac6c  mov     eax, ebx
0x18002ac6e  jmp     short loc_18002ACD8
0x18002ac70  mov     rbx, [rsp+130h+var_110]
0x18002ac75  lea     rcx, [rsp+130h+var_108]
0x18002ac7a  mov     [rsp+130h+var_108], 0
0x18002ac83  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18002ac88  lea     r8, [rsp+130h+var_108]
0x18002ac8d  mov     rcx, rbx
0x18002ac90  lea     rdx, [rsp+130h+var_100]
0x18002ac95  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x18002ac9a  lea     rcx, [rsp+130h+var_108]
0x18002ac9f  mov     ebx, eax
0x18002aca1  test    eax, eax
0x18002aca3  jns     short loc_18002ACB6
0x18002aca5  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18002acaa  lea     rcx, [rsp+130h+var_110]
0x18002acaf  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18002acb4  jmp     short loc_18002AC6C
0x18002acb6  mov     rax, [rsp+130h+var_108]
0x18002acbb  mov     [rdi], rax
0x18002acbe  mov     [rsp+130h+var_108], 0
0x18002acc7  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18002accc  lea     rcx, [rsp+130h+var_110]
0x18002acd1  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18002acd6  xor     eax, eax
0x18002acd8  mov     rcx, [rbp+30h+var_10]
0x18002acdc  xor     rcx, rsp; StackCookie
0x18002acdf  call    __security_check_cookie
0x18002ace4  lea     r11, [rsp+130h+var_s0]
0x18002acec  mov     rbx, [r11+10h]
0x18002acf0  mov     rdi, [r11+20h]
0x18002acf4  mov     rsp, r11
0x18002acf7  pop     rbp
0x18002acf8  retn
```
