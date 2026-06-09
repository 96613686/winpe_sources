# MsaaProxy::get_ExpandCollapseState(ExpandCollapseState *)

- ea: `0x1801122d0`
- end: `0x180112777`
- name: `?get_ExpandCollapseState@MsaaProxy@@UEAAJPEAW4ExpandCollapseState@@@Z`
- size: `1191`
- prototype: `__int64 __fastcall(MsaaProxy *__hidden this, enum ExpandCollapseState *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180276300`
- `0x180276460`

## callees

- `0x18000b790`
- `0x18000f680`
- `0x18002f580`
- `0x180048ab0`
- `0x18008438c`
- `0x180085540`
- `0x18008a8ec`
- `0x1801122d0`
- `0x180112780`
- `0x180112848`
- `0x1801128f8`
- `0x1801e8344`
- `0x180276808`
- `0x1802dd010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180112421`
- `OLEAUT32!__imp_VariantClear` at `0x1801124a4`
- `OLEAUT32!__imp_VariantClear` at `0x1801125e0`
- `OLEAUT32!__imp_VariantClear` at `0x1801126a5`
- `OLEAUT32!__imp_VariantClear` at `0x180112765`
- `OLEAUT32!__imp_VariantClear` at `0x180112421`
- `OLEAUT32!__imp_VariantClear` at `0x1801124a4`
- `OLEAUT32!__imp_VariantClear` at `0x1801125e0`
- `OLEAUT32!__imp_VariantClear` at `0x1801126a5`
- `OLEAUT32!__imp_VariantClear` at `0x180112765`
- `OLEACC!AccessibleChildren` at `0x180112465`
- `OLEACC!AccessibleChildren` at `0x180112465`

## string_xrefs

- `0x18011233b`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180112388`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1801123f2`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180112479`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180112675`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1801126bd`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x18011272b`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x18011262f`: `AccessibleChildren`
- `0x180112656`: `AccessibleChildren`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MsaaProxy::get_ExpandCollapseState(MsaaProxy *this, enum ExpandCollapseState *a2)
{
  int v4; // r15d
  int ExpandCollapseStateForAcc2; // eax
  MsaaProxy *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  int v10; // eax
  int v11; // r14d
  VARIANTARG *v12; // rdi
  unsigned int v13; // ebx
  unsigned int i; // esi
  HRESULT v15; // eax
  unsigned int v16; // ebx
  unsigned int j; // esi
  enum ExpandCollapseState v18; // r12d
  LONG k; // r14d
  VARIANTARG *v20; // rax
  int v21; // eax
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, struct IAccessible **); // r15
  __int64 (__fastcall *v23)(_QWORD, GUID *, struct IAccessible **); // rbx
  int v24; // eax
  int accState; // eax
  unsigned int v26; // ebx
  unsigned int n; // esi
  __int64 v29; // rbx
  unsigned int ii; // esi
  struct IAccessible *v31; // rcx
  __int64 v32; // rbx
  unsigned int m; // esi
  int pcObtained; // [rsp+20h] [rbp-58h]
  int pcObtaineda; // [rsp+20h] [rbp-58h]
  struct IAccessible *v36; // [rsp+30h] [rbp-48h] BYREF
  struct IAccessible2 *v37; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v38; // [rsp+40h] [rbp-38h] BYREF
  void *Block; // [rsp+48h] [rbp-30h]
  struct tagVARIANT v40; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  unsigned int v42; // [rsp+C0h] [rbp+48h] BYREF
  LONG cChildren; // [rsp+C8h] [rbp+50h] BYREF
  LONG v44; // [rsp+D0h] [rbp+58h] BYREF
  IAccessible *paccContainer; // [rsp+D8h] [rbp+60h] BYREF

  *a2 = ExpandCollapseState_LeafNode;
  v4 = 0;
  v37 = 0;
  ExpandCollapseStateForAcc2 = AgileInterface<IAccessible2>::TryGet((char *)this + 224, *((_QWORD *)this + 23), &v37);
  v7 = ExpandCollapseStateForAcc2;
  if ( ExpandCollapseStateForAcc2 < 0 )
  {
    v8 = 2602;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
      (const char *)(unsigned int)ExpandCollapseStateForAcc2,
      pcObtained);
    goto LABEL_42;
  }
  if ( v37 )
  {
    ExpandCollapseStateForAcc2 = MsaaProxy::GetExpandCollapseStateForAcc2(v6, v37, a2);
    v7 = ExpandCollapseStateForAcc2;
    if ( ExpandCollapseStateForAcc2 >= 0 )
      goto LABEL_41;
    v8 = 2605;
    goto LABEL_6;
  }
  if ( *((_DWORD *)this + 66) )
    goto LABEL_41;
  paccContainer = 0;
  v9 = AgileInterface<IAccessible>::Get((char *)this + 192, *((_QWORD *)this + 23), &paccContainer);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3B,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
      (const char *)(unsigned int)v9,
      pcObtained);
    wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&paccContainer);
    goto LABEL_42;
  }
  cChildren = 0;
  if ( (int)AccUtils::get_accChildCount(paccContainer, *((HWND *)this + 21), &cChildren) < 0 || !cChildren )
    goto LABEL_40;
  v38 = 0;
  Block = 0;
  v10 = StructArrayPair<tagVARIANT>::AllocInit(&v38);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA48,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
      (const char *)(unsigned int)v10,
      pcObtained);
    v12 = (VARIANTARG *)Block;
    if ( !Block )
    {
LABEL_17:
      wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&paccContainer);
      v7 = v11;
      goto LABEL_42;
    }
    v13 = 0;
    for ( i = v38; v13 < i; ++v13 )
      VariantClear(&v12[v13]);
LABEL_16:
    operator delete(v12);
    goto LABEL_17;
  }
  v44 = 0;
  v12 = (VARIANTARG *)Block;
  v15 = AccessibleChildren(paccContainer, 0, cChildren, (VARIANT *)Block, &v44);
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4A,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
      (const char *)(unsigned int)v15,
      pcObtaineda);
    if ( !v12 )
      goto LABEL_17;
    v16 = 0;
    for ( j = v38; v16 < j; ++v16 )
      VariantClear(&v12[v16]);
    goto LABEL_16;
  }
  v18 = ExpandCollapseState_Collapsed;
  for ( k = 0; ; ++k )
  {
    if ( k >= v44 )
      goto LABEL_36;
    v42 = 0;
    v20 = &v12[k];
    if ( v20->vt == 3 )
      break;
    if ( v20->vt != 9 )
    {
      Error::IAccessibleError((struct IUnknown *)paccContainer, L"AccessibleChildren", 0, *((HWND *)this + 21), 601);
      continue;
    }
    llVal = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IAccessible **))v20->llVal;
    if ( !llVal )
    {
      Error::IAccessibleError((struct IUnknown *)paccContainer, L"AccessibleChildren", 0, *((HWND *)this + 21), 602);
      v4 = 0;
      continue;
    }
    v36 = 0;
    v23 = **llVal;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    v24 = v23(llVal, &GUID_618736e0_3c3d_11cf_810c_00aa00389b71, &v36);
    v4 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA57,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
        (const char *)(unsigned int)v24,
        pcObtaineda);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
      if ( v12 )
      {
        v32 = 0;
        for ( m = v38; (unsigned int)v32 < m; v32 = (unsigned int)(v32 + 1) )
          VariantClear(&v12[v32]);
        goto LABEL_39;
      }
      goto LABEL_40;
    }
    memset(&v40, 0, sizeof(v40));
    v40.vt = 3;
    v4 = 0;
    v40.lVal = 0;
    accState = AccUtils::get_accState(v36, *((HWND *)this + 21), &v40, &v42);
    v7 = accState;
    if ( accState < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5B,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
        (const char *)(unsigned int)accState,
        pcObtaineda);
      v31 = v36;
      if ( v36 )
      {
        v36 = 0;
        ((void (__fastcall *)(struct IAccessible *))v31->lpVtbl->Release)(v31);
      }
      StructArrayPair<tagVARIANT>::SafeRelease(&v38);
      if ( paccContainer )
        ((void (__fastcall *)(IAccessible *))paccContainer->lpVtbl->Release)(paccContainer);
      if ( v37 )
        (*(void (__fastcall **)(struct IAccessible2 *))(*(_QWORD *)v37 + 16LL))(v37);
      return v7;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
LABEL_33:
    if ( (v42 & 0x8000) == 0 && (v42 & 0x10000) == 0 )
    {
      v18 = ExpandCollapseState_Expanded;
LABEL_36:
      *a2 = v18;
      if ( !v12 )
        goto LABEL_40;
      v26 = 0;
      for ( n = v38; v26 < n; ++v26 )
        VariantClear(&v12[v26]);
LABEL_39:
      operator delete(v12);
      goto LABEL_40;
    }
  }
  v21 = AccUtils::get_accState(paccContainer, *((HWND *)this + 21), &v12[k], &v42);
  v4 = v21;
  if ( v21 >= 0 )
  {
    v4 = 0;
    goto LABEL_33;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA50,
    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
    (const char *)(unsigned int)v21,
    pcObtaineda);
  if ( v12 )
  {
    v29 = 0;
    for ( ii = v38; (unsigned int)v29 < ii; v29 = (unsigned int)(v29 + 1) )
      VariantClear(&v12[v29]);
    goto LABEL_39;
  }
LABEL_40:
  wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&paccContainer);
LABEL_41:
  v7 = v4;
LABEL_42:
  wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v37);
  return v7;
}

```

## disassembly

```asm
0x1801122d0  push    rbp
0x1801122d2  push    rbx
0x1801122d3  push    rsi
0x1801122d4  push    rdi
0x1801122d5  push    r12
0x1801122d7  push    r13
0x1801122d9  push    r14
0x1801122db  push    r15
0x1801122dd  mov     rbp, rsp
0x1801122e0  sub     rsp, 78h
0x1801122e4  mov     r13, rdx
0x1801122e7  mov     rsi, rcx
0x1801122ea  mov     dword ptr [rdx], 3
0x1801122f0  add     rcx, 0E0h
0x1801122f7  xor     r15d, r15d
0x1801122fa  mov     [rbp+var_40], r15
0x1801122fe  lea     r8, [rbp+var_40]
0x180112302  mov     rdx, [rsi+0B8h]
0x180112309  call    ?TryGet@?$AgileInterface@UIAccessible2@@@@QEAAJPEAUIGlobalInterfaceTable@@PEAPEAUIAccessible2@@@Z; AgileInterface<IAccessible2>::TryGet(IGlobalInterfaceTable *,IAccessible2 * *)
0x18011230e  mov     ebx, eax
0x180112310  test    eax, eax
0x180112312  jns     short loc_18011231B
0x180112314  mov     edx, 0A2Ah
0x180112319  jmp     short loc_18011233B
0x18011231b  mov     rdx, [rbp+var_40]; struct IAccessible2 *
0x18011231f  test    rdx, rdx
0x180112322  jz      short loc_180112353
0x180112324  mov     r8, r13; enum ExpandCollapseState *
0x180112327  call    ?GetExpandCollapseStateForAcc2@MsaaProxy@@AEAAJPEAUIAccessible2@@PEAW4ExpandCollapseState@@@Z; MsaaProxy::GetExpandCollapseStateForAcc2(IAccessible2 *,ExpandCollapseState *)
0x18011232c  mov     ebx, eax
0x18011232e  test    eax, eax
0x180112330  jns     loc_1801125FE
0x180112336  mov     edx, 0A2Dh; void *
0x18011233b  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x180112342  mov     r9d, eax; char *
0x180112345  mov     rcx, [rbp+40h]; this
0x180112349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011234e  jmp     loc_180112601
0x180112353  cmp     [rsi+108h], r15d
0x18011235a  jnz     loc_1801125FE
0x180112360  mov     [rbp+paccContainer], r15
0x180112364  lea     rcx, [rsi+0C0h]
0x18011236b  lea     r8, [rbp+paccContainer]
0x18011236f  mov     rdx, [rsi+0B8h]
0x180112376  call    ?Get@?$AgileInterface@UIAccessible@@@@QEAAJPEAUIGlobalInterfaceTable@@PEAPEAUIAccessible@@@Z; AgileInterface<IAccessible>::Get(IGlobalInterfaceTable *,IAccessible * *)
0x18011237b  mov     ebx, eax
0x18011237d  test    eax, eax
0x18011237f  jns     short loc_1801123A8
0x180112381  mov     rcx, [rbp+40h]; this
0x180112385  mov     r9d, eax; char *
0x180112388  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x18011238f  mov     edx, 0A3Bh; void *
0x180112394  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112399  nop
0x18011239a  lea     rcx, [rbp+paccContainer]; void *
0x18011239e  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x1801123a3  jmp     loc_180112601
0x1801123a8  mov     [rbp+cChildren], r15d
0x1801123ac  lea     r8, [rbp+cChildren]; int *
0x1801123b0  mov     rdx, [rsi+0A8h]; HWND
0x1801123b7  mov     rcx, [rbp+paccContainer]; struct IAccessible *
0x1801123bb  call    ?get_accChildCount@AccUtils@@SAJPEAUIAccessible@@PEAUHWND__@@PEAJ@Z; AccUtils::get_accChildCount(IAccessible *,HWND__ *,long *)
0x1801123c0  test    eax, eax
0x1801123c2  js      loc_1801125F5
0x1801123c8  mov     edx, [rbp+cChildren]
0x1801123cb  test    edx, edx
0x1801123cd  jz      loc_1801125F5
0x1801123d3  mov     [rbp+var_38], r15d
0x1801123d7  mov     [rbp+Block], r15
0x1801123db  lea     rcx, [rbp+var_38]
0x1801123df  call    ?AllocInit@?$StructArrayPair@UtagVARIANT@@@@QEAAJI@Z; StructArrayPair<tagVARIANT>::AllocInit(uint)
0x1801123e4  mov     r14d, eax
0x1801123e7  test    eax, eax
0x1801123e9  jns     short loc_180112447
0x1801123eb  mov     rcx, [rbp+40h]; this
0x1801123ef  mov     r9d, eax; char *
0x1801123f2  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x1801123f9  mov     edx, 0A48h; void *
0x1801123fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112403  nop
0x180112404  mov     rdi, [rbp+Block]
0x180112408  test    rdi, rdi
0x18011240b  jz      short loc_180112436
0x18011240d  mov     ebx, r15d
0x180112410  mov     esi, [rbp+var_38]
0x180112413  test    esi, esi
0x180112415  jz      short loc_18011242D
0x180112417  mov     eax, ebx
0x180112419  lea     rdx, [rax+rax*2]
0x18011241d  lea     rcx, [rdi+rdx*8]; pvarg
0x180112421  call    cs:__imp_VariantClear
0x180112427  inc     ebx
0x180112429  cmp     ebx, esi
0x18011242b  jb      short loc_180112417
0x18011242d  mov     rcx, rdi; Block
0x180112430  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180112435  nop
0x180112436  lea     rcx, [rbp+paccContainer]; void *
0x18011243a  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x18011243f  mov     ebx, r14d
0x180112442  jmp     loc_180112601
0x180112447  mov     [rbp+arg_10], r15d
0x18011244b  lea     rax, [rbp+arg_10]
0x18011244f  mov     qword ptr [rsp+78h+pcObtained], rax; int
0x180112454  mov     rdi, [rbp+Block]
0x180112458  mov     r9, rdi; rgvarChildren
0x18011245b  mov     r8d, [rbp+cChildren]; cChildren
0x18011245f  xor     edx, edx; iChildStart
0x180112461  mov     rcx, [rbp+paccContainer]; paccContainer
0x180112465  call    cs:__imp_AccessibleChildren
0x18011246b  mov     r14d, eax
0x18011246e  test    eax, eax
0x180112470  jns     short loc_1801124B5
0x180112472  mov     rcx, [rbp+40h]; this
0x180112476  mov     r9d, eax; char *
0x180112479  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x180112480  mov     edx, 0A4Ah; void *
0x180112485  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011248a  nop
0x18011248b  test    rdi, rdi
0x18011248e  jz      short loc_180112436
0x180112490  mov     ebx, r15d
0x180112493  mov     esi, [rbp+var_38]
0x180112496  test    esi, esi
0x180112498  jz      short loc_18011242D
0x18011249a  mov     eax, ebx
0x18011249c  lea     rdx, [rax+rax*2]
0x1801124a0  lea     rcx, [rdi+rdx*8]; pvarg
0x1801124a4  call    cs:__imp_VariantClear
0x1801124aa  inc     ebx
0x1801124ac  cmp     ebx, esi
0x1801124ae  jb      short loc_18011249A
0x1801124b0  jmp     loc_18011242D
0x1801124b5  mov     r12d, r15d
0x1801124b8  mov     r14d, r15d
0x1801124bb  mov     ebx, 3
0x1801124c0  cmp     r14d, [rbp+arg_10]
0x1801124c4  jge     loc_1801125C3
0x1801124ca  mov     [rbp+arg_0], r15d
0x1801124ce  movsxd  rax, r14d
0x1801124d1  lea     rcx, [rax+rax*2]
0x1801124d5  lea     rax, [rdi+rcx*8]
0x1801124d9  cmp     [rax], bx
0x1801124dc  jnz     short loc_180112508
0x1801124de  lea     r9, [rbp+arg_0]; unsigned int *
0x1801124e2  mov     r8, rax; struct tagVARIANT *
0x1801124e5  mov     rdx, [rsi+0A8h]; HWND
0x1801124ec  mov     rcx, [rbp+paccContainer]; struct IAccessible *
0x1801124f0  call    ?get_accState@AccUtils@@SAJPEAUIAccessible@@PEAUHWND__@@AEBUtagVARIANT@@PEAK@Z; AccUtils::get_accState(IAccessible *,HWND__ *,tagVARIANT const &,ulong *)
0x1801124f5  mov     r15d, eax
0x1801124f8  test    eax, eax
0x1801124fa  js      loc_18011266E
0x180112500  xor     r15d, r15d
0x180112503  jmp     loc_1801125A3
0x180112508  cmp     word ptr [rax], 9
0x18011250c  jnz     loc_180112644
0x180112512  mov     r15, [rax+8]
0x180112516  test    r15, r15
0x180112519  jz      loc_18011261D
0x18011251f  mov     [rbp+var_48], 0
0x180112527  mov     rax, [r15]
0x18011252a  mov     rbx, [rax]
0x18011252d  lea     rcx, [rbp+var_48]
0x180112531  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180112536  lea     r8, [rbp+var_48]
0x18011253a  lea     rdx, _GUID_618736e0_3c3d_11cf_810c_00aa00389b71
0x180112541  mov     rcx, r15
0x180112544  mov     rax, rbx
0x180112547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011254c  mov     r15d, eax
0x18011254f  test    eax, eax
0x180112551  js      loc_180112724
0x180112557  xorps   xmm0, xmm0
0x18011255a  xor     eax, eax
0x18011255c  movups  xmmword ptr [rbp+var_28], xmm0
0x180112560  mov     qword ptr [rbp+var_28+10h], rax
0x180112564  mov     eax, 3
0x180112569  mov     word ptr [rbp+var_28], ax
0x18011256d  xor     r15d, r15d
0x180112570  mov     dword ptr [rbp+var_28+8], r15d
0x180112574  lea     r9, [rbp+arg_0]; unsigned int *
0x180112578  lea     r8, [rbp+var_28]; struct tagVARIANT *
0x18011257c  mov     rdx, [rsi+0A8h]; HWND
0x180112583  mov     rcx, [rbp+var_48]; struct IAccessible *
0x180112587  call    ?get_accState@AccUtils@@SAJPEAUIAccessible@@PEAUHWND__@@AEBUtagVARIANT@@PEAK@Z; AccUtils::get_accState(IAccessible *,HWND__ *,tagVARIANT const &,ulong *)
0x18011258c  mov     ebx, eax
0x18011258e  test    eax, eax
0x180112590  js      loc_1801126B6
0x180112596  lea     rcx, [rbp+var_48]
0x18011259a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18011259f  lea     ebx, [r15+3]
0x1801125a3  test    [rbp+arg_0], 8000h
0x1801125aa  jnz     loc_180112666
0x1801125b0  test    [rbp+arg_0], 10000h
0x1801125b7  jnz     loc_180112666
0x1801125bd  mov     r12d, 1
0x1801125c3  mov     [r13+0], r12d
0x1801125c7  test    rdi, rdi
0x1801125ca  jz      short loc_1801125F5
0x1801125cc  mov     ebx, r15d
0x1801125cf  mov     esi, [rbp+var_38]
0x1801125d2  test    esi, esi
0x1801125d4  jz      short loc_1801125EC
0x1801125d6  mov     eax, ebx
0x1801125d8  lea     rcx, [rax+rax*2]
0x1801125dc  lea     rcx, [rdi+rcx*8]; pvarg
0x1801125e0  call    cs:__imp_VariantClear
0x1801125e6  inc     ebx
0x1801125e8  cmp     ebx, esi
0x1801125ea  jb      short loc_1801125D6
0x1801125ec  mov     rcx, rdi; Block
0x1801125ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801125f4  nop
0x1801125f5  lea     rcx, [rbp+paccContainer]; void *
0x1801125f9  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x1801125fe  mov     ebx, r15d
0x180112601  lea     rcx, [rbp+var_40]; void *
0x180112605  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x18011260a  mov     eax, ebx
0x18011260c  add     rsp, 78h
0x180112610  pop     r15
0x180112612  pop     r14
0x180112614  pop     r13
0x180112616  pop     r12
0x180112618  pop     rdi
0x180112619  pop     rsi
0x18011261a  pop     rbx
0x18011261b  pop     rbp
0x18011261c  retn
0x18011261d  mov     [rsp+78h+pcObtained], 25Ah; int
0x180112625  mov     r9, [rsi+0A8h]; HWND
0x18011262c  xor     r8d, r8d; int
0x18011262f  lea     rdx, aAccessiblechil_0; "AccessibleChildren"
0x180112636  mov     rcx, [rbp+paccContainer]; struct IUnknown *
0x18011263a  call    ?IAccessibleError@Error@@SAXPEAUIUnknown@@PEBGJPEAUHWND__@@H@Z; Error::IAccessibleError(IUnknown *,ushort const *,long,HWND__ *,int)
0x18011263f  xor     r15d, r15d
0x180112642  jmp     short loc_180112666
0x180112644  mov     [rsp+78h+pcObtained], 259h; int
0x18011264c  mov     r9, [rsi+0A8h]; HWND
0x180112653  xor     r8d, r8d; int
0x180112656  lea     rdx, aAccessiblechil_0; "AccessibleChildren"
0x18011265d  mov     rcx, [rbp+paccContainer]; struct IUnknown *
0x180112661  call    ?IAccessibleError@Error@@SAXPEAUIUnknown@@PEBGJPEAUHWND__@@H@Z; Error::IAccessibleError(IUnknown *,ushort const *,long,HWND__ *,int)
0x180112666  inc     r14d
0x180112669  jmp     loc_1801124C0
0x18011266e  mov     rcx, [rbp+40h]; this
0x180112672  mov     r9d, r15d; char *
0x180112675  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x18011267c  mov     edx, 0A50h; void *
0x180112681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180112686  nop
0x180112687  test    rdi, rdi
0x18011268a  jz      loc_1801125F5
0x180112690  xor     ebx, ebx
0x180112692  mov     esi, [rbp+var_38]
0x180112695  test    esi, esi
0x180112697  jz      loc_1801125EC
0x18011269d  lea     rcx, [rbx+rbx*2]
0x1801126a1  lea     rcx, [rdi+rcx*8]; pvarg
0x1801126a5  call    cs:__imp_VariantClear
0x1801126ab  inc     ebx
0x1801126ad  cmp     ebx, esi
0x1801126af  jb      short loc_18011269D
0x1801126b1  jmp     loc_1801125EC
0x1801126b6  mov     rcx, [rbp+40h]; this
0x1801126ba  mov     r9d, ebx; char *
0x1801126bd  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x1801126c4  mov     edx, 0A5Bh; void *
0x1801126c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801126ce  nop
0x1801126cf  mov     rcx, [rbp+var_48]
0x1801126d3  test    rcx, rcx
0x1801126d6  jz      short loc_1801126E9
0x1801126d8  mov     [rbp+var_48], r15
0x1801126dc  mov     rax, [rcx]
0x1801126df  mov     rax, [rax+10h]
0x1801126e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801126e8  nop
0x1801126e9  lea     rcx, [rbp+var_38]
0x1801126ed  call    ?SafeRelease@?$StructArrayPair@UtagVARIANT@@@@QEAAXXZ; StructArrayPair<tagVARIANT>::SafeRelease(void)
0x1801126f2  nop
0x1801126f3  mov     rcx, [rbp+paccContainer]
0x1801126f7  test    rcx, rcx
0x1801126fa  jz      short loc_180112709
0x1801126fc  mov     rax, [rcx]
0x1801126ff  mov     rax, [rax+10h]
0x180112703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112708  nop
0x180112709  mov     rcx, [rbp+var_40]
0x18011270d  test    rcx, rcx
0x180112710  jz      short loc_18011271F
0x180112712  mov     rax, [rcx]
0x180112715  mov     rax, [rax+10h]
0x180112719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011271e  nop
0x18011271f  jmp     loc_18011260A
0x180112724  mov     rcx, [rbp+40h]; this
0x180112728  mov     r9d, r15d; char *
0x18011272b  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x180112732  mov     edx, 0A57h; void *
  ... truncated ...
```
