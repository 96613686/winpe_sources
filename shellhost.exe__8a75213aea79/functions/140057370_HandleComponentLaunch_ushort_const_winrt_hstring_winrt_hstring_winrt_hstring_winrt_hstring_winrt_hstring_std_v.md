# HandleComponentLaunch(ushort const *,winrt::hstring &,winrt::hstring &,winrt::hstring &,winrt::hstring &,winrt::hstring &,std::vector<std::pair<winrt::hstring,winrt::hstring>,std::allocator<std::pair<winrt::hstring,winrt::hstring>>> &,std::vector<std::pair<winrt::hstring,int>,std::allocator<std::pair<winrt::hstring,int>>> &,std::vector<std::pair<winrt::hstring,bool>,std::allocator<std::pair<winrt::hstring,bool>>> &)

- ea: `0x140057370`
- end: `0x1400574d7`
- name: `?HandleComponentLaunch@@YAXPEBGAEAUhstring@winrt@@1111AEAV?$vector@U?$pair@Uhstring@winrt@@U12@@std@@V?$allocator@U?$pair@Uhstring@winrt@@U12@@std@@@2@@std@@AEAV?$vector@U?$pair@Uhstring@winrt@@H@std@@V?$allocator@U?$pair@Uhstring@winrt@@H@std@@@2@@4@AEAV?$vector@U?$pair@Uhstring@winrt@@_N@std@@V?$allocator@U?$pair@Uhstring@winrt@@_N@std@@@2@@4@@Z`
- size: `359`
- prototype: `void __fastcall(__int64, struct winrt::hstring *, winrt::hstring *, winrt::hstring *, winrt::hstring *, ValueSetUtils *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14005c9f0`

## callees

- `0x14000a310`
- `0x14004c040`
- `0x140051884`
- `0x1400529c8`
- `0x140052bf8`
- `0x140052e64`
- `0x1400538ac`
- `0x140053948`
- `0x140057370`
- `0x140057e34`
- `0x14005b8bc`
- `0x14005e7d8`

## string_xrefs

- `0x1400573f8`: `UXFrameComponentDefinition`
- `0x1400573a6`: `com.microsoft.windows.extension.shellhost.component`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall HandleComponentLaunch(
        __int64 a1,
        struct winrt::hstring *a2,
        winrt::hstring *a3,
        winrt::hstring *a4,
        winrt::hstring *a5,
        ValueSetUtils *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v16[2]; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v17[3]; // [rsp+68h] [rbp-18h] BYREF
  char v18; // [rsp+A8h] [rbp+28h] BYREF

  v15 = 0;
  if ( !*(_QWORD *)a2 )
    goto LABEL_5;
  winrt::hstring::hstring((winrt::hstring *)v16, L"com.microsoft.windows.extension.shellhost.component");
  ValueSetUtils::TryGetValueSetFromAppExtension(&v18, v16, a2);
  std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(v16);
  v16[0] = 0;
  if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v18, v16) )
  {
    winrt::hstring::hstring((winrt::hstring *)v16, L"UXFrameComponentDefinition");
    v13 = ValueSetUtils::try_get_value<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::Collections::ValueSet>(
            v17,
            v16,
            &v18);
    winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(&v15, v13);
    winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)v17);
    std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(v16);
    winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v18);
LABEL_5:
    v17[0] = L"CommandLine";
    v17[1] = a1;
    std::pair<winrt::hstring,winrt::hstring>::pair<winrt::hstring,winrt::hstring>(v16, v17);
    v14 = a7;
    std::vector<std::pair<winrt::hstring,winrt::hstring>>::push_back(a7, v16);
    std::pair<winrt::hstring,winrt::hstring>::~pair<winrt::hstring,winrt::hstring>(v16);
    LaunchUXFrameAndWait(a2, a3, a4, a5, a6, v14, a8, a9, (__int64)&v15);
    goto LABEL_6;
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v18);
LABEL_6:
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v15);
}

```

## disassembly

```asm
0x140057370  mov     [rsp-18h+arg_0], rbx
0x140057375  mov     [rsp-18h+arg_10], rsi
0x14005737a  push    rbp
0x14005737b  push    rdi
0x14005737c  push    r14
0x14005737e  mov     rbp, rsp
0x140057381  sub     rsp, 80h
0x140057388  mov     rsi, r9
0x14005738b  mov     r14, r8
0x14005738e  mov     rdi, rdx
0x140057391  mov     rbx, rcx
0x140057394  mov     [rbp+var_30], 0
0x14005739c  cmp     qword ptr [rdx], 0
0x1400573a0  jz      loc_140057443
0x1400573a6  lea     rdx, aComMicrosoftWi; "com.microsoft.windows.extension.shellho"...
0x1400573ad  lea     rcx, [rbp+var_28]; this
0x1400573b1  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1400573b6  nop
0x1400573b7  mov     r8, rdi
0x1400573ba  lea     rdx, [rbp+var_28]
0x1400573be  lea     rcx, [rbp+arg_8]
0x1400573c2  call    ?TryGetValueSetFromAppExtension@ValueSetUtils@@YA?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUhstring@6@0@Z; ValueSetUtils::TryGetValueSetFromAppExtension(winrt::hstring const &,winrt::hstring const &)
0x1400573c7  nop
0x1400573c8  lea     rcx, [rbp+var_28]
0x1400573cc  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x1400573d1  mov     [rbp+var_28], 0
0x1400573d9  lea     rdx, [rbp+var_28]
0x1400573dd  lea     rcx, [rbp+arg_8]
0x1400573e1  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1400573e6  test    al, al
0x1400573e8  jz      short loc_1400573F8
0x1400573ea  lea     rcx, [rbp+arg_8]; this
0x1400573ee  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x1400573f3  jmp     loc_1400574B6
0x1400573f8  lea     rdx, aUxframecompone; "UXFrameComponentDefinition"
0x1400573ff  lea     rcx, [rbp+var_28]; this
0x140057403  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x140057408  nop
0x140057409  lea     r8, [rbp+arg_8]
0x14005740d  lea     rdx, [rbp+var_28]
0x140057411  lea     rcx, [rbp+var_18]
0x140057415  call    ??$try_get_value@UValueSet@Collections@Foundation@Windows@winrt@@U12345@@ValueSetUtils@@YA?AUValueSet@Collections@Foundation@Windows@winrt@@AEBUhstring@5@AEBU12345@@Z; ValueSetUtils::try_get_value<winrt::Windows::Foundation::Collections::ValueSet,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x14005741a  mov     rdx, rax
0x14005741d  lea     rcx, [rbp+var_30]
0x140057421  call    ??4?$com_ptr@UIRestrictedErrorInfo@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(winrt::com_ptr<winrt::impl::IRestrictedErrorInfo> &&)
0x140057426  lea     rcx, [rbp+var_18]; this
0x14005742a  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005742f  nop
0x140057430  lea     rcx, [rbp+var_28]
0x140057434  call    ??1?$pair@Uhstring@winrt@@_N@std@@QEAA@XZ; std::pair<winrt::hstring,bool>::~pair<winrt::hstring,bool>(void)
0x140057439  nop
0x14005743a  lea     rcx, [rbp+arg_8]; this
0x14005743e  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140057443  mov     rax, cs:off_14006A540; "CommandLine"
0x14005744a  mov     [rbp+var_18], rax
0x14005744e  mov     [rbp+var_10], rbx
0x140057452  lea     rdx, [rbp+var_18]
0x140057456  lea     rcx, [rbp+var_28]
0x14005745a  call    ??$?0PEBGPEBG$0A@@?$pair@Uhstring@winrt@@U12@@std@@QEAA@$$QEAU?$pair@PEBGPEBG@1@@Z; std::pair<winrt::hstring,winrt::hstring>::pair<winrt::hstring,winrt::hstring>(std::pair<ushort const *,ushort const *> &&)
0x14005745f  nop
0x140057460  lea     rdx, [rbp+var_28]
0x140057464  mov     rbx, [rbp+arg_30]
0x140057468  mov     rcx, rbx
0x14005746b  call    ?push_back@?$vector@U?$pair@Uhstring@winrt@@U12@@std@@V?$allocator@U?$pair@Uhstring@winrt@@U12@@std@@@2@@std@@QEAAX$$QEAU?$pair@Uhstring@winrt@@U12@@2@@Z; std::vector<std::pair<winrt::hstring,winrt::hstring>>::push_back(std::pair<winrt::hstring,winrt::hstring> &&)
0x140057470  nop
0x140057471  lea     rcx, [rbp+var_28]
0x140057475  call    ??1?$pair@Uhstring@winrt@@U12@@std@@QEAA@XZ; std::pair<winrt::hstring,winrt::hstring>::~pair<winrt::hstring,winrt::hstring>(void)
0x14005747a  lea     rax, [rbp+var_30]
0x14005747e  mov     [rsp+80h+var_40], rax; __int64
0x140057483  mov     rax, [rbp+arg_40]
0x140057487  mov     [rsp+80h+var_48], rax; __int64
0x14005748c  mov     rax, [rbp+arg_38]
0x140057490  mov     [rsp+80h+var_50], rax; __int64
0x140057495  mov     [rsp+80h+var_58], rbx; __int64
0x14005749a  mov     rax, [rbp+arg_28]
0x14005749e  mov     [rsp+80h+var_60], rax; ValueSetUtils *
0x1400574a3  mov     r9, [rbp+arg_20]; winrt::hstring *
0x1400574a7  mov     r8, rsi; winrt::hstring *
0x1400574aa  mov     rdx, r14; this
0x1400574ad  mov     rcx, rdi; struct winrt::hstring *
0x1400574b0  call    ?LaunchUXFrameAndWait@@YAXAEBUhstring@winrt@@AEAU12@111AEAV?$vector@U?$pair@Uhstring@winrt@@U12@@std@@V?$allocator@U?$pair@Uhstring@winrt@@U12@@std@@@2@@std@@AEAV?$vector@U?$pair@Uhstring@winrt@@H@std@@V?$allocator@U?$pair@Uhstring@winrt@@H@std@@@2@@4@AEAV?$vector@U?$pair@Uhstring@winrt@@_N@std@@V?$allocator@U?$pair@Uhstring@winrt@@_N@std@@@2@@4@AEBUValueSet@Collections@Foundation@Windows@2@@Z; LaunchUXFrameAndWait(winrt::hstring const &,winrt::hstring &,winrt::hstring &,winrt::hstring &,winrt::hstring &,std::vector<std::pair<winrt::hstring,winrt::hstring>> &,std::vector<std::pair<winrt::hstring,int>> &,std::vector<std::pair<winrt::hstring,bool>> &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x1400574b5  nop
0x1400574b6  lea     rcx, [rbp+var_30]; this
0x1400574ba  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x1400574bf  lea     r11, [rsp+80h+var_s0]
0x1400574c7  mov     rbx, [r11+20h]
0x1400574cb  mov     rsi, [r11+30h]
0x1400574cf  mov     rsp, r11
0x1400574d2  pop     r14
0x1400574d4  pop     rdi
0x1400574d5  pop     rbp
0x1400574d6  retn
```
