# utl::_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>>::~_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>>(void)

- ea: `0x18000beb4`
- end: `0x18000bed1`
- name: `??1?$_UninitializedAllocation@V?$allocator@U?$_HashNode@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@utl@@@utl@@@utl@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000bba0`

## callees

- `0x180006de0`
- `0x18000beb4`

## pseudocode

```c
void __fastcall utl::_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>>::~_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000beb4  sub     rsp, 28h
0x18000beb8  mov     rcx, [rcx]; Block
0x18000bebb  test    rcx, rcx
0x18000bebe  jz      short loc_18000BECC
0x18000bec0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000bec7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000becc  add     rsp, 28h
0x18000bed0  retn
```
