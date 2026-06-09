# utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_InsertAt(utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_InsertPosResult const &,utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>> *)

- ea: `0x18000e8e0`
- end: `0x18000e97c`
- name: `?_InsertAt@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@utl@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@2@@2@AEBU_InsertPosResult@12@PEAU?$_HashNode@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@2@@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bba0`

## callees

- `0x180006604`
- `0x18000e8e0`

## pseudocode

```c
__int64 **__fastcall utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_InsertAt(
        __int64 a1,
        __int64 **a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 v4; // rax
  char v6; // cl
  __int64 v8; // rdx
  __int64 v9; // r10
  __int64 **v10; // rcx
  char v11; // cl

  v4 = *a3;
  v6 = *(_BYTE *)(a1 + 32);
  v8 = *(_QWORD *)(a1 + 16);
  v9 = 2 * (a3[1] & ((8LL << v6) - 1));
  if ( !*a3 )
  {
    *(_QWORD *)(v8 + 16 * (a3[1] & ((8LL << v6) - 1))) = a4;
    v4 = a1;
LABEL_6:
    *(_QWORD *)(v8 + 8 * v9 + 8) = a4;
    goto LABEL_7;
  }
  if ( *(_QWORD *)(v8 + 16 * (a3[1] & ((8LL << v6) - 1))) == v4 )
  {
    *(_QWORD *)(v8 + 16 * (a3[1] & ((8LL << v6) - 1))) = a4;
    goto LABEL_7;
  }
  if ( **(_QWORD **)(v8 + 16 * (a3[1] & ((8LL << v6) - 1)) + 8) == v4 )
    goto LABEL_6;
LABEL_7:
  a4[2] = a3[1];
  v10 = *(__int64 ***)(v4 + 8);
  a4[1] = (__int64)v10;
  *a4 = v4;
  *a2 = a4;
  *v10 = a4;
  *(_QWORD *)(v4 + 8) = a4;
  ++*(_QWORD *)(a1 + 24);
  v11 = *(_BYTE *)(a1 + 32);
  if ( (unsigned __int64)*(unsigned __int8 *)(a1 + 33) < *(_QWORD *)(a1 + 24) >> v11 )
    utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_Rehash(
      a1,
      v11 + 1);
  return a2;
}

```

## disassembly

```asm
0x18000e8e0  push    rbx
0x18000e8e2  sub     rsp, 20h
0x18000e8e6  mov     rax, [r8]
0x18000e8e9  mov     r11, rcx
0x18000e8ec  mov     cl, [rcx+20h]
0x18000e8ef  mov     r10d, 8
0x18000e8f5  shl     r10, cl
0x18000e8f8  mov     rbx, rdx
0x18000e8fb  dec     r10
0x18000e8fe  and     r10, [r8+8]
0x18000e902  mov     rdx, [r11+10h]
0x18000e906  add     r10, r10
0x18000e909  test    rax, rax
0x18000e90c  jnz     short loc_18000E917
0x18000e90e  mov     [rdx+r10*8], r9
0x18000e912  mov     rax, r11
0x18000e915  jmp     short loc_18000E92D
0x18000e917  cmp     [rdx+r10*8], rax
0x18000e91b  jnz     short loc_18000E923
0x18000e91d  mov     [rdx+r10*8], r9
0x18000e921  jmp     short loc_18000E932
0x18000e923  mov     rcx, [rdx+r10*8+8]
0x18000e928  cmp     [rcx], rax
0x18000e92b  jnz     short loc_18000E932
0x18000e92d  mov     [rdx+r10*8+8], r9
0x18000e932  mov     rcx, [r8+8]
0x18000e936  mov     [r9+10h], rcx
0x18000e93a  mov     rcx, [rax+8]
0x18000e93e  mov     [r9+8], rcx
0x18000e942  mov     [r9], rax
0x18000e945  mov     [rbx], r9
0x18000e948  mov     [rcx], r9
0x18000e94b  mov     [rax+8], r9
0x18000e94f  inc     qword ptr [r11+18h]
0x18000e953  mov     r8, [r11+18h]
0x18000e957  mov     cl, [r11+20h]
0x18000e95b  movzx   eax, byte ptr [r11+21h]
0x18000e960  shr     r8, cl
0x18000e963  cmp     rax, r8
0x18000e966  jnb     short loc_18000E973
0x18000e968  lea     edx, [rcx+1]
0x18000e96b  mov     rcx, r11
0x18000e96e  call    ?_Rehash@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEAA_NE@Z; utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_Rehash(uchar)
0x18000e973  mov     rax, rbx
0x18000e976  add     rsp, 20h
0x18000e97a  pop     rbx
0x18000e97b  retn
```
