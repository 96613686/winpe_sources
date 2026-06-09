# Windows::Internal::ShellHelpers::PropertySetHelper::SetUInt32(HSTRING__ *,uint)

- ea: `0x1800ca978`
- end: `0x1800cabfb`
- name: `?SetUInt32@PropertySetHelper@ShellHelpers@Internal@Windows@@QEAAJPEAUHSTRING__@@I@Z`
- size: `643`
- prototype: `__int64 __fastcall(Windows::Internal::ShellHelpers::PropertySetHelper *__hidden this, HSTRING, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800cf920`

## callees

- `0x180008e64`
- `0x180092dd8`
- `0x1800ca89c`
- `0x1800ca978`
- `0x1800d35e8`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ca9c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ca9c0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800ca9dd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800ca9dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Internal::ShellHelpers::PropertySetHelper::SetUInt32(
        Windows::Internal::ShellHelpers::PropertySetHelper *this,
        HSTRING a2,
        unsigned int a3)
{
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int ActivationFactory; // eax
  int v10; // ebx
  __int64 v11; // rcx
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **); // rcx
  __int64 v14; // rcx
  int v15; // eax
  struct ABI::Windows::Foundation::IPropertyValue *v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **); // rcx
  __int64 v18; // rcx
  struct ABI::Windows::Foundation::IPropertyValue *v19; // rcx
  __int64 (__fastcall ***v20)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **); // rcx
  __int64 v21; // rcx
  struct ABI::Windows::Foundation::IPropertyValue *v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **); // rcx
  __int64 v24; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  __int64 v28; // [rsp+40h] [rbp-20h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **); // [rsp+48h] [rbp-18h] BYREF
  struct ABI::Windows::Foundation::IPropertyValue *v30; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v28 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    JUMPOUT(0x1800CABFALL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v28);
  v10 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v29 = 0;
    v12 =  ABI::Windows::Foundation::IPropertyValueStatics::`vcall'{88,{flat}}(v28, a3, &v29);
    v10 = v12;
    if ( v12 >= 0 )
    {
      v30 = 0;
      v15 = (**v29)(v29, &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62, &v30);
      v10 = v15;
      if ( v15 >= 0 )
      {
        v10 = Windows::Internal::ShellHelpers::PropertySetHelper::SetPropVal(this, a2, v30);
        if ( v10 >= 0 )
        {
          v22 = v30;
          if ( v30 )
          {
            v30 = 0;
            (*(void (__fastcall **)(struct ABI::Windows::Foundation::IPropertyValue *))(*(_QWORD *)v22 + 16LL))(v22);
          }
          v23 = v29;
          if ( v29 )
          {
            v29 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **)))(*v23)[2])(v23);
          }
          v24 = v28;
          if ( v28 )
          {
            v28 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          }
          return 0;
        }
        else
        {
          v19 = v30;
          if ( v30 )
          {
            v30 = 0;
            (*(void (__fastcall **)(struct ABI::Windows::Foundation::IPropertyValue *))(*(_QWORD *)v19 + 16LL))(v19);
          }
          v20 = v29;
          if ( v29 )
          {
            v29 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **)))(*v20)[2])(v20);
          }
          v21 = v28;
          if ( v28 )
          {
            v28 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x54,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\External\\PropertySetHelpers.h",
          (const char *)(unsigned int)v15,
          (int)hstringHeader.Reserved.Reserved1);
        v16 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(struct ABI::Windows::Foundation::IPropertyValue *))(*(_QWORD *)v16 + 16LL))(v16);
        }
        v17 = v29;
        if ( v29 )
        {
          v29 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **)))(*v17)[2])(v17);
        }
        v18 = v28;
        if ( v28 )
        {
          v28 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\External\\PropertySetHelpers.h",
        (const char *)(unsigned int)v12,
        (int)hstringHeader.Reserved.Reserved1);
      v13 = v29;
      if ( v29 )
      {
        v29 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct ABI::Windows::Foundation::IPropertyValue **)))(*v13)[2])(v13);
      }
      v14 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\External\\PropertySetHelpers.h",
      (const char *)(unsigned int)ActivationFactory,
      (int)hstringHeader.Reserved.Reserved1);
    v11 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800ca978  mov     [rsp-28h+arg_18], rbx
0x1800ca97d  push    rbp
0x1800ca97e  push    rsi
0x1800ca97f  push    rdi
0x1800ca980  push    r14
0x1800ca982  push    r15
0x1800ca984  mov     rbp, rsp
0x1800ca987  sub     rsp, 60h
0x1800ca98b  mov     rax, cs:__security_cookie
0x1800ca992  xor     rax, rsp
0x1800ca995  mov     [rbp+var_8], rax
0x1800ca999  mov     edi, r8d
0x1800ca99c  mov     r14, rdx
0x1800ca99f  mov     rsi, rcx
0x1800ca9a2  xor     r15d, r15d
0x1800ca9a5  mov     [rbp+var_20], r15
0x1800ca9a9  mov     [rbp+string], r15
0x1800ca9ad  lea     r9, [rbp+string]; string
0x1800ca9b1  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800ca9b5  lea     edx, [r15+20h]; length
0x1800ca9b9  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QB_WB; "Windows.Foundation.PropertyValue"
0x1800ca9c0  call    cs:__imp_WindowsCreateStringReference
0x1800ca9c6  test    eax, eax
0x1800ca9c8  js      loc_1800CABF3
0x1800ca9ce  lea     r8, [rbp+var_20]
0x1800ca9d2  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x1800ca9d9  mov     rcx, [rbp+string]
0x1800ca9dd  call    cs:__imp_RoGetActivationFactory
0x1800ca9e3  mov     ebx, eax
0x1800ca9e5  test    eax, eax
0x1800ca9e7  jns     short loc_1800CAA20
0x1800ca9e9  mov     rcx, [rbp+28h]; this
0x1800ca9ed  mov     r9d, eax; char *
0x1800ca9f0  lea     r8, aCW1SSrcOrchest_46; "C:\\__w\\1\\s\\src\\orchestrator\\Exter"...
0x1800ca9f7  lea     edx, [r15+50h]; void *
0x1800ca9fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800caa00  nop
0x1800caa01  mov     rcx, [rbp+var_20]
0x1800caa05  test    rcx, rcx
0x1800caa08  jz      short loc_1800CAA1B
0x1800caa0a  mov     [rbp+var_20], r15
0x1800caa0e  mov     rax, [rcx]
0x1800caa11  mov     rax, [rax+10h]
0x1800caa15  call    _guard_dispatch_icall
0x1800caa1a  nop
0x1800caa1b  jmp     loc_1800CABD1
0x1800caa20  mov     [rbp+var_18], r15
0x1800caa24  lea     r8, [rbp+var_18]
0x1800caa28  mov     edx, edi
0x1800caa2a  mov     rcx, [rbp+var_20]
0x1800caa2e  call    ??_9IPropertyValueStatics@Foundation@Windows@ABI@@$BFI@AA; [thunk]: ABI::Windows::Foundation::IPropertyValueStatics::`vcall'{88,{flat}}
0x1800caa33  mov     ebx, eax
0x1800caa35  test    eax, eax
0x1800caa37  jns     short loc_1800CAA8B
0x1800caa39  mov     rcx, [rbp+28h]; this
0x1800caa3d  mov     r9d, eax; char *
0x1800caa40  lea     r8, aCW1SSrcOrchest_46; "C:\\__w\\1\\s\\src\\orchestrator\\Exter"...
0x1800caa47  mov     edx, 52h ; 'R'; void *
0x1800caa4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800caa51  nop
0x1800caa52  mov     rcx, [rbp+var_18]
0x1800caa56  test    rcx, rcx
0x1800caa59  jz      short loc_1800CAA6C
0x1800caa5b  mov     [rbp+var_18], r15
0x1800caa5f  mov     rax, [rcx]
0x1800caa62  mov     rax, [rax+10h]
0x1800caa66  call    _guard_dispatch_icall
0x1800caa6b  nop
0x1800caa6c  mov     rcx, [rbp+var_20]
0x1800caa70  test    rcx, rcx
0x1800caa73  jz      short loc_1800CAA86
0x1800caa75  mov     [rbp+var_20], r15
0x1800caa79  mov     rax, [rcx]
0x1800caa7c  mov     rax, [rax+10h]
0x1800caa80  call    _guard_dispatch_icall
0x1800caa85  nop
0x1800caa86  jmp     loc_1800CABD1
0x1800caa8b  mov     [rbp+var_10], r15
0x1800caa8f  mov     rcx, [rbp+var_18]
0x1800caa93  mov     rax, [rcx]
0x1800caa96  lea     r8, [rbp+var_10]
0x1800caa9a  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1800caaa1  mov     rax, [rax]
0x1800caaa4  call    _guard_dispatch_icall
0x1800caaa9  mov     ebx, eax
0x1800caaab  test    eax, eax
0x1800caaad  jns     short loc_1800CAB1B
0x1800caaaf  mov     rcx, [rbp+28h]; this
0x1800caab3  mov     r9d, eax; char *
0x1800caab6  lea     r8, aCW1SSrcOrchest_46; "C:\\__w\\1\\s\\src\\orchestrator\\Exter"...
0x1800caabd  mov     edx, 54h ; 'T'; void *
0x1800caac2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800caac7  nop
0x1800caac8  mov     rcx, [rbp+var_10]
0x1800caacc  test    rcx, rcx
0x1800caacf  jz      short loc_1800CAAE2
0x1800caad1  mov     [rbp+var_10], r15
0x1800caad5  mov     rax, [rcx]
0x1800caad8  mov     rax, [rax+10h]
0x1800caadc  call    _guard_dispatch_icall
0x1800caae1  nop
0x1800caae2  mov     rcx, [rbp+var_18]
0x1800caae6  test    rcx, rcx
0x1800caae9  jz      short loc_1800CAAFC
0x1800caaeb  mov     [rbp+var_18], r15
0x1800caaef  mov     rax, [rcx]
0x1800caaf2  mov     rax, [rax+10h]
0x1800caaf6  call    _guard_dispatch_icall
0x1800caafb  nop
0x1800caafc  mov     rcx, [rbp+var_20]
0x1800cab00  test    rcx, rcx
0x1800cab03  jz      short loc_1800CAB16
0x1800cab05  mov     [rbp+var_20], r15
0x1800cab09  mov     rax, [rcx]
0x1800cab0c  mov     rax, [rax+10h]
0x1800cab10  call    _guard_dispatch_icall
0x1800cab15  nop
0x1800cab16  jmp     loc_1800CABD1
0x1800cab1b  mov     r8, [rbp+var_10]; struct ABI::Windows::Foundation::IPropertyValue *
0x1800cab1f  mov     rdx, r14; HSTRING
0x1800cab22  mov     rcx, rsi; this
0x1800cab25  call    ?SetPropVal@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@PEAUIPropertyValue@Foundation@4ABI@@@Z; Windows::Internal::ShellHelpers::PropertySetHelper::SetPropVal(HSTRING__ *,ABI::Windows::Foundation::IPropertyValue *)
0x1800cab2a  mov     ebx, eax
0x1800cab2c  test    eax, eax
0x1800cab2e  jns     short loc_1800CAB80
0x1800cab30  mov     rcx, [rbp+var_10]
0x1800cab34  test    rcx, rcx
0x1800cab37  jz      short loc_1800CAB4A
0x1800cab39  mov     [rbp+var_10], r15
0x1800cab3d  mov     rax, [rcx]
0x1800cab40  mov     rax, [rax+10h]
0x1800cab44  call    _guard_dispatch_icall
0x1800cab49  nop
0x1800cab4a  mov     rcx, [rbp+var_18]
0x1800cab4e  test    rcx, rcx
0x1800cab51  jz      short loc_1800CAB64
0x1800cab53  mov     [rbp+var_18], r15
0x1800cab57  mov     rax, [rcx]
0x1800cab5a  mov     rax, [rax+10h]
0x1800cab5e  call    _guard_dispatch_icall
0x1800cab63  nop
0x1800cab64  mov     rcx, [rbp+var_20]
0x1800cab68  test    rcx, rcx
0x1800cab6b  jz      short loc_1800CAB7E
0x1800cab6d  mov     [rbp+var_20], r15
0x1800cab71  mov     rax, [rcx]
0x1800cab74  mov     rax, [rax+10h]
0x1800cab78  call    _guard_dispatch_icall
0x1800cab7d  nop
0x1800cab7e  jmp     short loc_1800CABD1
0x1800cab80  mov     rcx, [rbp+var_10]
0x1800cab84  test    rcx, rcx
0x1800cab87  jz      short loc_1800CAB9A
0x1800cab89  mov     [rbp+var_10], r15
0x1800cab8d  mov     rax, [rcx]
0x1800cab90  mov     rax, [rax+10h]
0x1800cab94  call    _guard_dispatch_icall
0x1800cab99  nop
0x1800cab9a  mov     rcx, [rbp+var_18]
0x1800cab9e  test    rcx, rcx
0x1800caba1  jz      short loc_1800CABB4
0x1800caba3  mov     [rbp+var_18], r15
0x1800caba7  mov     rax, [rcx]
0x1800cabaa  mov     rax, [rax+10h]
0x1800cabae  call    _guard_dispatch_icall
0x1800cabb3  nop
0x1800cabb4  mov     rcx, [rbp+var_20]
0x1800cabb8  test    rcx, rcx
0x1800cabbb  jz      short loc_1800CABCE
0x1800cabbd  mov     [rbp+var_20], r15
0x1800cabc1  mov     rax, [rcx]
0x1800cabc4  mov     rax, [rax+10h]
0x1800cabc8  call    _guard_dispatch_icall
0x1800cabcd  nop
0x1800cabce  mov     ebx, r15d
0x1800cabd1  mov     eax, ebx
0x1800cabd3  mov     rcx, [rbp+var_8]
0x1800cabd7  xor     rcx, rsp; StackCookie
0x1800cabda  call    __security_check_cookie
0x1800cabdf  mov     rbx, [rsp+60h+arg_18]
0x1800cabe7  add     rsp, 60h
0x1800cabeb  pop     r15
0x1800cabed  pop     r14
0x1800cabef  pop     rdi
0x1800cabf0  pop     rsi
0x1800cabf1  pop     rbp
0x1800cabf2  retn
0x1800cabf3  mov     ecx, eax; this
0x1800cabf5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
