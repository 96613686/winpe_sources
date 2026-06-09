# IASExim::ImportSystemInfo(ushort *,ushort *,IXMLDOMNode * *)

- ea: `0x18003c96c`
- end: `0x18003cdcc`
- name: `?ImportSystemInfo@IASExim@@AEAAJPEAG0PEAPEAUIXMLDOMNode@@@Z`
- size: `1120`
- prototype: `int(IASExim *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d140`

## callees

- `0x180024cac`
- `0x18002cd00`
- `0x18002f08c`
- `0x18003b8ac`
- `0x18003c96c`
- `0x18003d9b0`
- `0x1800407e0`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `msvcrt!wcstol` at `0x18003cb7d`
- `msvcrt!wcstol` at `0x18003cb7d`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c9c2`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c9c2`
- `OLEAUT32!__imp_VariantInit` at `0x18003c9b1`
- `OLEAUT32!__imp_VariantInit` at `0x18003cad5`
- `OLEAUT32!__imp_VariantInit` at `0x18003c9b1`
- `OLEAUT32!__imp_VariantInit` at `0x18003cad5`
- `OLEAUT32!__imp_VariantClear` at `0x18003cb68`
- `OLEAUT32!__imp_VariantClear` at `0x18003cbb4`
- `OLEAUT32!__imp_VariantClear` at `0x18003cd92`
- `OLEAUT32!__imp_VariantClear` at `0x18003cb68`
- `OLEAUT32!__imp_VariantClear` at `0x18003cbb4`
- `OLEAUT32!__imp_VariantClear` at `0x18003cd92`

## string_xrefs

- `0x18003cc77`: `m_pXmlDom->save failed with 0x%x`
- `0x18003cabb`: `pSystemInfoNode->QueryInterface(IXMLDOMElement) failed with 0x%x`
- `0x18003ccf3`: `The operation is not supported. Cannot import configuration from ProcessorArchitecture[%d] to ProcessorArchitecture[%d].\n`
- `0x18003cc0a`: `m_pXmlDom->removeChild(pSystemInfoNode) failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall IASExim::ImportSystemInfo(
        IASExim *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IXMLDOMNode **a4)
{
  int DocumentRootElement; // ebx
  int v8; // edx
  __int16 v9; // dx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v13; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v15; // [rsp+50h] [rbp-20h] BYREF
  struct IXMLDOMElement *v16; // [rsp+A0h] [rbp+30h] BYREF
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // [rsp+A8h] [rbp+38h] BYREF

  v16 = 0;
  v17 = 0;
  v13 = 0;
  *((_DWORD *)this + 5) = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(a3);
  v15 = pvarg;
  DocumentRootElement = GetDocumentRootElement(*((struct IXMLDOMDocument2 **)this + 1), &v15, &v16);
  if ( DocumentRootElement < 0 || !v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("GetDocumentRootElement failed with 0x%x");
      v8 = 81;
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const unsigned __int16 *, _QWORD))v16->lpVtbl->selectSingleNode)(
                          v16,
                          L"SystemInfo",
                          &v17);
  if ( DocumentRootElement )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pRootElement->selectSingleNode failed with 0x%x");
      v8 = 82;
LABEL_43:
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        DocumentRootElement);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  DocumentRootElement = (**v17)(v17, &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60, &v13);
  if ( DocumentRootElement >= 0 )
  {
    VariantInit(&v15);
    DocumentRootElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v13 + 352LL))(
                            v13,
                            L"ProcessorArchitecture",
                            &v15);
    if ( DocumentRootElement < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("pSystemInfoElement->getAttribute(%S) failed with 0x%x");
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          84,
          (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
          (unsigned int)"NPSSDO",
          (__int64)L"ProcessorArchitecture",
          DocumentRootElement);
      }
LABEL_18:
      VariantClear(&v15);
      goto LABEL_44;
    }
    v9 = wcstol(v15.bstrVal, 0, 10);
    *((_WORD *)this + 9) = v9;
    if ( v9 == *((_WORD *)this + 8) )
    {
      v10 = 0;
    }
    else
    {
      if ( v9 || *((_WORD *)this + 8) != 9 )
      {
        DocumentRootElement = -2147024846;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("The operation is not supported. Cannot import configuration from ProcessorArchitecture[%d] to Proc"
                      "essorArchitecture[%d].\n");
          WPP_SF_sdd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            85,
            (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
            (unsigned int)"NPSSDO",
            *((_WORD *)this + 9),
            *((_WORD *)this + 8));
        }
        goto LABEL_18;
      }
      v10 = 1;
    }
    *((_DWORD *)this + 5) = v10;
    VariantClear(&v15);
    DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMElement *, _QWORD, struct IXMLDOMNode **))v16->lpVtbl->removeChild)(
                            v16,
                            v17,
                            a4);
    if ( DocumentRootElement >= 0 )
    {
      v11 = *((_QWORD *)this + 1);
      v15 = pvarg;
      DocumentRootElement = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v11 + 528LL))(v11, &v15);
      if ( DocumentRootElement < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("m_pXmlDom->save failed with 0x%x");
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            87,
            (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
            (unsigned int)"NPSSDO",
            DocumentRootElement);
        }
        TraceXMLFailure(*((struct IXMLDOMDocument2 **)this + 1));
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("m_pXmlDom->removeChild(pSystemInfoNode) failed with 0x%x");
      v8 = 86;
      goto LABEL_43;
    }
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("pSystemInfoNode->QueryInterface(IXMLDOMElement) failed with 0x%x");
    v8 = 83;
    goto LABEL_43;
  }
LABEL_44:
  VariantClear(&pvarg);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  return (unsigned int)DocumentRootElement;
}

```

## disassembly

```asm
0x18003c96c  mov     [rsp-28h+arg_10], rbx
0x18003c971  mov     [rsp-28h+arg_8], rdx
0x18003c976  push    rbp
0x18003c977  push    rsi
0x18003c978  push    rdi
0x18003c979  push    r14
0x18003c97b  push    r15
0x18003c97d  mov     rbp, rsp
0x18003c980  sub     rsp, 70h
0x18003c984  mov     rsi, r9
0x18003c987  mov     rbx, r8
0x18003c98a  mov     rdi, rcx
0x18003c98d  xor     r14d, r14d
0x18003c990  mov     [rbp+arg_0], r14
0x18003c994  mov     [rbp+arg_8], r14
0x18003c998  mov     [rbp+var_40], r14
0x18003c99c  mov     [rcx+14h], r14d
0x18003c9a0  xorps   xmm0, xmm0
0x18003c9a3  xor     eax, eax
0x18003c9a5  movups  xmmword ptr [rbp+pvarg], xmm0
0x18003c9a9  mov     qword ptr [rbp+pvarg+10h], rax
0x18003c9ad  lea     rcx, [rbp+pvarg]; pvarg
0x18003c9b1  call    cs:__imp_VariantInit
0x18003c9b7  lea     eax, [r14+8]
0x18003c9bb  mov     word ptr [rbp+pvarg], ax
0x18003c9bf  mov     rcx, rbx; psz
0x18003c9c2  call    cs:__imp_SysAllocString
0x18003c9c8  mov     qword ptr [rbp+pvarg+8], rax
0x18003c9cc  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18003c9d0  movaps  xmmword ptr [rbp+var_20], xmm0
0x18003c9d4  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18003c9d9  movsd   qword ptr [rbp+var_20+10h], xmm1
0x18003c9de  lea     r8, [rbp+arg_0]; struct IXMLDOMElement **
0x18003c9e2  lea     rdx, [rbp+var_20]; struct tagVARIANT
0x18003c9e6  mov     rcx, [rdi+8]; struct IXMLDOMDocument2 *
0x18003c9ea  call    ?GetDocumentRootElement@@YAJPEAUIXMLDOMDocument2@@UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z; GetDocumentRootElement(IXMLDOMDocument2 *,tagVARIANT,IXMLDOMElement * *)
0x18003c9ef  mov     ebx, eax
0x18003c9f1  test    eax, eax
0x18003c9f3  js      loc_18003CD37
0x18003c9f9  mov     rcx, [rbp+arg_0]
0x18003c9fd  test    rcx, rcx
0x18003ca00  jz      loc_18003CD37
0x18003ca06  mov     rax, [rcx]
0x18003ca09  lea     r8, [rbp+arg_8]
0x18003ca0d  lea     rdx, aSysteminfo; "SystemInfo"
0x18003ca14  mov     rax, [rax+128h]
0x18003ca1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca20  mov     ebx, eax
0x18003ca22  test    eax, eax
0x18003ca24  jz      short loc_18003CA6B
0x18003ca26  lea     rax, WPP_GLOBAL_Control
0x18003ca2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ca34  cmp     rcx, rax
0x18003ca37  jz      loc_18003CD8E
0x18003ca3d  cmp     byte ptr [rcx+19h], 2
0x18003ca41  jb      loc_18003CD8E
0x18003ca47  test    dword ptr [rcx+1Ch], 400h
0x18003ca4e  jz      loc_18003CD8E
0x18003ca54  mov     edx, ebx
0x18003ca56  lea     rcx, aProotelementSe; "pRootElement->selectSingleNode failed w"...
0x18003ca5d  call    WppDbgPrint
0x18003ca62  lea     edx, [r14+52h]
0x18003ca66  jmp     loc_18003CD6C
0x18003ca6b  mov     rcx, [rbp+arg_8]
0x18003ca6f  mov     rax, [rcx]
0x18003ca72  lea     r8, [rbp+var_40]
0x18003ca76  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18003ca7d  mov     rax, [rax]
0x18003ca80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca85  mov     ebx, eax
0x18003ca87  test    eax, eax
0x18003ca89  jns     short loc_18003CAD1
0x18003ca8b  lea     rax, WPP_GLOBAL_Control
0x18003ca92  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ca99  cmp     rcx, rax
0x18003ca9c  jz      loc_18003CD8E
0x18003caa2  cmp     byte ptr [rcx+19h], 2
0x18003caa6  jb      loc_18003CD8E
0x18003caac  test    dword ptr [rcx+1Ch], 400h
0x18003cab3  jz      loc_18003CD8E
0x18003cab9  mov     edx, ebx
0x18003cabb  lea     rcx, aPsysteminfonod; "pSystemInfoNode->QueryInterface(IXMLDOM"...
0x18003cac2  call    WppDbgPrint
0x18003cac7  mov     edx, 53h ; 'S'
0x18003cacc  jmp     loc_18003CD6C
0x18003cad1  lea     rcx, [rbp+var_20]; pvarg
0x18003cad5  call    cs:__imp_VariantInit
0x18003cadb  nop
0x18003cadc  mov     rcx, [rbp+var_40]
0x18003cae0  mov     rax, [rcx]
0x18003cae3  lea     r8, [rbp+var_20]
0x18003cae7  lea     r15, aProcessorarchi; "ProcessorArchitecture"
0x18003caee  mov     rdx, r15
0x18003caf1  mov     rax, [rax+160h]
0x18003caf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cafd  mov     ebx, eax
0x18003caff  test    eax, eax
0x18003cb01  jns     short loc_18003CB73
0x18003cb03  lea     rax, WPP_GLOBAL_Control
0x18003cb0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb11  cmp     rcx, rax
0x18003cb14  jz      short loc_18003CB64
0x18003cb16  cmp     byte ptr [rcx+19h], 2
0x18003cb1a  jb      short loc_18003CB64
0x18003cb1c  test    dword ptr [rcx+1Ch], 400h
0x18003cb23  jz      short loc_18003CB64
0x18003cb25  mov     r8d, ebx
0x18003cb28  mov     rdx, r15
0x18003cb2b  lea     rcx, aPsysteminfoele; "pSystemInfoElement->getAttribute(%S) fa"...
0x18003cb32  call    WppDbgPrint
0x18003cb37  mov     edx, 54h ; 'T'
0x18003cb3c  mov     [rsp+70h+var_48], ebx
0x18003cb40  mov     [rsp+70h+var_50], r15
0x18003cb45  lea     r9, aNpssdo; "NPSSDO"
0x18003cb4c  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003cb53  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb5a  mov     rcx, [rcx+10h]
0x18003cb5e  call    WPP_SF_sSd
0x18003cb63  nop
0x18003cb64  lea     rcx, [rbp+var_20]; pvarg
0x18003cb68  call    cs:__imp_VariantClear
0x18003cb6e  jmp     loc_18003CD8E
0x18003cb73  xor     edx, edx; EndPtr
0x18003cb75  lea     r8d, [rdx+0Ah]; Radix
0x18003cb79  mov     rcx, qword ptr [rbp+var_20+8]; String
0x18003cb7d  call    cs:__imp_wcstol
0x18003cb83  mov     edx, eax
0x18003cb85  mov     [rdi+12h], dx
0x18003cb89  cmp     ax, [rdi+10h]
0x18003cb8d  jnz     short loc_18003CB94
0x18003cb8f  mov     eax, r14d
0x18003cb92  jmp     short loc_18003CBAD
0x18003cb94  test    dx, dx
0x18003cb97  jnz     loc_18003CCB8
0x18003cb9d  cmp     word ptr [rdi+10h], 9
0x18003cba2  jnz     loc_18003CCB8
0x18003cba8  mov     eax, 1
0x18003cbad  mov     [rdi+14h], eax
0x18003cbb0  lea     rcx, [rbp+var_20]; pvarg
0x18003cbb4  call    cs:__imp_VariantClear
0x18003cbba  mov     rcx, [rbp+arg_0]
0x18003cbbe  mov     rax, [rcx]
0x18003cbc1  mov     r8, rsi
0x18003cbc4  mov     rdx, [rbp+arg_8]
0x18003cbc8  mov     rax, [rax+0A0h]
0x18003cbcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbd4  mov     ebx, eax
0x18003cbd6  test    eax, eax
0x18003cbd8  jns     short loc_18003CC20
0x18003cbda  lea     rax, WPP_GLOBAL_Control
0x18003cbe1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cbe8  cmp     rcx, rax
0x18003cbeb  jz      loc_18003CD8E
0x18003cbf1  cmp     byte ptr [rcx+19h], 2
0x18003cbf5  jb      loc_18003CD8E
0x18003cbfb  test    dword ptr [rcx+1Ch], 400h
0x18003cc02  jz      loc_18003CD8E
0x18003cc08  mov     edx, ebx
0x18003cc0a  lea     rcx, aMPxmldomRemove; "m_pXmlDom->removeChild(pSystemInfoNode)"...
0x18003cc11  call    WppDbgPrint
0x18003cc16  mov     edx, 56h ; 'V'
0x18003cc1b  jmp     loc_18003CD6C
0x18003cc20  mov     rcx, [rdi+8]
0x18003cc24  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18003cc28  movaps  xmmword ptr [rbp+var_20], xmm0
0x18003cc2c  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18003cc31  movsd   qword ptr [rbp+var_20+10h], xmm1
0x18003cc36  mov     rax, [rcx]
0x18003cc39  lea     rdx, [rbp+var_20]
0x18003cc3d  mov     rax, [rax+210h]
0x18003cc44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc49  mov     ebx, eax
0x18003cc4b  test    eax, eax
0x18003cc4d  jns     loc_18003CD8E
0x18003cc53  lea     rax, WPP_GLOBAL_Control
0x18003cc5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cc61  cmp     rcx, rax
0x18003cc64  jz      short loc_18003CCAA
0x18003cc66  cmp     byte ptr [rcx+19h], 2
0x18003cc6a  jb      short loc_18003CCAA
0x18003cc6c  test    dword ptr [rcx+1Ch], 400h
0x18003cc73  jz      short loc_18003CCAA
0x18003cc75  mov     edx, ebx
0x18003cc77  lea     rcx, aMPxmldomSaveFa; "m_pXmlDom->save failed with 0x%x"
0x18003cc7e  call    WppDbgPrint
0x18003cc83  mov     edx, 57h ; 'W'
0x18003cc88  mov     dword ptr [rsp+70h+var_50], ebx
0x18003cc8c  lea     r9, aNpssdo; "NPSSDO"
0x18003cc93  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003cc9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cca1  mov     rcx, [rcx+10h]
0x18003cca5  call    WPP_SF_sd
0x18003ccaa  mov     rcx, [rdi+8]; struct IXMLDOMDocument2 *
0x18003ccae  call    ?TraceXMLFailure@@YAXPEAUIXMLDOMDocument2@@@Z; TraceXMLFailure(IXMLDOMDocument2 *)
0x18003ccb3  jmp     loc_18003CD8E
0x18003ccb8  mov     ebx, 80070032h
0x18003ccbd  lea     rax, WPP_GLOBAL_Control
0x18003ccc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cccb  cmp     rcx, rax
0x18003ccce  jz      loc_18003CB64
0x18003ccd4  cmp     byte ptr [rcx+19h], 2
0x18003ccd8  jb      loc_18003CB64
0x18003ccde  test    dword ptr [rcx+1Ch], 400h
0x18003cce5  jz      loc_18003CB64
0x18003cceb  movzx   r8d, word ptr [rdi+10h]
0x18003ccf0  movzx   edx, dx
0x18003ccf3  lea     rcx, aTheOperationIs; "The operation is not supported. Cannot "...
0x18003ccfa  call    WppDbgPrint
0x18003ccff  movzx   eax, word ptr [rdi+10h]
0x18003cd03  movzx   ecx, word ptr [rdi+12h]
0x18003cd07  mov     edx, 55h ; 'U'
0x18003cd0c  mov     [rsp+70h+var_48], eax
0x18003cd10  mov     dword ptr [rsp+70h+var_50], ecx
0x18003cd14  lea     r9, aNpssdo; "NPSSDO"
0x18003cd1b  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003cd22  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd29  mov     rcx, [rcx+10h]
0x18003cd2d  call    WPP_SF_sdd
0x18003cd32  jmp     loc_18003CB64
0x18003cd37  lea     rax, WPP_GLOBAL_Control
0x18003cd3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd45  cmp     rcx, rax
0x18003cd48  jz      short loc_18003CD8E
0x18003cd4a  cmp     byte ptr [rcx+19h], 2
0x18003cd4e  jb      short loc_18003CD8E
0x18003cd50  test    dword ptr [rcx+1Ch], 400h
0x18003cd57  jz      short loc_18003CD8E
0x18003cd59  mov     edx, ebx
0x18003cd5b  lea     rcx, aGetdocumentroo; "GetDocumentRootElement failed with 0x%x"
0x18003cd62  call    WppDbgPrint
0x18003cd67  mov     edx, 51h ; 'Q'
0x18003cd6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd73  mov     dword ptr [rsp+70h+var_50], ebx
0x18003cd77  lea     r9, aNpssdo; "NPSSDO"
0x18003cd7e  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003cd85  mov     rcx, [rcx+10h]
0x18003cd89  call    WPP_SF_sd
0x18003cd8e  lea     rcx, [rbp+pvarg]; pvarg
0x18003cd92  call    cs:__imp_VariantClear
0x18003cd98  nop
0x18003cd99  lea     rcx, [rbp+var_40]
0x18003cd9d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003cda2  nop
0x18003cda3  lea     rcx, [rbp+arg_8]
0x18003cda7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003cdac  nop
0x18003cdad  lea     rcx, [rbp+arg_0]
0x18003cdb1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003cdb6  mov     eax, ebx
0x18003cdb8  mov     rbx, [rsp+70h+arg_10]
0x18003cdc0  add     rsp, 70h
0x18003cdc4  pop     r15
0x18003cdc6  pop     r14
0x18003cdc8  pop     rdi
0x18003cdc9  pop     rsi
0x18003cdca  pop     rbp
0x18003cdcb  retn
```
