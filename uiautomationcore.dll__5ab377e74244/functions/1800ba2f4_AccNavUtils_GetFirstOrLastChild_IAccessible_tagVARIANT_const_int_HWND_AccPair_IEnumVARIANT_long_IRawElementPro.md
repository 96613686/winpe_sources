# AccNavUtils::GetFirstOrLastChild(IAccessible *,tagVARIANT const &,int,HWND__ *,AccPair *,IEnumVARIANT * *,long *,IRawElementProviderFragment * *)

- ea: `0x1800ba2f4`
- end: `0x1800baa9b`
- name: `?GetFirstOrLastChild@AccNavUtils@@SAJPEAUIAccessible@@AEBUtagVARIANT@@HPEAUHWND__@@PEAUAccPair@@PEAPEAUIEnumVARIANT@@PEAJPEAPEAUIRawElementProviderFragment@@@Z`
- size: `1959`
- prototype: `__int64 __usercall@<rax>(struct IAccessible *@<rcx>, const struct tagVARIANT *@<rdx>, int@<r8d>, HWND@<r9>, struct AccPair *, struct IEnumVARIANT **, int *, struct IRawElementProviderFragment **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18011d950`

## callees

- `0x18000f680`
- `0x180013d90`
- `0x18001ed40`
- `0x180020230`
- `0x18002f580`
- `0x1800861ac`
- `0x1800b8740`
- `0x1800b8d60`
- `0x1800b9024`
- `0x1800ba0a0`
- `0x1800ba2f4`
- `0x1800bb9f4`
- `0x1800bbc88`
- `0x1801a1438`
- `0x18023791c`
- `0x1802dd010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800ba662`
- `OLEAUT32!__imp_VariantInit` at `0x1800ba662`
- `OLEAUT32!__imp_VariantClear` at `0x1800ba6e8`
- `OLEAUT32!__imp_VariantClear` at `0x1800ba919`
- `OLEAUT32!__imp_VariantClear` at `0x1800ba6e8`
- `OLEAUT32!__imp_VariantClear` at `0x1800ba919`

## string_xrefs

- `0x1800ba94e`: `onecore\windows\accessibletech\uiautomationcore\accnavutils.cpp`
- `0x1800ba966`: `onecore\windows\accessibletech\uiautomationcore\accnavutils.cpp`
- `0x1800baa32`: `onecore\windows\accessibletech\uiautomationcore\accnavutils.cpp`
- `0x1800ba668`: `IAccessible::get_accState`
- `0x1800ba7ad`: `onecore\windows\accessibletech\uiautomationcore\accutils.cpp`
- `0x1800ba7d4`: `onecore\windows\accessibletech\uiautomationcore\accutils.cpp`
- `0x1800ba8fa`: `onecore\windows\accessibletech\uiautomationcore\accutils.cpp`
- `0x1800ba9e4`: `onecore\windows\accessibletech\uiautomationcore\accutils.cpp`
- `0x1800ba34b`: `IAccessible::get_accChild`
- `0x1800ba44f`: `IAccessible::get_accChild`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AccNavUtils::GetFirstOrLastChild(
        struct IAccessible *a1,
        const struct tagVARIANT *a2,
        int a3,
        HWND a4,
        struct AccPair *a5,
        struct IEnumVARIANT **a6,
        int *a7,
        struct IRawElementProviderFragment **a8)
{
  int v9; // r12d
  struct IAccessible *v10; // r14
  struct IEnumVARIANT **v11; // r13
  int v12; // eax
  int v13; // ebx
  struct IEnumVARIANT *v15; // rdi
  struct IEnumVARIANT *v16; // rax
  struct IEnumVARIANT *v17; // rcx
  struct IEnumVARIANT *v18; // rbx
  int v19; // eax
  unsigned int v20; // esi
  LONG v21; // r12d
  int v22; // eax
  int v23; // ebx
  int v24; // eax
  unsigned int v25; // ebx
  struct IAccessible *v26; // r14
  struct IRawElementProviderFragment **v27; // rbx
  LONG v28; // r13d
  struct IEnumVARIANT *v29; // rbx
  HRESULT (__stdcall *Next)(IEnumVARIANT *, ULONG, VARIANT *, ULONG *); // r13
  struct IEnumVARIANT *v31; // rcx
  struct IEnumVARIANT *v32; // rax
  struct IEnumVARIANT *v33; // rcx
  struct IEnumVARIANT *v34; // rdx
  __int64 v35; // rcx
  int v36; // ebx
  LONG lVal; // r13d
  struct AccPair *v38; // rbx
  bool ShouldAcc2BeInTree; // bl
  bool v40; // zf
  signed int v41; // esi
  int v42; // eax
  struct IAccessible *v43; // r14
  int v44; // r12d
  struct AccPair *v45; // rbx
  int v46; // eax
  int v47; // edi
  struct IEnumVARIANT *v48; // rax
  int v49; // [rsp+28h] [rbp-B1h]
  int v50; // [rsp+28h] [rbp-B1h]
  struct IAccessible *v51; // [rsp+38h] [rbp-A1h] BYREF
  int v52; // [rsp+40h] [rbp-99h]
  __int64 v53; // [rsp+48h] [rbp-91h]
  struct IEnumVARIANT *v54; // [rsp+50h] [rbp-89h] BYREF
  const wchar_t *v55; // [rsp+58h] [rbp-81h] BYREF
  struct IAccessible *v56; // [rsp+60h] [rbp-79h]
  HWND v57; // [rsp+68h] [rbp-71h]
  int v58; // [rsp+70h] [rbp-69h]
  int v59; // [rsp+74h] [rbp-65h]
  char v60; // [rsp+78h] [rbp-61h]
  struct IEnumVARIANT *v61; // [rsp+80h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-51h] BYREF
  struct tagVARIANT v63; // [rsp+A8h] [rbp-31h] BYREF
  struct IEnumVARIANT *v64; // [rsp+C8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+47h]
  struct IEnumVARIANT *v67; // [rsp+130h] [rbp+57h] BYREF
  int v68; // [rsp+138h] [rbp+5Fh]
  HWND v69; // [rsp+140h] [rbp+67h]

  v69 = a4;
  v68 = a3;
  v9 = a3;
  v10 = a1;
  v11 = a6;
  *a6 = 0;
  *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a2->lVal )
    return 0;
  LODWORD(a6) = 0;
  v55 = L"IAccessible::get_accChild";
  v56 = a1;
  v57 = a4;
  v59 = 600;
  v60 = 1;
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    McTemplateU0zd_EventWriteTransfer(
      L"IAccessible::get_accChild",
      MsaaProviderCallout_Start,
      L"IAccessible::get_accChild",
      a4);
  v12 = ((__int64 (__fastcall *)(struct IAccessible *, struct IEnumVARIANT ***))v10->lpVtbl->get_accChildCount)(
          v10,
          &a6);
  v13 = v12;
  v58 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accutils.cpp",
      (const char *)(unsigned int)v12,
      v49);
    MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v55);
  }
  else
  {
    MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v55);
    v13 = 0;
  }
  if ( v13 < 0 || !(_DWORD)a6 )
    return 0;
  v15 = 0;
  v64 = 0;
  v16 = (struct IEnumVARIANT *)QI<IEnumVARIANT>(v10);
  v18 = v16;
  v54 = v16;
  if ( v16 )
  {
    v67 = 0;
    v46 = ProviderCallouts::IEnumVARIANT_Clone(v16, &v67);
    v47 = v46;
    if ( v46 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accutils.cpp",
        (const char *)(unsigned int)v46,
        v49);
    else
      v47 = 0;
    if ( v47 >= 0 && v67 )
    {
      ((void (__fastcall *)(struct IEnumVARIANT *))v18->lpVtbl->Release)(v18);
      v18 = v67;
    }
    AccUtils::Reset(v18, a4);
    v15 = v18;
    v64 = v18;
    v18 = 0;
  }
  if ( v18 )
    ((void (__fastcall *)(struct IEnumVARIANT *))v18->lpVtbl->Release)(v18);
  if ( !v15 )
  {
    v19 = 0;
    v20 = HIDWORD(v69);
    while ( 1 )
    {
      LODWORD(v53) = v19;
      if ( v19 >= (int)a6 )
        goto LABEL_53;
      if ( v68 )
        v21 = v19 + 1;
      else
        v21 = (_DWORD)a6 - v19;
      v51 = 0;
      v52 = 0;
      if ( !v21 )
        goto LABEL_73;
      LODWORD(v67) = 0;
      v55 = L"IAccessible::get_accChild";
      v56 = v10;
      v57 = (HWND)__PAIR64__(v20, (unsigned int)a4);
      v59 = 600;
      v60 = 1;
      if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v17,
          MsaaProviderCallout_Start,
          L"IAccessible::get_accChild",
          (unsigned int)a4);
      v22 = ((__int64 (__fastcall *)(struct IAccessible *, struct IEnumVARIANT **))v10->lpVtbl->get_accChildCount)(
              v10,
              &v67);
      v23 = v22;
      v58 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accutils.cpp",
          (const char *)(unsigned int)v22,
          v49);
        MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v55);
      }
      else
      {
        MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v55);
        v23 = 0;
      }
      if ( v23 < 0 || v21 > (int)v67 )
        goto LABEL_73;
      *(_OWORD *)&pvarg.vt = 0;
      pvarg.vt = 3;
      pvarg.lVal = v21;
      *(_OWORD *)&v63.vt = *(_OWORD *)&pvarg.vt;
      v63.pRecInfo = 0;
      v24 = AccNavUtils::AccPairFromVariant(
              v10,
              &v63,
              a4,
              (struct IUnknown *)v10,
              L"IAccessible::get_accChild",
              (struct AccPair *)&v51);
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11A,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accnavutils.cpp",
          (const char *)(unsigned int)v24,
          v49);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x92,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accnavutils.cpp",
          (const char *)v25,
          v50);
        goto LABEL_85;
      }
      v26 = v51;
      if ( !v51 )
        goto LABEL_73;
      v27 = a8;
      if ( a8 )
      {
        v48 = (struct IEnumVARIANT *)QI<IRawElementProviderFragment>(v51);
        v67 = v48;
        if ( v48 )
        {
          *v27 = (struct IRawElementProviderFragment *)v48;
          v67 = 0;
          AccPair::Set(a5, v26, v52);
          *a7 = v21;
          wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v67);
          goto LABEL_73;
        }
        wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v67);
      }
      v28 = v52;
      if ( !v52 )
      {
        v67 = 0;
        v54 = 0;
        ((void (__fastcall *)(struct IAccessible *, GUID *, struct IEnumVARIANT **))v26->lpVtbl->QueryInterface)(
          v26,
          &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
          &v54);
        v29 = v54;
        if ( v54 )
        {
          Next = v54->lpVtbl->Next;
          v31 = v67;
          v67 = 0;
          if ( v31 )
            ((void (__fastcall *)(struct IEnumVARIANT *))v31->lpVtbl->Release)(v31);
          ((void (__fastcall *)(struct IEnumVARIANT *, GUID *, GUID *, struct IEnumVARIANT **))Next)(
            v29,
            &GUID_e89f726e_c4f4_4c19_bb19_b647d7fa8478,
            &GUID_e89f726e_c4f4_4c19_bb19_b647d7fa8478,
            &v67);
          v29 = v54;
          v28 = v52;
        }
        if ( !v67 )
        {
          v61 = 0;
          ((void (__fastcall *)(struct IAccessible *, GUID *, struct IEnumVARIANT **))v26->lpVtbl->QueryInterface)(
            v26,
            &GUID_e89f726e_c4f4_4c19_bb19_b647d7fa8478,
            &v61);
          v32 = v61;
          v33 = 0;
          v61 = 0;
          v34 = v67;
          v67 = v32;
          if ( v34 )
          {
            ((void (__fastcall *)(struct IEnumVARIANT *))v34->lpVtbl->Release)(v34);
            v33 = v61;
          }
          if ( v33 )
            ((void (__fastcall *)(struct IEnumVARIANT *))v33->lpVtbl->Release)(v33);
          v29 = v54;
        }
        if ( v29 )
          ((void (__fastcall *)(struct IEnumVARIANT *))v29->lpVtbl->Release)(v29);
        if ( v67 )
        {
          ShouldAcc2BeInTree = AccNavUtils::ShouldAcc2BeInTree((struct IAccessible2 *)v67, a4);
          v17 = v67;
          if ( v67 )
            ((void (__fastcall *)(struct IEnumVARIANT *))v67->lpVtbl->Release)(v67);
          v40 = !ShouldAcc2BeInTree;
          goto LABEL_59;
        }
        wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v67);
      }
      *(_OWORD *)&v63.vt = 0;
      v63.vt = 3;
      v63.lVal = v28;
      VariantInit(&pvarg);
      v55 = L"IAccessible::get_accState";
      v56 = v26;
      v57 = (HWND)__PAIR64__(v20, (unsigned int)a4);
      v59 = 600;
      v60 = 1;
      if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
        McTemplateU0zd_EventWriteTransfer(
          v35,
          MsaaProviderCallout_Start,
          L"IAccessible::get_accState",
          (unsigned int)a4);
      v63.pRecInfo = 0;
      v36 = ((__int64 (__fastcall *)(struct IAccessible *, struct tagVARIANT *, VARIANTARG *))v26->lpVtbl->get_accState)(
              v26,
              &v63,
              &pvarg);
      v58 = v36;
      if ( v36 < 0 )
        goto LABEL_81;
      if ( pvarg.vt != 3 )
        break;
      lVal = pvarg.lVal;
      MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v55);
      VariantClear(&pvarg);
      v36 = 0;
LABEL_49:
      if ( v36 < 0 )
        goto LABEL_60;
      if ( (lVal & 0x8000) == 0 )
        goto LABEL_51;
      v40 = (lVal & 0x10000) == 0;
LABEL_59:
      if ( !v40 )
      {
LABEL_51:
        v38 = a5;
        *(_QWORD *)a5 = v26;
        ((void (__fastcall *)(struct IAccessible *))v26->lpVtbl->AddRef)(v26);
        *((_DWORD *)v38 + 2) = v52;
        *a7 = v21;
        if ( v26 )
          ((void (__fastcall *)(struct IAccessible *))v26->lpVtbl->Release)(v26);
        goto LABEL_53;
      }
LABEL_60:
      if ( v26 )
        ((void (__fastcall *)(struct IAccessible *))v26->lpVtbl->Release)(v26);
      v19 = v53 + 1;
      v10 = a1;
    }
    v58 = -2147467259;
    v59 = 601;
    v36 = -2147467259;
LABEL_81:
    lVal = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accutils.cpp",
      (const char *)(unsigned int)v36,
      v49);
    MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v55);
    VariantClear(&pvarg);
    goto LABEL_49;
  }
  v41 = (int)a6;
  while ( 1 )
  {
    if ( --v41 < 0 )
      goto LABEL_53;
    v51 = 0;
    v52 = 0;
    if ( !v9 && ((int)AccUtils::Reset(v15, a4) < 0 || v41 > 0 && (int)AccUtils::Skip(v15, a4, v41) < 0) )
    {
      v25 = 0;
LABEL_85:
      wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v51);
      wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v64);
      return v25;
    }
    v42 = AccNavUtils::AccPairFromEnumVarNext(v15, v10, a4, (struct AccPair *)&v51);
    v25 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accnavutils.cpp",
        (const char *)(unsigned int)v42,
        v49);
      goto LABEL_85;
    }
    v43 = v51;
    if ( !v51 )
      goto LABEL_73;
    v44 = v52;
    if ( (unsigned int)AccNavUtils::ShouldBeInTree(v51, v52, a4) )
      break;
    wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v51);
    v10 = a1;
    v9 = v68;
  }
  v45 = a5;
  *(_QWORD *)a5 = v43;
  ((void (__fastcall *)(struct IAccessible *))v43->lpVtbl->AddRef)(v43);
  *((_DWORD *)v45 + 2) = v44;
  *v11 = v15;
  v15 = 0;
LABEL_73:
  wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v51);
LABEL_53:
  if ( v15 )
    ((void (__fastcall *)(struct IEnumVARIANT *))v15->lpVtbl->Release)(v15);
  return 0;
}

```

## disassembly

```asm
0x1800ba2f4  mov     rax, rsp
0x1800ba2f7  mov     [rax+20h], r9
0x1800ba2fb  mov     [rax+18h], r8d
0x1800ba2ff  mov     [rax+8], rcx
0x1800ba303  push    rbp
0x1800ba304  push    rbx
0x1800ba305  push    rsi
0x1800ba306  push    rdi
0x1800ba307  push    r12
0x1800ba309  push    r13
0x1800ba30b  push    r14
0x1800ba30d  push    r15
0x1800ba30f  lea     rbp, [rax-47h]
0x1800ba313  sub     rsp, 0D8h
0x1800ba31a  mov     r15, r9
0x1800ba31d  mov     r12d, r8d
0x1800ba320  mov     r14, rcx
0x1800ba323  xor     esi, esi
0x1800ba325  mov     r13, [rbp+3Fh+arg_28]
0x1800ba329  mov     [r13+0], rsi
0x1800ba32d  mov     rax, [rbp+3Fh+arg_30]
0x1800ba331  mov     [rax], esi
0x1800ba333  mov     rax, [rbp+3Fh+arg_38]
0x1800ba33a  test    rax, rax
0x1800ba33d  jnz     loc_1800BA9D5
0x1800ba343  cmp     [rdx+8], esi
0x1800ba346  jnz     short loc_1800BA3B6
0x1800ba348  mov     dword ptr [rbp+3Fh+arg_28], esi
0x1800ba34b  lea     rcx, aIaccessibleGet_12; "IAccessible::get_accChild"
0x1800ba352  mov     [rsp+110h+var_C0], rcx
0x1800ba357  mov     [rbp+3Fh+var_B8], r14
0x1800ba35b  mov     dword ptr [rbp+3Fh+var_B0], r15d
0x1800ba35f  mov     rax, r15
0x1800ba362  sar     rax, 20h
0x1800ba366  mov     dword ptr [rbp+3Fh+var_B0+4], eax
0x1800ba369  mov     [rbp+3Fh+var_A4], 258h
0x1800ba370  mov     [rbp+3Fh+var_A0], 1
0x1800ba374  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800ba37b  jnz     loc_1800BA993
0x1800ba381  mov     rax, [r14]
0x1800ba384  lea     rdx, [rbp+3Fh+arg_28]
0x1800ba388  mov     rcx, r14
0x1800ba38b  mov     rax, [rax+40h]
0x1800ba38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba394  mov     ebx, eax
0x1800ba396  mov     [rbp+3Fh+var_A8], eax
0x1800ba399  test    eax, eax
0x1800ba39b  js      loc_1800BA7A6
0x1800ba3a1  lea     rcx, [rsp+110h+var_C0]; this
0x1800ba3a6  call    ??1MsaaProviderCallTrace@@QEAA@XZ; MsaaProviderCallTrace::~MsaaProviderCallTrace(void)
0x1800ba3ab  mov     ebx, esi
0x1800ba3ad  test    ebx, ebx
0x1800ba3af  js      short loc_1800BA3B6
0x1800ba3b1  cmp     dword ptr [rbp+3Fh+arg_28], esi
0x1800ba3b4  jnz     short loc_1800BA3CC
0x1800ba3b6  xor     eax, eax
0x1800ba3b8  add     rsp, 0D8h
0x1800ba3bf  pop     r15
0x1800ba3c1  pop     r14
0x1800ba3c3  pop     r13
0x1800ba3c5  pop     r12
0x1800ba3c7  pop     rdi
0x1800ba3c8  pop     rsi
0x1800ba3c9  pop     rbx
0x1800ba3ca  pop     rbp
0x1800ba3cb  retn
0x1800ba3cc  mov     rdi, rsi
0x1800ba3cf  mov     [rbp+3Fh+var_50], rsi
0x1800ba3d3  mov     rcx, r14
0x1800ba3d6  call    ??$QI@UIEnumVARIANT@@@@YAPEAUIEnumVARIANT@@PEAUIUnknown@@@Z; QI<IEnumVARIANT>(IUnknown *)
0x1800ba3db  mov     rbx, rax
0x1800ba3de  mov     [rsp+110h+var_C8], rax
0x1800ba3e3  test    rax, rax
0x1800ba3e6  jnz     loc_1800BA88C
0x1800ba3ec  test    rbx, rbx
0x1800ba3ef  jz      short loc_1800BA401
0x1800ba3f1  mov     rax, [rbx]
0x1800ba3f4  mov     rcx, rbx
0x1800ba3f7  mov     rax, [rax+10h]
0x1800ba3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba400  nop
0x1800ba401  test    rdi, rdi
0x1800ba404  jnz     loc_1800BA7F4
0x1800ba40a  mov     eax, esi
0x1800ba40c  mov     esi, [rbp+3Fh+arg_1C]
0x1800ba40f  mov     dword ptr [rsp+110h+var_D0], eax
0x1800ba413  mov     r12d, dword ptr [rbp+3Fh+arg_28]
0x1800ba417  cmp     eax, r12d
0x1800ba41a  jge     loc_1800BA73C
0x1800ba420  cmp     [rbp+3Fh+arg_10], 0
0x1800ba424  jz      loc_1800BA79E
0x1800ba42a  lea     r12d, [rax+1]
0x1800ba42e  mov     [rsp+110h+var_E0], 0
0x1800ba437  mov     [rsp+110h+var_D8], 0
0x1800ba43f  test    r12d, r12d
0x1800ba442  jz      loc_1800BAA95
0x1800ba448  mov     dword ptr [rbp+3Fh+arg_8], 0
0x1800ba44f  lea     r13, aIaccessibleGet_12; "IAccessible::get_accChild"
0x1800ba456  mov     [rsp+110h+var_C0], r13
0x1800ba45b  mov     [rbp+3Fh+var_B8], r14
0x1800ba45f  mov     dword ptr [rbp+3Fh+var_B0], r15d
0x1800ba463  mov     dword ptr [rbp+3Fh+var_B0+4], esi
0x1800ba466  mov     [rbp+3Fh+var_A4], 258h
0x1800ba46d  mov     [rbp+3Fh+var_A0], 1
0x1800ba471  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800ba478  jnz     loc_1800BA9A7
0x1800ba47e  mov     rax, [r14]
0x1800ba481  lea     rdx, [rbp+3Fh+arg_8]
0x1800ba485  mov     rcx, r14
0x1800ba488  mov     rax, [rax+40h]
0x1800ba48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba491  mov     ebx, eax
0x1800ba493  mov     [rbp+3Fh+var_A8], eax
0x1800ba496  test    eax, eax
0x1800ba498  js      loc_1800BA7CD
0x1800ba49e  lea     rcx, [rsp+110h+var_C0]; this
0x1800ba4a3  call    ??1MsaaProviderCallTrace@@QEAA@XZ; MsaaProviderCallTrace::~MsaaProviderCallTrace(void)
0x1800ba4a8  xor     ebx, ebx
0x1800ba4aa  test    ebx, ebx
0x1800ba4ac  js      loc_1800BAA95
0x1800ba4b2  cmp     r12d, dword ptr [rbp+3Fh+arg_8]
0x1800ba4b6  jg      loc_1800BAA95
0x1800ba4bc  xorps   xmm0, xmm0
0x1800ba4bf  xor     eax, eax
0x1800ba4c1  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x1800ba4c5  lea     ecx, [rax+3]
0x1800ba4c8  mov     word ptr [rbp+3Fh+pvarg], cx
0x1800ba4cc  mov     dword ptr [rbp+3Fh+pvarg+8], r12d
0x1800ba4d0  movups  xmm0, xmmword ptr [rbp+3Fh+pvarg]
0x1800ba4d4  movaps  xmmword ptr [rbp+3Fh+var_70], xmm0
0x1800ba4d8  mov     qword ptr [rbp+3Fh+var_70+10h], rax
0x1800ba4dc  lea     rax, [rsp+110h+var_E0]
0x1800ba4e1  mov     [rsp+110h+var_E8], rax; struct AccPair *
0x1800ba4e6  mov     [rsp+110h+var_F0], r13; int
0x1800ba4eb  mov     r9, r14; struct IUnknown *
0x1800ba4ee  mov     r8, r15; HWND
0x1800ba4f1  lea     rdx, [rbp+3Fh+var_70]; struct tagVARIANT
0x1800ba4f5  mov     rcx, r14; struct IAccessible *
0x1800ba4f8  call    ?AccPairFromVariant@AccNavUtils@@SAJPEAUIAccessible@@UtagVARIANT@@PEAUHWND__@@PEAUIUnknown@@PEAGPEAUAccPair@@@Z; AccNavUtils::AccPairFromVariant(IAccessible *,tagVARIANT,HWND__ *,IUnknown *,ushort *,AccPair *)
0x1800ba4fd  mov     ebx, eax
0x1800ba4ff  test    eax, eax
0x1800ba501  js      loc_1800BA947
0x1800ba507  mov     r14, [rsp+110h+var_E0]
0x1800ba50c  test    r14, r14
0x1800ba50f  jz      loc_1800BAA95
0x1800ba515  mov     rbx, [rbp+3Fh+arg_38]
0x1800ba51c  test    rbx, rbx
0x1800ba51f  jnz     loc_1800BAA49
0x1800ba525  mov     r13d, [rsp+110h+var_D8]
0x1800ba52a  test    r13d, r13d
0x1800ba52d  jnz     loc_1800BA64A
0x1800ba533  mov     [rbp+3Fh+arg_8], 0
0x1800ba53b  mov     [rsp+110h+var_C8], 0
0x1800ba544  mov     rax, [r14]
0x1800ba547  lea     r8, [rsp+110h+var_C8]
0x1800ba54c  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x1800ba553  mov     rcx, r14
0x1800ba556  mov     rax, [rax]
0x1800ba559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba55e  nop
0x1800ba55f  mov     rbx, [rsp+110h+var_C8]
0x1800ba564  test    rbx, rbx
0x1800ba567  jz      short loc_1800BA5B5
0x1800ba569  mov     rax, [rbx]
0x1800ba56c  mov     r13, [rax+18h]
0x1800ba570  mov     rcx, [rbp+3Fh+arg_8]
0x1800ba574  mov     [rbp+3Fh+arg_8], 0
0x1800ba57c  test    rcx, rcx
0x1800ba57f  jz      short loc_1800BA58E
0x1800ba581  mov     rdx, [rcx]
0x1800ba584  mov     rax, [rdx+10h]
0x1800ba588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba58d  nop
0x1800ba58e  lea     r9, [rbp+3Fh+arg_8]
0x1800ba592  lea     r8, _GUID_e89f726e_c4f4_4c19_bb19_b647d7fa8478
0x1800ba599  lea     rdx, _GUID_e89f726e_c4f4_4c19_bb19_b647d7fa8478
0x1800ba5a0  mov     rcx, rbx
0x1800ba5a3  mov     rax, r13
0x1800ba5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba5ab  mov     rbx, [rsp+110h+var_C8]
0x1800ba5b0  mov     r13d, [rsp+110h+var_D8]
0x1800ba5b5  cmp     [rbp+3Fh+arg_8], 0
0x1800ba5ba  jnz     short loc_1800BA61F
0x1800ba5bc  mov     [rbp+3Fh+var_98], 0
0x1800ba5c4  mov     rax, [r14]
0x1800ba5c7  lea     r8, [rbp+3Fh+var_98]
0x1800ba5cb  lea     rdx, _GUID_e89f726e_c4f4_4c19_bb19_b647d7fa8478
0x1800ba5d2  mov     rcx, r14
0x1800ba5d5  mov     rax, [rax]
0x1800ba5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba5dd  nop
0x1800ba5de  mov     rax, [rbp+3Fh+var_98]
0x1800ba5e2  xor     ecx, ecx
0x1800ba5e4  mov     [rbp+3Fh+var_98], rcx
0x1800ba5e8  mov     rdx, [rbp+3Fh+arg_8]
0x1800ba5ec  mov     [rbp+3Fh+arg_8], rax
0x1800ba5f0  test    rdx, rdx
0x1800ba5f3  jz      short loc_1800BA608
0x1800ba5f5  mov     rax, [rdx]
0x1800ba5f8  mov     rcx, rdx
0x1800ba5fb  mov     rax, [rax+10h]
0x1800ba5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba604  mov     rcx, [rbp+3Fh+var_98]
0x1800ba608  test    rcx, rcx
0x1800ba60b  jz      short loc_1800BA61A
0x1800ba60d  mov     rax, [rcx]
0x1800ba610  mov     rax, [rax+10h]
0x1800ba614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba619  nop
0x1800ba61a  mov     rbx, [rsp+110h+var_C8]
0x1800ba61f  test    rbx, rbx
0x1800ba622  jz      short loc_1800BA634
0x1800ba624  mov     rax, [rbx]
0x1800ba627  mov     rcx, rbx
0x1800ba62a  mov     rax, [rax+10h]
0x1800ba62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba633  nop
0x1800ba634  mov     rcx, [rbp+3Fh+arg_8]; struct IAccessible2 *
0x1800ba638  test    rcx, rcx
0x1800ba63b  jnz     loc_1800BA756
0x1800ba641  lea     rcx, [rbp+3Fh+arg_8]; void *
0x1800ba645  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x1800ba64a  xorps   xmm0, xmm0
0x1800ba64d  xor     ebx, ebx
0x1800ba64f  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x1800ba653  lea     eax, [rbx+3]
0x1800ba656  mov     word ptr [rbp+3Fh+var_70], ax
0x1800ba65a  mov     dword ptr [rbp+3Fh+var_70+8], r13d
0x1800ba65e  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x1800ba662  call    cs:__imp_VariantInit
0x1800ba668  lea     rax, aIaccessibleGet_7; "IAccessible::get_accState"
0x1800ba66f  mov     [rsp+110h+var_C0], rax
0x1800ba674  mov     [rbp+3Fh+var_B8], r14
0x1800ba678  mov     dword ptr [rbp+3Fh+var_B0], r15d
0x1800ba67c  mov     dword ptr [rbp+3Fh+var_B0+4], esi
0x1800ba67f  mov     [rbp+3Fh+var_A4], 258h
0x1800ba686  mov     [rbp+3Fh+var_A0], 1
0x1800ba68a  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800ba691  jnz     loc_1800BA9BE
0x1800ba697  movups  xmm0, xmmword ptr [rbp+3Fh+var_70]
0x1800ba69b  movaps  xmmword ptr [rbp+3Fh+var_70], xmm0
0x1800ba69f  mov     qword ptr [rbp+3Fh+var_70+10h], rbx
0x1800ba6a3  mov     rax, [r14]
0x1800ba6a6  lea     r8, [rbp+3Fh+pvarg]
0x1800ba6aa  lea     rdx, [rbp+3Fh+var_70]
0x1800ba6ae  mov     rcx, r14
0x1800ba6b1  mov     rax, [rax+70h]
0x1800ba6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba6ba  mov     ebx, eax
0x1800ba6bc  mov     [rbp+3Fh+var_A8], eax
0x1800ba6bf  test    eax, eax
0x1800ba6c1  js      loc_1800BA8F0
0x1800ba6c7  mov     eax, 3
0x1800ba6cc  cmp     word ptr [rbp+3Fh+pvarg], ax
0x1800ba6d0  jnz     loc_1800BA8DF
0x1800ba6d6  mov     r13d, dword ptr [rbp+3Fh+pvarg+8]
0x1800ba6da  lea     rcx, [rsp+110h+var_C0]; this
0x1800ba6df  call    ??1MsaaProviderCallTrace@@QEAA@XZ; MsaaProviderCallTrace::~MsaaProviderCallTrace(void)
0x1800ba6e4  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x1800ba6e8  call    cs:__imp_VariantClear
0x1800ba6ee  xor     ebx, ebx
0x1800ba6f0  test    ebx, ebx
0x1800ba6f2  js      loc_1800BA77A
0x1800ba6f8  bt      r13d, 0Fh
0x1800ba6fd  jb      loc_1800BA924
0x1800ba703  mov     rbx, [rbp+3Fh+arg_20]
0x1800ba707  mov     [rbx], r14
0x1800ba70a  mov     rax, [r14]
0x1800ba70d  mov     rcx, r14
0x1800ba710  mov     rax, [rax+8]
0x1800ba714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba719  mov     eax, [rsp+110h+var_D8]
0x1800ba71d  mov     [rbx+8], eax
0x1800ba720  mov     rax, [rbp+3Fh+arg_30]
0x1800ba724  mov     [rax], r12d
0x1800ba727  test    r14, r14
0x1800ba72a  jz      short loc_1800BA73C
0x1800ba72c  mov     rax, [r14]
0x1800ba72f  mov     rcx, r14
0x1800ba732  mov     rax, [rax+10h]
0x1800ba736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba73b  nop
0x1800ba73c  test    rdi, rdi
0x1800ba73f  jz      short loc_1800BA751
0x1800ba741  mov     rax, [rdi]
0x1800ba744  mov     rcx, rdi
0x1800ba747  mov     rax, [rax+10h]
0x1800ba74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba750  nop
0x1800ba751  jmp     loc_1800BA3B6
0x1800ba756  mov     rdx, r15; HWND
0x1800ba759  call    ?ShouldAcc2BeInTree@AccNavUtils@@SA_NPEAUIAccessible2@@PEAUHWND__@@@Z; AccNavUtils::ShouldAcc2BeInTree(IAccessible2 *,HWND__ *)
0x1800ba75e  mov     bl, al
0x1800ba760  mov     rcx, [rbp+3Fh+arg_8]
0x1800ba764  test    rcx, rcx
0x1800ba767  jz      short loc_1800BA776
0x1800ba769  mov     rdx, [rcx]
0x1800ba76c  mov     rax, [rdx+10h]
0x1800ba770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba775  nop
  ... truncated ...
```
