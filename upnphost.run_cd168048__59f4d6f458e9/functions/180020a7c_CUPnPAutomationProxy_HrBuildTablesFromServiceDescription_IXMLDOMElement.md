# CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(IXMLDOMElement *)

- ea: `0x180020a7c`
- end: `0x180020d93`
- name: `?HrBuildTablesFromServiceDescription@CUPnPAutomationProxy@@AEAAJPEAUIXMLDOMElement@@@Z`
- size: `791`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, struct IXMLDOMElement *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180021444`

## callees

- `0x18001f6f8`
- `0x18001fb78`
- `0x1800200f4`
- `0x180020a7c`
- `0x180020fd4`
- `0x18003c018`
- `0x180059010`

## string_xrefs

- `0x180020ad2`: `serviceStateTable`
- `0x180020bae`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to get <stateVariable> elements`
- `0x180020b6e`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to build variable table`
- `0x180020d26`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to get <serviceStateTable> element`
- `0x180020cc6`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to get <action> elements`
- `0x180020c86`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to build action table`
- `0x180020d67`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Exiting`
- `0x180020d06`: `CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(): Failed to get <actionList> element`

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
0x180020a7c  mov     [rsp-28h+arg_0], rbx
0x180020a81  push    rbp
0x180020a82  push    rsi
0x180020a83  push    rdi
0x180020a84  push    r13
0x180020a86  push    r14
0x180020a88  mov     rbp, rsp
0x180020a8b  sub     rsp, 30h
0x180020a8f  mov     rax, [rdx]
0x180020a92  lea     r8, [rbp+arg_8]
0x180020a96  mov     r9, rdx
0x180020a99  mov     [rbp+arg_8], 0
0x180020aa1  mov     rsi, rcx
0x180020aa4  lea     rdx, IID_IXMLDOMNode
0x180020aab  mov     rcx, r9
0x180020aae  mov     rax, [rax]
0x180020ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ab6  lea     r14, WPP_GLOBAL_Control
0x180020abd  mov     ebx, eax
0x180020abf  lea     r13, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180020ac6  test    eax, eax
0x180020ac8  js      loc_180020D4D
0x180020ace  mov     rcx, [rbp+arg_8]; struct IXMLDOMNode *
0x180020ad2  lea     rax, aServicestateta_2; "serviceStateTable"
0x180020ad9  lea     r9, [rbp+arg_18]; struct IXMLDOMNode **
0x180020add  mov     [rbp+arg_10], rax
0x180020ae1  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x180020ae5  mov     [rbp+arg_18], 0
0x180020aed  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x180020af2  mov     ebx, eax
0x180020af4  test    eax, eax
0x180020af6  js      loc_180020D0F
0x180020afc  mov     rdi, [rbp+arg_18]
0x180020b00  lea     rdx, [rbp+arg_10]
0x180020b04  mov     [rbp+arg_10], 0
0x180020b0c  mov     rcx, rdi
0x180020b0f  mov     rax, [rdi]
0x180020b12  mov     rax, [rax+60h]
0x180020b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b1b  mov     ebx, eax
0x180020b1d  test    eax, eax
0x180020b1f  js      short loc_180020B98
0x180020b21  mov     rdx, [rbp+arg_10]; struct IXMLDOMNodeList *
0x180020b25  mov     rcx, rsi; this
0x180020b28  call    ?HrBuildVariableTable@CUPnPAutomationProxy@@AEAAJPEAUIXMLDOMNodeList@@@Z; CUPnPAutomationProxy::HrBuildVariableTable(IXMLDOMNodeList *)
0x180020b2d  mov     ebx, eax
0x180020b2f  test    eax, eax
0x180020b31  js      short loc_180020B58
0x180020b33  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b3a  cmp     rcx, r14
0x180020b3d  jz      short loc_180020B86
0x180020b3f  test    byte ptr [rcx+1Ch], 40h
0x180020b43  jz      short loc_180020B86
0x180020b45  mov     rcx, [rcx+10h]
0x180020b49  mov     edx, 3Eh ; '>'
0x180020b4e  mov     r8, r13
0x180020b51  call    WPP_SF_
0x180020b56  jmp     short loc_180020B86
0x180020b58  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b5f  cmp     rcx, r14
0x180020b62  jz      short loc_180020B86
0x180020b64  test    byte ptr [rcx+1Ch], 1
0x180020b68  jz      short loc_180020B86
0x180020b6a  mov     rcx, [rcx+10h]
0x180020b6e  lea     r9, aCupnpautomatio_49; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x180020b75  mov     edx, 3Fh ; '?'
0x180020b7a  mov     [rsp+30h+var_10], eax
0x180020b7e  mov     r8, r13
0x180020b81  call    WPP_SF_sd
0x180020b86  mov     rcx, [rbp+arg_10]
0x180020b8a  mov     rax, [rcx]
0x180020b8d  mov     rax, [rax+10h]
0x180020b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b96  jmp     short loc_180020BC6
0x180020b98  mov     rcx, cs:WPP_GLOBAL_Control
0x180020b9f  cmp     rcx, r14
0x180020ba2  jz      short loc_180020BC6
0x180020ba4  test    byte ptr [rcx+1Ch], 1
0x180020ba8  jz      short loc_180020BC6
0x180020baa  mov     rcx, [rcx+10h]
0x180020bae  lea     r9, aCupnpautomatio_81; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x180020bb5  mov     edx, 40h ; '@'
0x180020bba  mov     [rsp+30h+var_10], eax
0x180020bbe  mov     r8, r13
0x180020bc1  call    WPP_SF_sd
0x180020bc6  mov     rax, [rdi]
0x180020bc9  mov     rcx, rdi
0x180020bcc  mov     rax, [rax+10h]
0x180020bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bd5  test    ebx, ebx
0x180020bd7  js      loc_180020D3D
0x180020bdd  mov     rcx, [rbp+arg_8]; struct IXMLDOMNode *
0x180020be1  lea     rax, aActionlist; "actionList"
0x180020be8  lea     r9, [rbp+arg_18]; struct IXMLDOMNode **
0x180020bec  mov     [rbp+arg_10], rax
0x180020bf0  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x180020bf4  mov     [rbp+arg_18], 0
0x180020bfc  call    ?HrGetNestedChildElement@@YAJPEAUIXMLDOMNode@@PEBQEBGKPEAPEAU1@@Z; HrGetNestedChildElement(IXMLDOMNode *,ushort const * const *,ulong,IXMLDOMNode * *)
0x180020c01  mov     ebx, eax
0x180020c03  test    eax, eax
0x180020c05  js      loc_180020CEF
0x180020c0b  cmp     eax, 1
0x180020c0e  jz      loc_180020CEF
0x180020c14  mov     rdi, [rbp+arg_18]
0x180020c18  lea     rdx, [rbp+arg_10]
0x180020c1c  mov     [rbp+arg_10], 0
0x180020c24  mov     rcx, rdi
0x180020c27  mov     rax, [rdi]
0x180020c2a  mov     rax, [rax+60h]
0x180020c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c33  mov     ebx, eax
0x180020c35  test    eax, eax
0x180020c37  js      short loc_180020CB0
0x180020c39  mov     rdx, [rbp+arg_10]; struct IXMLDOMNodeList *
0x180020c3d  mov     rcx, rsi; this
0x180020c40  call    ?HrBuildActionTable@CUPnPAutomationProxy@@AEAAJPEAUIXMLDOMNodeList@@@Z; CUPnPAutomationProxy::HrBuildActionTable(IXMLDOMNodeList *)
0x180020c45  mov     ebx, eax
0x180020c47  test    eax, eax
0x180020c49  js      short loc_180020C70
0x180020c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c52  cmp     rcx, r14
0x180020c55  jz      short loc_180020C9E
0x180020c57  test    byte ptr [rcx+1Ch], 40h
0x180020c5b  jz      short loc_180020C9E
0x180020c5d  mov     rcx, [rcx+10h]
0x180020c61  mov     edx, 42h ; 'B'
0x180020c66  mov     r8, r13
0x180020c69  call    WPP_SF_
0x180020c6e  jmp     short loc_180020C9E
0x180020c70  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c77  cmp     rcx, r14
0x180020c7a  jz      short loc_180020C9E
0x180020c7c  test    byte ptr [rcx+1Ch], 1
0x180020c80  jz      short loc_180020C9E
0x180020c82  mov     rcx, [rcx+10h]
0x180020c86  lea     r9, aCupnpautomatio_73; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x180020c8d  mov     edx, 43h ; 'C'
0x180020c92  mov     [rsp+30h+var_10], eax
0x180020c96  mov     r8, r13
0x180020c99  call    WPP_SF_sd
0x180020c9e  mov     rcx, [rbp+arg_10]
0x180020ca2  mov     rax, [rcx]
0x180020ca5  mov     rax, [rax+10h]
0x180020ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cae  jmp     short loc_180020CDE
0x180020cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cb7  cmp     rcx, r14
0x180020cba  jz      short loc_180020CDE
0x180020cbc  test    byte ptr [rcx+1Ch], 1
0x180020cc0  jz      short loc_180020CDE
0x180020cc2  mov     rcx, [rcx+10h]
0x180020cc6  lea     r9, aCupnpautomatio_65; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x180020ccd  mov     edx, 44h ; 'D'
0x180020cd2  mov     [rsp+30h+var_10], eax
0x180020cd6  mov     r8, r13
0x180020cd9  call    WPP_SF_sd
0x180020cde  mov     rax, [rdi]
0x180020ce1  mov     rcx, rdi
0x180020ce4  mov     rax, [rax+10h]
0x180020ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ced  jmp     short loc_180020D3D
0x180020cef  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cf6  cmp     rcx, r14
0x180020cf9  jz      short loc_180020D3D
0x180020cfb  test    byte ptr [rcx+1Ch], 1
0x180020cff  jz      short loc_180020D3D
0x180020d01  mov     edx, 45h ; 'E'
0x180020d06  lea     r9, aCupnpautomatio_5; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x180020d0d  jmp     short loc_180020D2D
0x180020d0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d16  cmp     rcx, r14
0x180020d19  jz      short loc_180020D3D
0x180020d1b  test    byte ptr [rcx+1Ch], 1
0x180020d1f  jz      short loc_180020D3D
0x180020d21  mov     edx, 41h ; 'A'
0x180020d26  lea     r9, aCupnpautomatio_67; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x180020d2d  mov     rcx, [rcx+10h]
0x180020d31  mov     r8, r13
0x180020d34  mov     [rsp+30h+var_10], eax
0x180020d38  call    WPP_SF_sd
0x180020d3d  mov     rcx, [rbp+arg_8]
0x180020d41  mov     rax, [rcx]
0x180020d44  mov     rax, [rax+10h]
0x180020d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d4d  test    ebx, ebx
0x180020d4f  jz      short loc_180020D7F
0x180020d51  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d58  cmp     rcx, r14
0x180020d5b  jz      short loc_180020D7F
0x180020d5d  test    byte ptr [rcx+1Ch], 1
0x180020d61  jz      short loc_180020D7F
0x180020d63  mov     rcx, [rcx+10h]
0x180020d67  lea     r9, aCupnpautomatio_28; "CUPnPAutomationProxy::HrBuildTablesFrom"...
0x180020d6e  mov     edx, 46h ; 'F'
0x180020d73  mov     [rsp+30h+var_10], ebx
0x180020d77  mov     r8, r13
0x180020d7a  call    WPP_SF_sd
0x180020d7f  mov     eax, ebx
0x180020d81  mov     rbx, [rsp+30h+arg_0]
0x180020d86  add     rsp, 30h
0x180020d8a  pop     r14
0x180020d8c  pop     r13
0x180020d8e  pop     rdi
0x180020d8f  pop     rsi
0x180020d90  pop     rbp
0x180020d91  retn
```
