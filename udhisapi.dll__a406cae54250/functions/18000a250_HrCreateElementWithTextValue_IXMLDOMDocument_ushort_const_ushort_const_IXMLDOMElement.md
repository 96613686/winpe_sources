# HrCreateElementWithTextValue(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMElement * *)

- ea: `0x18000a250`
- end: `0x18000a49d`
- name: `?HrCreateElementWithTextValue@@YAJPEAUIXMLDOMDocument@@PEBG1PEAPEAUIXMLDOMElement@@@Z`
- size: `589`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument *, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMElement **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000449c`

## callees

- `0x1800038ec`
- `0x18000a250`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a27b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a290`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a27b`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a290`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a2a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a43b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a444`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a2a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a43b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a444`
- `OLEAUT32!__imp_VariantInit` at `0x18000a310`
- `OLEAUT32!__imp_VariantInit` at `0x18000a310`

## string_xrefs

- `0x18000a36f`: `HrCreateElementWithTextValue(): Failed to insert text node`
- `0x18000a3d1`: `HrCreateElementWithTextValue(): Failed to create text node`
- `0x18000a41c`: `HrCreateElementWithTextValue(): Could not create element`
- `0x18000a46e`: `HrCreateElementWithTextValue(): Could not allocate BSTRs`

## pseudocode

```c
__int64 __fastcall HrCreateElementWithTextValue(
        struct IXMLDOMDocument *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IXMLDOMElement **a4)
{
  OLECHAR *v7; // rdi
  OLECHAR *v8; // r14
  int v9; // ebx
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  struct IXMLDOMElement v11; // rax
  HRESULT (__stdcall *insertBefore)(IXMLDOMElement *, IXMLDOMNode *, VARIANT, IXMLDOMNode **); // rax
  struct IXMLDOMElement *v13; // rcx
  __int64 v15; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-40h] BYREF
  __int128 v17; // [rsp+50h] [rbp-28h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-18h]
  struct IXMLDOMElement *v19; // [rsp+C8h] [rbp+50h] BYREF

  v19 = 0;
  *a4 = 0;
  v7 = SysAllocString(a2);
  if ( !v7 )
  {
    v9 = -2147024882;
    goto LABEL_21;
  }
  v8 = SysAllocString(a3);
  if ( !v8 )
  {
    v9 = -2147024882;
    SysFreeString(v7);
LABEL_21:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)"HrCreateElementWithTextValue(): Could not allocate BSTRs",
        14);
    return (unsigned int)v9;
  }
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, OLECHAR *, struct IXMLDOMElement **))a1->lpVtbl->createElement)(
         a1,
         v7,
         &v19);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)"HrCreateElementWithTextValue(): Could not create element",
        v9);
  }
  else
  {
    lpVtbl = a1->lpVtbl;
    v15 = 0;
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, OLECHAR *, __int64 *))lpVtbl->createTextNode)(a1, v8, &v15);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
          (unsigned int)"HrCreateElementWithTextValue(): Failed to create text node",
          v9);
    }
    else
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      pvarg.vt = 0;
      v11.lpVtbl = v19->lpVtbl;
      pRecInfo = pvarg.pRecInfo;
      insertBefore = v11.lpVtbl->insertBefore;
      v17 = *(_OWORD *)&pvarg.vt;
      v9 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64, __int128 *, _QWORD))insertBefore)(
             v19,
             v15,
             &v17,
             0);
      if ( v9 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
          (unsigned int)"HrCreateElementWithTextValue(): Failed to insert text node",
          v9);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( v9 >= 0 )
      {
        v13 = v19;
        *a4 = v19;
        ((void (__fastcall *)(struct IXMLDOMElement *))v13->lpVtbl->AddRef)(v13);
      }
    }
    ((void (__fastcall *)(struct IXMLDOMElement *))v19->lpVtbl->Release)(v19);
  }
  SysFreeString(v7);
  SysFreeString(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a250  push    rbp
0x18000a252  push    rbx
0x18000a253  push    rsi
0x18000a254  push    rdi
0x18000a255  push    r14
0x18000a257  push    r15
0x18000a259  mov     rbp, rsp
0x18000a25c  sub     rsp, 78h
0x18000a260  mov     rsi, rcx
0x18000a263  mov     [rbp+arg_18], 0
0x18000a26b  mov     rcx, rdx; psz
0x18000a26e  mov     qword ptr [r9], 0
0x18000a275  mov     r15, r9
0x18000a278  mov     rbx, r8
0x18000a27b  call    cs:__imp_SysAllocString
0x18000a281  mov     rdi, rax
0x18000a284  test    rax, rax
0x18000a287  jz      loc_18000A44C
0x18000a28d  mov     rcx, rbx; psz
0x18000a290  call    cs:__imp_SysAllocString
0x18000a296  mov     r14, rax
0x18000a299  test    rax, rax
0x18000a29c  jnz     short loc_18000A2B1
0x18000a29e  mov     rcx, rdi; bstrString
0x18000a2a1  mov     ebx, 8007000Eh
0x18000a2a6  call    cs:__imp_SysFreeString
0x18000a2ac  jmp     loc_18000A451
0x18000a2b1  mov     rax, [rsi]
0x18000a2b4  lea     r8, [rbp+arg_18]
0x18000a2b8  mov     rdx, rdi
0x18000a2bb  mov     rcx, rsi
0x18000a2be  mov     rax, [rax+178h]
0x18000a2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2ca  mov     ebx, eax
0x18000a2cc  test    eax, eax
0x18000a2ce  js      loc_18000A3FF
0x18000a2d4  mov     rax, [rsi]
0x18000a2d7  lea     r8, [rbp+var_48]
0x18000a2db  mov     rdx, r14
0x18000a2de  mov     [rbp+var_48], 0
0x18000a2e6  mov     rcx, rsi
0x18000a2e9  mov     rax, [rax+188h]
0x18000a2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2f5  mov     ebx, eax
0x18000a2f7  test    eax, eax
0x18000a2f9  js      loc_18000A3B4
0x18000a2ff  xorps   xmm0, xmm0
0x18000a302  lea     rcx, [rbp+pvarg]; pvarg
0x18000a306  xor     eax, eax
0x18000a308  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000a30c  mov     qword ptr [rbp+pvarg+10h], rax
0x18000a310  call    cs:__imp_VariantInit
0x18000a316  mov     rcx, [rbp+arg_18]
0x18000a31a  lea     r8, [rbp+var_28]
0x18000a31e  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000a323  xor     eax, eax
0x18000a325  mov     rdx, [rbp+var_48]
0x18000a329  xor     r9d, r9d
0x18000a32c  mov     word ptr [rbp+pvarg], ax
0x18000a330  mov     rax, [rcx]
0x18000a333  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000a337  movsd   [rbp+var_18], xmm1
0x18000a33c  mov     rax, [rax+90h]
0x18000a343  movaps  [rbp+var_28], xmm0
0x18000a347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a34c  mov     ebx, eax
0x18000a34e  test    eax, eax
0x18000a350  jns     short loc_18000A38B
0x18000a352  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a359  lea     rax, WPP_GLOBAL_Control
0x18000a360  cmp     rcx, rax
0x18000a363  jz      short loc_18000A38B
0x18000a365  test    byte ptr [rcx+1Ch], 1
0x18000a369  jz      short loc_18000A38B
0x18000a36b  mov     rcx, [rcx+10h]
0x18000a36f  lea     r9, aHrcreateelemen_6; "HrCreateElementWithTextValue(): Failed "...
0x18000a376  mov     edx, 3Ah ; ':'
0x18000a37b  mov     [rsp+78h+var_58], ebx
0x18000a37f  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a386  call    WPP_SF_sd
0x18000a38b  mov     rcx, [rbp+var_48]
0x18000a38f  mov     rax, [rcx]
0x18000a392  mov     rax, [rax+10h]
0x18000a396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a39b  test    ebx, ebx
0x18000a39d  js      short loc_18000A3ED
0x18000a39f  mov     rcx, [rbp+arg_18]
0x18000a3a3  mov     [r15], rcx
0x18000a3a6  mov     rax, [rcx]
0x18000a3a9  mov     rax, [rax+8]
0x18000a3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3b2  jmp     short loc_18000A3ED
0x18000a3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3bb  lea     rax, WPP_GLOBAL_Control
0x18000a3c2  cmp     rcx, rax
0x18000a3c5  jz      short loc_18000A3ED
0x18000a3c7  test    byte ptr [rcx+1Ch], 1
0x18000a3cb  jz      short loc_18000A3ED
0x18000a3cd  mov     rcx, [rcx+10h]
0x18000a3d1  lea     r9, aHrcreateelemen_7; "HrCreateElementWithTextValue(): Failed "...
0x18000a3d8  mov     edx, 3Bh ; ';'
0x18000a3dd  mov     [rsp+78h+var_58], ebx
0x18000a3e1  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a3e8  call    WPP_SF_sd
0x18000a3ed  mov     rcx, [rbp+arg_18]
0x18000a3f1  mov     rax, [rcx]
0x18000a3f4  mov     rax, [rax+10h]
0x18000a3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3fd  jmp     short loc_18000A438
0x18000a3ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a406  lea     rax, WPP_GLOBAL_Control
0x18000a40d  cmp     rcx, rax
0x18000a410  jz      short loc_18000A438
0x18000a412  test    byte ptr [rcx+1Ch], 1
0x18000a416  jz      short loc_18000A438
0x18000a418  mov     rcx, [rcx+10h]
0x18000a41c  lea     r9, aHrcreateelemen_10; "HrCreateElementWithTextValue(): Could n"...
0x18000a423  mov     edx, 3Ch ; '<'
0x18000a428  mov     [rsp+78h+var_58], ebx
0x18000a42c  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a433  call    WPP_SF_sd
0x18000a438  mov     rcx, rdi; bstrString
0x18000a43b  call    cs:__imp_SysFreeString
0x18000a441  mov     rcx, r14; bstrString
0x18000a444  call    cs:__imp_SysFreeString
0x18000a44a  jmp     short loc_18000A48E
0x18000a44c  mov     ebx, 8007000Eh
0x18000a451  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a458  lea     rax, WPP_GLOBAL_Control
0x18000a45f  cmp     rcx, rax
0x18000a462  jz      short loc_18000A48E
0x18000a464  test    byte ptr [rcx+1Ch], 1
0x18000a468  jz      short loc_18000A48E
0x18000a46a  mov     rcx, [rcx+10h]
0x18000a46e  lea     r9, aHrcreateelemen; "HrCreateElementWithTextValue(): Could n"...
0x18000a475  mov     edx, 3Dh ; '='
0x18000a47a  mov     [rsp+78h+var_58], 8007000Eh
0x18000a482  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a489  call    WPP_SF_sd
0x18000a48e  mov     eax, ebx
0x18000a490  add     rsp, 78h
0x18000a494  pop     r15
0x18000a496  pop     r14
0x18000a498  pop     rdi
0x18000a499  pop     rsi
0x18000a49a  pop     rbx
0x18000a49b  pop     rbp
0x18000a49c  retn
```
