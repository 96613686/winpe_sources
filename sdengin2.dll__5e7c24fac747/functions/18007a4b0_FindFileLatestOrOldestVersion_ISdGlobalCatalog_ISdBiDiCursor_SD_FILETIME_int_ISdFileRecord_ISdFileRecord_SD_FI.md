# FindFileLatestOrOldestVersion(ISdGlobalCatalog *,ISdBiDiCursor *,SD_FILETIME,int,ISdFileRecord *,ISdFileRecord * *,SD_FILETIME *,ISdFileRecord * *)

- ea: `0x18007a4b0`
- end: `0x18007a917`
- name: `?FindFileLatestOrOldestVersion@@YAJPEAUISdGlobalCatalog@@PEAUISdBiDiCursor@@TSD_FILETIME@@HPEAUISdFileRecord@@PEAPEAU4@PEAT3@4@Z`
- size: `1127`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007a920`
- `0x18007a9d0`

## callees

- `0x180003430`
- `0x180003450`
- `0x180003f30`
- `0x180015b08`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18007a4b0`
- `0x1800cb010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007a6aa`
- `ole32!CoTaskMemFree` at `0x18007a70d`
- `ole32!CoTaskMemFree` at `0x18007a8ad`
- `ole32!CoTaskMemFree` at `0x18007a8bf`
- `ole32!CoTaskMemFree` at `0x18007a8d1`
- `ole32!CoTaskMemFree` at `0x18007a8e3`
- `ole32!CoTaskMemFree` at `0x18007a6aa`
- `ole32!CoTaskMemFree` at `0x18007a70d`
- `ole32!CoTaskMemFree` at `0x18007a8ad`
- `ole32!CoTaskMemFree` at `0x18007a8bf`
- `ole32!CoTaskMemFree` at `0x18007a8d1`
- `ole32!CoTaskMemFree` at `0x18007a8e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FindFileLatestOrOldestVersion(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        int a4,
        struct IUnknown *a5,
        struct IUnknown **a6,
        unsigned __int64 *a7,
        struct IUnknown **a8)
{
  struct IUnknown **v11; // rcx
  unsigned __int64 *v12; // r12
  __int64 v13; // rcx
  unsigned __int64 *v14; // rax
  struct IUnknown **v15; // r15
  __int16 v16; // ax
  struct IUnknown *v17; // rsi
  int v18; // edi
  struct IUnknown *v19; // r14
  int v20; // ecx
  int v21; // esi
  unsigned __int16 *v22; // rax
  int v23; // ecx
  int v24; // edx
  unsigned __int16 *v25; // rax
  int v26; // ecx
  int v27; // edx
  struct IUnknown *v28; // rax
  struct IUnknown *v30; // [rsp+20h] [rbp-69h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-61h] BYREF
  LPVOID v32; // [rsp+30h] [rbp-59h] BYREF
  int v33; // [rsp+38h] [rbp-51h] BYREF
  __int16 v34; // [rsp+3Ch] [rbp-4Dh]
  __int16 v35; // [rsp+3Eh] [rbp-4Bh]
  LPVOID v36; // [rsp+70h] [rbp-19h] BYREF
  LPVOID v37; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int64 v38; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int64 v39[7]; // [rsp+88h] [rbp-1h] BYREF
  struct IUnknown *v40; // [rsp+D0h] [rbp+47h] BYREF
  int v41; // [rsp+E8h] [rbp+5Fh]

  v41 = a4;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v33, "FindFileLatestOrOldestVersion", 168, 1);
  v39[0] = 0;
  v38 = 0;
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v32);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&pv);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v37);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v36);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v30);
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&v40);
  v11 = a6;
  if ( a6 )
    *a6 = 0;
  v12 = a7;
  if ( a7 )
  {
    v13 = 8;
    v14 = a7;
    do
    {
      *(_BYTE *)v14 = 0;
      v14 = (unsigned __int64 *)((char *)v14 + 1);
      --v13;
    }
    while ( v13 );
    v11 = a6;
  }
  v15 = a8;
  if ( a8 )
    *a8 = 0;
  v16 = 182;
  if ( !a1 || (v34 = 182, v16 = 183, !a2) || (v34 = 183, v17 = a5, v16 = 184, !a5) || (v34 = 184, v16 = 185, !v11) )
  {
    v18 = -2147024809;
    goto LABEL_47;
  }
  v33 = 0;
  v34 = 185;
  v18 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))a5->lpVtbl[1].QueryInterface)(a5, &v37);
  v33 = v18;
  v16 = 187;
  if ( v18 < 0 )
    goto LABEL_48;
  v34 = 187;
  v18 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))v17->lpVtbl[1].AddRef)(v17, &v36);
  v33 = v18;
  v16 = 188;
  if ( v18 < 0 )
    goto LABEL_48;
  v34 = 188;
  v18 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int64 *))v17->lpVtbl[7].QueryInterface)(v17, &v38);
  v33 = v18;
  v16 = 189;
  if ( v18 < 0 )
    goto LABEL_48;
  v34 = 189;
  v19 = v30;
  if ( v30 != v17 )
  {
    ATL::AtlComPtrAssign(&v30, v17);
    v19 = v30;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)a2 + 24LL))(
          a2,
          &IID_ISdFileRecord,
          &v40);
  v20 = v18;
  v33 = v18;
  v16 = 193;
  if ( v18 < 0 )
    goto LABEL_48;
  v21 = v41;
  while ( 1 )
  {
    v34 = v16;
    if ( v20 == 1 )
      break;
    CoTaskMemFree(pv);
    pv = 0;
    v18 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))v40->lpVtbl[1].AddRef)(v40, &pv);
    v33 = v18;
    v16 = 197;
    if ( v18 < 0 )
      goto LABEL_48;
    v34 = 197;
    v22 = (unsigned __int16 *)v36;
    do
    {
      v23 = *(unsigned __int16 *)((char *)v22 + (_BYTE *)pv - (_BYTE *)v36);
      v24 = *v22 - v23;
      if ( v24 )
        break;
      ++v22;
    }
    while ( v23 );
    if ( v24 )
      break;
    CoTaskMemFree(v32);
    v32 = 0;
    v18 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))v40->lpVtbl[1].QueryInterface)(v40, &v32);
    v33 = v18;
    v16 = 205;
    if ( v18 < 0 )
      goto LABEL_48;
    v34 = 205;
    v25 = (unsigned __int16 *)v37;
    do
    {
      v26 = *(unsigned __int16 *)((char *)v25 + (_BYTE *)v32 - (_BYTE *)v37);
      v27 = *v25 - v26;
      if ( v27 )
        break;
      ++v25;
    }
    while ( v26 );
    if ( v27 )
      break;
    v18 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int64 *))v40->lpVtbl[7].QueryInterface)(v40, v39);
    v33 = v18;
    v16 = 212;
    if ( v18 < 0 )
      goto LABEL_48;
    v34 = 212;
    if ( v39[0] > a3 )
      break;
    if ( v21 )
    {
      v38 = v39[0];
      if ( v19 != v40 )
      {
        ATL::AtlComPtrAssign(&v30, v40);
        v19 = v30;
      }
    }
    ATL::CComPtrBase<ISdUniCursor>::Release(&v40);
    v18 = (*(__int64 (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)a2 + 24LL))(
            a2,
            &IID_ISdFileRecord,
            &v40);
    v20 = v18;
    v33 = v18;
    v16 = 232;
    if ( v18 < 0 )
      goto LABEL_48;
  }
  v30 = 0;
  *a6 = v19;
  if ( !v15 )
  {
    ATL::CComPtrBase<ISdUniCursor>::Release(&v40);
    v18 = (*(__int64 (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)a2 + 40LL))(
            a2,
            &IID_ISdFileRecord,
            &v40);
    v33 = v18;
    v16 = 246;
    if ( v18 < 0 )
    {
LABEL_48:
      v35 = v16;
      goto LABEL_49;
    }
    v34 = 246;
    if ( !v18 )
      goto LABEL_42;
    v18 = -2130706200;
    v16 = 248;
LABEL_47:
    v33 = v18;
    goto LABEL_48;
  }
  v28 = v40;
  v40 = 0;
  *v15 = v28;
LABEL_42:
  if ( v12 )
    *v12 = v38;
  v33 = 0;
  v34 = 258;
  v18 = 0;
LABEL_49:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v30);
  CoTaskMemFree(v36);
  v36 = 0;
  CoTaskMemFree(v37);
  v37 = 0;
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v32);
  v32 = 0;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v33);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18007a4b0  mov     [rsp-8+arg_8], rbx
0x18007a4b5  mov     [rsp-8+arg_18], r9d
0x18007a4ba  push    rbp
0x18007a4bb  push    rsi
0x18007a4bc  push    rdi
0x18007a4bd  push    r12
0x18007a4bf  push    r13
0x18007a4c1  push    r14
0x18007a4c3  push    r15
0x18007a4c5  lea     rbp, [rsp-7]
0x18007a4ca  sub     rsp, 90h
0x18007a4d1  mov     rbx, r8
0x18007a4d4  mov     r13, rdx
0x18007a4d7  mov     rdi, rcx
0x18007a4da  mov     r9d, 1; unsigned __int16
0x18007a4e0  mov     r8d, 0A8h; unsigned __int16
0x18007a4e6  lea     rdx, aFindfilelatest; "FindFileLatestOrOldestVersion"
0x18007a4ed  lea     rcx, [rbp+37h+var_88]; this
0x18007a4f1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18007a4f6  mov     [rbp+37h+var_38], 0
0x18007a4fe  mov     [rbp+37h+var_40], 0
0x18007a506  lea     rcx, [rbp+37h+var_90]; void *
0x18007a50a  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18007a50f  lea     rcx, [rbp+37h+pv]; void *
0x18007a513  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18007a518  lea     rcx, [rbp+37h+var_48]; void *
0x18007a51c  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18007a521  lea     rcx, [rbp+37h+var_50]; void *
0x18007a525  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18007a52a  lea     rcx, [rbp+37h+var_A0]; void *
0x18007a52e  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18007a533  lea     rcx, [rbp+37h+arg_0]; void *
0x18007a537  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18007a53c  mov     rcx, [rbp+37h+arg_28]
0x18007a540  test    rcx, rcx
0x18007a543  jz      short loc_18007A54C
0x18007a545  mov     qword ptr [rcx], 0
0x18007a54c  mov     r12, [rbp+37h+arg_30]
0x18007a550  test    r12, r12
0x18007a553  jz      short loc_18007A56D
0x18007a555  mov     ecx, 8
0x18007a55a  mov     rax, r12
0x18007a55d  mov     byte ptr [rax], 0
0x18007a560  inc     rax
0x18007a563  sub     rcx, 1
0x18007a567  jnz     short loc_18007A55D
0x18007a569  mov     rcx, [rbp+37h+arg_28]
0x18007a56d  mov     r15, [rbp+37h+arg_38]
0x18007a571  test    r15, r15
0x18007a574  jz      short loc_18007A57D
0x18007a576  mov     qword ptr [r15], 0
0x18007a57d  mov     eax, 0B6h
0x18007a582  test    rdi, rdi
0x18007a585  jz      loc_18007A889
0x18007a58b  mov     [rbp+37h+var_84], ax
0x18007a58f  mov     eax, 0B7h
0x18007a594  test    r13, r13
0x18007a597  jz      loc_18007A889
0x18007a59d  mov     [rbp+37h+var_84], ax
0x18007a5a1  mov     rsi, [rbp+37h+arg_20]
0x18007a5a5  mov     eax, 0B8h
0x18007a5aa  test    rsi, rsi
0x18007a5ad  jz      loc_18007A889
0x18007a5b3  mov     [rbp+37h+var_84], ax
0x18007a5b7  mov     eax, 0B9h
0x18007a5bc  test    rcx, rcx
0x18007a5bf  jz      loc_18007A889
0x18007a5c5  mov     [rbp+37h+var_88], 0
0x18007a5cc  mov     [rbp+37h+var_84], ax
0x18007a5d0  mov     rax, [rsi]
0x18007a5d3  lea     rdx, [rbp+37h+var_48]
0x18007a5d7  mov     rcx, rsi
0x18007a5da  mov     rax, [rax+18h]
0x18007a5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a5e3  mov     edi, eax
0x18007a5e5  mov     [rbp+37h+var_88], eax
0x18007a5e8  test    eax, eax
0x18007a5ea  mov     eax, 0BBh
0x18007a5ef  js      loc_18007A891
0x18007a5f5  mov     [rbp+37h+var_84], ax
0x18007a5f9  mov     rax, [rsi]
0x18007a5fc  lea     rdx, [rbp+37h+var_50]
0x18007a600  mov     rcx, rsi
0x18007a603  mov     rax, [rax+20h]
0x18007a607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a60c  mov     edi, eax
0x18007a60e  mov     [rbp+37h+var_88], eax
0x18007a611  test    eax, eax
0x18007a613  mov     eax, 0BCh
0x18007a618  js      loc_18007A891
0x18007a61e  mov     [rbp+37h+var_84], ax
0x18007a622  mov     rax, [rsi]
0x18007a625  lea     rdx, [rbp+37h+var_40]
0x18007a629  mov     rcx, rsi
0x18007a62c  mov     rax, [rax+0A8h]
0x18007a633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a638  mov     edi, eax
0x18007a63a  mov     [rbp+37h+var_88], eax
0x18007a63d  test    eax, eax
0x18007a63f  mov     eax, 0BDh
0x18007a644  js      loc_18007A891
0x18007a64a  mov     [rbp+37h+var_84], ax
0x18007a64e  mov     r14, [rbp+37h+var_A0]
0x18007a652  cmp     r14, rsi
0x18007a655  jz      short loc_18007A667
0x18007a657  mov     rdx, rsi; struct IUnknown *
0x18007a65a  lea     rcx, [rbp+37h+var_A0]; struct IUnknown **
0x18007a65e  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18007a663  mov     r14, [rbp+37h+var_A0]
0x18007a667  mov     rax, [r13+0]
0x18007a66b  lea     r8, [rbp+37h+arg_0]
0x18007a66f  lea     rdx, IID_ISdFileRecord
0x18007a676  mov     rcx, r13
0x18007a679  mov     rax, [rax+18h]
0x18007a67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a682  mov     edi, eax
0x18007a684  mov     ecx, eax
0x18007a686  mov     [rbp+37h+var_88], eax
0x18007a689  test    eax, eax
0x18007a68b  mov     eax, 0C1h
0x18007a690  js      loc_18007A891
0x18007a696  mov     esi, [rbp+37h+arg_18]
0x18007a699  mov     [rbp+37h+var_84], ax
0x18007a69d  cmp     ecx, 1
0x18007a6a0  jz      loc_18007A7FD
0x18007a6a6  mov     rcx, [rbp+37h+pv]; pv
0x18007a6aa  call    cs:__imp_CoTaskMemFree
0x18007a6b0  mov     [rbp+37h+pv], 0
0x18007a6b8  mov     rcx, [rbp+37h+arg_0]
0x18007a6bc  mov     rax, [rcx]
0x18007a6bf  lea     rdx, [rbp+37h+pv]
0x18007a6c3  mov     rax, [rax+20h]
0x18007a6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a6cc  mov     edi, eax
0x18007a6ce  mov     [rbp+37h+var_88], eax
0x18007a6d1  test    eax, eax
0x18007a6d3  mov     eax, 0C5h
0x18007a6d8  js      loc_18007A891
0x18007a6de  mov     [rbp+37h+var_84], ax
0x18007a6e2  mov     rax, [rbp+37h+var_50]
0x18007a6e6  mov     r8, [rbp+37h+pv]
0x18007a6ea  sub     r8, rax
0x18007a6ed  movzx   edx, word ptr [rax]
0x18007a6f0  movzx   ecx, word ptr [rax+r8]
0x18007a6f5  sub     edx, ecx
0x18007a6f7  jnz     short loc_18007A701
0x18007a6f9  add     rax, 2
0x18007a6fd  test    ecx, ecx
0x18007a6ff  jnz     short loc_18007A6ED
0x18007a701  test    edx, edx
0x18007a703  jnz     loc_18007A7FD
0x18007a709  mov     rcx, [rbp+37h+var_90]; pv
0x18007a70d  call    cs:__imp_CoTaskMemFree
0x18007a713  mov     [rbp+37h+var_90], 0
0x18007a71b  mov     rcx, [rbp+37h+arg_0]
0x18007a71f  mov     rax, [rcx]
0x18007a722  lea     rdx, [rbp+37h+var_90]
0x18007a726  mov     rax, [rax+18h]
0x18007a72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a72f  mov     edi, eax
0x18007a731  mov     [rbp+37h+var_88], eax
0x18007a734  test    eax, eax
0x18007a736  mov     eax, 0CDh
0x18007a73b  js      loc_18007A891
0x18007a741  mov     [rbp+37h+var_84], ax
0x18007a745  mov     rax, [rbp+37h+var_48]
0x18007a749  mov     r8, [rbp+37h+var_90]
0x18007a74d  sub     r8, rax
0x18007a750  movzx   edx, word ptr [rax]
0x18007a753  movzx   ecx, word ptr [rax+r8]
0x18007a758  sub     edx, ecx
0x18007a75a  jnz     short loc_18007A764
0x18007a75c  add     rax, 2
0x18007a760  test    ecx, ecx
0x18007a762  jnz     short loc_18007A750
0x18007a764  test    edx, edx
0x18007a766  jnz     loc_18007A7FD
0x18007a76c  mov     rcx, [rbp+37h+arg_0]
0x18007a770  mov     rax, [rcx]
0x18007a773  lea     rdx, [rbp+37h+var_38]
0x18007a777  mov     rax, [rax+0A8h]
0x18007a77e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a783  mov     edi, eax
0x18007a785  mov     [rbp+37h+var_88], eax
0x18007a788  test    eax, eax
0x18007a78a  mov     eax, 0D4h
0x18007a78f  js      loc_18007A891
0x18007a795  mov     [rbp+37h+var_84], ax
0x18007a799  mov     rax, [rbp+37h+var_38]
0x18007a79d  cmp     rax, rbx
0x18007a7a0  ja      short loc_18007A7FD
0x18007a7a2  test    esi, esi
0x18007a7a4  jz      short loc_18007A7C0
0x18007a7a6  mov     [rbp+37h+var_40], rax
0x18007a7aa  mov     rdx, [rbp+37h+arg_0]; struct IUnknown *
0x18007a7ae  cmp     r14, rdx
0x18007a7b1  jz      short loc_18007A7C0
0x18007a7b3  lea     rcx, [rbp+37h+var_A0]; struct IUnknown **
0x18007a7b7  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18007a7bc  mov     r14, [rbp+37h+var_A0]
0x18007a7c0  lea     rcx, [rbp+37h+arg_0]
0x18007a7c4  call    ?Release@?$CComPtrBase@UISdUniCursor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISdUniCursor>::Release(void)
0x18007a7c9  mov     rax, [r13+0]
0x18007a7cd  lea     r8, [rbp+37h+arg_0]
0x18007a7d1  lea     rdx, IID_ISdFileRecord
0x18007a7d8  mov     rcx, r13
0x18007a7db  mov     rax, [rax+18h]
0x18007a7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a7e4  mov     edi, eax
0x18007a7e6  mov     ecx, eax
0x18007a7e8  mov     [rbp+37h+var_88], eax
0x18007a7eb  test    eax, eax
0x18007a7ed  mov     eax, 0E8h
0x18007a7f2  jns     loc_18007A699
0x18007a7f8  jmp     loc_18007A891
0x18007a7fd  mov     [rbp+37h+var_A0], 0
0x18007a805  mov     rax, [rbp+37h+arg_28]
0x18007a809  mov     [rax], r14
0x18007a80c  test    r15, r15
0x18007a80f  jz      short loc_18007A822
0x18007a811  mov     rax, [rbp+37h+arg_0]
0x18007a815  mov     [rbp+37h+arg_0], 0
0x18007a81d  mov     [r15], rax
0x18007a820  jmp     short loc_18007A85C
0x18007a822  lea     rcx, [rbp+37h+arg_0]
0x18007a826  call    ?Release@?$CComPtrBase@UISdUniCursor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISdUniCursor>::Release(void)
0x18007a82b  mov     rax, [r13+0]
0x18007a82f  lea     r8, [rbp+37h+arg_0]
0x18007a833  lea     rdx, IID_ISdFileRecord
0x18007a83a  mov     rcx, r13
0x18007a83d  mov     rax, [rax+28h]
0x18007a841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a846  mov     edi, eax
0x18007a848  mov     [rbp+37h+var_88], eax
0x18007a84b  test    eax, eax
0x18007a84d  mov     eax, 0F6h
0x18007a852  js      short loc_18007A891
0x18007a854  mov     [rbp+37h+var_84], ax
0x18007a858  test    edi, edi
0x18007a85a  jnz     short loc_18007A87D
0x18007a85c  test    r12, r12
0x18007a85f  jz      short loc_18007A869
0x18007a861  mov     rax, [rbp+37h+var_40]
0x18007a865  mov     [r12], rax
0x18007a869  mov     [rbp+37h+var_88], 0
0x18007a870  mov     eax, 102h
0x18007a875  mov     [rbp+37h+var_84], ax
0x18007a879  xor     edi, edi
0x18007a87b  jmp     short loc_18007A895
0x18007a87d  mov     edi, 810000E8h
0x18007a882  mov     eax, 0F8h
0x18007a887  jmp     short loc_18007A88E
0x18007a889  mov     edi, 80070057h
0x18007a88e  mov     [rbp+37h+var_88], edi
0x18007a891  mov     [rbp+37h+var_82], ax
0x18007a895  lea     rcx, [rbp+37h+arg_0]
0x18007a899  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007a89e  nop
0x18007a89f  lea     rcx, [rbp+37h+var_A0]
0x18007a8a3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007a8a8  nop
0x18007a8a9  mov     rcx, [rbp+37h+var_50]; pv
0x18007a8ad  call    cs:__imp_CoTaskMemFree
0x18007a8b3  mov     [rbp+37h+var_50], 0
0x18007a8bb  mov     rcx, [rbp+37h+var_48]; pv
0x18007a8bf  call    cs:__imp_CoTaskMemFree
0x18007a8c5  mov     [rbp+37h+var_48], 0
0x18007a8cd  mov     rcx, [rbp+37h+pv]; pv
0x18007a8d1  call    cs:__imp_CoTaskMemFree
0x18007a8d7  mov     [rbp+37h+pv], 0
0x18007a8df  mov     rcx, [rbp+37h+var_90]; pv
0x18007a8e3  call    cs:__imp_CoTaskMemFree
0x18007a8e9  mov     [rbp+37h+var_90], 0
0x18007a8f1  lea     rcx, [rbp+37h+var_88]; this
0x18007a8f5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18007a8fa  mov     eax, edi
0x18007a8fc  mov     rbx, [rsp+0C0h+arg_8]
0x18007a904  add     rsp, 90h
0x18007a90b  pop     r15
0x18007a90d  pop     r14
0x18007a90f  pop     r13
0x18007a911  pop     r12
0x18007a913  pop     rdi
0x18007a914  pop     rsi
0x18007a915  pop     rbp
0x18007a916  retn
```
