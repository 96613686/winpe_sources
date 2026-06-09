# AlternatePhraseIsUnique(tagSPPHRASEALTREQUEST *,ISpPhraseBuilder *,tagSPPHRASEALT *,ulong,bool,ulong *)

- ea: `0x180082340`
- end: `0x1800827f9`
- name: `?AlternatePhraseIsUnique@@YA_NPEAUtagSPPHRASEALTREQUEST@@PEAUISpPhraseBuilder@@PEAUtagSPPHRASEALT@@K_NPEAK@Z`
- size: `1209`
- prototype: `bool(struct tagSPPHRASEALTREQUEST *, struct ISpPhraseBuilder *, struct tagSPPHRASEALT *, unsigned int, bool, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180082b2c`
- `0x180082b8c`

## callees

- `0x180002aac`
- `0x180002db8`
- `0x180006684`
- `0x1800073b4`
- `0x180082340`
- `0x180083340`
- `0x180083578`
- `0x1800838f0`
- `0x1800839c4`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008270e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008271c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008272d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008274c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082756`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008276a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082774`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008277e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008270e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008271c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008272d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008274c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082756`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082760`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008276a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082774`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008277e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800823ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800823fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800823ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800823fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall AlternatePhraseIsUnique(
        struct tagSPPHRASEALTREQUEST *a1,
        struct IUnknown *a2,
        struct IUnknown **a3,
        unsigned int a4,
        bool a5,
        unsigned int *a6)
{
  __int64 v6; // r15
  struct IUnknown *v8; // rbx
  struct IUnknown *v9; // rdi
  struct SPPHRASEREPLACEMENT *v10; // r13
  struct SPPHRASEREPLACEMENT *v11; // r12
  HRESULT Text; // esi
  __int64 v13; // rdx
  ULONG i; // r8d
  struct IUnknown **v15; // rbx
  struct tagSPPHRASEALT *v16; // r15
  unsigned int *v17; // r14
  unsigned __int16 *v18; // rax
  void *v19; // r9
  int v20; // ecx
  int v21; // edx
  __int64 v22; // rdx
  unsigned int v23; // r8d
  unsigned __int16 *v24; // rax
  int v25; // ecx
  int v26; // edx
  const struct SPPHRASEPROPERTY **v27; // r9
  struct SPPHRASE *v28; // r10
  bool IsEqualRecurse; // al
  char v30; // al
  bool v31; // bl
  char v33; // [rsp+38h] [rbp-69h]
  _BYTE v34[8]; // [rsp+40h] [rbp-61h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-59h] BYREF
  struct SPPHRASE *v36; // [rsp+50h] [rbp-51h] BYREF
  struct SPPHRASEREPLACEMENT *v37; // [rsp+58h] [rbp-49h] BYREF
  unsigned int v38; // [rsp+60h] [rbp-41h] BYREF
  LPVOID v39; // [rsp+68h] [rbp-39h] BYREF
  LPVOID v40; // [rsp+70h] [rbp-31h] BYREF
  struct SPPHRASEREPLACEMENT *v41; // [rsp+78h] [rbp-29h] BYREF
  LPVOID v42; // [rsp+80h] [rbp-21h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp-19h] BYREF
  unsigned int v44; // [rsp+90h] [rbp-11h] BYREF
  LPVOID v45; // [rsp+98h] [rbp-9h] BYREF
  LPVOID v46; // [rsp+A0h] [rbp-1h] BYREF
  struct IUnknown *v47; // [rsp+A8h] [rbp+7h] BYREF
  struct IUnknown *v48[7]; // [rsp+B0h] [rbp+Fh] BYREF

  v6 = a4;
  v33 = 0;
  v8 = 0;
  v48[0] = 0;
  v9 = 0;
  v47 = 0;
  ppv = 0;
  v42 = 0;
  v44 = 0;
  v38 = 0;
  v45 = 0;
  v39 = 0;
  v46 = 0;
  v40 = 0;
  v36 = 0;
  pv = 0;
  v10 = 0;
  v37 = 0;
  v11 = 0;
  v41 = 0;
  Text = CoCreateInstance(&CLSID_SpPhraseBuilder, 0, 0x17u, &GUID_88a3342a_0bed_4834_922b_88d43173162f, &ppv);
  if ( Text >= 0 )
  {
    Text = CoCreateInstance(&CLSID_SpPhraseBuilder, 0, 0x17u, &GUID_88a3342a_0bed_4834_922b_88d43173162f, &v42);
    if ( Text >= 0 )
    {
      if ( a2 )
      {
        ATL::AtlComPtrAssign(v48, a2);
        v8 = v48[0];
      }
      ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(v34, v8);
      Text = GetText(v34, 0, &v46);
      if ( Text >= 0 )
      {
        Text = ((__int64 (__fastcall *)(struct IUnknown *, struct SPPHRASE **))v8->lpVtbl[1].QueryInterface)(v8, &v36);
        if ( Text >= 0 )
        {
          if ( a1 )
          {
            Text = FilterReplacementsByPosition(v36, a1, 1, &v37, &v44);
            v10 = v37;
            if ( Text < 0 )
              goto LABEL_52;
            v13 = 0;
            for ( i = v44; (unsigned int)v13 < i; v13 = (unsigned int)(v13 + 1) )
              v10[v13].bDisplayAttributes &= ~0x10u;
            v36->pReplacements = v10;
            v36->cReplacements = i;
          }
          Text = (*(__int64 (__fastcall **)(LPVOID, struct SPPHRASE *))(*(_QWORD *)ppv + 56LL))(ppv, v36);
          if ( Text >= 0 )
          {
            ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(v34, ppv);
            Text = GetText(v34, 1, &v45);
            if ( Text >= 0 )
            {
              v15 = a3;
              v16 = (struct tagSPPHRASEALT *)&a3[5 * v6];
              if ( a3 < (struct IUnknown **)v16 )
              {
                v17 = a6;
                do
                {
                  if ( v9 != *v15 )
                  {
                    ATL::AtlComPtrAssign(&v47, *v15);
                    v9 = v47;
                  }
                  ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(v34, v9);
                  Text = GetText(v34, 0, &v40);
                  if ( Text < 0 )
                    break;
                  v18 = (unsigned __int16 *)v46;
                  v19 = v40;
                  do
                  {
                    v20 = *(unsigned __int16 *)((char *)v18 + (_BYTE *)v40 - (_BYTE *)v46);
                    v21 = *v18 - v20;
                    if ( v21 )
                      break;
                    ++v18;
                  }
                  while ( v20 );
                  if ( !v21 )
                  {
                    Text = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))v9->lpVtbl[1].QueryInterface)(v9, &pv);
                    if ( Text < 0 )
                      break;
                    if ( a1 )
                    {
                      Text = FilterReplacementsByPosition((struct SPPHRASE *)pv, a1, 1, &v41, &v38);
                      v11 = v41;
                      if ( Text < 0 )
                        break;
                      v22 = 0;
                      v23 = v38;
                      if ( v38 )
                      {
                        do
                        {
                          v11[v22].bDisplayAttributes &= ~0x10u;
                          v22 = (unsigned int)(v22 + 1);
                        }
                        while ( (unsigned int)v22 < v23 );
                        v17 = a6;
                      }
                      *((_QWORD *)pv + 15) = v11;
                      *((_DWORD *)pv + 28) = v23;
                    }
                    Text = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v42 + 56LL))(v42, pv);
                    if ( Text < 0 )
                      break;
                    ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(&v37, v42);
                    Text = GetText(&v37, 1, &v39);
                    if ( Text < 0 )
                      break;
                    CWinHeap::Free((CWinHeap *)&g_heap, v11);
                    v11 = 0;
                    v41 = 0;
                    v24 = (unsigned __int16 *)v45;
                    do
                    {
                      v25 = *(unsigned __int16 *)((char *)v24 + (_BYTE *)v39 - (_BYTE *)v45);
                      v26 = *v24 - v25;
                      if ( v26 )
                        break;
                      ++v24;
                    }
                    while ( v25 );
                    v27 = (const struct SPPHRASEPROPERTY **)pv;
                    if ( !v26 )
                    {
                      if ( a5
                        || (v28 = v36, v36 == pv)
                        || v36
                        && pv
                        && (v36->ullGrammarID != *((_QWORD *)pv + 1)
                          ? (IsEqualRecurse = 0)
                          : (IsEqualRecurse = PhraseRuleIsEqualRecurse(&v36->Rule, (const struct SPPHRASERULE *)pv + 1)),
                            IsEqualRecurse
                         && (v28 == (struct SPPHRASE *)v27
                          || v28 && v27 && PhrasePropertyIsEqualRecurse(v28->pProperties, v27[12]))) )
                      {
                        v33 = 1;
                        if ( v17 )
                          *v17 = -858993459 * (v15 - a3);
                      }
                    }
                    CoTaskMemFree(v27);
                    pv = 0;
                    CoTaskMemFree(v39);
                    v39 = 0;
                    v19 = v40;
                  }
                  CoTaskMemFree(v19);
                  v40 = 0;
                  v15 += 5;
                }
                while ( v15 < (struct IUnknown **)v16 );
              }
            }
          }
        }
      }
    }
  }
LABEL_52:
  CoTaskMemFree(v45);
  CoTaskMemFree(v39);
  CoTaskMemFree(v46);
  CoTaskMemFree(v40);
  CoTaskMemFree(v36);
  CoTaskMemFree(pv);
  CWinHeap::Free((CWinHeap *)&g_heap, v10);
  CWinHeap::Free((CWinHeap *)&g_heap, v11);
  v30 = v33;
  if ( Text )
    v30 = 1;
  v31 = v30 == 0;
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v42);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&ppv);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v47);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(v48);
  return v31;
}

```

## disassembly

```asm
0x180082340  mov     rax, rsp
0x180082343  mov     [rax+10h], rbx
0x180082347  mov     [rax+18h], r8
0x18008234b  mov     [rax+8], rcx
0x18008234f  push    rbp
0x180082350  push    rsi
0x180082351  push    rdi
0x180082352  push    r12
0x180082354  push    r13
0x180082356  push    r14
0x180082358  push    r15
0x18008235a  lea     rbp, [rax-4Fh]
0x18008235e  sub     rsp, 0B0h
0x180082365  mov     r15d, r9d
0x180082368  mov     r14, rdx
0x18008236b  xor     eax, eax
0x18008236d  mov     [rbp+47h+var_B0], al
0x180082370  mov     ebx, eax
0x180082372  mov     [rbp+47h+var_38], rax
0x180082376  mov     edi, eax
0x180082378  mov     [rbp+47h+var_40], rax
0x18008237c  mov     [rbp+47h+ppv], rax
0x180082380  mov     [rbp+47h+var_68], rax
0x180082384  mov     [rbp+47h+var_58], eax
0x180082387  mov     [rbp+47h+var_88], eax
0x18008238a  mov     [rbp+47h+var_50], rax
0x18008238e  mov     [rbp+47h+var_80], rax
0x180082392  mov     [rbp+47h+var_48], rax
0x180082396  mov     [rbp+47h+var_78], rax
0x18008239a  mov     [rbp+47h+var_98], rax
0x18008239e  mov     [rbp+47h+pv], rax
0x1800823a2  mov     r13d, eax
0x1800823a5  mov     [rbp+47h+var_90], rax
0x1800823a9  mov     r12d, eax
0x1800823ac  mov     [rbp+47h+var_70], rax
0x1800823b0  lea     rax, [rbp+47h+ppv]
0x1800823b4  mov     [rsp+20h], rax; ppv
0x1800823b9  lea     r9, _GUID_88a3342a_0bed_4834_922b_88d43173162f; riid
0x1800823c0  xor     edx, edx; pUnkOuter
0x1800823c2  lea     r8d, [r12+17h]; dwClsContext
0x1800823c7  lea     rcx, CLSID_SpPhraseBuilder; rclsid
0x1800823ce  call    cs:__imp_CoCreateInstance
0x1800823d4  mov     esi, eax
0x1800823d6  test    eax, eax
0x1800823d8  js      loc_180082748
0x1800823de  lea     rax, [rbp+47h+var_68]
0x1800823e2  mov     [rsp+20h], rax; ppv
0x1800823e7  lea     r9, _GUID_88a3342a_0bed_4834_922b_88d43173162f; riid
0x1800823ee  xor     edx, edx; pUnkOuter
0x1800823f0  lea     r8d, [r12+17h]; dwClsContext
0x1800823f5  lea     rcx, CLSID_SpPhraseBuilder; rclsid
0x1800823fc  call    cs:__imp_CoCreateInstance
0x180082402  mov     esi, eax
0x180082404  test    eax, eax
0x180082406  js      loc_180082748
0x18008240c  test    r14, r14
0x18008240f  jz      short loc_180082421
0x180082411  mov     rdx, r14; struct IUnknown *
0x180082414  lea     rcx, [rbp+47h+var_38]; struct IUnknown **
0x180082418  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18008241d  mov     rbx, [rbp+47h+var_38]
0x180082421  mov     rdx, rbx
0x180082424  lea     rcx, [rbp+47h+var_A8]
0x180082428  call    ??0?$CComPtrBase@UIMSASRLocaleHandler@@@ATL@@IEAA@PEAUIMSASRLocaleHandler@@@Z; ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(IMSASRLocaleHandler *)
0x18008242d  lea     r8, [rbp+47h+var_48]
0x180082431  xor     edx, edx
0x180082433  lea     rcx, [rbp+47h+var_A8]
0x180082437  call    ?GetText@@YAJV?$CComPtr@UISpPhraseBuilder@@@ATL@@HPEAPEAG@Z; GetText(ATL::CComPtr<ISpPhraseBuilder>,int,ushort * *)
0x18008243c  mov     esi, eax
0x18008243e  test    eax, eax
0x180082440  js      loc_180082748
0x180082446  mov     rax, [rbx]
0x180082449  lea     rdx, [rbp+47h+var_98]
0x18008244d  mov     rcx, rbx
0x180082450  mov     rax, [rax+18h]
0x180082454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082459  mov     esi, eax
0x18008245b  test    eax, eax
0x18008245d  js      loc_180082748
0x180082463  mov     rax, [rbp+47h+arg_0]
0x180082467  mov     ebx, 1
0x18008246c  test    rax, rax
0x18008246f  jz      short loc_1800824C7
0x180082471  lea     rcx, [rbp+47h+var_58]
0x180082475  mov     [rsp+20h], rcx; unsigned int *
0x18008247a  lea     r9, [rbp+47h+var_90]; struct SPPHRASEREPLACEMENT **
0x18008247e  mov     r8b, bl; bool
0x180082481  mov     rdx, rax; struct tagSPPHRASEALTREQUEST *
0x180082484  mov     rcx, [rbp+47h+var_98]; struct SPPHRASE *
0x180082488  call    ?FilterReplacementsByPosition@@YAJPEAUSPPHRASE@@PEAUtagSPPHRASEALTREQUEST@@_NPEAPEAUSPPHRASEREPLACEMENT@@PEAK@Z; FilterReplacementsByPosition(SPPHRASE *,tagSPPHRASEALTREQUEST *,bool,SPPHRASEREPLACEMENT * *,ulong *)
0x18008248d  mov     esi, eax
0x18008248f  mov     r13, [rbp+47h+var_90]
0x180082493  test    eax, eax
0x180082495  js      loc_180082748
0x18008249b  xor     edx, edx
0x18008249d  mov     r8d, [rbp+47h+var_58]
0x1800824a1  test    r8d, r8d
0x1800824a4  jz      short loc_1800824B7
0x1800824a6  lea     rcx, [rdx+rdx*2]
0x1800824aa  and     byte ptr [r13+rcx*8+0], 0EFh
0x1800824b0  add     edx, ebx
0x1800824b2  cmp     edx, r8d
0x1800824b5  jb      short loc_1800824A6
0x1800824b7  mov     rax, [rbp+47h+var_98]
0x1800824bb  mov     [rax+78h], r13
0x1800824bf  mov     rax, [rbp+47h+var_98]
0x1800824c3  mov     [rax+70h], r8d
0x1800824c7  mov     rcx, [rbp+47h+ppv]
0x1800824cb  mov     rax, [rcx]
0x1800824ce  mov     rdx, [rbp+47h+var_98]
0x1800824d2  mov     rax, [rax+38h]
0x1800824d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800824db  mov     esi, eax
0x1800824dd  test    eax, eax
0x1800824df  js      loc_180082748
0x1800824e5  mov     rdx, [rbp+47h+ppv]
0x1800824e9  lea     rcx, [rbp+47h+var_A8]
0x1800824ed  call    ??0?$CComPtrBase@UIMSASRLocaleHandler@@@ATL@@IEAA@PEAUIMSASRLocaleHandler@@@Z; ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(IMSASRLocaleHandler *)
0x1800824f2  lea     r8, [rbp+47h+var_50]
0x1800824f6  mov     edx, ebx
0x1800824f8  lea     rcx, [rbp+47h+var_A8]
0x1800824fc  call    ?GetText@@YAJV?$CComPtr@UISpPhraseBuilder@@@ATL@@HPEAPEAG@Z; GetText(ATL::CComPtr<ISpPhraseBuilder>,int,ushort * *)
0x180082501  mov     esi, eax
0x180082503  test    eax, eax
0x180082505  js      loc_180082748
0x18008250b  mov     rdx, [rbp+47h+arg_10]
0x18008250f  mov     rbx, rdx
0x180082512  lea     rcx, [r15+r15*4]
0x180082516  lea     r15, [rdx+rcx*8]
0x18008251a  cmp     rdx, r15
0x18008251d  jnb     loc_180082748
0x180082523  mov     r14, [rbp+47h+arg_28]
0x180082527  cmp     rdi, [rbx]
0x18008252a  jz      short loc_18008253C
0x18008252c  mov     rdx, [rbx]; struct IUnknown *
0x18008252f  lea     rcx, [rbp+47h+var_40]; struct IUnknown **
0x180082533  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180082538  mov     rdi, [rbp+47h+var_40]
0x18008253c  mov     rdx, rdi
0x18008253f  lea     rcx, [rbp+47h+var_A8]
0x180082543  call    ??0?$CComPtrBase@UIMSASRLocaleHandler@@@ATL@@IEAA@PEAUIMSASRLocaleHandler@@@Z; ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(IMSASRLocaleHandler *)
0x180082548  lea     r8, [rbp+47h+var_78]
0x18008254c  xor     edx, edx
0x18008254e  lea     rcx, [rbp+47h+var_A8]
0x180082552  call    ?GetText@@YAJV?$CComPtr@UISpPhraseBuilder@@@ATL@@HPEAPEAG@Z; GetText(ATL::CComPtr<ISpPhraseBuilder>,int,ushort * *)
0x180082557  mov     esi, eax
0x180082559  test    eax, eax
0x18008255b  js      loc_180082748
0x180082561  mov     rax, [rbp+47h+var_48]
0x180082565  mov     r9, [rbp+47h+var_78]
0x180082569  mov     r8, r9
0x18008256c  sub     r8, rax
0x18008256f  movzx   edx, word ptr [rax]
0x180082572  movzx   ecx, word ptr [rax+r8]
0x180082577  sub     edx, ecx
0x180082579  jnz     short loc_180082583
0x18008257b  add     rax, 2
0x18008257f  test    ecx, ecx
0x180082581  jnz     short loc_18008256F
0x180082583  test    edx, edx
0x180082585  jnz     loc_18008272A
0x18008258b  mov     rax, [rdi]
0x18008258e  lea     rdx, [rbp+47h+pv]
0x180082592  mov     rcx, rdi
0x180082595  mov     rax, [rax+18h]
0x180082599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008259e  mov     esi, eax
0x1800825a0  test    eax, eax
0x1800825a2  js      loc_180082748
0x1800825a8  mov     rax, [rbp+47h+arg_0]
0x1800825ac  test    rax, rax
0x1800825af  jz      short loc_18008260A
0x1800825b1  lea     rcx, [rbp+47h+var_88]
0x1800825b5  mov     [rsp+20h], rcx; unsigned int *
0x1800825ba  lea     r9, [rbp+47h+var_70]; struct SPPHRASEREPLACEMENT **
0x1800825be  mov     r8b, 1; bool
0x1800825c1  mov     rdx, rax; struct tagSPPHRASEALTREQUEST *
0x1800825c4  mov     rcx, [rbp+47h+pv]; struct SPPHRASE *
0x1800825c8  call    ?FilterReplacementsByPosition@@YAJPEAUSPPHRASE@@PEAUtagSPPHRASEALTREQUEST@@_NPEAPEAUSPPHRASEREPLACEMENT@@PEAK@Z; FilterReplacementsByPosition(SPPHRASE *,tagSPPHRASEALTREQUEST *,bool,SPPHRASEREPLACEMENT * *,ulong *)
0x1800825cd  mov     esi, eax
0x1800825cf  mov     r12, [rbp+47h+var_70]
0x1800825d3  test    eax, eax
0x1800825d5  js      loc_180082748
0x1800825db  xor     edx, edx
0x1800825dd  mov     r8d, [rbp+47h+var_88]
0x1800825e1  test    r8d, r8d
0x1800825e4  jz      short loc_1800825FA
0x1800825e6  lea     rcx, [rdx+rdx*2]
0x1800825ea  and     byte ptr [r12+rcx*8], 0EFh
0x1800825ef  inc     edx
0x1800825f1  cmp     edx, r8d
0x1800825f4  jb      short loc_1800825E6
0x1800825f6  mov     r14, [rbp+47h+arg_28]
0x1800825fa  mov     rax, [rbp+47h+pv]
0x1800825fe  mov     [rax+78h], r12
0x180082602  mov     rax, [rbp+47h+pv]
0x180082606  mov     [rax+70h], r8d
0x18008260a  mov     rcx, [rbp+47h+var_68]
0x18008260e  mov     rax, [rcx]
0x180082611  mov     rdx, [rbp+47h+pv]
0x180082615  mov     rax, [rax+38h]
0x180082619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008261e  mov     esi, eax
0x180082620  test    eax, eax
0x180082622  js      loc_180082748
0x180082628  mov     rdx, [rbp+47h+var_68]
0x18008262c  lea     rcx, [rbp+47h+var_90]
0x180082630  call    ??0?$CComPtrBase@UIMSASRLocaleHandler@@@ATL@@IEAA@PEAUIMSASRLocaleHandler@@@Z; ATL::CComPtrBase<IMSASRLocaleHandler>::CComPtrBase<IMSASRLocaleHandler>(IMSASRLocaleHandler *)
0x180082635  lea     r8, [rbp+47h+var_80]
0x180082639  mov     edx, 1
0x18008263e  lea     rcx, [rbp+47h+var_90]
0x180082642  call    ?GetText@@YAJV?$CComPtr@UISpPhraseBuilder@@@ATL@@HPEAPEAG@Z; GetText(ATL::CComPtr<ISpPhraseBuilder>,int,ushort * *)
0x180082647  mov     esi, eax
0x180082649  test    eax, eax
0x18008264b  js      loc_180082748
0x180082651  mov     rdx, r12; void *
0x180082654  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18008265b  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180082660  xor     r12d, r12d
0x180082663  mov     [rbp+47h+var_70], r12
0x180082667  mov     rax, [rbp+47h+var_50]
0x18008266b  mov     r8, [rbp+47h+var_80]
0x18008266f  sub     r8, rax
0x180082672  movzx   edx, word ptr [rax]
0x180082675  movzx   ecx, word ptr [rax+r8]
0x18008267a  sub     edx, ecx
0x18008267c  jnz     short loc_180082686
0x18008267e  add     rax, 2
0x180082682  test    ecx, ecx
0x180082684  jnz     short loc_180082672
0x180082686  mov     r9, [rbp+47h+pv]
0x18008268a  test    edx, edx
0x18008268c  jnz     short loc_18008270B
0x18008268e  cmp     [rbp+47h+arg_20], r12b
0x180082692  jnz     short loc_1800826E6
0x180082694  mov     r10, [rbp+47h+var_98]
0x180082698  cmp     r10, r9
0x18008269b  jz      short loc_1800826E6
0x18008269d  test    r10, r10
0x1800826a0  jz      short loc_18008270B
0x1800826a2  test    r9, r9
0x1800826a5  jz      short loc_18008270B
0x1800826a7  mov     rax, [r9+8]
0x1800826ab  cmp     [r10+8], rax
0x1800826af  jnz     short loc_1800826C0
0x1800826b1  lea     rdx, [r9+30h]; struct SPPHRASERULE *
0x1800826b5  lea     rcx, [r10+30h]; struct SPPHRASERULE *
0x1800826b9  call    ?PhraseRuleIsEqualRecurse@@YA_NPEBUSPPHRASERULE@@0@Z; PhraseRuleIsEqualRecurse(SPPHRASERULE const *,SPPHRASERULE const *)
0x1800826be  jmp     short loc_1800826C2
0x1800826c0  xor     al, al
0x1800826c2  test    al, al
0x1800826c4  jz      short loc_18008270B
0x1800826c6  cmp     r10, r9
0x1800826c9  jz      short loc_1800826E6
0x1800826cb  test    r10, r10
0x1800826ce  jz      short loc_18008270B
0x1800826d0  test    r9, r9
0x1800826d3  jz      short loc_18008270B
0x1800826d5  mov     rdx, [r9+60h]; struct SPPHRASEPROPERTY *
0x1800826d9  mov     rcx, [r10+60h]; struct SPPHRASEPROPERTY *
0x1800826dd  call    ?PhrasePropertyIsEqualRecurse@@YA_NPEBUSPPHRASEPROPERTY@@0@Z; PhrasePropertyIsEqualRecurse(SPPHRASEPROPERTY const *,SPPHRASEPROPERTY const *)
0x1800826e2  test    al, al
0x1800826e4  jz      short loc_18008270B
0x1800826e6  mov     [rbp+47h+var_B0], 1
0x1800826ea  test    r14, r14
0x1800826ed  jz      short loc_18008270B
0x1800826ef  mov     rax, rbx
0x1800826f2  sub     rax, [rbp+47h+arg_10]
0x1800826f6  sar     rax, 3
0x1800826fa  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x180082704  imul    rax, rcx
0x180082708  mov     [r14], eax
0x18008270b  mov     rcx, r9; pv
0x18008270e  call    cs:__imp_CoTaskMemFree
0x180082714  mov     [rbp+47h+pv], r12
0x180082718  mov     rcx, [rbp+47h+var_80]; pv
0x18008271c  call    cs:__imp_CoTaskMemFree
0x180082722  mov     [rbp+47h+var_80], r12
0x180082726  mov     r9, [rbp+47h+var_78]
0x18008272a  mov     rcx, r9; pv
0x18008272d  call    cs:__imp_CoTaskMemFree
0x180082733  mov     [rbp+47h+var_78], 0
0x18008273b  add     rbx, 28h ; '('
0x18008273f  cmp     rbx, r15
0x180082742  jb      loc_180082527
0x180082748  mov     rcx, [rbp+47h+var_50]; pv
0x18008274c  call    cs:__imp_CoTaskMemFree
0x180082752  mov     rcx, [rbp+47h+var_80]; pv
0x180082756  call    cs:__imp_CoTaskMemFree
0x18008275c  mov     rcx, [rbp+47h+var_48]; pv
0x180082760  call    cs:__imp_CoTaskMemFree
0x180082766  mov     rcx, [rbp+47h+var_78]; pv
0x18008276a  call    cs:__imp_CoTaskMemFree
0x180082770  mov     rcx, [rbp+47h+var_98]; pv
0x180082774  call    cs:__imp_CoTaskMemFree
0x18008277a  mov     rcx, [rbp+47h+pv]; pv
0x18008277e  call    cs:__imp_CoTaskMemFree
0x180082784  mov     rdx, r13; void *
0x180082787  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18008278e  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
  ... truncated ...
```
