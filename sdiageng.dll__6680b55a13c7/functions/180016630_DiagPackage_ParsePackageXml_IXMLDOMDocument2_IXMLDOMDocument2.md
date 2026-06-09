# DiagPackage::ParsePackageXml(IXMLDOMDocument2 *,IXMLDOMDocument2 *)

- ea: `0x180016630`
- end: `0x1800170b3`
- name: `?ParsePackageXml@DiagPackage@@AEAAJPEAUIXMLDOMDocument2@@0@Z`
- size: `2691`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180016080`

## callees

- `0x1800012a4`
- `0x18000330c`
- `0x1800038c4`
- `0x180003b2c`
- `0x18000615c`
- `0x1800151fc`
- `0x180015730`
- `0x180015c14`
- `0x180016228`
- `0x180016460`
- `0x180016630`
- `0x1800170bc`
- `0x1800175c4`
- `0x18001e6c0`
- `0x18001e75c`
- `0x18001eaf0`
- `0x18001fc10`
- `0x18002146c`
- `0x180026fa0`
- `0x180028038`
- `0x1800286a4`
- `0x1800288b8`
- `0x1800290bc`
- `0x18002a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180016be3`
- `msvcrt!_wcsicmp` at `0x180016be3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001682f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001683d`
- `OLEAUT32!__imp_SysFreeString` at `0x180016bfa`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f20`
- `OLEAUT32!__imp_SysFreeString` at `0x18001682f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001683d`
- `OLEAUT32!__imp_SysFreeString` at `0x180016bfa`
- `OLEAUT32!__imp_SysFreeString` at `0x180016f20`

## string_xrefs

- `0x180016ed0`: `SdpParseExtensionPoint`
- `0x1800166ad`: `DiagPackage::ParsePackageXml`
- `0x1800166fa`: `DiagPackage::ParsePackageXml`
- `0x180016766`: `DiagPackage::ParsePackageXml`
- `0x180016793`: `DiagPackage::ParsePackageXml`
- `0x1800168a3`: `DiagPackage::ParsePackageXml`
- `0x180016912`: `DiagPackage::ParsePackageXml`
- `0x180016a67`: `DiagPackage::ParsePackageXml`
- `0x180016ac6`: `DiagPackage::ParsePackageXml`
- `0x180016d43`: `DiagPackage::ParsePackageXml`
- `0x180017024`: `DiagPackage::ParsePackageXml`
- `0x180016ae1`: `PrivacyLink`
- `0x180016e7f`: `ExtensionPoint`

## pseudocode

```c
__int64 __fastcall DiagPackage::ParsePackageXml(
        DiagPackage *this,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMDocument2 *a3)
{
  struct IXMLDOMNodeList *v5; // r13
  struct IXMLDOMNode *v6; // rsi
  struct IXMLDOMNode *v7; // r15
  int v8; // r8d
  int v9; // ebx
  int v10; // r9d
  int RootNode; // eax
  int v12; // r8d
  int v13; // r9d
  struct IXMLDOMDocument2 *v14; // r14
  struct IXMLDOMElement *v15; // rdi
  __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // eax
  int ChildNodes; // eax
  unsigned __int16 *v20; // rdi
  int v22; // eax
  int v23; // r8d
  int v24; // eax
  unsigned __int16 *v25; // rax
  int v26; // ecx
  int v27; // edx
  int Locale; // eax
  Settings *v29; // rcx
  int v30; // eax
  int v31; // eax
  int InteractionsFromXml; // eax
  int v33; // r8d
  int v34; // r9d
  int v35; // eax
  int v36; // r8d
  int v37; // eax
  int v38; // eax
  struct IXMLDOMNode v39; // rax
  int v40; // eax
  int v41; // eax
  int v42; // eax
  __int64 v43; // rdx
  unsigned int v44; // ecx
  int v45; // eax
  struct IXMLDOMNode *v46; // rax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // r9d
  int v51; // r8d
  int v52; // eax
  wchar_t *v53; // rcx
  __int64 v54; // rcx
  int v55; // eax
  unsigned int v56; // eax
  int v57; // eax
  int updated; // eax
  __int64 v59; // rax
  __int64 v60; // r15
  int v61; // eax
  struct IXMLDOMDocument2 *v62; // [rsp+30h] [rbp-39h] BYREF
  BSTR v63; // [rsp+38h] [rbp-31h]
  struct IXMLDOMNode *v64; // [rsp+40h] [rbp-29h]
  struct IXMLDOMNode *v65; // [rsp+48h] [rbp-21h] BYREF
  int v66; // [rsp+50h] [rbp-19h] BYREF
  struct IXMLDOMNodeList *v67; // [rsp+58h] [rbp-11h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int16 *v69; // [rsp+68h] [rbp-1h] BYREF
  struct IXMLDOMNode *v70; // [rsp+70h] [rbp+7h] BYREF
  struct IXMLDOMElement *v71; // [rsp+78h] [rbp+Fh] BYREF
  void *Block; // [rsp+80h] [rbp+17h] BYREF
  unsigned __int16 *v73; // [rsp+88h] [rbp+1Fh] BYREF
  wchar_t *String2; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int v75; // [rsp+E8h] [rbp+7Fh] BYREF

  v71 = 0;
  v63 = 0;
  v69 = 0;
  v67 = 0;
  v5 = 0;
  v65 = 0;
  v6 = 0;
  v64 = 0;
  v7 = 0;
  v70 = 0;
  v75 = 0;
  v66 = 0;
  LODWORD(String2) = 0;
  bstrString = 0;
  Block = 0;
  v73 = 0;
  v62 = 0;
  if ( !a2 )
  {
    v8 = 1097;
    v9 = -2147024809;
    v10 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"DiagPackage::ParsePackageXml", v8, v10);
    return (unsigned int)v9;
  }
  if ( !*((_QWORD *)this + 1) )
  {
    v10 = -2147467261;
    v8 = 1098;
    v9 = -2147467261;
    goto LABEL_3;
  }
  RootNode = SdpXmlGetRootNode(a2, &v71);
  v9 = RootNode;
  if ( RootNode >= 0 )
  {
    v15 = v71;
    RootNode = SdpCheckBooleanAttribute((struct IXMLDOMNode *)v71, (OLECHAR *)L"Localized", (int *)&String2);
    v9 = RootNode;
    if ( RootNode < 0 )
    {
      v12 = 1106;
      goto LABEL_8;
    }
    v16 = *((_QWORD *)this + 1);
    v17 = *(_DWORD *)(v16 + 56);
    if ( (_DWORD)String2 )
      v18 = v17 | 4;
    else
      v18 = v17 & 0xFFFFFFFB;
    *(_DWORD *)(v16 + 56) = v18;
    ChildNodes = SdpXmlGetChildNodes(0, (struct IXMLDOMNode *)v15, &v67, &v75);
    v9 = ChildNodes;
    if ( ChildNodes < 0 )
    {
      SdpDebugTrace(1u, L"DiagPackage::ParsePackageXml", 1112, ChildNodes);
      v5 = v67;
      goto LABEL_10;
    }
    if ( v75 < 8 )
    {
      v9 = -2147024809;
      SdpDebugTrace(1u, L"DiagPackage::ParsePackageXml", 1116, -2147024809);
      v5 = v67;
LABEL_20:
      v14 = v62;
LABEL_21:
      v7 = v64;
      goto LABEL_22;
    }
    v5 = v67;
    v22 = SdpXmlNextNode(v67, &v65);
    v9 = v22;
    if ( v22 < 0 )
    {
      v23 = 1124;
LABEL_44:
      SdpDebugTrace(1u, L"DiagPackage::ParsePackageXml", v23, v22);
      v6 = v65;
      goto LABEL_10;
    }
    v6 = v65;
    RootNode = SdpXmlCheckNode(v65, L"DiagnosticIdentification");
    v9 = RootNode;
    if ( RootNode < 0 )
    {
      v12 = 1125;
      goto LABEL_8;
    }
    if ( RootNode == 1 || !v6 )
    {
      v13 = -2147467259;
      v12 = 1125;
      v9 = -2147467259;
      goto LABEL_9;
    }
    v24 = SdpParseDiagnosticIdentification(v6, &bstrString, &v69, (unsigned __int16 **)this + 5);
    v9 = v24;
    if ( v24 < 0 )
    {
      SdpDebugTrace(1u, L"DiagPackage::ParsePackageXml", 1131, v24);
      v20 = v69;
      v14 = v62;
      goto LABEL_23;
    }
    *((_QWORD *)this + 11) = v69;
    v63 = 0;
    if ( (int)Settings::get_PackageId(*((Settings **)this + 1), (unsigned __int16 **)&Block) < 0 )
    {
      Locale = Settings::get_Locale(*((Settings **)this + 1), &v73);
      v9 = Locale;
      if ( Locale < 0 )
      {
        v13 = Locale;
        v12 = 1157;
        goto LABEL_9;
      }
      v29 = (Settings *)*((_QWORD *)this + 1);
      if ( v73 && (*((_DWORD *)v29 + 14) & 0x200) == 0 )
      {
        v9 = 0;
        v12 = 1163;
        v13 = 0;
        goto LABEL_9;
      }
      v30 = Settings::set_PackageId(v29, bstrString);
      v9 = v30;
      if ( v30 < 0 )
      {
        v13 = v30;
        v12 = 1167;
        goto LABEL_9;
      }
    }
    else
    {
      v25 = (unsigned __int16 *)Block;
      do
      {
        v26 = *(unsigned __int16 *)((char *)v25 + (char *)bstrString - (_BYTE *)Block);
        v27 = *v25 - v26;
        if ( v27 )
          break;
        ++v25;
      }
      while ( v26 );
      if ( v27 )
      {
        v9 = -2147418113;
        v12 = 1146;
        v13 = -2147418113;
        goto LABEL_9;
      }
    }
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
    v65 = 0;
    v22 = SdpXmlNextNode(v5, &v65);
    v9 = v22;
    if ( v22 < 0 )
    {
      v23 = 1176;
      goto LABEL_44;
    }
    v6 = v65;
    v31 = SdpXmlCheckNode(v65, L"DisplayInformation");
    v9 = v31;
    if ( v31 < 0 )
    {
      v13 = v31;
LABEL_68:
      v12 = 1177;
      goto LABEL_9;
    }
    if ( v31 == 1 || !v6 )
    {
      v13 = -2147467259;
      v9 = -2147467259;
      goto LABEL_68;
    }
    InteractionsFromXml = SdpParseDisplayInformation(v6, (DiagPackage *)((char *)this + 48));
    v9 = InteractionsFromXml;
    if ( InteractionsFromXml < 0 )
    {
      v33 = 1180;
LABEL_73:
      v34 = InteractionsFromXml;
LABEL_74:
      SdpDebugTrace(1u, L"DiagPackage::ParsePackageXml", v33, v34);
      goto LABEL_20;
    }
    InteractionsFromXml = SdpLocalizeDisplayInformation(
                            *((struct Settings **)this + 1),
                            (DiagPackage *)((char *)this + 48),
                            1);
    v9 = InteractionsFromXml;
    if ( InteractionsFromXml < 0 )
    {
      v33 = 1183;
      goto LABEL_73;
    }
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
    v65 = 0;
    v35 = SdpXmlNextNode(v5, &v65);
    v9 = v35;
    if ( v35 < 0 )
    {
      v36 = 1191;
LABEL_79:
      SdpDebugTrace(1u, L"DiagPackage::ParsePackageXml", v36, v35);
      v6 = v65;
      goto LABEL_20;
    }
    v6 = v65;
    v37 = SdpXmlCheckNode(v65, L"PrivacyLink");
    v9 = v37;
    if ( v37 < 0 )
    {
      v34 = v37;
LABEL_82:
      v33 = 1192;
      goto LABEL_74;
    }
    if ( v37 == 1 || !v6 )
    {
      v34 = -2147467259;
      v9 = -2147467259;
      goto LABEL_82;
    }
    InteractionsFromXml = DiagPackage::ParsePrivacyLink(this, v6);
    v9 = InteractionsFromXml;
    if ( InteractionsFromXml < 0 )
    {
      v33 = 1195;
      goto LABEL_73;
    }
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
    v65 = 0;
    v35 = SdpXmlNextNode(v5, &v65);
    v9 = v35;
    if ( v35 < 0 )
    {
      v36 = 1202;
      goto LABEL_79;
    }
    v6 = v65;
    v38 = SdpXmlCheckNode(v65, L"PowerShellVersion");
    v9 = v38;
    if ( v38 < 0 )
    {
      v34 = v38;
LABEL_91:
      v33 = 1203;
      goto LABEL_74;
    }
    if ( v38 == 1 || !v6 )
    {
      v34 = -2147467259;
      v9 = -2147467259;
      goto LABEL_91;
    }
    v39.lpVtbl = v6->lpVtbl;
    String2 = 0;
    v40 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v39.lpVtbl->get_text)(v6, &String2);
    v9 = v40;
    if ( v40 >= 0 )
    {
      if ( _wcsicmp(L"2.0", String2) < 0 )
        *(_DWORD *)this &= ~1u;
    }
    else
    {
      SdpDebugTrace(1u, L"DiagPackage::CheckPowerShellVersion", 2534, v40);
    }
    if ( String2 )
      SysFreeString(String2);
    if ( v9 < 0 )
    {
      v34 = v9;
      v33 = 1206;
      goto LABEL_74;
    }
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
    v65 = 0;
    v35 = SdpXmlNextNode(v5, &v65);
    v9 = v35;
    if ( v35 < 0 )
    {
      v36 = 1214;
      goto LABEL_79;
    }
    v6 = v65;
    v41 = SdpXmlCheckNode(v65, L"SupportedOSVersion");
    v9 = v41;
    if ( v41 < 0 )
    {
      v34 = v41;
LABEL_106:
      v33 = 1215;
      goto LABEL_74;
    }
    if ( v41 == 1 || !v6 )
    {
      v34 = -2147467259;
      v9 = -2147467259;
      goto LABEL_106;
    }
    InteractionsFromXml = DiagPackage::CheckApplicability(this, v6);
    v9 = InteractionsFromXml;
    if ( InteractionsFromXml < 0 )
    {
      v33 = 1218;
      goto LABEL_73;
    }
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
    v65 = 0;
    v35 = SdpXmlNextNode(v5, &v65);
    v9 = v35;
    if ( v35 < 0 )
    {
      v36 = 1226;
      goto LABEL_79;
    }
    v6 = v65;
    v42 = SdpXmlCheckNode(v65, L"Troubleshooter");
    v9 = v42;
    if ( v42 < 0 )
    {
      v34 = v42;
      v33 = 1229;
      goto LABEL_74;
    }
    v43 = *((_QWORD *)this + 1);
    v44 = *(_DWORD *)(v43 + 56) | 1;
    if ( v42 == 1 )
      v44 = *(_DWORD *)(v43 + 56) & 0xFFFFFFFE;
    *(_DWORD *)(v43 + 56) = v44;
    if ( v42 == 1 )
    {
      v46 = v6;
      v6 = 0;
      v65 = 0;
    }
    else
    {
      InteractionsFromXml = DiagPackage::InitializeTroubleshooter(this, v6);
      v9 = InteractionsFromXml;
      if ( InteractionsFromXml < 0 )
      {
        v33 = 1238;
        goto LABEL_73;
      }
      v45 = SdpXmlNextNode(v5, &v70);
      v9 = v45;
      if ( v45 < 0 )
      {
        SdpDebugTrace(1u, L"DiagPackage::ParsePackageXml", 1241, v45);
        v7 = v70;
        goto LABEL_10;
      }
      v46 = v70;
    }
    v64 = v46;
    v47 = SdpXmlCheckNode(v46, L"Rootcauses");
    v9 = v47;
    if ( v47 < 0 )
    {
      v34 = v47;
LABEL_126:
      v33 = 1251;
      goto LABEL_74;
    }
    if ( v47 == 1 || !v64 )
    {
      v34 = -2147467259;
      v9 = -2147467259;
      goto LABEL_126;
    }
    if ( v6 )
    {
      ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
      v65 = 0;
    }
    v35 = SdpXmlNextNode(v5, &v65);
    v9 = v35;
    if ( v35 < 0 )
    {
      v36 = 1259;
      goto LABEL_79;
    }
    v6 = v65;
    v48 = SdpXmlCheckNode(v65, L"Interactions");
    v9 = v48;
    if ( v48 < 0 )
    {
      v34 = v48;
LABEL_135:
      v33 = 1260;
      goto LABEL_74;
    }
    if ( v48 == 1 || !v6 )
    {
      v34 = -2147467259;
      v9 = -2147467259;
      goto LABEL_135;
    }
    InteractionsFromXml = Interaction::CreateInteractionsFromXml(
                            *((struct Settings **)this + 1),
                            v6,
                            a3,
                            (struct Interaction ***)this + 14,
                            (unsigned int *)this + 30);
    v9 = InteractionsFromXml;
    if ( InteractionsFromXml < 0 )
    {
      v33 = 1267;
      goto LABEL_73;
    }
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
    v65 = 0;
    v35 = SdpXmlNextNode(v5, &v65);
    v9 = v35;
    if ( v35 < 0 )
    {
      v36 = 1275;
      goto LABEL_79;
    }
    v6 = v65;
    v49 = SdpXmlCheckNode(v65, L"ExtensionPoint");
    v9 = v49;
    if ( v49 < 0 )
    {
      v34 = v49;
LABEL_144:
      v33 = 1276;
      goto LABEL_74;
    }
    if ( v49 == 1 || !v6 )
    {
      v34 = -2147467259;
      v9 = -2147467259;
      goto LABEL_144;
    }
    String2 = 0;
    if ( this == (DiagPackage *)-80LL )
    {
      v9 = -2147024809;
      v50 = -2147024809;
      v51 = 248;
    }
    else
    {
      v52 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v6->lpVtbl->get_xml)(v6, &String2);
      v9 = v52;
      if ( v52 >= 0 )
      {
        *((_QWORD *)this + 10) = String2;
        String2 = 0;
        goto LABEL_153;
      }
      v50 = v52;
      v51 = 251;
    }
    SdpDebugTrace(1u, L"SdpParseExtensionPoint", v51, v50);
LABEL_153:
    v53 = String2;
    if ( String2 )
      SysFreeString(String2);
    if ( v9 < 0 )
    {
      v34 = v9;
      v33 = 1279;
      goto LABEL_74;
    }
    InteractionsFromXml = DiagPackage::CheckForceUserModeExtension((DiagPackage *)v53, v6, &v66);
    v9 = InteractionsFromXml;
    if ( InteractionsFromXml >= 0 )
    {
      v54 = *((_QWORD *)this + 1);
      v55 = *(_DWORD *)(v54 + 56);
      if ( v66 )
        v56 = v55 | 0x20000;
      else
        v56 = v55 & 0xFFFDFFFF;
      v7 = v64;
      *(_DWORD *)(v54 + 56) = v56;
      v57 = DiagPackage::InitializeRootcauses(this, v7);
      v9 = v57;
      if ( v57 < 0 )
      {
        v13 = v57;
        v12 = 1295;
        goto LABEL_9;
      }
      updated = DiagPackage::UpdateApplicability(this);
      v9 = updated;
      if ( updated < 0 )
      {
        v13 = updated;
        v12 = 1302;
        goto LABEL_9;
      }
      v59 = *((_QWORD *)this + 1);
      if ( !v59 )
      {
        v13 = -2147467261;
        v12 = 1308;
        v9 = -2147467261;
        goto LABEL_9;
      }
      v60 = *(_QWORD *)(v59 + 72);
      InteractionsFromXml = DiagPackage::BuildReportPackageXml(this, &v62);
      v9 = InteractionsFromXml;
      if ( InteractionsFromXml >= 0 )
      {
        if ( v60 )
        {
          v14 = v62;
          v61 = Reporter::AddXmlToReport(v60, v62, 0);
          v9 = v61;
          if ( v61 < 0 )
            SdpDebugTrace(1u, L"DiagPackage::ParsePackageXml", 1318, v61);
          goto LABEL_21;
        }
        v34 = -2147467261;
        v33 = 1315;
        v9 = -2147467261;
        goto LABEL_74;
      }
      v33 = 1313;
    }
    else
    {
      v33 = 1285;
    }
    goto LABEL_73;
  }
  v12 = 1101;
LABEL_8:
  v13 = RootNode;
LABEL_9:
  SdpDebugTrace(1u, L"DiagPackage::ParsePackageXml", v12, v13);
LABEL_10:
  v14 = v62;
LABEL_22:
  v20 = v63;
LABEL_23:
  if ( v71 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v71->lpVtbl->Release)(v71);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v5->lpVtbl->Release)(v5);
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v6->lpVtbl->Release)(v6);
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v7->lpVtbl->Release)(v7);
  if ( v14 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v14->lpVtbl->Release)(v14);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v20 )
    SysFreeString(v20);
  if ( Block )
    operator delete(Block);
  if ( v73 )
    operator delete(v73);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180016630  mov     [rsp-8+arg_0], rbx
0x180016635  push    rbp
0x180016636  push    rsi
0x180016637  push    rdi
0x180016638  push    r12
0x18001663a  push    r13
0x18001663c  push    r14
0x18001663e  push    r15
0x180016640  lea     rbp, [rsp-27h]
0x180016645  sub     rsp, 90h
0x18001664c  xor     edi, edi
0x18001664e  mov     r14, rcx
0x180016651  mov     [rbp+57h+var_48], rdi
0x180016655  mov     ecx, edi
0x180016657  mov     [rbp+57h+var_88], rcx
0x18001665b  mov     r12, r8
0x18001665e  mov     [rbp+57h+var_58], rcx
0x180016662  mov     rax, rdx
0x180016665  mov     [rbp+57h+var_68], rdi
0x180016669  mov     r13d, edi
0x18001666c  mov     [rbp+57h+var_78], rdi
0x180016670  mov     esi, edi
0x180016672  mov     [rbp+57h+var_80], rdi
0x180016676  mov     r15d, edi
0x180016679  mov     [rbp+57h+var_50], rdi
0x18001667d  mov     [rbp+57h+arg_18], edi
0x180016680  mov     [rbp+57h+var_70], edi
0x180016683  mov     dword ptr [rbp+57h+String2], edi
0x180016686  mov     [rbp+57h+bstrString], rdi
0x18001668a  mov     [rbp+57h+Block], rdi
0x18001668e  mov     [rbp+57h+var_38], rdi
0x180016692  mov     [rbp+57h+var_90], rdi
0x180016696  test    rdx, rdx
0x180016699  jnz     short loc_1800166C3
0x18001669b  mov     r15d, 80070057h
0x1800166a1  mov     r8d, 449h; int
0x1800166a7  mov     ebx, r15d
0x1800166aa  mov     r9d, r15d; int
0x1800166ad  lea     rdx, aDiagpackagePar_0; "DiagPackage::ParsePackageXml"
0x1800166b4  mov     ecx, 1; Level
0x1800166b9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800166be  jmp     loc_180016865
0x1800166c3  cmp     [r14+8], rdi
0x1800166c7  jnz     short loc_1800166DA
0x1800166c9  mov     r9d, 80004003h
0x1800166cf  mov     r8d, 44Ah
0x1800166d5  mov     ebx, r9d
0x1800166d8  jmp     short loc_1800166AD
0x1800166da  lea     rdx, [rbp+57h+var_48]; struct IXMLDOMElement **
0x1800166de  mov     rcx, rax; struct IXMLDOMDocument2 *
0x1800166e1  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x1800166e6  mov     ebx, eax
0x1800166e8  test    eax, eax
0x1800166ea  jns     short loc_18001670F
0x1800166ec  mov     r8d, 44Dh; int
0x1800166f2  mov     r9d, eax; int
0x1800166f5  mov     ecx, 1; Level
0x1800166fa  lea     rdx, aDiagpackagePar_0; "DiagPackage::ParsePackageXml"
0x180016701  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180016706  mov     r14, [rbp+57h+var_90]
0x18001670a  jmp     loc_1800167BC
0x18001670f  mov     rdi, [rbp+57h+var_48]
0x180016713  lea     r8, [rbp+57h+String2]; int *
0x180016717  mov     rcx, rdi; struct IXMLDOMNode *
0x18001671a  lea     rdx, aLocalized; "Localized"
0x180016721  call    ?SdpCheckBooleanAttribute@@YAJPEAUIXMLDOMNode@@PEBGPEAH@Z; SdpCheckBooleanAttribute(IXMLDOMNode *,ushort const *,int *)
0x180016726  mov     ebx, eax
0x180016728  test    eax, eax
0x18001672a  jns     short loc_180016734
0x18001672c  mov     r8d, 452h
0x180016732  jmp     short loc_1800166F2
0x180016734  mov     rcx, [r14+8]
0x180016738  mov     eax, [rcx+38h]
0x18001673b  cmp     dword ptr [rbp+57h+String2], esi
0x18001673e  jz      short loc_180016745
0x180016740  or      eax, 4
0x180016743  jmp     short loc_180016748
0x180016745  and     eax, 0FFFFFFFBh
0x180016748  mov     [rcx+38h], eax
0x18001674b  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x18001674f  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x180016751  lea     r8, [rbp+57h+var_68]; struct IXMLDOMNodeList **
0x180016755  mov     rdx, rdi; struct IXMLDOMNode *
0x180016758  call    ?SdpXmlGetChildNodes@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@PEAK@Z; SdpXmlGetChildNodes(IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *,ulong *)
0x18001675d  mov     ebx, eax
0x18001675f  test    eax, eax
0x180016761  jns     short loc_180016783
0x180016763  mov     r9d, eax; int
0x180016766  lea     rdx, aDiagpackagePar_0; "DiagPackage::ParsePackageXml"
0x18001676d  mov     r8d, 458h; int
0x180016773  mov     ecx, 1; Level
0x180016778  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001677d  mov     r13, [rbp+57h+var_68]
0x180016781  jmp     short loc_180016706
0x180016783  cmp     [rbp+57h+arg_18], 8
0x180016787  jnb     loc_180016882
0x18001678d  mov     r15d, 80070057h
0x180016793  lea     rdx, aDiagpackagePar_0; "DiagPackage::ParsePackageXml"
0x18001679a  mov     r9d, r15d; int
0x18001679d  mov     r8d, 45Ch; int
0x1800167a3  mov     ecx, 1; Level
0x1800167a8  mov     ebx, r15d
0x1800167ab  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800167b0  mov     r13, [rbp+57h+var_68]
0x1800167b4  mov     r14, [rbp+57h+var_90]
0x1800167b8  mov     r15, [rbp+57h+var_80]
0x1800167bc  mov     rdi, [rbp+57h+var_88]
0x1800167c0  mov     rcx, [rbp+57h+var_48]
0x1800167c4  test    rcx, rcx
0x1800167c7  jz      short loc_1800167D5
0x1800167c9  mov     rax, [rcx]
0x1800167cc  mov     rax, [rax+10h]
0x1800167d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167d5  test    r13, r13
0x1800167d8  jz      short loc_1800167EA
0x1800167da  mov     rax, [r13+0]
0x1800167de  mov     rcx, r13
0x1800167e1  mov     rax, [rax+10h]
0x1800167e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167ea  test    rsi, rsi
0x1800167ed  jz      short loc_1800167FE
0x1800167ef  mov     rax, [rsi]
0x1800167f2  mov     rcx, rsi
0x1800167f5  mov     rax, [rax+10h]
0x1800167f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167fe  test    r15, r15
0x180016801  jz      short loc_180016812
0x180016803  mov     rax, [r15]
0x180016806  mov     rcx, r15
0x180016809  mov     rax, [rax+10h]
0x18001680d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016812  test    r14, r14
0x180016815  jz      short loc_180016826
0x180016817  mov     rax, [r14]
0x18001681a  mov     rcx, r14
0x18001681d  mov     rax, [rax+10h]
0x180016821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016826  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18001682a  test    rcx, rcx
0x18001682d  jz      short loc_180016835
0x18001682f  call    cs:__imp_SysFreeString
0x180016835  test    rdi, rdi
0x180016838  jz      short loc_180016843
0x18001683a  mov     rcx, rdi; bstrString
0x18001683d  call    cs:__imp_SysFreeString
0x180016843  mov     rax, [rbp+57h+Block]
0x180016847  test    rax, rax
0x18001684a  jz      short loc_180016854
0x18001684c  mov     rcx, rax; Block
0x18001684f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016854  mov     rax, [rbp+57h+var_38]
0x180016858  test    rax, rax
0x18001685b  jz      short loc_180016865
0x18001685d  mov     rcx, rax; Block
0x180016860  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016865  mov     eax, ebx
0x180016867  mov     rbx, [rsp+0C0h+arg_0]
0x18001686f  add     rsp, 90h
0x180016876  pop     r15
0x180016878  pop     r14
0x18001687a  pop     r13
0x18001687c  pop     r12
0x18001687e  pop     rdi
0x18001687f  pop     rsi
0x180016880  pop     rbp
0x180016881  retn
0x180016882  mov     r13, [rbp+57h+var_68]
0x180016886  lea     rdx, [rbp+57h+var_78]; struct IXMLDOMNode **
0x18001688a  mov     rcx, r13; struct IXMLDOMNodeList *
0x18001688d  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180016892  mov     ebx, eax
0x180016894  test    eax, eax
0x180016896  jns     short loc_1800168BB
0x180016898  mov     r8d, 464h; int
0x18001689e  mov     ecx, 1; Level
0x1800168a3  lea     rdx, aDiagpackagePar_0; "DiagPackage::ParsePackageXml"
0x1800168aa  mov     r9d, eax; int
0x1800168ad  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800168b2  mov     rsi, [rbp+57h+var_78]
0x1800168b6  jmp     loc_180016706
0x1800168bb  mov     rsi, [rbp+57h+var_78]
0x1800168bf  lea     rdx, aDiagnosticiden; "DiagnosticIdentification"
0x1800168c6  mov     rcx, rsi; struct IXMLDOMNode *
0x1800168c9  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x1800168ce  mov     ebx, eax
0x1800168d0  test    eax, eax
0x1800168d2  jns     short loc_1800168DF
0x1800168d4  mov     r8d, 465h
0x1800168da  jmp     loc_1800166F2
0x1800168df  mov     edi, 1
0x1800168e4  cmp     eax, edi
0x1800168e6  jz      loc_18001709F
0x1800168ec  test    rsi, rsi
0x1800168ef  jz      loc_18001709F
0x1800168f5  lea     r9, [r14+28h]; unsigned __int16 **
0x1800168f9  mov     rcx, rsi; struct IXMLDOMNode *
0x1800168fc  lea     r8, [rbp+57h+var_58]; unsigned __int16 **
0x180016900  lea     rdx, [rbp+57h+bstrString]; unsigned __int16 **
0x180016904  call    ?SdpParseDiagnosticIdentification@@YAJPEAUIXMLDOMNode@@PEAPEAG11@Z; SdpParseDiagnosticIdentification(IXMLDOMNode *,ushort * *,ushort * *,ushort * *)
0x180016909  mov     ebx, eax
0x18001690b  test    eax, eax
0x18001690d  jns     short loc_180016933
0x18001690f  mov     r9d, eax; int
0x180016912  lea     rdx, aDiagpackagePar_0; "DiagPackage::ParsePackageXml"
0x180016919  mov     r8d, 46Bh; int
0x18001691f  mov     ecx, edi; Level
0x180016921  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180016926  mov     rdi, [rbp+57h+var_58]
0x18001692a  mov     r14, [rbp+57h+var_90]
0x18001692e  jmp     loc_1800167C0
0x180016933  mov     rax, [rbp+57h+var_58]
0x180016937  lea     rdx, [rbp+57h+Block]; unsigned __int16 **
0x18001693b  xor     ecx, ecx
0x18001693d  mov     [r14+58h], rax
0x180016941  mov     [rbp+57h+var_88], rcx
0x180016945  mov     rcx, [r14+8]; this
0x180016949  call    ?get_PackageId@Settings@@QEAAJPEAPEAG@Z; Settings::get_PackageId(ushort * *)
0x18001694e  test    eax, eax
0x180016950  js      short loc_18001698A
0x180016952  mov     rax, [rbp+57h+Block]
0x180016956  mov     r8, [rbp+57h+bstrString]
0x18001695a  sub     r8, rax
0x18001695d  movzx   edx, word ptr [rax]
0x180016960  movzx   ecx, word ptr [rax+r8]
0x180016965  sub     edx, ecx
0x180016967  jnz     short loc_180016971
0x180016969  add     rax, 2
0x18001696d  test    ecx, ecx
0x18001696f  jnz     short loc_18001695D
0x180016971  test    edx, edx
0x180016973  jz      short loc_1800169E2
0x180016975  mov     ebx, 8000FFFFh
0x18001697a  mov     r8d, 47Ah
0x180016980  mov     r9d, ebx
0x180016983  mov     ecx, edi
0x180016985  jmp     loc_1800166FA
0x18001698a  mov     rcx, [r14+8]; this
0x18001698e  lea     rdx, [rbp+57h+var_38]; unsigned __int16 **
0x180016992  call    ?get_Locale@Settings@@QEAAJPEAPEAG@Z; Settings::get_Locale(ushort * *)
0x180016997  mov     ebx, eax
0x180016999  test    eax, eax
0x18001699b  jns     short loc_1800169A8
0x18001699d  mov     r9d, eax
0x1800169a0  mov     r8d, 485h
0x1800169a6  jmp     short loc_180016983
0x1800169a8  mov     rcx, [r14+8]; this
0x1800169ac  cmp     [rbp+57h+var_38], r15
0x1800169b0  jz      short loc_1800169C8
0x1800169b2  test    dword ptr [rcx+38h], 200h
0x1800169b9  jnz     short loc_1800169C8
0x1800169bb  xor     ebx, ebx
0x1800169bd  mov     r8d, 48Bh
0x1800169c3  xor     r9d, r9d
0x1800169c6  jmp     short loc_180016983
0x1800169c8  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x1800169cc  call    ?set_PackageId@Settings@@QEAAJPEBG@Z; Settings::set_PackageId(ushort const *)
0x1800169d1  mov     ebx, eax
0x1800169d3  test    eax, eax
0x1800169d5  jns     short loc_1800169E2
0x1800169d7  mov     r9d, eax
0x1800169da  mov     r8d, 48Fh
0x1800169e0  jmp     short loc_180016983
0x1800169e2  mov     rax, [rsi]
0x1800169e5  mov     rcx, rsi
0x1800169e8  mov     rax, [rax+10h]
0x1800169ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169f1  lea     rdx, [rbp+57h+var_78]; struct IXMLDOMNode **
0x1800169f5  mov     [rbp+57h+var_78], r15
0x1800169f9  mov     rcx, r13; struct IXMLDOMNodeList *
0x1800169fc  call    ?SdpXmlNextNode@@YAJPEAUIXMLDOMNodeList@@PEAPEAUIXMLDOMNode@@@Z; SdpXmlNextNode(IXMLDOMNodeList *,IXMLDOMNode * *)
0x180016a01  mov     ebx, eax
0x180016a03  test    eax, eax
0x180016a05  jns     short loc_180016A14
0x180016a07  mov     r8d, 498h
0x180016a0d  mov     ecx, edi
0x180016a0f  jmp     loc_1800168A3
0x180016a14  mov     rsi, [rbp+57h+var_78]
0x180016a18  lea     rdx, aDisplayinforma; "DisplayInformation"
0x180016a1f  mov     rcx, rsi; struct IXMLDOMNode *
0x180016a22  call    ?SdpXmlCheckNode@@YAJPEAUIXMLDOMNode@@PEBG@Z; SdpXmlCheckNode(IXMLDOMNode *,ushort const *)
0x180016a27  mov     ebx, eax
0x180016a29  test    eax, eax
0x180016a2b  jns     short loc_180016A3B
0x180016a2d  mov     r9d, eax
0x180016a30  mov     r8d, 499h
0x180016a36  jmp     loc_180016983
0x180016a3b  cmp     eax, edi
0x180016a3d  jz      loc_180017091
0x180016a43  test    rsi, rsi
0x180016a46  jz      loc_180017091
0x180016a4c  lea     rdx, [r14+30h]; struct _SDIAG_DISPINFO *
0x180016a50  mov     rcx, rsi; struct IXMLDOMNode *
0x180016a53  call    ?SdpParseDisplayInformation@@YAJPEAUIXMLDOMNode@@PEAU_SDIAG_DISPINFO@@@Z; SdpParseDisplayInformation(IXMLDOMNode *,_SDIAG_DISPINFO *)
0x180016a58  mov     ebx, eax
0x180016a5a  test    eax, eax
0x180016a5c  jns     short loc_180016A7A
0x180016a5e  mov     r8d, 49Ch; int
0x180016a64  mov     r9d, eax; int
0x180016a67  lea     rdx, aDiagpackagePar_0; "DiagPackage::ParsePackageXml"
0x180016a6e  mov     ecx, edi; Level
  ... truncated ...
```
