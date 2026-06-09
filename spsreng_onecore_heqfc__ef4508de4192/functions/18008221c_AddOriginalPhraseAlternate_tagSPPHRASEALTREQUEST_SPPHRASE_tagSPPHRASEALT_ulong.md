# AddOriginalPhraseAlternate(tagSPPHRASEALTREQUEST *,SPPHRASE *,tagSPPHRASEALT *,ulong *)

- ea: `0x18008221c`
- end: `0x18008233a`
- name: `?AddOriginalPhraseAlternate@@YAJPEAUtagSPPHRASEALTREQUEST@@PEAUSPPHRASE@@PEAUtagSPPHRASEALT@@PEAK@Z`
- size: `286`
- prototype: `__int64 __fastcall(struct tagSPPHRASEALTREQUEST *, struct SPPHRASE *, struct tagSPPHRASEALT *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009cd0`

## callees

- `0x180002db8`
- `0x18008221c`
- `0x180082b2c`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008231a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008231a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180082294`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180082294`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AddOriginalPhraseAlternate(
        struct tagSPPHRASEALTREQUEST *a1,
        struct SPPHRASE *a2,
        struct tagSPPHRASEALT *a3,
        unsigned int *a4)
{
  HRESULT v8; // ebx
  __int64 v9; // rcx
  ISpPhraseBuilder *v10; // rax
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+10h] BYREF

  ppv = a2;
  if ( *a4 >= a1->ulRequestAltCount )
    return 0;
  ppv = 0;
  pv = 0;
  v8 = ((__int64 (__fastcall *)(ISpPhrase *, LPVOID *))a1->pPhrase->lpVtbl->GetPhrase)(a1->pPhrase, &pv);
  if ( v8 >= 0 )
  {
    v8 = CoCreateInstance(&CLSID_SpPhraseBuilder, 0, 0x17u, &GUID_88a3342a_0bed_4834_922b_88d43173162f, &ppv);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 56LL))(ppv, pv);
      if ( v8 >= 0 )
      {
        v9 = *a4;
        v10 = (ISpPhraseBuilder *)ppv;
        ppv = 0;
        a3[v9].pPhrase = v10;
        a3[v9].ulStartElementInParent = a1->ulStartElement;
        a3[v9].cElementsInParent = a1->cElements;
        a3[v9].cElementsInAlternate = a1->cElements;
        a3[v9].cbAltExtra = 0;
        a3[v9].pvAltExtra = 0;
        if ( !ConfirmOrFreeLastAlternate(a1, a3, a4, 0) )
          v8 = -2147467259;
      }
    }
  }
  CoTaskMemFree(pv);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008221c  mov     [rsp+arg_10], rbx
0x180082221  mov     [rsp+arg_8], rdx
0x180082226  push    rbp
0x180082227  push    rsi
0x180082228  push    rdi
0x180082229  sub     rsp, 30h
0x18008222d  mov     rbp, r9
0x180082230  mov     rsi, r8
0x180082233  mov     rdi, rcx
0x180082236  mov     eax, [rcx+8]
0x180082239  cmp     [r9], eax
0x18008223c  jb      short loc_180082245
0x18008223e  xor     eax, eax
0x180082240  jmp     loc_18008232D
0x180082245  mov     [rsp+48h+arg_8], 0
0x18008224e  mov     [rsp+48h+pv], 0
0x180082257  mov     rcx, [rcx+20h]
0x18008225b  mov     rax, [rcx]
0x18008225e  lea     rdx, [rsp+48h+pv]
0x180082263  mov     rax, [rax+18h]
0x180082267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008226c  mov     ebx, eax
0x18008226e  test    eax, eax
0x180082270  js      loc_180082315
0x180082276  lea     rax, [rsp+48h+arg_8]
0x18008227b  mov     [rsp+48h+ppv], rax; ppv
0x180082280  lea     r9, _GUID_88a3342a_0bed_4834_922b_88d43173162f; riid
0x180082287  xor     edx, edx; pUnkOuter
0x180082289  lea     r8d, [rdx+17h]; dwClsContext
0x18008228d  lea     rcx, CLSID_SpPhraseBuilder; rclsid
0x180082294  call    cs:__imp_CoCreateInstance
0x18008229a  mov     ebx, eax
0x18008229c  test    eax, eax
0x18008229e  js      short loc_180082315
0x1800822a0  mov     rcx, [rsp+48h+arg_8]
0x1800822a5  mov     rax, [rcx]
0x1800822a8  mov     rdx, [rsp+48h+pv]
0x1800822ad  mov     rax, [rax+38h]
0x1800822b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800822b6  mov     ebx, eax
0x1800822b8  test    eax, eax
0x1800822ba  js      short loc_180082315
0x1800822bc  mov     eax, [rbp+0]
0x1800822bf  lea     rcx, [rax+rax*4]
0x1800822c3  mov     rax, [rsp+48h+arg_8]
0x1800822c8  mov     [rsp+48h+arg_8], 0
0x1800822d1  mov     [rsi+rcx*8], rax
0x1800822d5  mov     eax, [rdi]
0x1800822d7  mov     [rsi+rcx*8+8], eax
0x1800822db  mov     eax, [rdi+4]
0x1800822de  mov     [rsi+rcx*8+0Ch], eax
0x1800822e2  mov     eax, [rdi+4]
0x1800822e5  mov     [rsi+rcx*8+10h], eax
0x1800822e9  mov     dword ptr [rsi+rcx*8+20h], 0
0x1800822f1  mov     qword ptr [rsi+rcx*8+18h], 0
0x1800822fa  xor     r9d, r9d; unsigned int *
0x1800822fd  mov     r8, rbp; unsigned int *
0x180082300  mov     rdx, rsi; struct tagSPPHRASEALT *
0x180082303  mov     rcx, rdi; struct tagSPPHRASEALTREQUEST *
0x180082306  call    ?ConfirmOrFreeLastAlternate@@YA_NPEAUtagSPPHRASEALTREQUEST@@PEAUtagSPPHRASEALT@@PEAK2@Z; ConfirmOrFreeLastAlternate(tagSPPHRASEALTREQUEST *,tagSPPHRASEALT *,ulong *,ulong *)
0x18008230b  mov     ecx, 80004005h
0x180082310  test    al, al
0x180082312  cmovz   ebx, ecx
0x180082315  mov     rcx, [rsp+48h+pv]; pv
0x18008231a  call    cs:__imp_CoTaskMemFree
0x180082320  nop
0x180082321  lea     rcx, [rsp+48h+arg_8]
0x180082326  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x18008232b  mov     eax, ebx
0x18008232d  mov     rbx, [rsp+48h+arg_10]
0x180082332  add     rsp, 30h
0x180082336  pop     rdi
0x180082337  pop     rsi
0x180082338  pop     rbp
0x180082339  retn
```
