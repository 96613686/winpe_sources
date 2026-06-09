# CUnnamedArguments::Create(long,ushort const * *,CUnnamedArguments * *)

- ea: `0x140013218`
- end: `0x1400133ae`
- name: `?Create@CUnnamedArguments@@SAJJPEAPEBGPEAPEAV1@@Z`
- size: `406`
- prototype: `__int64 __fastcall(int, const unsigned __int16 **, struct CUnnamedArguments **)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140012d54`

## callees

- `0x140001008`
- `0x140013218`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140013337`
- `OLEAUT32!__imp_SysAllocString` at `0x140013337`
- `OLEAUT32!__imp_VariantClear` at `0x14001335e`
- `OLEAUT32!__imp_VariantClear` at `0x14001335e`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1400132fc`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1400132fc`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140013352`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140013352`

## pseudocode

```c
__int64 __fastcall CUnnamedArguments::Create(int a1, const unsigned __int16 **a2, SAFEARRAY ***a3)
{
  HRESULT v3; // ebx
  SAFEARRAY **v7; // rax
  SAFEARRAY **v8; // rdi
  signed int v9; // esi
  int i; // edx
  int v11; // eax
  SAFEARRAY *v12; // rax
  LONG v13; // edx
  int v14; // r14d
  const OLECHAR *v15; // rcx
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-28h] BYREF
  VARIANTARG pv; // [rsp+28h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+A8h] [rbp+60h] BYREF

  v3 = 0;
  rgsabound = 0;
  rgIndices = 0;
  memset(&pv, 0, sizeof(pv));
  v7 = (SAFEARRAY **)operator new(0x50u);
  v8 = v7;
  if ( v7 )
  {
    v7[2] = (SAFEARRAY *)&CUnknown::`vftable';
    v7[5] = (SAFEARRAY *)&CUnknown::InnerUnknown::`vftable';
    *((_DWORD *)v7 + 12) = 1;
    v7[3] = (SAFEARRAY *)(v7 + 5);
    v7[4] = (SAFEARRAY *)v7;
    _InterlockedAdd(&Global::g_cObjects, 1u);
    *((_BYTE *)v7 + 64) = 0;
    v7[7] = (SAFEARRAY *)&TaUser_DescCUnnamedArguments;
    *v7 = (SAFEARRAY *)&CUnnamedArguments::`vftable'{for `IWSHUnnamedArguments'};
    v7[1] = (SAFEARRAY *)&CUnnamedArguments::`vftable'{for `IProvideClassInfo'};
    v7[2] = (SAFEARRAY *)&CUnnamedArguments::`vftable'{for `CDispatch'};
    v9 = 0;
    v7[9] = 0;
    for ( i = 0; i < a1; v9 = v11 )
    {
      v11 = v9 + 1;
      if ( *a2[i] == 47 )
        v11 = v9;
      ++i;
    }
    rgsabound.lLbound = 0;
    rgsabound.cElements = v9;
    v12 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    v8[9] = v12;
    if ( v12 )
    {
      rgIndices = 0;
      v13 = 0;
      if ( a1 > 0 )
      {
        v14 = 0;
        while ( v13 < v9 )
        {
          v15 = a2[v14];
          if ( *v15 != 47 )
          {
            pv.vt = 8;
            pv.llVal = (LONGLONG)SysAllocString(v15);
            if ( !pv.llVal )
              goto LABEL_16;
            v3 = SafeArrayPutElement(v8[9], &rgIndices, &pv);
            VariantClear(&pv);
            if ( v3 < 0 )
              goto LABEL_17;
            v13 = ++rgIndices;
            v3 = 0;
          }
          if ( ++v14 >= a1 )
            break;
        }
      }
      *a3 = v8;
    }
    else
    {
LABEL_16:
      v3 = -2147024882;
LABEL_17:
      ((void (__fastcall *)(SAFEARRAY **))(*v8)->pvData)(v8);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140013218  push    rbp
0x14001321a  push    rbx
0x14001321b  push    rsi
0x14001321c  push    rdi
0x14001321d  push    r12
0x14001321f  push    r13
0x140013221  push    r14
0x140013223  push    r15
0x140013225  mov     rbp, rsp
0x140013228  sub     rsp, 48h
0x14001322c  xor     ebx, ebx
0x14001322e  mov     r15d, ecx
0x140013231  xorps   xmm0, xmm0
0x140013234  mov     qword ptr [rbp+rgsabound.cElements], rbx
0x140013238  xor     eax, eax
0x14001323a  mov     [rbp+rgIndices], ebx
0x14001323d  mov     r12, r8
0x140013240  mov     [rbp+var_10], rax
0x140013244  lea     ecx, [rbx+50h]; Size
0x140013247  mov     r13, rdx
0x14001324a  movups  [rbp+pv], xmm0
0x14001324e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140013253  mov     rdi, rax
0x140013256  test    rax, rax
0x140013259  jz      loc_140013396
0x14001325f  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x140013266  mov     [rdi+10h], rax
0x14001326a  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x140013271  lea     rax, [rdi+28h]
0x140013275  mov     [rax], rcx
0x140013278  lea     r9d, [rbx+1]
0x14001327c  mov     [rax+8], r9d
0x140013280  mov     [rdi+18h], rax
0x140013284  mov     [rdi+20h], rdi
0x140013288  lock add cs:?g_cObjects@Global@@2JA, r9d; long Global::g_cObjects
0x140013290  mov     [rdi+40h], bl
0x140013293  lea     rax, ?TaUser_DescCUnnamedArguments@@3UTaDescDispatch@@A; TaDescDispatch TaUser_DescCUnnamedArguments
0x14001329a  mov     [rdi+38h], rax
0x14001329e  lea     rax, ??_7CUnnamedArguments@@6BIWSHUnnamedArguments@@@; const CUnnamedArguments::`vftable'{for `IWSHUnnamedArguments'}
0x1400132a5  mov     [rdi], rax
0x1400132a8  lea     rax, ??_7CUnnamedArguments@@6BIProvideClassInfo@@@; const CUnnamedArguments::`vftable'{for `IProvideClassInfo'}
0x1400132af  mov     [rdi+8], rax
0x1400132b3  lea     rax, ??_7CUnnamedArguments@@6BCDispatch@@@; const CUnnamedArguments::`vftable'{for `CDispatch'}
0x1400132ba  mov     [rdi+10h], rax
0x1400132be  mov     esi, ebx
0x1400132c0  mov     [rdi+48h], rbx
0x1400132c4  mov     edx, ebx
0x1400132c6  lea     r8d, [rbx+2Fh]
0x1400132ca  test    r15d, r15d
0x1400132cd  jle     short loc_1400132EA
0x1400132cf  mov     eax, edx
0x1400132d1  mov     rcx, [r13+rax*8+0]
0x1400132d6  lea     eax, [rsi+1]
0x1400132d9  cmp     r8w, [rcx]
0x1400132dd  cmovz   eax, esi
0x1400132e0  add     edx, r9d
0x1400132e3  mov     esi, eax
0x1400132e5  cmp     edx, r15d
0x1400132e8  jl      short loc_1400132CF
0x1400132ea  mov     ecx, 0Ch; vt
0x1400132ef  mov     [rbp+rgsabound.lLbound], ebx
0x1400132f2  lea     r8, [rbp+rgsabound]; rgsabound
0x1400132f6  mov     [rbp+rgsabound.cElements], esi
0x1400132f9  mov     edx, r9d; cDims
0x1400132fc  call    cs:__imp_SafeArrayCreate
0x140013302  mov     [rdi+48h], rax
0x140013306  test    rax, rax
0x140013309  jz      short loc_140013380
0x14001330b  mov     [rbp+rgIndices], ebx
0x14001330e  mov     edx, ebx
0x140013310  test    r15d, r15d
0x140013313  jle     short loc_14001337A
0x140013315  mov     r14d, ebx
0x140013318  cmp     edx, esi
0x14001331a  jge     short loc_14001337A
0x14001331c  mov     eax, r14d
0x14001331f  mov     rcx, [r13+rax*8+0]; psz
0x140013324  mov     eax, 2Fh ; '/'
0x140013329  cmp     ax, [rcx]
0x14001332c  jz      short loc_140013372
0x14001332e  mov     eax, 8
0x140013333  mov     word ptr [rbp+pv], ax
0x140013337  call    cs:__imp_SysAllocString
0x14001333d  mov     qword ptr [rbp+pv+8], rax
0x140013341  test    rax, rax
0x140013344  jz      short loc_140013380
0x140013346  mov     rcx, [rdi+48h]; psa
0x14001334a  lea     r8, [rbp+pv]; pv
0x14001334e  lea     rdx, [rbp+rgIndices]; rgIndices
0x140013352  call    cs:__imp_SafeArrayPutElement
0x140013358  lea     rcx, [rbp+pv]; pvarg
0x14001335c  mov     ebx, eax
0x14001335e  call    cs:__imp_VariantClear
0x140013364  test    ebx, ebx
0x140013366  js      short loc_140013385
0x140013368  mov     edx, [rbp+rgIndices]
0x14001336b  inc     edx
0x14001336d  mov     [rbp+rgIndices], edx
0x140013370  xor     ebx, ebx
0x140013372  inc     r14d
0x140013375  cmp     r14d, r15d
0x140013378  jl      short loc_140013318
0x14001337a  mov     [r12], rdi
0x14001337e  jmp     short loc_14001339B
0x140013380  mov     ebx, 8007000Eh
0x140013385  mov     rax, [rdi]
0x140013388  mov     rcx, rdi
0x14001338b  mov     rax, [rax+10h]
0x14001338f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013394  jmp     short loc_14001339B
0x140013396  mov     ebx, 8007000Eh
0x14001339b  mov     eax, ebx
0x14001339d  add     rsp, 48h
0x1400133a1  pop     r15
0x1400133a3  pop     r14
0x1400133a5  pop     r13
0x1400133a7  pop     r12
0x1400133a9  pop     rdi
0x1400133aa  pop     rsi
0x1400133ab  pop     rbx
0x1400133ac  pop     rbp
0x1400133ad  retn
```
