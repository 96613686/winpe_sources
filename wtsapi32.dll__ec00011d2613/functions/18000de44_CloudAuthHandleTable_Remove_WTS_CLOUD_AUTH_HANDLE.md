# CloudAuthHandleTable::Remove(WTS_CLOUD_AUTH_HANDLE__ *)

- ea: `0x18000de44`
- end: `0x18000df49`
- name: `?Remove@CloudAuthHandleTable@@QEAAJPEAUWTS_CLOUD_AUTH_HANDLE__@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(CloudAuthHandleTable *__hidden this, struct WTS_CLOUD_AUTH_HANDLE__ *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000ec70`

## callees

- `0x1800063c8`
- `0x18000bb00`
- `0x18000bf4c`
- `0x18000de44`
- `0x18000dfb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000de7e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000de7e`

## pseudocode

```c
__int64 __fastcall CloudAuthHandleTable::Remove(RTL_SRWLOCK *this, struct WTS_CLOUD_AUTH_HANDLE__ *a2)
{
  unsigned int v3; // ebx
  RTL_SRWLOCK *v4; // r8
  _QWORD *Ptr; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  RTL_SRWLOCK *v9; // rdx
  __int64 v10; // rcx
  PVOID v11; // rax
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct WTS_CLOUD_AUTH_HANDLE__ *v15; // [rsp+38h] [rbp+10h] BYREF
  RTL_SRWLOCK *v16; // [rsp+40h] [rbp+18h] BYREF
  char v17; // [rsp+48h] [rbp+20h] BYREF

  v15 = a2;
  if ( a2 )
  {
    AcquireSRWLockExclusive(this);
    v16 = this;
    v4 = *(RTL_SRWLOCK **)utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindFirst<utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindFirstFind,WTS_CLOUD_AUTH_HANDLE__ *>(
                            &this[1],
                            &v17,
                            &v15);
    if ( v4 == &this[1] )
    {
      v3 = -2147024894;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"clientcore\\termsrv\\wtsapi\\cloudauth.cpp",
        (const char *)0x80070002LL,
        v13);
    }
    else
    {
      Ptr = v4->Ptr;
      v6 = v4[1].Ptr;
      v7 = (8LL << LOBYTE(this[5].Ptr)) - 1;
      *v6 = v4->Ptr;
      Ptr[1] = v6;
      v8 = v7 & (__int64)v4[2].Ptr;
      v9 = (RTL_SRWLOCK *)this[3].Ptr;
      v10 = 2 * v8;
      if ( v9[v10].Ptr == v4 )
      {
        if ( v9[v10 + 1].Ptr == v4 )
        {
          v9[v10 + 1].Ptr = 0;
          v11 = 0;
        }
        else
        {
          v11 = v4->Ptr;
        }
        v9[v10].Ptr = v11;
      }
      else if ( v9[v10 + 1].Ptr == v4 )
      {
        v9[v10 + 1] = v4[1];
      }
      --this[4].Ptr;
      utl::_ContainerBase<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>::_DeleteNode<utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>(
        v10,
        v4);
      v3 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
  }
  else
  {
    v3 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"clientcore\\termsrv\\wtsapi\\cloudauth.cpp",
      (const char *)0x80070057LL,
      v13);
  }
  return v3;
}

```

## disassembly

```asm
0x18000de44  mov     [rsp+arg_0], rbx
0x18000de49  mov     [rsp+arg_8], rdx
0x18000de4e  push    rdi; int
0x18000de4f  sub     rsp, 20h
0x18000de53  mov     rdi, rcx
0x18000de56  test    rdx, rdx
0x18000de59  jnz     short loc_18000DE7E
0x18000de5b  mov     rcx, [rsp+28h]; this
0x18000de60  lea     r8, aClientcoreTerm; "clientcore\\termsrv\\wtsapi\\cloudauth."...
0x18000de67  mov     ebx, 80070057h
0x18000de6c  mov     edx, 0A4h; void *
0x18000de71  mov     r9d, ebx; char *
0x18000de74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de79  jmp     loc_18000DF3C
0x18000de7e  call    cs:__imp_AcquireSRWLockExclusive
0x18000de84  lea     rbx, [rdi+8]
0x18000de88  mov     [rsp+28h+arg_10], rdi
0x18000de8d  mov     rcx, rbx
0x18000de90  lea     r8, [rsp+28h+arg_8]
0x18000de95  lea     rdx, [rsp+28h+arg_18]
0x18000de9a  call    ??$_FindFirst@U_FindFirstFind@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@PEAUWTS_CLOUD_AUTH_HANDLE__@@@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEBA?AU_FindFirstFind@01@AEBQEAUWTS_CLOUD_AUTH_HANDLE__@@@Z; utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindFirst<utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindFirstFind,WTS_CLOUD_AUTH_HANDLE__ *>(WTS_CLOUD_AUTH_HANDLE__ * const &)
0x18000de9f  mov     r8, [rax]
0x18000dea2  cmp     r8, rbx
0x18000dea5  jnz     short loc_18000DEC7
0x18000dea7  mov     rcx, [rsp+28h]; this
0x18000deac  lea     r8, aClientcoreTerm; "clientcore\\termsrv\\wtsapi\\cloudauth."...
0x18000deb3  mov     ebx, 80070002h
0x18000deb8  mov     edx, 0A8h; void *
0x18000debd  mov     r9d, ebx; char *
0x18000dec0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dec5  jmp     short loc_18000DF32
0x18000dec7  mov     cl, [rdi+28h]
0x18000deca  mov     edx, 8
0x18000decf  mov     rax, [r8]
0x18000ded2  shl     rdx, cl
0x18000ded5  mov     rcx, [r8+8]
0x18000ded9  dec     rdx
0x18000dedc  mov     [rcx], rax
0x18000dedf  mov     [rax+8], rcx
0x18000dee3  mov     rcx, [r8+10h]
0x18000dee7  and     rcx, rdx
0x18000deea  mov     rdx, [rdi+18h]
0x18000deee  add     rcx, rcx
0x18000def1  cmp     [rdx+rcx*8], r8
0x18000def5  jnz     short loc_18000DF14
0x18000def7  cmp     [rdx+rcx*8+8], r8
0x18000defc  jnz     short loc_18000DF0B
0x18000defe  mov     qword ptr [rdx+rcx*8+8], 0
0x18000df07  xor     eax, eax
0x18000df09  jmp     short loc_18000DF0E
0x18000df0b  mov     rax, [r8]
0x18000df0e  mov     [rdx+rcx*8], rax
0x18000df12  jmp     short loc_18000DF24
0x18000df14  cmp     [rdx+rcx*8+8], r8
0x18000df19  jnz     short loc_18000DF24
0x18000df1b  mov     rax, [r8+8]
0x18000df1f  mov     [rdx+rcx*8+8], rax
0x18000df24  dec     qword ptr [rdi+20h]
0x18000df28  mov     rdx, r8
0x18000df2b  call    ??$_DeleteNode@U?$_HashNode@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@utl@@@?$_ContainerBase@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>::_DeleteNode<utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>>(utl::_HashNode<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>> *)
0x18000df30  xor     ebx, ebx
0x18000df32  lea     rcx, [rsp+28h+arg_10]
0x18000df37  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000df3c  mov     eax, ebx
0x18000df3e  mov     rbx, [rsp+28h+arg_0]
0x18000df43  add     rsp, 20h
0x18000df47  pop     rdi
0x18000df48  retn
```
