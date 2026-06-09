# CIASMigrationHelper::GetDWordValueFromNode(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>> &,ulong &)

- ea: `0x18004cf60`
- end: `0x18004cfc5`
- name: `?GetDWordValueFromNode@CIASMigrationHelper@@SAJAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@MSXML2@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEAK@Z`
- size: `101`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b420`
- `0x18004c16c`
- `0x18004f2cc`
- `0x180052d80`
- `0x1800534b0`

## callees

- `0x18002f240`
- `0x180047604`
- `0x18004cf60`
- `0x18004d294`
- `0x18004d498`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18004cfb7`
- `OLEAUT32!__imp_VariantClear` at `0x18004cfb7`

## pseudocode

```c
__int64 __fastcall CIASMigrationHelper::GetDWordValueFromNode(__int64 *a1, LONG *a2)
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
  if ( pvarg.vt == 3 )
  {
    *a2 = pvarg.lVal;
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
0x18004cf60  push    rbx
0x18004cf62  sub     rsp, 50h
0x18004cf66  mov     rbx, rdx
0x18004cf69  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument2@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x18004cf6e  lea     rdx, [rsp+58h+var_20]
0x18004cf73  mov     rcx, rax
0x18004cf76  call    ?GetnodeTypedValue@IXMLDOMNode@MSXML2@@QEAA?AV_variant_t@@XZ; MSXML2::IXMLDOMNode::GetnodeTypedValue(void)
0x18004cf7b  nop
0x18004cf7c  xor     ecx, ecx
0x18004cf7e  mov     word ptr [rsp+58h+pvarg], cx
0x18004cf83  mov     rdx, rax; struct tagVARIANT *
0x18004cf86  lea     rcx, [rsp+58h+pvarg]; this
0x18004cf8b  call    ?InternalCopy@CComVariant@ATL@@QEAAXPEBUtagVARIANT@@@Z; ATL::CComVariant::InternalCopy(tagVARIANT const *)
0x18004cf90  nop
0x18004cf91  lea     rcx, [rsp+58h+var_20]; this
0x18004cf96  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18004cf9b  cmp     word ptr [rsp+58h+pvarg], 3
0x18004cfa1  jz      short loc_18004CFAA
0x18004cfa3  mov     ebx, 80070057h
0x18004cfa8  jmp     short loc_18004CFB2
0x18004cfaa  mov     eax, dword ptr [rsp+58h+pvarg+8]
0x18004cfae  mov     [rbx], eax
0x18004cfb0  xor     ebx, ebx
0x18004cfb2  lea     rcx, [rsp+58h+pvarg]; pvarg
0x18004cfb7  call    cs:__imp_VariantClear
0x18004cfbd  mov     eax, ebx
0x18004cfbf  add     rsp, 50h
0x18004cfc3  pop     rbx
0x18004cfc4  retn
```
