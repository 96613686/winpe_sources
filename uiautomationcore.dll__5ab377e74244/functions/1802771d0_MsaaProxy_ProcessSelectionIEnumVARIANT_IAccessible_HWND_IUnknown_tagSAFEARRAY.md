# MsaaProxy::ProcessSelectionIEnumVARIANT(IAccessible *,HWND__ *,IUnknown *,tagSAFEARRAY * *)

- ea: `0x1802771d0`
- end: `0x180277815`
- name: `?ProcessSelectionIEnumVARIANT@MsaaProxy@@AEAAJPEAUIAccessible@@PEAUHWND__@@PEAUIUnknown@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `1605`
- prototype: `int(MsaaProxy *__hidden this, struct IAccessible *, HWND, struct IUnknown *, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180277ea0`

## callees

- `0x18000f680`
- `0x18001ed40`
- `0x18002f580`
- `0x18008a8ec`
- `0x1800b8d60`
- `0x1800b9108`
- `0x1800ba0a0`
- `0x180112780`
- `0x1801319ac`
- `0x18014ff90`
- `0x1801650c4`
- `0x1801e8344`
- `0x1801e88a0`
- `0x1801e9258`
- `0x1801ef098`
- `0x1802753cc`
- `0x1802771d0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1802772ca`
- `OLEAUT32!__imp_VariantClear` at `0x1802773eb`
- `OLEAUT32!__imp_VariantClear` at `0x180277415`
- `OLEAUT32!__imp_VariantClear` at `0x180277478`
- `OLEAUT32!__imp_VariantClear` at `0x18027754e`
- `OLEAUT32!__imp_VariantClear` at `0x18027766f`
- `OLEAUT32!__imp_VariantClear` at `0x1802776ca`
- `OLEAUT32!__imp_VariantClear` at `0x180277738`
- `OLEAUT32!__imp_VariantClear` at `0x180277789`
- `OLEAUT32!__imp_VariantClear` at `0x1802777d9`
- `OLEAUT32!__imp_VariantClear` at `0x1802772ca`
- `OLEAUT32!__imp_VariantClear` at `0x1802773eb`
- `OLEAUT32!__imp_VariantClear` at `0x180277415`
- `OLEAUT32!__imp_VariantClear` at `0x180277478`
- `OLEAUT32!__imp_VariantClear` at `0x18027754e`
- `OLEAUT32!__imp_VariantClear` at `0x18027766f`
- `OLEAUT32!__imp_VariantClear` at `0x1802776ca`
- `OLEAUT32!__imp_VariantClear` at `0x180277738`
- `OLEAUT32!__imp_VariantClear` at `0x180277789`
- `OLEAUT32!__imp_VariantClear` at `0x1802777d9`

## string_xrefs

- `0x180277258`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180277291`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1802773be`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180277516`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x18027762d`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180277688`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x180277700`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`
- `0x1802777b3`: `onecore\windows\accessibletech\uiautomationcore\proxies\msaaproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall MsaaProxy::ProcessSelectionIEnumVARIANT(
        MsaaProxy *this,
        struct IAccessible *a2,
        HWND a3,
        struct IUnknown *a4,
        struct tagSAFEARRAY **a5)
{
  unsigned int v7; // r15d
  struct IEnumVARIANT *v8; // rax
  struct IEnumVARIANT *v9; // rbx
  unsigned int v10; // esi
  int v11; // eax
  int v12; // eax
  VARIANTARG *v13; // rdi
  unsigned int v14; // ebx
  unsigned int i1; // r14d
  unsigned int v16; // esi
  int v17; // r12d
  unsigned int v18; // r14d
  int v19; // eax
  int v20; // eax
  unsigned int v21; // r12d
  VARIANTARG *v22; // rsi
  __int64 v23; // rbx
  unsigned int j; // r15d
  __int64 k; // rbx
  __int64 m; // rbx
  __int64 v28; // rax
  bool v29; // cf
  unsigned __int64 v30; // rax
  _QWORD *v31; // rax
  __int64 v32; // r8
  _QWORD *v33; // r12
  __int64 nn; // rbx
  unsigned __int64 n; // rax
  int v36; // eax
  int v37; // eax
  __int64 jj; // rbx
  __int64 ii; // rbx
  int v40; // eax
  __int64 mm; // rbx
  __int64 kk; // rbx
  __int64 i; // rbx
  int v44; // [rsp+28h] [rbp-71h]
  int v45; // [rsp+28h] [rbp-71h]
  int v46; // [rsp+28h] [rbp-71h]
  SAFEARRAY *v47; // [rsp+48h] [rbp-51h] BYREF
  _QWORD *v48; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int64 v49; // [rsp+58h] [rbp-41h] BYREF
  void *v50; // [rsp+60h] [rbp-39h]
  unsigned int v51[2]; // [rsp+68h] [rbp-31h] BYREF
  struct IEnumVARIANT *v52; // [rsp+70h] [rbp-29h] BYREF
  unsigned int v53; // [rsp+78h] [rbp-21h] BYREF
  void *Block; // [rsp+80h] [rbp-19h]
  __int64 v55; // [rsp+88h] [rbp-11h] BYREF
  int v56; // [rsp+90h] [rbp-9h]
  struct tagVARIANT v57; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+57h]

  v7 = 0;
  *a5 = 0;
  v8 = (struct IEnumVARIANT *)QI<IEnumVARIANT>(a4);
  v9 = v8;
  v52 = v8;
  if ( v8 )
  {
    v11 = AccUtils::Reset(v8, a3);
    v10 = v11;
    if ( v11 >= 0 )
    {
      v53 = 0;
      Block = 0;
      v12 = StructArrayPair<tagVARIANT>::AllocInit(&v53);
      v10 = v12;
      if ( v12 >= 0 )
      {
        v16 = 8;
        LODWORD(v47) = 8;
        v17 = 8;
        v13 = (VARIANTARG *)Block;
        v18 = v53;
        while ( 1 )
        {
          v51[0] = 0;
          v19 = AccUtils::Next(v9, a3, v16, &v13[v7], v51);
          v10 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1258,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
              (const char *)(unsigned int)v19,
              v45);
            if ( !v13 )
              goto LABEL_73;
            for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
              VariantClear(&v13[i]);
            goto LABEL_72;
          }
          v7 += v51[0];
          if ( !v19 )
            break;
          if ( !v51[0] )
          {
            Error::IAccessibleError((struct IUnknown *)v9, L"IEnumVARIANT::Next", v19, a3, 605);
            break;
          }
          if ( v51[0] < (unsigned int)v47 )
          {
            Error::IAccessibleError((struct IUnknown *)v9, L"IEnumVARIANT::Next", v19, a3, 606);
            break;
          }
          v16 = v17;
          LODWORD(v47) = v17;
          LODWORD(v48) = 2 * v17;
          LODWORD(v49) = 0;
          v50 = 0;
          v20 = StructArrayPair<tagVARIANT>::AllocInit(&v49);
          v21 = v20;
          if ( v20 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1272,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
              (const char *)(unsigned int)v20,
              v45);
            v22 = (VARIANTARG *)v50;
            if ( v50 )
            {
              v23 = 0;
              for ( j = v49; (unsigned int)v23 < j; v23 = (unsigned int)(v23 + 1) )
                VariantClear(&v22[v23]);
              operator delete(v22);
            }
            if ( v13 )
            {
              for ( k = 0; (unsigned int)k < v18; k = (unsigned int)(k + 1) )
                VariantClear(&v13[k]);
              operator delete(v13);
            }
            wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v52);
            return v21;
          }
          HrMemCopyItems<tagVARIANT>(v50, v13, v7);
          operator delete(v13);
          v13 = (VARIANTARG *)v50;
          Block = v50;
          v18 = v49;
          v53 = v49;
          v50 = 0;
          LODWORD(v49) = 0;
          v17 = (int)v48;
        }
        if ( !v7 )
        {
          if ( v13 )
          {
            for ( m = 0; (unsigned int)m < v18; m = (unsigned int)(m + 1) )
              VariantClear(&v13[m]);
            operator delete(v13);
          }
          v10 = 0;
          goto LABEL_73;
        }
        v48 = 0;
        v28 = 8LL * v7;
        if ( !is_mul_ok(v7, 8u) )
          v28 = -1;
        v29 = __CFADD__(v28, 8);
        v30 = v28 + 8;
        if ( v29 )
          v30 = -1;
        v31 = operator new[](v30, (const struct std::nothrow_t *)std::nothrow);
        v49 = (unsigned __int64)v31;
        if ( v31 )
        {
          *v31 = v7;
          v33 = v31 + 1;
          `eh vector constructor iterator'(
            v31 + 1,
            8u,
            v7,
            AutoRelease<IUIAutomationCondition *>::AutoRelease<IUIAutomationCondition *>,
            wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>);
        }
        else
        {
          v33 = 0;
        }
        v48 = v33;
        if ( v33 )
        {
          for ( n = 0; ; n = (unsigned int)((_DWORD)v47 + 1) )
          {
            LODWORD(v47) = n;
            if ( (unsigned int)n >= v7 )
              break;
            v55 = 0;
            v56 = 0;
            v49 = n;
            v57 = v13[n];
            v36 = AccNavUtils::AccPairFromVariant(
                    a2,
                    &v57,
                    a3,
                    (struct IUnknown *)v9,
                    L"IEnumVARIANT::Next",
                    (struct AccPair *)&v55);
            v10 = v36;
            if ( v36 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x128D,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
                (const char *)(unsigned int)v36,
                v46);
              wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v55);
              AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>::~AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>(&v48);
              if ( !v13 )
                goto LABEL_73;
              for ( ii = 0; (unsigned int)ii < v18; ii = (unsigned int)(ii + 1) )
                VariantClear(&v13[ii]);
              goto LABEL_72;
            }
            *(_QWORD *)v51 = 0;
            v37 = MsaaProxy::Wrap<IRawElementProviderSimple *>(
                    (_DWORD)this,
                    v55,
                    v56,
                    (_DWORD)a3,
                    *((_DWORD *)this + 60),
                    0,
                    (__int64)v51);
            v10 = v37;
            if ( v37 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x128F,
                (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
                (const char *)(unsigned int)v37,
                v45);
              wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v55);
              AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>::~AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>(&v48);
              if ( !v13 )
                goto LABEL_73;
              for ( jj = 0; (unsigned int)jj < v18; jj = (unsigned int)(jj + 1) )
                VariantClear(&v13[jj]);
              goto LABEL_72;
            }
            v33[v49] = *(_QWORD *)v51;
            wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v55);
          }
          v47 = 0;
          v40 = ArrayToSafeArray<IUnknown *>((__int64)v33, v7, v32, &v47);
          v10 = v40;
          if ( v40 >= 0 )
          {
            memset_0(v33, 0, 8LL * v7);
            *a5 = v47;
            AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>::~AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>(&v48);
            if ( v13 )
            {
              for ( kk = 0; (unsigned int)kk < v18; kk = (unsigned int)(kk + 1) )
                VariantClear(&v13[kk]);
              operator delete(v13);
            }
            wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v52);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1295,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
            (const char *)(unsigned int)v40,
            v45);
          AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>::~AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>(&v48);
          if ( !v13 )
            goto LABEL_73;
          for ( mm = 0; (unsigned int)mm < v18; mm = (unsigned int)(mm + 1) )
            VariantClear(&v13[mm]);
        }
        else
        {
          v10 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1289,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
            (const char *)0x8007000ELL,
            v45);
          AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>::~AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>(&v48);
          if ( !v13 )
            goto LABEL_73;
          for ( nn = 0; (unsigned int)nn < v18; nn = (unsigned int)(nn + 1) )
            VariantClear(&v13[nn]);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1252,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
          (const char *)(unsigned int)v12,
          v44);
        v13 = (VARIANTARG *)Block;
        if ( !Block )
          goto LABEL_73;
        v14 = 0;
        for ( i1 = v53; v14 < i1; ++v14 )
          VariantClear(&v13[v14]);
      }
LABEL_72:
      operator delete(v13);
      goto LABEL_73;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x124C,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\msaaproxy.cpp",
      (const char *)(unsigned int)v11,
      v44);
  }
  else
  {
    v10 = -2147467262;
    Error::IAccessibleError(a4, L"IDispatch::QueryInterface", -2147467262, a3, 603);
  }
LABEL_73:
  wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v52);
  return v10;
}

```

## disassembly

```asm
0x1802771d0  mov     rax, rsp
0x1802771d3  mov     [rax+18h], rbx
0x1802771d7  mov     [rax+10h], rdx
0x1802771db  mov     [rax+8], rcx
0x1802771df  push    rbp
0x1802771e0  push    rsi
0x1802771e1  push    rdi
0x1802771e2  push    r12
0x1802771e4  push    r13
0x1802771e6  push    r14
0x1802771e8  push    r15
0x1802771ea  lea     rbp, [rax-57h]
0x1802771ee  sub     rsp, 0B0h
0x1802771f5  mov     rdi, r9
0x1802771f8  mov     r13, r8
0x1802771fb  xor     r15d, r15d
0x1802771fe  mov     rax, [rbp+4Fh+arg_20]
0x180277202  mov     [rax], r15
0x180277205  mov     rcx, r9
0x180277208  call    ??$QI@UIEnumVARIANT@@@@YAPEAUIEnumVARIANT@@PEAUIUnknown@@@Z; QI<IEnumVARIANT>(IUnknown *)
0x18027720d  mov     rbx, rax
0x180277210  mov     [rbp+4Fh+var_78], rax
0x180277214  test    rax, rax
0x180277217  jnz     short loc_180277240
0x180277219  mov     dword ptr [rsp+0E0h+var_C0], 25Bh; int
0x180277221  mov     r9, r13; HWND
0x180277224  mov     esi, 80004002h
0x180277229  mov     r8d, esi; int
0x18027722c  lea     rdx, aIdispatchQuery; "IDispatch::QueryInterface"
0x180277233  mov     rcx, rdi; struct IUnknown *
0x180277236  call    ?IAccessibleError@Error@@SAXPEAUIUnknown@@PEBGJPEAUHWND__@@H@Z; Error::IAccessibleError(IUnknown *,ushort const *,long,HWND__ *,int)
0x18027723b  jmp     loc_1802777EF
0x180277240  mov     rdx, r13; HWND
0x180277243  mov     rcx, rbx; struct IEnumVARIANT *
0x180277246  call    ?Reset@AccUtils@@SAJPEAUIEnumVARIANT@@PEAUHWND__@@@Z; AccUtils::Reset(IEnumVARIANT *,HWND__ *)
0x18027724b  mov     esi, eax
0x18027724d  test    eax, eax
0x18027724f  jns     short loc_18027726E
0x180277251  mov     rcx, [rbp+57h]; this
0x180277255  mov     r9d, eax; char *
0x180277258  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x18027725f  mov     edx, 124Ch; void *
0x180277264  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180277269  jmp     loc_1802777EF
0x18027726e  mov     [rbp+4Fh+var_70], r15d
0x180277272  mov     [rbp+4Fh+Block], r15
0x180277276  mov     edx, 8
0x18027727b  lea     rcx, [rbp+4Fh+var_70]
0x18027727f  call    ?AllocInit@?$StructArrayPair@UtagVARIANT@@@@QEAAJI@Z; StructArrayPair<tagVARIANT>::AllocInit(uint)
0x180277284  mov     esi, eax
0x180277286  test    eax, eax
0x180277288  jns     short loc_1802772DC
0x18027728a  mov     rcx, [rbp+57h]; this
0x18027728e  mov     r9d, eax; char *
0x180277291  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x180277298  mov     edx, 1252h; void *
0x18027729d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802772a2  nop
0x1802772a3  mov     rdi, [rbp+4Fh+Block]
0x1802772a7  test    rdi, rdi
0x1802772aa  jz      loc_1802777EF
0x1802772b0  mov     ebx, r15d
0x1802772b3  mov     r14d, [rbp+4Fh+var_70]
0x1802772b7  test    r14d, r14d
0x1802772ba  jz      loc_1802777E6
0x1802772c0  mov     eax, ebx
0x1802772c2  lea     rdx, [rax+rax*2]
0x1802772c6  lea     rcx, [rdi+rdx*8]; pvarg
0x1802772ca  call    cs:__imp_VariantClear
0x1802772d0  inc     ebx
0x1802772d2  cmp     ebx, r14d
0x1802772d5  jb      short loc_1802772C0
0x1802772d7  jmp     loc_1802777E6
0x1802772dc  mov     esi, 8
0x1802772e1  mov     dword ptr [rbp+4Fh+var_A0], esi
0x1802772e4  mov     r12d, esi
0x1802772e7  mov     rdi, [rbp+4Fh+Block]
0x1802772eb  mov     r14d, [rbp+4Fh+var_70]
0x1802772ef  mov     [rbp+4Fh+var_80], 0
0x1802772f6  mov     eax, r15d
0x1802772f9  lea     rcx, [rax+rax*2]
0x1802772fd  lea     r9, [rdi+rcx*8]; struct tagVARIANT *
0x180277301  lea     rax, [rbp+4Fh+var_80]
0x180277305  mov     [rsp+0E0h+var_C0], rax; int
0x18027730a  mov     r8d, esi; unsigned int
0x18027730d  mov     rdx, r13; HWND
0x180277310  mov     rcx, rbx; struct IEnumVARIANT *
0x180277313  call    ?Next@AccUtils@@SAJPEAUIEnumVARIANT@@PEAUHWND__@@KPEAUtagVARIANT@@PEAK@Z; AccUtils::Next(IEnumVARIANT *,HWND__ *,ulong,tagVARIANT *,ulong *)
0x180277318  mov     esi, eax
0x18027731a  test    eax, eax
0x18027731c  js      loc_1802777AC
0x180277322  mov     eax, [rbp+4Fh+var_80]
0x180277325  add     r15d, eax
0x180277328  lea     rcx, aIenumvariantNe; "IEnumVARIANT::Next"
0x18027732f  test    esi, esi
0x180277331  jz      loc_18027745F
0x180277337  test    eax, eax
0x180277339  jz      loc_180277446
0x18027733f  cmp     eax, dword ptr [rbp+4Fh+var_A0]
0x180277342  jb      loc_18027743C
0x180277348  mov     esi, r12d
0x18027734b  mov     dword ptr [rbp+4Fh+var_A0], r12d
0x18027734f  add     r12d, r12d
0x180277352  mov     dword ptr [rbp+4Fh+var_98], r12d
0x180277356  mov     dword ptr [rbp+4Fh+var_90], 0
0x18027735d  mov     [rbp+4Fh+var_88], 0
0x180277365  mov     edx, r12d
0x180277368  lea     rcx, [rbp+4Fh+var_90]
0x18027736c  call    ?AllocInit@?$StructArrayPair@UtagVARIANT@@@@QEAAJI@Z; StructArrayPair<tagVARIANT>::AllocInit(uint)
0x180277371  mov     r12d, eax
0x180277374  test    eax, eax
0x180277376  js      short loc_1802773B7
0x180277378  mov     r8d, r15d
0x18027737b  mov     rdx, rdi
0x18027737e  mov     rcx, [rbp+4Fh+var_88]
0x180277382  call    ??$HrMemCopyItems@UtagVARIANT@@@@YAJPEAUtagVARIANT@@PEBU0@I@Z; HrMemCopyItems<tagVARIANT>(tagVARIANT *,tagVARIANT const *,uint)
0x180277387  mov     rcx, rdi; Block
0x18027738a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18027738f  mov     rdi, [rbp+4Fh+var_88]
0x180277393  mov     [rbp+4Fh+Block], rdi
0x180277397  mov     r14d, dword ptr [rbp+4Fh+var_90]
0x18027739b  mov     [rbp+4Fh+var_70], r14d
0x18027739f  mov     [rbp+4Fh+var_88], 0
0x1802773a7  mov     dword ptr [rbp+4Fh+var_90], 0
0x1802773ae  mov     r12d, dword ptr [rbp+4Fh+var_98]
0x1802773b2  jmp     loc_1802772EF
0x1802773b7  mov     rcx, [rbp+57h]; this
0x1802773bb  mov     r9d, r12d; char *
0x1802773be  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x1802773c5  mov     edx, 1272h; void *
0x1802773ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802773cf  mov     rsi, [rbp+4Fh+var_88]
0x1802773d3  test    rsi, rsi
0x1802773d6  jz      short loc_180277401
0x1802773d8  xor     ebx, ebx
0x1802773da  mov     r15d, dword ptr [rbp+4Fh+var_90]
0x1802773de  test    r15d, r15d
0x1802773e1  jz      short loc_1802773F8
0x1802773e3  lea     rdx, [rbx+rbx*2]
0x1802773e7  lea     rcx, [rsi+rdx*8]; pvarg
0x1802773eb  call    cs:__imp_VariantClear
0x1802773f1  inc     ebx
0x1802773f3  cmp     ebx, r15d
0x1802773f6  jb      short loc_1802773E3
0x1802773f8  mov     rcx, rsi; Block
0x1802773fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180277400  nop
0x180277401  test    rdi, rdi
0x180277404  jz      short loc_18027742B
0x180277406  xor     ebx, ebx
0x180277408  test    r14d, r14d
0x18027740b  jz      short loc_180277422
0x18027740d  lea     rcx, [rbx+rbx*2]
0x180277411  lea     rcx, [rdi+rcx*8]; pvarg
0x180277415  call    cs:__imp_VariantClear
0x18027741b  inc     ebx
0x18027741d  cmp     ebx, r14d
0x180277420  jb      short loc_18027740D
0x180277422  mov     rcx, rdi; Block
0x180277425  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18027742a  nop
0x18027742b  lea     rcx, [rbp+4Fh+var_78]; void *
0x18027742f  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x180277434  mov     eax, r12d
0x180277437  jmp     loc_1802777FA
0x18027743c  mov     dword ptr [rsp+0E0h+var_C0], 25Eh
0x180277444  jmp     short loc_18027744E
0x180277446  mov     dword ptr [rsp+0E0h+var_C0], 25Dh; int
0x18027744e  mov     rdx, rcx; unsigned __int16 *
0x180277451  mov     r9, r13; HWND
0x180277454  mov     r8d, esi; int
0x180277457  mov     rcx, rbx; struct IUnknown *
0x18027745a  call    ?IAccessibleError@Error@@SAXPEAUIUnknown@@PEBGJPEAUHWND__@@H@Z; Error::IAccessibleError(IUnknown *,ushort const *,long,HWND__ *,int)
0x18027745f  test    r15d, r15d
0x180277462  jnz     short loc_180277494
0x180277464  test    rdi, rdi
0x180277467  jz      short loc_18027748D
0x180277469  xor     ebx, ebx
0x18027746b  test    r14d, r14d
0x18027746e  jz      short loc_180277485
0x180277470  lea     rcx, [rbx+rbx*2]
0x180277474  lea     rcx, [rdi+rcx*8]; pvarg
0x180277478  call    cs:__imp_VariantClear
0x18027747e  inc     ebx
0x180277480  cmp     ebx, r14d
0x180277483  jb      short loc_180277470
0x180277485  mov     rcx, rdi; Block
0x180277488  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18027748d  xor     esi, esi
0x18027748f  jmp     loc_1802777EF
0x180277494  mov     [rbp+4Fh+var_98], 0
0x18027749c  mov     esi, r15d
0x18027749f  mov     eax, 8
0x1802774a4  mul     rsi
0x1802774a7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1802774ae  cmovb   rax, rcx
0x1802774b2  add     rax, 8
0x1802774b6  cmovb   rax, rcx
0x1802774ba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1802774c1  mov     rcx, rax; unsigned __int64
0x1802774c4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1802774c9  mov     [rbp+4Fh+var_90], rax
0x1802774cd  test    rax, rax
0x1802774d0  jz      short loc_1802774FE
0x1802774d2  mov     [rax], rsi
0x1802774d5  lea     r12, [rax+8]
0x1802774d9  lea     rax, ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x1802774e0  mov     [rsp+0E0h+var_C0], rax; void (*)(void *)
0x1802774e5  lea     r9, ??0?$AutoRelease@PEAUIUIAutomationCondition@@@@QEAA@XZ; void (*)(void *)
0x1802774ec  mov     r8d, esi; unsigned __int64
0x1802774ef  mov     edx, 8; unsigned __int64
0x1802774f4  mov     rcx, r12; void *
0x1802774f7  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1802774fc  jmp     short loc_180277501
0x1802774fe  xor     r12d, r12d
0x180277501  mov     [rbp+4Fh+var_98], r12
0x180277505  test    r12, r12
0x180277508  jnz     short loc_180277560
0x18027750a  mov     rcx, [rbp+57h]; this
0x18027750e  mov     esi, 8007000Eh
0x180277513  mov     r9d, esi; char *
0x180277516  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x18027751d  mov     edx, 1289h; void *
0x180277522  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180277527  nop
0x180277528  lea     rcx, [rbp+4Fh+var_98]
0x18027752c  call    ??1?$AutoDeleteArray@V?$AutoRelease@PEAUIUIAutomationCondition@@@@@@QEAA@XZ; AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>::~AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>(void)
0x180277531  nop
0x180277532  test    rdi, rdi
0x180277535  jz      loc_1802777EF
0x18027753b  xor     ebx, ebx
0x18027753d  test    r14d, r14d
0x180277540  jz      loc_1802777E6
0x180277546  lea     rcx, [rbx+rbx*2]
0x18027754a  lea     rcx, [rdi+rcx*8]; pvarg
0x18027754e  call    cs:__imp_VariantClear
0x180277554  inc     ebx
0x180277556  cmp     ebx, r14d
0x180277559  jb      short loc_180277546
0x18027755b  jmp     loc_1802777E6
0x180277560  xor     eax, eax
0x180277562  mov     dword ptr [rbp+4Fh+var_A0], eax
0x180277565  cmp     eax, r15d
0x180277568  jnb     loc_1802776DC
0x18027756e  mov     [rbp+4Fh+var_60], 0
0x180277576  mov     [rbp+4Fh+var_58], 0
0x18027757d  mov     [rbp+4Fh+var_90], rax
0x180277581  lea     rax, [rax+rax*2]
0x180277585  movups  xmm0, xmmword ptr [rdi+rax*8]
0x180277589  movaps  xmmword ptr [rbp+4Fh+var_50], xmm0
0x18027758d  movsd   xmm1, qword ptr [rdi+rax*8+10h]
0x180277593  movsd   qword ptr [rbp+4Fh+var_50+10h], xmm1
0x180277598  lea     rax, [rbp+4Fh+var_60]
0x18027759c  mov     [rsp+0E0h+var_B8], rax; struct AccPair *
0x1802775a1  lea     rax, aIenumvariantNe; "IEnumVARIANT::Next"
0x1802775a8  mov     [rsp+0E0h+var_C0], rax; int
0x1802775ad  mov     r9, rbx; struct IUnknown *
0x1802775b0  mov     r8, r13; HWND
0x1802775b3  lea     rdx, [rbp+4Fh+var_50]; struct tagVARIANT
0x1802775b7  mov     rcx, [rbp+4Fh+arg_8]; struct IAccessible *
0x1802775bb  call    ?AccPairFromVariant@AccNavUtils@@SAJPEAUIAccessible@@UtagVARIANT@@PEAUHWND__@@PEAUIUnknown@@PEAGPEAUAccPair@@@Z; AccNavUtils::AccPairFromVariant(IAccessible *,tagVARIANT,HWND__ *,IUnknown *,ushort *,AccPair *)
0x1802775c0  mov     esi, eax
0x1802775c2  test    eax, eax
0x1802775c4  js      loc_180277681
0x1802775ca  mov     qword ptr [rbp+4Fh+var_80], 0
0x1802775d2  lea     rax, [rbp+4Fh+var_80]
0x1802775d6  mov     [rsp+30h], rax
0x1802775db  mov     dword ptr [rsp+0E0h+var_B8], 0
0x1802775e3  mov     rcx, [rbp+4Fh+arg_0]
0x1802775e7  mov     eax, [rcx+0F0h]
0x1802775ed  mov     dword ptr [rsp+0E0h+var_C0], eax; int
0x1802775f1  mov     r9, r13
0x1802775f4  mov     r8d, [rbp+4Fh+var_58]
0x1802775f8  mov     rdx, [rbp+4Fh+var_60]
0x1802775fc  call    ??$Wrap@PEAUIRawElementProviderSimple@@@MsaaProxy@@QEAAJPEAUIAccessible@@JPEAUHWND__@@HW4TRISTATE@0@PEAPEAUIRawElementProviderSimple@@@Z; MsaaProxy::Wrap<IRawElementProviderSimple *>(IAccessible *,long,HWND__ *,int,MsaaProxy::TRISTATE,IRawElementProviderSimple * *)
0x180277601  mov     esi, eax
0x180277603  test    eax, eax
0x180277605  js      short loc_180277626
0x180277607  mov     rax, qword ptr [rbp+4Fh+var_80]
0x18027760b  mov     rcx, [rbp+4Fh+var_90]
0x18027760f  mov     [r12+rcx*8], rax
0x180277613  lea     rcx, [rbp+4Fh+var_60]; void *
0x180277617  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x18027761c  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x18027761f  inc     eax
0x180277621  jmp     loc_180277562
0x180277626  mov     rcx, [rbp+57h]; this
0x18027762a  mov     r9d, eax; char *
0x18027762d  lea     r8, aOnecoreWindows_186; "onecore\\windows\\accessibletech\\uiaut"...
0x180277634  mov     edx, 128Fh; void *
0x180277639  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027763e  nop
0x18027763f  lea     rcx, [rbp+4Fh+var_60]; void *
0x180277643  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x180277648  nop
0x180277649  lea     rcx, [rbp+4Fh+var_98]
0x18027764d  call    ??1?$AutoDeleteArray@V?$AutoRelease@PEAUIUIAutomationCondition@@@@@@QEAA@XZ; AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>::~AutoDeleteArray<AutoRelease<IUIAutomationCondition *>>(void)
0x180277652  nop
0x180277653  test    rdi, rdi
0x180277656  jz      loc_1802777EF
  ... truncated ...
```
