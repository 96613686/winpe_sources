# Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_ExecuteActionThroughLaunch(unsigned __int64,Windows::ApplicationModel::Contacts::Internal::ActivationSource,HSTRING__ *,HWND__ *)

- ea: `0x1801d0c8c`
- end: `0x1801d0e2e`
- name: `?_ExecuteActionThroughLaunch@ContactActionControlItemBase@Internal@Contacts@ApplicationModel@Windows@@IEAAJ_KW4ActivationSource@2345@PEAUHSTRING__@@PEAUHWND__@@@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1801cd810`

## callees

- `0x18000b7e8`
- `0x18000c350`
- `0x18006d698`
- `0x18013d330`
- `0x1801c2cd0`
- `0x1801ca7a4`
- `0x1801d0a68`
- `0x1801d0c8c`
- `0x1801d0e34`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0cc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0cd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0ce2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0deb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0df5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0dff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0cc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0cd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0ce2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0deb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0df5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801d0dff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d0d34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d0d44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d0d34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801d0d44`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_ExecuteActionThroughLaunch(
        _QWORD *a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  int ContactsProvider; // eax
  HSTRING v10; // r8
  HSTRING v11; // rbx
  int v12; // edi
  __int64 v13; // r8
  HSTRING v14; // rcx
  PCWSTR StringRawBuffer; // rax
  HSTRING v16; // rcx
  HSTRING string; // [rsp+50h] [rbp-41h] BYREF
  HSTRING v19; // [rsp+58h] [rbp-39h] BYREF
  HSTRING v20; // [rsp+60h] [rbp-31h] BYREF
  __int64 v21; // [rsp+68h] [rbp-29h] BYREF
  PCWSTR v22; // [rsp+70h] [rbp-21h] BYREF
  PCWSTR v23; // [rsp+78h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-11h] BYREF
  __int64 v25; // [rsp+98h] [rbp+7h]

  WindowsDeleteString(0);
  string = 0;
  WindowsDeleteString(0);
  v20 = 0;
  WindowsDeleteString(0);
  v19 = 0;
  ContactsProvider = InternalGetContactsProvider(&v19, &v20, &string);
  v11 = string;
  v12 = ContactsProvider;
  if ( ContactsProvider >= 0 )
  {
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                         (Microsoft::WRL::Wrappers::Details *)v19,
                         0,
                         v10) )
    {
      v14 = (HSTRING)a1[15];
      v21 = a1[8];
      string = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(v14, 0);
      v16 = (HSTRING)a1[12];
      v22 = StringRawBuffer;
      v23 = WindowsGetStringRawBuffer(v16, 0);
      v12 = Microsoft::WRL::Details::MakeAndInitialize<CContactCallActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,unsigned short const *,unsigned short const *,Windows::ApplicationModel::Contacts::IContact2 *>(
              &string,
              &v23,
              &v22,
              &v21);
      if ( v12 >= 0 )
      {
        v25 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Launch", 0xFu, 0xEu);
        v12 = Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_ExecuteActionThroughActivationFramework(
                a1,
                string,
                v25,
                3,
                a2,
                a3,
                a4,
                a5,
                v11);
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
    }
    else
    {
      Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_ExecuteActionThroughUriScheme(
        a1,
        L"ms-windows-store:PDP?PFN=%1",
        v13,
        a2,
        a3,
        a4,
        a5);
    }
  }
  WindowsDeleteString(v11);
  WindowsDeleteString(v20);
  WindowsDeleteString(v19);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1801d0c8c  mov     [rsp-8+arg_10], rbx
0x1801d0c91  push    rbp
0x1801d0c92  push    rsi
0x1801d0c93  push    rdi
0x1801d0c94  push    r12
0x1801d0c96  push    r13
0x1801d0c98  push    r14
0x1801d0c9a  push    r15
0x1801d0c9c  lea     rbp, [rsp-1Fh]
0x1801d0ca1  sub     rsp, 0B0h
0x1801d0ca8  mov     rax, cs:__security_cookie
0x1801d0caf  xor     rax, rsp
0x1801d0cb2  mov     [rbp+4Fh+var_40], rax
0x1801d0cb6  mov     r13, [rbp+4Fh+arg_20]
0x1801d0cba  mov     rsi, rcx
0x1801d0cbd  xor     ecx, ecx; string
0x1801d0cbf  mov     r12, r9
0x1801d0cc2  mov     r14d, r8d
0x1801d0cc5  mov     r15, rdx
0x1801d0cc8  call    cs:__imp_WindowsDeleteString
0x1801d0cce  xor     ebx, ebx
0x1801d0cd0  xor     ecx, ecx; string
0x1801d0cd2  mov     [rbp+4Fh+string], rbx
0x1801d0cd6  call    cs:__imp_WindowsDeleteString
0x1801d0cdc  xor     ecx, ecx; string
0x1801d0cde  mov     [rbp+4Fh+var_80], rbx
0x1801d0ce2  call    cs:__imp_WindowsDeleteString
0x1801d0ce8  lea     r8, [rbp+4Fh+string]; HSTRING *
0x1801d0cec  mov     [rbp+4Fh+var_88], rbx
0x1801d0cf0  lea     rdx, [rbp+4Fh+var_80]; HSTRING *
0x1801d0cf4  lea     rcx, [rbp+4Fh+var_88]; HSTRING *
0x1801d0cf8  call    ?InternalGetContactsProvider@@YAJPEAPEAUHSTRING__@@00@Z; InternalGetContactsProvider(HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1801d0cfd  mov     rbx, [rbp+4Fh+string]
0x1801d0d01  mov     edi, eax
0x1801d0d03  test    eax, eax
0x1801d0d05  js      loc_1801D0DE8
0x1801d0d0b  mov     rcx, [rbp+4Fh+var_88]; this
0x1801d0d0f  xor     edx, edx; HSTRING
0x1801d0d11  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1801d0d16  test    eax, eax
0x1801d0d18  jz      loc_1801D0DC7
0x1801d0d1e  mov     rax, [rsi+40h]
0x1801d0d22  xor     edx, edx; length
0x1801d0d24  mov     rcx, [rsi+78h]; string
0x1801d0d28  mov     [rbp+4Fh+var_78], rax
0x1801d0d2c  mov     [rbp+4Fh+string], 0
0x1801d0d34  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d0d3a  mov     rcx, [rsi+60h]; string
0x1801d0d3e  xor     edx, edx; length
0x1801d0d40  mov     [rbp+4Fh+var_70], rax
0x1801d0d44  call    cs:__imp_WindowsGetStringRawBuffer
0x1801d0d4a  lea     r9, [rbp+4Fh+var_78]
0x1801d0d4e  mov     [rbp+4Fh+var_68], rax
0x1801d0d52  lea     r8, [rbp+4Fh+var_70]
0x1801d0d56  lea     rdx, [rbp+4Fh+var_68]
0x1801d0d5a  lea     rcx, [rbp+4Fh+string]
0x1801d0d5e  call    ??$MakeAndInitialize@VCContactCallActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEBGPEBGPEAUIContact2@Contacts@45@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@@012@$$QEAPEBG1$$QEAPEAUIContact2@Contacts@ApplicationModel@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CContactCallActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,ushort const *,ushort const *,Windows::ApplicationModel::Contacts::IContact2 *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>>,ushort const * &&,ushort const * &&,Windows::ApplicationModel::Contacts::IContact2 * &&)
0x1801d0d63  mov     edi, eax
0x1801d0d65  test    eax, eax
0x1801d0d67  js      short loc_1801D0DBC
0x1801d0d69  mov     r9d, 0Eh; unsigned int
0x1801d0d6f  mov     [rbp+4Fh+var_48], 0
0x1801d0d77  lea     rdx, aWindowsLaunch; "Windows.Launch"
0x1801d0d7e  lea     rcx, [rbp+4Fh+hstringHeader]; hstringHeader
0x1801d0d82  lea     r8d, [r9+1]; unsigned int
0x1801d0d86  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801d0d8b  mov     r8, [rbp+4Fh+var_48]
0x1801d0d8f  mov     r9d, 3
0x1801d0d95  mov     rdx, [rbp+4Fh+string]
0x1801d0d99  mov     rcx, rsi
0x1801d0d9c  mov     [rsp+0E0h+var_A0], rbx
0x1801d0da1  mov     [rsp+0E0h+var_A8], r13
0x1801d0da6  mov     [rsp+0E0h+var_B0], r12
0x1801d0dab  mov     dword ptr [rsp+0E0h+var_B8], r14d
0x1801d0db0  mov     [rsp+0E0h+var_C0], r15
0x1801d0db5  call    ?_ExecuteActionThroughActivationFramework@ContactActionControlItemBase@Internal@Contacts@ApplicationModel@Windows@@IEAAJPEAUIActivatedEventArgs@Activation@45@PEAUHSTRING__@@W4APPLICATION_VIEW_SIZE_PREFERENCE@@_KW4ActivationSource@2345@1PEAUHWND__@@1@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_ExecuteActionThroughActivationFramework(Windows::ApplicationModel::Activation::IActivatedEventArgs *,HSTRING__ *,APPLICATION_VIEW_SIZE_PREFERENCE,unsigned __int64,Windows::ApplicationModel::Contacts::Internal::ActivationSource,HSTRING__ *,HWND__ *,HSTRING__ *)
0x1801d0dba  mov     edi, eax
0x1801d0dbc  lea     rcx, [rbp+4Fh+string]
0x1801d0dc0  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801d0dc5  jmp     short loc_1801D0DE8
0x1801d0dc7  mov     [rsp+0E0h+var_B0], r13
0x1801d0dcc  lea     rdx, aMsWindowsStore_3; "ms-windows-store:PDP?PFN=%1"
0x1801d0dd3  mov     [rsp+0E0h+var_B8], r12
0x1801d0dd8  mov     r9, r15
0x1801d0ddb  mov     rcx, rsi
0x1801d0dde  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1801d0de3  call    ?_ExecuteActionThroughUriScheme@ContactActionControlItemBase@Internal@Contacts@ApplicationModel@Windows@@IEAAJPEBGW4APPLICATION_VIEW_SIZE_PREFERENCE@@_KW4ActivationSource@2345@PEAUHSTRING__@@PEAUHWND__@@@Z; Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_ExecuteActionThroughUriScheme(ushort const *,APPLICATION_VIEW_SIZE_PREFERENCE,unsigned __int64,Windows::ApplicationModel::Contacts::Internal::ActivationSource,HSTRING__ *,HWND__ *)
0x1801d0de8  mov     rcx, rbx; string
0x1801d0deb  call    cs:__imp_WindowsDeleteString
0x1801d0df1  mov     rcx, [rbp+4Fh+var_80]; string
0x1801d0df5  call    cs:__imp_WindowsDeleteString
0x1801d0dfb  mov     rcx, [rbp+4Fh+var_88]; string
0x1801d0dff  call    cs:__imp_WindowsDeleteString
0x1801d0e05  mov     eax, edi
0x1801d0e07  mov     rcx, [rbp+4Fh+var_40]
0x1801d0e0b  xor     rcx, rsp; StackCookie
0x1801d0e0e  call    __security_check_cookie
0x1801d0e13  mov     rbx, [rsp+0E0h+arg_10]
0x1801d0e1b  add     rsp, 0B0h
0x1801d0e22  pop     r15
0x1801d0e24  pop     r14
0x1801d0e26  pop     r13
0x1801d0e28  pop     r12
0x1801d0e2a  pop     rdi
0x1801d0e2b  pop     rsi
0x1801d0e2c  pop     rbp
0x1801d0e2d  retn
```
