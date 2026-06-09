# utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_AllocBuckets(unsigned __int64)

- ea: `0x18000e72c`
- end: `0x18000e754`
- name: `?_AllocBuckets@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEAAPEAU?$_HashBucket@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@2@_K@Z`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006604`
- `0x18000e7a4`

## callees

- `0x180006cfc`
- `0x18000e72c`

## pseudocode

```c
void *__fastcall utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_AllocBuckets(
        __int64 a1,
        unsigned __int64 a2)
{
  if ( a2 > 0xFFFFFFFFFFFFFFFLL )
    return 0;
  else
    return operator new(16 * a2, (const struct std::nothrow_t *)std::nothrow);
}

```

## disassembly

```asm
0x18000e72c  mov     rcx, 0FFFFFFFFFFFFFFFh
0x18000e736  mov     rax, rdx
0x18000e739  cmp     rdx, rcx
0x18000e73c  ja      short loc_18000E751
0x18000e73e  shl     rax, 4
0x18000e742  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e749  mov     rcx, rax; unsigned __int64
0x18000e74c  jmp     ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e751  xor     eax, eax
0x18000e753  retn
```
