# CompositionIslandBridge::ConnectVisual(void)

- ea: `0x1800500bc`
- end: `0x18005035a`
- name: `?ConnectVisual@CompositionIslandBridge@@QEAAXXZ`
- size: `670`
- prototype: `void __fastcall(CompositionIslandBridge *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180059a00`

## callees

- `0x1800038e0`
- `0x18002eaa0`
- `0x1800500bc`
- `0x180050360`
- `0x180051568`
- `0x180051750`
- `0x1800518cc`
- `0x180051bc8`
- `0x180051c18`
- `0x1800c73c0`
- `0x1800ca010`

## string_xrefs

- `0x180050130`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050162`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050193`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x1800501ca`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x1800501fc`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x18005022d`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050252`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x1800502a1`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x1800502d5`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050302`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\compositionislandbridge.cpp`
- `0x180050108`: `Windows.Foundation.Private.CompositionVisual`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CompositionIslandBridge::ConnectVisual(CompositionIslandBridge *this)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int CoreApplicationViewOfCurrentThread; // eax
  int v6; // eax
  int v7; // eax
  int InputSink; // eax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // [rsp+20h] [rbp-58h] BYREF
  struct Windows::ApplicationModel::Core::ICoreApplicationView *v15; // [rsp+28h] [rbp-50h] BYREF
  __int64 v16; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+38h] [rbp-40h] BYREF
  __int64 v18; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  __int64 v20; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  if ( *((_BYTE *)this + 21) && *((_QWORD *)this + 5) )
  {
    v16 = 0;
    v20 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.Private.CompositionVisual",
      0x2Du,
      0x2Cu);
    v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICompositionVisual>>(
           v20,
           &v16);
    if ( v2 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v2,
        v14);
    v18 = 0;
    v3 = Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICompositionVisual>::As<IDCompositionVisualInterop>(
           &v16,
           &v18);
    if ( v3 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v3,
        v14);
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 32LL))(v18, *((_QWORD *)this + 5));
    if ( v4 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v4,
        v14);
    v15 = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v15);
    CoreApplicationViewOfCurrentThread = GetCoreApplicationViewOfCurrentThread(&v15);
    if ( CoreApplicationViewOfCurrentThread < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)CoreApplicationViewOfCurrentThread,
        v14);
    v17 = 0;
    v6 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationView>::As<Windows::Foundation::Private::ICoreApplicationView4>(
           &v15,
           &v17);
    if ( v6 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x60,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v6,
        v14);
    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 56LL))(v17, v16);
    if ( v7 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v7,
        v14);
    InputSink = CompositionIslandBridge::CreateInputSink(this);
    if ( InputSink < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)InputSink,
        v14);
    v14 = 0;
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
    v10 = **v9;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v14);
    v11 = v10(v9, &GUID_2c4eef28_1bc0_4736_b7dd_b62692f9bd67, &v14);
    if ( v11 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v11,
        v14);
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 280LL))(v14, *((_QWORD *)this + 1));
    if ( v12 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v12,
        v14);
    v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 24LL))(*((_QWORD *)this + 4));
    if ( v13 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\compositionislandbridge.cpp",
        (const char *)(unsigned int)v13,
        v14);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v14);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v17);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v15);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v18);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v16);
  }
}

```

## disassembly

```asm
0x1800500bc  push    rbp
0x1800500be  push    rbx
0x1800500bf  push    rsi
0x1800500c0  push    rdi
0x1800500c1  mov     rbp, rsp
0x1800500c4  sub     rsp, 78h
0x1800500c8  mov     rax, cs:__security_cookie
0x1800500cf  xor     rax, rsp
0x1800500d2  mov     [rbp+var_10], rax
0x1800500d6  mov     rsi, rcx
0x1800500d9  cmp     byte ptr [rcx+15h], 0
0x1800500dd  jz      loc_180050345
0x1800500e3  cmp     qword ptr [rcx+28h], 0
0x1800500e8  jz      loc_180050345
0x1800500ee  mov     [rbp+var_48], 0
0x1800500f6  mov     [rbp+var_18], 0
0x1800500fe  mov     r9d, 2Ch ; ','; unsigned int
0x180050104  lea     r8d, [r9+1]; unsigned int
0x180050108  lea     rdx, ?RuntimeClass_Windows_Foundation_Private_CompositionVisual@@3QBGB; "Windows.Foundation.Private.CompositionV"...
0x18005010f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180050113  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180050118  lea     rdx, [rbp+var_48]
0x18005011c  mov     rcx, [rbp+var_18]
0x180050120  call    ??$ActivateInstance@V?$ComPtr@UICompositionVisual@Private@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICompositionVisual@Private@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICompositionVisual>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICompositionVisual>>)
0x180050125  mov     rcx, [rbp+20h]; this
0x180050129  test    eax, eax
0x18005012b  jns     short loc_180050142
0x18005012d  mov     r9d, eax; char *
0x180050130  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050137  mov     edx, 56h ; 'V'; void *
0x18005013c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050142  mov     [rbp+var_38], 0
0x18005014a  lea     rdx, [rbp+var_38]
0x18005014e  lea     rcx, [rbp+var_48]
0x180050152  call    ??$As@UIDCompositionVisualInterop@@@?$ComPtr@UICompositionVisual@Private@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDCompositionVisualInterop@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICompositionVisual>::As<IDCompositionVisualInterop>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompositionVisualInterop>>)
0x180050157  mov     rcx, [rbp+20h]; this
0x18005015b  test    eax, eax
0x18005015d  jns     short loc_180050174
0x18005015f  mov     r9d, eax; char *
0x180050162  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050169  mov     edx, 58h ; 'X'; void *
0x18005016e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050174  mov     rcx, [rbp+var_38]
0x180050178  mov     rax, [rcx]
0x18005017b  mov     rdx, [rsi+28h]
0x18005017f  mov     rax, [rax+20h]
0x180050183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050188  mov     rcx, [rbp+20h]; this
0x18005018c  test    eax, eax
0x18005018e  jns     short loc_1800501A5
0x180050190  mov     r9d, eax; char *
0x180050193  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18005019a  mov     edx, 5Ah ; 'Z'; void *
0x18005019f  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800501a5  mov     [rbp+var_50], 0
0x1800501ad  lea     rcx, [rbp+var_50]
0x1800501b1  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800501b6  lea     rcx, [rbp+var_50]; struct Windows::ApplicationModel::Core::ICoreApplicationView **
0x1800501ba  call    ?GetCoreApplicationViewOfCurrentThread@@YAJPEAPEAUICoreApplicationView@Core@ApplicationModel@Windows@@@Z; GetCoreApplicationViewOfCurrentThread(Windows::ApplicationModel::Core::ICoreApplicationView * *)
0x1800501bf  mov     rcx, [rbp+20h]; this
0x1800501c3  test    eax, eax
0x1800501c5  jns     short loc_1800501DC
0x1800501c7  mov     r9d, eax; char *
0x1800501ca  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800501d1  mov     edx, 5Dh ; ']'; void *
0x1800501d6  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800501dc  mov     [rbp+var_40], 0
0x1800501e4  lea     rdx, [rbp+var_40]
0x1800501e8  lea     rcx, [rbp+var_50]
0x1800501ec  call    ??$As@UICoreApplicationView4@Private@Foundation@Windows@@@?$ComPtr@UICoreApplicationView@Core@ApplicationModel@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICoreApplicationView4@Private@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationView>::As<Windows::Foundation::Private::ICoreApplicationView4>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Private::ICoreApplicationView4>>)
0x1800501f1  mov     rcx, [rbp+20h]; this
0x1800501f5  test    eax, eax
0x1800501f7  jns     short loc_18005020E
0x1800501f9  mov     r9d, eax; char *
0x1800501fc  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050203  mov     edx, 60h ; '`'; void *
0x180050208  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18005020e  mov     rcx, [rbp+var_40]
0x180050212  mov     rax, [rcx]
0x180050215  mov     rdx, [rbp+var_48]
0x180050219  mov     rax, [rax+38h]
0x18005021d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050222  mov     rcx, [rbp+20h]; this
0x180050226  test    eax, eax
0x180050228  jns     short loc_18005023F
0x18005022a  mov     r9d, eax; char *
0x18005022d  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050234  mov     edx, 62h ; 'b'; void *
0x180050239  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18005023f  mov     rcx, rsi; this
0x180050242  call    ?CreateInputSink@CompositionIslandBridge@@AEAAJXZ; CompositionIslandBridge::CreateInputSink(void)
0x180050247  mov     rcx, [rbp+20h]; this
0x18005024b  test    eax, eax
0x18005024d  jns     short loc_180050264
0x18005024f  mov     r9d, eax; char *
0x180050252  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050259  mov     edx, 64h ; 'd'; void *
0x18005025e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050264  mov     [rbp+var_58], 0
0x18005026c  mov     rdi, [rsi+28h]
0x180050270  mov     rax, [rdi]
0x180050273  mov     rbx, [rax]
0x180050276  lea     rcx, [rbp+var_58]
0x18005027a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005027f  lea     r8, [rbp+var_58]
0x180050283  lea     rdx, _GUID_2c4eef28_1bc0_4736_b7dd_b62692f9bd67
0x18005028a  mov     rcx, rdi
0x18005028d  mov     rax, rbx
0x180050290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050295  nop
0x180050296  mov     rcx, [rbp+20h]; this
0x18005029a  test    eax, eax
0x18005029c  jns     short loc_1800502B3
0x18005029e  mov     r9d, eax; char *
0x1800502a1  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800502a8  mov     edx, 68h ; 'h'; void *
0x1800502ad  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800502b3  mov     rcx, [rbp+var_58]
0x1800502b7  mov     rax, [rcx]
0x1800502ba  mov     rdx, [rsi+8]
0x1800502be  mov     rax, [rax+118h]
0x1800502c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502ca  mov     rcx, [rbp+20h]; this
0x1800502ce  test    eax, eax
0x1800502d0  jns     short loc_1800502E7
0x1800502d2  mov     r9d, eax; char *
0x1800502d5  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800502dc  mov     edx, 6Ah ; 'j'; void *
0x1800502e1  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800502e7  mov     rcx, [rsi+20h]
0x1800502eb  mov     rax, [rcx]
0x1800502ee  mov     rax, [rax+18h]
0x1800502f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502f7  mov     rcx, [rbp+20h]; this
0x1800502fb  test    eax, eax
0x1800502fd  jns     short loc_180050314
0x1800502ff  mov     r9d, eax; char *
0x180050302  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180050309  mov     edx, 6Ch ; 'l'; void *
0x18005030e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180050314  lea     rcx, [rbp+var_58]
0x180050318  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005031d  nop
0x18005031e  lea     rcx, [rbp+var_40]
0x180050322  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050327  nop
0x180050328  lea     rcx, [rbp+var_50]
0x18005032c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050331  nop
0x180050332  lea     rcx, [rbp+var_38]
0x180050336  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18005033b  nop
0x18005033c  lea     rcx, [rbp+var_48]
0x180050340  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180050345  mov     rcx, [rbp+var_10]
0x180050349  xor     rcx, rsp; StackCookie
0x18005034c  call    __security_check_cookie
0x180050351  add     rsp, 78h
0x180050355  pop     rdi
0x180050356  pop     rsi
0x180050357  pop     rbx
0x180050358  pop     rbp
0x180050359  retn
```
