# CRecoExt::Commit(tagSPPHRASEALTREQUEST *,tagSPPHRASEALT *)

- ea: `0x1800038d0`
- end: `0x180003aa6`
- name: `?Commit@CRecoExt@@UEAAJPEAUtagSPPHRASEALTREQUEST@@PEAUtagSPPHRASEALT@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(CRecoExt *__hidden this, struct tagSPPHRASEALTREQUEST *, struct tagSPPHRASEALT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800031c8`
- `0x1800038d0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000398e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000398e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a87`

## pseudocode

```c
__int64 __fastcall CRecoExt::Commit(CRecoExt *this, struct tagSPPHRASEALTREQUEST *a2, struct tagSPPHRASEALT *a3)
{
  void *v3; // rdi
  int v7; // ebx
  ULONG v8; // r15d
  _DWORD *v9; // rax
  _DWORD *v10; // rbx
  char *v11; // rbx
  char *v12; // rbx
  void *Src; // [rsp+60h] [rbp+8h] BYREF
  void *pv; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  Src = 0;
  pv = 0;
  if ( *((_QWORD *)this + 15) && a2 && a3 )
  {
    v7 = ((__int64 (__fastcall *)(ISpPhrase *, void **))a2->pPhrase->lpVtbl->GetSerializedPhrase)(a2->pPhrase, &Src);
    if ( v7 >= 0 )
    {
      v7 = ((__int64 (__fastcall *)(ISpPhraseBuilder *, void **))a3->pPhrase->lpVtbl->GetSerializedPhrase)(
             a3->pPhrase,
             &pv);
      if ( v7 >= 0 )
      {
        v8 = *(_DWORD *)pv
           + ((a2->cbResultExtra + 7) & 0xFFFFFFF8)
           + ((a3->cbAltExtra + 7) & 0xFFFFFFF8)
           + *(_DWORD *)Src
           + 36;
        v9 = CoTaskMemAlloc(v8);
        v3 = v9;
        if ( v9 )
        {
          *v9 = 22;
          v10 = v9 + 9;
          v9[1] = a2->ulStartElement;
          v9[2] = a2->cElements;
          v9[3] = a2->ulRequestAltCount;
          v9[4] = a2->cbResultExtra;
          v9[5] = a3->ulStartElementInParent;
          v9[6] = a3->cElementsInParent;
          v9[7] = a3->cElementsInAlternate;
          v9[8] = a3->cbAltExtra;
          memcpy_0(v9 + 9, a2->pvResultExtra, a2->cbResultExtra);
          v11 = (char *)v10 + ((a2->cbResultExtra + 7) & 0xFFFFFFF8);
          memcpy_0(v11, a3->pvAltExtra, a3->cbAltExtra);
          v12 = &v11[(a3->cbAltExtra + 7) & 0xFFFFFFF8];
          memcpy_0(v12, Src, *(unsigned int *)Src);
          memcpy_0(&v12[*(unsigned int *)Src], pv, *(unsigned int *)pv);
          v7 = (*(__int64 (__fastcall **)(_QWORD, void *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 15) + 32LL))(
                 *((_QWORD *)this + 15),
                 v3,
                 v8,
                 0,
                 0);
        }
        else
        {
          v7 = -2147024882;
        }
      }
    }
  }
  else
  {
    v7 = -2147467259;
  }
  CoTaskMemFree(v3);
  CoTaskMemFree(Src);
  CoTaskMemFree(pv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800038d0  mov     r11, rsp
0x1800038d3  mov     [r11+10h], rbx
0x1800038d7  mov     [r11+18h], rbp
0x1800038db  push    rsi
0x1800038dc  push    rdi
0x1800038dd  push    r13
0x1800038df  push    r14
0x1800038e1  push    r15
0x1800038e3  sub     rsp, 30h
0x1800038e7  xor     edi, edi
0x1800038e9  mov     qword ptr [r11+8], 0
0x1800038f1  mov     rsi, r8
0x1800038f4  mov     r14, rdx
0x1800038f7  mov     rbp, rcx
0x1800038fa  mov     qword ptr [r11+20h], 0
0x180003902  cmp     [rcx+78h], rdi
0x180003906  jz      loc_180003A69
0x18000390c  test    rdx, rdx
0x18000390f  jz      loc_180003A69
0x180003915  test    r8, r8
0x180003918  jz      loc_180003A69
0x18000391e  mov     rcx, [rdx+20h]
0x180003922  lea     rdx, [r11+8]
0x180003926  mov     rax, [rcx]
0x180003929  mov     rax, [rax+20h]
0x18000392d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003932  mov     ebx, eax
0x180003934  test    eax, eax
0x180003936  js      loc_180003A6E
0x18000393c  mov     rcx, [rsi]
0x18000393f  lea     rdx, [rsp+58h+pv]
0x180003944  mov     rax, [rcx]
0x180003947  mov     rax, [rax+20h]
0x18000394b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003950  mov     ebx, eax
0x180003952  test    eax, eax
0x180003954  js      loc_180003A6E
0x18000395a  mov     eax, [r14+18h]
0x18000395e  mov     r13d, 0FFFFFFF8h
0x180003964  mov     edx, [rsi+20h]
0x180003967  add     eax, 7
0x18000396a  add     edx, 7
0x18000396d  and     eax, r13d
0x180003970  and     edx, r13d
0x180003973  add     edx, eax
0x180003975  mov     rax, [rsp+58h+pv]
0x18000397a  add     edx, [rax]
0x18000397c  mov     rax, [rsp+58h+Src]
0x180003981  mov     r15d, [rax]
0x180003984  add     r15d, 24h ; '$'
0x180003988  add     r15d, edx
0x18000398b  mov     ecx, r15d; cb
0x18000398e  call    cs:__imp_CoTaskMemAlloc
0x180003994  mov     rdi, rax
0x180003997  test    rax, rax
0x18000399a  jnz     short loc_1800039A6
0x18000399c  mov     ebx, 8007000Eh
0x1800039a1  jmp     loc_180003A6E
0x1800039a6  mov     dword ptr [rax], 16h
0x1800039ac  lea     rbx, [rdi+24h]
0x1800039b0  mov     eax, [r14]
0x1800039b3  mov     rcx, rbx; void *
0x1800039b6  mov     [rdi+4], eax
0x1800039b9  mov     eax, [r14+4]
0x1800039bd  mov     [rdi+8], eax
0x1800039c0  mov     eax, [r14+8]
0x1800039c4  mov     [rdi+0Ch], eax
0x1800039c7  mov     eax, [r14+18h]
0x1800039cb  mov     [rdi+10h], eax
0x1800039ce  mov     eax, [rsi+8]
0x1800039d1  mov     [rdi+14h], eax
0x1800039d4  mov     eax, [rsi+0Ch]
0x1800039d7  mov     [rdi+18h], eax
0x1800039da  mov     eax, [rsi+10h]
0x1800039dd  mov     [rdi+1Ch], eax
0x1800039e0  mov     eax, [rsi+20h]
0x1800039e3  mov     [rdi+20h], eax
0x1800039e6  mov     r8d, [r14+18h]; Size
0x1800039ea  mov     rdx, [r14+10h]; Src
0x1800039ee  call    memcpy_0
0x1800039f3  mov     eax, [r14+18h]
0x1800039f7  mov     r8d, [rsi+20h]; Size
0x1800039fb  add     eax, 7
0x1800039fe  mov     rdx, [rsi+18h]; Src
0x180003a02  and     rax, r13
0x180003a05  add     rbx, rax
0x180003a08  mov     rcx, rbx; void *
0x180003a0b  call    memcpy_0
0x180003a10  mov     eax, [rsi+20h]
0x180003a13  mov     rdx, [rsp+58h+Src]; Src
0x180003a18  add     eax, 7
0x180003a1b  and     rax, r13
0x180003a1e  add     rbx, rax
0x180003a21  mov     rcx, rbx; void *
0x180003a24  mov     r8d, [rdx]; Size
0x180003a27  call    memcpy_0
0x180003a2c  mov     rax, [rsp+58h+Src]
0x180003a31  mov     rdx, [rsp+58h+pv]; Src
0x180003a36  mov     ecx, [rax]
0x180003a38  mov     r8d, [rdx]; Size
0x180003a3b  add     rcx, rbx; void *
0x180003a3e  call    memcpy_0
0x180003a43  mov     rcx, [rbp+78h]
0x180003a47  xor     r9d, r9d
0x180003a4a  mov     r8d, r15d
0x180003a4d  mov     [rsp+58h+var_38], 0
0x180003a56  mov     rdx, rdi
0x180003a59  mov     rax, [rcx]
0x180003a5c  mov     rax, [rax+20h]
0x180003a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a65  mov     ebx, eax
0x180003a67  jmp     short loc_180003A6E
0x180003a69  mov     ebx, 80004005h
0x180003a6e  mov     rcx, rdi; pv
0x180003a71  call    cs:__imp_CoTaskMemFree
0x180003a77  mov     rcx, [rsp+58h+Src]; pv
0x180003a7c  call    cs:__imp_CoTaskMemFree
0x180003a82  mov     rcx, [rsp+58h+pv]; pv
0x180003a87  call    cs:__imp_CoTaskMemFree
0x180003a8d  mov     rbp, [rsp+58h+arg_10]
0x180003a92  mov     eax, ebx
0x180003a94  mov     rbx, [rsp+58h+arg_8]
0x180003a99  add     rsp, 30h
0x180003a9d  pop     r15
0x180003a9f  pop     r14
0x180003aa1  pop     r13
0x180003aa3  pop     rdi
0x180003aa4  pop     rsi
0x180003aa5  retn
```
