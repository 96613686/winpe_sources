# CApplicationPreLaunchNotifications::NotifyDefaultAppForPenClick(void)

- ea: `0x180025910`
- end: `0x180025ba2`
- name: `?NotifyDefaultAppForPenClick@CApplicationPreLaunchNotifications@@AEAAJXZ`
- size: `658`
- prototype: `__int64 __fastcall(CApplicationPreLaunchNotifications *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024274`

## callees

- `0x180008acc`
- `0x18000b7e8`
- `0x18000e028`
- `0x180025910`
- `0x1800a5cbc`
- `0x1800f21d0`
- `0x18013d330`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800259c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025a36`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800259c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025a36`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002596f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002596f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025afb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025b3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025afb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025b3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025b20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025b20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800259b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025a21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800259b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180025a21`

## pseudocode

```c
__int64 __fastcall CApplicationPreLaunchNotifications::NotifyDefaultAppForPenClick(
        CApplicationPreLaunchNotifications *this)
{
  LSTATUS ValueW; // eax
  signed int v2; // ebx
  HRESULT v3; // eax
  _QWORD *v4; // rbx
  __int64 v5; // rdi
  unsigned int v6; // eax
  UINT32 v7; // edx
  HRESULT v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  CApplicationPreLaunchNotifications *v16; // rcx
  __int64 v17; // rcx
  _QWORD *v18; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-29h] BYREF
  __int64 v21; // [rsp+48h] [rbp-21h] BYREF
  int pvData; // [rsp+50h] [rbp-19h] BYREF
  HSTRING v23; // [rsp+58h] [rbp-11h] BYREF
  __int64 v24; // [rsp+60h] [rbp-9h] BYREF
  __int64 v25; // [rsp+68h] [rbp-1h] BYREF
  _QWORD *v26; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+90h] [rbp+27h] BYREF

  pcbData = 4;
  pvData = 0;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\ClickNote\\UserCustomization\\SingleClickBelowLock",
             L"Override",
             0x10u,
             0,
             &pvData,
             &pcbData);
  v2 = ValueW;
  if ( ValueW > 0 )
    v2 = (unsigned __int16)ValueW | 0x80070000;
  if ( v2 >= 0 && pvData == 9 )
  {
    v26 = 0;
    string = 0;
    v3 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
    if ( v3 < 0 )
    {
      RaiseException(v3, 1u, 0, 0);
      __debugbreak();
    }
    v2 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
           string,
           &v26);
    if ( v2 >= 0 )
    {
      v4 = v26;
      v21 = 0;
      v5 = *v26;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v21);
      string = 0;
      v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x2Du);
      v7 = v6 - 1;
      if ( v6 > 0x2D )
        v7 = 45;
      v8 = WindowsCreateStringReference(L"Microsoft.Whiteboard_8wekyb3d8bbwe!Whiteboard", v7, &hstringHeader, &string);
      if ( v8 < 0 )
      {
        RaiseException(v8, 1u, 0, 0);
        __debugbreak();
      }
      v2 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v5 + 128))(v4, string, &v21);
      if ( v2 >= 0 )
      {
        pcbData = 0;
        v2 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v21 + 56LL))(v21, &pcbData);
        if ( v2 >= 0 && pcbData == 1 )
        {
          v9 = v21;
          v25 = 0;
          v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 48LL);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v25);
          v2 = v10(v9, 0, &v25);
          if ( v2 >= 0 )
          {
            v11 = v25;
            v24 = 0;
            v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 72LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
            v2 = v12(v11, &v24);
            if ( v2 >= 0 )
            {
              v13 = v24;
              v23 = 0;
              v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 112LL);
              WindowsDeleteString(0);
              v23 = 0;
              v2 = v14(v13, &v23);
              if ( v2 >= 0 )
              {
                StringRawBuffer = WindowsGetStringRawBuffer(v23, 0);
                CApplicationPreLaunchNotifications::NotifyDefaultApp(
                  v16,
                  L"Microsoft.Whiteboard_8wekyb3d8bbwe!Whiteboard",
                  StringRawBuffer,
                  0);
              }
              WindowsDeleteString(v23);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
          }
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v25);
        }
      }
      v17 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
    v18 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180025910  push    rbp
0x180025912  push    rbx
0x180025913  push    rsi
0x180025914  push    rdi
0x180025915  push    r14
0x180025917  lea     rbp, [rsp-37h]
0x18002591c  sub     rsp, 0A0h
0x180025923  mov     rax, cs:__security_cookie
0x18002592a  xor     rax, rsp
0x18002592d  mov     [rbp+57h+var_28], rax
0x180025931  xor     r14d, r14d
0x180025934  mov     [rbp+57h+var_80], 4
0x18002593b  lea     rax, [rbp+57h+var_80]
0x18002593f  mov     [rbp+57h+var_70], r14d
0x180025943  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180025948  lea     r8, aOverride; "Override"
0x18002594f  lea     rax, [rbp+57h+var_70]
0x180025953  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18002595a  mov     [rsp+0C0h+pvData], rax; pvData
0x18002595f  lea     r9d, [r14+10h]; dwFlags
0x180025963  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002596a  mov     [rsp+0C0h+pdwType], r14; pdwType
0x18002596f  call    cs:__imp_RegGetValueW
0x180025975  mov     ebx, eax
0x180025977  test    eax, eax
0x180025979  jle     short loc_180025984
0x18002597b  movzx   ebx, ax
0x18002597e  or      ebx, 80070000h
0x180025984  test    ebx, ebx
0x180025986  js      loc_180025B86
0x18002598c  cmp     [rbp+57h+var_70], 9
0x180025990  jnz     loc_180025B86
0x180025996  lea     r9, [rbp+57h+string]; string
0x18002599a  mov     [rbp+57h+var_50], r14
0x18002599e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800259a2  mov     [rbp+57h+string], r14
0x1800259a6  mov     edx, 2Ch ; ','; length
0x1800259ab  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800259b2  call    cs:__imp_WindowsCreateStringReference
0x1800259b8  test    eax, eax
0x1800259ba  jns     short loc_1800259CF
0x1800259bc  xor     r9d, r9d; lpArguments
0x1800259bf  xor     r8d, r8d; nNumberOfArguments
0x1800259c2  mov     ecx, eax; dwExceptionCode
0x1800259c4  lea     edx, [r9+1]; dwExceptionFlags
0x1800259c8  call    cs:__imp_RaiseException
0x1800259ce  int     3; Trap to Debugger
0x1800259cf  mov     rcx, [rbp+57h+string]
0x1800259d3  lea     rdx, [rbp+57h+var_50]
0x1800259d7  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x1800259dc  mov     ebx, eax
0x1800259de  test    eax, eax
0x1800259e0  js      loc_180025B6D
0x1800259e6  mov     rbx, [rbp+57h+var_50]
0x1800259ea  lea     rcx, [rbp+57h+var_78]
0x1800259ee  mov     [rbp+57h+var_78], r14
0x1800259f2  mov     rdi, [rbx]
0x1800259f5  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800259fa  mov     esi, 2Dh ; '-'
0x1800259ff  mov     [rbp+57h+string], r14
0x180025a03  mov     ecx, esi; unsigned int
0x180025a05  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180025a0a  cmp     eax, esi
0x180025a0c  lea     r9, [rbp+57h+string]; string
0x180025a10  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180025a14  lea     rcx, aMicrosoftWhite; "Microsoft.Whiteboard_8wekyb3d8bbwe!Whit"...
0x180025a1b  lea     edx, [rax-1]
0x180025a1e  cmova   edx, esi; length
0x180025a21  call    cs:__imp_WindowsCreateStringReference
0x180025a27  test    eax, eax
0x180025a29  jns     short loc_180025A3D
0x180025a2b  xor     r9d, r9d; lpArguments
0x180025a2e  lea     edx, [rsi-2Ch]; dwExceptionFlags
0x180025a31  xor     r8d, r8d; nNumberOfArguments
0x180025a34  mov     ecx, eax; dwExceptionCode
0x180025a36  call    cs:__imp_RaiseException
0x180025a3c  int     3; Trap to Debugger
0x180025a3d  mov     rdx, [rbp+57h+string]
0x180025a41  lea     r8, [rbp+57h+var_78]
0x180025a45  mov     rax, [rdi+80h]
0x180025a4c  mov     rcx, rbx
0x180025a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a54  mov     ebx, eax
0x180025a56  test    eax, eax
0x180025a58  js      loc_180025B54
0x180025a5e  mov     rcx, [rbp+57h+var_78]
0x180025a62  lea     rdx, [rbp+57h+var_80]
0x180025a66  mov     [rbp+57h+var_80], r14d
0x180025a6a  mov     rax, [rcx]
0x180025a6d  mov     rax, [rax+38h]
0x180025a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a76  mov     ebx, eax
0x180025a78  test    eax, eax
0x180025a7a  js      loc_180025B54
0x180025a80  cmp     [rbp+57h+var_80], 1
0x180025a84  jnz     loc_180025B54
0x180025a8a  mov     rdi, [rbp+57h+var_78]
0x180025a8e  lea     rcx, [rbp+57h+var_58]
0x180025a92  mov     [rbp+57h+var_58], r14
0x180025a96  mov     rax, [rdi]
0x180025a99  mov     rbx, [rax+30h]
0x180025a9d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180025aa2  lea     r8, [rbp+57h+var_58]
0x180025aa6  xor     edx, edx
0x180025aa8  mov     rcx, rdi
0x180025aab  mov     rax, rbx
0x180025aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ab3  mov     ebx, eax
0x180025ab5  test    eax, eax
0x180025ab7  js      loc_180025B4B
0x180025abd  mov     rdi, [rbp+57h+var_58]
0x180025ac1  lea     rcx, [rbp+57h+var_60]
0x180025ac5  mov     [rbp+57h+var_60], r14
0x180025ac9  mov     rax, [rdi]
0x180025acc  mov     rbx, [rax+48h]
0x180025ad0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025ad5  lea     rdx, [rbp+57h+var_60]
0x180025ad9  mov     rcx, rdi
0x180025adc  mov     rax, rbx
0x180025adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ae4  mov     ebx, eax
0x180025ae6  test    eax, eax
0x180025ae8  js      short loc_180025B42
0x180025aea  mov     rdi, [rbp+57h+var_60]
0x180025aee  xor     ecx, ecx; string
0x180025af0  mov     [rbp+57h+var_68], r14
0x180025af4  mov     rax, [rdi]
0x180025af7  mov     rbx, [rax+70h]
0x180025afb  call    cs:__imp_WindowsDeleteString
0x180025b01  lea     rdx, [rbp+57h+var_68]
0x180025b05  mov     [rbp+57h+var_68], r14
0x180025b09  mov     rcx, rdi
0x180025b0c  mov     rax, rbx
0x180025b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b14  mov     ebx, eax
0x180025b16  test    eax, eax
0x180025b18  js      short loc_180025B38
0x180025b1a  mov     rcx, [rbp+57h+var_68]; string
0x180025b1e  xor     edx, edx; length
0x180025b20  call    cs:__imp_WindowsGetStringRawBuffer
0x180025b26  xor     r9d, r9d; bool
0x180025b29  lea     rdx, aMicrosoftWhite; "Microsoft.Whiteboard_8wekyb3d8bbwe!Whit"...
0x180025b30  mov     r8, rax; unsigned __int16 *
0x180025b33  call    ?NotifyDefaultApp@CApplicationPreLaunchNotifications@@AEAAXPEBG0_N@Z; CApplicationPreLaunchNotifications::NotifyDefaultApp(ushort const *,ushort const *,bool)
0x180025b38  mov     rcx, [rbp+57h+var_68]; string
0x180025b3c  call    cs:__imp_WindowsDeleteString
0x180025b42  lea     rcx, [rbp+57h+var_60]
0x180025b46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180025b4b  lea     rcx, [rbp+57h+var_58]
0x180025b4f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180025b54  mov     rcx, [rbp+57h+var_78]
0x180025b58  test    rcx, rcx
0x180025b5b  jz      short loc_180025B6D
0x180025b5d  mov     [rbp+57h+var_78], r14
0x180025b61  mov     rax, [rcx]
0x180025b64  mov     rax, [rax+10h]
0x180025b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b6d  mov     rcx, [rbp+57h+var_50]
0x180025b71  test    rcx, rcx
0x180025b74  jz      short loc_180025B86
0x180025b76  mov     [rbp+57h+var_50], r14
0x180025b7a  mov     rax, [rcx]
0x180025b7d  mov     rax, [rax+10h]
0x180025b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b86  mov     eax, ebx
0x180025b88  mov     rcx, [rbp+57h+var_28]
0x180025b8c  xor     rcx, rsp; StackCookie
0x180025b8f  call    __security_check_cookie
0x180025b94  add     rsp, 0A0h
0x180025b9b  pop     r14
0x180025b9d  pop     rdi
0x180025b9e  pop     rsi
0x180025b9f  pop     rbx
0x180025ba0  pop     rbp
0x180025ba1  retn
```
