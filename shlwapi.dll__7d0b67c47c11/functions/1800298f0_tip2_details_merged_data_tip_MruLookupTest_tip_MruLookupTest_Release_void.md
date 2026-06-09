# tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>::Release(void)

- ea: `0x1800298f0`
- end: `0x180029928`
- name: `?Release@?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800291dc`
- `0x18002a52c`
- `0x18002b130`

## callees

- `0x180029244`
- `0x1800298f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029915`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>::~merged_data<_tip_MruLookupTest,_tip_MruLookupTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x1800298f0  mov     [rsp+arg_0], rbx
0x1800298f5  push    rdi
0x1800298f6  sub     rsp, 20h
0x1800298fa  mov     rdi, rcx
0x1800298fd  or      ebx, 0FFFFFFFFh
0x180029900  lock xadd [rcx+118h], ebx
0x180029908  sub     ebx, 1
0x18002990b  jnz     short loc_18002991B
0x18002990d  call    ??1?$merged_data@U_tip_MruLookupTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_MruLookupTest,_tip_MruLookupTest>::~merged_data<_tip_MruLookupTest,_tip_MruLookupTest>(void)
0x180029912  mov     rcx, rdi; pv
0x180029915  call    cs:__imp_CoTaskMemFree
0x18002991b  mov     eax, ebx
0x18002991d  mov     rbx, [rsp+28h+arg_0]
0x180029922  add     rsp, 20h
0x180029926  pop     rdi
0x180029927  retn
```
