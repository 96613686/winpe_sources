# XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)

- ea: `0x18004e4a4`
- end: `0x18004e551`
- name: `?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z`
- size: `173`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, OLECHAR *psz, OLECHAR *, unsigned int, const struct _XC_STRING_VALUE_MAPPING *, unsigned int, struct IXMLDOMNode **)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e9e0`
- `0x18000ef6c`
- `0x180018388`
- `0x1800450b4`
- `0x1800455c4`
- `0x18004721c`
- `0x1800474a8`
- `0x180047808`
- `0x18004e46c`
- `0x18004efd0`
- `0x18004f7e0`

## callees

- `0x18000ec9c`
- `0x180010088`
- `0x18004e4a4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004e53c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004e53c`

## pseudocode

```c
__int64 __fastcall XcAddChildElementEnum(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        OLECHAR *psz,
        OLECHAR *a4,
        unsigned int a5,
        const unsigned __int16 **a6,
        unsigned int a7,
        struct IXMLDOMNode **a8)
{
  OLECHAR *v8; // rbx
  unsigned int v11; // eax
  unsigned int v14; // edi

  v8 = 0;
  a8 = 0;
  v11 = 0;
  v14 = 1206;
  while ( v11 < a7 )
  {
    if ( LODWORD(a6[2 * v11 + 1]) == a5 )
    {
      AtlAssignNoThrow((struct ATL::CComBSTR *)&a8, a6[2 * v11]);
      v8 = (OLECHAR *)a8;
      if ( a8 )
        v14 = XcAddChildElement(a1, a2, psz, a4, (OLECHAR *)a8, 0);
      else
        v14 = 14;
      break;
    }
    ++v11;
  }
  SysFreeString(v8);
  return v14;
}

```

## disassembly

```asm
0x18004e4a4  mov     rax, rsp
0x18004e4a7  push    rbx
0x18004e4a8  push    rbp
0x18004e4a9  push    rsi
0x18004e4aa  push    rdi
0x18004e4ab  push    r14
0x18004e4ad  push    r15
0x18004e4af  sub     rsp, 38h
0x18004e4b3  mov     r10, [rsp+68h+arg_28]
0x18004e4bb  xor     ebx, ebx
0x18004e4bd  mov     r11d, [rsp+68h+arg_20]
0x18004e4c5  mov     rsi, r9
0x18004e4c8  mov     [rax+40h], rbx
0x18004e4cc  mov     rbp, r8
0x18004e4cf  xor     eax, eax
0x18004e4d1  mov     r14, rdx
0x18004e4d4  mov     r15, rcx
0x18004e4d7  mov     edi, 4B6h
0x18004e4dc  cmp     eax, [rsp+68h+arg_30]
0x18004e4e3  jnb     short loc_18004E539
0x18004e4e5  mov     edx, eax
0x18004e4e7  add     rdx, rdx
0x18004e4ea  cmp     [r10+rdx*8+8], r11d
0x18004e4ef  jz      short loc_18004E4F5
0x18004e4f1  inc     eax
0x18004e4f3  jmp     short loc_18004E4DC
0x18004e4f5  mov     rdx, [r10+rdx*8]; unsigned __int16 *
0x18004e4f9  lea     rcx, [rsp+68h+arg_38]; struct ATL::CComBSTR *
0x18004e501  call    ?AtlAssignNoThrow@@YAXAEAVCComBSTR@ATL@@PEBG@Z; AtlAssignNoThrow(ATL::CComBSTR &,ushort const *)
0x18004e506  mov     rbx, [rsp+68h+arg_38]
0x18004e50e  test    rbx, rbx
0x18004e511  jnz     short loc_18004E518
0x18004e513  lea     edi, [rbx+0Eh]
0x18004e516  jmp     short loc_18004E539
0x18004e518  mov     [rsp+68h+var_40], 0; struct IXMLDOMNode **
0x18004e521  mov     r9, rsi; OLECHAR *
0x18004e524  mov     r8, rbp; psz
0x18004e527  mov     [rsp+68h+var_48], rbx; OLECHAR *
0x18004e52c  mov     rdx, r14; struct IXMLDOMNode *
0x18004e52f  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18004e532  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18004e537  mov     edi, eax
0x18004e539  mov     rcx, rbx; bstrString
0x18004e53c  call    cs:__imp_SysFreeString
0x18004e542  mov     eax, edi
0x18004e544  add     rsp, 38h
0x18004e548  pop     r15
0x18004e54a  pop     r14
0x18004e54c  pop     rdi
0x18004e54d  pop     rsi
0x18004e54e  pop     rbp
0x18004e54f  pop     rbx
0x18004e550  retn
```
