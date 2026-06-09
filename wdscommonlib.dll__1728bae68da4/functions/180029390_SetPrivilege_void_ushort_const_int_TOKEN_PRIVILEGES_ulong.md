# SetPrivilege(void *,ushort const *,int,_TOKEN_PRIVILEGES *,ulong *)

- ea: `0x180029390`
- end: `0x180029482`
- name: `?SetPrivilege@@YAKPEAXPEBGHPEAU_TOKEN_PRIVILEGES@@PEAK@Z`
- size: `242`
- prototype: `unsigned int __usercall@<eax>(HANDLE TokenHandle@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, struct _TOKEN_PRIVILEGES *@<r9>, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180029390`
- `0x180029a2c`
- `0x180030390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800293d9`
- `KERNEL32!GetLastError` at `0x180029442`
- `KERNEL32!GetLastError` at `0x1800293d9`
- `KERNEL32!GetLastError` at `0x180029442`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180029432`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180029432`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1800293c9`
- `ADVAPI32!LookupPrivilegeValueW` at `0x1800293c9`

## pseudocode

```c
__int64 __fastcall SetPrivilege(
        HANDLE TokenHandle,
        const unsigned __int16 *a2,
        int a3,
        struct _TOKEN_PRIVILEGES *a4,
        unsigned int *ReturnLength)
{
  unsigned int v7; // ebx
  DWORD v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  DWORD LastError; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // eax
  struct _LUID Luid; // [rsp+30h] [rbp-48h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-40h] BYREF

  v7 = 0;
  Luid = 0;
  if ( LookupPrivilegeValueW(0, a2, &Luid) )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = a3 != 0 ? 2 : 0;
    if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, a4, ReturnLength) )
    {
      LastError = GetLastError();
      v15 = ElValidateWin32_19(LastError, v13, v14, 88);
      if ( !v15 )
        return 31;
      return v15;
    }
  }
  else
  {
    v9 = GetLastError();
    v7 = ElValidateWin32_19(v9, v10, v11, 70);
    if ( !v7 )
      return 31;
  }
  return v7;
}

```

## disassembly

```asm
0x180029390  push    rbx
0x180029392  push    rbp
0x180029393  push    rsi
0x180029394  push    rdi
0x180029395  push    r14
0x180029397  sub     rsp, 50h
0x18002939b  mov     rax, cs:__security_cookie
0x1800293a2  xor     rax, rsp
0x1800293a5  mov     [rsp+78h+var_30], rax
0x1800293aa  mov     r14, [rsp+78h+arg_20]
0x1800293b2  mov     edi, r8d
0x1800293b5  mov     rsi, rcx
0x1800293b8  lea     r8, [rsp+78h+Luid]; lpLuid
0x1800293bd  xor     ebx, ebx
0x1800293bf  xor     ecx, ecx; lpSystemName
0x1800293c1  and     qword ptr [rsp+78h+Luid.LowPart], rbx
0x1800293c6  mov     rbp, r9
0x1800293c9  call    cs:__imp_LookupPrivilegeValueW
0x1800293d0  nop     dword ptr [rax+rax+00h]
0x1800293d5  test    eax, eax
0x1800293d7  jnz     short loc_1800293FB
0x1800293d9  call    cs:__imp_GetLastError
0x1800293e0  nop     dword ptr [rax+rax+00h]
0x1800293e5  mov     ecx, eax
0x1800293e7  lea     r9d, [rbx+46h]
0x1800293eb  call    ElValidateWin32_19
0x1800293f0  mov     ebx, eax
0x1800293f2  test    eax, eax
0x1800293f4  jnz     short loc_180029467
0x1800293f6  lea     ebx, [rax+1Fh]
0x1800293f9  jmp     short loc_180029467
0x1800293fb  mov     rax, qword ptr [rsp+78h+Luid.LowPart]
0x180029400  lea     r8, [rsp+78h+NewState]; NewState
0x180029405  mov     qword ptr [rsp+78h+NewState.Privileges.Luid.LowPart], rax
0x18002940a  neg     edi
0x18002940c  mov     [rsp+78h+ReturnLength], r14; ReturnLength
0x180029411  mov     r9d, 10h; BufferLength
0x180029417  sbb     eax, eax
0x180029419  mov     [rsp+78h+NewState.PrivilegeCount], 1
0x180029421  and     eax, 2
0x180029424  mov     [rsp+78h+PreviousState], rbp; PreviousState
0x180029429  xor     edx, edx; DisableAllPrivileges
0x18002942b  mov     [rsp+78h+NewState.Privileges.Attributes], eax
0x18002942f  mov     rcx, rsi; TokenHandle
0x180029432  call    cs:__imp_AdjustTokenPrivileges
0x180029439  nop     dword ptr [rax+rax+00h]
0x18002943e  test    eax, eax
0x180029440  jnz     short loc_180029467
0x180029442  call    cs:__imp_GetLastError
0x180029449  nop     dword ptr [rax+rax+00h]
0x18002944e  mov     ecx, eax
0x180029450  mov     r9d, 58h ; 'X'
0x180029456  call    ElValidateWin32_19
0x18002945b  mov     ebx, 1Fh
0x180029460  test    eax, eax
0x180029462  cmovz   eax, ebx
0x180029465  mov     ebx, eax
0x180029467  mov     eax, ebx
0x180029469  mov     rcx, [rsp+78h+var_30]
0x18002946e  xor     rcx, rsp; StackCookie
0x180029471  call    __security_check_cookie
0x180029476  add     rsp, 50h
0x18002947a  pop     r14
0x18002947c  pop     rdi
0x18002947d  pop     rsi
0x18002947e  pop     rbp
0x18002947f  pop     rbx
0x180029480  retn
```
