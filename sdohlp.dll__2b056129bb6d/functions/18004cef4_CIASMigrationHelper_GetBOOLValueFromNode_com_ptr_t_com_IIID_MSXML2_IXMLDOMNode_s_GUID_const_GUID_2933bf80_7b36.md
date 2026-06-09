# CIASMigrationHelper::GetBOOLValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,int &)

- ea: `0x18004cef4`
- end: `0x18004cf5a`
- name: `?GetBOOLValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAH@Z`
- size: `102`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004a3b0`
- `0x18004b300`
- `0x18004e630`
- `0x18004f2cc`

## callees

- `0x18002f240`
- `0x180047604`
- `0x18004cef4`
- `0x18004d294`
- `0x18004d498`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18004cf4c`
- `OLEAUT32!__imp_VariantClear` at `0x18004cf4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIASMigrationHelper::GetBOOLValueFromNode(__int64 *a1, _DWORD *a2)
{
  __int64 v3; // rax
  const struct tagVARIANT *v4; // rax
  unsigned int v5; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-20h] BYREF

  v3 = _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(a1);
  v4 = (const struct tagVARIANT *)MSXML2::IXMLDOMNode::GetnodeTypedValue(v3, v8);
  pvarg.vt = 0;
  ATL::CComVariant::InternalCopy(&pvarg, v4);
  _variant_t::~_variant_t((_variant_t *)v8);
  if ( pvarg.vt == 11 )
  {
    *a2 = pvarg.iVal;
    v5 = 0;
  }
  else
  {
    v5 = -2147024809;
  }
  VariantClear(&pvarg);
  return v5;
}

```

## disassembly

```asm
0x18004cef4  push    rbx
0x18004cef6  sub     rsp, 50h
0x18004cefa  mov     rbx, rdx
0x18004cefd  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004cf02  lea     rdx, [rsp+58h+var_20]
0x18004cf07  mov     rcx, rax
0x18004cf0a  call    ?GetnodeTypedValue@IXMLDOMNode@MSXML2@@QEAA?AV_variant_t@@XZ; MSXML2::IXMLDOMNode::GetnodeTypedValue(void)
0x18004cf0f  nop
0x18004cf10  xor     ecx, ecx
0x18004cf12  mov     word ptr [rsp+58h+pvarg], cx
0x18004cf17  mov     rdx, rax; struct tagVARIANT *
0x18004cf1a  lea     rcx, [rsp+58h+pvarg]; this
0x18004cf1f  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18004cf24  nop
0x18004cf25  lea     rcx, [rsp+58h+var_20]; this
0x18004cf2a  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004cf2f  cmp     word ptr [rsp+58h+pvarg], 0Bh
0x18004cf35  jz      short loc_18004CF3E
0x18004cf37  mov     ebx, 80070057h
0x18004cf3c  jmp     short loc_18004CF47
0x18004cf3e  movsx   eax, word ptr [rsp+58h+pvarg+8]
0x18004cf43  mov     [rbx], eax
0x18004cf45  xor     ebx, ebx
0x18004cf47  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18004cf4c  call    cs:__imp_VariantClear
0x18004cf52  mov     eax, ebx
0x18004cf54  add     rsp, 50h
0x18004cf58  pop     rbx
0x18004cf59  retn
```
