# Windows::UI::ViewManagement::UISettings::EnsureAppThemeAPI(void)

- ea: `0x1800161e0`
- end: `0x180016290`
- name: `?EnsureAppThemeAPI@UISettings@ViewManagement@UI@Windows@@AEAAJXZ`
- size: `176`
- prototype: `__int64 __fastcall(Windows::UI::ViewManagement::UISettings *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015a00`
- `0x180015e94`
- `0x1800160f0`

## callees

- `0x180004dd4`
- `0x1800161e0`
- `0x1800a47e4`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016288`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016236`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016236`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001625a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001625a`

## pseudocode

```c
__int64 __fastcall Windows::UI::ViewManagement::UISettings::EnsureAppThemeAPI(
        Windows::UI::ViewManagement::UISettings *this)
{
  char *v1; // rdi
  __int64 result; // rax
  HSTRING v3; // rbx
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF

  v1 = (char *)this + 264;
  if ( *((_QWORD *)this + 33) )
    return 0;
  if ( WindowsCreateStringReference(L"ApplicationTheme.AppThemeAPI", 0x1Cu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v3 = string;
  Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(v1);
  result = RoGetActivationFactory(v3, &GUID_c5114793_b1f6_5005_bd97_ed6bec1b25f6, v1);
  if ( (_DWORD)result == -2147221164 )
  {
    Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(v1);
    return Microsoft::WRL::Details::MakeAndInitialize<AppThemeAPIPlaceholder,ApplicationTheme::IAppThemeApiStatics,>(v1);
  }
  return result;
}

```

## disassembly

```asm
0x1800161e0  mov     [rsp+arg_8], rbx
0x1800161e5  push    rdi
0x1800161e6  sub     rsp, 50h
0x1800161ea  mov     rax, cs:__security_cookie
0x1800161f1  xor     rax, rsp
0x1800161f4  mov     [rsp+58h+var_18], rax
0x1800161f9  lea     rdi, [rcx+108h]
0x180016200  cmp     qword ptr [rdi], 0
0x180016204  jz      short loc_180016220
0x180016206  xor     eax, eax
0x180016208  mov     rcx, [rsp+58h+var_18]
0x18001620d  xor     rcx, rsp; StackCookie
0x180016210  call    __security_check_cookie
0x180016215  mov     rbx, [rsp+58h+arg_8]
0x18001621a  add     rsp, 50h
0x18001621e  pop     rdi
0x18001621f  retn
0x180016220  lea     r9, [rsp+58h+string]; string
0x180016225  mov     edx, 1Ch; length
0x18001622a  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x18001622f  lea     rcx, ?RuntimeClass_ApplicationTheme_AppThemeAPI@@3QBGB; "ApplicationTheme.AppThemeAPI"
0x180016236  call    cs:__imp_WindowsCreateStringReference
0x18001623c  test    eax, eax
0x18001623e  js      short loc_180016279
0x180016240  mov     rbx, [rsp+58h+string]
0x180016245  mov     rcx, rdi
0x180016248  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x18001624d  mov     r8, rdi
0x180016250  lea     rdx, _GUID_c5114793_b1f6_5005_bd97_ed6bec1b25f6
0x180016257  mov     rcx, rbx
0x18001625a  call    cs:__imp_RoGetActivationFactory
0x180016260  cmp     eax, 80040154h
0x180016265  jnz     short loc_180016208
0x180016267  mov     rcx, rdi
0x18001626a  call    ?InternalRelease@?$ComPtr@VCInteractiveObjectDevice@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CInteractiveObjectDevice>::InternalRelease(void)
0x18001626f  mov     rcx, rdi
0x180016272  call    ??$MakeAndInitialize@VAppThemeAPIPlaceholder@@UIAppThemeApiStatics@ApplicationTheme@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIAppThemeApiStatics@ApplicationTheme@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AppThemeAPIPlaceholder,ApplicationTheme::IAppThemeApiStatics,>(ApplicationTheme::IAppThemeApiStatics * *)
0x180016277  jmp     short loc_180016208
0x180016279  xor     r9d, r9d; lpArguments
0x18001627c  xor     r8d, r8d; nNumberOfArguments
0x18001627f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180016284  lea     edx, [r9+1]; dwExceptionFlags
0x180016288  call    cs:__imp_RaiseException
0x18001628e  jmp     short loc_180016240
```
