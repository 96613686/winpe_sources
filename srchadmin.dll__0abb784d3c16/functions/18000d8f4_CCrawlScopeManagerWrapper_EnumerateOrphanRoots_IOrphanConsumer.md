# CCrawlScopeManagerWrapper::EnumerateOrphanRoots(IOrphanConsumer *)

- ea: `0x18000d8f4`
- end: `0x18000db0d`
- name: `?EnumerateOrphanRoots@CCrawlScopeManagerWrapper@@QEAAJPEAVIOrphanConsumer@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(CCrawlScopeManagerWrapper *__hidden this, struct IOrphanConsumer *)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180025fac`
- `0x180027abc`

## callees

- `0x1800038ac`
- `0x18000d8f4`
- `0x18000de7c`
- `0x18001d568`
- `0x180032010`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x18000d9cb`
- `SHLWAPI!StrStrW` at `0x18000d9cb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000da78`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000da78`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000da28`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000da28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d9d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d9d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da86`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCrawlScopeManagerWrapper::EnumerateOrphanRoots(
        CCrawlScopeManagerWrapper *this,
        struct IOrphanConsumer *a2)
{
  __int64 v3; // rcx
  signed int v4; // ebx
  __int64 v5; // r15
  WCHAR *v6; // r14
  WCHAR *v7; // rdi
  unsigned int j; // esi
  const WCHAR *v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rdx
  int cchCount2; // eax
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  LPCWCH lpString2[3]; // [rsp+38h] [rbp-18h]
  __int64 i; // [rsp+90h] [rbp+40h] BYREF
  PCWSTR pszFirst; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+58h] BYREF

  v3 = *(_QWORD *)this;
  v4 = v3 == 0 ? 0x8000FFFF : 0;
  LODWORD(v5) = 0;
  v6 = 0;
  v7 = 0;
  pszFirst = 0;
  v18 = 0;
  if ( v3 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 48LL))(v3, &v18);
    if ( v4 >= 0 && !v18 )
      v4 = 1;
  }
  for ( i = 0; !v4; ATL::CComPtrBase<ISearchRoot>::Release(&i) )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v18 + 24LL))(v18, 1, &i);
    if ( v4 )
      break;
    pv = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)i + 48LL))(i, &pv);
    if ( v4 >= 0 )
    {
      v4 = PathDupNormalize((const unsigned __int16 *)pv, (unsigned __int16 **)&pszFirst);
      v7 = (WCHAR *)pszFirst;
      if ( v4 >= 0 )
      {
        if ( StrStrW(pszFirst, L"*") )
        {
LABEL_10:
          CoTaskMemFree(v7);
          continue;
        }
        lpString2[0] = L"defaultroot:";
        lpString2[1] = L"winrt:";
        for ( j = 0; j < 2; ++j )
        {
          v9 = lpString2[j];
          v10 = -1;
          do
            ++v10;
          while ( v9[v10] );
          if ( CompareStringOrdinal(v7, v10, v9, -1, 1) == 2 )
            goto LABEL_10;
        }
      }
    }
    CoTaskMemFree(pv);
    if ( v4 >= 0 )
    {
      if ( !v6 )
        goto LABEL_25;
      v11 = -1;
      do
        ++v11;
      while ( v7[v11] );
      cchCount2 = v5;
      if ( (int)v5 >= (int)v11 )
        cchCount2 = v11;
      if ( CompareStringW(0x7Fu, 1u, v6, -1, v7, cchCount2) != 2 )
      {
        CoTaskMemFree(v6);
LABEL_25:
        v6 = v7;
        v7 = 0;
        pszFirst = 0;
        v5 = -1;
        do
          ++v5;
        while ( v6[v5] );
        v4 = (*(__int64 (__fastcall **)(struct IOrphanConsumer *, WCHAR *))(*(_QWORD *)a2 + 8LL))(a2, v6);
        continue;
      }
    }
  }
  if ( v4 >= 0 )
    v4 = (*(__int64 (__fastcall **)(struct IOrphanConsumer *))(*(_QWORD *)a2 + 16LL))(a2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&i);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d8f4  mov     [rsp-38h+arg_8], rbx
0x18000d8f9  push    rbp
0x18000d8fa  push    rsi
0x18000d8fb  push    rdi
0x18000d8fc  push    r12
0x18000d8fe  push    r13
0x18000d900  push    r14
0x18000d902  push    r15
0x18000d904  mov     rbp, rsp
0x18000d907  sub     rsp, 50h
0x18000d90b  mov     r12, rdx
0x18000d90e  mov     rcx, [rcx]
0x18000d911  mov     rax, rcx
0x18000d914  neg     rax
0x18000d917  sbb     ebx, ebx
0x18000d919  not     ebx
0x18000d91b  and     ebx, 8000FFFFh
0x18000d921  xor     r13d, r13d
0x18000d924  mov     r15d, r13d
0x18000d927  mov     r14d, r13d
0x18000d92a  mov     edi, r13d
0x18000d92d  mov     [rbp+pszFirst], r13
0x18000d931  mov     [rbp+arg_18], r13
0x18000d935  test    rcx, rcx
0x18000d938  jz      short loc_18000D95A
0x18000d93a  mov     rax, [rcx]
0x18000d93d  lea     rdx, [rbp+arg_18]
0x18000d941  mov     rax, [rax+30h]
0x18000d945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d94a  mov     ebx, eax
0x18000d94c  test    eax, eax
0x18000d94e  js      short loc_18000D95A
0x18000d950  cmp     [rbp+arg_18], r13
0x18000d954  jnz     short loc_18000D95A
0x18000d956  lea     ebx, [r13+1]
0x18000d95a  mov     [rbp+arg_0], r13
0x18000d95e  jmp     loc_18000DAC2
0x18000d963  mov     rcx, [rbp+arg_18]
0x18000d967  mov     rax, [rcx]
0x18000d96a  xor     r9d, r9d
0x18000d96d  lea     r8, [rbp+arg_0]
0x18000d971  lea     edx, [r9+1]
0x18000d975  mov     rax, [rax+18h]
0x18000d979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d97e  mov     ebx, eax
0x18000d980  test    eax, eax
0x18000d982  jnz     loc_18000DACA
0x18000d988  mov     [rbp+pv], r13
0x18000d98c  mov     rcx, [rbp+arg_0]
0x18000d990  mov     rax, [rcx]
0x18000d993  lea     rdx, [rbp+pv]
0x18000d997  mov     rax, [rax+30h]
0x18000d99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9a0  mov     ebx, eax
0x18000d9a2  test    eax, eax
0x18000d9a4  js      loc_18000DA37
0x18000d9aa  lea     rdx, [rbp+pszFirst]; unsigned __int16 **
0x18000d9ae  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18000d9b2  call    ?PathDupNormalize@@YAJPEBGPEAPEAG@Z; PathDupNormalize(ushort const *,ushort * *)
0x18000d9b7  mov     ebx, eax
0x18000d9b9  mov     rdi, [rbp+pszFirst]
0x18000d9bd  test    eax, eax
0x18000d9bf  js      short loc_18000DA37
0x18000d9c1  lea     rdx, pszSrch; "*"
0x18000d9c8  mov     rcx, rdi; pszFirst
0x18000d9cb  call    cs:__imp_StrStrW
0x18000d9d1  test    rax, rax
0x18000d9d4  jz      short loc_18000D9E4
0x18000d9d6  mov     rcx, rdi; pv
0x18000d9d9  call    cs:__imp_CoTaskMemFree
0x18000d9df  jmp     loc_18000DAB9
0x18000d9e4  lea     rax, aDefaultroot; "defaultroot:"
0x18000d9eb  mov     [rbp+lpString2], rax
0x18000d9ef  lea     rax, String2; "winrt:"
0x18000d9f6  mov     [rbp+var_10], rax
0x18000d9fa  mov     esi, r13d
0x18000d9fd  cmp     esi, 2
0x18000da00  jnb     short loc_18000DA37
0x18000da02  mov     eax, esi
0x18000da04  mov     r8, [rbp+rax*8+lpString2]; lpString2
0x18000da09  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000da0d  mov     rdx, rax
0x18000da10  inc     rdx; cchCount1
0x18000da13  cmp     [r8+rdx*2], r13w
0x18000da18  jnz     short loc_18000DA10
0x18000da1a  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x18000da22  mov     r9d, eax; cchCount2
0x18000da25  mov     rcx, rdi; lpString1
0x18000da28  call    cs:__imp_CompareStringOrdinal
0x18000da2e  cmp     eax, 2
0x18000da31  jz      short loc_18000D9D6
0x18000da33  inc     esi
0x18000da35  jmp     short loc_18000D9FD
0x18000da37  mov     rcx, [rbp+pv]; pv
0x18000da3b  call    cs:__imp_CoTaskMemFree
0x18000da41  test    ebx, ebx
0x18000da43  js      short loc_18000DAB9
0x18000da45  test    r14, r14
0x18000da48  jz      short loc_18000DA8C
0x18000da4a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000da4e  inc     rdx
0x18000da51  cmp     [rdi+rdx*2], r13w
0x18000da56  jnz     short loc_18000DA4E
0x18000da58  mov     eax, r15d
0x18000da5b  cmp     r15d, edx
0x18000da5e  cmovge  eax, edx
0x18000da61  mov     [rsp+50h+cchCount2], eax; cchCount2
0x18000da65  mov     qword ptr [rsp+50h+bIgnoreCase], rdi; lpString2
0x18000da6a  or      r9d, 0FFFFFFFFh; cchCount1
0x18000da6e  mov     r8, r14; lpString1
0x18000da71  lea     edx, [r9+2]; dwCmpFlags
0x18000da75  lea     ecx, [rdx+7Eh]; Locale
0x18000da78  call    cs:__imp_CompareStringW
0x18000da7e  cmp     eax, 2
0x18000da81  jz      short loc_18000DAB9
0x18000da83  mov     rcx, r14; pv
0x18000da86  call    cs:__imp_CoTaskMemFree
0x18000da8c  mov     r14, rdi
0x18000da8f  mov     rdi, r13
0x18000da92  mov     [rbp+pszFirst], r13
0x18000da96  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000da9a  inc     r15
0x18000da9d  cmp     [r14+r15*2], r13w
0x18000daa2  jnz     short loc_18000DA9A
0x18000daa4  mov     rax, [r12]
0x18000daa8  mov     rdx, r14
0x18000daab  mov     rcx, r12
0x18000daae  mov     rax, [rax+8]
0x18000dab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dab7  mov     ebx, eax
0x18000dab9  lea     rcx, [rbp+arg_0]
0x18000dabd  call    ?Release@?$CComPtrBase@UISearchRoot@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISearchRoot>::Release(void)
0x18000dac2  test    ebx, ebx
0x18000dac4  jz      loc_18000D963
0x18000daca  test    ebx, ebx
0x18000dacc  js      short loc_18000DAE0
0x18000dace  mov     rax, [r12]
0x18000dad2  mov     rcx, r12
0x18000dad5  mov     rax, [rax+10h]
0x18000dad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dade  mov     ebx, eax
0x18000dae0  lea     rcx, [rbp+arg_0]
0x18000dae4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000dae9  nop
0x18000daea  lea     rcx, [rbp+arg_18]
0x18000daee  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000daf3  mov     eax, ebx
0x18000daf5  mov     rbx, [rsp+50h+arg_8]
0x18000dafd  add     rsp, 50h
0x18000db01  pop     r15
0x18000db03  pop     r14
0x18000db05  pop     r13
0x18000db07  pop     r12
0x18000db09  pop     rdi
0x18000db0a  pop     rsi
0x18000db0b  pop     rbp
0x18000db0c  retn
```
