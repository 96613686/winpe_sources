# CUPnPAutomationProxy::HrInitializeArguments(IXMLDOMNodeList *,tagUPNP_ACTION *)

- ea: `0x18000c7d0`
- end: `0x18000d163`
- name: `?HrInitializeArguments@CUPnPAutomationProxy@@AEAAJPEAUIXMLDOMNodeList@@PEAUtagUPNP_ACTION@@@Z`
- size: `2451`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, struct IXMLDOMNodeList *, struct tagUPNP_ACTION *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000dfc4`

## callees

- `0x18000c570`
- `0x18000c7d0`
- `0x18000d16c`
- `0x18000db4c`
- `0x18000dbc0`
- `0x18000e3ec`
- `0x180038ce4`
- `0x180039388`
- `0x180046540`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000cc8d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000cc8d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c9a3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cda2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c9a3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cda2`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c96f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c96f`

## pseudocode

```c
__int64 __fastcall CUPnPAutomationProxy::HrInitializeArguments(
        CUPnPAutomationProxy *this,
        struct IXMLDOMNodeList *a2,
        struct tagUPNP_ACTION *a3)
{
  int TypedValueFromElement; // ebx
  unsigned int v5; // esi
  struct tagUPNP_ACTION *v6; // rdi
  struct IXMLDOMNodeList *v7; // r9
  struct IXMLDOMNodeListVtbl *lpVtbl; // rax
  int v9; // eax
  unsigned int v10; // r8d
  struct IXMLDOMNode *v11; // rcx
  LONGLONG *v12; // r14
  int NestedChildElement; // eax
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // r8d
  struct IXMLDOMNode *v16; // rdi
  STRSAFE_PCNZWCH v17; // rcx
  unsigned __int16 *bstrVal; // r15
  int v19; // eax
  const unsigned __int16 *v20; // rdx
  int v21; // edi
  struct IXMLDOMNode *v22; // rbx
  struct tagUPNP_STATE_VARIABLE *v23; // rax
  STRSAFE_PCNZWCH v24; // rcx
  int v25; // edx
  STRSAFE_PCNZWCH v26; // rcx
  unsigned int v27; // r15d
  struct IXMLDOMNodeListVtbl *v28; // rcx
  __int64 v29; // rdx
  unsigned int v30; // r8d
  struct IXMLDOMNode *v31; // rcx
  LONGLONG *v32; // r12
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  unsigned int v35; // r8d
  struct IXMLDOMNode *v36; // rdi
  STRSAFE_PCNZWCH v37; // rcx
  OLECHAR *v38; // r14
  int v39; // eax
  const unsigned __int16 *v40; // rdx
  struct IXMLDOMNode *v41; // rdi
  STRSAFE_PCNZWCH v42; // rcx
  __int64 i; // rbx
  unsigned int v44; // r8d
  _QWORD *v45; // rsi
  struct IXMLDOMNode *v47; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 *v48; // [rsp+38h] [rbp-28h] BYREF
  struct tagVARIANT pbstr; // [rsp+40h] [rbp-20h] BYREF
  struct IXMLDOMNode *v52; // [rsp+B8h] [rbp+58h] BYREF

  TypedValueFromElement = 0;
  v5 = 0;
  v6 = a3;
  v7 = a2;
  while ( v5 < *((_DWORD *)v6 + 3) )
  {
    lpVtbl = v7->lpVtbl;
    v52 = 0;
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, _QWORD, struct IXMLDOMNode **))lpVtbl->get_item)(
           v7,
           v5,
           &v52);
    TypedValueFromElement = v9;
    if ( v9 >= 0 )
    {
      v11 = v52;
      v12 = (LONGLONG *)(*((_QWORD *)v6 + 2) + 16LL * v5);
      v48 = L"name";
      memset(&pbstr, 0, sizeof(pbstr));
      *v12 = 0;
      v47 = 0;
      NestedChildElement = HrGetNestedChildElement(v11, (const unsigned __int16 *const *)&v48, v10, &v47);
      TypedValueFromElement = NestedChildElement;
      if ( NestedChildElement >= 0 )
      {
        v16 = v47;
        if ( !NestedChildElement )
          TypedValueFromElement = HrGetTypedValueFromElement(v47, v14, &pbstr);
        if ( v16 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v16->lpVtbl->Release)(v16);
        if ( TypedValueFromElement >= 0 )
        {
          if ( !TypedValueFromElement )
            *v12 = pbstr.llVal;
          v17 = WPP_GLOBAL_Control;
          goto LABEL_13;
        }
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        goto LABEL_96;
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
          (unsigned int)TypedValueFromElement);
        v17 = WPP_GLOBAL_Control;
      }
      if ( TypedValueFromElement < 0 )
      {
LABEL_96:
        if ( v17 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        {
          if ( (v17[14] & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)v17 + 2),
              18,
              WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
              (unsigned int)TypedValueFromElement);
            v17 = WPP_GLOBAL_Control;
          }
          if ( v17 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v17[14] & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)v17 + 2),
              110,
              (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
              (unsigned int)"CUPnPAutomationProxy::HrInitializeArguments(): Failed to get <name> value",
              TypedValueFromElement);
        }
        goto LABEL_29;
      }
LABEL_13:
      v48 = L"relatedStateVariable";
      if ( v17 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v17[14] & 0x40) != 0 )
        WPP_SF_S(*((_QWORD *)v17 + 2), 106, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids, *v12);
      v47 = 0;
      memset(&pbstr, 0, sizeof(pbstr));
      bstrVal = 0;
      v19 = HrGetNestedChildElement(v52, (const unsigned __int16 *const *)&v48, v15, &v47);
      v21 = v19;
      if ( v19 < 0 )
      {
        TypedValueFromElement = v19;
      }
      else
      {
        v22 = v47;
        if ( !v19 )
          v21 = HrGetTypedValueFromElement(v47, v20, &pbstr);
        if ( v22 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v22->lpVtbl->Release)(v22);
        TypedValueFromElement = v21;
        if ( v21 >= 0 )
        {
          if ( !v21 )
          {
            bstrVal = pbstr.bstrVal;
LABEL_24:
            if ( SysStringLen(bstrVal) )
            {
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
                WPP_SF_SS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  107,
                  (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                  *v12,
                  (__int64)bstrVal);
              v23 = CUPnPAutomationProxy::LookupVariableByName(this, bstrVal);
              if ( v23 )
              {
                v12[1] = (LONGLONG)v23;
              }
              else
              {
                v12[1] = 0;
                TypedValueFromElement = -2147024809;
                if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                  WPP_SF_sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    108,
                    (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                    (unsigned int)"CUPnPAutomationProxy::HrInitializeArguments(): Failed to find related state variable",
                    87);
              }
              SysFreeString(bstrVal);
            }
LABEL_29:
            ((void (__fastcall *)(struct IXMLDOMNode *))v52->lpVtbl->Release)(v52);
            v24 = WPP_GLOBAL_Control;
            v6 = a3;
            goto LABEL_30;
          }
          v26 = WPP_GLOBAL_Control;
LABEL_45:
          TypedValueFromElement = v21;
          if ( !v21 )
            goto LABEL_24;
          goto LABEL_46;
        }
      }
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        goto LABEL_45;
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
          (unsigned int)v21);
        v26 = WPP_GLOBAL_Control;
      }
      if ( v21 >= 0 || v26 == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (v26[14] & 1) == 0 )
        goto LABEL_45;
      WPP_SF_d(*((_QWORD *)v26 + 2), 18, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids, (unsigned int)v21);
      v26 = WPP_GLOBAL_Control;
LABEL_46:
      if ( v26 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v26[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)v26 + 2),
          109,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (unsigned int)"CUPnPAutomationProxy::HrInitializeArguments(): Failed to get <relatedStateVariable> value",
          v21);
      goto LABEL_29;
    }
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v25 = 111;
      goto LABEL_104;
    }
LABEL_30:
    ++v5;
    if ( TypedValueFromElement < 0 )
      goto LABEL_105;
    v7 = a2;
  }
  v27 = 0;
  while ( 1 )
  {
    if ( v27 >= *((_DWORD *)v6 + 6) )
      return (unsigned int)TypedValueFromElement;
    v28 = v7->lpVtbl;
    v29 = v27 + *((_DWORD *)v6 + 3);
    v52 = 0;
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, __int64, struct IXMLDOMNode **))v28->get_item)(
           v7,
           v29,
           &v52);
    TypedValueFromElement = v9;
    if ( v9 >= 0 )
    {
      v31 = v52;
      v48 = L"name";
      v32 = (LONGLONG *)(*((_QWORD *)v6 + 4) + 16LL * v27);
      memset(&pbstr, 0, sizeof(pbstr));
      v47 = 0;
      *v32 = 0;
      v33 = HrGetNestedChildElement(v31, (const unsigned __int16 *const *)&v48, v30, &v47);
      TypedValueFromElement = v33;
      if ( v33 >= 0 )
      {
        v36 = v47;
        if ( !v33 )
          TypedValueFromElement = HrGetTypedValueFromElement(v47, v34, &pbstr);
        if ( v36 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v36->lpVtbl->Release)(v36);
        if ( TypedValueFromElement >= 0 )
        {
          if ( !TypedValueFromElement )
            *v32 = pbstr.llVal;
          v37 = WPP_GLOBAL_Control;
          goto LABEL_62;
        }
        v6 = a3;
      }
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        goto LABEL_92;
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
          (unsigned int)TypedValueFromElement);
        v37 = WPP_GLOBAL_Control;
      }
      if ( TypedValueFromElement < 0 )
      {
        if ( v37 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        {
          if ( (v37[14] & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)v37 + 2),
              18,
              WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
              (unsigned int)TypedValueFromElement);
            v37 = WPP_GLOBAL_Control;
          }
          if ( v37 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v37[14] & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)v37 + 2),
              117,
              (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
              (unsigned int)"CUPnPAutomationProxy::HrInitializeArguments(): Failed to get <name> value",
              TypedValueFromElement);
        }
        goto LABEL_92;
      }
LABEL_62:
      v48 = L"relatedStateVariable";
      if ( v37 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v37[14] & 0x40) != 0 )
        WPP_SF_S(*((_QWORD *)v37 + 2), 112, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids, *v32);
      v47 = 0;
      memset(&pbstr, 0, sizeof(pbstr));
      v38 = 0;
      v39 = HrGetNestedChildElement(v52, (const unsigned __int16 *const *)&v48, v35, &v47);
      TypedValueFromElement = v39;
      if ( v39 >= 0 )
      {
        v41 = v47;
        if ( !v39 )
          TypedValueFromElement = HrGetTypedValueFromElement(v47, v40, &pbstr);
        if ( v41 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v41->lpVtbl->Release)(v41);
        if ( TypedValueFromElement >= 0 )
        {
          v42 = WPP_GLOBAL_Control;
          if ( !TypedValueFromElement )
            v38 = pbstr.bstrVal;
          goto LABEL_71;
        }
      }
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
            (unsigned int)TypedValueFromElement);
          v42 = WPP_GLOBAL_Control;
        }
        if ( TypedValueFromElement >= 0 )
        {
LABEL_71:
          if ( v42 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v42[14] & 0x40) != 0 )
            WPP_SF_SS(
              *((_QWORD *)v42 + 2),
              113,
              (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
              *v32,
              (__int64)v38);
          for ( i = 0; ; i = (unsigned int)(i + 1) )
          {
            if ( (unsigned int)i >= *((_DWORD *)this + 24) )
              goto LABEL_79;
            if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(*((_QWORD *)this + 13) + 24 * i), v38) )
              break;
          }
          v45 = (_QWORD *)(24 * i + *((_QWORD *)this + 13));
          if ( !v45 )
          {
LABEL_79:
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids, v38);
            v32[1] = 0;
            TypedValueFromElement = -2147024809;
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                115,
                (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                (unsigned int)"CUPnPAutomationProxy::HrInitializeArguments(): Failed to find related state variable",
                87);
LABEL_90:
            v6 = a3;
            goto LABEL_91;
          }
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids, *v45);
          v32[1] = (LONGLONG)v45;
          v48 = L"retval";
          v47 = 0;
          TypedValueFromElement = HrGetNestedChildElement(v52, (const unsigned __int16 *const *)&v48, v44, &v47);
          if ( TypedValueFromElement < 0 )
          {
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                114,
                (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                (unsigned int)"CUPnPAutomationProxy::HrInitializeArguments(): Failed get retval element",
                TypedValueFromElement);
            goto LABEL_90;
          }
          v6 = a3;
          if ( v47 )
            *((_QWORD *)a3 + 5) = v32;
LABEL_91:
          SysFreeString(v38);
          goto LABEL_92;
        }
      }
      if ( v42 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      {
        if ( (v42[14] & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)v42 + 2),
            18,
            WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
            (unsigned int)TypedValueFromElement);
          v42 = WPP_GLOBAL_Control;
        }
        if ( v42 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v42[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)v42 + 2),
            116,
            (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
            (unsigned int)"CUPnPAutomationProxy::HrInitializeArguments(): Failed to get <relatedStateVariable> value",
            TypedValueFromElement);
      }
      v6 = a3;
LABEL_92:
      ((void (__fastcall *)(struct IXMLDOMNode *))v52->lpVtbl->Release)(v52);
      v24 = WPP_GLOBAL_Control;
      goto LABEL_93;
    }
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      break;
LABEL_93:
    ++v27;
    if ( TypedValueFromElement < 0 )
      goto LABEL_105;
    v7 = a2;
  }
  v25 = 118;
LABEL_104:
  WPP_SF_sd(
    *((_QWORD *)v24 + 2),
    v25,
    (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
    (unsigned int)"CUPnPAutomationProxy::HrInitializeArguments(): Failed to get list item",
    v9);
  v24 = WPP_GLOBAL_Control;
LABEL_105:
  if ( v24 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v24[14] & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)v24 + 2),
      119,
      (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
      *(_QWORD *)v6,
      TypedValueFromElement);
  return (unsigned int)TypedValueFromElement;
}

```

## disassembly

```asm
0x18000c7d0  mov     [rsp-38h+arg_0], rbx
0x18000c7d5  mov     [rsp-38h+arg_10], r8
0x18000c7da  mov     [rsp-38h+arg_8], rdx
0x18000c7df  push    rbp
0x18000c7e0  push    rsi
0x18000c7e1  push    rdi
0x18000c7e2  push    r12
0x18000c7e4  push    r13
0x18000c7e6  push    r14
0x18000c7e8  push    r15
0x18000c7ea  mov     rbp, rsp
0x18000c7ed  sub     rsp, 60h
0x18000c7f1  xor     r12d, r12d
0x18000c7f4  lea     r15, aName; "name"
0x18000c7fb  mov     r13, rcx
0x18000c7fe  lea     r14, WPP_GLOBAL_Control
0x18000c805  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c80c  mov     ebx, r12d
0x18000c80f  mov     esi, r12d
0x18000c812  mov     rdi, r8
0x18000c815  mov     r9, rdx
0x18000c818  nop     dword ptr [rax+rax+00000000h]
0x18000c820  cmp     esi, [rdi+0Ch]
0x18000c823  jnb     loc_18000CB0D
0x18000c829  mov     rax, [r9]
0x18000c82c  lea     r8, [rbp+arg_18]
0x18000c830  mov     edx, esi
0x18000c832  mov     [rbp+arg_18], r12
0x18000c836  mov     rcx, r9
0x18000c839  mov     rax, [rax+38h]
0x18000c83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c842  mov     ebx, eax
0x18000c844  test    eax, eax
0x18000c846  js      loc_18000CA4E
0x18000c84c  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x18000c850  lea     r9, [rbp+var_30]; struct IXMLDOMNode **
0x18000c854  xorps   xmm0, xmm0
0x18000c857  mov     r14d, esi
0x18000c85a  xor     eax, eax
0x18000c85c  shl     r14, 4
0x18000c860  add     r14, [rdi+10h]
0x18000c864  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18000c868  mov     [rbp+var_28], r15
0x18000c86c  movups  xmmword ptr [rbp+pbstr], xmm0
0x18000c870  mov     [rbp+var_10], rax
0x18000c874  mov     [r14], r12
0x18000c877  mov     [rbp+var_30], r12
0x18000c87b  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x18000c880  mov     ebx, eax
0x18000c882  test    eax, eax
0x18000c884  js      loc_18000CF9C
0x18000c88a  mov     rdi, [rbp+var_30]
0x18000c88e  jnz     short loc_18000C89E
0x18000c890  lea     r8, [rbp+pbstr]; struct tagVARIANT *
0x18000c894  mov     rcx, rdi; struct IXMLDOMNode *
0x18000c897  call    ?HrGetTypedValueFromElement@@YAJPEAUIXMLDOMNode@@QEBGPEAUtagVARIANT@@@Z; HrGetTypedValueFromElement(IXMLDOMNode *,ushort const * const,tagVARIANT *)
0x18000c89c  mov     ebx, eax
0x18000c89e  test    rdi, rdi
0x18000c8a1  jz      short loc_18000C8B2
0x18000c8a3  mov     rax, [rdi]
0x18000c8a6  mov     rcx, rdi
0x18000c8a9  mov     rax, [rax+10h]
0x18000c8ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8b2  test    ebx, ebx
0x18000c8b4  js      loc_18000CF9C
0x18000c8ba  lea     rdi, WPP_GLOBAL_Control
0x18000c8c1  jnz     short loc_18000C8CA
0x18000c8c3  mov     rax, [rbp+pbstr+8]
0x18000c8c7  mov     [r14], rax
0x18000c8ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8d1  lea     rax, aRelatedstateva; "relatedStateVariable"
0x18000c8d8  mov     [rbp+var_28], rax
0x18000c8dc  cmp     rcx, rdi
0x18000c8df  jz      short loc_18000C8FF
0x18000c8e1  test    byte ptr [rcx+1Ch], 40h
0x18000c8e5  jz      short loc_18000C8FF
0x18000c8e7  mov     r9, [r14]
0x18000c8ea  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18000c8f1  mov     rcx, [rcx+10h]
0x18000c8f5  mov     edx, 6Ah ; 'j'
0x18000c8fa  call    WPP_SF_S
0x18000c8ff  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x18000c903  lea     r9, [rbp+var_30]; struct IXMLDOMNode **
0x18000c907  xorps   xmm0, xmm0
0x18000c90a  mov     [rbp+var_30], r12
0x18000c90e  xor     eax, eax
0x18000c910  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18000c914  movups  xmmword ptr [rbp+pbstr], xmm0
0x18000c918  mov     [rbp+var_10], rax
0x18000c91c  mov     r15, r12
0x18000c91f  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x18000c924  mov     edi, eax
0x18000c926  test    eax, eax
0x18000c928  js      loc_18000CA72
0x18000c92e  mov     rbx, [rbp+var_30]
0x18000c932  test    eax, eax
0x18000c934  jnz     short loc_18000C944
0x18000c936  lea     r8, [rbp+pbstr]; struct tagVARIANT *
0x18000c93a  mov     rcx, rbx; struct IXMLDOMNode *
0x18000c93d  call    ?HrGetTypedValueFromElement@@YAJPEAUIXMLDOMNode@@QEBGPEAUtagVARIANT@@@Z; HrGetTypedValueFromElement(IXMLDOMNode *,ushort const * const,tagVARIANT *)
0x18000c942  mov     edi, eax
0x18000c944  test    rbx, rbx
0x18000c947  jz      short loc_18000C958
0x18000c949  mov     rax, [rbx]
0x18000c94c  mov     rcx, rbx
0x18000c94f  mov     rax, [rax+10h]
0x18000c953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c958  mov     ebx, edi
0x18000c95a  test    edi, edi
0x18000c95c  js      loc_18000CA74
0x18000c962  jnz     loc_18000CAFD
0x18000c968  mov     r15, [rbp+pbstr+8]
0x18000c96c  mov     rcx, r15; pbstr
0x18000c96f  call    cs:__imp_SysStringLen
0x18000c975  test    eax, eax
0x18000c977  jz      short loc_18000C9A9
0x18000c979  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c980  lea     rdi, WPP_GLOBAL_Control
0x18000c987  cmp     rcx, rdi
0x18000c98a  jnz     short loc_18000C9E5
0x18000c98c  mov     rdx, r15; unsigned __int16 *
0x18000c98f  mov     rcx, r13; this
0x18000c992  call    ?LookupVariableByName@CUPnPAutomationProxy@@AEAAPEAUtagUPNP_STATE_VARIABLE@@PEBG@Z; CUPnPAutomationProxy::LookupVariableByName(ushort const *)
0x18000c997  test    rax, rax
0x18000c99a  jz      short loc_18000CA0A
0x18000c99c  mov     [r14+8], rax
0x18000c9a0  mov     rcx, r15; bstrString
0x18000c9a3  call    cs:__imp_SysFreeString
0x18000c9a9  lea     r15, aName; "name"
0x18000c9b0  mov     rcx, [rbp+arg_18]
0x18000c9b4  mov     rax, [rcx]
0x18000c9b7  mov     rax, [rax+10h]
0x18000c9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9c7  lea     r14, WPP_GLOBAL_Control
0x18000c9ce  mov     rdi, [rbp+arg_10]
0x18000c9d2  inc     esi
0x18000c9d4  test    ebx, ebx
0x18000c9d6  js      loc_18000CE80
0x18000c9dc  mov     r9, [rbp+arg_8]
0x18000c9e0  jmp     loc_18000C820
0x18000c9e5  test    byte ptr [rcx+1Ch], 40h
0x18000c9e9  jz      short loc_18000C98C
0x18000c9eb  mov     r9, [r14]
0x18000c9ee  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18000c9f5  mov     rcx, [rcx+10h]
0x18000c9f9  mov     edx, 6Bh ; 'k'
0x18000c9fe  mov     [rsp+60h+var_40], r15
0x18000ca03  call    WPP_SF_SS
0x18000ca08  jmp     short loc_18000C98C
0x18000ca0a  mov     [r14+8], r12
0x18000ca0e  mov     ebx, 80070057h
0x18000ca13  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca1a  cmp     rcx, rdi
0x18000ca1d  jz      short loc_18000C9A0
0x18000ca1f  test    byte ptr [rcx+1Ch], 1
0x18000ca23  jz      loc_18000C9A0
0x18000ca29  mov     rcx, [rcx+10h]
0x18000ca2d  lea     r9, aCupnpautomatio_37; "CUPnPAutomationProxy::HrInitializeArgum"...
0x18000ca34  mov     edx, 6Ch ; 'l'
0x18000ca39  mov     dword ptr [rsp+60h+var_40], ebx
0x18000ca3d  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18000ca44  call    WPP_SF_sd
0x18000ca49  jmp     loc_18000C9A0
0x18000ca4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca55  cmp     rcx, r14
0x18000ca58  jz      loc_18000C9D2
0x18000ca5e  test    byte ptr [rcx+1Ch], 1
0x18000ca62  jz      loc_18000C9D2
0x18000ca68  mov     edx, 6Fh ; 'o'
0x18000ca6d  jmp     loc_18000CE5E
0x18000ca72  mov     ebx, eax
0x18000ca74  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca7b  lea     rax, WPP_GLOBAL_Control
0x18000ca82  cmp     rcx, rax
0x18000ca85  jz      short loc_18000CABB
0x18000ca87  test    byte ptr [rcx+1Ch], 1
0x18000ca8b  jz      short loc_18000CAB3
0x18000ca8d  mov     rcx, [rcx+10h]
0x18000ca91  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000ca98  mov     edx, 10h
0x18000ca9d  mov     r9d, edi
0x18000caa0  call    WPP_SF_d
0x18000caa5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000caac  lea     rax, WPP_GLOBAL_Control
0x18000cab3  test    edi, edi
0x18000cab5  js      loc_18000CFE1
0x18000cabb  mov     ebx, edi
0x18000cabd  test    edi, edi
0x18000cabf  jz      loc_18000C96C
0x18000cac5  cmp     rcx, rax
0x18000cac8  jz      loc_18000C9A9
0x18000cace  test    byte ptr [rcx+1Ch], 1
0x18000cad2  jz      loc_18000C9A9
0x18000cad8  mov     rcx, [rcx+10h]
0x18000cadc  lea     r9, aCupnpautomatio_39; "CUPnPAutomationProxy::HrInitializeArgum"...
0x18000cae3  mov     edx, 6Dh ; 'm'
0x18000cae8  mov     dword ptr [rsp+60h+var_40], edi
0x18000caec  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18000caf3  call    WPP_SF_sd
0x18000caf8  jmp     loc_18000C9A9
0x18000cafd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb04  lea     rax, WPP_GLOBAL_Control
0x18000cb0b  jmp     short loc_18000CABB
0x18000cb0d  xor     esi, esi
0x18000cb0f  mov     r15d, esi
0x18000cb12  test    ebx, ebx
0x18000cb14  js      loc_18000CE80
0x18000cb1a  nop     word ptr [rax+rax+00h]
0x18000cb20  cmp     r15d, [rdi+18h]
0x18000cb24  jnb     loc_18000CEA7
0x18000cb2a  mov     rcx, [r9]
0x18000cb2d  lea     r8, [rbp+arg_18]
0x18000cb31  mov     edx, [rdi+0Ch]
0x18000cb34  add     edx, r15d
0x18000cb37  mov     [rbp+arg_18], rsi
0x18000cb3b  mov     rax, [rcx+38h]
0x18000cb3f  mov     rcx, r9
0x18000cb42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb47  mov     ebx, eax
0x18000cb49  test    eax, eax
0x18000cb4b  js      loc_18000D14E
0x18000cb51  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x18000cb55  lea     rax, aName; "name"
0x18000cb5c  mov     [rbp+var_28], rax
0x18000cb60  lea     r9, [rbp+var_30]; struct IXMLDOMNode **
0x18000cb64  xorps   xmm0, xmm0
0x18000cb67  mov     r12d, r15d
0x18000cb6a  xor     eax, eax
0x18000cb6c  shl     r12, 4
0x18000cb70  add     r12, [rdi+20h]
0x18000cb74  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18000cb78  movups  xmmword ptr [rbp+pbstr], xmm0
0x18000cb7c  mov     [rbp+var_10], rax
0x18000cb80  mov     [rbp+var_30], rsi
0x18000cb84  mov     [r12], rsi
0x18000cb88  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x18000cb8d  mov     ebx, eax
0x18000cb8f  test    eax, eax
0x18000cb91  js      loc_18000D023
0x18000cb97  mov     rdi, [rbp+var_30]
0x18000cb9b  jnz     short loc_18000CBAB
0x18000cb9d  lea     r8, [rbp+pbstr]; struct tagVARIANT *
0x18000cba1  mov     rcx, rdi; struct IXMLDOMNode *
0x18000cba4  call    ?HrGetTypedValueFromElement@@YAJPEAUIXMLDOMNode@@QEBGPEAUtagVARIANT@@@Z; HrGetTypedValueFromElement(IXMLDOMNode *,ushort const * const,tagVARIANT *)
0x18000cba9  mov     ebx, eax
0x18000cbab  test    rdi, rdi
0x18000cbae  jz      short loc_18000CBBF
0x18000cbb0  mov     rax, [rdi]
0x18000cbb3  mov     rcx, rdi
0x18000cbb6  mov     rax, [rax+10h]
0x18000cbba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbbf  test    ebx, ebx
0x18000cbc1  js      loc_18000D01F
0x18000cbc7  jnz     short loc_18000CBD1
0x18000cbc9  mov     rax, [rbp+pbstr+8]
0x18000cbcd  mov     [r12], rax
0x18000cbd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbd8  lea     rax, aRelatedstateva; "relatedStateVariable"
0x18000cbdf  mov     [rbp+var_28], rax
0x18000cbe3  cmp     rcx, r14
0x18000cbe6  jnz     loc_18000D061
0x18000cbec  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x18000cbf0  lea     r9, [rbp+var_30]; struct IXMLDOMNode **
0x18000cbf4  xorps   xmm0, xmm0
0x18000cbf7  mov     [rbp+var_30], rsi
0x18000cbfb  xor     eax, eax
0x18000cbfd  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18000cc01  movups  xmmword ptr [rbp+pbstr], xmm0
0x18000cc05  mov     [rbp+var_10], rax
0x18000cc09  mov     r14, rsi
0x18000cc0c  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x18000cc11  mov     ebx, eax
0x18000cc13  test    eax, eax
0x18000cc15  js      loc_18000D089
0x18000cc1b  mov     rdi, [rbp+var_30]
0x18000cc1f  jnz     short loc_18000CC2F
0x18000cc21  lea     r8, [rbp+pbstr]; struct tagVARIANT *
0x18000cc25  mov     rcx, rdi; struct IXMLDOMNode *
0x18000cc28  call    ?HrGetTypedValueFromElement@@YAJPEAUIXMLDOMNode@@QEBGPEAUtagVARIANT@@@Z; HrGetTypedValueFromElement(IXMLDOMNode *,ushort const * const,tagVARIANT *)
0x18000cc2d  mov     ebx, eax
0x18000cc2f  test    rdi, rdi
0x18000cc32  jz      short loc_18000CC43
0x18000cc34  mov     rax, [rdi]
0x18000cc37  mov     rcx, rdi
0x18000cc3a  mov     rax, [rax+10h]
0x18000cc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc43  test    ebx, ebx
0x18000cc45  js      loc_18000D089
0x18000cc4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc52  lea     rdi, WPP_GLOBAL_Control
0x18000cc59  jnz     short loc_18000CC5F
0x18000cc5b  mov     r14, [rbp+pbstr+8]
0x18000cc5f  cmp     rcx, rdi
0x18000cc62  jz      short loc_18000CC6E
0x18000cc64  test    byte ptr [rcx+1Ch], 40h
0x18000cc68  jnz     loc_18000D0CE
0x18000cc6e  xor     ebx, ebx
0x18000cc70  cmp     ebx, [r13+60h]
0x18000cc74  jnb     short loc_18000CCA4
  ... truncated ...
```
