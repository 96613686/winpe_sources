# _TryUnsnapAppView(void)

- ea: `0x1800135c8`
- end: `0x1800136a0`
- name: `?_TryUnsnapAppView@@YAXXZ`
- size: `216`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011b74`

## callees

- `0x180002610`
- `0x1800043a4`
- `0x1800135c8`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013618`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013618`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800135ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800135ff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013639`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180013639`

## pseudocode

```c
void _TryUnsnapAppView(void)
{
  HSTRING v0; // rbx
  _BYTE v1[4]; // [rsp+20h] [rbp-40h] BYREF
  int v2; // [rsp+24h] [rbp-3Ch] BYREF
  __int64 v3; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF

  v3 = 0;
  if ( WindowsCreateStringReference(L"Windows.UI.ViewManagement.ApplicationView", 0x29u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v0 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v3);
  if ( (int)RoGetActivationFactory(v0, &GUID_010a6306_c433_44e5_a9f2_bd84d4030a95, &v3) >= 0 )
  {
    v2 = 0;
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v3 + 48LL))(v3, &v2) >= 0 && v2 == 2 )
    {
      v1[0] = 0;
      (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v3 + 56LL))(v3, v1);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v3);
}

```

## disassembly

```asm
0x1800135c8  mov     [rsp-8+arg_0], rbx
0x1800135cd  push    rbp
0x1800135ce  mov     rbp, rsp
0x1800135d1  sub     rsp, 60h
0x1800135d5  mov     rax, cs:__security_cookie
0x1800135dc  xor     rax, rsp
0x1800135df  mov     [rbp+var_10], rax
0x1800135e3  lea     r9, [rbp+string]; string
0x1800135e7  mov     [rbp+var_38], 0
0x1800135ef  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800135f3  mov     edx, 29h ; ')'; length
0x1800135f8  lea     rcx, ?RuntimeClass_Windows_UI_ViewManagement_ApplicationView@@3QBGB; "Windows.UI.ViewManagement.ApplicationVi"...
0x1800135ff  call    cs:__imp_WindowsCreateStringReference
0x180013605  test    eax, eax
0x180013607  jns     short loc_18001361E
0x180013609  xor     r9d, r9d; lpArguments
0x18001360c  xor     r8d, r8d; nNumberOfArguments
0x18001360f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180013614  lea     edx, [r9+1]; dwExceptionFlags
0x180013618  call    cs:__imp_RaiseException
0x18001361e  mov     rbx, [rbp+string]
0x180013622  lea     rcx, [rbp+var_38]
0x180013626  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001362b  lea     r8, [rbp+var_38]
0x18001362f  mov     rcx, rbx
0x180013632  lea     rdx, _GUID_010a6306_c433_44e5_a9f2_bd84d4030a95
0x180013639  call    cs:__imp_RoGetActivationFactory
0x18001363f  test    eax, eax
0x180013641  js      short loc_180013680
0x180013643  mov     rcx, [rbp+var_38]
0x180013647  lea     rdx, [rbp+var_3C]
0x18001364b  mov     [rbp+var_3C], 0
0x180013652  mov     rax, [rcx]
0x180013655  mov     rax, [rax+30h]
0x180013659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001365e  test    eax, eax
0x180013660  js      short loc_180013680
0x180013662  cmp     [rbp+var_3C], 2
0x180013666  jnz     short loc_180013680
0x180013668  mov     rcx, [rbp+var_38]
0x18001366c  lea     rdx, [rbp+var_40]
0x180013670  mov     [rbp+var_40], 0
0x180013674  mov     rax, [rcx]
0x180013677  mov     rax, [rax+38h]
0x18001367b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013680  lea     rcx, [rbp+var_38]
0x180013684  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180013689  mov     rcx, [rbp+var_10]
0x18001368d  xor     rcx, rsp; StackCookie
0x180013690  call    __security_check_cookie
0x180013695  mov     rbx, [rsp+60h+arg_0]
0x18001369a  add     rsp, 60h
0x18001369e  pop     rbp
0x18001369f  retn
```
