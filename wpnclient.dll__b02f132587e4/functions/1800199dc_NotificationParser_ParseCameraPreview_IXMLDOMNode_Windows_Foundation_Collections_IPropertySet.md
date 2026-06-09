# NotificationParser::ParseCameraPreview(IXMLDOMNode *,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x1800199dc`
- end: `0x180019b43`
- name: `?ParseCameraPreview@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `359`
- prototype: `void __fastcall(NotificationParser *__hidden this, struct IXMLDOMNode *, struct Windows::Foundation::Collections::IPropertySet **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800192d4`

## callees

- `0x180005670`
- `0x180008390`
- `0x180008fe0`
- `0x180013fc0`
- `0x1800146f0`
- `0x1800199dc`
- `0x18001b848`
- `0x18001ff00`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall NotificationParser::ParseCameraPreview(
        NotificationParser *this,
        struct IXMLDOMNode *a2,
        struct Windows::Foundation::Collections::IPropertySet **a3)
{
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING, __int64 *); // rbx
  HSTRING *v9; // rax
  int v10; // eax
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, HSTRING, __int64, _BYTE *); // rdi
  __int64 v13; // rbx
  HSTRING *v14; // rax
  int v15; // eax
  struct Windows::Foundation::Collections::IPropertySet *v16; // rax
  int v17; // [rsp+20h] [rbp-60h]
  _BYTE v18[8]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v19; // [rsp+38h] [rbp-48h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v20; // [rsp+40h] [rbp-40h] BYREF
  __int64 v21; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string[4]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v20 = 0;
  v19 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v20);
  NotificationParser::CreateValueSet(v6, &v20, &v19);
  v21 = 0;
  v7 = *(_QWORD *)this;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(**(_QWORD **)this + 144LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  v9 = Windows::Internal::StringReference::StringReference(string, L"cameraPreview");
  v10 = v8(v7, *v9, &v21);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x451,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v10,
      v17);
  v18[0] = 0;
  v11 = v19;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v19 + 80LL);
  v13 = v21;
  v14 = Windows::Internal::StringReference::StringReference(string, L"item-type");
  v15 = v12(v11, *v14, v13, v18);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x454,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v15,
      v17);
  NotificationParser::GetAttributes((__int64 *)this, (__int64)a2, v19);
  v16 = v20;
  v20 = 0;
  *a3 = v16;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v20);
}

```

## disassembly

```asm
0x1800199dc  push    rbp
0x1800199de  push    rbx
0x1800199df  push    rsi
0x1800199e0  push    rdi
0x1800199e1  push    r12
0x1800199e3  push    r14
0x1800199e5  push    r15
0x1800199e7  mov     rbp, rsp
0x1800199ea  sub     rsp, 80h
0x1800199f1  mov     rax, cs:__security_cookie
0x1800199f8  xor     rax, rsp
0x1800199fb  mov     [rbp+var_10], rax
0x1800199ff  mov     r12, r8
0x180019a02  mov     r15, rdx
0x180019a05  mov     r14, rcx
0x180019a08  mov     [rbp+var_40], 0
0x180019a10  mov     [rbp+var_48], 0
0x180019a18  lea     rcx, [rbp+var_48]
0x180019a1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019a21  lea     rcx, [rbp+var_40]
0x180019a25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019a2a  lea     r8, [rbp+var_48]
0x180019a2e  lea     rdx, [rbp+var_40]
0x180019a32  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x180019a37  mov     [rbp+var_38], 0
0x180019a3f  mov     rdi, [r14]
0x180019a42  mov     rax, [rdi]
0x180019a45  mov     rbx, [rax+90h]
0x180019a4c  lea     rcx, [rbp+var_38]
0x180019a50  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019a55  lea     rdx, aCamerapreview; "cameraPreview"
0x180019a5c  lea     rcx, [rbp+string]; string
0x180019a60  call    ??$?0$0O@@StringReference@Internal@Windows@@QEAA@AEAY0O@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[14])
0x180019a65  lea     r8, [rbp+var_38]
0x180019a69  mov     rdx, [rax]
0x180019a6c  mov     rcx, rdi
0x180019a6f  mov     rax, rbx
0x180019a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a77  mov     rcx, [rbp+38h]; this
0x180019a7b  test    eax, eax
0x180019a7d  jns     short loc_180019A94
0x180019a7f  mov     r9d, eax; char *
0x180019a82  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019a89  mov     edx, 451h; void *
0x180019a8e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019a94  mov     [rbp+var_50], 0
0x180019a98  mov     rsi, [rbp+var_48]
0x180019a9c  mov     rax, [rsi]
0x180019a9f  mov     rdi, [rax+50h]
0x180019aa3  mov     rbx, [rbp+var_38]
0x180019aa7  lea     rdx, aItemType; "item-type"
0x180019aae  lea     rcx, [rbp+string]; string
0x180019ab2  call    ??$?0$09@StringReference@Internal@Windows@@QEAA@AEAY09$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[10])
0x180019ab7  lea     r9, [rbp+var_50]
0x180019abb  mov     r8, rbx
0x180019abe  mov     rdx, [rax]
0x180019ac1  mov     rcx, rsi
0x180019ac4  mov     rax, rdi
0x180019ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019acc  mov     rcx, [rbp+38h]; this
0x180019ad0  test    eax, eax
0x180019ad2  jns     short loc_180019AE9
0x180019ad4  mov     r9d, eax; char *
0x180019ad7  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019ade  mov     edx, 454h; void *
0x180019ae3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019ae9  mov     r8, [rbp+var_48]
0x180019aed  mov     rdx, r15
0x180019af0  mov     rcx, r14
0x180019af3  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x180019af8  mov     rax, [rbp+var_40]
0x180019afc  mov     [rbp+var_40], 0
0x180019b04  mov     [r12], rax
0x180019b08  lea     rcx, [rbp+var_38]
0x180019b0c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019b11  nop
0x180019b12  lea     rcx, [rbp+var_48]
0x180019b16  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019b1b  nop
0x180019b1c  lea     rcx, [rbp+var_40]
0x180019b20  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019b25  mov     rcx, [rbp+var_10]
0x180019b29  xor     rcx, rsp; StackCookie
0x180019b2c  call    __security_check_cookie
0x180019b31  add     rsp, 80h
0x180019b38  pop     r15
0x180019b3a  pop     r14
0x180019b3c  pop     r12
0x180019b3e  pop     rdi
0x180019b3f  pop     rsi
0x180019b40  pop     rbx
0x180019b41  pop     rbp
0x180019b42  retn
```
