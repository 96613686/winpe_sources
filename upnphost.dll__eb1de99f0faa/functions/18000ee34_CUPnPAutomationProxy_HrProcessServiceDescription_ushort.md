# CUPnPAutomationProxy::HrProcessServiceDescription(ushort *)

- ea: `0x18000ee34`
- end: `0x18000f109`
- name: `?HrProcessServiceDescription@CUPnPAutomationProxy@@AEAAJPEAG@Z`
- size: `725`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, OLECHAR *psz)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180035ee0`

## callees

- `0x18000db4c`
- `0x18000e498`
- `0x18000ee34`
- `0x180011bfc`
- `0x180011c90`
- `0x180038ce4`
- `0x180039388`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000eea6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000eea6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000eeb9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000eeb9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f049`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f049`

## string_xrefs

- `0x18000efa6`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Could not build tables from service description`
- `0x18000efe7`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Could not get document element`
- `0x18000f02f`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Could not set async property`
- `0x18000f00f`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Failed to load XML`
- `0x18000f0b0`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Could not create DOM document`
- `0x18000f06c`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Could not allocate BSTR service description`
- `0x18000f0de`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Exiting`

## pseudocode

```c
__int64 __fastcall CUPnPAutomationProxy::HrProcessServiceDescription(CUPnPAutomationProxy *this, OLECHAR *psz)
{
  HRESULT Instance; // eax
  unsigned int v5; // ebx
  OLECHAR *v6; // rdi
  int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // r8d
  int v10; // eax
  STRSAFE_PCNZWCH v11; // rcx
  int v12; // edx
  const char *v13; // r9
  STRSAFE_PCNZWCH v14; // rcx
  struct IXMLDOMElement *v16; // [rsp+30h] [rbp-10h] BYREF
  __int16 v17; // [rsp+80h] [rbp+40h] BYREF
  struct IXMLDOMDocument *ppv; // [rsp+88h] [rbp+48h] BYREF

  ppv = 0;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids, psz);
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, (LPVOID *)&ppv);
  v5 = Instance;
  if ( Instance >= 0 )
  {
    v6 = SysAllocString(psz);
    if ( !v6 )
    {
      v5 = -2147024882;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (unsigned int)"CUPnPAutomationProxy::HrProcessServiceDescription(): Could not allocate BSTR service description",
          14);
LABEL_33:
      ((void (__fastcall *)(struct IXMLDOMDocument *))ppv->lpVtbl->Release)(ppv);
      if ( !v5 )
        return v5;
      goto LABEL_38;
    }
    v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, _QWORD))ppv->lpVtbl->put_async)(ppv, 0);
    v5 = v7;
    if ( v7 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_29;
      v12 = 58;
      v13 = "CUPnPAutomationProxy::HrProcessServiceDescription(): Could not set async property";
    }
    else
    {
      v17 = 0;
      v8 = DwDHFileSizeLimit();
      RestrictDomDocument(ppv, v8, v9);
      v5 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, OLECHAR *, __int16 *))ppv->lpVtbl->loadXML)(ppv, v6, &v17);
      if ( (v5 & 0x80000000) != 0 || v17 != -1 )
      {
        if ( v5 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
            (unsigned int)"CUPnPAutomationProxy::HrProcessServiceDescription(): Failed to load XML",
            v5);
        goto LABEL_29;
      }
      v16 = 0;
      v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, struct IXMLDOMElement **))ppv->lpVtbl->get_documentElement)(
             ppv,
             &v16);
      v5 = v7;
      if ( !v7 )
      {
        v10 = CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(this, v16);
        v5 = v10;
        if ( v10 < 0 )
        {
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              54,
              (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
              (unsigned int)"CUPnPAutomationProxy::HrProcessServiceDescription(): Could not build tables from service description",
              v10);
        }
        else if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
            (unsigned int)v10);
        }
        ((void (__fastcall *)(struct IXMLDOMElement *))v16->lpVtbl->Release)(v16);
        goto LABEL_29;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_29:
        SysFreeString(v6);
        goto LABEL_33;
      }
      v12 = 56;
      v13 = "CUPnPAutomationProxy::HrProcessServiceDescription(): Could not get document element";
    }
    WPP_SF_sd(*((_QWORD *)v11 + 2), v12, (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids, (_DWORD)v13, v7);
    goto LABEL_29;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    return v5;
  if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
      (unsigned int)"CUPnPAutomationProxy::HrProcessServiceDescription(): Could not create DOM document",
      Instance);
LABEL_38:
    v14 = WPP_GLOBAL_Control;
  }
  if ( v14 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v14[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)v14 + 2),
      61,
      (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
      (unsigned int)"CUPnPAutomationProxy::HrProcessServiceDescription(): Exiting",
      v5);
  return v5;
}

```

## disassembly

```asm
0x18000ee34  mov     [rsp-28h+arg_0], rbx
0x18000ee39  push    rbp
0x18000ee3a  push    rsi
0x18000ee3b  push    rdi
0x18000ee3c  push    r14
0x18000ee3e  push    r15
0x18000ee40  mov     rbp, rsp
0x18000ee43  sub     rsp, 40h
0x18000ee47  mov     rdi, rdx
0x18000ee4a  mov     [rbp+arg_18], 0
0x18000ee52  mov     rsi, rcx
0x18000ee55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee5c  lea     r14, WPP_GLOBAL_Control
0x18000ee63  lea     r15, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18000ee6a  cmp     rcx, r14
0x18000ee6d  jz      short loc_18000EE89
0x18000ee6f  test    byte ptr [rcx+1Ch], 40h
0x18000ee73  jz      short loc_18000EE89
0x18000ee75  mov     rcx, [rcx+10h]
0x18000ee79  mov     edx, 34h ; '4'
0x18000ee7e  mov     r9, rdi
0x18000ee81  mov     r8, r15
0x18000ee84  call    WPP_SF_S
0x18000ee89  xor     edx, edx; pUnkOuter
0x18000ee8b  lea     rax, [rbp+arg_18]
0x18000ee8f  lea     r9, IID_IXMLDOMDocument; riid
0x18000ee96  mov     [rsp+40h+ppv], rax; ppv
0x18000ee9b  lea     rcx, CLSID_DOMDocument60; rclsid
0x18000eea2  lea     r8d, [rdx+1]; dwClsContext
0x18000eea6  call    cs:__imp_CoCreateInstance
0x18000eeac  mov     ebx, eax
0x18000eeae  test    eax, eax
0x18000eeb0  js      loc_18000F09A
0x18000eeb6  mov     rcx, rdi; psz
0x18000eeb9  call    cs:__imp_SysAllocString
0x18000eebf  mov     rdi, rax
0x18000eec2  test    rax, rax
0x18000eec5  jz      loc_18000F051
0x18000eecb  mov     rcx, [rbp+arg_18]
0x18000eecf  xor     edx, edx
0x18000eed1  mov     r8, [rcx]
0x18000eed4  mov     rax, [r8+1F8h]
0x18000eedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eee0  mov     ebx, eax
0x18000eee2  test    eax, eax
0x18000eee4  js      loc_18000F018
0x18000eeea  xor     eax, eax
0x18000eeec  mov     [rbp+arg_10], ax
0x18000eef0  call    ?DwDHFileSizeLimit@@YAKXZ; DwDHFileSizeLimit(void)
0x18000eef5  mov     rcx, [rbp+arg_18]; struct IXMLDOMDocument *
0x18000eef9  mov     edx, eax; unsigned int
0x18000eefb  call    ?RestrictDomDocument@@YAXPEAUIXMLDOMDocument@@KK@Z; RestrictDomDocument(IXMLDOMDocument *,ulong,ulong)
0x18000ef00  mov     rcx, [rbp+arg_18]
0x18000ef04  lea     r8, [rbp+arg_10]
0x18000ef08  mov     rdx, rdi
0x18000ef0b  mov     rax, [rcx]
0x18000ef0e  mov     rax, [rax+208h]
0x18000ef15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef1a  mov     ebx, eax
0x18000ef1c  test    eax, eax
0x18000ef1e  js      loc_18000EFF0
0x18000ef24  or      eax, 0FFFFFFFFh
0x18000ef27  cmp     ax, [rbp+arg_10]
0x18000ef2b  jnz     loc_18000EFF0
0x18000ef31  mov     rcx, [rbp+arg_18]
0x18000ef35  lea     rdx, [rbp+var_10]
0x18000ef39  mov     [rbp+var_10], 0
0x18000ef41  mov     rax, [rcx]
0x18000ef44  mov     rax, [rax+168h]
0x18000ef4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef50  mov     ebx, eax
0x18000ef52  test    eax, eax
0x18000ef54  jnz     short loc_18000EFD0
0x18000ef56  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x18000ef5a  mov     rcx, rsi; this
0x18000ef5d  call    ?HrBuildTablesFromServiceDescription@CUPnPAutomationProxy@@AEAAJPEAUIXMLDOMElement@@@Z; CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(IXMLDOMElement *)
0x18000ef62  mov     ebx, eax
0x18000ef64  test    eax, eax
0x18000ef66  js      short loc_18000EF90
0x18000ef68  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef6f  cmp     rcx, r14
0x18000ef72  jz      short loc_18000EFBE
0x18000ef74  test    byte ptr [rcx+1Ch], 40h
0x18000ef78  jz      short loc_18000EFBE
0x18000ef7a  mov     rcx, [rcx+10h]
0x18000ef7e  mov     edx, 35h ; '5'
0x18000ef83  mov     r9d, eax
0x18000ef86  mov     r8, r15
0x18000ef89  call    WPP_SF_d
0x18000ef8e  jmp     short loc_18000EFBE
0x18000ef90  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef97  cmp     rcx, r14
0x18000ef9a  jz      short loc_18000EFBE
0x18000ef9c  test    byte ptr [rcx+1Ch], 1
0x18000efa0  jz      short loc_18000EFBE
0x18000efa2  mov     rcx, [rcx+10h]
0x18000efa6  lea     r9, aCupnpautomatio_63; "CUPnPAutomationProxy::HrProcessServiceD"...
0x18000efad  mov     edx, 36h ; '6'
0x18000efb2  mov     dword ptr [rsp+40h+ppv], eax
0x18000efb6  mov     r8, r15
0x18000efb9  call    WPP_SF_sd
0x18000efbe  mov     rcx, [rbp+var_10]
0x18000efc2  mov     rax, [rcx]
0x18000efc5  mov     rax, [rax+10h]
0x18000efc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efce  jmp     short loc_18000F046
0x18000efd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efd7  cmp     rcx, r14
0x18000efda  jz      short loc_18000F046
0x18000efdc  test    byte ptr [rcx+1Ch], 1
0x18000efe0  jz      short loc_18000F046
0x18000efe2  mov     edx, 38h ; '8'
0x18000efe7  lea     r9, aCupnpautomatio_79; "CUPnPAutomationProxy::HrProcessServiceD"...
0x18000efee  jmp     short loc_18000F036
0x18000eff0  test    ebx, ebx
0x18000eff2  jz      short loc_18000F046
0x18000eff4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000effb  cmp     rcx, r14
0x18000effe  jz      short loc_18000F046
0x18000f000  test    byte ptr [rcx+1Ch], 1
0x18000f004  jz      short loc_18000F046
0x18000f006  mov     edx, 39h ; '9'
0x18000f00b  mov     dword ptr [rsp+40h+ppv], ebx
0x18000f00f  lea     r9, aCupnpautomatio_6; "CUPnPAutomationProxy::HrProcessServiceD"...
0x18000f016  jmp     short loc_18000F03A
0x18000f018  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f01f  cmp     rcx, r14
0x18000f022  jz      short loc_18000F046
0x18000f024  test    byte ptr [rcx+1Ch], 1
0x18000f028  jz      short loc_18000F046
0x18000f02a  mov     edx, 3Ah ; ':'
0x18000f02f  lea     r9, aCupnpautomatio_82; "CUPnPAutomationProxy::HrProcessServiceD"...
0x18000f036  mov     dword ptr [rsp+40h+ppv], eax
0x18000f03a  mov     rcx, [rcx+10h]
0x18000f03e  mov     r8, r15
0x18000f041  call    WPP_SF_sd
0x18000f046  mov     rcx, rdi; bstrString
0x18000f049  call    cs:__imp_SysFreeString
0x18000f04f  jmp     short loc_18000F084
0x18000f051  mov     ebx, 8007000Eh
0x18000f056  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f05d  cmp     rcx, r14
0x18000f060  jz      short loc_18000F084
0x18000f062  test    byte ptr [rcx+1Ch], 1
0x18000f066  jz      short loc_18000F084
0x18000f068  mov     rcx, [rcx+10h]
0x18000f06c  lea     r9, aCupnpautomatio_33; "CUPnPAutomationProxy::HrProcessServiceD"...
0x18000f073  mov     edx, 3Bh ; ';'
0x18000f078  mov     dword ptr [rsp+40h+ppv], ebx
0x18000f07c  mov     r8, r15
0x18000f07f  call    WPP_SF_sd
0x18000f084  mov     rcx, [rbp+arg_18]
0x18000f088  mov     rax, [rcx]
0x18000f08b  mov     rax, [rax+10h]
0x18000f08f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f094  test    ebx, ebx
0x18000f096  jnz     short loc_18000F0C8
0x18000f098  jmp     short loc_18000F0F6
0x18000f09a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0a1  cmp     rcx, r14
0x18000f0a4  jz      short loc_18000F0F6
0x18000f0a6  test    byte ptr [rcx+1Ch], 1
0x18000f0aa  jz      short loc_18000F0CF
0x18000f0ac  mov     rcx, [rcx+10h]
0x18000f0b0  lea     r9, aCupnpautomatio_35; "CUPnPAutomationProxy::HrProcessServiceD"...
0x18000f0b7  mov     edx, 3Ch ; '<'
0x18000f0bc  mov     dword ptr [rsp+40h+ppv], eax
0x18000f0c0  mov     r8, r15
0x18000f0c3  call    WPP_SF_sd
0x18000f0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0cf  cmp     rcx, r14
0x18000f0d2  jz      short loc_18000F0F6
0x18000f0d4  test    byte ptr [rcx+1Ch], 1
0x18000f0d8  jz      short loc_18000F0F6
0x18000f0da  mov     rcx, [rcx+10h]
0x18000f0de  lea     r9, aCupnpautomatio_72; "CUPnPAutomationProxy::HrProcessServiceD"...
0x18000f0e5  mov     edx, 3Dh ; '='
0x18000f0ea  mov     dword ptr [rsp+40h+ppv], ebx
0x18000f0ee  mov     r8, r15
0x18000f0f1  call    WPP_SF_sd
0x18000f0f6  mov     eax, ebx
0x18000f0f8  mov     rbx, [rsp+40h+arg_0]
0x18000f0fd  add     rsp, 40h
0x18000f101  pop     r15
0x18000f103  pop     r14
0x18000f105  pop     rdi
0x18000f106  pop     rsi
0x18000f107  pop     rbp
0x18000f108  retn
```
