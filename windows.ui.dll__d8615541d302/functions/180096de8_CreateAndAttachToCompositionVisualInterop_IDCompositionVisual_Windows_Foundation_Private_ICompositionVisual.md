# CreateAndAttachToCompositionVisualInterop(IDCompositionVisual *,Windows::Foundation::Private::ICompositionVisual * *)

- ea: `0x180096de8`
- end: `0x180096efe`
- name: `?CreateAndAttachToCompositionVisualInterop@@YAJPEAUIDCompositionVisual@@PEAPEAUICompositionVisual@Private@Foundation@Windows@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(struct IDCompositionVisual *, struct Windows::Foundation::Private::ICompositionVisual **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180059c90`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x180051bc8`
- `0x180051c18`
- `0x180096de8`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180096e4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180096e4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180096e36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180096e36`

## string_xrefs

- `0x180096e2f`: `Windows.Foundation.Private.CompositionVisual`
- `0x180096e8e`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\componenthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CreateAndAttachToCompositionVisualInterop(
        struct IDCompositionVisual *a1,
        struct Windows::Foundation::Private::ICompositionVisual **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  struct Windows::Foundation::Private::ICompositionVisual *v7; // rax
  struct Windows::Foundation::Private::ICompositionVisual *v9; // [rsp+20h] [rbp-40h] BYREF
  __int64 v10; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v9 = 0;
  v10 = 0;
  *a2 = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.Private.CompositionVisual", 0x2Cu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICompositionVisual>>(
         string,
         &v9);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v4 = Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICompositionVisual>::As<IDCompositionVisualInterop>(
           &v9,
           &v10);
    v5 = v4;
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, struct IDCompositionVisual *))(*(_QWORD *)v10 + 32LL))(v10, a1);
      v5 = v4;
      if ( v4 >= 0 )
      {
        v7 = v9;
        v9 = 0;
        *a2 = v7;
        v5 = 0;
        goto LABEL_11;
      }
      v6 = 365;
    }
    else
    {
      v6 = 364;
    }
  }
  else
  {
    v6 = 363;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\componenthelper.cpp",
    (const char *)(unsigned int)v4,
    (int)v9);
LABEL_11:
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v10);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v9);
  return v5;
}

```

## disassembly

```asm
0x180096de8  mov     [rsp-18h+arg_10], rbx
0x180096ded  push    rbp
0x180096dee  push    rsi
0x180096def  push    rdi
0x180096df0  mov     rbp, rsp
0x180096df3  sub     rsp, 60h
0x180096df7  mov     rax, cs:__security_cookie
0x180096dfe  xor     rax, rsp
0x180096e01  mov     [rbp+var_10], rax
0x180096e05  mov     rdi, rdx
0x180096e08  mov     rsi, rcx
0x180096e0b  mov     [rbp+var_40], 0
0x180096e13  mov     [rbp+var_38], 0
0x180096e1b  mov     qword ptr [rdx], 0
0x180096e22  lea     r9, [rbp+string]; string
0x180096e26  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180096e2a  mov     edx, 2Ch ; ','; length
0x180096e2f  lea     rcx, ?RuntimeClass_Windows_Foundation_Private_CompositionVisual@@3QBGB; "Windows.Foundation.Private.CompositionV"...
0x180096e36  call    cs:__imp_WindowsCreateStringReference
0x180096e3c  test    eax, eax
0x180096e3e  jns     short loc_180096E55
0x180096e40  xor     r9d, r9d; lpArguments
0x180096e43  xor     r8d, r8d; nNumberOfArguments
0x180096e46  lea     edx, [r9+1]; dwExceptionFlags
0x180096e4a  mov     ecx, 0C000000Dh; dwExceptionCode
0x180096e4f  call    cs:__imp_RaiseException
0x180096e55  lea     rdx, [rbp+var_40]
0x180096e59  mov     rcx, [rbp+string]
0x180096e5d  call    ??$ActivateInstance@V?$ComPtr@UICompositionVisual@Private@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICompositionVisual@Private@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICompositionVisual>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICompositionVisual>>)
0x180096e62  mov     ebx, eax
0x180096e64  test    eax, eax
0x180096e66  jns     short loc_180096E6F
0x180096e68  mov     edx, 16Bh
0x180096e6d  jmp     short loc_180096E87
0x180096e6f  lea     rdx, [rbp+var_38]
0x180096e73  lea     rcx, [rbp+var_40]
0x180096e77  call    ??$As@UIDCompositionVisualInterop@@@?$ComPtr@UICompositionVisual@Private@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDCompositionVisualInterop@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICompositionVisual>::As<IDCompositionVisualInterop>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompositionVisualInterop>>)
0x180096e7c  mov     ebx, eax
0x180096e7e  test    eax, eax
0x180096e80  jns     short loc_180096E9C
0x180096e82  mov     edx, 16Ch; void *
0x180096e87  mov     rcx, [rbp+18h]; this
0x180096e8b  mov     r9d, eax; char *
0x180096e8e  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180096e95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096e9a  jmp     short loc_180096ECD
0x180096e9c  mov     rcx, [rbp+var_38]
0x180096ea0  mov     rax, [rcx]
0x180096ea3  mov     rdx, rsi
0x180096ea6  mov     rax, [rax+20h]
0x180096eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096eaf  mov     ebx, eax
0x180096eb1  test    eax, eax
0x180096eb3  jns     short loc_180096EBC
0x180096eb5  mov     edx, 16Dh
0x180096eba  jmp     short loc_180096E87
0x180096ebc  mov     rax, [rbp+var_40]
0x180096ec0  mov     [rbp+var_40], 0
0x180096ec8  mov     [rdi], rax
0x180096ecb  xor     ebx, ebx
0x180096ecd  lea     rcx, [rbp+var_38]
0x180096ed1  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180096ed6  nop
0x180096ed7  lea     rcx, [rbp+var_40]
0x180096edb  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180096ee0  mov     eax, ebx
0x180096ee2  mov     rcx, [rbp+var_10]
0x180096ee6  xor     rcx, rsp; StackCookie
0x180096ee9  call    __security_check_cookie
0x180096eee  mov     rbx, [rsp+60h+arg_10]
0x180096ef6  add     rsp, 60h
0x180096efa  pop     rdi
0x180096efb  pop     rsi
0x180096efc  pop     rbp
0x180096efd  retn
```
