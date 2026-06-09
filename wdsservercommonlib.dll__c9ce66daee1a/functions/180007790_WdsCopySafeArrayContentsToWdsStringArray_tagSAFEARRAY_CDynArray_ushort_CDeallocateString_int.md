# WdsCopySafeArrayContentsToWdsStringArray(tagSAFEARRAY *,CDynArray<ushort *,CDeallocateString> *,int)

- ea: `0x180007790`
- end: `0x1800079f4`
- name: `?WdsCopySafeArrayContentsToWdsStringArray@@YAKPEAUtagSAFEARRAY@@PEAV?$CDynArray@PEAGVCDeallocateString@@@@H@Z`
- size: `612`
- prototype: `__int64 __fastcall(SAFEARRAY *psa)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800073a0`

## callees

- `0x1800017a8`
- `0x180006598`
- `0x18000689c`
- `0x180007790`
- `0x180007d30`
- `0x180007e2c`
- `0x1800165a0`
- `0x18002e468`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000796c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000796c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079cd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000785f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000785f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180007887`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180007887`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000789d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000789d`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800078e8`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800078e8`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800077de`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800077de`

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
0x180007790  mov     [rsp-38h+arg_10], rbx
0x180007795  mov     [rsp-38h+arg_8], rdx
0x18000779a  push    rbp
0x18000779b  push    rsi
0x18000779c  push    rdi
0x18000779d  push    r12
0x18000779f  push    r13
0x1800077a1  push    r14
0x1800077a3  push    r15
0x1800077a5  mov     rbp, rsp
0x1800077a8  sub     rsp, 40h
0x1800077ac  xor     ebx, ebx
0x1800077ae  xor     esi, esi
0x1800077b0  and     [rbp+pv], rbx
0x1800077b4  mov     r12d, r8d
0x1800077b7  mov     [rbp+var_18], rsi
0x1800077bb  mov     r15, rdx
0x1800077be  mov     r14, rcx
0x1800077c1  lea     eax, [rbx+0Dh]
0x1800077c4  mov     [rbp+pvt], ax
0x1800077c8  test    rcx, rcx
0x1800077cb  jz      loc_1800079B2
0x1800077d1  test    rdx, rdx
0x1800077d4  jz      loc_1800079B2
0x1800077da  lea     rdx, [rbp+pvt]; pvt
0x1800077de  call    cs:__imp_SafeArrayGetVartype
0x1800077e5  nop     dword ptr [rax+rax+00h]
0x1800077ea  mov     ecx, eax
0x1800077ec  mov     r9d, 59Ch
0x1800077f2  mov     edi, eax
0x1800077f4  call    ElValidateHr_0
0x1800077f9  test    eax, eax
0x1800077fb  jns     short loc_180007826
0x1800077fd  test    edi, edi
0x1800077ff  jns     short loc_18000781F
0x180007801  mov     eax, edi
0x180007803  mov     r14d, 1FFF0000h
0x180007809  and     eax, r14d
0x18000780c  mov     r15d, 70000h
0x180007812  cmp     eax, r15d
0x180007815  jnz     short loc_18000781F
0x180007817  movzx   ebx, di
0x18000781a  jmp     loc_1800079C4
0x18000781f  mov     ebx, edi
0x180007821  jmp     loc_1800079C4
0x180007826  mov     r13d, 8
0x18000782c  cmp     [rbp+pvt], r13w
0x180007831  jz      short loc_18000783C
0x180007833  lea     ebx, [r13+4Fh]
0x180007837  jmp     loc_1800079C4
0x18000783c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007843  mov     rcx, r13; unsigned __int64
0x180007846  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000784b  mov     rdi, rax
0x18000784e  test    rax, rax
0x180007851  jz      loc_1800079AD
0x180007857  and     [rax], rbx
0x18000785a  mov     rcx, [rax]; psa
0x18000785d  jz      short loc_18000786E
0x18000785f  call    cs:__imp_SafeArrayDestroy
0x180007866  nop     dword ptr [rax+rax+00h]
0x18000786b  and     [rdi], rbx
0x18000786e  and     [rbp+plUbound], ebx
0x180007871  lea     r8, [rbp+plUbound]; plUbound
0x180007875  and     [rbp+plLbound], ebx
0x180007878  mov     r13d, 1
0x18000787e  mov     edx, r13d; nDim
0x180007881  mov     [rdi], r14
0x180007884  mov     rcx, r14; psa
0x180007887  call    cs:__imp_SafeArrayGetUBound
0x18000788e  nop     dword ptr [rax+rax+00h]
0x180007893  mov     rcx, [rdi]; psa
0x180007896  lea     r8, [rbp+plLbound]; plLbound
0x18000789a  mov     edx, r13d; nDim
0x18000789d  call    cs:__imp_SafeArrayGetLBound
0x1800078a4  nop     dword ptr [rax+rax+00h]
0x1800078a9  mov     r13d, [rbp+plUbound]
0x1800078ad  sub     r13d, [rbp+plLbound]
0x1800078b1  inc     r13d
0x1800078b4  test    r12d, r12d
0x1800078b7  jnz     short loc_1800078C1
0x1800078b9  mov     rcx, r15
0x1800078bc  call    ?Clear@?$CDynArray@PEAGVCDeallocateString@@@@QEAAXXZ; CDynArray<ushort *,CDeallocateString>::Clear(void)
0x1800078c1  xor     r12d, r12d
0x1800078c4  test    r13d, r13d
0x1800078c7  jz      loc_18000799F
0x1800078cd  mov     r14d, 1FFF0000h
0x1800078d3  mov     r15d, 70000h
0x1800078d9  mov     rcx, [rdi]; psa
0x1800078dc  lea     r8, [rbp+pv]; pv
0x1800078e0  lea     rdx, [rbp+plUbound]; rgIndices
0x1800078e4  mov     [rbp+plUbound], r12d
0x1800078e8  call    cs:__imp_SafeArrayGetElement
0x1800078ef  nop     dword ptr [rax+rax+00h]
0x1800078f4  mov     ebx, eax
0x1800078f6  test    eax, eax
0x1800078f8  jns     short loc_180007905
0x1800078fa  and     eax, r14d
0x1800078fd  cmp     eax, r15d
0x180007900  jnz     short loc_180007905
0x180007902  movzx   ebx, bx
0x180007905  mov     r9d, 5C8h
0x18000790b  mov     ecx, ebx
0x18000790d  call    ElValidateWin32_1
0x180007912  test    eax, eax
0x180007914  jnz     loc_18000799F
0x18000791a  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18000791e  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180007922  call    ?WcsDupHr@@YAJPEBGPEAPEAG@Z; WcsDupHr(ushort const *,ushort * *)
0x180007927  mov     r9d, 5CBh
0x18000792d  mov     ecx, eax
0x18000792f  mov     ebx, eax
0x180007931  call    ElValidateHr_0
0x180007936  test    eax, eax
0x180007938  js      short loc_18000798A
0x18000793a  mov     rsi, [rbp+var_18]
0x18000793e  mov     rcx, [rbp+arg_8]
0x180007942  mov     rdx, rsi
0x180007945  call    ?AddItem@?$CDynArray@PEAGVCDeallocateString@@@@QEAAKPEAG@Z; CDynArray<ushort *,CDeallocateString>::AddItem(ushort *)
0x18000794a  mov     r9d, 5CEh
0x180007950  mov     ecx, eax
0x180007952  mov     ebx, eax
0x180007954  call    ElValidateWin32_1
0x180007959  test    eax, eax
0x18000795b  jnz     short loc_18000799F
0x18000795d  mov     rcx, [rbp+pv]; bstrString
0x180007961  xor     esi, esi
0x180007963  mov     [rbp+var_18], rsi
0x180007967  test    rcx, rcx
0x18000796a  jz      short loc_18000797C
0x18000796c  call    cs:__imp_SysFreeString
0x180007973  nop     dword ptr [rax+rax+00h]
0x180007978  and     [rbp+pv], rsi
0x18000797c  inc     r12d
0x18000797f  cmp     r12d, r13d
0x180007982  jb      loc_1800078D9
0x180007988  jmp     short loc_18000799F
0x18000798a  test    ebx, ebx
0x18000798c  jns     short loc_18000799B
0x18000798e  mov     eax, ebx
0x180007990  and     eax, r14d
0x180007993  cmp     eax, r15d
0x180007996  jnz     short loc_18000799B
0x180007998  movzx   ebx, bx
0x18000799b  mov     rsi, [rbp+var_18]
0x18000799f  and     qword ptr [rdi], 0
0x1800079a3  mov     rcx, rdi; lpMem
0x1800079a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800079ab  jmp     short loc_1800079B7
0x1800079ad  mov     ebx, r13d
0x1800079b0  jmp     short loc_1800079C4
0x1800079b2  mov     ebx, 57h ; 'W'
0x1800079b7  test    rsi, rsi
0x1800079ba  jz      short loc_1800079C4
0x1800079bc  mov     rcx, rsi; lpMem
0x1800079bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800079c4  mov     rcx, [rbp+pv]; bstrString
0x1800079c8  test    rcx, rcx
0x1800079cb  jz      short loc_1800079D9
0x1800079cd  call    cs:__imp_SysFreeString
0x1800079d4  nop     dword ptr [rax+rax+00h]
0x1800079d9  mov     eax, ebx
0x1800079db  mov     rbx, [rsp+40h+arg_10]
0x1800079e3  add     rsp, 40h
0x1800079e7  pop     r15
0x1800079e9  pop     r14
0x1800079eb  pop     r13
0x1800079ed  pop     r12
0x1800079ef  pop     rdi
0x1800079f0  pop     rsi
0x1800079f1  pop     rbp
0x1800079f2  retn
```
