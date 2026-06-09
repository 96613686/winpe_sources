# WuSmartPtr::XPtrBase<tagEnterprisePolicyValue_V1,WuSmartPtr::Policies::STPolicy<tagEnterprisePolicyValue_V1>>::~XPtrBase<tagEnterprisePolicyValue_V1,WuSmartPtr::Policies::STPolicy<tagEnterprisePolicyValue_V1>>(void)

- ea: `0x180014ba0`
- end: `0x180014bc8`
- name: `??1?$XPtrBase@UtagEnterprisePolicyValue_V1@@U?$STPolicy@UtagEnterprisePolicyValue_V1@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180038301`
- `0x180038457`
- `0x18003849f`
- `0x1800386bc`

## callees

- `0x180014ba0`
- `0x18003002c`

## pseudocode

```c
void __fastcall WuSmartPtr::XPtrBase<tagEnterprisePolicyValue_V1,WuSmartPtr::Policies::STPolicy<tagEnterprisePolicyValue_V1>>::~XPtrBase<tagEnterprisePolicyValue_V1,WuSmartPtr::Policies::STPolicy<tagEnterprisePolicyValue_V1>>(
        void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    operator delete(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180014ba0  push    rbx
0x180014ba2  sub     rsp, 20h
0x180014ba6  mov     rbx, rcx
0x180014ba9  mov     rcx, [rcx]; Block
0x180014bac  test    rcx, rcx
0x180014baf  jz      short loc_180014BC2
0x180014bb1  mov     edx, 30h ; '0'
0x180014bb6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014bbb  mov     qword ptr [rbx], 0
0x180014bc2  add     rsp, 20h
0x180014bc6  pop     rbx
0x180014bc7  retn
```
