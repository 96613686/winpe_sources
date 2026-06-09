# WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>::~XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>(void)

- ea: `0x18000ab18`
- end: `0x18000ab3c`
- name: `??1?$XPtrBaseWithArrayAllocation@_WU?$CoPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016b78`

## callees

- `0x18000ab18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab29`

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
0x18000ab18  push    rbx
0x18000ab1a  sub     rsp, 20h
0x18000ab1e  mov     rbx, rcx
0x18000ab21  mov     rcx, [rcx]; pv
0x18000ab24  test    rcx, rcx
0x18000ab27  jz      short loc_18000AB36
0x18000ab29  call    cs:__imp_CoTaskMemFree
0x18000ab2f  mov     qword ptr [rbx], 0
0x18000ab36  add     rsp, 20h
0x18000ab3a  pop     rbx
0x18000ab3b  retn
```
