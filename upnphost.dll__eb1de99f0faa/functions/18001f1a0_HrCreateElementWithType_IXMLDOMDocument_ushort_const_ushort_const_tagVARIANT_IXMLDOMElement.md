# HrCreateElementWithType(IXMLDOMDocument *,ushort const *,ushort const *,tagVARIANT,IXMLDOMElement * *)

- ea: `0x18001f1a0`
- end: `0x18001f3e7`
- name: `?HrCreateElementWithType@@YAJPEAUIXMLDOMDocument@@PEBG1UtagVARIANT@@PEAPEAUIXMLDOMElement@@@Z`
- size: `583`
- prototype: `int(struct IXMLDOMDocument *, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *__struct_ptr, struct IXMLDOMElement **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001ebf8`

## callees

- `0x18000db4c`
- `0x18001f1a0`
- `0x180055010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001f1c6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f20e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f1c6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001f20e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f2f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f38f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f2f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f38f`

## string_xrefs

- `0x18001f2d4`: `HrCreateElementWithType(): put_dataType`
- `0x18001f2ad`: `HrCreateElementWithType(): put_nodeTypedValue`
- `0x18001f370`: `HrCreateElementWithType(): Could not create element`
- `0x18001f320`: `HrCreateElementWithType(): SysAllocString`
- `0x18001f3bd`: `HrCreateElementWithType(): Could not allocate BSTR`

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
0x18001f1a0  push    rbx
0x18001f1a2  push    rbp
0x18001f1a3  push    rsi
0x18001f1a4  push    rdi
0x18001f1a5  push    r14
0x18001f1a7  sub     rsp, 50h
0x18001f1ab  mov     r14, [rsp+78h+arg_20]
0x18001f1b3  mov     rbx, rcx
0x18001f1b6  mov     rcx, rdx; psz
0x18001f1b9  mov     rbp, r9
0x18001f1bc  mov     rdi, r8
0x18001f1bf  mov     qword ptr [r14], 0
0x18001f1c6  call    cs:__imp_SysAllocString
0x18001f1cc  mov     rsi, rax
0x18001f1cf  test    rax, rax
0x18001f1d2  jz      loc_18001F397
0x18001f1d8  mov     rdx, [rbx]
0x18001f1db  lea     r8, [rsp+78h+arg_20]
0x18001f1e3  mov     rcx, rbx
0x18001f1e6  mov     [rsp+78h+arg_20], 0
0x18001f1f2  mov     rax, [rdx+178h]
0x18001f1f9  mov     rdx, rsi
0x18001f1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f201  mov     ebx, eax
0x18001f203  test    eax, eax
0x18001f205  js      loc_18001F353
0x18001f20b  mov     rcx, rdi; psz
0x18001f20e  call    cs:__imp_SysAllocString
0x18001f214  mov     rdi, rax
0x18001f217  test    rax, rax
0x18001f21a  jz      loc_18001F2FA
0x18001f220  mov     rcx, [rsp+78h+arg_20]
0x18001f228  mov     rdx, [rcx]
0x18001f22b  mov     rax, [rdx+108h]
0x18001f232  mov     rdx, rdi
0x18001f235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f23a  mov     ebx, eax
0x18001f23c  test    eax, eax
0x18001f23e  js      short loc_18001F2B6
0x18001f240  mov     rcx, [rsp+78h+arg_20]
0x18001f248  lea     rdx, [rsp+78h+var_48]
0x18001f24d  movaps  xmm0, xmmword ptr [rbp+0]
0x18001f251  movsd   xmm1, qword ptr [rbp+10h]
0x18001f256  movaps  [rsp+78h+var_48], xmm0
0x18001f25b  mov     rax, [rcx]
0x18001f25e  movsd   [rsp+78h+var_38], xmm1
0x18001f264  mov     rax, [rax+0F8h]
0x18001f26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f270  mov     ebx, eax
0x18001f272  test    eax, eax
0x18001f274  js      short loc_18001F28F
0x18001f276  mov     rcx, [rsp+78h+arg_20]
0x18001f27e  mov     [r14], rcx
0x18001f281  mov     rax, [rcx]
0x18001f284  mov     rax, [rax+8]
0x18001f288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f28d  jmp     short loc_18001F2EF
0x18001f28f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f296  lea     rax, WPP_GLOBAL_Control
0x18001f29d  cmp     rcx, rax
0x18001f2a0  jz      short loc_18001F2EF
0x18001f2a2  test    byte ptr [rcx+1Ch], 1
0x18001f2a6  jz      short loc_18001F2EF
0x18001f2a8  mov     edx, 35h ; '5'
0x18001f2ad  lea     r9, aHrcreateelemen; "HrCreateElementWithType(): put_nodeType"...
0x18001f2b4  jmp     short loc_18001F2DB
0x18001f2b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2bd  lea     rax, WPP_GLOBAL_Control
0x18001f2c4  cmp     rcx, rax
0x18001f2c7  jz      short loc_18001F2EF
0x18001f2c9  test    byte ptr [rcx+1Ch], 1
0x18001f2cd  jz      short loc_18001F2EF
0x18001f2cf  mov     edx, 36h ; '6'
0x18001f2d4  lea     r9, aHrcreateelemen_2; "HrCreateElementWithType(): put_dataType"
0x18001f2db  mov     rcx, [rcx+10h]
0x18001f2df  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18001f2e6  mov     [rsp+78h+var_58], ebx
0x18001f2ea  call    WPP_SF_sd
0x18001f2ef  mov     rcx, rdi; bstrString
0x18001f2f2  call    cs:__imp_SysFreeString
0x18001f2f8  jmp     short loc_18001F33D
0x18001f2fa  mov     r8d, 8007000Eh
0x18001f300  mov     ebx, r8d
0x18001f303  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f30a  lea     rax, WPP_GLOBAL_Control
0x18001f311  cmp     rcx, rax
0x18001f314  jz      short loc_18001F33D
0x18001f316  test    byte ptr [rcx+1Ch], 1
0x18001f31a  jz      short loc_18001F33D
0x18001f31c  mov     rcx, [rcx+10h]
0x18001f320  lea     r9, aHrcreateelemen_1; "HrCreateElementWithType(): SysAllocStri"...
0x18001f327  mov     [rsp+78h+var_58], r8d
0x18001f32c  mov     edx, 37h ; '7'
0x18001f331  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18001f338  call    WPP_SF_sd
0x18001f33d  mov     rcx, [rsp+78h+arg_20]
0x18001f345  mov     rax, [rcx]
0x18001f348  mov     rax, [rax+10h]
0x18001f34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f351  jmp     short loc_18001F38C
0x18001f353  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f35a  lea     rax, WPP_GLOBAL_Control
0x18001f361  cmp     rcx, rax
0x18001f364  jz      short loc_18001F38C
0x18001f366  test    byte ptr [rcx+1Ch], 1
0x18001f36a  jz      short loc_18001F38C
0x18001f36c  mov     rcx, [rcx+10h]
0x18001f370  lea     r9, aHrcreateelemen_3; "HrCreateElementWithType(): Could not cr"...
0x18001f377  mov     edx, 38h ; '8'
0x18001f37c  mov     [rsp+78h+var_58], ebx
0x18001f380  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18001f387  call    WPP_SF_sd
0x18001f38c  mov     rcx, rsi; bstrString
0x18001f38f  call    cs:__imp_SysFreeString
0x18001f395  jmp     short loc_18001F3DA
0x18001f397  mov     r8d, 8007000Eh
0x18001f39d  mov     ebx, r8d
0x18001f3a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f3a7  lea     rax, WPP_GLOBAL_Control
0x18001f3ae  cmp     rcx, rax
0x18001f3b1  jz      short loc_18001F3DA
0x18001f3b3  test    byte ptr [rcx+1Ch], 1
0x18001f3b7  jz      short loc_18001F3DA
0x18001f3b9  mov     rcx, [rcx+10h]
0x18001f3bd  lea     r9, aHrcreateelemen_0; "HrCreateElementWithType(): Could not al"...
0x18001f3c4  mov     [rsp+78h+var_58], r8d
0x18001f3c9  mov     edx, 39h ; '9'
0x18001f3ce  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18001f3d5  call    WPP_SF_sd
0x18001f3da  mov     eax, ebx
0x18001f3dc  add     rsp, 50h
0x18001f3e0  pop     r14
0x18001f3e2  pop     rdi
0x18001f3e3  pop     rsi
0x18001f3e4  pop     rbp
0x18001f3e5  pop     rbx
0x18001f3e6  retn
```
