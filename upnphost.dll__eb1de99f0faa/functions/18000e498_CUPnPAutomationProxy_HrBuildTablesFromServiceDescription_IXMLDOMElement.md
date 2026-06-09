# CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(IXMLDOMElement *)

- ea: `0x18000e498`
- end: `0x18000e7ae`
- name: `?HrBuildTablesFromServiceDescription@CUPnPAutomationProxy@@AEAAJPEAUIXMLDOMElement@@@Z`
- size: `790`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, struct IXMLDOMElement *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000ee34`

## callees

- `0x18000d16c`
- `0x18000d5e4`
- `0x18000db4c`
- `0x18000e498`
- `0x18000e9cc`
- `0x180039a84`
- `0x180055010`

## string_xrefs

- `0x18000e4ee`: `serviceStateTable`
- `0x18000e5ca`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to get <stateVariable> elements`
- `0x18000e58a`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to build variable table`
- `0x18000e742`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to get <serviceStateTable> element`
- `0x18000e6e2`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to get <action> elements`
- `0x18000e6a2`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to build action table`
- `0x18000e783`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Exiting`
- `0x18000e722`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to get <actionList> element`

## pseudocode

```c
__int64 __fastcall CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(
        CUPnPAutomationProxy *this,
        struct IXMLDOMElement *a2)
{
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  int v4; // ebx
  unsigned int v5; // r8d
  int NestedChildElement; // eax
  struct IXMLDOMNode *v7; // rdi
  int v8; // eax
  int v9; // eax
  unsigned int v10; // r8d
  struct IXMLDOMNode *v11; // rdi
  int v12; // eax
  int v13; // eax
  STRSAFE_PCNZWCH v14; // rcx
  int v15; // edx
  const char *v16; // r9
  struct IXMLDOMNode *v18; // [rsp+68h] [rbp+38h] BYREF
  struct IXMLDOMNodeList *v19; // [rsp+70h] [rbp+40h] BYREF
  struct IXMLDOMNode *v20; // [rsp+78h] [rbp+48h] BYREF

  lpVtbl = a2->lpVtbl;
  v18 = 0;
  v4 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, GUID *, struct IXMLDOMNode **))lpVtbl->QueryInterface)(
         a2,
         &IID_IXMLDOMNode,
         &v18);
  if ( v4 >= 0 )
  {
    v19 = (struct IXMLDOMNodeList *)L"serviceStateTable";
    v20 = 0;
    NestedChildElement = HrGetNestedChildElement(v18, (const unsigned __int16 *const *)&v19, v5, &v20);
    v4 = NestedChildElement;
    if ( NestedChildElement < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_38;
      v15 = 65;
      v16 = "CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to get <serviceStateTable> element";
    }
    else
    {
      v7 = v20;
      v19 = 0;
      v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNodeList **))v20->lpVtbl->get_childNodes)(
             v20,
             &v19);
      v4 = v8;
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            64,
            (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
            (unsigned int)"CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to get <stateVariable> elements",
            v8);
      }
      else
      {
        v9 = CUPnPAutomationProxy::HrBuildVariableTable(this, v19);
        v4 = v9;
        if ( v9 < 0 )
        {
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              63,
              (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
              (unsigned int)"CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to build variable table",
              v9);
        }
        else if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids);
        }
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v19->lpVtbl->Release)(v19);
      }
      ((void (__fastcall *)(struct IXMLDOMNode *))v7->lpVtbl->Release)(v7);
      if ( v4 < 0 )
        goto LABEL_38;
      v19 = (struct IXMLDOMNodeList *)L"actionList";
      v20 = 0;
      NestedChildElement = HrGetNestedChildElement(v18, (const unsigned __int16 *const *)&v19, v10, &v20);
      v4 = NestedChildElement;
      if ( NestedChildElement >= 0 && NestedChildElement != 1 )
      {
        v11 = v20;
        v19 = 0;
        v12 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct IXMLDOMNodeList **))v20->lpVtbl->get_childNodes)(
                v20,
                &v19);
        v4 = v12;
        if ( v12 < 0 )
        {
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              68,
              (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
              (unsigned int)"CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to get <action> elements",
              v12);
        }
        else
        {
          v13 = CUPnPAutomationProxy::HrBuildActionTable(this, v19);
          v4 = v13;
          if ( v13 < 0 )
          {
            if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                67,
                (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                (unsigned int)"CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to build action table",
                v13);
          }
          else if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids);
          }
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v19->lpVtbl->Release)(v19);
        }
        ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
        goto LABEL_38;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_38:
        ((void (__fastcall *)(struct IXMLDOMNode *))v18->lpVtbl->Release)(v18);
        goto LABEL_39;
      }
      v15 = 69;
      v16 = "CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to get <actionList> element";
    }
    WPP_SF_sd(
      *((_QWORD *)v14 + 2),
      v15,
      (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
      (_DWORD)v16,
      NestedChildElement);
    goto LABEL_38;
  }
LABEL_39:
  if ( v4 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
      (unsigned int)"CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Exiting",
      v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e498  mov     [rsp-28h+arg_0], rbx
0x18000e49d  push    rbp
0x18000e49e  push    rsi
0x18000e49f  push    rdi
0x18000e4a0  push    r13
0x18000e4a2  push    r14
0x18000e4a4  mov     rbp, rsp
0x18000e4a7  sub     rsp, 30h
0x18000e4ab  mov     rax, [rdx]
0x18000e4ae  lea     r8, [rbp+arg_8]
0x18000e4b2  mov     r9, rdx
0x18000e4b5  mov     [rbp+arg_8], 0
0x18000e4bd  mov     rsi, rcx
0x18000e4c0  lea     rdx, IID_IXMLDOMNode
0x18000e4c7  mov     rcx, r9
0x18000e4ca  mov     rax, [rax]
0x18000e4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4d2  lea     r14, WPP_GLOBAL_Control
0x18000e4d9  mov     ebx, eax
0x18000e4db  lea     r13, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18000e4e2  test    eax, eax
0x18000e4e4  js      loc_18000E769
0x18000e4ea  mov     rcx, [rbp+arg_8]; struct IXMLDOMNode *
0x18000e4ee  lea     rax, aServicestateta_2; "serviceStateTable"
0x18000e4f5  lea     r9, [rbp+arg_18]; struct IXMLDOMNode **
0x18000e4f9  mov     [rbp+arg_10], rax
0x18000e4fd  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18000e501  mov     [rbp+arg_18], 0
0x18000e509  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x18000e50e  mov     ebx, eax
0x18000e510  test    eax, eax
0x18000e512  js      loc_18000E72B
0x18000e518  mov     rdi, [rbp+arg_18]
0x18000e51c  lea     rdx, [rbp+arg_10]
0x18000e520  mov     [rbp+arg_10], 0
0x18000e528  mov     rcx, rdi
0x18000e52b  mov     rax, [rdi]
0x18000e52e  mov     rax, [rax+60h]
0x18000e532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e537  mov     ebx, eax
0x18000e539  test    eax, eax
0x18000e53b  js      short loc_18000E5B4
0x18000e53d  mov     rdx, [rbp+arg_10]; struct IXMLDOMNodeList *
0x18000e541  mov     rcx, rsi; this
0x18000e544  call    ?HrBuildVariableTable@CUPnPAutomationProxy@@AEAAJPEAUIXMLDOMNodeList@@@Z; CUPnPAutomationProxy::HrBuildVariableTable(IXMLDOMNodeList *)
0x18000e549  mov     ebx, eax
0x18000e54b  test    eax, eax
0x18000e54d  js      short loc_18000E574
0x18000e54f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e556  cmp     rcx, r14
0x18000e559  jz      short loc_18000E5A2
0x18000e55b  test    byte ptr [rcx+1Ch], 40h
0x18000e55f  jz      short loc_18000E5A2
0x18000e561  mov     rcx, [rcx+10h]
0x18000e565  mov     edx, 3Eh ; '>'
0x18000e56a  mov     r8, r13
0x18000e56d  call    WPP_SF_
0x18000e572  jmp     short loc_18000E5A2
0x18000e574  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e57b  cmp     rcx, r14
0x18000e57e  jz      short loc_18000E5A2
0x18000e580  test    byte ptr [rcx+1Ch], 1
0x18000e584  jz      short loc_18000E5A2
0x18000e586  mov     rcx, [rcx+10h]
0x18000e58a  lea     r9, aCupnpautomatio_49; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x18000e591  mov     edx, 3Fh ; '?'
0x18000e596  mov     [rsp+30h+var_10], eax
0x18000e59a  mov     r8, r13
0x18000e59d  call    WPP_SF_sd
0x18000e5a2  mov     rcx, [rbp+arg_10]
0x18000e5a6  mov     rax, [rcx]
0x18000e5a9  mov     rax, [rax+10h]
0x18000e5ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5b2  jmp     short loc_18000E5E2
0x18000e5b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5bb  cmp     rcx, r14
0x18000e5be  jz      short loc_18000E5E2
0x18000e5c0  test    byte ptr [rcx+1Ch], 1
0x18000e5c4  jz      short loc_18000E5E2
0x18000e5c6  mov     rcx, [rcx+10h]
0x18000e5ca  lea     r9, aCupnpautomatio_81; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x18000e5d1  mov     edx, 40h ; '@'
0x18000e5d6  mov     [rsp+30h+var_10], eax
0x18000e5da  mov     r8, r13
0x18000e5dd  call    WPP_SF_sd
0x18000e5e2  mov     rax, [rdi]
0x18000e5e5  mov     rcx, rdi
0x18000e5e8  mov     rax, [rax+10h]
0x18000e5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5f1  test    ebx, ebx
0x18000e5f3  js      loc_18000E759
0x18000e5f9  mov     rcx, [rbp+arg_8]; struct IXMLDOMNode *
0x18000e5fd  lea     rax, aActionlist; "actionList"
0x18000e604  lea     r9, [rbp+arg_18]; struct IXMLDOMNode **
0x18000e608  mov     [rbp+arg_10], rax
0x18000e60c  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18000e610  mov     [rbp+arg_18], 0
0x18000e618  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x18000e61d  mov     ebx, eax
0x18000e61f  test    eax, eax
0x18000e621  js      loc_18000E70B
0x18000e627  cmp     eax, 1
0x18000e62a  jz      loc_18000E70B
0x18000e630  mov     rdi, [rbp+arg_18]
0x18000e634  lea     rdx, [rbp+arg_10]
0x18000e638  mov     [rbp+arg_10], 0
0x18000e640  mov     rcx, rdi
0x18000e643  mov     rax, [rdi]
0x18000e646  mov     rax, [rax+60h]
0x18000e64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e64f  mov     ebx, eax
0x18000e651  test    eax, eax
0x18000e653  js      short loc_18000E6CC
0x18000e655  mov     rdx, [rbp+arg_10]; struct IXMLDOMNodeList *
0x18000e659  mov     rcx, rsi; this
0x18000e65c  call    ?HrBuildActionTable@CUPnPAutomationProxy@@AEAAJPEAUIXMLDOMNodeList@@@Z; CUPnPAutomationProxy::HrBuildActionTable(IXMLDOMNodeList *)
0x18000e661  mov     ebx, eax
0x18000e663  test    eax, eax
0x18000e665  js      short loc_18000E68C
0x18000e667  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e66e  cmp     rcx, r14
0x18000e671  jz      short loc_18000E6BA
0x18000e673  test    byte ptr [rcx+1Ch], 40h
0x18000e677  jz      short loc_18000E6BA
0x18000e679  mov     rcx, [rcx+10h]
0x18000e67d  mov     edx, 42h ; 'B'
0x18000e682  mov     r8, r13
0x18000e685  call    WPP_SF_
0x18000e68a  jmp     short loc_18000E6BA
0x18000e68c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e693  cmp     rcx, r14
0x18000e696  jz      short loc_18000E6BA
0x18000e698  test    byte ptr [rcx+1Ch], 1
0x18000e69c  jz      short loc_18000E6BA
0x18000e69e  mov     rcx, [rcx+10h]
0x18000e6a2  lea     r9, aCupnpautomatio_73; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x18000e6a9  mov     edx, 43h ; 'C'
0x18000e6ae  mov     [rsp+30h+var_10], eax
0x18000e6b2  mov     r8, r13
0x18000e6b5  call    WPP_SF_sd
0x18000e6ba  mov     rcx, [rbp+arg_10]
0x18000e6be  mov     rax, [rcx]
0x18000e6c1  mov     rax, [rax+10h]
0x18000e6c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ca  jmp     short loc_18000E6FA
0x18000e6cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6d3  cmp     rcx, r14
0x18000e6d6  jz      short loc_18000E6FA
0x18000e6d8  test    byte ptr [rcx+1Ch], 1
0x18000e6dc  jz      short loc_18000E6FA
0x18000e6de  mov     rcx, [rcx+10h]
0x18000e6e2  lea     r9, aCupnpautomatio_65; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x18000e6e9  mov     edx, 44h ; 'D'
0x18000e6ee  mov     [rsp+30h+var_10], eax
0x18000e6f2  mov     r8, r13
0x18000e6f5  call    WPP_SF_sd
0x18000e6fa  mov     rax, [rdi]
0x18000e6fd  mov     rcx, rdi
0x18000e700  mov     rax, [rax+10h]
0x18000e704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e709  jmp     short loc_18000E759
0x18000e70b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e712  cmp     rcx, r14
0x18000e715  jz      short loc_18000E759
0x18000e717  test    byte ptr [rcx+1Ch], 1
0x18000e71b  jz      short loc_18000E759
0x18000e71d  mov     edx, 45h ; 'E'
0x18000e722  lea     r9, aCupnpautomatio_5; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x18000e729  jmp     short loc_18000E749
0x18000e72b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e732  cmp     rcx, r14
0x18000e735  jz      short loc_18000E759
0x18000e737  test    byte ptr [rcx+1Ch], 1
0x18000e73b  jz      short loc_18000E759
0x18000e73d  mov     edx, 41h ; 'A'
0x18000e742  lea     r9, aCupnpautomatio_67; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x18000e749  mov     rcx, [rcx+10h]
0x18000e74d  mov     r8, r13
0x18000e750  mov     [rsp+30h+var_10], eax
0x18000e754  call    WPP_SF_sd
0x18000e759  mov     rcx, [rbp+arg_8]
0x18000e75d  mov     rax, [rcx]
0x18000e760  mov     rax, [rax+10h]
0x18000e764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e769  test    ebx, ebx
0x18000e76b  jz      short loc_18000E79B
0x18000e76d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e774  cmp     rcx, r14
0x18000e777  jz      short loc_18000E79B
0x18000e779  test    byte ptr [rcx+1Ch], 1
0x18000e77d  jz      short loc_18000E79B
0x18000e77f  mov     rcx, [rcx+10h]
0x18000e783  lea     r9, aCupnpautomatio_28; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x18000e78a  mov     edx, 46h ; 'F'
0x18000e78f  mov     [rsp+30h+var_10], ebx
0x18000e793  mov     r8, r13
0x18000e796  call    WPP_SF_sd
0x18000e79b  mov     eax, ebx
0x18000e79d  mov     rbx, [rsp+30h+arg_0]
0x18000e7a2  add     rsp, 30h
0x18000e7a6  pop     r14
0x18000e7a8  pop     r13
0x18000e7aa  pop     rdi
0x18000e7ab  pop     rsi
0x18000e7ac  pop     rbp
0x18000e7ad  retn
```
