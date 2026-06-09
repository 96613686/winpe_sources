# utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_InitBuckets(void)

- ea: `0x1800066f0`
- end: `0x18000672e`
- name: `?_InitBuckets@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEAAXXZ`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006604`
- `0x18000e7a4`

## callees

- `0x1800066f0`

## pseudocode

```c
__int64 __fastcall utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_InitBuckets(
        __int64 a1)
{
  __int64 v2; // r8
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 result; // rax

  v2 = 0;
  v3 = 8LL << *(_BYTE *)(a1 + 32);
  if ( v3 )
  {
    do
    {
      v4 = 2 * v2++;
      *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8 * v4) = 0;
      result = *(_QWORD *)(a1 + 16);
      *(_QWORD *)(result + 8 * v4 + 8) = 0;
    }
    while ( v2 != v3 );
  }
  return result;
}

```

## disassembly

```asm
0x1800066f0  mov     r9, rcx
0x1800066f3  mov     edx, 8
0x1800066f8  mov     cl, [rcx+20h]
0x1800066fb  xor     r8d, r8d
0x1800066fe  shl     rdx, cl
0x180006701  test    rdx, rdx
0x180006704  jz      short locret_18000672D
0x180006706  mov     rax, [r9+10h]
0x18000670a  mov     rcx, r8
0x18000670d  add     rcx, rcx
0x180006710  inc     r8
0x180006713  mov     qword ptr [rax+rcx*8], 0
0x18000671b  mov     rax, [r9+10h]
0x18000671f  mov     qword ptr [rax+rcx*8+8], 0
0x180006728  cmp     r8, rdx
0x18000672b  jnz     short loc_180006706
0x18000672d  retn
```
