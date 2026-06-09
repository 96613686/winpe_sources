# CGramFrontEnd::CompileStream2(IStream *,IStream *,IStream *,IUnknown *,ISpErrorLog *,ulong,ushort *,ushort *)

- ea: `0x1800d14b0`
- end: `0x1800d1ac0`
- name: `?CompileStream2@CGramFrontEnd@@UEAAJPEAUIStream@@00PEAUIUnknown@@PEAUISpErrorLog@@KPEAG3@Z`
- size: `1552`
- prototype: `__int64 __usercall@<rax>(CGramFrontEnd *__hidden this@<rcx>, struct IStream *@<rdx>, struct IStream *@<r8>, struct IStream *@<r9>, struct IUnknown *, struct ISpErrorLog *, unsigned int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000bec4`
- `0x180079e30`
- `0x18007d31c`
- `0x1800d06b0`
- `0x1800d14b0`
- `0x1800daac0`
- `0x1800fb528`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d150d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d150d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d1a5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d1a7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d1a5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d1a7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d17ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d1899`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d17ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d1899`

## pseudocode

```c
__int64 __fastcall CGramFrontEnd::CompileStream2(
        CGramFrontEnd *this,
        struct IStream *a2,
        struct IStream *a3,
        struct IStream *a4,
        struct IUnknown *a5,
        struct ISpErrorLog *a6)
{
  __int64 v6; // rsi
  HRESULT Instance; // ebx
  _DWORD *v12; // rax
  _DWORD *v13; // rdx
  __int64 v14; // rax
  void *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v26[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v27[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v29; // [rsp+68h] [rbp-98h]
  __int64 (__fastcall *v30)(); // [rsp+70h] [rbp-90h]
  int v31; // [rsp+78h] [rbp-88h]
  const wchar_t *v32; // [rsp+80h] [rbp-80h]
  __int64 (__fastcall *v33)(); // [rsp+88h] [rbp-78h]
  int v34; // [rsp+90h] [rbp-70h]
  const unsigned __int16 *v35; // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v36)(); // [rsp+A0h] [rbp-60h]
  int v37; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v38; // [rsp+B0h] [rbp-50h]
  __int64 (__fastcall *v39)(); // [rsp+B8h] [rbp-48h]
  int v40; // [rsp+C0h] [rbp-40h]
  const wchar_t *v41; // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v42)(); // [rsp+D0h] [rbp-30h]
  int v43; // [rsp+D8h] [rbp-28h]
  const wchar_t *v44; // [rsp+E0h] [rbp-20h]
  __int64 (__fastcall *v45)(); // [rsp+E8h] [rbp-18h]
  int v46; // [rsp+F0h] [rbp-10h]
  const unsigned __int16 *v47; // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall *v48)(); // [rsp+100h] [rbp+0h]
  int v49; // [rsp+108h] [rbp+8h]
  const wchar_t *v50; // [rsp+110h] [rbp+10h]
  __int64 (__fastcall *v51)(); // [rsp+118h] [rbp+18h]
  int v52; // [rsp+120h] [rbp+20h]
  const wchar_t *v53; // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v54)(); // [rsp+130h] [rbp+30h]
  int v55; // [rsp+138h] [rbp+38h]
  const wchar_t *v56; // [rsp+140h] [rbp+40h]
  __int64 (__fastcall *v57)(); // [rsp+148h] [rbp+48h]
  int v58; // [rsp+150h] [rbp+50h]
  const wchar_t *v59; // [rsp+158h] [rbp+58h]
  __int64 (__fastcall *v60)(); // [rsp+160h] [rbp+60h]
  int v61; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v62; // [rsp+170h] [rbp+70h]
  __int64 (__fastcall *v63)(); // [rsp+178h] [rbp+78h]
  int v64; // [rsp+180h] [rbp+80h]
  const unsigned __int16 *v65; // [rsp+188h] [rbp+88h]
  __int64 (__fastcall *v66)(); // [rsp+190h] [rbp+90h]
  int v67; // [rsp+198h] [rbp+98h]
  const unsigned __int16 *v68; // [rsp+1A0h] [rbp+A0h]
  __int64 (__fastcall *v69)(); // [rsp+1A8h] [rbp+A8h]
  int v70; // [rsp+1B0h] [rbp+B0h]
  const unsigned __int16 *v71; // [rsp+1B8h] [rbp+B8h]
  __int64 (__fastcall *v72)(); // [rsp+1C0h] [rbp+C0h]
  int v73; // [rsp+1C8h] [rbp+C8h]
  const unsigned __int16 *v74; // [rsp+1D0h] [rbp+D0h]
  __int64 (__fastcall *v75)(); // [rsp+1D8h] [rbp+D8h]
  int v76; // [rsp+1E0h] [rbp+E0h]
  const unsigned __int16 *v77; // [rsp+1E8h] [rbp+E8h]
  __int64 (__fastcall *v78)(); // [rsp+1F0h] [rbp+F0h]
  int v79; // [rsp+1F8h] [rbp+F8h]
  const wchar_t *v80; // [rsp+200h] [rbp+100h]
  __int64 v81; // [rsp+208h] [rbp+108h]
  int v82; // [rsp+210h] [rbp+110h]
  const wchar_t *v83; // [rsp+218h] [rbp+118h]
  __int64 v84; // [rsp+220h] [rbp+120h]
  int v85; // [rsp+228h] [rbp+128h]
  const WCHAR *v86; // [rsp+230h] [rbp+130h]
  __int64 (__fastcall *v87)(); // [rsp+238h] [rbp+138h]
  int v88; // [rsp+240h] [rbp+140h]

  v6 = (__int64)this + 16;
  v26[0] = 0;
  v25 = 0;
  if ( !this )
    v6 = 8;
  EnterCriticalSection((LPCRITICAL_SECTION)v6);
  *((_WORD *)this + 40) = 1033;
  if ( a2 && a3 && !a5 )
  {
    v28 = 0;
    v39 = CXMLNode<CPhraseNode>::CreateNode;
    v27[0] = L"GRAMMAR";
    v40 = 1;
    v27[1] = CXMLNode<CGrammarNode>::CreateNode;
    v29 = L"RULE";
    v30 = CXMLNode<CRuleNode>::CreateNode;
    v32 = L"DEFINE";
    v33 = CXMLNode<CDefineNode>::CreateNode;
    v35 = L"ID";
    v36 = CXMLNode<CIdNode>::CreateNode;
    v38 = L"PHRASE";
    v41 = L"PN";
    v44 = L"P";
    v47 = L"OPT";
    v50 = L"O";
    v53 = L"LIST";
    v56 = L"LN";
    v59 = L"L";
    v62 = L"RULEREF";
    v63 = CXMLNode<CRuleRefNode>::CreateNode;
    v65 = L"TEXTBUFFER";
    v66 = CXMLNode<CTextBufferNode>::CreateNode;
    v68 = L"SUBSET";
    v69 = CXMLNode<CTextSubsetNode>::CreateNode;
    v71 = L"WILDCARD";
    v72 = CXMLNode<CWildCardNode>::CreateNode;
    v43 = 1;
    v46 = 1;
    v74 = L"DICTATION";
    v42 = CXMLNode<CPhraseNode>::CreateNode;
    v45 = CXMLNode<CPhraseNode>::CreateNode;
    v48 = CXMLNode<CPhraseNode>::CreateNode;
    v49 = 2;
    v51 = CXMLNode<CPhraseNode>::CreateNode;
    v52 = 2;
    v75 = CXMLNode<CDictationNode>::CreateNode;
    v31 = 4;
    v34 = 9;
    v37 = 10;
    v54 = CXMLNode<CListNode>::CreateNode;
    v55 = 3;
    v57 = CXMLNode<CListNode>::CreateNode;
    v58 = 3;
    v60 = CXMLNode<CListNode>::CreateNode;
    v61 = 3;
    v64 = 5;
    v67 = 11;
    v70 = 12;
    v73 = 7;
    v76 = 13;
    v77 = L"RESOURCE";
    v79 = 6;
    v78 = CXMLNode<CResourceNode>::CreateNode;
    v81 = 0;
    v80 = L"OUTPUT";
    v82 = 16;
    v83 = L"SCRIPT";
    v84 = 0;
    v86 = &cchOriginalDestLength;
    v87 = CXMLNode<CLeafNode>::CreateNode;
    v85 = 17;
    v88 = 8;
    ppv = 0;
    Instance = CoCreateInstance(
                 &CLSID_FreeThreadedDOMDocument60,
                 0,
                 0x17u,
                 &GUID_d242361e_51a0_11d2_9caf_0060b0ec3d39,
                 &ppv);
    if ( Instance < 0 )
    {
      LogError(0xFFFFFFFF, Instance, a6, 0x94u, &cchOriginalDestLength);
    }
    else
    {
      v12 = operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
      v13 = v12;
      if ( v12 )
      {
        v12[2] = 1;
        *(_QWORD *)v12 = &CNodeFactory::`vftable';
        *((_QWORD *)v12 + 2) = 0;
        *((_QWORD *)v12 + 3) = 0;
        *((_QWORD *)v12 + 5) = 0;
        *((_QWORD *)v12 + 8) = 0;
        *((_QWORD *)v12 + 11) = a6;
        *((_QWORD *)v12 + 14) = v27;
        v12[30] = 21;
      }
      else
      {
        v13 = 0;
      }
      *((_QWORD *)this + 9) = v13;
      if ( v13 )
      {
        Instance = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 24LL))(ppv);
        if ( Instance < 0 )
          goto LABEL_35;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9));
        Instance = (*(__int64 (__fastcall **)(LPVOID, struct IStream *))(*(_QWORD *)ppv + 128LL))(ppv, a2);
        if ( Instance < 0 )
          goto LABEL_35;
        Instance = CoCreateInstance(
                     &CLSID_SpGramCompBackend,
                     0,
                     0x17u,
                     &GUID_3ddca27c_665c_4786_9f97_8c90c3488b61,
                     (LPVOID *)(*((_QWORD *)this + 9) + 24LL));
        if ( Instance < 0 )
          goto LABEL_35;
        Instance = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, struct ISpErrorLog *))(**(_QWORD **)(*((_QWORD *)this + 9) + 24LL)
                                                                                             + 88LL))(
                     *(_QWORD *)(*((_QWORD *)this + 9) + 24LL),
                     a3,
                     a6);
        if ( Instance < 0 )
          goto LABEL_35;
        v14 = *((_QWORD *)this + 9);
        *((_DWORD *)this + 24) = 0;
        *(_QWORD *)(v14 + 32) = this;
        v15 = operator new(0xE8u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v15 )
          v16 = CXMLNode<CGrammarNode>::CXMLNode<CGrammarNode>(v15);
        else
          v16 = 0;
        *((_QWORD *)this + 8) = v16;
        if ( v16 )
        {
          *(_QWORD *)(v16 + 56) = *((_QWORD *)this + 9);
          *(_DWORD *)(*((_QWORD *)this + 8) + 16LL) = 15;
          Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 176LL))(ppv, *((_QWORD *)this + 8));
          if ( Instance >= 0 )
          {
            v17 = *((_QWORD *)this + 9);
            v18 = *((_QWORD *)this + 8);
            *(_QWORD *)(v18 + 8) = *(_QWORD *)(v17 + 16);
            *(_QWORD *)(v17 + 16) = v18;
            if ( !ppv
              || (Instance = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 224LL))(ppv, 20),
                  Instance >= 0)
              && (!ppv
               || (Instance = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 192LL))(ppv, 0xFFFFFFFFLL),
                   Instance >= 0)) )
            {
              v19 = *((_QWORD *)this + 8);
              if ( !v19
                || (Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, struct ISpErrorLog *))(*(_QWORD *)v19 + 8LL))(
                                 v19,
                                 0,
                                 0,
                                 *(_QWORD *)(*((_QWORD *)this + 9) + 24LL),
                                 a6),
                    Instance >= 0) )
              {
                v20 = *((_QWORD *)this + 9);
                if ( !v20
                  || (Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v20 + 24) + 80LL))(
                                   *(_QWORD *)(v20 + 24),
                                   0),
                      Instance >= 0) )
                {
                  v21 = *((_QWORD *)this + 9);
                  if ( v21 )
                  {
                    v22 = *(_QWORD *)(v21 + 24);
                    if ( v22 )
                      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v22 + 88LL))(v22, 0, 0);
                  }
                  if ( a4 )
                    Instance = CGramFrontEnd::WriteDefines(this, a4);
                }
              }
            }
          }
          goto LABEL_35;
        }
      }
      Instance = -2147024882;
    }
LABEL_35:
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&ppv);
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v25);
    ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(v26);
    return (unsigned int)Instance;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(&v25);
  ATL::CComPtrBase<ISpLexicon2>::~CComPtrBase<ISpLexicon2>(v26);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800d14b0  push    rbp
0x1800d14b2  push    rbx
0x1800d14b3  push    rsi
0x1800d14b4  push    rdi
0x1800d14b5  push    r12
0x1800d14b7  push    r13
0x1800d14b9  push    r14
0x1800d14bb  push    r15
0x1800d14bd  lea     rbp, [rsp-168h]
0x1800d14c5  sub     rsp, 268h
0x1800d14cc  mov     rax, cs:__security_cookie
0x1800d14d3  xor     rax, rsp
0x1800d14d6  mov     [rbp+1A0h+var_50], rax
0x1800d14dd  mov     r14, [rbp+1A0h+arg_28]
0x1800d14e4  lea     rsi, [rcx+10h]
0x1800d14e8  xor     ebx, ebx
0x1800d14ea  mov     rdi, rcx
0x1800d14ed  test    rcx, rcx
0x1800d14f0  mov     [rsp+2A0h+var_260], rbx
0x1800d14f5  mov     r12, r9
0x1800d14f8  mov     [rsp+2A0h+var_268], rbx
0x1800d14fd  mov     r15, r8
0x1800d1500  mov     r13, rdx
0x1800d1503  lea     eax, [rbx+8]
0x1800d1506  cmovz   rsi, rax
0x1800d150a  mov     rcx, rsi; lpCriticalSection
0x1800d150d  call    cs:__imp_EnterCriticalSection
0x1800d1513  mov     word ptr [rdi+50h], 409h
0x1800d1519  test    r13, r13
0x1800d151c  jz      loc_1800D1A7B
0x1800d1522  test    r15, r15
0x1800d1525  jz      loc_1800D1A7B
0x1800d152b  cmp     [rbp+1A0h+arg_20], rbx
0x1800d1532  jnz     loc_1800D1A7B
0x1800d1538  lea     rdx, ?CreateNode@?$CXMLNode@VCPhraseNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CPhraseNode>::CreateNode(void)
0x1800d153f  mov     [rsp+2A0h+var_240], ebx
0x1800d1543  lea     rax, aGrammar_2; "GRAMMAR"
0x1800d154a  mov     [rbp+1A0h+var_1E8], rdx
0x1800d154e  mov     [rsp+2A0h+var_250], rax
0x1800d1553  lea     ecx, [rbx+1]
0x1800d1556  lea     rax, ?CreateNode@?$CXMLNode@VCGrammarNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CGrammarNode>::CreateNode(void)
0x1800d155d  mov     [rbp+1A0h+var_1E0], ecx
0x1800d1560  mov     [rsp+2A0h+var_248], rax
0x1800d1565  lea     rax, aRule_0; "RULE"
0x1800d156c  mov     [rsp+2A0h+var_238], rax
0x1800d1571  lea     rax, ?CreateNode@?$CXMLNode@VCRuleNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CRuleNode>::CreateNode(void)
0x1800d1578  mov     [rsp+2A0h+var_230], rax
0x1800d157d  lea     rax, aDefine; "DEFINE"
0x1800d1584  mov     [rbp+1A0h+var_220], rax
0x1800d1588  lea     rax, ?CreateNode@?$CXMLNode@VCDefineNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CDefineNode>::CreateNode(void)
0x1800d158f  mov     [rbp+1A0h+var_218], rax
0x1800d1593  lea     rax, aId_0; "ID"
0x1800d159a  mov     [rbp+1A0h+var_208], rax
0x1800d159e  lea     rax, ?CreateNode@?$CXMLNode@VCIdNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CIdNode>::CreateNode(void)
0x1800d15a5  mov     [rbp+1A0h+var_200], rax
0x1800d15a9  lea     rax, aPhrase; "PHRASE"
0x1800d15b0  mov     [rbp+1A0h+var_1F0], rax
0x1800d15b4  lea     rax, aPn; "PN"
0x1800d15bb  mov     [rbp+1A0h+var_1D8], rax
0x1800d15bf  lea     rax, aP_0; "P"
0x1800d15c6  mov     [rbp+1A0h+var_1C0], rax
0x1800d15ca  lea     rax, aOpt; "OPT"
0x1800d15d1  mov     [rbp+1A0h+var_1A8], rax
0x1800d15d5  lea     rax, aO; "O"
0x1800d15dc  mov     [rbp+1A0h+var_190], rax
0x1800d15e0  lea     rax, aList; "LIST"
0x1800d15e7  mov     [rbp+1A0h+var_178], rax
0x1800d15eb  lea     rax, aLn; "LN"
0x1800d15f2  mov     [rbp+1A0h+var_160], rax
0x1800d15f6  lea     rax, asc_1802C2930; "L"
0x1800d15fd  mov     [rbp+1A0h+var_148], rax
0x1800d1601  lea     rax, aRuleref; "RULEREF"
0x1800d1608  mov     [rbp+1A0h+var_130], rax
0x1800d160c  lea     rax, ?CreateNode@?$CXMLNode@VCRuleRefNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CRuleRefNode>::CreateNode(void)
0x1800d1613  mov     [rbp+1A0h+var_128], rax
0x1800d1617  lea     rax, aTextbuffer; "TEXTBUFFER"
0x1800d161e  mov     [rbp+1A0h+var_118], rax
0x1800d1625  lea     rax, ?CreateNode@?$CXMLNode@VCTextBufferNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CTextBufferNode>::CreateNode(void)
0x1800d162c  mov     [rbp+1A0h+var_110], rax
0x1800d1633  lea     rax, aSubset_0; "SUBSET"
0x1800d163a  mov     [rbp+1A0h+var_100], rax
0x1800d1641  lea     rax, ?CreateNode@?$CXMLNode@VCTextSubsetNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CTextSubsetNode>::CreateNode(void)
0x1800d1648  mov     [rbp+1A0h+var_F8], rax
0x1800d164f  lea     rax, aWildcard; "WILDCARD"
0x1800d1656  mov     [rbp+1A0h+var_E8], rax
0x1800d165d  lea     rax, ?CreateNode@?$CXMLNode@VCWildCardNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CWildCardNode>::CreateNode(void)
0x1800d1664  mov     [rbp+1A0h+var_E0], rax
0x1800d166b  lea     rax, aDictation_0; "DICTATION"
0x1800d1672  mov     [rbp+1A0h+var_1C8], ecx
0x1800d1675  mov     [rbp+1A0h+var_1B0], ecx
0x1800d1678  lea     ecx, [rbx+2]
0x1800d167b  mov     [rbp+1A0h+var_D0], rax
0x1800d1682  lea     rax, ?CreateNode@?$CXMLNode@VCDictationNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CDictationNode>::CreateNode(void)
0x1800d1689  mov     [rbp+1A0h+var_1D0], rdx
0x1800d168d  mov     [rbp+1A0h+var_1B8], rdx
0x1800d1691  mov     [rbp+1A0h+var_1A0], rdx
0x1800d1695  mov     [rbp+1A0h+var_198], ecx
0x1800d1698  mov     [rbp+1A0h+var_188], rdx
0x1800d169c  lea     rdx, ?CreateNode@?$CXMLNode@VCListNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CListNode>::CreateNode(void)
0x1800d16a3  mov     [rbp+1A0h+var_180], ecx
0x1800d16a6  lea     ecx, [rbx+3]
0x1800d16a9  mov     [rbp+1A0h+var_C8], rax
0x1800d16b0  mov     [rsp+2A0h+var_228], 4
0x1800d16b8  mov     [rbp+1A0h+var_210], 9
0x1800d16bf  mov     [rbp+1A0h+var_1F8], 0Ah
0x1800d16c6  mov     [rbp+1A0h+var_170], rdx
0x1800d16ca  mov     [rbp+1A0h+var_168], ecx
0x1800d16cd  mov     [rbp+1A0h+var_158], rdx
0x1800d16d1  mov     [rbp+1A0h+var_150], ecx
0x1800d16d4  mov     [rbp+1A0h+var_140], rdx
0x1800d16d8  mov     [rbp+1A0h+var_138], ecx
0x1800d16db  mov     [rbp+1A0h+var_120], 5
0x1800d16e5  mov     [rbp+1A0h+var_108], 0Bh
0x1800d16ef  mov     [rbp+1A0h+var_F0], 0Ch
0x1800d16f9  mov     [rbp+1A0h+var_D8], 7
0x1800d1703  lea     rax, aResource_0; "RESOURCE"
0x1800d170a  mov     [rbp+1A0h+var_C0], 0Dh
0x1800d1714  mov     [rbp+1A0h+var_B8], rax
0x1800d171b  lea     r9, _GUID_d242361e_51a0_11d2_9caf_0060b0ec3d39; riid
0x1800d1722  lea     rax, ?CreateNode@?$CXMLNode@VCResourceNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CResourceNode>::CreateNode(void)
0x1800d1729  mov     [rbp+1A0h+var_A8], 6
0x1800d1733  mov     [rbp+1A0h+var_B0], rax
0x1800d173a  lea     r8d, [rbx+17h]; dwClsContext
0x1800d173e  lea     rax, aOutput; "OUTPUT"
0x1800d1745  mov     [rbp+1A0h+var_98], rbx
0x1800d174c  mov     [rbp+1A0h+var_A0], rax
0x1800d1753  lea     rcx, CLSID_FreeThreadedDOMDocument60; rclsid
0x1800d175a  lea     rax, aScript; "SCRIPT"
0x1800d1761  mov     [rbp+1A0h+var_90], 10h
0x1800d176b  mov     [rbp+1A0h+var_88], rax
0x1800d1772  xor     edx, edx; pUnkOuter
0x1800d1774  lea     rax, cchOriginalDestLength
0x1800d177b  mov     [rbp+1A0h+var_80], rbx
0x1800d1782  mov     [rbp+1A0h+var_70], rax
0x1800d1789  lea     rax, ?CreateNode@?$CXMLNode@VCLeafNode@@@@SAPEAVCXMLTreeNode@@XZ; CXMLNode<CLeafNode>::CreateNode(void)
0x1800d1790  mov     [rbp+1A0h+var_68], rax
0x1800d1797  lea     rax, [rsp+2A0h+var_270]
0x1800d179c  mov     [rsp+2A0h+ppv], rax; ppv
0x1800d17a1  mov     [rbp+1A0h+var_78], 11h
0x1800d17ab  mov     [rbp+1A0h+var_60], 8
0x1800d17b5  mov     [rsp+2A0h+var_270], rbx
0x1800d17ba  call    cs:__imp_CoCreateInstance
0x1800d17c0  mov     ebx, eax
0x1800d17c2  test    eax, eax
0x1800d17c4  js      loc_1800D1A31
0x1800d17ca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d17d1  mov     ecx, 80h; unsigned __int64
0x1800d17d6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d17db  xor     ecx, ecx
0x1800d17dd  mov     rdx, rax
0x1800d17e0  test    rax, rax
0x1800d17e3  jz      short loc_1800D181C
0x1800d17e5  mov     dword ptr [rdx+8], 1
0x1800d17ec  lea     rax, ??_7CNodeFactory@@6B@; const CNodeFactory::`vftable'
0x1800d17f3  mov     [rdx], rax
0x1800d17f6  lea     rax, [rsp+2A0h+var_250]
0x1800d17fb  mov     [rdx+10h], rcx
0x1800d17ff  mov     [rdx+18h], rcx
0x1800d1803  mov     [rdx+28h], rcx
0x1800d1807  mov     [rdx+40h], rcx
0x1800d180b  mov     [rdx+58h], r14
0x1800d180f  mov     [rdx+70h], rax
0x1800d1813  mov     dword ptr [rdx+78h], 15h
0x1800d181a  jmp     short loc_1800D181F
0x1800d181c  mov     rdx, rcx
0x1800d181f  mov     [rdi+48h], rdx
0x1800d1823  test    rdx, rdx
0x1800d1826  jz      loc_1800D1A2A
0x1800d182c  mov     rcx, [rsp+2A0h+var_270]
0x1800d1831  mov     rax, [rcx]
0x1800d1834  mov     rax, [rax+18h]
0x1800d1838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d183d  mov     ebx, eax
0x1800d183f  test    eax, eax
0x1800d1841  js      loc_1800D1A50
0x1800d1847  mov     rcx, [rdi+48h]
0x1800d184b  mov     rax, [rcx]
0x1800d184e  mov     rax, [rax+10h]
0x1800d1852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1857  mov     rcx, [rsp+2A0h+var_270]
0x1800d185c  mov     rdx, r13
0x1800d185f  mov     rax, [rcx]
0x1800d1862  mov     rax, [rax+80h]
0x1800d1869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d186e  mov     ebx, eax
0x1800d1870  test    eax, eax
0x1800d1872  js      loc_1800D1A50
0x1800d1878  mov     rax, [rdi+48h]
0x1800d187c  lea     r9, _GUID_3ddca27c_665c_4786_9f97_8c90c3488b61; riid
0x1800d1883  xor     edx, edx; pUnkOuter
0x1800d1885  lea     rcx, CLSID_SpGramCompBackend; rclsid
0x1800d188c  add     rax, 18h
0x1800d1890  mov     [rsp+2A0h+ppv], rax; ppv
0x1800d1895  lea     r8d, [rdx+17h]; dwClsContext
0x1800d1899  call    cs:__imp_CoCreateInstance
0x1800d189f  mov     ebx, eax
0x1800d18a1  test    eax, eax
0x1800d18a3  js      loc_1800D1A50
0x1800d18a9  mov     rax, [rdi+48h]
0x1800d18ad  mov     r8, r14
0x1800d18b0  mov     rdx, r15
0x1800d18b3  mov     rcx, [rax+18h]
0x1800d18b7  mov     rax, [rcx]
0x1800d18ba  mov     rax, [rax+58h]
0x1800d18be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d18c3  mov     ebx, eax
0x1800d18c5  test    eax, eax
0x1800d18c7  js      loc_1800D1A50
0x1800d18cd  mov     rax, [rdi+48h]
0x1800d18d1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d18d8  mov     dword ptr [rdi+60h], 0
0x1800d18df  mov     ecx, 0E8h; unsigned __int64
0x1800d18e4  mov     [rax+20h], rdi
0x1800d18e8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d18ed  test    rax, rax
0x1800d18f0  jz      short loc_1800D18FF
0x1800d18f2  mov     rcx, rax
0x1800d18f5  call    ??0?$CXMLNode@VCGrammarNode@@@@QEAA@XZ; CXMLNode<CGrammarNode>::CXMLNode<CGrammarNode>(void)
0x1800d18fa  mov     rcx, rax
0x1800d18fd  jmp     short loc_1800D1901
0x1800d18ff  xor     ecx, ecx
0x1800d1901  mov     [rdi+40h], rcx
0x1800d1905  test    rcx, rcx
0x1800d1908  jz      loc_1800D1A2A
0x1800d190e  mov     rax, [rdi+48h]
0x1800d1912  mov     [rcx+38h], rax
0x1800d1916  mov     rax, [rdi+40h]
0x1800d191a  mov     dword ptr [rax+10h], 0Fh
0x1800d1921  mov     rcx, [rsp+2A0h+var_270]
0x1800d1926  mov     rdx, [rdi+40h]
0x1800d192a  mov     rax, [rcx]
0x1800d192d  mov     rax, [rax+0B0h]
0x1800d1934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1939  mov     ebx, eax
0x1800d193b  test    eax, eax
0x1800d193d  js      loc_1800D1A50
0x1800d1943  mov     rdx, [rdi+48h]
0x1800d1947  mov     rcx, [rdi+40h]
0x1800d194b  mov     rax, [rdx+10h]
0x1800d194f  mov     [rcx+8], rax
0x1800d1953  mov     [rdx+10h], rcx
0x1800d1957  mov     rcx, [rsp+2A0h+var_270]
0x1800d195c  test    rcx, rcx
0x1800d195f  jz      short loc_1800D19A5
0x1800d1961  mov     rax, [rcx]
0x1800d1964  mov     edx, 14h
0x1800d1969  mov     rax, [rax+0E0h]
0x1800d1970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1975  mov     ebx, eax
0x1800d1977  test    eax, eax
0x1800d1979  js      loc_1800D1A50
0x1800d197f  mov     rcx, [rsp+2A0h+var_270]
0x1800d1984  test    rcx, rcx
0x1800d1987  jz      short loc_1800D19A5
0x1800d1989  mov     rax, [rcx]
0x1800d198c  or      edx, 0FFFFFFFFh
0x1800d198f  mov     rax, [rax+0C0h]
0x1800d1996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d199b  mov     ebx, eax
0x1800d199d  test    eax, eax
0x1800d199f  js      loc_1800D1A50
0x1800d19a5  mov     rcx, [rdi+40h]
0x1800d19a9  test    rcx, rcx
0x1800d19ac  jz      short loc_1800D19D2
0x1800d19ae  mov     rax, [rcx]
0x1800d19b1  xor     r8d, r8d
0x1800d19b4  mov     r9, [rdi+48h]
0x1800d19b8  xor     edx, edx
0x1800d19ba  mov     [rsp+2A0h+ppv], r14
0x1800d19bf  mov     rax, [rax+8]
0x1800d19c3  mov     r9, [r9+18h]
0x1800d19c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d19cc  mov     ebx, eax
0x1800d19ce  test    eax, eax
0x1800d19d0  js      short loc_1800D1A50
0x1800d19d2  mov     rcx, [rdi+48h]
0x1800d19d6  test    rcx, rcx
0x1800d19d9  jz      short loc_1800D19F3
0x1800d19db  mov     rcx, [rcx+18h]
0x1800d19df  xor     edx, edx
0x1800d19e1  mov     rax, [rcx]
0x1800d19e4  mov     rax, [rax+50h]
0x1800d19e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d19ed  mov     ebx, eax
0x1800d19ef  test    eax, eax
0x1800d19f1  js      short loc_1800D1A50
0x1800d19f3  mov     rcx, [rdi+48h]
0x1800d19f7  test    rcx, rcx
0x1800d19fa  jz      short loc_1800D1A16
0x1800d19fc  mov     rcx, [rcx+18h]
0x1800d1a00  test    rcx, rcx
0x1800d1a03  jz      short loc_1800D1A16
0x1800d1a05  mov     rax, [rcx]
0x1800d1a08  xor     r8d, r8d
0x1800d1a0b  xor     edx, edx
0x1800d1a0d  mov     rax, [rax+58h]
0x1800d1a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1a16  test    r12, r12
0x1800d1a19  jz      short loc_1800D1A50
0x1800d1a1b  mov     rdx, r12; struct IStream *
  ... truncated ...
```
