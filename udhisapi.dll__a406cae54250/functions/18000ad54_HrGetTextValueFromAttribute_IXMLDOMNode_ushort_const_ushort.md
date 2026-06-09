# HrGetTextValueFromAttribute(IXMLDOMNode *,ushort const *,ushort * *)

- ea: `0x18000ad54`
- end: `0x18000af24`
- name: `?HrGetTextValueFromAttribute@@YAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z`
- size: `464`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009200`

## callees

- `0x1800024c4`
- `0x1800038ec`
- `0x18000ad54`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000ad9f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ad9f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae38`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aea2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae38`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aea2`
- `OLEAUT32!__imp_VariantInit` at `0x18000adc5`
- `OLEAUT32!__imp_VariantInit` at `0x18000adc5`

## string_xrefs

- `0x18000aec7`: `HrGetTextValueFromAttribute(): Failed to get IXMLDOMElement interface`

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
  OLECHAR *v8; // rbp
  int v9; // eax
  _QWORD *v10; // rcx
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
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
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
    v8 = SysAllocString(L"mustUnderstand");
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
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
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
  v10 = WPP_GLOBAL_Control;
LABEL_22:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
    WPP_SF_d(v10[2], 52, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000ad54  mov     r11, rsp
0x18000ad57  mov     [r11+8], rbx
0x18000ad5b  mov     [r11+18h], rbp
0x18000ad5f  mov     [r11+10h], rdx
0x18000ad63  push    rsi
0x18000ad64  push    rdi
0x18000ad65  push    r14
0x18000ad67  sub     rsp, 50h
0x18000ad6b  mov     rax, [rcx]
0x18000ad6e  lea     rdx, IID_IXMLDOMElement
0x18000ad75  mov     r14, r8
0x18000ad78  mov     qword ptr [r11+10h], 0
0x18000ad80  lea     r8, [r11+10h]
0x18000ad84  mov     rax, [rax]
0x18000ad87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad8c  mov     ebx, eax
0x18000ad8e  test    eax, eax
0x18000ad90  js      loc_18000AEAA
0x18000ad96  lea     rcx, aMustunderstand; "mustUnderstand"
0x18000ad9d  xor     esi, esi
0x18000ad9f  call    cs:__imp_SysAllocString
0x18000ada5  mov     rbp, rax
0x18000ada8  test    rax, rax
0x18000adab  jz      loc_18000AE40
0x18000adb1  xorps   xmm0, xmm0
0x18000adb4  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18000adb9  xor     eax, eax
0x18000adbb  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x18000adc0  mov     qword ptr [rsp+68h+pvarg+10h], rax
0x18000adc5  call    cs:__imp_VariantInit
0x18000adcb  mov     rcx, [rsp+68h+arg_8]
0x18000add0  lea     r8, [rsp+68h+pvarg]
0x18000add5  mov     rdx, [rcx]
0x18000add8  mov     rax, [rdx+160h]
0x18000addf  mov     rdx, rbp
0x18000ade2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ade7  lea     rdi, WPP_GLOBAL_Control
0x18000adee  mov     ebx, eax
0x18000adf0  test    eax, eax
0x18000adf2  js      short loc_18000AE03
0x18000adf4  cmp     word ptr [rsp+68h+pvarg], 8
0x18000adfa  jnz     short loc_18000AE35
0x18000adfc  mov     rsi, qword ptr [rsp+68h+pvarg+8]
0x18000ae01  jmp     short loc_18000AE35
0x18000ae03  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae0a  cmp     rcx, rdi
0x18000ae0d  jz      short loc_18000AE35
0x18000ae0f  test    byte ptr [rcx+1Ch], 1
0x18000ae13  jz      short loc_18000AE35
0x18000ae15  mov     rcx, [rcx+10h]
0x18000ae19  lea     r9, aHrgettextvalue; "HrGetTextValueFromAttribute(): Failed t"...
0x18000ae20  mov     edx, 31h ; '1'
0x18000ae25  mov     [rsp+68h+var_48], eax
0x18000ae29  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000ae30  call    WPP_SF_sd
0x18000ae35  mov     rcx, rbp; bstrString
0x18000ae38  call    cs:__imp_SysFreeString
0x18000ae3e  jmp     short loc_18000AE7E
0x18000ae40  mov     ebx, 8007000Eh
0x18000ae45  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae4c  lea     rdi, WPP_GLOBAL_Control
0x18000ae53  cmp     rcx, rdi
0x18000ae56  jz      short loc_18000AE7E
0x18000ae58  test    byte ptr [rcx+1Ch], 1
0x18000ae5c  jz      short loc_18000AE7E
0x18000ae5e  mov     rcx, [rcx+10h]
0x18000ae62  lea     r9, aHrgettextvalue_0; "HrGetTextValueFromAttribute(): Failed t"...
0x18000ae69  mov     edx, 32h ; '2'
0x18000ae6e  mov     [rsp+68h+var_48], ebx
0x18000ae72  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000ae79  call    WPP_SF_sd
0x18000ae7e  mov     rcx, [rsp+68h+arg_8]
0x18000ae83  mov     rax, [rcx]
0x18000ae86  mov     rax, [rax+10h]
0x18000ae8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae8f  test    ebx, ebx
0x18000ae91  js      short loc_18000AE9A
0x18000ae93  mov     [r14], rsi
0x18000ae96  jz      short loc_18000AF0D
0x18000ae98  jmp     short loc_18000AEE3
0x18000ae9a  test    rsi, rsi
0x18000ae9d  jz      short loc_18000AEE3
0x18000ae9f  mov     rcx, rsi; bstrString
0x18000aea2  call    cs:__imp_SysFreeString
0x18000aea8  jmp     short loc_18000AEE3
0x18000aeaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aeb1  lea     rdi, WPP_GLOBAL_Control
0x18000aeb8  cmp     rcx, rdi
0x18000aebb  jz      short loc_18000AF0D
0x18000aebd  test    byte ptr [rcx+1Ch], 1
0x18000aec1  jz      short loc_18000AEEA
0x18000aec3  mov     rcx, [rcx+10h]
0x18000aec7  lea     r9, aHrgettextvalue_1; "HrGetTextValueFromAttribute(): Failed t"...
0x18000aece  mov     edx, 33h ; '3'
0x18000aed3  mov     [rsp+68h+var_48], eax
0x18000aed7  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000aede  call    WPP_SF_sd
0x18000aee3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aeea  cmp     rcx, rdi
0x18000aeed  jz      short loc_18000AF0D
0x18000aeef  test    byte ptr [rcx+1Ch], 1
0x18000aef3  jz      short loc_18000AF0D
0x18000aef5  mov     rcx, [rcx+10h]
0x18000aef9  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000af00  mov     edx, 34h ; '4'
0x18000af05  mov     r9d, ebx
0x18000af08  call    WPP_SF_d
0x18000af0d  lea     r11, [rsp+68h+var_18]
0x18000af12  mov     eax, ebx
0x18000af14  mov     rbx, [r11+20h]
0x18000af18  mov     rbp, [r11+30h]
0x18000af1c  mov     rsp, r11
0x18000af1f  pop     r14
0x18000af21  pop     rdi
0x18000af22  pop     rsi
0x18000af23  retn
```
