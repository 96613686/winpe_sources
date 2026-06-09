# UtilGetFeatureConfigurations(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1802b0ca8`
- end: `0x1802b0f1e`
- name: `?UtilGetFeatureConfigurations@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d819c`

## callees

- `0x1800b2ccc`
- `0x18012de40`
- `0x18012eae4`
- `0x1801aa560`
- `0x1802af84c`
- `0x1802b02a0`
- `0x1802b0ca8`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b0e18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b0e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b0eda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b0e18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b0e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802b0eda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802b0e96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802b0e96`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1802b0efa`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1802b0efa`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1802b0d62`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1802b0d62`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1802b0cca`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1802b0cca`

## string_xrefs

- `0x1802b0d39`: `Windows.Internal.Flighting.FeatureConfiguration.FeatureConfigurationsManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UtilGetFeatureConfigurations(__int64 a1)
{
  int v2; // eax
  int v3; // ebx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, HSTRING *); // rbx
  _QWORD *v6; // rax
  __int64 v7; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v9; // rcx
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  __int64 v12; // [rsp+28h] [rbp-50h] BYREF
  __int64 v13; // [rsp+30h] [rbp-48h] BYREF
  char v14; // [rsp+39h] [rbp-3Fh]
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+58h] [rbp-20h]

  v2 = RoInitialize(1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v14 = 1;
    v16 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Flighting.FeatureConfiguration.FeatureConfigurationsManager",
      0x4Du,
      0x4Cu);
    v12 = 0;
    v13 = 0;
    v3 = RoActivateInstance(v16, &v13);
    if ( v3 >= 0 )
    {
      if ( !memcmp_0(&GUID_f40f94c5_e7db_4ff6_82a3_320f883847ec, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
      {
        v12 = v13;
      }
      else
      {
        v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v13)(
               v13,
               &GUID_f40f94c5_e7db_4ff6_82a3_320f883847ec,
               &v12);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          142,
          &WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
          (unsigned int)v3);
      goto LABEL_25;
    }
    string = 0;
    v4 = v12;
    v5 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v3 = v5(v4, &string);
    if ( v3 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              a1,
                              StringRawBuffer) )
      {
        WindowsDeleteString(string);
        string = 0;
        v3 = 0;
        goto LABEL_25;
      }
      v3 = -2147024882;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_19:
        WindowsDeleteString(string);
        string = 0;
LABEL_25:
        wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v12);
        RoUninitialize(v9);
        return (unsigned int)v3;
      }
      v7 = 144;
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v7 = 143;
    }
    WPP_SF_d(v6[2], v7, &WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, (unsigned int)v3);
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      141,
      &WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
      (unsigned int)v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1802b0ca8  push    rbp
0x1802b0caa  push    rbx
0x1802b0cab  push    rsi
0x1802b0cac  push    rdi
0x1802b0cad  mov     rbp, rsp
0x1802b0cb0  sub     rsp, 78h
0x1802b0cb4  mov     rax, cs:__security_cookie
0x1802b0cbb  xor     rax, rsp
0x1802b0cbe  mov     [rbp+var_18], rax
0x1802b0cc2  mov     rsi, rcx
0x1802b0cc5  mov     ecx, 1
0x1802b0cca  call    cs:__imp_RoInitialize
0x1802b0cd1  nop     dword ptr [rax+rax+00h]
0x1802b0cd6  mov     ebx, eax
0x1802b0cd8  test    eax, eax
0x1802b0cda  jns     short loc_1802B0D1B
0x1802b0cdc  lea     rcx, WPP_GLOBAL_Control
0x1802b0ce3  mov     r10, cs:WPP_GLOBAL_Control
0x1802b0cea  cmp     r10, rcx
0x1802b0ced  jz      loc_1802B0F06
0x1802b0cf3  test    byte ptr [r10+1Ch], 1
0x1802b0cf8  jz      loc_1802B0F06
0x1802b0cfe  mov     edx, 8Dh
0x1802b0d03  mov     r9d, eax
0x1802b0d06  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x1802b0d0d  mov     rcx, [r10+10h]
0x1802b0d11  call    WPP_SF_d
0x1802b0d16  jmp     loc_1802B0F06
0x1802b0d1b  mov     [rbp+var_3F], 1
0x1802b0d1f  mov     [rbp+var_50], 0
0x1802b0d27  mov     [rbp+var_20], 0
0x1802b0d2f  mov     r9d, 4Ch ; 'L'; unsigned int
0x1802b0d35  lea     r8d, [r9+1]; unsigned int
0x1802b0d39  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_FeatureConfiguration_FeatureConfigurationsManager@@3QB_WB; "Windows.Internal.Flighting.FeatureConfi"...
0x1802b0d40  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1802b0d44  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x1802b0d49  nop
0x1802b0d4a  mov     [rbp+var_50], 0
0x1802b0d52  mov     [rbp+var_48], 0
0x1802b0d5a  lea     rdx, [rbp+var_48]
0x1802b0d5e  mov     rcx, [rbp+var_20]
0x1802b0d62  call    cs:__imp_RoActivateInstance
0x1802b0d69  nop     dword ptr [rax+rax+00h]
0x1802b0d6e  mov     ebx, eax
0x1802b0d70  test    eax, eax
0x1802b0d72  js      short loc_1802B0DC8
0x1802b0d74  mov     r8d, 10h; Size
0x1802b0d7a  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1802b0d81  lea     rcx, _GUID_f40f94c5_e7db_4ff6_82a3_320f883847ec; Buf1
0x1802b0d88  call    memcmp_0
0x1802b0d8d  test    eax, eax
0x1802b0d8f  jnz     short loc_1802B0D9B
0x1802b0d91  mov     rax, [rbp+var_48]
0x1802b0d95  mov     [rbp+var_50], rax
0x1802b0d99  jmp     short loc_1802B0DC8
0x1802b0d9b  mov     rcx, [rbp+var_48]
0x1802b0d9f  mov     rax, [rcx]
0x1802b0da2  lea     r8, [rbp+var_50]
0x1802b0da6  lea     rdx, _GUID_f40f94c5_e7db_4ff6_82a3_320f883847ec
0x1802b0dad  mov     rax, [rax]
0x1802b0db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b0db5  mov     ebx, eax
0x1802b0db7  mov     rcx, [rbp+var_48]
0x1802b0dbb  mov     rax, [rcx]
0x1802b0dbe  mov     rax, [rax+10h]
0x1802b0dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b0dc7  nop
0x1802b0dc8  test    ebx, ebx
0x1802b0dca  jns     short loc_1802B0E03
0x1802b0dcc  lea     rcx, WPP_GLOBAL_Control
0x1802b0dd3  mov     rax, cs:WPP_GLOBAL_Control
0x1802b0dda  cmp     rax, rcx
0x1802b0ddd  jz      short loc_1802B0DFE
0x1802b0ddf  test    byte ptr [rax+1Ch], 1
0x1802b0de3  jz      short loc_1802B0DFE
0x1802b0de5  mov     edx, 8Eh
0x1802b0dea  mov     r9d, ebx
0x1802b0ded  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x1802b0df4  mov     rcx, [rax+10h]
0x1802b0df8  call    WPP_SF_d
0x1802b0dfd  nop
0x1802b0dfe  jmp     loc_1802B0EF0
0x1802b0e03  mov     [rbp+string], 0
0x1802b0e0b  mov     rdi, [rbp+var_50]
0x1802b0e0f  mov     rax, [rdi]
0x1802b0e12  mov     rbx, [rax+40h]
0x1802b0e16  xor     ecx, ecx; string
0x1802b0e18  call    cs:__imp_WindowsDeleteString
0x1802b0e1f  nop     dword ptr [rax+rax+00h]
0x1802b0e24  mov     [rbp+string], 0
0x1802b0e2c  lea     rdx, [rbp+string]
0x1802b0e30  mov     rcx, rdi
0x1802b0e33  mov     rax, rbx
0x1802b0e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b0e3b  mov     ebx, eax
0x1802b0e3d  test    eax, eax
0x1802b0e3f  jns     short loc_1802B0E90
0x1802b0e41  lea     rcx, WPP_GLOBAL_Control
0x1802b0e48  mov     rax, cs:WPP_GLOBAL_Control
0x1802b0e4f  cmp     rax, rcx
0x1802b0e52  jz      short loc_1802B0E73
0x1802b0e54  test    byte ptr [rax+1Ch], 1
0x1802b0e58  jz      short loc_1802B0E73
0x1802b0e5a  mov     edx, 8Fh
0x1802b0e5f  mov     r9d, ebx
0x1802b0e62  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x1802b0e69  mov     rcx, [rax+10h]
0x1802b0e6d  call    WPP_SF_d
0x1802b0e72  nop
0x1802b0e73  mov     rcx, [rbp+string]; string
0x1802b0e77  call    cs:__imp_WindowsDeleteString
0x1802b0e7e  nop     dword ptr [rax+rax+00h]
0x1802b0e83  mov     [rbp+string], 0
0x1802b0e8b  jmp     loc_1802B0DFE
0x1802b0e90  xor     edx, edx; length
0x1802b0e92  mov     rcx, [rbp+string]; string
0x1802b0e96  call    cs:__imp_WindowsGetStringRawBuffer
0x1802b0e9d  nop     dword ptr [rax+rax+00h]
0x1802b0ea2  mov     rdx, rax
0x1802b0ea5  mov     rcx, rsi
0x1802b0ea8  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1802b0ead  test    al, al
0x1802b0eaf  jnz     short loc_1802B0ED6
0x1802b0eb1  mov     ebx, 8007000Eh
0x1802b0eb6  lea     rcx, WPP_GLOBAL_Control
0x1802b0ebd  mov     rax, cs:WPP_GLOBAL_Control
0x1802b0ec4  cmp     rax, rcx
0x1802b0ec7  jz      short loc_1802B0E73
0x1802b0ec9  test    byte ptr [rax+1Ch], 1
0x1802b0ecd  jz      short loc_1802B0E73
0x1802b0ecf  mov     edx, 90h
0x1802b0ed4  jmp     short loc_1802B0E5F
0x1802b0ed6  mov     rcx, [rbp+string]; string
0x1802b0eda  call    cs:__imp_WindowsDeleteString
0x1802b0ee1  nop     dword ptr [rax+rax+00h]
0x1802b0ee6  mov     [rbp+string], 0
0x1802b0eee  xor     ebx, ebx
0x1802b0ef0  lea     rcx, [rbp+var_50]
0x1802b0ef4  call    ??1?$com_ptr_t@UIFlightData@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(void)
0x1802b0ef9  nop
0x1802b0efa  call    cs:__imp_RoUninitialize
0x1802b0f01  nop     dword ptr [rax+rax+00h]
0x1802b0f06  mov     eax, ebx
0x1802b0f08  mov     rcx, [rbp+var_18]
0x1802b0f0c  xor     rcx, rsp; StackCookie
0x1802b0f0f  call    __security_check_cookie
0x1802b0f14  add     rsp, 78h
0x1802b0f18  pop     rdi
0x1802b0f19  pop     rsi
0x1802b0f1a  pop     rbx
0x1802b0f1b  pop     rbp
0x1802b0f1c  retn
```
