# CSWbemObject::get_Derivation_(tagVARIANT *)

- ea: `0x18002c540`
- end: `0x18002c704`
- name: `?get_Derivation_@CSWbemObject@@UEAAJPEAUtagVARIANT@@@Z`
- size: `452`
- prototype: `__int64 __fastcall(CSWbemObject *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180006300`
- `0x180024774`
- `0x18002c540`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002c681`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c681`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c6a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c6a9`
- `OLEAUT32!__imp_VariantInit` at `0x18002c58d`
- `OLEAUT32!__imp_VariantInit` at `0x18002c658`
- `OLEAUT32!__imp_VariantInit` at `0x18002c58d`
- `OLEAUT32!__imp_VariantInit` at `0x18002c658`
- `OLEAUT32!__imp_VariantClear` at `0x18002c6b3`
- `OLEAUT32!__imp_VariantClear` at `0x18002c6d5`
- `OLEAUT32!__imp_VariantClear` at `0x18002c6b3`
- `OLEAUT32!__imp_VariantClear` at `0x18002c6d5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002c636`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002c636`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18002c606`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18002c606`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18002c619`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18002c619`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002c677`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18002c677`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18002c69f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18002c69f`

## pseudocode

```c
__int64 __fastcall CSWbemObject::get_Derivation_(CSWbemObject *this, struct tagVARIANT *a2)
{
  int v4; // ebx
  SAFEARRAY *v5; // rbx
  CWbemDispatchMgr *v6; // rcx
  OLECHAR *pv; // [rsp+40h] [rbp-40h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-30h] BYREF
  VARIANTARG v11; // [rsp+68h] [rbp-18h] BYREF
  LONG rgIndices; // [rsp+A8h] [rbp+28h] BYREF
  LONG plUbound; // [rsp+B0h] [rbp+30h] BYREF
  LONG plLbound; // [rsp+B8h] [rbp+38h] BYREF

  ResetLastErrors();
  if ( !a2 )
  {
    v4 = -2147217400;
LABEL_11:
    v6 = (CWbemDispatchMgr *)*((_QWORD *)this + 9);
    if ( v6 )
      CWbemDispatchMgr::RaiseException(v6, v4);
    return (unsigned int)v4;
  }
  v4 = -2147217407;
  if ( !*((_QWORD *)this + 8) )
    goto LABEL_11;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !(*(unsigned int (__fastcall **)(_QWORD, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 32LL))(
          *((_QWORD *)this + 8),
          L"__DERIVATION",
          0,
          &pvarg,
          0,
          0)
    && pvarg.vt == 8200
    && pvarg.llVal )
  {
    rgsabound.lLbound = 0;
    plLbound = 0;
    plUbound = 0;
    SafeArrayGetUBound(pvarg.parray, 1u, &plUbound);
    SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
    rgsabound.cElements = plUbound - plLbound + 1;
    pv = 0;
    v5 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    memset(&v11, 0, sizeof(v11));
    VariantInit(&v11);
    for ( rgIndices = 0; rgIndices <= plUbound; ++rgIndices )
    {
      SafeArrayGetElement(pvarg.parray, &rgIndices, &pv);
      v11.llVal = (LONGLONG)SysAllocString(pv);
      v11.vt = 8;
      SafeArrayPutElement(v5, &rgIndices, &v11);
      SysFreeString(pv);
      VariantClear(&v11);
    }
    a2->llVal = (LONGLONG)v5;
    v4 = 0;
    a2->vt = 8204;
  }
  VariantClear(&pvarg);
  if ( v4 < 0 )
    goto LABEL_11;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002c540  mov     [rsp-18h+arg_0], rbx
0x18002c545  push    rbp
0x18002c546  push    rsi
0x18002c547  push    rdi
0x18002c548  mov     rbp, rsp
0x18002c54b  sub     rsp, 80h
0x18002c552  mov     rdi, rdx
0x18002c555  mov     rsi, rcx
0x18002c558  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18002c55d  test    rdi, rdi
0x18002c560  jnz     short loc_18002C56C
0x18002c562  mov     ebx, 80041008h
0x18002c567  jmp     loc_18002C6DF
0x18002c56c  cmp     qword ptr [rsi+40h], 0
0x18002c571  mov     ebx, 80041001h
0x18002c576  jz      loc_18002C6DF
0x18002c57c  xorps   xmm0, xmm0
0x18002c57f  lea     rcx, [rbp+pvarg]; pvarg
0x18002c583  xor     eax, eax
0x18002c585  movups  xmmword ptr [rbp+pvarg], xmm0
0x18002c589  mov     qword ptr [rbp+pvarg+10h], rax
0x18002c58d  call    cs:__imp_VariantInit
0x18002c593  mov     rcx, [rsi+40h]
0x18002c597  lea     r9, [rbp+pvarg]
0x18002c59b  mov     [rsp+80h+var_58], 0
0x18002c5a4  lea     rdx, aDerivation; "__DERIVATION"
0x18002c5ab  xor     r8d, r8d
0x18002c5ae  mov     [rsp+80h+var_60], 0
0x18002c5b7  mov     rax, [rcx]
0x18002c5ba  mov     rax, [rax+20h]
0x18002c5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5c3  test    eax, eax
0x18002c5c5  jnz     loc_18002C6D1
0x18002c5cb  mov     eax, 2008h
0x18002c5d0  cmp     ax, word ptr [rbp+pvarg]
0x18002c5d4  jnz     loc_18002C6D1
0x18002c5da  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x18002c5de  test    rcx, rcx
0x18002c5e1  jz      loc_18002C6D1
0x18002c5e7  lea     r8, [rbp+plUbound]; plUbound
0x18002c5eb  mov     qword ptr [rbp+rgsabound.cElements], 0
0x18002c5f3  mov     edx, 1; nDim
0x18002c5f8  mov     [rbp+plLbound], 0
0x18002c5ff  mov     [rbp+plUbound], 0
0x18002c606  call    cs:__imp_SafeArrayGetUBound
0x18002c60c  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x18002c610  lea     r8, [rbp+plLbound]; plLbound
0x18002c614  mov     edx, 1; nDim
0x18002c619  call    cs:__imp_SafeArrayGetLBound
0x18002c61f  mov     eax, [rbp+plUbound]
0x18002c622  lea     r8, [rbp+rgsabound]; rgsabound
0x18002c626  sub     eax, [rbp+plLbound]
0x18002c629  mov     ecx, 0Ch; vt
0x18002c62e  inc     eax
0x18002c630  mov     [rbp+rgsabound.cElements], eax
0x18002c633  lea     edx, [rcx-0Bh]; cDims
0x18002c636  call    cs:__imp_SafeArrayCreate
0x18002c63c  xorps   xmm0, xmm0
0x18002c63f  mov     [rbp+pv], 0
0x18002c647  mov     rbx, rax
0x18002c64a  lea     rcx, [rbp+var_18]; pvarg
0x18002c64e  xor     eax, eax
0x18002c650  mov     qword ptr [rbp+var_18+10h], rax
0x18002c654  movups  xmmword ptr [rbp+var_18], xmm0
0x18002c658  call    cs:__imp_VariantInit
0x18002c65e  cmp     [rbp+plUbound], 0
0x18002c662  mov     [rbp+rgIndices], 0
0x18002c669  jl      short loc_18002C6C6
0x18002c66b  mov     rcx, qword ptr [rbp+pvarg+8]; psa
0x18002c66f  lea     r8, [rbp+pv]; pv
0x18002c673  lea     rdx, [rbp+rgIndices]; rgIndices
0x18002c677  call    cs:__imp_SafeArrayGetElement
0x18002c67d  mov     rcx, [rbp+pv]; psz
0x18002c681  call    cs:__imp_SysAllocString
0x18002c687  mov     ecx, 8
0x18002c68c  lea     r8, [rbp+var_18]; pv
0x18002c690  lea     rdx, [rbp+rgIndices]; rgIndices
0x18002c694  mov     qword ptr [rbp+var_18+8], rax
0x18002c698  mov     word ptr [rbp+var_18], cx
0x18002c69c  mov     rcx, rbx; psa
0x18002c69f  call    cs:__imp_SafeArrayPutElement
0x18002c6a5  mov     rcx, [rbp+pv]; bstrString
0x18002c6a9  call    cs:__imp_SysFreeString
0x18002c6af  lea     rcx, [rbp+var_18]; pvarg
0x18002c6b3  call    cs:__imp_VariantClear
0x18002c6b9  mov     eax, [rbp+rgIndices]
0x18002c6bc  inc     eax
0x18002c6be  mov     [rbp+rgIndices], eax
0x18002c6c1  cmp     eax, [rbp+plUbound]
0x18002c6c4  jle     short loc_18002C66B
0x18002c6c6  mov     [rdi+8], rbx
0x18002c6ca  xor     ebx, ebx
0x18002c6cc  mov     word ptr [rdi], 200Ch
0x18002c6d1  lea     rcx, [rbp+pvarg]; pvarg
0x18002c6d5  call    cs:__imp_VariantClear
0x18002c6db  test    ebx, ebx
0x18002c6dd  jns     short loc_18002C6EF
0x18002c6df  mov     rcx, [rsi+48h]; this
0x18002c6e3  test    rcx, rcx
0x18002c6e6  jz      short loc_18002C6EF
0x18002c6e8  mov     edx, ebx; int
0x18002c6ea  call    ?RaiseException@CWbemDispatchMgr@@QEAAXJ@Z; CWbemDispatchMgr::RaiseException(long)
0x18002c6ef  mov     eax, ebx
0x18002c6f1  mov     rbx, [rsp+80h+arg_0]
0x18002c6f9  add     rsp, 80h
0x18002c700  pop     rdi
0x18002c701  pop     rsi
0x18002c702  pop     rbp
0x18002c703  retn
```
