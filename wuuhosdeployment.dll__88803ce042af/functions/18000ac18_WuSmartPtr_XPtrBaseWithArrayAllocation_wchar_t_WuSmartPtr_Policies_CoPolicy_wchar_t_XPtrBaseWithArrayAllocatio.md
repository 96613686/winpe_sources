# WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>::~XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>(void)

- ea: `0x18000ac18`
- end: `0x18000ac3c`
- name: `??1?$XPtrBaseWithArrayAllocation@_WU?$CoPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004a1cc`
- `0x18004a495`
- `0x18004a4a7`
- `0x18004a69f`
- `0x18004a6e7`
- `0x18004a994`
- `0x18004b0f7`

## callees

- `0x18000ac18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ac29`

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
0x18000ac18  push    rbx
0x18000ac1a  sub     rsp, 20h
0x18000ac1e  mov     rbx, rcx
0x18000ac21  mov     rcx, [rcx]; pv
0x18000ac24  test    rcx, rcx
0x18000ac27  jz      short loc_18000AC36
0x18000ac29  call    cs:__imp_CoTaskMemFree
0x18000ac2f  mov     qword ptr [rbx], 0
0x18000ac36  add     rsp, 20h
0x18000ac3a  pop     rbx
0x18000ac3b  retn
```
