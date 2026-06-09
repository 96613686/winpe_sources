# UiaNode::ProviderGetRuntimeId(int,tagSAFEARRAY * *)

- ea: `0x1800c1080`
- end: `0x1800c1670`
- name: `?ProviderGetRuntimeId@UiaNode@@AEAAJHPEAPEAUtagSAFEARRAY@@@Z`
- size: `1520`
- prototype: `int(UiaNode *__hidden this, int, struct tagSAFEARRAY **)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004a4e0`
- `0x18004aa10`
- `0x1800bf960`

## callees

- `0x18000f680`
- `0x18002f580`
- `0x1800320ec`
- `0x1800c1080`
- `0x1800c1c70`
- `0x1800c2068`
- `0x1800c20c0`
- `0x180186cd0`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e88a0`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800c1182`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800c1182`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800c1154`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800c1154`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c13bd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c13fc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c14c0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c13bd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c13fc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c14c0`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c1274`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c1274`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c12e6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c12e6`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c12c9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c12c9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c130e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c130e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c137f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c158a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c137f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c158a`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c1293`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c1293`

## string_xrefs

- `0x1800c1452`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c1555`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c156b`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c147b`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c1635`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UiaNode::ProviderGetRuntimeId(UiaNode *this, unsigned int a2, struct tagSAFEARRAY **a3)
{
  __int64 v6; // rbx
  char *v7; // rdx
  __int64 (__fastcall ***v8)(_QWORD, GUID *, LONG *); // rbx
  __int64 v9; // rcx
  BOOL v10; // ecx
  int RuntimeIdFromProviderEntryPoint; // eax
  unsigned int v12; // edi
  int v13; // eax
  int v14; // ecx
  struct IRawElementProviderFragment *v15; // rsi
  int v16; // ecx
  int v17; // ebx
  HRESULT Vartype; // eax
  unsigned int v19; // ebx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  unsigned __int64 v22; // rax
  _DWORD *v23; // rdi
  unsigned int v24; // ecx
  int i; // ebx
  unsigned int RuntimeIdFromPartial; // ebx
  SAFEARRAY *v28; // rcx
  __int64 v29; // r14
  __int64 v30; // rdx
  __int64 v31; // r9
  int lpString2; // [rsp+20h] [rbp-E0h]
  int lpString2a; // [rsp+20h] [rbp-E0h]
  int lpString2b; // [rsp+20h] [rbp-E0h]
  VARTYPE pvt; // [rsp+30h] [rbp-D0h] BYREF
  SAFEARRAY *psa; // [rsp+38h] [rbp-C8h] BYREF
  LONG plUbound; // [rsp+40h] [rbp-C0h] BYREF
  LONG plLbound[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h]
  SAFEARRAY *v40; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+60h] [rbp-A0h]
  void *ppvData; // [rsp+68h] [rbp-98h] BYREF
  struct IRawElementProviderFragment *v43; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ClassName[128]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  *a3 = 0;
  if ( a2 < *((_DWORD *)this + 60) && a2 < 6 && (v6 = a2, *((_BYTE *)this + 24 * a2 + 104)) )
  {
    wil::com_query<IUiaNode,Microsoft::WRL::ComPtr<IUnknown> &>(plLbound, (char *)this + 24 * a2 + 96);
    v29 = *(_QWORD *)plLbound;
    if ( *(_QWORD *)plLbound )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)plLbound + 16LL))(*(_QWORD *)plLbound);
    if ( v29 )
      return (*(__int64 (__fastcall **)(__int64, struct tagSAFEARRAY **))(*(_QWORD *)v29 + 80LL))(v29, a3);
  }
  else
  {
    v6 = a2;
  }
  if ( a2 >= *((_DWORD *)this + 60) )
    return 0;
  if ( a2 >= 6 )
    return 0;
  v7 = (char *)this + 24 * v6;
  if ( v7[104] )
    return 0;
  _mm_lfence();
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, LONG *))*((_QWORD *)this + 3 * v6 + 12);
  if ( !v8 )
    return 0;
  if ( (v9 = *((_QWORD *)this + 32)) == 0
    || *(_DWORD *)(v9 + 40)
    || !*((_DWORD *)v7 + 27)
    || *(_BYTE *)(v9 + 60)
    || (!GetClassNameW(*(HWND *)(v9 + 24), ClassName, 128)
      ? (v10 = 0)
      : (v10 = CompareStringW(0x7Fu, 1u, ClassName, -1, L"Chrome_RenderWidgetHostHWND", -1) == 2),
        !v10) )
  {
    LOBYTE(pvt) = 0;
    RuntimeIdFromProviderEntryPoint = UiaNode::TryGetRuntimeIdFromProviderEntryPoint(this, a3, (bool *)&pvt);
    v12 = RuntimeIdFromProviderEntryPoint;
    if ( RuntimeIdFromProviderEntryPoint < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB3,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
        (const char *)(unsigned int)RuntimeIdFromProviderEntryPoint,
        lpString2);
      return v12;
    }
    if ( (_BYTE)pvt )
      return 0;
  }
  *(_QWORD *)plLbound = 0;
  v13 = (**v8)(v8, &GUID_f7063da8_8359_439c_9297_bbc5299a7d87, plLbound);
  v15 = *(struct IRawElementProviderFragment **)plLbound;
  if ( v13 )
    v15 = 0;
  v43 = v15;
  if ( !v15 )
    return 0;
  psa = 0;
  *(_QWORD *)plLbound = L"IRawElementProviderFragment::GetRuntimeId";
  v39 = 0;
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    McTemplateU0zqq_EventWriteTransfer(
      v14,
      (unsigned int)UiaProviderCallout_Start,
      (unsigned int)L"IRawElementProviderFragment::GetRuntimeId",
      0,
      0);
  v17 = ((__int64 (__fastcall *)(struct IRawElementProviderFragment *, SAFEARRAY **))v15->lpVtbl->GetRuntimeId)(
          v15,
          &psa);
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    McTemplateU0zqq_EventWriteTransfer(
      v16,
      (unsigned int)UiaProviderCallout_Stop,
      (unsigned int)L"IRawElementProviderFragment::GetRuntimeId",
      0,
      0);
  if ( v17 == -2147220991 )
  {
    AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(&psa);
    ((void (__fastcall *)(struct IRawElementProviderFragment *))v15->lpVtbl->Release)(v15);
    return 2147746305LL;
  }
  if ( v17 < 0 || !psa )
  {
    if ( psa )
    {
      SafeArrayDestroy(psa);
      psa = 0;
    }
    goto LABEL_49;
  }
  v41 = 0;
  ppvData = 0;
  v40 = psa;
  if ( SafeArrayGetDim(psa) != 1 )
  {
    v31 = 2147942487LL;
    v19 = -2147024809;
    v30 = 92;
    goto LABEL_65;
  }
  pvt = 0;
  Vartype = SafeArrayGetVartype(v40, &pvt);
  v19 = Vartype;
  if ( Vartype < 0 )
  {
    v30 = 95;
    v31 = (unsigned int)Vartype;
    goto LABEL_65;
  }
  if ( pvt != 3 && pvt != 22 )
  {
    v31 = 2147942487LL;
    v19 = -2147024809;
    v30 = 106;
LABEL_65:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v31,
      lpString2);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v19,
      lpString2b);
    v28 = v40;
    if ( v40 )
      goto LABEL_66;
    goto LABEL_52;
  }
  plLbound[0] = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(v40, 1u, plLbound);
  v19 = LBound;
  if ( LBound < 0 )
  {
    v30 = 111;
LABEL_62:
    v31 = (unsigned int)LBound;
    goto LABEL_65;
  }
  UBound = SafeArrayGetUBound(v40, 1u, &plUbound);
  v19 = UBound;
  if ( UBound < 0 )
  {
    v30 = 112;
    v31 = (unsigned int)UBound;
    goto LABEL_65;
  }
  v41 = plUbound - plLbound[0] + 1;
  LBound = SafeArrayAccessData(v40, &ppvData);
  v19 = LBound;
  if ( LBound < 0 )
  {
    v30 = 115;
    goto LABEL_62;
  }
  v22 = 4LL * (unsigned int)v41;
  if ( !is_mul_ok((unsigned int)v41, 4u) )
    v22 = -1;
  v23 = operator new[](v22, (const struct std::nothrow_t *)std::nothrow);
  if ( !v23 )
  {
    v19 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)0x8007000ELL,
      lpString2);
    v28 = v40;
    if ( v40 )
LABEL_66:
      SafeArrayUnaccessData(v28);
LABEL_52:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD6,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
      (const char *)v19,
      lpString2a);
    operator delete(0);
    AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(&psa);
    ((void (__fastcall *)(struct IRawElementProviderFragment *))v15->lpVtbl->Release)(v15);
    return v19;
  }
  v24 = 0;
  for ( i = v41; v24 < v41; i = v41 )
  {
    v23[v24] = *((_DWORD *)ppvData + v24);
    ++v24;
  }
  if ( v40 )
    SafeArrayUnaccessData(v40);
  if ( !i )
  {
    operator delete(v23);
    AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(&psa);
    wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v43);
    return 0;
  }
  if ( i == 1 || *v23 != 3 )
  {
    *a3 = psa;
    psa = 0;
    operator delete(v23);
    if ( psa )
    {
      SafeArrayDestroy(psa);
      psa = 0;
    }
LABEL_49:
    ((void (__fastcall *)(struct IRawElementProviderFragment *))v15->lpVtbl->Release)(v15);
    return 0;
  }
  RuntimeIdFromPartial = UiaNode::ProviderGetRuntimeIdFromPartial(v15, v23, i, a3);
  operator delete(v23);
  if ( psa )
  {
    SafeArrayDestroy(psa);
    psa = 0;
  }
  ((void (__fastcall *)(struct IRawElementProviderFragment *))v15->lpVtbl->Release)(v15);
  return RuntimeIdFromPartial;
}

```

## disassembly

```asm
0x1800c1080  mov     [rsp-8+arg_18], rbx
0x1800c1085  push    rbp
0x1800c1086  push    rsi
0x1800c1087  push    rdi
0x1800c1088  push    r12
0x1800c108a  push    r13
0x1800c108c  push    r14
0x1800c108e  push    r15
0x1800c1090  lea     rbp, [rsp-90h]
0x1800c1098  sub     rsp, 190h
0x1800c109f  mov     rax, cs:__security_cookie
0x1800c10a6  xor     rax, rsp
0x1800c10a9  mov     [rbp+0C0h+var_40], rax
0x1800c10b0  mov     r15, r8
0x1800c10b3  mov     edi, edx
0x1800c10b5  mov     rsi, rcx
0x1800c10b8  xor     r12d, r12d
0x1800c10bb  mov     [r8], r12
0x1800c10be  cmp     edx, [rcx+0F0h]
0x1800c10c4  jnb     short loc_1800C10DC
0x1800c10c6  cmp     edi, 6
0x1800c10c9  jnb     short loc_1800C10DC
0x1800c10cb  mov     ebx, edi
0x1800c10cd  lea     rax, [rdi+rdi*2]
0x1800c10d1  cmp     [rcx+rax*8+68h], r12b
0x1800c10d6  jnz     loc_1800C14E0
0x1800c10dc  mov     rbx, rdi
0x1800c10df  cmp     edi, [rsi+0F0h]
0x1800c10e5  jnb     loc_1800C1417
0x1800c10eb  cmp     edi, 6
0x1800c10ee  jnb     loc_1800C1417
0x1800c10f4  lea     rax, [rbx+rbx*2]
0x1800c10f8  lea     rdx, [rsi+rax*8]
0x1800c10fc  cmp     byte ptr [rdx+68h], 0
0x1800c1100  jnz     loc_1800C1417
0x1800c1106  lfence
0x1800c1109  lea     rax, [rbx+rbx*2]
0x1800c110d  mov     rbx, [rsi+rax*8+60h]
0x1800c1112  test    rbx, rbx
0x1800c1115  jz      loc_1800C1417
0x1800c111b  mov     rcx, [rsi+100h]
0x1800c1122  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800c1129  mov     r14d, 1
0x1800c112f  test    rcx, rcx
0x1800c1132  jz      short loc_1800C1196
0x1800c1134  cmp     dword ptr [rcx+28h], 0
0x1800c1138  jnz     short loc_1800C1196
0x1800c113a  cmp     dword ptr [rdx+6Ch], 0
0x1800c113e  jz      short loc_1800C1196
0x1800c1140  cmp     byte ptr [rcx+3Ch], 0
0x1800c1144  jnz     short loc_1800C1196
0x1800c1146  mov     r8d, 80h; nMaxCount
0x1800c114c  lea     rdx, [rbp+0C0h+ClassName]; lpClassName
0x1800c1150  mov     rcx, [rcx+18h]; hWnd
0x1800c1154  call    cs:__imp_GetClassNameW
0x1800c115a  test    eax, eax
0x1800c115c  jz      loc_1800C159F
0x1800c1162  mov     [rsp+1C0h+cchCount2], r13d; cchCount2
0x1800c1167  lea     rax, aChromeRenderwi; "Chrome_RenderWidgetHostHWND"
0x1800c116e  mov     [rsp+1C0h+lpString2], rax; int
0x1800c1173  mov     r9d, r13d; cchCount1
0x1800c1176  lea     r8, [rbp+0C0h+ClassName]; lpString1
0x1800c117a  mov     edx, r14d; dwCmpFlags
0x1800c117d  mov     ecx, 7Fh; Locale
0x1800c1182  call    cs:__imp_CompareStringW
0x1800c1188  mov     ecx, r12d
0x1800c118b  cmp     eax, 2
0x1800c118e  cmovz   ecx, r14d
0x1800c1192  test    ecx, ecx
0x1800c1194  jnz     short loc_1800C11C0
0x1800c1196  mov     byte ptr [rsp+1C0h+pvt], 0
0x1800c119b  lea     r8, [rsp+1C0h+pvt]; bool *
0x1800c11a0  mov     rdx, r15; struct tagSAFEARRAY **
0x1800c11a3  mov     rcx, rsi; this
0x1800c11a6  call    ?TryGetRuntimeIdFromProviderEntryPoint@UiaNode@@AEBAJPEAPEAUtagSAFEARRAY@@PEA_N@Z; UiaNode::TryGetRuntimeIdFromProviderEntryPoint(tagSAFEARRAY * *,bool *)
0x1800c11ab  mov     edi, eax
0x1800c11ad  test    eax, eax
0x1800c11af  js      loc_1800C162B
0x1800c11b5  cmp     byte ptr [rsp+1C0h+pvt], 0
0x1800c11ba  jnz     loc_1800C1417
0x1800c11c0  mov     qword ptr [rsp+1C0h+plLbound], r12
0x1800c11c5  mov     rax, [rbx]
0x1800c11c8  lea     r8, [rsp+1C0h+plLbound]
0x1800c11cd  lea     rdx, _GUID_f7063da8_8359_439c_9297_bbc5299a7d87
0x1800c11d4  mov     rcx, rbx
0x1800c11d7  mov     rax, [rax]
0x1800c11da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c11df  mov     rsi, qword ptr [rsp+1C0h+plLbound]
0x1800c11e4  test    eax, eax
0x1800c11e6  cmovnz  rsi, r12
0x1800c11ea  mov     [rsp+1C0h+var_150], rsi
0x1800c11ef  test    rsi, rsi
0x1800c11f2  jz      loc_1800C14B6
0x1800c11f8  mov     [rsp+1C0h+psa], r12
0x1800c11fd  lea     rdi, aIrawelementpro_0; "IRawElementProviderFragment::GetRuntime"...
0x1800c1204  mov     qword ptr [rsp+1C0h+plLbound], rdi
0x1800c1209  mov     [rsp+1C0h+var_170], r12
0x1800c120e  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800c1215  jnz     loc_1800C15CC
0x1800c121b  mov     rax, [rsi]
0x1800c121e  lea     rdx, [rsp+1C0h+psa]
0x1800c1223  mov     rcx, rsi
0x1800c1226  mov     rax, [rax+20h]
0x1800c122a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c122f  mov     ebx, eax
0x1800c1231  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800c1238  jnz     loc_1800C15E8
0x1800c123e  cmp     ebx, 80040201h
0x1800c1244  jz      loc_1800C15A7
0x1800c124a  mov     rcx, [rsp+1C0h+psa]; psa
0x1800c124f  test    ebx, ebx
0x1800c1251  js      loc_1800C14BB
0x1800c1257  test    rcx, rcx
0x1800c125a  jz      loc_1800C14BB
0x1800c1260  mov     [rsp+1C0h+var_168], r12
0x1800c1265  mov     [rsp+1C0h+var_160], r12d
0x1800c126a  mov     [rsp+1C0h+ppvData], r12
0x1800c126f  mov     [rsp+1C0h+var_168], rcx
0x1800c1274  call    cs:__imp_SafeArrayGetDim
0x1800c127a  cmp     eax, 1
0x1800c127d  jnz     loc_1800C1540
0x1800c1283  mov     [rsp+1C0h+pvt], r12w
0x1800c1289  lea     rdx, [rsp+1C0h+pvt]; pvt
0x1800c128e  mov     rcx, [rsp+1C0h+var_168]; psa
0x1800c1293  call    cs:__imp_SafeArrayGetVartype
0x1800c1299  mov     ebx, eax
0x1800c129b  test    eax, eax
0x1800c129d  js      loc_1800C1595
0x1800c12a3  movzx   eax, [rsp+1C0h+pvt]
0x1800c12a8  cmp     ax, 3
0x1800c12ac  jnz     loc_1800C160E
0x1800c12b2  mov     [rsp+1C0h+plLbound], r12d
0x1800c12b7  mov     [rsp+1C0h+plUbound], r12d
0x1800c12bc  lea     r8, [rsp+1C0h+plLbound]; plLbound
0x1800c12c1  mov     edx, r14d; nDim
0x1800c12c4  mov     rcx, [rsp+1C0h+var_168]; psa
0x1800c12c9  call    cs:__imp_SafeArrayGetLBound
0x1800c12cf  mov     ebx, eax
0x1800c12d1  test    eax, eax
0x1800c12d3  js      loc_1800C152C
0x1800c12d9  lea     r8, [rsp+1C0h+plUbound]; plUbound
0x1800c12de  mov     edx, r14d; nDim
0x1800c12e1  mov     rcx, [rsp+1C0h+var_168]; psa
0x1800c12e6  call    cs:__imp_SafeArrayGetUBound
0x1800c12ec  mov     ebx, eax
0x1800c12ee  test    eax, eax
0x1800c12f0  js      loc_1800C1536
0x1800c12f6  mov     eax, [rsp+1C0h+plUbound]
0x1800c12fa  sub     eax, [rsp+1C0h+plLbound]
0x1800c12fe  inc     eax
0x1800c1300  mov     [rsp+1C0h+var_160], eax
0x1800c1304  lea     rdx, [rsp+1C0h+ppvData]; ppvData
0x1800c1309  mov     rcx, [rsp+1C0h+var_168]; psa
0x1800c130e  call    cs:__imp_SafeArrayAccessData
0x1800c1314  mov     ebx, eax
0x1800c1316  test    eax, eax
0x1800c1318  js      loc_1800C1604
0x1800c131e  mov     ecx, [rsp+1C0h+var_160]
0x1800c1322  mov     eax, 4
0x1800c1327  mul     rcx
0x1800c132a  cmovb   rax, r13
0x1800c132e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c1335  mov     rcx, rax; unsigned __int64
0x1800c1338  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800c133d  mov     rdi, rax
0x1800c1340  test    rax, rax
0x1800c1343  jz      loc_1800C1443
0x1800c1349  mov     ecx, r12d
0x1800c134c  mov     ebx, [rsp+1C0h+var_160]
0x1800c1350  test    ebx, ebx
0x1800c1352  jz      short loc_1800C1375
0x1800c1354  mov     edx, ecx
0x1800c1356  lea     r8, ds:0[rdx*4]
0x1800c135e  mov     rdx, [rsp+1C0h+ppvData]
0x1800c1363  mov     eax, [rdx+r8]
0x1800c1367  mov     [rdi+r8], eax
0x1800c136b  inc     ecx
0x1800c136d  mov     ebx, [rsp+1C0h+var_160]
0x1800c1371  cmp     ecx, ebx
0x1800c1373  jb      short loc_1800C1354
0x1800c1375  mov     rcx, [rsp+1C0h+var_168]; psa
0x1800c137a  test    rcx, rcx
0x1800c137d  jz      short loc_1800C1385
0x1800c137f  call    cs:__imp_SafeArrayUnaccessData
0x1800c1385  test    ebx, ebx
0x1800c1387  jz      loc_1800C164D
0x1800c138d  cmp     ebx, 1
0x1800c1390  jz      short loc_1800C13DC
0x1800c1392  cmp     dword ptr [rdi], 3
0x1800c1395  jnz     short loc_1800C13DC
0x1800c1397  mov     r9, r15; struct tagSAFEARRAY **
0x1800c139a  mov     r8d, ebx; int
0x1800c139d  mov     rdx, rdi; int *
0x1800c13a0  mov     rcx, rsi; struct IRawElementProviderFragment *
0x1800c13a3  call    ?ProviderGetRuntimeIdFromPartial@UiaNode@@SAJPEAUIRawElementProviderFragment@@PEBHHPEAPEAUtagSAFEARRAY@@@Z; UiaNode::ProviderGetRuntimeIdFromPartial(IRawElementProviderFragment *,int const *,int,tagSAFEARRAY * *)
0x1800c13a8  mov     ebx, eax
0x1800c13aa  mov     rcx, rdi; Block
0x1800c13ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c13b2  nop
0x1800c13b3  mov     rcx, [rsp+1C0h+psa]; psa
0x1800c13b8  test    rcx, rcx
0x1800c13bb  jz      short loc_1800C13C8
0x1800c13bd  call    cs:__imp_SafeArrayDestroy
0x1800c13c3  mov     [rsp+1C0h+psa], r12
0x1800c13c8  mov     rax, [rsi]
0x1800c13cb  mov     rcx, rsi
0x1800c13ce  mov     rax, [rax+10h]
0x1800c13d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c13d7  nop
0x1800c13d8  mov     eax, ebx
0x1800c13da  jmp     short loc_1800C1419
0x1800c13dc  mov     rax, [rsp+1C0h+psa]
0x1800c13e1  mov     [r15], rax
0x1800c13e4  mov     [rsp+1C0h+psa], r12
0x1800c13e9  mov     rcx, rdi; Block
0x1800c13ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c13f1  nop
0x1800c13f2  mov     rcx, [rsp+1C0h+psa]; psa
0x1800c13f7  test    rcx, rcx
0x1800c13fa  jz      short loc_1800C1407
0x1800c13fc  call    cs:__imp_SafeArrayDestroy
0x1800c1402  mov     [rsp+1C0h+psa], r12
0x1800c1407  mov     rax, [rsi]
0x1800c140a  mov     rcx, rsi
0x1800c140d  mov     rax, [rax+10h]
0x1800c1411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1416  nop
0x1800c1417  xor     eax, eax
0x1800c1419  mov     rcx, [rbp+0C0h+var_40]
0x1800c1420  xor     rcx, rsp; StackCookie
0x1800c1423  call    __security_check_cookie
0x1800c1428  mov     rbx, [rsp+1C0h+arg_18]
0x1800c1430  add     rsp, 190h
0x1800c1437  pop     r15
0x1800c1439  pop     r14
0x1800c143b  pop     r13
0x1800c143d  pop     r12
0x1800c143f  pop     rdi
0x1800c1440  pop     rsi
0x1800c1441  pop     rbp
0x1800c1442  retn
0x1800c1443  mov     rcx, [rbp+0C8h]; this
0x1800c144a  mov     ebx, 8007000Eh
0x1800c144f  mov     r9d, ebx; char *
0x1800c1452  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c1459  mov     edx, 0A2h; void *
0x1800c145e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1463  mov     rcx, [rsp+1C0h+var_168]
0x1800c1468  test    rcx, rcx
0x1800c146b  jnz     loc_1800C158A
0x1800c1471  mov     rcx, [rbp+0C8h]; this
0x1800c1478  mov     r9d, ebx; char *
0x1800c147b  lea     r8, aOnecoreWindows_137; "onecore\\windows\\accessibletech\\uiaut"...
0x1800c1482  mov     edx, 0BD6h; void *
0x1800c1487  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c148c  xor     ecx, ecx; Block
0x1800c148e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c1493  nop
0x1800c1494  lea     rcx, [rsp+1C0h+psa]
0x1800c1499  call    ?SafeRelease@?$AutoCleanupInfo@PEAUtagSAFEARRAY@@@@SAXAEAPEAUtagSAFEARRAY@@@Z; AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(tagSAFEARRAY * &)
0x1800c149e  nop
0x1800c149f  mov     rcx, [rsi]
0x1800c14a2  mov     rax, [rcx+10h]
0x1800c14a6  mov     rcx, rsi
0x1800c14a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c14ae  nop
0x1800c14af  mov     eax, ebx
0x1800c14b1  jmp     loc_1800C1419
0x1800c14b6  jmp     loc_1800C1417
0x1800c14bb  test    rcx, rcx
0x1800c14be  jz      short loc_1800C14CB
0x1800c14c0  call    cs:__imp_SafeArrayDestroy
0x1800c14c6  mov     [rsp+1C0h+psa], r12
0x1800c14cb  mov     rax, [rsi]
0x1800c14ce  mov     rcx, rsi
0x1800c14d1  mov     rax, [rax+10h]
0x1800c14d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c14da  nop
0x1800c14db  jmp     loc_1800C1417
0x1800c14e0  add     rcx, 60h ; '`'
0x1800c14e4  lea     rdx, [rcx+rax*8]
0x1800c14e8  lea     rcx, [rsp+1C0h+plLbound]
0x1800c14ed  call    ??$com_query@VIUiaNode@@AEAV?$ComPtr@UIUnknown@@@WRL@Microsoft@@@wil@@YA?AV?$com_ptr_t@VIUiaNode@@Uerr_exception_policy@wil@@@0@AEAV?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Z; wil::com_query<IUiaNode,Microsoft::WRL::ComPtr<IUnknown> &>(Microsoft::WRL::ComPtr<IUnknown> &)
0x1800c14f2  mov     r14, qword ptr [rsp+1C0h+plLbound]
0x1800c14f7  test    r14, r14
0x1800c14fa  jz      short loc_1800C150C
0x1800c14fc  mov     rax, [r14]
0x1800c14ff  mov     rcx, r14
0x1800c1502  mov     rax, [rax+10h]
0x1800c1506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c150b  nop
0x1800c150c  test    r14, r14
0x1800c150f  jz      loc_1800C10DF
0x1800c1515  mov     rax, [r14]
0x1800c1518  mov     rdx, r15
0x1800c151b  mov     rcx, r14
0x1800c151e  mov     rax, [rax+50h]
0x1800c1522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1527  jmp     loc_1800C1419
0x1800c152c  mov     edx, 6Fh ; 'o'
  ... truncated ...
```
