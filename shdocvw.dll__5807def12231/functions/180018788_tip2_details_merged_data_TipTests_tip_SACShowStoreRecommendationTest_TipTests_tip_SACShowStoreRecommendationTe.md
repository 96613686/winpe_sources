# tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::Release(void)

- ea: `0x180018788`
- end: `0x1800187c0`
- name: `?Release@?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014bf4`
- `0x18001b048`
- `0x18001c2b8`

## callees

- `0x180014c74`
- `0x180018788`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800187ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800187ad`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::~merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180018788  mov     [rsp+arg_0], rbx
0x18001878d  push    rdi
0x18001878e  sub     rsp, 20h
0x180018792  mov     rdi, rcx
0x180018795  or      ebx, 0FFFFFFFFh
0x180018798  lock xadd [rcx+118h], ebx
0x1800187a0  sub     ebx, 1
0x1800187a3  jnz     short loc_1800187B3
0x1800187a5  call    ??1?$merged_data@U_tip_SACShowStoreRecommendationTest@TipTests@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>::~merged_data<TipTests::_tip_SACShowStoreRecommendationTest,TipTests::_tip_SACShowStoreRecommendationTest>(void)
0x1800187aa  mov     rcx, rdi; pv
0x1800187ad  call    cs:__imp_CoTaskMemFree
0x1800187b3  mov     eax, ebx
0x1800187b5  mov     rbx, [rsp+28h+arg_0]
0x1800187ba  add     rsp, 20h
0x1800187be  pop     rdi
0x1800187bf  retn
```
