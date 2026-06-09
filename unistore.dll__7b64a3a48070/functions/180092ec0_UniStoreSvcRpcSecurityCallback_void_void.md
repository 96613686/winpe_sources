# UniStoreSvcRpcSecurityCallback(void * *,void *)

- ea: `0x180092ec0`
- end: `0x18009303f`
- name: `?UniStoreSvcRpcSecurityCallback@@YAJPEAPEAXPEAX@Z`
- size: `383`
- prototype: `__int64 __fastcall(void **, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18006bd68`
- `0x180092e88`
- `0x180092ec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092f1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092fa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092f1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092fa9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092f2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180092f2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092f3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180092f3a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180092fa0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180092fa0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180092f10`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180092f65`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180092fed`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180092f10`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180092f65`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180092fed`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180092f76`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180092f76`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x180092ee5`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x180092ee5`

## pseudocode

```c
__int64 __fastcall UniStoreSvcRpcSecurityCallback(void **a1, void *a2)
{
  DWORD v2; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v4; // rdi
  void *v5; // rdx
  PUCHAR SidSubAuthorityCount; // rbx
  PDWORD SidSubAuthority; // rbx
  unsigned int v8; // ebx
  HANDLE TokenHandle[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+60h] [rbp+20h] BYREF
  int TokenInformation; // [rsp+68h] [rbp+28h] BYREF

  TokenHandle[0] = 0;
  if ( (int)GetRpcClientThreadToken(8u, TokenHandle) >= 0 )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle[0], TokenIntegrityLevel, 0, 0, &TokenInformationLength)
      || GetLastError() == 122 )
    {
      v2 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v4 = (PSID *)HeapAlloc(ProcessHeap, 8u, v2);
      if ( v4 )
      {
        if ( GetTokenInformation(
               TokenHandle[0],
               TokenIntegrityLevel,
               v4,
               TokenInformationLength,
               &TokenInformationLength) )
        {
          SidSubAuthorityCount = GetSidSubAuthorityCount(*v4);
          if ( !GetLastError() )
          {
            if ( SidSubAuthorityCount )
            {
              SidSubAuthority = GetSidSubAuthority(*v4, (unsigned __int8)(*SidSubAuthorityCount - 1));
              if ( !GetLastError() )
              {
                if ( SidSubAuthority )
                {
                  if ( *SidSubAuthority > 0x1000 )
                  {
                    v8 = 0;
LABEL_15:
                    wil::details::FreeProcessHeap((wil::details *)v4, v5);
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
                    return v8;
                  }
                  TokenInformation = 0;
                  TokenInformationLength = 0;
                  if ( GetTokenInformation(
                         TokenHandle[0],
                         TokenIsAppContainer,
                         &TokenInformation,
                         4u,
                         &TokenInformationLength) )
                  {
                    v8 = 5;
                    if ( TokenInformation )
                      v8 = 0;
                    goto LABEL_15;
                  }
                }
              }
            }
          }
        }
        wil::details::FreeProcessHeap((wil::details *)v4, v5);
      }
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
  return 5;
}

```

## disassembly

```asm
0x180092ec0  mov     [rsp-8+arg_0], rbx
0x180092ec5  mov     [rsp-8+arg_8], rdi
0x180092eca  push    rbp
0x180092ecb  mov     rbp, rsp
0x180092ece  sub     rsp, 40h
0x180092ed2  mov     edi, 8
0x180092ed7  mov     [rbp+TokenHandle], 0
0x180092edf  mov     ecx, edi
0x180092ee1  lea     rdx, [rbp+TokenHandle]
0x180092ee5  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x180092eeb  test    eax, eax
0x180092eed  js      loc_180093021
0x180092ef3  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180092ef7  lea     rax, [rbp+TokenInformationLength]
0x180092efb  xor     r9d, r9d; TokenInformationLength
0x180092efe  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180092f03  xor     r8d, r8d; TokenInformation
0x180092f06  mov     [rbp+TokenInformationLength], 0
0x180092f0d  lea     edx, [rdi+11h]; TokenInformationClass
0x180092f10  call    cs:__imp_GetTokenInformation
0x180092f16  test    eax, eax
0x180092f18  jnz     short loc_180092F29
0x180092f1a  call    cs:__imp_GetLastError
0x180092f20  cmp     eax, 7Ah ; 'z'
0x180092f23  jnz     loc_180093021
0x180092f29  mov     ebx, [rbp+TokenInformationLength]
0x180092f2c  call    cs:__imp_GetProcessHeap
0x180092f32  mov     r8d, ebx; dwBytes
0x180092f35  mov     edx, edi; dwFlags
0x180092f37  mov     rcx, rax; hHeap
0x180092f3a  call    cs:__imp_HeapAlloc
0x180092f40  mov     rdi, rax
0x180092f43  test    rax, rax
0x180092f46  jz      loc_180093021
0x180092f4c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180092f50  lea     rax, [rbp+TokenInformationLength]
0x180092f54  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180092f58  mov     r8, rdi; TokenInformation
0x180092f5b  mov     edx, 19h; TokenInformationClass
0x180092f60  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180092f65  call    cs:__imp_GetTokenInformation
0x180092f6b  test    eax, eax
0x180092f6d  jz      loc_180093019
0x180092f73  mov     rcx, [rdi]; pSid
0x180092f76  call    cs:__imp_GetSidSubAuthorityCount
0x180092f7c  mov     rbx, rax
0x180092f7f  call    cs:__imp_GetLastError
0x180092f85  test    eax, eax
0x180092f87  jnz     loc_180093019
0x180092f8d  test    rbx, rbx
0x180092f90  jz      loc_180093019
0x180092f96  mov     al, [rbx]
0x180092f98  mov     rcx, [rdi]; pSid
0x180092f9b  dec     al
0x180092f9d  movzx   edx, al; nSubAuthority
0x180092fa0  call    cs:__imp_GetSidSubAuthority
0x180092fa6  mov     rbx, rax
0x180092fa9  call    cs:__imp_GetLastError
0x180092faf  test    eax, eax
0x180092fb1  jnz     short loc_180093019
0x180092fb3  test    rbx, rbx
0x180092fb6  jz      short loc_180093019
0x180092fb8  cmp     dword ptr [rbx], 1000h
0x180092fbe  jbe     short loc_180092FC4
0x180092fc0  xor     ebx, ebx
0x180092fc2  jmp     short loc_180093004
0x180092fc4  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180092fc8  lea     rax, [rbp+TokenInformationLength]
0x180092fcc  mov     r9d, 4; TokenInformationLength
0x180092fd2  mov     [rbp+TokenInformation], 0
0x180092fd9  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180092fdd  mov     [rbp+TokenInformationLength], 0
0x180092fe4  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180092fe9  lea     edx, [r9+19h]; TokenInformationClass
0x180092fed  call    cs:__imp_GetTokenInformation
0x180092ff3  test    eax, eax
0x180092ff5  jz      short loc_180093019
0x180092ff7  xor     ecx, ecx
0x180092ff9  mov     ebx, 5
0x180092ffe  cmp     [rbp+TokenInformation], ecx
0x180093001  cmovnz  ebx, ecx
0x180093004  mov     rcx, rdi; this
0x180093007  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18009300c  lea     rcx, [rbp+TokenHandle]
0x180093010  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180093015  mov     eax, ebx
0x180093017  jmp     short loc_18009302F
0x180093019  mov     rcx, rdi; this
0x18009301c  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180093021  lea     rcx, [rbp+TokenHandle]
0x180093025  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009302a  mov     eax, 5
0x18009302f  mov     rbx, [rsp+40h+arg_0]
0x180093034  mov     rdi, [rsp+40h+arg_8]
0x180093039  add     rsp, 40h
0x18009303d  pop     rbp
0x18009303e  retn
```
