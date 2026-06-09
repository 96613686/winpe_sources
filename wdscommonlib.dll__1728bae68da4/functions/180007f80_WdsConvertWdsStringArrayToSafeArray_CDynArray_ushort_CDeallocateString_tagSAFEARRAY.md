# WdsConvertWdsStringArrayToSafeArray(CDynArray<ushort *,CDeallocateString> *,tagSAFEARRAY * *)

- ea: `0x180007f80`
- end: `0x1800081da`
- name: `?WdsConvertWdsStringArrayToSafeArray@@YAKPEAV?$CDynArray@PEAGVCDeallocateString@@@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `602`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180002158`
- `0x180007bb0`
- `0x180007f80`
- `0x180008878`
- `0x180008974`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800081b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800081b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800080f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000818a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800080f3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000818a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180008002`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180008002`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800081a3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800081a3`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800080b5`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800080b5`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000811e`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000811e`

## pseudocode

```c
__int64 __fastcall WdsConvertWdsStringArrayToSafeArray(__int64 a1, SAFEARRAY **a2)
{
  SAFEARRAY **v4; // rsi
  OLECHAR *v5; // rdi
  ULONG v6; // r12d
  SAFEARRAY **v7; // rax
  SAFEARRAY **v8; // r14
  SAFEARRAY *v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // ebp
  unsigned int v16; // r14d
  __int64 v17; // r12
  __int64 v18; // rdx
  __int64 v19; // r8
  SAFEARRAY *v20; // rcx
  HRESULT v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rbp
  __int64 v25; // rdx
  __int64 v26; // r8
  OLECHAR *psz; // [rsp+20h] [rbp-48h]
  LONG rgIndices; // [rsp+70h] [rbp+8h] BYREF
  void *pv; // [rsp+80h] [rbp+18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+88h] [rbp+20h] BYREF

  pv = 0;
  psz = 0;
  v4 = 0;
  v5 = 0;
  if ( a1 && a2 )
  {
    v6 = *(_DWORD *)(a1 + 12);
    rgIndices = v6;
    v7 = (SAFEARRAY **)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( !v7 )
    {
      LODWORD(v10) = 8;
      return (unsigned int)v10;
    }
    *v7 = 0;
    rgsabound.lLbound = 0;
    rgsabound.cElements = v6;
    v9 = SafeArrayCreate(8u, 1u, &rgsabound);
    *v8 = v9;
    LODWORD(v10) = v9 == 0 ? 8 : 0;
    v4 = v8;
    if ( (unsigned int)ElValidateWin32_1((unsigned int)v10, v11, v12, 1072) )
      goto LABEL_33;
    v15 = 0;
    if ( v6 )
    {
      v16 = rgIndices;
      v17 = 0;
      while ( 1 )
      {
        LODWORD(v10) = 0;
        if ( v15 < *(_DWORD *)(a1 + 12) )
          psz = *(OLECHAR **)(v17 + *(_QWORD *)a1);
        else
          LODWORD(v10) = 1413;
        if ( (unsigned int)ElValidateWin32_1((unsigned int)v10, v13, v14, 1082) )
          break;
        v10 = (unsigned int)SysAllocStringHr(psz, (unsigned __int16 **)&pv);
        if ( (int)ElValidateHr_0(v10, v18, v19, 1085) < 0 )
        {
          if ( (int)v10 < 0 && (v10 & 0x1FFF0000) == 0x70000 )
            LODWORD(v10) = (unsigned __int16)v10;
          v5 = (OLECHAR *)pv;
          break;
        }
        v5 = (OLECHAR *)pv;
        v20 = *v4;
        rgIndices = v15;
        v21 = SafeArrayPutElement(v20, &rgIndices, pv);
        LODWORD(v10) = v21;
        if ( v21 < 0 && (v21 & 0x1FFF0000) == 0x70000 )
          LODWORD(v10) = (unsigned __int16)v21;
        if ( (unsigned int)ElValidateWin32_1((unsigned int)v10, v22, v23, 1089) )
          break;
        if ( v5 )
        {
          SysFreeString(v5);
          v5 = 0;
          pv = 0;
        }
        ++v15;
        v17 += 8;
        if ( v15 >= v16 )
          goto LABEL_19;
      }
    }
    else
    {
LABEL_19:
      v24 = (unsigned int)SafeArrayCopy(*v4, a2);
      if ( (int)ElValidateHr_0(v24, v25, v26, 1108) < 0 )
      {
        if ( (int)v24 < 0 && (v24 & 0x1FFF0000) == 0x70000 )
          LODWORD(v10) = (unsigned __int16)v24;
        else
          LODWORD(v10) = v24;
      }
    }
  }
  else
  {
    LODWORD(v10) = 87;
  }
  if ( v5 )
    SysFreeString(v5);
  if ( v4 )
  {
LABEL_33:
    if ( *v4 )
    {
      SafeArrayDestroy(*v4);
      *v4 = 0;
    }
    operator delete(v4);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180007f80  mov     rax, rsp
0x180007f83  mov     [rax+10h], rbx
0x180007f87  push    rbp
0x180007f88  push    rsi
0x180007f89  push    rdi
0x180007f8a  push    r12
0x180007f8c  push    r13
0x180007f8e  push    r14
0x180007f90  push    r15
0x180007f92  sub     rsp, 30h
0x180007f96  xor     ebx, ebx
0x180007f98  mov     r13, rdx
0x180007f9b  mov     [rax+18h], rbx
0x180007f9f  mov     r15, rcx
0x180007fa2  mov     [rsp+68h+psz], rbx
0x180007fa7  mov     esi, ebx
0x180007fa9  mov     edi, ebx
0x180007fab  test    rcx, rcx
0x180007fae  jz      loc_18000817D
0x180007fb4  test    rdx, rdx
0x180007fb7  jz      loc_18000817D
0x180007fbd  mov     r12d, [rcx+0Ch]
0x180007fc1  lea     esi, [rbx+8]
0x180007fc4  mov     ecx, esi; unsigned __int64
0x180007fc6  mov     [rsp+68h+rgIndices], r12d
0x180007fcb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007fd2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007fd7  mov     r14, rax
0x180007fda  test    rax, rax
0x180007fdd  jz      loc_180008179
0x180007fe3  mov     ecx, esi; vt
0x180007fe5  mov     [rax], rbx
0x180007fe8  lea     r8, [rsp+68h+rgsabound]; rgsabound
0x180007ff0  mov     [rsp+68h+rgsabound.lLbound], ebx
0x180007ff7  lea     edx, [rbx+1]; cDims
0x180007ffa  mov     [rsp+68h+rgsabound.cElements], r12d
0x180008002  call    cs:__imp_SafeArrayCreate
0x180008009  nop     dword ptr [rax+rax+00h]
0x18000800e  mov     [r14], rax
0x180008011  mov     r9d, 430h
0x180008017  neg     rax
0x18000801a  sbb     ebx, ebx
0x18000801c  not     ebx
0x18000801e  and     ebx, esi
0x180008020  mov     rsi, r14
0x180008023  mov     ecx, ebx
0x180008025  call    ElValidateWin32_1
0x18000802a  test    eax, eax
0x18000802c  jnz     loc_18000819B
0x180008032  xor     ebp, ebp
0x180008034  test    r12d, r12d
0x180008037  jz      loc_180008118
0x18000803d  mov     r14d, [rsp+68h+rgIndices]
0x180008042  xor     r12d, r12d
0x180008045  xor     ebx, ebx
0x180008047  cmp     ebp, [r15+0Ch]
0x18000804b  jb      short loc_180008054
0x18000804d  mov     ebx, 585h
0x180008052  jmp     short loc_180008060
0x180008054  mov     rax, [r15]
0x180008057  mov     rax, [r12+rax]
0x18000805b  mov     [rsp+68h+psz], rax
0x180008060  mov     r9d, 43Ah
0x180008066  mov     ecx, ebx
0x180008068  call    ElValidateWin32_1
0x18000806d  test    eax, eax
0x18000806f  jnz     loc_180008182
0x180008075  mov     rcx, [rsp+68h+psz]; psz
0x18000807a  lea     rdx, [rsp+68h+pv]; unsigned __int16 **
0x180008082  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x180008087  mov     r9d, 43Dh
0x18000808d  mov     ecx, eax
0x18000808f  mov     ebx, eax
0x180008091  call    ElValidateHr_0
0x180008096  test    eax, eax
0x180008098  js      loc_180008156
0x18000809e  mov     rdi, [rsp+68h+pv]
0x1800080a6  lea     rdx, [rsp+68h+rgIndices]; rgIndices
0x1800080ab  mov     rcx, [rsi]; psa
0x1800080ae  mov     r8, rdi; pv
0x1800080b1  mov     [rsp+68h+rgIndices], ebp
0x1800080b5  call    cs:__imp_SafeArrayPutElement
0x1800080bc  nop     dword ptr [rax+rax+00h]
0x1800080c1  mov     ebx, eax
0x1800080c3  test    eax, eax
0x1800080c5  jns     short loc_1800080D6
0x1800080c7  and     eax, 1FFF0000h
0x1800080cc  cmp     eax, 70000h
0x1800080d1  jnz     short loc_1800080D6
0x1800080d3  movzx   ebx, bx
0x1800080d6  mov     r9d, 441h
0x1800080dc  mov     ecx, ebx
0x1800080de  call    ElValidateWin32_1
0x1800080e3  test    eax, eax
0x1800080e5  jnz     loc_180008182
0x1800080eb  test    rdi, rdi
0x1800080ee  jz      short loc_180008109
0x1800080f0  mov     rcx, rdi; bstrString
0x1800080f3  call    cs:__imp_SysFreeString
0x1800080fa  nop     dword ptr [rax+rax+00h]
0x1800080ff  xor     edi, edi
0x180008101  mov     [rsp+68h+pv], rdi
0x180008109  inc     ebp
0x18000810b  add     r12, 8
0x18000810f  cmp     ebp, r14d
0x180008112  jb      loc_180008045
0x180008118  mov     rcx, [rsi]; psa
0x18000811b  mov     rdx, r13; ppsaOut
0x18000811e  call    cs:__imp_SafeArrayCopy
0x180008125  nop     dword ptr [rax+rax+00h]
0x18000812a  mov     ecx, eax
0x18000812c  mov     r9d, 454h
0x180008132  mov     ebp, eax
0x180008134  call    ElValidateHr_0
0x180008139  test    eax, eax
0x18000813b  jns     short loc_180008182
0x18000813d  test    ebp, ebp
0x18000813f  jns     short loc_180008175
0x180008141  mov     ecx, ebp
0x180008143  and     ecx, 1FFF0000h
0x180008149  cmp     ecx, 70000h
0x18000814f  jnz     short loc_180008175
0x180008151  movzx   ebx, bp
0x180008154  jmp     short loc_180008182
0x180008156  test    ebx, ebx
0x180008158  jns     short loc_18000816B
0x18000815a  mov     eax, ebx
0x18000815c  and     eax, 1FFF0000h
0x180008161  cmp     eax, 70000h
0x180008166  jnz     short loc_18000816B
0x180008168  movzx   ebx, bx
0x18000816b  mov     rdi, [rsp+68h+pv]
0x180008173  jmp     short loc_180008182
0x180008175  mov     ebx, ebp
0x180008177  jmp     short loc_180008182
0x180008179  mov     ebx, esi
0x18000817b  jmp     short loc_1800081C2
0x18000817d  mov     ebx, 57h ; 'W'
0x180008182  test    rdi, rdi
0x180008185  jz      short loc_180008196
0x180008187  mov     rcx, rdi; bstrString
0x18000818a  call    cs:__imp_SysFreeString
0x180008191  nop     dword ptr [rax+rax+00h]
0x180008196  test    rsi, rsi
0x180008199  jz      short loc_1800081C2
0x18000819b  mov     rcx, [rsi]; psa
0x18000819e  test    rcx, rcx
0x1800081a1  jz      short loc_1800081B3
0x1800081a3  call    cs:__imp_SafeArrayDestroy
0x1800081aa  nop     dword ptr [rax+rax+00h]
0x1800081af  and     qword ptr [rsi], 0
0x1800081b3  mov     rcx, rsi
0x1800081b6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800081bd  nop     dword ptr [rax+rax+00h]
0x1800081c2  mov     eax, ebx
0x1800081c4  mov     rbx, [rsp+68h+arg_8]
0x1800081c9  add     rsp, 30h
0x1800081cd  pop     r15
0x1800081cf  pop     r14
0x1800081d1  pop     r13
0x1800081d3  pop     r12
0x1800081d5  pop     rdi
0x1800081d6  pop     rsi
0x1800081d7  pop     rbp
0x1800081d8  retn
```
