# WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>::~XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>(void)

- ea: `0x18000cb44`
- end: `0x18000cb68`
- name: `??1?$XPtrBaseWithArrayAllocation@_WU?$CoPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038c3b`

## callees

- `0x18000cb44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb55`

## pseudocode

```c
void __fastcall WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>::~XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>(
        void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18000cb44  push    rbx
0x18000cb46  sub     rsp, 20h
0x18000cb4a  mov     rbx, rcx
0x18000cb4d  mov     rcx, [rcx]; pv
0x18000cb50  test    rcx, rcx
0x18000cb53  jz      short loc_18000CB62
0x18000cb55  call    cs:__imp_CoTaskMemFree
0x18000cb5b  mov     qword ptr [rbx], 0
0x18000cb62  add     rsp, 20h
0x18000cb66  pop     rbx
0x18000cb67  retn
```
