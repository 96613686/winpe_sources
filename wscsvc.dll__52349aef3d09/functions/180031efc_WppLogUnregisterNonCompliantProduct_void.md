# WppLogUnregisterNonCompliantProduct(void *)

- ea: `0x180031efc`
- end: `0x180031fd4`
- name: `?WppLogUnregisterNonCompliantProduct@@YAJPEAX@Z`
- size: `216`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024630`
- `0x180024b40`
- `0x180025520`
- `0x180026450`
- `0x1800337d0`

## callees

- `0x180008e48`
- `0x18001abb0`
- `0x18001bb90`
- `0x18001fb24`
- `0x180029158`
- `0x180030ee8`
- `0x180031050`
- `0x180031efc`

## pseudocode

```c
__int64 __fastcall WppLogUnregisterNonCompliantProduct(void *a1)
{
  int CallerProcessPath; // ebx
  __int64 v3; // r8
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF
  char v6; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int16 *v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  CRpcImpersonateClient::CRpcImpersonateClient((CRpcImpersonateClient *)&v6, a1);
  CallerProcessPath = CSecurityVerificationManager::GetCallerProcessPath(a1, &v7);
  CRpcImpersonateClient::~CRpcImpersonateClient((CRpcImpersonateClient *)&v6);
  if ( CallerProcessPath >= 0 )
  {
    v3 = -1;
    do
      ++v3;
    while ( v7[v3] );
    wil::unique_any_array_ptr<unsigned short,ArrayDeleterFunctor<unsigned short>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<unsigned short,ArrayDeleterFunctor<unsigned short>,wil::empty_deleter,unsigned __int64>(
      v5,
      (__int64)v7,
      v3);
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v5[0]);
    }
    wil::unique_any_array_ptr<unsigned short,ArrayDeleterFunctor<unsigned short>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<unsigned short,ArrayDeleterFunctor<unsigned short>,wil::empty_deleter,unsigned __int64>((__int64)v5);
  }
  else if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      192,
      WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids,
      (unsigned int)CallerProcessPath);
  }
  return (unsigned int)CallerProcessPath;
}

```

## disassembly

```asm
0x180031efc  mov     [rsp+arg_0], rbx
0x180031f01  push    rdi
0x180031f02  sub     rsp, 30h
0x180031f06  mov     rbx, rcx
0x180031f09  mov     rdx, rcx; void *
0x180031f0c  xor     edi, edi
0x180031f0e  lea     rcx, [rsp+38h+arg_8]; this
0x180031f13  mov     [rsp+38h+arg_10], rdi
0x180031f18  call    ??0CRpcImpersonateClient@@QEAA@PEAX@Z; CRpcImpersonateClient::CRpcImpersonateClient(void *)
0x180031f1d  lea     rdx, [rsp+38h+arg_10]; unsigned __int16 **
0x180031f22  mov     rcx, rbx; void *
0x180031f25  call    ?GetCallerProcessPath@CSecurityVerificationManager@@SAJPEAXPEAPEAG@Z; CSecurityVerificationManager::GetCallerProcessPath(void *,ushort * *)
0x180031f2a  lea     rcx, [rsp+38h+arg_8]; this
0x180031f2f  mov     ebx, eax
0x180031f31  call    ??1CRpcImpersonateClient@@QEAA@XZ; CRpcImpersonateClient::~CRpcImpersonateClient(void)
0x180031f36  test    ebx, ebx
0x180031f38  jns     short loc_180031F6D
0x180031f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f41  lea     rax, WPP_GLOBAL_Control
0x180031f48  cmp     rcx, rax
0x180031f4b  jz      short loc_180031FC7
0x180031f4d  test    byte ptr [rcx+1Ch], 1
0x180031f51  jz      short loc_180031FC7
0x180031f53  mov     rcx, [rcx+10h]
0x180031f57  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180031f5e  mov     edx, 0C0h
0x180031f63  mov     r9d, ebx
0x180031f66  call    WPP_SF_d
0x180031f6b  jmp     short loc_180031FC7
0x180031f6d  mov     rdx, [rsp+38h+arg_10]
0x180031f72  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031f76  inc     r8
0x180031f79  cmp     [rdx+r8*2], di
0x180031f7e  jnz     short loc_180031F76
0x180031f80  lea     rcx, [rsp+38h+var_18]
0x180031f85  call    ??0?$unique_any_array_ptr@GU?$ArrayDeleterFunctor@G@@Uempty_deleter@wil@@_K@wil@@QEAA@PEAG_K@Z; wil::unique_any_array_ptr<ushort,ArrayDeleterFunctor<ushort>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<ushort,ArrayDeleterFunctor<ushort>,wil::empty_deleter,unsigned __int64>(ushort *,unsigned __int64)
0x180031f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f91  lea     rax, WPP_GLOBAL_Control
0x180031f98  cmp     rcx, rax
0x180031f9b  jz      short loc_180031FBD
0x180031f9d  test    byte ptr [rcx+1Ch], 4
0x180031fa1  jz      short loc_180031FBD
0x180031fa3  mov     r9, [rsp+38h+var_18]
0x180031fa8  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180031faf  mov     rcx, [rcx+10h]
0x180031fb3  mov     edx, 0C1h
0x180031fb8  call    WPP_SF_S
0x180031fbd  lea     rcx, [rsp+38h+var_18]
0x180031fc2  call    ??1?$unique_any_array_ptr@GU?$ArrayDeleterFunctor@G@@Uempty_deleter@wil@@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<ushort,ArrayDeleterFunctor<ushort>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<ushort,ArrayDeleterFunctor<ushort>,wil::empty_deleter,unsigned __int64>(void)
0x180031fc7  mov     eax, ebx
0x180031fc9  mov     rbx, [rsp+38h+arg_0]
0x180031fce  add     rsp, 30h
0x180031fd2  pop     rdi
0x180031fd3  retn
```
