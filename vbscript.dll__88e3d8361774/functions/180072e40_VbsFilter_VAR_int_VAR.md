# VbsFilter(VAR *,int,VAR *)

- ea: `0x180072e40`
- end: `0x1800730b3`
- name: `?VbsFilter@@YAJPEAVVAR@@H0@Z`
- size: `627`
- prototype: `int(struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800037b0`
- `0x1800038c0`
- `0x18001b260`
- `0x18001cf8c`
- `0x18001d6c0`
- `0x18001e7a0`
- `0x18001f2b0`
- `0x180036c90`
- `0x180072e40`
- `0x180073850`

## import_xrefs

- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x18007301f`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x18007301f`
- `OLEAUT32!SafeArrayAddRef` at `0x180072fbd`
- `OLEAUT32!SafeArrayAddRef` at `0x180072fbd`
- `OLEAUT32!SafeArrayReleaseData` at `0x180073010`
- `OLEAUT32!SafeArrayReleaseData` at `0x180073010`
- `OLEAUT32!__imp_SysFreeString` at `0x180072f33`
- `OLEAUT32!__imp_SysFreeString` at `0x180072fa9`
- `OLEAUT32!__imp_SysFreeString` at `0x180072fd2`
- `OLEAUT32!__imp_SysFreeString` at `0x180073032`
- `OLEAUT32!__imp_SysFreeString` at `0x180073063`
- `OLEAUT32!__imp_SysFreeString` at `0x18007308c`
- `OLEAUT32!__imp_SysFreeString` at `0x180072f33`
- `OLEAUT32!__imp_SysFreeString` at `0x180072fa9`
- `OLEAUT32!__imp_SysFreeString` at `0x180072fd2`
- `OLEAUT32!__imp_SysFreeString` at `0x180073032`
- `OLEAUT32!__imp_SysFreeString` at `0x180073063`
- `OLEAUT32!__imp_SysFreeString` at `0x18007308c`
- `KERNEL32!IsValidLocale` at `0x180072ea6`
- `KERNEL32!IsValidLocale` at `0x180072ea6`

## pseudocode

```c
__int64 __fastcall VbsFilter(struct VAR *a1, int a2, VARIANTARG *a3)
{
  int v3; // r12d
  VARIANTARG *v4; // rbx
  LCID Val; // eax
  unsigned int ConversionLocale; // edi
  int v10; // r14d
  struct VAR *TypeVal; // rax
  struct VAR *VarVal; // rax
  int v13; // r13d
  __int16 v14; // dx
  OLECHAR *v15; // rcx
  SAFEARRAY *v16; // rcx
  SAFEARRAY *v17; // rax
  OLECHAR *v18; // rbx
  HRESULT v19; // esi
  int v20; // edi
  struct tagSAFEARRAY *OneDim; // rdi
  struct VAR *v22; // rax
  _BYTE v23[8]; // [rsp+40h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-8h]
  SAFEARRAY *psa; // [rsp+90h] [rbp+40h] BYREF
  PVOID ppDataToRelease; // [rsp+A0h] [rbp+50h] BYREF
  struct tagSAFEARRAY *v27; // [rsp+A8h] [rbp+58h] BYREF

  v27 = 0;
  ppDataToRelease = 0;
  v3 = 1;
  *(_WORD *)a1 = 1;
  v4 = a3;
  if ( (unsigned int)(a2 - 2) > 2 )
    return 2148139458LL;
  if ( a2 != 4 )
  {
    v10 = 0;
LABEL_9:
    ConversionLocale = COleScript::GetConversionLocale();
    if ( a2 < 3 )
      goto LABEL_11;
    goto LABEL_10;
  }
  Val = VAR::UlGetVal((VAR *)a3);
  ++v4;
  ConversionLocale = Val;
  if ( Val < 2 )
  {
    v10 = Val;
    goto LABEL_9;
  }
  if ( !IsValidLocale(Val, 1u) )
    return 2148139013LL;
  v10 = 1;
LABEL_10:
  TypeVal = VAR::PvarGetTypeVal(v4++, 0xBu);
  v3 = *((__int16 *)TypeVal + 4);
LABEL_11:
  v23[0] = 0;
  bstrString = VAR::BstrGetVal((VAR *)v4);
  if ( bstrString == (BSTR)-1LL )
    return 2148139102LL;
  BSTRHelper::CloneIfNeeded((BSTRHelper *)v23, (struct VAR *)&v4[1]);
  VarVal = VAR::PvarGetVarVal((VAR *)&v4[1], 0);
  v13 = (int)VarVal;
  v14 = *(_WORD *)VarVal;
  if ( *(_WORD *)VarVal == 1 )
  {
LABEL_13:
    if ( v23[0] )
      SysFreeString(bstrString);
    return 2148139102LL;
  }
  if ( ((v14 - 8204) & 0xBFFF) != 0 )
  {
    if ( v23[0] )
    {
      v15 = bstrString;
LABEL_27:
      SysFreeString(v15);
      return 2148139021LL;
    }
    return 2148139021LL;
  }
  v16 = (SAFEARRAY *)*((_QWORD *)VarVal + 1);
  psa = v16;
  if ( (v14 & 0x4000) != 0 )
  {
    if ( !v16 )
      goto LABEL_13;
    v17 = *(SAFEARRAY **)&v16->cDims;
    v16 = v17;
    psa = v17;
  }
  else
  {
    v17 = v16;
  }
  v18 = bstrString;
  if ( v17 )
  {
    if ( v16->cDims != 1 )
    {
      if ( v23[0] )
      {
        v15 = bstrString;
        goto LABEL_27;
      }
      return 2148139021LL;
    }
    v19 = SafeArrayAddRef(v16, &ppDataToRelease);
    if ( v19 < 0 )
    {
      if ( v23[0] )
        SysFreeString(v18);
      return (unsigned int)v19;
    }
    v20 = rtFilter(v13, (unsigned int)&psa, (_DWORD)v18, v3, ConversionLocale, v10, (__int64)&v27);
    if ( ppDataToRelease )
      SafeArrayReleaseData(ppDataToRelease);
    if ( psa )
      SafeArrayReleaseDescriptor(psa);
    if ( v20 < 0 )
    {
      if ( v23[0] )
        SysFreeString(v18);
      return (unsigned int)v20;
    }
    OneDim = v27;
  }
  else
  {
    OneDim = psaMakeOneDim(0);
  }
  v22 = PvarAlloc();
  *((_QWORD *)a1 + 1) = v22;
  if ( v22 )
  {
    *(_WORD *)v22 = 8204;
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 8LL) = OneDim;
    *(_WORD *)a1 = 74;
    if ( v23[0] )
      SysFreeString(v18);
    return 0;
  }
  else
  {
    if ( v23[0] )
      SysFreeString(v18);
    return 2148139015LL;
  }
}

```

## disassembly

```asm
0x180072e40  mov     [rsp-38h+arg_8], rbx
0x180072e45  push    rbp
0x180072e46  push    rsi
0x180072e47  push    rdi
0x180072e48  push    r12
0x180072e4a  push    r13
0x180072e4c  push    r14
0x180072e4e  push    r15
0x180072e50  mov     rbp, rsp
0x180072e53  sub     rsp, 50h
0x180072e57  lea     eax, [rdx-2]
0x180072e5a  mov     [rbp+arg_18], 0
0x180072e62  mov     [rbp+ppDataToRelease], 0
0x180072e6a  mov     r12d, 1
0x180072e70  mov     [rcx], r12w
0x180072e74  mov     rbx, r8
0x180072e77  mov     esi, edx
0x180072e79  mov     r15, rcx
0x180072e7c  cmp     eax, 2
0x180072e7f  ja      loc_180073096
0x180072e85  cmp     edx, 4
0x180072e88  jnz     short loc_180072EC4
0x180072e8a  mov     rcx, rbx; this
0x180072e8d  call    ?UlGetVal@VAR@@QEAAKXZ; VAR::UlGetVal(void)
0x180072e92  add     rbx, 18h
0x180072e96  mov     edi, eax
0x180072e98  test    eax, eax
0x180072e9a  jz      short loc_180072EBF
0x180072e9c  cmp     eax, r12d
0x180072e9f  jz      short loc_180072EBF
0x180072ea1  mov     edx, r12d; dwFlags
0x180072ea4  mov     ecx, eax; Locale
0x180072ea6  call    cs:__imp_IsValidLocale
0x180072eac  test    eax, eax
0x180072eae  jnz     short loc_180072EBA
0x180072eb0  mov     eax, 800A0005h
0x180072eb5  jmp     loc_18007309B
0x180072eba  mov     r14d, r12d
0x180072ebd  jmp     short loc_180072ED3
0x180072ebf  mov     r14d, eax
0x180072ec2  jmp     short loc_180072EC7
0x180072ec4  xor     r14d, r14d
0x180072ec7  call    ?GetConversionLocale@COleScript@@SAKXZ; COleScript::GetConversionLocale(void)
0x180072ecc  mov     edi, eax
0x180072ece  cmp     esi, 3
0x180072ed1  jl      short loc_180072EE9
0x180072ed3  mov     edx, 0Bh; unsigned __int16
0x180072ed8  mov     rcx, rbx; pvarSrc
0x180072edb  call    ?PvarGetTypeVal@VAR@@QEAAPEAV1@H@Z; VAR::PvarGetTypeVal(int)
0x180072ee0  add     rbx, 18h
0x180072ee4  movsx   r12d, word ptr [rax+8]
0x180072ee9  xor     esi, esi
0x180072eeb  mov     rcx, rbx; this
0x180072eee  mov     [rbp+var_10], sil
0x180072ef2  call    ?BstrGetVal@VAR@@QEAAPEAGXZ; VAR::BstrGetVal(void)
0x180072ef7  mov     [rbp+bstrString], rax
0x180072efb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180072eff  jz      short loc_180072F39
0x180072f01  lea     rdx, [rbx+18h]; struct VAR *
0x180072f05  lea     rcx, [rbp+var_10]; this
0x180072f09  call    ?CloneIfNeeded@BSTRHelper@@QEAAXPEAVVAR@@@Z; BSTRHelper::CloneIfNeeded(VAR *)
0x180072f0e  xor     edx, edx; int
0x180072f10  lea     rcx, [rbx+18h]; this
0x180072f14  call    ?PvarGetVarVal@VAR@@QEAAPEAV1@H@Z; VAR::PvarGetVarVal(int)
0x180072f19  lea     r8d, [rsi+1]
0x180072f1d  mov     r13, rax
0x180072f20  movzx   edx, word ptr [rax]
0x180072f23  cmp     r8w, dx
0x180072f27  jnz     short loc_180072F43
0x180072f29  cmp     [rbp+var_10], sil
0x180072f2d  jz      short loc_180072F39
0x180072f2f  mov     rcx, [rbp+bstrString]; bstrString
0x180072f33  call    cs:__imp_SysFreeString
0x180072f39  mov     eax, 800A005Eh
0x180072f3e  jmp     loc_18007309B
0x180072f43  mov     ecx, 200Ch
0x180072f48  movzx   eax, dx
0x180072f4b  sub     ax, cx
0x180072f4e  mov     ecx, 0BFFFh
0x180072f53  test    cx, ax
0x180072f56  jz      short loc_180072F64
0x180072f58  cmp     [rbp+var_10], sil
0x180072f5c  jz      short loc_180072FAF
0x180072f5e  mov     rcx, [rbp+bstrString]
0x180072f62  jmp     short loc_180072FA9
0x180072f64  mov     rcx, [r13+8]; psa
0x180072f68  mov     eax, 4000h
0x180072f6d  and     dx, ax
0x180072f70  mov     [rbp+psa], rcx
0x180072f74  cmp     si, dx
0x180072f77  jz      short loc_180072F8A
0x180072f79  test    rcx, rcx
0x180072f7c  jz      short loc_180072F29
0x180072f7e  mov     rax, [rcx]
0x180072f81  mov     rcx, rax
0x180072f84  mov     [rbp+psa], rax
0x180072f88  jmp     short loc_180072F8D
0x180072f8a  mov     rax, rcx
0x180072f8d  mov     rbx, [rbp+bstrString]
0x180072f91  test    rax, rax
0x180072f94  jz      loc_180073042
0x180072f9a  cmp     r8w, [rcx]
0x180072f9e  jz      short loc_180072FB9
0x180072fa0  cmp     [rbp+var_10], sil
0x180072fa4  jz      short loc_180072FAF
0x180072fa6  mov     rcx, rbx; bstrString
0x180072fa9  call    cs:__imp_SysFreeString
0x180072faf  mov     eax, 800A000Dh
0x180072fb4  jmp     loc_18007309B
0x180072fb9  lea     rdx, [rbp+ppDataToRelease]; ppDataToRelease
0x180072fbd  call    cs:__imp_SafeArrayAddRef
0x180072fc3  mov     esi, eax
0x180072fc5  test    eax, eax
0x180072fc7  jns     short loc_180072FDF
0x180072fc9  cmp     [rbp+var_10], 0
0x180072fcd  jz      short loc_180072FD8
0x180072fcf  mov     rcx, rbx; bstrString
0x180072fd2  call    cs:__imp_SysFreeString
0x180072fd8  mov     eax, esi
0x180072fda  jmp     loc_18007309B
0x180072fdf  lea     rax, [rbp+arg_18]
0x180072fe3  mov     r9d, r12d
0x180072fe6  mov     [rsp+50h+var_20], rax
0x180072feb  lea     rdx, [rbp+psa]
0x180072fef  mov     [rsp+50h+var_28], r14d
0x180072ff4  mov     r8, rbx
0x180072ff7  mov     rcx, r13
0x180072ffa  mov     [rsp+50h+var_30], edi
0x180072ffe  call    rtFilter
0x180073003  mov     rcx, [rbp+ppDataToRelease]; pData
0x180073007  xor     esi, esi
0x180073009  mov     edi, eax
0x18007300b  test    rcx, rcx
0x18007300e  jz      short loc_180073016
0x180073010  call    cs:__imp_SafeArrayReleaseData
0x180073016  mov     rcx, [rbp+psa]; psa
0x18007301a  test    rcx, rcx
0x18007301d  jz      short loc_180073025
0x18007301f  call    cs:__imp_SafeArrayReleaseDescriptor
0x180073025  test    edi, edi
0x180073027  jns     short loc_18007303C
0x180073029  cmp     [rbp+var_10], sil
0x18007302d  jz      short loc_180073038
0x18007302f  mov     rcx, rbx; bstrString
0x180073032  call    cs:__imp_SysFreeString
0x180073038  mov     eax, edi
0x18007303a  jmp     short loc_18007309B
0x18007303c  mov     rdi, [rbp+arg_18]
0x180073040  jmp     short loc_18007304C
0x180073042  xor     ecx, ecx; int
0x180073044  call    ?psaMakeOneDim@@YAPEAUtagSAFEARRAY@@J@Z; psaMakeOneDim(long)
0x180073049  mov     rdi, rax
0x18007304c  call    ?PvarAlloc@@YAPEAVVAR@@XZ; PvarAlloc(void)
0x180073051  mov     [r15+8], rax
0x180073055  test    rax, rax
0x180073058  jnz     short loc_180073070
0x18007305a  cmp     [rbp+var_10], sil
0x18007305e  jz      short loc_180073069
0x180073060  mov     rcx, rbx; bstrString
0x180073063  call    cs:__imp_SysFreeString
0x180073069  mov     eax, 800A0007h
0x18007306e  jmp     short loc_18007309B
0x180073070  mov     word ptr [rax], 200Ch
0x180073075  mov     rax, [r15+8]
0x180073079  mov     [rax+8], rdi
0x18007307d  mov     word ptr [r15], 4Ah ; 'J'
0x180073083  cmp     [rbp+var_10], sil
0x180073087  jz      short loc_180073092
0x180073089  mov     rcx, rbx; bstrString
0x18007308c  call    cs:__imp_SysFreeString
0x180073092  xor     eax, eax
0x180073094  jmp     short loc_18007309B
0x180073096  mov     eax, 800A01C2h
0x18007309b  mov     rbx, [rsp+50h+arg_8]
0x1800730a3  add     rsp, 50h
0x1800730a7  pop     r15
0x1800730a9  pop     r14
0x1800730ab  pop     r13
0x1800730ad  pop     r12
0x1800730af  pop     rdi
0x1800730b0  pop     rsi
0x1800730b1  pop     rbp
0x1800730b2  retn
```
