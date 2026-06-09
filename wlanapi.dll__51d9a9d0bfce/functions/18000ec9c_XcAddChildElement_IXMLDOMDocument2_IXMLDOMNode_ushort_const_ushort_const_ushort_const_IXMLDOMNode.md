# XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)

- ea: `0x18000ec9c`
- end: `0x18000ef64`
- name: `?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z`
- size: `712`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, OLECHAR *psz, OLECHAR *, OLECHAR *, struct IXMLDOMNode **)`
- caller_count: `25`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e9e0`
- `0x18000ef6c`
- `0x180018388`
- `0x180018a10`
- `0x1800450b4`
- `0x1800455c4`
- `0x180045734`
- `0x180045a3c`
- `0x180045c8c`
- `0x180045d8c`
- `0x180046fb0`
- `0x18004721c`
- `0x180047348`
- `0x180047408`
- `0x1800474a8`
- `0x180047580`
- `0x1800476b4`
- `0x180047760`
- `0x180047808`
- `0x18004e4a4`
- `0x18004e558`
- `0x18004e6ec`
- `0x18004efd0`
- `0x18004f58c`
- `0x18004f7e0`

## callees

- `0x180009654`
- `0x18000ec9c`
- `0x180012348`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000eced`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ed13`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ed3a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000eced`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ed13`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ed3a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ece2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed08`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed23`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed2e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed4a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eda9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000edb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000edbb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ece2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ecfd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed08`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed23`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed2e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ed4a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eda9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000edb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000edbb`
- `OLEAUT32!__imp_VariantInit` at `0x18000ecc1`
- `OLEAUT32!__imp_VariantInit` at `0x18000ecc1`
- `OLEAUT32!__imp_VariantClear` at `0x18000eda0`
- `OLEAUT32!__imp_VariantClear` at `0x18000ee3b`
- `OLEAUT32!__imp_VariantClear` at `0x18000eda0`
- `OLEAUT32!__imp_VariantClear` at `0x18000ee3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XcAddChildElement(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        OLECHAR *psz,
        OLECHAR *a4,
        OLECHAR *psza,
        struct IXMLDOMNode **a6)
{
  OLECHAR *v10; // rsi
  BSTR v11; // rbx
  OLECHAR *v12; // rdi
  BSTR v13; // rbx
  OLECHAR *v14; // rbx
  BSTR v15; // r14
  unsigned int v16; // r14d
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  struct IXMLDOMNode *v22; // rax
  struct IXMLDOMNode *v23; // [rsp+30h] [rbp-50h] BYREF
  __int64 v24; // [rsp+38h] [rbp-48h] BYREF
  __int64 v25; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v27; // [rsp+60h] [rbp-20h] BYREF

  VariantInit(&pvarg);
  v25 = 0;
  v23 = 0;
  v24 = 0;
  SysFreeString(0);
  v10 = 0;
  v11 = SysAllocString(psz);
  if ( v11 )
  {
    SysFreeString(0);
    v10 = v11;
  }
  SysFreeString(0);
  v12 = 0;
  v13 = SysAllocString(a4);
  if ( v13 )
  {
    SysFreeString(0);
    v12 = v13;
  }
  SysFreeString(0);
  v14 = 0;
  v15 = SysAllocString(psza);
  if ( v15 )
  {
    SysFreeString(0);
    v14 = v15;
  }
  if ( !v10 || !v12 )
    goto LABEL_11;
  if ( v14 )
  {
    v18 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, __int64 *))a1->lpVtbl->createTextNode)(
            a1,
            v14,
            &v24);
    v16 = v18;
    if ( v18 < 0 )
    {
      if ( (v18 & 0x1FFF0000) == 0x70000 )
        v16 = (unsigned __int16)v18;
      if ( v16 )
        goto LABEL_12;
    }
  }
  else if ( psza )
  {
LABEL_11:
    v16 = 14;
    goto LABEL_12;
  }
  if ( a2 == (struct IXMLDOMNode *)a1 || (v16 = XcAddWhitespace(a1, a2)) == 0 )
  {
    if ( pvarg.vt != 3 )
    {
      VariantClear(&pvarg);
      pvarg.vt = 3;
    }
    pvarg.lVal = 1;
    v27 = pvarg;
    v19 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *, OLECHAR *, OLECHAR *, __int64 *))a1->lpVtbl->createNode)(
            a1,
            &v27,
            v10,
            v12,
            &v25);
    v16 = v19;
    if ( v19 >= 0 )
      goto LABEL_27;
    if ( (v19 & 0x1FFF0000) == 0x70000 )
      v16 = (unsigned __int16)v19;
    if ( !v16 )
    {
LABEL_27:
      v20 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, struct IXMLDOMNode **))a2->lpVtbl->appendChild)(
              a2,
              v25,
              &v23);
      v16 = v20;
      if ( v20 < 0 )
      {
        if ( (v20 & 0x1FFF0000) == 0x70000 )
          v16 = (unsigned __int16)v20;
        if ( v16 )
          goto LABEL_12;
      }
      else
      {
        v16 = 0;
      }
      if ( !v14 )
        goto LABEL_38;
      v21 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))v23->lpVtbl->appendChild)(v23, v24, 0);
      v16 = v21;
      if ( v21 >= 0 )
      {
        v16 = 0;
LABEL_38:
        if ( a2 == (struct IXMLDOMNode *)a1 || (v16 = XcAddWhitespace(a1, a2)) == 0 )
        {
          if ( a6 )
          {
            v22 = v23;
            v23 = 0;
            *a6 = v22;
          }
        }
        goto LABEL_12;
      }
      if ( (v21 & 0x1FFF0000) == 0x70000 )
        v16 = (unsigned __int16)v21;
      if ( !v16 )
        goto LABEL_38;
    }
  }
LABEL_12:
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v23);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v25);
  VariantClear(&pvarg);
  SysFreeString(v14);
  SysFreeString(v12);
  SysFreeString(v10);
  return v16;
}

```

## disassembly

```asm
0x18000ec9c  push    rbp
0x18000ec9e  push    rbx
0x18000ec9f  push    rsi
0x18000eca0  push    rdi
0x18000eca1  push    r12
0x18000eca3  push    r14
0x18000eca5  push    r15
0x18000eca7  mov     rbp, rsp
0x18000ecaa  sub     rsp, 80h
0x18000ecb1  mov     r14, r9
0x18000ecb4  mov     rbx, r8
0x18000ecb7  mov     r12, rdx
0x18000ecba  mov     r15, rcx
0x18000ecbd  lea     rcx, [rbp+pvarg]; pvarg
0x18000ecc1  call    cs:__imp_VariantInit
0x18000ecc7  nop
0x18000ecc8  mov     [rbp+var_40], 0
0x18000ecd0  mov     [rbp+var_50], 0
0x18000ecd8  mov     [rbp+var_48], 0
0x18000ece0  xor     ecx, ecx; bstrString
0x18000ece2  call    cs:__imp_SysFreeString
0x18000ece8  xor     esi, esi
0x18000ecea  mov     rcx, rbx; psz
0x18000eced  call    cs:__imp_SysAllocString
0x18000ecf3  mov     rbx, rax
0x18000ecf6  test    rax, rax
0x18000ecf9  jz      short loc_18000ED06
0x18000ecfb  xor     ecx, ecx; bstrString
0x18000ecfd  call    cs:__imp_SysFreeString
0x18000ed03  mov     rsi, rbx
0x18000ed06  xor     ecx, ecx; bstrString
0x18000ed08  call    cs:__imp_SysFreeString
0x18000ed0e  xor     edi, edi
0x18000ed10  mov     rcx, r14; psz
0x18000ed13  call    cs:__imp_SysAllocString
0x18000ed19  mov     rbx, rax
0x18000ed1c  test    rax, rax
0x18000ed1f  jz      short loc_18000ED2C
0x18000ed21  xor     ecx, ecx; bstrString
0x18000ed23  call    cs:__imp_SysFreeString
0x18000ed29  mov     rdi, rbx
0x18000ed2c  xor     ecx, ecx; bstrString
0x18000ed2e  call    cs:__imp_SysFreeString
0x18000ed34  xor     ebx, ebx
0x18000ed36  mov     rcx, [rbp+psz]; psz
0x18000ed3a  call    cs:__imp_SysAllocString
0x18000ed40  mov     r14, rax
0x18000ed43  test    rax, rax
0x18000ed46  jz      short loc_18000ED53
0x18000ed48  xor     ecx, ecx; bstrString
0x18000ed4a  call    cs:__imp_SysFreeString
0x18000ed50  mov     rbx, r14
0x18000ed53  test    rsi, rsi
0x18000ed56  jz      short loc_18000ED6C
0x18000ed58  test    rdi, rdi
0x18000ed5b  jz      short loc_18000ED6C
0x18000ed5d  test    rbx, rbx
0x18000ed60  jnz     short loc_18000EDD6
0x18000ed62  cmp     [rbp+psz], rbx
0x18000ed66  jz      loc_18000EE0F
0x18000ed6c  mov     r14d, 0Eh
0x18000ed72  mov     rcx, [rbp+var_48]
0x18000ed76  test    rcx, rcx
0x18000ed79  jz      short loc_18000ED88
0x18000ed7b  mov     rax, [rcx]
0x18000ed7e  mov     rax, [rax+10h]
0x18000ed82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed87  nop
0x18000ed88  lea     rcx, [rbp+var_50]
0x18000ed8c  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000ed91  nop
0x18000ed92  lea     rcx, [rbp+var_40]
0x18000ed96  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000ed9b  nop
0x18000ed9c  lea     rcx, [rbp+pvarg]; pvarg
0x18000eda0  call    cs:__imp_VariantClear
0x18000eda6  mov     rcx, rbx; bstrString
0x18000eda9  call    cs:__imp_SysFreeString
0x18000edaf  mov     rcx, rdi; bstrString
0x18000edb2  call    cs:__imp_SysFreeString
0x18000edb8  mov     rcx, rsi; bstrString
0x18000edbb  call    cs:__imp_SysFreeString
0x18000edc1  mov     eax, r14d
0x18000edc4  add     rsp, 80h
0x18000edcb  pop     r15
0x18000edcd  pop     r14
0x18000edcf  pop     r12
0x18000edd1  pop     rdi
0x18000edd2  pop     rsi
0x18000edd3  pop     rbx
0x18000edd4  pop     rbp
0x18000edd5  retn
0x18000edd6  mov     rax, [r15]
0x18000edd9  lea     r8, [rbp+var_48]
0x18000eddd  mov     rdx, rbx
0x18000ede0  mov     rcx, r15
0x18000ede3  mov     rax, [rax+188h]
0x18000edea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edef  mov     r14d, eax
0x18000edf2  test    eax, eax
0x18000edf4  jns     short loc_18000EE0F
0x18000edf6  and     eax, 1FFF0000h
0x18000edfb  cmp     eax, 70000h
0x18000ee00  jnz     short loc_18000EE06
0x18000ee02  movzx   r14d, r14w
0x18000ee06  test    r14d, r14d
0x18000ee09  jnz     loc_18000ED72
0x18000ee0f  cmp     r12, r15
0x18000ee12  jz      short loc_18000EE2A
0x18000ee14  mov     rdx, r12; struct IXMLDOMNode *
0x18000ee17  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18000ee1a  call    ?XcAddWhitespace@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XcAddWhitespace(IXMLDOMDocument2 *,IXMLDOMNode *)
0x18000ee1f  mov     r14d, eax
0x18000ee22  test    eax, eax
0x18000ee24  jnz     loc_18000ED72
0x18000ee2a  mov     r14d, 3
0x18000ee30  cmp     word ptr [rbp+pvarg], r14w
0x18000ee35  jz      short loc_18000EE46
0x18000ee37  lea     rcx, [rbp+pvarg]; pvarg
0x18000ee3b  call    cs:__imp_VariantClear
0x18000ee41  mov     word ptr [rbp+pvarg], r14w
0x18000ee46  mov     dword ptr [rbp+pvarg+8], 1
0x18000ee4d  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000ee51  movaps  [rbp+var_20], xmm0
0x18000ee55  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000ee5a  movsd   [rbp+var_10], xmm1
0x18000ee5f  mov     rax, [r15]
0x18000ee62  lea     rcx, [rbp+var_40]
0x18000ee66  mov     [rsp+80h+var_60], rcx
0x18000ee6b  mov     r9, rdi
0x18000ee6e  mov     r8, rsi
0x18000ee71  lea     rdx, [rbp+var_20]
0x18000ee75  mov     rcx, r15
0x18000ee78  mov     rax, [rax+1C0h]
0x18000ee7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee84  mov     r14d, eax
0x18000ee87  test    eax, eax
0x18000ee89  jns     short loc_18000EEA4
0x18000ee8b  and     eax, 1FFF0000h
0x18000ee90  cmp     eax, 70000h
0x18000ee95  jnz     short loc_18000EE9B
0x18000ee97  movzx   r14d, r14w
0x18000ee9b  test    r14d, r14d
0x18000ee9e  jnz     loc_18000ED72
0x18000eea4  mov     rax, [r12]
0x18000eea8  lea     r8, [rbp+var_50]
0x18000eeac  mov     rdx, [rbp+var_40]
0x18000eeb0  mov     rcx, r12
0x18000eeb3  mov     rax, [rax+0A8h]
0x18000eeba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eebf  mov     r14d, eax
0x18000eec2  test    eax, eax
0x18000eec4  js      short loc_18000EECB
0x18000eec6  xor     r14d, r14d
0x18000eec9  jmp     short loc_18000EEE4
0x18000eecb  and     eax, 1FFF0000h
0x18000eed0  cmp     eax, 70000h
0x18000eed5  jnz     short loc_18000EEDB
0x18000eed7  movzx   r14d, r14w
0x18000eedb  test    r14d, r14d
0x18000eede  jnz     loc_18000ED72
0x18000eee4  test    rbx, rbx
0x18000eee7  jz      short loc_18000EF28
0x18000eee9  mov     rcx, [rbp+var_50]
0x18000eeed  mov     rax, [rcx]
0x18000eef0  xor     r8d, r8d
0x18000eef3  mov     rdx, [rbp+var_48]
0x18000eef7  mov     rax, [rax+0A8h]
0x18000eefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef03  mov     r14d, eax
0x18000ef06  test    eax, eax
0x18000ef08  js      short loc_18000EF0F
0x18000ef0a  xor     r14d, r14d
0x18000ef0d  jmp     short loc_18000EF28
0x18000ef0f  and     eax, 1FFF0000h
0x18000ef14  cmp     eax, 70000h
0x18000ef19  jnz     short loc_18000EF1F
0x18000ef1b  movzx   r14d, r14w
0x18000ef1f  test    r14d, r14d
0x18000ef22  jnz     loc_18000ED72
0x18000ef28  cmp     r12, r15
0x18000ef2b  jz      short loc_18000EF43
0x18000ef2d  mov     rdx, r12; struct IXMLDOMNode *
0x18000ef30  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18000ef33  call    ?XcAddWhitespace@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XcAddWhitespace(IXMLDOMDocument2 *,IXMLDOMNode *)
0x18000ef38  mov     r14d, eax
0x18000ef3b  test    eax, eax
0x18000ef3d  jnz     loc_18000ED72
0x18000ef43  mov     rcx, [rbp+arg_28]
0x18000ef47  test    rcx, rcx
0x18000ef4a  jz      loc_18000ED72
0x18000ef50  mov     rax, [rbp+var_50]
0x18000ef54  mov     [rbp+var_50], 0
0x18000ef5c  mov     [rcx], rax
0x18000ef5f  jmp     loc_18000ED72
```
