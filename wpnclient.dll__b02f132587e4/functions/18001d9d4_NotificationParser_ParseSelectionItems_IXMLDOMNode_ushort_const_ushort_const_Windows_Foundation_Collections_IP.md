# NotificationParser::ParseSelectionItems(IXMLDOMNode *,ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x18001d9d4`
- end: `0x18001dc21`
- name: `?ParseSelectionItems@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `589`
- prototype: `void __fastcall(NotificationParser *__hidden this, struct IXMLDOMNode *, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Foundation::Collections::IPropertySet **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016334`

## callees

- `0x180005670`
- `0x180008390`
- `0x180008910`
- `0x18000dc30`
- `0x18001b848`
- `0x18001d9d4`
- `0x18001dc28`
- `0x18001ff00`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall NotificationParser::ParseSelectionItems(
        NotificationParser *this,
        struct IXMLDOMNode *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct Windows::Foundation::Collections::IPropertySet **a5)
{
  __int64 v8; // rcx
  HRESULT (__stdcall *get_childNodes)(IXMLDOMNode *, IXMLDOMNodeList **); // rbx
  int v10; // eax
  int v11; // eax
  unsigned int i; // r14d
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, struct IXMLDOMNode **); // rbx
  int v16; // eax
  const unsigned __int16 *v17; // r9
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *); // rdi
  struct Windows::Foundation::Collections::IPropertySet *v20; // rbx
  int v21; // eax
  struct Windows::Foundation::Collections::IPropertySet *v22; // rax
  int v23; // [rsp+20h] [rbp-61h]
  _BYTE v24[4]; // [rsp+30h] [rbp-51h] BYREF
  int v25; // [rsp+34h] [rbp-4Dh] BYREF
  __int64 v26; // [rsp+38h] [rbp-49h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v27; // [rsp+40h] [rbp-41h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v28; // [rsp+48h] [rbp-39h] BYREF
  struct IXMLDOMNode *v29; // [rsp+50h] [rbp-31h] BYREF
  __int64 v30; // [rsp+58h] [rbp-29h] BYREF
  _QWORD v31[4]; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int16 v32[12]; // [rsp+80h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v27 = 0;
  v30 = 0;
  v26 = 0;
  v24[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v27);
  NotificationParser::CreateValueSet(v8, &v27, &v30);
  v25 = 0;
  get_childNodes = a2->lpVtbl->get_childNodes;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))get_childNodes)(a2, &v26);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x60D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v10,
      v23);
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 64LL))(v26, &v25);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x60F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
      (const char *)(unsigned int)v11,
      v23);
  for ( i = 0; (int)i < v25; ++i )
  {
    v13 = StringCchPrintfW(v32, 0xAu, L"%ld", i);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x615,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v13,
        v23);
    v29 = 0;
    v14 = v26;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v26 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v29);
    v16 = v15(v14, i, &v29);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x619,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v16,
        v23);
    v28 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v28);
    NotificationParser::ParseSelectionItem(this, v29, a3, v17, &v28);
    v18 = v30;
    v19 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::Collections::IPropertySet *, _BYTE *))(*(_QWORD *)v30 + 80LL);
    v20 = v28;
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v31, v32);
    v21 = v19(v18, v31[0], v20, v24);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x61E,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v21,
        v23);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v29);
  }
  v22 = v27;
  v27 = 0;
  *a5 = v22;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v27);
}

```

## disassembly

```asm
0x18001d9d4  mov     [rsp-8+arg_18], rbx
0x18001d9d9  push    rbp
0x18001d9da  push    rsi
0x18001d9db  push    rdi
0x18001d9dc  push    r12
0x18001d9de  push    r13
0x18001d9e0  push    r14
0x18001d9e2  push    r15
0x18001d9e4  lea     rbp, [rsp-1Fh]
0x18001d9e9  sub     rsp, 0A0h
0x18001d9f0  mov     rax, cs:__security_cookie
0x18001d9f7  xor     rax, rsp
0x18001d9fa  mov     [rbp+4Fh+var_38], rax
0x18001d9fe  mov     r13, r8
0x18001da01  mov     rdi, rdx
0x18001da04  mov     r12, rcx
0x18001da07  mov     r15, [rbp+4Fh+arg_20]
0x18001da0b  xor     esi, esi
0x18001da0d  mov     [rbp+4Fh+var_90], rsi
0x18001da11  mov     [rbp+4Fh+var_78], rsi
0x18001da15  mov     [rbp+4Fh+var_98], rsi
0x18001da19  mov     [rbp+4Fh+var_A0], sil
0x18001da1d  lea     rcx, [rbp+4Fh+var_78]
0x18001da21  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001da26  lea     rcx, [rbp+4Fh+var_90]
0x18001da2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001da2f  lea     r8, [rbp+4Fh+var_78]
0x18001da33  lea     rdx, [rbp+4Fh+var_90]
0x18001da37  call    ?CreateValueSet@NotificationParser@@AEAAXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@345@@Z; NotificationParser::CreateValueSet(Windows::Foundation::Collections::IPropertySet * *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> * *)
0x18001da3c  mov     [rbp+4Fh+var_9C], esi
0x18001da3f  mov     rax, [rdi]
0x18001da42  mov     rbx, [rax+60h]
0x18001da46  lea     rcx, [rbp+4Fh+var_98]
0x18001da4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001da4f  lea     rdx, [rbp+4Fh+var_98]
0x18001da53  mov     rcx, rdi
0x18001da56  mov     rax, rbx
0x18001da59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da5e  mov     rcx, [rbp+57h]; this
0x18001da62  test    eax, eax
0x18001da64  jns     short loc_18001DA7B
0x18001da66  mov     r9d, eax; char *
0x18001da69  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001da70  mov     edx, 60Dh; void *
0x18001da75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001da7b  mov     rcx, [rbp+4Fh+var_98]
0x18001da7f  mov     rax, [rcx]
0x18001da82  lea     rdx, [rbp+4Fh+var_9C]
0x18001da86  mov     rax, [rax+40h]
0x18001da8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da8f  mov     rcx, [rbp+57h]; this
0x18001da93  test    eax, eax
0x18001da95  jns     short loc_18001DAAC
0x18001da97  mov     r9d, eax; char *
0x18001da9a  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001daa1  mov     edx, 60Fh; void *
0x18001daa6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001daac  mov     r14d, esi
0x18001daaf  cmp     [rbp+4Fh+var_9C], esi
0x18001dab2  jle     loc_18001DB93
0x18001dab8  mov     r9d, r14d
0x18001dabb  lea     r8, aLd; "%ld"
0x18001dac2  mov     edx, 0Ah; unsigned __int64
0x18001dac7  lea     rcx, [rbp+4Fh+var_50]; unsigned __int16 *
0x18001dacb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001dad0  mov     rcx, [rbp+57h]; this
0x18001dad4  test    eax, eax
0x18001dad6  js      loc_18001DC0C
0x18001dadc  mov     [rbp+4Fh+var_80], rsi
0x18001dae0  mov     rdi, [rbp+4Fh+var_98]
0x18001dae4  mov     rax, [rdi]
0x18001dae7  mov     rbx, [rax+38h]
0x18001daeb  lea     rcx, [rbp+4Fh+var_80]
0x18001daef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001daf4  lea     r8, [rbp+4Fh+var_80]
0x18001daf8  mov     edx, r14d
0x18001dafb  mov     rcx, rdi
0x18001dafe  mov     rax, rbx
0x18001db01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db06  mov     rcx, [rbp+57h]; this
0x18001db0a  test    eax, eax
0x18001db0c  js      loc_18001DBF7
0x18001db12  mov     [rbp+4Fh+var_88], rsi
0x18001db16  lea     rcx, [rbp+4Fh+var_88]
0x18001db1a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001db1f  lea     rax, [rbp+4Fh+var_88]
0x18001db23  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18001db28  mov     r8, r13; unsigned __int16 *
0x18001db2b  mov     rdx, [rbp+4Fh+var_80]; struct IXMLDOMNode *
0x18001db2f  mov     rcx, r12; this
0x18001db32  call    ?ParseSelectionItem@NotificationParser@@AEAAXPEAUIXMLDOMNode@@PEBG1PEAPEAUIPropertySet@Collections@Foundation@Windows@@@Z; NotificationParser::ParseSelectionItem(IXMLDOMNode *,ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet * *)
0x18001db37  mov     rsi, [rbp+4Fh+var_78]
0x18001db3b  mov     rax, [rsi]
0x18001db3e  mov     rdi, [rax+50h]
0x18001db42  mov     rbx, [rbp+4Fh+var_88]
0x18001db46  lea     rdx, [rbp+4Fh+var_50]; unsigned __int16 *
0x18001db4a  lea     rcx, [rbp+4Fh+var_70]; this
0x18001db4e  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001db53  lea     r9, [rbp+4Fh+var_A0]
0x18001db57  mov     r8, rbx
0x18001db5a  mov     rdx, [rbp+4Fh+var_70]
0x18001db5e  mov     rcx, rsi
0x18001db61  mov     rax, rdi
0x18001db64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db69  mov     rcx, [rbp+57h]; this
0x18001db6d  xor     esi, esi
0x18001db6f  test    eax, eax
0x18001db71  js      short loc_18001DBE2
0x18001db73  lea     rcx, [rbp+4Fh+var_88]
0x18001db77  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001db7c  nop
0x18001db7d  lea     rcx, [rbp+4Fh+var_80]
0x18001db81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001db86  inc     r14d
0x18001db89  cmp     r14d, [rbp+4Fh+var_9C]
0x18001db8d  jl      loc_18001DAB8
0x18001db93  mov     rax, [rbp+4Fh+var_90]
0x18001db97  mov     [rbp+4Fh+var_90], rsi
0x18001db9b  mov     [r15], rax
0x18001db9e  lea     rcx, [rbp+4Fh+var_98]
0x18001dba2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dba7  nop
0x18001dba8  lea     rcx, [rbp+4Fh+var_78]
0x18001dbac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dbb1  nop
0x18001dbb2  lea     rcx, [rbp+4Fh+var_90]
0x18001dbb6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dbbb  mov     rcx, [rbp+4Fh+var_38]
0x18001dbbf  xor     rcx, rsp; StackCookie
0x18001dbc2  call    __security_check_cookie
0x18001dbc7  mov     rbx, [rsp+0D0h+arg_18]
0x18001dbcf  add     rsp, 0A0h
0x18001dbd6  pop     r15
0x18001dbd8  pop     r14
0x18001dbda  pop     r13
0x18001dbdc  pop     r12
0x18001dbde  pop     rdi
0x18001dbdf  pop     rsi
0x18001dbe0  pop     rbp
0x18001dbe1  retn
0x18001dbe2  mov     r9d, eax; char *
0x18001dbe5  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001dbec  mov     edx, 61Eh; void *
0x18001dbf1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dbf7  mov     r9d, eax; char *
0x18001dbfa  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001dc01  mov     edx, 619h; void *
0x18001dc06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001dc0c  mov     r9d, eax; char *
0x18001dc0f  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001dc16  mov     edx, 615h; void *
0x18001dc1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
