# WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>::~XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>(void)

- ea: `0x14000bd78`
- end: `0x14000bd9c`
- name: `??1?$XPtrBaseWithArrayAllocation@_WU?$CoPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400217b3`
- `0x1400217d7`

## callees

- `0x14000bd78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bd89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bd89`

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
0x14000bd78  push    rbx
0x14000bd7a  sub     rsp, 20h
0x14000bd7e  mov     rbx, rcx
0x14000bd81  mov     rcx, [rcx]; pv
0x14000bd84  test    rcx, rcx
0x14000bd87  jz      short loc_14000BD96
0x14000bd89  call    cs:__imp_CoTaskMemFree
0x14000bd8f  mov     qword ptr [rbx], 0
0x14000bd96  add     rsp, 20h
0x14000bd9a  pop     rbx
0x14000bd9b  retn
```
