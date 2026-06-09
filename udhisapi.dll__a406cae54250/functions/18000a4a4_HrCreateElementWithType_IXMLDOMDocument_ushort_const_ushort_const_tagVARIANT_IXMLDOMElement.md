# HrCreateElementWithType(IXMLDOMDocument *,ushort const *,ushort const *,tagVARIANT,IXMLDOMElement * *)

- ea: `0x18000a4a4`
- end: `0x18000a6eb`
- name: `?HrCreateElementWithType@@YAJPEAUIXMLDOMDocument@@PEBG1UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument *, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *, struct IXMLDOMElement **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003dac`

## callees

- `0x1800038ec`
- `0x18000a4a4`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a4ca`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a512`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a4ca`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a512`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a5f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a693`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a5f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a693`

## string_xrefs

- `0x18000a5b1`: `HrCreateElementWithType(): put_nodeTypedValue`
- `0x18000a5d8`: `HrCreateElementWithType(): put_dataType`
- `0x18000a624`: `HrCreateElementWithType(): SysAllocString`
- `0x18000a674`: `HrCreateElementWithType(): Could not create element`
- `0x18000a6c1`: `HrCreateElementWithType(): Could not allocate BSTR`

## pseudocode

```c
__int64 __fastcall HrCreateElementWithType(
        struct IXMLDOMDocument *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct tagVARIANT *a4,
        struct IXMLDOMElement **a5)
{
  struct IXMLDOMElement **v5; // r14
  OLECHAR *v9; // rsi
  struct IXMLDOMDocumentVtbl *lpVtbl; // rdx
  int v11; // ebx
  OLECHAR *v12; // rdi
  IRecordInfo *pRecInfo; // xmm1_8
  struct IXMLDOMElement *v14; // rax
  struct IXMLDOMElement **v15; // rcx
  _QWORD *v16; // rcx
  int v17; // edx
  const char *v18; // r9
  __int128 v20; // [rsp+30h] [rbp-48h] BYREF
  IRecordInfo *v21; // [rsp+40h] [rbp-38h]

  v5 = a5;
  *a5 = 0;
  v9 = SysAllocString(a2);
  if ( v9 )
  {
    lpVtbl = a1->lpVtbl;
    a5 = 0;
    v11 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, OLECHAR *, struct IXMLDOMElement ***))lpVtbl->createElement)(
            a1,
            v9,
            &a5);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
          (unsigned int)"HrCreateElementWithType(): Could not create element",
          v11);
      goto LABEL_22;
    }
    v12 = SysAllocString(a3);
    if ( !v12 )
    {
      v11 = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
          (unsigned int)"HrCreateElementWithType(): SysAllocString",
          14);
      goto LABEL_18;
    }
    v11 = ((__int64 (__fastcall *)(struct IXMLDOMElement **, OLECHAR *))(*a5)[33].lpVtbl)(a5, v12);
    if ( v11 < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v17 = 54;
      v18 = "HrCreateElementWithType(): put_dataType";
    }
    else
    {
      pRecInfo = a4->pRecInfo;
      v20 = *(_OWORD *)&a4->vt;
      v14 = *a5;
      v21 = pRecInfo;
      v11 = ((__int64 (__fastcall *)(struct IXMLDOMElement **, __int128 *))v14[31].lpVtbl)(a5, &v20);
      if ( v11 >= 0 )
      {
        v15 = a5;
        *v5 = (struct IXMLDOMElement *)a5;
        ((void (__fastcall *)(struct IXMLDOMElement **))(*v15)[1].lpVtbl)(v15);
LABEL_14:
        SysFreeString(v12);
LABEL_18:
        ((void (__fastcall *)(struct IXMLDOMElement **))(*a5)[2].lpVtbl)(a5);
LABEL_22:
        SysFreeString(v9);
        return (unsigned int)v11;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v17 = 53;
      v18 = "HrCreateElementWithType(): put_nodeTypedValue";
    }
    WPP_SF_sd(v16[2], v17, (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids, (_DWORD)v18, v11);
    goto LABEL_14;
  }
  v11 = -2147024882;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
      (unsigned int)"HrCreateElementWithType(): Could not allocate BSTR",
      14);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000a4a4  push    rbx
0x18000a4a6  push    rbp
0x18000a4a7  push    rsi
0x18000a4a8  push    rdi
0x18000a4a9  push    r14
0x18000a4ab  sub     rsp, 50h
0x18000a4af  mov     r14, [rsp+78h+arg_20]
0x18000a4b7  mov     rbx, rcx
0x18000a4ba  mov     rcx, rdx; psz
0x18000a4bd  mov     rbp, r9
0x18000a4c0  mov     rdi, r8
0x18000a4c3  mov     qword ptr [r14], 0
0x18000a4ca  call    cs:__imp_SysAllocString
0x18000a4d0  mov     rsi, rax
0x18000a4d3  test    rax, rax
0x18000a4d6  jz      loc_18000A69B
0x18000a4dc  mov     rdx, [rbx]
0x18000a4df  lea     r8, [rsp+78h+arg_20]
0x18000a4e7  mov     rcx, rbx
0x18000a4ea  mov     [rsp+78h+arg_20], 0
0x18000a4f6  mov     rax, [rdx+178h]
0x18000a4fd  mov     rdx, rsi
0x18000a500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a505  mov     ebx, eax
0x18000a507  test    eax, eax
0x18000a509  js      loc_18000A657
0x18000a50f  mov     rcx, rdi; psz
0x18000a512  call    cs:__imp_SysAllocString
0x18000a518  mov     rdi, rax
0x18000a51b  test    rax, rax
0x18000a51e  jz      loc_18000A5FE
0x18000a524  mov     rcx, [rsp+78h+arg_20]
0x18000a52c  mov     rdx, [rcx]
0x18000a52f  mov     rax, [rdx+108h]
0x18000a536  mov     rdx, rdi
0x18000a539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a53e  mov     ebx, eax
0x18000a540  test    eax, eax
0x18000a542  js      short loc_18000A5BA
0x18000a544  mov     rcx, [rsp+78h+arg_20]
0x18000a54c  lea     rdx, [rsp+78h+var_48]
0x18000a551  movaps  xmm0, xmmword ptr [rbp+0]
0x18000a555  movsd   xmm1, qword ptr [rbp+10h]
0x18000a55a  movaps  [rsp+78h+var_48], xmm0
0x18000a55f  mov     rax, [rcx]
0x18000a562  movsd   [rsp+78h+var_38], xmm1
0x18000a568  mov     rax, [rax+0F8h]
0x18000a56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a574  mov     ebx, eax
0x18000a576  test    eax, eax
0x18000a578  js      short loc_18000A593
0x18000a57a  mov     rcx, [rsp+78h+arg_20]
0x18000a582  mov     [r14], rcx
0x18000a585  mov     rax, [rcx]
0x18000a588  mov     rax, [rax+8]
0x18000a58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a591  jmp     short loc_18000A5F3
0x18000a593  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a59a  lea     rax, WPP_GLOBAL_Control
0x18000a5a1  cmp     rcx, rax
0x18000a5a4  jz      short loc_18000A5F3
0x18000a5a6  test    byte ptr [rcx+1Ch], 1
0x18000a5aa  jz      short loc_18000A5F3
0x18000a5ac  mov     edx, 35h ; '5'
0x18000a5b1  lea     r9, aHrcreateelemen_0; "HrCreateElementWithType(): put_nodeType"...
0x18000a5b8  jmp     short loc_18000A5DF
0x18000a5ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5c1  lea     rax, WPP_GLOBAL_Control
0x18000a5c8  cmp     rcx, rax
0x18000a5cb  jz      short loc_18000A5F3
0x18000a5cd  test    byte ptr [rcx+1Ch], 1
0x18000a5d1  jz      short loc_18000A5F3
0x18000a5d3  mov     edx, 36h ; '6'
0x18000a5d8  lea     r9, aHrcreateelemen_3; "HrCreateElementWithType(): put_dataType"
0x18000a5df  mov     rcx, [rcx+10h]
0x18000a5e3  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a5ea  mov     [rsp+78h+var_58], ebx
0x18000a5ee  call    WPP_SF_sd
0x18000a5f3  mov     rcx, rdi; bstrString
0x18000a5f6  call    cs:__imp_SysFreeString
0x18000a5fc  jmp     short loc_18000A641
0x18000a5fe  mov     r8d, 8007000Eh
0x18000a604  mov     ebx, r8d
0x18000a607  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a60e  lea     rax, WPP_GLOBAL_Control
0x18000a615  cmp     rcx, rax
0x18000a618  jz      short loc_18000A641
0x18000a61a  test    byte ptr [rcx+1Ch], 1
0x18000a61e  jz      short loc_18000A641
0x18000a620  mov     rcx, [rcx+10h]
0x18000a624  lea     r9, aHrcreateelemen_2; "HrCreateElementWithType(): SysAllocStri"...
0x18000a62b  mov     [rsp+78h+var_58], r8d
0x18000a630  mov     edx, 37h ; '7'
0x18000a635  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a63c  call    WPP_SF_sd
0x18000a641  mov     rcx, [rsp+78h+arg_20]
0x18000a649  mov     rax, [rcx]
0x18000a64c  mov     rax, [rax+10h]
0x18000a650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a655  jmp     short loc_18000A690
0x18000a657  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a65e  lea     rax, WPP_GLOBAL_Control
0x18000a665  cmp     rcx, rax
0x18000a668  jz      short loc_18000A690
0x18000a66a  test    byte ptr [rcx+1Ch], 1
0x18000a66e  jz      short loc_18000A690
0x18000a670  mov     rcx, [rcx+10h]
0x18000a674  lea     r9, aHrcreateelemen_4; "HrCreateElementWithType(): Could not cr"...
0x18000a67b  mov     edx, 38h ; '8'
0x18000a680  mov     [rsp+78h+var_58], ebx
0x18000a684  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a68b  call    WPP_SF_sd
0x18000a690  mov     rcx, rsi; bstrString
0x18000a693  call    cs:__imp_SysFreeString
0x18000a699  jmp     short loc_18000A6DE
0x18000a69b  mov     r8d, 8007000Eh
0x18000a6a1  mov     ebx, r8d
0x18000a6a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6ab  lea     rax, WPP_GLOBAL_Control
0x18000a6b2  cmp     rcx, rax
0x18000a6b5  jz      short loc_18000A6DE
0x18000a6b7  test    byte ptr [rcx+1Ch], 1
0x18000a6bb  jz      short loc_18000A6DE
0x18000a6bd  mov     rcx, [rcx+10h]
0x18000a6c1  lea     r9, aHrcreateelemen_1; "HrCreateElementWithType(): Could not al"...
0x18000a6c8  mov     [rsp+78h+var_58], r8d
0x18000a6cd  mov     edx, 39h ; '9'
0x18000a6d2  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a6d9  call    WPP_SF_sd
0x18000a6de  mov     eax, ebx
0x18000a6e0  add     rsp, 50h
0x18000a6e4  pop     r14
0x18000a6e6  pop     rdi
0x18000a6e7  pop     rsi
0x18000a6e8  pop     rbp
0x18000a6e9  pop     rbx
0x18000a6ea  retn
```
