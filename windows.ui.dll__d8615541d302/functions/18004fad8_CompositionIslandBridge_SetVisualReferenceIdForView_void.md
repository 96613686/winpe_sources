# CompositionIslandBridge::SetVisualReferenceIdForView(void)

- ea: `0x18004fad8`
- end: `0x18004fc29`
- name: `?SetVisualReferenceIdForView@CompositionIslandBridge@@QEAAJXZ`
- size: `337`
- prototype: `__int64 __fastcall(CompositionIslandBridge *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004f9d8`

## callees

- `0x180014754`
- `0x18004fad8`
- `0x18004fc30`
- `0x180050360`
- `0x1800517f0`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004fba9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004fba9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004fb90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004fb90`

## string_xrefs

- `0x18004fb1d`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x18004fb55`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x18004fbc5`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x18004fbfa`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`

## pseudocode

```c
__int64 __fastcall CompositionIslandBridge::SetVisualReferenceIdForView(CompositionIslandBridge *this)
{
  bool v1; // zf
  int v4; // eax
  unsigned int v5; // edi
  int v6; // eax
  int v7; // eax
  int v8; // [rsp+20h] [rbp-48h]
  const char *v9; // [rsp+28h] [rbp-40h]
  __int64 v10; // [rsp+30h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v1 = *((_QWORD *)this + 7) == 0;
  v10 = 0;
  if ( v1 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
      (const char *)0x80070057LL,
      (int)"Island bridge not initialized",
      v9);
    return 2147942487LL;
  }
  else
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 12) + 88LL))(*((_QWORD *)this + 12), &v10);
    v5 = v4;
    if ( v4 >= 0 )
    {
      if ( !*((_QWORD *)this + 14) )
      {
        if ( WindowsCreateStringReference(
               L"Windows.UI.Core.InternalCoordinateConversionStatics",
               0x33u,
               &hstringHeader,
               &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoordinateConversionStatics>>(
               string,
               (char *)this + 112);
        if ( v6 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x150,
            (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
            (const char *)(unsigned int)v6,
            v8);
      }
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 14) + 80LL))(
             *((_QWORD *)this + 14),
             *((unsigned int *)this + 4),
             v10);
      if ( v7 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x155,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
          (const char *)(unsigned int)v7,
          v8);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x149,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v4,
        v8);
      return v5;
    }
  }
}

```

## disassembly

```asm
0x18004fad8  mov     [rsp+arg_8], rbx
0x18004fadd  push    rdi
0x18004fade  sub     rsp, 60h
0x18004fae2  mov     rax, cs:__security_cookie
0x18004fae9  xor     rax, rsp
0x18004faec  mov     [rsp+68h+var_10], rax
0x18004faf1  cmp     qword ptr [rcx+38h], 0
0x18004faf6  mov     rbx, rcx
0x18004faf9  mov     [rsp+68h+var_38], 0
0x18004fb02  jnz     short loc_18004FB35
0x18004fb04  mov     rcx, [rsp+68h]; this
0x18004fb09  lea     rax, aIslandBridgeNo; "Island bridge not initialized"
0x18004fb10  mov     ebx, 80070057h
0x18004fb15  mov     qword ptr [rsp+68h+var_48], rax; int
0x18004fb1a  mov     r9d, ebx; char *
0x18004fb1d  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18004fb24  mov     edx, 147h; void *
0x18004fb29  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004fb2e  mov     eax, ebx
0x18004fb30  jmp     loc_18004FC11
0x18004fb35  mov     rcx, [rcx+60h]
0x18004fb39  lea     rdx, [rsp+68h+var_38]
0x18004fb3e  mov     rax, [rcx]
0x18004fb41  mov     rax, [rax+58h]
0x18004fb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb4a  mov     edi, eax
0x18004fb4c  test    eax, eax
0x18004fb4e  jns     short loc_18004FB70
0x18004fb50  mov     rcx, [rsp+68h]; this
0x18004fb55  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18004fb5c  mov     r9d, eax; char *
0x18004fb5f  mov     edx, 149h; void *
0x18004fb64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004fb69  mov     eax, edi
0x18004fb6b  jmp     loc_18004FC11
0x18004fb70  lea     rdi, [rbx+70h]
0x18004fb74  cmp     qword ptr [rdi], 0
0x18004fb78  jnz     short loc_18004FBDA
0x18004fb7a  lea     r9, [rsp+68h+string]; string
0x18004fb7f  mov     edx, 33h ; '3'; length
0x18004fb84  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x18004fb89  lea     rcx, ?RuntimeClass_Windows_UI_Core_InternalCoordinateConversionStatics@@3QBGB; "Windows.UI.Core.InternalCoordinateConve"...
0x18004fb90  call    cs:__imp_WindowsCreateStringReference
0x18004fb96  test    eax, eax
0x18004fb98  jns     short loc_18004FBAF
0x18004fb9a  xor     r9d, r9d; lpArguments
0x18004fb9d  xor     r8d, r8d; nNumberOfArguments
0x18004fba0  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004fba5  lea     edx, [r9+1]; dwExceptionFlags
0x18004fba9  call    cs:__imp_RaiseException
0x18004fbaf  mov     rcx, [rsp+68h+string]
0x18004fbb4  mov     rdx, rdi
0x18004fbb7  call    ??$GetActivationFactory@V?$ComPtr@UIInternalCoordinateConversionStatics@Core@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIInternalCoordinateConversionStatics@Core@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoordinateConversionStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::IInternalCoordinateConversionStatics>>)
0x18004fbbc  test    eax, eax
0x18004fbbe  jns     short loc_18004FBDA
0x18004fbc0  mov     rcx, [rsp+68h]; this
0x18004fbc5  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18004fbcc  mov     r9d, eax; char *
0x18004fbcf  mov     edx, 150h; void *
0x18004fbd4  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18004fbda  mov     rcx, [rdi]
0x18004fbdd  mov     r8, [rsp+68h+var_38]
0x18004fbe2  mov     edx, [rbx+10h]
0x18004fbe5  mov     rax, [rcx]
0x18004fbe8  mov     rax, [rax+50h]
0x18004fbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbf1  test    eax, eax
0x18004fbf3  jns     short loc_18004FC0F
0x18004fbf5  mov     rcx, [rsp+68h]; this
0x18004fbfa  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18004fc01  mov     r9d, eax; char *
0x18004fc04  mov     edx, 155h; void *
0x18004fc09  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18004fc0f  xor     eax, eax
0x18004fc11  mov     rcx, [rsp+68h+var_10]
0x18004fc16  xor     rcx, rsp; StackCookie
0x18004fc19  call    __security_check_cookie
0x18004fc1e  mov     rbx, [rsp+68h+arg_8]
0x18004fc23  add     rsp, 60h
0x18004fc27  pop     rdi
0x18004fc28  retn
```
