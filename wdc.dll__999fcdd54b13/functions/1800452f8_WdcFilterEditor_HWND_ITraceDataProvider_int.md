# WdcFilterEditor(HWND__ *,ITraceDataProvider *,int)

- ea: `0x1800452f8`
- end: `0x18004558a`
- name: `?WdcFilterEditor@@YAJPEAUHWND__@@PEAUITraceDataProvider@@H@Z`
- size: `658`
- prototype: `__int64 __fastcall(HWND, struct ITraceDataProvider *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800607cc`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18003b0ac`
- `0x180043304`
- `0x1800452f8`
- `0x1800464e0`
- `0x180067f7c`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18004548e`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18004548e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180045474`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180045554`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180045474`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180045554`

## pseudocode

```c
__int64 __fastcall WdcFilterEditor(HWND a1, struct ITraceDataProvider *a2, int a3)
{
  unsigned __int16 v3; // si
  const char *v7; // rdx
  int v8; // r8d
  const char *v9; // rdx
  int v10; // r8d
  int v11; // eax
  unsigned int v12; // ebx
  _BYTE *v13; // rax
  struct ITraceDataProviderVtbl *lpVtbl; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  const char *v17; // rdx
  int v18; // r8d
  SAFEARRAY *v19; // rax
  struct ITraceDataProviderVtbl *v20; // rax
  __int64 v22; // [rsp+20h] [rbp-29h]
  SAFEARRAY *psa; // [rsp+30h] [rbp-19h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-11h] BYREF
  _BYTE v25[4]; // [rsp+40h] [rbp-9h] BYREF
  BOOL v26; // [rsp+44h] [rbp-5h]
  int v27; // [rsp+48h] [rbp-1h]
  ULONG v28; // [rsp+60h] [rbp+17h]
  SIZE_T dwBytes; // [rsp+68h] [rbp+1Fh]
  void *v30; // [rsp+70h] [rbp+27h]
  _BYTE *v31; // [rsp+78h] [rbp+2Fh]
  _DWORD v32[4]; // [rsp+80h] [rbp+37h] BYREF
  __int16 v33; // [rsp+C8h] [rbp+7Fh] BYREF

  v3 = -1;
  psa = 0;
  v33 = -1;
  rgsabound = 0;
  memset_0(v25, 0, 0x50u);
  dwBytes = 0x200000000400LL;
  v30 = WdcAlloc(0x4000u, v7, v8);
  if ( !v30 )
    goto LABEL_2;
  *(_WORD *)v30 = 0;
  v13 = WdcAlloc((unsigned int)dwBytes, v9, v10);
  v31 = v13;
  if ( !v13 )
    goto LABEL_2;
  *v13 = 0;
  lpVtbl = a2->lpVtbl;
  v27 = a3;
  v11 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, _DWORD *))lpVtbl->get_FilterType)(a2, v32);
  v12 = v11;
  if ( v11 < 0 )
    goto LABEL_20;
  v11 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, SAFEARRAY **))a2->lpVtbl->get_FilterData)(a2, &psa);
  v12 = v11;
  if ( v11 < 0 )
    goto LABEL_20;
  v11 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, __int16 *))a2->lpVtbl->get_FilterEnabled)(a2, &v33);
  v12 = v11;
  if ( v11 < 0 )
    goto LABEL_20;
  v26 = v33 == -1;
  v11 = WdcForEachElement<unsigned char>(psa, (__int64 (__fastcall *)(_BYTE *))WdcFilterEditorStoreByte, 2u, v25, 1);
  v12 = v11;
  if ( v11 < 0 )
    goto LABEL_20;
  v16 = IsolationAwareDialogBoxParamW(v15, 4200, a1, WdcFilterEditorDialog, v25);
  v11 = WdcHResultFromDlg(v16);
  v12 = v11;
  if ( v11 < 0 )
    goto LABEL_20;
  if ( v11 == 1 )
  {
    v12 = 0;
    goto LABEL_21;
  }
  rgsabound.lLbound = 0;
  rgsabound.cElements = v28;
  if ( psa )
  {
    SafeArrayDestroy(psa);
    psa = 0;
  }
  v19 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  psa = v19;
  if ( !v19 )
  {
LABEL_2:
    v11 = -2147024882;
    v12 = -2147024882;
LABEL_20:
    LODWORD(v22) = v11;
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\dialogs.cpp", "WdcFilterEditor", 0, L"FAILURE: 0x%08x", v22);
    goto LABEL_21;
  }
  v11 = WdcForEachElement<unsigned char>(v19, (__int64 (__fastcall *)(_BYTE *))WdcFilterEditorStoreByte, 2u, v25, 0);
  v12 = v11;
  if ( v11 < 0 )
    goto LABEL_20;
  v11 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, _QWORD))a2->lpVtbl->put_FilterType)(a2, v32[0]);
  v12 = v11;
  if ( v11 < 0 )
    goto LABEL_20;
  v11 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, SAFEARRAY *))a2->lpVtbl->put_FilterData)(a2, psa);
  v12 = v11;
  if ( v11 < 0 )
    goto LABEL_20;
  if ( !v26 )
    v3 = 0;
  v20 = a2->lpVtbl;
  v33 = v3;
  v11 = ((__int64 (__fastcall *)(struct ITraceDataProvider *, _QWORD))v20->put_FilterEnabled)(a2, v3);
  v12 = v11;
  if ( v11 < 0 )
    goto LABEL_20;
LABEL_21:
  if ( psa )
  {
    SafeArrayDestroy(psa);
    psa = 0;
  }
  if ( v30 )
    WdcFree(v30, v17, v18);
  return v12;
}

```

## disassembly

```asm
0x1800452f8  mov     [rsp-8+arg_0], rbx
0x1800452fd  mov     [rsp-8+arg_8], rsi
0x180045302  push    rbp
0x180045303  push    rdi
0x180045304  push    r14
0x180045306  lea     rbp, [rsp-47h]
0x18004530b  sub     rsp, 90h
0x180045312  or      esi, 0FFFFFFFFh
0x180045315  mov     [rbp+57h+psa], 0
0x18004531d  mov     ebx, r8d
0x180045320  mov     [rbp+57h+arg_18], si
0x180045324  mov     rdi, rdx
0x180045327  mov     qword ptr [rbp+57h+rgsabound.cElements], 0
0x18004532f  mov     r14, rcx
0x180045332  xor     edx, edx; Val
0x180045334  lea     r8d, [rsi+51h]; Size
0x180045338  lea     rcx, [rbp+57h+var_60]; void *
0x18004533c  call    memset_0
0x180045341  mov     ecx, 4000h; dwBytes
0x180045346  mov     dword ptr [rbp+57h+dwBytes], 400h
0x18004534d  mov     dword ptr [rbp+57h+dwBytes+4], 2000h
0x180045354  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180045359  mov     [rbp+57h+var_30], rax
0x18004535d  mov     rcx, rax
0x180045360  test    rax, rax
0x180045363  jnz     short loc_180045371
0x180045365  mov     eax, 8007000Eh
0x18004536a  mov     ebx, eax
0x18004536c  jmp     loc_18004552A
0x180045371  xor     eax, eax
0x180045373  mov     [rcx], ax
0x180045376  mov     ecx, dword ptr [rbp+57h+dwBytes]; dwBytes
0x180045379  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18004537e  mov     [rbp+57h+var_28], rax
0x180045382  test    rax, rax
0x180045385  jz      short loc_180045365
0x180045387  mov     byte ptr [rax], 0
0x18004538a  lea     rdx, [rbp+57h+var_20]
0x18004538e  mov     rax, [rdi]
0x180045391  mov     rcx, rdi
0x180045394  mov     [rbp+57h+var_58], ebx
0x180045397  mov     rax, [rax+88h]
0x18004539e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453a3  mov     ebx, eax
0x1800453a5  test    eax, eax
0x1800453a7  js      loc_18004552A
0x1800453ad  mov     rax, [rdi]
0x1800453b0  lea     rdx, [rbp+57h+psa]
0x1800453b4  mov     rcx, rdi
0x1800453b7  mov     rax, [rax+98h]
0x1800453be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453c3  mov     ebx, eax
0x1800453c5  test    eax, eax
0x1800453c7  js      loc_18004552A
0x1800453cd  mov     rax, [rdi]
0x1800453d0  lea     rdx, [rbp+57h+arg_18]
0x1800453d4  mov     rcx, rdi
0x1800453d7  mov     rax, [rax+78h]
0x1800453db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453e0  mov     ebx, eax
0x1800453e2  test    eax, eax
0x1800453e4  js      loc_18004552A
0x1800453ea  mov     rcx, [rbp+57h+psa]; psa
0x1800453ee  lea     r9, [rbp+57h+var_60]
0x1800453f2  xor     eax, eax
0x1800453f4  mov     [rsp+0A0h+var_80], 1
0x1800453fd  cmp     [rbp+57h+arg_18], si
0x180045401  lea     rdx, ?WdcFilterEditorStoreByte@@YAJPEAU?$WDC_SAFEARRAY_CALL@E@@@Z; WdcFilterEditorStoreByte(WDC_SAFEARRAY_CALL<uchar> *)
0x180045408  mov     r8d, 2
0x18004540e  setz    al
0x180045411  mov     [rbp+57h+var_5C], eax
0x180045414  call    ??$WdcForEachElement@E@@YAJPEAUtagSAFEARRAY@@P6AJPEAU?$WDC_SAFEARRAY_CALL@E@@@ZKZZ; WdcForEachElement<uchar>(tagSAFEARRAY *,long (*)(WDC_SAFEARRAY_CALL<uchar> *),ulong,...)
0x180045419  mov     ebx, eax
0x18004541b  test    eax, eax
0x18004541d  js      loc_18004552A
0x180045423  lea     rax, [rbp+57h+var_60]
0x180045427  mov     r8, r14
0x18004542a  lea     r9, ?WdcFilterEditorDialog@@YA_JPEAUHWND__@@I_K_J@Z; WdcFilterEditorDialog(HWND__ *,uint,unsigned __int64,__int64)
0x180045431  mov     [rsp+0A0h+var_80], rax
0x180045436  mov     edx, 1068h
0x18004543b  call    IsolationAwareDialogBoxParamW
0x180045440  mov     rcx, rax; __int64
0x180045443  call    ?WdcHResultFromDlg@@YAJ_J@Z; WdcHResultFromDlg(__int64)
0x180045448  mov     ebx, eax
0x18004544a  test    eax, eax
0x18004544c  js      loc_18004552A
0x180045452  cmp     eax, 1
0x180045455  jnz     short loc_18004545E
0x180045457  xor     ebx, ebx
0x180045459  jmp     loc_18004554B
0x18004545e  mov     rcx, [rbp+57h+psa]; psa
0x180045462  mov     eax, [rbp+57h+var_40]
0x180045465  mov     [rbp+57h+rgsabound.lLbound], 0
0x18004546c  mov     [rbp+57h+rgsabound.cElements], eax
0x18004546f  test    rcx, rcx
0x180045472  jz      short loc_180045482
0x180045474  call    cs:__imp_SafeArrayDestroy
0x18004547a  mov     [rbp+57h+psa], 0
0x180045482  mov     ecx, 11h; vt
0x180045487  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x18004548b  lea     edx, [rcx-10h]; cDims
0x18004548e  call    cs:__imp_SafeArrayCreate
0x180045494  mov     [rbp+57h+psa], rax
0x180045498  test    rax, rax
0x18004549b  jz      loc_180045365
0x1800454a1  lea     r9, [rbp+57h+var_60]
0x1800454a5  mov     [rsp+0A0h+var_80], 0
0x1800454ae  mov     r8d, 2
0x1800454b4  lea     rdx, ?WdcFilterEditorStoreByte@@YAJPEAU?$WDC_SAFEARRAY_CALL@E@@@Z; WdcFilterEditorStoreByte(WDC_SAFEARRAY_CALL<uchar> *)
0x1800454bb  mov     rcx, rax; psa
0x1800454be  call    ??$WdcForEachElement@E@@YAJPEAUtagSAFEARRAY@@P6AJPEAU?$WDC_SAFEARRAY_CALL@E@@@ZKZZ; WdcForEachElement<uchar>(tagSAFEARRAY *,long (*)(WDC_SAFEARRAY_CALL<uchar> *),ulong,...)
0x1800454c3  mov     ebx, eax
0x1800454c5  test    eax, eax
0x1800454c7  js      short loc_18004552A
0x1800454c9  mov     rax, [rdi]
0x1800454cc  mov     rcx, rdi
0x1800454cf  mov     edx, [rbp+57h+var_20]
0x1800454d2  mov     rax, [rax+90h]
0x1800454d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454de  mov     ebx, eax
0x1800454e0  test    eax, eax
0x1800454e2  js      short loc_18004552A
0x1800454e4  mov     rax, [rdi]
0x1800454e7  mov     rcx, rdi
0x1800454ea  mov     rdx, [rbp+57h+psa]
0x1800454ee  mov     rax, [rax+0A0h]
0x1800454f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454fa  mov     ebx, eax
0x1800454fc  test    eax, eax
0x1800454fe  js      short loc_18004552A
0x180045500  cmp     [rbp+57h+var_5C], 0
0x180045504  jnz     short loc_18004550B
0x180045506  xor     eax, eax
0x180045508  movzx   esi, ax
0x18004550b  mov     rax, [rdi]
0x18004550e  movzx   edx, si
0x180045511  mov     rcx, rdi
0x180045514  mov     [rbp+57h+arg_18], si
0x180045518  mov     rax, [rax+80h]
0x18004551f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045524  mov     ebx, eax
0x180045526  test    eax, eax
0x180045528  jns     short loc_18004554B
0x18004552a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180045531  mov     dword ptr [rsp+0A0h+var_80], eax
0x180045535  xor     r8d, r8d; int
0x180045538  lea     rdx, aWdcfilteredito_6; "WdcFilterEditor"
0x18004553f  lea     rcx, aBaseDiagnosisP_28; "base\\diagnosis\\pdui\\perfmon\\mmc\\di"...
0x180045546  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18004554b  mov     rcx, [rbp+57h+psa]; psa
0x18004554f  test    rcx, rcx
0x180045552  jz      short loc_180045562
0x180045554  call    cs:__imp_SafeArrayDestroy
0x18004555a  mov     [rbp+57h+psa], 0
0x180045562  mov     rcx, [rbp+57h+var_30]; void *
0x180045566  test    rcx, rcx
0x180045569  jz      short loc_180045570
0x18004556b  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180045570  lea     r11, [rsp+0A0h+var_10]
0x180045578  mov     eax, ebx
0x18004557a  mov     rbx, [r11+20h]
0x18004557e  mov     rsi, [r11+28h]
0x180045582  mov     rsp, r11
0x180045585  pop     r14
0x180045587  pop     rdi
0x180045588  pop     rbp
0x180045589  retn
```
