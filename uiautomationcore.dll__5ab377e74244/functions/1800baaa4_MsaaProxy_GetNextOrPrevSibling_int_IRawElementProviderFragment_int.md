# MsaaProxy::GetNextOrPrevSibling(int,IRawElementProviderFragment * *,int *)

- ea: `0x1800baaa4`
- end: `0x1800bb9eb`
- name: `?GetNextOrPrevSibling@MsaaProxy@@AEAAJHPEAPEAUIRawElementProviderFragment@@PEAH@Z`
- size: `3911`
- prototype: `__int64 __fastcall(MsaaProxy *__hidden this, int, struct IRawElementProviderFragment **, int *)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18011d950`

## callees

- `0x18000f680`
- `0x18001ed40`
- `0x180020230`
- `0x18002f580`
- `0x180036198`
- `0x180085540`
- `0x18008a8ec`
- `0x1800b8d60`
- `0x1800b9108`
- `0x1800b9c70`
- `0x1800b9cf4`
- `0x1800b9da0`
- `0x1800b9e64`
- `0x1800ba0e0`
- `0x1800ba120`
- `0x1800baaa4`
- `0x1800bb9f4`
- `0x1800d9490`
- `0x18010517c`
- `0x1801098d8`
- `0x18010d390`
- `0x180120584`
- `0x180121134`
- `0x18012556c`
- `0x180133084`
- `0x18017c850`
- `0x1801a1438`
- `0x1801a9d58`
- `0x1802c2e44`
- `0x1802dd010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800bb0b4`
- `OLEAUT32!__imp_VariantInit` at `0x1800bb0b4`
- `OLEAUT32!__imp_VariantClear` at `0x1800bb140`
- `OLEAUT32!__imp_VariantClear` at `0x1800bb4d2`
- `OLEAUT32!__imp_VariantClear` at `0x1800bb50e`
- `OLEAUT32!__imp_VariantClear` at `0x1800bb140`
- `OLEAUT32!__imp_VariantClear` at `0x1800bb4d2`
- `OLEAUT32!__imp_VariantClear` at `0x1800bb50e`

## string_xrefs

- `0x1800bb3af`: `onecore\windows\accessibletech\uiautomationcore\accnavutils.cpp`
- `0x1800bb4f9`: `onecore\windows\accessibletech\uiautomationcore\accnavutils.cpp`
- `0x1800baeb3`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1800bb200`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1800bb3c7`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1800bb51b`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1800bb619`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1800bb72b`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1800bb7a3`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1800bb907`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1800bb6a4`: `onecore\windows\accessibletech\uiautomationcore\proxies\MsaaProxy.h`
- `0x1800bb285`: `onecore\windows\accessibletech\uiautomationcore\accutils.cpp`
- `0x1800bb578`: `onecore\windows\accessibletech\uiautomationcore\accutils.cpp`
- `0x1800bb869`: `onecore\windows\accessibletech\uiautomationcore\accutils.cpp`
- `0x1800bb840`: `IAccessible::get_accChildCount`
- `0x1800baba5`: `IAccessible::get_accChild`
- `0x1800bafe8`: `IAccessible::get_accChild`
- `0x1800bb341`: `IAccessible::get_accChild`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall MsaaProxy::GetNextOrPrevSibling(
        MsaaProxy *this,
        int a2,
        struct IRawElementProviderFragment **a3,
        int *a4)
{
  int v5; // r12d
  struct IUnknown *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, struct IUnknown **); // rcx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // r14d
  int v16; // r13d
  unsigned int v17; // r12d
  __int64 v18; // rcx
  struct IUnknown *v19; // r14
  struct IUnknown *v20; // r15
  int v21; // eax
  int v22; // r13d
  __int128 v23; // xmm6
  int v24; // eax
  struct IUnknown *punkVal; // r13
  VARTYPE vt; // ax
  struct IAccessible *v27; // rax
  struct IUnknown *v28; // rbx
  unsigned int Lo; // r13d
  unsigned int BehaviorVersion; // eax
  struct ProviderEntryPoint *v31; // r14
  int v32; // eax
  unsigned int v33; // edi
  struct IEnumVARIANTVtbl *lpVtbl; // rax
  struct IEnumVARIANT *v35; // rcx
  int v37; // eax
  struct IEnumVARIANT *v38; // rbx
  char v39; // bl
  IRecordInfo *v40; // r9
  struct IUnknown *v41; // r14
  int v42; // eax
  int v43; // r15d
  int v44; // eax
  int v45; // r12d
  struct IAccessible *v46; // r14
  HWND v47; // rbx
  int v48; // eax
  unsigned int v49; // ebx
  struct ProviderEntryPoint *v50; // r14
  int v51; // eax
  __int64 v52; // rcx
  struct ProviderEntryPoint *v53; // rbx
  struct IEnumVARIANT *v54; // rdx
  __int64 v55; // rdx
  int NewIEnumVARIANT; // eax
  unsigned int ConnectionTimeout; // eax
  unsigned int TransactionTimeout; // eax
  int PositionInEnum; // eax
  __int64 v60; // rdx
  struct AccPair *v61; // r10
  int v62; // [rsp+28h] [rbp-E0h]
  int v63; // [rsp+28h] [rbp-E0h]
  int v64; // [rsp+28h] [rbp-E0h]
  int v65; // [rsp+28h] [rbp-E0h]
  int v66; // [rsp+28h] [rbp-E0h]
  int v67; // [rsp+28h] [rbp-E0h]
  int v68; // [rsp+28h] [rbp-E0h]
  struct IUnknown *v69; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v70[2]; // [rsp+60h] [rbp-A8h] BYREF
  struct IUnknown *v71; // [rsp+68h] [rbp-A0h] BYREF
  struct IUnknown *v72; // [rsp+70h] [rbp-98h] BYREF
  void *v73; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v74; // [rsp+80h] [rbp-88h]
  struct IEnumVARIANT *v75[2]; // [rsp+88h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-70h] BYREF
  struct tagVARIANT v77; // [rsp+B8h] [rbp-50h] BYREF
  int v78; // [rsp+D0h] [rbp-38h]
  int v79; // [rsp+D4h] [rbp-34h]
  char v80; // [rsp+D8h] [rbp-30h]
  struct IAccessible *v81[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v82; // [rsp+F8h] [rbp-10h]
  struct IAccessible *v83; // [rsp+108h] [rbp+0h]
  HWND v84; // [rsp+110h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+180h] [rbp+78h]
  int v86; // [rsp+188h] [rbp+80h] BYREF
  int v87; // [rsp+190h] [rbp+88h]
  struct ProviderEntryPoint *v88; // [rsp+198h] [rbp+90h] BYREF
  int *v89; // [rsp+1A0h] [rbp+98h]

  v89 = a4;
  v88 = (struct ProviderEntryPoint *)a3;
  v87 = a2;
  v5 = a2;
  *a3 = 0;
  v7 = 0;
  v75[0] = 0;
  if ( !*((_DWORD *)this + 123) )
  {
    MsaaProxy::DetermineEnumMode(this, v75);
    if ( !*((_DWORD *)this + 123) )
    {
      v35 = v75[0];
      if ( !v75[0] )
        return 0;
      lpVtbl = v75[0]->lpVtbl;
      goto LABEL_44;
    }
    v7 = (struct IUnknown *)v75[0];
  }
  v69 = 0;
  if ( *((_DWORD *)this + 132) )
    goto LABEL_145;
  v69 = 0;
  v8 = *((_QWORD *)this + 67);
  if ( !v8 )
  {
    v9 = *((unsigned int *)this + 138);
    if ( !(_DWORD)v9 && !*((_QWORD *)this + 68) )
      goto LABEL_47;
    v10 = *((_QWORD *)this + 68);
    if ( v10 )
    {
      v69 = 0;
      v11 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IUnknown **))(v10 + 32);
      if ( !v11 )
      {
        v13 = -2147467259;
LABEL_9:
        if ( (v13 & 0x80000000) == 0 )
          goto LABEL_10;
LABEL_146:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF2,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\MsaaProxy.h",
          (const char *)v13,
          v62);
        goto LABEL_48;
      }
      v12 = (**v11)(v11, &GUID_618736e0_3c3d_11cf_810c_00aa00389b71, &v69);
LABEL_8:
      v13 = v12;
      goto LABEL_9;
    }
    if ( (_DWORD)v9 )
    {
      v52 = *((_QWORD *)this + 31);
      if ( v52 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, struct IUnknown **))(*(_QWORD *)v52 + 40LL))(
                v52,
                v9,
                &GUID_618736e0_3c3d_11cf_810c_00aa00389b71,
                &v69);
        goto LABEL_8;
      }
    }
LABEL_145:
    v13 = -2147467259;
    goto LABEL_146;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v69 = (struct IUnknown *)*((_QWORD *)this + 67);
LABEL_10:
  if ( !v69 )
  {
LABEL_47:
    v13 = -2147467259;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12F3,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
      (const char *)v13,
      v62);
    if ( v69 )
      ((void (__fastcall *)(struct IUnknown *))v69->lpVtbl->Release)(v69);
    if ( v7 )
      ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
    return v13;
  }
  v14 = *((_DWORD *)this + 123);
  v15 = 1;
  if ( v14 != 1 )
  {
    if ( v14 != 2 )
      goto LABEL_40;
    v71 = 0;
    v37 = AgileInterface<IEnumVARIANT>::TryGet((char *)this + 496, *((_QWORD *)this + 31), &v71);
    v13 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1327,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
        (const char *)(unsigned int)v37,
        v62);
      if ( v71 )
        ((void (__fastcall *)(struct IUnknown *))v71->lpVtbl->Release)(v71);
      if ( v69 )
        ((void (__fastcall *)(struct IUnknown *))v69->lpVtbl->Release)(v69);
      if ( v7 )
        ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
      return v13;
    }
    if ( HwndUtils::IsTrident(*((HWND *)this + 29)) && (unsigned int)HwndUtils::IsEdgeHtml(*((HWND *)this + 29)) )
    {
      v38 = (struct IEnumVARIANT *)v71;
    }
    else
    {
      v38 = (struct IEnumVARIANT *)v71;
      if ( v5 )
      {
        if ( !v71 )
          goto LABEL_140;
        v15 = 0;
      }
    }
    if ( v38 )
    {
      v7 = (struct IUnknown *)v38;
      v75[0] = v38;
      v71 = 0;
      AgileInterface<IEnumVARIANT>::Clear((char *)this + 496, *((_QWORD *)this + 31));
      if ( v15 && (int)AccUtils::Reset(v38, *((HWND *)this + 29)) < 0 )
      {
        if ( v71 )
          ((void (__fastcall *)(struct IUnknown *))v71->lpVtbl->Release)(v71);
        if ( v69 )
          ((void (__fastcall *)(struct IUnknown *))v69->lpVtbl->Release)(v69);
        lpVtbl = v38->lpVtbl;
        v35 = v38;
LABEL_44:
        ((void (__fastcall *)(struct IEnumVARIANT *))lpVtbl->Release)(v35);
        return 0;
      }
LABEL_60:
      v72 = 0;
      v73 = 0;
      v74 = 0;
      v39 = 0;
      LOBYTE(v86) = 0;
      v70[0] = -1;
      if ( !v15 )
      {
LABEL_61:
        if ( !v5 )
          goto LABEL_85;
        v86 = 0;
        v40 = (IRecordInfo *)*((_QWORD *)this + 29);
        v41 = v69;
        *(_QWORD *)&v77.vt = L"IAccessible::get_accChild";
        v77.llVal = (LONGLONG)v69;
        v77.pRecInfo = v40;
        v79 = 600;
        v80 = 1;
        if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
          McTemplateU0zd_EventWriteTransfer(
            L"IAccessible::get_accChild",
            MsaaProviderCallout_Start,
            L"IAccessible::get_accChild",
            v40);
        v42 = ((__int64 (__fastcall *)(struct IUnknown *, int *))v41->lpVtbl[2].Release)(v41, &v86);
        v43 = v42;
        v78 = v42;
        if ( v42 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accutils.cpp",
            (const char *)(unsigned int)v42,
            v62);
          MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v77);
        }
        else
        {
          MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v77);
          v43 = 0;
        }
        if ( v43 < 0 || (v44 = v86) == 0 )
        {
          Error::IAccessibleError(v69, L"IAccessible::get_accChildCount", v43, *((HWND *)this + 29), 611);
          goto LABEL_85;
        }
        if ( v39 && v86 > 1 )
        {
          Error::IAccessibleError(v69, L"IEnumVARIANT::Next", -2147467259, *((HWND *)this + 29), 615);
          goto LABEL_85;
        }
        v45 = 0;
        if ( a4 )
          v45 = *a4;
        while ( 1 )
        {
          if ( v45 > v44 )
          {
            Error::IAccessibleError(v7, L"IEnumVARIANT::Next", v43, *((HWND *)this + 29), 612);
            goto LABEL_82;
          }
          if ( v44 == 1 )
            goto LABEL_82;
          v46 = 0;
          v81[0] = 0;
          LODWORD(v81[1]) = 0;
          v84 = (HWND)*((_QWORD *)this + 29);
          v47 = v84;
          v83 = (struct IAccessible *)v69;
          VariantInit(&pvarg);
          pvarg.llVal = 0;
          v70[0] = 0;
          v48 = AccUtils::Next((struct IEnumVARIANT *)v7, v47, 1u, &pvarg, v70);
          v13 = v48;
          if ( v48 < 0 )
          {
            v55 = 242;
            goto LABEL_132;
          }
          if ( v48 == 1 || !v70[0] )
          {
            VariantClear(&pvarg);
          }
          else
          {
            v77 = pvarg;
            v48 = AccNavUtils::AccPairFromVariant(v83, &v77, v84, v7, L"IEnumVARIANT::Next", (struct AccPair *)v81);
            v13 = v48;
            if ( v48 < 0 )
            {
              v55 = 249;
LABEL_132:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v55,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accnavutils.cpp",
                (const char *)(unsigned int)v48,
                v64);
              VariantClear(&pvarg);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1391,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
                (const char *)v13,
                v68);
              wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(v81);
LABEL_133:
              wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v73);
              wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v72);
LABEL_134:
              wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v71);
              wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v69);
              wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(v75);
              return v13;
            }
            VariantClear(&pvarg);
            v46 = v81[0];
          }
          if ( !v46 )
            goto LABEL_81;
          ++v45;
          v49 = (unsigned int)v81[1];
          if ( (unsigned int)AccNavUtils::ShouldBeInTree(v46, (int)v81[1], *((HWND *)this + 29)) )
          {
            v73 = v46;
            ((void (__fastcall *)(struct IAccessible *))v46->lpVtbl->AddRef)(v46);
            v74 = v49;
LABEL_81:
            wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(v81);
LABEL_82:
            if ( v89 )
              *v89 = v45;
            v5 = v87;
LABEL_85:
            v50 = v88;
            v65 = *((_DWORD *)this + 60);
            v51 = (*(__int64 (__fastcall **)(MsaaProxy *, void *, _QWORD, _QWORD))(*(_QWORD *)this + 8LL))(
                    this,
                    v73,
                    v74,
                    *((_QWORD *)this + 29));
            v13 = v51;
            if ( v51 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x13A5,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
                (const char *)(unsigned int)v51,
                v65);
              wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v73);
              if ( v72 )
                ((void (__fastcall *)(struct IUnknown *))v72->lpVtbl->Release)(v72);
              if ( v71 )
                ((void (__fastcall *)(struct IUnknown *))v71->lpVtbl->Release)(v71);
              if ( v69 )
                ((void (__fastcall *)(struct IUnknown *))v69->lpVtbl->Release)(v69);
              if ( v7 )
                ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
              return v13;
            }
            if ( *(_QWORD *)v50 )
            {
              if ( v5 )
                v54 = (struct IEnumVARIANT *)v7;
              else
                v54 = 0;
              MsaaProxy::SetNavMode_IEnumVARIANT((MsaaProxy *)(*(_QWORD *)v50 - 24LL), v54, (struct IAccessible *)v69);
            }
            wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v73);
            if ( v72 )
              ((void (__fastcall *)(struct IUnknown *))v72->lpVtbl->Release)(v72);
            if ( v71 )
              ((void (__fastcall *)(struct IUnknown *))v71->lpVtbl->Release)(v71);
LABEL_40:
            if ( v69 )
              ((void (__fastcall *)(struct IUnknown *))v69->lpVtbl->Release)(v69);
            if ( v7 )
            {
              lpVtbl = (struct IEnumVARIANTVtbl *)v7->lpVtbl;
              v35 = (struct IEnumVARIANT *)v7;
              goto LABEL_44;
            }
            return 0;
          }
          wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(v81);
          v44 = v86;
        }
      }
      PositionInEnum = AgileInterface<IAccessible>::Get((char *)this + 256, *((_QWORD *)this + 31), &v72);
      v13 = PositionInEnum;
      if ( PositionInEnum < 0 )
      {
        v60 = 4951;
LABEL_180:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v60,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
          (const char *)(unsigned int)PositionInEnum,
          v62);
        goto LABEL_133;
      }
      v61 = (struct AccPair *)&v73;
      if ( v5 )
        v61 = 0;
      PositionInEnum = AccNavUtils::GetPositionInEnum(
                         (struct IEnumVARIANT *)v7,
                         (struct IAccessible *)v69,
                         (struct IAccessible *)v72,
                         (const struct tagVARIANT *)((char *)this + 320),
                         *((HWND *)this + 29),
                         (int *)v70,
                         (bool *)((unsigned __int64)&v86 & -(__int64)(v5 != 0)),
                         v61);
      v13 = PositionInEnum;
      if ( PositionInEnum < 0 )
      {
        v60 = 4955;
        goto LABEL_180;
      }
      if ( v70[0] != -1 )
      {
        v39 = v86;
        goto LABEL_61;
      }
      wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v73);
      wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v72);
LABEL_176:
      v13 = 0;
      goto LABEL_134;
    }
LABEL_140:
    if ( !v7 )
    {
      NewIEnumVARIANT = AccNavUtils::GetNewIEnumVARIANT((struct IAccessible *)v69, *((HWND *)this + 29), v75);
      v13 = NewIEnumVARIANT;
      if ( NewIEnumVARIANT < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1332,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
          (const char *)(unsigned int)NewIEnumVARIANT,
          v62);
        goto LABEL_134;
      }
      v7 = (struct IUnknown *)v75[0];
      if ( !v75[0] )
        goto LABEL_176;
    }
    goto LABEL_60;
  }
  v16 = *((_DWORD *)this + 140);
  v17 = -2147467262;
  while ( 1 )
  {
    v73 = 0;
    v74 = 0;
    v18 = v87 != 0 ? 1 : -1;
    v86 = v18 + v16;
    if ( !((_DWORD)v18 + v16) )
      goto LABEL_53;
    v19 = (struct IUnknown *)*((_QWORD *)this + 29);
    v71 = v19;
    v20 = v69;
    v70[0] = 0;
    *(_QWORD *)&v77.vt = L"IAccessible::get_accChild";
    v77.llVal = (LONGLONG)v69;
    v77.pRecInfo = (IRecordInfo *)v19;
    v79 = 600;
    v80 = 1;
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0zd_EventWriteTransfer(v18, MsaaProviderCallout_Start, L"IAccessible::get_accChild", (unsigned int)v19);
    v21 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned int *))v20->lpVtbl[2].Release)(v20, v70);
    v22 = v21;
    v78 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accutils.cpp",
        (const char *)(unsigned int)v21,
        v62);
      MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v77);
    }
    else
    {
      MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v77);
      v22 = 0;
    }
    if ( v22 < 0 || v86 > (int)v70[0] )
    {
LABEL_53:
      wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v73);
      v31 = v88;
LABEL_38:
      if ( *(_QWORD *)v31 )
        MsaaProxy::SetNavMode_ChildIds((MsaaProxy *)(*(_QWORD *)v31 - 24LL), (struct IAccessible *)v69, v86);
      goto LABEL_40;
    }
    *(_OWORD *)&pvarg.vt = 0;
    pvarg.vt = 3;
    pvarg.lVal = v86;
    v23 = *(_OWORD *)&pvarg.vt;
    v72 = 0;
    *(_QWORD *)&v77.vt = L"IAccessible::get_accChild";
    v77.llVal = (LONGLONG)v20;
    v77.pRecInfo = (IRecordInfo *)__PAIR64__(HIDWORD(v71), (unsigned int)v19);
    v79 = 600;
    v80 = 1;
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0zd_EventWriteTransfer(3, MsaaProviderCallout_Start, L"IAccessible::get_accChild", (unsigned int)v19);
    *(_OWORD *)v81 = v23;
    v82 = 0;
    v24 = ((__int64 (__fastcall *)(struct IUnknown *, struct IAccessible **, struct IUnknown **))v20->lpVtbl[3].QueryInterface)(
            v20,
            v81,
            &v72);
    v78 = v24;
    if ( v24 < 0 )
    {
      if ( v24 == -2147467262 )
      {
        if ( HwndUtils::IsTrident((HWND)v19) )
          v80 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accutils.cpp",
          (const char *)(unsigned int)v24,
          v62);
      }
    }
    MsaaProviderCallTrace::~MsaaProviderCallTrace((MsaaProviderCallTrace *)&v77);
    punkVal = v72;
    if ( v72 )
    {
      vt = 9;
      pvarg.llVal = (LONGLONG)v72;
    }
    else
    {
      punkVal = pvarg.punkVal;
      vt = pvarg.vt;
    }
    if ( vt != 3 )
    {
      if ( vt == 9 )
      {
        if ( punkVal )
        {
          v27 = (struct IAccessible *)QI<IAccessible>(punkVal);
          v28 = (struct IUnknown *)v27;
          v83 = v27;
          if ( v27 )
          {
            v73 = v27;
            ((void (__fastcall *)(struct IAccessible *))v27->lpVtbl->AddRef)(v27);
            Lo = 0;
            v74 = 0;
            ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
            v71 = v28;
            goto LABEL_30;
          }
          Error::IAccessibleError(punkVal, L"IDispatch::QueryInterface", -2147467262, (HWND)v19, 603);
          if ( v72 )
            ((void (__fastcall *)(struct IUnknown *))v72->lpVtbl->Release)(v72);
LABEL_111:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11A,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\accnavutils.cpp",
            (const char *)v17,
            v66);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x12FE,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
            (const char *)v17,
            v67);
          wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v73);
          if ( v69 )
            ((void (__fastcall *)(struct IUnknown *))v69->lpVtbl->Release)(v69);
          if ( v7 )
            ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
          return v17;
        }
        v53 = 0;
        v88 = 0;
        if ( v19 )
        {
          v88 = 0;
          ProviderEntryPoint::CreateUsingHwnd((HWND)v19, &v88);
          v53 = v88;
        }
        Error::GeneralProviderError(v20, L"IAccessible::get_accChild", 0, v53, 602, 1);
        if ( v53 )
          (*(void (__fastcall **)(struct ProviderEntryPoint *))(*(_QWORD *)v53 + 16LL))(v53);
        if ( v72 )
          ((void (__fastcall *)(struct IUnknown *))v72->lpVtbl->Release)(v72);
      }
      else
      {
        Error::IAccessibleError(v20, L"IAccessible::get_accChild", 0, (HWND)v19, 601);
        if ( v72 )
          ((void (__fastcall *)(struct IUnknown *))v72->lpVtbl->Release)(v72);
      }
      v17 = -2147467259;
      goto LABEL_111;
    }
    v28 = v20;
    v73 = v20;
    ((void (__fastcall *)(struct IUnknown *))v20->lpVtbl->AddRef)(v20);
    Lo = pvarg.cyVal.Lo;
    v74 = pvarg.cyVal.Lo;
    v71 = v20;
LABEL_30:
    BehaviorVersion = AccUtils::GetBehaviorVersion((struct IAccessible *)v20, (HWND)v19);
    if ( BehaviorVersion > 0x70000 )
    {
      AccUtils::SetBehaviorVersion((struct IAccessible *)v71, (HWND)v19, BehaviorVersion);
      ConnectionTimeout = AccUtils::GetConnectionTimeout((struct IAccessible *)v20, (HWND)v19);
      AccUtils::SetConnectionTimeout((struct IAccessible *)v71, (HWND)v19, ConnectionTimeout);
      TransactionTimeout = AccUtils::GetTransactionTimeout((struct IAccessible *)v20, (HWND)v19);
      AccUtils::SetTransactionTimeout((struct IAccessible *)v71, (HWND)v19, TransactionTimeout);
    }
    if ( v72 )
      ((void (__fastcall *)(struct IUnknown *))v72->lpVtbl->Release)(v72);
    if ( !v28 )
      goto LABEL_53;
    if ( (unsigned int)AccNavUtils::ShouldBeInTree((struct IAccessible *)v28, Lo, *((HWND *)this + 29)) )
      break;
    wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v73);
    v16 = v86;
  }
  v31 = v88;
  v63 = *((_DWORD *)this + 60);
  v32 = (*(__int64 (__fastcall **)(MsaaProxy *, struct IUnknown *, _QWORD, _QWORD))(*(_QWORD *)this + 8LL))(
          this,
          v28,
          Lo,
          *((_QWORD *)this + 29));
  v33 = v32;
  if ( v32 >= 0 )
  {
    ((void (__fastcall *)(struct IUnknown *))v28->lpVtbl->Release)(v28);
    goto LABEL_38;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1307,
    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
    (const char *)(unsigned int)v32,
    v63);
  wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v73);
  if ( v69 )
    ((void (__fastcall *)(struct IUnknown *))v69->lpVtbl->Release)(v69);
  if ( v7 )
    ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
  return v33;
}

```

## disassembly

```asm
0x1800baaa4  mov     rax, rsp
0x1800baaa7  mov     [rax+20h], r9
0x1800baaab  mov     [rax+18h], r8
0x1800baaaf  mov     [rax+10h], edx
0x1800baab2  push    rbp
0x1800baab3  push    rbx
0x1800baab4  push    rsi
0x1800baab5  push    rdi
0x1800baab6  push    r12
0x1800baab8  push    r13
0x1800baaba  push    r14
0x1800baabc  push    r15
0x1800baabe  lea     rbp, [rax-78h]
0x1800baac2  sub     rsp, 138h
0x1800baac9  movaps  xmmword ptr [rax-58h], xmm6
0x1800baacd  movaps  xmmword ptr [rax-68h], xmm7
0x1800baad1  mov     r13, r9
0x1800baad4  mov     r12d, edx
0x1800baad7  mov     rdi, rcx
0x1800baada  mov     qword ptr [r8], 0
0x1800baae1  xor     esi, esi
0x1800baae3  mov     [rbp+70h+var_F0], rsi
0x1800baae7  cmp     [rcx+1ECh], esi
0x1800baaed  jz      loc_1800BB4A3
0x1800baaf3  mov     [rsp+170h+var_120], 0
0x1800baafc  cmp     dword ptr [rdi+210h], 0
0x1800bab03  jnz     loc_1800BB698
0x1800bab09  mov     [rsp+170h+var_120], 0
0x1800bab12  mov     rcx, [rdi+218h]
0x1800bab19  test    rcx, rcx
0x1800bab1c  jnz     loc_1800BB5CD
0x1800bab22  mov     edx, [rdi+228h]
0x1800bab28  test    edx, edx
0x1800bab2a  jz      loc_1800BAE99
0x1800bab30  mov     rcx, [rdi+220h]
0x1800bab37  test    rcx, rcx
0x1800bab3a  jz      loc_1800BB2BA
0x1800bab40  mov     [rsp+170h+var_120], 0
0x1800bab49  mov     rcx, [rcx+20h]
0x1800bab4d  test    rcx, rcx
0x1800bab50  jz      loc_1800BB792
0x1800bab56  mov     rax, [rcx]
0x1800bab59  lea     r8, [rsp+170h+var_120]
0x1800bab5e  lea     rdx, _GUID_618736e0_3c3d_11cf_810c_00aa00389b71
0x1800bab65  mov     rax, [rax]
0x1800bab68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bab6d  mov     ebx, eax
0x1800bab6f  test    ebx, ebx
0x1800bab71  js      loc_1800BB69D
0x1800bab77  cmp     [rsp+170h+var_120], 0
0x1800bab7d  jz      loc_1800BAEA7
0x1800bab83  mov     eax, [rdi+1ECh]
0x1800bab89  mov     r14d, 1
0x1800bab8f  cmp     eax, r14d
0x1800bab92  jnz     loc_1800BAF0C
0x1800bab98  mov     r13d, [rdi+230h]
0x1800bab9f  mov     r12d, 80004002h
0x1800baba5  lea     rbx, aIaccessibleGet_12; "IAccessible::get_accChild"
0x1800babac  mov     [rsp+170h+var_100], 0
0x1800babb5  mov     [rsp+170h+var_F8], 0
0x1800babbd  mov     eax, [rbp+70h+arg_8]
0x1800babc3  neg     eax
0x1800babc5  sbb     ecx, ecx
0x1800babc7  and     ecx, 2
0x1800babca  dec     ecx
0x1800babcc  add     r13d, ecx
0x1800babcf  mov     [rbp+70h+arg_0], r13d
0x1800babd6  jz      loc_1800BAEF6
0x1800babdc  mov     r14, [rdi+0E8h]
0x1800babe3  mov     [rsp+170h+var_110], r14
0x1800babe8  mov     r15, [rsp+170h+var_120]
0x1800babed  mov     [rsp+170h+var_118], 0
0x1800babf5  mov     qword ptr [rbp+70h+var_C0], rbx
0x1800babf9  mov     qword ptr [rbp+70h+var_C0+8], r15
0x1800babfd  mov     dword ptr [rbp+70h+var_C0+10h], r14d
0x1800bac01  mov     rax, r14
0x1800bac04  sar     rax, 20h
0x1800bac08  mov     dword ptr [rbp+70h+var_C0+14h], eax
0x1800bac0b  mov     [rbp+70h+var_A4], 258h
0x1800bac12  mov     [rbp+70h+var_A0], 1
0x1800bac16  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800bac1d  jnz     loc_1800BB77B
0x1800bac23  mov     rax, [r15]
0x1800bac26  lea     rdx, [rsp+170h+var_118]
0x1800bac2b  mov     rcx, r15
0x1800bac2e  mov     rax, [rax+40h]
0x1800bac32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bac37  mov     r13d, eax
0x1800bac3a  mov     [rbp+70h+var_A8], eax
0x1800bac3d  test    eax, eax
0x1800bac3f  js      loc_1800BB27E
0x1800bac45  lea     rcx, [rbp+70h+var_C0]; this
0x1800bac49  call    ??1MsaaProviderCallTrace@@QEAA@XZ; MsaaProviderCallTrace::~MsaaProviderCallTrace(void)
0x1800bac4e  xor     r13d, r13d
0x1800bac51  test    r13d, r13d
0x1800bac54  js      loc_1800BAEF6
0x1800bac5a  mov     r13d, [rbp+70h+arg_0]
0x1800bac61  cmp     r13d, [rsp+170h+var_118]
0x1800bac66  jg      loc_1800BAEF6
0x1800bac6c  xorps   xmm0, xmm0
0x1800bac6f  xor     eax, eax
0x1800bac71  movups  xmmword ptr [rbp+70h+pvarg], xmm0
0x1800bac75  lea     ecx, [rax+3]
0x1800bac78  mov     word ptr [rbp+70h+pvarg], cx
0x1800bac7c  mov     dword ptr [rbp+70h+pvarg+8], r13d
0x1800bac80  movups  xmm6, xmmword ptr [rbp+70h+pvarg]
0x1800bac84  movaps  xmmword ptr [rbp+70h+pvarg], xmm6
0x1800bac88  movq    xmm7, rax
0x1800bac8d  mov     [rsp+170h+var_108], rax
0x1800bac92  mov     qword ptr [rbp+70h+var_C0], rbx
0x1800bac96  mov     qword ptr [rbp+70h+var_C0+8], r15
0x1800bac9a  mov     dword ptr [rbp+70h+var_C0+10h], r14d
0x1800bac9e  mov     eax, dword ptr [rsp+170h+var_110+4]
0x1800baca2  mov     dword ptr [rbp+70h+var_C0+14h], eax
0x1800baca5  mov     [rbp+70h+var_A4], 258h
0x1800bacac  mov     [rbp+70h+var_A0], 1
0x1800bacb0  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800bacb7  jnz     loc_1800BB7FD
0x1800bacbd  movaps  xmmword ptr [rbp+70h+var_90], xmm6
0x1800bacc1  movsd   [rbp+70h+var_80], xmm7
0x1800bacc6  mov     rax, [r15]
0x1800bacc9  lea     r8, [rsp+170h+var_108]
0x1800bacce  lea     rdx, [rbp+70h+var_90]
0x1800bacd2  mov     rcx, r15
0x1800bacd5  mov     rax, [rax+48h]
0x1800bacd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bacde  mov     [rbp+70h+var_A8], eax
0x1800bace1  test    eax, eax
0x1800bace3  js      loc_1800BB85D
0x1800bace9  lea     rcx, [rbp+70h+var_C0]; this
0x1800baced  call    ??1MsaaProviderCallTrace@@QEAA@XZ; MsaaProviderCallTrace::~MsaaProviderCallTrace(void)
0x1800bacf2  nop
0x1800bacf3  mov     r13, [rsp+170h+var_108]
0x1800bacf8  mov     ecx, 9
0x1800bacfd  test    r13, r13
0x1800bad00  jz      loc_1800BB828
0x1800bad06  movzx   eax, cx
0x1800bad09  mov     qword ptr [rbp+70h+pvarg+8], r13
0x1800bad0d  mov     edx, 3
0x1800bad12  cmp     ax, dx
0x1800bad15  jz      loc_1800BB479
0x1800bad1b  cmp     ax, cx
0x1800bad1e  jnz     loc_1800BB597
0x1800bad24  test    r13, r13
0x1800bad27  jz      loc_1800BB300
0x1800bad2d  mov     rcx, r13
0x1800bad30  call    ??$QI@UIAccessible@@@@YAPEAUIAccessible@@PEAUIUnknown@@@Z; QI<IAccessible>(IUnknown *)
0x1800bad35  mov     rbx, rax
0x1800bad38  mov     [rbp+70h+var_70], rax
0x1800bad3c  test    rax, rax
0x1800bad3f  jz      loc_1800BB37C
0x1800bad45  mov     [rsp+170h+var_100], rax
0x1800bad4a  mov     rcx, [rax]
0x1800bad4d  mov     rax, [rcx+8]
0x1800bad51  mov     rcx, rbx
0x1800bad54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad59  xor     r13d, r13d
0x1800bad5c  mov     [rsp+170h+var_F8], r13d
0x1800bad61  mov     rax, [rbx]
0x1800bad64  mov     rcx, rbx
0x1800bad67  mov     rax, [rax+10h]
0x1800bad6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad70  nop
0x1800bad71  mov     [rsp+170h+var_110], rbx
0x1800bad76  mov     rdx, r14; HWND
0x1800bad79  mov     rcx, r15; struct IAccessible *
0x1800bad7c  call    ?GetBehaviorVersion@AccUtils@@SAKPEAUIAccessible@@PEAUHWND__@@@Z; AccUtils::GetBehaviorVersion(IAccessible *,HWND__ *)
0x1800bad81  cmp     eax, 70000h
0x1800bad86  ja      loc_1800BB64D
0x1800bad8c  mov     rcx, [rsp+170h+var_108]
0x1800bad91  test    rcx, rcx
0x1800bad94  jz      short loc_1800BADA3
0x1800bad96  mov     rax, [rcx]
0x1800bad99  mov     rax, [rax+10h]
0x1800bad9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bada2  nop
0x1800bada3  test    rbx, rbx
0x1800bada6  jz      loc_1800BAEF6
0x1800badac  mov     r8, [rdi+0E8h]; HWND
0x1800badb3  mov     edx, r13d; int
0x1800badb6  mov     rcx, rbx; struct IAccessible *
0x1800badb9  call    ?ShouldBeInTree@AccNavUtils@@SAHPEAUIAccessible@@JPEAUHWND__@@@Z; AccNavUtils::ShouldBeInTree(IAccessible *,long,HWND__ *)
0x1800badbe  test    eax, eax
0x1800badc0  jz      loc_1800BB2A4
0x1800badc6  mov     rax, [rdi]
0x1800badc9  mov     r14, [rbp+70h+arg_10]
0x1800badd0  mov     [rsp+170h+var_138], r14
0x1800badd5  lea     rcx, _GUID_f7063da8_8359_439c_9297_bbc5299a7d87
0x1800baddc  mov     [rsp+170h+var_140], rcx
0x1800bade1  mov     dword ptr [rsp+170h+var_148], 0
0x1800bade9  mov     ecx, [rdi+0F0h]
0x1800badef  mov     dword ptr [rsp+170h+var_150], ecx; int
0x1800badf3  mov     r9, [rdi+0E8h]
0x1800badfa  mov     r8d, r13d
0x1800badfd  mov     rdx, rbx
0x1800bae00  mov     rcx, rdi
0x1800bae03  mov     rax, [rax+8]
0x1800bae07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae0c  mov     edi, eax
0x1800bae0e  test    eax, eax
0x1800bae10  js      loc_1800BB724
0x1800bae16  test    rbx, rbx
0x1800bae19  jz      short loc_1800BAE2B
0x1800bae1b  mov     rax, [rbx]
0x1800bae1e  mov     rcx, rbx
0x1800bae21  mov     rax, [rax+10h]
0x1800bae25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae2a  nop
0x1800bae2b  mov     rcx, [r14]
0x1800bae2e  test    rcx, rcx
0x1800bae31  jz      short loc_1800BAE49
0x1800bae33  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800bae37  mov     r8d, [rbp+70h+arg_0]; int
0x1800bae3e  mov     rdx, [rsp+170h+var_120]; struct IAccessible *
0x1800bae43  call    ?SetNavMode_ChildIds@MsaaProxy@@AEAAXPEAUIAccessible@@J@Z; MsaaProxy::SetNavMode_ChildIds(IAccessible *,long)
0x1800bae48  nop
0x1800bae49  mov     rcx, [rsp+170h+var_120]
0x1800bae4e  test    rcx, rcx
0x1800bae51  jz      short loc_1800BAE60
0x1800bae53  mov     rax, [rcx]
0x1800bae56  mov     rax, [rax+10h]
0x1800bae5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae5f  nop
0x1800bae60  test    rsi, rsi
0x1800bae63  jz      short loc_1800BAE75
0x1800bae65  mov     rax, [rsi]
0x1800bae68  mov     rcx, rsi
0x1800bae6b  mov     rax, [rax+10h]
0x1800bae6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae74  nop
0x1800bae75  xor     eax, eax
0x1800bae77  lea     r11, [rsp+170h+var_38]
0x1800bae7f  movaps  xmm6, xmmword ptr [r11-18h]
0x1800bae84  movaps  xmm7, xmmword ptr [r11-28h]
0x1800bae89  mov     rsp, r11
0x1800bae8c  pop     r15
0x1800bae8e  pop     r14
0x1800bae90  pop     r13
0x1800bae92  pop     r12
0x1800bae94  pop     rdi
0x1800bae95  pop     rsi
0x1800bae96  pop     rbx
0x1800bae97  pop     rbp
0x1800bae98  retn
0x1800bae99  cmp     qword ptr [rdi+220h], 0
0x1800baea1  jnz     loc_1800BAB30
0x1800baea7  mov     ebx, 80004005h
0x1800baeac  mov     rcx, [rbp+78h]; this
0x1800baeb0  mov     r9d, ebx; char *
0x1800baeb3  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x1800baeba  mov     edx, 12F3h; void *
0x1800baebf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800baec4  nop
0x1800baec5  mov     rcx, [rsp+170h+var_120]
0x1800baeca  test    rcx, rcx
0x1800baecd  jz      short loc_1800BAEDC
0x1800baecf  mov     rax, [rcx]
0x1800baed2  mov     rax, [rax+10h]
0x1800baed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baedb  nop
0x1800baedc  test    rsi, rsi
0x1800baedf  jz      short loc_1800BAEF1
0x1800baee1  mov     rcx, [rsi]
0x1800baee4  mov     rax, [rcx+10h]
0x1800baee8  mov     rcx, rsi
0x1800baeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baef0  nop
0x1800baef1  jmp     loc_1800BB277
0x1800baef6  lea     rcx, [rsp+170h+var_100]; void *
0x1800baefb  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x1800baf00  mov     r14, [rbp+70h+arg_10]
0x1800baf07  jmp     loc_1800BAE2B
0x1800baf0c  cmp     eax, 2
0x1800baf0f  jnz     loc_1800BAE49
0x1800baf15  mov     [rsp+170h+var_110], 0
0x1800baf1e  lea     r15, [rdi+1F0h]
0x1800baf25  lea     r8, [rsp+170h+var_110]
0x1800baf2a  mov     rdx, [rdi+0F8h]
0x1800baf31  mov     rcx, r15
0x1800baf34  call    ?TryGet@?$AgileInterface@UIEnumVARIANT@@@@QEAAJPEAUIGlobalInterfaceTable@@PEAPEAUIEnumVARIANT@@@Z; AgileInterface<IEnumVARIANT>::TryGet(IGlobalInterfaceTable *,IEnumVARIANT * *)
0x1800baf39  mov     ebx, eax
0x1800baf3b  test    eax, eax
0x1800baf3d  js      loc_1800BB79C
0x1800baf43  mov     rcx, [rdi+0E8h]; hWnd
0x1800baf4a  call    ?IsTrident@HwndUtils@@SA_NPEAUHWND__@@@Z; HwndUtils::IsTrident(HWND__ *)
0x1800baf4f  test    al, al
0x1800baf51  jnz     loc_1800BB62F
0x1800baf57  mov     rbx, [rsp+170h+var_110]
0x1800baf5c  test    r12d, r12d
0x1800baf5f  jnz     loc_1800BB2EF
0x1800baf65  test    rbx, rbx
0x1800baf68  jz      loc_1800BB5EA
0x1800baf6e  mov     rsi, rbx
0x1800baf71  mov     [rbp+70h+var_F0], rbx
0x1800baf75  mov     [rsp+170h+var_110], 0
0x1800baf7e  mov     rdx, [rdi+0F8h]
0x1800baf85  mov     rcx, r15
0x1800baf88  call    ?Clear@?$AgileInterface@UIEnumVARIANT@@@@QEAAXPEAUIGlobalInterfaceTable@@@Z; AgileInterface<IEnumVARIANT>::Clear(IGlobalInterfaceTable *)
0x1800baf8d  test    r14d, r14d
0x1800baf90  jnz     loc_1800BB6BA
  ... truncated ...
```
