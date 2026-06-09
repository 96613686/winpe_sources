# IASExim::ExportRegistry(ushort *,ushort *)

- ea: `0x18003a880`
- end: `0x18003b315`
- name: `?ExportRegistry@IASExim@@AEAAJPEAG0@Z`
- size: `2709`
- prototype: `int(IASExim *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a6fc`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002f08c`
- `0x18002f240`
- `0x180039cc0`
- `0x18003a560`
- `0x18003a880`
- `0x18003b8ac`
- `0x18003d8b4`
- `0x18003d9b0`
- `0x1800404a4`
- `0x180041bb0`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `ADVAPI32!RegConnectRegistryW` at `0x18003a990`
- `ADVAPI32!RegConnectRegistryW` at `0x18003a990`
- `ADVAPI32!RegCloseKey` at `0x18003b2d2`
- `ADVAPI32!RegCloseKey` at `0x18003b2d2`
- `OLEAUT32!__imp_SysAllocString` at `0x18003a8dd`
- `OLEAUT32!__imp_SysAllocString` at `0x18003a8dd`
- `OLEAUT32!__imp_VariantInit` at `0x18003a8cc`
- `OLEAUT32!__imp_VariantInit` at `0x18003aa9a`
- `OLEAUT32!__imp_VariantInit` at `0x18003a8cc`
- `OLEAUT32!__imp_VariantInit` at `0x18003aa9a`
- `OLEAUT32!__imp_VariantClear` at `0x18003b2dc`
- `OLEAUT32!__imp_VariantClear` at `0x18003b2dc`

## string_xrefs

- `0x18003a9f5`: `registryKeys`
- `0x18003ab04`: `registryKey`
- `0x18003ab92`: `registryValue`
- `0x18003a9cd`: `RegConnectRegistry failed with 0x%x`
- `0x18003b28d`: `m_pXmlDom->save failed with 0x%x`
- `0x18003aa46`: `CreateAndAppendNode(%S) failed with 0x%x`
- `0x18003b103`: `GetRegistryValue(%S\%S) failed with 0x%x`
- `0x18003b013`: `CreateAndAppendNode(RegistryKeyNode) failed with 0x%x`
- `0x18003afb0`: `pRegistryKeyNode->QueryInterface(IXMLDOMElement) failed with 0x%x`
- `0x18003af52`: `SetStringAttribute(pRegistryKeyElement,%S) failed with 0x%x`
- `0x18003ae8f`: `CreateAndAppendNode(RegistryValueNode) failed with 0x%x`
- `0x18003ae2c`: `pRegistryValueNode->QueryInterface(IXMLDOMElement) failed with 0x%x`
- `0x18003ad77`: `SetStringAttribute(RegistryValueElement,%S) failed with 0x%x`
- `0x18003adce`: `SetStringAttribute(RegistryValueElement,%S) failed with 0x%x`
- `0x18003ad2d`: `pRegistryValueElement->setAttribute failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall IASExim::ExportRegistry(struct IXMLDOMDocument2 **this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  signed int DocumentRootElement; // ebx
  int v7; // r13d
  LSTATUS v8; // r15d
  unsigned int i; // edi
  int RegistryValue; // r15d
  int v11; // edx
  int v12; // edx
  int appended; // eax
  char v14; // bl
  int v15; // eax
  char v16; // bl
  struct IXMLDOMDocument2 *v17; // rcx
  struct IXMLDOMElement *v19; // [rsp+40h] [rbp-49h] BYREF
  struct IXMLDOMNode *v20; // [rsp+48h] [rbp-41h] BYREF
  VARIANTARG v21; // [rsp+50h] [rbp-39h] BYREF
  struct IXMLDOMNode *v22; // [rsp+70h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-11h] BYREF
  struct IXMLDOMNode *v24; // [rsp+80h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-1h] BYREF
  VARIANTARG v26; // [rsp+A0h] [rbp+17h] BYREF
  struct IXMLDOMNode *v27; // [rsp+F0h] [rbp+67h] BYREF
  struct IXMLDOMElement *v28; // [rsp+108h] [rbp+7Fh] BYREF

  v22 = 0;
  hKey = HKEY_LOCAL_MACHINE;
  v24 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(a3);
  v21 = pvarg;
  DocumentRootElement = GetDocumentRootElement(this[1], &v21, (struct IXMLDOMElement **)&v24);
  if ( DocumentRootElement < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("GetDocumentRootElement failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        DocumentRootElement);
    }
    goto LABEL_116;
  }
  v7 = 0;
  if ( a2 && *a2 )
  {
    v8 = RegConnectRegistryW(a2, hKey, &hKey);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("RegConnectRegistry failed with 0x%x");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
          (unsigned int)"NPSSDO",
          v8);
      }
      goto LABEL_116;
    }
    v7 = 1;
  }
  DocumentRootElement = CreateAndAppendNode(this[1], v24, L"registryKeys", &v22);
  if ( DocumentRootElement >= 0 )
  {
    for ( i = 0; i < 0x17; ++i )
    {
      VariantInit(&v21);
      RegistryValue = GetRegistryValue(
                        hKey,
                        IASKEYS[3 * (int)i],
                        IASKEYS[3 * (int)i + 2],
                        IASKEYS[3 * (int)i + 1],
                        &v21);
      if ( RegistryValue != 2 )
      {
        if ( RegistryValue )
        {
          if ( RegistryValue > 0 )
            DocumentRootElement = (unsigned __int16)RegistryValue | 0x80070000;
          else
            DocumentRootElement = RegistryValue;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("GetRegistryValue(%S\\%S) failed with 0x%x");
            WPP_SF_sSSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (__int64)IASKEYS[3 * (int)i],
              (__int64)IASKEYS[3 * (int)i + 1],
              RegistryValue);
          }
          goto LABEL_95;
        }
        DocumentRootElement = AppendNewLine(this[1], v22, 2u);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("AppendNewLine failed with 0x%x");
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              67,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              DocumentRootElement);
          }
          goto LABEL_95;
        }
        v27 = 0;
        DocumentRootElement = CreateAndAppendNode(this[1], v22, L"registryKey", &v27);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("CreateAndAppendNode(RegistryKeyNode) failed with 0x%x");
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              68,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              DocumentRootElement);
          }
          goto LABEL_83;
        }
        v28 = 0;
        DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMNode *, GUID *, struct IXMLDOMElement **))v27->lpVtbl->QueryInterface)(
                                v27,
                                &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
                                &v28);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          {
            goto LABEL_78;
          }
          WppDbgPrint("pRegistryKeyNode->QueryInterface(IXMLDOMElement) failed with 0x%x");
          v12 = 69;
LABEL_77:
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
            (unsigned int)"NPSSDO",
            DocumentRootElement);
          goto LABEL_78;
        }
        DocumentRootElement = SetStringAttribute(v28, L"keyName", IASKEYS[3 * (int)i]);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("SetStringAttribute(pRegistryKeyElement,%S) failed with 0x%x");
            WPP_SF_sSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              70,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              (__int64)L"keyName",
              DocumentRootElement);
          }
          goto LABEL_78;
        }
        DocumentRootElement = AppendNewLine(this[1], v27, 3u);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          {
            goto LABEL_78;
          }
          WppDbgPrint("AppendNewLine failed with 0x%x");
          v12 = 71;
          goto LABEL_77;
        }
        v20 = 0;
        DocumentRootElement = CreateAndAppendNode(this[1], v27, L"registryValue", &v20);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("CreateAndAppendNode(RegistryValueNode) failed with 0x%x");
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              72,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              DocumentRootElement);
          }
          goto LABEL_64;
        }
        v19 = 0;
        DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMNode *, GUID *, struct IXMLDOMElement **))v20->lpVtbl->QueryInterface)(
                                v20,
                                &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
                                &v19);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          {
            goto LABEL_59;
          }
          WppDbgPrint("pRegistryValueNode->QueryInterface(IXMLDOMElement) failed with 0x%x");
          v11 = 73;
LABEL_58:
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v11,
            (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
            (unsigned int)"NPSSDO",
            DocumentRootElement);
          goto LABEL_59;
        }
        DocumentRootElement = SetStringAttribute(v19, L"name", IASKEYS[3 * (int)i + 1]);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("SetStringAttribute(RegistryValueElement,%S) failed with 0x%x");
            WPP_SF_sSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              74,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              (__int64)L"name",
              DocumentRootElement);
          }
          goto LABEL_59;
        }
        DocumentRootElement = SetStringAttribute(v19, L"valueType", IASKEYS[3 * (int)i + 2]);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("SetStringAttribute(RegistryValueElement,%S) failed with 0x%x");
            WPP_SF_sSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              75,
              (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
              (unsigned int)"NPSSDO",
              (__int64)L"valueType",
              DocumentRootElement);
          }
          goto LABEL_59;
        }
        v26 = v21;
        DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const wchar_t *, VARIANTARG *))v19->lpVtbl->setAttribute)(
                                v19,
                                L"value",
                                &v26);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          {
            goto LABEL_59;
          }
          WppDbgPrint("pRegistryValueElement->setAttribute failed with 0x%x");
          v11 = 76;
          goto LABEL_58;
        }
        DocumentRootElement = AppendNewLine(this[1], v27, 2u);
        if ( DocumentRootElement < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("AppendNewLine failed with 0x%x");
            v11 = 77;
            goto LABEL_58;
          }
LABEL_59:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
LABEL_64:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
LABEL_78:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
LABEL_83:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
LABEL_95:
          _variant_t::~_variant_t((_variant_t *)&v21);
          goto LABEL_114;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
      }
      _variant_t::~_variant_t((_variant_t *)&v21);
    }
    appended = AppendNewLine(this[1], v22, 1u);
    v14 = appended;
    if ( appended < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("AppendNewLine failed with 0x%x");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          78,
          (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
          (unsigned int)"NPSSDO",
          v14);
      }
      TraceXMLFailure(this[1]);
    }
    v15 = AppendNewLine(this[1], v24, 0);
    v16 = v15;
    if ( v15 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("AppendNewLine failed with 0x%x");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          79,
          (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
          (unsigned int)"NPSSDO",
          v16);
      }
      TraceXMLFailure(this[1]);
    }
    v17 = this[1];
    v26 = pvarg;
    DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))v17->lpVtbl->save)(
                            v17,
                            &v26);
    if ( DocumentRootElement < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("m_pXmlDom->save failed with 0x%x");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          80,
          (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
          (unsigned int)"NPSSDO",
          DocumentRootElement);
      }
      TraceXMLFailure(this[1]);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("CreateAndAppendNode(%S) failed with 0x%x");
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      65,
      (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
      (unsigned int)"NPSSDO",
      (__int64)L"registryKeys",
      DocumentRootElement);
  }
LABEL_114:
  if ( v7 )
    RegCloseKey(hKey);
LABEL_116:
  VariantClear(&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
  return (unsigned int)DocumentRootElement;
}

```

## disassembly

```asm
0x18003a880  mov     [rsp-8+arg_8], rbx
0x18003a885  mov     [rsp-8+arg_10], rdi
0x18003a88a  push    rbp
0x18003a88b  push    r12
0x18003a88d  push    r13
0x18003a88f  push    r14
0x18003a891  push    r15
0x18003a893  lea     rbp, [rsp-37h]
0x18003a898  sub     rsp, 0C0h
0x18003a89f  mov     rbx, r8
0x18003a8a2  mov     rdi, rdx
0x18003a8a5  mov     r14, rcx
0x18003a8a8  xor     r15d, r15d
0x18003a8ab  mov     [rbp+57h+var_70], r15
0x18003a8af  mov     [rbp+57h+hKey], 0FFFFFFFF80000002h
0x18003a8b7  mov     [rbp+57h+var_60], r15
0x18003a8bb  xorps   xmm0, xmm0
0x18003a8be  xor     eax, eax
0x18003a8c0  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18003a8c4  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18003a8c8  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003a8cc  call    cs:__imp_VariantInit
0x18003a8d2  lea     eax, [r15+8]
0x18003a8d6  mov     word ptr [rbp+57h+pvarg], ax
0x18003a8da  mov     rcx, rbx; psz
0x18003a8dd  call    cs:__imp_SysAllocString
0x18003a8e3  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18003a8e7  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18003a8eb  movaps  xmmword ptr [rbp+57h+var_90], xmm0
0x18003a8ef  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18003a8f4  movsd   qword ptr [rbp+57h+var_90+10h], xmm1
0x18003a8f9  lea     r8, [rbp+57h+var_60]; struct IXMLDOMElement **
0x18003a8fd  lea     rdx, [rbp+57h+var_90]; struct tagVARIANT
0x18003a901  mov     rcx, [r14+8]; struct IXMLDOMDocument2 *
0x18003a905  call    ?GetDocumentRootElement@@YAJPEAUIXMLDOMDocument2@@UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z; GetDocumentRootElement(IXMLDOMDocument2 *,tagVARIANT,IXMLDOMElement * *)
0x18003a90a  mov     ebx, eax
0x18003a90c  test    eax, eax
0x18003a90e  jns     short loc_18003A977
0x18003a910  lea     rdi, WPP_GLOBAL_Control
0x18003a917  mov     rax, cs:WPP_GLOBAL_Control
0x18003a91e  cmp     rax, rdi
0x18003a921  jz      loc_18003B2D8
0x18003a927  cmp     byte ptr [rax+19h], 2
0x18003a92b  jb      loc_18003B2D8
0x18003a931  test    dword ptr [rax+1Ch], 400h
0x18003a938  jz      loc_18003B2D8
0x18003a93e  mov     edx, ebx
0x18003a940  lea     rcx, aGetdocumentroo; "GetDocumentRootElement failed with 0x%x"
0x18003a947  call    WppDbgPrint
0x18003a94c  lea     edx, [r15+3Fh]
0x18003a950  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18003a954  lea     r9, aNpssdo; "NPSSDO"
0x18003a95b  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003a962  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a969  mov     rcx, [rcx+10h]
0x18003a96d  call    WPP_SF_sd
0x18003a972  jmp     loc_18003B2D8
0x18003a977  mov     r13d, r15d
0x18003a97a  test    rdi, rdi
0x18003a97d  jz      short loc_18003A9F1
0x18003a97f  cmp     [rdi], r15w
0x18003a983  jz      short loc_18003A9F1
0x18003a985  lea     r8, [rbp+57h+hKey]; phkResult
0x18003a989  mov     rdx, [rbp+57h+hKey]; hKey
0x18003a98d  mov     rcx, rdi; lpMachineName
0x18003a990  call    cs:__imp_RegConnectRegistryW
0x18003a996  mov     r15d, eax
0x18003a999  test    eax, eax
0x18003a99b  jz      short loc_18003A9E8
0x18003a99d  lea     rdi, WPP_GLOBAL_Control
0x18003a9a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a9ab  cmp     rcx, rdi
0x18003a9ae  jz      loc_18003B2D8
0x18003a9b4  cmp     byte ptr [rcx+19h], 2
0x18003a9b8  jb      loc_18003B2D8
0x18003a9be  test    dword ptr [rcx+1Ch], 400h
0x18003a9c5  jz      loc_18003B2D8
0x18003a9cb  mov     edx, eax
0x18003a9cd  lea     rcx, aRegconnectregi; "RegConnectRegistry failed with 0x%x"
0x18003a9d4  call    WppDbgPrint
0x18003a9d9  mov     edx, 40h ; '@'
0x18003a9de  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x18003a9e3  jmp     loc_18003A954
0x18003a9e8  mov     r13d, 1
0x18003a9ee  xor     r15d, r15d
0x18003a9f1  lea     r9, [rbp+57h+var_70]; struct IXMLDOMNode **
0x18003a9f5  lea     r12, aRegistrykeys; "registryKeys"
0x18003a9fc  mov     r8, r12; unsigned __int16 *
0x18003a9ff  mov     rdx, [rbp+57h+var_60]; struct IXMLDOMNode *
0x18003aa03  mov     rcx, [r14+8]; struct IXMLDOMDocument2 *
0x18003aa07  call    ?CreateAndAppendNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAGPEAPEAU2@@Z; CreateAndAppendNode(IXMLDOMDocument2 *,IXMLDOMNode *,ushort *,IXMLDOMNode * *)
0x18003aa0c  mov     ebx, eax
0x18003aa0e  test    eax, eax
0x18003aa10  jns     short loc_18003AA83
0x18003aa12  lea     rdi, WPP_GLOBAL_Control
0x18003aa19  mov     rax, cs:WPP_GLOBAL_Control
0x18003aa20  cmp     rax, rdi
0x18003aa23  jz      loc_18003B2C9
0x18003aa29  cmp     byte ptr [rax+19h], 2
0x18003aa2d  jb      loc_18003B2C9
0x18003aa33  test    dword ptr [rax+1Ch], 400h
0x18003aa3a  jz      loc_18003B2C9
0x18003aa40  mov     r8d, ebx
0x18003aa43  mov     rdx, r12
0x18003aa46  lea     rcx, aCreateandappen_1; "CreateAndAppendNode(%S) failed with 0x%"...
0x18003aa4d  call    WppDbgPrint
0x18003aa52  mov     edx, 41h ; 'A'
0x18003aa57  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x18003aa5b  mov     [rsp+0E0h+var_C0], r12
0x18003aa60  lea     r9, aNpssdo; "NPSSDO"
0x18003aa67  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003aa6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aa75  mov     rcx, [rcx+10h]
0x18003aa79  call    WPP_SF_sSd
0x18003aa7e  jmp     loc_18003B2C9
0x18003aa83  mov     edi, r15d
0x18003aa86  lea     rbx, IASKEYS
0x18003aa8d  cmp     edi, 17h
0x18003aa90  jnb     loc_18003B159
0x18003aa96  lea     rcx, [rbp+57h+var_90]; pvarg
0x18003aa9a  call    cs:__imp_VariantInit
0x18003aaa0  nop
0x18003aaa1  movsxd  rax, edi
0x18003aaa4  lea     r12, [rax+rax*2]
0x18003aaa8  lea     rax, [rbp+57h+var_90]
0x18003aaac  mov     [rsp+0E0h+var_C0], rax
0x18003aab1  mov     r9, [rbx+r12*8+8]
0x18003aab6  mov     r8, [rbx+r12*8+10h]
0x18003aabb  mov     rdx, [rbx+r12*8]
0x18003aabf  mov     rcx, [rbp+57h+hKey]
0x18003aac3  call    GetRegistryValue
0x18003aac8  mov     r15d, eax
0x18003aacb  cmp     eax, 2
0x18003aace  jnz     short loc_18003AAD5
0x18003aad0  jmp     loc_18003ACA7
0x18003aad5  test    r15d, r15d
0x18003aad8  jnz     loc_18003B0BD
0x18003aade  lea     r8d, [r15+2]; unsigned int
0x18003aae2  mov     rdx, [rbp+57h+var_70]; struct IXMLDOMNode *
0x18003aae6  mov     rcx, [r14+8]; struct IXMLDOMDocument2 *
0x18003aaea  call    ?AppendNewLine@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@K@Z; AppendNewLine(IXMLDOMDocument2 *,IXMLDOMNode *,ulong)
0x18003aaef  mov     ebx, eax
0x18003aaf1  xor     r15d, r15d
0x18003aaf4  test    eax, eax
0x18003aaf6  js      loc_18003B055
0x18003aafc  mov     [rbp+57h+arg_0], r15
0x18003ab00  lea     r9, [rbp+57h+arg_0]; struct IXMLDOMNode **
0x18003ab04  lea     r8, aRegistrykey; "registryKey"
0x18003ab0b  mov     rdx, [rbp+57h+var_70]; struct IXMLDOMNode *
0x18003ab0f  mov     rcx, [r14+8]; struct IXMLDOMDocument2 *
0x18003ab13  call    ?CreateAndAppendNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAGPEAPEAU2@@Z; CreateAndAppendNode(IXMLDOMDocument2 *,IXMLDOMNode *,ushort *,IXMLDOMNode * *)
0x18003ab18  mov     ebx, eax
0x18003ab1a  test    eax, eax
0x18003ab1c  js      loc_18003AFEF
0x18003ab22  mov     [rbp+57h+arg_18], r15
0x18003ab26  mov     rcx, [rbp+57h+arg_0]
0x18003ab2a  mov     rax, [rcx]
0x18003ab2d  lea     r8, [rbp+57h+arg_18]
0x18003ab31  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18003ab38  mov     rax, [rax]
0x18003ab3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab40  mov     ebx, eax
0x18003ab42  test    eax, eax
0x18003ab44  js      loc_18003AF8C
0x18003ab4a  lea     r8, IASKEYS
0x18003ab51  mov     r8, [r8+r12*8]; unsigned __int16 *
0x18003ab55  lea     rdx, aKeyname; "keyName"
0x18003ab5c  mov     rcx, [rbp+57h+arg_18]; struct IXMLDOMElement *
0x18003ab60  call    ?SetStringAttribute@@YAJPEAUIXMLDOMElement@@PEAG1@Z; SetStringAttribute(IXMLDOMElement *,ushort *,ushort *)
0x18003ab65  mov     ebx, eax
0x18003ab67  test    eax, eax
0x18003ab69  js      loc_18003AF17
0x18003ab6f  lea     r8d, [r15+3]; unsigned int
0x18003ab73  mov     rdx, [rbp+57h+arg_0]; struct IXMLDOMNode *
0x18003ab77  mov     rcx, [r14+8]; struct IXMLDOMDocument2 *
0x18003ab7b  call    ?AppendNewLine@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@K@Z; AppendNewLine(IXMLDOMDocument2 *,IXMLDOMNode *,ulong)
0x18003ab80  mov     ebx, eax
0x18003ab82  test    eax, eax
0x18003ab84  js      loc_18003AED1
0x18003ab8a  mov     [rbp+57h+var_98], r15
0x18003ab8e  lea     r9, [rbp+57h+var_98]; struct IXMLDOMNode **
0x18003ab92  lea     r8, aRegistryvalue; "registryValue"
0x18003ab99  mov     rdx, [rbp+57h+arg_0]; struct IXMLDOMNode *
0x18003ab9d  mov     rcx, [r14+8]; struct IXMLDOMDocument2 *
0x18003aba1  call    ?CreateAndAppendNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAGPEAPEAU2@@Z; CreateAndAppendNode(IXMLDOMDocument2 *,IXMLDOMNode *,ushort *,IXMLDOMNode * *)
0x18003aba6  mov     ebx, eax
0x18003aba8  test    eax, eax
0x18003abaa  js      loc_18003AE6B
0x18003abb0  mov     [rbp+57h+var_A0], r15
0x18003abb4  mov     rcx, [rbp+57h+var_98]
0x18003abb8  mov     rax, [rcx]
0x18003abbb  lea     r8, [rbp+57h+var_A0]
0x18003abbf  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18003abc6  mov     rax, [rax]
0x18003abc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abce  mov     ebx, eax
0x18003abd0  test    eax, eax
0x18003abd2  js      loc_18003AE08
0x18003abd8  lea     rax, IASKEYS
0x18003abdf  mov     r8, [rax+r12*8+8]; unsigned __int16 *
0x18003abe4  lea     rdx, aName; "name"
0x18003abeb  mov     rcx, [rbp+57h+var_A0]; struct IXMLDOMElement *
0x18003abef  call    ?SetStringAttribute@@YAJPEAUIXMLDOMElement@@PEAG1@Z; SetStringAttribute(IXMLDOMElement *,ushort *,ushort *)
0x18003abf4  mov     ebx, eax
0x18003abf6  test    eax, eax
0x18003abf8  js      loc_18003AD93
0x18003abfe  lea     rax, IASKEYS
0x18003ac05  mov     r8, [rax+r12*8+10h]; unsigned __int16 *
0x18003ac0a  lea     r12, aValuetype; "valueType"
0x18003ac11  mov     rdx, r12; unsigned __int16 *
0x18003ac14  mov     rcx, [rbp+57h+var_A0]; struct IXMLDOMElement *
0x18003ac18  call    ?SetStringAttribute@@YAJPEAUIXMLDOMElement@@PEAG1@Z; SetStringAttribute(IXMLDOMElement *,ushort *,ushort *)
0x18003ac1d  mov     ebx, eax
0x18003ac1f  test    eax, eax
0x18003ac21  js      loc_18003AD43
0x18003ac27  mov     rcx, [rbp+57h+var_A0]
0x18003ac2b  movups  xmm0, xmmword ptr [rbp+57h+var_90]
0x18003ac2f  movaps  [rbp+57h+var_40], xmm0
0x18003ac33  movsd   xmm1, qword ptr [rbp+57h+var_90+10h]
0x18003ac38  movsd   [rbp+57h+var_30], xmm1
0x18003ac3d  mov     rax, [rcx]
0x18003ac40  lea     r8, [rbp+57h+var_40]
0x18003ac44  lea     rdx, aValue; "value"
0x18003ac4b  mov     rax, [rax+168h]
0x18003ac52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac57  mov     ebx, eax
0x18003ac59  test    eax, eax
0x18003ac5b  js      loc_18003ACFD
0x18003ac61  lea     r8d, [r15+2]; unsigned int
0x18003ac65  mov     rdx, [rbp+57h+arg_0]; struct IXMLDOMNode *
0x18003ac69  mov     rcx, [r14+8]; struct IXMLDOMDocument2 *
0x18003ac6d  call    ?AppendNewLine@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@K@Z; AppendNewLine(IXMLDOMDocument2 *,IXMLDOMNode *,ulong)
0x18003ac72  mov     ebx, eax
0x18003ac74  test    eax, eax
0x18003ac76  js      short loc_18003ACB7
0x18003ac78  lea     rcx, [rbp+57h+var_A0]
0x18003ac7c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003ac81  nop
0x18003ac82  lea     rcx, [rbp+57h+var_98]
0x18003ac86  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003ac8b  nop
0x18003ac8c  lea     rcx, [rbp+57h+arg_18]
0x18003ac90  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003ac95  nop
0x18003ac96  lea     rcx, [rbp+57h+arg_0]
0x18003ac9a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003ac9f  nop
0x18003aca0  lea     rbx, IASKEYS
0x18003aca7  lea     rcx, [rbp+57h+var_90]; this
0x18003acab  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18003acb0  inc     edi
0x18003acb2  jmp     loc_18003AA8D
0x18003acb7  lea     rdi, WPP_GLOBAL_Control
0x18003acbe  mov     rax, cs:WPP_GLOBAL_Control
0x18003acc5  cmp     rax, rdi
0x18003acc8  jz      loc_18003AE60
0x18003acce  cmp     byte ptr [rax+19h], 2
0x18003acd2  jb      loc_18003AE60
0x18003acd8  test    dword ptr [rax+1Ch], 400h
0x18003acdf  jz      loc_18003AE60
0x18003ace5  mov     edx, ebx
0x18003ace7  lea     rcx, aAppendnewlineF; "AppendNewLine failed with 0x%x"
0x18003acee  call    WppDbgPrint
0x18003acf3  mov     edx, 4Dh ; 'M'
0x18003acf8  jmp     loc_18003AE3D
0x18003acfd  lea     rdi, WPP_GLOBAL_Control
0x18003ad04  mov     rax, cs:WPP_GLOBAL_Control
0x18003ad0b  cmp     rax, rdi
0x18003ad0e  jz      loc_18003AE60
0x18003ad14  cmp     byte ptr [rax+19h], 2
0x18003ad18  jb      loc_18003AE60
0x18003ad1e  test    dword ptr [rax+1Ch], 400h
0x18003ad25  jz      loc_18003AE60
0x18003ad2b  mov     edx, ebx
0x18003ad2d  lea     rcx, aPregistryvalue; "pRegistryValueElement->setAttribute fai"...
0x18003ad34  call    WppDbgPrint
0x18003ad39  mov     edx, 4Ch ; 'L'
0x18003ad3e  jmp     loc_18003AE3D
0x18003ad43  lea     rdi, WPP_GLOBAL_Control
0x18003ad4a  mov     rax, cs:WPP_GLOBAL_Control
0x18003ad51  cmp     rax, rdi
0x18003ad54  jz      loc_18003AE60
0x18003ad5a  cmp     byte ptr [rax+19h], 2
0x18003ad5e  jb      loc_18003AE60
0x18003ad64  test    dword ptr [rax+1Ch], 400h
0x18003ad6b  jz      loc_18003AE60
0x18003ad71  mov     r8d, ebx
0x18003ad74  mov     rdx, r12
0x18003ad77  lea     rcx, aSetstringattri_0; "SetStringAttribute(RegistryValueElement"...
0x18003ad7e  call    WppDbgPrint
0x18003ad83  mov     edx, 4Bh ; 'K'
0x18003ad88  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x18003ad8c  mov     [rsp+0E0h+var_C0], r12
0x18003ad91  jmp     short loc_18003ADE8
0x18003ad93  lea     rdi, WPP_GLOBAL_Control
0x18003ad9a  mov     rax, cs:WPP_GLOBAL_Control
0x18003ada1  cmp     rax, rdi
0x18003ada4  jz      loc_18003AE60
0x18003adaa  cmp     byte ptr [rax+19h], 2
0x18003adae  jb      loc_18003AE60
  ... truncated ...
```
