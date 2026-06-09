# std::default_delete<KEY_MAP_RECORD_CACHE>::operator()(KEY_MAP_RECORD_CACHE *)

- ea: `0x18000f374`
- end: `0x18000f39d`
- name: `??R?$default_delete@UKEY_MAP_RECORD_CACHE@@@std@@QEBAXPEAUKEY_MAP_RECORD_CACHE@@@Z`
- size: `41`
- prototype: `void __fastcall(__int64, NCRYPT_HANDLE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000dc5c`
- `0x18000f6a0`

## callees

- `0x180002360`
- `0x1800068dc`
- `0x18000f374`

## pseudocode

```c
void __fastcall std::default_delete<KEY_MAP_RECORD_CACHE>::operator()(__int64 a1, NCRYPT_HANDLE *a2)
{
  if ( a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(a2 + 11);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x18000f374  test    rdx, rdx
0x18000f377  jz      short locret_18000F39C
0x18000f379  push    rbx
0x18000f37a  sub     rsp, 20h
0x18000f37e  lea     rcx, [rdx+58h]
0x18000f382  mov     rbx, rdx
0x18000f385  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18000f38a  mov     edx, 60h ; '`'
0x18000f38f  mov     rcx, rbx; Block
0x18000f392  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f397  add     rsp, 20h
0x18000f39b  pop     rbx
0x18000f39c  retn
```
