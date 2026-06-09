# WdsConvertWdsStringArrayToSafeArray(CDynArray<ushort *,CDeallocateString> *,tagSAFEARRAY * *)

- ea: `0x180007450`
- end: `0x1800076a3`
- name: `?WdsConvertWdsStringArrayToSafeArray@@YAKPEAV?$CDynArray@PEAGVCDeallocateString@@@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `595`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800017a8`
- `0x180007080`
- `0x180007450`
- `0x180007d30`
- `0x180007e2c`
- `0x18002e468`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800075c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000765a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800075c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000765a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800074d2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800074d2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007673`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180007673`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180007585`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180007585`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800075ee`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800075ee`

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
0x180007450  mov     rax, rsp
0x180007453  mov     [rax+10h], rbx
0x180007457  push    rbp
0x180007458  push    rsi
0x180007459  push    rdi
0x18000745a  push    r12
0x18000745c  push    r13
0x18000745e  push    r14
0x180007460  push    r15
0x180007462  sub     rsp, 30h
0x180007466  xor     ebx, ebx
0x180007468  mov     r13, rdx
0x18000746b  mov     [rax+18h], rbx
0x18000746f  mov     r15, rcx
0x180007472  mov     [rsp+68h+psz], rbx
0x180007477  mov     esi, ebx
0x180007479  mov     edi, ebx
0x18000747b  test    rcx, rcx
0x18000747e  jz      loc_18000764D
0x180007484  test    rdx, rdx
0x180007487  jz      loc_18000764D
0x18000748d  mov     r12d, [rcx+0Ch]
0x180007491  lea     esi, [rbx+8]
0x180007494  mov     ecx, esi; unsigned __int64
0x180007496  mov     [rsp+68h+rgIndices], r12d
0x18000749b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800074a2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800074a7  mov     r14, rax
0x1800074aa  test    rax, rax
0x1800074ad  jz      loc_180007649
0x1800074b3  mov     ecx, esi; vt
0x1800074b5  mov     [rax], rbx
0x1800074b8  lea     r8, [rsp+68h+rgsabound]; rgsabound
0x1800074c0  mov     [rsp+68h+rgsabound.lLbound], ebx
0x1800074c7  lea     edx, [rbx+1]; cDims
0x1800074ca  mov     [rsp+68h+rgsabound.cElements], r12d
0x1800074d2  call    cs:__imp_SafeArrayCreate
0x1800074d9  nop     dword ptr [rax+rax+00h]
0x1800074de  mov     [r14], rax
0x1800074e1  mov     r9d, 430h
0x1800074e7  neg     rax
0x1800074ea  sbb     ebx, ebx
0x1800074ec  not     ebx
0x1800074ee  and     ebx, esi
0x1800074f0  mov     rsi, r14
0x1800074f3  mov     ecx, ebx
0x1800074f5  call    ElValidateWin32_1
0x1800074fa  test    eax, eax
0x1800074fc  jnz     loc_18000766B
0x180007502  xor     ebp, ebp
0x180007504  test    r12d, r12d
0x180007507  jz      loc_1800075E8
0x18000750d  mov     r14d, [rsp+68h+rgIndices]
0x180007512  xor     r12d, r12d
0x180007515  xor     ebx, ebx
0x180007517  cmp     ebp, [r15+0Ch]
0x18000751b  jb      short loc_180007524
0x18000751d  mov     ebx, 585h
0x180007522  jmp     short loc_180007530
0x180007524  mov     rax, [r15]
0x180007527  mov     rax, [r12+rax]
0x18000752b  mov     [rsp+68h+psz], rax
0x180007530  mov     r9d, 43Ah
0x180007536  mov     ecx, ebx
0x180007538  call    ElValidateWin32_1
0x18000753d  test    eax, eax
0x18000753f  jnz     loc_180007652
0x180007545  mov     rcx, [rsp+68h+psz]; psz
0x18000754a  lea     rdx, [rsp+68h+pv]; unsigned __int16 **
0x180007552  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x180007557  mov     r9d, 43Dh
0x18000755d  mov     ecx, eax
0x18000755f  mov     ebx, eax
0x180007561  call    ElValidateHr_0
0x180007566  test    eax, eax
0x180007568  js      loc_180007626
0x18000756e  mov     rdi, [rsp+68h+pv]
0x180007576  lea     rdx, [rsp+68h+rgIndices]; rgIndices
0x18000757b  mov     rcx, [rsi]; psa
0x18000757e  mov     r8, rdi; pv
0x180007581  mov     [rsp+68h+rgIndices], ebp
0x180007585  call    cs:__imp_SafeArrayPutElement
0x18000758c  nop     dword ptr [rax+rax+00h]
0x180007591  mov     ebx, eax
0x180007593  test    eax, eax
0x180007595  jns     short loc_1800075A6
0x180007597  and     eax, 1FFF0000h
0x18000759c  cmp     eax, 70000h
0x1800075a1  jnz     short loc_1800075A6
0x1800075a3  movzx   ebx, bx
0x1800075a6  mov     r9d, 441h
0x1800075ac  mov     ecx, ebx
0x1800075ae  call    ElValidateWin32_1
0x1800075b3  test    eax, eax
0x1800075b5  jnz     loc_180007652
0x1800075bb  test    rdi, rdi
0x1800075be  jz      short loc_1800075D9
0x1800075c0  mov     rcx, rdi; bstrString
0x1800075c3  call    cs:__imp_SysFreeString
0x1800075ca  nop     dword ptr [rax+rax+00h]
0x1800075cf  xor     edi, edi
0x1800075d1  mov     [rsp+68h+pv], rdi
0x1800075d9  inc     ebp
0x1800075db  add     r12, 8
0x1800075df  cmp     ebp, r14d
0x1800075e2  jb      loc_180007515
0x1800075e8  mov     rcx, [rsi]; psa
0x1800075eb  mov     rdx, r13; ppsaOut
0x1800075ee  call    cs:__imp_SafeArrayCopy
0x1800075f5  nop     dword ptr [rax+rax+00h]
0x1800075fa  mov     ecx, eax
0x1800075fc  mov     r9d, 454h
0x180007602  mov     ebp, eax
0x180007604  call    ElValidateHr_0
0x180007609  test    eax, eax
0x18000760b  jns     short loc_180007652
0x18000760d  test    ebp, ebp
0x18000760f  jns     short loc_180007645
0x180007611  mov     ecx, ebp
0x180007613  and     ecx, 1FFF0000h
0x180007619  cmp     ecx, 70000h
0x18000761f  jnz     short loc_180007645
0x180007621  movzx   ebx, bp
0x180007624  jmp     short loc_180007652
0x180007626  test    ebx, ebx
0x180007628  jns     short loc_18000763B
0x18000762a  mov     eax, ebx
0x18000762c  and     eax, 1FFF0000h
0x180007631  cmp     eax, 70000h
0x180007636  jnz     short loc_18000763B
0x180007638  movzx   ebx, bx
0x18000763b  mov     rdi, [rsp+68h+pv]
0x180007643  jmp     short loc_180007652
0x180007645  mov     ebx, ebp
0x180007647  jmp     short loc_180007652
0x180007649  mov     ebx, esi
0x18000764b  jmp     short loc_18000768B
0x18000764d  mov     ebx, 57h ; 'W'
0x180007652  test    rdi, rdi
0x180007655  jz      short loc_180007666
0x180007657  mov     rcx, rdi; bstrString
0x18000765a  call    cs:__imp_SysFreeString
0x180007661  nop     dword ptr [rax+rax+00h]
0x180007666  test    rsi, rsi
0x180007669  jz      short loc_18000768B
0x18000766b  mov     rcx, [rsi]; psa
0x18000766e  test    rcx, rcx
0x180007671  jz      short loc_180007683
0x180007673  call    cs:__imp_SafeArrayDestroy
0x18000767a  nop     dword ptr [rax+rax+00h]
0x18000767f  and     qword ptr [rsi], 0
0x180007683  mov     rcx, rsi; lpMem
0x180007686  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000768b  mov     eax, ebx
0x18000768d  mov     rbx, [rsp+68h+arg_8]
0x180007692  add     rsp, 30h
0x180007696  pop     r15
0x180007698  pop     r14
0x18000769a  pop     r13
0x18000769c  pop     r12
0x18000769e  pop     rdi
0x18000769f  pop     rsi
0x1800076a0  pop     rbp
0x1800076a1  retn
```
