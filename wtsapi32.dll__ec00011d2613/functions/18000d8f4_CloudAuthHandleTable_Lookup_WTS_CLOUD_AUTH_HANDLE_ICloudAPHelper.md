# CloudAuthHandleTable::Lookup(WTS_CLOUD_AUTH_HANDLE__ *,ICloudAPHelper * *)

- ea: `0x18000d8f4`
- end: `0x18000d9cc`
- name: `?Lookup@CloudAuthHandleTable@@QEBAJPEAUWTS_CLOUD_AUTH_HANDLE__@@PEAPEAVICloudAPHelper@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(CloudAuthHandleTable *__hidden this, struct WTS_CLOUD_AUTH_HANDLE__ *, struct ICloudAPHelper **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c0c0`
- `0x18000c270`
- `0x18000c450`

## callees

- `0x18000bb00`
- `0x18000bf6c`
- `0x18000d8f4`
- `0x18000dfb8`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d949`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000d949`

## pseudocode

```c
__int64 __fastcall CloudAuthHandleTable::Lookup(
        RTL_SRWLOCK *this,
        struct WTS_CLOUD_AUTH_HANDLE__ *a2,
        struct ICloudAPHelper **a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  char *v7; // rbx
  _QWORD *First; // rax
  struct ICloudAPHelper *v9; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct WTS_CLOUD_AUTH_HANDLE__ *v12; // [rsp+38h] [rbp+10h] BYREF
  RTL_SRWLOCK *v13; // [rsp+40h] [rbp+18h] BYREF
  __int64 v14; // [rsp+48h] [rbp+20h] BYREF

  v12 = a2;
  if ( !a3 )
  {
    v5 = -2147467261;
    v6 = 150;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (int)"clientcore\\termsrv\\wtsapi\\cloudauth.cpp",
      (const char *)v5);
    return v5;
  }
  *a3 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 153;
    goto LABEL_3;
  }
  AcquireSRWLockShared(this);
  v13 = this;
  v7 = (char *)&this[1];
  First = utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindFirst<utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindFirstFind,WTS_CLOUD_AUTH_HANDLE__ *>(
            (__int64)v7,
            &v14,
            (__int64 *)&v12);
  if ( (char *)*First == v7 )
  {
    v5 = -2147024894;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (int)"clientcore\\termsrv\\wtsapi\\cloudauth.cpp",
      (const char *)0x80070002LL);
  }
  else
  {
    v9 = *(struct ICloudAPHelper **)(*First + 32LL);
    if ( v9 )
    {
      *a3 = v9;
      (*(void (__fastcall **)(struct ICloudAPHelper *))(*(_QWORD *)v9 + 8LL))(v9);
    }
    else
    {
      *a3 = 0;
    }
    v5 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  return v5;
}

```

## disassembly

```asm
0x18000d8f4  mov     [rsp+arg_0], rbx
0x18000d8f9  mov     [rsp+arg_8], rdx
0x18000d8fe  push    rdi; int
0x18000d8ff  sub     rsp, 20h
0x18000d903  mov     rdi, r8
0x18000d906  mov     rbx, rcx
0x18000d909  test    r8, r8
0x18000d90c  jnz     short loc_18000D931
0x18000d90e  mov     ebx, 80004003h
0x18000d913  mov     edx, 96h; void *
0x18000d918  mov     rcx, [rsp+28h]; this
0x18000d91d  lea     r8, aClientcoreTerm; "clientcore\\termsrv\\wtsapi\\cloudauth."...
0x18000d924  mov     r9d, ebx; char *
0x18000d927  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d92c  jmp     loc_18000D9BF
0x18000d931  mov     qword ptr [r8], 0
0x18000d938  test    rdx, rdx
0x18000d93b  jnz     short loc_18000D949
0x18000d93d  mov     ebx, 80070057h
0x18000d942  mov     edx, 99h
0x18000d947  jmp     short loc_18000D918
0x18000d949  call    cs:__imp_AcquireSRWLockShared
0x18000d94f  mov     [rsp+28h+arg_10], rbx
0x18000d954  lea     r8, [rsp+28h+arg_8]
0x18000d959  add     rbx, 8
0x18000d95d  lea     rdx, [rsp+28h+arg_18]
0x18000d962  mov     rcx, rbx
0x18000d965  call    ??$_FindFirst@U_FindFirstFind@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@PEAUWTS_CLOUD_AUTH_HANDLE__@@@?$_HashTable@PEAUWTS_CLOUD_AUTH_HANDLE__@@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$hash@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@U?$equal_to@PEAUWTS_CLOUD_AUTH_HANDLE__@@@3@V?$allocator@U?$pair@QEAUWTS_CLOUD_AUTH_HANDLE__@@V?$com_ptr_t@VICloudAPHelper@@Uerr_returncode_policy@wil@@@wil@@@utl@@@3@$0A@@utl@@AEBA?AU_FindFirstFind@01@AEBQEAUWTS_CLOUD_AUTH_HANDLE__@@@Z; utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindFirst<utl::_HashTable<WTS_CLOUD_AUTH_HANDLE__ *,utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>,utl::hash<WTS_CLOUD_AUTH_HANDLE__ *>,utl::equal_to<WTS_CLOUD_AUTH_HANDLE__ *>,utl::allocator<utl::pair<WTS_CLOUD_AUTH_HANDLE__ * const,wil::com_ptr_t<ICloudAPHelper,wil::err_returncode_policy>>>,0>::_FindFirstFind,WTS_CLOUD_AUTH_HANDLE__ *>(WTS_CLOUD_AUTH_HANDLE__ * const &)
0x18000d96a  mov     rcx, [rax]
0x18000d96d  cmp     rcx, rbx
0x18000d970  jnz     short loc_18000D992
0x18000d972  mov     rcx, [rsp+28h]; this
0x18000d977  lea     r8, aClientcoreTerm; "clientcore\\termsrv\\wtsapi\\cloudauth."...
0x18000d97e  mov     ebx, 80070002h
0x18000d983  mov     edx, 9Dh; void *
0x18000d988  mov     r9d, ebx; char *
0x18000d98b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d990  jmp     short loc_18000D9B5
0x18000d992  mov     rcx, [rcx+20h]
0x18000d996  test    rcx, rcx
0x18000d999  jz      short loc_18000D9AC
0x18000d99b  mov     [rdi], rcx
0x18000d99e  mov     rax, [rcx]
0x18000d9a1  mov     rax, [rax+8]
0x18000d9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9aa  jmp     short loc_18000D9B3
0x18000d9ac  mov     qword ptr [rdi], 0
0x18000d9b3  xor     ebx, ebx
0x18000d9b5  lea     rcx, [rsp+28h+arg_10]
0x18000d9ba  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000d9bf  mov     eax, ebx
0x18000d9c1  mov     rbx, [rsp+28h+arg_0]
0x18000d9c6  add     rsp, 20h
0x18000d9ca  pop     rdi
0x18000d9cb  retn
```
