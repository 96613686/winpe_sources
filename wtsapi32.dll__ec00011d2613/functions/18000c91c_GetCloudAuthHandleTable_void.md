# GetCloudAuthHandleTable(void)

- ea: `0x18000c91c`
- end: `0x18000c993`
- name: `?GetCloudAuthHandleTable@@YAAEAVCloudAuthHandleTable@@XZ`
- size: `119`
- prototype: `struct CloudAuthHandleTable *(void)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c010`
- `0x18000c0c0`
- `0x18000c270`
- `0x18000c450`
- `0x18000ec70`

## callees

- `0x180006c08`
- `0x180006c78`
- `0x180006dc0`
- `0x18000bd8c`
- `0x18000c91c`

## pseudocode

```c
struct CloudAuthHandleTable *GetCloudAuthHandleTable(void)
{
  if ( dword_18001FB34 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18001FB34);
    if ( dword_18001FB34 == -1 )
    {
      utl::unordered_map<WTS_CLOUD_AUTH_HANDLE__ *,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>::unordered_map<WTS_CLOUD_AUTH_HANDLE__ *,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>();
      qword_18001FB70 = 81700;
      atexit(GetCloudAuthHandleTable_::_2_::_dynamic_atexit_destructor_for__s_cloudAuthHandleTable__);
      Init_thread_footer(&dword_18001FB34);
    }
  }
  return (struct CloudAuthHandleTable *)&qword_18001FB40;
}

```

## disassembly

```asm
0x18000c91c  sub     rsp, 28h
0x18000c920  mov     ecx, cs:_tls_index
0x18000c926  mov     rax, gs:58h
0x18000c92f  mov     edx, 4
0x18000c934  mov     rax, [rax+rcx*8]
0x18000c938  mov     eax, [rdx+rax]
0x18000c93b  cmp     cs:dword_18001FB34, eax
0x18000c941  jle     short loc_18000C987
0x18000c943  lea     rcx, dword_18001FB34
0x18000c94a  call    _Init_thread_header
0x18000c94f  cmp     cs:dword_18001FB34, 0FFFFFFFFh
0x18000c956  jnz     short loc_18000C987
0x18000c958  lea     rcx, qword_18001FB48
0x18000c95f  call    ??0?$unordered_map@PEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@utl@@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@5@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@5@@utl@@QEAA@XZ; utl::unordered_map<WTS_CLOUD_AUTH_HANDLE__ *,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>::unordered_map<WTS_CLOUD_AUTH_HANDLE__ *,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>(void)
0x18000c964  lea     rcx, _GetCloudAuthHandleTable____2____dynamic_atexit_destructor_for__s_cloudAuthHandleTable__; void (__cdecl *)()
0x18000c96b  mov     cs:qword_18001FB70, 13F24h
0x18000c976  call    atexit
0x18000c97b  lea     rcx, dword_18001FB34
0x18000c982  call    _Init_thread_footer
0x18000c987  lea     rax, qword_18001FB40
0x18000c98e  add     rsp, 28h
0x18000c992  retn
```
