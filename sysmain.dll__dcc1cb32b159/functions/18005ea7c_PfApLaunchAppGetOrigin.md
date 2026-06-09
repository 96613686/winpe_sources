# PfApLaunchAppGetOrigin

- ea: `0x18005ea7c`
- end: `0x18005eb45`
- name: `PfApLaunchAppGetOrigin`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005a138`

## callees

- `0x18005ea7c`
- `0x18005eb4c`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eac4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005eb1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005eb1c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005ead3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005ead3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005eb0c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005eb0c`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackageOrigin` at `0x18005eafa`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackageOrigin` at `0x18005eafa`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18005eaba`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18005eaba`

## pseudocode

```c
__int64 __fastcall PfApLaunchAppGetOrigin(__int64 a1, __int64 a2, PackageOrigin *a3)
{
  __int64 v3; // rcx
  DWORD StagedPackageOrigin; // ebx
  PackageOrigin origin; // [rsp+20h] [rbp-128h] BYREF
  HANDLE hToken; // [rsp+28h] [rbp-120h] BYREF
  WCHAR packageFullName[128]; // [rsp+30h] [rbp-118h] BYREF

  v3 = *(unsigned int *)(a1 + 80);
  origin = PackageOrigin_Unknown;
  hToken = 0;
  if ( (unsigned int)QueryUserToken(v3, &hToken) && ImpersonateLoggedOnUser(hToken) )
  {
    StagedPackageOrigin = PfsGetPackageFullName(a2, packageFullName);
    if ( !StagedPackageOrigin )
    {
      StagedPackageOrigin = GetStagedPackageOrigin(packageFullName, &origin);
      if ( !StagedPackageOrigin )
        *a3 = origin;
    }
    RevertToSelf();
  }
  else
  {
    StagedPackageOrigin = GetLastError();
  }
  if ( hToken )
    CloseHandle(hToken);
  return StagedPackageOrigin;
}

```

## disassembly

```asm
0x18005ea7c  mov     [rsp+arg_18], rbx
0x18005ea81  push    rdi
0x18005ea82  sub     rsp, 140h
0x18005ea89  mov     rax, cs:__security_cookie
0x18005ea90  xor     rax, rsp
0x18005ea93  mov     [rsp+148h+var_18], rax
0x18005ea9b  mov     ecx, [rcx+50h]
0x18005ea9e  mov     rbx, rdx
0x18005eaa1  lea     rdx, [rsp+148h+hToken]
0x18005eaa6  mov     [rsp+148h+origin], 0
0x18005eaae  mov     rdi, r8
0x18005eab1  mov     [rsp+148h+hToken], 0
0x18005eaba  call    cs:__imp_QueryUserToken
0x18005eac0  test    eax, eax
0x18005eac2  jnz     short loc_18005EACE
0x18005eac4  call    cs:__imp_GetLastError
0x18005eaca  mov     ebx, eax
0x18005eacc  jmp     short loc_18005EB12
0x18005eace  mov     rcx, [rsp+148h+hToken]; hToken
0x18005ead3  call    cs:__imp_ImpersonateLoggedOnUser
0x18005ead9  test    eax, eax
0x18005eadb  jz      short loc_18005EAC4
0x18005eadd  lea     rdx, [rsp+148h+packageFullName]
0x18005eae2  mov     rcx, rbx
0x18005eae5  call    PfsGetPackageFullName
0x18005eaea  mov     ebx, eax
0x18005eaec  test    eax, eax
0x18005eaee  jnz     short loc_18005EB0C
0x18005eaf0  lea     rdx, [rsp+148h+origin]; origin
0x18005eaf5  lea     rcx, [rsp+148h+packageFullName]; packageFullName
0x18005eafa  call    cs:__imp_GetStagedPackageOrigin
0x18005eb00  mov     ebx, eax
0x18005eb02  test    eax, eax
0x18005eb04  jnz     short loc_18005EB0C
0x18005eb06  mov     eax, [rsp+148h+origin]
0x18005eb0a  mov     [rdi], eax
0x18005eb0c  call    cs:__imp_RevertToSelf
0x18005eb12  mov     rcx, [rsp+148h+hToken]; hObject
0x18005eb17  test    rcx, rcx
0x18005eb1a  jz      short loc_18005EB22
0x18005eb1c  call    cs:__imp_CloseHandle
0x18005eb22  mov     eax, ebx
0x18005eb24  mov     rcx, [rsp+148h+var_18]
0x18005eb2c  xor     rcx, rsp; StackCookie
0x18005eb2f  call    __security_check_cookie
0x18005eb34  mov     rbx, [rsp+148h+arg_18]
0x18005eb3c  add     rsp, 140h
0x18005eb43  pop     rdi
0x18005eb44  retn
```
