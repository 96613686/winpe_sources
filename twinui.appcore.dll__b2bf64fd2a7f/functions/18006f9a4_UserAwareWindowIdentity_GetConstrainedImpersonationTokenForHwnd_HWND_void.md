# UserAwareWindowIdentity::GetConstrainedImpersonationTokenForHwnd(HWND__ *,void * *)

- ea: `0x18006f9a4`
- end: `0x18006fb1e`
- name: `?GetConstrainedImpersonationTokenForHwnd@UserAwareWindowIdentity@@YAJPEAUHWND__@@PEAPEAX@Z`
- size: `378`
- prototype: `__int64 __fastcall(HWND hWnd, HWND, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18006fbbc`

## callees

- `0x180019534`
- `0x180019b14`
- `0x18001cc38`
- `0x18001e340`
- `0x18002d43c`
- `0x18006f9a4`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18006f9fc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18006f9fc`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18006faa3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18006faa3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18006fa38`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18006fa38`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006fa5b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006fa5b`

## pseudocode

```c
__int64 __fastcall UserAwareWindowIdentity::GetConstrainedImpersonationTokenForHwnd(HWND hWnd, _QWORD *a2, void **a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  const char *v13; // r9
  int v15; // eax
  __int64 v16; // rdx
  int ConstrainedUserToken; // eax
  __int64 v18; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  DWORD dwProcessId; // [rsp+58h] [rbp+28h] BYREF
  __int64 v21; // [rsp+60h] [rbp+30h] BYREF
  __int64 v22; // [rsp+68h] [rbp+38h] BYREF

  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 72;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\private\\base\\inc\\userawarewindowidentity.h",
      (const char *)v5,
      v18);
    return v5;
  }
  if ( !(unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent(hWnd, a2, a3)
    || !(unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent(v8, v7, v9)
    || !(unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent(v11, v10, v12) )
  {
    v5 = -2147467263;
    v6 = 73;
    goto LABEL_18;
  }
  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(hWnd, &dwProcessId) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x4C,
             (unsigned int)"onecoreuap\\private\\base\\inc\\userawarewindowidentity.h",
             v13);
  v22 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v22,
    0);
  v15 = UMgrOpenProcessTokenForQuery(dwProcessId, &v22);
  v5 = v15;
  if ( v15 >= 0 )
  {
    v18 = 0;
    v15 = UMgrQueryUserContext(v22, &v18);
    v5 = v15;
    if ( v15 >= 0 )
    {
      v21 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v21,
        0);
      ConstrainedUserToken = UMgrGetConstrainedUserToken(v22, v18, 0, &v21);
      v5 = ConstrainedUserToken;
      if ( ConstrainedUserToken >= 0 )
      {
        *a2 = v21;
        v21 = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
        v5 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x55,
          (unsigned int)"onecoreuap\\private\\base\\inc\\userawarewindowidentity.h",
          (const char *)(unsigned int)ConstrainedUserToken,
          v18);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
      }
      goto LABEL_16;
    }
    v16 = 82;
  }
  else
  {
    v16 = 79;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecoreuap\\private\\base\\inc\\userawarewindowidentity.h",
    (const char *)(unsigned int)v15,
    v18);
LABEL_16:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v22);
  return v5;
}

```

## disassembly

```asm
0x18006f9a4  push    rbp
0x18006f9a6  push    rbx
0x18006f9a7  push    rdi
0x18006f9a8  mov     rbp, rsp
0x18006f9ab  sub     rsp, 30h
0x18006f9af  mov     rdi, rdx
0x18006f9b2  mov     rbx, rcx
0x18006f9b5  test    rdx, rdx
0x18006f9b8  jnz     short loc_18006F9C7
0x18006f9ba  mov     ebx, 80070057h
0x18006f9bf  lea     edx, [rdi+48h]
0x18006f9c2  jmp     loc_18006FB01
0x18006f9c7  call    IsUMgrOpenProcessHandleForAccessPresent
0x18006f9cc  test    al, al
0x18006f9ce  jz      loc_18006FAF7
0x18006f9d4  call    IsUMgrOpenProcessHandleForAccessPresent
0x18006f9d9  test    al, al
0x18006f9db  jz      loc_18006FAF7
0x18006f9e1  call    IsUMgrOpenProcessHandleForAccessPresent
0x18006f9e6  test    al, al
0x18006f9e8  jz      loc_18006FAF7
0x18006f9ee  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18006f9f2  mov     [rbp+dwProcessId], 0
0x18006f9f9  mov     rcx, rbx; hWnd
0x18006f9fc  call    cs:__imp_GetWindowThreadProcessId
0x18006fa02  test    eax, eax
0x18006fa04  jnz     short loc_18006FA1E
0x18006fa06  mov     rcx, [rbp+18h]; this
0x18006fa0a  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\base\\inc\\userawa"...
0x18006fa11  lea     edx, [rax+4Ch]; void *
0x18006fa14  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006fa19  jmp     loc_18006FB16
0x18006fa1e  xor     edx, edx
0x18006fa20  mov     [rbp+arg_18], 0
0x18006fa28  lea     rcx, [rbp+arg_18]
0x18006fa2c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006fa31  mov     ecx, [rbp+dwProcessId]
0x18006fa34  lea     rdx, [rbp+arg_18]
0x18006fa38  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x18006fa3e  mov     ebx, eax
0x18006fa40  test    eax, eax
0x18006fa42  jns     short loc_18006FA4B
0x18006fa44  mov     edx, 4Fh ; 'O'
0x18006fa49  jmp     short loc_18006FA6C
0x18006fa4b  mov     rcx, [rbp+arg_18]
0x18006fa4f  lea     rdx, [rbp+var_10]
0x18006fa53  mov     [rbp+var_10], 0
0x18006fa5b  call    cs:__imp_UMgrQueryUserContext
0x18006fa61  mov     ebx, eax
0x18006fa63  test    eax, eax
0x18006fa65  jns     short loc_18006FA81
0x18006fa67  mov     edx, 52h ; 'R'; void *
0x18006fa6c  mov     rcx, [rbp+18h]; this
0x18006fa70  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\base\\inc\\userawa"...
0x18006fa77  mov     r9d, eax; char *
0x18006fa7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fa7f  jmp     short loc_18006FAEC
0x18006fa81  xor     edx, edx
0x18006fa83  mov     [rbp+arg_10], 0
0x18006fa8b  lea     rcx, [rbp+arg_10]
0x18006fa8f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006fa94  mov     rdx, [rbp+var_10]
0x18006fa98  lea     r9, [rbp+arg_10]
0x18006fa9c  mov     rcx, [rbp+arg_18]
0x18006faa0  xor     r8d, r8d
0x18006faa3  call    cs:__imp_UMgrGetConstrainedUserToken
0x18006faa9  mov     ebx, eax
0x18006faab  test    eax, eax
0x18006faad  jns     short loc_18006FAD2
0x18006faaf  mov     rcx, [rbp+18h]; this
0x18006fab3  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\base\\inc\\userawa"...
0x18006faba  mov     r9d, eax; char *
0x18006fabd  mov     edx, 55h ; 'U'; void *
0x18006fac2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fac7  lea     rcx, [rbp+arg_10]
0x18006facb  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006fad0  jmp     short loc_18006FAEC
0x18006fad2  mov     rax, [rbp+arg_10]
0x18006fad6  lea     rcx, [rbp+arg_10]
0x18006fada  mov     [rdi], rax
0x18006fadd  mov     [rbp+arg_10], 0
0x18006fae5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006faea  xor     ebx, ebx
0x18006faec  lea     rcx, [rbp+arg_18]
0x18006faf0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006faf5  jmp     short loc_18006FB14
0x18006faf7  mov     ebx, 80004001h
0x18006fafc  mov     edx, 49h ; 'I'; void *
0x18006fb01  mov     rcx, [rbp+18h]; this
0x18006fb05  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\base\\inc\\userawa"...
0x18006fb0c  mov     r9d, ebx; char *
0x18006fb0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fb14  mov     eax, ebx
0x18006fb16  add     rsp, 30h
0x18006fb1a  pop     rdi
0x18006fb1b  pop     rbx
0x18006fb1c  pop     rbp
0x18006fb1d  retn
```
