# HrCreateElementWithType(IXMLDOMDocument *,ushort const *,ushort const *,tagVARIANT,IXMLDOMElement * *)

- ea: `0x1800142e4`
- end: `0x180014544`
- name: `?HrCreateElementWithType@@YAJPEAUIXMLDOMDocument@@PEBG1UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z`
- size: `608`
- prototype: `int(struct IXMLDOMDocument *, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *__struct_ptr, struct IXMLDOMElement **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013cd0`

## callees

- `0x1800142e4`
- `0x1800200f4`
- `0x180059010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001430a`
- `OLEAUT32!__imp_SysAllocString` at `0x180014358`
- `OLEAUT32!__imp_SysAllocString` at `0x18001430a`
- `OLEAUT32!__imp_SysAllocString` at `0x180014358`
- `OLEAUT32!__imp_SysFreeString` at `0x180014442`
- `OLEAUT32!__imp_SysFreeString` at `0x1800144e5`
- `OLEAUT32!__imp_SysFreeString` at `0x180014442`
- `OLEAUT32!__imp_SysFreeString` at `0x1800144e5`

## string_xrefs

- `0x1800143fd`: `HrCreateElementWithType(): put_nodeTypedValue`
- `0x180014476`: `HrCreateElementWithType(): SysAllocString`
- `0x180014424`: `HrCreateElementWithType(): put_dataType`
- `0x180014519`: `HrCreateElementWithType(): Could not allocate BSTR`
- `0x1800144c6`: `HrCreateElementWithType(): Could not create element`

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
  STRSAFE_PCNZWCH v16; // rcx
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
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
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
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
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
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
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
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_14;
      v17 = 53;
      v18 = "HrCreateElementWithType(): put_nodeTypedValue";
    }
    WPP_SF_sd(
      *((_QWORD *)v16 + 2),
      v17,
      (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
      (_DWORD)v18,
      v11);
    goto LABEL_14;
  }
  v11 = -2147024882;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
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
0x1800142e4  push    rbx
0x1800142e6  push    rbp
0x1800142e7  push    rsi
0x1800142e8  push    rdi
0x1800142e9  push    r14
0x1800142eb  sub     rsp, 50h
0x1800142ef  mov     r14, [rsp+78h+arg_20]
0x1800142f7  mov     rbx, rcx
0x1800142fa  mov     rcx, rdx; psz
0x1800142fd  mov     rbp, r9
0x180014300  mov     rdi, r8
0x180014303  mov     qword ptr [r14], 0
0x18001430a  call    cs:__imp_SysAllocString
0x180014311  nop     dword ptr [rax+rax+00h]
0x180014316  mov     rsi, rax
0x180014319  test    rax, rax
0x18001431c  jz      loc_1800144F3
0x180014322  mov     rdx, [rbx]
0x180014325  lea     r8, [rsp+78h+arg_20]
0x18001432d  mov     rcx, rbx
0x180014330  mov     [rsp+78h+arg_20], 0
0x18001433c  mov     rax, [rdx+178h]
0x180014343  mov     rdx, rsi
0x180014346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001434b  mov     ebx, eax
0x18001434d  test    eax, eax
0x18001434f  js      loc_1800144A9
0x180014355  mov     rcx, rdi; psz
0x180014358  call    cs:__imp_SysAllocString
0x18001435f  nop     dword ptr [rax+rax+00h]
0x180014364  mov     rdi, rax
0x180014367  test    rax, rax
0x18001436a  jz      loc_180014450
0x180014370  mov     rcx, [rsp+78h+arg_20]
0x180014378  mov     rdx, [rcx]
0x18001437b  mov     rax, [rdx+108h]
0x180014382  mov     rdx, rdi
0x180014385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001438a  mov     ebx, eax
0x18001438c  test    eax, eax
0x18001438e  js      short loc_180014406
0x180014390  mov     rcx, [rsp+78h+arg_20]
0x180014398  lea     rdx, [rsp+78h+var_48]
0x18001439d  movaps  xmm0, xmmword ptr [rbp+0]
0x1800143a1  movsd   xmm1, qword ptr [rbp+10h]
0x1800143a6  movaps  [rsp+78h+var_48], xmm0
0x1800143ab  mov     rax, [rcx]
0x1800143ae  movsd   [rsp+78h+var_38], xmm1
0x1800143b4  mov     rax, [rax+0F8h]
0x1800143bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143c0  mov     ebx, eax
0x1800143c2  test    eax, eax
0x1800143c4  js      short loc_1800143DF
0x1800143c6  mov     rcx, [rsp+78h+arg_20]
0x1800143ce  mov     [r14], rcx
0x1800143d1  mov     rax, [rcx]
0x1800143d4  mov     rax, [rax+8]
0x1800143d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143dd  jmp     short loc_18001443F
0x1800143df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143e6  lea     rax, WPP_GLOBAL_Control
0x1800143ed  cmp     rcx, rax
0x1800143f0  jz      short loc_18001443F
0x1800143f2  test    byte ptr [rcx+1Ch], 1
0x1800143f6  jz      short loc_18001443F
0x1800143f8  mov     edx, 35h ; '5'
0x1800143fd  lea     r9, aHrcreateelemen; "HrCreateElementWithType(): put_nodeType"...
0x180014404  jmp     short loc_18001442B
0x180014406  mov     rcx, cs:WPP_GLOBAL_Control
0x18001440d  lea     rax, WPP_GLOBAL_Control
0x180014414  cmp     rcx, rax
0x180014417  jz      short loc_18001443F
0x180014419  test    byte ptr [rcx+1Ch], 1
0x18001441d  jz      short loc_18001443F
0x18001441f  mov     edx, 36h ; '6'
0x180014424  lea     r9, aHrcreateelemen_2; "HrCreateElementWithType(): put_dataType"
0x18001442b  mov     rcx, [rcx+10h]
0x18001442f  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x180014436  mov     [rsp+78h+var_58], ebx
0x18001443a  call    WPP_SF_sd
0x18001443f  mov     rcx, rdi; bstrString
0x180014442  call    cs:__imp_SysFreeString
0x180014449  nop     dword ptr [rax+rax+00h]
0x18001444e  jmp     short loc_180014493
0x180014450  mov     r8d, 8007000Eh
0x180014456  mov     ebx, r8d
0x180014459  mov     rcx, cs:WPP_GLOBAL_Control
0x180014460  lea     rax, WPP_GLOBAL_Control
0x180014467  cmp     rcx, rax
0x18001446a  jz      short loc_180014493
0x18001446c  test    byte ptr [rcx+1Ch], 1
0x180014470  jz      short loc_180014493
0x180014472  mov     rcx, [rcx+10h]
0x180014476  lea     r9, aHrcreateelemen_1; "HrCreateElementWithType(): SysAllocStri"...
0x18001447d  mov     [rsp+78h+var_58], r8d
0x180014482  mov     edx, 37h ; '7'
0x180014487  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18001448e  call    WPP_SF_sd
0x180014493  mov     rcx, [rsp+78h+arg_20]
0x18001449b  mov     rax, [rcx]
0x18001449e  mov     rax, [rax+10h]
0x1800144a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144a7  jmp     short loc_1800144E2
0x1800144a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144b0  lea     rax, WPP_GLOBAL_Control
0x1800144b7  cmp     rcx, rax
0x1800144ba  jz      short loc_1800144E2
0x1800144bc  test    byte ptr [rcx+1Ch], 1
0x1800144c0  jz      short loc_1800144E2
0x1800144c2  mov     rcx, [rcx+10h]
0x1800144c6  lea     r9, aHrcreateelemen_3; "HrCreateElementWithType(): Could not cr"...
0x1800144cd  mov     edx, 38h ; '8'
0x1800144d2  mov     [rsp+78h+var_58], ebx
0x1800144d6  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x1800144dd  call    WPP_SF_sd
0x1800144e2  mov     rcx, rsi; bstrString
0x1800144e5  call    cs:__imp_SysFreeString
0x1800144ec  nop     dword ptr [rax+rax+00h]
0x1800144f1  jmp     short loc_180014536
0x1800144f3  mov     r8d, 8007000Eh
0x1800144f9  mov     ebx, r8d
0x1800144fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180014503  lea     rax, WPP_GLOBAL_Control
0x18001450a  cmp     rcx, rax
0x18001450d  jz      short loc_180014536
0x18001450f  test    byte ptr [rcx+1Ch], 1
0x180014513  jz      short loc_180014536
0x180014515  mov     rcx, [rcx+10h]
0x180014519  lea     r9, aHrcreateelemen_0; "HrCreateElementWithType(): Could not al"...
0x180014520  mov     [rsp+78h+var_58], r8d
0x180014525  mov     edx, 39h ; '9'
0x18001452a  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x180014531  call    WPP_SF_sd
0x180014536  mov     eax, ebx
0x180014538  add     rsp, 50h
0x18001453c  pop     r14
0x18001453e  pop     rdi
0x18001453f  pop     rsi
0x180014540  pop     rbp
0x180014541  pop     rbx
0x180014542  retn
```
