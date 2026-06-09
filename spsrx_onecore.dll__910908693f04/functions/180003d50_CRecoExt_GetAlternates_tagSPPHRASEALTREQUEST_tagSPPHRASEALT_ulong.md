# CRecoExt::GetAlternates(tagSPPHRASEALTREQUEST *,tagSPPHRASEALT * *,ulong *)

- ea: `0x180003d50`
- end: `0x180004099`
- name: `?GetAlternates@CRecoExt@@UEAAJPEAUtagSPPHRASEALTREQUEST@@PEAPEAUtagSPPHRASEALT@@PEAK@Z`
- size: `841`
- prototype: `__int64 __fastcall(CRecoExt *__hidden this, struct tagSPPHRASEALTREQUEST *, struct tagSPPHRASEALT **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800031c8`
- `0x180003774`
- `0x180003d50`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003f55`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003f55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003df4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003eec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003fb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003df4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003eec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003fb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000401e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004028`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004054`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004065`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000406f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000401e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004028`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004054`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004065`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000406f`

## pseudocode

```c
__int64 __fastcall CRecoExt::GetAlternates(
        CRecoExt *this,
        struct tagSPPHRASEALTREQUEST *a2,
        struct tagSPPHRASEALT **a3,
        unsigned int *a4)
{
  char *v6; // r12
  struct tagSPPHRASEALT *v7; // rsi
  __int64 v8; // r14
  HRESULT v9; // edi
  char *v10; // rax
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  char *v13; // rbx
  ULONG *v14; // rbx
  __int64 v15; // r13
  __int64 v16; // r15
  _DWORD *v17; // rbx
  ISpPhraseBuilder *v18; // rax
  ULONG cbAltExtra; // eax
  void *v20; // rax
  __int64 i; // r15
  ULONG v23; // [rsp+30h] [rbp-20h]
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  void *Src; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-8h] BYREF
  int v27; // [rsp+90h] [rbp+40h] BYREF
  struct tagSPPHRASEALT **v28; // [rsp+A0h] [rbp+50h]
  unsigned int *v29; // [rsp+A8h] [rbp+58h]

  v29 = a4;
  v28 = a3;
  v27 = 0;
  ppv = 0;
  v6 = 0;
  Src = 0;
  v7 = 0;
  pv = 0;
  LODWORD(v8) = 0;
  if ( *((_QWORD *)this + 15) && a2 && a3 && a4 )
  {
    v9 = ((__int64 (__fastcall *)(ISpPhrase *, void **))a2->pPhrase->lpVtbl->GetSerializedPhrase)(a2->pPhrase, &Src);
    if ( v9 < 0 )
      goto LABEL_25;
    v23 = ((a2->cbResultExtra + 7) & 0xFFFFFFF8) + *(_DWORD *)Src + 20;
    v10 = (char *)CoTaskMemAlloc(v23);
    v6 = v10;
    if ( !v10 )
      goto LABEL_7;
    *(_DWORD *)v10 = 21;
    *((_DWORD *)v10 + 1) = a2->ulStartElement;
    *((_DWORD *)v10 + 2) = a2->cElements;
    *((_DWORD *)v10 + 3) = a2->ulRequestAltCount;
    *((_DWORD *)v10 + 4) = a2->cbResultExtra;
    memcpy_0(v10 + 20, a2->pvResultExtra, a2->cbResultExtra);
    memcpy_0(&v6[((a2->cbResultExtra + 7) & 0xFFFFFFF8) + 20], Src, *(unsigned int *)Src);
    v11 = (_QWORD *)((char *)this + 128);
    v9 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))this + 8))(
           *((_QWORD *)this + 8),
           &IID_ISpPrivateEngineCallEx,
           (char *)this + 128);
    if ( v9 >= 0 )
    {
      if ( *v11 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
        v12 = *v11;
      }
      else
      {
        v12 = *((_QWORD *)this + 15);
      }
      v9 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, LPVOID *, int *))(*(_QWORD *)v12 + 32LL))(
             v12,
             v6,
             v23,
             &pv,
             &v27);
      if ( v9 >= 0 )
      {
        v13 = (char *)pv;
        v8 = *(unsigned int *)pv;
        if ( (_DWORD)v8 )
        {
          v7 = (struct tagSPPHRASEALT *)CoTaskMemAlloc(40 * v8);
          if ( !v7 )
          {
LABEL_7:
            v9 = -2147024882;
            goto LABEL_25;
          }
          v14 = (ULONG *)(v13 + 8);
          v15 = 0;
          while ( 1 )
          {
            v16 = v15;
            v7[v16].ulStartElementInParent = *v14;
            v7[v16].cElementsInParent = v14[1];
            v7[v16].cElementsInAlternate = v14[2];
            v7[v16].cbAltExtra = v14[3];
            v9 = CoCreateInstance(&CLSID_SpPhraseBuilder, 0, 0x17u, &GUID_88a3342a_0bed_4834_922b_88d43173162f, &ppv);
            if ( v9 < 0 )
              break;
            v17 = v14 + 4;
            v9 = (*(__int64 (__fastcall **)(LPVOID, _DWORD *))(*(_QWORD *)ppv + 64LL))(ppv, v17);
            if ( v9 < 0 )
              break;
            v18 = (ISpPhraseBuilder *)ppv;
            ppv = 0;
            v7[v15].pPhrase = v18;
            v14 = (_DWORD *)((char *)v17 + ((*v17 + 7) & 0xFFFFFFF8));
            cbAltExtra = v7[v15].cbAltExtra;
            if ( cbAltExtra )
            {
              v20 = CoTaskMemAlloc(cbAltExtra);
              v7[v15].pvAltExtra = v20;
              if ( !v20 )
                goto LABEL_7;
              memcpy_0(v20, v14, v7[v15].cbAltExtra);
              v14 = (ULONG *)((char *)v14 + ((v7[v15].cbAltExtra + 7) & 0xFFFFFFF8));
            }
            else
            {
              v7[v15].pvAltExtra = 0;
            }
            v15 = (unsigned int)(v15 + 1);
            if ( (unsigned int)v15 >= (unsigned int)v8 )
              goto LABEL_23;
          }
        }
        else
        {
LABEL_23:
          *v29 = v8;
          *v28 = v7;
          v7 = 0;
        }
      }
    }
  }
  else
  {
    v9 = -2147467259;
  }
LABEL_25:
  CoTaskMemFree(v6);
  CoTaskMemFree(Src);
  if ( v7 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v8; i = (unsigned int)(i + 1) )
    {
      ((void (__fastcall *)(ISpPhraseBuilder *))v7[i].pPhrase->lpVtbl->Release)(v7[i].pPhrase);
      CoTaskMemFree(v7[i].pvAltExtra);
    }
    CoTaskMemFree(v7);
  }
  CoTaskMemFree(pv);
  ATL::CComPtrBase<ISpPhraseBuilder>::~CComPtrBase<ISpPhraseBuilder>(&ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003d50  mov     [rsp-38h+arg_8], rbx
0x180003d55  mov     [rsp-38h+arg_18], r9
0x180003d5a  mov     [rsp-38h+arg_10], r8
0x180003d5f  push    rbp
0x180003d60  push    rsi
0x180003d61  push    rdi
0x180003d62  push    r12
0x180003d64  push    r13
0x180003d66  push    r14
0x180003d68  push    r15
0x180003d6a  mov     rbp, rsp
0x180003d6d  sub     rsp, 50h
0x180003d71  mov     rax, r9
0x180003d74  mov     r15, rdx
0x180003d77  mov     r13, rcx
0x180003d7a  xor     ecx, ecx
0x180003d7c  mov     [rbp+arg_0], ecx
0x180003d7f  mov     [rbp+var_18], rcx
0x180003d83  mov     r12d, ecx
0x180003d86  mov     [rbp+Src], rcx
0x180003d8a  mov     esi, ecx
0x180003d8c  mov     [rbp+pv], rcx
0x180003d90  mov     r14d, ecx
0x180003d93  cmp     [r13+78h], rcx
0x180003d97  jz      loc_180004016
0x180003d9d  test    rdx, rdx
0x180003da0  jz      loc_180004016
0x180003da6  test    r8, r8
0x180003da9  jz      loc_180004016
0x180003daf  test    rax, rax
0x180003db2  jz      loc_180004016
0x180003db8  mov     rcx, [rdx+20h]
0x180003dbc  mov     rax, [rcx]
0x180003dbf  lea     rdx, [rbp+Src]
0x180003dc3  mov     rax, [rax+20h]
0x180003dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dcc  mov     edi, eax
0x180003dce  test    eax, eax
0x180003dd0  js      loc_18000401B
0x180003dd6  mov     edx, [r15+18h]
0x180003dda  add     edx, 7
0x180003ddd  mov     edi, 0FFFFFFF8h
0x180003de2  and     edx, edi
0x180003de4  mov     rax, [rbp+Src]
0x180003de8  mov     eax, [rax]
0x180003dea  add     eax, 14h
0x180003ded  add     eax, edx
0x180003def  mov     dword ptr [rbp+var_20], eax
0x180003df2  mov     ecx, eax; cb
0x180003df4  call    cs:__imp_CoTaskMemAlloc
0x180003dfa  mov     r12, rax
0x180003dfd  test    rax, rax
0x180003e00  jnz     short loc_180003E0C
0x180003e02  mov     edi, 8007000Eh
0x180003e07  jmp     loc_18000401B
0x180003e0c  mov     dword ptr [rax], 15h
0x180003e12  mov     eax, [r15]
0x180003e15  mov     [r12+4], eax
0x180003e1a  mov     eax, [r15+4]
0x180003e1e  mov     [r12+8], eax
0x180003e23  mov     eax, [r15+8]
0x180003e27  mov     [r12+0Ch], eax
0x180003e2c  mov     eax, [r15+18h]
0x180003e30  mov     [r12+10h], eax
0x180003e35  lea     rbx, [r12+14h]
0x180003e3a  mov     r8d, [r15+18h]; Size
0x180003e3e  mov     rdx, [r15+10h]; Src
0x180003e42  mov     rcx, rbx; void *
0x180003e45  call    memcpy_0
0x180003e4a  mov     rdx, [rbp+Src]; Src
0x180003e4e  mov     r8d, [rdx]; Size
0x180003e51  mov     ecx, [r15+18h]
0x180003e55  add     ecx, 7
0x180003e58  and     rcx, rdi
0x180003e5b  add     rcx, rbx; void *
0x180003e5e  call    memcpy_0
0x180003e63  mov     rcx, [r13+40h]
0x180003e67  lea     rbx, [r13+80h]
0x180003e6e  mov     rax, [rcx]
0x180003e71  mov     r8, rbx
0x180003e74  lea     rdx, IID_ISpPrivateEngineCallEx
0x180003e7b  mov     rax, [rax]
0x180003e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e83  mov     edi, eax
0x180003e85  test    eax, eax
0x180003e87  js      loc_18000401B
0x180003e8d  mov     rcx, [rbx]
0x180003e90  test    rcx, rcx
0x180003e93  jz      short loc_180003EA6
0x180003e95  mov     rax, [rcx]
0x180003e98  mov     rax, [rax+10h]
0x180003e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea1  mov     rcx, [rbx]
0x180003ea4  jmp     short loc_180003EAA
0x180003ea6  mov     rcx, [r13+78h]
0x180003eaa  lea     rdx, [rbp+arg_0]
0x180003eae  mov     [rsp+50h+ppv], rdx
0x180003eb3  mov     rax, [rcx]
0x180003eb6  lea     r9, [rbp+pv]
0x180003eba  mov     r8d, dword ptr [rbp+var_20]
0x180003ebe  mov     rdx, r12
0x180003ec1  mov     rax, [rax+20h]
0x180003ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eca  test    eax, eax
0x180003ecc  mov     edi, eax
0x180003ece  js      loc_18000401B
0x180003ed4  mov     rbx, [rbp+pv]
0x180003ed8  mov     r14d, [rbx]
0x180003edb  test    r14d, r14d
0x180003ede  jz      loc_180004004
0x180003ee4  lea     rcx, [r14+r14*4]
0x180003ee8  shl     rcx, 3; cb
0x180003eec  call    cs:__imp_CoTaskMemAlloc
0x180003ef2  mov     rsi, rax
0x180003ef5  test    rax, rax
0x180003ef8  jz      loc_180003E02
0x180003efe  add     rbx, 8
0x180003f02  xor     r13d, r13d
0x180003f05  test    r14d, r14d
0x180003f08  jz      loc_180004004
0x180003f0e  lea     r15, ds:0[r13*4]
0x180003f16  add     r15, r13
0x180003f19  mov     eax, [rbx]
0x180003f1b  mov     [rsi+r15*8+8], eax
0x180003f20  mov     eax, [rbx+4]
0x180003f23  mov     [rsi+r15*8+0Ch], eax
0x180003f28  mov     eax, [rbx+8]
0x180003f2b  mov     [rsi+r15*8+10h], eax
0x180003f30  mov     eax, [rbx+0Ch]
0x180003f33  mov     [rsi+r15*8+20h], eax
0x180003f38  lea     rax, [rbp+var_18]
0x180003f3c  mov     [rsp+50h+ppv], rax; ppv
0x180003f41  lea     r9, _GUID_88a3342a_0bed_4834_922b_88d43173162f; riid
0x180003f48  xor     edx, edx; pUnkOuter
0x180003f4a  lea     r8d, [rdx+17h]; dwClsContext
0x180003f4e  lea     rcx, CLSID_SpPhraseBuilder; rclsid
0x180003f55  call    cs:__imp_CoCreateInstance
0x180003f5b  mov     edi, eax
0x180003f5d  test    eax, eax
0x180003f5f  js      loc_18000401B
0x180003f65  add     rbx, 10h
0x180003f69  mov     rcx, [rbp+var_18]
0x180003f6d  mov     rax, [rcx]
0x180003f70  mov     rdx, rbx
0x180003f73  mov     rax, [rax+40h]
0x180003f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f7c  mov     edi, eax
0x180003f7e  test    eax, eax
0x180003f80  js      loc_18000401B
0x180003f86  mov     rax, [rbp+var_18]
0x180003f8a  mov     [rbp+var_18], 0
0x180003f92  mov     [rsi+r15*8], rax
0x180003f96  mov     eax, [rbx]
0x180003f98  add     eax, 7
0x180003f9b  mov     ecx, 0FFFFFFF8h
0x180003fa0  and     rax, rcx
0x180003fa3  add     rbx, rax
0x180003fa6  mov     [rbp+var_20], rbx
0x180003faa  mov     eax, [rsi+r15*8+20h]
0x180003faf  test    eax, eax
0x180003fb1  jz      short loc_180003FEF
0x180003fb3  mov     ecx, eax; cb
0x180003fb5  call    cs:__imp_CoTaskMemAlloc
0x180003fbb  mov     [rsi+r15*8+18h], rax
0x180003fc0  test    rax, rax
0x180003fc3  jz      loc_180003E02
0x180003fc9  mov     r8d, [rsi+r15*8+20h]; Size
0x180003fce  mov     rdx, rbx; Src
0x180003fd1  mov     rcx, rax; void *
0x180003fd4  call    memcpy_0
0x180003fd9  mov     ebx, [rsi+r15*8+20h]
0x180003fde  add     ebx, 7
0x180003fe1  mov     eax, 0FFFFFFF8h
0x180003fe6  and     rbx, rax
0x180003fe9  add     rbx, [rbp+var_20]
0x180003fed  jmp     short loc_180003FF8
0x180003fef  mov     qword ptr [rsi+r15*8+18h], 0
0x180003ff8  inc     r13d
0x180003ffb  cmp     r13d, r14d
0x180003ffe  jb      loc_180003F0E
0x180004004  mov     rax, [rbp+arg_18]
0x180004008  mov     [rax], r14d
0x18000400b  mov     rax, [rbp+arg_10]
0x18000400f  mov     [rax], rsi
0x180004012  xor     esi, esi
0x180004014  jmp     short loc_18000401B
0x180004016  mov     edi, 80004005h
0x18000401b  mov     rcx, r12; pv
0x18000401e  call    cs:__imp_CoTaskMemFree
0x180004024  mov     rcx, [rbp+Src]; pv
0x180004028  call    cs:__imp_CoTaskMemFree
0x18000402e  test    rsi, rsi
0x180004031  jz      short loc_18000406B
0x180004033  xor     r15d, r15d
0x180004036  test    r14d, r14d
0x180004039  jz      short loc_180004062
0x18000403b  lea     rbx, [r15+r15*4]
0x18000403f  mov     rcx, [rsi+rbx*8]
0x180004043  mov     rax, [rcx]
0x180004046  mov     rax, [rax+10h]
0x18000404a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000404f  mov     rcx, [rsi+rbx*8+18h]; pv
0x180004054  call    cs:__imp_CoTaskMemFree
0x18000405a  inc     r15d
0x18000405d  cmp     r15d, r14d
0x180004060  jb      short loc_18000403B
0x180004062  mov     rcx, rsi; pv
0x180004065  call    cs:__imp_CoTaskMemFree
0x18000406b  mov     rcx, [rbp+pv]; pv
0x18000406f  call    cs:__imp_CoTaskMemFree
0x180004075  nop
0x180004076  lea     rcx, [rbp+var_18]
0x18000407a  call    ??1?$CComPtrBase@UISpPhraseBuilder@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpPhraseBuilder>::~CComPtrBase<ISpPhraseBuilder>(void)
0x18000407f  mov     eax, edi
0x180004081  mov     rbx, [rsp+50h+arg_8]
0x180004089  add     rsp, 50h
0x18000408d  pop     r15
0x18000408f  pop     r14
0x180004091  pop     r13
0x180004093  pop     r12
0x180004095  pop     rdi
0x180004096  pop     rsi
0x180004097  pop     rbp
0x180004098  retn
```
