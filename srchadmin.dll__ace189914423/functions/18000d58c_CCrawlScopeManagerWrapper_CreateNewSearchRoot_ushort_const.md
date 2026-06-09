# CCrawlScopeManagerWrapper::CreateNewSearchRoot(ushort const *)

- ea: `0x18000d58c`
- end: `0x18000d786`
- name: `?CreateNewSearchRoot@CCrawlScopeManagerWrapper@@QEAAJPEBG@Z`
- size: `506`
- prototype: `int(CCrawlScopeManagerWrapper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180002270`

## callees

- `0x1800038ac`
- `0x18000d530`
- `0x18000d58c`
- `0x18000de7c`
- `0x18001d568`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d67a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d67a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000d72c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000d72c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d6f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d6f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d6a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d6a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCrawlScopeManagerWrapper::CreateNewSearchRoot(CCrawlScopeManagerWrapper *this, WCHAR *a2)
{
  __int64 v4; // rcx
  HRESULT v5; // ebx
  unsigned __int16 *lpString2; // rdi
  unsigned __int16 *v8; // [rsp+40h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+30h] BYREF
  __int64 v10; // [rsp+90h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+48h] BYREF

  v4 = *(_QWORD *)this;
  v5 = v4 == 0 ? 0x80004003 : 0;
  v10 = 0;
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 48LL))(v4, &v10);
    if ( v5 >= 0 && !v10 )
      v5 = 1;
  }
  for ( ppv = 0; !v5; ATL::CComPtrBase<ISearchRoot>::Release(&ppv) )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, _QWORD))(*(_QWORD *)v10 + 24LL))(v10, 1, &ppv, 0);
    if ( v5 )
      break;
    pv = 0;
    v5 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)ppv + 48LL))(ppv, &pv);
    lpString2 = 0;
    v8 = 0;
    if ( v5 >= 0 )
    {
      v5 = PathDupNormalize((const unsigned __int16 *)pv, &v8);
      lpString2 = v8;
    }
    CoTaskMemFree(pv);
    if ( v5 >= 0 )
    {
      if ( CompareStringW(0x7Fu, 1u, a2, -1, lpString2, -1) == 2 )
      {
        ATL::CComPtrBase<ISearchRoot>::Release(&ppv);
        CoTaskMemFree(lpString2);
        if ( !v5 )
        {
          v5 = 1;
          goto LABEL_23;
        }
        break;
      }
      CoTaskMemFree(lpString2);
    }
  }
  if ( v5 == 1 )
  {
    if ( ppv )
      ATL::AtlComPtrAssign((struct IUnknown **)&ppv, (struct IUnknown *)a2);
    v5 = CoCreateInstance(&CLSID_CSearchRoot, 0, 0x17u, &GUID_04c18ccf_1f57_4cbd_88cc_3900f5195ce3, &ppv);
    if ( v5 >= 0 )
    {
      v5 = CoSetProxyBlanket((IUnknown *)ppv, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *))(*(_QWORD *)ppv + 40LL))(ppv, a2);
        if ( v5 >= 0 )
          v5 = (*(__int64 (__fastcall **)(_QWORD, LPVOID))(**(_QWORD **)this + 32LL))(*(_QWORD *)this, ppv);
      }
    }
  }
LABEL_23:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d58c  push    rbp
0x18000d58e  push    rbx
0x18000d58f  push    rsi
0x18000d590  push    rdi
0x18000d591  push    r14
0x18000d593  mov     rbp, rsp
0x18000d596  sub     rsp, 50h
0x18000d59a  mov     r14, rdx
0x18000d59d  mov     rsi, rcx
0x18000d5a0  mov     rcx, [rcx]
0x18000d5a3  mov     rax, rcx
0x18000d5a6  neg     rax
0x18000d5a9  sbb     ebx, ebx
0x18000d5ab  not     ebx
0x18000d5ad  and     ebx, 80004003h
0x18000d5b3  mov     [rbp+arg_10], 0
0x18000d5bb  test    rcx, rcx
0x18000d5be  jz      short loc_18000D5E2
0x18000d5c0  mov     rax, [rcx]
0x18000d5c3  lea     rdx, [rbp+arg_10]
0x18000d5c7  mov     rax, [rax+30h]
0x18000d5cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5d0  mov     ebx, eax
0x18000d5d2  test    eax, eax
0x18000d5d4  js      short loc_18000D5E2
0x18000d5d6  cmp     [rbp+arg_10], 0
0x18000d5db  jnz     short loc_18000D5E2
0x18000d5dd  mov     ebx, 1
0x18000d5e2  mov     [rbp+ppv], 0
0x18000d5ea  test    ebx, ebx
0x18000d5ec  jnz     loc_18000D6BC
0x18000d5f2  mov     rcx, [rbp+arg_10]
0x18000d5f6  mov     rax, [rcx]
0x18000d5f9  xor     r9d, r9d
0x18000d5fc  lea     r8, [rbp+ppv]
0x18000d600  lea     edx, [rbx+1]
0x18000d603  mov     rax, [rax+18h]
0x18000d607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d60c  mov     ebx, eax
0x18000d60e  test    eax, eax
0x18000d610  jnz     loc_18000D6BC
0x18000d616  mov     [rbp+pv], 0
0x18000d61e  mov     rcx, [rbp+ppv]
0x18000d622  mov     rax, [rcx]
0x18000d625  lea     rdx, [rbp+pv]
0x18000d629  mov     rax, [rax+30h]
0x18000d62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d632  mov     ebx, eax
0x18000d634  xor     edi, edi
0x18000d636  mov     [rbp+var_10], rdi
0x18000d63a  test    eax, eax
0x18000d63c  js      short loc_18000D651
0x18000d63e  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x18000d642  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18000d646  call    ?PathDupNormalize@@YAJPEBGPEAPEAG@Z; PathDupNormalize(ushort const *,ushort * *)
0x18000d64b  mov     ebx, eax
0x18000d64d  mov     rdi, [rbp+var_10]
0x18000d651  mov     rcx, [rbp+pv]; pv
0x18000d655  call    cs:__imp_CoTaskMemFree
0x18000d65b  test    ebx, ebx
0x18000d65d  js      short loc_18000D68E
0x18000d65f  mov     [rsp+50h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000d667  mov     [rsp+50h+lpString2], rdi; lpString2
0x18000d66c  or      r9d, 0FFFFFFFFh; cchCount1
0x18000d670  mov     r8, r14; lpString1
0x18000d673  lea     edx, [r9+2]; dwCmpFlags
0x18000d677  lea     ecx, [rdx+7Eh]; Locale
0x18000d67a  call    cs:__imp_CompareStringW
0x18000d680  cmp     eax, 2
0x18000d683  jz      short loc_18000D69C
0x18000d685  mov     rcx, rdi; pv
0x18000d688  call    cs:__imp_CoTaskMemFree
0x18000d68e  lea     rcx, [rbp+ppv]
0x18000d692  call    ?Release@?$CComPtrBase@UISearchRoot@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISearchRoot>::Release(void)
0x18000d697  jmp     loc_18000D5EA
0x18000d69c  lea     rcx, [rbp+ppv]
0x18000d6a0  call    ?Release@?$CComPtrBase@UISearchRoot@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISearchRoot>::Release(void)
0x18000d6a5  mov     rcx, rdi; pv
0x18000d6a8  call    cs:__imp_CoTaskMemFree
0x18000d6ae  test    ebx, ebx
0x18000d6b0  jnz     short loc_18000D6BC
0x18000d6b2  mov     ebx, 1
0x18000d6b7  jmp     loc_18000D766
0x18000d6bc  cmp     ebx, 1
0x18000d6bf  jnz     loc_18000D766
0x18000d6c5  cmp     [rbp+ppv], 0
0x18000d6ca  jz      short loc_18000D6D5
0x18000d6cc  lea     rcx, [rbp+ppv]; struct IUnknown **
0x18000d6d0  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000d6d5  lea     rax, [rbp+ppv]
0x18000d6d9  mov     [rsp+50h+lpString2], rax; ppv
0x18000d6de  lea     r9, _GUID_04c18ccf_1f57_4cbd_88cc_3900f5195ce3; riid
0x18000d6e5  xor     edx, edx; pUnkOuter
0x18000d6e7  lea     r8d, [rdx+17h]; dwClsContext
0x18000d6eb  lea     rcx, CLSID_CSearchRoot; rclsid
0x18000d6f2  call    cs:__imp_CoCreateInstance
0x18000d6f8  mov     ebx, eax
0x18000d6fa  test    eax, eax
0x18000d6fc  js      short loc_18000D766
0x18000d6fe  mov     [rsp+50h+dwCapabilities], 0; dwCapabilities
0x18000d706  mov     [rsp+50h+pAuthInfo], 0; pAuthInfo
0x18000d70f  mov     [rsp+50h+cchCount2], 3; dwImpLevel
0x18000d717  mov     dword ptr [rsp+50h+lpString2], 0; dwAuthnLevel
0x18000d71f  xor     r9d, r9d; pServerPrincName
0x18000d722  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000d725  mov     r8d, edx; dwAuthzSvc
0x18000d728  mov     rcx, [rbp+ppv]; pProxy
0x18000d72c  call    cs:__imp_CoSetProxyBlanket
0x18000d732  mov     ebx, eax
0x18000d734  test    eax, eax
0x18000d736  js      short loc_18000D766
0x18000d738  mov     rcx, [rbp+ppv]
0x18000d73c  mov     rax, [rcx]
0x18000d73f  mov     rdx, r14
0x18000d742  mov     rax, [rax+28h]
0x18000d746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d74b  mov     ebx, eax
0x18000d74d  test    eax, eax
0x18000d74f  js      short loc_18000D766
0x18000d751  mov     rcx, [rsi]
0x18000d754  mov     rax, [rcx]
0x18000d757  mov     rdx, [rbp+ppv]
0x18000d75b  mov     rax, [rax+20h]
0x18000d75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d764  mov     ebx, eax
0x18000d766  lea     rcx, [rbp+ppv]
0x18000d76a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d76f  nop
0x18000d770  lea     rcx, [rbp+arg_10]
0x18000d774  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d779  mov     eax, ebx
0x18000d77b  add     rsp, 50h
0x18000d77f  pop     r14
0x18000d781  pop     rdi
0x18000d782  pop     rsi
0x18000d783  pop     rbx
0x18000d784  pop     rbp
0x18000d785  retn
```
