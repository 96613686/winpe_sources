# IASExim::CheckProductLimitsForXmlImport(ushort *)

- ea: `0x18003a164`
- end: `0x18003a558`
- name: `?CheckProductLimitsForXmlImport@IASExim@@AEAAJPEAG@Z`
- size: `1012`
- prototype: `int(IASExim *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003d140`

## callees

- `0x180024cac`
- `0x18002cca4`
- `0x18002cd00`
- `0x18003a164`
- `0x18003b8ac`
- `0x180042a80`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `iassvcs!IASGetProductLimits` at `0x18003a1b2`
- `iassvcs!IASGetProductLimits` at `0x18003a1b2`
- `OLEAUT32!__imp_SysAllocString` at `0x18003a1f5`
- `OLEAUT32!__imp_SysAllocString` at `0x18003a1f5`
- `OLEAUT32!__imp_VariantInit` at `0x18003a1e3`
- `OLEAUT32!__imp_VariantInit` at `0x18003a1e3`
- `OLEAUT32!__imp_VariantClear` at `0x18003a4ff`
- `OLEAUT32!__imp_VariantClear` at `0x18003a4ff`

## string_xrefs

- `0x18003a33d`: `Number of server groups in the config being imported is more than what is allowed by license.`
- `0x18003a48e`: `Number of clients in the config being imported is more than what is allowed by license.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall IASExim::CheckProductLimitsForXmlImport(struct IXMLDOMDocument2 **this, unsigned __int16 *a2)
{
  int v4; // eax
  signed int DocumentRootElement; // ebx
  int v6; // edx
  __int64 v7; // rdx
  int v9; // [rsp+30h] [rbp-49h] BYREF
  struct IXMLDOMElement *v10; // [rsp+38h] [rbp-41h] BYREF
  __int64 v11; // [rsp+40h] [rbp-39h] BYREF
  __int64 v12; // [rsp+48h] [rbp-31h] BYREF
  __int64 v13; // [rsp+50h] [rbp-29h] BYREF
  __int64 v14; // [rsp+58h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-19h] BYREF
  struct tagVARIANT v16; // [rsp+80h] [rbp+7h] BYREF
  __int64 v17; // [rsp+A0h] [rbp+27h] BYREF
  int v18; // [rsp+A8h] [rbp+2Fh]

  v17 = 0;
  v18 = 0;
  v10 = 0;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  v11 = 0;
  v9 = 0;
  v4 = IASGetProductLimits(0, &v17);
  DocumentRootElement = v4;
  if ( !v4 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(a2);
    v16 = pvarg;
    DocumentRootElement = GetDocumentRootElement(this[1], &v16, &v10);
    if ( DocumentRootElement >= 0 && v10 )
    {
      DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const wchar_t *, __int64 *))v10->lpVtbl->selectSingleNode)(
                              v10,
                              L"//RADIUS_Server_Groups/Children",
                              &v14);
      if ( DocumentRootElement )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_43;
        }
        WppDbgPrint("pRootElement->selectSingleNode for server groups failed with 0x%x");
        v6 = 97;
        goto LABEL_42;
      }
      DocumentRootElement = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 96LL))(v14, &v13);
      if ( DocumentRootElement < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_43;
        }
        WppDbgPrint("serverGroups->get_childNodes failed with 0x%x");
        v6 = 98;
        goto LABEL_42;
      }
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 64LL))(v13, &v9);
      if ( v9 > v18 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_22;
        }
        WppDbgPrint("Number of server groups in the config being imported is more than what is allowed by license.");
        v7 = 99;
        goto LABEL_21;
      }
      DocumentRootElement = ((__int64 (__fastcall *)(struct IXMLDOMElement *, const wchar_t *, __int64 *))v10->lpVtbl->selectSingleNode)(
                              v10,
                              L"//Clients/Children",
                              &v12);
      if ( DocumentRootElement )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_43;
        }
        WppDbgPrint("pRootElement->selectSingleNode for clients failed with 0x%x");
        v6 = 100;
      }
      else
      {
        DocumentRootElement = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 96LL))(v12, &v11);
        if ( DocumentRootElement >= 0 )
        {
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 64LL))(v11, &v9);
          if ( v9 <= (int)v17 )
            goto LABEL_43;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          {
LABEL_22:
            DocumentRootElement = -2147023501;
LABEL_43:
            VariantClear(&pvarg);
            goto LABEL_44;
          }
          WppDbgPrint("Number of clients in the config being imported is more than what is allowed by license.");
          v7 = 102;
LABEL_21:
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids, "NPSSDO");
          goto LABEL_22;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_43;
        }
        WppDbgPrint("radiusClients->get_childNodes failed with 0x%x");
        v6 = 101;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        goto LABEL_43;
      }
      WppDbgPrint("GetDocumentRootElement failed with 0x%x");
      v6 = 96;
    }
LABEL_42:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
      (unsigned int)"NPSSDO",
      DocumentRootElement);
    goto LABEL_43;
  }
  if ( v4 > 0 )
    DocumentRootElement = (unsigned __int16)v4 | 0x80070000;
LABEL_44:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  return (unsigned int)DocumentRootElement;
}

```

## disassembly

```asm
0x18003a164  mov     [rsp-8+arg_10], rbx
0x18003a169  push    rbp
0x18003a16a  push    rsi
0x18003a16b  push    rdi
0x18003a16c  lea     rbp, [rsp-47h]
0x18003a171  sub     rsp, 0C0h
0x18003a178  mov     rax, cs:__security_cookie
0x18003a17f  xor     rax, rsp
0x18003a182  mov     [rbp+57h+var_20], rax
0x18003a186  mov     rsi, rdx
0x18003a189  mov     rdi, rcx
0x18003a18c  xor     eax, eax
0x18003a18e  mov     [rbp+57h+var_30], rax
0x18003a192  mov     [rbp+57h+var_28], eax
0x18003a195  mov     [rbp+57h+var_98], rax
0x18003a199  mov     [rbp+57h+var_78], rax
0x18003a19d  mov     [rbp+57h+var_80], rax
0x18003a1a1  mov     [rbp+57h+var_88], rax
0x18003a1a5  mov     [rbp+57h+var_90], rax
0x18003a1a9  mov     [rbp+57h+var_A0], eax
0x18003a1ac  lea     rdx, [rbp+57h+var_30]
0x18003a1b0  xor     ecx, ecx
0x18003a1b2  call    cs:__imp_IASGetProductLimits
0x18003a1b8  mov     ebx, eax
0x18003a1ba  test    eax, eax
0x18003a1bc  jz      short loc_18003A1D2
0x18003a1be  jle     loc_18003A506
0x18003a1c4  movzx   ebx, ax
0x18003a1c7  or      ebx, 80070000h
0x18003a1cd  jmp     loc_18003A506
0x18003a1d2  xorps   xmm0, xmm0
0x18003a1d5  xor     eax, eax
0x18003a1d7  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18003a1db  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18003a1df  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003a1e3  call    cs:__imp_VariantInit
0x18003a1e9  mov     eax, 8
0x18003a1ee  mov     word ptr [rbp+57h+pvarg], ax
0x18003a1f2  mov     rcx, rsi; psz
0x18003a1f5  call    cs:__imp_SysAllocString
0x18003a1fb  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18003a1ff  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18003a203  movaps  xmmword ptr [rbp+57h+var_50], xmm0
0x18003a207  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18003a20c  movsd   qword ptr [rbp+57h+var_50+10h], xmm1
0x18003a211  lea     r8, [rbp+57h+var_98]; struct IXMLDOMElement **
0x18003a215  lea     rdx, [rbp+57h+var_50]; struct tagVARIANT
0x18003a219  mov     rcx, [rdi+8]; struct IXMLDOMDocument2 *
0x18003a21d  call    ?GetDocumentRootElement@@YAJPEAUIXMLDOMDocument2@@UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z; GetDocumentRootElement(IXMLDOMDocument2 *,tagVARIANT,IXMLDOMElement * *)
0x18003a222  mov     ebx, eax
0x18003a224  test    eax, eax
0x18003a226  js      loc_18003A4A4
0x18003a22c  mov     rcx, [rbp+57h+var_98]
0x18003a230  test    rcx, rcx
0x18003a233  jz      loc_18003A4A4
0x18003a239  mov     rax, [rcx]
0x18003a23c  lea     r8, [rbp+57h+var_78]
0x18003a240  lea     rdx, aRadiusServerGr; "//RADIUS_Server_Groups/Children"
0x18003a247  mov     rax, [rax+128h]
0x18003a24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a253  mov     ebx, eax
0x18003a255  test    eax, eax
0x18003a257  jz      short loc_18003A29F
0x18003a259  lea     rax, WPP_GLOBAL_Control
0x18003a260  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a267  cmp     rcx, rax
0x18003a26a  jz      loc_18003A4FB
0x18003a270  cmp     byte ptr [rcx+19h], 2
0x18003a274  jb      loc_18003A4FB
0x18003a27a  test    dword ptr [rcx+1Ch], 400h
0x18003a281  jz      loc_18003A4FB
0x18003a287  mov     edx, ebx
0x18003a289  lea     rcx, aProotelementSe_0; "pRootElement->selectSingleNode for serv"...
0x18003a290  call    WppDbgPrint
0x18003a295  mov     edx, 61h ; 'a'
0x18003a29a  jmp     loc_18003A4D9
0x18003a29f  mov     rcx, [rbp+57h+var_78]
0x18003a2a3  mov     rax, [rcx]
0x18003a2a6  lea     rdx, [rbp+57h+var_80]
0x18003a2aa  mov     rax, [rax+60h]
0x18003a2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2b3  mov     ebx, eax
0x18003a2b5  test    eax, eax
0x18003a2b7  jns     short loc_18003A2FF
0x18003a2b9  lea     rax, WPP_GLOBAL_Control
0x18003a2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a2c7  cmp     rcx, rax
0x18003a2ca  jz      loc_18003A4FB
0x18003a2d0  cmp     byte ptr [rcx+19h], 2
0x18003a2d4  jb      loc_18003A4FB
0x18003a2da  test    dword ptr [rcx+1Ch], 400h
0x18003a2e1  jz      loc_18003A4FB
0x18003a2e7  mov     edx, ebx
0x18003a2e9  lea     rcx, aServergroupsGe; "serverGroups->get_childNodes failed wit"...
0x18003a2f0  call    WppDbgPrint
0x18003a2f5  mov     edx, 62h ; 'b'
0x18003a2fa  jmp     loc_18003A4D9
0x18003a2ff  mov     rcx, [rbp+57h+var_80]
0x18003a303  mov     rax, [rcx]
0x18003a306  lea     rdx, [rbp+57h+var_A0]
0x18003a30a  mov     rax, [rax+40h]
0x18003a30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a313  mov     eax, [rbp+57h+var_28]
0x18003a316  cmp     [rbp+57h+var_A0], eax
0x18003a319  jle     short loc_18003A376
0x18003a31b  lea     rax, WPP_GLOBAL_Control
0x18003a322  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a329  cmp     rcx, rax
0x18003a32c  jz      short loc_18003A36C
0x18003a32e  cmp     byte ptr [rcx+19h], 2
0x18003a332  jb      short loc_18003A36C
0x18003a334  test    dword ptr [rcx+1Ch], 400h
0x18003a33b  jz      short loc_18003A36C
0x18003a33d  lea     rcx, aNumberOfServer; "Number of server groups in the config b"...
0x18003a344  call    WppDbgPrint
0x18003a349  mov     edx, 63h ; 'c'
0x18003a34e  lea     r9, aNpssdo; "NPSSDO"
0x18003a355  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003a35c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a363  mov     rcx, [rcx+10h]
0x18003a367  call    WPP_SF_s
0x18003a36c  mov     ebx, 80070573h
0x18003a371  jmp     loc_18003A4FB
0x18003a376  mov     rcx, [rbp+57h+var_98]
0x18003a37a  mov     rax, [rcx]
0x18003a37d  lea     r8, [rbp+57h+var_88]
0x18003a381  lea     rdx, aClientsChildre; "//Clients/Children"
0x18003a388  mov     rax, [rax+128h]
0x18003a38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a394  mov     ebx, eax
0x18003a396  test    eax, eax
0x18003a398  jz      short loc_18003A3E0
0x18003a39a  lea     rax, WPP_GLOBAL_Control
0x18003a3a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a3a8  cmp     rcx, rax
0x18003a3ab  jz      loc_18003A4FB
0x18003a3b1  cmp     byte ptr [rcx+19h], 2
0x18003a3b5  jb      loc_18003A4FB
0x18003a3bb  test    dword ptr [rcx+1Ch], 400h
0x18003a3c2  jz      loc_18003A4FB
0x18003a3c8  mov     edx, ebx
0x18003a3ca  lea     rcx, aProotelementSe_1; "pRootElement->selectSingleNode for clie"...
0x18003a3d1  call    WppDbgPrint
0x18003a3d6  mov     edx, 64h ; 'd'
0x18003a3db  jmp     loc_18003A4D9
0x18003a3e0  mov     rcx, [rbp+57h+var_88]
0x18003a3e4  mov     rax, [rcx]
0x18003a3e7  lea     rdx, [rbp+57h+var_90]
0x18003a3eb  mov     rax, [rax+60h]
0x18003a3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3f4  mov     ebx, eax
0x18003a3f6  test    eax, eax
0x18003a3f8  jns     short loc_18003A440
0x18003a3fa  lea     rax, WPP_GLOBAL_Control
0x18003a401  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a408  cmp     rcx, rax
0x18003a40b  jz      loc_18003A4FB
0x18003a411  cmp     byte ptr [rcx+19h], 2
0x18003a415  jb      loc_18003A4FB
0x18003a41b  test    dword ptr [rcx+1Ch], 400h
0x18003a422  jz      loc_18003A4FB
0x18003a428  mov     edx, ebx
0x18003a42a  lea     rcx, aRadiusclientsG; "radiusClients->get_childNodes failed wi"...
0x18003a431  call    WppDbgPrint
0x18003a436  mov     edx, 65h ; 'e'
0x18003a43b  jmp     loc_18003A4D9
0x18003a440  mov     rcx, [rbp+57h+var_90]
0x18003a444  mov     rax, [rcx]
0x18003a447  lea     rdx, [rbp+57h+var_A0]
0x18003a44b  mov     rax, [rax+40h]
0x18003a44f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a454  mov     eax, dword ptr [rbp+57h+var_30]
0x18003a457  cmp     [rbp+57h+var_A0], eax
0x18003a45a  jle     loc_18003A4FB
0x18003a460  lea     rax, WPP_GLOBAL_Control
0x18003a467  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a46e  cmp     rcx, rax
0x18003a471  jz      loc_18003A36C
0x18003a477  cmp     byte ptr [rcx+19h], 2
0x18003a47b  jb      loc_18003A36C
0x18003a481  test    dword ptr [rcx+1Ch], 400h
0x18003a488  jz      loc_18003A36C
0x18003a48e  lea     rcx, aNumberOfClient; "Number of clients in the config being i"...
0x18003a495  call    WppDbgPrint
0x18003a49a  mov     edx, 66h ; 'f'
0x18003a49f  jmp     loc_18003A34E
0x18003a4a4  lea     rax, WPP_GLOBAL_Control
0x18003a4ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4b2  cmp     rcx, rax
0x18003a4b5  jz      short loc_18003A4FB
0x18003a4b7  cmp     byte ptr [rcx+19h], 2
0x18003a4bb  jb      short loc_18003A4FB
0x18003a4bd  test    dword ptr [rcx+1Ch], 400h
0x18003a4c4  jz      short loc_18003A4FB
0x18003a4c6  mov     edx, ebx
0x18003a4c8  lea     rcx, aGetdocumentroo; "GetDocumentRootElement failed with 0x%x"
0x18003a4cf  call    WppDbgPrint
0x18003a4d4  mov     edx, 60h ; '`'
0x18003a4d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4e0  mov     [rsp+0D0h+var_B0], ebx
0x18003a4e4  lea     r9, aNpssdo; "NPSSDO"
0x18003a4eb  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003a4f2  mov     rcx, [rcx+10h]
0x18003a4f6  call    WPP_SF_sd
0x18003a4fb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18003a4ff  call    cs:__imp_VariantClear
0x18003a505  nop
0x18003a506  lea     rcx, [rbp+57h+var_90]
0x18003a50a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a50f  nop
0x18003a510  lea     rcx, [rbp+57h+var_88]
0x18003a514  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a519  nop
0x18003a51a  lea     rcx, [rbp+57h+var_80]
0x18003a51e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a523  nop
0x18003a524  lea     rcx, [rbp+57h+var_78]
0x18003a528  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a52d  nop
0x18003a52e  lea     rcx, [rbp+57h+var_98]
0x18003a532  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a537  mov     eax, ebx
0x18003a539  mov     rcx, [rbp+57h+var_20]
0x18003a53d  xor     rcx, rsp; StackCookie
0x18003a540  call    __security_check_cookie
0x18003a545  mov     rbx, [rsp+0D0h+arg_10]
0x18003a54d  add     rsp, 0C0h
0x18003a554  pop     rdi
0x18003a555  pop     rsi
0x18003a556  pop     rbp
0x18003a557  retn
```
