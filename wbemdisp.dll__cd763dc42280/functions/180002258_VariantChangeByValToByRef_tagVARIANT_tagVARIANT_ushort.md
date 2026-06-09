# VariantChangeByValToByRef(tagVARIANT *,tagVARIANT *,ushort)

- ea: `0x180002258`
- end: `0x18000239e`
- name: `?VariantChangeByValToByRef@@YAJPEAUtagVARIANT@@0G@Z`
- size: `326`
- prototype: `__int64 __fastcall(struct tagVARIANT *, struct tagVARIANT *, unsigned __int16)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002258`
- `0x180003a10`

## callees

- `0x180002258`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysReAllocString` at `0x180002351`
- `OLEAUT32!__imp_SysReAllocString` at `0x180002351`
- `OLEAUT32!__imp_VariantInit` at `0x180002275`
- `OLEAUT32!__imp_VariantInit` at `0x180002275`
- `OLEAUT32!__imp_VariantCopy` at `0x180002281`
- `OLEAUT32!__imp_VariantCopy` at `0x180002281`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800022ea`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800022ea`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800022fd`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800022fd`

## pseudocode

```c
__int64 __fastcall VariantChangeByValToByRef(struct tagVARIANT *a1, struct tagVARIANT *a2, __int16 a3)
{
  unsigned int v6; // esi
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  SAFEARRAY **pparray; // rdx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  LONGLONG llVal; // rax
  unsigned int v18; // ecx

  if ( (a3 & 0x4000) == 0 )
  {
    VariantInit(a1);
    return (unsigned int)VariantCopy(a1, a2);
  }
  v6 = 0;
  if ( (a3 & 0x2000) == 0 )
  {
    v8 = a3 & 0xBFFF;
    if ( v8 <= 8 )
    {
      if ( v8 == 8 )
      {
        SysReAllocString(a1->pbstrVal, a2->bstrVal);
        return v6;
      }
      v13 = v8 - 2;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( !v14 || (v15 = v14 - 1) == 0 )
        {
          *a1->plVal = a2->lVal;
          return v6;
        }
        v16 = v15 - 1;
        if ( v16 && v16 - 1 > 1 )
          return (unsigned int)-2147352571;
        llVal = a2->llVal;
LABEL_30:
        *a1->pllVal = llVal;
        return v6;
      }
    }
    else
    {
      v9 = v8 - 9;
      if ( !v9 )
      {
LABEL_29:
        (*(void (__fastcall **)(LONGLONG))(*a2->pllVal + 8))(a2->llVal);
        llVal = a2->llVal;
        goto LABEL_30;
      }
      v10 = v9 - 2;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( !v11 )
          return (unsigned int)VariantChangeByValToByRef(a1->pvarVal, a2, *a1->bstrVal);
        v18 = v11 - 1;
        if ( v18 )
        {
          if ( v18 == 4 )
          {
            *a1->pbVal = a2->bVal;
            return v6;
          }
          return (unsigned int)-2147352571;
        }
        goto LABEL_29;
      }
    }
    *a1->bstrVal = a2->uiVal;
    return v6;
  }
  pparray = a1->pparray;
  if ( a2->vt != 1 )
    return (unsigned int)SafeArrayCopy(a2->parray, pparray);
  if ( *pparray )
  {
    SafeArrayDestroy(*pparray);
    *a1->pllVal = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180002258  mov     [rsp+arg_0], rbx
0x18000225d  mov     [rsp+arg_8], rsi
0x180002262  push    rdi
0x180002263  sub     rsp, 20h
0x180002267  bt      r8w, 0Eh
0x18000226d  mov     rdi, rdx
0x180002270  mov     rbx, rcx
0x180002273  jb      short loc_18000229B
0x180002275  call    cs:__imp_VariantInit
0x18000227b  mov     rdx, rdi; pvargSrc
0x18000227e  mov     rcx, rbx; pvargDest
0x180002281  call    cs:__imp_VariantCopy
0x180002287  mov     esi, eax
0x180002289  mov     rbx, [rsp+28h+arg_0]
0x18000228e  mov     eax, esi
0x180002290  mov     rsi, [rsp+28h+arg_8]
0x180002295  add     rsp, 20h
0x180002299  pop     rdi
0x18000229a  retn
0x18000229b  xor     esi, esi
0x18000229d  bt      r8w, 0Dh
0x1800022a3  jb      short loc_1800022D8
0x1800022a5  movzx   ecx, r8w
0x1800022a9  btr     ecx, 0Eh
0x1800022ad  cmp     ecx, 8
0x1800022b0  jbe     short loc_180002305
0x1800022b2  sub     ecx, 9
0x1800022b5  jz      loc_18000237E
0x1800022bb  sub     ecx, 2
0x1800022be  jz      short loc_180002339
0x1800022c0  sub     ecx, 1
0x1800022c3  jnz     loc_18000235C
0x1800022c9  mov     rcx, [rbx+8]; struct tagVARIANT *
0x1800022cd  movzx   r8d, word ptr [rcx]; unsigned __int16
0x1800022d1  call    ?VariantChangeByValToByRef@@YAJPEAUtagVARIANT@@0G@Z; VariantChangeByValToByRef(tagVARIANT *,tagVARIANT *,ushort)
0x1800022d6  jmp     short loc_180002287
0x1800022d8  cmp     word ptr [rdi], 1
0x1800022dc  mov     rdx, [rcx+8]; ppsaOut
0x1800022e0  jnz     short loc_1800022F9
0x1800022e2  mov     rcx, [rdx]; psa
0x1800022e5  test    rcx, rcx
0x1800022e8  jz      short loc_180002289
0x1800022ea  call    cs:__imp_SafeArrayDestroy
0x1800022f0  mov     rax, [rbx+8]
0x1800022f4  mov     [rax], rsi
0x1800022f7  jmp     short loc_180002289
0x1800022f9  mov     rcx, [rdi+8]; psa
0x1800022fd  call    cs:__imp_SafeArrayCopy
0x180002303  jmp     short loc_180002287
0x180002305  jz      short loc_180002349
0x180002307  sub     ecx, 2
0x18000230a  jz      short loc_180002339
0x18000230c  sub     ecx, 1
0x18000230f  jz      short loc_18000232B
0x180002311  sub     ecx, 1
0x180002314  jz      short loc_18000232B
0x180002316  sub     ecx, 1
0x180002319  jz      short loc_180002325
0x18000231b  sub     ecx, 1
0x18000231e  jz      short loc_180002325
0x180002320  cmp     ecx, 1
0x180002323  jnz     short loc_180002374
0x180002325  mov     rax, [rdx+8]
0x180002329  jmp     short loc_180002392
0x18000232b  mov     rcx, [rbx+8]
0x18000232f  mov     eax, [rdx+8]
0x180002332  mov     [rcx], eax
0x180002334  jmp     loc_180002289
0x180002339  mov     rcx, [rbx+8]
0x18000233d  movzx   eax, word ptr [rdx+8]
0x180002341  mov     [rcx], ax
0x180002344  jmp     loc_180002289
0x180002349  mov     rdx, [rdx+8]; psz
0x18000234d  mov     rcx, [rbx+8]; pbstr
0x180002351  call    cs:__imp_SysReAllocString
0x180002357  jmp     loc_180002289
0x18000235c  sub     ecx, 1
0x18000235f  jz      short loc_18000237E
0x180002361  cmp     ecx, 4
0x180002364  jnz     short loc_180002374
0x180002366  mov     rcx, [rbx+8]
0x18000236a  mov     al, [rdx+8]
0x18000236d  mov     [rcx], al
0x18000236f  jmp     loc_180002289
0x180002374  mov     esi, 80020005h
0x180002379  jmp     loc_180002289
0x18000237e  mov     rcx, [rdx+8]
0x180002382  mov     rax, [rcx]
0x180002385  mov     rax, [rax+8]
0x180002389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000238e  mov     rax, [rdi+8]
0x180002392  mov     rcx, [rbx+8]
0x180002396  mov     [rcx], rax
0x180002399  jmp     loc_180002289
```
