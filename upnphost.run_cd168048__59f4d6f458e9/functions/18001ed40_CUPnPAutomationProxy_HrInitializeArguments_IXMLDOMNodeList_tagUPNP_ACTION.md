# CUPnPAutomationProxy::HrInitializeArguments(IXMLDOMNodeList *,tagUPNP_ACTION *)

- ea: `0x18001ed40`
- end: `0x18001f6f0`
- name: `?HrInitializeArguments@CUPnPAutomationProxy@@AEAAJPEAUIXMLDOMNodeList@@PEAUtagUPNP_ACTION@@@Z`
- size: `2480`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, struct IXMLDOMNodeList *, struct tagUPNP_ACTION *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180020588`

## callees

- `0x18001eac0`
- `0x18001ed40`
- `0x18001f6f8`
- `0x1800200f4`
- `0x180020170`
- `0x1800209c8`
- `0x18003b1cc`
- `0x18003b904`
- `0x180049258`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f20d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f20d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ef19`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f328`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ef19`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f328`
- `OLEAUT32!__imp_SysStringLen` at `0x18001eedf`
- `OLEAUT32!__imp_SysStringLen` at `0x18001eedf`

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
0x18001ed40  mov     [rsp-38h+arg_0], rbx
0x18001ed45  mov     [rsp-38h+arg_10], r8
0x18001ed4a  mov     [rsp-38h+arg_8], rdx
0x18001ed4f  push    rbp
0x18001ed50  push    rsi
0x18001ed51  push    rdi
0x18001ed52  push    r12
0x18001ed54  push    r13
0x18001ed56  push    r14
0x18001ed58  push    r15
0x18001ed5a  mov     rbp, rsp
0x18001ed5d  sub     rsp, 60h
0x18001ed61  xor     r12d, r12d
0x18001ed64  lea     r15, aName; "name"
0x18001ed6b  mov     r13, rcx
0x18001ed6e  lea     r14, WPP_GLOBAL_Control
0x18001ed75  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed7c  mov     ebx, r12d
0x18001ed7f  mov     esi, r12d
0x18001ed82  mov     rdi, r8
0x18001ed85  mov     r9, rdx
0x18001ed88  nop     dword ptr [rax+rax+00000000h]
0x18001ed90  cmp     esi, [rdi+0Ch]
0x18001ed93  jnb     loc_18001F090
0x18001ed99  mov     rax, [r9]
0x18001ed9c  lea     r8, [rbp+arg_18]
0x18001eda0  mov     edx, esi
0x18001eda2  mov     [rbp+arg_18], r12
0x18001eda6  mov     rcx, r9
0x18001eda9  mov     rax, [rax+38h]
0x18001edad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edb2  mov     ebx, eax
0x18001edb4  test    eax, eax
0x18001edb6  js      loc_18001EFD1
0x18001edbc  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x18001edc0  lea     r9, [rbp+var_30]; struct IXMLDOMNode **
0x18001edc4  xorps   xmm0, xmm0
0x18001edc7  mov     r14d, esi
0x18001edca  xor     eax, eax
0x18001edcc  shl     r14, 4
0x18001edd0  add     r14, [rdi+10h]
0x18001edd4  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18001edd8  mov     [rbp+var_28], r15
0x18001eddc  movups  xmmword ptr [rbp+pbstr], xmm0
0x18001ede0  mov     [rbp+var_10], rax
0x18001ede4  mov     [r14], r12
0x18001ede7  mov     [rbp+var_30], r12
0x18001edeb  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x18001edf0  mov     ebx, eax
0x18001edf2  test    eax, eax
0x18001edf4  js      loc_18001F529
0x18001edfa  mov     rdi, [rbp+var_30]
0x18001edfe  jnz     short loc_18001EE0E
0x18001ee00  lea     r8, [rbp+pbstr]; struct tagVARIANT *
0x18001ee04  mov     rcx, rdi; struct IXMLDOMNode *
0x18001ee07  call    ?HrGetTypedValueFromElement@@YAJPEAUIXMLDOMNode@@QEBGPEAUtagVARIANT@@@Z; HrGetTypedValueFromElement(IXMLDOMNode *,ushort const * const,tagVARIANT *)
0x18001ee0c  mov     ebx, eax
0x18001ee0e  test    rdi, rdi
0x18001ee11  jz      short loc_18001EE22
0x18001ee13  mov     rax, [rdi]
0x18001ee16  mov     rcx, rdi
0x18001ee19  mov     rax, [rax+10h]
0x18001ee1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee22  test    ebx, ebx
0x18001ee24  js      loc_18001F529
0x18001ee2a  lea     rdi, WPP_GLOBAL_Control
0x18001ee31  jnz     short loc_18001EE3A
0x18001ee33  mov     rax, [rbp+pbstr+8]
0x18001ee37  mov     [r14], rax
0x18001ee3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee41  lea     rax, aRelatedstateva; "relatedStateVariable"
0x18001ee48  mov     [rbp+var_28], rax
0x18001ee4c  cmp     rcx, rdi
0x18001ee4f  jz      short loc_18001EE6F
0x18001ee51  test    byte ptr [rcx+1Ch], 40h
0x18001ee55  jz      short loc_18001EE6F
0x18001ee57  mov     r9, [r14]
0x18001ee5a  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18001ee61  mov     rcx, [rcx+10h]
0x18001ee65  mov     edx, 6Ah ; 'j'
0x18001ee6a  call    WPP_SF_S
0x18001ee6f  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x18001ee73  lea     r9, [rbp+var_30]; struct IXMLDOMNode **
0x18001ee77  xorps   xmm0, xmm0
0x18001ee7a  mov     [rbp+var_30], r12
0x18001ee7e  xor     eax, eax
0x18001ee80  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18001ee84  movups  xmmword ptr [rbp+pbstr], xmm0
0x18001ee88  mov     [rbp+var_10], rax
0x18001ee8c  mov     r15, r12
0x18001ee8f  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x18001ee94  mov     edi, eax
0x18001ee96  test    eax, eax
0x18001ee98  js      loc_18001EFF5
0x18001ee9e  mov     rbx, [rbp+var_30]
0x18001eea2  test    eax, eax
0x18001eea4  jnz     short loc_18001EEB4
0x18001eea6  lea     r8, [rbp+pbstr]; struct tagVARIANT *
0x18001eeaa  mov     rcx, rbx; struct IXMLDOMNode *
0x18001eead  call    ?HrGetTypedValueFromElement@@YAJPEAUIXMLDOMNode@@QEBGPEAUtagVARIANT@@@Z; HrGetTypedValueFromElement(IXMLDOMNode *,ushort const * const,tagVARIANT *)
0x18001eeb2  mov     edi, eax
0x18001eeb4  test    rbx, rbx
0x18001eeb7  jz      short loc_18001EEC8
0x18001eeb9  mov     rax, [rbx]
0x18001eebc  mov     rcx, rbx
0x18001eebf  mov     rax, [rax+10h]
0x18001eec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eec8  mov     ebx, edi
0x18001eeca  test    edi, edi
0x18001eecc  js      loc_18001EFF7
0x18001eed2  jnz     loc_18001F080
0x18001eed8  mov     r15, [rbp+pbstr+8]
0x18001eedc  mov     rcx, r15; pbstr
0x18001eedf  call    cs:__imp_SysStringLen
0x18001eee6  nop     dword ptr [rax+rax+00h]
0x18001eeeb  test    eax, eax
0x18001eeed  jz      short loc_18001EF25
0x18001eeef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eef6  lea     rdi, WPP_GLOBAL_Control
0x18001eefd  cmp     rcx, rdi
0x18001ef00  jnz     short loc_18001EF61
0x18001ef02  mov     rdx, r15; unsigned __int16 *
0x18001ef05  mov     rcx, r13; this
0x18001ef08  call    ?LookupVariableByName@CUPnPAutomationProxy@@AEAAPEAUtagUPNP_STATE_VARIABLE@@PEBG@Z; CUPnPAutomationProxy::LookupVariableByName(ushort const *)
0x18001ef0d  test    rax, rax
0x18001ef10  jz      short loc_18001EF89
0x18001ef12  mov     [r14+8], rax
0x18001ef16  mov     rcx, r15; bstrString
0x18001ef19  call    cs:__imp_SysFreeString
0x18001ef20  nop     dword ptr [rax+rax+00h]
0x18001ef25  lea     r15, aName; "name"
0x18001ef2c  mov     rcx, [rbp+arg_18]
0x18001ef30  mov     rax, [rcx]
0x18001ef33  mov     rax, [rax+10h]
0x18001ef37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef43  lea     r14, WPP_GLOBAL_Control
0x18001ef4a  mov     rdi, [rbp+arg_10]
0x18001ef4e  inc     esi
0x18001ef50  test    ebx, ebx
0x18001ef52  js      loc_18001F40C
0x18001ef58  mov     r9, [rbp+arg_8]
0x18001ef5c  jmp     loc_18001ED90
0x18001ef61  test    byte ptr [rcx+1Ch], 40h
0x18001ef65  jz      short loc_18001EF02
0x18001ef67  mov     r9, [r14]
0x18001ef6a  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18001ef71  mov     rcx, [rcx+10h]
0x18001ef75  mov     edx, 6Bh ; 'k'
0x18001ef7a  mov     [rsp+60h+var_40], r15
0x18001ef7f  call    WPP_SF_SS
0x18001ef84  jmp     loc_18001EF02
0x18001ef89  mov     [r14+8], r12
0x18001ef8d  mov     ebx, 80070057h
0x18001ef92  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef99  cmp     rcx, rdi
0x18001ef9c  jz      loc_18001EF16
0x18001efa2  test    byte ptr [rcx+1Ch], 1
0x18001efa6  jz      loc_18001EF16
0x18001efac  mov     rcx, [rcx+10h]
0x18001efb0  lea     r9, aCupnpautomatio_37; "CUPnPAutomationProxy::HrInitializeArgum"...
0x18001efb7  mov     edx, 6Ch ; 'l'
0x18001efbc  mov     dword ptr [rsp+60h+var_40], ebx
0x18001efc0  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18001efc7  call    WPP_SF_sd
0x18001efcc  jmp     loc_18001EF16
0x18001efd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efd8  cmp     rcx, r14
0x18001efdb  jz      loc_18001EF4E
0x18001efe1  test    byte ptr [rcx+1Ch], 1
0x18001efe5  jz      loc_18001EF4E
0x18001efeb  mov     edx, 6Fh ; 'o'
0x18001eff0  jmp     loc_18001F3EA
0x18001eff5  mov     ebx, eax
0x18001eff7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001effe  lea     rax, WPP_GLOBAL_Control
0x18001f005  cmp     rcx, rax
0x18001f008  jz      short loc_18001F03E
0x18001f00a  test    byte ptr [rcx+1Ch], 1
0x18001f00e  jz      short loc_18001F036
0x18001f010  mov     rcx, [rcx+10h]
0x18001f014  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18001f01b  mov     edx, 10h
0x18001f020  mov     r9d, edi
0x18001f023  call    WPP_SF_d
0x18001f028  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f02f  lea     rax, WPP_GLOBAL_Control
0x18001f036  test    edi, edi
0x18001f038  js      loc_18001F56E
0x18001f03e  mov     ebx, edi
0x18001f040  test    edi, edi
0x18001f042  jz      loc_18001EEDC
0x18001f048  cmp     rcx, rax
0x18001f04b  jz      loc_18001EF25
0x18001f051  test    byte ptr [rcx+1Ch], 1
0x18001f055  jz      loc_18001EF25
0x18001f05b  mov     rcx, [rcx+10h]
0x18001f05f  lea     r9, aCupnpautomatio_39; "CUPnPAutomationProxy::HrInitializeArgum"...
0x18001f066  mov     edx, 6Dh ; 'm'
0x18001f06b  mov     dword ptr [rsp+60h+var_40], edi
0x18001f06f  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18001f076  call    WPP_SF_sd
0x18001f07b  jmp     loc_18001EF25
0x18001f080  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f087  lea     rax, WPP_GLOBAL_Control
0x18001f08e  jmp     short loc_18001F03E
0x18001f090  xor     esi, esi
0x18001f092  mov     r15d, esi
0x18001f095  test    ebx, ebx
0x18001f097  js      loc_18001F40C
0x18001f09d  nop     dword ptr [rax]
0x18001f0a0  cmp     r15d, [rdi+18h]
0x18001f0a4  jnb     loc_18001F433
0x18001f0aa  mov     rcx, [r9]
0x18001f0ad  lea     r8, [rbp+arg_18]
0x18001f0b1  mov     edx, [rdi+0Ch]
0x18001f0b4  add     edx, r15d
0x18001f0b7  mov     [rbp+arg_18], rsi
0x18001f0bb  mov     rax, [rcx+38h]
0x18001f0bf  mov     rcx, r9
0x18001f0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0c7  mov     ebx, eax
0x18001f0c9  test    eax, eax
0x18001f0cb  js      loc_18001F6DB
0x18001f0d1  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x18001f0d5  lea     rax, aName; "name"
0x18001f0dc  mov     [rbp+var_28], rax
0x18001f0e0  lea     r9, [rbp+var_30]; struct IXMLDOMNode **
0x18001f0e4  xorps   xmm0, xmm0
0x18001f0e7  mov     r12d, r15d
0x18001f0ea  xor     eax, eax
0x18001f0ec  shl     r12, 4
0x18001f0f0  add     r12, [rdi+20h]
0x18001f0f4  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18001f0f8  movups  xmmword ptr [rbp+pbstr], xmm0
0x18001f0fc  mov     [rbp+var_10], rax
0x18001f100  mov     [rbp+var_30], rsi
0x18001f104  mov     [r12], rsi
0x18001f108  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x18001f10d  mov     ebx, eax
0x18001f10f  test    eax, eax
0x18001f111  js      loc_18001F5B0
0x18001f117  mov     rdi, [rbp+var_30]
0x18001f11b  jnz     short loc_18001F12B
0x18001f11d  lea     r8, [rbp+pbstr]; struct tagVARIANT *
0x18001f121  mov     rcx, rdi; struct IXMLDOMNode *
0x18001f124  call    ?HrGetTypedValueFromElement@@YAJPEAUIXMLDOMNode@@QEBGPEAUtagVARIANT@@@Z; HrGetTypedValueFromElement(IXMLDOMNode *,ushort const * const,tagVARIANT *)
0x18001f129  mov     ebx, eax
0x18001f12b  test    rdi, rdi
0x18001f12e  jz      short loc_18001F13F
0x18001f130  mov     rax, [rdi]
0x18001f133  mov     rcx, rdi
0x18001f136  mov     rax, [rax+10h]
0x18001f13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f13f  test    ebx, ebx
0x18001f141  js      loc_18001F5AC
0x18001f147  jnz     short loc_18001F151
0x18001f149  mov     rax, [rbp+pbstr+8]
0x18001f14d  mov     [r12], rax
0x18001f151  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f158  lea     rax, aRelatedstateva; "relatedStateVariable"
0x18001f15f  mov     [rbp+var_28], rax
0x18001f163  cmp     rcx, r14
0x18001f166  jnz     loc_18001F5EE
0x18001f16c  mov     rcx, [rbp+arg_18]; struct IXMLDOMNode *
0x18001f170  lea     r9, [rbp+var_30]; struct IXMLDOMNode **
0x18001f174  xorps   xmm0, xmm0
0x18001f177  mov     [rbp+var_30], rsi
0x18001f17b  xor     eax, eax
0x18001f17d  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18001f181  movups  xmmword ptr [rbp+pbstr], xmm0
0x18001f185  mov     [rbp+var_10], rax
0x18001f189  mov     r14, rsi
0x18001f18c  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x18001f191  mov     ebx, eax
0x18001f193  test    eax, eax
0x18001f195  js      loc_18001F616
0x18001f19b  mov     rdi, [rbp+var_30]
0x18001f19f  jnz     short loc_18001F1AF
0x18001f1a1  lea     r8, [rbp+pbstr]; struct tagVARIANT *
0x18001f1a5  mov     rcx, rdi; struct IXMLDOMNode *
0x18001f1a8  call    ?HrGetTypedValueFromElement@@YAJPEAUIXMLDOMNode@@QEBGPEAUtagVARIANT@@@Z; HrGetTypedValueFromElement(IXMLDOMNode *,ushort const * const,tagVARIANT *)
0x18001f1ad  mov     ebx, eax
0x18001f1af  test    rdi, rdi
0x18001f1b2  jz      short loc_18001F1C3
0x18001f1b4  mov     rax, [rdi]
0x18001f1b7  mov     rcx, rdi
0x18001f1ba  mov     rax, [rax+10h]
0x18001f1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1c3  test    ebx, ebx
0x18001f1c5  js      loc_18001F616
0x18001f1cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1d2  lea     rdi, WPP_GLOBAL_Control
0x18001f1d9  jnz     short loc_18001F1DF
0x18001f1db  mov     r14, [rbp+pbstr+8]
0x18001f1df  cmp     rcx, rdi
0x18001f1e2  jz      short loc_18001F1EE
0x18001f1e4  test    byte ptr [rcx+1Ch], 40h
0x18001f1e8  jnz     loc_18001F65B
0x18001f1ee  xor     ebx, ebx
  ... truncated ...
```
