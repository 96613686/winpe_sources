# CombinePropertyBags(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> * *,bool)

- ea: `0x1800eee30`
- end: `0x1800ef386`
- name: `?CombinePropertyBags@@YAJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@0PEAPEAU1234@_N@Z`
- size: `1366`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800d4be4`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000f8e8`
- `0x180015830`
- `0x180015b00`
- `0x1800168f0`
- `0x180018428`
- `0x1800eee30`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef01f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef02f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef0ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef256`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef266`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef2af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef2d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef01f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef02f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef0ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef256`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef266`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef2af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef2d9`

## string_xrefs

- `0x1800eee79`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800eeecd`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800eef21`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800ef064`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800ef090`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800ef0ba`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800ef142`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800ef18e`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800ef292`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800ef2be`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800ef2e8`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800ef341`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CombinePropertyBags(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        _QWORD *a3,
        char a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rbx
  int v19; // eax
  int v20; // edi
  int v21; // eax
  __int64 v22; // rdx
  __int64 *v23; // rcx
  __int64 (__fastcall *v24)(_QWORD, GUID *, __int64 *); // rdi
  int v25; // eax
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, __int64 *); // rdi
  int v28; // eax
  int i; // eax
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  int View; // eax
  __int64 v34; // rax
  int v36; // [rsp+20h] [rbp-49h] BYREF
  __int64 v37; // [rsp+28h] [rbp-41h] BYREF
  __int64 v38; // [rsp+30h] [rbp-39h] BYREF
  __int64 v39; // [rsp+38h] [rbp-31h] BYREF
  __int64 v40; // [rsp+40h] [rbp-29h] BYREF
  HSTRING v41; // [rsp+48h] [rbp-21h] BYREF
  __int64 v42; // [rsp+50h] [rbp-19h] BYREF
  __int64 v43; // [rsp+58h] [rbp-11h] BYREF
  HSTRING string; // [rsp+60h] [rbp-9h] BYREF
  HSTRING v45; // [rsp+68h] [rbp-1h] BYREF
  __int64 v46; // [rsp+70h] [rbp+7h] BYREF
  HSTRING v47; // [rsp+78h] [rbp+Fh] BYREF
  _QWORD v48[8]; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v48[0] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(v48);
  v10 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Make(
          v9,
          v8,
          v48);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB5B,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)v10,
      v36);
    goto LABEL_66;
  }
  LOBYTE(v36) = 0;
  BYTE2(v36) = 0;
  v39 = 0;
  v12 = **a1;
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v39);
  v13 = v12(a1, &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b, &v39);
  v11 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB64,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)v13,
      v36);
LABEL_5:
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v39);
    goto LABEL_66;
  }
  v37 = 0;
  v14 = v39;
  v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 48LL);
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v37);
  v16 = v15(v14, &v37);
  v11 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB67,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)v16,
      v36);
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v37);
    goto LABEL_5;
  }
  BYTE1(v36) = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v37 + 56LL))(v37, &v36);
  v18 = v48[0];
  while ( v17 >= 0 && (_BYTE)v36 )
  {
    v42 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 48LL))(v37, &v42);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB6F,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v19,
        v36);
      goto LABEL_31;
    }
    v41 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 48LL))(v42, &v41);
    v20 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB72,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v21,
        v36);
      goto LABEL_28;
    }
    string = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 56LL))(v42, &string);
    if ( v20 < 0 )
    {
      v22 = 2933;
      goto LABEL_25;
    }
    if ( !a4 || (BYTE1(v36) = 0, (int)(*a2)[8](a2, (GUID *)v41, (__int64 *)((char *)&v36 + 1)) < 0) || !BYTE1(v36) )
    {
      v20 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
              v18,
              v41,
              string,
              (char *)&v36 + 2);
      if ( v20 < 0 )
      {
        v22 = 2945;
LABEL_25:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
          (const char *)(unsigned int)v20,
          v36);
        if ( string )
          WindowsDeleteString(string);
LABEL_28:
        if ( v41 )
          WindowsDeleteString(v41);
LABEL_31:
        Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v37);
        v23 = &v39;
LABEL_32:
        Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(v23);
        v11 = v20;
        goto LABEL_66;
      }
    }
    if ( string )
      WindowsDeleteString(string);
    if ( v41 )
      WindowsDeleteString(v41);
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v42);
    v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v37 + 64LL))(v37, &v36);
  }
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v39);
  if ( !a4 )
  {
    v40 = 0;
    v24 = **a2;
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v40);
    v25 = v24(a2, &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b, &v40);
    v20 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB8A,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v25,
        v36);
LABEL_36:
      v23 = &v40;
      goto LABEL_32;
    }
    v38 = 0;
    v26 = v40;
    v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL);
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v38);
    v28 = v27(v26, &v38);
    v20 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB8D,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)v28,
        v36);
LABEL_39:
      Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v38);
      goto LABEL_36;
    }
    for ( i = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 56LL))(v38, &v36);
          i >= 0 && (_BYTE)v36;
          i = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 64LL))(v38, &v36) )
    {
      v43 = 0;
      v30 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 48LL))(v38, &v43);
      v20 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB94,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
          (const char *)(unsigned int)v30,
          v36);
        goto LABEL_60;
      }
      v45 = 0;
      v31 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 48LL))(v43, &v45);
      v20 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB97,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
          (const char *)(unsigned int)v31,
          v36);
        goto LABEL_57;
      }
      v47 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 56LL))(v43, &v47);
      if ( v20 < 0 )
      {
        v32 = 2970;
        goto LABEL_54;
      }
      v20 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
              v18,
              v45,
              v47,
              (char *)&v36 + 2);
      if ( v20 < 0 )
      {
        v32 = 2972;
LABEL_54:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v32,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
          (const char *)(unsigned int)v20,
          v36);
        if ( v47 )
          WindowsDeleteString(v47);
LABEL_57:
        if ( v45 )
          WindowsDeleteString(v45);
LABEL_60:
        Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v43);
        goto LABEL_39;
      }
      if ( v47 )
        WindowsDeleteString(v47);
      if ( v45 )
        WindowsDeleteString(v45);
      Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v43);
    }
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v40);
  }
  v46 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  View = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetView(
           v18,
           &v46);
  v11 = View;
  if ( View >= 0 )
  {
    v34 = v46;
    v46 = 0;
    *a3 = v34;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA1,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)View,
      v36);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
LABEL_66:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(v48);
  return v11;
}

```

## disassembly

```asm
0x1800eee30  push    rbp
0x1800eee32  push    rbx
0x1800eee33  push    rsi
0x1800eee34  push    rdi
0x1800eee35  push    r12
0x1800eee37  push    r14
0x1800eee39  push    r15
0x1800eee3b  lea     rbp, [rsp-27h]
0x1800eee40  sub     rsp, 90h
0x1800eee47  mov     sil, r9b
0x1800eee4a  mov     r15, r8
0x1800eee4d  mov     r14, rdx
0x1800eee50  mov     rdi, rcx
0x1800eee53  xor     r12d, r12d
0x1800eee56  mov     [rbp+57h+var_40], r12
0x1800eee5a  lea     rcx, [rbp+57h+var_40]
0x1800eee5e  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(void)
0x1800eee63  lea     r8, [rbp+57h+var_40]
0x1800eee67  call    ?Make@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Make(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>> * *)
0x1800eee6c  mov     ebx, eax
0x1800eee6e  test    eax, eax
0x1800eee70  jns     short loc_1800EEE8F
0x1800eee72  mov     rcx, [rbp+5Fh]; this
0x1800eee76  mov     r9d, eax; char *
0x1800eee79  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800eee80  mov     edx, 0B5Bh; void *
0x1800eee85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eee8a  jmp     loc_1800EF369
0x1800eee8f  mov     [rbp+57h+var_A0], r12b
0x1800eee93  mov     [rbp+57h+var_9E], r12b
0x1800eee97  mov     [rbp+57h+var_88], r12
0x1800eee9b  mov     rax, [rdi]
0x1800eee9e  mov     rbx, [rax]
0x1800eeea1  lea     rcx, [rbp+57h+var_88]
0x1800eeea5  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800eeeaa  lea     r8, [rbp+57h+var_88]
0x1800eeeae  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x1800eeeb5  mov     rcx, rdi
0x1800eeeb8  mov     rax, rbx
0x1800eeebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eeec0  mov     ebx, eax
0x1800eeec2  test    eax, eax
0x1800eeec4  jns     short loc_1800EEEED
0x1800eeec6  mov     rcx, [rbp+5Fh]; this
0x1800eeeca  mov     r9d, eax; char *
0x1800eeecd  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800eeed4  mov     edx, 0B64h; void *
0x1800eeed9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eeede  nop
0x1800eeedf  lea     rcx, [rbp+57h+var_88]
0x1800eeee3  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800eeee8  jmp     loc_1800EF369
0x1800eeeed  mov     [rbp+57h+var_98], r12
0x1800eeef1  mov     rdi, [rbp+57h+var_88]
0x1800eeef5  mov     rax, [rdi]
0x1800eeef8  mov     rbx, [rax+30h]
0x1800eeefc  lea     rcx, [rbp+57h+var_98]
0x1800eef00  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800eef05  lea     rdx, [rbp+57h+var_98]
0x1800eef09  mov     rcx, rdi
0x1800eef0c  mov     rax, rbx
0x1800eef0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eef14  mov     ebx, eax
0x1800eef16  test    eax, eax
0x1800eef18  jns     short loc_1800EEF3E
0x1800eef1a  mov     rcx, [rbp+5Fh]; this
0x1800eef1e  mov     r9d, eax; char *
0x1800eef21  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800eef28  mov     edx, 0B67h; void *
0x1800eef2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eef32  nop
0x1800eef33  lea     rcx, [rbp+57h+var_98]
0x1800eef37  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800eef3c  jmp     short loc_1800EEEDF
0x1800eef3e  mov     [rbp+57h+var_9F], r12b
0x1800eef42  mov     rcx, [rbp+57h+var_98]
0x1800eef46  mov     rax, [rcx]
0x1800eef49  lea     rdx, [rbp+57h+var_A0]
0x1800eef4d  mov     rax, [rax+38h]
0x1800eef51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eef56  mov     rbx, [rbp+57h+var_40]
0x1800eef5a  test    eax, eax
0x1800eef5c  js      loc_1800EF0F0
0x1800eef62  cmp     [rbp+57h+var_A0], r12b
0x1800eef66  jz      loc_1800EF0F0
0x1800eef6c  mov     [rbp+57h+var_70], r12
0x1800eef70  mov     rcx, [rbp+57h+var_98]
0x1800eef74  mov     rax, [rcx]
0x1800eef77  lea     rdx, [rbp+57h+var_70]
0x1800eef7b  mov     rax, [rax+30h]
0x1800eef7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eef84  mov     edi, eax
0x1800eef86  test    eax, eax
0x1800eef88  js      loc_1800EF0B3
0x1800eef8e  mov     [rbp+57h+var_78], r12
0x1800eef92  mov     rcx, [rbp+57h+var_70]
0x1800eef96  mov     rax, [rcx]
0x1800eef99  lea     rdx, [rbp+57h+var_78]
0x1800eef9d  mov     rax, [rax+30h]
0x1800eefa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eefa6  mov     edi, eax
0x1800eefa8  test    eax, eax
0x1800eefaa  js      loc_1800EF089
0x1800eefb0  mov     [rbp+57h+string], r12
0x1800eefb4  mov     rcx, [rbp+57h+var_70]
0x1800eefb8  mov     rax, [rcx]
0x1800eefbb  lea     rdx, [rbp+57h+string]
0x1800eefbf  mov     rax, [rax+38h]
0x1800eefc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eefc8  mov     edi, eax
0x1800eefca  test    eax, eax
0x1800eefcc  js      loc_1800EF05F
0x1800eefd2  test    sil, sil
0x1800eefd5  jz      short loc_1800EEFFC
0x1800eefd7  mov     [rbp+57h+var_9F], r12b
0x1800eefdb  mov     rax, [r14]
0x1800eefde  lea     r8, [rbp+57h+var_9F]
0x1800eefe2  mov     rdx, [rbp+57h+var_78]
0x1800eefe6  mov     rcx, r14
0x1800eefe9  mov     rax, [rax+40h]
0x1800eefed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eeff2  test    eax, eax
0x1800eeff4  js      short loc_1800EEFFC
0x1800eeff6  cmp     [rbp+57h+var_9F], r12b
0x1800eeffa  jnz     short loc_1800EF016
0x1800eeffc  lea     r9, [rbp+57h+var_9E]
0x1800ef000  mov     r8, [rbp+57h+string]
0x1800ef004  mov     rdx, [rbp+57h+var_78]
0x1800ef008  mov     rcx, rbx
0x1800ef00b  call    ?Insert@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@0PEAE@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,HSTRING__ *,uchar *)
0x1800ef010  mov     edi, eax
0x1800ef012  test    eax, eax
0x1800ef014  js      short loc_1800EF058
0x1800ef016  mov     rcx, [rbp+57h+string]; string
0x1800ef01a  test    rcx, rcx
0x1800ef01d  jz      short loc_1800EF026
0x1800ef01f  call    cs:__imp_WindowsDeleteString
0x1800ef025  nop
0x1800ef026  mov     rcx, [rbp+57h+var_78]; string
0x1800ef02a  test    rcx, rcx
0x1800ef02d  jz      short loc_1800EF036
0x1800ef02f  call    cs:__imp_WindowsDeleteString
0x1800ef035  nop
0x1800ef036  lea     rcx, [rbp+57h+var_70]
0x1800ef03a  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800ef03f  mov     rcx, [rbp+57h+var_98]
0x1800ef043  mov     rax, [rcx]
0x1800ef046  lea     rdx, [rbp+57h+var_A0]
0x1800ef04a  mov     rax, [rax+40h]
0x1800ef04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef053  jmp     loc_1800EEF5A
0x1800ef058  mov     edx, 0B81h
0x1800ef05d  jmp     short loc_1800EF064
0x1800ef05f  mov     edx, 0B75h; void *
0x1800ef064  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800ef06b  mov     r9d, edi; char *
0x1800ef06e  mov     rcx, [rbp+5Fh]; this
0x1800ef072  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef077  nop
0x1800ef078  mov     rcx, [rbp+57h+string]; string
0x1800ef07c  test    rcx, rcx
0x1800ef07f  jz      short loc_1800EF0A2
0x1800ef081  call    cs:__imp_WindowsDeleteString
0x1800ef087  jmp     short loc_1800EF0A2
0x1800ef089  mov     rcx, [rbp+5Fh]; this
0x1800ef08d  mov     r9d, edi; char *
0x1800ef090  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800ef097  mov     edx, 0B72h; void *
0x1800ef09c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef0a1  nop
0x1800ef0a2  mov     rcx, [rbp+57h+var_78]; string
0x1800ef0a6  test    rcx, rcx
0x1800ef0a9  jz      short loc_1800EF0CC
0x1800ef0ab  call    cs:__imp_WindowsDeleteString
0x1800ef0b1  jmp     short loc_1800EF0CC
0x1800ef0b3  mov     rcx, [rbp+5Fh]; this
0x1800ef0b7  mov     r9d, edi; char *
0x1800ef0ba  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800ef0c1  mov     edx, 0B6Fh; void *
0x1800ef0c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef0cb  nop
0x1800ef0cc  lea     rcx, [rbp+57h+var_70]
0x1800ef0d0  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800ef0d5  nop
0x1800ef0d6  lea     rcx, [rbp+57h+var_98]
0x1800ef0da  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800ef0df  nop
0x1800ef0e0  lea     rcx, [rbp+57h+var_88]
0x1800ef0e4  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800ef0e9  mov     ebx, edi
0x1800ef0eb  jmp     loc_1800EF369
0x1800ef0f0  lea     rcx, [rbp+57h+var_98]
0x1800ef0f4  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800ef0f9  nop
0x1800ef0fa  lea     rcx, [rbp+57h+var_88]
0x1800ef0fe  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800ef103  test    sil, sil
0x1800ef106  jnz     loc_1800EF31B
0x1800ef10c  mov     [rbp+57h+var_80], r12
0x1800ef110  mov     rax, [r14]
0x1800ef113  mov     rdi, [rax]
0x1800ef116  lea     rcx, [rbp+57h+var_80]
0x1800ef11a  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800ef11f  lea     r8, [rbp+57h+var_80]
0x1800ef123  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x1800ef12a  mov     rcx, r14
0x1800ef12d  mov     rax, rdi
0x1800ef130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef135  mov     edi, eax
0x1800ef137  test    eax, eax
0x1800ef139  jns     short loc_1800EF15A
0x1800ef13b  mov     rcx, [rbp+5Fh]; this
0x1800ef13f  mov     r9d, eax; char *
0x1800ef142  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800ef149  mov     edx, 0B8Ah; void *
0x1800ef14e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef153  nop
0x1800ef154  lea     rcx, [rbp+57h+var_80]
0x1800ef158  jmp     short loc_1800EF0E4
0x1800ef15a  mov     [rbp+57h+var_90], r12
0x1800ef15e  mov     rsi, [rbp+57h+var_80]
0x1800ef162  mov     rax, [rsi]
0x1800ef165  mov     rdi, [rax+30h]
0x1800ef169  lea     rcx, [rbp+57h+var_90]
0x1800ef16d  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800ef172  lea     rdx, [rbp+57h+var_90]
0x1800ef176  mov     rcx, rsi
0x1800ef179  mov     rax, rdi
0x1800ef17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef181  mov     edi, eax
0x1800ef183  test    eax, eax
0x1800ef185  jns     short loc_1800EF1AB
0x1800ef187  mov     rcx, [rbp+5Fh]; this
0x1800ef18b  mov     r9d, eax; char *
0x1800ef18e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800ef195  mov     edx, 0B8Dh; void *
0x1800ef19a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef19f  nop
0x1800ef1a0  lea     rcx, [rbp+57h+var_90]
0x1800ef1a4  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800ef1a9  jmp     short loc_1800EF154
0x1800ef1ab  mov     rcx, [rbp+57h+var_90]
0x1800ef1af  mov     rax, [rcx]
0x1800ef1b2  mov     rax, [rax+38h]
0x1800ef1b6  lea     rdx, [rbp+57h+var_A0]
0x1800ef1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef1bf  test    eax, eax
0x1800ef1c1  js      loc_1800EF308
0x1800ef1c7  cmp     [rbp+57h+var_A0], r12b
0x1800ef1cb  jz      loc_1800EF308
0x1800ef1d1  mov     [rbp+57h+var_68], r12
0x1800ef1d5  mov     rcx, [rbp+57h+var_90]
0x1800ef1d9  mov     rax, [rcx]
0x1800ef1dc  lea     rdx, [rbp+57h+var_68]
0x1800ef1e0  mov     rax, [rax+30h]
0x1800ef1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef1e9  mov     edi, eax
0x1800ef1eb  test    eax, eax
0x1800ef1ed  js      loc_1800EF2E1
0x1800ef1f3  mov     [rbp+57h+var_58], r12
0x1800ef1f7  mov     rcx, [rbp+57h+var_68]
0x1800ef1fb  mov     rax, [rcx]
0x1800ef1fe  lea     rdx, [rbp+57h+var_58]
0x1800ef202  mov     rax, [rax+30h]
0x1800ef206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef20b  mov     edi, eax
0x1800ef20d  test    eax, eax
0x1800ef20f  js      loc_1800EF2B7
0x1800ef215  mov     [rbp+57h+var_48], r12
0x1800ef219  mov     rcx, [rbp+57h+var_68]
0x1800ef21d  mov     rax, [rcx]
0x1800ef220  lea     rdx, [rbp+57h+var_48]
0x1800ef224  mov     rax, [rax+38h]
0x1800ef228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef22d  mov     edi, eax
0x1800ef22f  test    eax, eax
0x1800ef231  js      short loc_1800EF28D
0x1800ef233  lea     r9, [rbp+57h+var_9E]
0x1800ef237  mov     r8, [rbp+57h+var_48]
0x1800ef23b  mov     rdx, [rbp+57h+var_58]
0x1800ef23f  mov     rcx, rbx
0x1800ef242  call    ?Insert@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@0PEAE@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,HSTRING__ *,uchar *)
0x1800ef247  mov     edi, eax
0x1800ef249  test    eax, eax
0x1800ef24b  js      short loc_1800EF286
0x1800ef24d  mov     rcx, [rbp+57h+var_48]; string
0x1800ef251  test    rcx, rcx
0x1800ef254  jz      short loc_1800EF25D
0x1800ef256  call    cs:__imp_WindowsDeleteString
0x1800ef25c  nop
0x1800ef25d  mov     rcx, [rbp+57h+var_58]; string
0x1800ef261  test    rcx, rcx
0x1800ef264  jz      short loc_1800EF26D
0x1800ef266  call    cs:__imp_WindowsDeleteString
0x1800ef26c  nop
0x1800ef26d  lea     rcx, [rbp+57h+var_68]
0x1800ef271  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800ef276  mov     rcx, [rbp+57h+var_90]
0x1800ef27a  mov     rax, [rcx]
0x1800ef27d  mov     rax, [rax+40h]
  ... truncated ...
```
