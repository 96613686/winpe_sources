# utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_TryEmplace<WTS_CLOUD_AUTH_HANDLE__ * const &,ICloudAPHelper * &>(WTS_CLOUD_AUTH_HANDLE__ * const &,ICloudAPHelper * &)

- ea: `0x18000bba0`
- end: `0x18000bc62`
- name: `??$_TryEmplace@AEBQEAUWTS_CLOUD_AUTH_HANDLE__@@AEAPEAVICloudAPHelper@@@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@IEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@utl@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@2@@utl@@_N@1@AEBQEAUWTS_CLOUD_AUTH_HANDLE__@@AEAPEAVICloudAPHelper@@@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d4b0`

## callees

- `0x180006cfc`
- `0x18000bba0`
- `0x18000bd5c`
- `0x18000beb4`
- `0x18000e7a4`
- `0x18000e8e0`

## pseudocode

```c
__int64 __fastcall utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_TryEmplace<WTS_CLOUD_AUTH_HANDLE__ * const &,ICloudAPHelper * &>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4)
{
  _QWORD *v8; // rbx
  _QWORD *v9; // rax
  _QWORD v11[2]; // [rsp+20h] [rbp-38h] BYREF
  char v12; // [rsp+30h] [rbp-28h]
  _QWORD *v13; // [rsp+68h] [rbp+10h] BYREF

  *(_QWORD *)a2 = 0;
  *(_BYTE *)(a2 + 8) = 0;
  utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindInsertPos(
    a1,
    v11);
  if ( v12 )
  {
    *(_QWORD *)a2 = v11[0];
  }
  else
  {
    v13 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
    v8 = v13;
    if ( v13 )
    {
      v13[3] = *a3;
      wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>(
        v8 + 4,
        *a4);
      v13 = 0;
    }
    utl::_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>>::~_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>>(&v13);
    if ( v8 )
    {
      v9 = (_QWORD *)utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_InsertAt(
                       a1,
                       &v13,
                       v11,
                       v8);
      *(_BYTE *)(a2 + 8) = 1;
      *(_QWORD *)a2 = *v9;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18000bba0  mov     [rsp+arg_0], rbx
0x18000bba5  mov     [rsp+arg_10], rbp
0x18000bbaa  push    rsi
0x18000bbab  push    rdi
0x18000bbac  push    r14
0x18000bbae  sub     rsp, 40h
0x18000bbb2  mov     rdi, rdx
0x18000bbb5  mov     qword ptr [rdx], 0
0x18000bbbc  mov     byte ptr [rdx+8], 0
0x18000bbc0  mov     r14, r9
0x18000bbc3  lea     rdx, [rsp+58h+var_38]
0x18000bbc8  mov     rsi, r8
0x18000bbcb  mov     rbp, rcx
0x18000bbce  call    ?_FindInsertPos@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEAA?AU_InsertPosResult@12@AEBQEAUWTS_CLOUD_AUTH_HANDLE__@@@Z; utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindInsertPos(WTS_CLOUD_AUTH_HANDLE__ * const &)
0x18000bbd3  cmp     [rsp+58h+var_28], 0
0x18000bbd8  jz      short loc_18000BBE4
0x18000bbda  mov     rax, [rsp+58h+var_38]
0x18000bbdf  mov     [rdi], rax
0x18000bbe2  jmp     short loc_18000BC4C
0x18000bbe4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bbeb  mov     ecx, 28h ; '('; unsigned __int64
0x18000bbf0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bbf5  mov     [rsp+58h+arg_8], rax
0x18000bbfa  mov     rbx, rax
0x18000bbfd  test    rax, rax
0x18000bc00  jz      short loc_18000BC1E
0x18000bc02  mov     rax, [rsi]
0x18000bc05  lea     rcx, [rbx+20h]
0x18000bc09  mov     [rbx+18h], rax
0x18000bc0d  mov     rdx, [r14]
0x18000bc10  call    ??0?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVICloudAPHelper@@@Z; wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>(ICloudAPHelper *)
0x18000bc15  mov     [rsp+58h+arg_8], 0
0x18000bc1e  lea     rcx, [rsp+58h+arg_8]
0x18000bc23  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_HashNode@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>>::~_UninitializedAllocation<utl::allocator<utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>>(void)
0x18000bc28  test    rbx, rbx
0x18000bc2b  jz      short loc_18000BC4C
0x18000bc2d  mov     r9, rbx
0x18000bc30  lea     r8, [rsp+58h+var_38]
0x18000bc35  lea     rdx, [rsp+58h+arg_8]
0x18000bc3a  mov     rcx, rbp
0x18000bc3d  call    ?_InsertAt@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@utl@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@2@@2@AEBU_InsertPosResult@12@PEAU?$_HashNode@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@2@@Z; utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_InsertAt(utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_InsertPosResult const &,utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>> *)
0x18000bc42  mov     byte ptr [rdi+8], 1
0x18000bc46  mov     rcx, [rax]
0x18000bc49  mov     [rdi], rcx
0x18000bc4c  mov     rbx, [rsp+58h+arg_0]
0x18000bc51  mov     rax, rdi
0x18000bc54  mov     rbp, [rsp+58h+arg_10]
0x18000bc59  add     rsp, 40h
0x18000bc5d  pop     r14
0x18000bc5f  pop     rdi
0x18000bc60  pop     rsi
0x18000bc61  retn
```
