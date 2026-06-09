# utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindInsertPos(WTS_CLOUD_AUTH_HANDLE__ * const &)

- ea: `0x18000e7a4`
- end: `0x18000e8d7`
- name: `?_FindInsertPos@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEAA?AU_InsertPosResult@12@AEBQEAUWTS_CLOUD_AUTH_HANDLE__@@@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bba0`

## callees

- `0x1800066f0`
- `0x18000e72c`
- `0x18000e7a4`

## pseudocode

```c
__int64 __fastcall utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindInsertPos(
        __int64 a1,
        __int64 a2,
        unsigned __int64 *a3)
{
  unsigned __int64 v3; // r9
  char v6; // cl
  __int64 v7; // r8
  __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  __int64 v11; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // rdx
  __int128 v15; // [rsp+20h] [rbp-28h]
  unsigned __int8 v16; // [rsp+30h] [rbp-18h]

  v3 = *a3;
  v6 = *(_BYTE *)(a1 + 32);
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  v7 = *(_QWORD *)(a1 + 16);
  v8 = 8LL << v6;
  v9 = 0xC4CEB9FE1A85EC53uLL
     * ((0xFF51AFD7ED558CCDuLL * (v3 ^ (v3 >> 33))) ^ ((0xFF51AFD7ED558CCDuLL * (v3 ^ (v3 >> 33))) >> 33));
  v10 = v9 ^ (v9 >> 33);
  if ( v7 )
  {
    v12 = *(_QWORD **)(v7 + 16 * (v10 & (v8 - 1)));
    if ( v12 )
    {
      v13 = **(_QWORD ***)(v7 + 16 * (v10 & (v8 - 1)) + 8);
      while ( v12 != v13 )
      {
        if ( v12[2] >= v10 )
        {
          if ( v12[2] > v10 )
            break;
          if ( v3 == v12[3] )
          {
            *(_QWORD *)&v15 = v12;
            v16 = 2;
            goto LABEL_16;
          }
        }
        v12 = (_QWORD *)*v12;
      }
      *(_QWORD *)&v15 = v12;
    }
    else
    {
      *(_QWORD *)&v15 = 0;
    }
    v16 = 0;
LABEL_16:
    *((_QWORD *)&v15 + 1) = v10;
    *(_OWORD *)a2 = v15;
    *(_QWORD *)(a2 + 16) = v16;
  }
  else
  {
    v11 = utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_AllocBuckets(
            v9,
            v8);
    *(_QWORD *)(a1 + 16) = v11;
    if ( v11 )
    {
      utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_InitBuckets(a1);
      *(_QWORD *)(a2 + 8) = v10;
      *(_QWORD *)a2 = 0;
      *(_BYTE *)(a2 + 16) = 0;
      *(_DWORD *)(a2 + 17) = 0;
      *(_WORD *)(a2 + 21) = 0;
      *(_BYTE *)(a2 + 23) = 0;
    }
    else
    {
      *(_QWORD *)a2 = 0;
      *(_DWORD *)(a2 + 17) = 0;
      *(_WORD *)(a2 + 21) = 0;
      *(_BYTE *)(a2 + 23) = 0;
      *(_QWORD *)(a2 + 8) = v10;
      *(_BYTE *)(a2 + 16) = 1;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18000e7a4  push    rbp
0x18000e7a6  push    rbx
0x18000e7a7  push    rsi
0x18000e7a8  push    rdi
0x18000e7a9  mov     rbp, rsp
0x18000e7ac  sub     rsp, 48h
0x18000e7b0  mov     r9, [r8]
0x18000e7b3  xor     eax, eax
0x18000e7b5  mov     rsi, rcx
0x18000e7b8  mov     rbx, rdx
0x18000e7bb  mov     cl, [rcx+20h]
0x18000e7be  xorps   xmm0, xmm0
0x18000e7c1  movups  xmmword ptr [rdx], xmm0
0x18000e7c4  mov     [rdx+10h], rax
0x18000e7c8  lea     edx, [rax+8]
0x18000e7cb  mov     r8, [rsi+10h]
0x18000e7cf  mov     rax, r9
0x18000e7d2  shl     rdx, cl
0x18000e7d5  mov     rcx, 0FF51AFD7ED558CCDh
0x18000e7df  shr     rax, 21h
0x18000e7e3  xor     rax, r9
0x18000e7e6  imul    rax, rcx
0x18000e7ea  mov     rcx, rax
0x18000e7ed  shr     rcx, 21h
0x18000e7f1  xor     rcx, rax
0x18000e7f4  mov     rax, 0C4CEB9FE1A85EC53h
0x18000e7fe  imul    rcx, rax
0x18000e802  mov     rdi, rcx
0x18000e805  shr     rdi, 21h
0x18000e809  xor     rdi, rcx
0x18000e80c  test    r8, r8
0x18000e80f  jnz     short loc_18000E85F
0x18000e811  call    ?_AllocBuckets@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEAAPEAU?$_HashBucket@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@2@_K@Z; utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_AllocBuckets(unsigned __int64)
0x18000e816  mov     [rsi+10h], rax
0x18000e81a  test    rax, rax
0x18000e81d  jz      short loc_18000E846
0x18000e81f  mov     rcx, rsi
0x18000e822  call    ?_InitBuckets@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_InitBuckets(void)
0x18000e827  xor     eax, eax
0x18000e829  mov     [rbx+8], rdi
0x18000e82d  xor     cl, cl
0x18000e82f  mov     [rbx], rax
0x18000e832  xor     edx, edx
0x18000e834  mov     [rbx+10h], cl
0x18000e837  mov     [rbx+11h], edx
0x18000e83a  mov     [rbx+15h], dx
0x18000e83e  mov     [rbx+17h], dl
0x18000e841  jmp     loc_18000E8CB
0x18000e846  xor     ecx, ecx
0x18000e848  mov     [rbx], rax
0x18000e84b  mov     [rbx+11h], ecx
0x18000e84e  mov     [rbx+15h], cx
0x18000e852  mov     [rbx+17h], cl
0x18000e855  mov     [rbx+8], rdi
0x18000e859  mov     byte ptr [rbx+10h], 1
0x18000e85d  jmp     short loc_18000E8CB
0x18000e85f  lea     rax, [rdx-1]
0x18000e863  and     rax, rdi
0x18000e866  add     rax, rax
0x18000e869  mov     rcx, [r8+rax*8]
0x18000e86d  test    rcx, rcx
0x18000e870  jnz     short loc_18000E878
0x18000e872  mov     qword ptr [rbp+var_28], rcx
0x18000e876  jmp     short loc_18000E8A6
0x18000e878  mov     rax, [r8+rax*8+8]
0x18000e87d  mov     rdx, [rax]
0x18000e880  cmp     rcx, rdx
0x18000e883  jz      short loc_18000E8A2
0x18000e885  cmp     [rcx+10h], rdi
0x18000e889  jb      short loc_18000E893
0x18000e88b  ja      short loc_18000E8A2
0x18000e88d  cmp     r9, [rcx+18h]
0x18000e891  jz      short loc_18000E898
0x18000e893  mov     rcx, [rcx]
0x18000e896  jmp     short loc_18000E880
0x18000e898  mov     qword ptr [rbp+var_28], rcx
0x18000e89c  mov     [rbp+var_18], 2
0x18000e8a0  jmp     short loc_18000E8AA
0x18000e8a2  mov     qword ptr [rbp+var_28], rcx
0x18000e8a6  mov     [rbp+var_18], 0
0x18000e8aa  xor     eax, eax
0x18000e8ac  mov     qword ptr [rbp+var_28+8], rdi
0x18000e8b0  movups  xmm0, [rbp+var_28]
0x18000e8b4  mov     dword ptr [rbp+var_18+1], eax
0x18000e8b7  mov     word ptr [rbp+var_18+5], ax
0x18000e8bb  mov     [rbp+var_18+7], al
0x18000e8be  movsd   xmm1, qword ptr [rbp+var_18]
0x18000e8c3  movups  xmmword ptr [rbx], xmm0
0x18000e8c6  movsd   qword ptr [rbx+10h], xmm1
0x18000e8cb  mov     rax, rbx
0x18000e8ce  add     rsp, 48h
0x18000e8d2  pop     rdi
0x18000e8d3  pop     rsi
0x18000e8d4  pop     rbx
0x18000e8d5  pop     rbp
0x18000e8d6  retn
```
