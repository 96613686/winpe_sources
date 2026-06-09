# CopyAllMissingSupplementalHiddenData(IShellItem *,IShellItem *)

- ea: `0x1801e7628`
- end: `0x1801e7acf`
- name: `?CopyAllMissingSupplementalHiddenData@@YAJPEAUIShellItem@@0@Z`
- size: `1191`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IShellItem *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801e6c50`

## callees

- `0x18000d6cc`
- `0x1800432f0`
- `0x1800ad4f4`
- `0x1801e7628`
- `0x1803a4cb0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e7764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e7798`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e784e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e7882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e78b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e794a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e79a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e79bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e79da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e7a12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e7a26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e7a54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e7764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e7798`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e784e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e7882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e78b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e794a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e79a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e79bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e79da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e7a12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e7a26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e7a54`

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
0x1801e7628  mov     [rsp-8+arg_10], rbx
0x1801e762d  mov     [rsp-8+arg_18], rsi
0x1801e7632  push    rbp
0x1801e7633  push    rdi
0x1801e7634  push    r14
0x1801e7636  lea     rbp, [rsp-47h]
0x1801e763b  sub     rsp, 90h
0x1801e7642  mov     rax, cs:__security_cookie
0x1801e7649  xor     rax, rsp
0x1801e764c  mov     [rbp+57h+var_20], rax
0x1801e7650  mov     rsi, rdx
0x1801e7653  mov     rdi, rcx
0x1801e7656  xor     r14d, r14d
0x1801e7659  mov     [rbp+57h+var_38], r14
0x1801e765d  mov     rax, [rcx]
0x1801e7660  mov     rbx, [rax]
0x1801e7663  lea     rcx, [rbp+57h+var_38]
0x1801e7667  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e766c  lea     r8, [rbp+57h+var_38]
0x1801e7670  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x1801e7677  mov     rcx, rdi
0x1801e767a  mov     rax, rbx
0x1801e767d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7682  mov     ebx, eax
0x1801e7684  test    eax, eax
0x1801e7686  jns     short loc_1801E76A5
0x1801e7688  mov     rcx, [rbp+5Fh]; this
0x1801e768c  mov     r9d, eax; char *
0x1801e768f  lea     r8, aOnecoreuapInte_37; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1801e7696  mov     edx, 107h; void *
0x1801e769b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e76a0  jmp     loc_1801E79F5
0x1801e76a5  mov     [rbp+57h+var_58], r14
0x1801e76a9  mov     rax, [rsi]
0x1801e76ac  mov     rbx, [rax]
0x1801e76af  lea     rcx, [rbp+57h+var_58]
0x1801e76b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e76b8  lea     r8, [rbp+57h+var_58]
0x1801e76bc  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x1801e76c3  mov     rcx, rsi
0x1801e76c6  mov     rax, rbx
0x1801e76c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e76ce  mov     ebx, eax
0x1801e76d0  test    eax, eax
0x1801e76d2  jns     short loc_1801E76F1
0x1801e76d4  mov     rcx, [rbp+5Fh]; this
0x1801e76d8  mov     r9d, eax; char *
0x1801e76db  lea     r8, aOnecoreuapInte_37; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1801e76e2  mov     edx, 10Ah; void *
0x1801e76e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e76ec  jmp     loc_1801E79EB
0x1801e76f1  mov     rbx, [rbp+57h+var_38]
0x1801e76f5  cmp     rbx, [rbp+57h+var_58]
0x1801e76f9  jnz     short loc_1801E770C
0x1801e76fb  lea     rcx, [rbp+57h+var_58]
0x1801e76ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e7704  mov     ebx, r14d
0x1801e7707  jmp     loc_1801E79F5
0x1801e770c  mov     [rbp+57h+var_40], r14
0x1801e7710  mov     [rbp+57h+pv], r14
0x1801e7714  mov     rax, [rbx]
0x1801e7717  mov     rdi, [rax+20h]
0x1801e771b  lea     rax, [rbp+57h+pv]
0x1801e771f  mov     [rbp+57h+var_70], rax
0x1801e7723  mov     [rbp+57h+var_68], r14
0x1801e7727  mov     [rbp+57h+var_60], 1
0x1801e772b  lea     rcx, [rbp+57h+var_40]
0x1801e772f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e7734  lea     r9, [rbp+57h+var_68]
0x1801e7738  lea     r8, [rbp+57h+var_40]
0x1801e773c  xor     edx, edx
0x1801e773e  mov     rcx, rbx
0x1801e7741  mov     rax, rdi
0x1801e7744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7749  mov     ebx, eax
0x1801e774b  cmp     [rbp+57h+var_60], r14b
0x1801e774f  jz      short loc_1801E776A
0x1801e7751  mov     r8, [rbp+57h+var_70]
0x1801e7755  mov     rcx, [r8]; pv
0x1801e7758  mov     rdx, [rbp+57h+var_68]
0x1801e775c  mov     [r8], rdx
0x1801e775f  test    rcx, rcx
0x1801e7762  jz      short loc_1801E776A
0x1801e7764  call    cs:__imp_CoTaskMemFree
0x1801e776a  test    ebx, ebx
0x1801e776c  jns     loc_1801E77F2
0x1801e7772  mov     rcx, [rbp+5Fh]; this
0x1801e7776  mov     r9d, ebx; char *
0x1801e7779  lea     r8, aOnecoreuapInte_37; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1801e7780  mov     edx, 113h; void *
0x1801e7785  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e778a  nop
0x1801e778b  mov     rcx, [rbp+57h+pv]; pv
0x1801e778f  mov     [rbp+57h+pv], r14
0x1801e7793  test    rcx, rcx
0x1801e7796  jz      short loc_1801E779F
0x1801e7798  call    cs:__imp_CoTaskMemFree
0x1801e779e  nop
0x1801e779f  mov     rcx, [rbp+57h+var_40]
0x1801e77a3  test    rcx, rcx
0x1801e77a6  jz      short loc_1801E77B9
0x1801e77a8  mov     [rbp+57h+var_40], r14
0x1801e77ac  mov     rax, [rcx]
0x1801e77af  mov     rax, [rax+10h]
0x1801e77b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e77b8  nop
0x1801e77b9  mov     rcx, [rbp+57h+var_58]
0x1801e77bd  test    rcx, rcx
0x1801e77c0  jz      short loc_1801E77D3
0x1801e77c2  mov     [rbp+57h+var_58], r14
0x1801e77c6  mov     rax, [rcx]
0x1801e77c9  mov     rax, [rax+10h]
0x1801e77cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e77d2  nop
0x1801e77d3  mov     rcx, [rbp+57h+var_38]
0x1801e77d7  test    rcx, rcx
0x1801e77da  jz      short loc_1801E77ED
0x1801e77dc  mov     [rbp+57h+var_38], r14
0x1801e77e0  mov     rax, [rcx]
0x1801e77e3  mov     rax, [rax+10h]
0x1801e77e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e77ec  nop
0x1801e77ed  jmp     loc_1801E79FE
0x1801e77f2  mov     [rbp+57h+var_30], r14
0x1801e77f6  mov     [rbp+57h+var_48], r14
0x1801e77fa  mov     rdi, [rbp+57h+var_58]
0x1801e77fe  mov     rax, [rdi]
0x1801e7801  mov     rbx, [rax+20h]
0x1801e7805  lea     rax, [rbp+57h+var_48]
0x1801e7809  mov     [rbp+57h+var_70], rax
0x1801e780d  mov     [rbp+57h+var_68], r14
0x1801e7811  mov     [rbp+57h+var_60], 1
0x1801e7815  lea     rcx, [rbp+57h+var_30]
0x1801e7819  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e781e  lea     r9, [rbp+57h+var_68]
0x1801e7822  lea     r8, [rbp+57h+var_30]
0x1801e7826  xor     edx, edx
0x1801e7828  mov     rcx, rdi
0x1801e782b  mov     rax, rbx
0x1801e782e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7833  mov     ebx, eax
0x1801e7835  cmp     [rbp+57h+var_60], r14b
0x1801e7839  jz      short loc_1801E7854
0x1801e783b  mov     r8, [rbp+57h+var_70]
0x1801e783f  mov     rcx, [r8]; pv
0x1801e7842  mov     rdx, [rbp+57h+var_68]
0x1801e7846  mov     [r8], rdx
0x1801e7849  test    rcx, rcx
0x1801e784c  jz      short loc_1801E7854
0x1801e784e  call    cs:__imp_CoTaskMemFree
0x1801e7854  test    ebx, ebx
0x1801e7856  jns     loc_1801E790A
0x1801e785c  mov     rcx, [rbp+5Fh]; this
0x1801e7860  mov     r9d, ebx; char *
0x1801e7863  lea     r8, aOnecoreuapInte_37; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1801e786a  mov     edx, 117h; void *
0x1801e786f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e7874  nop
0x1801e7875  mov     rcx, [rbp+57h+var_48]; pv
0x1801e7879  mov     [rbp+57h+var_48], r14
0x1801e787d  test    rcx, rcx
0x1801e7880  jz      short loc_1801E7889
0x1801e7882  call    cs:__imp_CoTaskMemFree
0x1801e7888  nop
0x1801e7889  mov     rcx, [rbp+57h+var_30]
0x1801e788d  test    rcx, rcx
0x1801e7890  jz      short loc_1801E78A3
0x1801e7892  mov     [rbp+57h+var_30], r14
0x1801e7896  mov     rax, [rcx]
0x1801e7899  mov     rax, [rax+10h]
0x1801e789d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e78a2  nop
0x1801e78a3  mov     rcx, [rbp+57h+pv]; pv
0x1801e78a7  mov     [rbp+57h+pv], r14
0x1801e78ab  test    rcx, rcx
0x1801e78ae  jz      short loc_1801E78B7
0x1801e78b0  call    cs:__imp_CoTaskMemFree
0x1801e78b6  nop
0x1801e78b7  mov     rcx, [rbp+57h+var_40]
0x1801e78bb  test    rcx, rcx
0x1801e78be  jz      short loc_1801E78D1
0x1801e78c0  mov     [rbp+57h+var_40], r14
0x1801e78c4  mov     rax, [rcx]
0x1801e78c7  mov     rax, [rax+10h]
0x1801e78cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e78d0  nop
0x1801e78d1  mov     rcx, [rbp+57h+var_58]
0x1801e78d5  test    rcx, rcx
0x1801e78d8  jz      short loc_1801E78EB
0x1801e78da  mov     [rbp+57h+var_58], r14
0x1801e78de  mov     rax, [rcx]
0x1801e78e1  mov     rax, [rax+10h]
0x1801e78e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e78ea  nop
0x1801e78eb  mov     rcx, [rbp+57h+var_38]
0x1801e78ef  test    rcx, rcx
0x1801e78f2  jz      short loc_1801E7905
0x1801e78f4  mov     [rbp+57h+var_38], r14
0x1801e78f8  mov     rax, [rcx]
0x1801e78fb  mov     rax, [rax+10h]
0x1801e78ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7904  nop
0x1801e7905  jmp     loc_1801E79FE
0x1801e790a  mov     [rbp+57h+var_28], r14
0x1801e790e  lea     rax, [rbp+57h+var_28]
0x1801e7912  mov     [rbp+57h+var_70], rax
0x1801e7916  mov     [rbp+57h+var_68], r14
0x1801e791a  mov     [rbp+57h+var_60], 1
0x1801e791e  lea     r8, [rbp+57h+var_68]; struct _ITEMID_CHILD **
0x1801e7922  mov     rdx, [rbp+57h+var_48]; struct _ITEMID_CHILD *
0x1801e7926  mov     rcx, [rbp+57h+pv]; struct _ITEMID_CHILD *
0x1801e792a  call    ?CopyAllMissingSupplementalHiddenData@@YAJPEFBU_ITEMID_CHILD@@0PEAPEAU1@@Z; CopyAllMissingSupplementalHiddenData(_ITEMID_CHILD const *,_ITEMID_CHILD const *,_ITEMID_CHILD * *)
0x1801e792f  mov     ebx, eax
0x1801e7931  cmp     [rbp+57h+var_60], r14b
0x1801e7935  jz      short loc_1801E7950
0x1801e7937  mov     r8, [rbp+57h+var_70]
0x1801e793b  mov     rcx, [r8]; pv
0x1801e793e  mov     rdx, [rbp+57h+var_68]
0x1801e7942  mov     [r8], rdx
0x1801e7945  test    rcx, rcx
0x1801e7948  jz      short loc_1801E7950
0x1801e794a  call    cs:__imp_CoTaskMemFree
0x1801e7950  test    ebx, ebx
0x1801e7952  jns     short loc_1801E795E
0x1801e7954  mov     r9d, ebx
0x1801e7957  mov     edx, 11Ah
0x1801e795c  jmp     short loc_1801E798A
0x1801e795e  mov     rcx, [rbp+57h+var_58]
0x1801e7962  mov     rax, [rcx]
0x1801e7965  mov     r9, [rbp+57h+var_28]
0x1801e7969  mov     r8, [rbp+57h+var_30]
0x1801e796d  xor     edx, edx
0x1801e796f  mov     rax, [rax+18h]
0x1801e7973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7978  mov     ebx, eax
0x1801e797a  test    eax, eax
0x1801e797c  jns     loc_1801E7A05
0x1801e7982  mov     r9d, eax; char *
0x1801e7985  mov     edx, 11Ch; void *
0x1801e798a  lea     r8, aOnecoreuapInte_37; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1801e7991  mov     rcx, [rbp+5Fh]; this
0x1801e7995  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e799a  nop
0x1801e799b  mov     rcx, [rbp+57h+var_28]; pv
0x1801e799f  test    rcx, rcx
0x1801e79a2  mov     [rbp+57h+var_28], r14
0x1801e79a6  jz      short loc_1801E79AF
0x1801e79a8  call    cs:__imp_CoTaskMemFree
0x1801e79ae  nop
0x1801e79af  mov     rcx, [rbp+57h+var_48]; pv
0x1801e79b3  test    rcx, rcx
0x1801e79b6  mov     [rbp+57h+var_48], r14
0x1801e79ba  jz      short loc_1801E79C3
0x1801e79bc  call    cs:__imp_CoTaskMemFree
0x1801e79c2  nop
0x1801e79c3  lea     rcx, [rbp+57h+var_30]
0x1801e79c7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e79cc  nop
0x1801e79cd  mov     rcx, [rbp+57h+pv]; pv
0x1801e79d1  test    rcx, rcx
0x1801e79d4  mov     [rbp+57h+pv], r14
0x1801e79d8  jz      short loc_1801E79E1
0x1801e79da  call    cs:__imp_CoTaskMemFree
0x1801e79e0  nop
0x1801e79e1  lea     rcx, [rbp+57h+var_40]
0x1801e79e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e79ea  nop
0x1801e79eb  lea     rcx, [rbp+57h+var_58]
0x1801e79ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e79f4  nop
0x1801e79f5  lea     rcx, [rbp+57h+var_38]
0x1801e79f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801e79fe  mov     eax, ebx
0x1801e7a00  jmp     loc_1801E7AAB
0x1801e7a05  mov     rcx, [rbp+57h+var_28]; pv
0x1801e7a09  mov     [rbp+57h+var_28], r14
0x1801e7a0d  test    rcx, rcx
0x1801e7a10  jz      short loc_1801E7A19
0x1801e7a12  call    cs:__imp_CoTaskMemFree
0x1801e7a18  nop
0x1801e7a19  mov     rcx, [rbp+57h+var_48]; pv
0x1801e7a1d  mov     [rbp+57h+var_48], r14
0x1801e7a21  test    rcx, rcx
0x1801e7a24  jz      short loc_1801E7A2D
0x1801e7a26  call    cs:__imp_CoTaskMemFree
0x1801e7a2c  nop
0x1801e7a2d  mov     rcx, [rbp+57h+var_30]
0x1801e7a31  test    rcx, rcx
0x1801e7a34  jz      short loc_1801E7A47
0x1801e7a36  mov     [rbp+57h+var_30], r14
0x1801e7a3a  mov     rax, [rcx]
0x1801e7a3d  mov     rax, [rax+10h]
0x1801e7a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7a46  nop
0x1801e7a47  mov     rcx, [rbp+57h+pv]; pv
0x1801e7a4b  mov     [rbp+57h+pv], r14
0x1801e7a4f  test    rcx, rcx
0x1801e7a52  jz      short loc_1801E7A5B
0x1801e7a54  call    cs:__imp_CoTaskMemFree
0x1801e7a5a  nop
  ... truncated ...
```
