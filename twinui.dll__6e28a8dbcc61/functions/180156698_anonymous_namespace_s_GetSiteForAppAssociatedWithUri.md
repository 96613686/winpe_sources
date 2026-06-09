# _anonymous_namespace_::s_GetSiteForAppAssociatedWithUri

- ea: `0x180156698`
- end: `0x1801568db`
- name: `_anonymous_namespace_::s_GetSiteForAppAssociatedWithUri`
- size: `579`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18015657c`

## callees

- `0x18000b7e8`
- `0x18000c350`
- `0x180027ee4`
- `0x180037e18`
- `0x180052980`
- `0x18013d330`
- `0x180151c98`
- `0x180156698`
- `0x18036034c`
- `0x1803a3010`

## import_xrefs

- `SHELL32!SHCreateAssociationRegistration` at `0x1801566e5`
- `SHELL32!SHCreateAssociationRegistration` at `0x1801566e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180156784`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015680e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180156887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015689a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180156784`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015680e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180156887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015689a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801567d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180156860`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801567d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180156860`

## string_xrefs

- `0x180156707`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::s_GetSiteForAppAssociatedWithUri(
        unsigned __int16 *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, IUnknown **),
        struct IUnknown **a3)
{
  HRESULT AppIdFromProgId; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  void *v12; // rdi
  __int64 (__fastcall *v13)(void *, PCWSTR, __int64, __int64, HSTRING_HEADER *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 (__fastcall **v15)(_QWORD, GUID *, IUnknown **); // rax
  __int64 (__fastcall *v16)(_QWORD, GUID *, IUnknown **); // rbx
  ImmersiveAssociationHelpers *v17; // rax
  HSTRING string; // [rsp+30h] [rbp-39h] BYREF
  IUnknown *punk; // [rsp+38h] [rbp-31h] BYREF
  HSTRING v21; // [rsp+40h] [rbp-29h] BYREF
  __int64 v22; // [rsp+48h] [rbp-21h] BYREF
  void *ppv; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-9h] BYREF
  __int64 v26; // [rsp+78h] [rbp+Fh]

  string = (HSTRING)a1;
  ppv = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  AppIdFromProgId = SHCreateAssociationRegistration(&GUID_a357134e_8c1e_4edd_8474_40a80546f54f, &ppv);
  if ( AppIdFromProgId >= 0 )
  {
    v24 = 0;
    v26 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
    AppIdFromProgId = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
                        v26,
                        &v24);
    if ( AppIdFromProgId >= 0 )
    {
      v7 = v24;
      v22 = 0;
      v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 48LL);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
      v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &string);
      AppIdFromProgId = v8(v7, *(_QWORD *)(v9 + 24), &v22);
      if ( AppIdFromProgId >= 0 )
      {
        v10 = v22;
        string = 0;
        v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 136LL);
        WindowsDeleteString(0);
        string = 0;
        AppIdFromProgId = v11(v10, &string);
        if ( AppIdFromProgId >= 0 )
        {
          v12 = ppv;
          memset(&hstringHeader, 0, sizeof(hstringHeader));
          v13 = *(__int64 (__fastcall **)(void *, PCWSTR, __int64, __int64, HSTRING_HEADER *))(*(_QWORD *)ppv + 64LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = -1;
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          AppIdFromProgId = v13(v12, StringRawBuffer, 1, 1, &hstringHeader);
          if ( AppIdFromProgId >= 0 )
          {
            v21 = 0;
            WindowsDeleteString(0);
            v21 = 0;
            AppIdFromProgId = GetAppIdFromProgId((unsigned __int16 *)hstringHeader.Reserved.Reserved1, (HSTRING)&v21);
            if ( AppIdFromProgId >= 0 )
            {
              v15 = *a2;
              punk = 0;
              v16 = *v15;
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&punk);
              AppIdFromProgId = v16(a2, &GUID_adf3165c_ba9e_42a7_922f_2005d7bd711a, &punk);
              if ( AppIdFromProgId >= 0 )
              {
                v17 = (ImmersiveAssociationHelpers *)WindowsGetStringRawBuffer(v21, 0);
                AppIdFromProgId = GetMainWindowViewPreferenceSite(punk, a1, v17, a3);
              }
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&punk);
            }
            WindowsDeleteString(v21);
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
        }
        WindowsDeleteString(string);
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v22);
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v24);
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  return (unsigned int)AppIdFromProgId;
}

```

## disassembly

```asm
0x180156698  push    rbp
0x18015669a  push    rbx
0x18015669b  push    rsi
0x18015669c  push    rdi
0x18015669d  push    r12
0x18015669f  push    r14
0x1801566a1  push    r15
0x1801566a3  lea     rbp, [rsp-27h]
0x1801566a8  sub     rsp, 90h
0x1801566af  mov     rax, cs:__security_cookie
0x1801566b6  xor     rax, rsp
0x1801566b9  mov     [rbp+57h+var_40], rax
0x1801566bd  mov     rsi, rcx
0x1801566c0  mov     [rbp+57h+string], rcx
0x1801566c4  xor     r12d, r12d
0x1801566c7  lea     rcx, [rbp+57h+ppv]
0x1801566cb  mov     [rbp+57h+ppv], r12
0x1801566cf  mov     r15, r8
0x1801566d2  mov     r14, rdx
0x1801566d5  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801566da  lea     rdx, [rbp+57h+ppv]; ppv
0x1801566de  lea     rcx, _GUID_a357134e_8c1e_4edd_8474_40a80546f54f; riid
0x1801566e5  call    cs:__imp_SHCreateAssociationRegistration
0x1801566eb  mov     ebx, eax
0x1801566ed  test    eax, eax
0x1801566ef  js      loc_1801568B2
0x1801566f5  lea     r9d, [r12+16h]; unsigned int
0x1801566fa  mov     [rbp+57h+var_68], r12
0x1801566fe  lea     r8d, [r12+17h]; unsigned int
0x180156703  mov     [rbp+57h+var_48], r12
0x180156707  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18015670e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180156712  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180156717  mov     rcx, [rbp+57h+var_48]
0x18015671b  lea     rdx, [rbp+57h+var_68]
0x18015671f  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x180156724  mov     ebx, eax
0x180156726  test    eax, eax
0x180156728  js      loc_1801568A9
0x18015672e  mov     rdi, [rbp+57h+var_68]
0x180156732  lea     rcx, [rbp+57h+var_78]
0x180156736  mov     [rbp+57h+var_78], r12
0x18015673a  mov     rax, [rdi]
0x18015673d  mov     rbx, [rax+30h]
0x180156741  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180156746  lea     rdx, [rbp+57h+string]
0x18015674a  lea     rcx, [rbp+57h+hstringHeader]
0x18015674e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180156753  lea     r8, [rbp+57h+var_78]
0x180156757  mov     rcx, rdi
0x18015675a  mov     rdx, [rax+18h]
0x18015675e  mov     rax, rbx
0x180156761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180156766  mov     ebx, eax
0x180156768  test    eax, eax
0x18015676a  js      loc_1801568A0
0x180156770  mov     rdi, [rbp+57h+var_78]
0x180156774  xor     ecx, ecx; string
0x180156776  mov     [rbp+57h+string], r12
0x18015677a  mov     rax, [rdi]
0x18015677d  mov     rbx, [rax+88h]
0x180156784  call    cs:__imp_WindowsDeleteString
0x18015678a  lea     rdx, [rbp+57h+string]
0x18015678e  mov     [rbp+57h+string], r12
0x180156792  mov     rcx, rdi
0x180156795  mov     rax, rbx
0x180156798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015679d  mov     ebx, eax
0x18015679f  test    eax, eax
0x1801567a1  js      loc_180156896
0x1801567a7  mov     rdi, [rbp+57h+ppv]
0x1801567ab  lea     rcx, [rbp+57h+hstringHeader]
0x1801567af  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r12
0x1801567b3  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r12
0x1801567b7  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r12
0x1801567bb  mov     rax, [rdi]
0x1801567be  mov     rbx, [rax+40h]
0x1801567c2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801567c7  mov     rcx, [rbp+57h+string]; string
0x1801567cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801567cf  xor     edx, edx; length
0x1801567d1  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x1801567d5  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rax
0x1801567d9  call    cs:__imp_WindowsGetStringRawBuffer
0x1801567df  lea     rcx, [rbp+57h+hstringHeader]
0x1801567e3  mov     rdx, rax
0x1801567e6  lea     r8d, [r12+1]
0x1801567eb  mov     [rsp+0C0h+var_A0], rcx
0x1801567f0  mov     rcx, rdi
0x1801567f3  mov     r9d, r8d
0x1801567f6  mov     rax, rbx
0x1801567f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801567fe  mov     ebx, eax
0x180156800  test    eax, eax
0x180156802  js      loc_18015688D
0x180156808  xor     ecx, ecx; string
0x18015680a  mov     [rbp+57h+var_80], r12
0x18015680e  call    cs:__imp_WindowsDeleteString
0x180156814  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]; unsigned __int16 *
0x180156818  lea     rdx, [rbp+57h+var_80]; HSTRING
0x18015681c  mov     [rbp+57h+var_80], r12
0x180156820  call    GetAppIdFromProgId
0x180156825  mov     ebx, eax
0x180156827  test    eax, eax
0x180156829  js      short loc_180156883
0x18015682b  mov     rax, [r14]
0x18015682e  lea     rcx, [rbp+57h+punk]
0x180156832  mov     [rbp+57h+punk], r12
0x180156836  mov     rbx, [rax]
0x180156839  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18015683e  lea     r8, [rbp+57h+punk]
0x180156842  mov     rcx, r14
0x180156845  lea     rdx, _GUID_adf3165c_ba9e_42a7_922f_2005d7bd711a
0x18015684c  mov     rax, rbx
0x18015684f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180156854  mov     ebx, eax
0x180156856  test    eax, eax
0x180156858  js      short loc_18015687A
0x18015685a  mov     rcx, [rbp+57h+var_80]; string
0x18015685e  xor     edx, edx; length
0x180156860  call    cs:__imp_WindowsGetStringRawBuffer
0x180156866  mov     rcx, [rbp+57h+punk]; punk
0x18015686a  mov     r9, r15; struct IUnknown **
0x18015686d  mov     r8, rax; this
0x180156870  mov     rdx, rsi; unsigned __int16 *
0x180156873  call    ?GetMainWindowViewPreferenceSite@@YAJPEAUIMainWindowActivationInfo@Actions@ApplicationModel@Windows@@PEBG1PEAPEAUIUnknown@@@Z; GetMainWindowViewPreferenceSite(Windows::ApplicationModel::Actions::IMainWindowActivationInfo *,ushort const *,ushort const *,IUnknown * *)
0x180156878  mov     ebx, eax
0x18015687a  lea     rcx, [rbp+57h+punk]
0x18015687e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180156883  mov     rcx, [rbp+57h+var_80]; string
0x180156887  call    cs:__imp_WindowsDeleteString
0x18015688d  lea     rcx, [rbp+57h+hstringHeader]
0x180156891  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180156896  mov     rcx, [rbp+57h+string]; string
0x18015689a  call    cs:__imp_WindowsDeleteString
0x1801568a0  lea     rcx, [rbp+57h+var_78]
0x1801568a4  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801568a9  lea     rcx, [rbp+57h+var_68]
0x1801568ad  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801568b2  lea     rcx, [rbp+57h+ppv]
0x1801568b6  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801568bb  mov     eax, ebx
0x1801568bd  mov     rcx, [rbp+57h+var_40]
0x1801568c1  xor     rcx, rsp; StackCookie
0x1801568c4  call    __security_check_cookie
0x1801568c9  add     rsp, 90h
0x1801568d0  pop     r15
0x1801568d2  pop     r14
0x1801568d4  pop     r12
0x1801568d6  pop     rdi
0x1801568d7  pop     rsi
0x1801568d8  pop     rbx
0x1801568d9  pop     rbp
0x1801568da  retn
```
