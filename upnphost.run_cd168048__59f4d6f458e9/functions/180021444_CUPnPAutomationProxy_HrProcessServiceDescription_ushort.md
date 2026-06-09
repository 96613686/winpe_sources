# CUPnPAutomationProxy::HrProcessServiceDescription(ushort *)

- ea: `0x180021444`
- end: `0x18002172c`
- name: `?HrProcessServiceDescription@CUPnPAutomationProxy@@AEAAJPEAG@Z`
- size: `744`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *__hidden this, OLECHAR *psz)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180038280`

## callees

- `0x180005b24`
- `0x180005bc0`
- `0x1800200f4`
- `0x180020a7c`
- `0x180021444`
- `0x18003b1cc`
- `0x18003b904`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800214b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800214b6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800214cf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800214cf`
- `OLEAUT32!__imp_SysFreeString` at `0x180021665`
- `OLEAUT32!__imp_SysFreeString` at `0x180021665`

## string_xrefs

- `0x1800215c2`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Could not build tables from service description`
- `0x180021603`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Could not get document element`
- `0x18002164b`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Could not set async property`
- `0x18002162b`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Failed to load XML`
- `0x1800216d2`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Could not create DOM document`
- `0x18002168e`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Could not allocate BSTR service description`
- `0x180021700`: `CUPnPAutomationProxy::HrProcessServiceDescription(): Exiting`

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
0x180021444  mov     [rsp-28h+arg_0], rbx
0x180021449  push    rbp
0x18002144a  push    rsi
0x18002144b  push    rdi
0x18002144c  push    r14
0x18002144e  push    r15
0x180021450  mov     rbp, rsp
0x180021453  sub     rsp, 40h
0x180021457  mov     rdi, rdx
0x18002145a  mov     [rbp+arg_18], 0
0x180021462  mov     rsi, rcx
0x180021465  mov     rcx, cs:WPP_GLOBAL_Control
0x18002146c  lea     r14, WPP_GLOBAL_Control
0x180021473  lea     r15, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002147a  cmp     rcx, r14
0x18002147d  jz      short loc_180021499
0x18002147f  test    byte ptr [rcx+1Ch], 40h
0x180021483  jz      short loc_180021499
0x180021485  mov     rcx, [rcx+10h]
0x180021489  mov     edx, 34h ; '4'
0x18002148e  mov     r9, rdi
0x180021491  mov     r8, r15
0x180021494  call    WPP_SF_S
0x180021499  xor     edx, edx; pUnkOuter
0x18002149b  lea     rax, [rbp+arg_18]
0x18002149f  lea     r9, IID_IXMLDOMDocument; riid
0x1800214a6  mov     [rsp+40h+ppv], rax; ppv
0x1800214ab  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800214b2  lea     r8d, [rdx+1]; dwClsContext
0x1800214b6  call    cs:__imp_CoCreateInstance
0x1800214bd  nop     dword ptr [rax+rax+00h]
0x1800214c2  mov     ebx, eax
0x1800214c4  test    eax, eax
0x1800214c6  js      loc_1800216BC
0x1800214cc  mov     rcx, rdi; psz
0x1800214cf  call    cs:__imp_SysAllocString
0x1800214d6  nop     dword ptr [rax+rax+00h]
0x1800214db  mov     rdi, rax
0x1800214de  test    rax, rax
0x1800214e1  jz      loc_180021673
0x1800214e7  mov     rcx, [rbp+arg_18]
0x1800214eb  xor     edx, edx
0x1800214ed  mov     r8, [rcx]
0x1800214f0  mov     rax, [r8+1F8h]
0x1800214f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214fc  mov     ebx, eax
0x1800214fe  test    eax, eax
0x180021500  js      loc_180021634
0x180021506  xor     eax, eax
0x180021508  mov     [rbp+arg_10], ax
0x18002150c  call    ?DwDHFileSizeLimit@@YAKXZ; DwDHFileSizeLimit(void)
0x180021511  mov     rcx, [rbp+arg_18]; struct IXMLDOMDocument *
0x180021515  mov     edx, eax; unsigned int
0x180021517  call    ?RestrictDomDocument@@YAXPEAUIXMLDOMDocument@@KK@Z; RestrictDomDocument(IXMLDOMDocument *,ulong,ulong)
0x18002151c  mov     rcx, [rbp+arg_18]
0x180021520  lea     r8, [rbp+arg_10]
0x180021524  mov     rdx, rdi
0x180021527  mov     rax, [rcx]
0x18002152a  mov     rax, [rax+208h]
0x180021531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021536  mov     ebx, eax
0x180021538  test    eax, eax
0x18002153a  js      loc_18002160C
0x180021540  or      eax, 0FFFFFFFFh
0x180021543  cmp     ax, [rbp+arg_10]
0x180021547  jnz     loc_18002160C
0x18002154d  mov     rcx, [rbp+arg_18]
0x180021551  lea     rdx, [rbp+var_10]
0x180021555  mov     [rbp+var_10], 0
0x18002155d  mov     rax, [rcx]
0x180021560  mov     rax, [rax+168h]
0x180021567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002156c  mov     ebx, eax
0x18002156e  test    eax, eax
0x180021570  jnz     short loc_1800215EC
0x180021572  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x180021576  mov     rcx, rsi; this
0x180021579  call    ?HrBuildTablesFromServiceDescription@CUPnPAutomationProxy@@AEAAJPEAUIXMLDOMElement@@@Z; CUPnPAutomationProxy::HrBuildTablesFromServiceDescription(IXMLDOMElement *)
0x18002157e  mov     ebx, eax
0x180021580  test    eax, eax
0x180021582  js      short loc_1800215AC
0x180021584  mov     rcx, cs:WPP_GLOBAL_Control
0x18002158b  cmp     rcx, r14
0x18002158e  jz      short loc_1800215DA
0x180021590  test    byte ptr [rcx+1Ch], 40h
0x180021594  jz      short loc_1800215DA
0x180021596  mov     rcx, [rcx+10h]
0x18002159a  mov     edx, 35h ; '5'
0x18002159f  mov     r9d, eax
0x1800215a2  mov     r8, r15
0x1800215a5  call    WPP_SF_d
0x1800215aa  jmp     short loc_1800215DA
0x1800215ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215b3  cmp     rcx, r14
0x1800215b6  jz      short loc_1800215DA
0x1800215b8  test    byte ptr [rcx+1Ch], 1
0x1800215bc  jz      short loc_1800215DA
0x1800215be  mov     rcx, [rcx+10h]
0x1800215c2  lea     r9, aCupnpautomatio_63; "CUPnPAutomationProxy::HrProcessServiceD"...
0x1800215c9  mov     edx, 36h ; '6'
0x1800215ce  mov     dword ptr [rsp+40h+ppv], eax
0x1800215d2  mov     r8, r15
0x1800215d5  call    WPP_SF_sd
0x1800215da  mov     rcx, [rbp+var_10]
0x1800215de  mov     rax, [rcx]
0x1800215e1  mov     rax, [rax+10h]
0x1800215e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215ea  jmp     short loc_180021662
0x1800215ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215f3  cmp     rcx, r14
0x1800215f6  jz      short loc_180021662
0x1800215f8  test    byte ptr [rcx+1Ch], 1
0x1800215fc  jz      short loc_180021662
0x1800215fe  mov     edx, 38h ; '8'
0x180021603  lea     r9, aCupnpautomatio_79; "CUPnPAutomationProxy::HrProcessServiceD"...
0x18002160a  jmp     short loc_180021652
0x18002160c  test    ebx, ebx
0x18002160e  jz      short loc_180021662
0x180021610  mov     rcx, cs:WPP_GLOBAL_Control
0x180021617  cmp     rcx, r14
0x18002161a  jz      short loc_180021662
0x18002161c  test    byte ptr [rcx+1Ch], 1
0x180021620  jz      short loc_180021662
0x180021622  mov     edx, 39h ; '9'
0x180021627  mov     dword ptr [rsp+40h+ppv], ebx
0x18002162b  lea     r9, aCupnpautomatio_6; "CUPnPAutomationProxy::HrProcessServiceD"...
0x180021632  jmp     short loc_180021656
0x180021634  mov     rcx, cs:WPP_GLOBAL_Control
0x18002163b  cmp     rcx, r14
0x18002163e  jz      short loc_180021662
0x180021640  test    byte ptr [rcx+1Ch], 1
0x180021644  jz      short loc_180021662
0x180021646  mov     edx, 3Ah ; ':'
0x18002164b  lea     r9, aCupnpautomatio_82; "CUPnPAutomationProxy::HrProcessServiceD"...
0x180021652  mov     dword ptr [rsp+40h+ppv], eax
0x180021656  mov     rcx, [rcx+10h]
0x18002165a  mov     r8, r15
0x18002165d  call    WPP_SF_sd
0x180021662  mov     rcx, rdi; bstrString
0x180021665  call    cs:__imp_SysFreeString
0x18002166c  nop     dword ptr [rax+rax+00h]
0x180021671  jmp     short loc_1800216A6
0x180021673  mov     ebx, 8007000Eh
0x180021678  mov     rcx, cs:WPP_GLOBAL_Control
0x18002167f  cmp     rcx, r14
0x180021682  jz      short loc_1800216A6
0x180021684  test    byte ptr [rcx+1Ch], 1
0x180021688  jz      short loc_1800216A6
0x18002168a  mov     rcx, [rcx+10h]
0x18002168e  lea     r9, aCupnpautomatio_33; "CUPnPAutomationProxy::HrProcessServiceD"...
0x180021695  mov     edx, 3Bh ; ';'
0x18002169a  mov     dword ptr [rsp+40h+ppv], ebx
0x18002169e  mov     r8, r15
0x1800216a1  call    WPP_SF_sd
0x1800216a6  mov     rcx, [rbp+arg_18]
0x1800216aa  mov     rax, [rcx]
0x1800216ad  mov     rax, [rax+10h]
0x1800216b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216b6  test    ebx, ebx
0x1800216b8  jnz     short loc_1800216EA
0x1800216ba  jmp     short loc_180021718
0x1800216bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216c3  cmp     rcx, r14
0x1800216c6  jz      short loc_180021718
0x1800216c8  test    byte ptr [rcx+1Ch], 1
0x1800216cc  jz      short loc_1800216F1
0x1800216ce  mov     rcx, [rcx+10h]
0x1800216d2  lea     r9, aCupnpautomatio_35; "CUPnPAutomationProxy::HrProcessServiceD"...
0x1800216d9  mov     edx, 3Ch ; '<'
0x1800216de  mov     dword ptr [rsp+40h+ppv], eax
0x1800216e2  mov     r8, r15
0x1800216e5  call    WPP_SF_sd
0x1800216ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216f1  cmp     rcx, r14
0x1800216f4  jz      short loc_180021718
0x1800216f6  test    byte ptr [rcx+1Ch], 1
0x1800216fa  jz      short loc_180021718
0x1800216fc  mov     rcx, [rcx+10h]
0x180021700  lea     r9, aCupnpautomatio_72; "CUPnPAutomationProxy::HrProcessServiceD"...
0x180021707  mov     edx, 3Dh ; '='
0x18002170c  mov     dword ptr [rsp+40h+ppv], ebx
0x180021710  mov     r8, r15
0x180021713  call    WPP_SF_sd
0x180021718  mov     eax, ebx
0x18002171a  mov     rbx, [rsp+40h+arg_0]
0x18002171f  add     rsp, 40h
0x180021723  pop     r15
0x180021725  pop     r14
0x180021727  pop     rdi
0x180021728  pop     rsi
0x180021729  pop     rbp
0x18002172a  retn
```
