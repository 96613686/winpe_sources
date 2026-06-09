# WdcXmlGetTableSetting(IXMLDOMElement *,ulong,_WDC_TABLE_SETTING *)

- ea: `0x18001d7fc`
- end: `0x18001dca1`
- name: `?WdcXmlGetTableSetting@@YAJPEAUIXMLDOMElement@@KPEAU_WDC_TABLE_SETTING@@@Z`
- size: `1189`
- prototype: `__int64 __fastcall(struct IXMLDOMElement *, unsigned int, struct _WDC_TABLE_SETTING *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180073a60`

## callees

- `0x18000b854`
- `0x18001d7fc`
- `0x18001dca8`
- `0x18001de00`
- `0x18001df40`
- `0x18001e9a0`
- `0x180023bb0`
- `0x18003a3c0`
- `0x180073ef4`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001d8a4`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d9b0`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d8a4`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d9b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001da11`
- `OLEAUT32!__imp_SysFreeString` at `0x18001db5a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001db68`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dbf6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001da11`
- `OLEAUT32!__imp_SysFreeString` at `0x18001db5a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001db68`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dbf6`
- `OLEAUT32!__imp_VariantInit` at `0x18001db9b`
- `OLEAUT32!__imp_VariantInit` at `0x18001db9b`

## string_xrefs

- `0x18001d9f1`: `WdcXmlGetAttribute`
- `0x18001dbca`: `WdcXmlGetAttribute`
- `0x18001d959`: `WdcXmlNodeToElement`

## pseudocode

```c
__int64 __fastcall WdcXmlGetTableSetting(struct IXMLDOMElement *a1, unsigned int a2, struct _WDC_TABLE_SETTING *a3)
{
  unsigned int v4; // esi
  unsigned __int16 *bstrVal; // rbx
  unsigned int v7; // r15d
  BSTR v8; // rax
  OLECHAR *v9; // r14
  _QWORD *v10; // rsi
  unsigned int v11; // r14d
  __int64 (__fastcall **v12)(_QWORD *, GUID *, struct IXMLDOMElement **); // rax
  int v13; // eax
  struct IXMLDOMElement *v14; // rsi
  OLECHAR *v15; // r15
  int Attribute; // eax
  int v18; // eax
  int v19; // esi
  unsigned int v20; // esi
  int v21; // eax
  int v22; // eax
  struct IXMLDOMElement *v23; // rcx
  __int64 v24; // [rsp+20h] [rbp-99h]
  __int64 v25; // [rsp+20h] [rbp-99h]
  bool v26[4]; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v27; // [rsp+34h] [rbp-85h]
  unsigned int v28; // [rsp+38h] [rbp-81h] BYREF
  struct IXMLDOMElement *v29; // [rsp+40h] [rbp-79h] BYREF
  int v30; // [rsp+48h] [rbp-71h] BYREF
  _QWORD *v31; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v32; // [rsp+58h] [rbp-61h]
  int v33; // [rsp+5Ch] [rbp-5Dh] BYREF
  __int64 v34; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int16 *v35; // [rsp+68h] [rbp-51h] BYREF
  OLECHAR *v36; // [rsp+70h] [rbp-49h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-41h] BYREF
  int v38[16]; // [rsp+90h] [rbp-29h] BYREF

  v32 = a2;
  v26[0] = 0;
  v4 = a2;
  v30 = 0;
  bstrVal = 0;
  v34 = 0;
  v35 = 0;
  v31 = 0;
  v29 = 0;
  v28 = 0;
  v7 = 0;
  v27 = 0;
  if ( WdcXmlGetAttribute(a1, L"hidden", v26) >= 0 )
    *(_DWORD *)a3 = v26[0];
  if ( WdcXmlGetAttribute(a1, L"height", &v30) >= 0 && (unsigned int)v30 <= 0x7D0 )
    *((_DWORD *)a3 + 1) = v30;
  v8 = SysAllocString(L"column");
  v36 = v8;
  v9 = v8;
  if ( !v8 )
  {
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
      "WdcAssignString",
      0,
      L"FAILURE: 0x%08x",
      -2147024882);
    v9 = 0;
    goto LABEL_27;
  }
  if ( ((int (__fastcall *)(struct IXMLDOMElement *, BSTR, __int64 *))a1->lpVtbl->selectNodes)(a1, v8, &v34) >= 0 )
  {
    (*(void (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v34 + 72LL))(v34, &v31);
    v10 = v31;
    if ( !v31 )
      goto LABEL_26;
    v11 = v32;
    while ( 1 )
    {
      v12 = (__int64 (__fastcall **)(_QWORD *, GUID *, struct IXMLDOMElement **))*v10;
      v33 = 0;
      v13 = ((__int64 (__fastcall *)(_QWORD *, int *))v12[10])(v10, &v33);
      if ( v13 < 0 )
        goto LABEL_12;
      if ( v33 != 1 )
        goto LABEL_18;
      v13 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IXMLDOMElement **))*v10)(
              v10,
              &GUID_2933bf86_7b36_11d2_b20e_00c04f983e60,
              &v29);
      if ( v13 < 0 )
      {
LABEL_12:
        LODWORD(v24) = v13;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
          "WdcXmlNodeToElement",
          0,
          L"FAILURE: 0x%08x",
          v24);
      }
      else
      {
        v14 = v29;
        memset(&pvarg, 0, sizeof(pvarg));
        v15 = SysAllocString(L"id");
        if ( v15 )
        {
          VariantInit(&pvarg);
          v18 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, OLECHAR *, VARIANTARG *))v14->lpVtbl->getAttribute)(
                  v14,
                  v15,
                  &pvarg);
          v19 = v18;
          if ( v18 >= 0 )
          {
            if ( v18 == 1 )
            {
              v19 = -2147467259;
            }
            else
            {
              bstrVal = pvarg.bstrVal;
              v35 = pvarg.bstrVal;
            }
          }
          else
          {
            LODWORD(v24) = v18;
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
              "WdcXmlGetAttribute",
              0,
              L"FAILURE: 0x%08x",
              v24);
          }
          SysFreeString(v15);
          if ( v19 >= 0 && (int)WdcXmlIdToColumnIndex(bstrVal, v11, &v28) >= 0 )
          {
            v26[0] = 0;
            WdcXmlGetAttribute(v29, L"hidden", v26);
            v20 = v28;
            v21 = 1 << v28;
            if ( v26[0] )
              v22 = *((_DWORD *)a3 + 2) & ~v21;
            else
              v22 = *((_DWORD *)a3 + 2) | v21;
            v23 = v29;
            *((_DWORD *)a3 + 2) = v22;
            if ( WdcXmlGetAttribute(v23, L"width", &v30) >= 0 && (unsigned int)v30 <= 0x7D0 )
              *((_DWORD *)a3 + v20 + 3) = v30;
            v7 = v27;
            if ( v27 < 0x10 )
            {
              v38[v27] = v20;
              v27 = ++v7;
            }
            goto LABEL_18;
          }
        }
        else
        {
          LODWORD(v24) = -2147024882;
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
            "WdcAssignString",
            0,
            L"FAILURE: 0x%08x",
            v24);
          LODWORD(v25) = -2147024882;
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mon\\setting.cpp",
            "WdcXmlGetAttribute",
            0,
            L"FAILURE: 0x%08x",
            v25);
        }
        v7 = v27;
      }
LABEL_18:
      if ( bstrVal )
      {
        SysFreeString(bstrVal);
        bstrVal = 0;
        v35 = 0;
      }
      if ( v29 )
      {
        ((void (__fastcall *)(struct IXMLDOMElement *))v29->lpVtbl->Release)(v29);
        v29 = 0;
      }
      if ( v31 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
        v31 = 0;
      }
      (*(void (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v34 + 72LL))(v34, &v31);
      v10 = v31;
      if ( !v31 )
      {
        v9 = v36;
LABEL_26:
        v4 = v32;
        break;
      }
    }
  }
LABEL_27:
  WdcReconcileColumnOrder((int *const)a3 + 19, v38, v7);
  if ( WdcXmlOpenElement((struct IXMLDOMNode *)a1, L"sort", &v29) >= 0 )
  {
    Attribute = WdcXmlGetAttribute(v29, L"column", &v35);
    bstrVal = v35;
    if ( Attribute >= 0 && (int)WdcXmlIdToColumnIndex(v35, v4, &v28) >= 0 )
      *((_DWORD *)a3 + 35) = v28;
    v26[0] = 0;
    WdcXmlGetAttribute(v29, L"descending", v26);
    *((_DWORD *)a3 + 36) = v26[0];
  }
  if ( v29 )
  {
    ((void (__fastcall *)(struct IXMLDOMElement *))v29->lpVtbl->Release)(v29);
    v29 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v9 )
    SysFreeString(v9);
  if ( bstrVal )
    SysFreeString(bstrVal);
  return 0;
}

```

## disassembly

```asm
0x18001d7fc  mov     [rsp-8+arg_18], rbx
0x18001d801  push    rbp
0x18001d802  push    rsi
0x18001d803  push    rdi
0x18001d804  push    r12
0x18001d806  push    r13
0x18001d808  push    r14
0x18001d80a  push    r15
0x18001d80c  lea     rbp, [rsp-27h]
0x18001d811  sub     rsp, 0E0h
0x18001d818  mov     rax, cs:__security_cookie
0x18001d81f  xor     rax, rsp
0x18001d822  mov     [rbp+57h+var_40], rax
0x18001d826  xor     r12d, r12d
0x18001d829  mov     [rbp+57h+var_B8], edx
0x18001d82c  mov     rdi, r8
0x18001d82f  mov     [rsp+110h+var_E0], r12b
0x18001d834  mov     esi, edx
0x18001d836  mov     [rbp+57h+var_C8], r12d
0x18001d83a  mov     ebx, r12d
0x18001d83d  mov     [rbp+57h+var_B0], r12
0x18001d841  lea     r8, [rsp+110h+var_E0]; bool *
0x18001d846  mov     [rbp+57h+var_A8], rbx
0x18001d84a  lea     rdx, aHidden; "hidden"
0x18001d851  mov     [rbp+57h+var_C0], r12
0x18001d855  mov     r13, rcx
0x18001d858  mov     [rbp+57h+var_D0], r12
0x18001d85c  mov     [rsp+110h+var_D8], r12d
0x18001d861  mov     r15d, r12d
0x18001d864  mov     [rsp+110h+var_DC], r12d
0x18001d869  call    ?WdcXmlGetAttribute@@YAJPEAUIXMLDOMElement@@PEBGPEA_N@Z; WdcXmlGetAttribute(IXMLDOMElement *,ushort const *,bool *)
0x18001d86e  test    eax, eax
0x18001d870  js      short loc_18001D879
0x18001d872  movzx   eax, [rsp+110h+var_E0]
0x18001d877  mov     [rdi], eax
0x18001d879  lea     r8, [rbp+57h+var_C8]; int *
0x18001d87d  mov     rcx, r13; struct IXMLDOMElement *
0x18001d880  lea     rdx, aHeight; "height"
0x18001d887  call    ?WdcXmlGetAttribute@@YAJPEAUIXMLDOMElement@@PEBGPEAH@Z; WdcXmlGetAttribute(IXMLDOMElement *,ushort const *,int *)
0x18001d88c  test    eax, eax
0x18001d88e  js      short loc_18001D89D
0x18001d890  mov     eax, [rbp+57h+var_C8]
0x18001d893  cmp     eax, 7D0h
0x18001d898  ja      short loc_18001D89D
0x18001d89a  mov     [rdi+4], eax
0x18001d89d  lea     rcx, aColumn; "column"
0x18001d8a4  call    cs:__imp_SysAllocString
0x18001d8aa  mov     [rbp+57h+var_A0], rax
0x18001d8ae  mov     r14, rax
0x18001d8b1  test    rax, rax
0x18001d8b4  jnz     short loc_18001D8E3
0x18001d8b6  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18001d8bd  mov     [rsp+110h+var_F0], 8007000Eh
0x18001d8c5  xor     r8d, r8d; int
0x18001d8c8  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18001d8cf  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18001d8d6  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001d8db  mov     r14, r12
0x18001d8de  jmp     loc_18001DA82
0x18001d8e3  mov     rax, [r13+0]
0x18001d8e7  lea     r8, [rbp+57h+var_B0]
0x18001d8eb  mov     rdx, r14
0x18001d8ee  mov     rcx, r13
0x18001d8f1  mov     rax, [rax+120h]
0x18001d8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8fd  test    eax, eax
0x18001d8ff  js      loc_18001DA82
0x18001d905  mov     rcx, [rbp+57h+var_B0]
0x18001d909  lea     rdx, [rbp+57h+var_C0]
0x18001d90d  mov     rax, [rcx]
0x18001d910  mov     rax, [rax+48h]
0x18001d914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d919  mov     rsi, [rbp+57h+var_C0]
0x18001d91d  test    rsi, rsi
0x18001d920  jz      loc_18001DA7F
0x18001d926  mov     r14d, [rbp+57h+var_B8]
0x18001d92a  lea     r12, aFailure0x08x; "FAILURE: 0x%08x"
0x18001d931  mov     rax, [rsi]
0x18001d934  lea     rdx, [rbp+57h+var_B4]
0x18001d938  mov     rcx, rsi
0x18001d93b  mov     [rbp+57h+var_B4], 0
0x18001d942  mov     rax, [rax+50h]
0x18001d946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d94b  test    eax, eax
0x18001d94d  jns     short loc_18001D971
0x18001d94f  mov     r9, r12; unsigned __int16 *
0x18001d952  mov     [rsp+110h+var_F0], eax
0x18001d956  xor     r8d, r8d; int
0x18001d959  lea     rdx, aWdcxmlnodetoel; "WdcXmlNodeToElement"
0x18001d960  lea     rcx, aBaseDiagnosisP_7; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18001d967  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001d96c  jmp     loc_18001DA09
0x18001d971  cmp     [rbp+57h+var_B4], 1
0x18001d975  jnz     loc_18001DA09
0x18001d97b  mov     rax, [rsi]
0x18001d97e  lea     r8, [rbp+57h+var_D0]
0x18001d982  lea     rdx, _GUID_2933bf86_7b36_11d2_b20e_00c04f983e60
0x18001d989  mov     rcx, rsi
0x18001d98c  mov     rax, [rax]
0x18001d98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d994  test    eax, eax
0x18001d996  js      short loc_18001D94F
0x18001d998  mov     rsi, [rbp+57h+var_D0]
0x18001d99c  lea     rcx, aId; "id"
0x18001d9a3  xorps   xmm0, xmm0
0x18001d9a6  xor     eax, eax
0x18001d9a8  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001d9ac  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001d9b0  call    cs:__imp_SysAllocString
0x18001d9b6  mov     r15, rax
0x18001d9b9  test    rax, rax
0x18001d9bc  jnz     loc_18001DB97
0x18001d9c2  mov     r9, r12; unsigned __int16 *
0x18001d9c5  mov     [rsp+110h+var_F0], 8007000Eh
0x18001d9cd  xor     r8d, r8d; int
0x18001d9d0  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18001d9d7  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18001d9de  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001d9e3  mov     r9, r12; unsigned __int16 *
0x18001d9e6  mov     [rsp+110h+var_F0], 8007000Eh
0x18001d9ee  xor     r8d, r8d; int
0x18001d9f1  lea     rdx, aWdcxmlgetattri; "WdcXmlGetAttribute"
0x18001d9f8  lea     rcx, aBaseDiagnosisP_7; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18001d9ff  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001da04  mov     r15d, [rsp+110h+var_DC]
0x18001da09  test    rbx, rbx
0x18001da0c  jz      short loc_18001DA1D
0x18001da0e  mov     rcx, rbx; bstrString
0x18001da11  call    cs:__imp_SysFreeString
0x18001da17  xor     ebx, ebx
0x18001da19  mov     [rbp+57h+var_A8], rbx
0x18001da1d  mov     rcx, [rbp+57h+var_D0]
0x18001da21  test    rcx, rcx
0x18001da24  jz      short loc_18001DA3A
0x18001da26  mov     rax, [rcx]
0x18001da29  mov     rax, [rax+10h]
0x18001da2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da32  mov     [rbp+57h+var_D0], 0
0x18001da3a  mov     rcx, [rbp+57h+var_C0]
0x18001da3e  test    rcx, rcx
0x18001da41  jz      short loc_18001DA57
0x18001da43  mov     rax, [rcx]
0x18001da46  mov     rax, [rax+10h]
0x18001da4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da4f  mov     [rbp+57h+var_C0], 0
0x18001da57  mov     rcx, [rbp+57h+var_B0]
0x18001da5b  lea     rdx, [rbp+57h+var_C0]
0x18001da5f  mov     rax, [rcx]
0x18001da62  mov     rax, [rax+48h]
0x18001da66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da6b  mov     rsi, [rbp+57h+var_C0]
0x18001da6f  test    rsi, rsi
0x18001da72  jnz     loc_18001D931
0x18001da78  mov     r14, [rbp+57h+var_A0]
0x18001da7c  xor     r12d, r12d
0x18001da7f  mov     esi, [rbp+57h+var_B8]
0x18001da82  lea     rcx, [rdi+4Ch]; int *
0x18001da86  mov     r8d, r15d; unsigned int
0x18001da89  lea     rdx, [rbp+57h+var_80]; int *
0x18001da8d  call    ?WdcReconcileColumnOrder@@YAJQEAH0K@Z; WdcReconcileColumnOrder(int * const,int * const,ulong)
0x18001da92  lea     r8, [rbp+57h+var_D0]; struct IXMLDOMElement **
0x18001da96  mov     rcx, r13; struct IXMLDOMNode *
0x18001da99  lea     rdx, aSort; "sort"
0x18001daa0  call    ?WdcXmlOpenElement@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@@Z; WdcXmlOpenElement(IXMLDOMNode *,ushort const *,IXMLDOMElement * *)
0x18001daa5  test    eax, eax
0x18001daa7  js      short loc_18001DB07
0x18001daa9  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMElement *
0x18001daad  lea     r8, [rbp+57h+var_A8]; unsigned __int16 **
0x18001dab1  lea     rdx, aColumn; "column"
0x18001dab8  call    ?WdcXmlGetAttribute@@YAJPEAUIXMLDOMElement@@PEBGPEAPEAG@Z; WdcXmlGetAttribute(IXMLDOMElement *,ushort const *,ushort * *)
0x18001dabd  mov     rbx, [rbp+57h+var_A8]
0x18001dac1  test    eax, eax
0x18001dac3  js      short loc_18001DAE2
0x18001dac5  lea     r8, [rsp+110h+var_D8]; unsigned int *
0x18001daca  mov     edx, esi; unsigned int
0x18001dacc  mov     rcx, rbx; unsigned __int16 *
0x18001dacf  call    ?WdcXmlIdToColumnIndex@@YAJPEBGKPEAK@Z; WdcXmlIdToColumnIndex(ushort const *,ulong,ulong *)
0x18001dad4  test    eax, eax
0x18001dad6  js      short loc_18001DAE2
0x18001dad8  mov     eax, [rsp+110h+var_D8]
0x18001dadc  mov     [rdi+8Ch], eax
0x18001dae2  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMElement *
0x18001dae6  lea     r8, [rsp+110h+var_E0]; bool *
0x18001daeb  lea     rdx, aDescending; "descending"
0x18001daf2  mov     [rsp+110h+var_E0], r12b
0x18001daf7  call    ?WdcXmlGetAttribute@@YAJPEAUIXMLDOMElement@@PEBGPEA_N@Z; WdcXmlGetAttribute(IXMLDOMElement *,ushort const *,bool *)
0x18001dafc  movzx   eax, [rsp+110h+var_E0]
0x18001db01  mov     [rdi+90h], eax
0x18001db07  mov     rcx, [rbp+57h+var_D0]
0x18001db0b  test    rcx, rcx
0x18001db0e  jz      short loc_18001DB20
0x18001db10  mov     rax, [rcx]
0x18001db13  mov     rax, [rax+10h]
0x18001db17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db1c  mov     [rbp+57h+var_D0], r12
0x18001db20  mov     rcx, [rbp+57h+var_C0]
0x18001db24  test    rcx, rcx
0x18001db27  jz      short loc_18001DB39
0x18001db29  mov     rax, [rcx]
0x18001db2c  mov     rax, [rax+10h]
0x18001db30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db35  mov     [rbp+57h+var_C0], r12
0x18001db39  mov     rcx, [rbp+57h+var_B0]
0x18001db3d  test    rcx, rcx
0x18001db40  jz      short loc_18001DB52
0x18001db42  mov     rax, [rcx]
0x18001db45  mov     rax, [rax+10h]
0x18001db49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db4e  mov     [rbp+57h+var_B0], r12
0x18001db52  test    r14, r14
0x18001db55  jz      short loc_18001DB60
0x18001db57  mov     rcx, r14; bstrString
0x18001db5a  call    cs:__imp_SysFreeString
0x18001db60  test    rbx, rbx
0x18001db63  jz      short loc_18001DB6E
0x18001db65  mov     rcx, rbx; bstrString
0x18001db68  call    cs:__imp_SysFreeString
0x18001db6e  xor     eax, eax
0x18001db70  mov     rcx, [rbp+57h+var_40]
0x18001db74  xor     rcx, rsp; StackCookie
0x18001db77  call    __security_check_cookie
0x18001db7c  mov     rbx, [rsp+110h+arg_18]
0x18001db84  add     rsp, 0E0h
0x18001db8b  pop     r15
0x18001db8d  pop     r14
0x18001db8f  pop     r13
0x18001db91  pop     r12
0x18001db93  pop     rdi
0x18001db94  pop     rsi
0x18001db95  pop     rbp
0x18001db96  retn
0x18001db97  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001db9b  call    cs:__imp_VariantInit
0x18001dba1  mov     rax, [rsi]
0x18001dba4  lea     r8, [rbp+57h+pvarg]
0x18001dba8  mov     rdx, r15
0x18001dbab  mov     rcx, rsi
0x18001dbae  mov     rax, [rax+160h]
0x18001dbb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbba  mov     esi, eax
0x18001dbbc  test    eax, eax
0x18001dbbe  jns     short loc_18001DBDF
0x18001dbc0  mov     r9, r12; unsigned __int16 *
0x18001dbc3  mov     [rsp+110h+var_F0], eax
0x18001dbc7  xor     r8d, r8d; int
0x18001dbca  lea     rdx, aWdcxmlgetattri; "WdcXmlGetAttribute"
0x18001dbd1  lea     rcx, aBaseDiagnosisP_7; "base\\diagnosis\\pdui\\perfmon\\mon\\se"...
0x18001dbd8  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18001dbdd  jmp     short loc_18001DBF3
0x18001dbdf  cmp     eax, 1
0x18001dbe2  jnz     short loc_18001DBEB
0x18001dbe4  mov     esi, 80004005h
0x18001dbe9  jmp     short loc_18001DBF3
0x18001dbeb  mov     rbx, qword ptr [rbp+57h+pvarg+8]
0x18001dbef  mov     [rbp+57h+var_A8], rbx
0x18001dbf3  mov     rcx, r15; bstrString
0x18001dbf6  call    cs:__imp_SysFreeString
0x18001dbfc  test    esi, esi
0x18001dbfe  js      loc_18001DA04
0x18001dc04  lea     r8, [rsp+110h+var_D8]; unsigned int *
0x18001dc09  mov     edx, r14d; unsigned int
0x18001dc0c  mov     rcx, rbx; unsigned __int16 *
0x18001dc0f  call    ?WdcXmlIdToColumnIndex@@YAJPEBGKPEAK@Z; WdcXmlIdToColumnIndex(ushort const *,ulong,ulong *)
0x18001dc14  test    eax, eax
0x18001dc16  js      loc_18001DA04
0x18001dc1c  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMElement *
0x18001dc20  lea     r8, [rsp+110h+var_E0]; bool *
0x18001dc25  lea     rdx, aHidden; "hidden"
0x18001dc2c  mov     [rsp+110h+var_E0], 0
0x18001dc31  call    ?WdcXmlGetAttribute@@YAJPEAUIXMLDOMElement@@PEBGPEA_N@Z; WdcXmlGetAttribute(IXMLDOMElement *,ushort const *,bool *)
0x18001dc36  mov     esi, [rsp+110h+var_D8]
0x18001dc3a  mov     eax, 1
0x18001dc3f  mov     ecx, esi
0x18001dc41  shl     eax, cl
0x18001dc43  cmp     [rsp+110h+var_E0], 0
0x18001dc48  jz      short loc_18001DC51
0x18001dc4a  not     eax
0x18001dc4c  and     eax, [rdi+8]
0x18001dc4f  jmp     short loc_18001DC54
0x18001dc51  or      eax, [rdi+8]
0x18001dc54  mov     rcx, [rbp+57h+var_D0]; struct IXMLDOMElement *
0x18001dc58  lea     r8, [rbp+57h+var_C8]; int *
0x18001dc5c  lea     rdx, aWidth; "width"
0x18001dc63  mov     [rdi+8], eax
0x18001dc66  call    ?WdcXmlGetAttribute@@YAJPEAUIXMLDOMElement@@PEBGPEAH@Z; WdcXmlGetAttribute(IXMLDOMElement *,ushort const *,int *)
0x18001dc6b  test    eax, eax
0x18001dc6d  js      short loc_18001DC80
0x18001dc6f  mov     ecx, [rbp+57h+var_C8]
0x18001dc72  cmp     ecx, 7D0h
0x18001dc78  ja      short loc_18001DC80
0x18001dc7a  mov     eax, esi
0x18001dc7c  mov     [rdi+rax*4+0Ch], ecx
0x18001dc80  mov     r15d, [rsp+110h+var_DC]
0x18001dc85  cmp     r15d, 10h
0x18001dc89  jnb     loc_18001DA09
0x18001dc8f  mov     [rbp+r15*4+57h+var_80], esi
0x18001dc94  inc     r15d
0x18001dc97  mov     [rsp+110h+var_DC], r15d
0x18001dc9c  jmp     loc_18001DA09
```
