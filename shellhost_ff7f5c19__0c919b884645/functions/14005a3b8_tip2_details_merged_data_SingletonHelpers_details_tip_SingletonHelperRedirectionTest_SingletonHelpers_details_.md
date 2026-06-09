# tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::Release(void)

- ea: `0x14005a3b8`
- end: `0x14005a3f0`
- name: `?Release@?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140052d90`
- `0x14005db48`
- `0x14005eaa8`

## callees

- `0x140052e08`
- `0x14005a3b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005a3dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005a3dd`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 78);
  if ( !v2 )
  {
    tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::~merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x14005a3b8  mov     [rsp+arg_0], rbx
0x14005a3bd  push    rdi
0x14005a3be  sub     rsp, 20h
0x14005a3c2  mov     rdi, rcx
0x14005a3c5  or      ebx, 0FFFFFFFFh
0x14005a3c8  lock xadd [rcx+138h], ebx
0x14005a3d0  sub     ebx, 1
0x14005a3d3  jnz     short loc_14005A3E3
0x14005a3d5  call    ??1?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@QEAA@XZ; tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>::~merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>(void)
0x14005a3da  mov     rcx, rdi; pv
0x14005a3dd  call    cs:__imp_CoTaskMemFree
0x14005a3e3  mov     eax, ebx
0x14005a3e5  mov     rbx, [rsp+28h+arg_0]
0x14005a3ea  add     rsp, 20h
0x14005a3ee  pop     rdi
0x14005a3ef  retn
```
