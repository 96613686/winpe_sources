# tip2::details::merged_data<_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes,tip2::test_data_basic>::Release(void)

- ea: `0x18000da20`
- end: `0x18000da58`
- name: `?Release@?$merged_data@U_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009ff0`
- `0x18001262c`
- `0x1800126cc`
- `0x18004a150`
- `0x18004a1f0`
- `0x18004a290`
- `0x18004ec80`

## callees

- `0x18000a054`
- `0x18000da20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000da45`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_WOSC_TIP_CnsMergeWithOneSettings_attributes,tip2::test_data_basic>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 84);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>::~merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18000da20  mov     [rsp+arg_0], rbx
0x18000da25  push    rdi
0x18000da26  sub     rsp, 20h
0x18000da2a  mov     rdi, rcx
0x18000da2d  or      ebx, 0FFFFFFFFh
0x18000da30  lock xadd [rcx+150h], ebx
0x18000da38  sub     ebx, 1
0x18000da3b  jnz     short loc_18000DA4B
0x18000da3d  call    ??1?$merged_data@U_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>::~merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>(void)
0x18000da42  mov     rcx, rdi; pv
0x18000da45  call    cs:__imp_CoTaskMemFree
0x18000da4b  mov     eax, ebx
0x18000da4d  mov     rbx, [rsp+28h+arg_0]
0x18000da52  add     rsp, 20h
0x18000da56  pop     rdi
0x18000da57  retn
```
