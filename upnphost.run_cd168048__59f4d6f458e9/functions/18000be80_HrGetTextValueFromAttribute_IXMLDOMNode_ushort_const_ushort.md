# HrGetTextValueFromAttribute(IXMLDOMNode *,ushort const *,ushort * *)

- ea: `0x18000be80`
- end: `0x18000c08e`
- name: `?HrGetTextValueFromAttribute@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z`
- size: `526`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ba1c`
- `0x18001fb78`

## callees

- `0x18000be80`
- `0x1800200f4`
- `0x18003b1cc`
- `0x180059010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000becd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000becd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf3e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c00c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf3e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c00c`
- `OLEAUT32!__imp_VariantInit` at `0x18000bef9`
- `OLEAUT32!__imp_VariantInit` at `0x18000bef9`

## string_xrefs

- `0x18000c03b`: `HrGetTextValueFromAttribute(): Failed to get IXMLDOMElement interface`

## pseudocode

```c
__int64 __fastcall HrGetTextValueFromAttribute(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v5; // eax
  unsigned int v6; // ebx
  OLECHAR *bstrVal; // rsi
  OLECHAR *v8; // rdi
  int v9; // eax
  STRSAFE_PCNZWCH v11; // rcx
  VARIANTARG pvarg; // [rsp+30h] [rbp-38h] BYREF
  const unsigned __int16 *v13; // [rsp+78h] [rbp+10h] BYREF

  v13 = a2;
  lpVtbl = a1->lpVtbl;
  v13 = 0;
  v5 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, GUID *, const unsigned __int16 **))lpVtbl->QueryInterface)(
         a1,
         &IID_IXMLDOMElement,
         &v13);
  v6 = v5;
  if ( v5 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      return v6;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_22;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
      (unsigned int)"HrGetTextValueFromAttribute(): Failed to get IXMLDOMElement interface",
      v5);
  }
  else
  {
    bstrVal = 0;
    v8 = SysAllocString(L"sendEvents");
    if ( v8 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v9 = (*(__int64 (__fastcall **)(const unsigned __int16 *, OLECHAR *, VARIANTARG *))(*(_QWORD *)v13 + 352LL))(
             v13,
             v8,
             &pvarg);
      v6 = v9;
      if ( v9 < 0 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
            (unsigned int)"HrGetTextValueFromAttribute(): Failed to get attribute value",
            v9);
      }
      else if ( pvarg.vt == 8 )
      {
        bstrVal = pvarg.bstrVal;
      }
      SysFreeString(v8);
    }
    else
    {
      v6 = -2147024882;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
          (unsigned int)"HrGetTextValueFromAttribute(): Failed to allocate attribute name BSTR",
          14);
    }
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v13 + 16LL))(v13);
    if ( (v6 & 0x80000000) != 0 )
    {
      if ( bstrVal )
        SysFreeString(bstrVal);
    }
    else
    {
      *a3 = bstrVal;
      if ( !v6 )
        return v6;
    }
  }
  v11 = WPP_GLOBAL_Control;
LABEL_22:
  if ( v11 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v11[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v11 + 2), 52, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000be80  mov     [rsp+arg_10], rbx
0x18000be85  mov     [rsp+arg_8], rdx
0x18000be8a  push    rbp
0x18000be8b  push    rsi
0x18000be8c  push    r14
0x18000be8e  sub     rsp, 50h
0x18000be92  mov     rax, [rcx]
0x18000be95  lea     rdx, IID_IXMLDOMElement
0x18000be9c  mov     r14, r8
0x18000be9f  mov     [rsp+68h+arg_8], 0
0x18000bea8  lea     r8, [rsp+68h+arg_8]
0x18000bead  mov     rax, [rax]
0x18000beb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beb5  mov     ebx, eax
0x18000beb7  test    eax, eax
0x18000beb9  js      loc_18000C01A
0x18000bebf  lea     rcx, psz; "sendEvents"
0x18000bec6  mov     [rsp+68h+arg_0], rdi
0x18000becb  xor     esi, esi
0x18000becd  call    cs:__imp_SysAllocString
0x18000bed4  nop     dword ptr [rax+rax+00h]
0x18000bed9  mov     rdi, rax
0x18000bedc  test    rax, rax
0x18000bedf  jz      loc_18000BFB9
0x18000bee5  xorps   xmm0, xmm0
0x18000bee8  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18000beed  xor     eax, eax
0x18000beef  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x18000bef4  mov     qword ptr [rsp+68h+pvarg+10h], rax
0x18000bef9  call    cs:__imp_VariantInit
0x18000bf00  nop     dword ptr [rax+rax+00h]
0x18000bf05  mov     rcx, [rsp+68h+arg_8]
0x18000bf0a  lea     r8, [rsp+68h+pvarg]
0x18000bf0f  mov     rdx, [rcx]
0x18000bf12  mov     rax, [rdx+160h]
0x18000bf19  mov     rdx, rdi
0x18000bf1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf21  lea     rbp, WPP_GLOBAL_Control
0x18000bf28  mov     ebx, eax
0x18000bf2a  test    eax, eax
0x18000bf2c  js      short loc_18000BF85
0x18000bf2e  cmp     word ptr [rsp+68h+pvarg], 8
0x18000bf34  jnz     short loc_18000BF3B
0x18000bf36  mov     rsi, qword ptr [rsp+68h+pvarg+8]
0x18000bf3b  mov     rcx, rdi; bstrString
0x18000bf3e  call    cs:__imp_SysFreeString
0x18000bf45  nop     dword ptr [rax+rax+00h]
0x18000bf4a  mov     rcx, [rsp+68h+arg_8]
0x18000bf4f  mov     rax, [rcx]
0x18000bf52  mov     rax, [rax+10h]
0x18000bf56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf5b  mov     rdi, [rsp+68h+arg_0]
0x18000bf60  test    ebx, ebx
0x18000bf62  js      loc_18000C004
0x18000bf68  mov     [r14], rsi
0x18000bf6b  jnz     loc_18000C057
0x18000bf71  mov     eax, ebx
0x18000bf73  mov     rbx, [rsp+68h+arg_10]
0x18000bf7b  add     rsp, 50h
0x18000bf7f  pop     r14
0x18000bf81  pop     rsi
0x18000bf82  pop     rbp
0x18000bf83  retn
0x18000bf85  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf8c  cmp     rcx, rbp
0x18000bf8f  jz      short loc_18000BF3B
0x18000bf91  test    byte ptr [rcx+1Ch], 1
0x18000bf95  jz      short loc_18000BF3B
0x18000bf97  mov     rcx, [rcx+10h]
0x18000bf9b  lea     r9, aHrgettextvalue; "HrGetTextValueFromAttribute(): Failed t"...
0x18000bfa2  mov     edx, 31h ; '1'
0x18000bfa7  mov     [rsp+68h+var_48], eax
0x18000bfab  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000bfb2  call    WPP_SF_sd
0x18000bfb7  jmp     short loc_18000BF3B
0x18000bfb9  mov     ebx, 8007000Eh
0x18000bfbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bfc5  lea     rbp, WPP_GLOBAL_Control
0x18000bfcc  cmp     rcx, rbp
0x18000bfcf  jz      loc_18000BF4A
0x18000bfd5  test    byte ptr [rcx+1Ch], 1
0x18000bfd9  jz      loc_18000BF4A
0x18000bfdf  mov     rcx, [rcx+10h]
0x18000bfe3  lea     r9, aHrgettextvalue_0; "HrGetTextValueFromAttribute(): Failed t"...
0x18000bfea  mov     edx, 32h ; '2'
0x18000bfef  mov     [rsp+68h+var_48], ebx
0x18000bff3  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000bffa  call    WPP_SF_sd
0x18000bfff  jmp     loc_18000BF4A
0x18000c004  test    rsi, rsi
0x18000c007  jz      short loc_18000C057
0x18000c009  mov     rcx, rsi; bstrString
0x18000c00c  call    cs:__imp_SysFreeString
0x18000c013  nop     dword ptr [rax+rax+00h]
0x18000c018  jmp     short loc_18000C057
0x18000c01a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c021  lea     rbp, WPP_GLOBAL_Control
0x18000c028  cmp     rcx, rbp
0x18000c02b  jz      loc_18000BF71
0x18000c031  test    byte ptr [rcx+1Ch], 1
0x18000c035  jz      short loc_18000C05E
0x18000c037  mov     rcx, [rcx+10h]
0x18000c03b  lea     r9, aHrgettextvalue_1; "HrGetTextValueFromAttribute(): Failed t"...
0x18000c042  mov     edx, 33h ; '3'
0x18000c047  mov     [rsp+68h+var_48], eax
0x18000c04b  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000c052  call    WPP_SF_sd
0x18000c057  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c05e  cmp     rcx, rbp
0x18000c061  jz      loc_18000BF71
0x18000c067  test    byte ptr [rcx+1Ch], 1
0x18000c06b  jz      loc_18000BF71
0x18000c071  mov     rcx, [rcx+10h]
0x18000c075  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000c07c  mov     edx, 34h ; '4'
0x18000c081  mov     r9d, ebx
0x18000c084  call    WPP_SF_d
0x18000c089  jmp     loc_18000BF71
```
