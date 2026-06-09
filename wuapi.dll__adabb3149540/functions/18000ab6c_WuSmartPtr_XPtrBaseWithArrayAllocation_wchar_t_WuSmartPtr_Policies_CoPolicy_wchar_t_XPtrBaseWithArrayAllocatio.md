# WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>::~XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>(void)

- ea: `0x18000ab6c`
- end: `0x18000ab90`
- name: `??1?$XPtrBaseWithArrayAllocation@_WU?$CoPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016bc8`

## callees

- `0x18000ab6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab7d`

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
0x18000ab6c  push    rbx
0x18000ab6e  sub     rsp, 20h
0x18000ab72  mov     rbx, rcx
0x18000ab75  mov     rcx, [rcx]; pv
0x18000ab78  test    rcx, rcx
0x18000ab7b  jz      short loc_18000AB8A
0x18000ab7d  call    cs:__imp_CoTaskMemFree
0x18000ab83  mov     qword ptr [rbx], 0
0x18000ab8a  add     rsp, 20h
0x18000ab8e  pop     rbx
0x18000ab8f  retn
```
