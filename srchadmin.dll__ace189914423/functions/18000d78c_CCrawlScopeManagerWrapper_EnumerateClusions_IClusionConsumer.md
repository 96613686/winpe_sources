# CCrawlScopeManagerWrapper::EnumerateClusions(IClusionConsumer *)

- ea: `0x18000d78c`
- end: `0x18000d8ec`
- name: `?EnumerateClusions@CCrawlScopeManagerWrapper@@QEAAJPEAVIClusionConsumer@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(CCrawlScopeManagerWrapper *__hidden this, struct IClusionConsumer *)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180025fac`
- `0x1800268f8`
- `0x180027abc`

## callees

- `0x1800038ac`
- `0x18000d78c`
- `0x18000de7c`
- `0x18001d568`
- `0x180032010`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x18000d876`
- `SHLWAPI!StrStrW` at `0x18000d876`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d862`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d89e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d862`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d89e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCrawlScopeManagerWrapper::EnumerateClusions(
        CCrawlScopeManagerWrapper *this,
        struct IClusionConsumer *a2)
{
  __int64 v3; // rcx
  signed int v4; // ebx
  unsigned __int16 *v5; // rdi
  __int64 v7; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v8; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v9; // [rsp+60h] [rbp+20h] BYREF
  __int64 i; // [rsp+70h] [rbp+30h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF

  v3 = *(_QWORD *)this;
  v4 = v3 == 0 ? 0x80004003 : 0;
  v7 = 0;
  if ( v3 )
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 80LL))(v3, &v7);
  for ( i = 0; !v4; ATL::CComPtrBase<ISearchRoot>::Release(&i) )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v7 + 24LL))(v7, 1, &i);
    if ( v4 )
      break;
    v9 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)i + 32LL))(i, &v9);
    if ( v4 < 0 )
      continue;
    pv = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)i + 24LL))(i, &pv);
    v5 = 0;
    v8 = 0;
    if ( v4 >= 0 )
    {
      v4 = PathDupNormalize((const unsigned __int16 *)pv, &v8);
      v5 = v8;
    }
    CoTaskMemFree(pv);
    if ( v4 < 0 )
      goto LABEL_11;
    if ( !StrStrW(v5, L"*") )
    {
      (**(void (__fastcall ***)(struct IClusionConsumer *, unsigned __int16 *, _QWORD))a2)(a2, v5, v9);
LABEL_11:
      if ( !v5 )
        continue;
    }
    CoTaskMemFree(v5);
  }
  if ( v4 >= 0 )
    v4 = (*(__int64 (__fastcall **)(struct IClusionConsumer *))(*(_QWORD *)a2 + 8LL))(a2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&i);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d78c  mov     [rsp-18h+arg_8], rbx
0x18000d791  push    rbp
0x18000d792  push    rsi
0x18000d793  push    rdi
0x18000d794  mov     rbp, rsp
0x18000d797  sub     rsp, 40h
0x18000d79b  mov     rsi, rdx
0x18000d79e  mov     rcx, [rcx]
0x18000d7a1  mov     rax, rcx
0x18000d7a4  neg     rax
0x18000d7a7  sbb     ebx, ebx
0x18000d7a9  not     ebx
0x18000d7ab  and     ebx, 80004003h
0x18000d7b1  mov     [rbp+var_10], 0
0x18000d7b9  test    rcx, rcx
0x18000d7bc  jz      short loc_18000D7D0
0x18000d7be  mov     rax, [rcx]
0x18000d7c1  lea     rdx, [rbp+var_10]
0x18000d7c5  mov     rax, [rax+50h]
0x18000d7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7ce  mov     ebx, eax
0x18000d7d0  mov     [rbp+arg_10], 0
0x18000d7d8  jmp     loc_18000D8AD
0x18000d7dd  mov     rcx, [rbp+var_10]
0x18000d7e1  mov     rax, [rcx]
0x18000d7e4  xor     r9d, r9d
0x18000d7e7  lea     r8, [rbp+arg_10]
0x18000d7eb  lea     edx, [r9+1]
0x18000d7ef  mov     rax, [rax+18h]
0x18000d7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7f8  mov     ebx, eax
0x18000d7fa  test    eax, eax
0x18000d7fc  jnz     loc_18000D8B5
0x18000d802  mov     [rbp+arg_0], eax
0x18000d805  mov     rcx, [rbp+arg_10]
0x18000d809  mov     rax, [rcx]
0x18000d80c  lea     rdx, [rbp+arg_0]
0x18000d810  mov     rax, [rax+20h]
0x18000d814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d819  mov     ebx, eax
0x18000d81b  test    eax, eax
0x18000d81d  js      loc_18000D8A4
0x18000d823  mov     [rbp+pv], 0
0x18000d82b  mov     rcx, [rbp+arg_10]
0x18000d82f  mov     rax, [rcx]
0x18000d832  lea     rdx, [rbp+pv]
0x18000d836  mov     rax, [rax+18h]
0x18000d83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d83f  mov     ebx, eax
0x18000d841  xor     edi, edi
0x18000d843  mov     [rbp+var_8], rdi
0x18000d847  test    eax, eax
0x18000d849  js      short loc_18000D85E
0x18000d84b  lea     rdx, [rbp+var_8]; unsigned __int16 **
0x18000d84f  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18000d853  call    ?PathDupNormalize@@YAJPEBGPEAPEAG@Z; PathDupNormalize(ushort const *,ushort * *)
0x18000d858  mov     ebx, eax
0x18000d85a  mov     rdi, [rbp+var_8]
0x18000d85e  mov     rcx, [rbp+pv]; pv
0x18000d862  call    cs:__imp_CoTaskMemFree
0x18000d868  test    ebx, ebx
0x18000d86a  js      short loc_18000D896
0x18000d86c  lea     rdx, pszSrch; "*"
0x18000d873  mov     rcx, rdi; pszFirst
0x18000d876  call    cs:__imp_StrStrW
0x18000d87c  test    rax, rax
0x18000d87f  jnz     short loc_18000D89B
0x18000d881  mov     rax, [rsi]
0x18000d884  mov     r8d, [rbp+arg_0]
0x18000d888  mov     rdx, rdi
0x18000d88b  mov     rcx, rsi
0x18000d88e  mov     rax, [rax]
0x18000d891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d896  test    rdi, rdi
0x18000d899  jz      short loc_18000D8A4
0x18000d89b  mov     rcx, rdi; pv
0x18000d89e  call    cs:__imp_CoTaskMemFree
0x18000d8a4  lea     rcx, [rbp+arg_10]
0x18000d8a8  call    ?Release@?$CComPtrBase@UISearchRoot@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISearchRoot>::Release(void)
0x18000d8ad  test    ebx, ebx
0x18000d8af  jz      loc_18000D7DD
0x18000d8b5  test    ebx, ebx
0x18000d8b7  js      short loc_18000D8CA
0x18000d8b9  mov     rax, [rsi]
0x18000d8bc  mov     rcx, rsi
0x18000d8bf  mov     rax, [rax+8]
0x18000d8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8c8  mov     ebx, eax
0x18000d8ca  lea     rcx, [rbp+arg_10]
0x18000d8ce  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d8d3  nop
0x18000d8d4  lea     rcx, [rbp+var_10]
0x18000d8d8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d8dd  mov     eax, ebx
0x18000d8df  mov     rbx, [rsp+40h+arg_8]
0x18000d8e4  add     rsp, 40h
0x18000d8e8  pop     rdi
0x18000d8e9  pop     rsi
0x18000d8ea  pop     rbp
0x18000d8eb  retn
```
