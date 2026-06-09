# CNamedArguments::Create(long,ushort const * *,CNamedArguments * *)

- ea: `0x140012f20`
- end: `0x140013210`
- name: `?Create@CNamedArguments@@SAJJPEAPEBGPEAPEAV1@@Z`
- size: `752`
- prototype: `__int64 __fastcall(int, const unsigned __int16 **, struct CNamedArguments **)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140012d54`

## callees

- `0x140001008`
- `0x140012f20`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140013162`
- `OLEAUT32!__imp_SysAllocString` at `0x140013162`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400130e8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400130e8`
- `OLEAUT32!__imp_VariantClear` at `0x140013121`
- `OLEAUT32!__imp_VariantClear` at `0x1400131b7`
- `OLEAUT32!__imp_VariantClear` at `0x140013121`
- `OLEAUT32!__imp_VariantClear` at `0x1400131b7`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140013024`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140013040`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140013024`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140013040`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140013115`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1400131ab`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x140013115`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1400131ab`

## pseudocode

```c
__int64 __fastcall CNamedArguments::Create(int a1, const unsigned __int16 **a2, SAFEARRAY ***a3)
{
  const unsigned __int16 **v4; // rbx
  SAFEARRAY **v5; // rax
  SAFEARRAY **v6; // rdi
  signed int v7; // r14d
  __int64 v8; // rdx
  int v9; // eax
  SAFEARRAY *v10; // rax
  SAFEARRAY *v11; // rax
  LONG v12; // ecx
  __int64 v13; // r12
  const unsigned __int16 *v14; // rdx
  const OLECHAR *v15; // r9
  UINT v16; // r8d
  unsigned __int16 v17; // cx
  const OLECHAR *v18; // r15
  int v19; // esi
  unsigned __int16 *v20; // rdx
  HRESULT v21; // ebx
  int v22; // esi
  SHORT v23; // ax
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-30h] BYREF
  BSTR v26; // [rsp+28h] [rbp-28h]
  VARIANTARG pv; // [rsp+30h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+A8h] [rbp+58h] BYREF

  rgsabound = 0;
  rgIndices = 0;
  v4 = a2;
  memset(&pv, 0, sizeof(pv));
  v5 = (SAFEARRAY **)operator new(0x58u);
  v6 = v5;
  if ( v5 )
  {
    v5[2] = (SAFEARRAY *)&CUnknown::`vftable';
    v5[5] = (SAFEARRAY *)&CUnknown::InnerUnknown::`vftable';
    *((_DWORD *)v5 + 12) = 1;
    v5[3] = (SAFEARRAY *)(v5 + 5);
    v5[4] = (SAFEARRAY *)v5;
    _InterlockedAdd(&Global::g_cObjects, 1u);
    *((_BYTE *)v5 + 64) = 0;
    v5[7] = (SAFEARRAY *)&TaUser_DescCNamedArguments;
    v5[9] = 0;
    *v5 = (SAFEARRAY *)&CNamedArguments::`vftable'{for `IWSHNamedArguments'};
    v7 = 0;
    v5[10] = 0;
    v5[1] = (SAFEARRAY *)&CUnnamedArguments::`vftable'{for `IProvideClassInfo'};
    v8 = 0;
    for ( v5[2] = (SAFEARRAY *)&CNamedArguments::`vftable'{for `CDispatch'}; (int)v8 < a1; v7 = v9 )
    {
      v9 = v7 + 1;
      if ( *v4[v8] != 47 )
        v9 = v7;
      v8 = (unsigned int)(v8 + 1);
    }
    rgsabound.lLbound = 0;
    rgsabound.cElements = v7;
    v10 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    v6[9] = v10;
    if ( v10 && (v11 = SafeArrayCreate(0xCu, 1u, &rgsabound), (v6[10] = v11) != 0) )
    {
      v12 = 0;
      rgIndices = 0;
      if ( a1 > 0 )
      {
        v13 = 0;
        while ( v12 < v7 )
        {
          v14 = v4[v13];
          if ( *v14 == 47 )
          {
            v15 = v14 + 1;
            v16 = 0;
            v17 = v14[1];
            v18 = v14 + 1;
            v19 = 0;
            while ( v17 )
            {
              v20 = (unsigned __int16 *)(v18 + 1);
              if ( v17 == 58 )
              {
                v19 = 1;
                ++v18;
                break;
              }
              if ( !*v20 && ((v17 - 43) & 0xFFFD) == 0 )
              {
                v19 = 2;
                break;
              }
              v17 = *v20;
              ++v16;
              ++v18;
            }
            pv.vt = 8;
            v26 = SysAllocStringLen(v15, v16);
            pv.llVal = (LONGLONG)v26;
            if ( !v26 )
              goto LABEL_31;
            v21 = SafeArrayPutElement(v6[9], &rgIndices, &pv);
            VariantClear(&pv);
            if ( v21 < 0 )
              goto LABEL_32;
            if ( v19 )
            {
              v22 = v19 - 1;
              if ( v22 )
              {
                if ( v22 == 1 )
                {
                  pv.vt = 11;
                  if ( *v18 == 43 )
                    v23 = -1;
                  else
                    v23 = 0;
                  pv.iVal = v23;
                }
              }
              else
              {
                pv.vt = 8;
                v26 = SysAllocString(v18);
                pv.llVal = (LONGLONG)v26;
                if ( !v26 )
                  goto LABEL_31;
              }
            }
            else
            {
              pv.vt = 0;
            }
            v21 = SafeArrayPutElement(v6[10], &rgIndices, &pv);
            VariantClear(&pv);
            if ( v21 < 0 )
              goto LABEL_32;
            v4 = a2;
            v12 = ++rgIndices;
          }
          v13 = (unsigned int)(v13 + 1);
          if ( (int)v13 >= a1 )
            break;
        }
      }
      v21 = 0;
      *a3 = v6;
    }
    else
    {
LABEL_31:
      v21 = -2147024882;
LABEL_32:
      ((void (__fastcall *)(SAFEARRAY **))(*v6)->pvData)(v6);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x140012f20  mov     [rsp-38h+arg_0], rbx
0x140012f25  mov     [rsp-38h+arg_10], r8
0x140012f2a  mov     [rsp-38h+arg_8], rdx
0x140012f2f  push    rbp
0x140012f30  push    rsi
0x140012f31  push    rdi
0x140012f32  push    r12
0x140012f34  push    r13
0x140012f36  push    r14
0x140012f38  push    r15
0x140012f3a  mov     rbp, rsp
0x140012f3d  sub     rsp, 50h
0x140012f41  xor     eax, eax
0x140012f43  mov     qword ptr [rbp+rgsabound.cElements], 0
0x140012f4b  mov     r13d, ecx
0x140012f4e  mov     [rbp+var_10], rax
0x140012f52  xorps   xmm0, xmm0
0x140012f55  mov     [rbp+rgIndices], eax
0x140012f58  mov     rbx, rdx
0x140012f5b  lea     ecx, [rax+58h]; Size
0x140012f5e  movups  [rbp+pv], xmm0
0x140012f62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012f67  mov     rdi, rax
0x140012f6a  test    rax, rax
0x140012f6d  jz      loc_1400131F1
0x140012f73  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x140012f7a  mov     esi, 1
0x140012f7f  mov     [rdi+10h], rax
0x140012f83  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x140012f8a  lea     rax, [rdi+28h]
0x140012f8e  mov     [rax], rcx
0x140012f91  mov     [rax+8], esi
0x140012f94  mov     [rdi+18h], rax
0x140012f98  mov     [rdi+20h], rdi
0x140012f9c  lock add cs:?g_cObjects@Global@@2JA, esi; long Global::g_cObjects
0x140012fa3  mov     byte ptr [rdi+40h], 0
0x140012fa7  lea     rax, ?TaUser_DescCNamedArguments@@3UTaDescDispatch@@A; TaDescDispatch TaUser_DescCNamedArguments
0x140012fae  mov     [rdi+38h], rax
0x140012fb2  lea     r8d, [rsi+2Eh]
0x140012fb6  lea     rax, ??_7CNamedArguments@@6BIWSHNamedArguments@@@; const CNamedArguments::`vftable'{for `IWSHNamedArguments'}
0x140012fbd  mov     qword ptr [rdi+48h], 0
0x140012fc5  mov     [rdi], rax
0x140012fc8  xor     r14d, r14d
0x140012fcb  lea     rax, ??_7CUnnamedArguments@@6BIProvideClassInfo@@@; const CUnnamedArguments::`vftable'{for `IProvideClassInfo'}
0x140012fd2  mov     qword ptr [rdi+50h], 0
0x140012fda  mov     [rdi+8], rax
0x140012fde  xor     edx, edx
0x140012fe0  lea     rax, ??_7CNamedArguments@@6BCDispatch@@@; const CNamedArguments::`vftable'{for `CDispatch'}
0x140012fe7  mov     [rdi+10h], rax
0x140012feb  test    r13d, r13d
0x140012fee  jle     short loc_14001300A
0x140012ff0  mov     rcx, [rbx+rdx*8]
0x140012ff4  lea     eax, [r14+1]
0x140012ff8  cmp     r8w, [rcx]
0x140012ffc  cmovnz  eax, r14d
0x140013000  add     edx, esi
0x140013002  mov     r14d, eax
0x140013005  cmp     edx, r13d
0x140013008  jl      short loc_140012FF0
0x14001300a  mov     r15d, 0Ch
0x140013010  mov     [rbp+rgsabound.lLbound], 0
0x140013017  mov     ecx, r15d; vt
0x14001301a  mov     [rbp+rgsabound.cElements], r14d
0x14001301e  lea     r8, [rbp+rgsabound]; rgsabound
0x140013022  mov     edx, esi; cDims
0x140013024  call    cs:__imp_SafeArrayCreate
0x14001302a  mov     [rdi+48h], rax
0x14001302e  test    rax, rax
0x140013031  jz      loc_140013183
0x140013037  mov     ecx, r15d; vt
0x14001303a  lea     r8, [rbp+rgsabound]; rgsabound
0x14001303e  mov     edx, esi; cDims
0x140013040  call    cs:__imp_SafeArrayCreate
0x140013046  mov     [rdi+50h], rax
0x14001304a  test    rax, rax
0x14001304d  jz      loc_140013183
0x140013053  xor     ecx, ecx
0x140013055  mov     [rbp+rgIndices], ecx
0x140013058  test    r13d, r13d
0x14001305b  jle     loc_1400131E6
0x140013061  xor     r12d, r12d
0x140013064  lea     r10d, [r15+1Fh]
0x140013068  lea     r11d, [r15-4]
0x14001306c  cmp     ecx, r14d
0x14001306f  jge     loc_1400131E6
0x140013075  mov     rdx, [rbx+r12*8]
0x140013079  mov     eax, 2Fh ; '/'
0x14001307e  cmp     ax, [rdx]
0x140013081  jnz     loc_1400131DA
0x140013087  lea     r9, [rdx+2]
0x14001308b  xor     r8d, r8d
0x14001308e  movzx   ecx, word ptr [r9]
0x140013092  mov     r15, r9
0x140013095  xor     esi, esi
0x140013097  jmp     short loc_1400130C5
0x140013099  mov     eax, 3Ah ; ':'
0x14001309e  lea     rdx, [r15+2]
0x1400130a2  cmp     ax, cx
0x1400130a5  jz      short loc_1400130D5
0x1400130a7  xor     eax, eax
0x1400130a9  cmp     ax, [rdx]
0x1400130ac  jnz     short loc_1400130BC
0x1400130ae  sub     cx, r10w
0x1400130b2  mov     eax, 0FFFDh
0x1400130b7  test    ax, cx
0x1400130ba  jz      short loc_1400130CE
0x1400130bc  movzx   ecx, word ptr [rdx]
0x1400130bf  inc     r8d
0x1400130c2  mov     r15, rdx
0x1400130c5  xor     eax, eax
0x1400130c7  cmp     ax, cx
0x1400130ca  jnz     short loc_140013099
0x1400130cc  jmp     short loc_1400130DD
0x1400130ce  mov     esi, 2
0x1400130d3  jmp     short loc_1400130DD
0x1400130d5  mov     esi, 1
0x1400130da  mov     r15, rdx
0x1400130dd  mov     edx, r8d; ui
0x1400130e0  mov     word ptr [rbp+pv], r11w
0x1400130e5  mov     rcx, r9; strIn
0x1400130e8  call    cs:__imp_SysAllocStringLen
0x1400130ee  mov     [rbp+var_28], rax
0x1400130f2  mov     ecx, dword ptr [rbp+var_28+2]
0x1400130f5  mov     dword ptr [rbp+pv+0Ah], ecx
0x1400130f8  movzx   ecx, word ptr [rbp+var_28+6]
0x1400130fc  mov     word ptr [rbp+pv+0Eh], cx
0x140013100  mov     word ptr [rbp+pv+8], ax
0x140013104  test    rax, rax
0x140013107  jz      short loc_140013183
0x140013109  mov     rcx, [rdi+48h]; psa
0x14001310d  lea     r8, [rbp+pv]; pv
0x140013111  lea     rdx, [rbp+rgIndices]; rgIndices
0x140013115  call    cs:__imp_SafeArrayPutElement
0x14001311b  lea     rcx, [rbp+pv]; pvarg
0x14001311f  mov     ebx, eax
0x140013121  call    cs:__imp_VariantClear
0x140013127  test    ebx, ebx
0x140013129  js      short loc_140013188
0x14001312b  test    esi, esi
0x14001312d  jz      short loc_140013199
0x14001312f  sub     esi, 1
0x140013132  jz      short loc_140013156
0x140013134  cmp     esi, 1
0x140013137  jnz     short loc_14001319F
0x140013139  lea     eax, [rsi+0Ah]
0x14001313c  mov     word ptr [rbp+pv], ax
0x140013140  lea     eax, [rsi+2Ah]
0x140013143  cmp     ax, [r15]
0x140013147  jnz     short loc_14001314E
0x140013149  or      eax, 0FFFFFFFFh
0x14001314c  jmp     short loc_140013150
0x14001314e  xor     eax, eax
0x140013150  mov     word ptr [rbp+pv+8], ax
0x140013154  jmp     short loc_14001319F
0x140013156  mov     eax, 8
0x14001315b  mov     rcx, r15; psz
0x14001315e  mov     word ptr [rbp+pv], ax
0x140013162  call    cs:__imp_SysAllocString
0x140013168  mov     [rbp+var_28], rax
0x14001316c  mov     ecx, dword ptr [rbp+var_28+2]
0x14001316f  mov     dword ptr [rbp+pv+0Ah], ecx
0x140013172  movzx   ecx, word ptr [rbp+var_28+6]
0x140013176  mov     word ptr [rbp+pv+0Eh], cx
0x14001317a  mov     word ptr [rbp+pv+8], ax
0x14001317e  test    rax, rax
0x140013181  jnz     short loc_14001319F
0x140013183  mov     ebx, 8007000Eh
0x140013188  mov     rax, [rdi]
0x14001318b  mov     rcx, rdi
0x14001318e  mov     rax, [rax+10h]
0x140013192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013197  jmp     short loc_1400131F6
0x140013199  xor     eax, eax
0x14001319b  mov     word ptr [rbp+pv], ax
0x14001319f  mov     rcx, [rdi+50h]; psa
0x1400131a3  lea     r8, [rbp+pv]; pv
0x1400131a7  lea     rdx, [rbp+rgIndices]; rgIndices
0x1400131ab  call    cs:__imp_SafeArrayPutElement
0x1400131b1  lea     rcx, [rbp+pv]; pvarg
0x1400131b5  mov     ebx, eax
0x1400131b7  call    cs:__imp_VariantClear
0x1400131bd  test    ebx, ebx
0x1400131bf  js      short loc_140013188
0x1400131c1  mov     ecx, [rbp+rgIndices]
0x1400131c4  mov     esi, 1
0x1400131c9  mov     rbx, [rbp+arg_8]
0x1400131cd  add     ecx, esi
0x1400131cf  mov     [rbp+rgIndices], ecx
0x1400131d2  lea     r10d, [rsi+2Ah]
0x1400131d6  lea     r11d, [rsi+7]
0x1400131da  add     r12d, esi
0x1400131dd  cmp     r12d, r13d
0x1400131e0  jl      loc_14001306C
0x1400131e6  mov     rax, [rbp+arg_10]
0x1400131ea  xor     ebx, ebx
0x1400131ec  mov     [rax], rdi
0x1400131ef  jmp     short loc_1400131F6
0x1400131f1  mov     ebx, 8007000Eh
0x1400131f6  mov     eax, ebx
0x1400131f8  mov     rbx, [rsp+50h+arg_0]
0x140013200  add     rsp, 50h
0x140013204  pop     r15
0x140013206  pop     r14
0x140013208  pop     r13
0x14001320a  pop     r12
0x14001320c  pop     rdi
0x14001320d  pop     rsi
0x14001320e  pop     rbp
0x14001320f  retn
```
