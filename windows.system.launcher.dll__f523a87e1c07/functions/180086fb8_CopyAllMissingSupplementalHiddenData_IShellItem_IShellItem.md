# CopyAllMissingSupplementalHiddenData(IShellItem *,IShellItem *)

- ea: `0x180086fb8`
- end: `0x180087292`
- name: `?CopyAllMissingSupplementalHiddenData@@YAJPEAUIShellItem@@0@Z`
- size: `730`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IShellItem *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004e94c`
- `0x180086c28`

## callees

- `0x180010c04`
- `0x180041e84`
- `0x18004966c`
- `0x180086fb8`
- `0x1800e6410`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800870f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008717c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800871eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008722d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008725f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800870f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008717c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800871eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008722d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008725f`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
  bool v12; // zf
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *, struct _ITEMID_CHILD **); // rbx
  struct _ITEMID_CHILD *v15; // rcx
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  void *v18; // rcx
  int v19; // eax
  void *v20; // rcx
  struct _ITEMID_CHILD *v21; // rcx
  void *v22; // rcx
  int v24; // [rsp+20h] [rbp-50h]
  LPVOID v25; // [rsp+30h] [rbp-40h] BYREF
  __int64 v26; // [rsp+38h] [rbp-38h] BYREF
  __int64 v27; // [rsp+40h] [rbp-30h] BYREF
  __int64 v28; // [rsp+48h] [rbp-28h] BYREF
  void *p_pv; // [rsp+50h] [rbp-20h] BYREF
  struct _ITEMID_CHILD *v30; // [rsp+58h] [rbp-18h] BYREF
  char v31; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  LPVOID pv; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v34; // [rsp+B0h] [rbp+40h] BYREF
  struct _ITEMID_CHILD *v35; // [rsp+B8h] [rbp+48h] BYREF

  v28 = 0;
  QueryInterface = a1->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v28);
  v5 = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64 *))QueryInterface)(
         a1,
         &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
         &v28);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v34 = 0;
    v7 = a2->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v34);
    v8 = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64 *))v7)(
           a2,
           &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
           &v34);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
        (const char *)(unsigned int)v8,
        v24);
LABEL_5:
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v34);
      goto LABEL_31;
    }
    v9 = v28;
    if ( v28 != v34 )
    {
      v27 = 0;
      pv = 0;
      v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, struct _ITEMID_CHILD **))(*(_QWORD *)v28 + 32LL);
      p_pv = &pv;
      v30 = 0;
      v31 = 1;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
      v6 = v10(v9, 0, &v27, &v30);
      wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x113,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
          (const char *)(unsigned int)v6,
          v24);
LABEL_9:
        v11 = pv;
        v12 = pv == 0;
        pv = 0;
        if ( !v12 )
          CoTaskMemFree(v11);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
        goto LABEL_5;
      }
      v26 = 0;
      v35 = 0;
      v13 = v34;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, struct _ITEMID_CHILD **))(*(_QWORD *)v34 + 32LL);
      p_pv = &v35;
      v30 = 0;
      v31 = 1;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
      v6 = v14(v13, 0, &v26, &v30);
      wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x117,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
          (const char *)(unsigned int)v6,
          v24);
LABEL_14:
        v15 = v35;
        v12 = v35 == 0;
        v35 = 0;
        if ( !v12 )
          CoTaskMemFree(v15);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
        goto LABEL_9;
      }
      v25 = 0;
      p_pv = &v25;
      v30 = 0;
      v31 = 1;
      v6 = CopyAllMissingSupplementalHiddenData((const struct _ITEMID_CHILD *)pv, v35, &v30);
      wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
      if ( v6 < 0 )
      {
        v16 = (unsigned int)v6;
        v17 = 282;
        goto LABEL_19;
      }
      v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, LPVOID))(*(_QWORD *)v34 + 24LL))(v34, 0, v26, v25);
      v6 = v19;
      if ( v19 < 0 )
      {
        v16 = (unsigned int)v19;
        v17 = 284;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
          (const char *)v16,
          v24);
        v18 = v25;
        v12 = v25 == 0;
        v25 = 0;
        if ( !v12 )
          CoTaskMemFree(v18);
        goto LABEL_14;
      }
      v20 = v25;
      v25 = 0;
      if ( v20 )
        CoTaskMemFree(v20);
      v21 = v35;
      v35 = 0;
      if ( v21 )
        CoTaskMemFree(v21);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
      v22 = pv;
      pv = 0;
      if ( v22 )
        CoTaskMemFree(v22);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v34);
    v6 = 0;
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x107,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\hiddenproperties.h",
    (const char *)(unsigned int)v5,
    v24);
LABEL_31:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v28);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180086fb8  push    rbp
0x180086fba  push    rbx
0x180086fbb  push    rsi
0x180086fbc  push    rdi
0x180086fbd  push    r14
0x180086fbf  mov     rbp, rsp
0x180086fc2  sub     rsp, 70h
0x180086fc6  mov     rsi, rdx
0x180086fc9  mov     rdi, rcx
0x180086fcc  xor     r14d, r14d
0x180086fcf  mov     [rbp+var_28], r14
0x180086fd3  mov     rax, [rcx]
0x180086fd6  mov     rbx, [rax]
0x180086fd9  lea     rcx, [rbp+var_28]
0x180086fdd  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180086fe2  lea     r8, [rbp+var_28]
0x180086fe6  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x180086fed  mov     rcx, rdi
0x180086ff0  mov     rax, rbx
0x180086ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086ff8  mov     ebx, eax
0x180086ffa  test    eax, eax
0x180086ffc  jns     short loc_18008701B
0x180086ffe  mov     rcx, [rbp+28h]; this
0x180087002  mov     r9d, eax; char *
0x180087005  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18008700c  mov     edx, 107h; void *
0x180087011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087016  jmp     loc_18008727C
0x18008701b  mov     [rbp+arg_10], r14
0x18008701f  mov     rax, [rsi]
0x180087022  mov     rbx, [rax]
0x180087025  lea     rcx, [rbp+arg_10]
0x180087029  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18008702e  lea     r8, [rbp+arg_10]
0x180087032  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x180087039  mov     rcx, rsi
0x18008703c  mov     rax, rbx
0x18008703f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087044  mov     ebx, eax
0x180087046  test    eax, eax
0x180087048  jns     short loc_180087071
0x18008704a  mov     rcx, [rbp+28h]; this
0x18008704e  mov     r9d, eax; char *
0x180087051  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180087058  mov     edx, 10Ah; void *
0x18008705d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087062  nop
0x180087063  lea     rcx, [rbp+arg_10]
0x180087067  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18008706c  jmp     loc_18008727C
0x180087071  mov     rbx, [rbp+var_28]
0x180087075  cmp     rbx, [rbp+arg_10]
0x180087079  jz      loc_180087270
0x18008707f  mov     [rbp+var_30], r14
0x180087083  mov     [rbp+pv], r14
0x180087087  mov     rax, [rbx]
0x18008708a  mov     rdi, [rax+20h]
0x18008708e  lea     rax, [rbp+pv]
0x180087092  mov     [rbp+var_20], rax
0x180087096  mov     [rbp+var_18], r14
0x18008709a  mov     [rbp+var_10], 1
0x18008709e  lea     rcx, [rbp+var_30]
0x1800870a2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800870a7  lea     r9, [rbp+var_18]
0x1800870ab  lea     r8, [rbp+var_30]
0x1800870af  xor     edx, edx
0x1800870b1  mov     rcx, rbx
0x1800870b4  mov     rax, rdi
0x1800870b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800870bc  mov     ebx, eax
0x1800870be  lea     rcx, [rbp+var_20]
0x1800870c2  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800870c7  test    ebx, ebx
0x1800870c9  jns     short loc_180087106
0x1800870cb  mov     rcx, [rbp+28h]; this
0x1800870cf  mov     r9d, ebx; char *
0x1800870d2  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800870d9  mov     edx, 113h; void *
0x1800870de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800870e3  nop
0x1800870e4  mov     rcx, [rbp+pv]; pv
0x1800870e8  test    rcx, rcx
0x1800870eb  mov     [rbp+pv], r14
0x1800870ef  jz      short loc_1800870F8
0x1800870f1  call    cs:__imp_CoTaskMemFree
0x1800870f7  nop
0x1800870f8  lea     rcx, [rbp+var_30]
0x1800870fc  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180087101  jmp     loc_180087063
0x180087106  mov     [rbp+var_38], r14
0x18008710a  mov     [rbp+arg_18], r14
0x18008710e  mov     rdi, [rbp+arg_10]
0x180087112  mov     rax, [rdi]
0x180087115  mov     rbx, [rax+20h]
0x180087119  lea     rax, [rbp+arg_18]
0x18008711d  mov     [rbp+var_20], rax
0x180087121  mov     [rbp+var_18], r14
0x180087125  mov     [rbp+var_10], 1
0x180087129  lea     rcx, [rbp+var_38]
0x18008712d  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180087132  lea     r9, [rbp+var_18]
0x180087136  lea     r8, [rbp+var_38]
0x18008713a  xor     edx, edx
0x18008713c  mov     rcx, rdi
0x18008713f  mov     rax, rbx
0x180087142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087147  mov     ebx, eax
0x180087149  lea     rcx, [rbp+var_20]
0x18008714d  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180087152  test    ebx, ebx
0x180087154  jns     short loc_180087191
0x180087156  mov     rcx, [rbp+28h]; this
0x18008715a  mov     r9d, ebx; char *
0x18008715d  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180087164  mov     edx, 117h; void *
0x180087169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008716e  nop
0x18008716f  mov     rcx, [rbp+arg_18]; pv
0x180087173  test    rcx, rcx
0x180087176  mov     [rbp+arg_18], r14
0x18008717a  jz      short loc_180087183
0x18008717c  call    cs:__imp_CoTaskMemFree
0x180087182  nop
0x180087183  lea     rcx, [rbp+var_38]
0x180087187  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18008718c  jmp     loc_1800870E4
0x180087191  mov     [rbp+var_40], r14
0x180087195  lea     rax, [rbp+var_40]
0x180087199  mov     [rbp+var_20], rax
0x18008719d  mov     [rbp+var_18], r14
0x1800871a1  mov     [rbp+var_10], 1
0x1800871a5  lea     r8, [rbp+var_18]; struct _ITEMID_CHILD **
0x1800871a9  mov     rdx, [rbp+arg_18]; struct _ITEMID_CHILD *
0x1800871ad  mov     rcx, [rbp+pv]; struct _ITEMID_CHILD *
0x1800871b1  call    ?CopyAllMissingSupplementalHiddenData@@YAJPEFBU_ITEMID_CHILD@@0PEAPEAU1@@Z; CopyAllMissingSupplementalHiddenData(_ITEMID_CHILD const *,_ITEMID_CHILD const *,_ITEMID_CHILD * *)
0x1800871b6  mov     ebx, eax
0x1800871b8  lea     rcx, [rbp+var_20]
0x1800871bc  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800871c1  test    ebx, ebx
0x1800871c3  jns     short loc_1800871F6
0x1800871c5  mov     r9d, ebx; char *
0x1800871c8  mov     edx, 11Ah; void *
0x1800871cd  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800871d4  mov     rcx, [rbp+28h]; this
0x1800871d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800871dd  nop
0x1800871de  mov     rcx, [rbp+var_40]; pv
0x1800871e2  test    rcx, rcx
0x1800871e5  mov     [rbp+var_40], r14
0x1800871e9  jz      short loc_18008716F
0x1800871eb  call    cs:__imp_CoTaskMemFree
0x1800871f1  jmp     loc_18008716F
0x1800871f6  mov     rcx, [rbp+arg_10]
0x1800871fa  mov     rax, [rcx]
0x1800871fd  mov     r9, [rbp+var_40]
0x180087201  mov     r8, [rbp+var_38]
0x180087205  xor     edx, edx
0x180087207  mov     rax, [rax+18h]
0x18008720b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087210  mov     ebx, eax
0x180087212  test    eax, eax
0x180087214  jns     short loc_180087220
0x180087216  mov     r9d, eax
0x180087219  mov     edx, 11Ch
0x18008721e  jmp     short loc_1800871CD
0x180087220  mov     rcx, [rbp+var_40]; pv
0x180087224  mov     [rbp+var_40], r14
0x180087228  test    rcx, rcx
0x18008722b  jz      short loc_180087234
0x18008722d  call    cs:__imp_CoTaskMemFree
0x180087233  nop
0x180087234  mov     rcx, [rbp+arg_18]; pv
0x180087238  mov     [rbp+arg_18], r14
0x18008723c  test    rcx, rcx
0x18008723f  jz      short loc_180087248
0x180087241  call    cs:__imp_CoTaskMemFree
0x180087247  nop
0x180087248  lea     rcx, [rbp+var_38]
0x18008724c  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180087251  nop
0x180087252  mov     rcx, [rbp+pv]; pv
0x180087256  mov     [rbp+pv], r14
0x18008725a  test    rcx, rcx
0x18008725d  jz      short loc_180087266
0x18008725f  call    cs:__imp_CoTaskMemFree
0x180087265  nop
0x180087266  lea     rcx, [rbp+var_30]
0x18008726a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18008726f  nop
0x180087270  lea     rcx, [rbp+arg_10]
0x180087274  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180087279  mov     ebx, r14d
0x18008727c  lea     rcx, [rbp+var_28]
0x180087280  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180087285  mov     eax, ebx
0x180087287  add     rsp, 70h
0x18008728b  pop     r14
0x18008728d  pop     rdi
0x18008728e  pop     rsi
0x18008728f  pop     rbx
0x180087290  pop     rbp
0x180087291  retn
```
