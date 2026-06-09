# EnforceAlternateBoundaries(tagSPPHRASEALTREQUEST *,tagSPPHRASEALT *,ulong)

- ea: `0x180082fc4`
- end: `0x180083339`
- name: `?EnforceAlternateBoundaries@@YAJPEAUtagSPPHRASEALTREQUEST@@PEAUtagSPPHRASEALT@@K@Z`
- size: `885`
- prototype: `__int64 __fastcall(struct tagSPPHRASEALTREQUEST *, struct tagSPPHRASEALT *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009cd0`

## callees

- `0x180002aac`
- `0x180002db8`
- `0x180082abc`
- `0x180082fc4`
- `0x180083340`
- `0x180083b04`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800832ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800832f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800832fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800832ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800832f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800832fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800831d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800831d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnforceAlternateBoundaries(
        struct tagSPPHRASEALTREQUEST *a1,
        struct tagSPPHRASEALT *a2,
        unsigned int a3)
{
  __int64 v3; // r14
  struct SPPHRASEREPLACEMENT *v5; // rbx
  HRESULT v6; // edi
  ULONG cReplacements; // r12d
  unsigned int v8; // r13d
  struct SPPHRASEREPLACEMENT *v9; // r15
  struct SPPHRASEREPLACEMENT *v10; // rdi
  unsigned int v11; // r11d
  ULONG cElementsInAlternate; // r15d
  struct SPPHRASEREPLACEMENT *v13; // r14
  unsigned int v14; // ebx
  ULONG cElementsInParent; // r12d
  unsigned int v16; // r15d
  struct SPPHRASE *v17; // r14
  unsigned int v18; // r13d
  bool v19; // r12
  bool v20; // al
  ISpPhraseBuilder *v21; // rax
  __int64 v22; // rdx
  struct SPPHRASEREPLACEMENT *v24; // [rsp+30h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-40h] BYREF
  struct SPPHRASE *v27; // [rsp+48h] [rbp-38h] BYREF
  ULONG v28; // [rsp+50h] [rbp-30h]
  unsigned int v29; // [rsp+54h] [rbp-2Ch]
  HRESULT v30; // [rsp+58h] [rbp-28h]
  struct SPPHRASEREPLACEMENT *v31; // [rsp+60h] [rbp-20h]
  unsigned int v32; // [rsp+68h] [rbp-18h]
  struct SPPHRASEREPLACEMENT *pReplacements; // [rsp+70h] [rbp-10h]
  struct tagSPPHRASEALT *v34; // [rsp+78h] [rbp-8h]
  unsigned int v36; // [rsp+D8h] [rbp+58h] BYREF

  v3 = a3;
  v36 = 0;
  ppv = 0;
  v27 = 0;
  pv = 0;
  v5 = 0;
  v24 = 0;
  v6 = ((__int64 (__fastcall *)(ISpPhrase *, struct SPPHRASE **))a1->pPhrase->lpVtbl->GetPhrase)(a1->pPhrase, &v27);
  if ( v6 >= 0 )
  {
    cReplacements = v27->cReplacements;
    v29 = cReplacements;
    pReplacements = (struct SPPHRASEREPLACEMENT *)v27->pReplacements;
    v32 = v27->Rule.ulCountOfElements - 1;
    v34 = &a2[v3];
    if ( a2 < v34 )
    {
      while ( 1 )
      {
        v6 = ((__int64 (__fastcall *)(ISpPhraseBuilder *, LPVOID *))a2->pPhrase->lpVtbl->GetPhrase)(a2->pPhrase, &pv);
        v30 = v6;
        if ( v6 < 0 )
          break;
        v8 = *((_DWORD *)pv + 28);
        v9 = (struct SPPHRASEREPLACEMENT *)*((_QWORD *)pv + 15);
        v31 = v9;
        v10 = pReplacements;
        while ( StraddledByReplacement(a2->ulStartElementInParent, v10, cReplacements)
             || StraddledByReplacement(v11, v9, v8) )
        {
          a2->ulStartElementInParent = v11 - 1;
          ++a2->cElementsInParent;
          ++a2->cElementsInAlternate;
        }
        cElementsInAlternate = a2->cElementsInAlternate;
        v13 = v31;
        v14 = v29;
        while ( 1 )
        {
          v28 = cElementsInAlternate;
          cElementsInParent = a2->cElementsInParent;
          LODWORD(v31) = cElementsInParent + v11;
          if ( !StraddledByReplacement(cElementsInParent + v11, v10, v14)
            && !StraddledByReplacement(v11 + cElementsInAlternate, v13, v8) )
          {
            break;
          }
          a2->cElementsInParent = cElementsInParent + 1;
          a2->cElementsInAlternate = ++cElementsInAlternate;
        }
        v16 = v11 - 1;
        v17 = (struct SPPHRASE *)pv;
        v18 = *((_DWORD *)pv + 16);
        v19 = 1;
        v5 = v24;
        v6 = v30;
        if ( v11 )
          v19 = CompareSegments(v27, 0, v16, (struct SPPHRASE *)pv, 0, v11 - 1);
        v20 = 1;
        if ( (unsigned int)v31 < v18 )
          v20 = CompareSegments(v27, v16 + a2->cElementsInParent + 1, v32, v17, v16 + v28 + 1, v18 - 1);
        if ( !v19 || !v20 )
        {
          v6 = FilterReplacementsByPosition(v17, a1, 1, &v24, &v36);
          if ( v6 < 0
            || (v6 = CoCreateInstance(
                       &CLSID_SpPhraseBuilder,
                       0,
                       0x17u,
                       &GUID_88a3342a_0bed_4834_922b_88d43173162f,
                       &ppv),
                v6 < 0)
            || (*((_QWORD *)pv + 15) = 0,
                *((_DWORD *)pv + 28) = 0,
                v6 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 56LL))(ppv, pv),
                v6 < 0) )
          {
            v5 = v24;
            break;
          }
          v5 = v24;
          if ( v24 )
          {
            v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct SPPHRASEREPLACEMENT *))(*(_QWORD *)ppv + 96LL))(
                   ppv,
                   v36,
                   v24);
            if ( v6 < 0 )
              break;
            CWinHeap::Free((CWinHeap *)&g_heap, v5);
            v24 = 0;
          }
          v6 = FilterReplacementsByPosition(v27, a1, 0, &v24, &v36);
          v5 = v24;
          if ( v6 < 0 )
            break;
          if ( v24 )
          {
            v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct SPPHRASEREPLACEMENT *))(*(_QWORD *)ppv + 96LL))(
                   ppv,
                   v36,
                   v24);
            if ( v6 < 0 )
              break;
            CWinHeap::Free((CWinHeap *)&g_heap, v5);
            v5 = 0;
            v24 = 0;
          }
          ((void (__fastcall *)(ISpPhraseBuilder *))a2->pPhrase->lpVtbl->Release)(a2->pPhrase);
          v21 = (ISpPhraseBuilder *)ppv;
          ppv = 0;
          a2->pPhrase = v21;
          v17 = (struct SPPHRASE *)pv;
        }
        CoTaskMemFree(v17);
        pv = 0;
        if ( ++a2 >= v34 )
          break;
        cReplacements = v29;
      }
    }
  }
  CoTaskMemFree(v27);
  CoTaskMemFree(pv);
  CWinHeap::Free((CWinHeap *)&g_heap, v5);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&ppv, v22);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180082fc4  mov     [rsp-38h+arg_8], rbx
0x180082fc9  mov     [rsp-38h+arg_0], rcx
0x180082fce  push    rbp
0x180082fcf  push    rsi
0x180082fd0  push    rdi
0x180082fd1  push    r12
0x180082fd3  push    r13
0x180082fd5  push    r14
0x180082fd7  push    r15
0x180082fd9  mov     rbp, rsp
0x180082fdc  sub     rsp, 80h
0x180082fe3  mov     r14d, r8d
0x180082fe6  mov     rsi, rdx
0x180082fe9  xor     r13d, r13d
0x180082fec  mov     [rbp+arg_18], r13d
0x180082ff0  mov     [rbp+var_40], r13
0x180082ff4  mov     [rbp+var_38], r13
0x180082ff8  mov     [rbp+pv], r13
0x180082ffc  mov     ebx, r13d
0x180082fff  mov     [rbp+var_50], rbx
0x180083003  mov     rcx, [rcx+20h]
0x180083007  mov     rax, [rcx]
0x18008300a  lea     rdx, [rbp+var_38]
0x18008300e  mov     rax, [rax+18h]
0x180083012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083017  mov     edi, eax
0x180083019  test    eax, eax
0x18008301b  js      loc_1800832EF
0x180083021  mov     rcx, [rbp+var_38]
0x180083025  mov     r12d, [rcx+70h]
0x180083029  mov     [rbp+var_2C], r12d
0x18008302d  mov     rax, [rcx+78h]
0x180083031  mov     [rbp+var_10], rax
0x180083035  mov     eax, [rcx+40h]
0x180083038  dec     eax
0x18008303a  mov     [rbp+var_18], eax
0x18008303d  lea     rdx, [r14+r14*4]
0x180083041  lea     rax, [rsi+rdx*8]
0x180083045  mov     [rbp+var_8], rax
0x180083049  cmp     rsi, rax
0x18008304c  jnb     loc_1800832EF
0x180083052  mov     rcx, [rsi]
0x180083055  mov     rax, [rcx]
0x180083058  lea     rdx, [rbp+pv]
0x18008305c  mov     rax, [rax+18h]
0x180083060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083065  mov     edi, eax
0x180083067  mov     [rbp+var_28], eax
0x18008306a  test    eax, eax
0x18008306c  js      loc_1800832EF
0x180083072  mov     r14, [rbp+pv]
0x180083076  mov     r13d, [r14+70h]
0x18008307a  mov     r15, [r14+78h]
0x18008307e  mov     [rbp+var_20], r15
0x180083082  mov     rdi, [rbp+var_10]
0x180083086  mov     r11d, [rsi+8]
0x18008308a  mov     r8d, r12d; unsigned int
0x18008308d  mov     rdx, rdi; struct SPPHRASEREPLACEMENT *
0x180083090  mov     ecx, r11d; unsigned int
0x180083093  call    ?StraddledByReplacement@@YA_NKPEBUSPPHRASEREPLACEMENT@@K@Z; StraddledByReplacement(ulong,SPPHRASEREPLACEMENT const *,ulong)
0x180083098  test    al, al
0x18008309a  jnz     short loc_1800830AE
0x18008309c  mov     r8d, r13d; unsigned int
0x18008309f  mov     rdx, r15; struct SPPHRASEREPLACEMENT *
0x1800830a2  mov     ecx, r11d; unsigned int
0x1800830a5  call    ?StraddledByReplacement@@YA_NKPEBUSPPHRASEREPLACEMENT@@K@Z; StraddledByReplacement(ulong,SPPHRASEREPLACEMENT const *,ulong)
0x1800830aa  test    al, al
0x1800830ac  jz      short loc_1800830BD
0x1800830ae  lea     eax, [r11-1]
0x1800830b2  mov     [rsi+8], eax
0x1800830b5  inc     dword ptr [rsi+0Ch]
0x1800830b8  inc     dword ptr [rsi+10h]
0x1800830bb  jmp     short loc_180083086
0x1800830bd  mov     r15d, [rsi+10h]
0x1800830c1  mov     r14, [rbp+var_20]
0x1800830c5  mov     ebx, [rbp+var_2C]
0x1800830c8  mov     [rbp+var_30], r15d
0x1800830cc  mov     r12d, [rsi+0Ch]
0x1800830d0  lea     eax, [r12+r11]
0x1800830d4  mov     dword ptr [rbp+var_20], eax
0x1800830d7  mov     r8d, ebx; unsigned int
0x1800830da  mov     rdx, rdi; struct SPPHRASEREPLACEMENT *
0x1800830dd  mov     ecx, eax; unsigned int
0x1800830df  call    ?StraddledByReplacement@@YA_NKPEBUSPPHRASEREPLACEMENT@@K@Z; StraddledByReplacement(ulong,SPPHRASEREPLACEMENT const *,ulong)
0x1800830e4  test    al, al
0x1800830e6  jnz     short loc_1800830FB
0x1800830e8  lea     ecx, [r11+r15]; unsigned int
0x1800830ec  mov     r8d, r13d; unsigned int
0x1800830ef  mov     rdx, r14; struct SPPHRASEREPLACEMENT *
0x1800830f2  call    ?StraddledByReplacement@@YA_NKPEBUSPPHRASEREPLACEMENT@@K@Z; StraddledByReplacement(ulong,SPPHRASEREPLACEMENT const *,ulong)
0x1800830f7  test    al, al
0x1800830f9  jz      short loc_18008310C
0x1800830fb  lea     eax, [r12+1]
0x180083100  mov     [rsi+0Ch], eax
0x180083103  inc     r15d
0x180083106  mov     [rsi+10h], r15d
0x18008310a  jmp     short loc_1800830C8
0x18008310c  lea     r15d, [r11-1]
0x180083110  mov     r14, [rbp+pv]
0x180083114  mov     r13d, [r14+40h]
0x180083118  mov     r12b, 1
0x18008311b  test    r11d, r11d
0x18008311e  mov     rbx, [rbp+var_50]
0x180083122  mov     edi, [rbp+var_28]
0x180083125  jz      short loc_180083148
0x180083127  mov     [rsp+80h+var_58], r15d; unsigned int
0x18008312c  mov     dword ptr [rsp+80h+ppv], 0; unsigned int
0x180083134  mov     r9, r14; struct SPPHRASE *
0x180083137  mov     r8d, r15d; unsigned int
0x18008313a  xor     edx, edx; unsigned int
0x18008313c  mov     rcx, [rbp+var_38]; struct SPPHRASE *
0x180083140  call    ?CompareSegments@@YA_NPEAUSPPHRASE@@KK0KK@Z; CompareSegments(SPPHRASE *,ulong,ulong,SPPHRASE *,ulong,ulong)
0x180083145  mov     r12b, al
0x180083148  mov     al, 1
0x18008314a  cmp     dword ptr [rbp+var_20], r13d
0x18008314e  jnb     short loc_180083180
0x180083150  lea     r8d, [r13-1]
0x180083154  mov     r9d, [rbp+var_30]
0x180083158  inc     r9d
0x18008315b  add     r9d, r15d
0x18008315e  mov     edx, [rsi+0Ch]
0x180083161  inc     edx
0x180083163  add     edx, r15d; unsigned int
0x180083166  mov     [rsp+80h+var_58], r8d; unsigned int
0x18008316b  mov     dword ptr [rsp+80h+ppv], r9d; unsigned int
0x180083170  mov     r9, r14; struct SPPHRASE *
0x180083173  mov     r8d, [rbp+var_18]; unsigned int
0x180083177  mov     rcx, [rbp+var_38]; struct SPPHRASE *
0x18008317b  call    ?CompareSegments@@YA_NPEAUSPPHRASE@@KK0KK@Z; CompareSegments(SPPHRASE *,ulong,ulong,SPPHRASE *,ulong,ulong)
0x180083180  xor     r13d, r13d
0x180083183  test    r12b, r12b
0x180083186  jz      short loc_180083190
0x180083188  test    al, al
0x18008318a  jnz     loc_1800832CB
0x180083190  lea     rax, [rbp+arg_18]
0x180083194  mov     [rsp+80h+ppv], rax; unsigned int *
0x180083199  lea     r9, [rbp+var_50]; struct SPPHRASEREPLACEMENT **
0x18008319d  mov     r8b, 1; bool
0x1800831a0  mov     r15, [rbp+arg_0]
0x1800831a4  mov     rdx, r15; struct tagSPPHRASEALTREQUEST *
0x1800831a7  mov     rcx, r14; struct SPPHRASE *
0x1800831aa  call    ?FilterReplacementsByPosition@@YAJPEAUSPPHRASE@@PEAUtagSPPHRASEALTREQUEST@@_NPEAPEAUSPPHRASEREPLACEMENT@@PEAK@Z; FilterReplacementsByPosition(SPPHRASE *,tagSPPHRASEALTREQUEST *,bool,SPPHRASEREPLACEMENT * *,ulong *)
0x1800831af  mov     edi, eax
0x1800831b1  test    eax, eax
0x1800831b3  js      loc_1800832EB
0x1800831b9  lea     rax, [rbp+var_40]
0x1800831bd  mov     [rsp+80h+ppv], rax; ppv
0x1800831c2  lea     r9, _GUID_88a3342a_0bed_4834_922b_88d43173162f; riid
0x1800831c9  xor     edx, edx; pUnkOuter
0x1800831cb  lea     r8d, [rdx+17h]; dwClsContext
0x1800831cf  lea     rcx, CLSID_SpPhraseBuilder; rclsid
0x1800831d6  call    cs:__imp_CoCreateInstance
0x1800831dc  mov     edi, eax
0x1800831de  test    eax, eax
0x1800831e0  js      loc_1800832EB
0x1800831e6  mov     rax, [rbp+pv]
0x1800831ea  mov     [rax+78h], r13
0x1800831ee  mov     rax, [rbp+pv]
0x1800831f2  mov     [rax+70h], r13d
0x1800831f6  mov     rcx, [rbp+var_40]
0x1800831fa  mov     rax, [rcx]
0x1800831fd  mov     rdx, [rbp+pv]
0x180083201  mov     rax, [rax+38h]
0x180083205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008320a  mov     edi, eax
0x18008320c  test    eax, eax
0x18008320e  js      loc_1800832EB
0x180083214  mov     rbx, [rbp+var_50]
0x180083218  test    rbx, rbx
0x18008321b  jz      short loc_180083250
0x18008321d  mov     rcx, [rbp+var_40]
0x180083221  mov     rax, [rcx]
0x180083224  mov     r8, rbx
0x180083227  mov     edx, [rbp+arg_18]
0x18008322a  mov     rax, [rax+60h]
0x18008322e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083233  mov     edi, eax
0x180083235  test    eax, eax
0x180083237  js      loc_1800832EF
0x18008323d  mov     rdx, rbx; void *
0x180083240  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180083247  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18008324c  mov     [rbp+var_50], r13
0x180083250  lea     rax, [rbp+arg_18]
0x180083254  mov     [rsp+80h+ppv], rax; unsigned int *
0x180083259  lea     r9, [rbp+var_50]; struct SPPHRASEREPLACEMENT **
0x18008325d  xor     r8d, r8d; bool
0x180083260  mov     rdx, r15; struct tagSPPHRASEALTREQUEST *
0x180083263  mov     rcx, [rbp+var_38]; struct SPPHRASE *
0x180083267  call    ?FilterReplacementsByPosition@@YAJPEAUSPPHRASE@@PEAUtagSPPHRASEALTREQUEST@@_NPEAPEAUSPPHRASEREPLACEMENT@@PEAK@Z; FilterReplacementsByPosition(SPPHRASE *,tagSPPHRASEALTREQUEST *,bool,SPPHRASEREPLACEMENT * *,ulong *)
0x18008326c  mov     edi, eax
0x18008326e  mov     rbx, [rbp+var_50]
0x180083272  test    eax, eax
0x180083274  js      short loc_1800832EF
0x180083276  test    rbx, rbx
0x180083279  jz      short loc_1800832AD
0x18008327b  mov     rcx, [rbp+var_40]
0x18008327f  mov     rax, [rcx]
0x180083282  mov     r8, rbx
0x180083285  mov     edx, [rbp+arg_18]
0x180083288  mov     rax, [rax+60h]
0x18008328c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083291  mov     edi, eax
0x180083293  test    eax, eax
0x180083295  js      short loc_1800832EF
0x180083297  mov     rdx, rbx; void *
0x18008329a  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800832a1  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800832a6  mov     rbx, r13
0x1800832a9  mov     [rbp+var_50], rbx
0x1800832ad  mov     rcx, [rsi]
0x1800832b0  mov     rax, [rcx]
0x1800832b3  mov     rax, [rax+10h]
0x1800832b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800832bc  mov     rax, [rbp+var_40]
0x1800832c0  mov     [rbp+var_40], r13
0x1800832c4  mov     [rsi], rax
0x1800832c7  mov     r14, [rbp+pv]
0x1800832cb  mov     rcx, r14; pv
0x1800832ce  call    cs:__imp_CoTaskMemFree
0x1800832d4  mov     [rbp+pv], r13
0x1800832d8  add     rsi, 28h ; '('
0x1800832dc  cmp     rsi, [rbp+var_8]
0x1800832e0  jnb     short loc_1800832EF
0x1800832e2  mov     r12d, [rbp+var_2C]
0x1800832e6  jmp     loc_180083052
0x1800832eb  mov     rbx, [rbp+var_50]
0x1800832ef  mov     rcx, [rbp+var_38]; pv
0x1800832f3  call    cs:__imp_CoTaskMemFree
0x1800832f9  mov     rcx, [rbp+pv]; pv
0x1800832fd  call    cs:__imp_CoTaskMemFree
0x180083303  mov     rdx, rbx; void *
0x180083306  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18008330d  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180083312  nop
0x180083313  lea     rcx, [rbp+var_40]
0x180083317  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18008331c  mov     eax, edi
0x18008331e  mov     rbx, [rsp+80h+arg_8]
0x180083326  add     rsp, 80h
0x18008332d  pop     r15
0x18008332f  pop     r14
0x180083331  pop     r13
0x180083333  pop     r12
0x180083335  pop     rdi
0x180083336  pop     rsi
0x180083337  pop     rbp
0x180083338  retn
```
