# HrGetTypedValueFromElement(IXMLDOMNode *,ushort const * const,tagVARIANT *)

- ea: `0x18000afb4`
- end: `0x18000b150`
- name: `?HrGetTypedValueFromElement@@YAJPEAUIXMLDOMNode@@QEBGPEAUtagVARIANT@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, OLECHAR *psz, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180004c94`
- `0x18000af2c`

## callees

- `0x180003728`
- `0x1800038ec`
- `0x18000a6f4`
- `0x18000a8b4`
- `0x18000afb4`
- `0x18000bab5`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000afff`
- `OLEAUT32!__imp_SysAllocString` at `0x18000afff`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b104`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b104`
- `OLEAUT32!__imp_VariantInit` at `0x18000b0c7`
- `OLEAUT32!__imp_VariantInit` at `0x18000b0c7`

## pseudocode

```c
__int64 __fastcall HrGetTypedValueFromElement(struct IXMLDOMNode *a1, OLECHAR *psz, struct tagVARIANT *a3)
{
  BSTR v6; // rax
  wchar_t *v7; // rdi
  int v8; // eax
  int v9; // ebx
  int Base64DecodedValue; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids, psz);
  v6 = SysAllocString(psz);
  v7 = v6;
  if ( v6 )
  {
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR))a1->lpVtbl->put_dataType)(a1, v6);
    v9 = v8;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
          (unsigned int)"HrGetTypedValueFromElement: put_dataType()",
          v8);
      goto LABEL_20;
    }
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct tagVARIANT *))a1->lpVtbl->get_nodeTypedValue)(a1, a3);
    if ( v9 == -2147467259 )
    {
      if ( !wcscmp_0(v7, L"bin.base64") )
      {
        Base64DecodedValue = HrGetBase64DecodedValue(a1, a3);
      }
      else
      {
        if ( wcscmp_0(v7, L"boolean") )
          goto LABEL_13;
        Base64DecodedValue = HrGetBooleanValue(a1, a3);
      }
      v9 = Base64DecodedValue;
    }
    if ( v9 >= 0 )
    {
LABEL_20:
      SysFreeString(v7);
      return (unsigned int)v9;
    }
LABEL_13:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)"HrGetTypedValueFromElement: get_nodeTypedValue()",
        v9);
    VariantInit(a3);
    goto LABEL_20;
  }
  v9 = -2147024882;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
      (unsigned int)"HrGetTypedValueFromElement: SysAllocString()",
      14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000afb4  push    rbx
0x18000afb6  push    rbp
0x18000afb7  push    rsi
0x18000afb8  push    rdi
0x18000afb9  push    r14
0x18000afbb  sub     rsp, 30h
0x18000afbf  mov     rbp, r8
0x18000afc2  mov     rbx, rdx
0x18000afc5  mov     rsi, rcx
0x18000afc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afcf  lea     r14, WPP_GLOBAL_Control
0x18000afd6  cmp     rcx, r14
0x18000afd9  jz      short loc_18000AFFC
0x18000afdb  test    dword ptr [rcx+1Ch], 100h
0x18000afe2  jz      short loc_18000AFFC
0x18000afe4  mov     rcx, [rcx+10h]
0x18000afe8  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000afef  mov     edx, 0Ch
0x18000aff4  mov     r9, rbx
0x18000aff7  call    WPP_SF_S
0x18000affc  mov     rcx, rbx; psz
0x18000afff  call    cs:__imp_SysAllocString
0x18000b005  mov     rdi, rax
0x18000b008  test    rax, rax
0x18000b00b  jz      loc_18000B10C
0x18000b011  mov     rcx, [rsi]
0x18000b014  mov     rdx, rdi
0x18000b017  mov     rax, [rcx+108h]
0x18000b01e  mov     rcx, rsi
0x18000b021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b026  mov     ebx, eax
0x18000b028  test    eax, eax
0x18000b02a  js      loc_18000B0CF
0x18000b030  mov     rax, [rsi]
0x18000b033  mov     rdx, rbp
0x18000b036  mov     rcx, rsi
0x18000b039  mov     rax, [rax+0F0h]
0x18000b040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b045  mov     ebx, eax
0x18000b047  cmp     eax, 80004005h
0x18000b04c  jnz     short loc_18000B08E
0x18000b04e  lea     rdx, aBinBase64; "bin.base64"
0x18000b055  mov     rcx, rdi; String1
0x18000b058  call    wcscmp_0
0x18000b05d  test    eax, eax
0x18000b05f  jnz     short loc_18000B06E
0x18000b061  mov     rdx, rbp; struct tagVARIANT *
0x18000b064  mov     rcx, rsi; struct IXMLDOMNode *
0x18000b067  call    ?HrGetBase64DecodedValue@@YAJPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; HrGetBase64DecodedValue(IXMLDOMNode *,tagVARIANT *)
0x18000b06c  jmp     short loc_18000B08C
0x18000b06e  lea     rdx, aBoolean; "boolean"
0x18000b075  mov     rcx, rdi; String1
0x18000b078  call    wcscmp_0
0x18000b07d  test    eax, eax
0x18000b07f  jnz     short loc_18000B092
0x18000b081  mov     rdx, rbp; struct tagVARIANT *
0x18000b084  mov     rcx, rsi; struct IXMLDOMNode *
0x18000b087  call    ?HrGetBooleanValue@@YAJPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; HrGetBooleanValue(IXMLDOMNode *,tagVARIANT *)
0x18000b08c  mov     ebx, eax
0x18000b08e  test    ebx, ebx
0x18000b090  jns     short loc_18000B101
0x18000b092  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b099  cmp     rcx, r14
0x18000b09c  jz      short loc_18000B0C4
0x18000b09e  test    byte ptr [rcx+1Ch], 1
0x18000b0a2  jz      short loc_18000B0C4
0x18000b0a4  mov     rcx, [rcx+10h]
0x18000b0a8  lea     r9, aHrgettypedvalu_0; "HrGetTypedValueFromElement: get_nodeTyp"...
0x18000b0af  mov     edx, 0Dh
0x18000b0b4  mov     [rsp+58h+var_38], ebx
0x18000b0b8  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000b0bf  call    WPP_SF_sd
0x18000b0c4  mov     rcx, rbp; pvarg
0x18000b0c7  call    cs:__imp_VariantInit
0x18000b0cd  jmp     short loc_18000B101
0x18000b0cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0d6  cmp     rcx, r14
0x18000b0d9  jz      short loc_18000B101
0x18000b0db  test    byte ptr [rcx+1Ch], 1
0x18000b0df  jz      short loc_18000B101
0x18000b0e1  mov     rcx, [rcx+10h]
0x18000b0e5  lea     r9, aHrgettypedvalu; "HrGetTypedValueFromElement: put_dataTyp"...
0x18000b0ec  mov     edx, 0Eh
0x18000b0f1  mov     [rsp+58h+var_38], eax
0x18000b0f5  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000b0fc  call    WPP_SF_sd
0x18000b101  mov     rcx, rdi; bstrString
0x18000b104  call    cs:__imp_SysFreeString
0x18000b10a  jmp     short loc_18000B143
0x18000b10c  mov     ebx, 8007000Eh
0x18000b111  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b118  cmp     rcx, r14
0x18000b11b  jz      short loc_18000B143
0x18000b11d  test    byte ptr [rcx+1Ch], 1
0x18000b121  jz      short loc_18000B143
0x18000b123  mov     rcx, [rcx+10h]
0x18000b127  lea     r9, aHrgettypedvalu_1; "HrGetTypedValueFromElement: SysAllocStr"...
0x18000b12e  mov     edx, 0Fh
0x18000b133  mov     [rsp+58h+var_38], ebx
0x18000b137  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000b13e  call    WPP_SF_sd
0x18000b143  mov     eax, ebx
0x18000b145  add     rsp, 30h
0x18000b149  pop     r14
0x18000b14b  pop     rdi
0x18000b14c  pop     rsi
0x18000b14d  pop     rbp
0x18000b14e  pop     rbx
0x18000b14f  retn
```
