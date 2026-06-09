# ATL::CComPtr<ISearchCrawlScopeManager>::~CComPtr<ISearchCrawlScopeManager>(void)

- ea: `0x180004ad4`
- end: `0x180004af2`
- name: `??1?$CComPtr@UISearchCrawlScopeManager@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dc3e`
- `0x18000dc50`
- `0x18000dc62`
- `0x18000dc74`
- `0x18000dc86`

## callees

- `0x180004ad4`
- `0x18000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<ISearchCrawlScopeManager>::~CComPtr<ISearchCrawlScopeManager>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180004ad4  sub     rsp, 28h
0x180004ad8  mov     rcx, [rcx]
0x180004adb  test    rcx, rcx
0x180004ade  jz      short loc_180004AED
0x180004ae0  mov     rax, [rcx]
0x180004ae3  mov     rax, [rax+10h]
0x180004ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aec  nop
0x180004aed  add     rsp, 28h
0x180004af1  retn
```
