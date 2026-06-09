# CWiaPropStg::GetPropsFromStorage(IPropertyStorage *,ulong *,tagPROPSPEC * *,tagPROPVARIANT * *)

- ea: `0x18005d490`
- end: `0x18005d873`
- name: `?GetPropsFromStorage@CWiaPropStg@@AEAAJPEAUIPropertyStorage@@PEAKPEAPEAUtagPROPSPEC@@PEAPEAUtagPROPVARIANT@@@Z`
- size: `995`
- prototype: `__int64 __fastcall(CWiaPropStg *__hidden this, struct IPropertyStorage *, unsigned int *, struct tagPROPSPEC **, struct tagPROPVARIANT **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18005da08`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18002de18`
- `0x18002def8`
- `0x18005d490`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005d776`
- `KERNEL32!LocalFree` at `0x18005d78a`
- `KERNEL32!LocalFree` at `0x18005d776`
- `KERNEL32!LocalFree` at `0x18005d78a`
- `KERNEL32!LocalAlloc` at `0x18005d52f`
- `KERNEL32!LocalAlloc` at `0x18005d546`
- `KERNEL32!LocalAlloc` at `0x18005d52f`
- `KERNEL32!LocalAlloc` at `0x18005d546`
- `ole32!CoTaskMemFree` at `0x18005d5e6`
- `ole32!CoTaskMemFree` at `0x18005d644`
- `ole32!CoTaskMemFree` at `0x18005d5e6`
- `ole32!CoTaskMemFree` at `0x18005d644`
- `ole32!PropVariantClear` at `0x18005d7ea`
- `ole32!PropVariantClear` at `0x18005d84f`
- `ole32!PropVariantClear` at `0x18005d7ea`
- `ole32!PropVariantClear` at `0x18005d84f`

## string_xrefs

- `0x18005d7f4`: `CWiaPropStg::GetPropsFromStream, reading WIA_NUM_PROPS_ID failed`
- `0x18005d81f`: `CWiaPropStg::GetPropsFromStream, reading WIA_NUM_PROPS_ID failed`
- `0x18005d667`: `CWiaPropStg::GetPropsFromStream, read multiple failed`
- `0x18005d68d`: `CWiaPropStg::GetPropsFromStream, read multiple failed`

## pseudocode

```c
__int64 __fastcall CWiaPropStg::GetPropsFromStorage(
        CWiaPropStg *this,
        struct IPropertyStorage *a2,
        unsigned int *a3,
        struct tagPROPSPEC **a4,
        struct tagPROPVARIANT **a5)
{
  struct IPropertyStorageVtbl *lpVtbl; // rax
  HRESULT (__stdcall *ReadMultiple)(IPropertyStorage *, ULONG, const PROPSPEC[], PROPVARIANT[]); // rax
  unsigned int v10; // ebx
  struct tagPROPSPEC *v11; // rdi
  struct tagPROPVARIANT *v12; // r14
  int v13; // esi
  int i; // ebx
  int v15; // eax
  __int64 v16; // rcx
  char *v17; // rbx
  void *v18; // rdx
  void **lpMem; // rax
  void *v20; // rdx
  __int64 v21; // rcx
  char *v22; // rbx
  void *v23; // rdx
  void **v24; // rax
  void *v25; // rdx
  __int64 v26; // rcx
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  char *v32; // rbx
  void *v33; // rdx
  void **v34; // rax
  void *v35; // rdx
  __int64 v36; // rcx
  char *v37; // rbx
  void *v38; // rdx
  void **v39; // rax
  void *v40; // rdx
  __int64 v41; // rcx
  char *v43; // rbx
  void *v44; // rdx
  void **v45; // rax
  void *v46; // rdx
  __int64 v47; // rcx
  struct tagPROPVARIANT **v48; // rax
  LPVOID pv[2]; // [rsp+30h] [rbp-48h] BYREF
  _DWORD v50[4]; // [rsp+40h] [rbp-38h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-28h] BYREF
  __int64 v52; // [rsp+60h] [rbp-18h]
  __int64 v53; // [rsp+C0h] [rbp+48h] BYREF

  v53 = 0;
  v52 = 0;
  lpVtbl = a2->lpVtbl;
  v50[2] = 111111;
  v50[0] = 1;
  ReadMultiple = lpVtbl->ReadMultiple;
  *(_OWORD *)pv = 0;
  *(_OWORD *)pvar = 0;
  if ( !((unsigned int (__fastcall *)(struct IPropertyStorage *, __int64, _DWORD *, PROPVARIANT *))ReadMultiple)(
          a2,
          1,
          v50,
          pvar) )
  {
    if ( SLODWORD(pvar[1]) < 0 || (unsigned __int64)SLODWORD(pvar[1]) > 0x5555555 )
    {
      v37 = (char *)WiaTrace_TraceLog("Invalid property count (%u), wrong storage? (E_FAIL)");
      WriteDbgTraceErrorWI("CWiaPropStg::GetPropsFromStorage", v37);
      WiaTrcLib::Free((WiaTrcLib *)v37, v38);
      v39 = (void **)WiaTrace_Trace("Invalid property count (%u), wrong storage? (E_FAIL)", LODWORD(pvar[1]));
      WiaTrace_ProcessTrace_Ex(v41, v40, (void *)"CWiaPropStg::GetPropsFromStorage", 1, v39);
      v10 = -2147467259;
      goto LABEL_31;
    }
    if ( !LODWORD(pvar[1]) )
    {
      v10 = 0;
LABEL_31:
      PropVariantClear(pvar);
      return v10;
    }
    v11 = (struct tagPROPSPEC *)LocalAlloc(0x40u, 16LL * SLODWORD(pvar[1]));
    v12 = (struct tagPROPVARIANT *)LocalAlloc(0x40u, 24LL * SLODWORD(pvar[1]));
    if ( v12 && v11 )
    {
      v13 = ((__int64 (__fastcall *)(struct IPropertyStorage *, __int64 *))a2->lpVtbl->Enum)(a2, &v53);
      if ( v13 < 0 )
      {
        v27 = (char *)WiaTrace_TraceLog("CWiaPropStg::GetPropsFromStream, Enum failed");
        WriteDbgTraceErrorWI("CWiaPropStg::GetPropsFromStorage", v27);
        WiaTrcLib::Free((WiaTrcLib *)v27, v28);
        v29 = (void **)WiaTrace_Trace("CWiaPropStg::GetPropsFromStream, Enum failed");
        WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"CWiaPropStg::GetPropsFromStorage", 1, v29);
LABEL_27:
        LocalFree(v11);
        v11 = 0;
LABEL_28:
        if ( v12 )
        {
          LocalFree(v12);
          v12 = 0;
        }
        goto LABEL_33;
      }
      for ( i = 0; i < SLODWORD(pvar[1]); ++i )
      {
        v15 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, _QWORD))(*(_QWORD *)v53 + 24LL))(v53, 1, pv, 0);
        if ( LODWORD(pv[1]) == 111111 )
          v15 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, _QWORD))(*(_QWORD *)v53 + 24LL))(v53, 1, pv, 0);
        if ( v15 )
        {
          v17 = (char *)WiaTrace_TraceLog("CWiaPropStg::GetPropsFromStream, error enumerating properties");
          WriteDbgTraceErrorWI("CWiaPropStg::GetPropsFromStorage", v17);
          WiaTrcLib::Free((WiaTrcLib *)v17, v18);
          lpMem = (void **)WiaTrace_Trace("CWiaPropStg::GetPropsFromStream, error enumerating properties");
          WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"CWiaPropStg::GetPropsFromStorage", 1, lpMem);
          v13 = -2147024809;
          if ( pv[0] )
            CoTaskMemFree(pv[0]);
          goto LABEL_22;
        }
        v16 = i;
        v11[v16].ulKind = 1;
        v11[v16].propid = (PROPID)pv[1];
        if ( pv[0] )
          CoTaskMemFree(pv[0]);
      }
      v13 = ((__int64 (__fastcall *)(struct IPropertyStorage *, _QWORD, struct tagPROPSPEC *, struct tagPROPVARIANT *))a2->lpVtbl->ReadMultiple)(
              a2,
              LODWORD(pvar[1]),
              v11,
              v12);
      if ( v13 )
      {
        v22 = (char *)WiaTrace_TraceLog("CWiaPropStg::GetPropsFromStream, read multiple failed");
        WriteDbgTraceErrorWI("CWiaPropStg::GetPropsFromStorage", v22);
        WiaTrcLib::Free((WiaTrcLib *)v22, v23);
        v24 = (void **)WiaTrace_Trace("CWiaPropStg::GetPropsFromStream, read multiple failed");
        WiaTrace_ProcessTrace_Ex(v26, v25, (void *)"CWiaPropStg::GetPropsFromStorage", 1, v24);
        if ( v13 == 1 )
          v13 = -2147024809;
      }
LABEL_22:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      if ( v13 >= 0 )
        goto LABEL_33;
    }
    else
    {
      v32 = (char *)WiaTrace_TraceLog("CWiaPropStg::GetPropsFromStream, out of memory");
      WriteDbgTraceErrorWI("CWiaPropStg::GetPropsFromStorage", v32);
      WiaTrcLib::Free((WiaTrcLib *)v32, v33);
      v34 = (void **)WiaTrace_Trace("CWiaPropStg::GetPropsFromStream, out of memory");
      WiaTrace_ProcessTrace_Ex(v36, v35, (void *)"CWiaPropStg::GetPropsFromStorage", 1, v34);
      v13 = -2147024882;
    }
    if ( !v11 )
      goto LABEL_28;
    goto LABEL_27;
  }
  v11 = 0;
  v12 = 0;
  v43 = (char *)WiaTrace_TraceLog("CWiaPropStg::GetPropsFromStream, reading WIA_NUM_PROPS_ID failed");
  WriteDbgTraceErrorWI("CWiaPropStg::GetPropsFromStorage", v43);
  WiaTrcLib::Free((WiaTrcLib *)v43, v44);
  v45 = (void **)WiaTrace_Trace("CWiaPropStg::GetPropsFromStream, reading WIA_NUM_PROPS_ID failed");
  WiaTrace_ProcessTrace_Ex(v47, v46, (void *)"CWiaPropStg::GetPropsFromStorage", 1, v45);
  v13 = -2147024809;
LABEL_33:
  *a3 = (unsigned int)pvar[1];
  PropVariantClear(pvar);
  v48 = a5;
  *a4 = v11;
  *v48 = v12;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18005d490  mov     [rsp-40h+arg_0], rcx
0x18005d495  push    rbp
0x18005d496  push    rbx
0x18005d497  push    rsi
0x18005d498  push    rdi
0x18005d499  push    r12
0x18005d49b  push    r13
0x18005d49d  push    r14
0x18005d49f  push    r15
0x18005d4a1  mov     rbp, rsp
0x18005d4a4  sub     rsp, 78h
0x18005d4a8  xor     eax, eax
0x18005d4aa  mov     [rbp+arg_0], 0
0x18005d4b2  mov     [rbp+var_18], rax
0x18005d4b6  mov     r15, rdx
0x18005d4b9  mov     rax, [rdx]
0x18005d4bc  xorps   xmm0, xmm0
0x18005d4bf  mov     esi, 1
0x18005d4c4  mov     [rbp+var_30], 1B207h
0x18005d4cb  mov     r12, r9
0x18005d4ce  mov     [rbp+var_38], esi
0x18005d4d1  mov     r13, r8
0x18005d4d4  lea     r9, [rbp+pvar]
0x18005d4d8  mov     rax, [rax+18h]
0x18005d4dc  lea     r8, [rbp+var_38]
0x18005d4e0  mov     edx, esi
0x18005d4e2  mov     rcx, r15
0x18005d4e5  movups  xmmword ptr [rbp+pv], xmm0
0x18005d4e9  movups  xmmword ptr [rbp+pvar], xmm0
0x18005d4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d4f2  test    eax, eax
0x18005d4f4  jnz     loc_18005D7F4
0x18005d4fa  movsxd  rdx, dword ptr [rbp+pvar+8]
0x18005d4fe  test    edx, edx
0x18005d500  js      loc_18005D798
0x18005d506  mov     rax, rdx
0x18005d509  cmp     rdx, 5555555h
0x18005d510  ja      loc_18005D798
0x18005d516  test    edx, edx
0x18005d518  jnz     short loc_18005D521
0x18005d51a  xor     ebx, ebx
0x18005d51c  jmp     loc_18005D7E6
0x18005d521  shl     rax, 4
0x18005d525  mov     ebx, 40h ; '@'
0x18005d52a  mov     rdx, rax; uBytes
0x18005d52d  mov     ecx, ebx; uFlags
0x18005d52f  call    cs:__imp_LocalAlloc
0x18005d535  movsxd  rdx, dword ptr [rbp+pvar+8]
0x18005d539  mov     ecx, ebx; uFlags
0x18005d53b  mov     rdi, rax
0x18005d53e  lea     rdx, [rdx+rdx*2]
0x18005d542  shl     rdx, 3; uBytes
0x18005d546  call    cs:__imp_LocalAlloc
0x18005d54c  mov     r14, rax
0x18005d54f  test    rax, rax
0x18005d552  jz      loc_18005D723
0x18005d558  test    rdi, rdi
0x18005d55b  jz      loc_18005D723
0x18005d561  mov     rcx, [r15]
0x18005d564  lea     rdx, [rbp+arg_0]
0x18005d568  mov     rax, [rcx+58h]
0x18005d56c  mov     rcx, r15
0x18005d56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d574  mov     esi, eax
0x18005d576  test    eax, eax
0x18005d578  js      loc_18005D6D8
0x18005d57e  xor     ebx, ebx
0x18005d580  lea     esi, [rbx+1]
0x18005d583  mov     edx, dword ptr [rbp+pvar+8]
0x18005d586  cmp     ebx, edx
0x18005d588  jge     loc_18005D64C
0x18005d58e  mov     rcx, [rbp+arg_0]
0x18005d592  lea     r8, [rbp+pv]
0x18005d596  xor     r9d, r9d
0x18005d599  mov     edx, esi
0x18005d59b  mov     rax, [rcx]
0x18005d59e  mov     rax, [rax+18h]
0x18005d5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d5a7  cmp     dword ptr [rbp+pv+8], 1B207h
0x18005d5ae  jnz     short loc_18005D5C9
0x18005d5b0  mov     rcx, [rbp+arg_0]
0x18005d5b4  lea     r8, [rbp+pv]
0x18005d5b8  xor     r9d, r9d
0x18005d5bb  mov     edx, esi
0x18005d5bd  mov     rax, [rcx]
0x18005d5c0  mov     rax, [rax+18h]
0x18005d5c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d5c9  test    eax, eax
0x18005d5cb  jnz     short loc_18005D5F0
0x18005d5cd  movsxd  rcx, ebx
0x18005d5d0  add     rcx, rcx
0x18005d5d3  mov     [rdi+rcx*8], esi
0x18005d5d6  mov     eax, dword ptr [rbp+pv+8]
0x18005d5d9  mov     [rdi+rcx*8+8], eax
0x18005d5dd  mov     rcx, [rbp+pv]; pv
0x18005d5e1  test    rcx, rcx
0x18005d5e4  jz      short loc_18005D5EC
0x18005d5e6  call    cs:__imp_CoTaskMemFree
0x18005d5ec  add     ebx, esi
0x18005d5ee  jmp     short loc_18005D583
0x18005d5f0  lea     rcx, aCwiapropstgGet; "CWiaPropStg::GetPropsFromStream, error "...
0x18005d5f7  call    WiaTrace_TraceLog
0x18005d5fc  mov     rdx, rax; char *
0x18005d5ff  lea     rcx, aCwiapropstgGet_7; "CWiaPropStg::GetPropsFromStorage"
0x18005d606  mov     rbx, rax
0x18005d609  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005d60e  mov     rcx, rbx; this
0x18005d611  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005d616  lea     rcx, aCwiapropstgGet; "CWiaPropStg::GetPropsFromStream, error "...
0x18005d61d  call    WiaTrace_Trace
0x18005d622  mov     r9d, esi; int
0x18005d625  mov     [rsp+78h+lpMem], rax; lpMem
0x18005d62a  lea     r8, aCwiapropstgGet_7; "CWiaPropStg::GetPropsFromStorage"
0x18005d631  call    WiaTrace_ProcessTrace_Ex
0x18005d636  mov     rcx, [rbp+pv]; pv
0x18005d63a  mov     esi, 80070057h
0x18005d63f  test    rcx, rcx
0x18005d642  jz      short loc_18005D6BB
0x18005d644  call    cs:__imp_CoTaskMemFree
0x18005d64a  jmp     short loc_18005D6BB
0x18005d64c  mov     rax, [r15]
0x18005d64f  mov     r9, r14
0x18005d652  mov     r8, rdi
0x18005d655  mov     rcx, r15
0x18005d658  mov     rax, [rax+18h]
0x18005d65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d661  mov     esi, eax
0x18005d663  test    eax, eax
0x18005d665  jz      short loc_18005D6BB
0x18005d667  lea     rcx, aCwiapropstgGet_0; "CWiaPropStg::GetPropsFromStream, read m"...
0x18005d66e  call    WiaTrace_TraceLog
0x18005d673  mov     rdx, rax; char *
0x18005d676  lea     rcx, aCwiapropstgGet_7; "CWiaPropStg::GetPropsFromStorage"
0x18005d67d  mov     rbx, rax
0x18005d680  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005d685  mov     rcx, rbx; this
0x18005d688  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005d68d  lea     rcx, aCwiapropstgGet_0; "CWiaPropStg::GetPropsFromStream, read m"...
0x18005d694  call    WiaTrace_Trace
0x18005d699  mov     r9d, 1; int
0x18005d69f  mov     [rsp+78h+lpMem], rax; lpMem
0x18005d6a4  lea     r8, aCwiapropstgGet_7; "CWiaPropStg::GetPropsFromStorage"
0x18005d6ab  call    WiaTrace_ProcessTrace_Ex
0x18005d6b0  cmp     esi, 1
0x18005d6b3  mov     eax, 80070057h
0x18005d6b8  cmovz   esi, eax
0x18005d6bb  mov     rcx, [rbp+arg_0]
0x18005d6bf  mov     rax, [rcx]
0x18005d6c2  mov     rax, [rax+10h]
0x18005d6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d6cb  test    esi, esi
0x18005d6cd  jns     loc_18005D844
0x18005d6d3  jmp     loc_18005D76E
0x18005d6d8  lea     rcx, aCwiapropstgGet_2; "CWiaPropStg::GetPropsFromStream, Enum f"...
0x18005d6df  call    WiaTrace_TraceLog
0x18005d6e4  mov     rdx, rax; char *
0x18005d6e7  lea     rcx, aCwiapropstgGet_7; "CWiaPropStg::GetPropsFromStorage"
0x18005d6ee  mov     rbx, rax
0x18005d6f1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005d6f6  mov     rcx, rbx; this
0x18005d6f9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005d6fe  lea     rcx, aCwiapropstgGet_2; "CWiaPropStg::GetPropsFromStream, Enum f"...
0x18005d705  call    WiaTrace_Trace
0x18005d70a  mov     r9d, 1; int
0x18005d710  mov     [rsp+78h+lpMem], rax; lpMem
0x18005d715  lea     r8, aCwiapropstgGet_7; "CWiaPropStg::GetPropsFromStorage"
0x18005d71c  call    WiaTrace_ProcessTrace_Ex
0x18005d721  jmp     short loc_18005D773
0x18005d723  lea     rcx, aCwiapropstgGet_6; "CWiaPropStg::GetPropsFromStream, out of"...
0x18005d72a  call    WiaTrace_TraceLog
0x18005d72f  mov     rdx, rax; char *
0x18005d732  lea     rcx, aCwiapropstgGet_7; "CWiaPropStg::GetPropsFromStorage"
0x18005d739  mov     rbx, rax
0x18005d73c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005d741  mov     rcx, rbx; this
0x18005d744  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005d749  lea     rcx, aCwiapropstgGet_6; "CWiaPropStg::GetPropsFromStream, out of"...
0x18005d750  call    WiaTrace_Trace
0x18005d755  mov     r9d, esi; int
0x18005d758  mov     [rsp+78h+lpMem], rax; lpMem
0x18005d75d  lea     r8, aCwiapropstgGet_7; "CWiaPropStg::GetPropsFromStorage"
0x18005d764  call    WiaTrace_ProcessTrace_Ex
0x18005d769  mov     esi, 8007000Eh
0x18005d76e  test    rdi, rdi
0x18005d771  jz      short loc_18005D77E
0x18005d773  mov     rcx, rdi; hMem
0x18005d776  call    cs:__imp_LocalFree
0x18005d77c  xor     edi, edi
0x18005d77e  test    r14, r14
0x18005d781  jz      loc_18005D844
0x18005d787  mov     rcx, r14; hMem
0x18005d78a  call    cs:__imp_LocalFree
0x18005d790  xor     r14d, r14d
0x18005d793  jmp     loc_18005D844
0x18005d798  lea     rcx, aInvalidPropert; "Invalid property count (%u), wrong stor"...
0x18005d79f  call    WiaTrace_TraceLog
0x18005d7a4  mov     rdx, rax; char *
0x18005d7a7  lea     rcx, aCwiapropstgGet_7; "CWiaPropStg::GetPropsFromStorage"
0x18005d7ae  mov     rbx, rax
0x18005d7b1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005d7b6  mov     rcx, rbx; this
0x18005d7b9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005d7be  mov     edx, dword ptr [rbp+pvar+8]
0x18005d7c1  lea     rcx, aInvalidPropert; "Invalid property count (%u), wrong stor"...
0x18005d7c8  call    WiaTrace_Trace
0x18005d7cd  mov     r9d, esi; int
0x18005d7d0  mov     [rsp+78h+lpMem], rax; lpMem
0x18005d7d5  lea     r8, aCwiapropstgGet_7; "CWiaPropStg::GetPropsFromStorage"
0x18005d7dc  call    WiaTrace_ProcessTrace_Ex
0x18005d7e1  mov     ebx, 80004005h
0x18005d7e6  lea     rcx, [rbp+pvar]; pvar
0x18005d7ea  call    cs:__imp_PropVariantClear
0x18005d7f0  mov     eax, ebx
0x18005d7f2  jmp     short loc_18005D862
0x18005d7f4  lea     rcx, aCwiapropstgGet_8; "CWiaPropStg::GetPropsFromStream, readin"...
0x18005d7fb  xor     edi, edi
0x18005d7fd  xor     r14d, r14d
0x18005d800  call    WiaTrace_TraceLog
0x18005d805  mov     rdx, rax; char *
0x18005d808  lea     rcx, aCwiapropstgGet_7; "CWiaPropStg::GetPropsFromStorage"
0x18005d80f  mov     rbx, rax
0x18005d812  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18005d817  mov     rcx, rbx; this
0x18005d81a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005d81f  lea     rcx, aCwiapropstgGet_8; "CWiaPropStg::GetPropsFromStream, readin"...
0x18005d826  call    WiaTrace_Trace
0x18005d82b  mov     r9d, esi; int
0x18005d82e  mov     [rsp+78h+lpMem], rax; lpMem
0x18005d833  lea     r8, aCwiapropstgGet_7; "CWiaPropStg::GetPropsFromStorage"
0x18005d83a  call    WiaTrace_ProcessTrace_Ex
0x18005d83f  mov     esi, 80070057h
0x18005d844  mov     eax, dword ptr [rbp+pvar+8]
0x18005d847  lea     rcx, [rbp+pvar]; pvar
0x18005d84b  mov     [r13+0], eax
0x18005d84f  call    cs:__imp_PropVariantClear
0x18005d855  mov     rax, [rbp+arg_20]
0x18005d859  mov     [r12], rdi
0x18005d85d  mov     [rax], r14
0x18005d860  mov     eax, esi
0x18005d862  add     rsp, 78h
0x18005d866  pop     r15
0x18005d868  pop     r14
0x18005d86a  pop     r13
0x18005d86c  pop     r12
0x18005d86e  pop     rdi
0x18005d86f  pop     rsi
0x18005d870  pop     rbx
0x18005d871  pop     rbp
0x18005d872  retn
```
