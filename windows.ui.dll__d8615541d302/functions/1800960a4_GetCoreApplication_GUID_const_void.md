# GetCoreApplication(_GUID const &,void * *)

- ea: `0x1800960a4`
- end: `0x18009618f`
- name: `?GetCoreApplication@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `235`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180051568`
- `0x180096818`

## callees

- `0x1800038e0`
- `0x180014754`
- `0x1800960a4`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800960f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800960f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800960de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800960de`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009611b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009611b`

## string_xrefs

- `0x180096153`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\helper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCoreApplication(const struct _GUID *a1, void **a2)
{
  HSTRING v3; // rbx
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 (__fastcall ***v8)(_QWORD, GUID *, void **); // [rsp+20h] [rbp-38h] BYREF
  HSTRING v9; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER v10; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = 0;
  if ( WindowsCreateStringReference(L"Windows.ApplicationModel.Core.CoreApplication", 0x2Du, &v10, &v9) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v3 = v9;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v8);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1, &v8);
  v5 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = (**v8)(v8, &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1, a2);
    v5 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v5 = 0;
      goto LABEL_9;
    }
    v6 = 835;
  }
  else
  {
    v6 = 834;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\helper.cpp",
    (const char *)(unsigned int)ActivationFactory,
    (int)v8);
LABEL_9:
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v8);
  return v5;
}

```

## disassembly

```asm
0x1800960a4  mov     r11, rsp
0x1800960a7  mov     [r11+8], rbx
0x1800960ab  push    rdi
0x1800960ac  sub     rsp, 50h
0x1800960b0  mov     rax, cs:__security_cookie
0x1800960b7  xor     rax, rsp
0x1800960ba  mov     [rsp+58h+var_10], rax
0x1800960bf  mov     rdi, rdx
0x1800960c2  mov     qword ptr [r11-38h], 0
0x1800960ca  lea     r9, [r11-30h]; string
0x1800960ce  lea     r8, [r11-28h]; hstringHeader
0x1800960d2  mov     edx, 2Dh ; '-'; length
0x1800960d7  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x1800960de  call    cs:__imp_WindowsCreateStringReference
0x1800960e4  test    eax, eax
0x1800960e6  jns     short loc_1800960FD
0x1800960e8  xor     r9d, r9d; lpArguments
0x1800960eb  xor     r8d, r8d; nNumberOfArguments
0x1800960ee  lea     edx, [r9+1]; dwExceptionFlags
0x1800960f2  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800960f7  call    cs:__imp_RaiseException
0x1800960fd  mov     rbx, [rsp+58h+var_30]
0x180096102  lea     rcx, [rsp+58h+var_38]
0x180096107  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009610c  lea     r8, [rsp+58h+var_38]
0x180096111  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180096118  mov     rcx, rbx
0x18009611b  call    cs:__imp_RoGetActivationFactory
0x180096121  mov     ebx, eax
0x180096123  test    eax, eax
0x180096125  jns     short loc_18009612E
0x180096127  mov     edx, 342h
0x18009612c  jmp     short loc_180096153
0x18009612e  mov     rcx, [rsp+58h+var_38]
0x180096133  mov     rax, [rcx]
0x180096136  mov     r8, rdi
0x180096139  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180096140  mov     rax, [rax]
0x180096143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096148  mov     ebx, eax
0x18009614a  test    eax, eax
0x18009614c  jns     short loc_180096169
0x18009614e  mov     edx, 343h; void *
0x180096153  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18009615a  mov     r9d, eax; char *
0x18009615d  mov     rcx, [rsp+58h]; this
0x180096162  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096167  jmp     short loc_18009616B
0x180096169  xor     ebx, ebx
0x18009616b  lea     rcx, [rsp+58h+var_38]
0x180096170  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180096175  mov     eax, ebx
0x180096177  mov     rcx, [rsp+58h+var_10]
0x18009617c  xor     rcx, rsp; StackCookie
0x18009617f  call    __security_check_cookie
0x180096184  mov     rbx, [rsp+58h+arg_0]
0x180096189  add     rsp, 50h
0x18009618d  pop     rdi
0x18009618e  retn
```
