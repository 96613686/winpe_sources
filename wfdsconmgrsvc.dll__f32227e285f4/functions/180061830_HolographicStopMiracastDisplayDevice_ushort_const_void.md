# HolographicStopMiracastDisplayDevice(ushort const *,void *)

- ea: `0x180061830`
- end: `0x180061932`
- name: `?HolographicStopMiracastDisplayDevice@@YA?AW4D3DKMT_MIRACAST_DEVICE_STATUS@@PEBGPEAX@Z`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180043ad0`

## callees

- `0x180002600`
- `0x180061584`
- `0x1800615c0`
- `0x180061830`
- `0x180061938`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006189c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006189c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800618f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800618f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061886`

## pseudocode

```c
__int64 __fastcall HolographicStopMiracastDisplayDevice(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  HRESULT v4; // eax
  int v6; // [rsp+30h] [rbp-50h] BYREF
  HSTRING v7; // [rsp+38h] [rbp-48h] BYREF
  __int64 v8; // [rsp+40h] [rbp-40h] BYREF
  __int64 v9; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF

  v9 = a1;
  v3 = -2147483647;
  v8 = 0;
  v6 = -2147483647;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Internal.Holographic.Miracast.HolographicMiracastControl",
         0x40u,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v7 = 0;
  if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>>(
              (__int64)string,
              (__int64)&v8) < 0
    || (int)Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v7, &v9) < 0
    || (*(int (__fastcall **)(__int64, HSTRING, __int64, int *))(*(_QWORD *)v8 + 56LL))(v8, v7, a2, &v6) < 0 )
  {
    v6 = -2147483647;
  }
  else
  {
    v3 = v6;
  }
  WindowsDeleteString(v7);
  v7 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>::InternalRelease(&v8);
  return v3;
}

```

## disassembly

```asm
0x180061830  mov     [rsp-8+arg_10], rbx
0x180061835  mov     [rsp-8+arg_18], rdi
0x18006183a  push    rbp
0x18006183b  mov     rbp, rsp
0x18006183e  sub     rsp, 80h
0x180061845  mov     rax, cs:__security_cookie
0x18006184c  xor     rax, rsp
0x18006184f  mov     [rbp+var_10], rax
0x180061853  mov     rdi, rdx
0x180061856  mov     [rbp+var_38], rcx
0x18006185a  mov     ebx, 80000001h
0x18006185f  mov     [rbp+var_40], 0
0x180061867  mov     edx, 40h ; '@'; length
0x18006186c  mov     [rbp+var_50], ebx
0x18006186f  lea     rcx, ?RuntimeClass_Windows_Internal_Holographic_Miracast_HolographicMiracastControl@@3QBGB; "Windows.Internal.Holographic.Miracast.H"...
0x180061876  mov     [rbp+string], 0
0x18006187e  lea     r9, [rbp+string]; string
0x180061882  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180061886  call    cs:__imp_WindowsCreateStringReference
0x18006188c  test    eax, eax
0x18006188e  jns     short loc_1800618A3
0x180061890  xor     r9d, r9d; lpArguments
0x180061893  xor     r8d, r8d; nNumberOfArguments
0x180061896  mov     ecx, eax; dwExceptionCode
0x180061898  lea     edx, [r9+1]; dwExceptionFlags
0x18006189c  call    cs:__imp_RaiseException
0x1800618a2  int     3; Trap to Debugger
0x1800618a3  mov     rcx, [rbp+string]
0x1800618a7  lea     rdx, [rbp+var_40]
0x1800618ab  call    ??$GetActivationFactory@V?$ComPtr@UIHolographicMiracastControlStatics@Miracast@Holographic@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIHolographicMiracastControlStatics@Miracast@Holographic@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>>)
0x1800618b0  mov     [rbp+var_48], 0
0x1800618b8  test    eax, eax
0x1800618ba  js      short loc_1800618F1
0x1800618bc  lea     rdx, [rbp+var_38]
0x1800618c0  lea     rcx, [rbp+var_48]
0x1800618c4  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800618c9  test    eax, eax
0x1800618cb  js      short loc_1800618F1
0x1800618cd  mov     rcx, [rbp+var_40]
0x1800618d1  lea     r9, [rbp+var_50]
0x1800618d5  mov     rdx, [rbp+var_48]
0x1800618d9  mov     r8, rdi
0x1800618dc  mov     rax, [rcx]
0x1800618df  mov     rax, [rax+38h]
0x1800618e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800618e8  test    eax, eax
0x1800618ea  js      short loc_1800618F1
0x1800618ec  mov     ebx, [rbp+var_50]
0x1800618ef  jmp     short loc_1800618F4
0x1800618f1  mov     [rbp+var_50], ebx
0x1800618f4  mov     rcx, [rbp+var_48]; string
0x1800618f8  call    cs:__imp_WindowsDeleteString
0x1800618fe  lea     rcx, [rbp+var_40]
0x180061902  mov     [rbp+var_48], 0
0x18006190a  call    ?InternalRelease@?$ComPtr@UIHolographicMiracastControlStatics@Miracast@Holographic@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>::InternalRelease(void)
0x18006190f  mov     eax, ebx
0x180061911  mov     rcx, [rbp+var_10]
0x180061915  xor     rcx, rsp; StackCookie
0x180061918  call    __security_check_cookie
0x18006191d  lea     r11, [rsp+80h+var_s0]
0x180061925  mov     rbx, [r11+20h]
0x180061929  mov     rdi, [r11+28h]
0x18006192d  mov     rsp, r11
0x180061930  pop     rbp
0x180061931  retn
```
