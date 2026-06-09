# UiaNodeTraverser::Traverse(IUiaNodeVisitor *,IUiaNode *,int,TraverseStateIn *,TraverseStateOut *,IConnectionBase *)

- ea: `0x18004aa10`
- end: `0x18004c8ba`
- name: `?Traverse@UiaNodeTraverser@@SAJPEAVIUiaNodeVisitor@@PEAVIUiaNode@@HPEAUTraverseStateIn@@PEAUTraverseStateOut@@PEAVIConnectionBase@@@Z`
- size: `7850`
- prototype: `static int(struct IUiaNodeVisitor *, struct IUiaNode *, int, struct TraverseStateIn *, struct TraverseStateOut *, struct IConnectionBase *)`
- caller_count: `11`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800c3f08`
- `0x1800c4710`
- `0x1800c4ee8`
- `0x1800c4ff0`
- `0x1800d12e4`
- `0x1801269e0`
- `0x180126b84`
- `0x18014c330`
- `0x18014ca78`
- `0x18026d1c0`
- `0x18026d51c`

## callees

- `0x18000f680`
- `0x18001c498`
- `0x180029ee0`
- `0x18002a94c`
- `0x18002b608`
- `0x18002f580`
- `0x180046000`
- `0x18004a5c0`
- `0x18004aa10`
- `0x18004cb90`
- `0x180061630`
- `0x180065b70`
- `0x1800c1080`
- `0x1800c2008`
- `0x1800e8338`
- `0x18012d4f8`
- `0x1801457f0`
- `0x18014dfe4`
- `0x180181488`
- `0x180186cd0`
- `0x1801a8ea4`
- `0x1801b2924`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e887c`
- `0x1801e88a0`
- `0x1801e9234`
- `0x18023b1a0`
- `0x18023b9cc`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004c7a8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004c7a8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ac7f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004adc3`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b523`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b5de`
- `OLEAUT32!__imp_SysFreeString` at `0x18004ac7f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004adc3`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b523`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b5de`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004b9a7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004ba20`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004ba85`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004b9a7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004ba20`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004ba85`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18004b892`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18004b892`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18004b905`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18004b905`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18004b8e8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18004b8e8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004b928`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004b928`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004b99a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004ba15`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004ba75`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004b99a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004ba15`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004ba75`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18004b8af`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18004b8af`

## string_xrefs

- `0x18004b9e5`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18004b9fb`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18004ba5b`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18004bbdd`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004c5bb`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004c656`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004c768`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x18004bbff`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004bc40`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004bc5b`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004bd82`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004bf8f`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004bff7`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004c03e`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004c05c`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004c17f`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004c277`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004c2ea`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004c3c7`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004c67a`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004c7e1`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004c7fd`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004c818`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004c85d`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`
- `0x18004c897`: `onecore\windows\accessibletech\uiautomationcore\uianodetraverser.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall UiaNodeTraverser::Traverse(
        struct IUiaNodeVisitor *a1,
        struct IUiaNode *a2,
        int a3,
        struct TraverseStateIn *a4,
        struct TraverseStateOut *a5,
        struct IConnectionBase *a6)
{
  struct TraverseStateIn *v6; // r15
  unsigned int v7; // r12d
  struct IUiaNode *v8; // rsi
  struct IUiaNodeVisitor *v9; // rdi
  struct TraverseStateOut *v10; // r13
  _QWORD *v11; // r14
  __int64 v12; // rax
  __int64 v13; // rbx
  const WCHAR *v14; // rax
  WCHAR *v15; // r13
  bool v16; // r12
  __int64 v17; // rax
  __int64 v18; // rdi
  int v19; // ecx
  struct IUnknown *v20; // rdx
  unsigned __int8 v21; // r8
  __int64 v22; // rbx
  int v23; // ecx
  int v24; // r15d
  SAFEARRAY *v25; // rcx
  OLECHAR *v26; // rcx
  __int64 v27; // rcx
  unsigned int v28; // eax
  unsigned int v29; // ebx
  char v30; // cl
  char v31; // cl
  char v32; // al
  char v33; // r15
  __int64 j; // rdx
  __int64 k; // rdx
  __int64 v36; // rbx
  __int64 v37; // rcx
  struct TraverseStateIn *v38; // rax
  int v39; // eax
  unsigned int v40; // edi
  BOOL v41; // r12d
  __int64 v42; // r13
  WCHAR *v43; // rax
  __int64 v44; // r15
  unsigned int ii; // ebx
  int v46; // eax
  int v47; // edi
  struct IUiaNode *v48; // r12
  __int64 v49; // rbx
  int v50; // eax
  unsigned int v51; // edi
  int v52; // edx
  int v53; // edx
  int v54; // r8d
  unsigned int v55; // r13d
  unsigned int v56; // ecx
  bool v57; // zf
  unsigned int v58; // edx
  struct IRawElementProviderSimple *v59; // rbx
  unsigned int v60; // edi
  int v61; // eax
  struct IUiaNode *v62; // r15
  __int64 v63; // rcx
  int v64; // ecx
  int v65; // edi
  struct IRawElementProviderSimple *v66; // rdi
  int v67; // eax
  unsigned int v68; // r15d
  struct IUiaNode *SlotAsNode; // r15
  __int64 v70; // rax
  unsigned int v71; // edi
  _DWORD *v72; // rax
  _QWORD *v73; // rbx
  void *v74; // rcx
  int v75; // eax
  int NextSibling; // eax
  unsigned int v77; // ebx
  _QWORD *v78; // rcx
  struct IUiaNode *v79; // rbx
  unsigned int v80; // edi
  int v81; // r13d
  bool v82; // r12
  __int64 v83; // rax
  __int64 v84; // rdi
  int v85; // ecx
  struct IUnknown *v86; // rdx
  unsigned __int8 v87; // r8
  __int64 v88; // rbx
  int v89; // ecx
  int v90; // r15d
  struct IUiaNode *v91; // rcx
  OLECHAR *v92; // rcx
  __int64 v93; // rcx
  unsigned int v94; // edx
  unsigned int v95; // ebx
  char v96; // al
  char v97; // al
  char v98; // cl
  int v99; // edx
  int v100; // eax
  unsigned int v101; // ebx
  __int64 v102; // rcx
  _QWORD *v103; // rcx
  __int64 v104; // rbx
  __int64 v105; // rax
  struct UiaNode *v106; // rbx
  __int64 v107; // rcx
  struct IUiaNode *v108; // r9
  int v109; // r13d
  int v110; // r15d
  unsigned int i; // edi
  unsigned int v112; // eax
  unsigned int v113; // edx
  struct IUiaNode *v114; // rcx
  __int64 m; // rdx
  __int64 n; // rdx
  __int64 v117; // rbx
  __int64 v118; // rcx
  HRESULT Vartype; // eax
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  unsigned __int64 v122; // rax
  _DWORD *v123; // r15
  __int64 v124; // r8
  unsigned int jj; // ebx
  __int64 v126; // rdx
  __int64 v127; // r9
  struct TraverseStateOut *v128; // rcx
  int Parent; // eax
  unsigned int v131; // ebx
  const WCHAR *v132; // rbx
  __int64 v133; // rcx
  int TempIdString; // eax
  _QWORD *v135; // rcx
  __int64 v136; // rbx
  struct TraverseStateOut *v137; // rcx
  _QWORD *v138; // rcx
  __int64 v139; // rbx
  _QWORD *v140; // rcx
  __int64 v141; // rdi
  _QWORD *v142; // rcx
  __int64 v143; // rbx
  struct TraverseStateOut *v144; // rcx
  struct TraverseStateOut *v145; // rcx
  _QWORD *v146; // rcx
  __int64 v147; // rbx
  struct TraverseStateOut *v148; // rcx
  int v149; // ecx
  struct TraverseStateOut *v150; // rcx
  UiaNode *v151; // rax
  __int64 v152; // rax
  const char *v153; // r9
  struct UiaNode *v154; // rbx
  int DefaultParent; // eax
  unsigned int v156; // edi
  int v157; // eax
  unsigned int v158; // r12d
  int v159; // eax
  int v160; // eax
  int RuntimeId; // eax
  int v162; // ebx
  SAFEARRAY **lpString2; // [rsp+20h] [rbp-E0h]
  int lpString2b; // [rsp+20h] [rbp-E0h]
  int lpString2a; // [rsp+20h] [rbp-E0h]
  int lpString2c; // [rsp+20h] [rbp-E0h]
  int lpString2d; // [rsp+20h] [rbp-E0h]
  int lpString2e; // [rsp+20h] [rbp-E0h]
  int v169; // [rsp+30h] [rbp-D0h] BYREF
  int v170; // [rsp+34h] [rbp-CCh]
  int v171; // [rsp+38h] [rbp-C8h]
  int v172[2]; // [rsp+40h] [rbp-C0h] BYREF
  bool v173; // [rsp+48h] [rbp-B8h] BYREF
  int v174; // [rsp+4Ch] [rbp-B4h] BYREF
  _QWORD *v175; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v176; // [rsp+58h] [rbp-A8h] BYREF
  struct TraverseStateIn *v177; // [rsp+60h] [rbp-A0h]
  PCNZWCH lpString1; // [rsp+68h] [rbp-98h] BYREF
  struct TraverseStateOut *v179; // [rsp+70h] [rbp-90h]
  SAFEARRAY *psa; // [rsp+78h] [rbp-88h] BYREF
  struct IUiaNodeVisitor *v181; // [rsp+80h] [rbp-80h]
  struct IUiaNode *v182; // [rsp+88h] [rbp-78h] BYREF
  VARTYPE pvt; // [rsp+90h] [rbp-70h] BYREF
  struct IUiaNode *v184; // [rsp+98h] [rbp-68h] BYREF
  struct IUiaNode *v185; // [rsp+A0h] [rbp-60h] BYREF
  struct IUiaNode *v186; // [rsp+A8h] [rbp-58h] BYREF
  BSTR bstrString; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v188; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v189; // [rsp+C0h] [rbp-40h] BYREF
  BSTR v190; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v191; // [rsp+D0h] [rbp-30h] BYREF
  LONG plUbound; // [rsp+D8h] [rbp-28h] BYREF
  LONG plLbound; // [rsp+DCh] [rbp-24h] BYREF
  SAFEARRAY *v194; // [rsp+E0h] [rbp-20h]
  unsigned int v195; // [rsp+E8h] [rbp-18h]
  void *ppvData; // [rsp+F0h] [rbp-10h] BYREF
  struct IUiaNode *v197; // [rsp+F8h] [rbp-8h] BYREF
  struct IUnknown *v198; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 v199; // [rsp+108h] [rbp+8h]
  GUID Buf1; // [rsp+10Ch] [rbp+Ch] BYREF
  BSTR v201; // [rsp+120h] [rbp+20h]
  char v202[8]; // [rsp+148h] [rbp+48h] BYREF
  char v203; // [rsp+150h] [rbp+50h]
  struct IUiaNode *v204; // [rsp+160h] [rbp+60h] BYREF
  __int64 v205; // [rsp+168h] [rbp+68h]
  void *Buf2; // [rsp+170h] [rbp+70h]
  struct IRawElementProviderSimple *v207; // [rsp+178h] [rbp+78h] BYREF
  struct UiaNode *v208; // [rsp+180h] [rbp+80h] BYREF
  int v209[2]; // [rsp+188h] [rbp+88h]
  const unsigned __int16 *v210; // [rsp+190h] [rbp+90h]
  __int64 v211; // [rsp+198h] [rbp+98h]
  const wchar_t *v212; // [rsp+1A0h] [rbp+A0h]
  __int64 v213; // [rsp+1A8h] [rbp+A8h]
  const unsigned __int16 *v214; // [rsp+1B0h] [rbp+B0h]
  __int64 v215; // [rsp+1B8h] [rbp+B8h]
  struct IUiaNode *v216; // [rsp+1C0h] [rbp+C0h]
  __int64 v217; // [rsp+1C8h] [rbp+C8h]
  WCHAR *v218; // [rsp+1D0h] [rbp+D0h]
  __int64 v219; // [rsp+1D8h] [rbp+D8h]
  WCHAR *v220; // [rsp+1E0h] [rbp+E0h]
  GUID v221; // [rsp+1E8h] [rbp+E8h] BYREF
  GUID v222; // [rsp+1F8h] [rbp+F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v6 = a4;
  v177 = a4;
  v7 = a3;
  v171 = a3;
  v8 = a2;
  v9 = a1;
  v181 = a1;
  v10 = a5;
  v179 = a5;
  *(_QWORD *)v209 = a6;
  (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)a2 + 8LL))(a2);
  v184 = v8;
  v11 = 0;
  v205 = 0;
  v12 = (*(__int64 (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 32LL))(v8);
  if ( v12 )
    v205 = *(_QWORD *)(v12 + 88);
  v176 = 0;
  LODWORD(v13) = *((_DWORD *)v6 + 1);
  v172[0] = v13;
  v175 = 0;
  v170 = *((_DWORD *)v6 + 10);
  while ( 1 )
  {
    while ( 1 )
    {
LABEL_4:
      while ( !(*(unsigned int (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 24LL))(v8) )
      {
        *((_DWORD *)v6 + 1) = v13;
        *((_DWORD *)v6 + 10) = v170;
        LODWORD(lpString2) = (_DWORD)v10;
        v100 = (*(__int64 (__fastcall **)(struct IUiaNodeVisitor *, struct IUiaNode *, _QWORD, struct TraverseStateIn *))(*(_QWORD *)v9 + 16LL))(
                 v9,
                 v8,
                 v7,
                 v6);
        v101 = v100;
        if ( v100 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x30C,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
            (const char *)(unsigned int)v100,
            (int)v10);
          while ( v11 )
          {
            v140 = v11;
            v11 = (_QWORD *)*v11;
            v141 = v140[1];
            operator delete(v140);
            if ( !v141 )
              break;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
          }
          if ( v8 )
            (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
          return v101;
        }
        v102 = *((_QWORD *)v10 + 1);
        if ( v102 )
        {
          if ( *((_BYTE *)v10 + 24) )
          {
            v151 = (UiaNode *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v102 + 32LL))(v102);
            if ( v151 )
            {
              if ( UiaNode::IsRepositionedEndpointRootNode(v151) )
              {
                v152 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v10 + 1) + 32LL))(*((_QWORD *)v10 + 1));
                wil::com_ptr_t<UiaNode,wil::err_exception_policy>::com_ptr_t<UiaNode,wil::err_exception_policy>(
                  &v208,
                  v152);
                v154 = v208;
                if ( !v208 )
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    (void *)0x324,
                    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
                    v153);
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 + 1) + 16LL))(*((_QWORD *)v10 + 1));
                *((_QWORD *)v10 + 1) = 0;
                v185 = 0;
                DefaultParent = UiaNodeTraverser::GetDefaultParent(v154, &v185, 0);
                v156 = DefaultParent;
                if ( DefaultParent < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x32F,
                    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
                    (const char *)(unsigned int)DefaultParent,
                    (int)v10);
                  wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v185);
                  if ( v154 )
                    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IUiaNode>::Release(v154);
                  NodeStack::Reset((NodeStack *)&v175);
                  wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v184);
                  return v156;
                }
                if ( v185 )
                {
                  (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
                  v8 = v185;
                  v185 = 0;
                  v184 = v8;
                  v176 = 0;
                  *((_DWORD *)v6 + 2) = 1;
                  v170 = *((_DWORD *)v10 + 5) - 1;
                  NodeStack::Reset((NodeStack *)&v175);
                  v172[0] = 0;
                  wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v185);
                  if ( v154 )
                    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IUiaNode>::Release(v154);
                  v11 = v175;
                  LODWORD(v13) = v172[0];
                  v9 = v181;
                  continue;
                }
                v68 = -2147418113;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x330,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
                  (const char *)0x8000FFFFLL,
                  (int)v10);
                wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v185);
                if ( v154 )
                  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IUiaNode>::Release(v154);
                NodeStack::Reset((NodeStack *)&v175);
                goto LABEL_357;
              }
            }
          }
        }
        (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
        v8 = (struct IUiaNode *)*((_QWORD *)v10 + 1);
        v184 = v8;
        v176 = 0;
        *((_QWORD *)v10 + 1) = 0;
        *((_DWORD *)v6 + 2) = *(_DWORD *)v10;
        v170 = *((_DWORD *)v10 + 5);
        while ( v11 )
        {
          v103 = v11;
          v11 = (_QWORD *)*v11;
          v175 = v11;
          v104 = v103[1];
          operator delete(v103);
          if ( !v104 )
            break;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
        }
        if ( !v8 )
        {
          while ( v11 )
          {
            v142 = v11;
            v11 = (_QWORD *)*v11;
            v143 = v142[1];
            operator delete(v142);
            if ( !v143 )
              break;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v143 + 16LL))(v143);
          }
          return 0;
        }
        LODWORD(v13) = v172[0];
        if ( ((*((_DWORD *)v6 + 2) - 1) & 0xFFFFFFFD) == 0 )
        {
          v105 = (*(__int64 (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 32LL))(v8);
          v106 = (struct UiaNode *)v105;
          if ( !v105 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x354,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
              (const char *)0x8000FFFFLL,
              (int)v10);
            NodeStack::Reset((NodeStack *)&v175);
            (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
            return 2147549183LL;
          }
          v204 = 0;
          v107 = *((unsigned int *)v10 + 4);
          if ( (unsigned int)v107 >= 6 || (unsigned int)v107 >= *(_DWORD *)(v105 + 240) )
            v108 = 0;
          else
            v108 = *(struct IUiaNode **)(v105 + 24 * (v107 + 4));
          v186 = v108;
          v109 = *(_DWORD *)v6;
          v110 = 0;
          for ( i = 0; ; ++i )
          {
            v112 = *((_DWORD *)v106 + 60);
            if ( i >= v112 )
            {
              v6 = v177;
              *((_DWORD *)v177 + 2) = 1;
              LODWORD(v13) = v172[0];
              v10 = v179;
              v9 = v181;
              goto LABEL_4;
            }
            v113 = i;
            if ( v109 )
              v113 = v112 + ~i;
            if ( v110 )
            {
              v157 = UiaNodeTraverser::SimpleNavigateSlot(
                       v106,
                       v113,
                       v7,
                       (enum NavigateDirection)(4 - (v109 != 0)),
                       &v204);
              v158 = v157;
              if ( v157 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xB6,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
                  (const char *)(unsigned int)v157,
                  (int)lpString2);
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x357,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
                  (const char *)v158,
                  lpString2e);
                NodeStack::Reset((NodeStack *)&v175);
                (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
                return v158;
              }
              v7 = v171;
              if ( v204 )
              {
                (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
                v8 = v204;
                v184 = v204;
                v176 = 0;
                v6 = v177;
                *((_DWORD *)v177 + 2) = 0;
                v13 = (*(unsigned int (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 24LL))(v8) == 0;
                v172[0] = v13;
                v10 = v179;
                v9 = v181;
                goto LABEL_4;
              }
              v108 = v186;
            }
            else
            {
              if ( v113 >= 6 || v113 >= v112 )
                v114 = 0;
              else
                v114 = (struct IUiaNode *)*((_QWORD *)v106 + 3 * v113 + 12);
              if ( v114 == v108 )
                v110 = 1;
            }
          }
        }
      }
      v14 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 32LL))(v8);
      v15 = (WCHAR *)v14;
      lpString1 = v14;
      if ( !v14 )
      {
        v68 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x36D,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
          (const char *)0x8000FFFFLL,
          (int)lpString2);
        NodeStack::Reset((NodeStack *)&v175);
LABEL_357:
        wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v184);
        return v68;
      }
      Buf2 = (void *)(v14 + 24);
      v16 = 0;
      v17 = (*(__int64 (__fastcall **)(const WCHAR *))(*((_QWORD *)v14 + 6) + 32LL))(v14 + 24);
      v18 = v17;
      if ( v171 || !v17 )
      {
        v38 = v177;
        v33 = 0;
      }
      else
      {
        v198 = 0;
        v19 = v199;
        LOBYTE(v19) = v199 & 0xC0;
        v199 &= 0xC0u;
        Buf1 = GUID_NULL;
        v201 = 0;
        v203 = 0;
        v20 = *(struct IUnknown **)(v17 + 256);
        if ( v20 )
        {
          ATL::AtlComPtrAssign(&v198, v20);
          v19 = v199;
        }
        LOBYTE(v19) = v19 & 0xFC;
        v21 = v19 | (*(_DWORD *)(v18 + 248) != 0);
        v199 = v21;
        if ( *(_DWORD *)(v18 + 240) == 1 && !*(_BYTE *)(v18 + 104) )
        {
          v22 = *(_QWORD *)(v18 + 96);
          if ( v22 )
          {
            v169 = 0;
            v210 = L"IRawElementProviderSimple::get_ProviderOptions";
            v211 = 0;
            if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
              McTemplateU0zqq_EventWriteTransfer(
                v19,
                (unsigned int)UiaProviderCallout_Start,
                (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
                0,
                0);
            v24 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 24LL))(v22, &v169);
            if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
              McTemplateU0zqq_EventWriteTransfer(
                v23,
                (unsigned int)UiaProviderCallout_Stop,
                (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
                0,
                0);
            if ( v24 >= 0 )
            {
              if ( (v169 & 8) != 0 )
              {
                v199 |= 2u;
              }
              else if ( (v169 & 4) != 0 )
              {
                v199 |= 4u;
              }
            }
            v188 = 0;
            v221 = 0;
            bstrString = 0;
            if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v22)(
                   v22,
                   &GUID_62f62f5a_5ec0_48f5_a032_783445df9a89,
                   &v188) >= 0
              && v188
              && (*(int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v188 + 24LL))(v188, &v221) >= 0
              && (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v188 + 32LL))(v188, &bstrString) >= 0 )
            {
              Buf1 = v221;
              v201 = bstrString;
              v26 = 0;
              bstrString = 0;
            }
            else
            {
              psa = 0;
              (**(void (__fastcall ***)(__int64, GUID *, SAFEARRAY **))v22)(
                v22,
                &GUID_a3d361a2_2919_42a1_b3dd_6595b432f2dd,
                &psa);
              v25 = psa;
              if ( psa )
              {
                v159 = UiaNode::PopulateCrossMachinePlaceholderInfo(
                         (UiaNode *)psa,
                         (struct IUiaCrossMachineConnectionProvider *)psa,
                         (struct ElementExtraInfo *)&v198);
                if ( v159 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x1299,
                    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                    (const char *)(unsigned int)v159,
                    (int)lpString2);
                v25 = psa;
              }
              if ( v25 )
                (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&v25->cDims + 16LL))(v25);
              v26 = bstrString;
            }
            if ( v26 )
            {
              SysFreeString(v26);
              bstrString = 0;
            }
            v27 = v188;
            if ( v188 )
            {
              v188 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
            }
            v21 = v199;
          }
        }
        v28 = 0;
        v29 = *(_DWORD *)(v18 + 240);
        while ( v28 < v29 )
        {
          if ( v28 < 6 && *(_DWORD *)(v18 + 24LL * v28 + 108) == 5 )
            goto LABEL_37;
          ++v28;
        }
        v28 = -1;
        v15 = (WCHAR *)lpString1;
LABEL_37:
        v30 = 0;
        if ( v28 != -1 )
          v30 = 8;
        v31 = v21 & 0xF7 | v30;
        v32 = (*(_BYTE *)(v18 + 272) & 6) != 0 ? 16 : 0;
        v199 = v32 | v31 & 0xEF;
        if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
        {
          if ( v203 )
          {
            v16 = 1;
            v33 = 1;
          }
          else
          {
            v33 = 0;
            for ( j = 0; (unsigned int)j < v29; j = (unsigned int)(j + 1) )
            {
              if ( (unsigned int)j < 6 && !*(_DWORD *)(v18 + 24 * j + 108) )
                goto LABEL_61;
            }
            for ( k = 0; (unsigned int)k < v29; k = (unsigned int)(k + 1) )
            {
              if ( (unsigned int)k < 6 && *(_DWORD *)(v18 + 24 * k + 108) == 1 )
                goto LABEL_61;
            }
            v36 = 0;
            v37 = *(_QWORD *)(v18 + 256);
            if ( v37 )
            {
              v36 = *(_QWORD *)(v18 + 256);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
            }
            v16 = v36 != 0;
            if ( v36 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          }
        }
        else
        {
          v16 = 1;
          v33 = 1;
        }
LABEL_61:
        if ( v203 )
          wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(v202);
        if ( v201 )
        {
          SysFreeString(v201);
          v201 = 0;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v198);
        v38 = v177;
        if ( v16 && !v172[0] && !*((_BYTE *)v177 + 44) )
        {
          v144 = v179;
          *(_DWORD *)v179 = *((_DWORD *)v177 + 2);
          *((_DWORD *)v144 + 5) = v170;
          *((_QWORD *)v144 + 1) = v8;
          v184 = 0;
          NodeStack::Reset((NodeStack *)&v175);
          return 0;
        }
      }
      if ( *((_DWORD *)v38 + 2) )
        break;
      if ( *((_BYTE *)v38 + 44) && v33 )
      {
        LODWORD(v48) = 0;
LABEL_256:
        v6 = v177;
LABEL_90:
        *((_DWORD *)v6 + 2) = 1;
        LODWORD(v13) = (_DWORD)v48;
        v172[0] = (int)v48;
        v7 = v171;
        v10 = v179;
        v9 = v181;
        continue;
      }
      v6 = v177;
      if ( !*((_BYTE *)v177 + 44) && v16 )
      {
        v48 = 0;
      }
      else
      {
        v48 = 0;
        v169 = 0;
        v218 = v15;
        v49 = *((_QWORD *)v15 + 11);
        v217 = v49;
        *((_QWORD *)v15 + 11) = v205;
        LODWORD(lpString2) = v209[0];
        v50 = (**(__int64 (__fastcall ***)(struct IUiaNodeVisitor *, WCHAR *, int *, unsigned int *))v181)(
                v181,
                v15,
                &v169,
                &v176);
        v51 = v50;
        if ( v50 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x394,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
            (const char *)(unsigned int)v50,
            (int)lpString2);
          *((_QWORD *)v15 + 11) = v49;
          NodeStack::Reset((NodeStack *)&v175);
          if ( v8 )
            (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
          return v51;
        }
        v52 = 1;
        if ( v169 == 1 )
        {
          v52 = 0;
        }
        else if ( v169 == 2 )
        {
          v145 = v179;
          *((_QWORD *)v179 + 1) = 0;
          *(_DWORD *)v145 = 1;
          *((_DWORD *)v145 + 5) = v170;
          *((_QWORD *)v15 + 11) = v49;
          while ( v11 )
          {
            v146 = v11;
            v11 = (_QWORD *)*v11;
            v147 = v146[1];
            operator delete(v146);
            if ( !v147 )
              break;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v147 + 16LL))(v147);
          }
          goto LABEL_261;
        }
        *((_QWORD *)v15 + 11) = v49;
        if ( !v52 )
          goto LABEL_90;
      }
      if ( v170 == 500 )
      {
        Error::OtherError(700);
        goto LABEL_90;
      }
      v53 = *(_DWORD *)v6;
      LODWORD(psa) = v53;
      v54 = 4 - (v53 != 0);
      v174 = v54;
      v55 = 0;
LABEL_94:
      v182 = v48;
      v56 = *((_DWORD *)lpString1 + 60);
      if ( v55 >= v56 )
        goto LABEL_256;
      v57 = v53 == 0;
      v58 = v55;
      if ( !v57 && (v58 = v56 + ~v55, v58 >= v56)
        || v58 >= 6
        || LOBYTE(lpString1[12 * v58 + 52])
        || (_mm_lfence(), (v59 = *(struct IRawElementProviderSimple **)&lpString1[12 * v58 + 48]) == 0) )
      {
        SlotAsNode = UiaNode::GetSlotAsNode((UiaNode *)lpString1, v58);
        (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)SlotAsNode + 8LL))(SlotAsNode);
        goto LABEL_121;
      }
      v60 = v54;
      v169 = v54;
      v207 = v59;
      ((void (__fastcall *)(struct IRawElementProviderSimple *))v59->lpVtbl->AddRef)(v59);
      v48 = (struct IUiaNode *)v59;
      while ( 1 )
      {
        v186 = 0;
        *(_QWORD *)v172 = 0;
        v61 = (**(__int64 (__fastcall ***)(struct IUiaNode *, GUID *, int *))v48)(
                v48,
                &GUID_f7063da8_8359_439c_9297_bbc5299a7d87,
                v172);
        v48 = 0;
        v62 = *(struct IUiaNode **)v172;
        if ( v61 )
          v62 = 0;
        v216 = v62;
        if ( !v62 )
        {
LABEL_265:
          if ( v59 )
            ((void (__fastcall *)(struct IRawElementProviderSimple *))v59->lpVtbl->Release)(v59);
          ++v55;
          v54 = v174;
          v53 = (int)psa;
          goto LABEL_94;
        }
        v63 = *((_QWORD *)lpString1 + 33);
        v189 = 0;
        if ( v63 )
        {
          lpString2 = (SAFEARRAY **)&v189;
          v65 = InProcClientAPIStub::InvokeInProcAPI(v63, 128, v62, v60);
        }
        else
        {
          v212 = L"IRawElementProviderFragment::Navigate";
          v213 = 0;
          if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
            McTemplateU0zqq_EventWriteTransfer(
              0,
              (unsigned int)UiaProviderCallout_Start,
              (unsigned int)L"IRawElementProviderFragment::Navigate",
              0,
              0);
          v65 = (*(__int64 (__fastcall **)(struct IUiaNode *, _QWORD, __int64 *))(*(_QWORD *)v62 + 24LL))(
                  v62,
                  v60,
                  &v189);
          if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
            McTemplateU0zqq_EventWriteTransfer(
              v64,
              (unsigned int)UiaProviderCallout_Stop,
              (unsigned int)L"IRawElementProviderFragment::Navigate",
              0,
              0);
        }
        if ( v65 < 0 )
        {
          v189 = 0;
LABEL_274:
          v66 = 0;
          v186 = 0;
          goto LABEL_114;
        }
        if ( !v189 )
          goto LABEL_274;
        *(_QWORD *)v172 = 0;
        if ( !(**(unsigned int (__fastcall ***)(__int64, GUID *, int *))v189)(
                v189,
                &GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c,
                v172) )
          v48 = *(struct IUiaNode **)v172;
        v66 = (struct IRawElementProviderSimple *)v48;
        v186 = v48;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v189 + 16LL))(v189);
LABEL_114:
        (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v62 + 16LL))(v62);
        if ( !v48 )
          goto LABEL_265;
        v172[0] = -1;
        v67 = UiaNodeFactory::FromLocalProvider(v66, v171, *((struct UiaClientState **)lpString1 + 10), &v182, v172);
        v68 = v67;
        if ( v67 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x59,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
            (const char *)(unsigned int)v67,
            (int)lpString2);
          ((void (__fastcall *)(struct IRawElementProviderSimple *))v66->lpVtbl->Release)(v66);
          if ( v59 )
            ((void (__fastcall *)(struct IRawElementProviderSimple *))v59->lpVtbl->Release)(v59);
LABEL_278:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x95,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
            (const char *)v68,
            lpString2a);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3AF,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
            (const char *)v68,
            lpString2c);
          NodeStack::Reset((NodeStack *)&v175);
          if ( v8 )
            (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
          return v68;
        }
        SlotAsNode = v182;
        v70 = (*(__int64 (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v182 + 32LL))(v182);
        if ( !v70 )
        {
          v68 = -2147418113;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5D,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
            (const char *)0x8000FFFFLL,
            (int)lpString2);
          wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v186);
          wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v207);
          goto LABEL_278;
        }
        if ( v172[0] == *(_DWORD *)(v70 + 244) )
          break;
        ((void (__fastcall *)(struct IRawElementProviderSimple *))v59->lpVtbl->Release)(v59);
        v59 = v66;
        v207 = v66;
        (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v48 + 8LL))(v48);
        (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)SlotAsNode + 16LL))(SlotAsNode);
        v182 = 0;
        v149 = 1;
        if ( ((v169 - 1) & 0xFFFFFFFD) != 0 )
          v149 = 2;
        v169 = v149;
        ((void (__fastcall *)(struct IRawElementProviderSimple *))v66->lpVtbl->Release)(v66);
        v60 = v169;
      }
      ((void (__fastcall *)(struct IRawElementProviderSimple *))v66->lpVtbl->Release)(v66);
      if ( v59 )
        ((void (__fastcall *)(struct IRawElementProviderSimple *))v59->lpVtbl->Release)(v59);
      LODWORD(v48) = 0;
LABEL_121:
      if ( TESTPARAMS_ENABLE_TRAVERSAL_STACK )
      {
        v71 = v176;
        v72 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        v73 = v72;
        if ( !v72 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2AB,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
            (const char *)0x8007000ELL,
            (int)lpString2);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3B3,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
            (const char *)0x8007000ELL,
            lpString2d);
          NodeStack::Reset((NodeStack *)&v175);
          if ( v8 )
            (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
          return 2147942414LL;
        }
        v72[5] = (_DWORD)v48;
        *(_QWORD *)v72 = v11;
        v74 = Buf2;
        *((_QWORD *)v72 + 1) = Buf2;
        v72[4] = v71;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v74 + 8LL))(v74);
        v11 = v73;
        v175 = v73;
      }
      ++v170;
      (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
      v8 = SlotAsNode;
      v184 = SlotAsNode;
      v176 = (unsigned int)v48;
      LODWORD(v13) = (_DWORD)v48;
      LOBYTE(v13) = (*(unsigned int (__fastcall **)(struct IUiaNode *))(*(_QWORD *)SlotAsNode + 24LL))(SlotAsNode) == 0;
      v172[0] = v13;
      v6 = v177;
      v7 = v171;
      v10 = v179;
      v9 = v181;
    }
    if ( *((_BYTE *)v38 + 44) && v33 )
    {
      v169 = 0;
      v6 = v177;
    }
    else
    {
      v169 = 1;
      v6 = v177;
      if ( *((_BYTE *)v177 + 44) || !v16 )
      {
        v174 = 0;
        v220 = v15;
        v13 = *((_QWORD *)v15 + 11);
        v219 = v13;
        *((_QWORD *)v15 + 11) = v205;
        v39 = (*(__int64 (__fastcall **)(struct IUiaNodeVisitor *, WCHAR *, int *, _QWORD))(*(_QWORD *)v181 + 8LL))(
                v181,
                v15,
                &v174,
                v176);
        v40 = v39;
        if ( v39 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3D7,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
            (const char *)(unsigned int)v39,
            (int)lpString2);
          *((_QWORD *)v15 + 11) = v13;
          NodeStack::Reset((NodeStack *)&v175);
          if ( v8 )
            (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
          return v40;
        }
        switch ( v174 )
        {
          case 1:
            v169 = 0;
            break;
          case 2:
            v128 = v179;
            *((_QWORD *)v179 + 1) = 0;
            *(_DWORD *)v128 = 1;
            *((_DWORD *)v128 + 5) = v170;
            *((_QWORD *)v15 + 11) = v13;
            while ( v11 )
            {
              v135 = v11;
              v11 = (_QWORD *)*v11;
              v136 = v135[1];
              operator delete(v135);
              if ( !v136 )
                break;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v136 + 16LL))(v136);
            }
            goto LABEL_261;
          case 3:
            *((_DWORD *)v6 + 2) = 0;
            *((_QWORD *)v15 + 11) = v13;
            LODWORD(v13) = v172[0];
            v7 = v171;
            v10 = v179;
            v9 = v181;
            goto LABEL_4;
        }
        *((_QWORD *)v15 + 11) = v13;
      }
    }
    Buf2 = (void *)*((_QWORD *)v6 + 2);
    v41 = 0;
    if ( Buf2 )
      break;
LABEL_282:
    v132 = (const WCHAR *)*((_QWORD *)v6 + 4);
    if ( v132 )
    {
      lpString1 = 0;
      v133 = *((_QWORD *)v15 + 33);
      if ( v133 )
        TempIdString = InProcClientAPIStub::InvokeInProcAPI(v133, 23, v15, &lpString1);
      else
        TempIdString = UiaNode::Provider_GetTempIdString((UiaNode *)v15, (unsigned __int16 **)&lpString1);
      v47 = TempIdString;
      if ( TempIdString >= 0 && lpString1 )
      {
        v162 = CompareStringW(0x7Fu, 0, lpString1, -1, v132, -1);
        AutoCleanupInfo<unsigned short *>::SafeRelease(&lpString1);
        v41 = v162 == 2;
      }
      else
      {
        AutoCleanupInfo<unsigned short *>::SafeRelease(&lpString1);
      }
      goto LABEL_127;
    }
LABEL_130:
    v75 = *((_DWORD *)v6 + 2);
    if ( v75 == 1 )
    {
      if ( v169 )
      {
        v182 = 0;
        v174 = 0;
        v7 = v171;
        NextSibling = UiaNodeTraverser::GetNextSibling(*(_DWORD *)v6, v171, (struct UiaNode *)v15, &v182, &v174);
        v77 = NextSibling;
        if ( NextSibling < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x411,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
            (const char *)(unsigned int)NextSibling,
            (int)lpString2);
          NodeStack::Reset((NodeStack *)&v175);
          if ( v8 )
            (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
          return v77;
        }
        if ( v182 )
        {
          (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
          v8 = v182;
          v184 = v182;
          v176 = 0;
          if ( (*(unsigned int (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v182 + 24LL))(v182) )
          {
            LODWORD(v13) = 0;
            v172[0] = 0;
          }
          else
          {
            LODWORD(v13) = 1;
            v172[0] = 1;
            v10 = v179;
            v9 = v181;
            if ( v174 )
              goto LABEL_4;
          }
          *((_DWORD *)v6 + 2) = 0;
          v10 = v179;
          v9 = v181;
          goto LABEL_4;
        }
      }
      *((_DWORD *)v6 + 2) = 2;
    }
    else if ( v75 != 2 )
    {
      goto LABEL_291;
    }
    v173 = 0;
    if ( v11 )
    {
      v78 = v11;
      v11 = (_QWORD *)*v11;
      v175 = v11;
      v79 = (struct IUiaNode *)v78[1];
      v80 = *((_DWORD *)v78 + 4);
      operator delete(v78);
      v197 = v79;
      if ( v79 )
        goto LABEL_137;
    }
    else
    {
      v80 = 0;
      v197 = 0;
    }
    Parent = UiaNodeTraverser::GetParent(v171, (struct UiaNode *)v15, &v197, &v173);
    v131 = Parent;
    if ( Parent < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x434,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianodetraverser.cpp",
        (const char *)(unsigned int)Parent,
        (int)lpString2);
      NodeStack::Reset((NodeStack *)&v175);
      if ( v8 )
        (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
      return v131;
    }
    if ( !v197 )
    {
LABEL_291:
      v137 = v179;
      *(_DWORD *)v179 = 1;
      *((_QWORD *)v137 + 1) = 0;
      *((_DWORD *)v137 + 5) = v170;
      while ( v11 )
      {
        v138 = v11;
        v11 = (_QWORD *)*v11;
        v139 = v138[1];
        operator delete(v138);
        if ( !v139 )
          break;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v139 + 16LL))(v139);
      }
      goto LABEL_261;
    }
LABEL_137:
    (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
    v8 = v197;
    v184 = v197;
    v176 = v80;
    v81 = (*(__int64 (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v197 + 24LL))(v197);
    LODWORD(v13) = v81 == 0;
    v172[0] = v13;
    v82 = 0;
    v83 = (*(__int64 (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 32LL))(v8);
    v84 = v83;
    if ( !v171 && v83 )
    {
      v198 = 0;
      v85 = v199;
      LOBYTE(v85) = v199 & 0xC0;
      v199 &= 0xC0u;
      Buf1 = GUID_NULL;
      v201 = 0;
      v203 = 0;
      v86 = *(struct IUnknown **)(v83 + 256);
      if ( v86 )
      {
        ATL::AtlComPtrAssign(&v198, v86);
        v85 = v199;
      }
      LOBYTE(v85) = v85 & 0xFC;
      v87 = v85 | (*(_DWORD *)(v84 + 248) != 0);
      v199 = v87;
      if ( *(_DWORD *)(v84 + 240) == 1 && !*(_BYTE *)(v84 + 104) )
      {
        v88 = *(_QWORD *)(v84 + 96);
        if ( v88 )
        {
          v174 = 0;
          v214 = L"IRawElementProviderSimple::get_ProviderOptions";
          v215 = 0;
          if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
            McTemplateU0zqq_EventWriteTransfer(
              v85,
              (unsigned int)UiaProviderCallout_Start,
              (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
              0,
              0);
          v90 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v88 + 24LL))(v88, &v174);
          if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
            McTemplateU0zqq_EventWriteTransfer(
              v89,
              (unsigned int)UiaProviderCallout_Stop,
              (unsigned int)L"IRawElementProviderSimple::get_ProviderOptions",
              0,
              0);
          if ( v90 >= 0 )
          {
            if ( (v174 & 8) != 0 )
            {
              v199 |= 2u;
            }
            else if ( (v174 & 4) != 0 )
            {
              v199 |= 4u;
            }
          }
          v191 = 0;
          v222 = 0;
          v190 = 0;
          if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v88)(
                 v88,
                 &GUID_62f62f5a_5ec0_48f5_a032_783445df9a89,
                 &v191) >= 0
            && v191
            && (*(int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v191 + 24LL))(v191, &v222) >= 0
            && (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v191 + 32LL))(v191, &v190) >= 0 )
          {
            Buf1 = v222;
            v201 = v190;
            v92 = 0;
            v190 = 0;
          }
          else
          {
            v182 = 0;
            (**(void (__fastcall ***)(__int64, GUID *, struct IUiaNode **))v88)(
              v88,
              &GUID_a3d361a2_2919_42a1_b3dd_6595b432f2dd,
              &v182);
            v91 = v182;
            if ( v182 )
            {
              v160 = UiaNode::PopulateCrossMachinePlaceholderInfo(v182, v182, (struct ElementExtraInfo *)&v198);
              if ( v160 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x1299,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
                  (const char *)(unsigned int)v160,
                  (int)lpString2);
              v91 = v182;
            }
            if ( v91 )
              (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v91 + 16LL))(v91);
            v92 = v190;
          }
          if ( v92 )
          {
            SysFreeString(v92);
            v190 = 0;
          }
          v93 = v191;
          if ( v191 )
          {
            v191 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
          }
          v87 = v199;
          v6 = v177;
        }
      }
      v94 = 0;
      v95 = *(_DWORD *)(v84 + 240);
      while ( v94 < v95 )
      {
        if ( v94 < 6 && *(_DWORD *)(v84 + 24LL * v94 + 108) == 5 )
          goto LABEL_168;
        ++v94;
      }
      v94 = -1;
LABEL_168:
      v96 = 0;
      if ( v94 != -1 )
        v96 = 8;
      v97 = v87 & 0xF7 | v96;
      if ( (*(_BYTE *)(v84 + 272) & 6) != 0 )
        v98 = 16;
      else
        v98 = 0;
      v199 = v98 | v97 & 0xEF;
      if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
      {
        if ( v203 )
        {
          v82 = 1;
        }
        else
        {
          for ( m = 0; (unsigned int)m < v95; m = (unsigned int)(m + 1) )
          {
            if ( (unsigned int)m < 6 && !*(_DWORD *)(v84 + 24 * m + 108) )
              goto LABEL_174;
          }
          for ( n = 0; (unsigned int)n < v95; n = (unsigned int)(n + 1) )
          {
            if ( (unsigned int)n < 6 && *(_DWORD *)(v84 + 24 * n + 108) == 1 )
              goto LABEL_174;
          }
          v117 = 0;
          v118 = *(_QWORD *)(v84 + 256);
          if ( v118 )
          {
            v117 = *(_QWORD *)(v84 + 256);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 8LL))(v118);
          }
          v82 = v117 != 0;
          if ( v117 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
        }
      }
      else
      {
        v82 = 1;
      }
LABEL_174:
      if ( v203 )
        wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(v202);
      if ( v201 )
      {
        SysFreeString(v201);
        v201 = 0;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v198);
      LODWORD(v13) = v172[0];
    }
    v99 = --v170;
    if ( v82 && !*((_BYTE *)v6 + 44) )
    {
      v148 = v179;
      *((_QWORD *)v179 + 1) = v8;
      v184 = 0;
      *(_DWORD *)v148 = v169 + 2;
      *((_DWORD *)v148 + 5) = v99;
      NodeStack::Reset((NodeStack *)&v175);
      return 0;
    }
    if ( v81 || v173 )
    {
      *((_DWORD *)v6 + 2) = 1;
      v172[0] = v13;
      v7 = v171;
      v10 = v179;
      v9 = v181;
    }
    else
    {
      v7 = v171;
      v10 = v179;
      v9 = v181;
    }
  }
  v42 = *((int *)v6 + 6);
  if ( !(_DWORD)v42 )
  {
    v15 = (WCHAR *)lpString1;
    goto LABEL_282;
  }
  v43 = (WCHAR *)lpString1;
  v44 = *((_QWORD *)lpString1 + 33);
  for ( ii = 0; ; ++ii )
  {
    psa = 0;
    if ( ii >= *((_DWORD *)v43 + 60) )
    {
      v47 = 0;
      goto LABEL_126;
    }
    if ( v44 )
    {
      lpString2 = &psa;
      v46 = InProcClientAPIStub::InvokeInProcAPI(v44, 11, v43, ii);
      v47 = v46;
      if ( v46 >= 0 )
        goto LABEL_81;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB78,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
        (const char *)(unsigned int)v46,
        (int)&psa);
LABEL_126:
      v15 = (WCHAR *)lpString1;
      v6 = v177;
      goto LABEL_127;
    }
    RuntimeId = UiaNode::ProviderGetRuntimeId((UiaNode *)v43, ii, &psa);
    v47 = RuntimeId;
    if ( RuntimeId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB7C,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
        (const char *)(unsigned int)RuntimeId,
        (int)lpString2);
      goto LABEL_126;
    }
LABEL_81:
    if ( psa )
      break;
    v43 = (WCHAR *)lpString1;
  }
  v195 = 0;
  ppvData = 0;
  v194 = psa;
  if ( SafeArrayGetDim(psa) != 1 )
  {
    v47 = -2147024809;
    v126 = 92;
    v127 = 2147942487LL;
    goto LABEL_243;
  }
  pvt = 0;
  Vartype = SafeArrayGetVartype(v194, &pvt);
  v47 = Vartype;
  if ( Vartype < 0 )
  {
    v126 = 95;
    v127 = (unsigned int)Vartype;
    goto LABEL_243;
  }
  if ( pvt != 3 && pvt != 22 )
  {
    v47 = -2147024809;
    v126 = 106;
    v127 = 2147942487LL;
LABEL_243:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v126,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v127,
      (int)lpString2);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)(unsigned int)v47,
      lpString2b);
    if ( v194 )
      SafeArrayUnaccessData(v194);
    SafeArrayDestroy(psa);
    if ( v47 >= 0 )
    {
      v123 = 0;
      goto LABEL_247;
    }
    goto LABEL_253;
  }
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(v194, 1u, &plLbound);
  v47 = LBound;
  if ( LBound < 0 )
  {
    v126 = 111;
LABEL_311:
    v127 = (unsigned int)LBound;
    goto LABEL_243;
  }
  UBound = SafeArrayGetUBound(v194, 1u, &plUbound);
  v47 = UBound;
  if ( UBound < 0 )
  {
    v126 = 112;
    v127 = (unsigned int)UBound;
    goto LABEL_243;
  }
  v195 = plUbound - plLbound + 1;
  LBound = SafeArrayAccessData(v194, &ppvData);
  v47 = LBound;
  if ( LBound < 0 )
  {
    v126 = 115;
    goto LABEL_311;
  }
  v122 = 4LL * v195;
  if ( !is_mul_ok(v195, 4u) )
    v122 = -1;
  v123 = operator new[](v122, (const struct std::nothrow_t *)std::nothrow);
  if ( !v123 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)0x8007000ELL,
      (int)lpString2);
    if ( v194 )
      SafeArrayUnaccessData(v194);
    v47 = -2147024882;
    SafeArrayDestroy(psa);
    goto LABEL_253;
  }
  v124 = 0;
  for ( jj = v195; (unsigned int)v124 < v195; jj = v195 )
  {
    v123[v124] = *((_DWORD *)ppvData + v124);
    v124 = (unsigned int)(v124 + 1);
  }
  if ( v194 )
    SafeArrayUnaccessData(v194);
  v47 = 0;
  SafeArrayDestroy(psa);
  if ( jj != (_DWORD)v42 || (v41 = 1, memcmp_0(v123, Buf2, 4 * v42)) )
LABEL_247:
    v41 = 0;
  if ( v123 )
  {
    operator delete(v123);
    v15 = (WCHAR *)lpString1;
    v6 = v177;
  }
  else
  {
LABEL_253:
    v15 = (WCHAR *)lpString1;
    v6 = v177;
  }
LABEL_127:
  if ( v47 == -2146233083 || v47 == -2147023436 )
  {
    NodeStack::Reset((NodeStack *)&v175);
    if ( v8 )
      (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
    return (unsigned int)v47;
  }
  else
  {
    if ( !v41 )
      goto LABEL_130;
    v150 = v179;
    *(_DWORD *)v179 = 1;
    *((_QWORD *)v150 + 1) = 0;
    *((_DWORD *)v150 + 5) = v170;
    NodeStack::Reset((NodeStack *)&v175);
LABEL_261:
    if ( v8 )
      (*(void (__fastcall **)(struct IUiaNode *))(*(_QWORD *)v8 + 16LL))(v8);
    return 0;
  }
}

```

## disassembly

```asm
0x18004aa10  push    rbp
0x18004aa12  push    rbx
0x18004aa13  push    rsi
0x18004aa14  push    rdi
0x18004aa15  push    r12
0x18004aa17  push    r13
0x18004aa19  push    r14
0x18004aa1b  push    r15
0x18004aa1d  lea     rbp, [rsp-118h]
0x18004aa25  sub     rsp, 218h
0x18004aa2c  mov     rax, cs:__security_cookie
0x18004aa33  xor     rax, rsp
0x18004aa36  mov     [rbp+150h+var_48], rax
0x18004aa3d  mov     r15, r9
0x18004aa40  mov     [rsp+250h+var_1F0], r9
0x18004aa45  mov     r12d, r8d
0x18004aa48  mov     [rsp+250h+var_218], r8d
0x18004aa4d  mov     rsi, rdx
0x18004aa50  mov     rdi, rcx
0x18004aa53  mov     [rbp+150h+var_1D0], rcx
0x18004aa57  mov     r13, [rbp+150h+arg_20]
0x18004aa5e  mov     [rsp+250h+var_1E0], r13
0x18004aa63  mov     rax, [rbp+150h+arg_28]
0x18004aa6a  mov     qword ptr [rbp+150h+var_C8], rax
0x18004aa71  mov     rax, [rdx]
0x18004aa74  mov     rcx, rdx
0x18004aa77  mov     rax, [rax+8]
0x18004aa7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa80  mov     [rbp+150h+var_1B8], rsi
0x18004aa84  xor     r14d, r14d
0x18004aa87  mov     [rbp+150h+var_E8], r14
0x18004aa8b  mov     rax, [rsi]
0x18004aa8e  mov     rcx, rsi
0x18004aa91  mov     rax, [rax+20h]
0x18004aa95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa9a  test    rax, rax
0x18004aa9d  jz      short loc_18004AAA7
0x18004aa9f  mov     rax, [rax+58h]
0x18004aaa3  mov     [rbp+150h+var_E8], rax
0x18004aaa7  mov     [rsp+250h+var_1F8], r14d
0x18004aaac  mov     ebx, [r15+4]
0x18004aab0  mov     [rsp+250h+var_210], ebx
0x18004aab4  mov     [rsp+250h+var_200], r14
0x18004aab9  mov     eax, [r15+28h]
0x18004aabd  mov     [rsp+250h+var_21C], eax
0x18004aac1  mov     rax, [rsi]
0x18004aac4  mov     rcx, rsi
0x18004aac7  mov     rax, [rax+18h]
0x18004aacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aad0  test    eax, eax
0x18004aad2  jz      loc_18004B68E
0x18004aad8  mov     rax, [rsi]
0x18004aadb  mov     rcx, rsi
0x18004aade  mov     rax, [rax+20h]
0x18004aae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aae7  mov     r13, rax
0x18004aaea  mov     [rsp+250h+lpString1], rax
0x18004aaef  test    rax, rax
0x18004aaf2  jz      loc_18004C887
0x18004aaf8  lea     rcx, [rax+30h]
0x18004aafc  mov     [rbp+150h+Buf2], rcx
0x18004ab00  xor     r12b, r12b
0x18004ab03  mov     rax, [rcx]
0x18004ab06  mov     rax, [rax+20h]
0x18004ab0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab0f  mov     rdi, rax
0x18004ab12  cmp     [rsp+250h+var_218], 0
0x18004ab17  jnz     loc_18004BD6B
0x18004ab1d  test    rax, rax
0x18004ab20  jz      loc_18004BD6B
0x18004ab26  xor     r15d, r15d
0x18004ab29  mov     [rbp+150h+var_150], r15
0x18004ab2d  movzx   ecx, [rbp+150h+var_148]
0x18004ab31  and     cl, 0C0h
0x18004ab34  mov     [rbp+150h+var_148], cl
0x18004ab37  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004ab3e  movups  xmmword ptr [rbp+150h+Buf1.Data1], xmm0
0x18004ab42  mov     [rbp+150h+var_130], r15
0x18004ab46  mov     [rbp+150h+var_100], r12b
0x18004ab4a  mov     rdx, [rax+100h]; struct IUnknown *
0x18004ab51  test    rdx, rdx
0x18004ab54  jz      short loc_18004AB63
0x18004ab56  lea     rcx, [rbp+150h+var_150]; struct IUnknown **
0x18004ab5a  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18004ab5f  movzx   ecx, [rbp+150h+var_148]
0x18004ab63  cmp     dword ptr [rdi+0F8h], 0
0x18004ab6a  setnz   r8b
0x18004ab6e  and     cl, 0FCh
0x18004ab71  or      r8b, cl
0x18004ab74  mov     [rbp+150h+var_148], r8b
0x18004ab78  cmp     dword ptr [rdi+0F0h], 1
0x18004ab7f  jnz     loc_18004ACA8
0x18004ab85  cmp     byte ptr [rdi+68h], 0
0x18004ab89  jnz     loc_18004ACA8
0x18004ab8f  mov     rbx, [rdi+60h]
0x18004ab93  test    rbx, rbx
0x18004ab96  jz      loc_18004ACA8
0x18004ab9c  mov     [rsp+250h+var_220], r15d
0x18004aba1  lea     rax, aIrawelementpro_9; "IRawElementProviderSimple::get_Provider"...
0x18004aba8  mov     [rbp+150h+var_C0], rax
0x18004abaf  mov     [rbp+150h+var_B8], r15
0x18004abb6  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x18004abbd  jnz     loc_18004C327
0x18004abc3  mov     rax, [rbx]
0x18004abc6  lea     rdx, [rsp+250h+var_220]
0x18004abcb  mov     rcx, rbx
0x18004abce  mov     rax, [rax+18h]
0x18004abd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abd7  mov     r15d, eax
0x18004abda  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x18004abe1  jnz     loc_18004C343
0x18004abe7  test    r15d, r15d
0x18004abea  js      short loc_18004AC00
0x18004abec  mov     eax, [rsp+250h+var_220]
0x18004abf0  test    al, 8
0x18004abf2  jnz     loc_18004BCE7
0x18004abf8  test    al, 4
0x18004abfa  jz      short loc_18004AC00
0x18004abfc  or      [rbp+150h+var_148], 4
0x18004ac00  xor     r15d, r15d
0x18004ac03  mov     [rbp+150h+var_198], r15
0x18004ac07  xorps   xmm0, xmm0
0x18004ac0a  movups  [rbp+150h+var_68], xmm0
0x18004ac11  mov     [rbp+150h+bstrString], r15
0x18004ac15  mov     rax, [rbx]
0x18004ac18  lea     r8, [rbp+150h+var_198]
0x18004ac1c  lea     rdx, _GUID_62f62f5a_5ec0_48f5_a032_783445df9a89
0x18004ac23  mov     rcx, rbx
0x18004ac26  mov     rax, [rax]
0x18004ac29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac2e  test    eax, eax
0x18004ac30  jns     loc_18004C53E
0x18004ac36  mov     [rsp+250h+psa], r15
0x18004ac3b  mov     rax, [rbx]
0x18004ac3e  lea     r8, [rsp+250h+psa]
0x18004ac43  lea     rdx, _GUID_a3d361a2_2919_42a1_b3dd_6595b432f2dd
0x18004ac4a  mov     rcx, rbx
0x18004ac4d  mov     rax, [rax]
0x18004ac50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac55  nop
0x18004ac56  mov     rcx, [rsp+250h+psa]; this
0x18004ac5b  test    rcx, rcx
0x18004ac5e  jnz     loc_18004C5A1
0x18004ac64  test    rcx, rcx
0x18004ac67  jz      short loc_18004AC76
0x18004ac69  mov     rax, [rcx]
0x18004ac6c  mov     rax, [rax+10h]
0x18004ac70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac75  nop
0x18004ac76  mov     rcx, [rbp+150h+bstrString]; bstrString
0x18004ac7a  test    rcx, rcx
0x18004ac7d  jz      short loc_18004AC89
0x18004ac7f  call    cs:__imp_SysFreeString
0x18004ac85  mov     [rbp+150h+bstrString], r15
0x18004ac89  mov     rcx, [rbp+150h+var_198]
0x18004ac8d  test    rcx, rcx
0x18004ac90  jz      short loc_18004ACA3
0x18004ac92  mov     [rbp+150h+var_198], r15
0x18004ac96  mov     rax, [rcx]
0x18004ac99  mov     rax, [rax+10h]
0x18004ac9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aca2  nop
0x18004aca3  movzx   r8d, [rbp+150h+var_148]
0x18004aca8  mov     eax, r15d
0x18004acab  mov     ebx, [rdi+0F0h]
0x18004acb1  cmp     eax, ebx
0x18004acb3  jnb     short loc_18004ACCB
0x18004acb5  cmp     eax, 6
0x18004acb8  jnb     short loc_18004ACC7
0x18004acba  mov     ecx, eax
0x18004acbc  lea     rdx, [rcx+rcx*2]
0x18004acc0  cmp     dword ptr [rdi+rdx*8+6Ch], 5
0x18004acc5  jz      short loc_18004ACD5
0x18004acc7  inc     eax
0x18004acc9  jmp     short loc_18004ACB1
0x18004accb  mov     eax, 0FFFFFFFFh
0x18004acd0  mov     r13, [rsp+250h+lpString1]
0x18004acd5  mov     ecx, r15d
0x18004acd8  cmp     eax, 0FFFFFFFFh
0x18004acdb  mov     eax, 8
0x18004ace0  cmovnz  ecx, eax
0x18004ace3  and     r8b, 0F7h
0x18004ace7  or      cl, r8b
0x18004acea  test    byte ptr [rdi+110h], 6
0x18004acf1  jz      loc_18004C2D9
0x18004acf7  mov     al, 10h
0x18004acf9  and     cl, 0EFh
0x18004acfc  or      cl, al
0x18004acfe  mov     [rbp+150h+var_148], cl
0x18004ad01  mov     r8d, 10h; Size
0x18004ad07  lea     rdx, GUID_NULL; Buf2
0x18004ad0e  lea     rcx, [rbp+150h+Buf1]; Buf1
0x18004ad12  call    memcmp_0
0x18004ad17  test    eax, eax
0x18004ad19  jnz     loc_18004ADA9
0x18004ad1f  cmp     [rbp+150h+var_100], al
0x18004ad22  jnz     loc_18004C712
0x18004ad28  xor     r15b, r15b
0x18004ad2b  xor     edx, edx
0x18004ad2d  nop     dword ptr [rax]
0x18004ad30  cmp     edx, ebx
0x18004ad32  jnb     short loc_18004AD4D
0x18004ad34  cmp     edx, 6
0x18004ad37  jnb     short loc_18004AD44
0x18004ad39  lea     rcx, [rdx+rdx*2]
0x18004ad3d  cmp     dword ptr [rdi+rcx*8+6Ch], 0
0x18004ad42  jz      short loc_18004AD48
0x18004ad44  inc     edx
0x18004ad46  jmp     short loc_18004AD30
0x18004ad48  cmp     edx, 0FFFFFFFFh
0x18004ad4b  jnz     short loc_18004ADB0
0x18004ad4d  xor     edx, edx
0x18004ad4f  nop
0x18004ad50  cmp     edx, ebx
0x18004ad52  jnb     short loc_18004AD6D
0x18004ad54  cmp     edx, 6
0x18004ad57  jnb     short loc_18004AD64
0x18004ad59  lea     rcx, [rdx+rdx*2]
0x18004ad5d  cmp     dword ptr [rdi+rcx*8+6Ch], 1
0x18004ad62  jz      short loc_18004AD68
0x18004ad64  inc     edx
0x18004ad66  jmp     short loc_18004AD50
0x18004ad68  cmp     edx, 0FFFFFFFFh
0x18004ad6b  jnz     short loc_18004ADB0
0x18004ad6d  xor     ebx, ebx
0x18004ad6f  mov     rcx, [rdi+100h]
0x18004ad76  test    rcx, rcx
0x18004ad79  jz      short loc_18004AD8B
0x18004ad7b  mov     rbx, rcx
0x18004ad7e  mov     rax, [rcx]
0x18004ad81  mov     rax, [rax+8]
0x18004ad85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad8a  nop
0x18004ad8b  test    rbx, rbx
0x18004ad8e  setnz   r12b
0x18004ad92  test    rbx, rbx
0x18004ad95  jz      short loc_18004ADA7
0x18004ad97  mov     rax, [rbx]
0x18004ad9a  mov     rcx, rbx
0x18004ad9d  mov     rax, [rax+10h]
0x18004ada1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ada6  nop
0x18004ada7  jmp     short loc_18004ADB0
0x18004ada9  mov     r12b, 1
0x18004adac  movzx   r15d, r12b
0x18004adb0  cmp     [rbp+150h+var_100], 0
0x18004adb4  jnz     loc_18004C71E
0x18004adba  mov     rcx, [rbp+150h+var_130]; bstrString
0x18004adbe  test    rcx, rcx
0x18004adc1  jz      short loc_18004ADD1
0x18004adc3  call    cs:__imp_SysFreeString
0x18004adc9  mov     [rbp+150h+var_130], 0
0x18004add1  lea     rcx, [rbp+150h+var_150]
0x18004add5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004adda  mov     rax, [rsp+250h+var_1F0]
0x18004addf  test    r12b, r12b
0x18004ade2  jnz     loc_18004BE0F
0x18004ade8  cmp     dword ptr [rax+8], 0
0x18004adec  jz      loc_18004AF10
0x18004adf2  cmp     byte ptr [rax+2Ch], 0
0x18004adf6  jnz     loc_18004C72C
0x18004adfc  mov     [rsp+250h+var_220], 1
0x18004ae04  mov     r15, [rsp+250h+var_1F0]
0x18004ae09  cmp     byte ptr [r15+2Ch], 0
0x18004ae0e  jnz     short loc_18004AE19
0x18004ae10  test    r12b, r12b
0x18004ae13  jnz     loc_18004BFE0
0x18004ae19  xor     r12d, r12d
0x18004ae1c  mov     [rsp+250h+var_204], r12d
0x18004ae21  mov     [rbp+150h+var_70], r13
0x18004ae28  mov     rbx, [r13+58h]
0x18004ae2c  mov     [rbp+150h+var_78], rbx
0x18004ae33  mov     rax, [rbp+150h+var_E8]
0x18004ae37  mov     [r13+58h], rax
0x18004ae3b  mov     rcx, [rbp+150h+var_1D0]
0x18004ae3f  mov     rax, [rcx]
0x18004ae42  mov     r9d, [rsp+250h+var_1F8]
0x18004ae47  lea     r8, [rsp+250h+var_204]
0x18004ae4c  mov     rdx, r13
0x18004ae4f  mov     rax, [rax+8]
0x18004ae53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae58  mov     edi, eax
0x18004ae5a  test    eax, eax
0x18004ae5c  js      loc_18004BF85
0x18004ae62  mov     ecx, [rsp+250h+var_204]
0x18004ae66  sub     ecx, 1
0x18004ae69  jz      loc_18004BB3E
0x18004ae6f  sub     ecx, 1
0x18004ae72  jz      loc_18004BAE1
0x18004ae78  cmp     ecx, 1
0x18004ae7b  jz      loc_18004BBA4
0x18004ae81  xor     edx, edx
0x18004ae83  mov     [r13+58h], rbx
0x18004ae87  mov     rax, [r15+10h]
0x18004ae8b  mov     [rbp+150h+Buf2], rax
0x18004ae8f  mov     r12d, edx
0x18004ae92  test    rax, rax
0x18004ae95  jz      loc_18004BC9A
0x18004ae9b  movsxd  r13, dword ptr [r15+18h]
0x18004ae9f  test    r13d, r13d
  ... truncated ...
```
