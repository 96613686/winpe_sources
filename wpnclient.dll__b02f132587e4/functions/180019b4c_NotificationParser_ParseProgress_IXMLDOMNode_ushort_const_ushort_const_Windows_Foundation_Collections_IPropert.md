# NotificationParser::ParseProgress(IXMLDOMNode *,ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x180019b4c`
- end: `0x180019cfd`
- name: `?ParseProgress@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `433`
- prototype: `void __fastcall(NotificationParser *__hidden this, struct IXMLDOMNode *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Foundation::Collections::IPropertySet **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800192d4`

## callees

- `0x180005670`
- `0x180008390`
- `0x180008fe0`
- `0x18000b440`
- `0x180013fc0`
- `0x180019b4c`
- `0x18001a610`
- `0x18001b848`
- `0x18001ff00`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall NotificationParser::ParseProgress(
        NotificationParser *this,
        struct IXMLDOMNode *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct Windows::Foundation::Collections::IPropertySet **a5)
{
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING, __int64 *); // rbx
  HSTRING *v11; // rax
  int v12; // eax
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, HSTRING, __int64, _BYTE *); // rdi
  __int64 v15; // rbx
  HSTRING *v16; // rax
  int v17; // eax
  struct Windows::Foundation::Collections::IPropertySet *v18; // rax
  int v19; // [rsp+20h] [rbp-60h]
  _BYTE v20[8]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v22; // [rsp+40h] [rbp-40h] BYREF
  __int64 v23; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string[4]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v22 = 0;
  v21 = 0;
  v23 = 0;
  v20[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v22);
  NotificationParser::CreateValueSet(v8, &v22, &v21);
  v9 = *(_QWORD *)this;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(**(_QWORD **)this + 144LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  v11 = Windows::Internal::StringReference::StringReference(string, L"progress");
  v12 = v10(v9, *v11, &v23);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v12,
      v19);
  v13 = v21;
  v14 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v21 + 80LL);
  v15 = v23;
  v16 = Windows::Internal::StringReference::StringReference(string, L"item-type");
  v17 = v14(v13, *v16, v15, v20);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v17,
      v19);
  NotificationParser::GetAttributes((__int64 *)this, (__int64)a2, v21);
  NotificationParser::ResolveTextElement(this, v21, L"status", (__int64)a3);
  NotificationParser::ResolveTextElement(this, v21, L"title", (__int64)a3);
  NotificationParser::ResolveTextElement(this, v21, L"valueStringOverride", (__int64)a3);
  v18 = v22;
  v22 = 0;
  *a5 = v18;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v22);
}

```

## disassembly

```asm
0x180019b4c  mov     [rsp-38h+arg_18], rbx
0x180019b51  push    rbp
0x180019b52  push    rsi
0x180019b53  push    rdi
0x180019b54  push    r12
0x180019b56  push    r13
0x180019b58  push    r14
0x180019b5a  push    r15
0x180019b5c  mov     rbp, rsp
0x180019b5f  sub     rsp, 80h
0x180019b66  mov     rax, cs:__security_cookie
0x180019b6d  xor     rax, rsp
0x180019b70  mov     [rbp+var_10], rax
0x180019b74  mov     r15, r8
0x180019b77  mov     r12, rdx
0x180019b7a  mov     r14, rcx
0x180019b7d  mov     r13, [rbp+arg_20]
0x180019b81  xor     esi, esi
0x180019b83  mov     [rbp+var_40], rsi
0x180019b87  mov     [rbp+var_48], rsi
0x180019b8b  mov     [rbp+var_38], rsi
0x180019b8f  mov     [rbp+var_50], sil
0x180019b93  lea     rcx, [rbp+var_48]
0x180019b97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019b9c  lea     rcx, [rbp+var_40]
0x180019ba0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019ba5  lea     r8, [rbp+var_48]
0x180019ba9  lea     rdx, [rbp+var_40]
0x180019bad  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x180019bb2  mov     rdi, [r14]
0x180019bb5  mov     rax, [rdi]
0x180019bb8  mov     rbx, [rax+90h]
0x180019bbf  lea     rcx, [rbp+var_38]
0x180019bc3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019bc8  lea     rdx, aProgress; "progress"
0x180019bcf  lea     rcx, [rbp+string]; string
0x180019bd3  call    ??$?0$08@StringReference@Internal@Windows@@QEAA@AEAY08$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[9])
0x180019bd8  lea     r8, [rbp+var_38]
0x180019bdc  mov     rdx, [rax]
0x180019bdf  mov     rcx, rdi
0x180019be2  mov     rax, rbx
0x180019be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bea  mov     rcx, [rbp+38h]; this
0x180019bee  test    eax, eax
0x180019bf0  jns     short loc_180019C07
0x180019bf2  mov     r9d, eax; char *
0x180019bf5  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019bfc  mov     edx, 43Ah; void *
0x180019c01  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019c07  mov     rsi, [rbp+var_48]
0x180019c0b  mov     rax, [rsi]
0x180019c0e  mov     rdi, [rax+50h]
0x180019c12  mov     rbx, [rbp+var_38]
0x180019c16  lea     rdx, aItemType; "item-type"
0x180019c1d  lea     rcx, [rbp+string]; string
0x180019c21  call    ??$?0$09@StringReference@Internal@Windows@@QEAA@AEAY09$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[10])
0x180019c26  lea     r9, [rbp+var_50]
0x180019c2a  mov     r8, rbx
0x180019c2d  mov     rdx, [rax]
0x180019c30  mov     rcx, rsi
0x180019c33  mov     rax, rdi
0x180019c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c3b  mov     rcx, [rbp+38h]; this
0x180019c3f  test    eax, eax
0x180019c41  jns     short loc_180019C58
0x180019c43  mov     r9d, eax; char *
0x180019c46  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180019c4d  mov     edx, 43Dh; void *
0x180019c52  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019c58  mov     r8, [rbp+var_48]
0x180019c5c  mov     rdx, r12
0x180019c5f  mov     rcx, r14
0x180019c62  call    ?GetAttributes@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z; NotificationParser::GetAttributes(IXMLDOMNode *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)
0x180019c67  mov     r9, r15
0x180019c6a  lea     r8, aStatus; "status"
0x180019c71  mov     rdx, [rbp+var_48]
0x180019c75  mov     rcx, r14
0x180019c78  call    ?ResolveTextElement@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG11@Z; NotificationParser::ResolveTextElement(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,ushort const *)
0x180019c7d  mov     r9, r15
0x180019c80  lea     r8, aTitle; "title"
0x180019c87  mov     rdx, [rbp+var_48]
0x180019c8b  mov     rcx, r14
0x180019c8e  call    ?ResolveTextElement@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG11@Z; NotificationParser::ResolveTextElement(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,ushort const *)
0x180019c93  mov     r9, r15
0x180019c96  lea     r8, aValuestringove; "valueStringOverride"
0x180019c9d  mov     rdx, [rbp+var_48]
0x180019ca1  mov     rcx, r14
0x180019ca4  call    ?ResolveTextElement@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEBG11@Z; NotificationParser::ResolveTextElement(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,ushort const *,ushort const *,ushort const *)
0x180019ca9  mov     rax, [rbp+var_40]
0x180019cad  mov     [rbp+var_40], 0
0x180019cb5  mov     [r13+0], rax
0x180019cb9  lea     rcx, [rbp+var_38]
0x180019cbd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019cc2  nop
0x180019cc3  lea     rcx, [rbp+var_48]
0x180019cc7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019ccc  nop
0x180019ccd  lea     rcx, [rbp+var_40]
0x180019cd1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180019cd6  mov     rcx, [rbp+var_10]
0x180019cda  xor     rcx, rsp; StackCookie
0x180019cdd  call    __security_check_cookie
0x180019ce2  mov     rbx, [rsp+80h+arg_18]
0x180019cea  add     rsp, 80h
0x180019cf1  pop     r15
0x180019cf3  pop     r14
0x180019cf5  pop     r13
0x180019cf7  pop     r12
0x180019cf9  pop     rdi
0x180019cfa  pop     rsi
0x180019cfb  pop     rbp
0x180019cfc  retn
```
