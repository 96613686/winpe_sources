# GetSoftLandingFolderForUser(void *,wchar_t *,unsigned __int64)

- ea: `0x1802bc644`
- end: `0x1802bc7eb`
- name: `?GetSoftLandingFolderForUser@@YAJPEAXPEA_W_K@Z`
- size: `423`
- prototype: `__int64 __fastcall(HANDLE hToken, LPCWSTR lpPathName, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802bc570`

## callees

- `0x180026ecc`
- `0x18007fae8`
- `0x18008bd1c`
- `0x1801594d8`
- `0x1802bc54c`
- `0x1802bc644`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802bc746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802bc746`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1802bc736`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1802bc736`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1802bc6e7`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1802bc6e7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802bc75b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802bc793`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802bc75b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802bc793`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802bc71c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802bc71c`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateFolder` at `0x1802bc6ba`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateFolder` at `0x1802bc6ba`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x1802bc682`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x1802bc682`

## pseudocode

```c
__int64 __fastcall GetSoftLandingFolderForUser(HANDLE hToken, WCHAR *lpPathName, __int64 a3)
{
  __int64 v5; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  HRESULT v8; // eax
  HRESULT v9; // edi
  unsigned int v10; // ebx
  DWORD v11; // ebx
  unsigned int LastError; // eax
  unsigned int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v16; // [rsp+40h] [rbp+18h] BYREF
  __int64 v17; // [rsp+48h] [rbp+20h] BYREF

  v16 = a3;
  if ( !(unsigned __int8)IsOpenStateExplicitPresent() || !(unsigned __int8)IsOpenStateExplicitPresent() )
    return 2147942527LL;
  v5 = OpenStateExplicit(hToken, L"Microsoft.Windows.ContentDeliveryManager_cw5n1h2txyewy");
  v17 = v5;
  if ( !v5 )
  {
    v7 = 22;
LABEL_20:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v7,
                  (unsigned int)"onecoreuap\\shell\\twinui\\softlanding\\published\\softlandingcampaign.cpp",
                  v6);
    goto LABEL_21;
  }
  v16 = 260;
  if ( !(unsigned int)GetStateFolder(v5, 1, lpPathName, &v16) )
  {
    v7 = 25;
    goto LABEL_20;
  }
  v16 = 260;
  v8 = PathCchCombine(lpPathName, 0x104u, lpPathName, L"Tips");
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\shell\\twinui\\softlanding\\published\\softlandingcampaign.cpp",
      (const char *)(unsigned int)v8,
      v14);
    v10 = v9;
    goto LABEL_22;
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    v7 = 31;
    goto LABEL_20;
  }
  if ( !CreateDirectoryW(lpPathName, 0) )
  {
    v11 = GetLastError();
    if ( v11 != 183 )
    {
      if ( !RevertToSelf() )
      {
        v7 = 38;
        goto LABEL_20;
      }
      if ( v11 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x27,
                      (unsigned int)"onecoreuap\\shell\\twinui\\softlanding\\published\\softlandingcampaign.cpp",
                      (const char *)v11,
                      v14);
LABEL_21:
        v10 = LastError;
        goto LABEL_22;
      }
      v10 = 0;
LABEL_22:
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
      return v10;
    }
  }
  if ( !RevertToSelf() )
  {
    v7 = 43;
    goto LABEL_20;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
  return 0;
}

```

## disassembly

```asm
0x1802bc644  mov     [rsp+arg_0], rbx
0x1802bc649  mov     [rsp+arg_8], rsi
0x1802bc64e  mov     [rsp+arg_10], r8
0x1802bc653  push    rdi; unsigned int
0x1802bc654  sub     rsp, 20h
0x1802bc658  mov     rbx, rdx
0x1802bc65b  mov     rsi, rcx
0x1802bc65e  call    IsOpenStateExplicitPresent
0x1802bc663  test    al, al
0x1802bc665  jz      loc_1802BC7D5
0x1802bc66b  call    IsOpenStateExplicitPresent
0x1802bc670  test    al, al
0x1802bc672  jz      loc_1802BC7D5
0x1802bc678  lea     rdx, ?c_ContentDeliveryManagerPackageFamilyName@Shared@CreativeFramework@@3QBGB; "Microsoft.Windows.ContentDeliveryManage"...
0x1802bc67f  mov     rcx, rsi
0x1802bc682  call    cs:__imp_OpenStateExplicit
0x1802bc689  nop     dword ptr [rax+rax+00h]
0x1802bc68e  mov     [rsp+28h+arg_18], rax
0x1802bc693  test    rax, rax
0x1802bc696  jnz     short loc_1802BC6A0
0x1802bc698  lea     edx, [rax+16h]
0x1802bc69b  jmp     loc_1802BC7A6
0x1802bc6a0  mov     edi, 104h
0x1802bc6a5  lea     r9, [rsp+28h+arg_10]
0x1802bc6aa  mov     r8, rbx
0x1802bc6ad  mov     [rsp+28h+arg_10], rdi
0x1802bc6b2  mov     edx, 1
0x1802bc6b7  mov     rcx, rax
0x1802bc6ba  call    cs:__imp_GetStateFolder
0x1802bc6c1  nop     dword ptr [rax+rax+00h]
0x1802bc6c6  test    eax, eax
0x1802bc6c8  jnz     short loc_1802BC6D2
0x1802bc6ca  lea     edx, [rax+19h]
0x1802bc6cd  jmp     loc_1802BC7A6
0x1802bc6d2  lea     r9, aTips; "Tips"
0x1802bc6d9  mov     [rsp+28h+arg_10], rdi
0x1802bc6de  mov     r8, rbx; pszPathIn
0x1802bc6e1  mov     rdx, rdi; cchPathOut
0x1802bc6e4  mov     rcx, rbx; pszPathOut
0x1802bc6e7  call    cs:__imp_PathCchCombine
0x1802bc6ee  nop     dword ptr [rax+rax+00h]
0x1802bc6f3  mov     edi, eax
0x1802bc6f5  test    eax, eax
0x1802bc6f7  jns     short loc_1802BC719
0x1802bc6f9  mov     rcx, [rsp+28h]; this
0x1802bc6fe  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\twinui\\softlanding"...
0x1802bc705  mov     r9d, eax; char *
0x1802bc708  mov     edx, 1Dh; void *
0x1802bc70d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802bc712  mov     ebx, edi
0x1802bc714  jmp     loc_1802BC7B9
0x1802bc719  mov     rcx, rsi; hToken
0x1802bc71c  call    cs:__imp_ImpersonateLoggedOnUser
0x1802bc723  nop     dword ptr [rax+rax+00h]
0x1802bc728  test    eax, eax
0x1802bc72a  jnz     short loc_1802BC731
0x1802bc72c  lea     edx, [rax+1Fh]
0x1802bc72f  jmp     short loc_1802BC7A6
0x1802bc731  xor     edx, edx; lpSecurityAttributes
0x1802bc733  mov     rcx, rbx; lpPathName
0x1802bc736  call    cs:__imp_CreateDirectoryW
0x1802bc73d  nop     dword ptr [rax+rax+00h]
0x1802bc742  test    eax, eax
0x1802bc744  jnz     short loc_1802BC793
0x1802bc746  call    cs:__imp_GetLastError
0x1802bc74d  nop     dword ptr [rax+rax+00h]
0x1802bc752  mov     ebx, eax
0x1802bc754  cmp     eax, 0B7h
0x1802bc759  jz      short loc_1802BC793
0x1802bc75b  call    cs:__imp_RevertToSelf
0x1802bc762  nop     dword ptr [rax+rax+00h]
0x1802bc767  test    eax, eax
0x1802bc769  jnz     short loc_1802BC770
0x1802bc76b  lea     edx, [rax+26h]
0x1802bc76e  jmp     short loc_1802BC7A6
0x1802bc770  test    ebx, ebx
0x1802bc772  jz      short loc_1802BC78F
0x1802bc774  mov     rcx, [rsp+28h]; this
0x1802bc779  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\twinui\\softlanding"...
0x1802bc780  mov     r9d, ebx; char *
0x1802bc783  mov     edx, 27h ; '''; void *
0x1802bc788  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802bc78d  jmp     short loc_1802BC7B7
0x1802bc78f  xor     ebx, ebx
0x1802bc791  jmp     short loc_1802BC7B9
0x1802bc793  call    cs:__imp_RevertToSelf
0x1802bc79a  nop     dword ptr [rax+rax+00h]
0x1802bc79f  test    eax, eax
0x1802bc7a1  jnz     short loc_1802BC7C7
0x1802bc7a3  lea     edx, [rax+2Bh]; void *
0x1802bc7a6  mov     rcx, [rsp+28h]; this
0x1802bc7ab  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\twinui\\softlanding"...
0x1802bc7b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802bc7b7  mov     ebx, eax
0x1802bc7b9  lea     rcx, [rsp+28h+arg_18]
0x1802bc7be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802bc7c3  mov     eax, ebx
0x1802bc7c5  jmp     short loc_1802BC7DA
0x1802bc7c7  lea     rcx, [rsp+28h+arg_18]
0x1802bc7cc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1802bc7d1  xor     eax, eax
0x1802bc7d3  jmp     short loc_1802BC7DA
0x1802bc7d5  mov     eax, 8007007Fh
0x1802bc7da  mov     rbx, [rsp+28h+arg_0]
0x1802bc7df  mov     rsi, [rsp+28h+arg_8]
0x1802bc7e4  add     rsp, 20h
0x1802bc7e8  pop     rdi
0x1802bc7e9  retn
```
