# tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>::Release(void)

- ea: `0x180029930`
- end: `0x180029968`
- name: `?Release@?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800291f8`
- `0x18002a58c`
- `0x18002b158`

## callees

- `0x180029274`
- `0x180029930`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029955`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029955`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>::~merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180029930  mov     [rsp+arg_0], rbx
0x180029935  push    rdi
0x180029936  sub     rsp, 20h
0x18002993a  mov     rdi, rcx
0x18002993d  or      ebx, 0FFFFFFFFh
0x180029940  lock xadd [rcx+118h], ebx
0x180029948  sub     ebx, 1
0x18002994b  jnz     short loc_18002995B
0x18002994d  call    ??1?$merged_data@U_tip_PidlNormalizationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>::~merged_data<_tip_PidlNormalizationTest,_tip_PidlNormalizationTest>(void)
0x180029952  mov     rcx, rdi; pv
0x180029955  call    cs:__imp_CoTaskMemFree
0x18002995b  mov     eax, ebx
0x18002995d  mov     rbx, [rsp+28h+arg_0]
0x180029962  add     rsp, 20h
0x180029966  pop     rdi
0x180029967  retn
```
