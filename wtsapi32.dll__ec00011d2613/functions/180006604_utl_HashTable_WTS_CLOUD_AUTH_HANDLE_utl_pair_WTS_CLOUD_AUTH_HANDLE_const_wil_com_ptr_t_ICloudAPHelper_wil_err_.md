# utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_Rehash(uchar)

- ea: `0x180006604`
- end: `0x1800066ea`
- name: `?_Rehash@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEAA_NE@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000e8e0`

## callees

- `0x180006604`
- `0x1800066f0`
- `0x180006de0`
- `0x18000e72c`

## pseudocode

```c
char __fastcall utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_Rehash(
        __int64 a1,
        unsigned __int8 a2)
{
  char v2; // bp
  __int64 v4; // rbx
  __int64 v5; // r14
  void *v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // r9
  _QWORD *v10; // rcx
  _QWORD *v11; // r11
  _QWORD *v12; // r14
  _QWORD *v13; // rsi
  __int64 v14; // r8
  _QWORD *v15; // r10
  _QWORD *v16; // r10
  _QWORD *v17; // rdx

  v2 = 0;
  v4 = a1;
  if ( a2 <= 0x38u )
  {
    LOBYTE(a1) = a2;
    v5 = utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_AllocBuckets(
           a1,
           8LL << a2);
    if ( v5 )
    {
      v6 = *(void **)(v4 + 16);
      v2 = 1;
      if ( v6 )
        operator delete(v6);
      *(_QWORD *)(v4 + 16) = v5;
      *(_BYTE *)(v4 + 32) = a2;
      utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_InitBuckets(v4);
      v7 = *(_QWORD **)v4;
      v8 = (8LL << *(_BYTE *)(v4 + 32)) - 1;
      while ( v7 != (_QWORD *)v4 )
      {
        v9 = *(_QWORD *)(v4 + 16);
        v10 = v7;
        v11 = (_QWORD *)*v7;
        v12 = v7;
        v13 = v7;
        v7 = (_QWORD *)*v7;
        v14 = 2 * (v8 & v10[2]);
        v15 = *(_QWORD **)(v9 + 16 * (v8 & v10[2]) + 8);
        if ( v15 )
        {
          v16 = (_QWORD *)*v15;
          if ( v16 != v10 )
          {
            v17 = (_QWORD *)v11[1];
            *(_QWORD *)v13[1] = v11;
            v11[1] = v13[1];
            v13[1] = v16[1];
            *(_QWORD *)v16[1] = v13;
            *v17 = v16;
            v16[1] = v17;
          }
        }
        else
        {
          *(_QWORD *)(v9 + 16 * (v8 & v10[2])) = v10;
        }
        *(_QWORD *)(v9 + 8 * v14 + 8) = v12;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180006604  push    rbx
0x180006606  push    rbp
0x180006607  push    rsi
0x180006608  push    rdi
0x180006609  push    r14
0x18000660b  sub     rsp, 20h
0x18000660f  xor     bpl, bpl
0x180006612  mov     sil, dl
0x180006615  mov     rbx, rcx
0x180006618  cmp     dl, 38h ; '8'
0x18000661b  ja      loc_1800066DC
0x180006621  mov     cl, dl
0x180006623  mov     edi, 8
0x180006628  mov     edx, edi
0x18000662a  shl     rdx, cl
0x18000662d  call    ?_AllocBuckets@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEAAPEAU?$_HashBucket@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@2@_K@Z; utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_AllocBuckets(unsigned __int64)
0x180006632  mov     r14, rax
0x180006635  test    rax, rax
0x180006638  jz      loc_1800066DC
0x18000663e  mov     rcx, [rbx+10h]; Block
0x180006642  lea     ebp, [rdi-7]
0x180006645  test    rcx, rcx
0x180006648  jz      short loc_180006656
0x18000664a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180006651  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006656  mov     rcx, rbx
0x180006659  mov     [rbx+10h], r14
0x18000665d  mov     [rbx+20h], sil
0x180006661  call    ?_InitBuckets@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_InitBuckets(void)
0x180006666  mov     cl, [rbx+20h]
0x180006669  mov     rax, [rbx]
0x18000666c  shl     rdi, cl
0x18000666f  sub     rdi, rbp
0x180006672  cmp     rax, rbx
0x180006675  jz      short loc_1800066DC
0x180006677  mov     r9, [rbx+10h]
0x18000667b  mov     rcx, rax
0x18000667e  mov     r11, [rax]
0x180006681  mov     r14, rax
0x180006684  mov     rsi, rax
0x180006687  mov     rax, r11
0x18000668a  mov     r8, [rcx+10h]
0x18000668e  and     r8, rdi
0x180006691  add     r8, r8
0x180006694  mov     r10, [r9+r8*8+8]
0x180006699  test    r10, r10
0x18000669c  jz      short loc_1800066D1
0x18000669e  mov     r10, [r10]
0x1800066a1  cmp     r10, rcx
0x1800066a4  jz      short loc_1800066D5
0x1800066a6  mov     rcx, [rsi+8]
0x1800066aa  mov     rdx, [r11+8]
0x1800066ae  mov     [rcx], r11
0x1800066b1  mov     rcx, [rsi+8]
0x1800066b5  mov     [r11+8], rcx
0x1800066b9  mov     rcx, [r10+8]
0x1800066bd  mov     [rsi+8], rcx
0x1800066c1  mov     rcx, [r10+8]
0x1800066c5  mov     [rcx], rsi
0x1800066c8  mov     [rdx], r10
0x1800066cb  mov     [r10+8], rdx
0x1800066cf  jmp     short loc_1800066D5
0x1800066d1  mov     [r9+r8*8], rcx
0x1800066d5  mov     [r9+r8*8+8], r14
0x1800066da  jmp     short loc_180006672
0x1800066dc  mov     al, bpl
0x1800066df  add     rsp, 20h
0x1800066e3  pop     r14
0x1800066e5  pop     rdi
0x1800066e6  pop     rsi
0x1800066e7  pop     rbp
0x1800066e8  pop     rbx
0x1800066e9  retn
```
