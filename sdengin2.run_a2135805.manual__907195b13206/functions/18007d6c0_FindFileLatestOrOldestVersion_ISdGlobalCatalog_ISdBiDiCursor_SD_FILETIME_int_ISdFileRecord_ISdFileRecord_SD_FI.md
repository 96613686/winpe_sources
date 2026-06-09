# FindFileLatestOrOldestVersion(ISdGlobalCatalog *,ISdBiDiCursor *,SD_FILETIME,int,ISdFileRecord *,ISdFileRecord * *,SD_FILETIME *,ISdFileRecord * *)

- ea: `0x18007d6c0`
- end: `0x18007db4c`
- name: `?FindFileLatestOrOldestVersion@@YAJPEAUISdGlobalCatalog@@PEAUISdBiDiCursor@@TSD_FILETIME@@HPEAUISdFileRecord@@PEAPEAU4@PEAT3@4@Z`
- size: `1164`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007db54`
- `0x18007dc04`

## callees

- `0x180003520`
- `0x180003540`
- `0x180004080`
- `0x18001646c`
- `0x180072e08`
- `0x180072f14`
- `0x18007d6c0`
- `0x1800d1010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007d8ba`
- `ole32!CoTaskMemFree` at `0x18007d923`
- `ole32!CoTaskMemFree` at `0x18007dac9`
- `ole32!CoTaskMemFree` at `0x18007dae1`
- `ole32!CoTaskMemFree` at `0x18007daf9`
- `ole32!CoTaskMemFree` at `0x18007db11`
- `ole32!CoTaskMemFree` at `0x18007d8ba`
- `ole32!CoTaskMemFree` at `0x18007d923`
- `ole32!CoTaskMemFree` at `0x18007dac9`
- `ole32!CoTaskMemFree` at `0x18007dae1`
- `ole32!CoTaskMemFree` at `0x18007daf9`
- `ole32!CoTaskMemFree` at `0x18007db11`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v33, "FindFileLatestOrOldestVersion", 0xA8u, 1u);
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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
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
0x18007d6c0  mov     [rsp-8+arg_8], rbx
0x18007d6c5  mov     [rsp-8+arg_18], r9d
0x18007d6ca  push    rbp
0x18007d6cb  push    rsi
0x18007d6cc  push    rdi
0x18007d6cd  push    r12
0x18007d6cf  push    r13
0x18007d6d1  push    r14
0x18007d6d3  push    r15
0x18007d6d5  lea     rbp, [rsp-7]
0x18007d6da  sub     rsp, 90h
0x18007d6e1  mov     rbx, r8
0x18007d6e4  mov     r13, rdx
0x18007d6e7  mov     rdi, rcx
0x18007d6ea  mov     r9d, 1; unsigned __int16
0x18007d6f0  mov     r8d, 0A8h; unsigned __int16
0x18007d6f6  lea     rdx, aFindfilelatest; "FindFileLatestOrOldestVersion"
0x18007d6fd  lea     rcx, [rbp+37h+var_88]; this
0x18007d701  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18007d706  mov     [rbp+37h+var_38], 0
0x18007d70e  mov     [rbp+37h+var_40], 0
0x18007d716  lea     rcx, [rbp+37h+var_90]; void *
0x18007d71a  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18007d71f  lea     rcx, [rbp+37h+pv]; void *
0x18007d723  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18007d728  lea     rcx, [rbp+37h+var_48]; void *
0x18007d72c  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18007d731  lea     rcx, [rbp+37h+var_50]; void *
0x18007d735  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18007d73a  lea     rcx, [rbp+37h+var_A0]; void *
0x18007d73e  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18007d743  lea     rcx, [rbp+37h+arg_0]; void *
0x18007d747  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18007d74c  mov     rcx, [rbp+37h+arg_28]
0x18007d750  test    rcx, rcx
0x18007d753  jz      short loc_18007D75C
0x18007d755  mov     qword ptr [rcx], 0
0x18007d75c  mov     r12, [rbp+37h+arg_30]
0x18007d760  test    r12, r12
0x18007d763  jz      short loc_18007D77D
0x18007d765  mov     ecx, 8
0x18007d76a  mov     rax, r12
0x18007d76d  mov     byte ptr [rax], 0
0x18007d770  inc     rax
0x18007d773  sub     rcx, 1
0x18007d777  jnz     short loc_18007D76D
0x18007d779  mov     rcx, [rbp+37h+arg_28]
0x18007d77d  mov     r15, [rbp+37h+arg_38]
0x18007d781  test    r15, r15
0x18007d784  jz      short loc_18007D78D
0x18007d786  mov     qword ptr [r15], 0
0x18007d78d  mov     eax, 0B6h
0x18007d792  test    rdi, rdi
0x18007d795  jz      loc_18007DAA5
0x18007d79b  mov     [rbp+37h+var_84], ax
0x18007d79f  mov     eax, 0B7h
0x18007d7a4  test    r13, r13
0x18007d7a7  jz      loc_18007DAA5
0x18007d7ad  mov     [rbp+37h+var_84], ax
0x18007d7b1  mov     rsi, [rbp+37h+arg_20]
0x18007d7b5  mov     eax, 0B8h
0x18007d7ba  test    rsi, rsi
0x18007d7bd  jz      loc_18007DAA5
0x18007d7c3  mov     [rbp+37h+var_84], ax
0x18007d7c7  mov     eax, 0B9h
0x18007d7cc  test    rcx, rcx
0x18007d7cf  jz      loc_18007DAA5
0x18007d7d5  mov     [rbp+37h+var_88], 0
0x18007d7dc  mov     [rbp+37h+var_84], ax
0x18007d7e0  mov     rax, [rsi]
0x18007d7e3  lea     rdx, [rbp+37h+var_48]
0x18007d7e7  mov     rcx, rsi
0x18007d7ea  mov     rax, [rax+18h]
0x18007d7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d7f3  mov     edi, eax
0x18007d7f5  mov     [rbp+37h+var_88], eax
0x18007d7f8  test    eax, eax
0x18007d7fa  mov     eax, 0BBh
0x18007d7ff  js      loc_18007DAAD
0x18007d805  mov     [rbp+37h+var_84], ax
0x18007d809  mov     rax, [rsi]
0x18007d80c  lea     rdx, [rbp+37h+var_50]
0x18007d810  mov     rcx, rsi
0x18007d813  mov     rax, [rax+20h]
0x18007d817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d81c  mov     edi, eax
0x18007d81e  mov     [rbp+37h+var_88], eax
0x18007d821  test    eax, eax
0x18007d823  mov     eax, 0BCh
0x18007d828  js      loc_18007DAAD
0x18007d82e  mov     [rbp+37h+var_84], ax
0x18007d832  mov     rax, [rsi]
0x18007d835  lea     rdx, [rbp+37h+var_40]
0x18007d839  mov     rcx, rsi
0x18007d83c  mov     rax, [rax+0A8h]
0x18007d843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d848  mov     edi, eax
0x18007d84a  mov     [rbp+37h+var_88], eax
0x18007d84d  test    eax, eax
0x18007d84f  mov     eax, 0BDh
0x18007d854  js      loc_18007DAAD
0x18007d85a  mov     [rbp+37h+var_84], ax
0x18007d85e  mov     r14, [rbp+37h+var_A0]
0x18007d862  cmp     r14, rsi
0x18007d865  jz      short loc_18007D877
0x18007d867  mov     rdx, rsi; struct IUnknown *
0x18007d86a  lea     rcx, [rbp+37h+var_A0]; struct IUnknown **
0x18007d86e  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18007d873  mov     r14, [rbp+37h+var_A0]
0x18007d877  mov     rax, [r13+0]
0x18007d87b  lea     r8, [rbp+37h+arg_0]
0x18007d87f  lea     rdx, IID_ISdFileRecord
0x18007d886  mov     rcx, r13
0x18007d889  mov     rax, [rax+18h]
0x18007d88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d892  mov     edi, eax
0x18007d894  mov     ecx, eax
0x18007d896  mov     [rbp+37h+var_88], eax
0x18007d899  test    eax, eax
0x18007d89b  mov     eax, 0C1h
0x18007d8a0  js      loc_18007DAAD
0x18007d8a6  mov     esi, [rbp+37h+arg_18]
0x18007d8a9  mov     [rbp+37h+var_84], ax
0x18007d8ad  cmp     ecx, 1
0x18007d8b0  jz      loc_18007DA19
0x18007d8b6  mov     rcx, [rbp+37h+pv]; pv
0x18007d8ba  call    cs:__imp_CoTaskMemFree
0x18007d8c1  nop     dword ptr [rax+rax+00h]
0x18007d8c6  mov     [rbp+37h+pv], 0
0x18007d8ce  mov     rcx, [rbp+37h+arg_0]
0x18007d8d2  mov     rax, [rcx]
0x18007d8d5  lea     rdx, [rbp+37h+pv]
0x18007d8d9  mov     rax, [rax+20h]
0x18007d8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d8e2  mov     edi, eax
0x18007d8e4  mov     [rbp+37h+var_88], eax
0x18007d8e7  test    eax, eax
0x18007d8e9  mov     eax, 0C5h
0x18007d8ee  js      loc_18007DAAD
0x18007d8f4  mov     [rbp+37h+var_84], ax
0x18007d8f8  mov     rax, [rbp+37h+var_50]
0x18007d8fc  mov     r8, [rbp+37h+pv]
0x18007d900  sub     r8, rax
0x18007d903  movzx   edx, word ptr [rax]
0x18007d906  movzx   ecx, word ptr [rax+r8]
0x18007d90b  sub     edx, ecx
0x18007d90d  jnz     short loc_18007D917
0x18007d90f  add     rax, 2
0x18007d913  test    ecx, ecx
0x18007d915  jnz     short loc_18007D903
0x18007d917  test    edx, edx
0x18007d919  jnz     loc_18007DA19
0x18007d91f  mov     rcx, [rbp+37h+var_90]; pv
0x18007d923  call    cs:__imp_CoTaskMemFree
0x18007d92a  nop     dword ptr [rax+rax+00h]
0x18007d92f  mov     [rbp+37h+var_90], 0
0x18007d937  mov     rcx, [rbp+37h+arg_0]
0x18007d93b  mov     rax, [rcx]
0x18007d93e  lea     rdx, [rbp+37h+var_90]
0x18007d942  mov     rax, [rax+18h]
0x18007d946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d94b  mov     edi, eax
0x18007d94d  mov     [rbp+37h+var_88], eax
0x18007d950  test    eax, eax
0x18007d952  mov     eax, 0CDh
0x18007d957  js      loc_18007DAAD
0x18007d95d  mov     [rbp+37h+var_84], ax
0x18007d961  mov     rax, [rbp+37h+var_48]
0x18007d965  mov     r8, [rbp+37h+var_90]
0x18007d969  sub     r8, rax
0x18007d96c  movzx   edx, word ptr [rax]
0x18007d96f  movzx   ecx, word ptr [rax+r8]
0x18007d974  sub     edx, ecx
0x18007d976  jnz     short loc_18007D980
0x18007d978  add     rax, 2
0x18007d97c  test    ecx, ecx
0x18007d97e  jnz     short loc_18007D96C
0x18007d980  test    edx, edx
0x18007d982  jnz     loc_18007DA19
0x18007d988  mov     rcx, [rbp+37h+arg_0]
0x18007d98c  mov     rax, [rcx]
0x18007d98f  lea     rdx, [rbp+37h+var_38]
0x18007d993  mov     rax, [rax+0A8h]
0x18007d99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d99f  mov     edi, eax
0x18007d9a1  mov     [rbp+37h+var_88], eax
0x18007d9a4  test    eax, eax
0x18007d9a6  mov     eax, 0D4h
0x18007d9ab  js      loc_18007DAAD
0x18007d9b1  mov     [rbp+37h+var_84], ax
0x18007d9b5  mov     rax, [rbp+37h+var_38]
0x18007d9b9  cmp     rax, rbx
0x18007d9bc  ja      short loc_18007DA19
0x18007d9be  test    esi, esi
0x18007d9c0  jz      short loc_18007D9DC
0x18007d9c2  mov     [rbp+37h+var_40], rax
0x18007d9c6  mov     rdx, [rbp+37h+arg_0]; struct IUnknown *
0x18007d9ca  cmp     r14, rdx
0x18007d9cd  jz      short loc_18007D9DC
0x18007d9cf  lea     rcx, [rbp+37h+var_A0]; struct IUnknown **
0x18007d9d3  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18007d9d8  mov     r14, [rbp+37h+var_A0]
0x18007d9dc  lea     rcx, [rbp+37h+arg_0]
0x18007d9e0  call    ?Release@?$CComPtrBase@UISdUniCursor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISdUniCursor>::Release(void)
0x18007d9e5  mov     rax, [r13+0]
0x18007d9e9  lea     r8, [rbp+37h+arg_0]
0x18007d9ed  lea     rdx, IID_ISdFileRecord
0x18007d9f4  mov     rcx, r13
0x18007d9f7  mov     rax, [rax+18h]
0x18007d9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da00  mov     edi, eax
0x18007da02  mov     ecx, eax
0x18007da04  mov     [rbp+37h+var_88], eax
0x18007da07  test    eax, eax
0x18007da09  mov     eax, 0E8h
0x18007da0e  jns     loc_18007D8A9
0x18007da14  jmp     loc_18007DAAD
0x18007da19  mov     [rbp+37h+var_A0], 0
0x18007da21  mov     rax, [rbp+37h+arg_28]
0x18007da25  mov     [rax], r14
0x18007da28  test    r15, r15
0x18007da2b  jz      short loc_18007DA3E
0x18007da2d  mov     rax, [rbp+37h+arg_0]
0x18007da31  mov     [rbp+37h+arg_0], 0
0x18007da39  mov     [r15], rax
0x18007da3c  jmp     short loc_18007DA78
0x18007da3e  lea     rcx, [rbp+37h+arg_0]
0x18007da42  call    ?Release@?$CComPtrBase@UISdUniCursor@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISdUniCursor>::Release(void)
0x18007da47  mov     rax, [r13+0]
0x18007da4b  lea     r8, [rbp+37h+arg_0]
0x18007da4f  lea     rdx, IID_ISdFileRecord
0x18007da56  mov     rcx, r13
0x18007da59  mov     rax, [rax+28h]
0x18007da5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007da62  mov     edi, eax
0x18007da64  mov     [rbp+37h+var_88], eax
0x18007da67  test    eax, eax
0x18007da69  mov     eax, 0F6h
0x18007da6e  js      short loc_18007DAAD
0x18007da70  mov     [rbp+37h+var_84], ax
0x18007da74  test    edi, edi
0x18007da76  jnz     short loc_18007DA99
0x18007da78  test    r12, r12
0x18007da7b  jz      short loc_18007DA85
0x18007da7d  mov     rax, [rbp+37h+var_40]
0x18007da81  mov     [r12], rax
0x18007da85  mov     [rbp+37h+var_88], 0
0x18007da8c  mov     eax, 102h
0x18007da91  mov     [rbp+37h+var_84], ax
0x18007da95  xor     edi, edi
0x18007da97  jmp     short loc_18007DAB1
0x18007da99  mov     edi, 810000E8h
0x18007da9e  mov     eax, 0F8h
0x18007daa3  jmp     short loc_18007DAAA
0x18007daa5  mov     edi, 80070057h
0x18007daaa  mov     [rbp+37h+var_88], edi
0x18007daad  mov     [rbp+37h+var_82], ax
0x18007dab1  lea     rcx, [rbp+37h+arg_0]
0x18007dab5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007daba  nop
0x18007dabb  lea     rcx, [rbp+37h+var_A0]
0x18007dabf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18007dac4  nop
0x18007dac5  mov     rcx, [rbp+37h+var_50]; pv
0x18007dac9  call    cs:__imp_CoTaskMemFree
0x18007dad0  nop     dword ptr [rax+rax+00h]
0x18007dad5  mov     [rbp+37h+var_50], 0
0x18007dadd  mov     rcx, [rbp+37h+var_48]; pv
0x18007dae1  call    cs:__imp_CoTaskMemFree
0x18007dae8  nop     dword ptr [rax+rax+00h]
0x18007daed  mov     [rbp+37h+var_48], 0
0x18007daf5  mov     rcx, [rbp+37h+pv]; pv
0x18007daf9  call    cs:__imp_CoTaskMemFree
0x18007db00  nop     dword ptr [rax+rax+00h]
0x18007db05  mov     [rbp+37h+pv], 0
0x18007db0d  mov     rcx, [rbp+37h+var_90]; pv
0x18007db11  call    cs:__imp_CoTaskMemFree
0x18007db18  nop     dword ptr [rax+rax+00h]
0x18007db1d  mov     [rbp+37h+var_90], 0
0x18007db25  lea     rcx, [rbp+37h+var_88]; this
0x18007db29  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18007db2e  mov     eax, edi
0x18007db30  mov     rbx, [rsp+0C0h+arg_8]
0x18007db38  add     rsp, 90h
0x18007db3f  pop     r15
0x18007db41  pop     r14
0x18007db43  pop     r13
0x18007db45  pop     r12
0x18007db47  pop     rdi
0x18007db48  pop     rsi
0x18007db49  pop     rbp
0x18007db4a  retn
```
