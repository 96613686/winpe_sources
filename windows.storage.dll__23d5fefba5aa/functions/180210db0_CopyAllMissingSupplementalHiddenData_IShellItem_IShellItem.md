# CopyAllMissingSupplementalHiddenData(IShellItem *,IShellItem *)

- ea: `0x180210db0`
- end: `0x1802112a0`
- name: `?CopyAllMissingSupplementalHiddenData@@YAJPEAUIShellItem@@0@Z`
- size: `1264`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IShellItem *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180210774`

## callees

- `0x180009fc0`
- `0x180038f50`
- `0x1801470fc`
- `0x180210db0`
- `0x1803b1f60`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180210eec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180210f26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180210fe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021101c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180211050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802110f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180211154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021116e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180211192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802111d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802111ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021121e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180210eec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180210f26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180210fe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021101c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180211050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802110f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180211154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021116e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180211192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802111d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802111ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021121e`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CopyAllMissingSupplementalHiddenData(struct IShellItem *a1, struct IShellItem *a2)
{
  HRESULT (__stdcall *QueryInterface)(IShellItem *, const IID *const, void **); // rbx
  int v5; // eax
  int v6; // ebx
  HRESULT (__stdcall *v7)(IShellItem *, const IID *const, void **); // rbx
  int v8; // eax
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *, struct _ITEMID_CHILD **); // rdi
  void *v11; // rcx
  void *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *, struct _ITEMID_CHILD **); // rbx
  struct _ITEMID_CHILD *v18; // rcx
  struct _ITEMID_CHILD *v19; // rcx
  __int64 v20; // rcx
  void *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  void *v25; // rcx
  unsigned __int64 v26; // r9
  __int64 v27; // rdx
  int v28; // eax
  void *v29; // rcx
  bool v30; // zf
  struct _ITEMID_CHILD *v31; // rcx
  void *v32; // rcx
  void *v34; // rcx
  struct _ITEMID_CHILD *v35; // rcx
  __int64 v36; // rcx
  void *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  int v41; // [rsp+20h] [rbp-29h]
  struct _ITEMID_CHILD *v42; // [rsp+38h] [rbp-11h] BYREF
  char v43; // [rsp+40h] [rbp-9h]
  __int64 v44; // [rsp+48h] [rbp-1h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+7h]
  struct _ITEMID_CHILD *v46; // [rsp+58h] [rbp+Fh]
  __int64 v47; // [rsp+60h] [rbp+17h] BYREF
  __int64 v48; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v49; // [rsp+70h] [rbp+27h] BYREF
  LPVOID v50; // [rsp+78h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v48 = 0;
  QueryInterface = a1->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  v5 = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64 *))QueryInterface)(
         a1,
         &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
         &v48);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
      (const char *)(unsigned int)v5,
      v41);
LABEL_52:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    return (unsigned int)v6;
  }
  v44 = 0;
  v7 = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  v8 = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64 *))v7)(
         a2,
         &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
         &v44);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
      (const char *)(unsigned int)v8,
      v41);
LABEL_51:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    goto LABEL_52;
  }
  v9 = v48;
  if ( v48 == v44 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    v6 = 0;
    goto LABEL_52;
  }
  v47 = 0;
  pv = 0;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, struct _ITEMID_CHILD **))(*(_QWORD *)v48 + 32LL);
  v42 = 0;
  v43 = 1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  v6 = v10(v9, 0, &v47, &v42);
  if ( v43 )
  {
    v11 = pv;
    pv = v42;
    if ( v11 )
      CoTaskMemFree(v11);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x113,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
      (const char *)(unsigned int)v6,
      v41);
    v12 = pv;
    pv = 0;
    if ( v12 )
      CoTaskMemFree(v12);
    v13 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return (unsigned int)v6;
  }
  v49 = 0;
  v46 = 0;
  v16 = v44;
  v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, struct _ITEMID_CHILD **))(*(_QWORD *)v44 + 32LL);
  v42 = 0;
  v43 = 1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  v6 = v17(v16, 0, &v49, &v42);
  if ( v43 )
  {
    v18 = v46;
    v46 = v42;
    if ( v18 )
      CoTaskMemFree(v18);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
      (const char *)(unsigned int)v6,
      v41);
    v19 = v46;
    v46 = 0;
    if ( v19 )
      CoTaskMemFree(v19);
    v20 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = pv;
    pv = 0;
    if ( v21 )
      CoTaskMemFree(v21);
    v22 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    return (unsigned int)v6;
  }
  v50 = 0;
  v42 = 0;
  v43 = 1;
  v6 = CopyAllMissingSupplementalHiddenData((const struct _ITEMID_CHILD *)pv, v46, &v42);
  if ( v43 )
  {
    v25 = v50;
    v50 = v42;
    if ( v25 )
      CoTaskMemFree(v25);
  }
  if ( v6 < 0 )
  {
    v26 = (unsigned int)v6;
    v27 = 282;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
      (const char *)v26,
      v41);
    v29 = v50;
    v30 = v50 == 0;
    v50 = 0;
    if ( !v30 )
      CoTaskMemFree(v29);
    v31 = v46;
    v30 = v46 == 0;
    v46 = 0;
    if ( !v30 )
      CoTaskMemFree(v31);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    v32 = pv;
    v30 = pv == 0;
    pv = 0;
    if ( !v30 )
      CoTaskMemFree(v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    goto LABEL_51;
  }
  v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, LPVOID))(*(_QWORD *)v44 + 24LL))(v44, 0, v49, v50);
  v6 = v28;
  if ( v28 < 0 )
  {
    v26 = (unsigned int)v28;
    v27 = 284;
    goto LABEL_44;
  }
  v34 = v50;
  v50 = 0;
  if ( v34 )
    CoTaskMemFree(v34);
  v35 = v46;
  v46 = 0;
  if ( v35 )
    CoTaskMemFree(v35);
  v36 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  v37 = pv;
  pv = 0;
  if ( v37 )
    CoTaskMemFree(v37);
  v38 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v39 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  v40 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  return 0;
}

```

## disassembly

```asm
0x180210db0  mov     [rsp-8+arg_10], rbx
0x180210db5  mov     [rsp-8+arg_18], rsi
0x180210dba  push    rbp
0x180210dbb  push    rdi
0x180210dbc  push    r14
0x180210dbe  lea     rbp, [rsp-47h]
0x180210dc3  sub     rsp, 90h
0x180210dca  mov     rax, cs:__security_cookie
0x180210dd1  xor     rax, rsp
0x180210dd4  mov     [rbp+57h+var_20], rax
0x180210dd8  mov     rsi, rdx
0x180210ddb  mov     rdi, rcx
0x180210dde  xor     r14d, r14d
0x180210de1  mov     [rbp+57h+var_38], r14
0x180210de5  mov     rax, [rcx]
0x180210de8  mov     rbx, [rax]
0x180210deb  lea     rcx, [rbp+57h+var_38]
0x180210def  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180210df4  lea     r8, [rbp+57h+var_38]
0x180210df8  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x180210dff  mov     rcx, rdi
0x180210e02  mov     rax, rbx
0x180210e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180210e0a  mov     ebx, eax
0x180210e0c  test    eax, eax
0x180210e0e  jns     short loc_180210E2D
0x180210e10  mov     rcx, [rbp+5Fh]; this
0x180210e14  mov     r9d, eax; char *
0x180210e17  lea     r8, aOnecoreuapInte_36; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180210e1e  mov     edx, 107h; void *
0x180210e23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180210e28  jmp     loc_1802111B3
0x180210e2d  mov     [rbp+57h+var_58], r14
0x180210e31  mov     rax, [rsi]
0x180210e34  mov     rbx, [rax]
0x180210e37  lea     rcx, [rbp+57h+var_58]
0x180210e3b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180210e40  lea     r8, [rbp+57h+var_58]
0x180210e44  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x180210e4b  mov     rcx, rsi
0x180210e4e  mov     rax, rbx
0x180210e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180210e56  mov     ebx, eax
0x180210e58  test    eax, eax
0x180210e5a  jns     short loc_180210E79
0x180210e5c  mov     rcx, [rbp+5Fh]; this
0x180210e60  mov     r9d, eax; char *
0x180210e63  lea     r8, aOnecoreuapInte_36; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180210e6a  mov     edx, 10Ah; void *
0x180210e6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180210e74  jmp     loc_1802111A9
0x180210e79  mov     rbx, [rbp+57h+var_38]
0x180210e7d  cmp     rbx, [rbp+57h+var_58]
0x180210e81  jnz     short loc_180210E94
0x180210e83  lea     rcx, [rbp+57h+var_58]
0x180210e87  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180210e8c  mov     ebx, r14d
0x180210e8f  jmp     loc_1802111B3
0x180210e94  mov     [rbp+57h+var_40], r14
0x180210e98  mov     [rbp+57h+pv], r14
0x180210e9c  mov     rax, [rbx]
0x180210e9f  mov     rdi, [rax+20h]
0x180210ea3  lea     rax, [rbp+57h+pv]
0x180210ea7  mov     [rbp+57h+var_70], rax
0x180210eab  mov     [rbp+57h+var_68], r14
0x180210eaf  mov     [rbp+57h+var_60], 1
0x180210eb3  lea     rcx, [rbp+57h+var_40]
0x180210eb7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180210ebc  lea     r9, [rbp+57h+var_68]
0x180210ec0  lea     r8, [rbp+57h+var_40]
0x180210ec4  xor     edx, edx
0x180210ec6  mov     rcx, rbx
0x180210ec9  mov     rax, rdi
0x180210ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180210ed1  mov     ebx, eax
0x180210ed3  cmp     [rbp+57h+var_60], r14b
0x180210ed7  jz      short loc_180210EF8
0x180210ed9  mov     r8, [rbp+57h+var_70]
0x180210edd  mov     rcx, [r8]; pv
0x180210ee0  mov     rdx, [rbp+57h+var_68]
0x180210ee4  mov     [r8], rdx
0x180210ee7  test    rcx, rcx
0x180210eea  jz      short loc_180210EF8
0x180210eec  call    cs:__imp_CoTaskMemFree
0x180210ef3  nop     dword ptr [rax+rax+00h]
0x180210ef8  test    ebx, ebx
0x180210efa  jns     loc_180210F86
0x180210f00  mov     rcx, [rbp+5Fh]; this
0x180210f04  mov     r9d, ebx; char *
0x180210f07  lea     r8, aOnecoreuapInte_36; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180210f0e  mov     edx, 113h; void *
0x180210f13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180210f18  nop
0x180210f19  mov     rcx, [rbp+57h+pv]; pv
0x180210f1d  mov     [rbp+57h+pv], r14
0x180210f21  test    rcx, rcx
0x180210f24  jz      short loc_180210F33
0x180210f26  call    cs:__imp_CoTaskMemFree
0x180210f2d  nop     dword ptr [rax+rax+00h]
0x180210f32  nop
0x180210f33  mov     rcx, [rbp+57h+var_40]
0x180210f37  test    rcx, rcx
0x180210f3a  jz      short loc_180210F4D
0x180210f3c  mov     [rbp+57h+var_40], r14
0x180210f40  mov     rax, [rcx]
0x180210f43  mov     rax, [rax+10h]
0x180210f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180210f4c  nop
0x180210f4d  mov     rcx, [rbp+57h+var_58]
0x180210f51  test    rcx, rcx
0x180210f54  jz      short loc_180210F67
0x180210f56  mov     [rbp+57h+var_58], r14
0x180210f5a  mov     rax, [rcx]
0x180210f5d  mov     rax, [rax+10h]
0x180210f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180210f66  nop
0x180210f67  mov     rcx, [rbp+57h+var_38]
0x180210f6b  test    rcx, rcx
0x180210f6e  jz      short loc_180210F81
0x180210f70  mov     [rbp+57h+var_38], r14
0x180210f74  mov     rax, [rcx]
0x180210f77  mov     rax, [rax+10h]
0x180210f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180210f80  nop
0x180210f81  jmp     loc_1802111BC
0x180210f86  mov     [rbp+57h+var_30], r14
0x180210f8a  mov     [rbp+57h+var_48], r14
0x180210f8e  mov     rdi, [rbp+57h+var_58]
0x180210f92  mov     rax, [rdi]
0x180210f95  mov     rbx, [rax+20h]
0x180210f99  lea     rax, [rbp+57h+var_48]
0x180210f9d  mov     [rbp+57h+var_70], rax
0x180210fa1  mov     [rbp+57h+var_68], r14
0x180210fa5  mov     [rbp+57h+var_60], 1
0x180210fa9  lea     rcx, [rbp+57h+var_30]
0x180210fad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180210fb2  lea     r9, [rbp+57h+var_68]
0x180210fb6  lea     r8, [rbp+57h+var_30]
0x180210fba  xor     edx, edx
0x180210fbc  mov     rcx, rdi
0x180210fbf  mov     rax, rbx
0x180210fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180210fc7  mov     ebx, eax
0x180210fc9  cmp     [rbp+57h+var_60], r14b
0x180210fcd  jz      short loc_180210FEE
0x180210fcf  mov     r8, [rbp+57h+var_70]
0x180210fd3  mov     rcx, [r8]; pv
0x180210fd6  mov     rdx, [rbp+57h+var_68]
0x180210fda  mov     [r8], rdx
0x180210fdd  test    rcx, rcx
0x180210fe0  jz      short loc_180210FEE
0x180210fe2  call    cs:__imp_CoTaskMemFree
0x180210fe9  nop     dword ptr [rax+rax+00h]
0x180210fee  test    ebx, ebx
0x180210ff0  jns     loc_1802110B0
0x180210ff6  mov     rcx, [rbp+5Fh]; this
0x180210ffa  mov     r9d, ebx; char *
0x180210ffd  lea     r8, aOnecoreuapInte_36; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180211004  mov     edx, 117h; void *
0x180211009  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021100e  nop
0x18021100f  mov     rcx, [rbp+57h+var_48]; pv
0x180211013  mov     [rbp+57h+var_48], r14
0x180211017  test    rcx, rcx
0x18021101a  jz      short loc_180211029
0x18021101c  call    cs:__imp_CoTaskMemFree
0x180211023  nop     dword ptr [rax+rax+00h]
0x180211028  nop
0x180211029  mov     rcx, [rbp+57h+var_30]
0x18021102d  test    rcx, rcx
0x180211030  jz      short loc_180211043
0x180211032  mov     [rbp+57h+var_30], r14
0x180211036  mov     rax, [rcx]
0x180211039  mov     rax, [rax+10h]
0x18021103d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180211042  nop
0x180211043  mov     rcx, [rbp+57h+pv]; pv
0x180211047  mov     [rbp+57h+pv], r14
0x18021104b  test    rcx, rcx
0x18021104e  jz      short loc_18021105D
0x180211050  call    cs:__imp_CoTaskMemFree
0x180211057  nop     dword ptr [rax+rax+00h]
0x18021105c  nop
0x18021105d  mov     rcx, [rbp+57h+var_40]
0x180211061  test    rcx, rcx
0x180211064  jz      short loc_180211077
0x180211066  mov     [rbp+57h+var_40], r14
0x18021106a  mov     rax, [rcx]
0x18021106d  mov     rax, [rax+10h]
0x180211071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180211076  nop
0x180211077  mov     rcx, [rbp+57h+var_58]
0x18021107b  test    rcx, rcx
0x18021107e  jz      short loc_180211091
0x180211080  mov     [rbp+57h+var_58], r14
0x180211084  mov     rax, [rcx]
0x180211087  mov     rax, [rax+10h]
0x18021108b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180211090  nop
0x180211091  mov     rcx, [rbp+57h+var_38]
0x180211095  test    rcx, rcx
0x180211098  jz      short loc_1802110AB
0x18021109a  mov     [rbp+57h+var_38], r14
0x18021109e  mov     rax, [rcx]
0x1802110a1  mov     rax, [rax+10h]
0x1802110a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802110aa  nop
0x1802110ab  jmp     loc_1802111BC
0x1802110b0  mov     [rbp+57h+var_28], r14
0x1802110b4  lea     rax, [rbp+57h+var_28]
0x1802110b8  mov     [rbp+57h+var_70], rax
0x1802110bc  mov     [rbp+57h+var_68], r14
0x1802110c0  mov     [rbp+57h+var_60], 1
0x1802110c4  lea     r8, [rbp+57h+var_68]; struct _ITEMID_CHILD **
0x1802110c8  mov     rdx, [rbp+57h+var_48]; struct _ITEMID_CHILD *
0x1802110cc  mov     rcx, [rbp+57h+pv]; struct _ITEMID_CHILD *
0x1802110d0  call    ?CopyAllMissingSupplementalHiddenData@@YAJPEFBU_ITEMID_CHILD@@0PEAPEAU1@@Z; CopyAllMissingSupplementalHiddenData(_ITEMID_CHILD const *,_ITEMID_CHILD const *,_ITEMID_CHILD * *)
0x1802110d5  mov     ebx, eax
0x1802110d7  cmp     [rbp+57h+var_60], r14b
0x1802110db  jz      short loc_1802110FC
0x1802110dd  mov     r8, [rbp+57h+var_70]
0x1802110e1  mov     rcx, [r8]; pv
0x1802110e4  mov     rdx, [rbp+57h+var_68]
0x1802110e8  mov     [r8], rdx
0x1802110eb  test    rcx, rcx
0x1802110ee  jz      short loc_1802110FC
0x1802110f0  call    cs:__imp_CoTaskMemFree
0x1802110f7  nop     dword ptr [rax+rax+00h]
0x1802110fc  test    ebx, ebx
0x1802110fe  jns     short loc_18021110A
0x180211100  mov     r9d, ebx
0x180211103  mov     edx, 11Ah
0x180211108  jmp     short loc_180211136
0x18021110a  mov     rcx, [rbp+57h+var_58]
0x18021110e  mov     rax, [rcx]
0x180211111  mov     r9, [rbp+57h+var_28]
0x180211115  mov     r8, [rbp+57h+var_30]
0x180211119  xor     edx, edx
0x18021111b  mov     rax, [rax+18h]
0x18021111f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180211124  mov     ebx, eax
0x180211126  test    eax, eax
0x180211128  jns     loc_1802111C3
0x18021112e  mov     r9d, eax; char *
0x180211131  mov     edx, 11Ch; void *
0x180211136  lea     r8, aOnecoreuapInte_36; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18021113d  mov     rcx, [rbp+5Fh]; this
0x180211141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180211146  nop
0x180211147  mov     rcx, [rbp+57h+var_28]; pv
0x18021114b  test    rcx, rcx
0x18021114e  mov     [rbp+57h+var_28], r14
0x180211152  jz      short loc_180211161
0x180211154  call    cs:__imp_CoTaskMemFree
0x18021115b  nop     dword ptr [rax+rax+00h]
0x180211160  nop
0x180211161  mov     rcx, [rbp+57h+var_48]; pv
0x180211165  test    rcx, rcx
0x180211168  mov     [rbp+57h+var_48], r14
0x18021116c  jz      short loc_18021117B
0x18021116e  call    cs:__imp_CoTaskMemFree
0x180211175  nop     dword ptr [rax+rax+00h]
0x18021117a  nop
0x18021117b  lea     rcx, [rbp+57h+var_30]
0x18021117f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180211184  nop
0x180211185  mov     rcx, [rbp+57h+pv]; pv
0x180211189  test    rcx, rcx
0x18021118c  mov     [rbp+57h+pv], r14
0x180211190  jz      short loc_18021119F
0x180211192  call    cs:__imp_CoTaskMemFree
0x180211199  nop     dword ptr [rax+rax+00h]
0x18021119e  nop
0x18021119f  lea     rcx, [rbp+57h+var_40]
0x1802111a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802111a8  nop
0x1802111a9  lea     rcx, [rbp+57h+var_58]
0x1802111ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802111b2  nop
0x1802111b3  lea     rcx, [rbp+57h+var_38]
0x1802111b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802111bc  mov     eax, ebx
0x1802111be  jmp     loc_18021127B
0x1802111c3  mov     rcx, [rbp+57h+var_28]; pv
0x1802111c7  mov     [rbp+57h+var_28], r14
0x1802111cb  test    rcx, rcx
0x1802111ce  jz      short loc_1802111DD
0x1802111d0  call    cs:__imp_CoTaskMemFree
0x1802111d7  nop     dword ptr [rax+rax+00h]
0x1802111dc  nop
0x1802111dd  mov     rcx, [rbp+57h+var_48]; pv
0x1802111e1  mov     [rbp+57h+var_48], r14
0x1802111e5  test    rcx, rcx
0x1802111e8  jz      short loc_1802111F7
0x1802111ea  call    cs:__imp_CoTaskMemFree
0x1802111f1  nop     dword ptr [rax+rax+00h]
0x1802111f6  nop
0x1802111f7  mov     rcx, [rbp+57h+var_30]
0x1802111fb  test    rcx, rcx
0x1802111fe  jz      short loc_180211211
  ... truncated ...
```
