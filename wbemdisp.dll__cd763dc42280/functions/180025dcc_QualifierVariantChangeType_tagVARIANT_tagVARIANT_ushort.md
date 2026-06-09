# QualifierVariantChangeType(tagVARIANT *,tagVARIANT *,ushort)

- ea: `0x180025dcc`
- end: `0x180025f97`
- name: `?QualifierVariantChangeType@@YAJPEAUtagVARIANT@@0G@Z`
- size: `459`
- prototype: `int(struct tagVARIANT *, struct tagVARIANT *, unsigned __int16)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180020de0`
- `0x180020ff0`
- `0x180023590`

## callees

- `0x180025dcc`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180025ec0`
- `OLEAUT32!__imp_VariantInit` at `0x180025ec0`
- `OLEAUT32!__imp_VariantClear` at `0x180025f23`
- `OLEAUT32!__imp_VariantClear` at `0x180025f53`
- `OLEAUT32!__imp_VariantClear` at `0x180025f23`
- `OLEAUT32!__imp_VariantClear` at `0x180025f53`
- `OLEAUT32!__imp_VariantCopy` at `0x180025df9`
- `OLEAUT32!__imp_VariantCopy` at `0x180025df9`
- `OLEAUT32!__imp_VariantChangeType` at `0x180025ef5`
- `OLEAUT32!__imp_VariantChangeType` at `0x180025f75`
- `OLEAUT32!__imp_VariantChangeType` at `0x180025ef5`
- `OLEAUT32!__imp_VariantChangeType` at `0x180025f75`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180025e8f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180025e8f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025f66`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025f66`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180025e56`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180025e56`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180025e37`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180025e37`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180025ee0`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180025ee0`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180025f17`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180025f17`

## pseudocode

```c
int __fastcall QualifierVariantChangeType(struct tagVARIANT *a1, struct tagVARIANT *a2, VARTYPE a3)
{
  int result; // eax
  SAFEARRAY *parray; // r12
  HRESULT v8; // ebx
  SAFEARRAY *v9; // r14
  int i; // eax
  void *bstrVal; // r8
  LONG v12; // ecx
  LONG plLbound; // [rsp+20h] [rbp-30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+98h] [rbp+48h] BYREF
  LONG plUbound; // [rsp+A8h] [rbp+58h] BYREF

  if ( a2->vt == 1 )
    return VariantCopy(a1, a2);
  if ( (a3 & 0x2000) == 0 )
    return VariantChangeType(a1, a2, 1u, a3);
  if ( (a2->vt & 0x2000) == 0 )
    return -2147352571;
  parray = a2->parray;
  plLbound = 0;
  result = SafeArrayGetLBound(parray, 1u, &plLbound);
  if ( result >= 0 )
  {
    plUbound = 0;
    result = SafeArrayGetUBound(parray, 1u, &plUbound);
    v8 = result;
    if ( result >= 0 )
    {
      rgsabound.lLbound = plLbound;
      rgsabound.cElements = plUbound - plLbound + 1;
      v9 = SafeArrayCreate(a3 & 0xDFFF, 1u, &rgsabound);
      if ( !v9 )
        return -2147217402;
      for ( i = plLbound; ; i = rgIndices + 1 )
      {
        v12 = plUbound;
        rgIndices = i;
        if ( i > plUbound )
          break;
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        pvarg.vt = a2->vt & 0xDFFF;
        SafeArrayGetElement(parray, &rgIndices, &pvarg.decVal.8);
        v8 = VariantChangeType(&pvarg, &pvarg, 0, a3 & 0xDFFF);
        if ( v8 >= 0 )
        {
          bstrVal = pvarg.bstrVal;
          if ( pvarg.vt != 8 )
            bstrVal = &pvarg.decVal.8;
          v8 = SafeArrayPutElement(v9, &rgIndices, bstrVal);
        }
        VariantClear(&pvarg);
        i = rgIndices;
        if ( v8 < 0 )
        {
          v12 = plUbound;
          break;
        }
      }
      if ( v12 >= i )
      {
        SafeArrayDestroy(v9);
      }
      else
      {
        v8 = 0;
        if ( a1 == a2 )
          VariantClear(a2);
        a1->vt = a3;
        a1->llVal = (LONGLONG)v9;
      }
      return v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180025dcc  mov     [rsp-38h+arg_0], rbx
0x180025dd1  push    rbp
0x180025dd2  push    rsi
0x180025dd3  push    rdi
0x180025dd4  push    r12
0x180025dd6  push    r13
0x180025dd8  push    r14
0x180025dda  push    r15
0x180025ddc  mov     rbp, rsp
0x180025ddf  sub     rsp, 50h
0x180025de3  mov     r14d, 1
0x180025de9  movzx   r15d, r8w
0x180025ded  mov     rdi, rdx
0x180025df0  mov     rsi, rcx
0x180025df3  cmp     [rdx], r14w
0x180025df7  jnz     short loc_180025E04
0x180025df9  call    cs:__imp_VariantCopy
0x180025dff  jmp     loc_180025F7F
0x180025e04  mov     eax, 2000h
0x180025e09  test    ax, r15w
0x180025e0d  jz      loc_180025F6E
0x180025e13  test    [rdx], ax
0x180025e16  jnz     short loc_180025E22
0x180025e18  mov     eax, 80020005h
0x180025e1d  jmp     loc_180025F7F
0x180025e22  mov     r12, [rdx+8]
0x180025e26  lea     r8, [rbp+plLbound]; plLbound
0x180025e2a  mov     rcx, r12; psa
0x180025e2d  mov     [rbp+plLbound], 0
0x180025e34  mov     edx, r14d; nDim
0x180025e37  call    cs:__imp_SafeArrayGetLBound
0x180025e3d  test    eax, eax
0x180025e3f  js      loc_180025F7F
0x180025e45  lea     r8, [rbp+plUbound]; plUbound
0x180025e49  mov     [rbp+plUbound], 0
0x180025e50  mov     edx, r14d; nDim
0x180025e53  mov     rcx, r12; psa
0x180025e56  call    cs:__imp_SafeArrayGetUBound
0x180025e5c  mov     ebx, eax
0x180025e5e  test    eax, eax
0x180025e60  js      loc_180025F7F
0x180025e66  mov     eax, [rbp+plLbound]
0x180025e69  lea     r8, [rbp+rgsabound]; rgsabound
0x180025e6d  mov     ecx, [rbp+plUbound]
0x180025e70  movzx   r13d, r15w
0x180025e74  sub     ecx, eax
0x180025e76  mov     [rbp+rgsabound.lLbound], eax
0x180025e79  add     ecx, r14d
0x180025e7c  mov     eax, 0DFFFh
0x180025e81  and     r13w, ax
0x180025e85  mov     [rbp+rgsabound.cElements], ecx
0x180025e88  movzx   ecx, r13w; vt
0x180025e8c  mov     edx, r14d; cDims
0x180025e8f  call    cs:__imp_SafeArrayCreate
0x180025e95  mov     r14, rax
0x180025e98  test    rax, rax
0x180025e9b  jnz     short loc_180025EA7
0x180025e9d  mov     eax, 80041006h
0x180025ea2  jmp     loc_180025F7F
0x180025ea7  mov     eax, [rbp+plLbound]
0x180025eaa  jmp     loc_180025F32
0x180025eaf  xorps   xmm0, xmm0
0x180025eb2  lea     rcx, [rbp+pvarg]; pvarg
0x180025eb6  xor     eax, eax
0x180025eb8  movups  xmmword ptr [rbp+pvarg], xmm0
0x180025ebc  mov     qword ptr [rbp+pvarg+10h], rax
0x180025ec0  call    cs:__imp_VariantInit
0x180025ec6  movzx   eax, word ptr [rdi]
0x180025ec9  lea     r8, [rbp+pvarg+8]; pv
0x180025ecd  mov     ecx, 0DFFFh
0x180025ed2  lea     rdx, [rbp+rgIndices]; rgIndices
0x180025ed6  and     ax, cx
0x180025ed9  mov     rcx, r12; psa
0x180025edc  mov     word ptr [rbp+pvarg], ax
0x180025ee0  call    cs:__imp_SafeArrayGetElement
0x180025ee6  xor     r8d, r8d; wFlags
0x180025ee9  lea     rdx, [rbp+pvarg]; pvarSrc
0x180025eed  movzx   r9d, r13w; vt
0x180025ef1  lea     rcx, [rbp+pvarg]; pvargDest
0x180025ef5  call    cs:__imp_VariantChangeType
0x180025efb  mov     ebx, eax
0x180025efd  test    eax, eax
0x180025eff  js      short loc_180025F1F
0x180025f01  cmp     word ptr [rbp+pvarg], 8
0x180025f06  lea     rdx, [rbp+rgIndices]; rgIndices
0x180025f0a  mov     r8, qword ptr [rbp+pvarg+8]
0x180025f0e  mov     rcx, r14; psa
0x180025f11  jz      short loc_180025F17
0x180025f13  lea     r8, [rbp+pvarg+8]; pv
0x180025f17  call    cs:__imp_SafeArrayPutElement
0x180025f1d  mov     ebx, eax
0x180025f1f  lea     rcx, [rbp+pvarg]; pvarg
0x180025f23  call    cs:__imp_VariantClear
0x180025f29  mov     eax, [rbp+rgIndices]
0x180025f2c  test    ebx, ebx
0x180025f2e  js      short loc_180025F42
0x180025f30  inc     eax
0x180025f32  mov     ecx, [rbp+plUbound]
0x180025f35  mov     [rbp+rgIndices], eax
0x180025f38  cmp     eax, ecx
0x180025f3a  jle     loc_180025EAF
0x180025f40  jmp     short loc_180025F45
0x180025f42  mov     ecx, [rbp+plUbound]
0x180025f45  cmp     ecx, eax
0x180025f47  jge     short loc_180025F63
0x180025f49  xor     ebx, ebx
0x180025f4b  cmp     rsi, rdi
0x180025f4e  jnz     short loc_180025F59
0x180025f50  mov     rcx, rdi; pvarg
0x180025f53  call    cs:__imp_VariantClear
0x180025f59  mov     [rsi], r15w
0x180025f5d  mov     [rsi+8], r14
0x180025f61  jmp     short loc_180025F7D
0x180025f63  mov     rcx, r14; psa
0x180025f66  call    cs:__imp_SafeArrayDestroy
0x180025f6c  jmp     short loc_180025F7D
0x180025f6e  mov     r8d, r14d; wFlags
0x180025f71  movzx   r9d, r15w; vt
0x180025f75  call    cs:__imp_VariantChangeType
0x180025f7b  mov     ebx, eax
0x180025f7d  mov     eax, ebx
0x180025f7f  mov     rbx, [rsp+50h+arg_0]
0x180025f87  add     rsp, 50h
0x180025f8b  pop     r15
0x180025f8d  pop     r14
0x180025f8f  pop     r13
0x180025f91  pop     r12
0x180025f93  pop     rdi
0x180025f94  pop     rsi
0x180025f95  pop     rbp
0x180025f96  retn
```
