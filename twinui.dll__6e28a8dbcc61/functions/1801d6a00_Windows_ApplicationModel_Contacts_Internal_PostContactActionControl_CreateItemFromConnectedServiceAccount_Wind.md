# Windows::ApplicationModel::Contacts::Internal::PostContactActionControl::_CreateItemFromConnectedServiceAccount(Windows::ApplicationModel::Contacts::IContactConnectedServiceAccount *,Windows::ApplicationModel::Contacts::Internal::ContactServiceActions,Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager *,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem * *)

- ea: `0x1801d6a00`
- end: `0x1801d6bf2`
- name: `?_CreateItemFromConnectedServiceAccount@PostContactActionControl@Internal@Contacts@ApplicationModel@Windows@@MEAAJPEAUIContactConnectedServiceAccount@345@W4ContactServiceActions@2345@PEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@5@PEAUIContactPreferenceManager@2345@PEAPEAUIContactActionControlItem@2345@@Z`
- size: `498`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000b7e8`
- `0x18000c350`
- `0x180052980`
- `0x1801168d0`
- `0x18013d330`
- `0x1801cd3cc`
- `0x1801d6308`
- `0x1801d67a8`
- `0x1801d6a00`
- `0x1801d7430`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6a52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6a5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6a6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6bb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6bc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6a52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6a5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6a6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6bb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d6bc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d6b0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d6b0e`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::PostContactActionControl::_CreateItemFromConnectedServiceAccount(
        __int64 a1,
        __int64 *a2,
        int a3,
        __int64 *a4,
        __int64 a5,
        _QWORD *a6)
{
  int ConnectedServiceAccountData; // eax
  HSTRING v11; // rbx
  int Instance; // r14d
  HSTRING v13; // rdi
  HSTRING v14; // rsi
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v16; // r13
  __int64 v17; // rax
  __int64 v18; // r15
  HSTRING v19; // r12
  __int64 v20; // r14
  unsigned int v21; // eax
  HSTRING string; // [rsp+50h] [rbp-49h] BYREF
  HSTRING v24; // [rsp+58h] [rbp-41h] BYREF
  HSTRING v25; // [rsp+60h] [rbp-39h] BYREF
  __int64 v26; // [rsp+68h] [rbp-31h]
  _QWORD *v27; // [rsp+70h] [rbp-29h]
  __int64 v28; // [rsp+78h] [rbp-21h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-19h] BYREF
  __int64 v30; // [rsp+98h] [rbp-1h]

  v28 = a5;
  v26 = a1;
  v27 = a6;
  *a6 = 0;
  WindowsDeleteString(0);
  v24 = 0;
  WindowsDeleteString(0);
  v25 = 0;
  WindowsDeleteString(0);
  string = 0;
  ConnectedServiceAccountData = Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_GetConnectedServiceAccountData(
                                  a2,
                                  a3,
                                  a4,
                                  &string,
                                  &v25,
                                  &v24);
  v11 = string;
  Instance = ConnectedServiceAccountData;
  v13 = v25;
  v14 = v24;
  if ( ConnectedServiceAccountData >= 0 && string )
  {
    string = 0;
    v30 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.ApplicationModel.Contacts.Contact",
      0x2Au,
      0x29u);
    Instance = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Contacts::IContact2>>(
                 v30,
                 &string);
    if ( Instance >= 0 )
    {
      Instance = Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_CopyContactNameAndThumbnail(
                   *(__int64 (__fastcall ****)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *))(a1 + 112),
                   (__int64 (__fastcall ***)(struct Windows::ApplicationModel::Contacts::IContact2 *, GUID *, __int64 *))string);
      if ( Instance >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v11, 0);
        Instance = Windows::ApplicationModel::Contacts::Internal::PostContactActionControl::_CopyMatchingContactConnectedServiceAccounts(
                     *(struct Windows::ApplicationModel::Contacts::IContact2 **)(a1 + 112),
                     (struct Windows::ApplicationModel::Contacts::IContact2 *)string,
                     StringRawBuffer);
        if ( Instance >= 0 )
        {
          v16 = *(_QWORD *)(a1 + 120);
          v24 = (HSTRING)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 120LL))(a1);
          v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v24);
          v18 = *(_QWORD *)(a1 + 72);
          v19 = string;
          v20 = *(_QWORD *)(v17 + 24);
          v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 112LL))(v26);
          Instance = Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(
                       v21,
                       v19,
                       v18,
                       v20,
                       v14,
                       v13,
                       v11,
                       v16,
                       v28,
                       v27);
        }
      }
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
  }
  WindowsDeleteString(v14);
  WindowsDeleteString(v13);
  WindowsDeleteString(v11);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801d6a00  mov     [rsp-8+arg_10], rbx
0x1801d6a05  push    rbp
0x1801d6a06  push    rsi
0x1801d6a07  push    rdi
0x1801d6a08  push    r12
0x1801d6a0a  push    r13
0x1801d6a0c  push    r14
0x1801d6a0e  push    r15
0x1801d6a10  lea     rbp, [rsp-17h]
0x1801d6a15  sub     rsp, 0B0h
0x1801d6a1c  mov     rax, cs:__security_cookie
0x1801d6a23  xor     rax, rsp
0x1801d6a26  mov     [rbp+47h+var_40], rax
0x1801d6a2a  mov     rax, [rbp+47h+arg_20]
0x1801d6a2e  mov     r15, rcx
0x1801d6a31  mov     [rbp+47h+var_68], rax
0x1801d6a35  xor     r12d, r12d
0x1801d6a38  mov     rax, [rbp+47h+arg_28]
0x1801d6a3c  mov     rsi, r9
0x1801d6a3f  mov     [rbp+47h+var_78], rcx
0x1801d6a43  mov     ebx, r8d
0x1801d6a46  xor     ecx, ecx; string
0x1801d6a48  mov     [rbp+47h+var_70], rax
0x1801d6a4c  mov     rdi, rdx
0x1801d6a4f  mov     [rax], r12
0x1801d6a52  call    cs:__imp_WindowsDeleteString
0x1801d6a58  xor     ecx, ecx; string
0x1801d6a5a  mov     [rbp+47h+var_88], r12
0x1801d6a5e  call    cs:__imp_WindowsDeleteString
0x1801d6a64  xor     ecx, ecx; string
0x1801d6a66  mov     [rbp+47h+var_80], r12
0x1801d6a6a  call    cs:__imp_WindowsDeleteString
0x1801d6a70  lea     rax, [rbp+47h+var_88]
0x1801d6a74  mov     [rbp+47h+string], r12
0x1801d6a78  mov     [rsp+0E0h+var_B8], rax
0x1801d6a7d  lea     r9, [rbp+47h+string]
0x1801d6a81  lea     rax, [rbp+47h+var_80]
0x1801d6a85  mov     r8, rsi
0x1801d6a88  mov     edx, ebx
0x1801d6a8a  mov     [rsp+0E0h+var_C0], rax
0x1801d6a8f  mov     rcx, rdi
0x1801d6a92  call    ?_GetConnectedServiceAccountData@ContactActionControlBase@Internal@Contacts@ApplicationModel@Windows@@KAJPEAUIContactConnectedServiceAccount@345@W4ContactServiceActions@2345@PEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@5@PEAPEAUHSTRING__@@33@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_GetConnectedServiceAccountData(Windows::ApplicationModel::Contacts::IContactConnectedServiceAccount *,Windows::ApplicationModel::Contacts::Internal::ContactServiceActions,Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1801d6a97  mov     rbx, [rbp+47h+string]
0x1801d6a9b  mov     r14d, eax
0x1801d6a9e  mov     rdi, [rbp+47h+var_80]
0x1801d6aa2  mov     rsi, [rbp+47h+var_88]
0x1801d6aa6  test    eax, eax
0x1801d6aa8  js      loc_1801D6BAD
0x1801d6aae  test    rbx, rbx
0x1801d6ab1  jz      loc_1801D6BAD
0x1801d6ab7  lea     r9d, [r12+29h]; unsigned int
0x1801d6abc  mov     [rbp+47h+string], r12
0x1801d6ac0  lea     r8d, [r12+2Ah]; unsigned int
0x1801d6ac5  mov     [rbp+47h+var_48], r12
0x1801d6ac9  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Contacts_Contact@@3QBGB; "Windows.ApplicationModel.Contacts.Conta"...
0x1801d6ad0  lea     rcx, [rbp+47h+hstringHeader]; hstringHeader
0x1801d6ad4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801d6ad9  mov     rcx, [rbp+47h+var_48]
0x1801d6add  lea     rdx, [rbp+47h+string]
0x1801d6ae1  call    ??$ActivateInstance@V?$ComPtr@UIContact2@Contacts@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIContact2@Contacts@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Contacts::IContact2>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Contacts::IContact2>>)
0x1801d6ae6  mov     r14d, eax
0x1801d6ae9  test    eax, eax
0x1801d6aeb  js      loc_1801D6BA4
0x1801d6af1  mov     rdx, [rbp+47h+string]; struct Windows::ApplicationModel::Contacts::IContact2 *
0x1801d6af5  mov     rcx, [r15+70h]; struct Windows::ApplicationModel::Contacts::IContact2 *
0x1801d6af9  call    ?_CopyContactNameAndThumbnail@ContactActionControlBase@Internal@Contacts@ApplicationModel@Windows@@KAJPEAUIContact2@345@0@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlBase::_CopyContactNameAndThumbnail(Windows::ApplicationModel::Contacts::IContact2 *,Windows::ApplicationModel::Contacts::IContact2 *)
0x1801d6afe  mov     r14d, eax
0x1801d6b01  test    eax, eax
0x1801d6b03  js      loc_1801D6BA4
0x1801d6b09  xor     edx, edx; length
0x1801d6b0b  mov     rcx, rbx; string
0x1801d6b0e  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d6b14  mov     rdx, [rbp+47h+string]; struct Windows::ApplicationModel::Contacts::IContact2 *
0x1801d6b18  mov     r8, rax; unsigned __int16 *
0x1801d6b1b  mov     rcx, [r15+70h]; struct Windows::ApplicationModel::Contacts::IContact2 *
0x1801d6b1f  call    ?_CopyMatchingContactConnectedServiceAccounts@PostContactActionControl@Internal@Contacts@ApplicationModel@Windows@@KAJPEAUIContact2@345@0PEBG@Z; Windows::ApplicationModel::Contacts::Internal::PostContactActionControl::_CopyMatchingContactConnectedServiceAccounts(Windows::ApplicationModel::Contacts::IContact2 *,Windows::ApplicationModel::Contacts::IContact2 *,ushort const *)
0x1801d6b24  mov     r14d, eax
0x1801d6b27  test    eax, eax
0x1801d6b29  js      short loc_1801D6BA4
0x1801d6b2b  mov     rax, [r15]
0x1801d6b2e  mov     rcx, r15
0x1801d6b31  mov     r13, [r15+78h]
0x1801d6b35  mov     rax, [rax+78h]
0x1801d6b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d6b3e  lea     rdx, [rbp+47h+var_88]
0x1801d6b42  mov     [rbp+47h+var_88], rax
0x1801d6b46  lea     rcx, [rbp+47h+hstringHeader]
0x1801d6b4a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801d6b4f  mov     rcx, [rbp+47h+var_78]
0x1801d6b53  mov     r15, [r15+48h]
0x1801d6b57  mov     r12, [rbp+47h+string]
0x1801d6b5b  mov     r14, [rax+18h]
0x1801d6b5f  mov     rax, [rcx]
0x1801d6b62  mov     rax, [rax+70h]
0x1801d6b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d6b6b  mov     rcx, [rbp+47h+var_70]
0x1801d6b6f  mov     r9, r14
0x1801d6b72  mov     [rsp+0E0h+var_98], rcx
0x1801d6b77  mov     r8, r15
0x1801d6b7a  mov     rcx, [rbp+47h+var_68]
0x1801d6b7e  mov     rdx, r12
0x1801d6b81  mov     [rsp+0E0h+var_A0], rcx
0x1801d6b86  mov     ecx, eax
0x1801d6b88  mov     [rsp+0E0h+var_A8], r13
0x1801d6b8d  mov     [rsp+0E0h+var_B0], rbx
0x1801d6b92  mov     [rsp+0E0h+var_B8], rdi
0x1801d6b97  mov     [rsp+0E0h+var_C0], rsi
0x1801d6b9c  call    ?ContactActionControlItem_CreateInstance@Internal@Contacts@ApplicationModel@Windows@@YAJW4ControlType@1234@PEAUIContact2@234@PEAUHSTRING__@@2222PEAUIShellItem@@PEAUIContactPreferenceManager@1234@PEAPEAUIContactActionControlItem@1234@@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlItem_CreateInstance(Windows::ApplicationModel::Contacts::Internal::ControlType,Windows::ApplicationModel::Contacts::IContact2 *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,IShellItem *,Windows::ApplicationModel::Contacts::Internal::IContactPreferenceManager *,Windows::ApplicationModel::Contacts::Internal::IContactActionControlItem * *)
0x1801d6ba1  mov     r14d, eax
0x1801d6ba4  lea     rcx, [rbp+47h+string]
0x1801d6ba8  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d6bad  mov     rcx, rsi; string
0x1801d6bb0  call    cs:__imp_WindowsDeleteString
0x1801d6bb6  mov     rcx, rdi; string
0x1801d6bb9  call    cs:__imp_WindowsDeleteString
0x1801d6bbf  mov     rcx, rbx; string
0x1801d6bc2  call    cs:__imp_WindowsDeleteString
0x1801d6bc8  mov     eax, r14d
0x1801d6bcb  mov     rcx, [rbp+47h+var_40]
0x1801d6bcf  xor     rcx, rsp; StackCookie
0x1801d6bd2  call    __security_check_cookie
0x1801d6bd7  mov     rbx, [rsp+0E0h+arg_10]
0x1801d6bdf  add     rsp, 0B0h
0x1801d6be6  pop     r15
0x1801d6be8  pop     r14
0x1801d6bea  pop     r13
0x1801d6bec  pop     r12
0x1801d6bee  pop     rdi
0x1801d6bef  pop     rsi
0x1801d6bf0  pop     rbp
0x1801d6bf1  retn
```
