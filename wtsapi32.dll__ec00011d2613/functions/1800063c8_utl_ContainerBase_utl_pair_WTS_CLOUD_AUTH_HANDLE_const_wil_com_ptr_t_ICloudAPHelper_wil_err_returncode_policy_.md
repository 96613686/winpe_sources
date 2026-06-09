# utl::_ContainerBase<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>::_DeleteNode<utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>(utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>> *)

- ea: `0x1800063c8`
- end: `0x1800063ee`
- name: `??$_DeleteNode@U?$_HashNode@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@utl@@@?$_ContainerBase@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@1@@Z`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000de44`
- `0x180015a10`

## callees

- `0x180006de0`
- `0x18000bed8`

## pseudocode

```c
void __fastcall utl::_ContainerBase<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>::_DeleteNode<utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>(
        __int64 a1,
        __int64 *a2)
{
  wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>::~com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>(a2 + 4);
  operator delete(a2);
}

```

## disassembly

```asm
0x1800063c8  push    rbx
0x1800063ca  sub     rsp, 20h
0x1800063ce  lea     rcx, [rdx+20h]
0x1800063d2  mov     rbx, rdx
0x1800063d5  call    ??1?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>::~com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>(void)
0x1800063da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800063e1  mov     rcx, rbx; Block
0x1800063e4  add     rsp, 20h
0x1800063e8  pop     rbx
0x1800063e9  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
