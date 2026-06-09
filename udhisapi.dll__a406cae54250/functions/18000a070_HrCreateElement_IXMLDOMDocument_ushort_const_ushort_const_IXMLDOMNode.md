# HrCreateElement(IXMLDOMDocument *,ushort const *,ushort const *,IXMLDOMNode * *)

- ea: `0x18000a070`
- end: `0x18000a249`
- name: `?HrCreateElement@@YAJPEAUIXMLDOMDocument@@PEBG1PEAPEAUIXMLDOMNode@@@Z`
- size: `473`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument *, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMNode **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003dac`
- `0x18000449c`
- `0x1800063e0`

## callees

- `0x1800038ec`
- `0x18000a070`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000a094`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a0b0`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a094`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a0b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a1ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a1b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a1ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a1b5`
- `OLEAUT32!__imp_VariantInit` at `0x18000a118`
- `OLEAUT32!__imp_VariantInit` at `0x18000a118`

## string_xrefs

- `0x18000a0eb`: `HrCreateElement(): Failed to allocate memory for name string`
- `0x18000a1ec`: `HrCreateElement(): Failed to allocate memory for name string`
- `0x18000a188`: `HrCreateElement(): Failed to create element node`
- `0x18000a21e`: `HrCreateElement(): Exiting`

## pseudocode

```c
__int64 __fastcall HrCreateElement(
        struct IXMLDOMDocument *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IXMLDOMNode **a4)
{
  OLECHAR *v7; // r14
  OLECHAR *v8; // rsi
  unsigned int v9; // ebx
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  HRESULT (__stdcall *createNode)(IXMLDOMDocument *, VARIANT, BSTR, BSTR, IXMLDOMNode **); // rax
  int v12; // eax
  _QWORD *v13; // rcx
  struct IXMLDOMNode *v15; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-40h] BYREF
  __int128 v17; // [rsp+50h] [rbp-28h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-18h]

  v15 = 0;
  v7 = SysAllocString(a2);
  if ( !v7 )
  {
    v9 = -2147024882;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_21;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
      (unsigned int)"HrCreateElement(): Failed to allocate memory for name string",
      14);
LABEL_20:
    v13 = WPP_GLOBAL_Control;
LABEL_21:
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
      WPP_SF_sd(
        v13[2],
        65,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)"HrCreateElement(): Exiting",
        v9);
    return v9;
  }
  v8 = 0;
  if ( !a3 || (v8 = SysAllocString(a3)) != 0 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    pvarg.lVal = 1;
    pvarg.vt = 3;
    lpVtbl = a1->lpVtbl;
    pRecInfo = pvarg.pRecInfo;
    createNode = lpVtbl->createNode;
    v17 = *(_OWORD *)&pvarg.vt;
    v12 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int128 *, OLECHAR *, OLECHAR *, struct IXMLDOMNode **))createNode)(
            a1,
            &v17,
            v7,
            v8,
            &v15);
    v9 = v12;
    if ( v12 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)"HrCreateElement(): Failed to create element node",
        v12);
    }
    if ( v8 )
      SysFreeString(v8);
  }
  else
  {
    v9 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)"HrCreateElement(): Failed to allocate memory for name string",
        14);
  }
  SysFreeString(v7);
  if ( (v9 & 0x80000000) == 0 )
    *a4 = v15;
  if ( v9 )
    goto LABEL_20;
  return v9;
}

```

## disassembly

```asm
0x18000a070  push    rbp
0x18000a072  push    rbx
0x18000a073  push    rsi
0x18000a074  push    rdi
0x18000a075  push    r14
0x18000a077  push    r15
0x18000a079  mov     rbp, rsp
0x18000a07c  sub     rsp, 78h
0x18000a080  mov     rdi, rcx
0x18000a083  mov     [rbp+var_48], 0
0x18000a08b  mov     rcx, rdx; psz
0x18000a08e  mov     r15, r9
0x18000a091  mov     rbx, r8
0x18000a094  call    cs:__imp_SysAllocString
0x18000a09a  mov     r14, rax
0x18000a09d  test    rax, rax
0x18000a0a0  jz      loc_18000A1CA
0x18000a0a6  xor     esi, esi
0x18000a0a8  test    rbx, rbx
0x18000a0ab  jz      short loc_18000A107
0x18000a0ad  mov     rcx, rbx; psz
0x18000a0b0  call    cs:__imp_SysAllocString
0x18000a0b6  mov     rsi, rax
0x18000a0b9  test    rax, rax
0x18000a0bc  jnz     short loc_18000A107
0x18000a0be  mov     ebx, 8007000Eh
0x18000a0c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0ca  lea     rdi, WPP_GLOBAL_Control
0x18000a0d1  cmp     rcx, rdi
0x18000a0d4  jz      loc_18000A1B2
0x18000a0da  test    byte ptr [rcx+1Ch], 1
0x18000a0de  jz      loc_18000A1B2
0x18000a0e4  mov     rcx, [rcx+10h]
0x18000a0e8  lea     edx, [rax+3Eh]
0x18000a0eb  lea     r9, aHrcreateelemen_9; "HrCreateElement(): Failed to allocate m"...
0x18000a0f2  mov     dword ptr [rsp+78h+var_58], ebx
0x18000a0f6  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a0fd  call    WPP_SF_sd
0x18000a102  jmp     loc_18000A1B2
0x18000a107  xorps   xmm0, xmm0
0x18000a10a  lea     rcx, [rbp+pvarg]; pvarg
0x18000a10e  xor     eax, eax
0x18000a110  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000a114  mov     qword ptr [rbp+pvarg+10h], rax
0x18000a118  call    cs:__imp_VariantInit
0x18000a11e  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000a123  lea     rcx, [rbp+var_48]
0x18000a127  mov     eax, 3
0x18000a12c  mov     dword ptr [rbp+pvarg+8], 1
0x18000a133  mov     word ptr [rbp+pvarg], ax
0x18000a137  lea     rdx, [rbp+var_28]
0x18000a13b  mov     rax, [rdi]
0x18000a13e  mov     r9, rsi
0x18000a141  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000a145  mov     [rsp+78h+var_58], rcx
0x18000a14a  mov     r8, r14
0x18000a14d  mov     rcx, rdi
0x18000a150  movsd   [rbp+var_18], xmm1
0x18000a155  mov     rax, [rax+1C0h]
0x18000a15c  movaps  [rbp+var_28], xmm0
0x18000a160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a165  lea     rdi, WPP_GLOBAL_Control
0x18000a16c  mov     ebx, eax
0x18000a16e  test    eax, eax
0x18000a170  jns     short loc_18000A1A4
0x18000a172  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a179  cmp     rcx, rdi
0x18000a17c  jz      short loc_18000A1A4
0x18000a17e  test    byte ptr [rcx+1Ch], 1
0x18000a182  jz      short loc_18000A1A4
0x18000a184  mov     rcx, [rcx+10h]
0x18000a188  lea     r9, aHrcreateelemen_8; "HrCreateElement(): Failed to create ele"...
0x18000a18f  mov     edx, 3Fh ; '?'
0x18000a194  mov     dword ptr [rsp+78h+var_58], eax
0x18000a198  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a19f  call    WPP_SF_sd
0x18000a1a4  test    rsi, rsi
0x18000a1a7  jz      short loc_18000A1B2
0x18000a1a9  mov     rcx, rsi; bstrString
0x18000a1ac  call    cs:__imp_SysFreeString
0x18000a1b2  mov     rcx, r14; bstrString
0x18000a1b5  call    cs:__imp_SysFreeString
0x18000a1bb  test    ebx, ebx
0x18000a1bd  js      short loc_18000A1C6
0x18000a1bf  mov     rax, [rbp+var_48]
0x18000a1c3  mov     [r15], rax
0x18000a1c6  jz      short loc_18000A23A
0x18000a1c8  jmp     short loc_18000A208
0x18000a1ca  mov     ebx, 8007000Eh
0x18000a1cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1d6  lea     rdi, WPP_GLOBAL_Control
0x18000a1dd  cmp     rcx, rdi
0x18000a1e0  jz      short loc_18000A23A
0x18000a1e2  test    byte ptr [rcx+1Ch], 1
0x18000a1e6  jz      short loc_18000A20F
0x18000a1e8  mov     rcx, [rcx+10h]
0x18000a1ec  lea     r9, aHrcreateelemen_9; "HrCreateElement(): Failed to allocate m"...
0x18000a1f3  mov     edx, 40h ; '@'
0x18000a1f8  mov     dword ptr [rsp+78h+var_58], ebx
0x18000a1fc  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a203  call    WPP_SF_sd
0x18000a208  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a20f  cmp     rcx, rdi
0x18000a212  jz      short loc_18000A23A
0x18000a214  test    byte ptr [rcx+1Ch], 1
0x18000a218  jz      short loc_18000A23A
0x18000a21a  mov     rcx, [rcx+10h]
0x18000a21e  lea     r9, aHrcreateelemen_5; "HrCreateElement(): Exiting"
0x18000a225  mov     edx, 41h ; 'A'
0x18000a22a  mov     dword ptr [rsp+78h+var_58], ebx
0x18000a22e  lea     r8, WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids
0x18000a235  call    WPP_SF_sd
0x18000a23a  mov     eax, ebx
0x18000a23c  add     rsp, 78h
0x18000a240  pop     r15
0x18000a242  pop     r14
0x18000a244  pop     rdi
0x18000a245  pop     rsi
0x18000a246  pop     rbx
0x18000a247  pop     rbp
0x18000a248  retn
```
