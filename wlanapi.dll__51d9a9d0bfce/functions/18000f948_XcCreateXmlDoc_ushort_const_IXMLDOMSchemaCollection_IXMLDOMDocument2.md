# XcCreateXmlDoc(ushort const *,IXMLDOMSchemaCollection *,IXMLDOMDocument2 * *)

- ea: `0x18000f948`
- end: `0x18000fb60`
- name: `?XcCreateXmlDoc@@YAKPEBGPEAUIXMLDOMSchemaCollection@@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `536`
- prototype: `unsigned int __fastcall(OLECHAR *psz, struct IXMLDOMSchemaCollection *, struct IXMLDOMDocument2 **)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f390`
- `0x18000f450`
- `0x18004bd7c`
- `0x18004e7d4`
- `0x18004ec20`

## callees

- `0x180009654`
- `0x18000f948`
- `0x180010088`
- `0x1800100d8`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f9ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f9ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fb31`
- `OLEAUT32!__imp_SysFreeString` at `0x18000fb31`
- `OLEAUT32!__imp_VariantInit` at `0x18000f981`
- `OLEAUT32!__imp_VariantInit` at `0x18000f98b`
- `OLEAUT32!__imp_VariantInit` at `0x18000f981`
- `OLEAUT32!__imp_VariantInit` at `0x18000f98b`
- `OLEAUT32!__imp_VariantClear` at `0x18000faa5`
- `OLEAUT32!__imp_VariantClear` at `0x18000fb1e`
- `OLEAUT32!__imp_VariantClear` at `0x18000fb28`
- `OLEAUT32!__imp_VariantClear` at `0x18000faa5`
- `OLEAUT32!__imp_VariantClear` at `0x18000fb1e`
- `OLEAUT32!__imp_VariantClear` at `0x18000fb28`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XcCreateXmlDoc(OLECHAR *psz, struct IXMLDOMSchemaCollection *a2, struct IXMLDOMDocument2 **a3)
{
  OLECHAR *v6; // rbx
  HRESULT v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  struct IXMLDOMDocument2 *v12; // rcx
  OLECHAR *v14; // [rsp+30h] [rbp-29h] BYREF
  VARIANTARG v15; // [rsp+38h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-9h] BYREF
  VARIANTARG v17; // [rsp+70h] [rbp+17h] BYREF
  LPVOID ppv; // [rsp+D8h] [rbp+7Fh] BYREF

  ppv = 0;
  v6 = 0;
  v14 = 0;
  VariantInit(&pvarg);
  VariantInit(&v15);
  v7 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, &ppv);
  v8 = v7;
  if ( v7 >= 0 )
    goto LABEL_5;
  if ( (v7 & 0x1FFF0000) == 0x70000 )
    v8 = (unsigned __int16)v7;
  if ( !v8 )
  {
LABEL_5:
    v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( (v9 & 0x1FFF0000) == 0x70000 )
        v8 = (unsigned __int16)v9;
      if ( v8 )
        goto LABEL_26;
    }
    else
    {
      v8 = 0;
    }
    if ( psz )
    {
      AtlAssignNoThrow((struct ATL::CComBSTR *)&v14, L"SelectionNamespaces");
      AtlAssignNoThrow((struct ATL::CComVariant *)&pvarg, psz);
      v8 = 8;
      v6 = v14;
      if ( !v14 || pvarg.vt != 8 || !pvarg.llVal )
        goto LABEL_26;
      v17 = pvarg;
      v10 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)ppv + 640LL))(ppv, v14, &v17);
      v8 = v10;
      if ( v10 < 0 )
      {
        if ( (v10 & 0x1FFF0000) == 0x70000 )
          v8 = (unsigned __int16)v10;
        if ( v8 )
          goto LABEL_26;
      }
      else
      {
        v8 = 0;
      }
    }
    if ( !a2 )
    {
LABEL_25:
      v12 = (struct IXMLDOMDocument2 *)ppv;
      ppv = 0;
      *a3 = v12;
      goto LABEL_26;
    }
    VariantClear(&v15);
    v15.vt = 9;
    v15.llVal = (LONGLONG)a2;
    ((void (__fastcall *)(struct IXMLDOMSchemaCollection *))a2->lpVtbl->AddRef)(a2);
    v17 = v15;
    v11 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *))(*(_QWORD *)ppv + 624LL))(ppv, &v17);
    v8 = v11;
    if ( v11 >= 0 )
    {
      v8 = 0;
      goto LABEL_25;
    }
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      v8 = (unsigned __int16)v11;
    if ( !v8 )
      goto LABEL_25;
  }
LABEL_26:
  VariantClear(&v15);
  VariantClear(&pvarg);
  SysFreeString(v6);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x18000f948  mov     [rsp-8+arg_0], rbx
0x18000f94d  mov     [rsp-8+arg_8], rsi
0x18000f952  push    rbp
0x18000f953  push    rdi
0x18000f954  push    r13
0x18000f956  push    r14
0x18000f958  push    r15
0x18000f95a  lea     rbp, [rsp-37h]
0x18000f95f  sub     rsp, 90h
0x18000f966  mov     r15, r8
0x18000f969  mov     r14, rdx
0x18000f96c  mov     rsi, rcx
0x18000f96f  mov     [rbp+57h+arg_18], 0
0x18000f977  xor     ebx, ebx
0x18000f979  mov     [rbp+57h+var_80], rbx
0x18000f97d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000f981  call    cs:__imp_VariantInit
0x18000f987  lea     rcx, [rbp+57h+var_78]; pvarg
0x18000f98b  call    cs:__imp_VariantInit
0x18000f991  lea     rax, [rbp+57h+arg_18]
0x18000f995  mov     [rsp+0B0h+ppv], rax; ppv
0x18000f99a  lea     r9, IID_IXMLDOMDocument2; riid
0x18000f9a1  xor     edx, edx; pUnkOuter
0x18000f9a3  lea     r8d, [rbx+1]; dwClsContext
0x18000f9a7  lea     rcx, CLSID_DOMDocument60; rclsid
0x18000f9ae  call    cs:__imp_CoCreateInstance
0x18000f9b4  mov     edi, eax
0x18000f9b6  mov     r13d, 1FFF0000h
0x18000f9bc  test    eax, eax
0x18000f9be  jns     short loc_18000F9D5
0x18000f9c0  and     eax, r13d
0x18000f9c3  cmp     eax, 70000h
0x18000f9c8  jnz     short loc_18000F9CD
0x18000f9ca  movzx   edi, di
0x18000f9cd  test    edi, edi
0x18000f9cf  jnz     loc_18000FB1A
0x18000f9d5  mov     rcx, [rbp+57h+arg_18]
0x18000f9d9  mov     rax, [rcx]
0x18000f9dc  xor     edx, edx
0x18000f9de  mov     rax, [rax+1F8h]
0x18000f9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9ea  mov     edi, eax
0x18000f9ec  test    eax, eax
0x18000f9ee  js      short loc_18000F9F4
0x18000f9f0  xor     edi, edi
0x18000f9f2  jmp     short loc_18000FA09
0x18000f9f4  and     eax, r13d
0x18000f9f7  cmp     eax, 70000h
0x18000f9fc  jnz     short loc_18000FA01
0x18000f9fe  movzx   edi, di
0x18000fa01  test    edi, edi
0x18000fa03  jnz     loc_18000FB1A
0x18000fa09  test    rsi, rsi
0x18000fa0c  jz      loc_18000FA9C
0x18000fa12  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18000fa19  lea     rcx, [rbp+57h+var_80]; struct ATL::CComBSTR *
0x18000fa1d  call    ?AtlAssignNoThrow@@YAXAEAVCComBSTR@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComBSTR &,ushort const *)
0x18000fa22  mov     rdx, rsi; psz
0x18000fa25  lea     rcx, [rbp+57h+pvarg]; Destination
0x18000fa29  call    ?AtlAssignNoThrow@@YAXAEAVCComVariant@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComVariant &,ushort const *)
0x18000fa2e  mov     edi, 8
0x18000fa33  mov     rbx, [rbp+57h+var_80]
0x18000fa37  test    rbx, rbx
0x18000fa3a  jz      loc_18000FB1A
0x18000fa40  cmp     word ptr [rbp+57h+pvarg], di
0x18000fa44  jnz     loc_18000FB1A
0x18000fa4a  cmp     qword ptr [rbp+57h+pvarg+8], 0
0x18000fa4f  jz      loc_18000FB1A
0x18000fa55  mov     rcx, [rbp+57h+arg_18]
0x18000fa59  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18000fa5d  movaps  [rbp+57h+var_40], xmm0
0x18000fa61  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18000fa66  movsd   [rbp+57h+var_30], xmm1
0x18000fa6b  mov     rax, [rcx]
0x18000fa6e  lea     r8, [rbp+57h+var_40]
0x18000fa72  mov     rdx, rbx
0x18000fa75  mov     rax, [rax+280h]
0x18000fa7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa81  mov     edi, eax
0x18000fa83  test    eax, eax
0x18000fa85  js      short loc_18000FA8B
0x18000fa87  xor     edi, edi
0x18000fa89  jmp     short loc_18000FA9C
0x18000fa8b  and     eax, r13d
0x18000fa8e  cmp     eax, 70000h
0x18000fa93  jnz     short loc_18000FA98
0x18000fa95  movzx   edi, di
0x18000fa98  test    edi, edi
0x18000fa9a  jnz     short loc_18000FB1A
0x18000fa9c  test    r14, r14
0x18000fa9f  jz      short loc_18000FB0B
0x18000faa1  lea     rcx, [rbp+57h+var_78]; pvarg
0x18000faa5  call    cs:__imp_VariantClear
0x18000faab  mov     eax, 9
0x18000fab0  mov     word ptr [rbp+57h+var_78], ax
0x18000fab4  mov     qword ptr [rbp+57h+var_78+8], r14
0x18000fab8  mov     rax, [r14]
0x18000fabb  mov     rcx, r14
0x18000fabe  mov     rax, [rax+8]
0x18000fac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fac7  mov     rcx, [rbp+57h+arg_18]
0x18000facb  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x18000facf  movaps  [rbp+57h+var_40], xmm0
0x18000fad3  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x18000fad8  movsd   [rbp+57h+var_30], xmm1
0x18000fadd  mov     rax, [rcx]
0x18000fae0  lea     rdx, [rbp+57h+var_40]
0x18000fae4  mov     rax, [rax+270h]
0x18000faeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faf0  mov     edi, eax
0x18000faf2  test    eax, eax
0x18000faf4  js      short loc_18000FAFA
0x18000faf6  xor     edi, edi
0x18000faf8  jmp     short loc_18000FB0B
0x18000fafa  and     eax, r13d
0x18000fafd  cmp     eax, 70000h
0x18000fb02  jnz     short loc_18000FB07
0x18000fb04  movzx   edi, di
0x18000fb07  test    edi, edi
0x18000fb09  jnz     short loc_18000FB1A
0x18000fb0b  mov     rcx, [rbp+57h+arg_18]
0x18000fb0f  mov     [rbp+57h+arg_18], 0
0x18000fb17  mov     [r15], rcx
0x18000fb1a  lea     rcx, [rbp+57h+var_78]; pvarg
0x18000fb1e  call    cs:__imp_VariantClear
0x18000fb24  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000fb28  call    cs:__imp_VariantClear
0x18000fb2e  mov     rcx, rbx; bstrString
0x18000fb31  call    cs:__imp_SysFreeString
0x18000fb37  nop
0x18000fb38  lea     rcx, [rbp+57h+arg_18]
0x18000fb3c  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000fb41  nop
0x18000fb42  mov     eax, edi
0x18000fb44  lea     r11, [rsp+0B0h+var_20]
0x18000fb4c  mov     rbx, [r11+30h]
0x18000fb50  mov     rsi, [r11+38h]
0x18000fb54  mov     rsp, r11
0x18000fb57  pop     r15
0x18000fb59  pop     r14
0x18000fb5b  pop     r13
0x18000fb5d  pop     rdi
0x18000fb5e  pop     rbp
0x18000fb5f  retn
```
