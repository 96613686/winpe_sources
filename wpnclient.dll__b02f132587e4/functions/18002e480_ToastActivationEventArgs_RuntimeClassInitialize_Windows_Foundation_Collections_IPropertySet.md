# ToastActivationEventArgs::RuntimeClassInitialize(Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18002e480`
- end: `0x18002e74d`
- name: `?RuntimeClassInitialize@ToastActivationEventArgs@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `717`
- prototype: `__int64 __fastcall(ToastActivationEventArgs *__hidden this, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800277b0`

## callees

- `0x180005670`
- `0x1800070e8`
- `0x180010a54`
- `0x180014440`
- `0x18001478c`
- `0x18001ff00`
- `0x18002e140`
- `0x18002e480`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e5fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e5fb`

## string_xrefs

- `0x18002e4bf`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18002e50f`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18002e584`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18002e5c4`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`
- `0x18002e6bf`: `onecoreuap\base\diagnosis\platform\notifications\client\toastactivationplugin\src\toastactivationeventargs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ToastActivationEventArgs::RuntimeClassInitialize(
        HSTRING *this,
        struct Windows::Foundation::Collections::IPropertySet *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall *v6)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rdi
  __int64 v15; // rdi
  int (__fastcall *v16)(__int64, __int64, _QWORD); // rbx
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rdi
  int v19; // eax
  __int64 v21; // [rsp+20h] [rbp-50h] BYREF
  __int64 v22; // [rsp+28h] [rbp-48h] BYREF
  __int64 v23; // [rsp+30h] [rbp-40h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-38h] BYREF
  __int64 v25; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v27; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v4 = CActivatedEventArgsWithViewIdBase::RuntimeClassInitialize((CActivatedEventArgsWithViewIdBase *)(this + 2), a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v25 = 0;
    v6 = **(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, __int64 *))a2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    v7 = v6(a2, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v25);
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastact"
                      "ivationeventargs.cpp",
        (const char *)(unsigned int)v7,
        v21);
LABEL_19:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      return v5;
    }
    v21 = 0;
    v8 = v25;
    v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v25 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    v27 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Arguments", 0xAu, 9u);
    v10 = v9(v8, v27, &v21);
    v5 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastact"
                      "ivationeventargs.cpp",
        (const char *)(unsigned int)v10,
        v21);
LABEL_7:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      goto LABEL_19;
    }
    v22 = 0;
    v11 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v21, &v22);
    v5 = v11;
    if ( v11 >= 0 )
    {
      v13 = v22;
      v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 152LL);
      WindowsDeleteString(this[34]);
      this[34] = 0;
      v11 = v14(v13, this + 34);
      v5 = v11;
      if ( v11 >= 0 )
      {
        v24 = 0;
        v15 = v25;
        v16 = *(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v25 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
        v27 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserInput", 0xAu, 9u);
        if ( v16(v15, v27, &v24) >= 0 )
        {
          v23 = 0;
          v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v24;
          v18 = **v24;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
          v19 = v18(v17, &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &v23);
          v5 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4A,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\to"
                            "astactivationeventargs.cpp",
              (const char *)(unsigned int)v19,
              v21);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
            goto LABEL_11;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::operator=(this + 35, &v23);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
        v5 = 0;
        goto LABEL_19;
      }
      v12 = 68;
    }
    else
    {
      v12 = 67;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastactiv"
                    "ationeventargs.cpp",
      (const char *)(unsigned int)v11,
      v21);
LABEL_11:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    goto LABEL_7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3B,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\toastactivationplugin\\src\\toastactivat"
                  "ioneventargs.cpp",
    (const char *)(unsigned int)v4,
    v21);
  return v5;
}

```

## disassembly

```asm
0x18002e480  mov     [rsp-18h+arg_10], rbx
0x18002e485  mov     [rsp-18h+arg_18], rsi
0x18002e48a  push    rbp
0x18002e48b  push    rdi
0x18002e48c  push    r14
0x18002e48e  mov     rbp, rsp
0x18002e491  sub     rsp, 70h
0x18002e495  mov     rax, cs:__security_cookie
0x18002e49c  xor     rax, rsp
0x18002e49f  mov     [rbp+var_8], rax
0x18002e4a3  mov     rdi, rdx
0x18002e4a6  mov     r14, rcx
0x18002e4a9  add     rcx, 10h; this
0x18002e4ad  call    ?RuntimeClassInitialize@CActivatedEventArgsWithViewIdBase@@QEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; CActivatedEventArgsWithViewIdBase::RuntimeClassInitialize(Windows::Foundation::Collections::IPropertySet *)
0x18002e4b2  mov     ebx, eax
0x18002e4b4  test    eax, eax
0x18002e4b6  jns     short loc_18002E4D5
0x18002e4b8  mov     rcx, [rbp+18h]; this
0x18002e4bc  mov     r9d, eax; char *
0x18002e4bf  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e4c6  mov     edx, 3Bh ; ';'; void *
0x18002e4cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e4d0  jmp     loc_18002E72A
0x18002e4d5  mov     [rbp+var_30], 0
0x18002e4dd  mov     rax, [rdi]
0x18002e4e0  mov     rbx, [rax]
0x18002e4e3  lea     rcx, [rbp+var_30]
0x18002e4e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e4ec  lea     r8, [rbp+var_30]
0x18002e4f0  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18002e4f7  mov     rcx, rdi
0x18002e4fa  mov     rax, rbx
0x18002e4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e502  mov     ebx, eax
0x18002e504  test    eax, eax
0x18002e506  jns     short loc_18002E525
0x18002e508  mov     rcx, [rbp+18h]; this
0x18002e50c  mov     r9d, eax; char *
0x18002e50f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e516  mov     edx, 3Eh ; '>'; void *
0x18002e51b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e520  jmp     loc_18002E721
0x18002e525  mov     [rbp+var_50], 0
0x18002e52d  mov     rdi, [rbp+var_30]
0x18002e531  mov     rax, [rdi]
0x18002e534  mov     rbx, [rax+30h]
0x18002e538  lea     rcx, [rbp+var_50]
0x18002e53c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e541  mov     [rbp+var_10], 0
0x18002e549  mov     r9d, 9; unsigned int
0x18002e54f  lea     r8d, [r9+1]; unsigned int
0x18002e553  lea     rdx, aArguments_0; "Arguments"
0x18002e55a  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002e55e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002e563  nop
0x18002e564  lea     r8, [rbp+var_50]
0x18002e568  mov     rdx, [rbp+var_10]
0x18002e56c  mov     rcx, rdi
0x18002e56f  mov     rax, rbx
0x18002e572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e577  mov     ebx, eax
0x18002e579  test    eax, eax
0x18002e57b  jns     short loc_18002E5A4
0x18002e57d  mov     rcx, [rbp+18h]; this
0x18002e581  mov     r9d, eax; char *
0x18002e584  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e58b  mov     edx, 41h ; 'A'; void *
0x18002e590  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e595  nop
0x18002e596  lea     rcx, [rbp+var_50]
0x18002e59a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e59f  jmp     loc_18002E721
0x18002e5a4  mov     [rbp+var_48], 0
0x18002e5ac  lea     rdx, [rbp+var_48]
0x18002e5b0  lea     rcx, [rbp+var_50]
0x18002e5b4  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18002e5b9  mov     ebx, eax
0x18002e5bb  test    eax, eax
0x18002e5bd  jns     short loc_18002E5E3
0x18002e5bf  mov     edx, 43h ; 'C'; void *
0x18002e5c4  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e5cb  mov     r9d, eax; char *
0x18002e5ce  mov     rcx, [rbp+18h]; this
0x18002e5d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e5d7  nop
0x18002e5d8  lea     rcx, [rbp+var_48]
0x18002e5dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e5e1  jmp     short loc_18002E596
0x18002e5e3  mov     rsi, [rbp+var_48]
0x18002e5e7  mov     rax, [rsi]
0x18002e5ea  mov     rdi, [rax+98h]
0x18002e5f1  lea     rbx, [r14+110h]
0x18002e5f8  mov     rcx, [rbx]; string
0x18002e5fb  call    cs:__imp_WindowsDeleteString
0x18002e601  mov     qword ptr [rbx], 0
0x18002e608  mov     rdx, rbx
0x18002e60b  mov     rcx, rsi
0x18002e60e  mov     rax, rdi
0x18002e611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e616  mov     ebx, eax
0x18002e618  test    eax, eax
0x18002e61a  jns     short loc_18002E623
0x18002e61c  mov     edx, 44h ; 'D'
0x18002e621  jmp     short loc_18002E5C4
0x18002e623  mov     [rbp+var_38], 0
0x18002e62b  mov     rdi, [rbp+var_30]
0x18002e62f  mov     rax, [rdi]
0x18002e632  mov     rbx, [rax+30h]
0x18002e636  lea     rcx, [rbp+var_38]
0x18002e63a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e63f  mov     [rbp+var_10], 0
0x18002e647  mov     r9d, 9; unsigned int
0x18002e64d  lea     r8d, [r9+1]; unsigned int
0x18002e651  lea     rdx, aUserinput; "UserInput"
0x18002e658  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002e65c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002e661  nop
0x18002e662  lea     r8, [rbp+var_38]
0x18002e666  mov     rdx, [rbp+var_10]
0x18002e66a  mov     rcx, rdi
0x18002e66d  mov     rax, rbx
0x18002e670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e675  nop
0x18002e676  shr     eax, 1Fh
0x18002e679  xor     al, 1
0x18002e67b  jz      loc_18002E702
0x18002e681  mov     [rbp+var_40], 0
0x18002e689  mov     rbx, [rbp+var_38]
0x18002e68d  mov     rax, [rbx]
0x18002e690  mov     rdi, [rax]
0x18002e693  lea     rcx, [rbp+var_40]
0x18002e697  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e69c  lea     r8, [rbp+var_40]
0x18002e6a0  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x18002e6a7  mov     rcx, rbx
0x18002e6aa  mov     rax, rdi
0x18002e6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6b2  mov     ebx, eax
0x18002e6b4  test    eax, eax
0x18002e6b6  jns     short loc_18002E6E8
0x18002e6b8  mov     rcx, [rbp+18h]; this
0x18002e6bc  mov     r9d, eax; char *
0x18002e6bf  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002e6c6  mov     edx, 4Ah ; 'J'; void *
0x18002e6cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e6d0  lea     rcx, [rbp+var_40]
0x18002e6d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e6d9  nop
0x18002e6da  lea     rcx, [rbp+var_38]
0x18002e6de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e6e3  jmp     loc_18002E5D8
0x18002e6e8  lea     rcx, [r14+118h]
0x18002e6ef  lea     rdx, [rbp+var_40]
0x18002e6f3  call    ??4?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::operator=(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> const &)
0x18002e6f8  lea     rcx, [rbp+var_40]
0x18002e6fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e701  nop
0x18002e702  lea     rcx, [rbp+var_38]
0x18002e706  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e70b  nop
0x18002e70c  lea     rcx, [rbp+var_48]
0x18002e710  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e715  nop
0x18002e716  lea     rcx, [rbp+var_50]
0x18002e71a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e71f  xor     ebx, ebx
0x18002e721  lea     rcx, [rbp+var_30]
0x18002e725  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e72a  mov     eax, ebx
0x18002e72c  mov     rcx, [rbp+var_8]
0x18002e730  xor     rcx, rsp; StackCookie
0x18002e733  call    __security_check_cookie
0x18002e738  lea     r11, [rsp+70h+var_s0]
0x18002e73d  mov     rbx, [r11+30h]
0x18002e741  mov     rsi, [r11+38h]
0x18002e745  mov     rsp, r11
0x18002e748  pop     r14
0x18002e74a  pop     rdi
0x18002e74b  pop     rbp
0x18002e74c  retn
```
