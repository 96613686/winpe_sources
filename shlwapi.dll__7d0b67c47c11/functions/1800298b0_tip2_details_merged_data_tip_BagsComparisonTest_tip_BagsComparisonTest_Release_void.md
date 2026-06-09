# tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::Release(void)

- ea: `0x1800298b0`
- end: `0x1800298e8`
- name: `?Release@?$merged_data@U_tip_BagsComparisonTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800088e0`
- `0x1800291c0`
- `0x18002b108`

## callees

- `0x180029214`
- `0x1800298b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800298d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800298d5`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 72);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::~merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x1800298b0  mov     [rsp+arg_0], rbx
0x1800298b5  push    rdi
0x1800298b6  sub     rsp, 20h
0x1800298ba  mov     rdi, rcx
0x1800298bd  or      ebx, 0FFFFFFFFh
0x1800298c0  lock xadd [rcx+120h], ebx
0x1800298c8  sub     ebx, 1
0x1800298cb  jnz     short loc_1800298DB
0x1800298cd  call    ??1?$merged_data@U_tip_BagsComparisonTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>::~merged_data<_tip_BagsComparisonTest,_tip_BagsComparisonTest>(void)
0x1800298d2  mov     rcx, rdi; pv
0x1800298d5  call    cs:__imp_CoTaskMemFree
0x1800298db  mov     eax, ebx
0x1800298dd  mov     rbx, [rsp+28h+arg_0]
0x1800298e2  add     rsp, 20h
0x1800298e6  pop     rdi
0x1800298e7  retn
```
