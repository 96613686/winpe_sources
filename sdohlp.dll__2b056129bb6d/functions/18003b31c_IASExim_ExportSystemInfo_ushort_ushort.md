# IASExim::ExportSystemInfo(ushort *,ushort *)

- ea: `0x18003b31c`
- end: `0x18003b8a4`
- name: `?ExportSystemInfo@IASExim@@AEAAJPEAG0@Z`
- size: `1416`
- prototype: `int(IASExim *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a6fc`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002f08c`
- `0x180039cc0`
- `0x18003a560`
- `0x18003b31c`
- `0x18003b8ac`
- `0x18003d9b0`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x18003b4bf`
- `KERNEL32!GetSystemInfo` at `0x18003b4bf`
- `OLEAUT32!__imp_SysAllocString` at `0x18003b374`
- `OLEAUT32!__imp_SysAllocString` at `0x18003b374`
- `OLEAUT32!__imp_VariantInit` at `0x18003b362`
- `OLEAUT32!__imp_VariantInit` at `0x18003b362`
- `OLEAUT32!__imp_VariantClear` at `0x18003b576`
- `OLEAUT32!__imp_VariantClear` at `0x18003b62d`
- `OLEAUT32!__imp_VariantClear` at `0x18003b6e4`
- `OLEAUT32!__imp_VariantClear` at `0x18003b6f3`
- `OLEAUT32!__imp_VariantClear` at `0x18003b6fe`
- `OLEAUT32!__imp_VariantClear` at `0x18003b709`
- `OLEAUT32!__imp_VariantClear` at `0x18003b870`
- `OLEAUT32!__imp_VariantClear` at `0x18003b576`
- `OLEAUT32!__imp_VariantClear` at `0x18003b62d`
- `OLEAUT32!__imp_VariantClear` at `0x18003b6e4`
- `OLEAUT32!__imp_VariantClear` at `0x18003b6f3`
- `OLEAUT32!__imp_VariantClear` at `0x18003b6fe`
- `OLEAUT32!__imp_VariantClear` at `0x18003b709`
- `OLEAUT32!__imp_VariantClear` at `0x18003b870`

## string_xrefs

- `0x18003b7d7`: `m_pXmlDom->save failed with 0x%x`
- `0x18003b409`: `CreateAndAppendNode(%S) failed with 0x%x`
- `0x18003b496`: `pSystemInfoNode->QueryInterface(IXMLDOMElement) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall IASExim::ExportSystemInfo(
        struct IXMLDOMDocument2 **this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  int DocumentRootElement; // ebx
  int v6; // edx
  int appended; // eax
  char v8; // bl
  struct IXMLDOMDocument2 *v9; // rcx
  VARIANTARG v11; // [rsp+30h] [rbp-89h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-69h] BYREF
  VARIANTARG v13; // [rsp+70h] [rbp-49h] BYREF
  VARIANTARG v14; // [rsp+90h] [rbp-29h] BYREF
  VARIANTARG v15; // [rsp+A8h] [rbp-11h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+C0h] [rbp+7h] BYREF
  struct IXMLDOMNode *v17; // [rsp+120h] [rbp+67h] BYREF
  __int64 v18; // [rsp+128h] [rbp+6Fh] BYREF
  struct IXMLDOMNode *v19; // [rsp+138h] [rbp+7Fh] BYREF

  v17 = 0;
  v19 = 0;
  v18 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(a3);
  v13 = pvarg;
  DocumentRootElement = GetDocumentRootElement(this[1], &v13, (struct IXMLDOMElement **)&v17);
  if ( DocumentRootElement < 0 || !v17 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_48;
    }
    WppDbgPrint("GetDocumentRootElement failed with 0x%x");
    v6 = 88;
LABEL_47:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
      (unsigned int)"NPSSDO",
      DocumentRootElement);
    goto LABEL_48;
  }
  DocumentRootElement = CreateAndAppendNode(this[1], v17, L"SystemInfo", &v19);
  if ( DocumentRootElement < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("CreateAndAppendNode(%S) failed with 0x%x");
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        (__int64)L"SystemInfo",
        DocumentRootElement);
    }
    goto LABEL_48;
  }
  DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMNode *, GUID *, __int64 *))v19->lpVtbl->QueryInterface)(
                          v19,
                          &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
                          &v18);
  if ( DocumentRootElement < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_48;
    }
    WppDbgPrint("pSystemInfoNode->QueryInterface(IXMLDOMElement) failed with 0x%x");
    v6 = 90;
    goto LABEL_47;
  }
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  v14.vt = 18;
  v14.iVal = SystemInfo.wProcessorArchitecture;
  v11 = v14;
  DocumentRootElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v18 + 360LL))(
                          v18,
                          L"ProcessorArchitecture",
                          &v11);
  if ( DocumentRootElement < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("setAttribute(%S) failed with 0x%x");
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        91,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        (__int64)L"ProcessorArchitecture",
        DocumentRootElement);
    }
    goto LABEL_18;
  }
  v15.vt = 18;
  v15.iVal = SystemInfo.wProcessorLevel;
  v11 = v15;
  DocumentRootElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v18 + 360LL))(
                          v18,
                          L"ProcessorLevel",
                          &v11);
  if ( DocumentRootElement < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("setAttribute(%S) failed with 0x%x");
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        (__int64)L"ProcessorLevel",
        DocumentRootElement);
    }
LABEL_24:
    VariantClear(&v15);
LABEL_18:
    VariantClear(&v14);
    goto LABEL_48;
  }
  v13.vt = 18;
  v13.iVal = SystemInfo.wProcessorRevision;
  v11 = v13;
  DocumentRootElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v18 + 360LL))(
                          v18,
                          L"ProcessorRevision",
                          &v11);
  if ( DocumentRootElement < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("setAttribute(%S) failed with 0x%x");
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        (__int64)L"ProcessorRevision",
        DocumentRootElement);
    }
    VariantClear(&v13);
    goto LABEL_24;
  }
  VariantClear(&v13);
  VariantClear(&v15);
  VariantClear(&v14);
  appended = AppendNewLine(this[1], v17, 0);
  v8 = appended;
  if ( appended < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("AppendNewLine failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        94,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        v8);
    }
    TraceXMLFailure(this[1]);
  }
  v9 = this[1];
  v11 = pvarg;
  DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))v9->lpVtbl->save)(v9, &v11);
  if ( DocumentRootElement < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("m_pXmlDom->save failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        DocumentRootElement);
    }
    TraceXMLFailure(this[1]);
  }
LABEL_48:
  VariantClear(&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  return (unsigned int)DocumentRootElement;
}

```

## disassembly

```asm
0x18003b31c  mov     [rsp-8+arg_8], rdx
0x18003b321  push    rbp
0x18003b322  push    rbx
0x18003b323  push    rsi
0x18003b324  push    rdi
0x18003b325  push    r15
0x18003b327  lea     rbp, [rsp-37h]
0x18003b32c  sub     rsp, 0F0h
0x18003b333  mov     rbx, r8
0x18003b336  mov     rsi, rcx
0x18003b339  mov     [rbp+57h+arg_0], 0
0x18003b341  mov     [rbp+57h+arg_18], 0
0x18003b349  mov     [rbp+57h+arg_8], 0
0x18003b351  xorps   xmm0, xmm0
0x18003b354  xor     eax, eax
0x18003b356  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18003b35a  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18003b35e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003b362  call    cs:__imp_VariantInit
0x18003b368  mov     eax, 8
0x18003b36d  mov     word ptr [rbp+57h+pvarg], ax
0x18003b371  mov     rcx, rbx; psz
0x18003b374  call    cs:__imp_SysAllocString
0x18003b37a  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18003b37e  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18003b382  movaps  xmmword ptr [rbp+57h+var_A0], xmm0
0x18003b386  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18003b38b  movsd   qword ptr [rbp+57h+var_A0+10h], xmm1
0x18003b390  lea     r8, [rbp+57h+arg_0]; struct IXMLDOMElement **
0x18003b394  lea     rdx, [rbp+57h+var_A0]; struct tagVARIANT
0x18003b398  mov     rcx, [rsi+8]; struct IXMLDOMDocument2 *
0x18003b39c  call    ?GetDocumentRootElement@@YAJPEAUIXMLDOMDocument2@@UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z; GetDocumentRootElement(IXMLDOMDocument2 *,tagVARIANT,IXMLDOMElement * *)
0x18003b3a1  mov     ebx, eax
0x18003b3a3  test    eax, eax
0x18003b3a5  js      loc_18003B815
0x18003b3ab  mov     rdx, [rbp+57h+arg_0]; struct IXMLDOMNode *
0x18003b3af  test    rdx, rdx
0x18003b3b2  jz      loc_18003B815
0x18003b3b8  lea     r9, [rbp+57h+arg_18]; struct IXMLDOMNode **
0x18003b3bc  lea     r15, aSysteminfo; "SystemInfo"
0x18003b3c3  mov     r8, r15; unsigned __int16 *
0x18003b3c6  mov     rcx, [rsi+8]; struct IXMLDOMDocument2 *
0x18003b3ca  call    ?CreateAndAppendNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAGPEAPEAU2@@Z; CreateAndAppendNode(IXMLDOMDocument2 *,IXMLDOMNode *,ushort *,IXMLDOMNode * *)
0x18003b3cf  mov     ebx, eax
0x18003b3d1  test    eax, eax
0x18003b3d3  jns     short loc_18003B446
0x18003b3d5  lea     rdi, WPP_GLOBAL_Control
0x18003b3dc  mov     rax, cs:WPP_GLOBAL_Control
0x18003b3e3  cmp     rax, rdi
0x18003b3e6  jz      loc_18003B86C
0x18003b3ec  cmp     byte ptr [rax+19h], 2
0x18003b3f0  jb      loc_18003B86C
0x18003b3f6  test    dword ptr [rax+1Ch], 400h
0x18003b3fd  jz      loc_18003B86C
0x18003b403  mov     r8d, ebx
0x18003b406  mov     rdx, r15
0x18003b409  lea     rcx, aCreateandappen_1; "CreateAndAppendNode(%S) failed with 0x%"...
0x18003b410  call    WppDbgPrint
0x18003b415  mov     edx, 59h ; 'Y'
0x18003b41a  mov     [rsp+110h+var_E8], ebx
0x18003b41e  mov     [rsp+110h+var_F0], r15
0x18003b423  lea     r9, aNpssdo; "NPSSDO"
0x18003b42a  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003b431  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b438  mov     rcx, [rcx+10h]
0x18003b43c  call    WPP_SF_sSd
0x18003b441  jmp     loc_18003B86C
0x18003b446  mov     rcx, [rbp+57h+arg_18]
0x18003b44a  mov     rax, [rcx]
0x18003b44d  lea     r8, [rbp+57h+arg_8]
0x18003b451  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18003b458  mov     rax, [rax]
0x18003b45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b460  mov     ebx, eax
0x18003b462  test    eax, eax
0x18003b464  jns     short loc_18003B4AC
0x18003b466  lea     rdi, WPP_GLOBAL_Control
0x18003b46d  mov     rax, cs:WPP_GLOBAL_Control
0x18003b474  cmp     rax, rdi
0x18003b477  jz      loc_18003B86C
0x18003b47d  cmp     byte ptr [rax+19h], 2
0x18003b481  jb      loc_18003B86C
0x18003b487  test    dword ptr [rax+1Ch], 400h
0x18003b48e  jz      loc_18003B86C
0x18003b494  mov     edx, ebx
0x18003b496  lea     rcx, aPsysteminfonod; "pSystemInfoNode->QueryInterface(IXMLDOM"...
0x18003b49d  call    WppDbgPrint
0x18003b4a2  mov     edx, 5Ah ; 'Z'
0x18003b4a7  jmp     loc_18003B84A
0x18003b4ac  xorps   xmm0, xmm0
0x18003b4af  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x18003b4b3  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18003b4b7  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x18003b4bb  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x18003b4bf  call    cs:__imp_GetSystemInfo
0x18003b4c5  mov     edi, 12h
0x18003b4ca  mov     word ptr [rbp+57h+var_80], di
0x18003b4ce  movzx   eax, word ptr [rbp+57h+SystemInfo]
0x18003b4d2  mov     word ptr [rbp+57h+var_80+8], ax
0x18003b4d6  mov     rcx, [rbp+57h+arg_8]
0x18003b4da  movups  xmm0, xmmword ptr [rbp+57h+var_80]
0x18003b4de  movaps  [rsp+110h+var_E0], xmm0
0x18003b4e3  movsd   xmm1, qword ptr [rbp+57h+var_80+10h]
0x18003b4e8  movsd   [rbp+57h+var_D0], xmm1
0x18003b4ed  mov     rax, [rcx]
0x18003b4f0  lea     r8, [rsp+110h+var_E0]
0x18003b4f5  lea     r15, aProcessorarchi; "ProcessorArchitecture"
0x18003b4fc  mov     rdx, r15
0x18003b4ff  mov     rax, [rax+168h]
0x18003b506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b50b  mov     ebx, eax
0x18003b50d  test    eax, eax
0x18003b50f  jns     short loc_18003B581
0x18003b511  lea     rdi, WPP_GLOBAL_Control
0x18003b518  mov     rax, cs:WPP_GLOBAL_Control
0x18003b51f  cmp     rax, rdi
0x18003b522  jz      short loc_18003B572
0x18003b524  cmp     byte ptr [rax+19h], 2
0x18003b528  jb      short loc_18003B572
0x18003b52a  test    dword ptr [rax+1Ch], 400h
0x18003b531  jz      short loc_18003B572
0x18003b533  mov     r8d, ebx
0x18003b536  mov     rdx, r15
0x18003b539  lea     rcx, aSetattributeSF; "setAttribute(%S) failed with 0x%x"
0x18003b540  call    WppDbgPrint
0x18003b545  mov     edx, 5Bh ; '['
0x18003b54a  mov     [rsp+110h+var_E8], ebx
0x18003b54e  mov     [rsp+110h+var_F0], r15
0x18003b553  lea     r9, aNpssdo; "NPSSDO"
0x18003b55a  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003b561  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b568  mov     rcx, [rcx+10h]
0x18003b56c  call    WPP_SF_sSd
0x18003b571  nop
0x18003b572  lea     rcx, [rbp+57h+var_80]; pvarg
0x18003b576  call    cs:__imp_VariantClear
0x18003b57c  jmp     loc_18003B86C
0x18003b581  mov     word ptr [rbp+57h+var_68], di
0x18003b585  movzx   eax, [rbp+57h+SystemInfo.wProcessorLevel]
0x18003b589  mov     word ptr [rbp+57h+var_68+8], ax
0x18003b58d  mov     rcx, [rbp+57h+arg_8]
0x18003b591  movups  xmm0, xmmword ptr [rbp+57h+var_68]
0x18003b595  movaps  [rsp+110h+var_E0], xmm0
0x18003b59a  movsd   xmm1, qword ptr [rbp+57h+var_68+10h]
0x18003b59f  movsd   [rbp+57h+var_D0], xmm1
0x18003b5a4  mov     rax, [rcx]
0x18003b5a7  lea     r8, [rsp+110h+var_E0]
0x18003b5ac  lea     r15, aProcessorlevel; "ProcessorLevel"
0x18003b5b3  mov     rdx, r15
0x18003b5b6  mov     rax, [rax+168h]
0x18003b5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5c2  mov     ebx, eax
0x18003b5c4  test    eax, eax
0x18003b5c6  jns     short loc_18003B638
0x18003b5c8  lea     rdi, WPP_GLOBAL_Control
0x18003b5cf  mov     rax, cs:WPP_GLOBAL_Control
0x18003b5d6  cmp     rax, rdi
0x18003b5d9  jz      short loc_18003B629
0x18003b5db  cmp     byte ptr [rax+19h], 2
0x18003b5df  jb      short loc_18003B629
0x18003b5e1  test    dword ptr [rax+1Ch], 400h
0x18003b5e8  jz      short loc_18003B629
0x18003b5ea  mov     r8d, ebx
0x18003b5ed  mov     rdx, r15
0x18003b5f0  lea     rcx, aSetattributeSF; "setAttribute(%S) failed with 0x%x"
0x18003b5f7  call    WppDbgPrint
0x18003b5fc  mov     edx, 5Ch ; '\'
0x18003b601  mov     [rsp+110h+var_E8], ebx
0x18003b605  mov     [rsp+110h+var_F0], r15
0x18003b60a  lea     r9, aNpssdo; "NPSSDO"
0x18003b611  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003b618  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b61f  mov     rcx, [rcx+10h]
0x18003b623  call    WPP_SF_sSd
0x18003b628  nop
0x18003b629  lea     rcx, [rbp+57h+var_68]; pvarg
0x18003b62d  call    cs:__imp_VariantClear
0x18003b633  jmp     loc_18003B572
0x18003b638  mov     word ptr [rbp+57h+var_A0], di
0x18003b63c  movzx   eax, [rbp+57h+SystemInfo.wProcessorRevision]
0x18003b640  mov     word ptr [rbp+57h+var_A0+8], ax
0x18003b644  mov     rcx, [rbp+57h+arg_8]
0x18003b648  movups  xmm0, xmmword ptr [rbp+57h+var_A0]
0x18003b64c  movaps  [rsp+110h+var_E0], xmm0
0x18003b651  movsd   xmm1, qword ptr [rbp+57h+var_A0+10h]
0x18003b656  movsd   [rbp+57h+var_D0], xmm1
0x18003b65b  mov     rax, [rcx]
0x18003b65e  lea     r8, [rsp+110h+var_E0]
0x18003b663  lea     r15, aProcessorrevis; "ProcessorRevision"
0x18003b66a  mov     rdx, r15
0x18003b66d  mov     rax, [rax+168h]
0x18003b674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b679  mov     ebx, eax
0x18003b67b  test    eax, eax
0x18003b67d  jns     short loc_18003B6EF
0x18003b67f  lea     rdi, WPP_GLOBAL_Control
0x18003b686  mov     rax, cs:WPP_GLOBAL_Control
0x18003b68d  cmp     rax, rdi
0x18003b690  jz      short loc_18003B6E0
0x18003b692  cmp     byte ptr [rax+19h], 2
0x18003b696  jb      short loc_18003B6E0
0x18003b698  test    dword ptr [rax+1Ch], 400h
0x18003b69f  jz      short loc_18003B6E0
0x18003b6a1  mov     r8d, ebx
0x18003b6a4  mov     rdx, r15
0x18003b6a7  lea     rcx, aSetattributeSF; "setAttribute(%S) failed with 0x%x"
0x18003b6ae  call    WppDbgPrint
0x18003b6b3  mov     edx, 5Dh ; ']'
0x18003b6b8  mov     [rsp+110h+var_E8], ebx
0x18003b6bc  mov     [rsp+110h+var_F0], r15
0x18003b6c1  lea     r9, aNpssdo; "NPSSDO"
0x18003b6c8  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003b6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6d6  mov     rcx, [rcx+10h]
0x18003b6da  call    WPP_SF_sSd
0x18003b6df  nop
0x18003b6e0  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18003b6e4  call    cs:__imp_VariantClear
0x18003b6ea  jmp     loc_18003B629
0x18003b6ef  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18003b6f3  call    cs:__imp_VariantClear
0x18003b6f9  nop
0x18003b6fa  lea     rcx, [rbp+57h+var_68]; pvarg
0x18003b6fe  call    cs:__imp_VariantClear
0x18003b704  nop
0x18003b705  lea     rcx, [rbp+57h+var_80]; pvarg
0x18003b709  call    cs:__imp_VariantClear
0x18003b70f  xor     r8d, r8d; unsigned int
0x18003b712  mov     rdx, [rbp+57h+arg_0]; struct IXMLDOMNode *
0x18003b716  mov     rcx, [rsi+8]; struct IXMLDOMDocument2 *
0x18003b71a  call    ?AppendNewLine@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@K@Z; AppendNewLine(IXMLDOMDocument2 *,IXMLDOMNode *,ulong)
0x18003b71f  mov     ebx, eax
0x18003b721  lea     rdi, WPP_GLOBAL_Control
0x18003b728  test    eax, eax
0x18003b72a  jns     short loc_18003B785
0x18003b72c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b733  cmp     rcx, rdi
0x18003b736  jz      short loc_18003B77C
0x18003b738  cmp     byte ptr [rcx+19h], 2
0x18003b73c  jb      short loc_18003B77C
0x18003b73e  test    dword ptr [rcx+1Ch], 400h
0x18003b745  jz      short loc_18003B77C
0x18003b747  mov     edx, eax
0x18003b749  lea     rcx, aAppendnewlineF; "AppendNewLine failed with 0x%x"
0x18003b750  call    WppDbgPrint
0x18003b755  mov     edx, 5Eh ; '^'
0x18003b75a  mov     dword ptr [rsp+110h+var_F0], ebx
0x18003b75e  lea     r9, aNpssdo; "NPSSDO"
0x18003b765  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003b76c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b773  mov     rcx, [rcx+10h]
0x18003b777  call    WPP_SF_sd
0x18003b77c  mov     rcx, [rsi+8]; struct IXMLDOMDocument2 *
0x18003b780  call    ?TraceXMLFailure@@YAXPEAUIXMLDOMDocument2@@@Z; TraceXMLFailure(IXMLDOMDocument2 *)
0x18003b785  mov     rcx, [rsi+8]
0x18003b789  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18003b78d  movaps  [rsp+110h+var_E0], xmm0
0x18003b792  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18003b797  movsd   [rbp+57h+var_D0], xmm1
0x18003b79c  mov     rax, [rcx]
0x18003b79f  lea     rdx, [rsp+110h+var_E0]
0x18003b7a4  mov     rax, [rax+210h]
0x18003b7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7b0  mov     ebx, eax
0x18003b7b2  test    eax, eax
0x18003b7b4  jns     loc_18003B86C
0x18003b7ba  mov     rax, cs:WPP_GLOBAL_Control
0x18003b7c1  cmp     rax, rdi
0x18003b7c4  jz      short loc_18003B80A
0x18003b7c6  cmp     byte ptr [rax+19h], 2
0x18003b7ca  jb      short loc_18003B80A
0x18003b7cc  test    dword ptr [rax+1Ch], 400h
0x18003b7d3  jz      short loc_18003B80A
0x18003b7d5  mov     edx, ebx
0x18003b7d7  lea     rcx, aMPxmldomSaveFa; "m_pXmlDom->save failed with 0x%x"
0x18003b7de  call    WppDbgPrint
0x18003b7e3  mov     edx, 5Fh ; '_'
0x18003b7e8  mov     dword ptr [rsp+110h+var_F0], ebx
0x18003b7ec  lea     r9, aNpssdo; "NPSSDO"
0x18003b7f3  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003b7fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b801  mov     rcx, [rcx+10h]
0x18003b805  call    WPP_SF_sd
0x18003b80a  mov     rcx, [rsi+8]; struct IXMLDOMDocument2 *
0x18003b80e  call    ?TraceXMLFailure@@YAXPEAUIXMLDOMDocument2@@@Z; TraceXMLFailure(IXMLDOMDocument2 *)
0x18003b813  jmp     short loc_18003B86C
0x18003b815  lea     rdi, WPP_GLOBAL_Control
0x18003b81c  mov     rax, cs:WPP_GLOBAL_Control
0x18003b823  cmp     rax, rdi
0x18003b826  jz      short loc_18003B86C
0x18003b828  cmp     byte ptr [rax+19h], 2
0x18003b82c  jb      short loc_18003B86C
0x18003b82e  test    dword ptr [rax+1Ch], 400h
0x18003b835  jz      short loc_18003B86C
0x18003b837  mov     edx, ebx
0x18003b839  lea     rcx, aGetdocumentroo; "GetDocumentRootElement failed with 0x%x"
0x18003b840  call    WppDbgPrint
0x18003b845  mov     edx, 58h ; 'X'
0x18003b84a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b851  mov     dword ptr [rsp+110h+var_F0], ebx
  ... truncated ...
```
