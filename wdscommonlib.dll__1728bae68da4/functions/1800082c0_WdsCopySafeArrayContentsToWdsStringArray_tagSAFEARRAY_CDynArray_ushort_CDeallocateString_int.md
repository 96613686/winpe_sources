# WdsCopySafeArrayContentsToWdsStringArray(tagSAFEARRAY *,CDynArray<ushort *,CDeallocateString> *,int)

- ea: `0x1800082c0`
- end: `0x180008532`
- name: `?WdsCopySafeArrayContentsToWdsStringArray@@YAKPEAUtagSAFEARRAY@@PEAV?$CDynArray@PEAGVCDeallocateString@@@@H@Z`
- size: `626`
- prototype: `__int64 __fastcall(SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180007ed0`

## callees

- `0x180002158`
- `0x180007078`
- `0x1800073a0`
- `0x1800082c0`
- `0x180008878`
- `0x180008974`
- `0x180017330`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800084d6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800084f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800084d6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800084f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000849c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000850b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000849c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000850b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000838f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000838f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800083b7`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800083b7`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800083cd`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800083cd`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180008418`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180008418`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18000830e`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18000830e`

## pseudocode

```c
__int64 __fastcall WdsCopySafeArrayContentsToWdsStringArray(SAFEARRAY *psa, __int64 a2, int a3)
{
  int v3; // ebx
  unsigned __int16 *v4; // rsi
  HRESULT Vartype; // edi
  __int64 v9; // rdx
  __int64 v10; // r8
  SAFEARRAY **v11; // rax
  SAFEARRAY **v12; // rdi
  unsigned int v13; // r13d
  LONG v14; // r12d
  SAFEARRAY *v15; // rcx
  HRESULT Element; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  LONG plLbound; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v25; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int16 *pv; // [rsp+30h] [rbp-10h] BYREF
  VARTYPE pvt; // [rsp+80h] [rbp+40h] BYREF
  __int64 v28; // [rsp+88h] [rbp+48h]
  LONG plUbound; // [rsp+98h] [rbp+58h] BYREF

  v28 = a2;
  v3 = 0;
  v4 = 0;
  pv = 0;
  v25 = 0;
  pvt = 13;
  if ( psa && a2 )
  {
    Vartype = SafeArrayGetVartype(psa, &pvt);
    if ( (int)ElValidateHr_0(Vartype, v9, v10, 0x59Cu) < 0 )
    {
      if ( Vartype < 0 && (Vartype & 0x1FFF0000) == 0x70000 )
        v3 = (unsigned __int16)Vartype;
      else
        v3 = Vartype;
      goto LABEL_33;
    }
    if ( pvt != 8 )
    {
      v3 = 87;
      goto LABEL_33;
    }
    v11 = (SAFEARRAY **)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v11;
    if ( !v11 )
    {
      v3 = 8;
      goto LABEL_33;
    }
    *v11 = 0;
    plUbound = 0;
    plLbound = 0;
    *v11 = psa;
    SafeArrayGetUBound(psa, 1u, &plUbound);
    SafeArrayGetLBound(*v12, 1u, &plLbound);
    v13 = plUbound - plLbound + 1;
    if ( !a3 )
      CDynArray<unsigned short *,CDeallocateString>::Clear(a2);
    v14 = 0;
    if ( v13 )
    {
      while ( 1 )
      {
        v15 = *v12;
        plUbound = v14;
        Element = SafeArrayGetElement(v15, &plUbound, &pv);
        v3 = Element;
        if ( Element < 0 && (Element & 0x1FFF0000) == 0x70000 )
          v3 = (unsigned __int16)Element;
        if ( (unsigned int)ElValidateWin32_1(v3, v17, v18, 0x5C8u) )
          break;
        v3 = WcsDupHr(pv, &v25);
        if ( (int)ElValidateHr_0(v3, v19, v20, 0x5CBu) < 0 )
        {
          if ( v3 < 0 && (v3 & 0x1FFF0000) == 0x70000 )
            v3 = (unsigned __int16)v3;
          v4 = v25;
          break;
        }
        v4 = v25;
        v3 = CDynArray<unsigned short *,CDeallocateString>::AddItem(v28, v25);
        if ( !(unsigned int)ElValidateWin32_1(v3, v21, v22, 0x5CEu) )
        {
          v4 = 0;
          v25 = 0;
          if ( pv )
          {
            SysFreeString(pv);
            pv = 0;
          }
          if ( ++v14 < v13 )
            continue;
        }
        break;
      }
    }
    *v12 = 0;
    operator delete(v12);
  }
  else
  {
    v3 = 87;
  }
  if ( v4 )
    operator delete(v4);
LABEL_33:
  if ( pv )
    SysFreeString(pv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800082c0  mov     [rsp-38h+arg_10], rbx
0x1800082c5  mov     [rsp-38h+arg_8], rdx
0x1800082ca  push    rbp
0x1800082cb  push    rsi
0x1800082cc  push    rdi
0x1800082cd  push    r12
0x1800082cf  push    r13
0x1800082d1  push    r14
0x1800082d3  push    r15
0x1800082d5  mov     rbp, rsp
0x1800082d8  sub     rsp, 40h
0x1800082dc  xor     ebx, ebx
0x1800082de  xor     esi, esi
0x1800082e0  and     [rbp+pv], rbx
0x1800082e4  mov     r12d, r8d
0x1800082e7  mov     [rbp+var_18], rsi
0x1800082eb  mov     r15, rdx
0x1800082ee  mov     r14, rcx
0x1800082f1  lea     eax, [rbx+0Dh]
0x1800082f4  mov     [rbp+pvt], ax
0x1800082f8  test    rcx, rcx
0x1800082fb  jz      loc_1800084E9
0x180008301  test    rdx, rdx
0x180008304  jz      loc_1800084E9
0x18000830a  lea     rdx, [rbp+pvt]; pvt
0x18000830e  call    cs:__imp_SafeArrayGetVartype
0x180008315  nop     dword ptr [rax+rax+00h]
0x18000831a  mov     ecx, eax
0x18000831c  mov     r9d, 59Ch
0x180008322  mov     edi, eax
0x180008324  call    ElValidateHr_0
0x180008329  test    eax, eax
0x18000832b  jns     short loc_180008356
0x18000832d  test    edi, edi
0x18000832f  jns     short loc_18000834F
0x180008331  mov     eax, edi
0x180008333  mov     r14d, 1FFF0000h
0x180008339  and     eax, r14d
0x18000833c  mov     r15d, 70000h
0x180008342  cmp     eax, r15d
0x180008345  jnz     short loc_18000834F
0x180008347  movzx   ebx, di
0x18000834a  jmp     loc_180008502
0x18000834f  mov     ebx, edi
0x180008351  jmp     loc_180008502
0x180008356  mov     r13d, 8
0x18000835c  cmp     [rbp+pvt], r13w
0x180008361  jz      short loc_18000836C
0x180008363  lea     ebx, [r13+4Fh]
0x180008367  jmp     loc_180008502
0x18000836c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008373  mov     rcx, r13; unsigned __int64
0x180008376  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000837b  mov     rdi, rax
0x18000837e  test    rax, rax
0x180008381  jz      loc_1800084E4
0x180008387  and     [rax], rbx
0x18000838a  mov     rcx, [rax]; psa
0x18000838d  jz      short loc_18000839E
0x18000838f  call    cs:__imp_SafeArrayDestroy
0x180008396  nop     dword ptr [rax+rax+00h]
0x18000839b  and     [rdi], rbx
0x18000839e  and     [rbp+plUbound], ebx
0x1800083a1  lea     r8, [rbp+plUbound]; plUbound
0x1800083a5  and     [rbp+plLbound], ebx
0x1800083a8  mov     r13d, 1
0x1800083ae  mov     edx, r13d; nDim
0x1800083b1  mov     [rdi], r14
0x1800083b4  mov     rcx, r14; psa
0x1800083b7  call    cs:__imp_SafeArrayGetUBound
0x1800083be  nop     dword ptr [rax+rax+00h]
0x1800083c3  mov     rcx, [rdi]; psa
0x1800083c6  lea     r8, [rbp+plLbound]; plLbound
0x1800083ca  mov     edx, r13d; nDim
0x1800083cd  call    cs:__imp_SafeArrayGetLBound
0x1800083d4  nop     dword ptr [rax+rax+00h]
0x1800083d9  mov     r13d, [rbp+plUbound]
0x1800083dd  sub     r13d, [rbp+plLbound]
0x1800083e1  inc     r13d
0x1800083e4  test    r12d, r12d
0x1800083e7  jnz     short loc_1800083F1
0x1800083e9  mov     rcx, r15
0x1800083ec  call    ?Clear@?$CDynArray@PEAGVCDeallocateString@@@@QEAAXXZ; CDynArray<ushort *,CDeallocateString>::Clear(void)
0x1800083f1  xor     r12d, r12d
0x1800083f4  test    r13d, r13d
0x1800083f7  jz      loc_1800084CF
0x1800083fd  mov     r14d, 1FFF0000h
0x180008403  mov     r15d, 70000h
0x180008409  mov     rcx, [rdi]; psa
0x18000840c  lea     r8, [rbp+pv]; pv
0x180008410  lea     rdx, [rbp+plUbound]; rgIndices
0x180008414  mov     [rbp+plUbound], r12d
0x180008418  call    cs:__imp_SafeArrayGetElement
0x18000841f  nop     dword ptr [rax+rax+00h]
0x180008424  mov     ebx, eax
0x180008426  test    eax, eax
0x180008428  jns     short loc_180008435
0x18000842a  and     eax, r14d
0x18000842d  cmp     eax, r15d
0x180008430  jnz     short loc_180008435
0x180008432  movzx   ebx, bx
0x180008435  mov     r9d, 5C8h
0x18000843b  mov     ecx, ebx
0x18000843d  call    ElValidateWin32_1
0x180008442  test    eax, eax
0x180008444  jnz     loc_1800084CF
0x18000844a  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18000844e  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180008452  call    ?WcsDupHr@@YAJPEBGPEAPEAG@Z; WcsDupHr(ushort const *,ushort * *)
0x180008457  mov     r9d, 5CBh
0x18000845d  mov     ecx, eax
0x18000845f  mov     ebx, eax
0x180008461  call    ElValidateHr_0
0x180008466  test    eax, eax
0x180008468  js      short loc_1800084BA
0x18000846a  mov     rsi, [rbp+var_18]
0x18000846e  mov     rcx, [rbp+arg_8]
0x180008472  mov     rdx, rsi
0x180008475  call    ?AddItem@?$CDynArray@PEAGVCDeallocateString@@@@QEAAKPEAG@Z; CDynArray<ushort *,CDeallocateString>::AddItem(ushort *)
0x18000847a  mov     r9d, 5CEh
0x180008480  mov     ecx, eax
0x180008482  mov     ebx, eax
0x180008484  call    ElValidateWin32_1
0x180008489  test    eax, eax
0x18000848b  jnz     short loc_1800084CF
0x18000848d  mov     rcx, [rbp+pv]; bstrString
0x180008491  xor     esi, esi
0x180008493  mov     [rbp+var_18], rsi
0x180008497  test    rcx, rcx
0x18000849a  jz      short loc_1800084AC
0x18000849c  call    cs:__imp_SysFreeString
0x1800084a3  nop     dword ptr [rax+rax+00h]
0x1800084a8  and     [rbp+pv], rsi
0x1800084ac  inc     r12d
0x1800084af  cmp     r12d, r13d
0x1800084b2  jb      loc_180008409
0x1800084b8  jmp     short loc_1800084CF
0x1800084ba  test    ebx, ebx
0x1800084bc  jns     short loc_1800084CB
0x1800084be  mov     eax, ebx
0x1800084c0  and     eax, r14d
0x1800084c3  cmp     eax, r15d
0x1800084c6  jnz     short loc_1800084CB
0x1800084c8  movzx   ebx, bx
0x1800084cb  mov     rsi, [rbp+var_18]
0x1800084cf  and     qword ptr [rdi], 0
0x1800084d3  mov     rcx, rdi
0x1800084d6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800084dd  nop     dword ptr [rax+rax+00h]
0x1800084e2  jmp     short loc_1800084EE
0x1800084e4  mov     ebx, r13d
0x1800084e7  jmp     short loc_180008502
0x1800084e9  mov     ebx, 57h ; 'W'
0x1800084ee  test    rsi, rsi
0x1800084f1  jz      short loc_180008502
0x1800084f3  mov     rcx, rsi
0x1800084f6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800084fd  nop     dword ptr [rax+rax+00h]
0x180008502  mov     rcx, [rbp+pv]; bstrString
0x180008506  test    rcx, rcx
0x180008509  jz      short loc_180008517
0x18000850b  call    cs:__imp_SysFreeString
0x180008512  nop     dword ptr [rax+rax+00h]
0x180008517  mov     eax, ebx
0x180008519  mov     rbx, [rsp+40h+arg_10]
0x180008521  add     rsp, 40h
0x180008525  pop     r15
0x180008527  pop     r14
0x180008529  pop     r13
0x18000852b  pop     r12
0x18000852d  pop     rdi
0x18000852e  pop     rsi
0x18000852f  pop     rbp
0x180008530  retn
```
