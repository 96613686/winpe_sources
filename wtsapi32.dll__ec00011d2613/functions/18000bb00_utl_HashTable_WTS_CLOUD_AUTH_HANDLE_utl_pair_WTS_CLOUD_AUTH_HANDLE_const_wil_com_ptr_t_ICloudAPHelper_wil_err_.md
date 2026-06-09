# utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindFirst<utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindFirstFind,WTS_CLOUD_AUTH_HANDLE__ *>(WTS_CLOUD_AUTH_HANDLE__ * const &)

- ea: `0x18000bb00`
- end: `0x18000bb97`
- name: `??$_FindFirst@U_FindFirstFind@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@PEAUWTS_CLOUD_AUTH_HANDLE__@@@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEBA?AU_FindFirstFind@01@AEBQEAUWTS_CLOUD_AUTH_HANDLE__@@@Z`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d8f4`
- `0x18000de44`

## callees

- `0x18000bb00`

## pseudocode

```c
_QWORD *__fastcall utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindFirst<utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindFirstFind,WTS_CLOUD_AUTH_HANDLE__ *>(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  unsigned __int64 v6; // r8
  _QWORD *v7; // rcx
  _QWORD *v8; // r10

  v3 = *(_QWORD *)(a1 + 16);
  if ( v3 )
  {
    v5 = *a3;
    v6 = (0xC4CEB9FE1A85EC53uLL
        * ((0xFF51AFD7ED558CCDuLL * (*a3 ^ ((unsigned __int64)*a3 >> 33)))
         ^ ((0xFF51AFD7ED558CCDuLL * (*a3 ^ ((unsigned __int64)*a3 >> 33))) >> 33)))
       ^ ((0xC4CEB9FE1A85EC53uLL
         * ((0xFF51AFD7ED558CCDuLL * (*a3 ^ ((unsigned __int64)*a3 >> 33)))
          ^ ((0xFF51AFD7ED558CCDuLL * (*a3 ^ ((unsigned __int64)*a3 >> 33))) >> 33))) >> 33);
    v7 = *(_QWORD **)(v3 + 16 * (v6 & ((8LL << *(_BYTE *)(a1 + 32)) - 1)));
    if ( v7 )
    {
      v8 = **(_QWORD ***)(v3 + 16 * (v6 & ((8LL << *(_BYTE *)(a1 + 32)) - 1)) + 8);
      while ( v7 != v8 )
      {
        if ( v7[2] >= v6 )
        {
          if ( v7[2] > v6 )
            break;
          if ( v5 == v7[3] )
          {
            *a2 = v7;
            return a2;
          }
        }
        v7 = (_QWORD *)*v7;
      }
    }
  }
  *a2 = a1;
  return a2;
}

```

## disassembly

```asm
0x18000bb00  mov     r10, [rcx+10h]
0x18000bb04  mov     r9, rcx
0x18000bb07  test    r10, r10
0x18000bb0a  jz      loc_18000BB90
0x18000bb10  mov     r11, [r8]
0x18000bb13  mov     rcx, 0FF51AFD7ED558CCDh
0x18000bb1d  mov     rax, r11
0x18000bb20  shr     rax, 21h
0x18000bb24  xor     rax, r11
0x18000bb27  imul    rax, rcx
0x18000bb2b  mov     rcx, rax
0x18000bb2e  shr     rcx, 21h
0x18000bb32  xor     rcx, rax
0x18000bb35  mov     rax, 0C4CEB9FE1A85EC53h
0x18000bb3f  imul    rcx, rax
0x18000bb43  mov     eax, 8
0x18000bb48  mov     r8, rcx
0x18000bb4b  shr     r8, 21h
0x18000bb4f  xor     r8, rcx
0x18000bb52  mov     cl, [r9+20h]
0x18000bb56  shl     rax, cl
0x18000bb59  dec     rax
0x18000bb5c  and     rax, r8
0x18000bb5f  add     rax, rax
0x18000bb62  mov     rcx, [r10+rax*8]
0x18000bb66  test    rcx, rcx
0x18000bb69  jz      short loc_18000BB90
0x18000bb6b  mov     rax, [r10+rax*8+8]
0x18000bb70  mov     r10, [rax]
0x18000bb73  cmp     rcx, r10
0x18000bb76  jz      short loc_18000BB90
0x18000bb78  cmp     [rcx+10h], r8
0x18000bb7c  jb      short loc_18000BB86
0x18000bb7e  ja      short loc_18000BB90
0x18000bb80  cmp     r11, [rcx+18h]
0x18000bb84  jz      short loc_18000BB8B
0x18000bb86  mov     rcx, [rcx]
0x18000bb89  jmp     short loc_18000BB73
0x18000bb8b  mov     [rdx], rcx
0x18000bb8e  jmp     short loc_18000BB93
0x18000bb90  mov     [rdx], r9
0x18000bb93  mov     rax, rdx
0x18000bb96  retn
```
