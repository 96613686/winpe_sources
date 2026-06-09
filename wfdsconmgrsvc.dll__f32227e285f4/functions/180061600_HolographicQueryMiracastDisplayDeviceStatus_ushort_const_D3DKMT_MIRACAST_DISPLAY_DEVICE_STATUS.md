# HolographicQueryMiracastDisplayDeviceStatus(ushort const *,_D3DKMT_MIRACAST_DISPLAY_DEVICE_STATUS *)

- ea: `0x180061600`
- end: `0x18006170f`
- name: `?HolographicQueryMiracastDisplayDeviceStatus@@YA?AW4D3DKMT_MIRACAST_DEVICE_STATUS@@PEBGPEAU_D3DKMT_MIRACAST_DISPLAY_DEVICE_STATUS@@@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180042ca0`

## callees

- `0x180002600`
- `0x180061584`
- `0x1800615c0`
- `0x180061600`
- `0x180061938`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006166c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006166c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800616d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800616d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180061656`

## pseudocode

```c
__int64 __fastcall HolographicQueryMiracastDisplayDeviceStatus(__int64 a1, _DWORD *a2)
{
  unsigned int v3; // ebx
  HRESULT v4; // eax
  int v6; // [rsp+30h] [rbp-50h] BYREF
  __int64 v7; // [rsp+38h] [rbp-48h] BYREF
  HSTRING v8; // [rsp+40h] [rbp-40h] BYREF
  __int64 v9; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF

  v7 = a1;
  v3 = -2147483647;
  v9 = 0;
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
  v8 = 0;
  if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>>(
              (__int64)string,
              (__int64)&v9) < 0
    || (int)Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v8, &v7) < 0
    || (LODWORD(v7) = 0,
        (*(int (__fastcall **)(__int64, HSTRING, __int64 *, int *))(*(_QWORD *)v9 + 64LL))(v9, v8, &v7, &v6) < 0) )
  {
    v6 = -2147483647;
  }
  else
  {
    v3 = v6;
    *a2 = v7;
  }
  WindowsDeleteString(v8);
  v8 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>::InternalRelease(&v9);
  return v3;
}

```

## disassembly

```asm
0x180061600  mov     [rsp-8+arg_10], rbx
0x180061605  mov     [rsp-8+arg_18], rdi
0x18006160a  push    rbp
0x18006160b  mov     rbp, rsp
0x18006160e  sub     rsp, 80h
0x180061615  mov     rax, cs:__security_cookie
0x18006161c  xor     rax, rsp
0x18006161f  mov     [rbp+var_10], rax
0x180061623  mov     rdi, rdx
0x180061626  mov     [rbp+var_48], rcx
0x18006162a  mov     ebx, 80000001h
0x18006162f  mov     [rbp+var_38], 0
0x180061637  mov     edx, 40h ; '@'; length
0x18006163c  mov     [rbp+var_50], ebx
0x18006163f  lea     rcx, ?RuntimeClass_Windows_Internal_Holographic_Miracast_HolographicMiracastControl@@3QBGB; "Windows.Internal.Holographic.Miracast.H"...
0x180061646  mov     [rbp+string], 0
0x18006164e  lea     r9, [rbp+string]; string
0x180061652  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180061656  call    cs:__imp_WindowsCreateStringReference
0x18006165c  test    eax, eax
0x18006165e  jns     short loc_180061673
0x180061660  xor     r9d, r9d; lpArguments
0x180061663  xor     r8d, r8d; nNumberOfArguments
0x180061666  mov     ecx, eax; dwExceptionCode
0x180061668  lea     edx, [r9+1]; dwExceptionFlags
0x18006166c  call    cs:__imp_RaiseException
0x180061672  int     3; Trap to Debugger
0x180061673  mov     rcx, [rbp+string]
0x180061677  lea     rdx, [rbp+var_38]
0x18006167b  call    ??$GetActivationFactory@V?$ComPtr@UIHolographicMiracastControlStatics@Miracast@Holographic@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIHolographicMiracastControlStatics@Miracast@Holographic@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>>)
0x180061680  mov     [rbp+var_40], 0
0x180061688  test    eax, eax
0x18006168a  js      short loc_1800616CE
0x18006168c  lea     rdx, [rbp+var_48]
0x180061690  lea     rcx, [rbp+var_40]
0x180061694  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180061699  test    eax, eax
0x18006169b  js      short loc_1800616CE
0x18006169d  mov     rcx, [rbp+var_38]
0x1800616a1  lea     r9, [rbp+var_50]
0x1800616a5  mov     rdx, [rbp+var_40]
0x1800616a9  lea     r8, [rbp+var_48]
0x1800616ad  mov     dword ptr [rbp+var_48], 0
0x1800616b4  mov     rax, [rcx]
0x1800616b7  mov     rax, [rax+40h]
0x1800616bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800616c0  test    eax, eax
0x1800616c2  js      short loc_1800616CE
0x1800616c4  mov     eax, dword ptr [rbp+var_48]
0x1800616c7  mov     ebx, [rbp+var_50]
0x1800616ca  mov     [rdi], eax
0x1800616cc  jmp     short loc_1800616D1
0x1800616ce  mov     [rbp+var_50], ebx
0x1800616d1  mov     rcx, [rbp+var_40]; string
0x1800616d5  call    cs:__imp_WindowsDeleteString
0x1800616db  lea     rcx, [rbp+var_38]
0x1800616df  mov     [rbp+var_40], 0
0x1800616e7  call    ?InternalRelease@?$ComPtr@UIHolographicMiracastControlStatics@Miracast@Holographic@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Holographic::Miracast::IHolographicMiracastControlStatics>::InternalRelease(void)
0x1800616ec  mov     eax, ebx
0x1800616ee  mov     rcx, [rbp+var_10]
0x1800616f2  xor     rcx, rsp; StackCookie
0x1800616f5  call    __security_check_cookie
0x1800616fa  lea     r11, [rsp+80h+var_s0]
0x180061702  mov     rbx, [r11+20h]
0x180061706  mov     rdi, [r11+28h]
0x18006170a  mov     rsp, r11
0x18006170d  pop     rbp
0x18006170e  retn
```
