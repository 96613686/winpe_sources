# HrGetTextValueFromAttribute(IXMLDOMNode *,ushort const *,ushort * *)

- ea: `0x180017a70`
- end: `0x180017c65`
- name: `?HrGetTextValueFromAttribute@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z`
- size: `501`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d5e4`
- `0x180017660`

## callees

- `0x18000db4c`
- `0x180017a70`
- `0x180038ce4`
- `0x180055010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180017abd`
- `OLEAUT32!__imp_SysAllocString` at `0x180017abd`
- `OLEAUT32!__imp_SysFreeString` at `0x180017b22`
- `OLEAUT32!__imp_SysFreeString` at `0x180017be9`
- `OLEAUT32!__imp_SysFreeString` at `0x180017b22`
- `OLEAUT32!__imp_SysFreeString` at `0x180017be9`
- `OLEAUT32!__imp_VariantInit` at `0x180017ae3`
- `OLEAUT32!__imp_VariantInit` at `0x180017ae3`

## string_xrefs

- `0x180017c12`: `HrGetTextValueFromAttribute(): Failed to get IXMLDOMElement interface`

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
0x180017a70  mov     [rsp+arg_10], rbx
0x180017a75  mov     [rsp+arg_8], rdx
0x180017a7a  push    rbp
0x180017a7b  push    rsi
0x180017a7c  push    r14
0x180017a7e  sub     rsp, 50h
0x180017a82  mov     rax, [rcx]
0x180017a85  lea     rdx, IID_IXMLDOMElement
0x180017a8c  mov     r14, r8
0x180017a8f  mov     [rsp+68h+arg_8], 0
0x180017a98  lea     r8, [rsp+68h+arg_8]
0x180017a9d  mov     rax, [rax]
0x180017aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017aa5  mov     ebx, eax
0x180017aa7  test    eax, eax
0x180017aa9  js      loc_180017BF1
0x180017aaf  lea     rcx, psz; "sendEvents"
0x180017ab6  mov     [rsp+68h+arg_0], rdi
0x180017abb  xor     esi, esi
0x180017abd  call    cs:__imp_SysAllocString
0x180017ac3  mov     rdi, rax
0x180017ac6  test    rax, rax
0x180017ac9  jz      loc_180017B96
0x180017acf  xorps   xmm0, xmm0
0x180017ad2  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180017ad7  xor     eax, eax
0x180017ad9  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x180017ade  mov     qword ptr [rsp+68h+pvarg+10h], rax
0x180017ae3  call    cs:__imp_VariantInit
0x180017ae9  mov     rcx, [rsp+68h+arg_8]
0x180017aee  lea     r8, [rsp+68h+pvarg]
0x180017af3  mov     rdx, [rcx]
0x180017af6  mov     rax, [rdx+160h]
0x180017afd  mov     rdx, rdi
0x180017b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b05  lea     rbp, WPP_GLOBAL_Control
0x180017b0c  mov     ebx, eax
0x180017b0e  test    eax, eax
0x180017b10  js      short loc_180017B62
0x180017b12  cmp     word ptr [rsp+68h+pvarg], 8
0x180017b18  jnz     short loc_180017B1F
0x180017b1a  mov     rsi, qword ptr [rsp+68h+pvarg+8]
0x180017b1f  mov     rcx, rdi; bstrString
0x180017b22  call    cs:__imp_SysFreeString
0x180017b28  mov     rcx, [rsp+68h+arg_8]
0x180017b2d  mov     rax, [rcx]
0x180017b30  mov     rax, [rax+10h]
0x180017b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b39  mov     rdi, [rsp+68h+arg_0]
0x180017b3e  test    ebx, ebx
0x180017b40  js      loc_180017BE1
0x180017b46  mov     [r14], rsi
0x180017b49  jnz     loc_180017C2E
0x180017b4f  mov     eax, ebx
0x180017b51  mov     rbx, [rsp+68h+arg_10]
0x180017b59  add     rsp, 50h
0x180017b5d  pop     r14
0x180017b5f  pop     rsi
0x180017b60  pop     rbp
0x180017b61  retn
0x180017b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b69  cmp     rcx, rbp
0x180017b6c  jz      short loc_180017B1F
0x180017b6e  test    byte ptr [rcx+1Ch], 1
0x180017b72  jz      short loc_180017B1F
0x180017b74  mov     rcx, [rcx+10h]
0x180017b78  lea     r9, aHrgettextvalue; "HrGetTextValueFromAttribute(): Failed t"...
0x180017b7f  mov     edx, 31h ; '1'
0x180017b84  mov     [rsp+68h+var_48], eax
0x180017b88  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x180017b8f  call    WPP_SF_sd
0x180017b94  jmp     short loc_180017B1F
0x180017b96  mov     ebx, 8007000Eh
0x180017b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ba2  lea     rbp, WPP_GLOBAL_Control
0x180017ba9  cmp     rcx, rbp
0x180017bac  jz      loc_180017B28
0x180017bb2  test    byte ptr [rcx+1Ch], 1
0x180017bb6  jz      loc_180017B28
0x180017bbc  mov     rcx, [rcx+10h]
0x180017bc0  lea     r9, aHrgettextvalue_0; "HrGetTextValueFromAttribute(): Failed t"...
0x180017bc7  mov     edx, 32h ; '2'
0x180017bcc  mov     [rsp+68h+var_48], ebx
0x180017bd0  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x180017bd7  call    WPP_SF_sd
0x180017bdc  jmp     loc_180017B28
0x180017be1  test    rsi, rsi
0x180017be4  jz      short loc_180017C2E
0x180017be6  mov     rcx, rsi; bstrString
0x180017be9  call    cs:__imp_SysFreeString
0x180017bef  jmp     short loc_180017C2E
0x180017bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bf8  lea     rbp, WPP_GLOBAL_Control
0x180017bff  cmp     rcx, rbp
0x180017c02  jz      loc_180017B4F
0x180017c08  test    byte ptr [rcx+1Ch], 1
0x180017c0c  jz      short loc_180017C35
0x180017c0e  mov     rcx, [rcx+10h]
0x180017c12  lea     r9, aHrgettextvalue_1; "HrGetTextValueFromAttribute(): Failed t"...
0x180017c19  mov     edx, 33h ; '3'
0x180017c1e  mov     [rsp+68h+var_48], eax
0x180017c22  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x180017c29  call    WPP_SF_sd
0x180017c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c35  cmp     rcx, rbp
0x180017c38  jz      loc_180017B4F
0x180017c3e  test    byte ptr [rcx+1Ch], 1
0x180017c42  jz      loc_180017B4F
0x180017c48  mov     rcx, [rcx+10h]
0x180017c4c  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x180017c53  mov     edx, 34h ; '4'
0x180017c58  mov     r9d, ebx
0x180017c5b  call    WPP_SF_d
0x180017c60  jmp     loc_180017B4F
```
