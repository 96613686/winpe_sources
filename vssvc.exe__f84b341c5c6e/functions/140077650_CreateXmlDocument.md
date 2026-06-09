# CreateXmlDocument

- ea: `0x140077650`
- end: `0x1400779e5`
- name: `CreateXmlDocument`
- size: `917`
- prototype: `__int64 __fastcall(AsrSystem *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14006168c`

## callees

- `0x140021ca0`
- `0x1400235a8`
- `0x140025abc`
- `0x140046a64`
- `0x140055ba4`
- `0x140058d00`
- `0x14005cfc0`
- `0x140070588`
- `0x140077650`
- `0x1400779ec`
- `0x14007a2f0`
- `0x1400d257c`
- `0x1400d25f8`
- `0x1400d2cfc`
- `0x1400d3470`
- `0x1400d9488`
- `0x1400d9cbc`
- `0x1400da314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400779c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400779c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400776f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007771d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007775f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007782c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007787d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400778a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400778ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400778f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400776f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007771d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007775f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007782c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007787d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400778a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400778ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400778f7`
- `OLEAUT32!__imp_SysFreeString` at `0x1400779ae`
- `OLEAUT32!__imp_SysFreeString` at `0x1400779ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400779a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400779a5`

## string_xrefs

- `0x140077670`: `CreateXmlDocument`
- `0x1400779b4`: `CreateXmlDocument`
- `0x14007795f`: `pwszXmlDoc`
- `0x1400776c0`: `ppwszOutXmlDoc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateXmlDocument(AsrSystem *this, AsrFmt *a2, AsrLdm *a3, _QWORD *a4)
{
  struct IXMLDOMDocument *v8; // rdx
  unsigned __int16 *v9; // r13
  unsigned int v10; // edi
  DWORD LastError; // ebx
  DWORD v12; // eax
  int v13; // eax
  CXMLNode *v14; // rsi
  DWORD v15; // eax
  DWORD v16; // eax
  int v17; // edx
  unsigned __int16 *v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // r15d
  _WORD *v21; // rax
  _WORD *v22; // r14
  char v24[8]; // [rsp+30h] [rbp-38h] BYREF
  struct IUnknown *v25; // [rsp+38h] [rbp-30h] BYREF
  struct IUnknown *v26; // [rsp+40h] [rbp-28h] BYREF
  int v27; // [rsp+50h] [rbp-18h]
  CXMLNode *v28; // [rsp+C8h] [rbp+60h] BYREF

  TraceFunctionEnter(L"CreateXmlDocument");
  CXMLDocument::CXMLDocument((CXMLDocument *)v24, v8);
  v28 = 0;
  v9 = 0;
  if ( !a4 )
  {
    v10 = 0;
    LastError = 87;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        10,
        (unsigned int)WPP_cb2b14357a2c349c2c07fc822528e543_Traceguids,
        87,
        "ppwszOutXmlDoc");
    }
    goto LABEL_40;
  }
  if ( !(unsigned int)XmlDocInit((struct CXMLDocument *)v24) )
  {
    v10 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v12 = GetLastError();
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        11,
        (unsigned int)WPP_cb2b14357a2c349c2c07fc822528e543_Traceguids,
        v12,
        "GetLastError()");
    }
    goto LABEL_40;
  }
  v13 = XmlDocCreateNode((struct CXMLDocument *)v24, L"AsrSif", &v28);
  v14 = v28;
  if ( !v13 )
  {
    v10 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v15 = GetLastError();
      WPP_SF_DsS(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        12,
        (unsigned int)WPP_cb2b14357a2c349c2c07fc822528e543_Traceguids,
        v15,
        (__int64)"GetLastError()",
        (__int64)L"Version");
    }
    goto LABEL_38;
  }
  v27 = 0;
  ATL::CComPtr<IVssSnapshotSetDescription>::operator=(&v25, *((struct IUnknown **)v28 + 1));
  ATL::CComPtr<IVssSnapshotProvider>::operator=(&v26, &v25);
  if ( !this || (unsigned int)AsrSystem::BuildXmlNodes(this, (struct CXMLDocument *)v24, v14) )
  {
    if ( !a2 || (unsigned int)AsrFmt::BuildXmlNodes(a2, (struct CXMLDocument *)v24, v14) )
    {
      if ( !a3 || AsrLdm::BuildXmlNodes(a3, (struct CXMLDocument *)v24, v14) )
      {
        v18 = CXMLNode::SaveAsXML(v14);
        v9 = v18;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        v20 = v19 + 1;
        v21 = ASR_ALLOC((unsigned int)(2 * (v19 + 1)));
        v22 = v21;
        if ( v21 )
        {
          LastError = 0;
          v10 = 1;
          memcpy_0(v21, v9, 2LL * v20);
          v22[v20 - 1] = 0;
          *a4 = v22;
        }
        else
        {
          v10 = 0;
          LastError = 14;
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              16,
              (unsigned int)WPP_cb2b14357a2c349c2c07fc822528e543_Traceguids,
              14,
              "pwszXmlDoc");
          }
        }
        goto LABEL_38;
      }
      v10 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v16 = GetLastError();
        v17 = 15;
        goto LABEL_19;
      }
    }
    else
    {
      v10 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v16 = GetLastError();
        v17 = 14;
        goto LABEL_19;
      }
    }
  }
  else
  {
    v10 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v16 = GetLastError();
      v17 = 13;
LABEL_19:
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        v17,
        (unsigned int)WPP_cb2b14357a2c349c2c07fc822528e543_Traceguids,
        v16,
        "GetLastError()");
    }
  }
LABEL_38:
  if ( v14 )
    CXMLNode::`scalar deleting destructor'(v14);
LABEL_40:
  CoTaskMemFree(0);
  SysFreeString(v9);
  TraceFunctionExit(L"CreateXmlDocument");
  SetLastError(LastError);
  CXMLDocument::~CXMLDocument((CXMLDocument *)v24);
  return v10;
}

```

## disassembly

```asm
0x140077650  push    rbp
0x140077652  push    rbx
0x140077653  push    rsi
0x140077654  push    rdi
0x140077655  push    r12
0x140077657  push    r13
0x140077659  push    r14
0x14007765b  push    r15
0x14007765d  mov     rbp, rsp
0x140077660  sub     rsp, 68h
0x140077664  mov     r12, r9
0x140077667  mov     rdi, r8
0x14007766a  mov     rbx, rdx
0x14007766d  mov     r14, rcx
0x140077670  lea     rcx, aCreatexmldocum; "CreateXmlDocument"
0x140077677  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x14007767c  lea     rcx, [rbp+var_38]; this
0x140077680  call    ??0CXMLDocument@@QEAA@PEAUIXMLDOMDocument@@@Z; CXMLDocument::CXMLDocument(IXMLDOMDocument *)
0x140077685  nop
0x140077686  xor     r15d, r15d
0x140077689  mov     [rbp+arg_18], r15
0x14007768d  mov     r13d, r15d
0x140077690  test    r12, r12
0x140077693  jnz     short loc_1400776E4
0x140077695  mov     edi, r15d
0x140077698  lea     ebx, [r15+57h]
0x14007769c  lea     rax, WPP_GLOBAL_Control
0x1400776a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400776aa  cmp     rcx, rax
0x1400776ad  jz      loc_1400779A3
0x1400776b3  test    byte ptr [rcx+1Ch], 8
0x1400776b7  jz      loc_1400779A3
0x1400776bd  lea     edx, [rbx-4Dh]
0x1400776c0  lea     rax, aPpwszoutxmldoc; "ppwszOutXmlDoc"
0x1400776c7  mov     [rsp+68h+var_48], rax
0x1400776cc  mov     r9d, ebx
0x1400776cf  lea     r8, WPP_cb2b14357a2c349c2c07fc822528e543_Traceguids
0x1400776d6  mov     rcx, [rcx+10h]
0x1400776da  call    WPP_SF_Ds
0x1400776df  jmp     loc_1400779A3
0x1400776e4  lea     rcx, [rbp+var_38]; struct CXMLDocument *
0x1400776e8  call    ?XmlDocInit@@YAHPEAVCXMLDocument@@@Z; XmlDocInit(CXMLDocument *)
0x1400776ed  test    eax, eax
0x1400776ef  jnz     short loc_140077740
0x1400776f1  mov     edi, r15d
0x1400776f4  call    cs:__imp_GetLastError
0x1400776fa  mov     ebx, eax
0x1400776fc  lea     rax, WPP_GLOBAL_Control
0x140077703  mov     rcx, cs:WPP_GLOBAL_Control
0x14007770a  cmp     rcx, rax
0x14007770d  jz      loc_1400779A3
0x140077713  test    byte ptr [rcx+1Ch], 8
0x140077717  jz      loc_1400779A3
0x14007771d  call    cs:__imp_GetLastError
0x140077723  mov     edx, 0Bh
0x140077728  lea     rcx, aGetlasterror_1; "GetLastError()"
0x14007772f  mov     [rsp+68h+var_48], rcx
0x140077734  mov     r9d, eax
0x140077737  mov     rcx, cs:WPP_GLOBAL_Control
0x14007773e  jmp     short loc_1400776CF
0x140077740  lea     r8, [rbp+arg_18]; struct CXMLNode **
0x140077744  lea     rdx, aAsrsif; "AsrSif"
0x14007774b  lea     rcx, [rbp+var_38]; struct CXMLDocument *
0x14007774f  call    ?XmlDocCreateNode@@YAHPEAVCXMLDocument@@PEAGPEAPEAVCXMLNode@@@Z; XmlDocCreateNode(CXMLDocument *,ushort *,CXMLNode * *)
0x140077754  mov     rsi, [rbp+arg_18]
0x140077758  test    eax, eax
0x14007775a  jnz     short loc_1400777CA
0x14007775c  mov     edi, r15d
0x14007775f  call    cs:__imp_GetLastError
0x140077765  mov     ebx, eax
0x140077767  lea     rax, WPP_GLOBAL_Control
0x14007776e  mov     rcx, cs:WPP_GLOBAL_Control
0x140077775  cmp     rcx, rax
0x140077778  jz      loc_140077996
0x14007777e  test    byte ptr [rcx+1Ch], 8
0x140077782  jz      loc_140077996
0x140077788  call    cs:__imp_GetLastError
0x14007778e  mov     edx, 0Ch
0x140077793  lea     rcx, aVersion; "Version"
0x14007779a  mov     [rsp+68h+var_40], rcx
0x14007779f  lea     rcx, aGetlasterror_1; "GetLastError()"
0x1400777a6  mov     [rsp+68h+var_48], rcx
0x1400777ab  mov     r9d, eax
0x1400777ae  lea     r8, WPP_cb2b14357a2c349c2c07fc822528e543_Traceguids
0x1400777b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400777bc  mov     rcx, [rcx+10h]
0x1400777c0  call    WPP_SF_DsS
0x1400777c5  jmp     loc_140077996
0x1400777ca  mov     [rbp+var_18], r15d
0x1400777ce  mov     rdx, [rsi+8]
0x1400777d2  lea     rcx, [rbp+var_30]
0x1400777d6  call    ??4?$CComPtr@VIVssSnapshotSetDescription@@@ATL@@QEAAPEAVIVssSnapshotSetDescription@@PEAV2@@Z; ATL::CComPtr<IVssSnapshotSetDescription>::operator=(IVssSnapshotSetDescription *)
0x1400777db  lea     rdx, [rbp+var_30]
0x1400777df  lea     rcx, [rbp+var_28]
0x1400777e3  call    ??4?$CComPtr@UIVssSnapshotProvider@@@ATL@@QEAAPEAUIVssSnapshotProvider@@AEBV01@@Z; ATL::CComPtr<IVssSnapshotProvider>::operator=(ATL::CComPtr<IVssSnapshotProvider> const &)
0x1400777e8  test    r14, r14
0x1400777eb  jz      short loc_140077862
0x1400777ed  mov     r8, rsi; struct CXMLNode *
0x1400777f0  lea     rdx, [rbp+var_38]; struct CXMLDocument *
0x1400777f4  mov     rcx, r14; this
0x1400777f7  call    ?BuildXmlNodes@AsrSystem@@QEAAHPEAVCXMLDocument@@PEAVCXMLNode@@@Z; AsrSystem::BuildXmlNodes(CXMLDocument *,CXMLNode *)
0x1400777fc  test    eax, eax
0x1400777fe  jnz     short loc_140077862
0x140077800  mov     edi, r15d
0x140077803  call    cs:__imp_GetLastError
0x140077809  mov     ebx, eax
0x14007780b  lea     rax, WPP_GLOBAL_Control
0x140077812  mov     rcx, cs:WPP_GLOBAL_Control
0x140077819  cmp     rcx, rax
0x14007781c  jz      loc_140077996
0x140077822  test    byte ptr [rcx+1Ch], 8
0x140077826  jz      loc_140077996
0x14007782c  call    cs:__imp_GetLastError
0x140077832  mov     edx, 0Dh
0x140077837  lea     rcx, aGetlasterror_1; "GetLastError()"
0x14007783e  mov     [rsp+68h+var_48], rcx
0x140077843  mov     r9d, eax
0x140077846  mov     rcx, cs:WPP_GLOBAL_Control
0x14007784d  lea     r8, WPP_cb2b14357a2c349c2c07fc822528e543_Traceguids
0x140077854  mov     rcx, [rcx+10h]
0x140077858  call    WPP_SF_Ds
0x14007785d  jmp     loc_140077996
0x140077862  test    rbx, rbx
0x140077865  jz      short loc_1400778B3
0x140077867  mov     r8, rsi; struct CXMLNode *
0x14007786a  lea     rdx, [rbp+var_38]; struct CXMLDocument *
0x14007786e  mov     rcx, rbx; this
0x140077871  call    ?BuildXmlNodes@AsrFmt@@QEAAHPEAVCXMLDocument@@PEAVCXMLNode@@@Z; AsrFmt::BuildXmlNodes(CXMLDocument *,CXMLNode *)
0x140077876  test    eax, eax
0x140077878  jnz     short loc_1400778B3
0x14007787a  mov     edi, r15d
0x14007787d  call    cs:__imp_GetLastError
0x140077883  mov     ebx, eax
0x140077885  lea     rax, WPP_GLOBAL_Control
0x14007788c  mov     rcx, cs:WPP_GLOBAL_Control
0x140077893  cmp     rcx, rax
0x140077896  jz      loc_140077996
0x14007789c  test    byte ptr [rcx+1Ch], 8
0x1400778a0  jz      loc_140077996
0x1400778a6  call    cs:__imp_GetLastError
0x1400778ac  mov     edx, 0Eh
0x1400778b1  jmp     short loc_140077837
0x1400778b3  test    rdi, rdi
0x1400778b6  jz      short loc_140077907
0x1400778b8  mov     r8, rsi; struct CXMLNode *
0x1400778bb  lea     rdx, [rbp+var_38]; struct CXMLDocument *
0x1400778bf  mov     rcx, rdi; this
0x1400778c2  call    ?BuildXmlNodes@AsrLdm@@QEAAHPEAVCXMLDocument@@PEAVCXMLNode@@@Z; AsrLdm::BuildXmlNodes(CXMLDocument *,CXMLNode *)
0x1400778c7  test    eax, eax
0x1400778c9  jnz     short loc_140077907
0x1400778cb  mov     edi, r15d
0x1400778ce  call    cs:__imp_GetLastError
0x1400778d4  mov     ebx, eax
0x1400778d6  lea     rax, WPP_GLOBAL_Control
0x1400778dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400778e4  cmp     rcx, rax
0x1400778e7  jz      loc_140077996
0x1400778ed  test    byte ptr [rcx+1Ch], 8
0x1400778f1  jz      loc_140077996
0x1400778f7  call    cs:__imp_GetLastError
0x1400778fd  mov     edx, 0Fh
0x140077902  jmp     loc_140077837
0x140077907  mov     rcx, rsi; this
0x14007790a  call    ?SaveAsXML@CXMLNode@@QEAAPEAGXZ; CXMLNode::SaveAsXML(void)
0x14007790f  mov     r13, rax
0x140077912  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140077916  inc     rcx
0x140077919  cmp     [rax+rcx*2], r15w
0x14007791e  jnz     short loc_140077916
0x140077920  lea     r15d, [rcx+1]
0x140077924  lea     ecx, [r15+r15]; Size
0x140077928  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x14007792d  mov     r14, rax
0x140077930  test    rax, rax
0x140077933  jnz     short loc_140077970
0x140077935  xor     r15d, r15d
0x140077938  mov     edi, r15d
0x14007793b  lea     r9d, [rax+0Eh]
0x14007793f  mov     ebx, r9d
0x140077942  lea     rax, WPP_GLOBAL_Control
0x140077949  mov     rcx, cs:WPP_GLOBAL_Control
0x140077950  cmp     rcx, rax
0x140077953  jz      short loc_140077996
0x140077955  test    byte ptr [rcx+1Ch], 8
0x140077959  jz      short loc_140077996
0x14007795b  lea     edx, [r14+10h]
0x14007795f  lea     rax, aPwszxmldoc; "pwszXmlDoc"
0x140077966  mov     [rsp+68h+var_48], rax
0x14007796b  jmp     loc_14007784D
0x140077970  xor     ebx, ebx
0x140077972  lea     edi, [rbx+1]
0x140077975  mov     r8d, r15d
0x140077978  add     r8, r8; Size
0x14007797b  mov     rdx, r13; Src
0x14007797e  mov     rcx, r14; void *
0x140077981  call    memcpy_0
0x140077986  lea     eax, [r15-1]
0x14007798a  xor     r15d, r15d
0x14007798d  mov     [r14+rax*2], r15w
0x140077992  mov     [r12], r14
0x140077996  test    rsi, rsi
0x140077999  jz      short loc_1400779A3
0x14007799b  mov     rcx, rsi; this
0x14007799e  call    ??_GCXMLNode@@QEAAPEAXI@Z; CXMLNode::`scalar deleting destructor'(uint)
0x1400779a3  xor     ecx, ecx; pv
0x1400779a5  call    cs:__imp_CoTaskMemFree
0x1400779ab  mov     rcx, r13; bstrString
0x1400779ae  call    cs:__imp_SysFreeString
0x1400779b4  lea     rcx, aCreatexmldocum; "CreateXmlDocument"
0x1400779bb  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400779c0  mov     ecx, ebx; dwErrCode
0x1400779c2  call    cs:__imp_SetLastError
0x1400779c8  nop
0x1400779c9  lea     rcx, [rbp+var_38]; this
0x1400779cd  call    ??1CXMLDocument@@QEAA@XZ; CXMLDocument::~CXMLDocument(void)
0x1400779d2  mov     eax, edi
0x1400779d4  add     rsp, 68h
0x1400779d8  pop     r15
0x1400779da  pop     r14
0x1400779dc  pop     r13
0x1400779de  pop     r12
0x1400779e0  pop     rdi
0x1400779e1  pop     rsi
0x1400779e2  pop     rbx
0x1400779e3  pop     rbp
0x1400779e4  retn
```
