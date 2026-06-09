# CIASMigrationHelper::GetStringValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,_bstr_t &)

- ea: `0x18004d11c`
- end: `0x18004d188`
- name: `?GetStringValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAV_bstr_t@@@Z`
- size: `108`
- prototype: ``
- caller_count: `14`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049500`
- `0x18004a3b0`
- `0x18004b540`
- `0x18004b6d0`
- `0x18004c610`
- `0x18004c8d0`
- `0x18004cfcc`
- `0x18004dea0`
- `0x18004e1b0`
- `0x18004e630`
- `0x18004ef90`
- `0x18004f2cc`
- `0x180052d80`
- `0x1800534b0`

## callees

- `0x18002f240`
- `0x18004724c`
- `0x180047604`
- `0x18004d11c`
- `0x18004d294`
- `0x18004d498`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18004d17a`
- `OLEAUT32!__imp_VariantClear` at `0x18004d17a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CIASMigrationHelper::GetStringValueFromNode(__int64 *a1, __int64 a2)
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
  if ( pvarg.vt == 8 )
  {
    _bstr_t::operator=(a2, pvarg.llVal);
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
0x18004d11c  push    rbx
0x18004d11e  sub     rsp, 50h
0x18004d122  mov     rbx, rdx
0x18004d125  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004d12a  lea     rdx, [rsp+58h+var_20]
0x18004d12f  mov     rcx, rax
0x18004d132  call    ?GetnodeTypedValue@IXMLDOMNode@MSXML2@@QEAA?AV_variant_t@@XZ; MSXML2::IXMLDOMNode::GetnodeTypedValue(void)
0x18004d137  nop
0x18004d138  xor     ecx, ecx
0x18004d13a  mov     word ptr [rsp+58h+pvarg], cx
0x18004d13f  mov     rdx, rax; struct tagVARIANT *
0x18004d142  lea     rcx, [rsp+58h+pvarg]; this
0x18004d147  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18004d14c  nop
0x18004d14d  lea     rcx, [rsp+58h+var_20]; this
0x18004d152  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004d157  cmp     word ptr [rsp+58h+pvarg], 8
0x18004d15d  jz      short loc_18004D166
0x18004d15f  mov     ebx, 80070057h
0x18004d164  jmp     short loc_18004D175
0x18004d166  mov     rdx, qword ptr [rsp+58h+pvarg+8]
0x18004d16b  mov     rcx, rbx
0x18004d16e  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18004d173  xor     ebx, ebx
0x18004d175  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18004d17a  call    cs:__imp_VariantClear
0x18004d180  mov     eax, ebx
0x18004d182  add     rsp, 50h
0x18004d186  pop     rbx
0x18004d187  retn
```
